# This is a test environment for the NCAE Cyber Games competition. 

## Please be aware that this environment has over 14 machines, not which need to all run concurrently, but scale at your own desire. 

## All of the necessary information and files will have their documentation provided in each section, there may or may not be mistakes. I would appreciate any corrections if found. 

---

# Scoring Engine 

For this scoring engine I used this repository: `https://github.com/scoringengine/scoringengine` which provides a fully fledged scoring engine and checks. I made the following changes to the competition configuration file which I will leave under the scoring engine file in this repository. 

Steps: 
1. Install Make && Git
2. Git clone the repository provided above and start the original scoring engine with `docker compose up -d`
3. Replace the original competition configuration file `scoring-engine/bin/competition.yaml` with the one provided in this repository in the `scoreengine` directory
4. Run the command in the base directory of the original scoring engine repository `make rebuild-new`

