# BATCH_STEP_EXECUTION

## Description

<details>
<summary><strong>Table Definition</strong></summary>

```sql
CREATE TABLE `BATCH_STEP_EXECUTION` (
  `STEP_EXECUTION_ID` bigint NOT NULL,
  `VERSION` bigint NOT NULL,
  `STEP_NAME` varchar(100) NOT NULL,
  `JOB_EXECUTION_ID` bigint NOT NULL,
  `CREATE_TIME` datetime(6) NOT NULL,
  `START_TIME` datetime(6) DEFAULT NULL,
  `END_TIME` datetime(6) DEFAULT NULL,
  `STATUS` varchar(10) DEFAULT NULL,
  `COMMIT_COUNT` bigint DEFAULT NULL,
  `READ_COUNT` bigint DEFAULT NULL,
  `FILTER_COUNT` bigint DEFAULT NULL,
  `WRITE_COUNT` bigint DEFAULT NULL,
  `READ_SKIP_COUNT` bigint DEFAULT NULL,
  `WRITE_SKIP_COUNT` bigint DEFAULT NULL,
  `PROCESS_SKIP_COUNT` bigint DEFAULT NULL,
  `ROLLBACK_COUNT` bigint DEFAULT NULL,
  `EXIT_CODE` varchar(2500) DEFAULT NULL,
  `EXIT_MESSAGE` varchar(2500) DEFAULT NULL,
  `LAST_UPDATED` datetime(6) DEFAULT NULL,
  PRIMARY KEY (`STEP_EXECUTION_ID`),
  KEY `JOB_EXEC_STEP_FK` (`JOB_EXECUTION_ID`),
  CONSTRAINT `JOB_EXEC_STEP_FK` FOREIGN KEY (`JOB_EXECUTION_ID`) REFERENCES `BATCH_JOB_EXECUTION` (`JOB_EXECUTION_ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

</details>

## Columns

| Name | Type | Default | Nullable | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | -------- | ------- | ------- |
| STEP_EXECUTION_ID | bigint |  | false | [BATCH_STEP_EXECUTION_CONTEXT](BATCH_STEP_EXECUTION_CONTEXT.md) |  |  |
| VERSION | bigint |  | false |  |  |  |
| STEP_NAME | varchar(100) |  | false |  |  |  |
| JOB_EXECUTION_ID | bigint |  | false |  | [BATCH_JOB_EXECUTION](BATCH_JOB_EXECUTION.md) |  |
| CREATE_TIME | datetime(6) |  | false |  |  |  |
| START_TIME | datetime(6) |  | true |  |  |  |
| END_TIME | datetime(6) |  | true |  |  |  |
| STATUS | varchar(10) |  | true |  |  |  |
| COMMIT_COUNT | bigint |  | true |  |  |  |
| READ_COUNT | bigint |  | true |  |  |  |
| FILTER_COUNT | bigint |  | true |  |  |  |
| WRITE_COUNT | bigint |  | true |  |  |  |
| READ_SKIP_COUNT | bigint |  | true |  |  |  |
| WRITE_SKIP_COUNT | bigint |  | true |  |  |  |
| PROCESS_SKIP_COUNT | bigint |  | true |  |  |  |
| ROLLBACK_COUNT | bigint |  | true |  |  |  |
| EXIT_CODE | varchar(2500) |  | true |  |  |  |
| EXIT_MESSAGE | varchar(2500) |  | true |  |  |  |
| LAST_UPDATED | datetime(6) |  | true |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| JOB_EXEC_STEP_FK | FOREIGN KEY | FOREIGN KEY (JOB_EXECUTION_ID) REFERENCES BATCH_JOB_EXECUTION (JOB_EXECUTION_ID) |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (STEP_EXECUTION_ID) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| JOB_EXEC_STEP_FK | KEY JOB_EXEC_STEP_FK (JOB_EXECUTION_ID) USING BTREE |
| PRIMARY | PRIMARY KEY (STEP_EXECUTION_ID) USING BTREE |

## Relations

![er](BATCH_STEP_EXECUTION.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
