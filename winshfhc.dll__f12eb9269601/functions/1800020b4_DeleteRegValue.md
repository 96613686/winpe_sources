# DeleteRegValue

- ea: `0x1800020b4`
- end: `0x180002362`
- name: `DeleteRegValue`
- size: `686`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180002688`

## callees

- `0x180001b50`
- `0x1800020b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000223f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000223f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000210e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000233f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000210e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000233f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800021f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800021f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800020f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800020f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000212a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000225d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000212a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000225d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800021a8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002323`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800021a8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002323`
- `WDSCORE!CurrentIP` at `0x180002138`
- `WDSCORE!CurrentIP` at `0x180002214`
- `WDSCORE!CurrentIP` at `0x18000226b`
- `WDSCORE!CurrentIP` at `0x1800022b2`
- `WDSCORE!CurrentIP` at `0x180002138`
- `WDSCORE!CurrentIP` at `0x180002214`
- `WDSCORE!CurrentIP` at `0x18000226b`
- `WDSCORE!CurrentIP` at `0x1800022b2`

## string_xrefs

- `0x18000216c`: `DeleteRegValue`
- `0x1800022e7`: `DeleteRegValue`
- `0x180002147`: `MRTGeneralize:%d - ERROR: Could not open Windows Defender key HKLM\%ls with KEY_QUERY_VALUE: error code %d`
- `0x180002223`: `MRTGeneralize:%d - ERROR: Could not open Windows Defender key HKLM\%ls with KEY_SET_VALUE: error code %d`
- `0x18000228b`: `MRTGeneralize:%d - ERROR: Failed to delete Windows Defender value HKLM\%ls\%ls: error code %d`

## pseudocode

