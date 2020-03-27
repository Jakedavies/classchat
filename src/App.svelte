<script>
  import Message from "./Message.svelte";
  export let name;

  let rooms = [{ name: "Math 11" }, { name: "Chem 11" }];
  let teachers = [{ name: "Mr. Jeffries" }, { name: "Mr. D" }];
  let messages = [
    { body: "text1", from: "Mr.D", createdAt: "11:32" },
    { body: "Lorem ipsum 1", from: "Mrs. Jeffries", createdAt: "11:33" },
    { body: "Hello number 2", from: "Student 1", createdAt: "11:55" },
    { body: "Hello number 3", from: "Student 2", createdAt: "13:45" }
  ];
</script>

<style>
  main {
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    text-align: left;
    margin-top: 0;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }

  li span {
    font-weight: bold;
  }

  ul {
    padding-left: 0;
    list-style: none;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .container {
    display: flex;
  }
  .highlight-text {
    color: #ff3e00;
  }

  .left-pane {
    width: 13em;
  }

  .main-chat {
    flex: 1;
  }

  li > a {
    color: #303030;
  }

  .main-chat h3 {
    text-align: center;
  }

  .left-pane > h4 {
    text-transform: uppercase;
    font-weight: 300;
  }

  textarea {
    width: 100%;
    resize: none;
  }
</style>

<main>
  <h1 class="highlight-text">Lunchroom.io</h1>
  <div class="container">
    <div class="left-pane">
      <h4>Classes</h4>
      <ul>
        {#each rooms as room}
          <li>
            <a href="">
              <span class="highlight-text">#</span>
              {room.name}
            </a>
          </li>
        {/each}
      </ul>

      <h4>Teachers</h4>
      <ul>
        {#each teachers as teacher}
          <li>
            <a href="">
              <span class="highlight-text">#</span>
              {teacher.name}
            </a>
          </li>
        {/each}
      </ul>
    </div>
    <div class="main-chat">
      <h3>Chem 11</h3>
      <div>
        {#each messages as message}
          <Message
            from={message.from}
            createdAt={message.createdAt}
            message={message.body} />
        {/each}
        <textarea rows="1" placeholder="Send Message" />
      </div>
    </div>
  </div>
</main>
