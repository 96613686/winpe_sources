# WdcGetTempFileName(ushort *,ulong)

- ea: `0x1800373f0`
- end: `0x18003752b`
- name: `?WdcGetTempFileName@@YAJPEAGK@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned __int16 *, const char *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180026b48`
- `0x180052168`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800373f0`
- `0x180064cf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037456`
- `KERNEL32!GetLastError` at `0x180037493`
- `KERNEL32!GetLastError` at `0x1800374d3`
- `KERNEL32!GetLastError` at `0x180037456`
- `KERNEL32!GetLastError` at `0x180037493`
- `KERNEL32!GetLastError` at `0x1800374d3`
- `KERNEL32!DeleteFileW` at `0x1800374c9`
- `KERNEL32!DeleteFileW` at `0x1800374c9`
- `KERNEL32!GetTempPath2W` at `0x18003744c`
- `KERNEL32!GetTempPath2W` at `0x18003744c`
- `KERNEL32!GetTempFileNameW` at `0x180037489`
- `KERNEL32!GetTempFileNameW` at `0x180037489`

## string_xrefs

- `0x180037427`: `WdcGetTempFileName`
- `0x180037516`: `WdcGetTempFileName`

## pseudocode

```c
__int64 __fastcall WdcGetTempFileName(unsigned __int16 *a1, const char *a2, int a3)
{
  WCHAR *v4; // rdi
  signed int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  int v8; // eax
  const char *v9; // rdx
  int v10; // r8d
  unsigned __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v4 = (WCHAR *)WdcAlloc(0x208u, a2, a3);
  if ( v4 )
  {
    *v4 = 0;
    if ( !(unsigned int)GetTempPath2W(260, v4) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( !LastError )
        goto LABEL_19;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_20;
    }
    if ( GetTempFileNameW(v4, L"wdc", 0, a1) )
      goto LABEL_13;
    v7 = GetLastError();
    v5 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_13:
        v8 = StringCchLengthW(a1, 0x400u, &v12);
        v5 = v8;
        if ( v8 >= 0 )
        {
          if ( !DeleteFileW(a1) )
            GetLastError();
          v5 = 0;
          goto LABEL_17;
        }
LABEL_21:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
          "WdcGetTempFileName",
          0,
          L"FAILURE: 0x%08x",
          v8);
LABEL_17:
        WdcFree(v4, v9, v10);
        return (unsigned int)v5;
      }
LABEL_20:
      v8 = v5;
      goto LABEL_21;
    }
LABEL_19:
    v5 = -2147467259;
    goto LABEL_20;
  }
  v5 = -2147024882;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
    "WdcGetTempFileName",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800373f0  mov     [rsp+arg_0], rbx
0x1800373f5  mov     [rsp+arg_8], rsi
0x1800373fa  push    rdi
0x1800373fb  sub     rsp, 30h
0x1800373ff  mov     rsi, rcx
0x180037402  mov     ecx, 208h; dwBytes
0x180037407  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18003740c  mov     rdi, rax
0x18003740f  test    rax, rax
0x180037412  jnz     short loc_18003743F
0x180037414  mov     ebx, 8007000Eh
0x180037419  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180037420  xor     r8d, r8d; int
0x180037423  mov     [rsp+38h+var_18], ebx
0x180037427  lea     rdx, aWdcgettempfile; "WdcGetTempFileName"
0x18003742e  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180037435  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003743a  jmp     loc_1800374EF
0x18003743f  xor     eax, eax
0x180037441  mov     rdx, rdi
0x180037444  mov     ecx, 104h
0x180037449  mov     [rdi], ax
0x18003744c  call    cs:__imp_GetTempPath2W
0x180037452  test    eax, eax
0x180037454  jnz     short loc_180037479
0x180037456  call    cs:__imp_GetLastError
0x18003745c  mov     ebx, eax
0x18003745e  test    eax, eax
0x180037460  jz      loc_180037501
0x180037466  jle     short loc_180037471
0x180037468  movzx   ebx, ax
0x18003746b  or      ebx, 80070000h
0x180037471  test    ebx, ebx
0x180037473  js      loc_180037506
0x180037479  mov     r9, rsi; lpTempFileName
0x18003747c  lea     rdx, PrefixString; "wdc"
0x180037483  xor     r8d, r8d; uUnique
0x180037486  mov     rcx, rdi; lpPathName
0x180037489  call    cs:__imp_GetTempFileNameW
0x18003748f  test    eax, eax
0x180037491  jnz     short loc_1800374AE
0x180037493  call    cs:__imp_GetLastError
0x180037499  mov     ebx, eax
0x18003749b  test    eax, eax
0x18003749d  jz      short loc_180037501
0x18003749f  jle     short loc_1800374AA
0x1800374a1  movzx   ebx, ax
0x1800374a4  or      ebx, 80070000h
0x1800374aa  test    ebx, ebx
0x1800374ac  js      short loc_180037506
0x1800374ae  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x1800374b3  mov     edx, 400h; unsigned __int64
0x1800374b8  mov     rcx, rsi; unsigned __int16 *
0x1800374bb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800374c0  mov     ebx, eax
0x1800374c2  test    eax, eax
0x1800374c4  js      short loc_180037508
0x1800374c6  mov     rcx, rsi; lpFileName
0x1800374c9  call    cs:__imp_DeleteFileW
0x1800374cf  test    eax, eax
0x1800374d1  jnz     short loc_1800374E5
0x1800374d3  call    cs:__imp_GetLastError
0x1800374d9  test    eax, eax
0x1800374db  jle     short loc_1800374E5
0x1800374dd  movzx   eax, ax
0x1800374e0  or      eax, 80070000h
0x1800374e5  xor     ebx, ebx
0x1800374e7  mov     rcx, rdi; void *
0x1800374ea  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x1800374ef  mov     rsi, [rsp+38h+arg_8]
0x1800374f4  mov     eax, ebx
0x1800374f6  mov     rbx, [rsp+38h+arg_0]
0x1800374fb  add     rsp, 30h
0x1800374ff  pop     rdi
0x180037500  retn
0x180037501  mov     ebx, 80004005h
0x180037506  mov     eax, ebx
0x180037508  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18003750f  mov     [rsp+38h+var_18], eax
0x180037513  xor     r8d, r8d; int
0x180037516  lea     rdx, aWdcgettempfile; "WdcGetTempFileName"
0x18003751d  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180037524  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037529  jmp     short loc_1800374E7
```
