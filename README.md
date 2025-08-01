# Wingate-Bing-Competition-
Bingo tasks
import { useState } from "react";

const tasks = [
  "Got a sunrise or sunset photo on the golf course",
  "Joined our month-end lunch buffet",
  "High-fived or fist-bumped a stranger at the club",
  "Joined the Road Runners for 1 x walk or run",
  "Took a selfie with a Wingate employee",
  "Tried something from our monthly specials’ menu",
  "Played a game of Padel",
  "Rate and reviewed us on our Facebook page",
  "Brought a friend or family member for lunch",
  "Played a game of bowls or joined the bowls buddy day",
  "Tagged Wingate on a personal post on Instagram or Facebook",
  "Downloaded the Wingate mobile app",
  "Did 10 000 steps at Wingate",
  "Hit a bucket of balls at the driving range",
  "Ordered a drinks special from the bar",
  "Ordered a pizza from the Club Restaurant"
];

export default function BingoApp() {
  const [completed, setCompleted] = useState(Array(tasks.length).fill(false));

  const toggleTask = (index) => {
    const updated = [...completed];
    updated[index] = !updated[index];
    setCompleted(updated);
  };

  return (
    <div className="p-4 bg-green-50 min-h-screen">
      <h1 className="text-2xl font-bold text-center mb-6">🏌️ Wingate Bingo Challenge</h1>
      <div className="grid grid-cols-4 gap-3">
        {tasks.map((task, i) => (
          <div
            key={i}
            className={`rounded-2xl p-2 h-32 flex items-center justify-center text-center text-sm cursor-pointer shadow-md transition-all ${
              completed[i] ? "bg-green-400 text-white" : "bg-white"
            }`}
            onClick={() => toggleTask(i)}
          >
            {task}
          </div>
        ))}
      </div>
      <p className="text-center mt-6 text-sm text-gray-600">
        Tap a block to mark the task as done. Complete all to win!
      </p>
    </div>
  );
}


