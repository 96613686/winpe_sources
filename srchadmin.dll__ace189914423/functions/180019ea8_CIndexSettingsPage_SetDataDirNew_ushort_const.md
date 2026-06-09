# CIndexSettingsPage::_SetDataDirNew(ushort const *)

- ea: `0x180019ea8`
- end: `0x180019f77`
- name: `?_SetDataDirNew@CIndexSettingsPage@@AEAAJPEBG@Z`
- size: `207`
- prototype: `int(CIndexSettingsPage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004360`

## callees

- `0x180019ea8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019f3c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019f3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019f02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019f02`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180019f11`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180019f11`

## string_xrefs

- `0x180019f1c`: `DataDirectory`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_SetDataDirNew(CIndexSettingsPage *this, const unsigned __int16 *a2)
{
  LSTATUS v4; // ebx
  int v5; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\Windows Search\\Preferences",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v4 )
  {
    v5 = lstrlenW(a2);
    v4 = RegSetValueExW(hKey, L"DataDirectory", 0, 1u, (const BYTE *)a2, 2 * v5 + 2);
    RegCloseKey(hKey);
    if ( !v4 )
      *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) = 1;
  }
  return v4 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180019ea8  mov     r11, rsp
0x180019eab  mov     [r11+8], rbx
0x180019eaf  mov     [r11+10h], rsi
0x180019eb3  push    rdi
0x180019eb4  sub     rsp, 50h
0x180019eb8  mov     qword ptr [r11-18h], 0
0x180019ec0  lea     rax, [r11+18h]
0x180019ec4  mov     [r11-20h], rax
0x180019ec8  mov     rsi, rdx
0x180019ecb  mov     qword ptr [r11-28h], 0
0x180019ed3  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\Windows S"...
0x180019eda  mov     rdi, rcx
0x180019edd  mov     [rsp+58h+samDesired], 2; samDesired
0x180019ee5  xor     r9d, r9d; lpClass
0x180019ee8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180019ef0  xor     r8d, r8d; Reserved
0x180019ef3  mov     qword ptr [r11+18h], 0
0x180019efb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019f02  call    cs:__imp_RegCreateKeyExW
0x180019f08  mov     ebx, eax
0x180019f0a  test    eax, eax
0x180019f0c  jnz     short loc_180019F5A
0x180019f0e  mov     rcx, rsi; lpString
0x180019f11  call    cs:__imp_lstrlenW
0x180019f17  mov     rcx, [rsp+58h+hKey]; hKey
0x180019f1c  lea     rdx, aDatadirectory; "DataDirectory"
0x180019f23  xor     r8d, r8d; Reserved
0x180019f26  lea     eax, ds:2[rax*2]
0x180019f2d  mov     [rsp+58h+samDesired], eax; cbData
0x180019f31  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x180019f36  lea     esi, [rbx+1]
0x180019f39  mov     r9d, esi; dwType
0x180019f3c  call    cs:__imp_RegSetValueExW
0x180019f42  mov     rcx, [rsp+58h+hKey]; hKey
0x180019f47  mov     ebx, eax
0x180019f49  call    cs:__imp_RegCloseKey
0x180019f4f  test    ebx, ebx
0x180019f51  jnz     short loc_180019F5A
0x180019f53  mov     rax, [rdi+8]
0x180019f57  mov     [rax+0Ch], esi
0x180019f5a  mov     rsi, [rsp+58h+arg_8]
0x180019f5f  xor     eax, eax
0x180019f61  sub     eax, ebx
0x180019f63  mov     rbx, [rsp+58h+arg_0]
0x180019f68  neg     eax
0x180019f6a  sbb     eax, eax
0x180019f6c  and     eax, 80004005h
0x180019f71  add     rsp, 50h
0x180019f75  pop     rdi
0x180019f76  retn
```
