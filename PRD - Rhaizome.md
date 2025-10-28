---
up: 
related: []
created: 2025-10-27
log: "[[2025-10-27]]"
tags:
---
## 🧬 **Rhaizome** 
### _Evolutionary Knowledge Synthesis from Slack to Obsidian_
#### Product Requirements Document v1.0
**Tagline:** _Your Slack channel becomes a living knowledge organism that evolves, connects, and distills wisdom over time._
---
### **🎯 THE VISION**
**The Problem:** You save 100 brilliant things to Slack. You revisit 3. The other 97 die in the archive—wasted potential, lost insights, forgotten breakthroughs.
**The Solution:** Memetic Garden watches your Slack channel and transforms chaos into an **evolutionary knowledge ecosystem** where:
- Ideas compete for survival based on actual value
- Strong concepts propagate and connect
- Weak patterns die off
- Mutations (outliers) are preserved in case they're revolutionary
- A "Master Prompt" evolves as the DNA of your best practices
- Everything is interconnected in beautiful, navigable Obsidian/Notion
**Core Magic:**
- 🧬 **Evolutionary Pressure** - Ideas compete, best survive
- 🕸️ **Automatic Bidirectional Linking** - Concepts find each other
- 📊 **Living Dashboard** - Visual knowledge universe
- 🔄 **Self-Synthesizing** - Summaries write themselves
- 💎 **Distillation Engine** - Noise becomes signal
- 🌱 **Master Prompt Evolution** - Your coding wisdom grows organically
- 🦋 **Mutation Bucket** - Outliers that might change everything
---
### **I. SYSTEM ARCHITECTURE** 🏗️
```
                    🌟 THE MEMETIC CORE
                   (Evolution & Synthesis)
                           |
        ┌─────────────────┼─────────────────┐
        │                 │                 │
    INGESTION         EVOLUTION          OUTPUT
        │                 │                 │
    ┌───┴───┐         ┌───┴───┐       ┌───┴───┐
  SLACK   X        SELECT LINK      OBS  DASH
    │     │           │     │         │     │
    └──┬──┘           └──┬──┘         └──┬──┘
       │                 │                │
       └────────┬────────┴────────┬───────┘
                │                 │
           INTELLIGENCE      MASTER PROMPT
           EXTRACTION         EVOLUTION
```
---
### **II. THE EVOLUTIONARY MODEL** 🧬
#### **Knowledge as Living Organisms**
```typescript
interface MemeticOrganism {
  // Identity
  id: string;
  type: "tool" | "insight" | "research" | "tip" | "design" | "prompt_pattern";
  content: string;
  source: {
    platform: "slack" | "twitter";
    url: string;
    timestamp: Date;
    originalPoster?: string;
  };
  // Evolutionary Metrics
  fitness: {
    referenceCount: number; // How often linked to
    synthesisCount: number; // How often combined with other ideas
    applicationCount: number; // How often actually used
    lastAccessed: Date;
    decayRate: number; // Loses fitness over time if unused
    overallScore: number; // 0-100
  };
  // Genetic Information
  genes: {
    categories: string[]; // ["LLM", "prompting", "Claude"]
    concepts: string[]; // ["chain-of-thought", "temperature"]
    techniques: string[]; // ["few-shot", "XML tags"]
    relationships: string[]; // IDs of related organisms
    ancestors: string[]; // What spawned this
    descendants: string[]; // What this spawned
  };
  // Mutations
  mutationScore: number; // How different from existing patterns
  clusterAssignment: string | "outlier";
  // Lifecycle
  generation: number;
  birthDate: Date;
  lastMutation: Date;
  status: "thriving" | "stable" | "declining" | "archived" | "outlier";
}
```
---
#### **Evolutionary Processes**
```typescript
interface EvolutionEngine {
  // 1. SELECTION (Natural Selection)
  selection: {
    fitnessFunction: (organism: MemeticOrganism) => number;
    survivalCriteria: {
      minimumFitness: 30; // Below this, organism is archived
      referenceThreshold: 3; // Must be referenced at least 3 times in 90 days
      decayRate: 0.1; // Fitness decreases 10% per month if unused
    };
    elitismRate: 0.1; // Top 10% always survive
    pressures: [
      "Is this actually useful?",
      "Does this connect to other ideas?",
      "Has this been applied?",
      "Is this still relevant?",
      "Does this generate new ideas?"
    ];
  };
  // 2. RECOMBINATION (Sexual Reproduction)
  recombination: {
    process: "Find two high-fitness organisms, synthesize insights";
    crossover: (parent1: MemeticOrganism, parent2: MemeticOrganism) => {
      // Create new organism that combines both
      offspring: MemeticOrganism;
      synthesisNote: string; // "What happens when we combine X and Y?"
    };
    frequency: "Weekly synthesis pass";
  };
  // 3. MUTATION (Random Variation)
  mutation: {
    detection: "Identify ideas that don't fit existing clusters";
    mutationScore: (organism: MemeticOrganism) => {
      // How different is this from everything else?
      novelty: number; // 0-100
      disruptivePotential: number; // 0-100
    };
    mutationBucket: {
      threshold: 80; // Mutation score > 80 = outlier
      purpose: "Preserve weird ideas that might be revolutionary";
      review: "Monthly review of mutations - promote to main population or archive";
    };
  };
  // 4. ADAPTATION (Learning)
  adaptation: {
    process: "Master Prompt evolves based on what works";
    learningSignals: [
      "Which techniques appear repeatedly?",
      "Which patterns correlate with success?",
      "What rules emerge from practice?",
      "What antipatterns should be avoided?"
    ];
    updateFrequency: "Master Prompt updates weekly";
  };
  // 5. SPECIATION (Divergence)
  speciation: {
    clusterFormation: "Organisms cluster by similarity";
    species: {
      "Prompting Techniques": Cluster;
      "Tool Discoveries": Cluster;
      "Research Insights": Cluster;
      "Design Patterns": Cluster;
      "Meta-Learning": Cluster;
    };
    crossSpeciesInsights: "What happens when different species interact?";
  };
}
```
---
### **III. INGESTION PIPELINE** 📥
#### **Slack Watcher**
```typescript
interface SlackIngestion {
  // Configuration
  config: {
    workspace: string;
    channelId: string; // The channel you save to
    watchMode: "real-time" | "polling";
    pollInterval: 60; // seconds
  };
  // What to Capture
  capture: {
    messages: {
      text: boolean;
      attachments: boolean;
      links: boolean;
      threads: boolean;
      reactions: boolean; // Reactions = fitness signal
    };
    unfurling: {
      tweets: boolean; // Auto-fetch full tweet content
      articles: boolean; // Fetch article text
      githubRepos: boolean; // Fetch README
      videos: boolean; // Fetch transcript if available
    };
    metadata: {
      timestamp: boolean;
      author: boolean; // Who posted
      reactors: boolean; // Who reacted
      threadContext: boolean; // Full thread if reply
    };
  };
  // Intelligence Extraction
  extraction: {
    // Use Claude to extract structured info
    process: async (message: SlackMessage) => {
      const prompt = `
