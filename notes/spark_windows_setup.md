
# ✅ PySpark + Spark Setup on Windows (Local Machine)

## 1. Install Java (JDK)
- Download and install **Java 11 (LTS)** (OpenJDK or Adoptium).
- Confirm installation:
  ```bash
  java -version
  ```
  Example output:
  ```
  openjdk version "11.0.xx"
  ```

- Set environment variables:
  ```
  JAVA_HOME = C:\Program Files\Eclipse Adoptium\jdk-11
  PATH += %JAVA_HOME%\bin
  ```

---

## 2. Download Spark
- Download **Spark 3.5.x pre-built for Hadoop** from [Apache Spark](https://spark.apache.org/downloads.html).
- Extract to:
  ```
  C:\spark
  ```

---

## 3. Hadoop Winutils (Windows compatibility)
- Download `winutils.exe` (Hadoop 3.3.x).
- Place in:
  ```
  C:\hadoop\bin\winutils.exe
  ```
- Set environment variables:
  ```
  HADOOP_HOME = C:\hadoop
  PATH += %HADOOP_HOME%\bin
  ```

---

## 4. Set Spark Environment Variables
Add to **User variables** in Environment Variables:

```
SPARK_HOME = C:\spark
SPARK_LOCAL_IP = 127.0.0.1
SPARK_MASTER = local[*]
```

And add to PATH:
```
%SPARK_HOME%\bin
```

---

## 5. Create Virtual Environment + Install PySpark
Inside your project folder:
```bash
python -m venv venv
venv\Scripts\activate
pip install pyspark
```

---

## 6. Verify Setup in Python
Run:
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("Test").getOrCreate()
print("Spark Version:", spark.version)
```

✅ If you see the Spark version, setup is complete.

---

## 7. Common Fixes
- **Firewall popup** → Allow access (needed for Spark driver → executor communication).
- **`JAVA_GATEWAY_EXITED` error** → Check Java installation & `JAVA_HOME`.
- **`Invalid Spark URL` error** → Ensure `SPARK_LOCAL_IP=127.0.0.1` is set.
- **Winutils not found** → Confirm `HADOOP_HOME` + `winutils.exe` path.
