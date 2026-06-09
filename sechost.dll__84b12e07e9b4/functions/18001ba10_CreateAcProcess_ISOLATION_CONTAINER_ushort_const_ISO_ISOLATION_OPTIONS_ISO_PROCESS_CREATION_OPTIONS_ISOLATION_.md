# CreateAcProcess(_ISOLATION_CONTAINER *,ushort const *,_ISO_ISOLATION_OPTIONS *,_ISO_PROCESS_CREATION_OPTIONS *,_ISOLATION_MANIFSET_PROPERTIES *,_PROCESS_INFORMATION *)

- ea: `0x18001ba10`
- end: `0x18001bb8c`
- name: `?CreateAcProcess@@YAJPEAU_ISOLATION_CONTAINER@@PEBGPEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISO_PROCESS_CREATION_OPTIONS@@PEAU_ISOLATION_MANIFSET_PROPERTIES@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `380`
- prototype: `__int64 __usercall@<rax>(struct _ISOLATION_CONTAINER *@<rcx>, wchar_t *Source@<rdx>, struct _ISO_ISOLATION_OPTIONS *@<r8>, struct _ISO_PROCESS_CREATION_OPTIONS *@<r9>, struct _ISOLATION_MANIFSET_PROPERTIES *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a6d8`

## callees

- `0x180019fb0`
- `0x18001b2b4`
- `0x18001b5dc`
- `0x18001ba10`
- `0x18001bb94`
- `0x18004a1fc`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001ba76`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001ba76`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18001ba8d`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18001ba8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb30`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001bb26`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001bb26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb59`

## pseudocode

```c
__int64 __fastcall CreateAcProcess(
        struct _ISOLATION_CONTAINER *a1,
        wchar_t *Source,
        struct _ISO_ISOLATION_OPTIONS *a3,
        struct _ISO_PROCESS_CREATION_OPTIONS *a4,
        struct _ISOLATION_MANIFSET_PROPERTIES *a5,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  struct _ISO_ISOLATION_OPTIONS *v9; // rdx
  int IsolatedProcessToken; // ebx
  signed int LastError; // eax
  HANDLE hToken[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOEXW Destination; // [rsp+70h] [rbp-90h] BYREF
  wchar_t CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&Destination, 0, sizeof(Destination));
  memcpy_s(&Destination, 0x70u, (char *)a4 + 96, 0x70u);
  Destination.StartupInfo.cb = 112;
  wcscpy_s(CommandLine, 0x104u, Source);
  hToken[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    hToken,
    0);
  IsolatedProcessToken = CreateIsolatedProcessToken(a1, hToken);
  if ( IsolatedProcessToken >= 0 )
  {
    IsolatedProcessToken = GenerateThreadProcAttributeList(a1, v9, a5, &Destination);
    if ( IsolatedProcessToken >= 0 )
    {
      IsolatedProcessToken = 0;
      if ( !CreateProcessAsUserW(
              hToken[0],
              0,
              CommandLine,
              *((LPSECURITY_ATTRIBUTES *)a4 + 7),
              *((LPSECURITY_ATTRIBUTES *)a4 + 8),
              *((_DWORD *)a4 + 18),
              *((_DWORD *)a4 + 19) | 0x80000,
              *((LPVOID *)a4 + 10),
              *((LPCWSTR *)a4 + 11),
              &Destination.StartupInfo,
              lpProcessInformation) )
      {
        LastError = GetLastError();
        IsolatedProcessToken = LastError;
        if ( LastError > 0 )
          IsolatedProcessToken = (unsigned __int16)LastError | 0x80070000;
        IsolationApi::TelemetryHelper::LogAcProcessCreationFailure(IsolatedProcessToken);
      }
      if ( Destination.lpAttributeList != (LPPROC_THREAD_ATTRIBUTE_LIST)*((_QWORD *)a4 + 25) )
        LocalFree(Destination.lpAttributeList);
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hToken);
  return (unsigned int)IsolatedProcessToken;
}

```

## disassembly

```asm
0x18001ba10  push    rbp
0x18001ba12  push    rbx
0x18001ba13  push    rsi
0x18001ba14  push    rdi
0x18001ba15  push    r12
0x18001ba17  push    r14
0x18001ba19  push    r15
0x18001ba1b  lea     rbp, [rsp-200h]
0x18001ba23  sub     rsp, 300h
0x18001ba2a  mov     rax, cs:__security_cookie
0x18001ba31  xor     rax, rsp
0x18001ba34  mov     [rbp+230h+var_40], rax
0x18001ba3b  mov     r14, [rbp+230h+arg_20]
0x18001ba42  mov     rbx, rdx
0x18001ba45  mov     r15, [rbp+230h+arg_28]
0x18001ba4c  mov     rsi, rcx
0x18001ba4f  mov     r12d, 70h ; 'p'
0x18001ba55  lea     rcx, [rsp+330h+Destination]; void *
0x18001ba5a  mov     r8d, r12d; Size
0x18001ba5d  xor     edx, edx; Val
0x18001ba5f  mov     rdi, r9
0x18001ba62  call    memset_0
0x18001ba67  lea     r8, [rdi+60h]; Source
0x18001ba6b  mov     r9d, r12d; SourceSize
0x18001ba6e  mov     edx, r12d; DestinationSize
0x18001ba71  lea     rcx, [rsp+330h+Destination]; Destination
0x18001ba76  call    cs:__imp_memcpy_s
0x18001ba7c  mov     r8, rbx; Source
0x18001ba7f  mov     [rsp+330h+Destination], r12d
0x18001ba84  mov     edx, 104h; SizeInWords
0x18001ba89  lea     rcx, [rbp+230h+CommandLine]; Destination
0x18001ba8d  call    cs:__imp_wcscpy_s
0x18001ba93  xor     edx, edx
0x18001ba95  mov     [rsp+330h+hToken], 0
0x18001ba9e  lea     rcx, [rsp+330h+hToken]
0x18001baa3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001baa8  lea     rdx, [rsp+330h+hToken]; void **
0x18001baad  mov     rcx, rsi; struct _ISOLATION_CONTAINER *
0x18001bab0  call    ?CreateIsolatedProcessToken@@YAJPEAU_ISOLATION_CONTAINER@@PEAPEAX@Z; CreateIsolatedProcessToken(_ISOLATION_CONTAINER *,void * *)
0x18001bab5  mov     ebx, eax
0x18001bab7  test    eax, eax
0x18001bab9  js      loc_18001BB5F
0x18001babf  lea     r9, [rsp+330h+Destination]; struct _STARTUPINFOEXW *
0x18001bac4  mov     r8, r14; struct _ISOLATION_MANIFSET_PROPERTIES *
0x18001bac7  mov     rcx, rsi; struct _ISOLATION_CONTAINER *
0x18001baca  call    ?GenerateThreadProcAttributeList@@YAJPEAU_ISOLATION_CONTAINER@@PEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISOLATION_MANIFSET_PROPERTIES@@PEAU_STARTUPINFOEXW@@@Z; GenerateThreadProcAttributeList(_ISOLATION_CONTAINER *,_ISO_ISOLATION_OPTIONS *,_ISOLATION_MANIFSET_PROPERTIES *,_STARTUPINFOEXW *)
0x18001bacf  mov     ebx, eax
0x18001bad1  test    eax, eax
0x18001bad3  js      loc_18001BB5F
0x18001bad9  mov     edx, [rdi+4Ch]
0x18001badc  lea     rax, [rsp+330h+Destination]
0x18001bae1  mov     r9, [rdi+38h]; lpProcessAttributes
0x18001bae5  lea     r8, [rbp+230h+CommandLine]; lpCommandLine
0x18001bae9  mov     rcx, [rsp+330h+hToken]; hToken
0x18001baee  bts     edx, 13h
0x18001baf2  mov     [rsp+330h+lpProcessInformation], r15; lpProcessInformation
0x18001baf7  xor     ebx, ebx
0x18001baf9  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18001bafe  mov     rax, [rdi+58h]
0x18001bb02  mov     [rsp+330h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18001bb07  mov     rax, [rdi+50h]
0x18001bb0b  mov     [rsp+330h+lpEnvironment], rax; lpEnvironment
0x18001bb10  mov     eax, [rdi+48h]
0x18001bb13  mov     [rsp+330h+dwCreationFlags], edx; dwCreationFlags
0x18001bb17  xor     edx, edx; lpApplicationName
0x18001bb19  mov     [rsp+330h+bInheritHandles], eax; bInheritHandles
0x18001bb1d  mov     rax, [rdi+40h]
0x18001bb21  mov     [rsp+330h+lpThreadAttributes], rax; lpThreadAttributes
0x18001bb26  call    cs:__imp_CreateProcessAsUserW
0x18001bb2c  test    eax, eax
0x18001bb2e  jnz     short loc_18001BB4C
0x18001bb30  call    cs:__imp_GetLastError
0x18001bb36  mov     ebx, eax
0x18001bb38  test    eax, eax
0x18001bb3a  jle     short loc_18001BB45
0x18001bb3c  movzx   ebx, ax
0x18001bb3f  or      ebx, 80070000h
0x18001bb45  mov     ecx, ebx; int
0x18001bb47  call    ?LogAcProcessCreationFailure@TelemetryHelper@IsolationApi@@SAXJ@Z; IsolationApi::TelemetryHelper::LogAcProcessCreationFailure(long)
0x18001bb4c  mov     rcx, [rbp+230h+hMem]; hMem
0x18001bb50  cmp     rcx, [rdi+0C8h]
0x18001bb57  jz      short loc_18001BB5F
0x18001bb59  call    cs:__imp_LocalFree
0x18001bb5f  lea     rcx, [rsp+330h+hToken]
0x18001bb64  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001bb69  mov     eax, ebx
0x18001bb6b  mov     rcx, [rbp+230h+var_40]
0x18001bb72  xor     rcx, rsp; StackCookie
0x18001bb75  call    __security_check_cookie
0x18001bb7a  add     rsp, 300h
0x18001bb81  pop     r15
0x18001bb83  pop     r14
0x18001bb85  pop     r12
0x18001bb87  pop     rdi
0x18001bb88  pop     rsi
0x18001bb89  pop     rbx
0x18001bb8a  pop     rbp
0x18001bb8b  retn
```
