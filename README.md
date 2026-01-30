# PDIntervu

PDIntervu is an intelligent technical interview assessment system that conducts structured competency evaluations using a multi-actor, multi-mode architecture. The system evaluates candidates across Elixir language topics, functional programming patterns, and data structures using rubric-based assessments.

## Architecture

PDIntervu uses a **3-mode-6-actor** pattern:

### Modes

1. **Cognitive Understanding Mode** - Evaluates conceptual understanding and theoretical knowledge
2. **Code Problem Mode** - Assesses practical coding and problem-solving skills
3. **Coaching Mode** - Provides guidance and feedback (invalidates assessment when entered)

### Actors

Each mode has two actors with different technical backgrounds:

- **Cognitive Understanding Mode**: Alex (Senior Software Engineer) & Marcus (Principal Engineer)
- **Code Problem Mode**: Jordan (Backend Engineer) & Ryan (Systems Architect)
- **Coaching Mode**: Samantha (Senior Technical Interviewer) & David (Engineering Manager)

## Assessment System

The system uses rubric-based assessments with three competency levels:

- **Not Yet Ready** - Candidate needs more development
- **Competent** - Candidate meets the requirements
- **Exceptional** - Candidate exceeds expectations

### Rubrics

- `data_structure_rubic.jsonld` - Assessment criteria for data structures competency
- `patterns_rubric.jsonld` - Assessment criteria for design patterns competency
- `final_assessment_rubric.jsonld` - Aggregation rules for overall assessment

## File Structure

```
PDIntervu/
├── PDIntervu.jsonld              # Main agent definition and execution instructions
├── data_structure_rubic.jsonld    # Data structures assessment rubric
├── data_structures_pseudocode.jsonld  # Pseudocode examples for data structures
├── patterns_rubric.jsonld         # Design patterns assessment rubric
├── patterns.jsonld                # Pattern definitions and examples
├── final_assessment_rubric.jsonld # Final assessment aggregation rules
├── pseudocode_primer.jsonld       # Pseudocode primer and guidelines
└── PDIntervu-build-log.md         # Decision log and development history
```

## Features

- **Flexible Mode Switching**: Users can switch between modes at any time
- **Independent Assessment**: Each actor maintains an independent perspective
- **Comprehensive Logging**: 
  - Markdown session logs (`<topic>_log.md`)
  - JSON-LD session logs (`<topic>_log.jsonld`)
  - Persistent competency tracking table
- **Assessment Invalidation**: Entering Coaching Mode or simulation requests invalidate the assessment
- **Time Tracking**: Monitors interview duration and time spent in each mode

## Usage

The system is designed to be executed as an AALang prompt. When loaded, the PDIntervu agent will:

1. Display initial instructions
2. Ask the user to select a competency topic
3. Conduct the interview using the appropriate mode and actors
4. Generate assessments based on the rubrics
5. Provide a final hire/no-hire recommendation

## Technical Details

- **Format**: JSON-LD (JSON for Linking Data)
- **Vocabulary**: Uses AALang.org specification (`https://aalang.org/spec/`)
- **State Management**: Shared state across modes for coordination
- **Assessment Logic**: Rubric-based with aggregation rules

## License

This project is licensed under a custom "No-Sale License" that:

- ✅ Allows commercial use (companies can use it in their operations)
- ✅ Allows educational use
- ✅ Allows modification and distribution
- ❌ Prohibits selling the software or any derivative works

See the [LICENSE](LICENSE) file for full details.

