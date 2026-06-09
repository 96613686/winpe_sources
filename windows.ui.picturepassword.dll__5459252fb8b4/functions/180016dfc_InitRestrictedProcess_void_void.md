# _InitRestrictedProcess(void * *,void * *)

- ea: `0x180016dfc`
- end: `0x180016f74`
- name: `?_InitRestrictedProcess@@YAJPEAPEAX0@Z`
- size: `376`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ad34`

## callees

- `0x180002610`
- `0x180002f94`
- `0x1800092b8`
- `0x180016a8c`
- `0x180016c5c`
- `0x180016dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016e7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016e7c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016f12`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f45`

## pseudocode

```c
__int64 __fastcall _InitRestrictedProcess(void **a1, void **a2)
{
  const unsigned __int16 *v4; // rcx
  int Error; // ebx
  HANDLE EventW; // rdi
  HANDLE hThread; // rcx
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CommandLine[264]; // [rsp+F0h] [rbp-10h] BYREF

  *a1 = 0;
  *a2 = 0;
  hToken = 0;
  Error = _CreateRestrictedToken((__int64)a1, &hToken);
  if ( Error >= 0 )
  {
    Error = _GetCommandLine(v4, CommandLine);
    if ( Error >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, L"22d8c27b-47a1-48d1-ad08-7da7abd79617");
      if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        *(_QWORD *)&StartupInfo.cb = 104;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        memset_0(&StartupInfo.lpReserved, 0, 0x60u);
        StartupInfo.dwFlags = 128;
        if ( CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          Error = 0;
LABEL_8:
          hThread = ProcessInformation.hThread;
          *a1 = ProcessInformation.hProcess;
          *a2 = EventW;
LABEL_11:
          CloseHandle(hThread);
          return (unsigned int)Error;
        }
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
          goto LABEL_8;
        if ( EventW )
        {
          hThread = EventW;
          goto LABEL_11;
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180016dfc  mov     [rsp-8+arg_10], rbx
0x180016e01  mov     [rsp-8+arg_18], rsi
0x180016e06  push    rbp
0x180016e07  push    rdi
0x180016e08  push    r14
0x180016e0a  lea     rbp, [rsp-210h]
0x180016e12  sub     rsp, 310h
0x180016e19  mov     rax, cs:__security_cookie
0x180016e20  xor     rax, rsp
0x180016e23  mov     [rbp+220h+var_20], rax
0x180016e2a  mov     qword ptr [rcx], 0
0x180016e31  mov     r14, rdx
0x180016e34  mov     qword ptr [rdx], 0
0x180016e3b  mov     rsi, rcx
0x180016e3e  lea     rdx, [rsp+320h+hToken]; void **
0x180016e43  mov     [rsp+320h+hToken], 0
0x180016e4c  call    ?_CreateRestrictedToken@@YAJ_NPEAPEAX@Z; _CreateRestrictedToken(bool,void * *)
0x180016e51  mov     ebx, eax
0x180016e53  test    eax, eax
0x180016e55  js      loc_180016F4B
0x180016e5b  lea     rdx, [rbp+220h+CommandLine]; unsigned __int16 *
0x180016e5f  call    ?_GetCommandLine@@YAJPEBGPEAGI@Z; _GetCommandLine(ushort const *,ushort *,uint)
0x180016e64  mov     ebx, eax
0x180016e66  test    eax, eax
0x180016e68  js      loc_180016F4B
0x180016e6e  lea     r9, Name; "22d8c27b-47a1-48d1-ad08-7da7abd79617"
0x180016e75  xor     r8d, r8d; bInitialState
0x180016e78  xor     edx, edx; bManualReset
0x180016e7a  xor     ecx, ecx; lpEventAttributes
0x180016e7c  call    cs:__imp_CreateEventW
0x180016e82  mov     rdi, rax
0x180016e85  test    rax, rax
0x180016e88  jnz     short loc_180016E99
0x180016e8a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016e8f  mov     ebx, eax
0x180016e91  test    eax, eax
0x180016e93  js      loc_180016F4B
0x180016e99  xor     eax, eax
0x180016e9b  mov     qword ptr [rbp+220h+StartupInfo.cb], 68h ; 'h'
0x180016ea3  xorps   xmm0, xmm0
0x180016ea6  mov     qword ptr [rsp+320h+ProcessInformation.dwProcessId], rax
0x180016eab  xor     edx, edx; Val
0x180016ead  lea     rcx, [rbp+220h+StartupInfo.lpReserved]; void *
0x180016eb1  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x180016eb6  lea     r8d, [rax+60h]; Size
0x180016eba  call    memset_0
0x180016ebf  mov     rcx, [rsp+320h+hToken]; hToken
0x180016ec4  lea     rax, [rsp+320h+ProcessInformation]
0x180016ec9  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x180016ece  lea     r8, [rbp+220h+CommandLine]; lpCommandLine
0x180016ed2  lea     rax, [rbp+220h+StartupInfo]
0x180016ed6  mov     [rbp+220h+StartupInfo.dwFlags], 80h
0x180016edd  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x180016ee2  xor     r9d, r9d; lpProcessAttributes
0x180016ee5  mov     [rsp+320h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180016eee  xor     edx, edx; lpApplicationName
0x180016ef0  mov     [rsp+320h+lpEnvironment], 0; lpEnvironment
0x180016ef9  mov     [rsp+320h+dwCreationFlags], 0; dwCreationFlags
0x180016f01  mov     [rsp+320h+bInheritHandles], 0; bInheritHandles
0x180016f09  mov     [rsp+320h+lpThreadAttributes], 0; lpThreadAttributes
0x180016f12  call    cs:__imp_CreateProcessAsUserW
0x180016f18  test    eax, eax
0x180016f1a  jz      short loc_180016F20
0x180016f1c  xor     ebx, ebx
0x180016f1e  jmp     short loc_180016F2B
0x180016f20  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016f25  mov     ebx, eax
0x180016f27  test    eax, eax
0x180016f29  js      short loc_180016F3D
0x180016f2b  mov     rax, [rsp+320h+ProcessInformation.hProcess]
0x180016f30  mov     rcx, [rsp+320h+ProcessInformation.hThread]
0x180016f35  mov     [rsi], rax
0x180016f38  mov     [r14], rdi
0x180016f3b  jmp     short loc_180016F45
0x180016f3d  test    rdi, rdi
0x180016f40  jz      short loc_180016F4B
0x180016f42  mov     rcx, rdi; hObject
0x180016f45  call    cs:__imp_CloseHandle
0x180016f4b  mov     eax, ebx
0x180016f4d  mov     rcx, [rbp+220h+var_20]
0x180016f54  xor     rcx, rsp; StackCookie
0x180016f57  call    __security_check_cookie
0x180016f5c  lea     r11, [rsp+320h+var_10]
0x180016f64  mov     rbx, [r11+30h]
0x180016f68  mov     rsi, [r11+38h]
0x180016f6c  mov     rsp, r11
0x180016f6f  pop     r14
0x180016f71  pop     rdi
0x180016f72  pop     rbp
0x180016f73  retn
```
