# TPrinterDriver::LoadPrinterDriver(void *)

- ea: `0x14000f1e4`
- end: `0x14000f379`
- name: `?LoadPrinterDriver@TPrinterDriver@@IEAAPEAXPEAX@Z`
- size: `405`
- prototype: `void *(TPrinterDriver *__hidden this, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1400069b8`
- `0x14000e89c`
- `0x14000ed78`

## callees

- `0x140001b90`
- `0x140001b9c`
- `0x140001ee0`
- `0x14000f1e4`
- `0x140014a90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f244`
- `KERNEL32!GetLastError` at `0x14000f2d3`
- `KERNEL32!GetLastError` at `0x14000f244`
- `KERNEL32!GetLastError` at `0x14000f2d3`
- `KERNEL32!LoadLibraryExW` at `0x14000f2ab`
- `KERNEL32!LoadLibraryExW` at `0x14000f2ab`
- `WINSPOOL!GetPrinterDriverW` at `0x14000f237`
- `WINSPOOL!GetPrinterDriverW` at `0x14000f28a`
- `WINSPOOL!GetPrinterDriverW` at `0x14000f237`
- `WINSPOOL!GetPrinterDriverW` at `0x14000f28a`

## pseudocode

```c
HMODULE __fastcall TPrinterDriver::LoadPrinterDriver(TPrinterDriver *this, void *a2)
{
  HMODULE Library; // rdi
  LPCWSTR *v4; // rbx
  int v5; // esi
  DWORD LastError; // eax
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  DWORD pcbNeeded; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+60h] [rbp-A0h]
  DWORD v17; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  BYTE pDriverInfo[1024]; // [rsp+80h] [rbp-80h] BYREF

  pcbNeeded = 0;
  if ( GetPrinterDriverW(a2, 0, 5u, pDriverInfo, 0x400u, &pcbNeeded) )
  {
    v5 = 0;
    v4 = (LPCWSTR *)pDriverInfo;
  }
  else
  {
    Library = 0;
    if ( GetLastError() != 122 )
      return Library;
    v4 = (LPCWSTR *)operator new[](pcbNeeded);
    if ( !v4 )
      return Library;
    v5 = 1;
    if ( !GetPrinterDriverW(a2, 0, 5u, (LPBYTE)v4, pcbNeeded, &pcbNeeded) )
    {
LABEL_15:
      operator delete(v4);
      return Library;
    }
  }
  Library = LoadLibraryExW(v4[5], 0, 8u);
  if ( !Library )
  {
    v14 = 116;
    v15 = 4;
    v16 = 0;
    LastError = GetLastError();
    v7 = v4[5];
    v17 = LastError;
    v18 = 4;
    v19 = 0;
    if ( v7 )
    {
      v11 = v7;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      v12 = 2 * v8 + 2;
    }
    else
    {
      v12 = 4;
      v11 = L"-";
    }
    v13 = 1;
    SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, (struct SplLogType *)&v11, &v17, &v14, 0);
  }
  if ( v5 )
    goto LABEL_15;
  return Library;
}

```

## disassembly

