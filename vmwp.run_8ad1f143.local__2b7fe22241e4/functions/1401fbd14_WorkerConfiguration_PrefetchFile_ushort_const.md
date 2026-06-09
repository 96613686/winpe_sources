# WorkerConfiguration::PrefetchFile(ushort const *)

- ea: `0x1401fbd14`
- end: `0x1401fc081`
- name: `?PrefetchFile@WorkerConfiguration@@AEAAXPEBG@Z`
- size: `877`
- prototype: `void(WorkerConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400c4cd8`

## callees

- `0x14005145c`
- `0x14005b648`
- `0x1400d2d9c`
- `0x1401202b4`
- `0x14012bec0`
- `0x140132960`
- `0x140132990`
- `0x140132cd0`
- `0x140133a1c`
- `0x140133ab4`
- `0x1401fbd14`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1401fbdcd`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1401fbdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401fbf99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401fbf99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401fbe0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1401fbe0b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1401fbe57`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1401fbe57`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1401fbf70`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1401fbf70`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401fbef8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401fc006`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401fbef8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1401fc006`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401fbe9d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401fbe9d`

## string_xrefs

- `0x1401fbe35`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401fbe6f`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401fbeb6`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401fbf10`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401fbfac`: `onecore\vm\worker\config\workerconfiguration.cpp`
- `0x1401fc01e`: `onecore\vm\worker\config\workerconfiguration.cpp`

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
        (void *)0xA5F,
        (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
        v11);
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA62,
        (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
        v12);
    for ( j = FileSize; j.QuadPart; j.QuadPart -= QuadPart )
    {
      v14 = WaitForMultipleObjects(4u, Handles, 0, 0xFFFFFFFF);
      if ( v14 >= 4 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xA68,
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
            (void *)0xA6F,
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
            (void *)0xA81,
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
            (void *)0xA8E,
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
      (void *)0xA92,
      (unsigned int)"onecore\\vm\\worker\\config\\workerconfiguration.cpp",
      v26);
  }
}

