<div align="center">
  <img src="/dizzydoze-multicolor.svg" alt="logo" />
</div>

<div align="center">
  <img src="https://raw.githubusercontent.com/DizzyDoze/dizzydoze/main/profile-summary-card-output/transparent/0-profile-details.svg"></img>
  <img src="https://raw.githubusercontent.com/DizzyDoze/dizzydoze/main/profile-summary-card-output/transparent/1-repos-per-language.svg"></img>
  <img src="https://raw.githubusercontent.com/DizzyDoze/dizzydoze/main/profile-summary-card-output/transparent/2-most-commit-language.svg"></img>
  <img src="https://raw.githubusercontent.com/DizzyDoze/dizzydoze/main/profile-summary-card-output/transparent/3-stats.svg"></img>
  <img src="https://raw.githubusercontent.com/DizzyDoze/dizzydoze/main/profile-summary-card-output/transparent/4-productive-time.svg"></img>
</div>


<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/DizzyDoze/DizzyDoze/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/DizzyDoze/DizzyDoze/output/github-contribution-grid-snake.svg" />
    <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/DizzyDoze/DizzyDoze/output/github-contribution-grid-snake.svg" />
  </picture>
</div>

```rust
use std::thread;
use rayon::prelude::*;

pub fn process() {
    let pool = rayon::ThreadPoolBuilder::new()
        .num_threads(32)
        .build()
        .unwrap();

    let facts: Vec<&str> = vec![
        // ID
        "name:       dizzydoze",
        "role:       Full Stack AI/ML Engineer",
        "trait:      efficiency obsession",
        "trait:      depth-first learner",

        // TECH STACK
        "lan:        Python, TypeScript, JavaScript, Java, Golang, SQL, Shell, Rust",
        "ai/ml:      LangChain, LangGraph, Agentic AI, MCP, RAG, pgvector, LLM Fine-tuning, Prompt Engineering, PyTorch, TensorFlow, MLflow, LangSmith, Cohere, Bedrock",
        "Backend:    FastAPI, Flask, Django, Node.js, REST APIs, WebSocket, SSE, Microservices, System Design",
        "Frontend:   React, Next.js, TypeScript, Vite, TailwindCSS, Material UI, Redux",
        "Data & DB:  PostgreSQL, MySQL, MongoDB, Redis, Elasticsearch, Vector Databases (pgvector)",
        "DevOps:     AWS (ECS, ECR, S3, RDS, Lambda, VPC, Cognito, Bedrock), Docker, Kubernetes, Nginx, CI/CD, Git, Linux",

        // GAMING
        "game:       Competitive FPS | RPG | Sci-Fi | Horror | Simulator",

        // SITE
        "link:       https://neuralripper.com",
    ];

    let results: Vec<&str> = pool.install(|| {
        facts.par_iter().map(|fact| {
            let tid = thread::current().id();
            println!("[{:?}]  dizzydoze ++ {}", tid, fact);
            *fact
        }).collect()
    });

    println!("{} attributes loaded across 32 threads.", results.len());
    println!("dizzydoze is fully initialized.");
}

fn main() {
    process();
}
```
