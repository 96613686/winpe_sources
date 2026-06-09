# JsonHtmlFormatter::HtmlFormatterCallback::HtmlFormatterCallback(void)

- ea: `0x18001d39c`
- end: `0x18001dc1f`
- name: `??0HtmlFormatterCallback@JsonHtmlFormatter@@QEAA@XZ`
- size: `2179`
- prototype: `JsonHtmlFormatter::HtmlFormatterCallback *__fastcall(JsonHtmlFormatter::HtmlFormatterCallback *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d228`

## callees

- `0x18000ee04`
- `0x1800106e8`
- `0x180011be4`
- `0x18001613c`
- `0x1800185a8`
- `0x180018b04`
- `0x180018eec`
- `0x180018f80`
- `0x180019080`
- `0x18001ca98`
- `0x18001cbcc`
- `0x18001cf38`
- `0x18001d39c`
- `0x18001dcc8`
- `0x18001fcc0`
- `0x18001fd7c`
- `0x1800202d4`
- `0x18002042c`
- `0x180028d84`
- `0x180028ed4`
- `0x18008fe00`
- `0x1800961f0`

## string_xrefs

- `0x18001d9f1`: `\n        function getIndicatorText(direction) {\n            if (direction === 'asc') {\n                return ' (Order: Asc)';\n            }\n            if (direction === 'desc') {\n                return ' (Order: Desc)';\n            }\n            return ' (Order: None)';\n        }\n\n        function setHeaderIndicator(headerElement, direction) {\n            let indicator = headerElement.getElementsByClassName('sort-indicator')[0];\n            if (!indicator) {\n                indic`

## pseudocode

