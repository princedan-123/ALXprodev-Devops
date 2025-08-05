
**File**: `data_extraction_automation-0x01`

---

### 2. Batch Pokémon Data Retrieval ✅
- Loops through a Pokémon list:  
`[Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon]`
- Retrieves data from API.
- Saves to `pokemon_data/<name>.json`.
- Adds delay to handle rate limits.

**File**: `batchProcessing-0x02`

---

### 3. Summarize Pokémon Data ✅
- Reads JSON files from Task 2.
- Extracts name, height, weight.
- Generates a CSV file: `pokemon_report.csv`
- Calculates average height and weight using `awk`.

**File**: `summaryData-0x03`

---

### 4. Error Handling and Retry Logic ✅
- Adds retry mechanism (up to 3 attempts per Pokémon).
- Logs failed attempts and moves on gracefully.

**File**: `batchProcessing-0x02` (updated)

---

### 5. Parallel Data Fetching ✅
- Fetches Pokémon data **in parallel** using background jobs.
- Ensures all background processes complete before script ends.

**File**: `batchProcessing-0x04`

---

## 🧪 Manual Review

When all tasks are completed, submit your project for **manual QA review**.

---

## 🛠 Tools & Commands Used

- `curl` – to make HTTP API requests
- `jq` – to parse and extract data from JSON
- `awk`, `sed` – for formatting and summarizing data
- `sleep` – to handle API rate limits
- Background processes (`&`), `wait` – for parallel execution
- Conditional statements and retry loops for error handling

---

## 📌 Sample Output

```bash
Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.
CSV Report generated at: pokemon_report.csv

Name,Height (m),Weight (kg)
Bulbasaur,0.7,6.9
Ivysaur,1.0,13.0
...
Average Height: 1.08 m
Average Weight: 29.48 kg
