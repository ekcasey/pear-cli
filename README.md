# pear-cli

`pear` is a command-line tool for pair suggestion and rotation management used by software development teams that practice [pair programming](https://en.wikipedia.org/wiki/Pair_programming). In this programming exercise you will start to implement `pear`'s core functionality. After you have [set up your development environment](#setting-up-your-development-environment), you should spend around 4 hours implementing the features described in the stories outlined below. These stories are not designed to all be completed in full within the given time frame, but rather to let us know how you write code and approach a problem. We encourage you to try to [test drive](https://en.wikipedia.org/wiki/Test-driven_development) your code and have included a sample test setup in this repository to help you get started. If you would like to use any alternative testing frameworks or libraries please feel free to do so. When you come to a stopping point please follow the instructions below for [submitting your solution](#submitting-your-solution).


## Setting up your development environment

Ensure you have the following programs installed and on your `PATH`:

- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

Clone this repository and run the setup script:

```
git clone https://github.com/ekcasey/pear-cli
cd pear-cli
<run setup script>
```

You are now ready to build `pear`:

```
<run build script>
<simple pear command>
```

And run the `pear` tests:

```
<run test script>
```

## Stories

The items in the list below describe "stories" or incremental pieces of functionality that present value to users who in this case are the engineering teams that want to utilize `pear` to manage their pair programming rotations. The stories are written from the perspective of the user and include acceptance criteria to help us define how successful we are in delivering the requested features. The features of `pear` described here are intended to be built step by step and in the order they are presented. As mentioned earlier, test driving the code you write is recommended. Including tests can help ensure your implementation is well organized, can serve as documentation, demonstrate that requirements are met, and make certain that edge cases are taken care of. 

**Note:** If there are any additional requirements that you think are helpful or required as part of implementing these stories, feel free to note them down in the corresponding story descriptions.

### 1. As a member of a team that pair programs, I can use `pear` to generate a set of team pairs for the day

**Motivation**

Engineering teams that pair program want a tool to generate team pairs for them because picking pairs manually each morning can become cumbersome. It is often hard to decide and rotate pairs in a manner that promotes knowledge sharing within the team.

**Acceptance Criteria**

*When* I build the `pear`binary and place a file with the below contents in `~/.pear/team.yml`

```
---
team:
- name: Dave
- name: Nicole
- name: Remy
- name: Paul
- name: Emily
```

*And* I run `pear up`

I see output on the command line of the format:

```
Emily
Dave

Remy
Nicole

Paul
```

### 2. As a member of a team that pair programs, I can view the current pairs and generate a new set

**Motivation**

Users find it helpful to view the current set of pairs during the day and before generating new pairs. In addition, pair rotation is a common practice in order to share context and exposure within a team. `pear` should allow users to shuffle pairs from day to day.

**Acceptance Criteria**

*When* I run `pear up` twice

I see different pairs output to the command line each time

*And*

*When* I run `pear show`

I see the output of the latest `pear up` command is output to the command line

### 3. As a member of a team that pair programs, I can exclude someone from the pair selection when generating a set of pairs

**Motivation**

When a member of the team is absent and unable to pair (due to sickness, on a business trip, etc.) users would like to not include them in the generated pairs for the day.

**Acceptance Criteria**

*Given* my `pear` team file has the following content:

```
---
team:
- name: Dave
- name: Nicole
- name: Remy
- name: Paul
- name: Emily
```

*When* I run `pear up --absent Nicole,Paul`

I see that Paul and Nicole are not included in the list of pairs output to the command line

### 4. As a member of a team that pair programs, I can edit the generated set of pairs before committing them

**Motivation**

Generating pairs automatically is not alway desirable, sometimes manual intervention by users is required to fulfill certain pairing requirements. As such, users should be able to modify the generated pairs before they get set for the day.

**Acceptance Criteria**

*When* I run `pear up --edit`

I am presented with file in an editor with the day's generated pairs

*And*

*When* I edit, save, and close the file and then run `pear show`

I see my edits were reflected in the day's list of pairs

## Submitting your solution

**Coming Soon**
