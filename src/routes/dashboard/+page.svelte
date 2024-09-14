<script>
    let isOpen = true;
  
    function toggleSidebar() {
      isOpen = !isOpen;
    }
    let transactions = [
          { 
            id:1,
            amount: '350,00€',
            description: 'sam.',
            method: 'Card',
            date: '20.3.2021'
          },
          {
            id:2,
            amount: '29,90€',
            description: 'adipiscing.',
            method: 'Card',
            date: '19.3.2021'
          },
          {
            id:3,
            amount: '50,00€',
            description: 'heppi',
            method: 'Card',
            date: '18.3.2021'
          },
          {
            id:4,
            amount: '290,00€',
            description: 'jihhhjkbjbb',
            method: 'Card',
            date: '17.3.2021'
          },
          {
            id:5,
            amount: '49,90€',
            description: 'delhi',
            method: 'Card',
            date: '16.3.2021'
          },
          {
            id:6,
            amount: '25,00€',
            description: 'happyui',
            method: 'Card',
            date: '15.3.2021'
          },
          {
            id:7,
            amount: '290,00€',
            description: 'Suspendisse blandit sodales eros, quis aliquet leo aliquet ultrices lorem ipsum dolor sit amet consectetuer adipiscing.',
            method: 'Card',
            date: '17.3.2021'
          },
          {
            id:8,
            amount: '49,90€',
            description: 'Suspendisse blandit sodales eros, quis aliquet leo aliquet ultrices lorem ipsum dolor sit amet consectetuer adipiscing.',
            method: 'Card',
            date: '16.3.2021'
          },
          {
            id:9,
            amount: '25,00€',
            description: 'quis aliquet leo aliquet ultrices lorem ipsum dolor sit amet consectetuer adipiscing.',
            method: 'Card',
            date: '15.3.2021'
          }
        ];
      
       
        let inputValue = '';

// Computed property to filter transactions based on input value
$: filteredTransactions = transactions.filter(transaction =>
  transaction.amount.toLowerCase().includes(inputValue.toLowerCase()) ||
  transaction.description.toLowerCase().includes(inputValue.toLowerCase()) ||
  transaction.method.toLowerCase().includes(inputValue.toLowerCase()) ||
  transaction.date.toLowerCase().includes(inputValue.toLowerCase())
);

function handleButtonClick(transaction) {
  alert(`You clicked on the transaction of ${transaction.amount}`);
}
  

  </script>
  
  <style>
    /* Same styles as above */
    .container {
      display: flex;
      height: 100vh;
    }
  
    .sidebar {
      width: 250px;
      background-color: #2e3440;
      color: white;
      transition: width 0.3s ease;
      overflow-x: hidden;
      display: flex;
      flex-direction: column;
      padding: 15px;
    }
  
    .collapsed {
      width: 70px;
    }
  
    .sidebar a {
      padding: 15px;
      text-decoration: none;
      color: white;
      display: flex;
      align-items: center;
      transition: background-color 0.3s;
    }
  
    .sidebar a:hover {
      background-color: #4c566a;
    }
  
    .main-content {
      flex-grow: 1;
      padding: 20px;
      background-color: #eceff4;
    }
  
    .toggle-btn {
      padding: 10px;
      background-color: #5e81ac;
      color: white;
      border: none;
      cursor: pointer;
    }
  
    .toggle-btn:hover {
      background-color: #81a1c1;
    }
  
    .sidebar-icon {
      margin-right: 10px;
      display: inline-block;
    }
  
    .collapsed .sidebar-icon {
      margin-right: 0;
    }
  
    .collapsed .text {
      display: none;
    }
    
    .table-container {
    max-height: 400px; /* Adjust as needed */
    overflow-y: auto;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
        
        table {
          width: 100%;
          border-collapse: collapse;
        }
      
        th, td {
          padding: 12px;
          text-align: left;
          border-bottom: 1px solid #ddd;
        }
      
        th.n-table-align-right,
        td.n-table-align-right {
          text-align: right;
        }
      
        td.n-table-ellipsis {
          white-space: nowrap;
          overflow: hidden;
          text-overflow: ellipsis;
          max-width: 250px; /* Adjust as needed */
        }
      
        th {
          background-color: #2e3440;
          color: white;
        }
      
        tbody tr:hover {
          background-color: #f1f1f1;
        }
      
        button {
          padding: 8px 12px;
          background-color: #007bff;
          color: white;
          border: none;
          cursor: pointer;
          border-radius: 4px;
        }
      
        button:hover {
          background-color: #0056b3;
        }
      
        .input-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 1em;
}

.input-container label {
  margin-bottom: 0.5em;
  font-weight: bold;
}

.input-container input {
  padding: 0.8em;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1em;
  box-sizing: border-box;
}

.input-container input:focus {
  border-color: #007bff;
  outline: none;
}

      
  </style>
  
  <div class="container">
    <!-- Sidebar with optional icon-based collapsed mode -->
    <div class="sidebar {isOpen ? '' : 'collapsed'}">
      <button class="toggle-btn" on:click={toggleSidebar}>
        
      </button>
      <a href="#services">
        <span class="sidebar-icon">💼</span>
        <span class="text">Shipments</span>
      </a>
      <a href="#about">
        <span class="sidebar-icon">ℹ️</span>
        <span class="text">Unit</span>
      </a>
      <a href="#contact">
        <span class="sidebar-icon">📞</span>
        <span class="text">Logout</span>
      </a>
    </div>
  
    <!-- Main Content -->
    <div class="main-content">
      <h1 style="background-color: #81a1c1;">
        Hack ' N ' Seek
      </h1>
      <div class="input-container">
        <input
          id="formal-input"
          type="text"
          bind:value={inputValue}
          placeholder="Enter your text here"
        />
      </div>
      
      <div class="table-container">
        <table>
          <thead>
            <tr style="position: -webkit-sticky; position: sticky; top: 0; background-color: #2e3440; color: white; z-index: 1;">
              <th style="text-align: right;">Amount</th>
              <th>Description</th>
              <th>Method</th>
              <th style="text-align: right;">Date</th>
              <th>Action</th>
            </tr>
          </thead>
          <tbody>
            {#each filteredTransactions as transaction}
              <tr>
                <td class="n-table-align-right">{transaction.amount}</td>
                <td class="n-table-ellipsis">{transaction.description}</td>
                <td>{transaction.method}</td>
                <td class="n-table-align-right">{transaction.date}</td>
                <td>
                  <button on:click={() => handleButtonClick(transaction)}>
                    <a href={transaction.id}>View</a>
                  </button>
                </td>
              </tr>
            {/each}
          </tbody>
        </table>
      </div>
      
      
      
      
    </div>
  </div>
  