```c
__int64 __fastcall DeleteRegValue(LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  unsigned int v4; // esi
  DWORD LastError; // edi
  __int64 v6; // rax
  LPCWSTR v7; // r9
  const char *v8; // rdx
  unsigned int v9; // ebp
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  LSTATUS v12; // eax
  __int64 v13; // rax
  const wchar_t *v14; // r9
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-68h]
  DWORD dwDisposition; // [rsp+A0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = lpSubKey;
    v8 = "MRTGeneralize:%d - ERROR: Could not open Windows Defender key HKLM\\%ls with KEY_QUERY_VALUE: error code %d";
    v9 = 157;
LABEL_5:
    dwOptions[0] = v4;
    v10 = v6;
    v11 = ConstructPartialMsgW(0x2000000u, v8, v9, v7, *(_QWORD *)dwOptions);
LABEL_6:
    WdsSetupLogMessageW(
      v11,
      983040,
      L"D",
      0,
      v9,
      L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
      L"DeleteRegValue",
      v10,
      LastError,
      0,
      0);
    goto LABEL_13;
  }
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 4u, 2u, 0, &hKey, &dwDisposition);
  if ( v4 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = lpSubKey;
    v8 = "MRTGeneralize:%d - ERROR: Could not open Windows Defender key HKLM\\%ls with KEY_SET_VALUE: error code %d";
    v9 = 176;
    goto LABEL_5;
  }
  v12 = RegDeleteValueW(hKey, lpValueName);
  v4 = v12;
  if ( v12 )
  {
    if ( (unsigned int)(v12 - 2) > 1 )
    {
      LastError = GetLastError();
      v13 = CurrentIP();
      v14 = lpSubKey;
      v9 = 200;
      v10 = v13;
      v11 = ConstructPartialMsgW(
              0x2000000u,
              "MRTGeneralize:%d - ERROR: Failed to delete Windows Defender value HKLM\\%ls\\%ls: error code %d",
              200,
              v14,
              lpValueName,
              v4);
      goto LABEL_6;
    }
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(
            0x4000000u,
            "MRTGeneralize:%d - Windows Defender value HKLM\\%ls\\%ls does not exist, skipping action.",
            192,
            lpSubKey,
            lpValueName);
    WdsSetupLogMessageW(
      v17,
      983040,
      L"D",
      0,
      192,
      L"onecore\\amcore\\antimalware\\source\\filehascode\\table\\mrtgeneralize.cpp",
      L"DeleteRegValue",
      v16,
      v15,
      0,
      0);
    v4 = 0;
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800020b4  mov     r11, rsp
0x1800020b7  mov     [r11+8], rbx
0x1800020bb  push    rbp
0x1800020bc  push    rsi
0x1800020bd  push    rdi
0x1800020be  push    r14
0x1800020c0  push    r15
0x1800020c2  sub     rsp, 60h
0x1800020c6  xor     r15d, r15d
0x1800020c9  lea     rax, [r11+20h]
0x1800020cd  mov     r14, rdx
0x1800020d0  mov     [r11+20h], r15
0x1800020d4  mov     rbp, rcx
0x1800020d7  mov     [r11+18h], r15d
0x1800020db  mov     rdx, rcx; lpSubKey
0x1800020de  mov     [r11-68h], rax
0x1800020e2  mov     rbx, 0FFFFFFFF80000002h
0x1800020e9  lea     r9d, [r15+1]; samDesired
0x1800020ed  xor     r8d, r8d; ulOptions
0x1800020f0  mov     rcx, rbx; hKey
0x1800020f3  call    cs:__imp_RegOpenKeyExW
0x1800020fa  nop     dword ptr [rax+rax+00h]
0x1800020ff  mov     rcx, [rsp+88h+hKey]; hKey
0x180002107  mov     esi, eax
0x180002109  test    rcx, rcx
0x18000210c  jz      short loc_180002122
0x18000210e  call    cs:__imp_RegCloseKey
0x180002115  nop     dword ptr [rax+rax+00h]
0x18000211a  mov     [rsp+88h+hKey], r15
0x180002122  test    esi, esi
0x180002124  jz      loc_1800021B9
0x18000212a  call    cs:__imp_GetLastError
0x180002131  nop     dword ptr [rax+rax+00h]
0x180002136  mov     edi, eax
0x180002138  call    cs:__imp_CurrentIP
0x18000213f  nop     dword ptr [rax+rax+00h]
0x180002144  mov     r9, rbp
0x180002147  lea     rdx, aMrtgeneralizeD_6; "MRTGeneralize:%d - ERROR: Could not ope"...
0x18000214e  mov     ebp, 9Dh
0x180002153  mov     r8d, ebp
0x180002156  mov     [rsp+88h+dwOptions], esi
0x18000215a  mov     ecx, 2000000h; unsigned int
0x18000215f  mov     rbx, rax
0x180002162  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002167  mov     [rsp+88h+var_38], r15d
0x18000216c  lea     rcx, aDeleteregvalue; "DeleteRegValue"
0x180002173  mov     [rsp+88h+var_40], r15
0x180002178  lea     r8, aD; "D"
0x18000217f  mov     dword ptr [rsp+88h+lpdwDisposition], edi
0x180002183  xor     r9d, r9d
0x180002186  mov     [rsp+88h+phkResult], rbx
0x18000218b  mov     edx, 0F0000h
0x180002190  mov     [rsp+88h+lpSecurityAttributes], rcx
0x180002195  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x18000219c  mov     qword ptr [rsp+88h+samDesired], rcx
0x1800021a1  mov     rcx, rax
0x1800021a4  mov     [rsp+88h+dwOptions], ebp
0x1800021a8  call    cs:__imp_WdsSetupLogMessageW
0x1800021af  nop     dword ptr [rax+rax+00h]
0x1800021b4  jmp     loc_180002332
0x1800021b9  lea     rax, [rsp+88h+dwDisposition]
0x1800021c1  xor     r9d, r9d; lpClass
0x1800021c4  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x1800021c9  xor     r8d, r8d; Reserved
0x1800021cc  lea     rax, [rsp+88h+hKey]
0x1800021d4  mov     rdx, rbp; lpSubKey
0x1800021d7  mov     [rsp+88h+phkResult], rax; phkResult
0x1800021dc  mov     rcx, rbx; hKey
0x1800021df  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800021e4  mov     [rsp+88h+samDesired], 2; samDesired
0x1800021ec  mov     [rsp+88h+dwOptions], 4; dwOptions
0x1800021f4  call    cs:__imp_RegCreateKeyExW
0x1800021fb  nop     dword ptr [rax+rax+00h]
0x180002200  mov     esi, eax
0x180002202  test    eax, eax
0x180002204  jz      short loc_180002234
0x180002206  call    cs:__imp_GetLastError
0x18000220d  nop     dword ptr [rax+rax+00h]
0x180002212  mov     edi, eax
0x180002214  call    cs:__imp_CurrentIP
0x18000221b  nop     dword ptr [rax+rax+00h]
0x180002220  mov     r9, rbp
0x180002223  lea     rdx, aMrtgeneralizeD_10; "MRTGeneralize:%d - ERROR: Could not ope"...
0x18000222a  mov     ebp, 0B0h
0x18000222f  jmp     loc_180002153
0x180002234  mov     rcx, [rsp+88h+hKey]; hKey
0x18000223c  mov     rdx, r14; lpValueName
0x18000223f  call    cs:__imp_RegDeleteValueW
0x180002246  nop     dword ptr [rax+rax+00h]
0x18000224b  mov     esi, eax
0x18000224d  test    eax, eax
0x18000224f  jz      loc_180002332
0x180002255  add     eax, 0FFFFFFFEh
0x180002258  cmp     eax, 1
0x18000225b  jbe     short loc_1800022A4
0x18000225d  call    cs:__imp_GetLastError
0x180002264  nop     dword ptr [rax+rax+00h]
0x180002269  mov     edi, eax
0x18000226b  call    cs:__imp_CurrentIP
0x180002272  nop     dword ptr [rax+rax+00h]
0x180002277  mov     r9, rbp
0x18000227a  mov     [rsp+88h+samDesired], esi
0x18000227e  mov     ebp, 0C8h
0x180002283  mov     qword ptr [rsp+88h+dwOptions], r14
0x180002288  mov     r8d, ebp
0x18000228b  lea     rdx, aMrtgeneralizeD_13; "MRTGeneralize:%d - ERROR: Failed to del"...
0x180002292  mov     ecx, 2000000h; unsigned int
0x180002297  mov     rbx, rax
0x18000229a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000229f  jmp     loc_180002167
0x1800022a4  call    cs:__imp_GetLastError
0x1800022ab  nop     dword ptr [rax+rax+00h]
0x1800022b0  mov     edi, eax
0x1800022b2  call    cs:__imp_CurrentIP
0x1800022b9  nop     dword ptr [rax+rax+00h]
0x1800022be  mov     esi, 0C0h
0x1800022c3  mov     qword ptr [rsp+88h+dwOptions], r14
0x1800022c8  mov     r8d, esi
0x1800022cb  lea     rdx, aMrtgeneralizeD_0; "MRTGeneralize:%d - Windows Defender val"...
0x1800022d2  mov     r9, rbp
0x1800022d5  mov     ecx, 4000000h; unsigned int
0x1800022da  mov     rbx, rax
0x1800022dd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800022e2  mov     [rsp+88h+var_38], r15d
0x1800022e7  lea     rcx, aDeleteregvalue; "DeleteRegValue"
0x1800022ee  mov     [rsp+88h+var_40], r15
0x1800022f3  lea     r8, aD; "D"
0x1800022fa  mov     dword ptr [rsp+88h+lpdwDisposition], edi
0x1800022fe  xor     r9d, r9d
0x180002301  mov     [rsp+88h+phkResult], rbx
0x180002306  mov     edx, 0F0000h
0x18000230b  mov     [rsp+88h+lpSecurityAttributes], rcx
0x180002310  lea     rcx, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\f"...
0x180002317  mov     qword ptr [rsp+88h+samDesired], rcx
0x18000231c  mov     rcx, rax
0x18000231f  mov     [rsp+88h+dwOptions], esi
0x180002323  call    cs:__imp_WdsSetupLogMessageW
0x18000232a  nop     dword ptr [rax+rax+00h]
0x18000232f  mov     esi, r15d
0x180002332  mov     rcx, [rsp+88h+hKey]; hKey
0x18000233a  test    rcx, rcx
0x18000233d  jz      short loc_18000234B
0x18000233f  call    cs:__imp_RegCloseKey
0x180002346  nop     dword ptr [rax+rax+00h]
0x18000234b  mov     rbx, [rsp+88h+arg_0]
0x180002353  mov     eax, esi
0x180002355  add     rsp, 60h
0x180002359  pop     r15
0x18000235b  pop     r14
0x18000235d  pop     rdi
0x18000235e  pop     rsi
0x18000235f  pop     rbp
0x180002360  retn
```
