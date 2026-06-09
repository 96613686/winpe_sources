# CAppxBlockTable::InitSandbox(wchar_t const *,bool)

- ea: `0x18021c754`
- end: `0x18021ca50`
- name: `?InitSandbox@CAppxBlockTable@@QEAAJPEB_W_N@Z`
- size: `764`
- prototype: `__int64 __fastcall(CAppxBlockTable *this, const wchar_t *, char)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180205e18`
- `0x180215294`

## callees

- `0x18000c6b4`
- `0x18010fdd8`
- `0x180110914`
- `0x180113ae8`
- `0x180116648`
- `0x18012b618`
- `0x18021c754`
- `0x18021ca94`
- `0x18021cdb4`
- `0x18021ce04`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c8a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c8a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021c980`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021ca05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021ca05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021c896`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021c896`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18021c971`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18021c971`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18021c91a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18021c91a`

## string_xrefs

- `0x18021c8d3`: `InitSandbox: CreateFile failed for %ws, 0x%08lx`
- `0x18021c953`: `InitSandbox: CreateFileMapping failed for %ws, 0x%08lx`

## pseudocode

```c
__int64 __fastcall CAppxBlockTable::InitSandbox(CAppxBlockTable *this, const wchar_t *a2, char a3)
{
  signed int CombinedPath; // edi
  const wchar_t **v7; // r15
  void *v8; // rcx
  LPCWSTR *v9; // rsi
  void *v10; // rcx
  LPCWSTR *v11; // r14
  void **v12; // rbp
  HANDLE FileW; // rax
  signed int LastError; // eax
  HANDLE FileMappingW; // rax
  signed int v16; // eax
  LPVOID v17; // rax
  signed int v18; // eax
  unsigned int i; // esi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E8h]
  wchar_t v22[8]; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t v23[56]; // [rsp+50h] [rbp-B8h] BYREF

  memset(v23, 0, 98);
  CombinedPath = 0;
  wcscpy(v22, L"EXT.dat");
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 0) )
    return (unsigned int)CombinedPath;
  if ( !*((_DWORD *)this + 13) || *((_DWORD *)this + 13) > 0xFFFFFFFu )
  {
    CombinedPath = -2145116151;
    v11 = (LPCWSTR *)((char *)this + 40);
    v12 = (void **)((char *)this + 32);
    goto LABEL_37;
  }
  v7 = (const wchar_t **)((char *)this + 32);
  v8 = (void *)*((_QWORD *)this + 4);
  if ( v8 )
  {
    SusFree(v8);
    *v7 = 0;
  }
  v9 = (LPCWSTR *)((char *)this + 40);
  v10 = (void *)*((_QWORD *)this + 5);
  if ( v10 )
  {
    SusFree(v10);
    *v9 = 0;
  }
  CombinedPath = DuplicateString<wchar_t const *,wchar_t *>(a2, (char *)this + 32);
  v11 = (LPCWSTR *)((char *)this + 40);
  v12 = (void **)((char *)this + 32);
  if ( CombinedPath < 0 )
    goto LABEL_37;
  CombinedPath = HexEncode((const unsigned __int8 *)this + 8, 0x14u, v23, 0x31u);
  if ( CombinedPath < 0 )
    goto LABEL_37;
  CombinedPath = StringCchCatW(v23, 0x31u, v22);
  if ( CombinedPath < 0 )
    goto LABEL_37;
  CombinedPath = CreateCombinedPath(*v7, v23, (wchar_t **)this + 5);
  if ( CombinedPath < 0 )
    goto LABEL_37;
  FileW = CreateFileW(*v9, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
  *((_QWORD *)this + 11) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CombinedPath = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      CombinedPath = LastError;
    if ( CombinedPath >= 0 )
      CombinedPath = -2147418113;
    WUTrace(
      0,
      0,
      4096,
      1,
      0,
      L"InitSandbox: CreateFile failed for %ws, 0x%08lx",
      *v9,
      CombinedPath,
      *(_QWORD *)v22,
      *(_QWORD *)&v22[4]);
LABEL_18:
    v12 = (void **)((char *)this + 32);
LABEL_37:
    CAppxBlockTable::CloseBlockTableExtensionFile(this);
    if ( *v11 )
      DeleteFileW(*v11);
    SusFree((void *)*v11);
    *v11 = 0;
    SusFree(*v12);
    *v12 = 0;
    return (unsigned int)CombinedPath;
  }
  dwCreationDisposition = 16 * *((_DWORD *)this + 13);
  *((_DWORD *)this + 27) = 0;
  FileMappingW = CreateFileMappingW(FileW, 0, 4u, 0, dwCreationDisposition, 0);
  *((_QWORD *)this + 10) = FileMappingW;
  if ( !FileMappingW )
  {
    v16 = GetLastError();
    CombinedPath = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      CombinedPath = v16;
    if ( CombinedPath >= 0 )
      CombinedPath = -2147418113;
    WUTrace(
      0,
      0,
      4096,
      1,
      0,
      L"InitSandbox: CreateFileMapping failed for %ws, 0x%08lx",
      *v9,
      CombinedPath,
      *(_QWORD *)v22,
      *(_QWORD *)&v22[4]);
    goto LABEL_18;
  }
  v17 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
  *((_QWORD *)this + 12) = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    CombinedPath = (unsigned __int16)v18 | 0x80070000;
    if ( v18 <= 0 )
      CombinedPath = v18;
    if ( CombinedPath >= 0 )
      CombinedPath = -2147418113;
    WUTrace(
      0,
      0,
      4096,
      1,
      0,
      L"InitSandbox: MapViewOfFile failed for %ws, 0x%08lx",
      *v9,
      CombinedPath,
      *(_QWORD *)v22,
      *(_QWORD *)&v22[4]);
    goto LABEL_18;
  }
  for ( i = 0; i < *((_DWORD *)this + 13); ++i )
  {
    if ( !(unsigned int)CAppxBlockTable::GetBlockState(this, i) )
      CAppxBlockTable::SetBlockState(this, i, 1);
  }
  *((_BYTE *)this + 104) = a3;
  return (unsigned int)CombinedPath;
}

```

