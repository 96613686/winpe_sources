# CZipFolder::_AreFilesEncrypted(void)

- ea: `0x18001111c`
- end: `0x1800112f0`
- name: `?_AreFilesEncrypted@CZipFolder@@AEAAHXZ`
- size: `468`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012730`

## callees

- `0x18000d7e0`
- `0x18000fe10`
- `0x18001111c`
- `0x180036f50`
- `0x180037958`
- `0x1800390fd`
- `0x1800405b4`
- `0x18006e9a0`

## import_xrefs

- `SHELL32!__imp_PathIsSlowW` at `0x1800112c0`
- `SHELL32!__imp_PathIsSlowW` at `0x1800112c0`
- `SHLWAPI!PathIsUNCW` at `0x180011233`
- `SHLWAPI!PathIsUNCW` at `0x180011233`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800112a9`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800112a9`

## pseudocode

```c
__int64 __fastcall CZipFolder::_AreFilesEncrypted(CZipFolder *this, __int64 a2, int a3, int a4)
{
  unsigned int v5; // edi
  size_t *v6; // r8
  int v8; // r14d
  int i; // esi
  PEVENT_DATA_DESCRIPTOR v10; // [rsp+20h] [rbp-E0h]
  _BYTE v11[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+34h] [rbp-CCh]
  wchar_t *v13; // [rsp+38h] [rbp-C8h]
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+5Ch] [rbp-A4h]
  __int64 v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+78h] [rbp-88h]
  _BYTE *v18; // [rsp+A4h] [rbp-5Ch]
  wchar_t pszDest[916]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v20[4240]; // [rsp+7E0h] [rbp+6E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+1870h] [rbp+1770h] BYREF

  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&ShellTraceId_ZipFolder_CheckEncrypted_Start, a3, a4, &v21);
  if ( *((_DWORD *)this + 285) )
  {
    v5 = *((_DWORD *)this + 284);
  }
  else
  {
    v5 = 0;
    memset_0(v20, 0, 0x1086u);
    memcpy_0(v11, &unk_1800721A0, 0x7A4u);
    if ( this != (CZipFolder *)-72LL )
    {
      if ( StringCopyWorkerW(pszDest, 0x104u, v6, (STRSAFE_PCNZWCH)this + 36, (size_t)v10) < 0 )
        goto LABEL_9;
      v13 = pszDest;
    }
    v12 = 1;
    v18 = v20;
    v14 = 0;
    v15 = 0;
    v16 = 1;
    if ( !(unsigned int)dunzip(v11) )
    {
      if ( PathIsUNCW((LPCWSTR)this + 36)
        || GetDriveTypeW((LPCWSTR)this + 36) == 4
        || (v8 = 2000, PathIsSlowW((LPCWSTR)this + 36, 0xFFFFFFFF)) )
      {
        v8 = 20;
      }
      if ( v17 < v8 )
        v8 = v17;
      for ( i = 0; i < v8; ++i )
      {
        v12 = 7;
        v14 = i;
        if ( !(unsigned int)dunzip(v11) && (*((_DWORD *)v18 + 6) & 0x8000) != 0 )
        {
          v5 = 1;
          break;
        }
      }
    }
    *((_DWORD *)this + 284) = v5;
    *((_DWORD *)this + 285) = 1;
  }
LABEL_9:
  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&ShellTraceId_ZipFolder_CheckEncrypted_Stop, a3, a4, &v21);
  return v5;
}

