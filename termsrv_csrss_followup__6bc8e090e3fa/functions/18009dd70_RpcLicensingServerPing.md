# RpcLicensingServerPing

- ea: `0x18009dd70`
- end: `0x18009dec5`
- name: `RpcLicensingServerPing`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180009940`
- `0x180025540`
- `0x180097ff0`
- `0x18009dd70`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009de0c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009ddfc`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009ddfc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18009dd9c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18009dd9c`
- `RPCRT4!RpcRevertToSelf` at `0x18009de2c`
- `RPCRT4!RpcRevertToSelf` at `0x18009de3a`
- `RPCRT4!RpcRevertToSelf` at `0x18009de2c`
- `RPCRT4!RpcRevertToSelf` at `0x18009de3a`
- `RPCRT4!RpcImpersonateClient` at `0x18009dddc`
- `RPCRT4!RpcImpersonateClient` at `0x18009dddc`

## string_xrefs

- `0x18009de18`: `RpcLicensingServerPing FAILED - Error in ProcessIdToSessionId: 0x%x`
- `0x18009ddec`: `RpcLicensingServerPing FAILED - Error in RpcImpersonateClient: 0x%x`

## pseudocode

```c
char __fastcall RpcLicensingServerPing(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD LastError; // eax
  int InstanceOfLicenseManager; // eax
  unsigned int Pid; // [rsp+38h] [rbp+18h] BYREF
  DWORD pSessionId; // [rsp+40h] [rbp+20h] BYREF
  struct IEnfLicenseManager *v10; // [rsp+48h] [rbp+28h] BYREF

  v10 = 0;
  Pid = 0;
  pSessionId = 0;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v3 )
  {
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in I_RpcBindingInqLocalClientPID: 0x%x", v3);
    goto LABEL_14;
  }
  _DbgPrintMessage(1, "TSENF: Ping is received from Process ID 0x%x", Pid);
  v4 = RpcImpersonateClient(0);
  if ( v4 )
    goto LABEL_5;
  if ( !ProcessIdToSessionId(Pid, &pSessionId) )
  {
    LastError = GetLastError();
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in ProcessIdToSessionId: 0x%x", LastError);
    RpcRevertToSelf();
    goto LABEL_14;
  }
  v4 = RpcRevertToSelf();
  if ( v4 )
  {
LABEL_5:
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Error in RpcImpersonateClient: 0x%x", v4);
  }
  else if ( g_pEnfCore )
  {
    InstanceOfLicenseManager = CEnforcementCore::GetInstanceOfLicenseManager(g_pEnfCore, &v10);
    if ( InstanceOfLicenseManager >= 0 )
      (*(void (__fastcall **)(struct IEnfLicenseManager *, _QWORD, _QWORD))(*(_QWORD *)v10 + 72LL))(
        v10,
        pSessionId,
        Pid);
    else
      _DbgPrintMessage(
        8,
        "GetInstanceOfLicenseManager failed: 0x%x in %s",
        InstanceOfLicenseManager,
        "RpcLicensingServerPing");
  }
  else
  {
    _DbgPrintMessage(8, "RpcLicensingServerPing FAILED - Enforcement core not started");
  }
LABEL_14:
  *a2 = 0;
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(&v10);
  return 1;
}

