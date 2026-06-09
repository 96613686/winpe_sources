# CMmStream::Read(void *,unsigned __int64,ulong,ulong &)

- ea: `0x1801fcc10`
- end: `0x1801fcdb5`
- name: `?Read@CMmStream@@UEAAXPEAX_KKAEAK@Z`
- size: `421`
- prototype: `void(CMmStream *__hidden this, void *, unsigned __int64, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180072768`
- `0x180073748`
- `0x180074fac`
- `0x180096528`
- `0x180147154`
- `0x1801fcc10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fcc95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fcd43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fcc95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fcd43`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801fcd39`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801fcd39`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801fcc86`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801fcc86`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801fcd62`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801fcd62`

## string_xrefs

- `0x1801fcc5e`: `[Index] ReadFile %#x, into %#p, offset %#I64x cb, %d\n`
- `0x1801fcc34`: `[Index] Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMmStream::Read(
        CMmStream *this,
        struct _SECURITY_ATTRIBUTES *a2,
        __int64 a3,
        const wchar_t *a4,
        unsigned int *a5)
{
  __int64 v5; // rdi
  DWORD FileSize; // eax
  const char *v10; // r9
  int v11; // ecx
  unsigned int v12; // ebx
  const char *v13; // r9
  const char *v14; // r9
  void *v15; // [rsp+40h] [rbp-30h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 NumberOfBytesRead; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v19; // [rsp+B0h] [rbp+40h]

  v19 = a3;
  v5 = (unsigned int)a4;
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
    (const wchar_t *)0x44C,
    (unsigned int)L"[Index] Read",
    a4);
  SearchIndexerDebug::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
    (const wchar_t *)0x44F,
    (unsigned int)L"[Index] ReadFile %#x, into %#p, offset %#I64x cb, %d\n",
    *((const wchar_t **)this + 2));
  *((_DWORD *)this + 12) = 0;
  FileSize = GetFileSize(*((HANDLE *)this + 2), (LPDWORD)this + 9);
  *((_DWORD *)this + 8) = FileSize;
  if ( FileSize == -1 && GetLastError() )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x46B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
      v10);
  *a5 = v5;
  v11 = *((_DWORD *)this + 8);
  NumberOfBytesRead = *((_QWORD *)this + 4);
  if ( NumberOfBytesRead > a3 )
  {
    if ( NumberOfBytesRead < a3 + v5 )
      LODWORD(v5) = v11 - a3;
    v12 = HIDWORD(v19);
    LODWORD(NumberOfBytesRead) = 0;
    v15 = 0;
    CEventSem::InternalCreate((CEventSem *)&v15, 1u, 0, (const wchar_t *)v10, a2);
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.Pointer = (PVOID)__PAIR64__(v12, a3);
    Overlapped.hEvent = v15;
    if ( !ReadFile(*((HANDLE *)this + 2), a2, v5, (LPDWORD)&NumberOfBytesRead, &Overlapped) )
    {
      if ( GetLastError() != 997 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x4A3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
          v13);
      if ( !GetOverlappedResult(*((HANDLE *)this + 2), &Overlapped, (LPDWORD)&NumberOfBytesRead, 1) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x49F,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\mmstrm.cxx",
          v14);
    }
    SNullHandle::~SNullHandle((SNullHandle *)&v15);
  }
}

```

## disassembly