Analyze this Slack message and extract structured information:
MESSAGE: ${message.text}
LINKS: ${message.links}
CONTEXT: ${message.thread}
Extract:
1. TYPE: tool | insight | research | tip | design | prompt_pattern | other
2. CATEGORIES: Relevant tags (e.g., ["LLM", "Claude", "prompting"])
3. KEY CONCEPTS: Core ideas mentioned
4. TECHNIQUES: Specific techniques or methods
5. ACTIONABILITY: Is this immediately actionable? How?
6. NOVELTY: How new/different is this? (0-100)
7. SUMMARY: One-sentence summary
8. CONNECTIONS: What existing concepts might this relate to?
Return as JSON.
`;
      const extracted = await claudeExtract(prompt);
      return extracted;
    };
  };
  // Deduplication
  deduplication: {
    semanticSimilarity: {
      threshold: 0.85; // 85% similar = duplicate
      method: "embedding-based (Claude embeddings or OpenAI)";
    };
    urlDedup: {
      normalizeUrls: boolean; // Remove tracking params
      checkExisting: boolean; // Compare against existing notes
    };
    onDuplicate: "Merge fitness scores, update last_seen date";
  };
}
```
---
#### **Twitter Integration (Optional)**
```typescript
interface TwitterIngestion {
  // For tweets you save to Slack
  process: {
    extractThreads: boolean; // Get full thread context
    extractAuthorBio: boolean; // Who said this? Their expertise?
    extractMediaText: boolean; // OCR on images with text
    extractReplies: boolean; // Sometimes insight is in replies
  };
  // Enhanced metadata
  metadata: {
    authorFollowers: number; // Credibility signal
    likes: number; // Popularity signal
    threadLength: number; // Depth signal
    replierCredentials: string[]; // Who engaged?
  };
}
```
---
### **IV. INTELLIGENCE LAYER** 🧠
#### **Concept Extraction**
```typescript
class ConceptExtractor {
  async extractConcepts(content: string): Promise<Concepts> {
    const prompt = `
You are a concept extraction specialist. Analyze this content and identify:
CONTENT:
${content}
Extract:
1. **Core Concepts** (2-5): Main ideas (noun phrases)
   - Format: "[[Concept Name]]" (Obsidian link format)
   - Only concepts that are reusable/general
2. **Techniques** (0-10): Specific methods or approaches
   - Format: "[[Technique: Name]]"
   - Must be actionable
3. **Tools** (0-10): Software, libraries, services mentioned
   - Format: "[[Tool: Name]]"
4. **Principles** (0-5): Higher-order rules or guidelines
   - Format: "[[Principle: Name]]"
5. **Antipatterns** (0-5): Things to avoid
   - Format: "[[Antipattern: Name]]"
6. **Examples** (0-10): Concrete instances or use cases
   - Format: Brief description, not links
7. **Questions Raised** (0-5): Unanswered questions this content prompts
Return as JSON with arrays for each category.
`;
    const response = await this.callClaude(prompt);
    return this.parseConcepts(response);
  }
  async findConnections(
    organism: MemeticOrganism,
    existingNotes: MemeticOrganism[]
  ): Promise<Connection[]> {
    const connectionPrompt = `
Given this new content:
${organism.content}
And these existing notes:
${existingNotes.slice(0, 50).map(n => `- ${n.id}: ${n.content.slice(0, 200)}`).join('\n')}
Identify STRONG connections (not weak associations).
For each connection:
8. What's the relationship? (builds_on | contrasts_with | example_of | enables | requires | similar_to)
9. Why is this connection meaningful?
10. What insight emerges from the connection?
Return top 5 connections as JSON.
`;
    const response = await this.callClaude(connectionPrompt);
    return this.parseConnections(response);
  }
}
```
---
#### **Semantic Clustering**
```typescript
class SemanticClusterer {
  async clusterOrganisms(organisms: MemeticOrganism[]): Promise<Clusters> {
    // 1. Generate embeddings for all organisms
    const embeddings = await this.generateEmbeddings(organisms);
    // 2. Cluster using HDBSCAN (finds natural clusters + outliers)
    const clusters = await this.hdbscan(embeddings, {
      minClusterSize: 5,
      minSamples: 3,
      clusterSelectionEpsilon: 0.3
    });
    // 3. Label clusters using Claude
    for (const cluster of clusters) {
      const clusterLabel = await this.labelCluster(cluster.organisms);
      cluster.label = clusterLabel;
    }
    // 4. Identify outliers (mutation candidates)
    const outliers = organisms.filter(o => o.clusterAssignment === "outlier");
    return {
      clusters,
      outliers,
      clusterMap: this.buildClusterMap(clusters)
    };
  }
  async labelCluster(organisms: MemeticOrganism[]): Promise<ClusterLabel> {
    const summaries = organisms.slice(0, 10).map(o => o.content.slice(0, 200));
    const labelPrompt = `
These content pieces have been clustered together. What theme unifies them?
SAMPLES:
${summaries.join('\n\n')}
Provide:
1. **Cluster Name** (2-4 words, descriptive)
2. **Theme** (One sentence explaining the pattern)
3. **Key Characteristics** (What makes this cluster distinct?)
Return as JSON.
`;
    const response = await this.callClaude(labelPrompt);
    return this.parseClusterLabel(response);
  }
}
```
---
### **V. THE EVOLUTION ENGINE** 🌱
#### **Fitness Calculation**
```typescript
class FitnessCalculator {
  calculateFitness(organism: MemeticOrganism, graph: KnowledgeGraph): number {
    const metrics = {
      // 1. Reference Score (40%)
      referenceScore: this.calculateReferenceScore(organism, graph),
      // 2. Synthesis Score (25%)
      synthesisScore: this.calculateSynthesisScore(organism, graph),
      // 3. Application Score (20%)
      applicationScore: this.calculateApplicationScore(organism),
      // 4. Recency Score (10%)
      recencyScore: this.calculateRecencyScore(organism),
      // 5. Reaction Score (5%)
      reactionScore: organism.source.reactions?.length || 0
    };
    const weightedScore = 
      metrics.referenceScore * 0.40 +
      metrics.synthesisScore * 0.25 +
      metrics.applicationScore * 0.20 +
      metrics.recencyScore * 0.10 +
      metrics.reactionScore * 0.05;
    return Math.min(100, weightedScore);
  }
  calculateReferenceScore(organism: MemeticOrganism, graph: KnowledgeGraph): number {
    // How many other notes link to this one?
    const inboundLinks = graph.getInboundLinks(organism.id);
    // Quality-weighted: links from high-fitness organisms count more
    const weightedReferences = inboundLinks.reduce((sum, link) => {
      const sourceOrganism = graph.getOrganism(link.sourceId);
      const weight = sourceOrganism.fitness.overallScore / 100;
      return sum + weight;
    }, 0);
    // Diminishing returns after 10 references
    return Math.min(100, weightedReferences * 10);
  }
  calculateSynthesisScore(organism: MemeticOrganism, graph: KnowledgeGraph): number {
    // Has this organism spawned new insights?
    const descendants = graph.getDescendants(organism.id);
    // More valuable if descendants are also high-fitness
    const qualityDescendants = descendants.filter(d => d.fitness.overallScore > 60);
    return Math.min(100, qualityDescendants.length * 15);
  }
  calculateApplicationScore(organism: MemeticOrganism): number {
    // Has this been marked as "applied" or "used"?
    // This comes from user interaction (tagging a note as #applied)
    return organism.metadata?.applied ? 100 : 0;
  }
  calculateRecencyScore(organism: MemeticOrganism): number {
    const ageInDays = (Date.now() - organism.birthDate.getTime()) / (1000 * 60 * 60 * 24);
    // Decay curve: 100 at day 0, 50 at 90 days, 0 at 365 days
    if (ageInDays <= 90) {
      return 100 - (ageInDays / 90) * 50;
    } else if (ageInDays <= 365) {
      return 50 - ((ageInDays - 90) / 275) * 50;
    } else {
      return 0;
    }
  }
}
```
---
#### **Selection Pressure**
```typescript
class SelectionEngine {
  async runSelection(generation: number): Promise<SelectionResults> {
    console.log(`🧬 Running selection for Generation ${generation}...`);
    const allOrganisms = await this.getAllOrganisms();
    // 1. Calculate fitness for all
    const withFitness = await Promise.all(
      allOrganisms.map(async o => {
        const fitness = await this.fitnessCalc.calculateFitness(o, this.graph);
        return { ...o, fitness: { ...o.fitness, overallScore: fitness } };
      })
    );
    // 2. Sort by fitness
    const sorted = withFitness.sort((a, b) => 
      b.fitness.overallScore - a.fitness.overallScore
    );
    // 3. Apply selection pressure
    const results = {
      thriving: sorted.filter(o => o.fitness.overallScore >= 70),
      stable: sorted.filter(o => o.fitness.overallScore >= 40 && o.fitness.overallScore < 70),
      declining: sorted.filter(o => o.fitness.overallScore >= 20 && o.fitness.overallScore < 40),
      archived: sorted.filter(o => o.fitness.overallScore < 20),
      elites: sorted.slice(0, Math.ceil(sorted.length * 0.1)), // Top 10%
    };
    // 4. Archive low-fitness organisms
    for (const organism of results.archived) {
      await this.archiveOrganism(organism);
    }
    // 5. Generate selection report
    const report = await this.generateSelectionReport(results);
    return {
      ...results,
      report,
      generation
    };
  }
  async generateSelectionReport(results: SelectionResults): Promise<string> {
    const reportPrompt = `
