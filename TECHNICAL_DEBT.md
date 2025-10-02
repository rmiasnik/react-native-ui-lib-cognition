# Technical Debt & Future Improvements

This document tracks technical debt items and planned improvements identified during code quality reviews.

## High Priority (Next Sprint)

### 1. Address React Hooks ESLint Warnings
- **Status**: 100+ warnings across codebase
- **Issue**: Missing dependencies in `useEffect`, `useCallback`, and `useMemo` hooks
- **Risk**: Could cause subtle bugs and stale closures
- **Affected Files**: TabController, Picker, Carousel, and 20+ other components
- **Action**: Systematically review and fix hook dependencies, test thoroughly
- **Estimated Effort**: 2-3 days

### 2. Improve Test Coverage
- **Current**: Services (50%), Design Tokens (0%), some components (<60%)
- **Target**: 80%+ coverage across all critical paths
- **Focus Areas**:
  - LogService and HapticService (currently 50%)
  - Design tokens (currently 0%)
  - Components with <60% coverage
- **Estimated Effort**: 1-2 weeks

## Medium Priority (Next Quarter)

### 3. React Native 0.77 Upgrade
- **Current**: 0.73.9
- **Target**: 0.77.x (as noted in README)
- **Blockers**: New Architecture support needed
- **Requirements**: Thorough testing, update peer dependencies
- **Estimated Effort**: 2-3 weeks

### 4. TypeScript Strict Mode
- **Current**: Loose TypeScript configuration
- **Target**: Enable strict mode progressively
- **Benefits**: Better type safety, catch more bugs at compile time
- **Action**: Enable strict flags incrementally, fix type errors
- **Estimated Effort**: 2-3 weeks

### 5. Update Major Dependencies
- **react**: 18.2.0 → 19.2.0
- **@testing-library/react-native**: 11.5.4 → 13.3.3
- **react-native-reanimated**: 3.16.7 → 4.1.2
- **react-native-gesture-handler**: 2.14.1 → 2.28.0
- **Requirements**: Test thoroughly, update to new APIs if needed
- **Estimated Effort**: 1-2 weeks per major dependency

## Low Priority (Future)

### 6. ESLint 9.x Migration
- **Current**: 8.57.0
- **Target**: 9.x
- **Breaking Changes**: Flat config format, plugin API changes
- **Requirements**: Update all plugins, migrate config format
- **Estimated Effort**: 1 week

### 7. E2E Testing Setup
- **Current**: Unit tests only
- **Target**: Add E2E tests for critical user flows
- **Tool Options**: Detox (already in related repos), Maestro, or Appium
- **Estimated Effort**: 2-3 weeks

### 8. Performance Monitoring
- **Current**: Manual performance testing with reassure
- **Target**: Automated performance regression detection in CI
- **Requirements**: Baseline performance metrics, automated comparisons
- **Estimated Effort**: 1 week

## Code Style Improvements

### 9. Address Disabled ESLint Rules
- **Current**: Several rules disabled in .eslintrc.js
  - `no-trailing-spaces`: 'off'
  - `operator-linebreak`: 'off'
  - `new-cap`: ['off'] with TODO comment
- **Action**: Fix violations and re-enable rules
- **Estimated Effort**: 2-3 days

### 10. Line Length Violations
- **Current**: ~20 files exceed 120 character limit
- **Action**: Refactor long lines, possibly adjust limit if needed
- **Estimated Effort**: 1-2 days

## Monitoring & Process

### 11. Coverage Reporting
- **Current**: Coverage runs locally only
- **Target**: Automated coverage reporting in CI with Codecov/Coveralls
- **Benefits**: Track coverage trends over time, prevent regressions
- **Status**: CI workflow created, need to set up Codecov token

### 12. Dependency Update Automation
- **Current**: Manual updates
- **Target**: Automated PRs with Renovate or Dependabot
- **Benefits**: Stay up-to-date automatically, security patches
- **Estimated Setup**: 1-2 hours

---

Last Updated: October 2025
Contributors: Code Review Team