```

## disassembly

```asm
0x18001111c  push    rbp
0x18001111e  push    rbx
0x18001111f  push    rsi
0x180011120  push    rdi
0x180011121  push    r12
0x180011123  push    r14
0x180011125  lea     rbp, [rsp-1798h]
0x18001112d  mov     eax, 1898h
0x180011132  call    _alloca_probe
0x180011137  sub     rsp, rax
0x18001113a  mov     rax, cs:__security_cookie
0x180011141  xor     rax, rsp
0x180011144  mov     [rbp+17C0h+var_40], rax
0x18001114b  mov     r12d, 1
0x180011151  mov     rbx, rcx
0x180011154  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, r12b
0x18001115b  jnz     loc_180011289
0x180011161  cmp     dword ptr [rbx+474h], 0
0x180011168  jnz     loc_180011228
0x18001116e  xor     edx, edx; Val
0x180011170  lea     rcx, [rbp+17C0h+var_10E0]; void *
0x180011177  mov     r8d, 1086h; Size
0x18001117d  xor     edi, edi
0x18001117f  call    memset_0
0x180011184  lea     rcx, [rsp+18C0h+var_1890]; void *
0x180011189  mov     r8d, 7A4h; Size
0x18001118f  lea     rdx, unk_1800721A0; Src
0x180011196  lea     rsi, [rbx+48h]
0x18001119a  call    memcpy_0
0x18001119f  test    rsi, rsi
0x1800111a2  jz      short loc_1800111C2
0x1800111a4  mov     r9, rsi; pszSrc
0x1800111a7  lea     rcx, [rbp+17C0h+pszDest]; pszDest
0x1800111ab  mov     edx, 104h; cchDest
0x1800111b0  call    StringCopyWorkerW
0x1800111b5  test    eax, eax
0x1800111b7  js      short loc_1800111FA
0x1800111b9  lea     rax, [rbp+17C0h+pszDest]
0x1800111bd  mov     [rsp+18C0h+var_1888], rax
0x1800111c2  lea     rax, [rbp+17C0h+var_10E0]
0x1800111c9  mov     [rsp+18C0h+var_188C], r12d
0x1800111ce  lea     rcx, [rsp+18C0h+var_1890]
0x1800111d3  mov     [rbp+17C0h+var_181C], rax
0x1800111d7  mov     [rsp+18C0h+var_1878], edi
0x1800111db  mov     [rsp+18C0h+var_1864], edi
0x1800111df  mov     [rsp+18C0h+var_1860], r12
0x1800111e4  call    dunzip
0x1800111e9  test    eax, eax
0x1800111eb  jz      short loc_180011230
0x1800111ed  mov     [rbx+470h], edi
0x1800111f3  mov     [rbx+474h], r12d
0x1800111fa  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, r12b
0x180011201  jnz     loc_1800112D3
0x180011207  mov     eax, edi
0x180011209  mov     rcx, [rbp+17C0h+var_40]
0x180011210  xor     rcx, rsp; StackCookie
0x180011213  call    __security_check_cookie
0x180011218  add     rsp, 1898h
0x18001121f  pop     r14
0x180011221  pop     r12
0x180011223  pop     rdi
0x180011224  pop     rsi
0x180011225  pop     rbx
0x180011226  pop     rbp
0x180011227  retn
0x180011228  mov     edi, [rbx+470h]
0x18001122e  jmp     short loc_1800111FA
0x180011230  mov     rcx, rsi; pszPath
0x180011233  call    cs:__imp_PathIsUNCW
0x180011239  test    eax, eax
0x18001123b  jz      short loc_1800112A6
0x18001123d  mov     r14d, 14h
0x180011243  cmp     [rsp+18C0h+var_1848], r14d
0x180011248  cmovl   r14d, [rsp+18C0h+var_1848]
0x18001124e  xor     esi, esi
0x180011250  cmp     esi, r14d
0x180011253  jge     short loc_1800111ED
0x180011255  lea     rcx, [rsp+18C0h+var_1890]
0x18001125a  mov     [rsp+18C0h+var_188C], 7
0x180011262  mov     [rsp+18C0h+var_1878], esi
0x180011266  call    dunzip
0x18001126b  test    eax, eax
0x18001126d  jnz     short loc_18001127C
0x18001126f  mov     rax, [rbp+17C0h+var_181C]
0x180011273  test    dword ptr [rax+18h], 8000h
0x18001127a  jnz     short loc_180011281
0x18001127c  add     esi, r12d
0x18001127f  jmp     short loc_180011250
0x180011281  mov     edi, r12d
0x180011284  jmp     loc_1800111ED
0x180011289  lea     rax, [rbp+17C0h+var_50]
0x180011290  lea     rdx, ShellTraceId_ZipFolder_CheckEncrypted_Start; int
0x180011297  mov     [rsp+18C0h+var_18A0], rax; PEVENT_DATA_DESCRIPTOR
0x18001129c  call    McGenEventWrite_EventWriteTransfer
0x1800112a1  jmp     loc_180011161
0x1800112a6  mov     rcx, rsi; lpRootPathName
0x1800112a9  call    cs:__imp_GetDriveTypeW
0x1800112af  cmp     eax, 4
0x1800112b2  jz      short loc_18001123D
0x1800112b4  or      edx, 0FFFFFFFFh; dwAttr
0x1800112b7  mov     rcx, rsi; pszFile
0x1800112ba  mov     r14d, 7D0h
0x1800112c0  call    cs:__imp_PathIsSlowW
0x1800112c6  test    eax, eax
0x1800112c8  jz      loc_180011243
0x1800112ce  jmp     loc_18001123D
0x1800112d3  lea     rax, [rbp+17C0h+var_50]
0x1800112da  lea     rdx, ShellTraceId_ZipFolder_CheckEncrypted_Stop; int
0x1800112e1  mov     [rsp+18C0h+var_18A0], rax; PEVENT_DATA_DESCRIPTOR
0x1800112e6  call    McGenEventWrite_EventWriteTransfer
0x1800112eb  jmp     loc_180011207
```
