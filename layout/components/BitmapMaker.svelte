<script>
  import Led from "./Led.svelte";
  import Palette from "./Palette.svelte";
  import LedMatrix from "./LedMatrix.svelte";
  import MatrixList from "./MatrixList.svelte";
  let matrix = [
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0]
  ];
  let list = [];
  let intensity = 6;
  const toggle = () => {
    console.log("TOGGLED");
  };
  const newIntensity = event => {
    intensity = event.detail.intensity;
    console.log("NEW INTENSITY", intensity);
  };
  const changeLED = event => {
    let i = event.detail.row;
    let j = event.detail.col;
    matrix[i][j] = intensity;
  };
  const setAllIntensities = () => {
    for (let row = 0; row < 7; row++) {
      for (let col = 0; col < 5; col++) {
        matrix[row][col] = intensity;
      }
    }
  };
  const saveImage = () => {
    console.log(list);
    list.push({ matrix: matrix, selected: true, name: "Image" + list.length });
    list = list; // reactivity
  };
</script>

<style>
  /* your styles go here */
</style>

<h1>Bitmap Maker COMPONENT</h1>
<p>
  Bitmap Maker is a tool for BBC's micro:bit microcomputer board. Bitmap images
  and animations can quickly be made and modified using the graphical interface.
  Once you are happy with your crations, the code can be copied and paste into
  your code editor
</p>

<Palette {intensity} on:newIntensity={newIntensity} />
<p>Edit Matrix</p>
<LedMatrix {matrix} on:selectLED={changeLED} />

<button class="button" on:click={setAllIntensities}>Set All LEDs</button>

<MatrixList />
<button class="button" on:click={saveImage}>Save Image</button>
<button class="button">Play Animation</button>
