# WitnessUpcallServerInitialize

- ea: `0x18000cba4`
- end: `0x18000ce0e`
- name: `WitnessUpcallServerInitialize`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c978`

## callees

- `0x18000cba4`
- `0x180024550`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000cbe5`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cbe5`
- `ntdll!RtlReleaseResource` at `0x18000cdc6`
- `ntdll!RtlReleaseResource` at `0x18000cdc6`
- `ntdll!RtlDeleteResource` at `0x18000cddd`
- `ntdll!RtlDeleteResource` at `0x18000cddd`
- `ntdll!RtlInitializeResource` at `0x18000cbca`
- `ntdll!RtlInitializeResource` at `0x18000cbca`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18000cc7f`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18000cc7f`
- `RPCRT4!RpcEpRegisterW` at `0x18000cd17`
- `RPCRT4!RpcEpRegisterW` at `0x18000cd17`
- `RPCRT4!RpcServerInqBindings` at `0x18000cccb`
- `RPCRT4!RpcServerInqBindings` at `0x18000cccb`
- `RPCRT4!RpcBindingVectorFree` at `0x18000cdb3`
- `RPCRT4!RpcBindingVectorFree` at `0x18000cdb3`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000cd6c`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000cd6c`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000cc01`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000cc01`

## pseudocode

```c
__int64 __fastcall WitnessUpcallServerInitialize(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp+8h] BYREF

  pUpcallDispatch = a1;
  BindingVector = 0;
  RtlInitializeResource(&UpcallServerResource);
  RtlAcquireResourceExclusive(&UpcallServerResource, 1u);
  v1 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, 0, 0);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v4 = 14;
LABEL_6:
      WPP_SF_d(v3[2], v4, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v1);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  v1 = RpcServerRegisterIfEx(
         qword_1800380C0,
         0,
         0,
         0xB1u,
         0x4D2u,
         (RPC_IF_CALLBACK_FN *)WitnessUpcallServerSecurityCallback);
  v2 = v1;
  if ( !v1 )
  {
    v5 = RpcServerInqBindings(&BindingVector);
    if ( v5 )
    {
      v6 = WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control
        || (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
LABEL_23:
        v1 = RpcServerUnregisterIf(qword_1800380C0, 0, 1u);
        v2 = v1;
        if ( v1 )
        {
          v3 = WPP_witness_GLOBAL_Control;
          if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
            && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
          {
            v4 = 19;
            goto LABEL_6;
          }
        }
        goto LABEL_29;
      }
      v7 = 16;
    }
    else
    {
      v5 = RpcEpRegisterW(qword_1800380C0, BindingVector, 0, (RPC_WSTR)L"Witness Client Upcall Server");
      v2 = v5;
      if ( !v5 )
      {
        UpcallServerState = 1;
        goto LABEL_29;
      }
      v6 = WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control
        || (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        goto LABEL_23;
      }
      v7 = 17;
    }
    WPP_SF_d(v6[2], v7, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v5);
    goto LABEL_23;
  }
  v3 = WPP_witness_GLOBAL_Control;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    v4 = 15;
    goto LABEL_6;
  }
