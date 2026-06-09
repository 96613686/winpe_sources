# SxMergeExtraLogs(ushort const *,ulong)

- ea: `0x14000f510`
- end: `0x14000f797`
- name: `?SxMergeExtraLogs@@YAJPEBGK@Z`
- size: `647`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000f7a0`

## callees

- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000f24c`
- `0x14000f510`
- `0x140010168`
- `0x140010744`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14000f700`
- `KERNEL32!MoveFileExW` at `0x14000f700`
- `KERNEL32!DeleteFileW` at `0x14000f661`
- `KERNEL32!DeleteFileW` at `0x14000f661`
- `KERNEL32!GetLastError` at `0x14000f66f`
- `KERNEL32!GetLastError` at `0x14000f70a`
- `KERNEL32!GetLastError` at `0x14000f66f`
- `KERNEL32!GetLastError` at `0x14000f70a`

## pseudocode

```c
__int64 __fastcall SxMergeExtraLogs(const unsigned __int16 *a1, unsigned int a2)
{
  __int16 v3; // ax
  int v4; // ebx
  signed int v5; // edi
  unsigned int v6; // r14d
  const unsigned __int16 *v7; // rdx
  signed int LastError; // eax
  __int16 v9; // ax
  __int64 v10; // r9
  signed int v11; // eax
  unsigned int v12; // ebx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-29h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-9h] BYREF
  __int16 v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+56h] [rbp-3h]
  unsigned int v19; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v20; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+77h] BYREF

  v20 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxMergeExtraLogs", 0x159u, 1u);
  v21 = 0;
  lpFileName[0] = (LPCWSTR)qword_140013960;
  lpNewFileName[0] = (LPCWSTR)qword_140013960;
  v20 = 0;
  v19 = 0;
  lpFileName[1] = 0;
  lpNewFileName[1] = 0;
  if ( !a1 )
  {
    v16 = -2147024809;
    v3 = 356;
    goto LABEL_34;
  }
  v16 = 0;
  v17 = 357;
  v16 = SxGet0XLogFileCount(a1, &v21, &v20, &v19);
  v3 = 364;
  if ( v16 < 0 )
    goto LABEL_34;
  v17 = 364;
  if ( !v20 )
  {
    v16 = 0;
    v17 = 369;
    goto LABEL_35;
  }
  v4 = 2;
  v5 = -v19;
  v6 = 2;
  if ( (signed int)-v19 > 2 )
    goto LABEL_35;
  while ( 1 )
  {
    v7 = L"%s.%d.%s";
    if ( v4 >= (int)(3 - v20) )
    {
      v16 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, (unsigned int)v4, L"etl");
      v3 = 384;
      if ( v16 < 0 )
        goto LABEL_34;
      v17 = 384;
      if ( DeleteFileW(lpFileName[0]) )
        goto LABEL_25;
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError;
        v3 = 388;
        goto LABEL_34;
      }
      v9 = 388;
      goto LABEL_14;
    }
    v10 = (unsigned int)-v4;
    if ( v4 > 0 )
      v10 = (unsigned int)v4;
    if ( v4 < 0 )
      v7 = L"%s.0.%d.%s";
    v16 = CBsString::Format((CBsString *)lpFileName, v7, a1, v10, L"etl");
    v3 = 400;
    if ( v16 < 0 )
      goto LABEL_34;
    v17 = 400;
    v16 = CBsString::Format((CBsString *)lpNewFileName, L"%s.%d.%s", a1, v6, L"etl");
    v3 = 405;
    if ( v16 < 0 )
      goto LABEL_34;
    v17 = 405;
    if ( MoveFileExW(lpFileName[0], lpNewFileName[0], 1u) )
    {
      --v6;
      goto LABEL_25;
    }
    v11 = GetLastError();
    if ( v11 != 2 )
      break;
    v9 = 410;
LABEL_14:
    v16 = 0;
    v17 = v9;
LABEL_25:
    if ( --v4 < v5 )
      goto LABEL_35;
  }
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  v16 = v11;
  v3 = 410;
