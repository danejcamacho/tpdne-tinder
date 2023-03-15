<script>
    let users = [
      { name: "John", age: 25, imgSrc: "/favicon.png"},
      { name: "Sarah", age: 30, imgSrc: "/person1.jpg" },
      { name: "Mike", age: 27, imgSrc: "/person2.jpg" },
      { name: "Emily", age: 22, imgSrc: "/person3.jpg"  }
    ];
    let current = 0;
    let liked = [];
    let disliked = [];
    
    function handleLike() {
      liked.push(users[current]);
      current++;
    }
    
    function handleDislike() {
      disliked.push(users[current]);
      current++;
    }
  </script>
  
  <div class="card-container">
    {#if current < users.length}
      <div class="card">
        <img src={users[current].imgSrc} alt="person's face" width="70%" height="70%">
        <h3>{users[current].name}, {users[current].age}</h3>
        <div class="buttons">
          <button on:click={handleDislike}>No</button>
          <button on:click={handleLike}>Yes</button>
        </div>
      </div>
    {:else}
      <p></p>
    {/if}
  </div>
  
  <style>
    .card-container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    
    .card {
      background-color: white;
      border-radius: 10px;
      box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.1);
      padding: 20px;
      text-align: center;
      width: 300px;
      font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    
    .buttons {
      display: flex;
      justify-content: center;
      margin-top: 20px;
    }
    
    button {
      background-color: white;
      border: none;
      border-radius: 5px;
      box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.1);
      color: #333;
      cursor: pointer;
      font-size: 16px;
      margin: 0 10px;
      padding: 10px 20px;
    }
    
    button:hover {
      background-color: #f5f5f5;
    }
    
    p {
      font-size: 20px;
      text-align: center;

    }
  </style>
  