Generate a selection report for this generation:
**Thriving** (${results.thriving.length}): High-fitness organisms
Top 5: ${results.thriving.slice(0, 5).map(o => o.content.slice(0, 100)).join('; ')}
**Stable** (${results.stable.length}): Medium-fitness organisms
**Declining** (${results.declining.length}): Low-fitness organisms
**Archived** (${results.archived.length}): Removed from active population
**Insights:**
1. What patterns are succeeding? (What do thriving organisms have in common?)
2. What's declining? (What types of content aren't useful?)
3. What should I focus on collecting more of?
4. What should I stop saving?
Write a concise report (200-300 words).
`;
    const report = await this.callClaude(reportPrompt);
    return report;
  }
}
```
---
#### **Synthesis Engine (Recombination)**
```typescript
class SynthesisEngine {
  async runWeeklySynthesis(): Promise<SynthesisResults> {
    console.log("🧬 Running weekly synthesis (recombination)...");
    // 1. Find high-fitness organisms from different clusters
    const elites = await this.getEliteOrganisms();
    const clusters = await this.clusterer.clusterOrganisms(elites);
    // 2. Cross-cluster synthesis (sexual reproduction)
    const syntheses = [];
    for (const cluster1 of clusters) {
      for (const cluster2 of clusters) {
        if (cluster1.id === cluster2.id) continue;
        // Find best representative from each cluster
        const parent1 = cluster1.organisms[0];
        const parent2 = cluster2.organisms[0];
        // Synthesize
        const offspring = await this.synthesize(parent1, parent2);
        if (offspring) {
          syntheses.push(offspring);
        }
      }
    }
    // 3. Within-cluster synthesis (asexual reproduction)
    for (const cluster of clusters) {
      const clusterSynthesis = await this.synthesizeCluster(cluster);
      if (clusterSynthesis) {
        syntheses.push(clusterSynthesis);
      }
    }
    return {
      newOrganisms: syntheses,
      count: syntheses.length
    };
  }
  async synthesize(
    parent1: MemeticOrganism,
    parent2: MemeticOrganism
  ): Promise<MemeticOrganism | null> {
    const synthesisPrompt = `
You are a knowledge synthesizer. Two high-value ideas have been selected for recombination:
IDEA 1:
${parent1.content}
Categories: ${parent1.genes.categories.join(', ')}
IDEA 2:
${parent2.content}
Categories: ${parent2.genes.categories.join(', ')}
Create a NEW insight by combining these ideas:
1. **What emerges when we combine these?**
2. **What novel technique or approach results?**
3. **What becomes possible that wasn't before?**
4. **Is this synthesis actually valuable, or forced?**
If there's NO meaningful synthesis, return null.
If there IS a valuable synthesis, return:
{
  "title": "Brief title for the new insight",
  "content": "2-3 paragraph explanation of the synthesized insight",
  "novelty": "What's new here that neither parent had alone?",
  "applicability": "How could this be used?",
  "confidence": 0-100 (how confident are you this is valuable?)
}
`;
    const response = await this.callClaude(synthesisPrompt);
    const synthesis = this.parseSynthesis(response);
    // Only create organism if confidence > 60
    if (!synthesis || synthesis.confidence < 60) {
      return null;
    }
    return {
      id: this.generateId(),
      type: "insight",
      content: synthesis.content,
      source: {
        platform: "synthesis",
        url: "",
        timestamp: new Date(),
        parents: [parent1.id, parent2.id]
      },
      genes: {
        categories: [...new Set([...parent1.genes.categories, ...parent2.genes.categories])],
        concepts: this.mergeConcepts(parent1.genes.concepts, parent2.genes.concepts),
        techniques: [...new Set([...parent1.genes.techniques, ...parent2.genes.techniques])],
        relationships: [parent1.id, parent2.id],
        ancestors: [parent1.id, parent2.id],
        descendants: []
      },
      fitness: {
        overallScore: 50, // Starts at baseline
        referenceCount: 0,
        synthesisCount: 0,
        applicationCount: 0,
        lastAccessed: new Date(),
        decayRate: 0.1
      },
      mutationScore: 0,
      clusterAssignment: "unassigned",
      generation: Math.max(parent1.generation, parent2.generation) + 1,
      birthDate: new Date(),
      lastMutation: new Date(),
      status: "stable"
    };
  }
  async synthesizeCluster(cluster: Cluster): Promise<MemeticOrganism | null> {
    // Create a meta-note that summarizes the cluster theme
    const clusterSummaryPrompt = `
