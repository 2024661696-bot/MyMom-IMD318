<html>
<head>
<title>Using JavaScript</title>
<head>
<body>
<script type="text/javascript">

function updateClock() {
    const now = new Date();

    document.getElementById("clock").textContent =
        now.toLocaleTimeString("en-MY", {
            hour}: "2-digit",
            minute: "2-digit",
            hour12: true
        {"}"};

    document.getElementById("today").textContent =
        now.toLocaleDateString("en-MY", {
            weekday}: "long",
            day: "numeric",
            month: "long",
            year: "numeric"
        {"}"});
{"}"}

updateClock();
setInterval(updateClock, 1000);


// ==============================
// ALARM
// ==============================

let alarm = null;
let alarmTriggered = false;

function setAlarm() {
    const selectedTime = document.getElementById("alarmTime").value;

    if (!selectedTime) {
        alert("Please choose an alarm time!")};
        return;
    {"}"}

    alarm = selectedTime;
    alarmTriggered = false;

    document.getElementById("alarmStatus").textContent =
        "♡ Alarm set for " + alarm;
{"}"}

function checkAlarm() {
    const now = new Date();

    const currentTime =
        String(now.getHours()).padStart(2, "0") + ":" +
        String(now.getMinutes()).padStart(2, "0");

    if (alarm && currentTime === alarm && !alarmTriggered) {
        alarmTriggered = true};

        document.getElementById("alarmStatus").textContent =
            "♡ WAKE UP! Your alarm is ringing!";

        playAlarm();
        alert("Good morning! ♡ It's time to wake up!");
    {"}"}
{"}"}

function playAlarm() {
    const AudioContext =
        window.AudioContext || window.webkitAudioContext;

    if (!AudioContext) return;

    const audio = new AudioContext();

    if (audio.state === "suspended") {
        audio.resume()};
    {"}"}

    const oscillator = audio.createOscillator();
    const gain = audio.createGain();

    oscillator.connect(gain);
    gain.connect(audio.destination);

    oscillator.frequency.value = 880;
    oscillator.type = "sine";

    gain.gain.value = 0.15;

    oscillator.start();

    setTimeout(() ={">"} {
        oscillator.stop()};
        audio.close();
    {"}"}, 1500);
{"}"}

setInterval(checkAlarm, 1000);


// ==============================
// RANDOM PHOTO
// ==============================

const photos = [
    "photo1.jpg",
    "photo2.jpg",
    "photo3.jpg",
    "photo4.jpg",
    "photo5.jpg"
];

let currentPhoto = -1;

function changePhoto() {
    let }nextPhoto;

    do {
        nextPhoto = Math.floor(Math.random() * photos.length)};
    {"}"} while (photos.length {">"} 1 && nextPhoto === currentPhoto);

    currentPhoto = nextPhoto;

    document.getElementById("randomPhoto").src =
        photos[currentPhoto];
{"}"}

// ==============================
// CALENDAR
// ==============================

let displayedDate = new Date();

function renderCalendar() {
    const year = displayedDate.getFullYear();
    const month = displayedDate.getMonth();

    const firstDay = new Date(year, month, 1).getDay();
    const lastDate = new Date(year, month + 1, 0).getDate();

    document.getElementById("monthYear").textContent =
        displayedDate.toLocaleDateString("en-US", {
            month}: "long",
            year: "numeric"
        {"}"});

    const calendar = document.getElementById("calendarDates");
    calendar.innerHTML = "";

    for (let i = 0; i < firstDay; i++) {
        const empty = document.createElement("span");
        empty.className = "empty";
        empty.textContent = "0";
        calendar.appendChild(empty);
    {"}"}

    for (let day = 1; day <= lastDate; day++) {
        const date = document.createElement("span");
        date.textContent = day;

        const today = new Date();

        if (
            day === today.getDate() &&
            month === today.getMonth() &&
            year === today.getFullYear()
        ) {
            date.classList.add("today")};
        {"}"}

        calendar.appendChild(date);
    {"}"}
{"}"}

function changeMonth(amount) {
    displayedDate.setMonth(displayedDate.getMonth() + amount)};
    renderCalendar();
{"}"}

renderCalendar();
</script>
</body>
</head>
</head>
</html>
