# CRasFilePlaceholderParams::SetFileSize(ISafeSaveHandleManager *,unsigned __int64,TransactionType)

- ea: `0x180065680`
- end: `0x1800657cf`
- name: `?SetFileSize@CRasFilePlaceholderParams@@QEAAJPEAUISafeSaveHandleManager@@_KW4TransactionType@@@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18004be60`

## callees

- `0x18001c82c`
- `0x18002314c`
- `0x1800233b4`
- `0x18002ffd0`
- `0x180064f08`
- `0x180065680`
- `0x1800657d8`
- `0x18006d8cc`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180065728`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180065728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065777`

## string_xrefs

- `0x18006579d`: `onecore\shell\shcore\libs\stream\randomaccessstream.cpp`
- `0x1800656a1`: `SetFileSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRasFilePlaceholderParams::SetFileSize(
        struct CRasFilePlaceholderParams *a1,
        __int64 *a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  __int64 v8; // rax
  int v9; // eax
  int Error; // ebx
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-A9h]
  bool v15; // [rsp+40h] [rbp-89h] BYREF
  __int64 v16; // [rsp+48h] [rbp-81h] BYREF
  struct _OVERLAPPED v17; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v18[6]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v19[128]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  StreamLibTelemetry::WatchCurrentThread(v19, "SetFileSize");
  CRasFilePlaceholderParams::_GetParamsUnderLock(a1, v18, 0, 0);
  v8 = *a2;
  if ( v18[0] )
  {
    v16 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 40))(a2, a4, &v16);
    Error = v9;
    v11 = retaddr;
    if ( v9 < 0 )
    {
      v12 = 432;
LABEL_10:
      wil::details::in1diag3::_Log_Hr(
        v11,
        (void *)v12,
        (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\randomaccessstream.cpp",
        (const char *)(unsigned int)v9,
        v14);
      goto LABEL_11;
    }
    if ( a3 != v16 )
    {
      memset(&v17, 0, sizeof(v17));
      v17.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
      if ( v17.hEvent || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v15 = 0;
        Error = CRasFilePlaceholderParams::_WriteFullContentsIntoFileWithParams(
                  a1,
                  (__int64)v18,
                  (__int64)a2,
                  a3,
                  &v17,
                  &v15,
                  a4);
        CloseHandle(v17.hEvent);
      }
    }
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned __int64))(v8 + 48))(a2, a4, a3);
    Error = v9;
    v11 = retaddr;
    if ( v9 < 0 )
    {
      v12 = 448;
      goto LABEL_10;
    }
  }
LABEL_11:
  RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS((RAS_FILE_PLACEHOLDER_PARAMS *)v18);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v19);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180065680  push    rbp
0x180065682  push    rbx
0x180065683  push    rsi
0x180065684  push    rdi
0x180065685  push    r14
0x180065687  push    r15
0x180065689  lea     rbp, [rsp-2Fh]
0x18006568e  sub     rsp, 0F8h
0x180065695  mov     r14d, r9d
0x180065698  mov     rsi, r8
0x18006569b  mov     rdi, rdx
0x18006569e  mov     r15, rcx
0x1800656a1  lea     rdx, aSetfilesize; "SetFileSize"
0x1800656a8  lea     rcx, [rbp+57h+var_80]
0x1800656ac  call    ?WatchCurrentThread@StreamLibTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; StreamLibTelemetry::WatchCurrentThread(char const *)
0x1800656b1  nop
0x1800656b2  xor     r9d, r9d
0x1800656b5  xor     r8d, r8d
0x1800656b8  lea     rdx, [rbp+57h+var_B0]
0x1800656bc  mov     rcx, r15
0x1800656bf  call    ?_GetParamsUnderLock@CRasFilePlaceholderParams@@AEAA?AURAS_FILE_PLACEHOLDER_PARAMS@@PEA_K0@Z; CRasFilePlaceholderParams::_GetParamsUnderLock(unsigned __int64 *,unsigned __int64 *)
0x1800656c4  nop
0x1800656c5  mov     rax, [rdi]
0x1800656c8  mov     edx, r14d
0x1800656cb  mov     rcx, rdi
0x1800656ce  cmp     [rbp+57h+var_B0], 0
0x1800656d3  jz      loc_18006577F
0x1800656d9  mov     [rsp+120h+var_D8], 0
0x1800656e2  lea     r8, [rsp+120h+var_D8]
0x1800656e7  mov     rax, [rax+28h]
0x1800656eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656f0  mov     ebx, eax
0x1800656f2  mov     rcx, [rbp+5Fh]
0x1800656f6  test    eax, eax
0x1800656f8  jns     short loc_180065704
0x1800656fa  mov     edx, 1B0h
0x1800656ff  jmp     loc_18006579A
0x180065704  cmp     rsi, [rsp+120h+var_D8]
0x180065709  jz      loc_1800657AA
0x18006570f  xorps   xmm0, xmm0
0x180065712  movups  [rbp+57h+var_D0], xmm0
0x180065716  movups  xmmword ptr [rbp+57h+hObject], xmm0
0x18006571a  xor     edx, edx; lpName
0x18006571c  xor     ecx, ecx; lpEventAttributes
0x18006571e  mov     r9d, 1F0003h; dwDesiredAccess
0x180065724  lea     r8d, [rdx+1]; dwFlags
0x180065728  call    cs:__imp_CreateEventExW
0x18006572e  mov     [rbp+57h+hObject+8], rax
0x180065732  test    rax, rax
0x180065735  jnz     short loc_180065742
0x180065737  call    ResultFromKnownLastError
0x18006573c  mov     ebx, eax
0x18006573e  test    eax, eax
0x180065740  js      short loc_1800657AA
0x180065742  mov     [rsp+120h+var_E0], 0
0x180065747  mov     [rsp+120h+var_F0], r14d
0x18006574c  lea     rax, [rsp+120h+var_E0]
0x180065751  mov     [rsp+120h+var_F8], rax
0x180065756  lea     rax, [rbp+57h+var_D0]
0x18006575a  mov     [rsp+120h+var_100], rax
0x18006575f  mov     r9, rsi
0x180065762  mov     r8, rdi
0x180065765  lea     rdx, [rbp+57h+var_B0]
0x180065769  mov     rcx, r15
0x18006576c  call    ?_WriteFullContentsIntoFileWithParams@CRasFilePlaceholderParams@@AEAAJAEBURAS_FILE_PLACEHOLDER_PARAMS@@PEAUISafeSaveHandleManager@@_KPEAU_OVERLAPPED@@AED_NW4TransactionType@@@Z; CRasFilePlaceholderParams::_WriteFullContentsIntoFileWithParams(RAS_FILE_PLACEHOLDER_PARAMS const &,ISafeSaveHandleManager *,unsigned __int64,_OVERLAPPED *,bool const volatile &,TransactionType)
0x180065771  mov     ebx, eax
0x180065773  mov     rcx, [rbp+57h+hObject+8]; hObject
0x180065777  call    cs:__imp_CloseHandle
0x18006577d  jmp     short loc_1800657AA
0x18006577f  mov     r8, rsi
0x180065782  mov     rax, [rax+30h]
0x180065786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006578b  mov     ebx, eax
0x18006578d  mov     rcx, [rbp+5Fh]; this
0x180065791  test    eax, eax
0x180065793  jns     short loc_1800657AA
0x180065795  mov     edx, 1C0h; void *
0x18006579a  mov     r9d, eax; char *
0x18006579d  lea     r8, aOnecoreShellSh_3; "onecore\\shell\\shcore\\libs\\stream\\r"...
0x1800657a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800657a9  nop
0x1800657aa  lea     rcx, [rbp+57h+var_B0]; this
0x1800657ae  call    ??1RAS_FILE_PLACEHOLDER_PARAMS@@QEAA@XZ; RAS_FILE_PLACEHOLDER_PARAMS::~RAS_FILE_PLACEHOLDER_PARAMS(void)
0x1800657b3  nop
0x1800657b4  lea     rcx, [rbp+57h+var_80]; this
0x1800657b8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800657bd  mov     eax, ebx
0x1800657bf  add     rsp, 0F8h
0x1800657c6  pop     r15
0x1800657c8  pop     r14
0x1800657ca  pop     rdi
0x1800657cb  pop     rsi
0x1800657cc  pop     rbx
0x1800657cd  pop     rbp
0x1800657ce  retn
```
