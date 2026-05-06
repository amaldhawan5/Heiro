import { useState } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input";

export default function StudentHelperApp() { const [tasks, setTasks] = useState([]); const [taskInput, setTaskInput] = useState(""); const [timeInput, setTimeInput] = useState(""); const [question, setQuestion] = useState(""); const [answer, setAnswer] = useState("");

const addTask = () => { if (!taskInput || !timeInput) return; setTasks([...tasks, { task: taskInput, time: timeInput }]); setTaskInput(""); setTimeInput(""); };

const deleteTask = (index) => { const newTasks = tasks.filter((_, i) => i !== index); setTasks(newTasks); };

const handleQuestion = () => { let res = "Try studying consistently and revising."; if (question.toLowerCase().includes("math")) { res = "Break problems step by step and practice formulas."; } else if (question.toLowerCase().includes("science")) { res = "Focus on concepts and diagrams."; } else if (question.toLowerCase().includes("history")) { res = "Make timelines and short notes."; } setAnswer(res); };

return ( <div className="p-4 grid gap-4"> <h1 className="text-2xl font-bold">📚 Student Helper</h1>

{/* Chatbot */}
  <Card>
    <CardContent className="p-4">
      <h2 className="font-semibold mb-2">Ask Study Question</h2>
      <Input
        placeholder="Ask something..."
        value={question}
        onChange={(e) => setQuestion(e.target.value)}
      />
      <Button className="mt-2" onClick={handleQuestion}>
        Ask
      </Button>
      {answer && <p className="mt-2">🤖 {answer}</p>}
    </CardContent>
  </Card>

  {/* Task Manager */}
  <Card>
    <CardContent className="p-4">
      <h2 className="font-semibold mb-2">Task Manager</h2>
      <div className="flex gap-2">
        <Input
          placeholder="Task"
          value={taskInput}
          onChange={(e) => setTaskInput(e.target.value)}
        />
        <Input
          placeholder="Time"
          value={timeInput}
          onChange={(e) => setTimeInput(e.target.value)}
        />
        <Button onClick={addTask}>Add</Button>
      </div>

      <ul className="mt-4">
        {tasks.map((t, i) => (
          <li key={i} className="flex justify-between mb-2">
            <span>
              {t
