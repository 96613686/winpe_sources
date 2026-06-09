# WslSession::Launch(ushort const *,int,void *,void *,void *,void * *)

- ea: `0x180007b58`
- end: `0x180007c97`
- name: `?Launch@WslSession@@QEBAJPEBGHPEAX11PEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(WslSession *this, const unsigned __int16 *, __int64, void *, void *, void *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007a80`
- `0x180007ca0`

## callees

- `0x180001dc0`
- `0x180002ab4`
- `0x180004fb4`
- `0x180004fd4`
- `0x18000698c`
- `0x180007b58`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180007c3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180007c3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c60`

## pseudocode

```c
__int64 __fastcall WslSession::Launch(
        WslSession *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4,
        void *a5,
        void *a6,
        void **a7)
{
  __int64 v7; // rcx
  int CommandLineForDistro; // eax
  unsigned int LastError; // ebx
  const char *v11; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-C1h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-91h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-71h] BYREF
  LPWSTR lpCommandLine; // [rsp+E0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = *(_QWORD *)this;
  lpCommandLine = 0;
  CommandLineForDistro = WslSession::s_GetCommandLineForDistro(v7, a2, a3, &lpCommandLine);
  LastError = CommandLineForDistro;
  if ( CommandLineForDistro >= 0 )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 256;
    StartupInfo.hStdInput = a4;
    StartupInfo.hStdOutput = a5;
    StartupInfo.hStdError = a6;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, lpCommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      CloseHandle(ProcessInformation.hThread);
      LastError = 0;
      *a7 = ProcessInformation.hProcess;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x69,
                    (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\launch.cpp",
                    v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\launch.cpp",
      (const char *)(unsigned int)CommandLineForDistro,
      bInheritHandles);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpCommandLine);
  return LastError;
}

```

## disassembly

```asm
0x180007b58  push    rbp
0x180007b5a  push    rbx
0x180007b5b  push    rsi
0x180007b5c  push    rdi
0x180007b5d  push    r14
0x180007b5f  push    r15
0x180007b61  lea     rbp, [rsp-17h]
0x180007b66  sub     rsp, 0F8h
0x180007b6d  mov     rax, cs:__security_cookie
0x180007b74  xor     rax, rsp
0x180007b77  mov     [rbp+3Fh+var_38], rax
0x180007b7b  mov     rcx, [rcx]
0x180007b7e  mov     rsi, r9
0x180007b81  mov     r14, [rbp+3Fh+arg_20]
0x180007b85  lea     r9, [rbp+3Fh+lpCommandLine]
0x180007b89  mov     r15, [rbp+3Fh+arg_28]
0x180007b8d  mov     rdi, [rbp+3Fh+arg_30]
0x180007b91  mov     [rbp+3Fh+lpCommandLine], 0
0x180007b99  call    ?s_GetCommandLineForDistro@WslSession@@CAJPEBG0HAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WslSession::s_GetCommandLineForDistro(ushort const *,ushort const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180007b9e  mov     ebx, eax
0x180007ba0  test    eax, eax
0x180007ba2  jns     short loc_180007BC1
0x180007ba4  mov     rcx, [rbp+47h]; this
0x180007ba8  lea     r8, aOnecoreVmWslLx_4; "onecore\\vm\\wsl\\lxss\\wslapi\\launch."...
0x180007baf  mov     r9d, eax; char *
0x180007bb2  mov     edx, 54h ; 'T'; void *
0x180007bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bbc  jmp     loc_180007C70
0x180007bc1  mov     ebx, 68h ; 'h'
0x180007bc6  lea     rcx, [rbp+3Fh+StartupInfo]; void *
0x180007bca  mov     r8d, ebx; Size
0x180007bcd  xor     edx, edx; Val
0x180007bcf  call    memset_0
0x180007bd4  mov     rdx, [rbp+3Fh+lpCommandLine]; lpCommandLine
0x180007bd8  xor     eax, eax
0x180007bda  mov     qword ptr [rsp+120h+ProcessInformation.dwProcessId], rax
0x180007bdf  xorps   xmm0, xmm0
0x180007be2  lea     rax, [rsp+120h+ProcessInformation]
0x180007be7  mov     [rbp+3Fh+StartupInfo.cb], ebx
0x180007bea  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x180007bef  xor     r9d, r9d; lpThreadAttributes
0x180007bf2  lea     rax, [rbp+3Fh+StartupInfo]
0x180007bf6  mov     [rbp+3Fh+StartupInfo.dwFlags], 100h
0x180007bfd  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x180007c02  xor     r8d, r8d; lpProcessAttributes
0x180007c05  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180007c0e  xor     ecx, ecx; lpApplicationName
0x180007c10  mov     [rsp+120h+lpEnvironment], 0; lpEnvironment
0x180007c19  mov     [rsp+120h+dwCreationFlags], 0; dwCreationFlags
0x180007c21  mov     [rsp+120h+bInheritHandles], 1; bInheritHandles
0x180007c29  mov     [rbp+3Fh+StartupInfo.hStdInput], rsi
0x180007c2d  mov     [rbp+3Fh+StartupInfo.hStdOutput], r14
0x180007c31  mov     [rbp+3Fh+StartupInfo.hStdError], r15
0x180007c35  movups  xmmword ptr [rsp+120h+ProcessInformation.hProcess], xmm0
0x180007c3a  call    cs:__imp_CreateProcessW
0x180007c40  test    eax, eax
0x180007c42  jnz     short loc_180007C5B
0x180007c44  mov     rcx, [rbp+47h]; this
0x180007c48  lea     r8, aOnecoreVmWslLx_4; "onecore\\vm\\wsl\\lxss\\wslapi\\launch."...
0x180007c4f  lea     edx, [rbx+1]; void *
0x180007c52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007c57  mov     ebx, eax
0x180007c59  jmp     short loc_180007C70
0x180007c5b  mov     rcx, [rsp+120h+ProcessInformation.hThread]; hObject
0x180007c60  call    cs:__imp_CloseHandle
0x180007c66  mov     rax, [rsp+120h+ProcessInformation.hProcess]
0x180007c6b  xor     ebx, ebx
0x180007c6d  mov     [rdi], rax
0x180007c70  lea     rcx, [rbp+3Fh+lpCommandLine]
0x180007c74  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007c79  mov     eax, ebx
0x180007c7b  mov     rcx, [rbp+3Fh+var_38]
0x180007c7f  xor     rcx, rsp; StackCookie
0x180007c82  call    __security_check_cookie
0x180007c87  add     rsp, 0F8h
0x180007c8e  pop     r15
0x180007c90  pop     r14
0x180007c92  pop     rdi
0x180007c93  pop     rsi
0x180007c94  pop     rbx
0x180007c95  pop     rbp
0x180007c96  retn
```
