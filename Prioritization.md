# Kano Prioritization Method

This report uses the Kano prioritization framework to classify the corrective findings identified in the baseline report.

Each finding is assigned to one of the following categories:

- Basic Needs – Essential improvements that users expect. Failure to address these issues results in dissatisfaction and negatively affects the overall user experience.
- Performance – Improvements where increased performance directly leads to greater user satisfaction. The better these aspects are optimized, the better the user experience.
- Delighters – Enhancements that provide additional value beyond user expectations but are not considered essential.

Unlike numeric prioritization methods, the Kano model classifies findings according to their influence on user satisfaction rather than calculating a numerical score.

## Corrective Finding Classification

| Finding | Kano Category | Justification |
|---------|---------------|---------------|
| Finding 1 – Very Large Network Payload | Basic Need | A total resource size of approximately 36.6 MB significantly increases loading times, particularly for users on slower networks. Reducing the initial payload is essential for acceptable website performance. |
| Finding 2 – Excessive JavaScript Blocking | Basic Need | Heavy JavaScript execution contributes directly to long blocking times and delayed interactions, preventing the website from responding quickly to user input. |
| Finding 3 – Extremely High Number of Network Requests | Performance | Reducing the number of requests improves loading efficiency and lowers network overhead, resulting in faster page loads and better overall responsiveness. |
| Finding 4 – Images Dominate the Download Size | Performance | Optimizing image delivery reduces bandwidth usage and improves loading performance, particularly for users on mobile devices or slower connections. |
| Finding 5 – Heavy Dependence on Third-Party Resources | Performance | Reducing reliance on external advertising, analytics, and tracking services improves stability and decreases the likelihood of performance degradation caused by third-party providers. |

## Priority Summary

### Basic Needs (Highest Priority)

1. Very Large Network Payload
2. Excessive JavaScript Blocking

These findings directly affect loading speed, responsiveness, and overall usability. Addressing these issues is essential to provide an acceptable user experience before focusing on additional performance optimizations.

### Performance (Medium Priority)

3. Images Dominate the Download Size
4. Extremely High Number of Network Requests
5. Heavy Dependence on Third-Party Resources

These findings improve performance beyond the basic level expected by users. Optimizing these areas enhances loading efficiency, reduces bandwidth usage, and improves the overall browsing experience.

### Delighters

No corrective findings were classified as Delighters.

The identified findings focus on resolving existing performance deficiencies rather than introducing additional features or enhancements beyond user expectations. The primary objective is to meet fundamental performance requirements before considering improvements that would provide additional value.
