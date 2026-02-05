# Topic Guide Template

Use this template when creating detailed guides for individual learning topics. Each topic should be comprehensive yet focused on practical, actionable information.

## Template Structure

```markdown
# [Topic Number]: [Topic Name]

**Category:** [Foundations/Intermediate/Advanced/Day-to-Day/Modernization/Quality/etc.]
**Prerequisites:** [List required prior knowledge, or "None" for foundation topics]
**Estimated Learning Time:** [Optional: e.g., "30 minutes", "1-2 hours"]

## Overview

[2-3 sentences that answer:
- What is this topic about?
- Why does it matter?
- What will the learner be able to do after completing this?]

## Key Concepts

[Break down the main ideas into digestible sections. Use subheadings for clarity.]

### Concept 1: [Name]
[Explanation of the concept - what it is, why it exists, when to use it]

**Example:**
```[language]
[Clear, runnable code example demonstrating the concept]
```

**Explanation:** [Walk through what the example shows]

### Concept 2: [Name]
[Continue pattern for each major concept]

## Practical Examples

[Real-world scenarios that demonstrate how these concepts work together]

### Example 1: [Scenario Name]
**Problem:** [Describe the real-world problem]
**Solution:** [Show how the concepts solve it]

```[language]
[Code example]
```

**Why this works:** [Explain the approach and key decisions]

### Example 2: [Scenario Name]
[Continue pattern for 2-3 practical examples]

## Common Patterns

[Frequently used patterns or idioms related to this topic]

### Pattern 1: [Pattern Name]
**When to use:** [Scenarios where this pattern applies]
**How it works:** [Brief explanation]

```[language]
[Code example]
```

### Pattern 2: [Pattern Name]
[Continue for common patterns]

## Best Practices

[Current recommendations and things to watch out for]

**Do:**
- [Recommended practice with brief explanation]
- [Another recommended practice]

**Avoid:**
- [Anti-pattern or common mistake with explanation]
- [Another thing to avoid]

**Modern Approaches (2025-2026):**
- [Current best practices or new patterns]
- [Tools or techniques that have become standard]

## Common Pitfalls

[Mistakes learners often make with this topic]

### Pitfall 1: [Name]
**What happens:** [Description of the mistake]
**Why it's wrong:** [Explanation]
**How to fix:** [Correct approach]

### Pitfall 2: [Name]
[Continue pattern]

## Related Topics

[Links to other topics in the learning path]

- **Prerequisites:** [Topics that should be learned before this]
- **Builds on:** [Topics this extends or relates to]
- **Next steps:** [Topics to learn after mastering this]

## Additional Resources

[Optional: Links to external resources]

- [Official documentation]
- [Tutorial or article]
- [Video or interactive resource]

**Note:** These are supplementary - the guide should be complete without external resources.

---

## Progress Tracking

**You've completed topic [X] of [Total]**

### Quick Self-Check
Answer these to verify understanding:
1. [Key question about main concept]
2. [Question about practical application]
3. [Question about when to use/avoid this approach]

### What's Next?

[Provide a clear recommendation based on the learning path]

**Suggested next topic:** [Topic Number and Name]

**Or choose your own path:**
- [Alternative relevant topic]
- [Another alternative]
- Return to main menu to see all topics

---

**Need help?** Describe what you're trying to accomplish, and I'll help you find the right topic or provide additional examples.
```

## Content Guidelines

### 1. Clarity Over Comprehensiveness

- Focus on understanding, not encyclopedic coverage
- Use clear, simple language
- Define technical terms on first use
- Break complex concepts into smaller pieces

### 2. Show, Don't Just Tell

- Every concept should have a code example
- Examples should be realistic and runnable
- Explain *why* the code works, not just what it does
- Use comments sparingly - prefer clear variable names

### 3. Progressive Complexity

- Start with the simplest case
- Add complexity incrementally
- Explain what each addition accomplishes
- Show both basic and realistic examples

### 4. Practical Focus

- Emphasize when/why to use something, not just how
- Include real-world scenarios
- Discuss trade-offs and alternatives
- Address common use cases explicitly

### 5. Current and Accurate

- Use 2025-2026 best practices
- Mention if older patterns are deprecated
- Include modern tooling and approaches
- Reference current version numbers when relevant

## Length Guidelines

- **Foundations topics:** 800-1500 words
  - More explanation, simpler examples
  - Build understanding carefully
  - Assume no prior knowledge

- **Intermediate topics:** 1000-2000 words
  - Assume foundation knowledge
  - More complex examples
  - Focus on practical application

- **Advanced topics:** 1500-2500 words
  - Deep dives into complex patterns
  - Multiple realistic scenarios
  - Performance considerations
  - Architecture and design decisions

