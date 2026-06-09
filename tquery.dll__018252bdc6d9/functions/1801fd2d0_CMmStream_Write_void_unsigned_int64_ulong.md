# CMmStream::Write(void *,unsigned __int64,ulong)

- ea: `0x1801fd2d0`
- end: `0x1801fd4ba`
- name: `?Write@CMmStream@@UEAAXPEAX_KK@Z`
- size: `490`
- prototype: `void(CMmStream *__hidden this, void *, unsigned __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180038f08`
- `0x180072768`
- `0x180073748`
- `0x180074fac`
- `0x180096528`
- `0x180147154`
- `0x18015aa68`
- `0x18019c5f0`
- `0x1801fd2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fd417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fd482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fd417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fd482`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801fd40d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801fd40d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801fd474`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801fd474`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801fd436`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801fd436`

## string_xrefs

- `0x1801fd380`: `[Index] CMmStream::Write -- Not enogh disk space, need %I64d have %I64d\n`
- `0x1801fd31d`: `[Index] WriteFile %#x, from %#p, offset %#I64x cb, %d\n`
- `0x1801fd2f2`: `[Index] Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMmStream::Write(CMmStream *this, struct _SECURITY_ATTRIBUTES *a2, char *a3, const wchar_t *a4)
{
  __int64 v4; // r15
  const wchar_t *v8; // r9
  const wchar_t *v9; // rbx
  unsigned int v10; // ebx
  const char *v11; // r9
  const char *v12; // r9
  DWORD FileSize; // eax
  const char *v14; // r9
  int lpOverlapped; // [rsp+20h] [rbp-50h]
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v20; // [rsp+B0h] [rbp+40h]
  void *v21; // [rsp+C0h] [rbp+50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+C8h] [rbp+58h] BYREF

  v21 = a3;
  v4 = (unsigned int)a4;
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
    (const wchar_t *)0x4BF,
    (unsigned int)L"[Index] Write",
    a4);
  SearchIndexerDebug::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
    (const wchar_t *)0x4C2,
    (unsigned int)L"[Index] WriteFile %#x, from %#p, offset %#I64x cb, %d\n",
    *((const wchar_t **)this + 2));
  *((_DWORD *)this + 12) = 0;
  v20 = *((_QWORD *)this + 4);
  if ( (__int64)&a3[v4] > v20 )
  {
    v16 = 0;
    CDriveInfo::GetDiskSpace(*((CDriveInfo **)this + 8), &v17, &v16);
    v9 = (const wchar_t *)&a3[v4 - v20];
    if ( (__int64)v9 > v16 )
    {
      lpOverlapped = v16;
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
        (const wchar_t *)0x4D7,
        (unsigned int)L"[Index] CMmStream::Write -- Not enogh disk space, need %I64d have %I64d\n",
        v9);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D9,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
        (const char *)0x80041828LL,
        lpOverlapped);
    }
  }
  v10 = HIDWORD(v21);
  NumberOfBytesWritten = 0;
  v21 = 0;
  CEventSem::InternalCreate((CEventSem *)&v21, 1u, 0, v8, a2);
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  Overlapped.Pointer = (PVOID)__PAIR64__(v10, (unsigned int)a3);
  Overlapped.hEvent = v21;
  if ( !WriteFile(*((HANDLE *)this + 2), a2, v4, &NumberOfBytesWritten, &Overlapped) )
  {
    if ( GetLastError() != 997 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4FA,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
        v11);
    if ( !GetOverlappedResult(*((HANDLE *)this + 2), &Overlapped, &NumberOfBytesWritten, 1) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4F6,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
        v12);
  }
  FileSize = GetFileSize(*((HANDLE *)this + 2), (LPDWORD)this + 9);
  *((_DWORD *)this + 8) = FileSize;
  if ( FileSize == -1 && GetLastError() )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x501,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
      v14);
  SNullHandle::~SNullHandle((SNullHandle *)&v21);
}

```

## disassembly

