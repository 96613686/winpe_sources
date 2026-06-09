# WSP_ReplicationGroup_Invoke_CreateReplica

- ea: `0x180003cc0`
- end: `0x180003d81`
- name: `WSP_ReplicationGroup_Invoke_CreateReplica`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800039a4`
- `0x180003cc0`
- `0x18000950c`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180003d13`
- `MISpace!WspIsRemoteInstance` at `0x180003d13`
- `MISpace!WspInvokeRemoteMethod` at `0x180003d3f`
- `MISpace!WspInvokeRemoteMethod` at `0x180003d3f`
- `MISpace!WspProviderEnter` at `0x180003cf3`
- `MISpace!WspProviderEnter` at `0x180003cf3`
- `MISpace!WspProviderExit` at `0x180003d64`
- `MISpace!WspProviderExit` at `0x180003d64`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_CreateReplica(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_ReplicationGroup_CreateReplica *a7)
{
  MI_Result v9; // eax
  _DWORD v11[6]; // [rsp+30h] [rbp-18h] BYREF

  v11[0] = 0;
  v9 = (unsigned int)WspProviderEnter(a2, a6[4].value, 1, v11);
  if ( v9 == MI_RESULT_OK )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(a6[4].value) )
    {
      SrSmapiCreateReplica(a6, a7, a2);
      return WspProviderExit(v11[0]);
    }
    v9 = (unsigned int)WspInvokeRemoteMethod(a2, a4, a6[4].value, a5, a7);
  }
  MI_Context_PostResult_0(a2, v9);
  return WspProviderExit(v11[0]);
}

```

## disassembly

```asm
0x180003cc0  mov     rax, rsp
0x180003cc3  mov     [rax+8], rbx
0x180003cc7  mov     [rax+10h], rsi
0x180003ccb  push    rdi
0x180003ccc  sub     rsp, 40h
0x180003cd0  mov     rdi, [rsp+48h+arg_28]
0x180003cd5  mov     rbx, rdx
0x180003cd8  mov     rsi, r9
0x180003cdb  mov     dword ptr [rax-18h], 0
0x180003ce2  lea     r9, [rax-18h]
0x180003ce6  mov     r8d, 1
0x180003cec  mov     rcx, rbx
0x180003cef  mov     rdx, [rdi+40h]
0x180003cf3  call    cs:__imp_WspProviderEnter
0x180003cfa  nop     dword ptr [rax+rax+00h]
0x180003cff  test    eax, eax
0x180003d01  jz      short loc_180003D0F
0x180003d03  mov     edx, eax; result
0x180003d05  mov     rcx, rbx; context
0x180003d08  call    MI_Context_PostResult_0
0x180003d0d  jmp     short loc_180003D60
0x180003d0f  mov     rcx, [rdi+40h]
0x180003d13  call    cs:__imp_WspIsRemoteInstance
0x180003d1a  nop     dword ptr [rax+rax+00h]
0x180003d1f  test    al, al
0x180003d21  jz      short loc_180003D4D
0x180003d23  mov     rax, [rsp+48h+arg_30]
0x180003d2b  mov     rdx, rsi
0x180003d2e  mov     r9, [rsp+48h+arg_20]
0x180003d33  mov     rcx, rbx
0x180003d36  mov     r8, [rdi+40h]
0x180003d3a  mov     [rsp+48h+var_28], rax
0x180003d3f  call    cs:__imp_WspInvokeRemoteMethod
0x180003d46  nop     dword ptr [rax+rax+00h]
0x180003d4b  jmp     short loc_180003D03
0x180003d4d  mov     rdx, [rsp+48h+arg_30]; struct _WSP_ReplicationGroup_CreateReplica *
0x180003d55  mov     r8, rbx; struct _MI_Context *
0x180003d58  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x180003d5b  call    ?SrSmapiCreateReplica@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_CreateReplica@@PEAU_MI_Context@@@Z; SrSmapiCreateReplica(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_CreateReplica const *,_MI_Context *)
0x180003d60  mov     ecx, [rsp+48h+var_18]
0x180003d64  call    cs:__imp_WspProviderExit
0x180003d6b  nop     dword ptr [rax+rax+00h]
0x180003d70  mov     rbx, [rsp+48h+arg_0]
0x180003d75  mov     rsi, [rsp+48h+arg_8]
0x180003d7a  add     rsp, 40h
0x180003d7e  pop     rdi
0x180003d7f  retn
```
