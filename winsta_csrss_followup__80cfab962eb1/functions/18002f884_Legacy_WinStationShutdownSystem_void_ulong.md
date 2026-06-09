# Legacy_WinStationShutdownSystem(void *,ulong)

- ea: `0x18002f884`
- end: `0x18002f9da`
- name: `?Legacy_WinStationShutdownSystem@@YAEPEAXK@Z`
- size: `342`
- prototype: `unsigned __int8 __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a330`

## callees

- `0x180005b40`
- `0x18000a784`
- `0x18002e180`
- `0x18002eeec`
- `0x18002f884`
- `0x18003154c`
- `0x180032c20`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002f94d`
- `ntdll!RtlNtStatusToDosError` at `0x18002f94d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002f8c8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002f8c8`
- `RPCRT4!NdrClientCall3` at `0x18002f931`
- `RPCRT4!NdrClientCall3` at `0x18002f931`

## pseudocode

```c
unsigned __int8 __fastcall Legacy_WinStationShutdownSystem(void *a1, int a2)
{
  CPublicBinding *v3; // rcx
  void *LegacyBinding; // rax
  void *v5; // rdi
  ULONG SessionId; // ecx
  CLIENT_CALL_RETURN v7; // rbx
  NTSTATUS v8; // eax
  NTSTATUS Status; // [rsp+44h] [rbp-54h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-50h] BYREF
  void *v12; // [rsp+50h] [rbp-48h]
  CLIENT_CALL_RETURN v13; // [rsp+58h] [rbp-40h]
  WCHAR Buffer[16]; // [rsp+60h] [rbp-38h] BYREF

  Status = 0;
  nSize = 16;
  if ( (unsigned int)IsLocalServer(a1) )
  {
    GetComputerNameW(Buffer, &nSize);
    LegacyBinding = Legacy_WinStationOpenServerW(Buffer);
  }
  else
  {
    LegacyBinding = CPublicBinding::GetLegacyBinding(v3);
  }
  v5 = LegacyBinding;
  v12 = LegacyBinding;
  if ( LegacyBinding )
  {
    SessionId = NtCurrentPeb()->SessionId;
    v13.Simple = 0;
    v7.Pointer = NdrClientCall3(
                   (MIDL_STUBLESS_PROXY_INFO *)&stru_18003D150,
                   0xFu,
                   0,
                   LegacyBinding,
                   &Status,
                   SessionId,
                   a2).Pointer;
    v13.Pointer = v7.Pointer;
    v8 = RtlNtStatusToDosError(Status);
    Status = v8;
    if ( !LOBYTE(v7.Pointer) )
      _DbgPrintMessage(8, "RpcWinStationShutdownSystem() returned error %#x!", v8);
    Legacy_WinStationCloseServer(v5);
    if ( !LOBYTE(v7.Pointer) )
      SetLastError(Status);
    LOBYTE(LegacyBinding) = v7.Pointer;
  }
  return (unsigned __int8)LegacyBinding;
}

```

## disassembly

```asm
0x18002f884  mov     [rsp+arg_0], rbx
0x18002f889  push    rdi
0x18002f88a  sub     rsp, 90h
0x18002f891  mov     rax, cs:__security_cookie
0x18002f898  xor     rax, rsp
0x18002f89b  mov     [rsp+98h+var_18], rax
0x18002f8a3  mov     ebx, edx
0x18002f8a5  mov     [rsp+98h+Status], 0
0x18002f8ad  mov     [rsp+98h+nSize], 10h
0x18002f8b5  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002f8ba  test    eax, eax
0x18002f8bc  jz      short loc_18002F8E0
0x18002f8be  lea     rdx, [rsp+98h+nSize]; nSize
0x18002f8c3  lea     rcx, [rsp+98h+Buffer]; lpBuffer
0x18002f8c8  call    cs:__imp_GetComputerNameW
0x18002f8cf  nop     dword ptr [rax+rax+00h]
0x18002f8d4  lea     rcx, [rsp+98h+Buffer]; unsigned __int16 *
0x18002f8d9  call    ?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z; Legacy_WinStationOpenServerW(void *)
0x18002f8de  jmp     short loc_18002F8E5
0x18002f8e0  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002f8e5  mov     rdi, rax
0x18002f8e8  mov     [rsp+98h+var_48], rax
0x18002f8ed  test    rax, rax
0x18002f8f0  jz      loc_18002F9B8
0x18002f8f6  mov     rax, gs:60h
0x18002f8ff  mov     ecx, [rax+2C0h]
0x18002f905  mov     [rsp+98h+var_40], 0
0x18002f90e  mov     [rsp+98h+var_68], ebx
0x18002f912  mov     [rsp+98h+var_70], ecx
0x18002f916  lea     rax, [rsp+98h+Status]
0x18002f91b  mov     [rsp+98h+var_78], rax
0x18002f920  mov     r9, rdi
0x18002f923  xor     r8d, r8d; pReturnValue
0x18002f926  lea     edx, [r8+0Fh]; nProcNum
0x18002f92a  lea     rcx, stru_18003D150; pProxyInfo
0x18002f931  call    cs:__imp_NdrClientCall3
0x18002f938  nop     dword ptr [rax+rax+00h]
0x18002f93d  mov     rbx, rax
0x18002f940  mov     [rsp+98h+var_40], rax
0x18002f945  mov     [rsp+98h+var_58], bl
0x18002f949  mov     ecx, [rsp+98h+Status]; Status
0x18002f94d  call    cs:__imp_RtlNtStatusToDosError
0x18002f954  nop     dword ptr [rax+rax+00h]
0x18002f959  mov     [rsp+98h+Status], eax
0x18002f95d  test    bl, bl
0x18002f95f  jnz     short loc_18002F975
0x18002f961  mov     r8d, eax
0x18002f964  lea     rdx, aRpcwinstations; "RpcWinStationShutdownSystem() returned "...
0x18002f96b  mov     ecx, 8; int
0x18002f970  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f975  jmp     short loc_18002F99A
0x18002f977  mov     [rsp+98h+Status], eax
0x18002f97b  mov     r8d, eax
0x18002f97e  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002f985  mov     ecx, 8; int
0x18002f98a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f98f  xor     bl, bl
0x18002f991  mov     [rsp+98h+var_58], bl
0x18002f995  mov     rdi, [rsp+98h+var_48]
0x18002f99a  mov     rcx, rdi; void *
0x18002f99d  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x18002f9a2  test    bl, bl
0x18002f9a4  jnz     short loc_18002F9B6
0x18002f9a6  mov     ecx, [rsp+98h+Status]; dwErrCode
0x18002f9aa  call    cs:__imp_SetLastError
0x18002f9b1  nop     dword ptr [rax+rax+00h]
0x18002f9b6  mov     al, bl
0x18002f9b8  mov     rcx, [rsp+98h+var_18]
0x18002f9c0  xor     rcx, rsp; StackCookie
0x18002f9c3  call    __security_check_cookie
0x18002f9c8  mov     rbx, [rsp+98h+arg_0]
0x18002f9d0  add     rsp, 90h
0x18002f9d7  pop     rdi
0x18002f9d8  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