This cluster contains ${cluster.organisms.length} related pieces of content:
CLUSTER THEME: ${cluster.label}
SAMPLES (top 5):
${cluster.organisms.slice(0, 5).map(o => `- ${o.content.slice(0, 200)}`).join('\n')}
Create a synthesized "master note" for this cluster:
5. **Theme Summary**: What unifies these ideas?
6. **Key Patterns**: What patterns emerge across all items?
7. **Actionable Framework**: How can these ideas be systematized?
8. **Best Practices**: What rules or guidelines emerge?
9. **Gaps**: What's missing from this cluster?
Write a comprehensive synthesis (500-800 words).
`;
    const synthesis = await this.callClaude(clusterSummaryPrompt);
    return this.createClusterSummaryOrganism(cluster, synthesis);
  }
}
```
---
### **VI. MASTER PROMPT EVOLUTION** 🧬
#### **The Living Document**
```typescript
interface MasterPrompt {
  // Core Identity
  metadata: {
    version: string; // "v1.47"
    lastUpdated: Date;
    generation: number;
    confidence: number; // How stable is this? (0-100)
  };
  // Evolved Sections
  sections: {
    // 1. Core Principles (Highest Level)
    principles: Principle[];
    // 2. Rules (Mid Level)
    rules: Rule[];
    // 3. Techniques (Tactical Level)
    techniques: Technique[];
    // 4. Antipatterns (What NOT to Do)
    antipatterns: Antipattern[];
    // 5. Context Modifiers (When to Break Rules)
    contextModifiers: ContextModifier[];
    // 6. Tool-Specific Guidance
    toolSpecific: {
      claude: ToolGuidance;
      cursor: ToolGuidance;
      midjourney: ToolGuidance;
      // ... others
    };
    // 7. Meta-Learning (How to Learn)
    metaLearning: MetaPattern[];
  };
  // Evolution Tracking
  evolution: {
    addedThisWeek: Change[];
    removedThisWeek: Change[];
    modifiedThisWeek: Change[];
    stabilityScore: number; // How much is it changing?
  };
}
```
---
#### **Evolution Algorithm**
```typescript
class MasterPromptEvolution {
  async evolve(): Promise<MasterPrompt> {
    console.log("🧬 Evolving Master Prompt...");
    const currentPrompt = await this.loadCurrentMasterPrompt();
    const eliteOrganisms = await this.getEliteOrganisms(); // High-fitness only
    // 1. Extract patterns from elite organisms
    const patterns = await this.extractPatterns(eliteOrganisms);
    // 2. Identify principles (highest abstraction)
    const principles = await this.identifyPrinciples(patterns);
    // 3. Identify rules (mid-level)
    const rules = await this.identifyRules(patterns);
    // 4. Identify techniques (tactical)
    const techniques = await this.identifyTechniques(patterns);
    // 5. Identify antipatterns (what fails)
    const antipatterns = await this.identifyAntipatterns();
    // 6. Merge with current prompt
    const evolved = await this.merge(currentPrompt, {
      principles,
      rules,
      techniques,
      antipatterns
    });
    // 7. Validate evolution (does this make sense?)
    const validated = await this.validate(evolved);
    // 8. Generate diff and changelog
    const changelog = await this.generateChangelog(currentPrompt, validated);
    return {
      ...validated,
      evolution: {
        addedThisWeek: changelog.added,
        removedThisWeek: changelog.removed,
        modifiedThisWeek: changelog.modified,
        stabilityScore: this.calculateStability(changelog)
      }
    };
  }
  async extractPatterns(organisms: MemeticOrganism[]): Promise<Pattern[]> {
    const patternPrompt = `
Analyze these high-value pieces of content and extract recurring PATTERNS:
CONTENT (Top 20):
${organisms.slice(0, 20).map(o => `- ${o.content.slice(0, 300)}`).join('\n\n')}
Identify:
1. **Recurring Techniques**: What methods appear repeatedly?
2. **Success Patterns**: What approaches consistently work?
3. **Failure Patterns**: What approaches consistently fail?
4. **Meta-Patterns**: Patterns about patterns (e.g., "Always start with examples before abstractions")
For each pattern:
- Description (what is it?)
- Frequency (how often does it appear?)
- Evidence (which specific pieces exemplify it?)
- Confidence (0-100: how sure are you this is a real pattern?)
Return top 10 patterns as JSON.
`;
    const response = await this.callClaude(patternPrompt);
    return this.parsePatterns(response);
  }
  async identifyPrinciples(patterns: Pattern[]): Promise<Principle[]> {
    const principlePrompt = `
From these patterns, extract HIGH-LEVEL PRINCIPLES:
PATTERNS:
${patterns.map(p => `- ${p.description} (confidence: ${p.confidence}%)`).join('\n')}
A principle is:
- Universal (applies broadly)
- Fundamental (underlies many techniques)
- Stable (unlikely to change with trends)
- Explanatory (helps understand WHY things work)
Examples of principles:
- "Concrete before abstract" (pedagogy)
- "Show, don't tell" (communication)
- "Optimize for deletion" (code quality)
Extract 5-10 principles. For each:
{
  "name": "Brief name (2-5 words)",
  "statement": "One sentence articulation",
  "explanation": "2-3 sentence explanation of WHY this matters",
  "evidence": "Which patterns support this?",
  "applicability": "When does this apply?",
  "confidence": 0-100
}
`;
    const response = await this.callClaude(principlePrompt);
    return this.parsePrinciples(response);
  }
  async identifyRules(patterns: Pattern[]): Promise<Rule[]> {
    const rulePrompt = `
From these patterns, extract MID-LEVEL RULES:
PATTERNS:
${patterns.map(p => `- ${p.description}`).join('\n')}
A rule is:
- Actionable (tells you what to do)
- Specific (more concrete than a principle)
- Contextual (may have exceptions)
- Proven (emerges from repeated success)
Examples of rules:
- "Use XML tags for structured outputs in Claude"
- "Always provide 3+ examples when teaching a concept"
- "Set temperature=1 for creative tasks, 0 for factual"
Extract 10-20 rules. For each:
{
  "rule": "One sentence imperative",
  "context": "When does this apply?",
  "rationale": "Why does this work?",
  "exceptions": "When should you break this rule?",
  "evidence": "Which patterns support this?",
  "confidence": 0-100
}
`;
    const response = await this.callClaude(rulePrompt);
    return this.parseRules(response);
  }
  async merge(
    current: MasterPrompt,
    newContent: {
      principles: Principle[];
      rules: Rule[];
      techniques: Technique[];
      antipatterns: Antipattern[];
    }
  ): Promise<MasterPrompt> {
    const mergePrompt = `
You are merging the CURRENT master prompt with NEW patterns.
CURRENT MASTER PROMPT:
${JSON.stringify(current.sections, null, 2)}
NEW CONTENT:
Principles: ${newContent.principles.length} new
Rules: ${newContent.rules.length} new
Techniques: ${newContent.techniques.length} new
Antipatterns: ${newContent.antipatterns.length} new
For each new item:
1. **Keep if**: Confidence >70 AND doesn't conflict with existing
2. **Replace if**: Supersedes existing item
3. **Merge if**: Complements existing item (combine them)
4. **Discard if**: Low confidence OR redundant
Return updated master prompt with:
- What was added
- What was removed
- What was modified
- Explanation for each change
`;
    const response = await this.callClaude(mergePrompt);
    return this.parseUpdatedPrompt(response);
  }
  async validate(evolved: MasterPrompt): Promise<MasterPrompt> {
    // Sanity checks
    const validationPrompt = `