```

## disassembly

```asm
0x18009dd70  mov     [rsp-8+arg_0], rbx
0x18009dd75  push    rbp
0x18009dd76  mov     rbp, rsp
0x18009dd79  sub     rsp, 20h
0x18009dd7d  mov     rbx, rdx
0x18009dd80  mov     [rbp+arg_18], 0
0x18009dd88  lea     rdx, [rbp+Pid]; Pid
0x18009dd8c  mov     [rbp+Pid], 0
0x18009dd93  xor     ecx, ecx; Binding
0x18009dd95  mov     [rbp+pSessionId], 0
0x18009dd9c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18009dda3  nop     dword ptr [rax+rax+00h]
0x18009dda8  test    eax, eax
0x18009ddaa  jz      short loc_18009DDC5
0x18009ddac  lea     rdx, aRpclicensingse_2; "RpcLicensingServerPing FAILED - Error i"...
0x18009ddb3  mov     r8d, eax
0x18009ddb6  mov     ecx, 8; int
0x18009ddbb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009ddc0  jmp     loc_18009DEA8
0x18009ddc5  mov     r8d, [rbp+Pid]
0x18009ddc9  lea     rdx, aTsenfPingIsRec; "TSENF: Ping is received from Process ID"...
0x18009ddd0  mov     ecx, 1; int
0x18009ddd5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009ddda  xor     ecx, ecx; BindingHandle
0x18009dddc  call    cs:__imp_RpcImpersonateClient
0x18009dde3  nop     dword ptr [rax+rax+00h]
0x18009dde8  test    eax, eax
0x18009ddea  jz      short loc_18009DDF5
0x18009ddec  lea     rdx, aRpclicensingse_6; "RpcLicensingServerPing FAILED - Error i"...
0x18009ddf3  jmp     short loc_18009DDB3
0x18009ddf5  mov     ecx, [rbp+Pid]; dwProcessId
0x18009ddf8  lea     rdx, [rbp+pSessionId]; pSessionId
0x18009ddfc  call    cs:__imp_ProcessIdToSessionId
0x18009de03  nop     dword ptr [rax+rax+00h]
0x18009de08  test    eax, eax
0x18009de0a  jnz     short loc_18009DE3A
0x18009de0c  call    cs:__imp_GetLastError
0x18009de13  nop     dword ptr [rax+rax+00h]
0x18009de18  lea     rdx, aRpclicensingse_3; "RpcLicensingServerPing FAILED - Error i"...
0x18009de1f  mov     ecx, 8; int
0x18009de24  mov     r8d, eax
0x18009de27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009de2c  call    cs:__imp_RpcRevertToSelf
0x18009de33  nop     dword ptr [rax+rax+00h]
0x18009de38  jmp     short loc_18009DEA8
0x18009de3a  call    cs:__imp_RpcRevertToSelf
0x18009de41  nop     dword ptr [rax+rax+00h]
0x18009de46  test    eax, eax
0x18009de48  jnz     short loc_18009DDEC
0x18009de4a  mov     rcx, cs:?g_pEnfCore@@3PEAVCEnforcementCore@@EA; this
0x18009de51  test    rcx, rcx
0x18009de54  jnz     short loc_18009DE67
0x18009de56  lea     rdx, aRpclicensingse_1; "RpcLicensingServerPing FAILED - Enforce"...
0x18009de5d  lea     ecx, [rax+8]; int
0x18009de60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009de65  jmp     short loc_18009DEA8
0x18009de67  lea     rdx, [rbp+arg_18]; struct IEnfLicenseManager **
0x18009de6b  call    ?GetInstanceOfLicenseManager@CEnforcementCore@@UEAAJPEAPEAVIEnfLicenseManager@@@Z; CEnforcementCore::GetInstanceOfLicenseManager(IEnfLicenseManager * *)
0x18009de70  test    eax, eax
0x18009de72  jns     short loc_18009DE91
0x18009de74  lea     r9, aRpclicensingse_7; "RpcLicensingServerPing"
0x18009de7b  mov     r8d, eax
0x18009de7e  lea     rdx, aGetinstanceofl_0; "GetInstanceOfLicenseManager failed: 0x%"...
0x18009de85  mov     ecx, 8; int
0x18009de8a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009de8f  jmp     short loc_18009DEA8
0x18009de91  mov     rcx, [rbp+arg_18]
0x18009de95  mov     r8d, [rbp+Pid]
0x18009de99  mov     rdx, [rcx]
0x18009de9c  mov     rax, [rdx+48h]
0x18009dea0  mov     edx, [rbp+pSessionId]
0x18009dea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dea8  lea     rcx, [rbp+arg_18]
0x18009deac  mov     dword ptr [rbx], 0
0x18009deb2  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x18009deb7  mov     rbx, [rsp+20h+arg_0]
0x18009debc  mov     al, 1
0x18009debe  add     rsp, 20h
0x18009dec2  pop     rbp
0x18009dec3  retn
```
