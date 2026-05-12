# SO4 Predictor 一次成功部署清单（Streamlit Community Cloud）

## 1) GitHub 仓库应只包含这些文件

- `app.py`
- `predictor_core.py`
- `requirements.txt`
- `runtime.txt`
- `.gitignore`
- `.streamlit/config.toml`

> 不要上传模型 `.joblib` 到仓库主分支。

## 2) GitHub Release 资产（tag: `assets-v1`）

在仓库 **Releases** 页面创建 `assets-v1`，上传以下文件（平铺上传，不放子目录）：

- `catboost_model.joblib`
- `catboost_b_model.joblib`
- `lightgbm_model.joblib`
- `xgboost_model.joblib`
- `xgboost_b_model.joblib`
- `stacked_cat_model.joblib`
- `stacked_ridge_model.joblib`
- `cleaned_rows_aggregated.csv`
- `metrics.json`
- `esandt_extension_summary.json`
- `random_similarity_bin_error_summary.csv`
- `scaffold_similarity_bin_error_summary.csv`

## 3) Streamlit Deploy 参数

- Repository: `chenchao-0118/so4-radical-predictor`
- Branch: `main`
- Main file path: `app.py`

## 4) 首次启动行为

首次冷启动会自动从：

`https://github.com/chenchao-0118/so4-radical-predictor/releases/download/assets-v1/`

下载模型与数据到运行时目录 `artifacts/big_qsar_so4_v2_mixed/`。

## 5) 若更换仓库名或 tag（可选）

在 Streamlit App 的环境变量中设置：

- `SO4_RELEASE_REPO`（例如 `yourname/yourrepo`）
- `SO4_RELEASE_TAG`（例如 `assets-v1`）