Review this evolved master prompt for coherence:
${JSON.stringify(evolved.sections, null, 2)}
Check:
1. **Internal Consistency**: Do rules contradict each other?
2. **Completeness**: Are there obvious gaps?
3. **Redundancy**: Are multiple items saying the same thing?
4. **Actionability**: Are rules concrete enough to apply?
5. **Evidence**: Is each item well-supported?
For any issues found, suggest fixes.
Return:
{
  "issues": [...],
  "fixes": [...],
  "overallQuality": 0-100
}
`;
    const validation = await this.callClaude(validationPrompt);
    // Apply fixes if needed
    return this.applyFixes(evolved, validation.fixes);
  }
}
```
---
### **VII. OBSIDIAN OUTPUT** 📝
#### **Note Structure**
```markdown
---
id: mem_2024_001_quantum_prompting
type: insight
categories: [LLM, prompting, Claude, quantum-thinking]
concepts: [[Superposition]], [[Entanglement]], [[Prompt Engineering]]
techniques: [[Multi-Path Reasoning]], [[Parallel Idea Generation]]
fitness_score: 87
generation: 3
created: 2024-10-27
last_accessed: 2024-11-15
status: thriving
cluster: Prompting Techniques
parents: [mem_2024_045, mem_2024_092]
children: [mem_2024_156]
---
## Quantum-Inspired Prompt Design
### Core Insight
By structuring prompts to explore multiple reasoning paths simultaneously (like quantum superposition), we can get richer, more creative responses from LLMs.
### The Technique
Instead of asking Claude to follow ONE reasoning path:
```
Analyze this problem step-by-step.
```
Ask Claude to explore MULTIPLE paths in parallel:
```
Analyze this problem from 3 different perspectives simultaneously:
1. First principles physics approach
2. Biological systems analogy
3. Economic game theory lens
Hold all three in mind, then synthesize the insights.
```
### Why This Works
- **Avoids premature convergence** - Doesn't lock into one path too early
- **Surface hidden assumptions** - Different angles reveal blind spots
- **Emergent synthesis** - Combination yields insights none alone would
### Applications
- [[Creative Problem Solving]]
- [[Research Question Formulation]]
- [[Design Thinking]]
### Evidence
- Used successfully in [[Project: AI Research Engine]]
- Yielded 3x more novel insights than linear prompting
- Recommended by [[Claude 4 Documentation]]
### Related Ideas
- **Builds on**: [[CoT Prompting]], [[Tree of Thoughts]]
- **Contrasts with**: [[Linear Reasoning]], [[Sequential Analysis]]
- **Enables**: [[Meta-Cognitive Prompting]], [[Self-Reflection]]
### Antipatterns
- ❌ Don't use for factual retrieval (overcomplicates)
- ❌ Don't exceed 5 paths (cognitive overload)
- ❌ Don't ask for synthesis if paths are incompatible
### Synthesis History
- **Generation 1**: Parent idea [[Multi-Path Reasoning]] (mem_2024_045)
- **Generation 2**: Combined with [[Quantum Metaphors]] (mem_2024_092)
- **Generation 3**: This synthesis
- **Spawned**: [[Entangled Context Windows]] (mem_2024_156)
### Fitness Metrics
- Referenced by: 12 other notes
- Spawned: 3 child ideas
- Applied in: 5 projects
- Last used: 2024-11-15
---
### Original Source
Saved from Twitter thread by @AIResearcher
https://twitter.com/AIResearcher/status/...
Saved to Slack: 2024-10-27 14:32
### Raw Content
[Original tweet/message text preserved]
---
*This note is part of the [[Memetic Garden]] knowledge evolution system.*
*Generated by Synthesis Oracle v1.0*
```
---
#### **Bidirectional Linking**
```typescript
class ObsidianLinkGenerator {
  async generateLinks(organism: MemeticOrganism): Promise<string[]> {
    // Find all concepts, techniques, etc. and link them
    const links = [];
    // 1. Explicit concept links
    for (const concept of organism.genes.concepts) {
      links.push(`[[${concept}]]`);
    }
    // 2. Technique links
    for (const technique of organism.genes.techniques) {
      links.push(`[[Technique: ${technique}]]`);
    }
    // 3. Tool links
    const toolMatches = this.extractTools(organism.content);
    for (const tool of toolMatches) {
      links.push(`[[Tool: ${tool}]]`);
    }
    // 4. Relationship links (semantic)
    const semanticLinks = await this.findSemanticLinks(organism);
    links.push(...semanticLinks);
    // 5. Ancestor/descendant links
    for (const ancestorId of organism.genes.ancestors) {
      const ancestor = await this.getOrganism(ancestorId);
      links.push(`[[${ancestor.title}]]`);
    }
    return [...new Set(links)]; // Deduplicate
  }
  async findSemanticLinks(organism: MemeticOrganism): Promise<string[]> {
    // Use embeddings to find semantically similar notes
    const embedding = await this.generateEmbedding(organism.content);
    const similar = await this.vectorSearch(embedding, {
      limit: 10,
      threshold: 0.7 // 70% similarity
    });
    // Filter to only high-fitness similar notes
    const highQuality = similar.filter(s => s.fitness.overallScore > 60);
    return highQuality.map(s => `[[${s.title}]]`);
  }
}
```
---
#### **MOC (Map of Content) Generation**
```typescript
class MOCGenerator {
  async generateMOC(cluster: Cluster): Promise<string> {
    // Create a Map of Content for each cluster
    const mocPrompt = `
Create a "Map of Content" (MOC) for this cluster:
CLUSTER: ${cluster.label}
THEME: ${cluster.theme}
NOTES IN CLUSTER (${cluster.organisms.length} total):
${cluster.organisms.map(o => `- [[${o.title}]] (fitness: ${o.fitness.overallScore})`).join('\n')}
Create an MOC that:
1. Introduces the theme (2-3 sentences)
2. Organizes notes into sub-themes
3. Shows progression (basics → advanced)
4. Highlights connections between notes
5. Identifies gaps or missing pieces
Format as Obsidian markdown with:
- Clear sections
- Bidirectional links [[like this]]
- Visual hierarchy (headers, bullets)
- Actionable "Start Here" section
Write the MOC now.
`;
    const moc = await this.callClaude(mocPrompt);
    return moc;
  }
  async createHomeDashboard(): Promise<string> {
    const clusters = await this.getAllClusters();
    const elites = await this.getEliteOrganisms();
    const mutations = await this.getMutations();
    const recentSyntheses = await this.getRecentSyntheses();
    const dashboard = `