LABEL_34:
  v18 = v3;
LABEL_35:
  v12 = v16;
  CBsString::_Release((CBsString *)lpNewFileName);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v12;
}

```

## disassembly

```asm
0x14000f510  mov     [rsp-8+arg_8], edx
0x14000f514  push    rbp
0x14000f515  push    rbx
0x14000f516  push    rsi
0x14000f517  push    rdi
0x14000f518  push    r14
0x14000f51a  lea     rbp, [rsp-37h]
0x14000f51f  sub     rsp, 90h
0x14000f526  mov     rsi, rcx
0x14000f529  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f530  lea     rax, WPP_GLOBAL_Control
0x14000f537  cmp     rcx, rax
0x14000f53a  jz      short loc_14000F55A
0x14000f53c  test    dword ptr [rcx+1Ch], 20000000h
0x14000f543  jz      short loc_14000F55A
0x14000f545  mov     rcx, [rcx+10h]
0x14000f549  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000f550  mov     edx, 13h
0x14000f555  call    WPP_SF_
0x14000f55a  mov     r9d, 1; unsigned __int16
0x14000f560  lea     rdx, aSxmergeextralo; "SxMergeExtraLogs"
0x14000f567  mov     r8d, 159h; unsigned __int16
0x14000f56d  lea     rcx, [rbp+57h+var_60]; this
0x14000f571  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000f576  mov     [rbp+57h+arg_10], 0
0x14000f57d  lea     rax, qword_140013960
0x14000f584  mov     [rbp+57h+lpFileName], rax
0x14000f588  mov     [rbp+57h+lpNewFileName], rax
0x14000f58c  mov     [rbp+57h+arg_8], 0
0x14000f593  mov     [rbp+57h+arg_0], 0
0x14000f59a  mov     [rbp+57h+var_78], 0
0x14000f5a2  mov     [rbp+57h+var_68], 0
0x14000f5aa  test    rsi, rsi
0x14000f5ad  jz      loc_14000F759
0x14000f5b3  mov     eax, 165h
0x14000f5b8  mov     [rbp+57h+var_60], 0
0x14000f5bf  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x14000f5c3  mov     [rbp+57h+var_5C], ax
0x14000f5c7  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x14000f5cb  mov     rcx, rsi; unsigned __int16 *
0x14000f5ce  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x14000f5d2  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x14000f5d7  mov     [rbp+57h+var_60], eax
0x14000f5da  test    eax, eax
0x14000f5dc  mov     eax, 16Ch
0x14000f5e1  js      loc_14000F765
0x14000f5e7  cmp     [rbp+57h+arg_8], 0
0x14000f5eb  mov     [rbp+57h+var_5C], ax
0x14000f5ef  jnz     short loc_14000F606
0x14000f5f1  mov     eax, 171h
0x14000f5f6  mov     [rbp+57h+var_60], 0
0x14000f5fd  mov     [rbp+57h+var_5C], ax
0x14000f601  jmp     loc_14000F769
0x14000f606  mov     edi, [rbp+57h+arg_0]
0x14000f609  mov     ebx, 2
0x14000f60e  neg     edi
0x14000f610  mov     r14d, ebx
0x14000f613  cmp     edi, ebx
0x14000f615  jg      loc_14000F769
0x14000f61b  lea     rcx, aEtl; "etl"
0x14000f622  mov     eax, 3
0x14000f627  sub     eax, [rbp+57h+arg_8]
0x14000f62a  lea     rdx, aSDS; "%s.%d.%s"
0x14000f631  mov     [rsp+0B0h+var_90], rcx
0x14000f636  mov     r9d, ebx
0x14000f639  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f63d  mov     r8, rsi
0x14000f640  cmp     ebx, eax
0x14000f642  jl      short loc_14000F693
0x14000f644  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f649  mov     [rbp+57h+var_60], eax
0x14000f64c  test    eax, eax
0x14000f64e  mov     eax, 180h
0x14000f653  js      loc_14000F765
0x14000f659  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14000f65d  mov     [rbp+57h+var_5C], ax
0x14000f661  call    cs:__imp_DeleteFileW
0x14000f667  test    eax, eax
0x14000f669  jnz     loc_14000F722
0x14000f66f  call    cs:__imp_GetLastError
0x14000f675  cmp     eax, 2
0x14000f678  jnz     loc_14000F72D
0x14000f67e  mov     eax, 184h
0x14000f683  mov     [rbp+57h+var_60], 0
0x14000f68a  mov     [rbp+57h+var_5C], ax
0x14000f68e  jmp     loc_14000F722
0x14000f693  neg     r9d
0x14000f696  lea     rax, aS0DS; "%s.0.%d.%s"
0x14000f69d  cmovs   r9d, ebx
0x14000f6a1  test    ebx, ebx
0x14000f6a3  cmovs   rdx, rax; unsigned __int16 *
0x14000f6a7  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f6ac  mov     [rbp+57h+var_60], eax
0x14000f6af  test    eax, eax
0x14000f6b1  mov     eax, 190h
0x14000f6b6  js      loc_14000F765
0x14000f6bc  mov     [rbp+57h+var_5C], ax
0x14000f6c0  lea     rdx, aSDS; "%s.%d.%s"
0x14000f6c7  lea     rax, aEtl; "etl"
0x14000f6ce  mov     r9d, r14d
0x14000f6d1  mov     r8, rsi
0x14000f6d4  mov     [rsp+0B0h+var_90], rax
0x14000f6d9  lea     rcx, [rbp+57h+lpNewFileName]; this
0x14000f6dd  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f6e2  mov     [rbp+57h+var_60], eax
0x14000f6e5  test    eax, eax
0x14000f6e7  mov     eax, 195h
0x14000f6ec  js      short loc_14000F765
0x14000f6ee  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x14000f6f2  mov     r8d, 1; dwFlags
0x14000f6f8  mov     rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x14000f6fc  mov     [rbp+57h+var_5C], ax
0x14000f700  call    cs:__imp_MoveFileExW
0x14000f706  test    eax, eax
0x14000f708  jnz     short loc_14000F71F
0x14000f70a  call    cs:__imp_GetLastError
0x14000f710  cmp     eax, 2
0x14000f713  jnz     short loc_14000F743
0x14000f715  mov     eax, 19Ah
0x14000f71a  jmp     loc_14000F683
0x14000f71f  dec     r14d
0x14000f722  dec     ebx
0x14000f724  cmp     ebx, edi
0x14000f726  jl      short loc_14000F769
0x14000f728  jmp     loc_14000F61B
0x14000f72d  test    eax, eax
0x14000f72f  jle     short loc_14000F739
0x14000f731  movzx   eax, ax
0x14000f734  or      eax, 80070000h
0x14000f739  mov     [rbp+57h+var_60], eax
0x14000f73c  mov     eax, 184h
0x14000f741  jmp     short loc_14000F765
0x14000f743  test    eax, eax
0x14000f745  jle     short loc_14000F74F
0x14000f747  movzx   eax, ax
0x14000f74a  or      eax, 80070000h
0x14000f74f  mov     [rbp+57h+var_60], eax
0x14000f752  mov     eax, 19Ah
0x14000f757  jmp     short loc_14000F765
0x14000f759  mov     [rbp+57h+var_60], 80070057h
0x14000f760  mov     eax, 164h
0x14000f765  mov     [rbp+57h+var_5A], ax
0x14000f769  mov     ebx, [rbp+57h+var_60]
0x14000f76c  lea     rcx, [rbp+57h+lpNewFileName]; this
0x14000f770  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000f775  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f779  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000f77e  lea     rcx, [rbp+57h+var_60]; this
0x14000f782  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000f787  mov     eax, ebx
0x14000f789  add     rsp, 90h
0x14000f790  pop     r14
0x14000f792  pop     rdi
0x14000f793  pop     rsi
0x14000f794  pop     rbx
0x14000f795  pop     rbp
0x14000f796  retn
```
