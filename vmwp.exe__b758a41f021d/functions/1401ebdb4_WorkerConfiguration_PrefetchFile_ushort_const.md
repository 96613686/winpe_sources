# WorkerConfiguration::PrefetchFile(ushort const *)

- ea: `0x1401ebdb4`
- end: `0x1401ec121`
- name: `?PrefetchFile@WorkerConfiguration@@AEAAXPEBG@Z`
- size: `877`
- prototype: `void(WorkerConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140066190`

## callees

- `0x14004f6dc`
- `0x14007cee4`
- `0x140083990`
- `0x1400c015c`
- `0x140110924`
- `0x14011ea40`
- `0x14011ea70`
- `0x14011edb0`
- `0x14011fafc`
- `0x14011fb94`
- `0x1401ebdb4`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1401ebe6d`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1401ebe6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401ec039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401ec039`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401ebeab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401ebeab`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1401ebef7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1401ebef7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1401ec010`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1401ec010`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401ebf98`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401ec0a6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401ebf98`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401ec0a6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401ebf3d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401ebf3d`

## string_xrefs

- `0x1401ebed5`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401ebf0f`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401ebf56`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401ebfb0`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401ec04c`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401ec0be`: `onecore\vm\worker\config\workerconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WorkerConfiguration::PrefetchFile(WorkerConfiguration *this, const unsigned __int16 *a2)
{
  wil::details *v3; // rax
  const struct std::nothrow_t *v4; // rdx
  wil::details *v5; // rcx
  wil::details *v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdi
  wil::details **i; // rbx
  char *FileW; // rbx
  const char *v11; // r9
  const char *v12; // r9
  union _LARGE_INTEGER j; // rsi
  DWORD v14; // eax
  void *v15; // rdx
  const char *v16; // r9
  __int64 v17; // rdi
  const char *v18; // r9
  __int64 QuadPart; // r15
  LONGLONG v20; // rax
  void *v21; // rdx
  char v22; // al
  const char *v23; // r9
  wil::details **k; // rdi
  const char *v25; // r9
  const char *v26; // r9
  char *v27; // [rsp+40h] [rbp-168h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp-160h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-158h] BYREF
  HANDLE Handles[2]; // [rsp+58h] [rbp-150h] BYREF
  __int128 v31; // [rsp+68h] [rbp-140h]
  wil::details *v32[2]; // [rsp+80h] [rbp-128h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+90h] [rbp-118h] BYREF
  LPVOID lpBuffer[22]; // [rsp+B0h] [rbp-F8h]
  _QWORD v35[9]; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  try
  {
    `eh vector constructor iterator'(
      v32,
      0x38u,
      4u,
      WorkerConfiguration::PrefetchFile_::_3_::ReadContext::ReadContext,
      WorkerConfiguration::PrefetchFile_::_3_::ReadContext::_ReadContext);
    *(_OWORD *)Handles = 0;
    v31 = 0;
    v8 = 0;
    for ( i = v32; i != v35; i += 7 )
    {
      v3 = (wil::details *)operator new[](0x100000u);
      v5 = i[6];
      i[6] = v3;
      if ( v5 )
        operator delete(v5, v4);
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        i,
        3);
      v6 = *i;
      i[5] = *i;
      v7 = v8;
      if ( v8 >= 4 )
        std::_Xout_of_range("invalid array<T, N> subscript");
      ++v8;
      Handles[v7] = v6;
    }
    FileW = (char *)CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x40000080u, 0);
    v27 = FileW;
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA7E,
        (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
        v11);
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA81,
        (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
        v12);
    for ( j = FileSize; j.QuadPart; j.QuadPart -= QuadPart )
    {
      v14 = WaitForMultipleObjects(4u, Handles, 0, 0xFFFFFFFF);
      if ( v14 >= 4 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xA87,
          (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
          v16);
      v17 = 7LL * v14;
      if ( LOBYTE(v32[v17 + 1]) )
      {
        NumberOfBytesTransferred = 0;
        if ( !GetOverlappedResult(
                FileW,
                (struct _OVERLAPPED *)((char *)&Overlapped + v17 * 8),
                &NumberOfBytesTransferred,
                1) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xA8E,
            (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
            v18);
      }
      QuadPart = 0x100000;
      if ( j.QuadPart < 0x100000uLL )
        QuadPart = j.QuadPart;
      v20 = FileSize.QuadPart - j.QuadPart;
      *(DWORD *)((char *)&Overlapped.Offset + v17 * 8) = FileSize.LowPart - j.LowPart;
      *(_DWORD *)((char *)&Overlapped.Pointer + v17 * 8 + 4) = HIDWORD(v20);
      wil::details::ResetEvent(v32[v17], v15);
      if ( ReadFile(FileW, lpBuffer[v17], 0x100000u, 0, (struct _OVERLAPPED *)((char *)&Overlapped + v17 * 8)) )
      {
        wil::details::SetEvent(v32[v17], v21);
        v22 = 0;
      }
      else
      {
        if ( GetLastError() != 997 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xAA0,
            (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
            v23);
        v22 = 1;
      }
      LOBYTE(v32[v17 + 1]) = v22;
    }
    for ( k = v32; k != v35; k += 7 )
    {
      if ( *((_BYTE *)k + 8) )
      {
        NumberOfBytesTransferred = 0;
        if ( !GetOverlappedResult(FileW, (LPOVERLAPPED)(k + 2), &NumberOfBytesTransferred, 1) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xAAD,
            (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
            v25);
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
    `eh vector destructor iterator'(v32, 0x38u, 4u, WorkerConfiguration::PrefetchFile_::_3_::ReadContext::_ReadContext);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xAB1,
      (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
      v26);
  }
}

