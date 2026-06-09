# LPatchUserDevmodes

- ea: `0x1400058a0`
- end: `0x140005b61`
- name: `LPatchUserDevmodes`
- size: `705`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004e90`

## callees

- `0x1400058a0`
- `0x140005b68`
- `0x140023974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400059b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400059b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400059f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400059f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005a2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005a2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140005b1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140005b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400059ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005b48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400059ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005b48`

## string_xrefs

- `0x140005a39`: `Count of previous attempts : %u. Status : %d`
- `0x140005a5c`: `The devmode has already been validated`
- `0x140005ada`: `Increase attempts count by one`
- `0x140005ac5`: `Complete attempts count`

## pseudocode

```c
__int64 __fastcall LPatchUserDevmodes(WCHAR *lpValueName)
{
  __int64 v2; // rax
  WCHAR v3; // r10
  int v4; // r9d
  unsigned int v5; // r8d
  LPCWSTR v6; // r11
  WCHAR v7; // dx
  bool v8; // zf
  int v9; // ecx
  HKEY v10; // rsi
  DWORD LastError; // ebx
  unsigned int v12; // ebx
  __int64 v13; // rbx
  int v15; // esi
  int v16; // ebx
  int v17; // eax
  unsigned int Data; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  cbData = 4;
  hKey = 0;
  Data = 0;
  if ( !lpValueName )
    return 1801;
  v2 = -1;
  do
    ++v2;
  while ( lpValueName[v2] );
  v3 = *lpValueName;
  if ( !*lpValueName )
    return 1801;
  v4 = 0;
  v5 = 0;
  v6 = lpValueName;
  v7 = *lpValueName;
  while ( v7 )
  {
    if ( v7 == 44 || v5 > (unsigned int)v2 )
      return 1801;
    v8 = v7 == 92;
    v9 = v4 + 1;
    v7 = v6[1];
    if ( !v8 )
      v9 = v4;
    ++v6;
    v4 = v9;
    ++v5;
  }
  if ( v5 > (unsigned int)v2
    || v4 && (v4 != 3 || v3 != 92 || lpValueName[1] != 92 || lpValueName[2] == 92 || lpValueName[v5 - 1] == 92) )
  {
    return 1801;
  }
  DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchUserDevmodes", L"START PATCH: Printer: %ws", lpValueName);
  v10 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v10);
    SetLastError(LastError);
  }
  hKey = 0;
  v12 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Printers\\ConvertUserDevModesCount", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !v12 )
  {
    v13 = (unsigned int)RegQueryValueExW(hKey, lpValueName, 0, 0, (LPBYTE)&Data, &cbData);
    DevmodeSizePatchTelemetry::WriteDbgTraceInfo(
      "LPatchUserDevmodes",
      L"Count of previous attempts : %u. Status : %d",
      Data,
      v13);
    if ( !(_DWORD)v13 && Data )
    {
      DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchUserDevmodes", L"The devmode has already been validated");
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    v15 = 1;
    v16 = LPatchDevmodeOfHandleType(1, lpValueName);
    v17 = LPatchDevmodeOfHandleType(2, lpValueName);
    if ( (v16 & 0xFFFFFFFD) != 0 || (v17 & 0xFFFFFFFD) != 0 )
    {
      DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchUserDevmodes", L"Increase attempts count by one");
      v15 = Data + 1;
    }
    else
    {
      DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchUserDevmodes", L"Complete attempts count");
    }
    Data = v15;
    v12 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  }
  DevmodeSizePatchTelemetry::WriteDbgTraceInfo("LPatchUserDevmodes", L"END PATCH: Patch Status : %d", v12);
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x1400058a0  push    rbp
0x1400058a2  push    rdi
0x1400058a3  sub     rsp, 58h
0x1400058a7  xor     ebp, ebp
0x1400058a9  mov     [rsp+68h+cbData], 4
0x1400058b1  mov     [rsp+68h+hKey], rbp
0x1400058b9  mov     rdi, rcx
0x1400058bc  mov     [rsp+68h+Data], ebp
0x1400058c0  test    rcx, rcx
0x1400058c3  jz      loc_140005B55
0x1400058c9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400058d0  inc     rax
0x1400058d3  cmp     [rcx+rax*2], bp
0x1400058d7  jnz     short loc_1400058D0
0x1400058d9  movzx   r10d, word ptr [rcx]
0x1400058dd  test    r10w, r10w
0x1400058e1  jz      loc_140005B55
0x1400058e7  mov     r9d, ebp
0x1400058ea  mov     r8d, ebp
0x1400058ed  mov     r11, rdi
0x1400058f0  movzx   edx, r10w
0x1400058f4  test    dx, dx
0x1400058f7  jz      short loc_140005929
0x1400058f9  cmp     dx, 2Ch ; ','
0x1400058fd  jz      loc_140005B55
0x140005903  cmp     r8d, eax
0x140005906  ja      loc_140005B55
0x14000590c  cmp     dx, 5Ch ; '\'
0x140005910  lea     ecx, [r9+1]
0x140005914  movzx   edx, word ptr [r11+2]
0x140005919  cmovnz  ecx, r9d
0x14000591d  add     r11, 2
0x140005921  mov     r9d, ecx
0x140005924  inc     r8d
0x140005927  jmp     short loc_1400058F4
0x140005929  cmp     r8d, eax
0x14000592c  ja      loc_140005B55
0x140005932  test    r9d, r9d
0x140005935  jz      short loc_140005971
0x140005937  cmp     r9d, 3
0x14000593b  jnz     loc_140005B55
0x140005941  cmp     r10w, 5Ch ; '\'
0x140005946  jnz     loc_140005B55
0x14000594c  cmp     [rdi+2], r10w
0x140005951  jnz     loc_140005B55
0x140005957  cmp     [rdi+4], r10w
0x14000595c  jz      loc_140005B55
0x140005962  lea     eax, [r8-1]
0x140005966  cmp     [rdi+rax*2], r10w
0x14000596b  jz      loc_140005B55
0x140005971  mov     [rsp+68h+arg_18], rbx
0x140005979  lea     rdx, aStartPatchPrin; "START PATCH: Printer: %ws"
0x140005980  mov     r8, rdi
0x140005983  mov     [rsp+68h+var_18], rsi
0x140005988  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x14000598f  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005994  mov     rsi, [rsp+68h+hKey]
0x14000599c  test    rsi, rsi
0x14000599f  jz      short loc_1400059BA
0x1400059a1  call    cs:__imp_GetLastError
0x1400059a7  mov     rcx, rsi; hKey
0x1400059aa  mov     ebx, eax
0x1400059ac  call    cs:__imp_RegCloseKey
0x1400059b2  mov     ecx, ebx; dwErrCode
0x1400059b4  call    cs:__imp_SetLastError
0x1400059ba  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x1400059bf  lea     rax, [rsp+68h+hKey]
0x1400059c7  mov     [rsp+68h+phkResult], rax; phkResult
0x1400059cc  lea     rdx, SubKey; "Printers\\ConvertUserDevModesCount"
0x1400059d3  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1400059d8  xor     r9d, r9d; lpClass
0x1400059db  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1400059e3  xor     r8d, r8d; Reserved
0x1400059e6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400059ed  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x1400059f1  mov     [rsp+68h+hKey], rbp
0x1400059f9  call    cs:__imp_RegCreateKeyExW
0x1400059ff  mov     ebx, eax
0x140005a01  test    eax, eax
0x140005a03  jnz     loc_140005B25
0x140005a09  mov     rcx, [rsp+68h+hKey]; hKey
0x140005a11  lea     rax, [rsp+68h+cbData]
0x140005a16  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x140005a1b  xor     r9d, r9d; lpType
0x140005a1e  lea     rax, [rsp+68h+Data]
0x140005a23  xor     r8d, r8d; lpReserved
0x140005a26  mov     rdx, rdi; lpValueName
0x140005a29  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140005a2e  call    cs:__imp_RegQueryValueExW
0x140005a34  mov     r8d, [rsp+68h+Data]
0x140005a39  lea     rdx, aCountOfPreviou; "Count of previous attempts : %u. Status"...
0x140005a40  mov     r9d, eax
0x140005a43  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140005a4a  mov     ebx, eax
0x140005a4c  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005a51  test    ebx, ebx
0x140005a53  jnz     short loc_140005A98
0x140005a55  cmp     [rsp+68h+Data], 1
0x140005a5a  jb      short loc_140005A98
0x140005a5c  lea     rdx, aTheDevmodeHasA; "The devmode has already been validated"
0x140005a63  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140005a6a  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005a6f  mov     rcx, [rsp+68h+hKey]; hKey
0x140005a77  test    rcx, rcx
0x140005a7a  jz      short loc_140005A82
0x140005a7c  call    cs:__imp_RegCloseKey
0x140005a82  xor     eax, eax
0x140005a84  mov     rbx, [rsp+68h+arg_18]
0x140005a8c  mov     rsi, [rsp+68h+var_18]
0x140005a91  add     rsp, 58h
0x140005a95  pop     rdi
0x140005a96  pop     rbp
0x140005a97  retn
0x140005a98  mov     esi, 1
0x140005a9d  mov     rdx, rdi
0x140005aa0  mov     ecx, esi
0x140005aa2  call    LPatchDevmodeOfHandleType
0x140005aa7  mov     rdx, rdi
0x140005aaa  mov     ecx, 2
0x140005aaf  mov     ebx, eax
0x140005ab1  call    LPatchDevmodeOfHandleType
0x140005ab6  test    ebx, 0FFFFFFFDh
0x140005abc  jnz     short loc_140005ADA
0x140005abe  test    eax, 0FFFFFFFDh
0x140005ac3  jnz     short loc_140005ADA
0x140005ac5  lea     rdx, aCompleteAttemp; "Complete attempts count"
0x140005acc  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140005ad3  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005ad8  jmp     short loc_140005AF3
0x140005ada  lea     rdx, aIncreaseAttemp; "Increase attempts count by one"
0x140005ae1  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140005ae8  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005aed  mov     esi, [rsp+68h+Data]
0x140005af1  inc     esi
0x140005af3  mov     rcx, [rsp+68h+hKey]; hKey
0x140005afb  lea     rax, [rsp+68h+Data]
0x140005b00  mov     [rsp+68h+samDesired], 4; cbData
0x140005b08  mov     r9d, 4; dwType
0x140005b0e  xor     r8d, r8d; Reserved
0x140005b11  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140005b16  mov     rdx, rdi; lpValueName
0x140005b19  mov     [rsp+68h+Data], esi
0x140005b1d  call    cs:__imp_RegSetValueExW
0x140005b23  mov     ebx, eax
0x140005b25  mov     r8d, ebx
0x140005b28  lea     rdx, aEndPatchPatchS; "END PATCH: Patch Status : %d"
0x140005b2f  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140005b36  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140005b3b  mov     rcx, [rsp+68h+hKey]; hKey
0x140005b43  test    rcx, rcx
0x140005b46  jz      short loc_140005B4E
0x140005b48  call    cs:__imp_RegCloseKey
0x140005b4e  mov     eax, ebx
0x140005b50  jmp     loc_140005A84
0x140005b55  mov     eax, 709h
0x140005b5a  add     rsp, 58h
0x140005b5e  pop     rdi
0x140005b5f  pop     rbp
0x140005b60  retn
```
