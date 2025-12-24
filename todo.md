## System pipeline
User uploads dashboard image
          ↓
YOLO runs → detects rule violations
          ↓
Send: (image + detected rules) → LLaVA
          ↓
LLaVA generates explanation + recommendation
          ↓
Return result to user

## There are rules for non-compliant:

S1 Axis not zero

S2 Unequal tick spacing

S3 Distorted range

S4 Missing axis labels

S5 Dual Y misuse

## Already done with YOLO
Train arround 150 picture both Ok_NoIssue and S1_AxisNotTrue -> results quite good, not perfect (arround 60%) can be improve by adding more data but it can be done later.

Later can extend to S2–S5 the same way. (optional)

## Start with VLM
### Add a VLM as the “Reasoning + Recommendation” Brain
Input to VLM:

- dashboard image

- YOLO detected rule(s)

Output:

- compliant / non-compliant

- issue explanation

- recommended fix

- (optional) example guidance


## Optionally Explore Research Papers

From teacher:

- download pretrained chart-reasoning models from the papers

- just run inference on some charts (no training needed)

- compare how they behave vs your system

- note whether mistakes are perception vs reasoning

=>This is only optional but gives academic value.