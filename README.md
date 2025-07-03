### 🏥 Hospital Queue Simulation

This is a Java-based simulation project that models how patients are handled in a hospital setting using two types of queues:  
- **Normal Queue** (FIFO)
- **Priority Queue** (based on medical urgency)

The simulation incorporates realistic behavior by factoring in arrival times, service durations, and patient criticality.

---

## 📌 Features

- **Normal Queue**: Patients are served in the order of arrival.
- **Priority Queue**: Patients are served based on criticality:
  - `1` → Critical  
  - `2` → Urgent  
  - `3` → Normal  
- **Multiple Doctors**: You can set the number of available doctors (servers).
- **Distributions**:
  - **Arrival Time**: Exponentially distributed (Poisson process)
  - **Service Time**: Normally distributed (Gaussian)

---

## 🛠️ Implementation Details

### Key Classes

- `PatientNormal`: Represents a patient in the normal queue.
- `PatientPriority`: Represents a patient in the priority queue, including criticality level.
- `NormalHospitalQueue`: Manages FIFO queue logic and patient assignment to doctors.
- `PriorityHospitalQueue`: Handles triage logic with multiple criticality levels and scheduling.
- `Main`: Generates patients, runs the simulation, and prints results.

### Core Logic Highlights

- Patients are inserted into queues based on:
  - Arrival time (Normal Queue)
  - Criticality level and arrival time (Priority Queue)
- No preemption: Once a doctor starts treating a patient, they complete the treatment even if a more critical patient arrives.
- Patient generation:
  ```java
  double arrivalTime = Math.max(0, -Math.log(1 - random.nextDouble()) * arrivalMean);
  double serviceTime = Math.max(0, serviceMean + serviceStd * random.nextGaussian());
  ```

---

## 📊 Output Example

```
=== Simulation Results ===

Normal Queue:
Arrival Time | Service Time | Departure Time
--------------------------------------------
     3.75    |     11.81    |     15.56
    13.34    |     13.42    |     28.98
    ...

Priority Queue:
Arrival Time | Service Time | Departure Time | Criticality
-----------------------------------------------------------
     5.23    |     7.14     |     12.38      | Critical
     1.58    |     10.03    |     22.41      | Urgent
     ...
```

---

## 🧪 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```

2. Compile the Java files:
   ```bash
   javac Hospital/*.java
   ```

3. Run the simulation:
   ```bash
   java Hospital.Main
   ```

---

## 🚀 More Features

- Three levels of patient criticality (Critical, Urgent, Normal)
- Adjustable number of doctors
- Dynamic patient generation using realistic statistical models

---

## 📂 Project Structure

```
Hospital/
├── Main.java
├── NormalHospitalQueue.java
├── PriorityHospitalQueue.java
├── PatientNormal.java
├── PatientPriority.java
```
