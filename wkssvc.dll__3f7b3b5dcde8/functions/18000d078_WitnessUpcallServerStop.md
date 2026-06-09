# WitnessUpcallServerStop

- ea: `0x18000d078`
- end: `0x18000d236`
- name: `WitnessUpcallServerStop`
- size: `446`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ce80`

## callees

- `0x18000d078`
- `0x180022b54`
- `0x180022b7c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000d0d8`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000d0d8`
- `ntdll!RtlReleaseResource` at `0x18000d0f8`
- `ntdll!RtlReleaseResource` at `0x18000d1c3`
- `ntdll!RtlReleaseResource` at `0x18000d0f8`
- `ntdll!RtlReleaseResource` at `0x18000d1c3`
- `ntdll!RtlDeleteResource` at `0x18000d219`
- `ntdll!RtlDeleteResource` at `0x18000d219`
- `RPCRT4!RpcEpUnregister` at `0x18000d16d`
- `RPCRT4!RpcEpUnregister` at `0x18000d16d`
- `RPCRT4!RpcServerInqBindings` at `0x18000d14d`
- `RPCRT4!RpcServerInqBindings` at `0x18000d14d`
- `RPCRT4!RpcBindingVectorFree` at `0x18000d1ac`
- `RPCRT4!RpcBindingVectorFree` at `0x18000d1ac`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000d1d6`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000d1d6`

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
        v2 = RpcEpUnregister(qword_1800350C0, BindingVector, 0);
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
      v3 = RpcServerUnregisterIf(qword_1800350C0, 0, 1u);
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
0x18000d078  mov     [rsp+arg_8], rbx
0x18000d07d  push    rdi
0x18000d07e  sub     rsp, 20h
0x18000d082  cmp     cs:UpcallServerResourceInitialized, 0
0x18000d089  mov     [rsp+28h+BindingVector], 0
0x18000d092  jnz     short loc_18000D0CF
0x18000d094  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d09b  lea     rbx, WPP_witness_GLOBAL_Control
0x18000d0a2  cmp     rcx, rbx
0x18000d0a5  jz      short loc_18000D0C8
0x18000d0a7  test    byte ptr [rcx+1Ch], 1
0x18000d0ab  jz      short loc_18000D0C8
0x18000d0ad  cmp     byte ptr [rcx+19h], 3
0x18000d0b1  jb      short loc_18000D0C8
0x18000d0b3  mov     rcx, [rcx+10h]
0x18000d0b7  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000d0be  mov     edx, 14h
0x18000d0c3  call    WPP_SF_
0x18000d0c8  xor     eax, eax
0x18000d0ca  jmp     loc_18000D22B
0x18000d0cf  mov     dl, 1; Wait
0x18000d0d1  lea     rcx, UpcallServerResource; Resource
0x18000d0d8  call    cs:__imp_RtlAcquireResourceExclusive
0x18000d0de  cmp     cs:UpcallServerState, 1
0x18000d0e5  jz      short loc_18000D148
0x18000d0e7  lea     rcx, UpcallServerResource; Resource
0x18000d0ee  mov     cs:UpcallServerState, 2
0x18000d0f8  call    cs:__imp_RtlReleaseResource
0x18000d0fe  mov     edi, 0B7h
0x18000d103  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d10a  lea     rbx, WPP_witness_GLOBAL_Control
0x18000d111  cmp     rcx, rbx
0x18000d114  jz      loc_18000D212
0x18000d11a  test    byte ptr [rcx+1Ch], 1
0x18000d11e  jz      loc_18000D212
0x18000d124  cmp     byte ptr [rcx+19h], 1
0x18000d128  jb      loc_18000D212
0x18000d12e  mov     rcx, [rcx+10h]
0x18000d132  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000d139  mov     edx, 15h
0x18000d13e  call    WPP_SF_
0x18000d143  jmp     loc_18000D212
0x18000d148  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000d14d  call    cs:__imp_RpcServerInqBindings
0x18000d153  lea     rbx, WPP_witness_GLOBAL_Control
0x18000d15a  test    eax, eax
0x18000d15c  jnz     short loc_18000D1B2
0x18000d15e  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x18000d163  lea     rcx, qword_1800350C0; IfSpec
0x18000d16a  xor     r8d, r8d; UuidVector
0x18000d16d  call    cs:__imp_RpcEpUnregister
0x18000d173  test    eax, eax
0x18000d175  jz      short loc_18000D1A7
0x18000d177  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d17e  cmp     rcx, rbx
0x18000d181  jz      short loc_18000D1A7
0x18000d183  test    byte ptr [rcx+1Ch], 1
0x18000d187  jz      short loc_18000D1A7
0x18000d189  cmp     byte ptr [rcx+19h], 3
0x18000d18d  jb      short loc_18000D1A7
0x18000d18f  mov     rcx, [rcx+10h]
0x18000d193  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000d19a  mov     edx, 16h
0x18000d19f  mov     r9d, eax
0x18000d1a2  call    WPP_SF_d
0x18000d1a7  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000d1ac  call    cs:__imp_RpcBindingVectorFree
0x18000d1b2  lea     rcx, UpcallServerResource; Resource
0x18000d1b9  mov     cs:UpcallServerState, 2
0x18000d1c3  call    cs:__imp_RtlReleaseResource
0x18000d1c9  xor     edx, edx; MgrTypeUuid
0x18000d1cb  lea     rcx, qword_1800350C0; IfSpec
0x18000d1d2  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000d1d6  call    cs:__imp_RpcServerUnregisterIf
0x18000d1dc  mov     edi, eax
0x18000d1de  test    eax, eax
0x18000d1e0  jz      short loc_18000D212
0x18000d1e2  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000d1e9  cmp     rcx, rbx
0x18000d1ec  jz      short loc_18000D212
0x18000d1ee  test    byte ptr [rcx+1Ch], 1
0x18000d1f2  jz      short loc_18000D212
0x18000d1f4  cmp     byte ptr [rcx+19h], 1
0x18000d1f8  jb      short loc_18000D212
0x18000d1fa  mov     rcx, [rcx+10h]
0x18000d1fe  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000d205  mov     edx, 17h
0x18000d20a  mov     r9d, eax
0x18000d20d  call    WPP_SF_d
0x18000d212  lea     rcx, UpcallServerResource; Resource
0x18000d219  call    cs:__imp_RtlDeleteResource
0x18000d21f  mov     eax, edi
0x18000d221  mov     cs:UpcallServerResourceInitialized, 0
0x18000d22b  mov     rbx, [rsp+28h+arg_8]
0x18000d230  add     rsp, 20h
0x18000d234  pop     rdi
0x18000d235  retn
```
