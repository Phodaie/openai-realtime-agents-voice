Hacked https://github.com/openai/openai-realtime-agents so each agent has voice attribute. Set voice property of the agent to one of the supported voices. 

```ts
export interface AgentConfig {
  name: string;
  voice?: string;
  publicDescription: string; // gives context to agent transfer tool
  instructions: string;
  tools: Tool[];
  toolLogic?: Record<
    string,
    (args: any, transcriptLogsFiltered: TranscriptItem[]) => Promise<any> | any
  >;
  downstreamAgents?: AgentConfig[] | { name: string; publicDescription: string }[];
}

```