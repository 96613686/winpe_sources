# Legacy_WinStationShutdownSystem(void *,ulong)

- ea: `0x18002d438`
- end: `0x18002d575`
- name: `?Legacy_WinStationShutdownSystem@@YAEPEAXK@Z`
- size: `317`
- prototype: `unsigned __int8 __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028780`

## callees

- `0x180004554`
- `0x180007890`
- `0x18002bf2c`
- `0x18002cb5c`
- `0x18002d438`
- `0x18002eabc`
- `0x18002fe40`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002d4f5`
- `ntdll!RtlNtStatusToDosError` at `0x18002d4f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d54c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d54c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002d47c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002d47c`
- `RPCRT4!NdrClientCall3` at `0x18002d4df`
- `RPCRT4!NdrClientCall3` at `0x18002d4df`

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
                   (MIDL_STUBLESS_PROXY_INFO *)&stru_18003A150,
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
0x18002d438  mov     [rsp+arg_0], rbx
0x18002d43d  push    rdi
0x18002d43e  sub     rsp, 90h
0x18002d445  mov     rax, cs:__security_cookie
0x18002d44c  xor     rax, rsp
0x18002d44f  mov     [rsp+98h+var_18], rax
0x18002d457  mov     ebx, edx
0x18002d459  mov     [rsp+98h+Status], 0
0x18002d461  mov     [rsp+98h+nSize], 10h
0x18002d469  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002d46e  test    eax, eax
0x18002d470  jz      short loc_18002D48E
0x18002d472  lea     rdx, [rsp+98h+nSize]; nSize
0x18002d477  lea     rcx, [rsp+98h+Buffer]; lpBuffer
0x18002d47c  call    cs:__imp_GetComputerNameW
0x18002d482  lea     rcx, [rsp+98h+Buffer]; unsigned __int16 *
0x18002d487  call    ?Legacy_WinStationOpenServerW@@YAPEAXPEAX@Z; Legacy_WinStationOpenServerW(void *)
0x18002d48c  jmp     short loc_18002D493
0x18002d48e  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002d493  mov     rdi, rax
0x18002d496  mov     [rsp+98h+var_48], rax
0x18002d49b  test    rax, rax
0x18002d49e  jz      loc_18002D554
0x18002d4a4  mov     rax, gs:60h
0x18002d4ad  mov     ecx, [rax+2C0h]
0x18002d4b3  mov     [rsp+98h+var_40], 0
0x18002d4bc  mov     [rsp+98h+var_68], ebx
0x18002d4c0  mov     [rsp+98h+var_70], ecx
0x18002d4c4  lea     rax, [rsp+98h+Status]
0x18002d4c9  mov     [rsp+98h+var_78], rax
0x18002d4ce  mov     r9, rdi
0x18002d4d1  xor     r8d, r8d; pReturnValue
0x18002d4d4  lea     edx, [r8+0Fh]; nProcNum
0x18002d4d8  lea     rcx, stru_18003A150; pProxyInfo
0x18002d4df  call    cs:__imp_NdrClientCall3
0x18002d4e5  mov     rbx, rax
0x18002d4e8  mov     [rsp+98h+var_40], rax
0x18002d4ed  mov     [rsp+98h+var_58], bl
0x18002d4f1  mov     ecx, [rsp+98h+Status]; Status
0x18002d4f5  call    cs:__imp_RtlNtStatusToDosError
0x18002d4fb  mov     [rsp+98h+Status], eax
0x18002d4ff  test    bl, bl
0x18002d501  jnz     short loc_18002D517
0x18002d503  mov     r8d, eax
0x18002d506  lea     rdx, aRpcwinstations; "RpcWinStationShutdownSystem() returned "...
0x18002d50d  mov     ecx, 8; int
0x18002d512  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d517  jmp     short loc_18002D53C
0x18002d519  mov     [rsp+98h+Status], eax
0x18002d51d  mov     r8d, eax
0x18002d520  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002d527  mov     ecx, 8; int
0x18002d52c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d531  xor     bl, bl
0x18002d533  mov     [rsp+98h+var_58], bl
0x18002d537  mov     rdi, [rsp+98h+var_48]
0x18002d53c  mov     rcx, rdi; void *
0x18002d53f  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x18002d544  test    bl, bl
0x18002d546  jnz     short loc_18002D552
0x18002d548  mov     ecx, [rsp+98h+Status]; dwErrCode
0x18002d54c  call    cs:__imp_SetLastError
0x18002d552  mov     al, bl
0x18002d554  mov     rcx, [rsp+98h+var_18]
0x18002d55c  xor     rcx, rsp; StackCookie
0x18002d55f  call    __security_check_cookie
0x18002d564  mov     rbx, [rsp+98h+arg_0]
0x18002d56c  add     rsp, 90h
0x18002d573  pop     rdi
0x18002d574  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
