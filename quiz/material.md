# 📋 iOS Client Interview – Prep Summary

This will be your **first meeting with the actual client team**, likely including:
- iOS Tech Lead  
- Project Manager  
- VP of Engineering

Expect the interview to last **~1 hour**, in **English**, with a mix of technical, architectural, and process-oriented questions.

---

## 🟣 1. General Experience

- Overview of your iOS development career
- Types of apps you've built (e.g., consumer, enterprise)
- Team size, structure, and collaboration model
- Development process (Agile/Scrum, tools used)
- Code quality practices:
  - Code reviews
  - Test coverage
  - Pull request workflow
- Experience with:
  - Pair programming
  - TDD (Test-Driven Development)
- Handling App Store rejections and Apple support interactions

---

## 🟡 2. Project Management & Workflow

- Context switching and multitasking
- Managing deadlines and overlapping responsibilities
- Prioritization techniques and focus strategies

---

## 🔵 3. Working in Challenging Environments

- Strategies for dealing with:
  - Legacy codebases
  - Unstructured environments
  - Solo development with no test coverage
- Refactoring and incremental improvements
- Navigating unknown code responsibly

---

## 🟢 4. Testing & Code Quality

- Unit testing practices (XCTest or others)
- Test structure and organization
- Use of mocking techniques (manual or library-based)
- Dependency injection:
  - Constructor injection
  - Factories / Environment injection
  - Singletons: usage and alternatives

---

## 🟠 5. Swift vs Objective-C

- Preference and justification (Swift vs ObjC)
- Key language differences:
  - Enums
  - Optionals
  - Type safety
- Integration experience:
  - Bridging between Swift and Objective-C
  - Calling C/C++ from Swift when needed

---

## 🔴 6. Concurrency & Performance

- Experience with:
  - Async/Await
  - Combine
  - DispatchQueue / DispatchGroup
  - NSOperationQueue
  - Semaphores (and when to avoid them)
- Swift concurrency:
  - Actors and value isolation
  - Choosing the right concurrency model

---

## 🟤 7. Memory Management

- Value types vs. reference types:
  - Use cases
  - Tradeoffs in performance and readability
- ARC basics and edge cases
- Alternatives to reference types (structs, actors)
- Access-time and mutability considerations

---

## ⚪ 8. SDKs & Libraries

- Experience integrating SDKs (e.g., Firebase, Stripe)
- Building internal reusable SDKs/modules
- Static vs. dynamic libraries:
  - Build size
  - Runtime performance
  - Update strategies

---

## ⚫ 9. macOS vs iOS Development

- Differences in:
  - Lifecycle and UI frameworks (UIKit vs AppKit)
  - Background execution
  - File system and sandboxing
- Experience with:
  - Catalyst
  - Shared codebases for multiplatform apps

---

## 🟡 10. App Lifecycle & Background Processes

- Changes introduced post iOS 13:
  - SceneDelegate
  - Multitasking and state restoration
- Use of:
  - Background modes (e.g., location, audio)
  - Push Notification Extensions
  - App Extensions (and communication with the main app)
- Background execution timing:
  - Location tracking vs. music playback
  - Power and system constraints
- Knowledge of:
  - Network Extensions (if applicable)
  - System background policies

---

## ✅ 11. Architecture Principles (especially emphasized)

- Deep understanding of **SOLID principles**
- How you apply:
  - Single Responsibility
  - Open/Closed
  - Liskov Substitution
  - Interface Segregation
  - Dependency Inversion
- Real-world examples of applying architecture patterns in modular projects

---

## 📎 Additional Preparation

- Review blog link from Danijela *(optional)*
- Study provided **PDF questions in depth** (primary prep focus)
- Prepare examples and anecdotes from your past projects
- Practice technical vocabulary and fluent self-expression in English

### 🔍 Blog Summary: “Managing Dependencies – Beyond the Basics” by Kean Wong

**Link:** [https://kean.blog/post/dependency-injection-beyond](https://kean.blog/post/dependency-injection-beyond)

The article explores advanced dependency management in Swift, focusing on clarity, testability, and composability — all of which are aligned with modern architecture practices.

---

### 💡 Core Concepts

#### 1. Avoiding Overengineering
- Prefer simple **constructor injection** over complex containers or service locators.
- Always pass dependencies explicitly — avoid hiding them behind singletons or global access.

#### 2. Factories and Initializers
- Use factories when:
  - Multiple instances are needed
  - Lazy instantiation is required
  - You need internal logic to decide what to create
- Otherwise, prefer injecting already-initialized objects.

#### 3. Environment Pattern
- Inspired by SwiftUI’s `EnvironmentValues`.
- Use a plain struct to group dependencies:
  ```swift
  struct Environment {
	  var analytics: AnalyticsClient
	  var dateProvider: () -> Date
	  var uuidProvider: () -> UUID
  }
  
  