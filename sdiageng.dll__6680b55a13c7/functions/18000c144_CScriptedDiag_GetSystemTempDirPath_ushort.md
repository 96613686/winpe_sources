# CScriptedDiag::GetSystemTempDirPath(ushort * *)

- ea: `0x18000c144`
- end: `0x18000c314`
- name: `?GetSystemTempDirPath@CScriptedDiag@@AEAAJPEAPEAG@Z`
- size: `464`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c3fc`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x1800020f8`
- `0x18000c144`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c209`
- `msvcrt!_wcsicmp` at `0x18000c25e`
- `msvcrt!_wcsicmp` at `0x18000c209`
- `msvcrt!_wcsicmp` at `0x18000c25e`
- `KERNEL32!GetLastError` at `0x18000c1bf`
- `KERNEL32!GetLastError` at `0x18000c237`
- `KERNEL32!GetLastError` at `0x18000c27a`
- `KERNEL32!GetLastError` at `0x18000c1bf`
- `KERNEL32!GetLastError` at `0x18000c237`
- `KERNEL32!GetLastError` at `0x18000c27a`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000c270`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000c270`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c1b5`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c22d`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c1b5`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18000c22d`

## string_xrefs

- `0x18000c16e`: `CScriptedDiag::GetSystemTempDirPath`
- `0x18000c1e7`: `CScriptedDiag::GetSystemTempDirPath`
- `0x18000c2ce`: `CScriptedDiag::GetSystemTempDirPath`
- `0x18000c221`: `%TEMP%`
- `0x18000c254`: `%TEMP%`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::GetSystemTempDirPath(CScriptedDiag *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbp
  unsigned int v4; // ebx
  int v5; // r8d
  WCHAR *v6; // rax
  wchar_t *v7; // rdi
  signed int LastError; // eax
  int v9; // r8d
  signed int v10; // eax
  UINT WindowsDirectoryW; // eax
  signed int v12; // eax
  int v13; // eax
  unsigned __int16 *v15; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v15 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 1911;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::GetSystemTempDirPath", v5, v4);
    return v4;
  }
  v6 = (WCHAR *)operator new[](0x208u);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    v5 = 1914;
    goto LABEL_3;
  }
  if ( !ExpandEnvironmentStringsForUserW(0, L"%TMP%", v6, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v9 = 1924;
LABEL_10:
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    goto LABEL_12;
  }
  v4 = 0;
  if ( _wcsicmp(v7, L"%TMP%") )
    goto LABEL_14;
  if ( !ExpandEnvironmentStringsForUserW(0, L"%TEMP%", v7, 0x104u) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    v9 = 1941;
    goto LABEL_10;
  }
  if ( _wcsicmp(v7, L"%TEMP%") )
  {
LABEL_14:
    *a2 = v7;
    return v4;
  }
  WindowsDirectoryW = GetWindowsDirectoryW(v7, 0x104u);
  if ( !WindowsDirectoryW )
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    v9 = 1956;
    goto LABEL_10;
  }
  if ( WindowsDirectoryW > 0x104 )
  {
    v4 = -2147024785;
    v9 = 1960;
LABEL_12:
    SdpDebugTrace(1u, L"CScriptedDiag::GetSystemTempDirPath", v9, v4);
    goto LABEL_29;
  }
  v13 = SdpBuildPath(v7, L"Temp", &v15);
  v4 = v13;
  if ( v13 >= 0 )
  {
    *a2 = v15;
  }
  else
  {
    SdpDebugTrace(1u, L"CScriptedDiag::GetSystemTempDirPath", 1964, v13);
    v2 = v15;
  }
LABEL_29:
  operator delete(v7);
  if ( v2 )
    operator delete(v2);
  return v4;
}

```

## disassembly