## 🧬 Memetic Garden Dashboard
Last Updated: ${new Date().toISOString()}
Generation: ${await this.getCurrentGeneration()}
---
### 🌟 Elite Ideas (Top 20 by Fitness)
${elites.slice(0, 20).map((o, i) => 
  `${i+1}. [[${o.title}]] (fitness: ${o.fitness.overallScore}) - ${o.genes.categories.join(', ')}`
).join('\n')}
---
### 🗺️ Knowledge Clusters
${clusters.map(c => `
#### [[${c.label}]] (${c.organisms.length} notes)
${c.theme}
Top Notes:
${c.organisms.slice(0, 5).map(o => `- [[${o.title}]]`).join('\n')}
[[View Full MOC|${c.label}-MOC]]
`).join('\n')}
---
### 🧪 Recent Syntheses
New insights generated from recombination:
${recentSyntheses.map(s => `
#### [[${s.title}]]
Combined: [[${s.parents[0].title}]] + [[${s.parents[1].title}]]
${s.content.slice(0, 200)}...
`).join('\n')}
---
### 🦋 Mutations (Outliers)
Ideas that don't fit existing patterns (might be revolutionary):
${mutations.map(m => `
#### [[${m.title}]] (novelty: ${m.mutationScore})
${m.content.slice(0, 150)}...
`).join('\n')}
---
### 📊 Garden Statistics
- **Total Organisms**: ${await this.getTotalCount()}
- **Thriving** (fitness >70): ${await this.getThrivingCount()}
- **Stable** (fitness 40-70): ${await this.getStableCount()}
- **Declining** (fitness 20-40): ${await this.getDecliningCount()}
- **Archived this week**: ${await this.getArchivedCount()}
- **New syntheses this week**: ${recentSyntheses.length}
- **Master Prompt version**: ${await this.getMasterPromptVersion()}
---
### 🎯 Action Items
Based on this week's evolution:
${await this.generateActionItems()}
---
### 📖 Master Prompt
Current version: [[Master Prompt]] v${await this.getMasterPromptVersion()}
[View Full Master Prompt →](Master-Prompt.md)
[View Changelog →](Master-Prompt-Changelog.md)
---
*Garden maintained by Memetic Garden Evolution Engine*
*Next evolution cycle: ${await this.getNextEvolutionDate()}*
`;
    return dashboard;
  }
}
```
---
### **VIII. THE DASHBOARD** 📊
#### **Visual Knowledge Universe**
```typescript
interface Dashboard {
  // 1. Knowledge Graph Visualization
  graph: {
    type: "force-directed" | "hierarchical" | "circular";
    nodes: {
      id: string;
      label: string;
      size: number; // Based on fitness
      color: string; // Based on cluster
      type: "concept" | "technique" | "tool" | "insight";
    }[];
    edges: {
      source: string;
      target: string;
      type: "builds_on" | "contrasts_with" | "enables" | "similar_to";
      weight: number; // Strength of connection
    }[];
    interactions: {
      hover: "Show node details + connections";
      click: "Open note in Obsidian";
      doubleClick: "Focus on node neighborhood";
      drag: "Rearrange graph";
    };
  };
  // 2. Fitness Timeline
  fitnessOverTime: {
    chart: "Line chart showing fitness evolution";
    series: {
      avgFitness: number[];
      topDecileFitness: number[];
      newOrganisms: number[];
      archived: number[];
    };
    xAxis: Date[];
  };
  // 3. Cluster Map
  clusterMap: {
    type: "Voronoi diagram" | "Circle packing" | "Treemap";
    clusters: {
      id: string;
      label: string;
      size: number; // Number of organisms
      color: string;
      organisms: Organism[];
    }[];
  };
  // 4. Mutation Tracker
  mutationTracker: {
    outliers: Organism[];
    noveltyScore: number;
    reviewQueue: Organism[]; // Mutations awaiting human review
  };
  // 5. Master Prompt Viewer
  masterPromptViewer: {
    currentVersion: string;
    sections: Section[];
    recentChanges: Change[];
    stabilityTrend: number[]; // Is it stabilizing?
  };
  // 6. Activity Feed
  activityFeed: {
    recentAdditions: Organism[];
    recentSyntheses: Synthesis[];
    recentArchives: Organism[];
    fitnessChanges: FitnessChange[];
  };
  // 7. Search & Filter
  search: {
    semanticSearch: boolean; // Embedding-based
    filters: {
      fitnessRange: [number, number];
      clusters: string[];
      types: string[];
      dateRange: [Date, Date];
      status: string[];
    };
  };
}
```
---
#### **Dashboard UI (Obsidian Plugin)**
```typescript
// Obsidian plugin that renders interactive dashboard
class MemeticGardenPlugin extends Plugin {
  async onload() {
    // 1. Register view
    this.registerView(
      "memetic-garden-dashboard",
      (leaf) => new MemeticGardenView(leaf)
    );
    // 2. Add ribbon icon
    this.addRibbonIcon("dna", "Memetic Garden", () => {
      this.activateView();
    });
    // 3. Add commands
    this.addCommand({
      id: "evolve-garden",
      name: "Run Evolution Cycle",
      callback: () => this.runEvolution()
    });
    this.addCommand({
      id: "synthesize-insights",
      name: "Generate New Syntheses",
      callback: () => this.runSynthesis()
    });
    this.addCommand({
      id: "update-master-prompt",
      name: "Evolve Master Prompt",
      callback: () => this.evolveMasterPrompt()
    });
  }
  async activateView() {
    const { workspace } = this.app;
    let leaf = workspace.getLeavesOfType("memetic-garden-dashboard")[0];
    if (!leaf) {
      leaf = workspace.getRightLeaf(false);
      await leaf.setViewState({
        type: "memetic-garden-dashboard",
        active: true
      });
    }
    workspace.revealLeaf(leaf);
  }
}
class MemeticGardenView extends ItemView {
  async onOpen() {
    const container = this.containerEl.children[1];
    container.empty();
    // Render dashboard
    await this.renderDashboard(container);
  }
  async renderDashboard(container: HTMLElement) {
    // 1. Stats Cards
    const stats = await this.getStats();
    container.createDiv("stats-grid", (el) => {
      el.createDiv("stat-card", (card) => {
        card.createEl("h3", { text: "Total Organisms" });
        card.createEl("div", { text: stats.total, cls: "stat-value" });
      });
      el.createDiv("stat-card", (card) => {
        card.createEl("h3", { text: "Avg Fitness" });
        card.createEl("div", { text: stats.avgFitness, cls: "stat-value" });
      });
      el.createDiv("stat-card", (card) => {
        card.createEl("h3", { text: "This Week" });
        card.createEl("div", { text: `+${stats.newThisWeek}`, cls: "stat-value" });
      });
      el.createDiv("stat-card", (card) => {
        card.createEl("h3", { text: "Mutations" });
        card.createEl("div", { text: stats.mutations, cls: "stat-value" });
      });
    });
    // 2. Knowledge Graph (using D3.js)
    const graphContainer = container.createDiv("knowledge-graph");
    await this.renderGraph(graphContainer);
    // 3. Elite Ideas List
    const eliteContainer = container.createDiv("elite-ideas");
    await this.renderEliteIdeas(eliteContainer);
    // 4. Cluster Overview
    const clusterContainer = container.createDiv("clusters");
    await this.renderClusters(clusterContainer);
    // 5. Master Prompt Summary
    const promptContainer = container.createDiv("master-prompt");
    await this.renderMasterPromptSummary(promptContainer);
  }
  async renderGraph(container: HTMLElement) {
    // Use D3.js force-directed graph
    const data = await this.getGraphData();
    const width = container.clientWidth;
    const height = 600;
    const svg = d3.select(container)
      .append("svg")
      .attr("width", width)
      .attr("height", height);
    // Create force simulation
    const simulation = d3.forceSimulation(data.nodes)
      .force("link", d3.forceLink(data.links).id(d => d.id))
      .force("charge", d3.forceManyBody().strength(-100))
      .force("center", d3.forceCenter(width / 2, height / 2));
    // Draw links
    const link = svg.append("g")
      .selectAll("line")
      .data(data.links)
      .enter()
      .append("line")
      .attr("stroke", "#999")
      .attr("stroke-width", d => Math.sqrt(d.weight));
    // Draw nodes
    const node = svg.append("g")
      .selectAll("circle")
      .data(data.nodes)
      .enter()
      .append("circle")
      .attr("r", d => Math.sqrt(d.fitness) * 2)
      .attr("fill", d => this.getClusterColor(d.cluster))
      .call(d3.drag()
        .on("start", dragstarted)
        .on("drag", dragged)
        .on("end", dragended))
      .on("click", (event, d) => {
        // Open note in Obsidian
        this.app.workspace.openLinkText(d.label, "");
      });
    // Add labels
    const label = svg.append("g")
      .selectAll("text")
      .data(data.nodes)
      .enter()
      .append("text")
      .text(d => d.label)
      .attr("font-size", "10px")
      .attr("dx", 12)
      .attr("dy", 4);
    // Update positions on tick
    simulation.on("tick", () => {
      link
        .attr("x1", d => d.source.x)
        .attr("y1", d => d.source.y)
        .attr("x2", d => d.target.x)
        .attr("y2", d => d.target.y);
      node
        .attr("cx", d => d.x)
        .attr("cy", d => d.y);
      label
        .attr("x", d => d.x)
        .attr("y", d => d.y);
    });
  }
}
```
---
### **IX. MUTATION BUCKET** 🦋
#### **Outlier Detection**
```typescript
class MutationDetector {
  async detectMutations(): Promise<Mutation[]> {
    const allOrganisms = await this.getAllOrganisms();
    const embeddings = await this.generateEmbeddings(allOrganisms);
    // 1. Cluster with HDBSCAN (detects outliers)
    const clustering = await this.hdbscan(embeddings, {
      minClusterSize: 5,
      minSamples: 3
    });
    // 2. Organisms with clusterLabel = -1 are outliers
    const outliers = allOrganisms.filter((o, i) => 
      clustering.labels[i] === -1
    );
    // 3. Calculate mutation scores
    const mutations = await Promise.all(
      outliers.map(async o => {
        const score = await this.calculateMutationScore(o, allOrganisms);
        return {
          organism: o,
          mutationScore: score,
          reason: await this.explainMutation(o, allOrganisms)
        };
      })
    );
    // 4. Sort by mutation score
    return mutations.sort((a, b) => b.mutationScore - a.mutationScore);
  }
  async calculateMutationScore(
    organism: MemeticOrganism,
    population: MemeticOrganism[]
  ): Promise<number> {
    // Factors:
    // 1. Semantic distance from nearest neighbor (50%)
    const nearestDist = await this.getNearestNeighborDistance(organism, population);
    const distanceScore = Math.min(100, nearestDist * 100);
    // 2. Concept novelty (30%)
    const novelConcepts = organism.genes.concepts.filter(c => 
      !this.isCommonConcept(c, population)
    );
    const noveltyScore = (novelConcepts.length / organism.genes.concepts.length) * 100;
    // 3. Category rarity (20%)
    const rarityScore = this.calculateCategoryRarity(organism, population);
    return (
      distanceScore * 0.5 +
      noveltyScore * 0.3 +
      rarityScore * 0.2
    );
  }
  async explainMutation(
    organism: MemeticOrganism,
    population: MemeticOrganism[]
  ): Promise<string> {
    const explainPrompt = `
