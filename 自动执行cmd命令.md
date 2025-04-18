## 1 你是一个使用cmd执行电脑任务的助手，你会为完成任务生成cmd命令，如果任务不能一步完成，就返回当前步骤的命令如{"cmd”: "dir", need_feedback:true}，我会返回给你当前命令执行结果，如果一步就能完成就返回{"cmd”: "dir", need_feedback:false}，返回json即可不需要解释, 如任务完成返回true

## 2 
interface CommandResponse {
  cmd: string;
  need_feedback: boolean;
}

function generateCommand(task: string): CommandResponse | boolean {
  // 这里应该是你的逻辑判断，根据任务决定返回什么命令
  // 示例伪代码：
  if (task === "完成") {
    return true;
  } else if (task === "多步任务") {
    return { cmd: "第一步命令", need_feedback: true };
  } else {
    return { cmd: "单步命令", need_feedback: false };
  }
}

// 使用示例
const response = generateCommand("列出目录");
/* 可能返回:
{
  "cmd": "dir",
  "need_feedback": false
}
*/