```asm
0x18000c144  mov     [rsp+arg_0], rcx
0x18000c149  push    rbx
0x18000c14a  push    rbp
0x18000c14b  push    rsi
0x18000c14c  push    rdi
0x18000c14d  sub     rsp, 28h
0x18000c151  xor     ebp, ebp
0x18000c153  mov     rsi, rdx
0x18000c156  mov     [rsp+48h+arg_0], rbp
0x18000c15b  test    rdx, rdx
0x18000c15e  jnz     short loc_18000C184
0x18000c160  mov     ebx, 80070057h
0x18000c165  mov     r8d, 777h; int
0x18000c16b  mov     r9d, ebx; int
0x18000c16e  lea     rdx, aCscripteddiagG_11; "CScriptedDiag::GetSystemTempDirPath"
0x18000c175  mov     ecx, 1; Level
0x18000c17a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c17f  jmp     loc_18000C309
0x18000c184  mov     ecx, 208h; unsigned __int64
0x18000c189  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c18e  mov     rdi, rax
0x18000c191  test    rax, rax
0x18000c194  jnz     short loc_18000C1A3
0x18000c196  mov     ebx, 8007000Eh
0x18000c19b  mov     r8d, 77Ah
0x18000c1a1  jmp     short loc_18000C16B
0x18000c1a3  mov     r9d, 104h; dwSize
0x18000c1a9  lea     rdx, aTmp; "%TMP%"
0x18000c1b0  mov     r8, rdi; lpDest
0x18000c1b3  xor     ecx, ecx; hToken
0x18000c1b5  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000c1bb  test    eax, eax
0x18000c1bd  jnz     short loc_18000C1FD
0x18000c1bf  call    cs:__imp_GetLastError
0x18000c1c5  mov     ebx, eax
0x18000c1c7  test    eax, eax
0x18000c1c9  jle     short loc_18000C1D4
0x18000c1cb  movzx   ebx, ax
0x18000c1ce  or      ebx, 80070000h
0x18000c1d4  mov     r8d, 784h; int
0x18000c1da  test    ebx, ebx
0x18000c1dc  mov     eax, 80004005h
0x18000c1e1  cmovns  ebx, eax
0x18000c1e4  mov     r9d, ebx; int
0x18000c1e7  lea     rdx, aCscripteddiagG_11; "CScriptedDiag::GetSystemTempDirPath"
0x18000c1ee  mov     ecx, 1; Level
0x18000c1f3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c1f8  jmp     loc_18000C2F4
0x18000c1fd  lea     rdx, aTmp; "%TMP%"
0x18000c204  mov     rcx, rdi; String1
0x18000c207  xor     ebx, ebx
0x18000c209  call    cs:__imp__wcsicmp
0x18000c20f  test    eax, eax
0x18000c211  jz      short loc_18000C21B
0x18000c213  mov     [rsi], rdi
0x18000c216  jmp     loc_18000C309
0x18000c21b  mov     r9d, 104h; dwSize
0x18000c221  lea     rdx, aTemp; "%TEMP%"
0x18000c228  mov     r8, rdi; lpDest
0x18000c22b  xor     ecx, ecx; hToken
0x18000c22d  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18000c233  test    eax, eax
0x18000c235  jnz     short loc_18000C254
0x18000c237  call    cs:__imp_GetLastError
0x18000c23d  mov     ebx, eax
0x18000c23f  test    eax, eax
0x18000c241  jle     short loc_18000C24C
0x18000c243  movzx   ebx, ax
0x18000c246  or      ebx, 80070000h
0x18000c24c  mov     r8d, 795h
0x18000c252  jmp     short loc_18000C1DA
0x18000c254  lea     rdx, aTemp; "%TEMP%"
0x18000c25b  mov     rcx, rdi; String1
0x18000c25e  call    cs:__imp__wcsicmp
0x18000c264  test    eax, eax
0x18000c266  jnz     short loc_18000C213
0x18000c268  mov     edx, 104h; uSize
0x18000c26d  mov     rcx, rdi; lpBuffer
0x18000c270  call    cs:__imp_GetWindowsDirectoryW
0x18000c276  test    eax, eax
0x18000c278  jnz     short loc_18000C29A
0x18000c27a  call    cs:__imp_GetLastError
0x18000c280  mov     ebx, eax
0x18000c282  test    eax, eax
0x18000c284  jle     short loc_18000C28F
0x18000c286  movzx   ebx, ax
0x18000c289  or      ebx, 80070000h
0x18000c28f  mov     r8d, 7A4h
0x18000c295  jmp     loc_18000C1DA
0x18000c29a  cmp     eax, 104h
0x18000c29f  jbe     short loc_18000C2B1
0x18000c2a1  mov     ebx, 8007006Fh
0x18000c2a6  mov     r8d, 7A8h
0x18000c2ac  jmp     loc_18000C1E4
0x18000c2b1  lea     r8, [rsp+48h+arg_0]; unsigned __int16 **
0x18000c2b6  mov     rcx, rdi; unsigned __int16 *
0x18000c2b9  lea     rdx, aTemp_0; "Temp"
0x18000c2c0  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000c2c5  mov     ebx, eax
0x18000c2c7  test    eax, eax
0x18000c2c9  jns     short loc_18000C2EC
0x18000c2cb  mov     r9d, eax; int
0x18000c2ce  lea     rdx, aCscripteddiagG_11; "CScriptedDiag::GetSystemTempDirPath"
0x18000c2d5  mov     r8d, 7ACh; int
0x18000c2db  mov     ecx, 1; Level
0x18000c2e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c2e5  mov     rbp, [rsp+48h+arg_0]
0x18000c2ea  jmp     short loc_18000C2F4
0x18000c2ec  mov     rax, [rsp+48h+arg_0]
0x18000c2f1  mov     [rsi], rax
0x18000c2f4  mov     rcx, rdi; Block
0x18000c2f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c2fc  test    rbp, rbp
0x18000c2ff  jz      short loc_18000C309
0x18000c301  mov     rcx, rbp; Block
0x18000c304  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c309  mov     eax, ebx
0x18000c30b  add     rsp, 28h
0x18000c30f  pop     rdi
0x18000c310  pop     rsi
0x18000c311  pop     rbp
0x18000c312  pop     rbx
0x18000c313  retn
```
