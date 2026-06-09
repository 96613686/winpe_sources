# Legacy_WinStationShadowTarget(void *,ulong,_WINSTATIONCONFIG2W *,_ICA_STACK_ADDRESS *,void *,ulong,void *,ulong,void *,ulong)

- ea: `0x18002d2a0`
- end: `0x18002d431`
- name: `?Legacy_WinStationShadowTarget@@YAJPEAXKPEAU_WINSTATIONCONFIG2W@@PEAU_ICA_STACK_ADDRESS@@0K0K0K@Z`
- size: `401`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONCONFIG2W *@<r8>, struct _ICA_STACK_ADDRESS *@<r9>, void *, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800200c0`

## callees

- `0x180004554`
- `0x180007890`
- `0x18002d2a0`
- `0x18002d754`
- `0x18002eabc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002d3e4`
- `ntdll!RtlNtStatusToDosError` at `0x18002d3e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d3fd`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d85`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030d85`
- `RPCRT4!NdrClientCall3` at `0x18002d3cb`
- `RPCRT4!NdrClientCall3` at `0x18002d3cb`

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
  ULONG v17; // eax
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
                                   (MIDL_STUBLESS_PROXY_INFO *)&stru_18003A150,
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
0x18002d2a0  mov     rax, rsp
0x18002d2a3  push    rbx
0x18002d2a4  push    rsi
0x18002d2a5  push    rdi
0x18002d2a6  push    r14
0x18002d2a8  sub     rsp, 98h
0x18002d2af  mov     rsi, r9
0x18002d2b2  mov     r14, r8
0x18002d2b5  mov     edi, edx
0x18002d2b7  mov     rbx, rcx
0x18002d2ba  mov     dword ptr [rax+8], 0
0x18002d2c1  test    rcx, rcx
0x18002d2c4  jnz     short loc_18002D2D6
0x18002d2c6  lea     ecx, [rbx+57h]; dwErrCode
0x18002d2c9  call    cs:__imp_SetLastError
0x18002d2cf  xor     eax, eax
0x18002d2d1  jmp     loc_18002D424
0x18002d2d6  mov     [rsp+0B8h+var_38], rbx
0x18002d2de  lea     rcx, [rsp+0B8h+var_38]; this
0x18002d2e6  call    ?Open@CSmartWinStation@@QEAAHXZ; CSmartWinStation::Open(void)
0x18002d2eb  test    eax, eax
0x18002d2ed  jz      short loc_18002D2CF
0x18002d2ef  cmp     edi, 0FFFFFFFFh
0x18002d2f2  jnz     short loc_18002D333
0x18002d2f4  mov     rcx, rbx; void *
0x18002d2f7  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002d2fc  test    eax, eax
0x18002d2fe  jnz     short loc_18002D324
0x18002d300  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002d307  lea     ecx, [rax+4]; int
0x18002d30a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d30f  mov     ecx, 57h ; 'W'; dwErrCode
0x18002d314  call    cs:__imp_SetLastError
0x18002d31a  mov     eax, 1
0x18002d31f  jmp     loc_18002D424
0x18002d324  mov     rax, gs:60h
0x18002d32d  mov     edi, [rax+2C0h]
0x18002d333  mov     rcx, rbx; this
0x18002d336  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002d33b  mov     [rsp+0B8h+var_38], 0
0x18002d347  mov     ecx, [rsp+0B8h+arg_48]
0x18002d34e  mov     [rsp+0B8h+var_40], ecx
0x18002d352  mov     rcx, [rsp+0B8h+arg_40]
0x18002d35a  mov     [rsp+0B8h+var_48], rcx
0x18002d35f  mov     ecx, [rsp+0B8h+arg_38]
0x18002d366  mov     [rsp+0B8h+var_50], ecx
0x18002d36a  mov     rcx, [rsp+0B8h+arg_30]
0x18002d372  mov     [rsp+0B8h+var_58], rcx
0x18002d377  mov     ecx, [rsp+0B8h+arg_28]
0x18002d37e  mov     [rsp+0B8h+var_60], ecx
0x18002d382  mov     rcx, [rsp+0B8h+arg_20]
0x18002d38a  mov     [rsp+0B8h+var_68], rcx
0x18002d38f  mov     [rsp+0B8h+var_70], 80h
0x18002d397  mov     [rsp+0B8h+var_78], rsi
0x18002d39c  mov     [rsp+0B8h+var_80], 28E8h
0x18002d3a4  mov     [rsp+0B8h+var_88], r14
0x18002d3a9  mov     [rsp+0B8h+var_90], edi
0x18002d3ad  lea     rcx, [rsp+0B8h+Status]
0x18002d3b5  mov     [rsp+0B8h+var_98], rcx
0x18002d3ba  mov     r9, rax
0x18002d3bd  xor     r8d, r8d; pReturnValue
0x18002d3c0  lea     edx, [r8+13h]; nProcNum
0x18002d3c4  lea     rcx, stru_18003A150; pProxyInfo
0x18002d3cb  call    cs:__imp_NdrClientCall3
0x18002d3d1  mov     [rsp+0B8h+var_38], rax
0x18002d3d9  test    al, al
0x18002d3db  jnz     short loc_18002D3F2
0x18002d3dd  mov     ecx, [rsp+0B8h+Status]; Status
0x18002d3e4  call    cs:__imp_RtlNtStatusToDosError
0x18002d3ea  mov     ecx, eax; dwErrCode
0x18002d3ec  call    cs:__imp_SetLastError
0x18002d3f2  jmp     short loc_18002D41D
0x18002d3f4  mov     [rsp+0B8h+Status], eax
0x18002d3fb  mov     ecx, eax; dwErrCode
0x18002d3fd  call    cs:__imp_SetLastError
0x18002d403  mov     r8d, [rsp+0B8h+Status]
0x18002d40b  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002d412  mov     ecx, 8; int
0x18002d417  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d41c  nop
0x18002d41d  mov     eax, [rsp+0B8h+Status]
0x18002d424  add     rsp, 98h
0x18002d42b  pop     r14
0x18002d42d  pop     rdi
0x18002d42e  pop     rsi
0x18002d42f  pop     rbx
0x18002d430  retn
0x180030d74  push    rbp
0x180030d76  sub     rsp, 80h
0x180030d7d  mov     rbp, rdx
0x180030d80  mov     rcx, [rcx]
0x180030d83  mov     ecx, [rcx]; ExceptionCode
0x180030d85  call    cs:__imp_I_RpcExceptionFilter
0x180030d8b  nop
0x180030d8c  add     rsp, 80h
0x180030d93  pop     rbp
0x180030d94  retn
```