LABEL_29:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  RtlReleaseResource(&UpcallServerResource);
  if ( v2 )
  {
    RtlDeleteResource(&UpcallServerResource);
    UpcallServerState = 2;
  }
  else
  {
    UpcallServerResourceInitialized = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18000cba4  mov     [rsp+arg_8], rbx
0x18000cba9  mov     [rsp+arg_10], rsi
0x18000cbae  push    rdi
0x18000cbaf  sub     rsp, 30h
0x18000cbb3  mov     cs:pUpcallDispatch, rcx
0x18000cbba  lea     rcx, UpcallServerResource; Resource
0x18000cbc1  mov     [rsp+38h+BindingVector], 0
0x18000cbca  call    cs:__imp_RtlInitializeResource
0x18000cbd1  nop     dword ptr [rax+rax+00h]
0x18000cbd6  mov     esi, 1
0x18000cbdb  lea     rcx, UpcallServerResource; Resource
0x18000cbe2  mov     dl, sil; Wait
0x18000cbe5  call    cs:__imp_RtlAcquireResourceExclusive
0x18000cbec  nop     dword ptr [rax+rax+00h]
0x18000cbf1  xor     r9d, r9d; SecurityDescriptor
0x18000cbf4  lea     edx, [rsi+9]; MaxCalls
0x18000cbf7  xor     r8d, r8d; Endpoint
0x18000cbfa  lea     rcx, String2; "ncalrpc"
0x18000cc01  call    cs:__imp_RpcServerUseProtseqEpW
0x18000cc08  nop     dword ptr [rax+rax+00h]
0x18000cc0d  mov     ebx, eax
0x18000cc0f  test    eax, eax
0x18000cc11  jz      short loc_18000CC59
0x18000cc13  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cc1a  lea     rdi, WPP_witness_GLOBAL_Control
0x18000cc21  cmp     rcx, rdi
0x18000cc24  jz      loc_18000CDA6
0x18000cc2a  test    [rcx+1Ch], sil
0x18000cc2e  jz      loc_18000CDA6
0x18000cc34  cmp     [rcx+19h], sil
0x18000cc38  jb      loc_18000CDA6
0x18000cc3e  lea     edx, [rsi+0Dh]
0x18000cc41  mov     rcx, [rcx+10h]
0x18000cc45  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000cc4c  mov     r9d, eax
0x18000cc4f  call    WPP_SF_d
0x18000cc54  jmp     loc_18000CDA6
0x18000cc59  lea     rax, WitnessUpcallServerSecurityCallback
0x18000cc60  mov     r9d, 0B1h; Flags
0x18000cc66  mov     [rsp+38h+IfCallback], rax; IfCallback
0x18000cc6b  lea     rcx, qword_1800380C0; IfSpec
0x18000cc72  xor     r8d, r8d; MgrEpv
0x18000cc75  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x18000cc7d  xor     edx, edx; MgrTypeUuid
0x18000cc7f  call    cs:__imp_RpcServerRegisterIfEx
0x18000cc86  nop     dword ptr [rax+rax+00h]
0x18000cc8b  mov     ebx, eax
0x18000cc8d  test    eax, eax
0x18000cc8f  jz      short loc_18000CCC6
0x18000cc91  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cc98  lea     rdi, WPP_witness_GLOBAL_Control
0x18000cc9f  cmp     rcx, rdi
0x18000cca2  jz      loc_18000CDA6
0x18000cca8  test    [rcx+1Ch], sil
0x18000ccac  jz      loc_18000CDA6
0x18000ccb2  cmp     [rcx+19h], sil
0x18000ccb6  jb      loc_18000CDA6
0x18000ccbc  mov     edx, 0Fh
0x18000ccc1  jmp     loc_18000CC41
0x18000ccc6  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x18000cccb  call    cs:__imp_RpcServerInqBindings
0x18000ccd2  nop     dword ptr [rax+rax+00h]
0x18000ccd7  test    eax, eax
0x18000ccd9  jz      short loc_18000CD01
0x18000ccdb  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cce2  lea     rdi, WPP_witness_GLOBAL_Control
0x18000cce9  cmp     rcx, rdi
0x18000ccec  jz      short loc_18000CD60
0x18000ccee  test    [rcx+1Ch], sil
0x18000ccf2  jz      short loc_18000CD60
0x18000ccf4  cmp     [rcx+19h], sil
0x18000ccf8  jb      short loc_18000CD60
0x18000ccfa  mov     edx, 10h
0x18000ccff  jmp     short loc_18000CD4D
0x18000cd01  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x18000cd06  lea     r9, aWitnessClientU; "Witness Client Upcall Server"
0x18000cd0d  xor     r8d, r8d; UuidVector
0x18000cd10  lea     rcx, qword_1800380C0; IfSpec
0x18000cd17  call    cs:__imp_RpcEpRegisterW
0x18000cd1e  nop     dword ptr [rax+rax+00h]
0x18000cd23  mov     ebx, eax
0x18000cd25  test    eax, eax
0x18000cd27  jz      short loc_18000CDA0
0x18000cd29  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cd30  lea     rdi, WPP_witness_GLOBAL_Control
0x18000cd37  cmp     rcx, rdi
0x18000cd3a  jz      short loc_18000CD60
0x18000cd3c  test    [rcx+1Ch], sil
0x18000cd40  jz      short loc_18000CD60
0x18000cd42  cmp     [rcx+19h], sil
0x18000cd46  jb      short loc_18000CD60
0x18000cd48  mov     edx, 11h
0x18000cd4d  mov     rcx, [rcx+10h]
0x18000cd51  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000cd58  mov     r9d, eax
0x18000cd5b  call    WPP_SF_d
0x18000cd60  mov     r8d, esi; WaitForCallsToComplete
0x18000cd63  lea     rcx, qword_1800380C0; IfSpec
0x18000cd6a  xor     edx, edx; MgrTypeUuid
0x18000cd6c  call    cs:__imp_RpcServerUnregisterIf
0x18000cd73  nop     dword ptr [rax+rax+00h]
0x18000cd78  mov     ebx, eax
0x18000cd7a  test    eax, eax
0x18000cd7c  jz      short loc_18000CDA6
0x18000cd7e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000cd85  cmp     rcx, rdi
0x18000cd88  jz      short loc_18000CDA6
0x18000cd8a  test    [rcx+1Ch], sil
0x18000cd8e  jz      short loc_18000CDA6
0x18000cd90  cmp     [rcx+19h], sil
0x18000cd94  jb      short loc_18000CDA6
0x18000cd96  mov     edx, 13h
0x18000cd9b  jmp     loc_18000CC41
0x18000cda0  mov     cs:UpcallServerState, esi
0x18000cda6  cmp     [rsp+38h+BindingVector], 0
0x18000cdac  jz      short loc_18000CDBF
0x18000cdae  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x18000cdb3  call    cs:__imp_RpcBindingVectorFree
0x18000cdba  nop     dword ptr [rax+rax+00h]
0x18000cdbf  lea     rcx, UpcallServerResource; Resource
0x18000cdc6  call    cs:__imp_RtlReleaseResource
0x18000cdcd  nop     dword ptr [rax+rax+00h]
0x18000cdd2  test    ebx, ebx
0x18000cdd4  jz      short loc_18000CDF5
0x18000cdd6  lea     rcx, UpcallServerResource; Resource
0x18000cddd  call    cs:__imp_RtlDeleteResource
0x18000cde4  nop     dword ptr [rax+rax+00h]
0x18000cde9  mov     cs:UpcallServerState, 2
0x18000cdf3  jmp     short loc_18000CDFB
0x18000cdf5  mov     cs:UpcallServerResourceInitialized, esi
0x18000cdfb  mov     rsi, [rsp+38h+arg_10]
0x18000ce00  mov     eax, ebx
0x18000ce02  mov     rbx, [rsp+38h+arg_8]
0x18000ce07  add     rsp, 30h
0x18000ce0b  pop     rdi
0x18000ce0c  retn
```