```asm
0x1801fcc10  mov     [rsp-28h+arg_8], rbx
0x1801fcc15  mov     [rsp-28h+arg_10], r8
0x1801fcc1a  push    rbp
0x1801fcc1b  push    rsi
0x1801fcc1c  push    rdi
0x1801fcc1d  push    r14
0x1801fcc1f  push    r15
0x1801fcc21  mov     rbp, rsp
0x1801fcc24  sub     rsp, 70h
0x1801fcc28  mov     edi, r9d
0x1801fcc2b  mov     rsi, r8
0x1801fcc2e  mov     r15, rdx
0x1801fcc31  mov     r14, rcx
0x1801fcc34  lea     r8, aIndexRead; "[Index] Read"
0x1801fcc3b  mov     edx, 44Ch; wchar_t *
0x1801fcc40  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fcc47  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1801fcc4c  mov     [rsp+70h+var_40], edi
0x1801fcc50  mov     [rsp+70h+var_48], rsi
0x1801fcc55  mov     [rsp+70h+lpOverlapped], r15; struct _SECURITY_ATTRIBUTES *
0x1801fcc5a  mov     r9, [r14+10h]; wchar_t *
0x1801fcc5e  lea     r8, aIndexReadfileX; "[Index] ReadFile %#x, into %#p, offset "...
0x1801fcc65  mov     edx, 44Fh; wchar_t *
0x1801fcc6a  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fcc71  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x1801fcc76  mov     dword ptr [r14+30h], 0
0x1801fcc7e  lea     rdx, [r14+24h]; lpFileSizeHigh
0x1801fcc82  mov     rcx, [r14+10h]; hFile
0x1801fcc86  call    cs:__imp_GetFileSize
0x1801fcc8c  mov     [r14+20h], eax
0x1801fcc90  cmp     eax, 0FFFFFFFFh
0x1801fcc93  jnz     short loc_1801FCCB5
0x1801fcc95  call    cs:__imp_GetLastError
0x1801fcc9b  test    eax, eax
0x1801fcc9d  jz      short loc_1801FCCB5
0x1801fcc9f  mov     rcx, [rbp+28h]; this
0x1801fcca3  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fccaa  mov     edx, 46Bh; void *
0x1801fccaf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fccb5  mov     rax, [rbp+arg_20]
0x1801fccb9  mov     [rax], edi
0x1801fccbb  mov     ecx, [r14+20h]
0x1801fccbf  mov     dword ptr [rbp+NumberOfBytesRead], ecx
0x1801fccc2  mov     eax, [r14+24h]
0x1801fccc6  mov     dword ptr [rbp+NumberOfBytesRead+4], eax
0x1801fccc9  cmp     [rbp+NumberOfBytesRead], rsi
0x1801fcccd  jle     loc_1801FCDA1
0x1801fccd3  lea     rax, [rsi+rdi]
0x1801fccd7  cmp     [rbp+NumberOfBytesRead], rax
0x1801fccdb  jge     short loc_1801FCCE1
0x1801fccdd  mov     edi, ecx
0x1801fccdf  sub     edi, esi
0x1801fcce1  mov     ebx, dword ptr [rbp+arg_10+4]
0x1801fcce4  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x1801fcceb  mov     [rbp+var_30], 0
0x1801fccf3  xor     r8d, r8d; unsigned int
0x1801fccf6  lea     edx, [r8+1]; unsigned int
0x1801fccfa  lea     rcx, [rbp+var_30]; this
0x1801fccfe  call    ?InternalCreate@CEventSem@@IEAAXKKPEB_WQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::InternalCreate(ulong,ulong,wchar_t const *,_SECURITY_ATTRIBUTES * const)
0x1801fcd03  nop
0x1801fcd04  mov     [rbp+Overlapped.Internal], 0
0x1801fcd0c  mov     [rbp+Overlapped.InternalHigh], 0
0x1801fcd14  mov     dword ptr [rbp+Overlapped.10h], esi
0x1801fcd17  mov     dword ptr [rbp+Overlapped.10h+4], ebx
0x1801fcd1a  mov     rax, [rbp+var_30]
0x1801fcd1e  mov     [rbp+Overlapped.hEvent], rax
0x1801fcd22  lea     rax, [rbp+Overlapped]
0x1801fcd26  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x1801fcd2b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801fcd2f  mov     r8d, edi; nNumberOfBytesToRead
0x1801fcd32  mov     rdx, r15; lpBuffer
0x1801fcd35  mov     rcx, [r14+10h]; hFile
0x1801fcd39  call    cs:__imp_ReadFile
0x1801fcd3f  test    eax, eax
0x1801fcd41  jnz     short loc_1801FCD98
0x1801fcd43  call    cs:__imp_GetLastError
0x1801fcd49  cmp     eax, 3E5h
0x1801fcd4e  jnz     short loc_1801FCD82
0x1801fcd50  mov     r9d, 1; bWait
0x1801fcd56  lea     r8, [rbp+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x1801fcd5a  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1801fcd5e  mov     rcx, [r14+10h]; hFile
0x1801fcd62  call    cs:__imp_GetOverlappedResult
0x1801fcd68  test    eax, eax
0x1801fcd6a  jnz     short loc_1801FCD98
0x1801fcd6c  mov     rcx, [rbp+28h]; this
0x1801fcd70  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fcd77  mov     edx, 49Fh; void *
0x1801fcd7c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fcd82  mov     rcx, [rbp+28h]; this
0x1801fcd86  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801fcd8d  mov     edx, 4A3h; void *
0x1801fcd92  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801fcd98  lea     rcx, [rbp+var_30]; this
0x1801fcd9c  call    ??1SNullHandle@@QEAA@XZ; SNullHandle::~SNullHandle(void)
0x1801fcda1  mov     rbx, [rsp+70h+arg_8]
0x1801fcda9  add     rsp, 70h
0x1801fcdad  pop     r15
0x1801fcdaf  pop     r14
0x1801fcdb1  pop     rdi
0x1801fcdb2  pop     rsi
0x1801fcdb3  pop     rbp
0x1801fcdb4  retn
```