```

## disassembly

```asm
0x1401ebdb4  push    rbx
0x1401ebdb6  push    rsi
0x1401ebdb7  push    rdi
0x1401ebdb8  push    r13
0x1401ebdba  push    r14
0x1401ebdbc  push    r15
0x1401ebdbe  sub     rsp, 178h
0x1401ebdc5  mov     rax, cs:__security_cookie
0x1401ebdcc  xor     rax, rsp
0x1401ebdcf  mov     [rsp+1A8h+var_48], rax
0x1401ebdd7  mov     rsi, rdx
0x1401ebdda  lea     rax, _WorkerConfiguration__PrefetchFile____3___ReadContext___ReadContext
0x1401ebde1  mov     qword ptr [rsp+1A8h+dwCreationDisposition], rax; void (*)(void *)
0x1401ebde6  lea     r9, _WorkerConfiguration__PrefetchFile____3___ReadContext__ReadContext; void (*)(void *)
0x1401ebded  mov     r13d, 4
0x1401ebdf3  mov     r8d, r13d; unsigned __int64
0x1401ebdf6  lea     edx, [r13+34h]; unsigned __int64
0x1401ebdfa  lea     rcx, [rsp+1A8h+var_128]; void *
0x1401ebe02  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401ebe07  nop
0x1401ebe08  xorps   xmm0, xmm0
0x1401ebe0b  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x1401ebe10  movups  [rsp+1A8h+var_140], xmm0
0x1401ebe15  xor     edi, edi
0x1401ebe17  lea     rbx, [rsp+1A8h+var_128]
0x1401ebe1f  lea     r15, [rsp+1A8h+var_48]
0x1401ebe27  lea     r14d, [r13-1]
0x1401ebe2b  cmp     rbx, r15
0x1401ebe2e  jz      short loc_1401EBE87
0x1401ebe30  mov     ecx, 100000h; unsigned __int64
0x1401ebe35  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1401ebe3a  mov     rcx, [rbx+30h]; void *
0x1401ebe3e  mov     [rbx+30h], rax
0x1401ebe42  test    rcx, rcx
0x1401ebe45  jz      short loc_1401EBE4C
0x1401ebe47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1401ebe4c  mov     edx, r14d
0x1401ebe4f  mov     rcx, rbx
0x1401ebe52  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1401ebe57  mov     rax, [rbx]
0x1401ebe5a  mov     [rbx+28h], rax
0x1401ebe5e  mov     rcx, rdi
0x1401ebe61  cmp     rdi, r13
0x1401ebe64  jb      short loc_1401EBE79
0x1401ebe66  lea     rcx, aInvalidArrayTN; "invalid array<T, N> subscript"
0x1401ebe6d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1401ebe74  nop     dword ptr [rax+rax+00h]
0x1401ebe79  inc     rdi
0x1401ebe7c  mov     [rsp+rcx*8+1A8h+Handles], rax
0x1401ebe81  add     rbx, 38h ; '8'
0x1401ebe85  jmp     short loc_1401EBE2B
0x1401ebe87  mov     [rsp+1A8h+hTemplateFile], 0; hTemplateFile
0x1401ebe90  mov     [rsp+1A8h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1401ebe98  mov     [rsp+1A8h+dwCreationDisposition], r14d; dwCreationDisposition
0x1401ebe9d  xor     r9d, r9d; lpSecurityAttributes
0x1401ebea0  mov     r8d, r14d; dwShareMode
0x1401ebea3  mov     edx, 80000000h; dwDesiredAccess
0x1401ebea8  mov     rcx, rsi; lpFileName
0x1401ebeab  call    cs:__imp_CreateFileW
0x1401ebeb2  nop     dword ptr [rax+rax+00h]
0x1401ebeb7  mov     rbx, rax
0x1401ebeba  mov     [rsp+1A8h+var_168], rax
0x1401ebebf  dec     rax
0x1401ebec2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401ebec6  setnbe  al
0x1401ebec9  mov     rcx, [rsp+1A8h]; this
0x1401ebed1  test    al, al
0x1401ebed3  jz      short loc_1401EBEE6
0x1401ebed5  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ebedc  mov     edx, 0A7Eh; void *
0x1401ebee1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ebee6  mov     qword ptr [rsp+1A8h+FileSize], 0
0x1401ebeef  lea     rdx, [rsp+1A8h+FileSize]; lpFileSize
0x1401ebef4  mov     rcx, rbx; hFile
0x1401ebef7  call    cs:__imp_GetFileSizeEx
0x1401ebefe  nop     dword ptr [rax+rax+00h]
0x1401ebf03  mov     rcx, [rsp+1A8h]; this
0x1401ebf0b  test    eax, eax
0x1401ebf0d  jnz     short loc_1401EBF20
0x1401ebf0f  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ebf16  mov     edx, 0A81h; void *
0x1401ebf1b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ebf20  mov     rsi, qword ptr [rsp+1A8h+FileSize]
0x1401ebf25  test    rsi, rsi
0x1401ebf28  jz      loc_1401EC071
0x1401ebf2e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401ebf32  xor     r8d, r8d; bWaitAll
0x1401ebf35  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x1401ebf3a  mov     ecx, r13d; nCount
0x1401ebf3d  call    cs:__imp_WaitForMultipleObjects
0x1401ebf44  nop     dword ptr [rax+rax+00h]
0x1401ebf49  mov     rcx, [rsp+1A8h]; this
0x1401ebf51  cmp     eax, r13d
0x1401ebf54  jb      short loc_1401EBF67
0x1401ebf56  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ebf5d  mov     edx, 0A87h; void *
0x1401ebf62  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ebf67  mov     eax, eax
0x1401ebf69  imul    rdi, rax, 38h ; '8'
0x1401ebf6d  lea     r14, [rsp+rdi+1A8h+Overlapped]
0x1401ebf75  cmp     [rsp+rdi+1A8h+var_120], 0
0x1401ebf7d  jz      short loc_1401EBFC1
0x1401ebf7f  mov     [rsp+1A8h+NumberOfBytesTransferred], 0
0x1401ebf87  mov     r9d, 1; bWait
0x1401ebf8d  lea     r8, [rsp+1A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1401ebf92  mov     rdx, r14; lpOverlapped
0x1401ebf95  mov     rcx, rbx; hFile
0x1401ebf98  call    cs:__imp_GetOverlappedResult
0x1401ebf9f  nop     dword ptr [rax+rax+00h]
0x1401ebfa4  mov     rcx, [rsp+1A8h]; this
0x1401ebfac  test    eax, eax
0x1401ebfae  jnz     short loc_1401EBFC1
0x1401ebfb0  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ebfb7  mov     edx, 0A8Eh; void *
0x1401ebfbc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ebfc1  mov     eax, 100000h
0x1401ebfc6  mov     r15d, eax
0x1401ebfc9  cmp     rsi, rax
0x1401ebfcc  cmovb   r15, rsi
0x1401ebfd0  mov     rax, qword ptr [rsp+1A8h+FileSize]
0x1401ebfd5  sub     rax, rsi
0x1401ebfd8  mov     dword ptr [rsp+rdi+1A8h+Overlapped.10h], eax
0x1401ebfdf  shr     rax, 20h
0x1401ebfe3  mov     dword ptr [rsp+rdi+1A8h+Overlapped.10h+4], eax
0x1401ebfea  mov     rcx, [rsp+rdi+1A8h+var_128]; this
0x1401ebff2  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1401ebff7  mov     qword ptr [rsp+1A8h+dwCreationDisposition], r14; lpOverlapped
0x1401ebffc  xor     r9d, r9d; lpNumberOfBytesRead
0x1401ebfff  mov     r8d, 100000h; nNumberOfBytesToRead
0x1401ec005  mov     rdx, [rsp+rdi+1A8h+lpBuffer]; lpBuffer
0x1401ec00d  mov     rcx, rbx; hFile
0x1401ec010  call    cs:__imp_ReadFile
0x1401ec017  nop     dword ptr [rax+rax+00h]
0x1401ec01c  test    eax, eax
0x1401ec01e  jz      short loc_1401EC031
0x1401ec020  mov     rcx, [rsp+rdi+1A8h+var_128]; this
0x1401ec028  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1401ec02d  xor     al, al
0x1401ec02f  jmp     short loc_1401EC062
0x1401ec031  mov     r14, [rsp+1A8h]
0x1401ec039  call    cs:__imp_GetLastError
0x1401ec040  nop     dword ptr [rax+rax+00h]
0x1401ec045  cmp     eax, 3E5h
0x1401ec04a  jz      short loc_1401EC060
0x1401ec04c  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ec053  mov     edx, 0AA0h; void *
0x1401ec058  mov     rcx, r14; this
0x1401ec05b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ec060  mov     al, 1
0x1401ec062  mov     [rsp+rdi+1A8h+var_120], al
0x1401ec069  sub     rsi, r15
0x1401ec06c  jmp     loc_1401EBF25
0x1401ec071  lea     rdi, [rsp+1A8h+var_128]
0x1401ec079  lea     rsi, [rsp+1A8h+var_48]
0x1401ec081  cmp     rdi, rsi
0x1401ec084  jz      short loc_1401EC0D5
0x1401ec086  cmp     byte ptr [rdi+8], 0
0x1401ec08a  jz      short loc_1401EC0CF
0x1401ec08c  mov     [rsp+1A8h+NumberOfBytesTransferred], 0
0x1401ec094  lea     rdx, [rdi+10h]; lpOverlapped
0x1401ec098  mov     r9d, 1; bWait
0x1401ec09e  lea     r8, [rsp+1A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1401ec0a3  mov     rcx, rbx; hFile
0x1401ec0a6  call    cs:__imp_GetOverlappedResult
0x1401ec0ad  nop     dword ptr [rax+rax+00h]
0x1401ec0b2  mov     rcx, [rsp+1A8h]; this
0x1401ec0ba  test    eax, eax
0x1401ec0bc  jnz     short loc_1401EC0CF
0x1401ec0be  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401ec0c5  mov     edx, 0AADh; void *
0x1401ec0ca  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401ec0cf  add     rdi, 38h ; '8'
0x1401ec0d3  jmp     short loc_1401EC081
0x1401ec0d5  lea     rcx, [rsp+1A8h+var_168]
0x1401ec0da  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401ec0df  nop
0x1401ec0e0  lea     r9, _WorkerConfiguration__PrefetchFile____3___ReadContext___ReadContext; void (*)(void *)
0x1401ec0e7  mov     r8, r13; unsigned __int64
0x1401ec0ea  mov     edx, 38h ; '8'; unsigned __int64
0x1401ec0ef  lea     rcx, [rsp+1A8h+var_128]; void *
0x1401ec0f7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1401ec0fc  nop
0x1401ec0fd  jmp     short $+2
0x1401ec0ff  mov     rcx, [rsp+1A8h+var_48]
0x1401ec107  xor     rcx, rsp; StackCookie
0x1401ec10a  call    __security_check_cookie
0x1401ec10f  add     rsp, 178h
0x1401ec116  pop     r15
0x1401ec118  pop     r14
0x1401ec11a  pop     r13
0x1401ec11c  pop     rdi
0x1401ec11d  pop     rsi
0x1401ec11e  pop     rbx
0x1401ec11f  retn
```