This idea has been flagged as a MUTATION (outlier) in the knowledge garden:
IDEA:
${organism.content}
Categories: ${organism.genes.categories.join(', ')}
Concepts: ${organism.genes.concepts.join(', ')}
CONTEXT (what's normal in the garden):
Common categories: ${this.getCommonCategories(population).join(', ')}
Common concepts: ${this.getCommonConcepts(population).join(', ')}
Why is this idea unusual? What makes it different from everything else?
Is this:
a) Revolutionary - Could spawn entirely new branch of knowledge
b) Interesting - Worth keeping, doesn't fit current patterns
c) Noise - Just random, not actually valuable
d) Misclassified - Actually fits somewhere but algorithm missed it
Explain in 2-3 sentences.
`;
    const explanation = await this.callClaude(explainPrompt);
    return explanation;
  }
}
```
---
#### **Mutation Review Dashboard**
```markdown
## 🦋 Mutation Bucket
Outlier ideas that don't fit existing patterns. Review monthly to decide:
- **Promote** to main garden (they're actually valuable)
- **Create new cluster** (this is a new species)
- **Archive** (it was just noise)
---
### High-Priority Mutations (Score >90)
#### [[Quantum Error Correction for Prompt Design]]
**Mutation Score**: 95
**Why Unusual**: Combines quantum computing terminology with LLM prompting (nobody else is doing this)
**Potential**: Could be revolutionary if the analogy is deep
**Action**: Test in next 10 prompts, evaluate results
#### [[Mycelial Networks as Knowledge Graph Metaphor]]
**Mutation Score**: 92
**Why Unusual**: Biological metaphor not commonly used in AI tooling
**Potential**: Interesting way to think about information flow
**Action**: Explore further, write synthesis note
---
### Medium Mutations (Score 70-90)
[Continue for all mutations]
---
### Monthly Review
Last reviewed: 2024-11-01
**Promoted to Main Garden**: 3 mutations
- [[Emergent Behavior in Agent Swarms]] - Created new cluster
- [[Reverse Prompting]] - Added to Prompting Techniques cluster
**Archived**: 8 mutations
- Deemed noise after review
**Still Pending**: 12 mutations
- Need more time to evaluate
---
```
---
### **X. IMPLEMENTATION ROADMAP** 🗺️
#### **Phase 1: Foundation (Weeks 1-2)**
```typescript
// MVP: Slack → Obsidian Pipeline
const mvp = {
  features: [
    "✅ Slack webhook integration",
    "✅ Message extraction and parsing",
    "✅ Claude-based content analysis",
    "✅ Basic markdown note generation",
    "✅ Concept extraction and linking",
    "✅ Simple fitness scoring",
    "✅ Obsidian file output"
  ],
  architecture: {
    slackListener: "Listen to specific channel",
    processor: "Extract content + metadata",
    analyzer: "Claude extracts concepts/techniques",
    noteGenerator: "Create markdown with frontmatter",
    fileWriter: "Write to Obsidian vault"
  },
  deliverable: "Working pipeline: Slack message → Obsidian note with links"
};
```
---
#### **Phase 2: Intelligence (Weeks 3-4)**
```typescript
const intelligence = {
  features: [
    "✅ Semantic similarity (embeddings)",
    "✅ Automatic bidirectional linking",
    "✅ Cluster detection (HDBSCAN)",
    "✅ Knowledge graph construction",
    "✅ MOC generation per cluster",
    "✅ Duplicate detection",
    "✅ Fitness calculation"
  ],
  deliverable: "Notes automatically find and link to each other; clusters emerge"
};
```
---
#### **Phase 3: Evolution (Weeks 5-6)**
```typescript
const evolution = {
  features: [
    "✅ Fitness-based selection",
    "✅ Weekly synthesis (recombination)",
    "✅ Mutation detection",
    "✅ Archive low-fitness notes",
    "✅ Master Prompt evolution",
    "✅ Generation tracking",
    "✅ Evolutionary reports"
  ],
  deliverable: "Self-improving knowledge garden that gets smarter over time"
};
```
---
#### **Phase 4: Dashboard (Weeks 7-8)**
```typescript
const dashboard = {
  features: [
    "✅ Obsidian plugin with visual dashboard",
    "✅ Interactive knowledge graph (D3.js)",
    "✅ Fitness timeline charts",
    "✅ Cluster visualization",
    "✅ Mutation review interface",
    "✅ Master Prompt viewer",
    "✅ Activity feed"
  ],
  deliverable: "Beautiful, interactive dashboard showing the living knowledge ecosystem"
};
```
---
#### **Phase 5: Polish (Weeks 9-10)**
```typescript
const polish = {
  features: [
    "✅ Notion sync (optional)",
    "✅ Twitter direct integration",
    "✅ Mobile notifications for mutations",
    "✅ Weekly email digest",
    "✅ Export to PDF/Markdown",
    "✅ API for programmatic access",
    "✅ Advanced search",
    "✅ Custom clustering algorithms"
  ],
  deliverable: "Production-ready knowledge evolution system"
};
```
---
### **XI. TECH STACK** 💻
```typescript
const techStack = {
  // Core
  backend: "Node.js + TypeScript",
  database: "PostgreSQL (Supabase) + pgvector",
  ai: "Claude Sonnet 4 (Anthropic API)",
  embeddings: "Voyage AI or OpenAI embeddings",
  // Integrations
  slack: "Slack SDK + Webhooks",
  obsidian: "Direct file system write + Obsidian plugin API",
  notion: "Notion API (optional)",
  twitter: "Twitter API v2 (if needed)",
  // Processing
  clustering: "HDBSCAN (Python via child_process or pure JS implementation)",
  graphDB: "Neo4j (optional) or pure pgvector",
  // Visualization
  dashboard: "Obsidian plugin (TypeScript)",
  graphViz: "D3.js force-directed graph",
  charts: "Chart.js or Recharts",
  // Deployment
  hosting: "Railway or Render (always-on service)",
  cron: "Node-cron for scheduled tasks",
  storage: "Local file system (Obsidian vault)",
  // Dev
  ide: "Cursor.sh (obviously 😎)",
  versionControl: "Git + GitHub"
};
```
---
### **XII. FILE STRUCTURE**
```
memetic-garden/
├── server/
│   ├── src/
│   │   ├── ingestion/
│   │   │   ├── slack-listener.ts
│   │   │   ├── twitter-integration.ts
│   │   │   └── content-extractor.ts
│   │   ├── intelligence/
│   │   │   ├── concept-extractor.ts
│   │   │   ├── semantic-similarity.ts
│   │   │   ├── clustering.ts
│   │   │   └── knowledge-graph.ts
│   │   ├── evolution/
│   │   │   ├── fitness-calculator.ts
│   │   │   ├── selection-engine.ts
│   │   │   ├── synthesis-engine.ts
│   │   │   ├── mutation-detector.ts
│   │   │   └── master-prompt-evolution.ts
│   │   ├── output/
│   │   │   ├── obsidian-writer.ts
│   │   │   ├── note-generator.ts
│   │   │   ├── moc-generator.ts
│   │   │   └── dashboard-data.ts
│   │   └── utils/
│   │       ├── anthropic-client.ts
│   │       ├── embeddings.ts
│   │       └── database.ts
│   ├── config/
│   └── types/
│       ├── organisms.ts
│       ├── clusters.ts
│       └── evolution.ts
├── obsidian-plugin/
│   ├── src/
│   │   ├── main.ts
│   │   ├── views/
│   │   │   ├── dashboard-view.ts
│   │   │   ├── graph-view.ts
│   │   │   └── mutation-review.ts
│   │   └── components/
│   │       ├── stats-cards.ts
│   │       ├── cluster-viz.ts
│   │       └── fitness-chart.ts
│   ├── styles.css
│   └── manifest.json
├── data/
│   ├── organisms.json
│   ├── clusters.json
│   ├── master-prompt.json
│   └── evolution-log.json
└── vault/ (Obsidian vault)
    ├── 00-Dashboard/
    │   ├── Home.md
    │   ├── Master-Prompt.md
    │   └── Mutation-Bucket.md
    ├── 01-Organisms/ (auto-generated notes)
    ├── 02-Clusters/ (MOCs)
    ├── 03-Syntheses/ (recombined insights)
    └── 04-Archive/ (archived notes)
```
---
### **XIII. FIRST 100 LINES OF CODE** 🚀
```bash
## In Cursor terminal
mkdir memetic-garden
cd memetic-garden
npm init -y
npm install @slack/bolt @anthropic-ai/sdk
npm install @supabase/supabase-js
npm install node-cron dotenv typescript tsx
## Create structure
mkdir -p server/src/{ingestion,intelligence,evolution,output}
mkdir -p server/types
## Start with Slack listener
```
```typescript
// server/src/ingestion/slack-listener.ts
import { App } from '@slack/bolt';
import Anthropic from '@anthropic-ai/sdk';
import { MemeticOrganism } from '../types/organisms';
export class SlackListener {
  private app: App;
  private anthropic: Anthropic;
  private channelId: string;
  constructor(channelId: string) {
    this.app = new App({
      token: process.env.SLACK_BOT_TOKEN,
      signingSecret: process.env.SLACK_SIGNING_SECRET,
      socketMode: true,
      appToken: process.env.SLACK_APP_TOKEN
    });
    this.anthropic = new Anthropic({
      apiKey: process.env.ANTHROPIC_API_KEY
    });
    this.channelId = channelId;
  }
  async start() {
    console.log('🧬 Memetic Garden listening to Slack...');
    // Listen to all messages in the channel
    this.app.message(async ({ message, say }) => {
      // @ts-ignore
      if (message.channel === this.channelId) {
        await this.processMessage(message);
      }
    });
    await this.app.start();
  }
  private async processMessage(message: any) {
    console.log(`📥 New message: ${message.text?.slice(0, 50)}...`);
    try {
      // 1. Extract content
      const content = await this.extractContent(message);
      // 2. Analyze with Claude
      const analysis = await this.analyzeContent(content);
      // 3. Create organism
      const organism = await this.createOrganism(message, content, analysis);
      // 4. Generate Obsidian note
      await this.generateNote(organism);
      console.log(`✅ Processed: ${organism.id}`);
    } catch (error) {
      console.error('❌ Error processing message:', error);
    }
  }
  private async extractContent(message: any): Promise<string> {
    let content = message.text || '';
    // Extract links
    if (message.attachments) {
      for (const attachment of message.attachments) {
        if (attachment.title_link) {
          // Fetch article content if it's a URL
          content += `\n\n[Link: ${attachment.title_link}]`;
        }
      }
    }
    return content;
  }
  private async analyzeContent(content: string): Promise<Analysis> {
    const prompt = `
