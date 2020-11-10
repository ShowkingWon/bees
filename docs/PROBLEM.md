# Apache POI
 ## EXCEL导入失败
 原因: 平台采用Apache POI作为Excel的解析组件， POI目前仅支持的 BIFF8 format (from Excel versions 97/2000/XP/2003)。上传的文件为 Excel 5.0/7.0 (BIFF5) 格式， 通俗理解为window office 95， 不在兼容范围之内。 