```

## disassembly

```asm
0x1401fbd14  push    rbx
0x1401fbd16  push    rsi
0x1401fbd17  push    rdi
0x1401fbd18  push    r13
0x1401fbd1a  push    r14
0x1401fbd1c  push    r15
0x1401fbd1e  sub     rsp, 178h
0x1401fbd25  mov     rax, cs:__security_cookie
0x1401fbd2c  xor     rax, rsp
0x1401fbd2f  mov     [rsp+1A8h+var_48], rax
0x1401fbd37  mov     rsi, rdx
0x1401fbd3a  lea     rax, _WorkerConfiguration__PrefetchFile____3___ReadContext___ReadContext
0x1401fbd41  mov     qword ptr [rsp+1A8h+dwCreationDisposition], rax; void (*)(void *)
0x1401fbd46  lea     r9, _WorkerConfiguration__PrefetchFile____3___ReadContext__ReadContext; void (*)(void *)
0x1401fbd4d  mov     r13d, 4
0x1401fbd53  mov     r8d, r13d; unsigned __int64
0x1401fbd56  lea     edx, [r13+34h]; unsigned __int64
0x1401fbd5a  lea     rcx, [rsp+1A8h+var_128]; void *
0x1401fbd62  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401fbd67  nop
0x1401fbd68  xorps   xmm0, xmm0
0x1401fbd6b  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x1401fbd70  movups  [rsp+1A8h+var_140], xmm0
0x1401fbd75  xor     edi, edi
0x1401fbd77  lea     rbx, [rsp+1A8h+var_128]
0x1401fbd7f  lea     r15, [rsp+1A8h+var_48]
0x1401fbd87  lea     r14d, [r13-1]
0x1401fbd8b  cmp     rbx, r15
0x1401fbd8e  jz      short loc_1401FBDE7
0x1401fbd90  mov     ecx, 100000h; unsigned __int64
0x1401fbd95  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1401fbd9a  mov     rcx, [rbx+30h]; void *
0x1401fbd9e  mov     [rbx+30h], rax
0x1401fbda2  test    rcx, rcx
0x1401fbda5  jz      short loc_1401FBDAC
0x1401fbda7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1401fbdac  mov     edx, r14d
0x1401fbdaf  mov     rcx, rbx
0x1401fbdb2  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1401fbdb7  mov     rax, [rbx]
0x1401fbdba  mov     [rbx+28h], rax
0x1401fbdbe  mov     rcx, rdi
0x1401fbdc1  cmp     rdi, r13
0x1401fbdc4  jb      short loc_1401FBDD9
0x1401fbdc6  lea     rcx, aInvalidArrayTN; "invalid array<T, N> subscript"
0x1401fbdcd  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1401fbdd4  nop     dword ptr [rax+rax+00h]
0x1401fbdd9  inc     rdi
0x1401fbddc  mov     [rsp+rcx*8+1A8h+Handles], rax
0x1401fbde1  add     rbx, 38h ; '8'
0x1401fbde5  jmp     short loc_1401FBD8B
0x1401fbde7  mov     [rsp+1A8h+hTemplateFile], 0; hTemplateFile
0x1401fbdf0  mov     [rsp+1A8h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1401fbdf8  mov     [rsp+1A8h+dwCreationDisposition], r14d; dwCreationDisposition
0x1401fbdfd  xor     r9d, r9d; lpSecurityAttributes
0x1401fbe00  mov     r8d, r14d; dwShareMode
0x1401fbe03  mov     edx, 80000000h; dwDesiredAccess
0x1401fbe08  mov     rcx, rsi; lpFileName
0x1401fbe0b  call    cs:__imp_CreateFileW
0x1401fbe12  nop     dword ptr [rax+rax+00h]
0x1401fbe17  mov     rbx, rax
0x1401fbe1a  mov     [rsp+1A8h+var_168], rax
0x1401fbe1f  dec     rax
0x1401fbe22  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401fbe26  setnbe  al
0x1401fbe29  mov     rcx, [rsp+1A8h]; this
0x1401fbe31  test    al, al
0x1401fbe33  jz      short loc_1401FBE46
0x1401fbe35  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fbe3c  mov     edx, 0A5Fh; void *
0x1401fbe41  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fbe46  mov     qword ptr [rsp+1A8h+FileSize], 0
0x1401fbe4f  lea     rdx, [rsp+1A8h+FileSize]; lpFileSize
0x1401fbe54  mov     rcx, rbx; hFile
0x1401fbe57  call    cs:__imp_GetFileSizeEx
0x1401fbe5e  nop     dword ptr [rax+rax+00h]
0x1401fbe63  mov     rcx, [rsp+1A8h]; this
0x1401fbe6b  test    eax, eax
0x1401fbe6d  jnz     short loc_1401FBE80
0x1401fbe6f  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fbe76  mov     edx, 0A62h; void *
0x1401fbe7b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fbe80  mov     rsi, qword ptr [rsp+1A8h+FileSize]
0x1401fbe85  test    rsi, rsi
0x1401fbe88  jz      loc_1401FBFD1
0x1401fbe8e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401fbe92  xor     r8d, r8d; bWaitAll
0x1401fbe95  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x1401fbe9a  mov     ecx, r13d; nCount
0x1401fbe9d  call    cs:__imp_WaitForMultipleObjects
0x1401fbea4  nop     dword ptr [rax+rax+00h]
0x1401fbea9  mov     rcx, [rsp+1A8h]; this
0x1401fbeb1  cmp     eax, r13d
0x1401fbeb4  jb      short loc_1401FBEC7
0x1401fbeb6  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fbebd  mov     edx, 0A68h; void *
0x1401fbec2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fbec7  mov     eax, eax
0x1401fbec9  imul    rdi, rax, 38h ; '8'
0x1401fbecd  lea     r14, [rsp+rdi+1A8h+Overlapped]
0x1401fbed5  cmp     [rsp+rdi+1A8h+var_120], 0
0x1401fbedd  jz      short loc_1401FBF21
0x1401fbedf  mov     [rsp+1A8h+NumberOfBytesTransferred], 0
0x1401fbee7  mov     r9d, 1; bWait
0x1401fbeed  lea     r8, [rsp+1A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1401fbef2  mov     rdx, r14; lpOverlapped
0x1401fbef5  mov     rcx, rbx; hFile
0x1401fbef8  call    cs:__imp_GetOverlappedResult
0x1401fbeff  nop     dword ptr [rax+rax+00h]
0x1401fbf04  mov     rcx, [rsp+1A8h]; this
0x1401fbf0c  test    eax, eax
0x1401fbf0e  jnz     short loc_1401FBF21
0x1401fbf10  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fbf17  mov     edx, 0A6Fh; void *
0x1401fbf1c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fbf21  mov     eax, 100000h
0x1401fbf26  mov     r15d, eax
0x1401fbf29  cmp     rsi, rax
0x1401fbf2c  cmovb   r15, rsi
0x1401fbf30  mov     rax, qword ptr [rsp+1A8h+FileSize]
0x1401fbf35  sub     rax, rsi
0x1401fbf38  mov     dword ptr [rsp+rdi+1A8h+Overlapped.10h], eax
0x1401fbf3f  shr     rax, 20h
0x1401fbf43  mov     dword ptr [rsp+rdi+1A8h+Overlapped.10h+4], eax
0x1401fbf4a  mov     rcx, [rsp+rdi+1A8h+var_128]; this
0x1401fbf52  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1401fbf57  mov     qword ptr [rsp+1A8h+dwCreationDisposition], r14; lpOverlapped
0x1401fbf5c  xor     r9d, r9d; lpNumberOfBytesRead
0x1401fbf5f  mov     r8d, 100000h; nNumberOfBytesToRead
0x1401fbf65  mov     rdx, [rsp+rdi+1A8h+lpBuffer]; lpBuffer
0x1401fbf6d  mov     rcx, rbx; hFile
0x1401fbf70  call    cs:__imp_ReadFile
0x1401fbf77  nop     dword ptr [rax+rax+00h]
0x1401fbf7c  test    eax, eax
0x1401fbf7e  jz      short loc_1401FBF91
0x1401fbf80  mov     rcx, [rsp+rdi+1A8h+var_128]; this
0x1401fbf88  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1401fbf8d  xor     al, al
0x1401fbf8f  jmp     short loc_1401FBFC2
0x1401fbf91  mov     r14, [rsp+1A8h]
0x1401fbf99  call    cs:__imp_GetLastError
0x1401fbfa0  nop     dword ptr [rax+rax+00h]
0x1401fbfa5  cmp     eax, 3E5h
0x1401fbfaa  jz      short loc_1401FBFC0
0x1401fbfac  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fbfb3  mov     edx, 0A81h; void *
0x1401fbfb8  mov     rcx, r14; this
0x1401fbfbb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fbfc0  mov     al, 1
0x1401fbfc2  mov     [rsp+rdi+1A8h+var_120], al
0x1401fbfc9  sub     rsi, r15
0x1401fbfcc  jmp     loc_1401FBE85
0x1401fbfd1  lea     rdi, [rsp+1A8h+var_128]
0x1401fbfd9  lea     rsi, [rsp+1A8h+var_48]
0x1401fbfe1  cmp     rdi, rsi
0x1401fbfe4  jz      short loc_1401FC035
0x1401fbfe6  cmp     byte ptr [rdi+8], 0
0x1401fbfea  jz      short loc_1401FC02F
0x1401fbfec  mov     [rsp+1A8h+NumberOfBytesTransferred], 0
0x1401fbff4  lea     rdx, [rdi+10h]; lpOverlapped
0x1401fbff8  mov     r9d, 1; bWait
0x1401fbffe  lea     r8, [rsp+1A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1401fc003  mov     rcx, rbx; hFile
0x1401fc006  call    cs:__imp_GetOverlappedResult
0x1401fc00d  nop     dword ptr [rax+rax+00h]
0x1401fc012  mov     rcx, [rsp+1A8h]; this
0x1401fc01a  test    eax, eax
0x1401fc01c  jnz     short loc_1401FC02F
0x1401fc01e  lea     r8, aOnecoreVmWorke_92; "onecore\\vm\\worker\\config\\workerconf"...
0x1401fc025  mov     edx, 0A8Eh; void *
0x1401fc02a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401fc02f  add     rdi, 38h ; '8'
0x1401fc033  jmp     short loc_1401FBFE1
0x1401fc035  lea     rcx, [rsp+1A8h+var_168]
0x1401fc03a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401fc03f  nop
0x1401fc040  lea     r9, _WorkerConfiguration__PrefetchFile____3___ReadContext___ReadContext; void (*)(void *)
0x1401fc047  mov     r8, r13; unsigned __int64
0x1401fc04a  mov     edx, 38h ; '8'; unsigned __int64
0x1401fc04f  lea     rcx, [rsp+1A8h+var_128]; void *
0x1401fc057  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1401fc05c  nop
0x1401fc05d  jmp     short $+2
0x1401fc05f  mov     rcx, [rsp+1A8h+var_48]
0x1401fc067  xor     rcx, rsp; StackCookie
0x1401fc06a  call    __security_check_cookie
0x1401fc06f  add     rsp, 178h
0x1401fc076  pop     r15
0x1401fc078  pop     r14
0x1401fc07a  pop     r13
0x1401fc07c  pop     rdi
0x1401fc07d  pop     rsi
0x1401fc07e  pop     rbx
0x1401fc07f  retn
```