```c
JsonHtmlFormatter::HtmlFormatterCallback *__fastcall JsonHtmlFormatter::HtmlFormatterCallback::HtmlFormatterCallback(
        JsonHtmlFormatter::HtmlFormatterCallback *this)
{
  char *v2; // rdi
  _QWORD *v3; // rax
  __int64 ResourceString; // rbx
  __int64 v5; // rbx
  _QWORD *ClassArray; // rax
  unsigned __int64 v7; // r8
  __int128 *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rbx
  _QWORD *v11; // rax
  unsigned __int64 v12; // r8
  __int128 *v13; // rdx
  __int64 v14; // rax
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[40]; // [rsp+78h] [rbp-88h] BYREF
  JsonHtmlFormatter::HtmlFormatterCallback *v21; // [rsp+A0h] [rbp-60h]
  __int128 v22; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v24; // [rsp+D0h] [rbp-30h]
  _QWORD v25[40]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v26[40]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v27[320]; // [rsp+360h] [rbp+260h] BYREF

  v21 = this;
  *(_QWORD *)this = &JsonHtmlFormatter::HtmlFormatterCallback::`vftable';
  v2 = (char *)this + 8;
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>((char *)this + 8);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  v3 = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
  v3[1] = 0;
  *((_QWORD *)this + 32) = v3;
  *v3 = (char *)this + 256;
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"<html>", 6u);
  JsonHtmlFormatter::HtmlFormatterCallback::PushTagContext(this, 0, &v16, v2);
  std::wstring::~wstring(&v16);
  memset(v27, 0, 0x138u);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"<head>", 6u);
  HtmlTagContext::HtmlTagContext((unsigned int)v27, (_DWORD)v2, 0, (unsigned int)&v16, 0);
  std::wstring::~wstring(&v16);
  ResourceString = DiagUtils::LoadResourceString(v20, 2001);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, L"<title>", 7u);
  HtmlTagContext::WriteInnerTag(v27, &v18, ResourceString);
  std::wstring::~wstring(&v18);
  std::wstring::~wstring(v20);
  memset(v25, 0, 0x138u);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, L"<style>", 7u);
  HtmlTagContext::HtmlTagContext((unsigned int)v25, (_DWORD)v2, 1, (unsigned int)&v18, 0);
  std::wstring::~wstring(&v18);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L"body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 20px; }",
    0x54u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".section-header { background-color: #0078d4; color: white; padding: 10px; margin: 20px 0 0 0; font-weight: bold; }",
    0x72u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".section-table { width: 100%; border-collapse: collapse; margin-bottom: 20px; }",
    0x4Fu);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".section-table td { padding: 8px; border-bottom: 1px solid #ddd; }",
    0x42u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".section-table td:first-child { font-weight: bold; width: 30%; }",
    0x40u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L".section-table td:last-child { width: 70%; }", 0x2Cu);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".array-table { width: 100%; border-collapse: collapse; margin-bottom: 20px; }",
    0x4Du);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".array-table th { background-color: #f5f5f5; padding: 8px; border-bottom: 2px solid #ddd; font-weight: bold; text-align: left; }",
    0x80u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v16,
    L".array-table td { padding: 8px; border-bottom: 1px solid #ddd; }",
    0x40u);
  HtmlTagContext::WriteInnerLine(v25, &v16);
  std::wstring::~wstring(&v16);
  HtmlTagContext::~HtmlTagContext((HtmlTagContext *)v25);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"array-table", 0xBu);
  if ( *((_QWORD *)&v22 + 1) == (_QWORD)v23 )
  {
    std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
      (__int64 *)&v22,
      *((__int64 *)&v22 + 1),
      (__int64)&v16);
  }
  else
  {
    std::wstring::wstring(*((__int64 *)&v22 + 1), (__int64)&v16);
    *((_QWORD *)&v22 + 1) += 32LL;
  }
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"section-table", 0xDu);
  if ( *((_QWORD *)&v22 + 1) == (_QWORD)v23 )
  {
    std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
      (__int64 *)&v22,
      *((__int64 *)&v22 + 1),
      (__int64)&v16);
  }
  else
  {
    std::wstring::wstring(*((__int64 *)&v22 + 1), (__int64)&v16);
    *((_QWORD *)&v22 + 1) += 32LL;
  }
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"array-table", 0xBu);
  if ( (_QWORD)v24 == *((_QWORD *)&v24 + 1) )
  {
    std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
      (__int64 *)&v23 + 1,
      v24,
      (__int64)&v16);
  }
  else
  {
    std::wstring::wstring(v24, (__int64)&v16);
    *(_QWORD *)&v24 = v24 + 32;
  }
  std::wstring::~wstring(&v16);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, L"section-table", 0xDu);
  if ( (_QWORD)v24 == *((_QWORD *)&v24 + 1) )
  {
    std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
      (__int64 *)&v23 + 1,
      v24,
      (__int64)&v16);
  }
  else
  {
    std::wstring::wstring(v24, (__int64)&v16);
    *(_QWORD *)&v24 = v24 + 32;
  }
  std::wstring::~wstring(&v16);
  memset(v26, 0, 0x138u);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, L"<script>", 8u);
  HtmlTagContext::HtmlTagContext((unsigned int)v26, (_DWORD)v2, 1, (unsigned int)&v18, 0);
  std::wstring::~wstring(&v18);
  v5 = v26[0];
  memset(v25, 0, 0xF8u);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v25);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(
    (__int64)&v25[2],
    (__int64)L"\n"
              "        function getIndicatorText(direction) {\n"
              "            if (direction === 'asc') {\n"
              "                return ' (Order: Asc)';\n"
              "            }\n"
              "            if (direction === 'desc') {\n"
              "                return ' (Order: Desc)';\n"
              "            }\n"
              "            return ' (Order: None)';\n"
              "        }\n"
              "\n"
              "        function setHeaderIndicator(headerElement, direction) {\n"
              "            let indicator = headerElement.getElementsByClassName('sort-indicator')[0];\n"
              "            if (!indicator) {\n"
              "                indicator = document.createElement('div');\n"
              "                indicator.className = 'sort-indicator';\n"
              "                headerElement.appendChild(indicator);\n"
              "            }\n"
              "\n"
              "            indicator.textContent = getIndicatorText(direction);\n"
              "        }\n"
              "\n"
              "        function sortTable(tableElement, headerIndex, dataStartIndex) {\n"
              "            const allDirectRows = Array.from(tableElement.querySelectorAll(':scope > tr, :scope > tbody > "
              "tr'));\n"
              "            const rows = allDirectRows.slice(dataStartIndex);\n"
              "            if (rows.length === 0) {\n"
              "                return;\n"
              "            }\n"
              "\n"
              "            const sortAttr = 'direction-' + headerIndex;\n"
              "            const currentDirection = tableElement.getAttribute(sortAttr) || 'none';\n"
              "            const nextDirection = currentDirection === 'asc' ? 'desc' : 'asc';\n"
              "\n"
              "            const cells = [];\n"
              "            for (const row of rows) {\n"
              "                const cell = row.cells[headerIndex];\n"
              "                if (cell) {\n"
              "                    cells.push(cell);\n"
              "                }\n"
              "            }\n"
              "\n"
              "            const areNumbers = cells.length > 0 && cells.every(cell => {\n"
              "                const text = cell.innerText.trim();\n"
              "                return text.length > 0 && !Number.isNaN(Number(text));\n"
              "            });\n"
              "\n"
              "            rows.sort((rowA, rowB) => {\n"
              "                const cellA = rowA.cells[headerIndex];\n"
              "                const cellB = rowB.cells[headerIndex];\n"
              "                const textA = cellA ? cellA.innerText.trim() : '';\n"
              "                const textB = cellB ? cellB.innerText.trim() : '';\n"
              "\n"
              "                let compareResult = 0;\n"
              "                if (areNumbers) {\n"
              "                    compareResult = Number(textA) - Number(textB);\n"
              "                } else {\n"
              "                    compareResult = textA.localeCompare(textB);\n"
              "                }\n"
              "\n"
              "                return nextDirection === 'asc' ? compareResult : -compareResult;\n"
              "            });\n"
              "\n"
              "            rows.forEach(row => tableElement.appendChild(row));\n"
              "            tableElement.setAttribute(sortAttr, nextDirection);\n"
              "\n"
              "            const headers = Array.from(tableElement.getElementsByClassName('sortable')).filter(h => h.clos"
              "est('table') === tableElement);\n"
              "            if (headers.length === 0) {\n"
              "                const sectionHeaderElement = tableElement.previousElementSibling;\n"
              "                if (sectionHeaderElement) {\n"
              "                    setHeaderIndicator(sectionHeaderElement, nextDirection);\n"
              "                }\n"
              "                return;\n"
              "            }\n"
              "            for (let index = 0; index < headers.length; ++index) {\n"
              "                setHeaderIndicator(headers[index], index === headerIndex ? nextDirection : 'none');\n"
              "            }\n"
              "        }\n"
              "\n"
              "        document.addEventListener('DOMContentLoaded', function () {\n"
              "            const sortClasses = ");
  ClassArray = (_QWORD *)GetClassArray(v20, &v22);
  v7 = ClassArray[2];
  if ( ClassArray[3] > 7u )
    ClassArray = (_QWORD *)*ClassArray;
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>((__int64)&v25[2], (__int64)ClassArray, v7);
  std::wstring::~wstring(v20);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(
    (__int64)&v25[2],
    (__int64)L"; \n"
              "\n"
              "            sortClasses.forEach(className => {\n"
              "                Array.from(document.getElementsByClassName(className)).forEach(tableElement => {\n"
              "                    const hasSortableHeaderRow = tableElement.getElementsByClassName('sortable').length > "
              "0;\n"
              "\n"
              "                    if (hasSortableHeaderRow) {\n"
              "                        const headers = tableElement.getElementsByClassName('sortable');\n"
              "                        for (let index = 0; index < headers.length; ++index) {\n"
              "                            const header = headers[index];\n"
              "                            header.style.cursor = 'pointer';\n"
              "                            setHeaderIndicator(header, 'none');\n"
              "                            header.addEventListener('click', function () {\n"
              "                                sortTable(tableElement, index, 1);\n"
              "                            });\n"
              "                        }\n"
              "                    } else {\n"
              "                        const firstRow = tableElement.rows.length > 0 ? tableElement.rows[0] : null;\n"
              "                        if (!firstRow) {\n"
              "                            return;\n"
              "                        }\n"
              "                        const headerElement = tableElement.previousElementSibling;\n"
              "                        if (!headerElement) {\n"
              "                            return;\n"
              "                        }\n"
              "                        const sectionHeaderElement = tableElement.previousElementSibling;\n"
              "                        if (!sectionHeaderElement) {\n"
              "                            return;\n"
              "                        }\n"
              "                        sectionHeaderElement.style.cursor = 'pointer';\n"
              "                        setHeaderIndicator(sectionHeaderElement, 'none');\n"
              "                        sectionHeaderElement.addEventListener('click', function () {\n"
              "                            sortTable(tableElement, 0, 0);\n"
              "                        });\n"
              "                    }\n"
              "                });\n"
              "            });\n"
              "        });\n"
              "    ");
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v25, &v16);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v25[19]);
  v25[19] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v25[19]);
  v8 = &v16;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v8 = (__int128 *)v16;
  v9 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v5 + 16, (__int64)v8, v17);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v9, (__int64)L"\n");
  std::wstring::~wstring(&v16);
  v10 = v26[0];
  memset(v25, 0, 0xF8u);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v25);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(
    (__int64)&v25[2],
    (__int64)L"\n"
              "        function filterTable(tableElement, columnIndex, filterValue) {\n"
              "            if (!tableElement || !tableElement.rows || tableElement.rows.length <= 1) {\n"
              "                return;\n"
              "            }\n"
              "\n"
              "            const rows = Array.from(tableElement.querySelectorAll(':scope > tr, :scope > tbody > tr')).sli"
              "ce(1);\n"
              "            rows.forEach(row => {\n"
              "                const cell = row.cells[columnIndex];\n"
              "                if (!cell) {\n"
              "                    return;\n"
              "                }\n"
              "                const cellText = cell.innerText.trim().toLowerCase();\n"
              "                row.style.display = cellText.includes(filterValue.toLowerCase()) ? '' : 'none';\n"
              "            });\n"
              "        }\n"
              "        document.addEventListener('DOMContentLoaded', function () {\n"
              "            const filterClasses = ");
  v11 = (_QWORD *)GetClassArray(v20, (char *)&v23 + 8);
  v12 = v11[2];
  if ( v11[3] > 7u )
    v11 = (_QWORD *)*v11;
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>((__int64)&v25[2], (__int64)v11, v12);
  std::wstring::~wstring(v20);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(
    (__int64)&v25[2],
    (__int64)L"; \n"
              "\n"
              "            filterClasses.forEach(className => {\n"
              "                Array.from(document.getElementsByClassName(className)).forEach(tableElement => {\n"
              "                    const hasHeaderRow = tableElement.getElementsByTagName('th').length > 0;\n"
              "\n"
              "                    if (hasHeaderRow) {\n"
              "                        const headers = tableElement.getElementsByTagName('th');\n"
              "                        for (let index = 0; index < headers.length; ++index) {\n"
              "                            const header = headers[index];\n"
              "                            const searchInput = header.getElementsByClassName('search-input')[0];\n"
              "                            if (searchInput) {\n"
              "                                searchInput.addEventListener('keyup', function (event) {\n"
              "                                    const filterValue = event.target.value;\n"
              "                                    filterTable(tableElement, index, filterValue);\n"
              "                                });\n"
              "                                searchInput.addEventListener('click', function (event) {\n"
              "                                    event.stopPropagation();\n"
              "                                });\n"
              "                            }\n"
              "                        }\n"
              "                    } else {\n"
              "                        const firstRow = tableElement.rows.length > 0 ? tableElement.rows[0] : null;\n"
              "                        if (!firstRow) {\n"
              "                            return;\n"
              "                        }\n"
              "                        const headerElement = tableElement.previousElementSibling;\n"
              "                        if (!headerElement) {\n"
              "                            return;\n"
              "                        }\n"
              "                        const sectionHeaderElement = tableElement.previousElementSibling;\n"
              "                        if (!sectionHeaderElement) {\n"
              "                            return;\n"
              "                        }\n"
              "                        const searchInput = sectionHeaderElement.getElementsByClassName('search-input')[0]"
              ";\n"
              "                        if (searchInput) {\n"
              "                            searchInput.addEventListener('keyup', function (event) {\n"
              "                                const filterValue = event.target.value;\n"
              "                                filterTable(tableElement, 0, filterValue);\n"
              "                            });\n"
              "                            searchInput.addEventListener('click', function (event) {\n"
              "                                event.stopPropagation();\n"
              "                            });\n"
              "                        }\n"
              "                    }\n"
              "                });\n"
              "            });\n"
              "        });\n"
              "    ");
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v25, &v16);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v25[19]);
  v25[19] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v25[19]);
  v13 = &v16;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v13 = (__int128 *)v16;
  v14 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v10 + 16, (__int64)v13, v17);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v14, (__int64)L"\n");
  std::wstring::~wstring(&v16);
  HtmlTagContext::~HtmlTagContext((HtmlTagContext *)v26);
  std::vector<std::filesystem::path>::~vector<std::filesystem::path>((char *)&v23 + 8);
  std::vector<std::filesystem::path>::~vector<std::filesystem::path>(&v22);
  HtmlTagContext::~HtmlTagContext((HtmlTagContext *)v27);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, L"<body>", 6u);
  JsonHtmlFormatter::HtmlFormatterCallback::PushTagContext(this, 0, &v18, v2);
  std::wstring::~wstring(&v18);
  return this;
}

