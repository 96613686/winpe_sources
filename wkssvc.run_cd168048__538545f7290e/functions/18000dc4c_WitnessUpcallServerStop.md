# WitnessUpcallServerStop

- ea: `0x18000dc4c`
- end: `0x18000de3b`
- name: `WitnessUpcallServerStop`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000da34`

## callees

- `0x18000dc4c`
- `0x180024520`
- `0x180024550`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000dcac`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000dcac`
- `ntdll!RtlReleaseResource` at `0x18000dcd2`
- `ntdll!RtlReleaseResource` at `0x18000ddb5`
- `ntdll!RtlReleaseResource` at `0x18000dcd2`
- `ntdll!RtlReleaseResource` at `0x18000ddb5`
- `ntdll!RtlDeleteResource` at `0x18000de17`
- `ntdll!RtlDeleteResource` at `0x18000de17`
- `RPCRT4!RpcEpUnregister` at `0x18000dd53`
- `RPCRT4!RpcEpUnregister` at `0x18000dd53`
- `RPCRT4!RpcServerInqBindings` at `0x18000dd2d`
- `RPCRT4!RpcServerInqBindings` at `0x18000dd2d`
- `RPCRT4!RpcBindingVectorFree` at `0x18000dd98`
- `RPCRT4!RpcBindingVectorFree` at `0x18000dd98`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000ddce`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000ddce`

## pseudocode

```c
__int64 WitnessUpcallServerStop()
{
  __int64 result; // rax
  unsigned int v1; // edi
  unsigned int v2; // eax
  unsigned int v3; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp+8h] BYREF

  BindingVector = 0;
  if ( UpcallServerResourceInitialized )
  {
    RtlAcquireResourceExclusive(&UpcallServerResource, 1u);
    if ( UpcallServerState == 1 )
    {
      if ( !RpcServerInqBindings(&BindingVector) )
      {
        v2 = RpcEpUnregister(qword_1800380C0, BindingVector, 0);
        if ( v2
          && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
          && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 22, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v2);
        }
        RpcBindingVectorFree(&BindingVector);
      }
      UpcallServerState = 2;
      RtlReleaseResource(&UpcallServerResource);
      v3 = RpcServerUnregisterIf(qword_1800380C0, 0, 1u);
      v1 = v3;
      if ( v3
        && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 23, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v3);
      }
    }
    else
    {
      UpcallServerState = 2;
      RtlReleaseResource(&UpcallServerResource);
      v1 = 183;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 21, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids);
      }
    }
    RtlDeleteResource(&UpcallServerResource);
    result = v1;
    UpcallServerResourceInitialized = 0;
  }
  else
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 20, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000dc4c  mov     [rsp+arg_8], rbx
0x18000dc51  push    rdi
0x18000dc52  sub     rsp, 20h
0x18000dc56  cmp     cs:UpcallServerResourceInitialized, 0
0x18000dc5d  mov     [rsp+28h+BindingVector], 0
0x18000dc66  jnz     short loc_18000DCA3
0x18000dc68  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000dc6f  lea     rbx, WPP_witness_GLOBAL_Control
0x18000dc76  cmp     rcx, rbx
0x18000dc79  jz      short loc_18000DC9C
0x18000dc7b  test    byte ptr [rcx+1Ch], 1
0x18000dc7f  jz      short loc_18000DC9C
0x18000dc81  cmp     byte ptr [rcx+19h], 3
0x18000dc85  jb      short loc_18000DC9C
0x18000dc87  mov     rcx, [rcx+10h]
0x18000dc8b  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000dc92  mov     edx, 14h
0x18000dc97  call    WPP_SF_
0x18000dc9c  xor     eax, eax
0x18000dc9e  jmp     loc_18000DE2F
0x18000dca3  mov     dl, 1; Wait
0x18000dca5  lea     rcx, UpcallServerResource; Resource
0x18000dcac  call    cs:__imp_RtlAcquireResourceExclusive
0x18000dcb3  nop     dword ptr [rax+rax+00h]
0x18000dcb8  cmp     cs:UpcallServerState, 1
0x18000dcbf  jz      short loc_18000DD28
0x18000dcc1  lea     rcx, UpcallServerResource; Resource
0x18000dcc8  mov     cs:UpcallServerState, 2
0x18000dcd2  call    cs:__imp_RtlReleaseResource
0x18000dcd9  nop     dword ptr [rax+rax+00h]
0x18000dcde  mov     edi, 0B7h
0x18000dce3  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000dcea  lea     rbx, WPP_witness_GLOBAL_Control
0x18000dcf1  cmp     rcx, rbx
0x18000dcf4  jz      loc_18000DE10
0x18000dcfa  test    byte ptr [rcx+1Ch], 1
0x18000dcfe  jz      loc_18000DE10
0x18000dd04  cmp     byte ptr [rcx+19h], 1
0x18000dd08  jb      loc_18000DE10
0x18000dd0e  mov     rcx, [rcx+10h]
0x18000dd12  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000dd19  mov     edx, 15h
0x18000dd1e  call    WPP_SF_
0x18000dd23  jmp     loc_18000DE10
0x18000dd28  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000dd2d  call    cs:__imp_RpcServerInqBindings
0x18000dd34  nop     dword ptr [rax+rax+00h]
0x18000dd39  lea     rbx, WPP_witness_GLOBAL_Control
0x18000dd40  test    eax, eax
0x18000dd42  jnz     short loc_18000DDA4
0x18000dd44  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x18000dd49  lea     rcx, qword_1800380C0; IfSpec
0x18000dd50  xor     r8d, r8d; UuidVector
0x18000dd53  call    cs:__imp_RpcEpUnregister
0x18000dd5a  nop     dword ptr [rax+rax+00h]
0x18000dd5f  test    eax, eax
0x18000dd61  jz      short loc_18000DD93
0x18000dd63  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000dd6a  cmp     rcx, rbx
0x18000dd6d  jz      short loc_18000DD93
0x18000dd6f  test    byte ptr [rcx+1Ch], 1
0x18000dd73  jz      short loc_18000DD93
0x18000dd75  cmp     byte ptr [rcx+19h], 3
0x18000dd79  jb      short loc_18000DD93
0x18000dd7b  mov     rcx, [rcx+10h]
0x18000dd7f  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000dd86  mov     edx, 16h
0x18000dd8b  mov     r9d, eax
0x18000dd8e  call    WPP_SF_d
0x18000dd93  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000dd98  call    cs:__imp_RpcBindingVectorFree
0x18000dd9f  nop     dword ptr [rax+rax+00h]
0x18000dda4  lea     rcx, UpcallServerResource; Resource
0x18000ddab  mov     cs:UpcallServerState, 2
0x18000ddb5  call    cs:__imp_RtlReleaseResource
0x18000ddbc  nop     dword ptr [rax+rax+00h]
0x18000ddc1  xor     edx, edx; MgrTypeUuid
0x18000ddc3  lea     rcx, qword_1800380C0; IfSpec
0x18000ddca  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000ddce  call    cs:__imp_RpcServerUnregisterIf
0x18000ddd5  nop     dword ptr [rax+rax+00h]
0x18000ddda  mov     edi, eax
0x18000dddc  test    eax, eax
0x18000ddde  jz      short loc_18000DE10
0x18000dde0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000dde7  cmp     rcx, rbx
0x18000ddea  jz      short loc_18000DE10
0x18000ddec  test    byte ptr [rcx+1Ch], 1
0x18000ddf0  jz      short loc_18000DE10
0x18000ddf2  cmp     byte ptr [rcx+19h], 1
0x18000ddf6  jb      short loc_18000DE10
0x18000ddf8  mov     rcx, [rcx+10h]
0x18000ddfc  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000de03  mov     edx, 17h
0x18000de08  mov     r9d, eax
0x18000de0b  call    WPP_SF_d
0x18000de10  lea     rcx, UpcallServerResource; Resource
0x18000de17  call    cs:__imp_RtlDeleteResource
0x18000de1e  nop     dword ptr [rax+rax+00h]
0x18000de23  mov     eax, edi
0x18000de25  mov     cs:UpcallServerResourceInitialized, 0
0x18000de2f  mov     rbx, [rsp+28h+arg_8]
0x18000de34  add     rsp, 20h
0x18000de38  pop     rdi
0x18000de39  retn
```
