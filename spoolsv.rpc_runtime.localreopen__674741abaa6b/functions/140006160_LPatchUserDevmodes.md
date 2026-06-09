# LPatchUserDevmodes

- ea: `0x140006160`
- end: `0x140006453`
- name: `LPatchUserDevmodes`
- size: `755`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005630`

## callees

- `0x140006160`
- `0x14000645c`
- `0x14002591c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006261`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006280`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006280`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400062cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400062cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006306`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006306`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006402`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000635a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000635a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006433`

## string_xrefs

- `0x140006317`: `Count of previous attempts : %u. Status : %d`
- `0x14000633a`: `The devmode has already been validated`
- `0x1400063bf`: `Increase attempts count by one`
- `0x1400063aa`: `Complete attempts count`

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
0x140006160  push    rbp
0x140006162  push    rdi
0x140006163  sub     rsp, 58h
0x140006167  xor     ebp, ebp
0x140006169  mov     [rsp+68h+cbData], 4
0x140006171  mov     [rsp+68h+hKey], rbp
0x140006179  mov     rdi, rcx
0x14000617c  mov     [rsp+68h+Data], ebp
0x140006180  test    rcx, rcx
0x140006183  jz      loc_140006446
0x140006189  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140006190  inc     rax
0x140006193  cmp     [rcx+rax*2], bp
0x140006197  jnz     short loc_140006190
0x140006199  movzx   r10d, word ptr [rcx]
0x14000619d  test    r10w, r10w
0x1400061a1  jz      loc_140006446
0x1400061a7  mov     r9d, ebp
0x1400061aa  mov     r8d, ebp
0x1400061ad  mov     r11, rdi
0x1400061b0  movzx   edx, r10w
0x1400061b4  test    dx, dx
0x1400061b7  jz      short loc_1400061E9
0x1400061b9  cmp     dx, 2Ch ; ','
0x1400061bd  jz      loc_140006446
0x1400061c3  cmp     r8d, eax
0x1400061c6  ja      loc_140006446
0x1400061cc  cmp     dx, 5Ch ; '\'
0x1400061d0  lea     ecx, [r9+1]
0x1400061d4  movzx   edx, word ptr [r11+2]
0x1400061d9  cmovnz  ecx, r9d
0x1400061dd  add     r11, 2
0x1400061e1  mov     r9d, ecx
0x1400061e4  inc     r8d
0x1400061e7  jmp     short loc_1400061B4
0x1400061e9  cmp     r8d, eax
0x1400061ec  ja      loc_140006446
0x1400061f2  test    r9d, r9d
0x1400061f5  jz      short loc_140006231
0x1400061f7  cmp     r9d, 3
0x1400061fb  jnz     loc_140006446
0x140006201  cmp     r10w, 5Ch ; '\'
0x140006206  jnz     loc_140006446
0x14000620c  cmp     [rdi+2], r10w
0x140006211  jnz     loc_140006446
0x140006217  cmp     [rdi+4], r10w
0x14000621c  jz      loc_140006446
0x140006222  lea     eax, [r8-1]
0x140006226  cmp     [rdi+rax*2], r10w
0x14000622b  jz      loc_140006446
0x140006231  mov     [rsp+68h+arg_18], rbx
0x140006239  lea     rdx, aStartPatchPrin; "START PATCH: Printer: %ws"
0x140006240  mov     r8, rdi
0x140006243  mov     [rsp+68h+var_18], rsi
0x140006248  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x14000624f  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006254  mov     rsi, [rsp+68h+hKey]
0x14000625c  test    rsi, rsi
0x14000625f  jz      short loc_14000628C
0x140006261  call    cs:__imp_GetLastError
0x140006268  nop     dword ptr [rax+rax+00h]
0x14000626d  mov     rcx, rsi; hKey
0x140006270  mov     ebx, eax
0x140006272  call    cs:__imp_RegCloseKey
0x140006279  nop     dword ptr [rax+rax+00h]
0x14000627e  mov     ecx, ebx; dwErrCode
0x140006280  call    cs:__imp_SetLastError
0x140006287  nop     dword ptr [rax+rax+00h]
0x14000628c  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x140006291  lea     rax, [rsp+68h+hKey]
0x140006299  mov     [rsp+68h+phkResult], rax; phkResult
0x14000629e  lea     rdx, SubKey; "Printers\\ConvertUserDevModesCount"
0x1400062a5  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1400062aa  xor     r9d, r9d; lpClass
0x1400062ad  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1400062b5  xor     r8d, r8d; Reserved
0x1400062b8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400062bf  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x1400062c3  mov     [rsp+68h+hKey], rbp
0x1400062cb  call    cs:__imp_RegCreateKeyExW
0x1400062d2  nop     dword ptr [rax+rax+00h]
0x1400062d7  mov     ebx, eax
0x1400062d9  test    eax, eax
0x1400062db  jnz     loc_140006410
0x1400062e1  mov     rcx, [rsp+68h+hKey]; hKey
0x1400062e9  lea     rax, [rsp+68h+cbData]
0x1400062ee  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1400062f3  xor     r9d, r9d; lpType
0x1400062f6  lea     rax, [rsp+68h+Data]
0x1400062fb  xor     r8d, r8d; lpReserved
0x1400062fe  mov     rdx, rdi; lpValueName
0x140006301  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140006306  call    cs:__imp_RegQueryValueExW
0x14000630d  nop     dword ptr [rax+rax+00h]
0x140006312  mov     r8d, [rsp+68h+Data]
0x140006317  lea     rdx, aCountOfPreviou; "Count of previous attempts : %u. Status"...
0x14000631e  mov     r9d, eax
0x140006321  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140006328  mov     ebx, eax
0x14000632a  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000632f  test    ebx, ebx
0x140006331  jnz     short loc_14000637D
0x140006333  cmp     [rsp+68h+Data], 1
0x140006338  jb      short loc_14000637D
0x14000633a  lea     rdx, aTheDevmodeHasA; "The devmode has already been validated"
0x140006341  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140006348  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000634d  mov     rcx, [rsp+68h+hKey]; hKey
0x140006355  test    rcx, rcx
0x140006358  jz      short loc_140006366
0x14000635a  call    cs:__imp_RegCloseKey
0x140006361  nop     dword ptr [rax+rax+00h]
0x140006366  xor     eax, eax
0x140006368  mov     rbx, [rsp+68h+arg_18]
0x140006370  mov     rsi, [rsp+68h+var_18]
0x140006375  add     rsp, 58h
0x140006379  pop     rdi
0x14000637a  pop     rbp
0x14000637b  retn
0x14000637d  mov     esi, 1
0x140006382  mov     rdx, rdi
0x140006385  mov     ecx, esi
0x140006387  call    LPatchDevmodeOfHandleType
0x14000638c  mov     rdx, rdi
0x14000638f  mov     ecx, 2
0x140006394  mov     ebx, eax
0x140006396  call    LPatchDevmodeOfHandleType
0x14000639b  test    ebx, 0FFFFFFFDh
0x1400063a1  jnz     short loc_1400063BF
0x1400063a3  test    eax, 0FFFFFFFDh
0x1400063a8  jnz     short loc_1400063BF
0x1400063aa  lea     rdx, aCompleteAttemp; "Complete attempts count"
0x1400063b1  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x1400063b8  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400063bd  jmp     short loc_1400063D8
0x1400063bf  lea     rdx, aIncreaseAttemp; "Increase attempts count by one"
0x1400063c6  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x1400063cd  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400063d2  mov     esi, [rsp+68h+Data]
0x1400063d6  inc     esi
0x1400063d8  mov     rcx, [rsp+68h+hKey]; hKey
0x1400063e0  lea     rax, [rsp+68h+Data]
0x1400063e5  mov     [rsp+68h+samDesired], 4; cbData
0x1400063ed  mov     r9d, 4; dwType
0x1400063f3  xor     r8d, r8d; Reserved
0x1400063f6  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1400063fb  mov     rdx, rdi; lpValueName
0x1400063fe  mov     [rsp+68h+Data], esi
0x140006402  call    cs:__imp_RegSetValueExW
0x140006409  nop     dword ptr [rax+rax+00h]
0x14000640e  mov     ebx, eax
0x140006410  mov     r8d, ebx
0x140006413  lea     rdx, aEndPatchPatchS; "END PATCH: Patch Status : %d"
0x14000641a  lea     rcx, aLpatchuserdevm; "LPatchUserDevmodes"
0x140006421  call    ?WriteDbgTraceInfo@DevmodeSizePatchTelemetry@@SAXPEADPEAGZZ; DevmodeSizePatchTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006426  mov     rcx, [rsp+68h+hKey]; hKey
0x14000642e  test    rcx, rcx
0x140006431  jz      short loc_14000643F
0x140006433  call    cs:__imp_RegCloseKey
0x14000643a  nop     dword ptr [rax+rax+00h]
0x14000643f  mov     eax, ebx
0x140006441  jmp     loc_140006368
0x140006446  mov     eax, 709h
0x14000644b  add     rsp, 58h
0x14000644f  pop     rdi
0x140006450  pop     rbp
0x140006451  retn
```