Analyze this content saved to a knowledge garden:
CONTENT:
${content}
Extract structured information:
{
  "type": "tool" | "insight" | "research" | "tip" | "design" | "prompt_pattern",
  "categories": ["array", "of", "tags"],
  "concepts": ["Core Concepts"],
  "techniques": ["Specific techniques mentioned"],
  "summary": "One sentence summary",
  "novelty": 0-100,
  "actionable": true/false,
  "connections": ["Concepts this might relate to"]
}
Return ONLY valid JSON, no markdown.
`;
    const response = await this.anthropic.messages.create({
      model: 'claude-sonnet-4-20250514',
      max_tokens: 1000,
      messages: [{ role: 'user', content: prompt }]
    });
    const text = response.content[0].text;
    return JSON.parse(text);
  }
  private async createOrganism(
    message: any,
    content: string,
    analysis: Analysis
  ): Promise<MemeticOrganism> {
    return {
      id: `mem_${Date.now()}_${Math.random().toString(36).slice(2, 9)}`,
      type: analysis.type,
      content,
      source: {
        platform: 'slack',
        url: message.permalink || '',
        timestamp: new Date(parseFloat(message.ts) * 1000),
        originalPoster: message.user
      },
      fitness: {
        referenceCount: 0,
        synthesisCount: 0,
        applicationCount: 0,
        lastAccessed: new Date(),
        decayRate: 0.1,
        overallScore: 50 // Baseline
      },
      genes: {
        categories: analysis.categories,
        concepts: analysis.concepts,
        techniques: analysis.techniques,
        relationships: [],
        ancestors: [],
        descendants: []
      },
      mutationScore: analysis.novelty,
      clusterAssignment: 'unassigned',
      generation: 1,
      birthDate: new Date(),
      lastMutation: new Date(),
      status: 'stable'
    };
  }
  private async generateNote(organism: MemeticOrganism) {
    // Generate markdown note
    // Write to Obsidian vault
    // (Implementation in next phase)
  }
}
// Start listening
const listener = new SlackListener(process.env.SLACK_CHANNEL_ID!);
listener.start();
```
---
### **🌟 THE MAGIC** ✨
This system is transcendent because:
1. **You never lose anything valuable** - Selection pressure ensures quality rises
2. **Ideas connect themselves** - Semantic linking finds relationships you'd miss
3. **Knowledge compounds** - Synthesis creates insights you couldn't have alone
4. **Evolution never stops** - The garden gets smarter as you add more
5. **Master Prompt evolves** - Your coding wisdom distills automatically
6. **Outliers are preserved** - Revolutionary ideas don't get lost
7. **Zero manual curation** - The system curates itself through fitness
8. **Obsidian becomes alive** - Your second brain actually thinks
**This isn't just note-taking. It's knowledge cultivation.** 🧬
---
### **🚀 NEXT STEPS**
Use Cursor Composer:
> "Build the complete Slack listener that watches a channel, extracts content, analyzes it with Claude, generates structured organisms, and writes Obsidian markdown notes with automatic bidirectional linking. Include all types, error handling, and logging."
Then:
> "Build the fitness calculator that scores organisms based on references, syntheses, applications, and recency. Include decay over time."
Then:
> "Build the weekly evolution cycle that runs selection, creates syntheses by combining high-fitness organisms, detects mutations, and generates a report."
**And watch your Slack chaos become a living knowledge organism.** 🌱
Ready to plant the first seed? 🐝🫵🏼