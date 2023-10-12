<script>
    let data = null;
  
    const fetchData = async () => {
      try {
        const response = await fetch('https://api.recruitly.io/api/dashboard/ats/data/placementmonthlymetrics?start=01%2F01%2F2023&end=11%2F10%2F2023&apiKey=TEST45684CB2A93F41FC40869DC739BD4D126D77');
        if (response.ok) {
          data = await response.json();
          console.log(data);
        } else {
          console.error('Failed to fetch data from the API');
        }
      } catch (error) {
        console.error('An error occurred:', error);
      }
    };
  </script>
  
  <main>
    <h1>Svelte API Demo</h1>
    <button on:click={fetchData}>Fetch Data</button>
    <pre>{JSON.stringify(data, null, 2)}</pre>
  </main>
  