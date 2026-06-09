# Legacy_WinStationShadowTarget(void *,ulong,_WINSTATIONCONFIG2W *,_ICA_STACK_ADDRESS *,void *,ulong,void *,ulong,void *,ulong)

- ea: `0x18002f6c8`
- end: `0x18002f87e`
- name: `?Legacy_WinStationShadowTarget@@YAJPEAXKPEAU_WINSTATIONCONFIG2W@@PEAU_ICA_STACK_ADDRESS@@0K0K0K@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONCONFIG2W *@<r8>, struct _ICA_STACK_ADDRESS *@<r9>, void *, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180021810`

## callees

- `0x180005b40`
- `0x18000a784`
- `0x18002f6c8`
- `0x18002fbf4`
- `0x18003154c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002f81e`
- `ntdll!RtlNtStatusToDosError` at `0x18002f81e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f6f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f742`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f82c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f843`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f6f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f742`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f82c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f843`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033cc5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033cc5`
- `RPCRT4!NdrClientCall3` at `0x18002f7ff`
- `RPCRT4!NdrClientCall3` at `0x18002f7ff`

## pseudocode

```c
__int64 __fastcall Legacy_WinStationShadowTarget(
        unsigned __int16 **this,
        ULONG SessionId,
        struct _WINSTATIONCONFIG2W *a3,
        struct _ICA_STACK_ADDRESS *a4,
        void *a5,
        unsigned int a6,
        void *a7,
        unsigned int a8,
        void *a9,
        unsigned int a10)
{
  const unsigned __int16 *v15; // rdx
  unsigned __int16 *LegacyBinding; // rax
  DWORD v17; // eax
  unsigned __int16 **Pointer; // [rsp+80h] [rbp-38h] BYREF
  NTSTATUS Status; // [rsp+C0h] [rbp+8h] BYREF

  Status = 0;
  if ( !this )
  {
    SetLastError(0x57u);
    return 0;
  }
  Pointer = this;
  if ( !CSmartWinStation::Open(&Pointer) )
    return 0;
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(this) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      SetLastError(0x57u);
      return 1;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  LegacyBinding = CPublicBinding::GetLegacyBinding(this, v15);
  Pointer = (unsigned __int16 **)NdrClientCall3(
                                   (MIDL_STUBLESS_PROXY_INFO *)&stru_18003D150,
                                   0x13u,
                                   0,
                                   LegacyBinding,
                                   &Status,
                                   SessionId,
                                   a3,
                                   10472,
                                   a4,
                                   128,
                                   a5,
                                   a6,
                                   a7,
                                   a8,
                                   a9,
                                   a10,
                                   0).Pointer;
  if ( !(_BYTE)Pointer )
  {
    v17 = RtlNtStatusToDosError(Status);
    SetLastError(v17);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x18002f6c8  mov     rax, rsp
0x18002f6cb  push    rbx
0x18002f6cc  push    rsi
0x18002f6cd  push    rdi
0x18002f6ce  push    r14
0x18002f6d0  sub     rsp, 98h
0x18002f6d7  mov     rsi, r9
0x18002f6da  mov     r14, r8
0x18002f6dd  mov     edi, edx
0x18002f6df  mov     rbx, rcx
0x18002f6e2  mov     dword ptr [rax+8], 0
0x18002f6e9  test    rcx, rcx
0x18002f6ec  jnz     short loc_18002F704
0x18002f6ee  lea     ecx, [rbx+57h]; dwErrCode
0x18002f6f1  call    cs:__imp_SetLastError
0x18002f6f8  nop     dword ptr [rax+rax+00h]
0x18002f6fd  xor     eax, eax
0x18002f6ff  jmp     loc_18002F870
0x18002f704  mov     [rsp+0B8h+var_38], rbx
0x18002f70c  lea     rcx, [rsp+0B8h+var_38]; this
0x18002f714  call    ?Open@CSmartWinStation@@QEAAHXZ; CSmartWinStation::Open(void)
0x18002f719  test    eax, eax
0x18002f71b  jz      short loc_18002F6FD
0x18002f71d  cmp     edi, 0FFFFFFFFh
0x18002f720  jnz     short loc_18002F767
0x18002f722  mov     rcx, rbx; void *
0x18002f725  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002f72a  test    eax, eax
0x18002f72c  jnz     short loc_18002F758
0x18002f72e  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002f735  lea     ecx, [rax+4]; int
0x18002f738  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f73d  mov     ecx, 57h ; 'W'; dwErrCode
0x18002f742  call    cs:__imp_SetLastError
0x18002f749  nop     dword ptr [rax+rax+00h]
0x18002f74e  mov     eax, 1
0x18002f753  jmp     loc_18002F870
0x18002f758  mov     rax, gs:60h
0x18002f761  mov     edi, [rax+2C0h]
0x18002f767  mov     rcx, rbx; this
0x18002f76a  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002f76f  mov     [rsp+0B8h+var_38], 0
0x18002f77b  mov     ecx, [rsp+0B8h+arg_48]
0x18002f782  mov     [rsp+0B8h+var_40], ecx
0x18002f786  mov     rcx, [rsp+0B8h+arg_40]
0x18002f78e  mov     [rsp+0B8h+var_48], rcx
0x18002f793  mov     ecx, [rsp+0B8h+arg_38]
0x18002f79a  mov     [rsp+0B8h+var_50], ecx
0x18002f79e  mov     rcx, [rsp+0B8h+arg_30]
0x18002f7a6  mov     [rsp+0B8h+var_58], rcx
0x18002f7ab  mov     ecx, [rsp+0B8h+arg_28]
0x18002f7b2  mov     [rsp+0B8h+var_60], ecx
0x18002f7b6  mov     rcx, [rsp+0B8h+arg_20]
0x18002f7be  mov     [rsp+0B8h+var_68], rcx
0x18002f7c3  mov     [rsp+0B8h+var_70], 80h
0x18002f7cb  mov     [rsp+0B8h+var_78], rsi
0x18002f7d0  mov     [rsp+0B8h+var_80], 28E8h
0x18002f7d8  mov     [rsp+0B8h+var_88], r14
0x18002f7dd  mov     [rsp+0B8h+var_90], edi
0x18002f7e1  lea     rcx, [rsp+0B8h+Status]
0x18002f7e9  mov     [rsp+0B8h+var_98], rcx
0x18002f7ee  mov     r9, rax
0x18002f7f1  xor     r8d, r8d; pReturnValue
0x18002f7f4  lea     edx, [r8+13h]; nProcNum
0x18002f7f8  lea     rcx, stru_18003D150; pProxyInfo
0x18002f7ff  call    cs:__imp_NdrClientCall3
0x18002f806  nop     dword ptr [rax+rax+00h]
0x18002f80b  mov     [rsp+0B8h+var_38], rax
0x18002f813  test    al, al
0x18002f815  jnz     short loc_18002F838
0x18002f817  mov     ecx, [rsp+0B8h+Status]; Status
0x18002f81e  call    cs:__imp_RtlNtStatusToDosError
0x18002f825  nop     dword ptr [rax+rax+00h]
0x18002f82a  mov     ecx, eax; dwErrCode
0x18002f82c  call    cs:__imp_SetLastError
0x18002f833  nop     dword ptr [rax+rax+00h]
0x18002f838  jmp     short loc_18002F869
0x18002f83a  mov     [rsp+0B8h+Status], eax
0x18002f841  mov     ecx, eax; dwErrCode
0x18002f843  call    cs:__imp_SetLastError
0x18002f84a  nop     dword ptr [rax+rax+00h]
0x18002f84f  mov     r8d, [rsp+0B8h+Status]
0x18002f857  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002f85e  mov     ecx, 8; int
0x18002f863  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f868  nop
0x18002f869  mov     eax, [rsp+0B8h+Status]
0x18002f870  add     rsp, 98h
0x18002f877  pop     r14
0x18002f879  pop     rdi
0x18002f87a  pop     rsi
0x18002f87b  pop     rbx
0x18002f87c  retn
0x180033cb4  push    rbp
0x180033cb6  sub     rsp, 80h
0x180033cbd  mov     rbp, rdx
0x180033cc0  mov     rcx, [rcx]
0x180033cc3  mov     ecx, [rcx]; ExceptionCode
0x180033cc5  call    cs:__imp_I_RpcExceptionFilter
0x180033ccc  nop     dword ptr [rax+rax+00h]
0x180033cd1  nop
0x180033cd2  add     rsp, 80h
0x180033cd9  pop     rbp
0x180033cda  retn
```