## disassembly

```asm
0x18021c754  mov     [rsp+arg_10], rbx
0x18021c759  push    rbp
0x18021c75a  push    rsi
0x18021c75b  push    rdi
0x18021c75c  push    r12
0x18021c75e  push    r13
0x18021c760  push    r14
0x18021c762  push    r15
0x18021c764  sub     rsp, 0D0h
0x18021c76b  mov     rax, cs:__security_cookie
0x18021c772  xor     rax, rsp
0x18021c775  mov     [rsp+108h+var_48], rax
0x18021c77d  movups  xmm0, xmmword ptr cs:aExtDat; "EXT.dat"
0x18021c784  xor     r13d, r13d
0x18021c787  mov     r12b, r8b
0x18021c78a  mov     rbp, rdx
0x18021c78d  mov     [rsp+108h+var_B8], r13w
0x18021c793  mov     rbx, rcx
0x18021c796  xor     edx, edx; Val
0x18021c798  lea     rcx, [rsp+108h+var_B6]; void *
0x18021c79d  mov     edi, r13d
0x18021c7a0  lea     r8d, [r13+60h]; Size
0x18021c7a4  movdqu  xmmword ptr [rsp+108h+var_C8], xmm0
0x18021c7aa  call    memset
0x18021c7af  xor     eax, eax
0x18021c7b1  lock cmpxchg [rbx+6Ch], r13d
0x18021c7b7  jz      loc_18021CA23
0x18021c7bd  cmp     [rbx+34h], r13d
0x18021c7c1  jz      loc_18021C9E8
0x18021c7c7  cmp     dword ptr [rbx+34h], 0FFFFFFFh
0x18021c7ce  ja      loc_18021C9E8
0x18021c7d4  lea     r15, [rbx+20h]
0x18021c7d8  mov     rcx, [r15]; lpMem
0x18021c7db  test    rcx, rcx
0x18021c7de  jz      short loc_18021C7E8
0x18021c7e0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18021c7e5  mov     [r15], r13
0x18021c7e8  lea     rsi, [rbx+28h]
0x18021c7ec  mov     rcx, [rsi]; lpMem
0x18021c7ef  test    rcx, rcx
0x18021c7f2  jz      short loc_18021C7FC
0x18021c7f4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18021c7f9  mov     [rsi], r13
0x18021c7fc  mov     rdx, r15
0x18021c7ff  mov     rcx, rbp
0x18021c802  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18021c807  mov     edi, eax
0x18021c809  mov     r14, rsi
0x18021c80c  mov     rbp, r15
0x18021c80f  test    eax, eax
0x18021c811  js      loc_18021C9F5
0x18021c817  mov     r9d, 31h ; '1'; unsigned int
0x18021c81d  lea     rcx, [rbx+8]; unsigned __int8 *
0x18021c821  lea     r8, [rsp+108h+var_B8]; wchar_t *
0x18021c826  lea     edx, [r9-1Dh]; unsigned int
0x18021c82a  call    ?HexEncode@@YAJPEBEKPEA_WK@Z; HexEncode(uchar const *,ulong,wchar_t *,ulong)
0x18021c82f  mov     edi, eax
0x18021c831  test    eax, eax
0x18021c833  js      loc_18021C9F5
0x18021c839  lea     r8, [rsp+108h+var_C8]; wchar_t *
0x18021c83e  mov     edx, 31h ; '1'; unsigned __int64
0x18021c843  lea     rcx, [rsp+108h+var_B8]; wchar_t *
0x18021c848  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18021c84d  mov     edi, eax
0x18021c84f  test    eax, eax
0x18021c851  js      loc_18021C9F5
0x18021c857  mov     rcx, [r15]; wchar_t *
0x18021c85a  lea     rdx, [rsp+108h+var_B8]; wchar_t *
0x18021c85f  mov     r8, rsi; wchar_t **
0x18021c862  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18021c867  mov     edi, eax
0x18021c869  test    eax, eax
0x18021c86b  js      loc_18021C9F5
0x18021c871  mov     rcx, [rsi]; lpFileName
0x18021c874  mov     ebp, 4
0x18021c879  mov     [rsp+108h+hTemplateFile], r13; hTemplateFile
0x18021c87e  xor     r9d, r9d; lpSecurityAttributes
0x18021c881  mov     [rsp+108h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18021c889  mov     edx, 0C0000000h; dwDesiredAccess
0x18021c88e  mov     [rsp+108h+dwCreationDisposition], ebp; dwCreationDisposition
0x18021c892  lea     r8d, [rbp-1]; dwShareMode
0x18021c896  call    cs:__imp_CreateFileW
0x18021c89c  mov     [rbx+58h], rax
0x18021c8a0  mov     rcx, rax; hFile
0x18021c8a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18021c8a7  jnz     short loc_18021C8FF
0x18021c8a9  call    cs:__imp_GetLastError
0x18021c8af  movzx   edi, ax
0x18021c8b2  or      edi, 80070000h
0x18021c8b8  test    eax, eax
0x18021c8ba  cmovle  edi, eax
0x18021c8bd  mov     eax, 8000FFFFh
0x18021c8c2  test    edi, edi
0x18021c8c4  cmovns  edi, eax
0x18021c8c7  mov     rax, [rsi]
0x18021c8ca  mov     [rsp+108h+var_D0], edi
0x18021c8ce  mov     [rsp+108h+hTemplateFile], rax
0x18021c8d3  lea     rax, aInitsandboxCre; "InitSandbox: CreateFile failed for %ws,"...
0x18021c8da  xor     edx, edx
0x18021c8dc  mov     qword ptr [rsp+108h+dwFlagsAndAttributes], rax
0x18021c8e1  xor     ecx, ecx
0x18021c8e3  mov     qword ptr [rsp+108h+dwCreationDisposition], r13
0x18021c8e8  mov     r8d, 1000h
0x18021c8ee  lea     r9d, [rdx+1]
0x18021c8f2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18021c8f7  mov     rbp, r15
0x18021c8fa  jmp     loc_18021C9F5
0x18021c8ff  mov     eax, [rbx+34h]
0x18021c902  xor     r9d, r9d; dwMaximumSizeHigh
0x18021c905  shl     eax, 4
0x18021c908  mov     r8d, ebp; flProtect
0x18021c90b  mov     qword ptr [rsp+108h+dwFlagsAndAttributes], r13; lpName
0x18021c910  xor     edx, edx; lpFileMappingAttributes
0x18021c912  mov     [rsp+108h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18021c916  mov     [rbx+6Ch], r13d
0x18021c91a  call    cs:__imp_CreateFileMappingW
0x18021c920  mov     [rbx+50h], rax
0x18021c924  test    rax, rax
0x18021c927  jnz     short loc_18021C95F
0x18021c929  call    cs:__imp_GetLastError
0x18021c92f  movzx   edi, ax
0x18021c932  or      edi, 80070000h
0x18021c938  test    eax, eax
0x18021c93a  cmovle  edi, eax
0x18021c93d  mov     eax, 8000FFFFh
0x18021c942  test    edi, edi
0x18021c944  cmovns  edi, eax
0x18021c947  mov     rax, [rsi]
0x18021c94a  mov     [rsp+108h+var_D0], edi
0x18021c94e  mov     [rsp+108h+hTemplateFile], rax
0x18021c953  lea     rax, aInitsandboxCre_0; "InitSandbox: CreateFileMapping failed f"...
0x18021c95a  jmp     loc_18021C8DA
0x18021c95f  xor     r9d, r9d; dwFileOffsetLow
0x18021c962  mov     qword ptr [rsp+108h+dwCreationDisposition], r13; dwNumberOfBytesToMap
0x18021c967  xor     r8d, r8d; dwFileOffsetHigh
0x18021c96a  mov     rcx, rax; hFileMappingObject
0x18021c96d  lea     edx, [r9+2]; dwDesiredAccess
0x18021c971  call    cs:__imp_MapViewOfFile
0x18021c977  mov     [rbx+60h], rax
0x18021c97b  test    rax, rax
0x18021c97e  jnz     short loc_18021C9B6
0x18021c980  call    cs:__imp_GetLastError
0x18021c986  movzx   edi, ax
0x18021c989  or      edi, 80070000h
0x18021c98f  test    eax, eax
0x18021c991  cmovle  edi, eax
0x18021c994  mov     eax, 8000FFFFh
0x18021c999  test    edi, edi
0x18021c99b  cmovns  edi, eax
0x18021c99e  mov     rax, [rsi]
0x18021c9a1  mov     [rsp+108h+var_D0], edi
0x18021c9a5  mov     [rsp+108h+hTemplateFile], rax
0x18021c9aa  lea     rax, aInitsandboxMap; "InitSandbox: MapViewOfFile failed for %"...
0x18021c9b1  jmp     loc_18021C8DA
0x18021c9b6  mov     esi, r13d
0x18021c9b9  cmp     [rbx+34h], r13d
0x18021c9bd  jbe     short loc_18021C9E2
0x18021c9bf  mov     edx, esi
0x18021c9c1  mov     rcx, rbx
0x18021c9c4  call    ?GetBlockState@CAppxBlockTable@@QEBA?AW4BlockState@@K@Z; CAppxBlockTable::GetBlockState(ulong)
0x18021c9c9  test    eax, eax
0x18021c9cb  jnz     short loc_18021C9DB
0x18021c9cd  lea     r8d, [rax+1]
0x18021c9d1  mov     edx, esi
0x18021c9d3  mov     rcx, rbx
0x18021c9d6  call    ?SetBlockState@CAppxBlockTable@@QEAAJKW4BlockState@@@Z; CAppxBlockTable::SetBlockState(ulong,BlockState)
0x18021c9db  inc     esi
0x18021c9dd  cmp     esi, [rbx+34h]
0x18021c9e0  jb      short loc_18021C9BF
0x18021c9e2  mov     [rbx+68h], r12b
0x18021c9e6  jmp     short loc_18021CA23
0x18021c9e8  mov     edi, 80242009h
0x18021c9ed  lea     r14, [rbx+28h]
0x18021c9f1  lea     rbp, [rbx+20h]
0x18021c9f5  mov     rcx, rbx; this
0x18021c9f8  call    ?CloseBlockTableExtensionFile@CAppxBlockTable@@AEAAXXZ; CAppxBlockTable::CloseBlockTableExtensionFile(void)
0x18021c9fd  mov     rcx, [r14]; lpFileName
0x18021ca00  test    rcx, rcx
0x18021ca03  jz      short loc_18021CA0B
0x18021ca05  call    cs:__imp_DeleteFileW
0x18021ca0b  mov     rcx, [r14]; lpMem
0x18021ca0e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18021ca13  mov     [r14], r13
0x18021ca16  mov     rcx, [rbp+0]; lpMem
0x18021ca1a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18021ca1f  mov     [rbp+0], r13
0x18021ca23  mov     eax, edi
0x18021ca25  mov     rcx, [rsp+108h+var_48]
0x18021ca2d  xor     rcx, rsp; StackCookie
0x18021ca30  call    __security_check_cookie
0x18021ca35  mov     rbx, [rsp+108h+arg_10]
0x18021ca3d  add     rsp, 0D0h
0x18021ca44  pop     r15
0x18021ca46  pop     r14
0x18021ca48  pop     r13
0x18021ca4a  pop     r12
0x18021ca4c  pop     rdi
0x18021ca4d  pop     rsi
0x18021ca4e  pop     rbp
0x18021ca4f  retn
```
