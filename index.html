<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Jogo da Velha Online</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; background: #222; color: white; }
    h1 { color: #ffcc00; }
    #board { display: grid; grid-template-columns: repeat(3, 100px); gap: 5px; margin: 20px auto; }
    .cell {
      width: 100px; height: 100px; font-size: 2em; background: #333;
      display: flex; align-items: center; justify-content: center; cursor: pointer;
      border-radius: 8px;
    }
    .cell:hover { background: #444; }
    input, button { padding: 8px; margin: 5px; }
  </style>
</head>
<body>
  <h1>Jogo da Velha Online</h1>
  <div>
    <input type="text" id="room" placeholder="Nome da sala">
    <button onclick="joinRoom()">Entrar na Sala</button>
  </div>
  <h2 id="status">Digite um nome de sala para começar</h2>
  <div id="board"></div>

  <!-- Firebase SDK -->
  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-database.js"></script>

  <script>
    // Suas credenciais do Firebase
    const firebaseConfig = {
      apiKey: "AIzaSyBdpi76-rKqI4slxyMPmtf6iyIn89DTunQ",
      authDomain: "project-game-online.firebaseapp.com",
      databaseURL: "https://project-game-online-default-rtdb.firebaseio.com",
      projectId: "project-game-online",
      storageBucket: "project-game-online.firebasestorage.app",
      messagingSenderId: "1080384334408",
      appId: "1:1080384334408:web:a851bdbcce0cb03d0e467d",
      measurementId: "G-NWNWY1W9NZ"
    };

    firebase.initializeApp(firebaseConfig);
    const db = firebase.database();

    let roomName = "";
    let playerSymbol = "";
    let myTurn = false;

    const boardEl = document.getElementById("board");
    const statusEl = document.getElementById("status");

    // Criar o tabuleiro
    function createBoard() {
      boardEl.innerHTML = "";
      for (let i = 0; i < 9; i++) {
        const cell = document.createElement("div");
        cell.className = "cell";
        cell.dataset.index = i;
        cell.addEventListener("click", () => makeMove(i));
        boardEl.appendChild(cell);
      }
    }
    createBoard();

    function joinRoom() {
      roomName = document.getElementById("room").value.trim();
      if (!roomName) return alert("Digite o nome da sala!");

      const roomRef = db.ref("rooms/" + roomName);

      roomRef.once("value").then(snapshot => {
        const roomData = snapshot.val();
        if (!roomData) {
          playerSymbol = "X";
          myTurn = true;
          roomRef.set({
            board: Array(9).fill(""),
            turn: "X"
          });
          statusEl.innerText = "Você é X. Sua vez!";
        } else {
          playerSymbol = "O";
          myTurn = false;
          statusEl.innerText = "Você é O. Vez do adversário!";
        }
      });

      db.ref("rooms/" + roomName).on("value", snapshot => {
        const data = snapshot.val();
        if (!data) return;
        updateBoard(data.board);
        if (data.turn === playerSymbol) {
          myTurn = true;
          statusEl.innerText = "Sua vez!";
        } else {
          myTurn = false;
          statusEl.innerText = "Vez do adversário!";
        }
        checkWinner(data.board);
      });
    }

    function makeMove(index) {
      if (!myTurn) return;
      const roomRef = db.ref("rooms/" + roomName);

      roomRef.once("value").then(snapshot => {
        const data = snapshot.val();
        if (!data.board[index]) {
          data.board[index] = playerSymbol;
          data.turn = playerSymbol === "X" ? "O" : "X";
          roomRef.set(data);
        }
      });
    }

    function updateBoard(board) {
      document.querySelectorAll(".cell").forEach((cell, i) => {
        cell.innerText = board[i];
      });
    }

    function checkWinner(board) {
      const wins = [
        [0,1,2],[3,4,5],[6,7,8],
        [0,3,6],[1,4,7],[2,5,8],
        [0,4,8],[2,4,6]
      ];
      for (let combo of wins) {
        const [a,b,c] = combo;
        if (board[a] && board[a] === board[b] && board[a] === board[c]) {
          statusEl.innerText = board[a] + " venceu!";
          myTurn = false;
        }
      }
    }
  </script>
</body>
</html>