- **Use case guides:** 1000-1800 words
  - Focused on specific scenario
  - End-to-end examples
  - Integration of multiple concepts
  - Production considerations

## Code Example Guidelines

### Good Code Examples

```javascript
// Good: Clear purpose, realistic scenario
function calculateTotalPrice(items, discountCode) {
  const subtotal = items.reduce((sum, item) => sum + item.price, 0);
  const discount = getDiscountAmount(subtotal, discountCode);
  return subtotal - discount;
}
```

**Why this is good:**
- Realistic function name and parameters
- Clear business logic
- Shows a real pattern (array reduction)
- Could exist in production code

### Avoid

```javascript
// Avoid: Contrived, no context
function foo(arr) {
  return arr.map(x => x * 2);
}
```

**Why to avoid:**
- No context for why you'd do this
- Meaningless names (foo, arr, x)
- Doesn't teach when to use this pattern
- Feels academic, not practical

## Adaptation Based on Difficulty

### Foundations Topics

- **More scaffolding:** Explain concepts step-by-step
- **Simpler examples:** Focus on one thing at a time
- **More context:** Explain why things exist
- **Less assumption:** Define everything

Example:
```markdown
### What is a Variable?

A variable is a container that stores a value. Think of it like a labeled box where you can put information and retrieve it later.

```javascript
// Creating a variable named "age" and storing the number 25
const age = 25;
```

The `const` keyword tells JavaScript we're creating a variable that won't change...
```

### Intermediate Topics

- **Less scaffolding:** Assume foundation concepts known
- **Combined concepts:** Show multiple ideas working together
- **More choices:** Present alternatives and trade-offs
- **Pattern focus:** Emphasize when/why to use patterns

Example:
```markdown
### Managing Asynchronous State

When fetching data, you need to handle loading, success, and error states. Here's a common pattern:

```javascript
const [data, setData] = useState(null);
const [loading, setLoading] = useState(false);
const [error, setError] = useState(null);

// This pattern ensures consistent state management
```

**Why three separate states?** This gives you fine-grained control...
```

### Advanced Topics

- **Minimal scaffolding:** Dive into complex scenarios
- **Architecture focus:** Discuss design decisions
- **Performance:** Consider optimization and trade-offs
- **Production:** Address real-world constraints

Example:
```markdown
### Optimizing React Renders with Memoization

In large applications, unnecessary re-renders can cause performance issues. React provides several memoization strategies:

```javascript
// Component-level memoization
const ExpensiveComponent = React.memo(({ data, onUpdate }) => {
  // Only re-renders if data or onUpdate change
  return <ComplexVisualization data={data} />;
});

// Value memoization
const processedData = useMemo(() => {
  return heavyComputation(rawData);
}, [rawData]);
```

**When to use each approach:** `React.memo` prevents component re-renders...
```

## Interactive Elements

### Self-Check Questions

Include 3-5 questions that verify understanding:

```markdown
### Quick Self-Check

1. **When should you use [concept]?**
   - [Hint: Think about the scenarios where...]

2. **What's the difference between [A] and [B]?**
   - [Hint: Consider their use cases...]

3. **Why might you choose [pattern] over [alternative]?**
   - [Hint: Think about trade-offs...]
```

### Practice Suggestions

Offer concrete exercises:

```markdown
### Try It Yourself

**Exercise 1:** Modify the example above to [variation]
**Exercise 2:** Build a [small project] using these concepts
**Challenge:** Implement [complex scenario] without looking at the solution
```

## Consistency Across Topics

### Maintain consistent structure

All topics in a learning path should follow the same general structure so users know what to expect.

### Use consistent terminology

If you call something "components" in one topic, don't call them "modules" in another.

### Reference previous topics

```markdown
Remember from Topic 03 (State Management) that...
This builds on the concept of [X] we covered earlier...
```

### Link to related topics

```markdown
For more on [concept], see Topic 07 (Advanced Patterns)
If this seems complex, revisit Topic 02 (Foundations)
```

## Summary Checklist

Before finalizing a topic guide, verify:

- [ ] Clear overview that states what learner will gain
- [ ] Prerequisites are accurate and listed
- [ ] Each key concept has a code example
- [ ] Examples are realistic and runnable
- [ ] Practical examples show real-world scenarios
- [ ] Best practices are current (2025-2026)
- [ ] Common pitfalls are addressed
- [ ] Related topics are linked
- [ ] Progress tracking and next steps included
- [ ] Self-check questions verify understanding
- [ ] Length is appropriate for topic complexity
- [ ] Code examples follow quality guidelines
- [ ] Terminology is consistent with other topics