```asm
0x14000f1e4  push    rbp
0x14000f1e6  push    rbx
0x14000f1e7  push    rsi
0x14000f1e8  push    rdi
0x14000f1e9  push    r14
0x14000f1eb  push    r15
0x14000f1ed  lea     rbp, [rsp-398h]
0x14000f1f5  sub     rsp, 498h
0x14000f1fc  mov     rax, cs:__security_cookie
0x14000f203  xor     rax, rsp
0x14000f206  mov     [rbp+3C0h+var_40], rax
0x14000f20d  mov     r14, rdx
0x14000f210  lea     rax, [rsp+4C0h+var_490]
0x14000f215  xor     r15d, r15d
0x14000f218  mov     [rsp+4C0h+pcbNeeded], rax; pcbNeeded
0x14000f21d  lea     r9, [rbp+3C0h+pDriverInfo]; pDriverInfo
0x14000f221  mov     [rsp+4C0h+var_490], r15d
0x14000f226  xor     edx, edx; pEnvironment
0x14000f228  mov     [rsp+4C0h+cbBuf], 400h; cbBuf
0x14000f230  mov     rcx, r14; hPrinter
0x14000f233  lea     r8d, [r15+5]; Level
0x14000f237  call    cs:__imp_GetPrinterDriverW
0x14000f23d  test    eax, eax
0x14000f23f  jnz     short loc_14000F29A
0x14000f241  mov     edi, r15d
0x14000f244  call    cs:__imp_GetLastError
0x14000f24a  cmp     eax, 7Ah ; 'z'
0x14000f24d  jnz     loc_14000F357
0x14000f253  mov     ecx, [rsp+4C0h+var_490]; unsigned __int64
0x14000f257  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000f25c  mov     rbx, rax
0x14000f25f  test    rax, rax
0x14000f262  jz      loc_14000F357
0x14000f268  mov     edx, [rsp+4C0h+var_490]
0x14000f26c  lea     rax, [rsp+4C0h+var_490]
0x14000f271  mov     [rsp+4C0h+pcbNeeded], rax; pcbNeeded
0x14000f276  lea     r8d, [r15+5]; Level
0x14000f27a  mov     [rsp+4C0h+cbBuf], edx; cbBuf
0x14000f27e  lea     esi, [r15+1]
0x14000f282  xor     edx, edx; pEnvironment
0x14000f284  mov     r9, rbx; pDriverInfo
0x14000f287  mov     rcx, r14; hPrinter
0x14000f28a  call    cs:__imp_GetPrinterDriverW
0x14000f290  test    eax, eax
0x14000f292  jz      loc_14000F34F
0x14000f298  jmp     short loc_14000F2A1
0x14000f29a  mov     esi, r15d
0x14000f29d  lea     rbx, [rbp+3C0h+pDriverInfo]
0x14000f2a1  mov     rcx, [rbx+28h]; lpLibFileName
0x14000f2a5  xor     edx, edx; hFile
0x14000f2a7  lea     r8d, [rdx+8]; dwFlags
0x14000f2ab  call    cs:__imp_LoadLibraryExW
0x14000f2b1  mov     rdi, rax
0x14000f2b4  test    rax, rax
0x14000f2b7  jnz     loc_14000F34B
0x14000f2bd  lea     r14d, [rax+4]
0x14000f2c1  mov     [rsp+4C0h+var_470], 74h ; 't'
0x14000f2c9  mov     [rsp+4C0h+var_468], r14
0x14000f2ce  mov     [rsp+4C0h+var_460], r15d
0x14000f2d3  call    cs:__imp_GetLastError
0x14000f2d9  mov     rcx, [rbx+28h]
0x14000f2dd  mov     [rsp+4C0h+var_458], eax
0x14000f2e1  mov     [rsp+4C0h+var_450], r14
0x14000f2e6  mov     [rsp+4C0h+var_448], r15d
0x14000f2eb  test    rcx, rcx
0x14000f2ee  jz      short loc_14000F312
0x14000f2f0  mov     [rsp+4C0h+var_488], rcx
0x14000f2f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f2f9  inc     rax
0x14000f2fc  cmp     [rcx+rax*2], r15w
0x14000f301  jnz     short loc_14000F2F9
0x14000f303  lea     rax, ds:2[rax*2]
0x14000f30b  mov     [rsp+4C0h+var_480], rax
0x14000f310  jmp     short loc_14000F323
0x14000f312  lea     rax, asc_14001A8D8; "-"
0x14000f319  mov     [rsp+4C0h+var_480], r14
0x14000f31e  mov     [rsp+4C0h+var_488], rax
0x14000f323  lea     r9, [rsp+4C0h+var_470]
0x14000f328  mov     [rsp+4C0h+var_478], 1
0x14000f330  lea     r8, [rsp+4C0h+var_458]
0x14000f335  mov     qword ptr [rsp+4C0h+cbBuf], r15
0x14000f33a  lea     rdx, [rsp+4C0h+var_488]; struct SplLogType *
0x14000f33f  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x14000f346  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x14000f34b  test    esi, esi
0x14000f34d  jz      short loc_14000F357
0x14000f34f  mov     rcx, rbx; Block
0x14000f352  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f357  mov     rax, rdi
0x14000f35a  mov     rcx, [rbp+3C0h+var_40]
0x14000f361  xor     rcx, rsp; StackCookie
0x14000f364  call    __security_check_cookie
0x14000f369  add     rsp, 498h
0x14000f370  pop     r15
0x14000f372  pop     r14
0x14000f374  pop     rdi
0x14000f375  pop     rsi
0x14000f376  pop     rbx
0x14000f377  pop     rbp
0x14000f378  retn
```