```asm
0x1801fd2d0  mov     [rsp-38h+arg_10], r8
0x1801fd2d5  push    rbp
0x1801fd2d6  push    rbx
0x1801fd2d7  push    rsi
0x1801fd2d8  push    rdi
0x1801fd2d9  push    r12
0x1801fd2db  push    r14
0x1801fd2dd  push    r15
0x1801fd2df  mov     rbp, rsp
0x1801fd2e2  sub     rsp, 70h
0x1801fd2e6  mov     r15d, r9d
0x1801fd2e9  mov     r14, r8
0x1801fd2ec  mov     r12, rdx
0x1801fd2ef  mov     rdi, rcx
0x1801fd2f2  lea     r8, aIndexWrite; "[Index] Write"
0x1801fd2f9  mov     edx, 4BFh; wchar_t *
0x1801fd2fe  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd305  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1801fd30a  mov     [rsp+70h+var_40], r15d
0x1801fd30f  mov     [rsp+70h+var_48], r14
0x1801fd314  mov     [rsp+70h+lpOverlapped], r12; struct _SECURITY_ATTRIBUTES *
0x1801fd319  mov     r9, [rdi+10h]; wchar_t *
0x1801fd31d  lea     r8, aIndexWritefile; "[Index] WriteFile %#x, from %#p, offset"...
0x1801fd324  mov     edx, 4C2h; wchar_t *
0x1801fd329  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd330  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x1801fd335  mov     dword ptr [rdi+30h], 0
0x1801fd33c  lea     rbx, [r14+r15]
0x1801fd340  mov     eax, [rdi+20h]
0x1801fd343  mov     dword ptr [rbp+arg_0], eax
0x1801fd346  mov     eax, [rdi+24h]
0x1801fd349  mov     dword ptr [rbp+arg_0+4], eax
0x1801fd34c  cmp     rbx, [rbp+arg_0]
0x1801fd350  jle     short loc_1801FD3B4
0x1801fd352  mov     [rbp+var_30], 0
0x1801fd35a  lea     r8, [rbp+var_30]; __int64 *
0x1801fd35e  lea     rdx, [rbp+var_28]; __int64 *
0x1801fd362  mov     rcx, [rdi+40h]; this
0x1801fd366  call    ?GetDiskSpace@CDriveInfo@@QEAAXAEA_J0@Z; CDriveInfo::GetDiskSpace(__int64 &,__int64 &)
0x1801fd36b  sub     rbx, [rbp+arg_0]
0x1801fd36f  mov     rax, [rbp+var_30]
0x1801fd373  cmp     rbx, rax
0x1801fd376  jle     short loc_1801FD3B4
0x1801fd378  mov     [rsp+70h+lpOverlapped], rax; int
0x1801fd37d  mov     r9, rbx; wchar_t *
0x1801fd380  lea     r8, aIndexCmmstream_3; "[Index] CMmStream::Write -- Not enogh d"...
0x1801fd387  mov     edx, 4D7h; wchar_t *
0x1801fd38c  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd393  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1801fd398  mov     rcx, [rbp+38h]; this
0x1801fd39c  mov     r9d, 80041828h; char *
0x1801fd3a2  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd3a9  mov     edx, 4D9h; void *
0x1801fd3ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801fd3b4  mov     ebx, dword ptr [rbp+arg_10+4]
0x1801fd3b7  mov     [rbp+NumberOfBytesWritten], 0
0x1801fd3be  mov     [rbp+arg_10], 0
0x1801fd3c6  xor     r8d, r8d; unsigned int
0x1801fd3c9  lea     edx, [r8+1]; unsigned int
0x1801fd3cd  lea     rcx, [rbp+arg_10]; this
0x1801fd3d1  call    ?InternalCreate@CEventSem@@IEAAXKKPEB_WQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::InternalCreate(ulong,ulong,wchar_t const *,_SECURITY_ATTRIBUTES * const)
0x1801fd3d6  nop
0x1801fd3d7  mov     [rbp+Overlapped.Internal], 0
0x1801fd3df  mov     [rbp+Overlapped.InternalHigh], 0
0x1801fd3e7  mov     dword ptr [rbp+Overlapped.10h], r14d
0x1801fd3eb  mov     dword ptr [rbp+Overlapped.10h+4], ebx
0x1801fd3ee  mov     rax, [rbp+arg_10]
0x1801fd3f2  mov     [rbp+Overlapped.hEvent], rax
0x1801fd3f6  lea     rax, [rbp+Overlapped]
0x1801fd3fa  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x1801fd3ff  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801fd403  mov     r8d, r15d; nNumberOfBytesToWrite
0x1801fd406  mov     rdx, r12; lpBuffer
0x1801fd409  mov     rcx, [rdi+10h]; hFile
0x1801fd40d  call    cs:__imp_WriteFile
0x1801fd413  test    eax, eax
0x1801fd415  jnz     short loc_1801FD46C
0x1801fd417  call    cs:__imp_GetLastError
0x1801fd41d  cmp     eax, 3E5h
0x1801fd422  jnz     short loc_1801FD456
0x1801fd424  mov     r9d, 1; bWait
0x1801fd42a  lea     r8, [rbp+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x1801fd42e  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801fd432  mov     rcx, [rdi+10h]; hFile
0x1801fd436  call    cs:__imp_GetOverlappedResult
0x1801fd43c  test    eax, eax
0x1801fd43e  jnz     short loc_1801FD46C
0x1801fd440  mov     rcx, [rbp+38h]; this
0x1801fd444  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd44b  mov     edx, 4F6h; void *
0x1801fd450  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fd456  mov     rcx, [rbp+38h]; this
0x1801fd45a  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd461  mov     edx, 4FAh; void *
0x1801fd466  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fd46c  lea     rdx, [rdi+24h]; lpFileSizeHigh
0x1801fd470  mov     rcx, [rdi+10h]; hFile
0x1801fd474  call    cs:__imp_GetFileSize
0x1801fd47a  mov     [rdi+20h], eax
0x1801fd47d  cmp     eax, 0FFFFFFFFh
0x1801fd480  jnz     short loc_1801FD4A2
0x1801fd482  call    cs:__imp_GetLastError
0x1801fd488  test    eax, eax
0x1801fd48a  jz      short loc_1801FD4A2
0x1801fd48c  mov     rcx, [rbp+38h]; this
0x1801fd490  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fd497  mov     edx, 501h; void *
0x1801fd49c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fd4a2  lea     rcx, [rbp+arg_10]; this
0x1801fd4a6  call    ??1SNullHandle@@QEAA@XZ; SNullHandle::~SNullHandle(void)
0x1801fd4ab  add     rsp, 70h
0x1801fd4af  pop     r15
0x1801fd4b1  pop     r14
0x1801fd4b3  pop     r12
0x1801fd4b5  pop     rdi
0x1801fd4b6  pop     rsi
0x1801fd4b7  pop     rbx
0x1801fd4b8  pop     rbp
0x1801fd4b9  retn
```