```

## disassembly

```asm
0x18001d39c  mov     [rsp-8+arg_8], rbx
0x18001d3a1  mov     [rsp-8+arg_10], rsi
0x18001d3a6  push    rbp
0x18001d3a7  push    rdi
0x18001d3a8  push    r12
0x18001d3aa  push    r13
0x18001d3ac  push    r15
0x18001d3ae  lea     rbp, [rsp-3B0h]
0x18001d3b6  sub     rsp, 4B0h
0x18001d3bd  mov     rax, cs:__security_cookie
0x18001d3c4  xor     rax, rsp
0x18001d3c7  mov     [rbp+3D0h+var_30], rax
0x18001d3ce  mov     rsi, rcx
0x18001d3d1  mov     [rbp+3D0h+var_430], rcx
0x18001d3d5  xor     r15d, r15d
0x18001d3d8  lea     rax, ??_7HtmlFormatterCallback@JsonHtmlFormatter@@6B@; const JsonHtmlFormatter::HtmlFormatterCallback::`vftable'
0x18001d3df  mov     [rcx], rax
0x18001d3e2  lea     rdi, [rcx+8]
0x18001d3e6  mov     rcx, rdi
0x18001d3e9  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18001d3ee  nop
0x18001d3ef  lea     rbx, [rsi+100h]
0x18001d3f6  mov     [rbx], r15
0x18001d3f9  mov     [rbx+8], r15
0x18001d3fd  mov     [rbx+10h], r15
0x18001d401  mov     [rbx+18h], r15
0x18001d405  mov     [rbx+20h], r15
0x18001d409  lea     ecx, [r15+10h]
0x18001d40d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001d412  mov     [rax+8], r15
0x18001d416  mov     [rbx], rax
0x18001d419  mov     [rax], rbx
0x18001d41c  xorps   xmm0, xmm0
0x18001d41f  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d424  xorps   xmm1, xmm1
0x18001d427  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d42d  lea     ebx, [r15+6]
0x18001d431  mov     r8d, ebx
0x18001d434  lea     rdx, aHtml; "<html>"
0x18001d43b  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d440  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d445  nop
0x18001d446  mov     r9, rdi
0x18001d449  lea     r8, [rsp+4D0h+var_4A0]
0x18001d44e  xor     edx, edx
0x18001d450  mov     rcx, rsi
0x18001d453  call    ?PushTagContext@HtmlFormatterCallback@JsonHtmlFormatter@@AEAAXHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; JsonHtmlFormatter::HtmlFormatterCallback::PushTagContext(int,std::wstring const &,std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)
0x18001d458  nop
0x18001d459  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d45e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d463  mov     r13d, 138h
0x18001d469  mov     r8d, r13d; Size
0x18001d46c  xor     edx, edx; Val
0x18001d46e  lea     rcx, [rbp+3D0h+var_170]; void *
0x18001d475  call    memset
0x18001d47a  xorps   xmm0, xmm0
0x18001d47d  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d482  xorps   xmm1, xmm1
0x18001d485  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d48b  mov     r8d, ebx
0x18001d48e  lea     rdx, aHead; "<head>"
0x18001d495  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d49a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d49f  nop
0x18001d4a0  mov     [rsp+4D0h+var_4B0], r15b
0x18001d4a5  lea     r9, [rsp+4D0h+var_4A0]
0x18001d4aa  xor     r8d, r8d
0x18001d4ad  mov     rdx, rdi
0x18001d4b0  lea     rcx, [rbp+3D0h+var_170]
0x18001d4b7  call    ??0HtmlTagContext@@QEAA@AEAV?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_N@Z; HtmlTagContext::HtmlTagContext(std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,int,std::wstring const &,bool)
0x18001d4bc  nop
0x18001d4bd  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d4c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d4c7  mov     edx, 7D1h
0x18001d4cc  lea     rcx, [rsp+4D0h+var_458]
0x18001d4d1  call    ?LoadResourceString@DiagUtils@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; DiagUtils::LoadResourceString(uint)
0x18001d4d6  mov     rbx, rax
0x18001d4d9  xorps   xmm0, xmm0
0x18001d4dc  movups  [rsp+4D0h+var_480], xmm0
0x18001d4e1  xorps   xmm1, xmm1
0x18001d4e4  movdqu  [rsp+4D0h+var_470], xmm1
0x18001d4ea  lea     r8d, [r15+7]
0x18001d4ee  lea     rdx, aTitle_0; "<title>"
0x18001d4f5  lea     rcx, [rsp+4D0h+var_480]
0x18001d4fa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d4ff  nop
0x18001d500  mov     r8, rbx
0x18001d503  lea     rdx, [rsp+4D0h+var_480]
0x18001d508  lea     rcx, [rbp+3D0h+var_170]
0x18001d50f  call    ?WriteInnerTag@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; HtmlTagContext::WriteInnerTag(std::wstring const &,std::wstring const &)
0x18001d514  nop
0x18001d515  lea     rcx, [rsp+4D0h+var_480]
0x18001d51a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d51f  nop
0x18001d520  lea     rcx, [rsp+4D0h+var_458]
0x18001d525  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d52a  mov     r8d, r13d; Size
0x18001d52d  xor     edx, edx; Val
0x18001d52f  lea     rcx, [rbp+3D0h+var_3F0]; void *
0x18001d533  call    memset
0x18001d538  xorps   xmm0, xmm0
0x18001d53b  movups  [rsp+4D0h+var_480], xmm0
0x18001d540  xorps   xmm1, xmm1
0x18001d543  movdqu  [rsp+4D0h+var_470], xmm1
0x18001d549  lea     r8d, [r15+7]
0x18001d54d  lea     rdx, aStyle; "<style>"
0x18001d554  lea     rcx, [rsp+4D0h+var_480]
0x18001d559  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d55e  nop
0x18001d55f  mov     [rsp+4D0h+var_4B0], r15b
0x18001d564  lea     r9, [rsp+4D0h+var_480]
0x18001d569  lea     r8d, [r15+1]
0x18001d56d  mov     rdx, rdi
0x18001d570  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d574  call    ??0HtmlTagContext@@QEAA@AEAV?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_N@Z; HtmlTagContext::HtmlTagContext(std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,int,std::wstring const &,bool)
0x18001d579  nop
0x18001d57a  lea     rcx, [rsp+4D0h+var_480]
0x18001d57f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d584  xorps   xmm0, xmm0
0x18001d587  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d58c  xorps   xmm1, xmm1
0x18001d58f  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d595  lea     r8d, [r15+54h]
0x18001d599  lea     rdx, aBodyFontFamily; "body { font-family: 'Segoe UI', Tahoma,"...
0x18001d5a0  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d5a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d5aa  nop
0x18001d5ab  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d5b0  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d5b4  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d5b9  nop
0x18001d5ba  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d5bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d5c4  xorps   xmm0, xmm0
0x18001d5c7  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d5cc  xorps   xmm1, xmm1
0x18001d5cf  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d5d5  lea     r8d, [r15+72h]
0x18001d5d9  lea     rdx, aSectionHeaderB; ".section-header { background-color: #00"...
0x18001d5e0  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d5e5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d5ea  nop
0x18001d5eb  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d5f0  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d5f4  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d5f9  nop
0x18001d5fa  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d5ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d604  xorps   xmm0, xmm0
0x18001d607  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d60c  xorps   xmm1, xmm1
0x18001d60f  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d615  lea     r8d, [r15+4Fh]
0x18001d619  lea     rdx, aSectionTableWi; ".section-table { width: 100%; border-co"...
0x18001d620  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d625  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d62a  nop
0x18001d62b  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d630  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d634  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d639  nop
0x18001d63a  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d63f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d644  xorps   xmm0, xmm0
0x18001d647  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d64c  xorps   xmm1, xmm1
0x18001d64f  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d655  lea     r8d, [r15+42h]
0x18001d659  lea     rdx, aSectionTableTd_1; ".section-table td { padding: 8px; borde"...
0x18001d660  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d665  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d66a  nop
0x18001d66b  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d670  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d674  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d679  nop
0x18001d67a  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d67f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d684  xorps   xmm0, xmm0
0x18001d687  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d68c  xorps   xmm1, xmm1
0x18001d68f  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d695  lea     ebx, [r15+40h]
0x18001d699  mov     r8d, ebx
0x18001d69c  lea     rdx, aSectionTableTd; ".section-table td:first-child { font-we"...
0x18001d6a3  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d6a8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d6ad  nop
0x18001d6ae  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d6b3  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d6b7  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d6bc  nop
0x18001d6bd  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d6c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d6c7  xorps   xmm0, xmm0
0x18001d6ca  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d6cf  xorps   xmm1, xmm1
0x18001d6d2  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d6d8  lea     r8d, [r15+2Ch]
0x18001d6dc  lea     rdx, aSectionTableTd_0; ".section-table td:last-child { width: 7"...
0x18001d6e3  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d6e8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d6ed  nop
0x18001d6ee  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d6f3  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d6f7  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d6fc  nop
0x18001d6fd  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d702  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d707  xorps   xmm0, xmm0
0x18001d70a  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d70f  xorps   xmm1, xmm1
0x18001d712  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d718  lea     r8d, [r15+4Dh]
0x18001d71c  lea     rdx, aArrayTableWidt; ".array-table { width: 100%; border-coll"...
0x18001d723  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d728  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d72d  nop
0x18001d72e  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d733  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d737  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d73c  nop
0x18001d73d  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d742  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d747  xorps   xmm0, xmm0
0x18001d74a  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d74f  xorps   xmm1, xmm1
0x18001d752  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d758  lea     r8d, [rbx+40h]
0x18001d75c  lea     rdx, aArrayTableThBa; ".array-table th { background-color: #f5"...
0x18001d763  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d768  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d76d  nop
0x18001d76e  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d773  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d777  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d77c  nop
0x18001d77d  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d782  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d787  xorps   xmm0, xmm0
0x18001d78a  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d78f  xorps   xmm1, xmm1
0x18001d792  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d798  mov     r8d, ebx
0x18001d79b  lea     rdx, aArrayTableTdPa; ".array-table td { padding: 8px; border-"...
0x18001d7a2  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d7a7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d7ac  nop
0x18001d7ad  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d7b2  lea     rcx, [rbp+3D0h+var_3F0]
0x18001d7b6  call    ?WriteInnerLine@HtmlTagContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; HtmlTagContext::WriteInnerLine(std::wstring const &)
0x18001d7bb  nop
0x18001d7bc  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d7c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d7c6  nop
0x18001d7c7  lea     rcx, [rbp+3D0h+var_3F0]; this
0x18001d7cb  call    ??1HtmlTagContext@@QEAA@XZ; HtmlTagContext::~HtmlTagContext(void)
0x18001d7d0  xorps   xmm0, xmm0
0x18001d7d3  movdqu  [rbp+3D0h+var_420], xmm0
0x18001d7d8  xorps   xmm1, xmm1
0x18001d7db  movdqu  [rbp+3D0h+var_410], xmm1
0x18001d7e0  movdqu  [rbp+3D0h+var_400], xmm0
0x18001d7e5  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d7ea  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d7f0  lea     r12d, [r15+0Bh]
0x18001d7f4  mov     r8d, r12d
0x18001d7f7  lea     rdx, aArrayTable; "array-table"
0x18001d7fe  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d803  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d808  nop
0x18001d809  mov     rax, qword ptr [rbp+3D0h+var_420+8]
0x18001d80d  cmp     rax, qword ptr [rbp+3D0h+var_410]
0x18001d811  jz      short loc_18001D827
0x18001d813  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d818  mov     rcx, rax
0x18001d81b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d820  add     qword ptr [rbp+3D0h+var_420+8], 20h ; ' '
0x18001d825  jmp     short loc_18001D839
0x18001d827  lea     r8, [rsp+4D0h+var_4A0]
0x18001d82c  mov     rdx, rax
0x18001d82f  lea     rcx, [rbp+3D0h+var_420]
0x18001d833  call    ??$_Emplace_reallocate@AEBVpath@filesystem@std@@@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAPEAVpath@filesystem@1@QEAV231@AEBV231@@Z; std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(std::filesystem::path * const,std::filesystem::path const &)
0x18001d838  nop
0x18001d839  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d83e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d843  xorps   xmm0, xmm0
0x18001d846  movups  [rsp+4D0h+var_4A0], xmm0
0x18001d84b  xorps   xmm1, xmm1
0x18001d84e  movdqu  [rsp+4D0h+var_490], xmm1
0x18001d854  mov     ebx, 0Dh
0x18001d859  mov     r8d, ebx
0x18001d85c  lea     rdx, aSectionTable; "section-table"
0x18001d863  lea     rcx, [rsp+4D0h+var_4A0]
0x18001d868  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d86d  nop
0x18001d86e  mov     rax, qword ptr [rbp+3D0h+var_420+8]
0x18001d872  cmp     rax, qword ptr [rbp+3D0h+var_410]
0x18001d876  jz      short loc_18001D88C
0x18001d878  lea     rdx, [rsp+4D0h+var_4A0]
0x18001d87d  mov     rcx, rax
  ... truncated ...
```
