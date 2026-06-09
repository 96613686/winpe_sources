# WSP_ReplicationGroup_Invoke_DeleteObject

- ea: `0x180003db0`
- end: `0x180003e69`
- name: `WSP_ReplicationGroup_Invoke_DeleteObject`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800039a4`
- `0x180003db0`
- `0x180009994`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180003e03`
- `MISpace!WspIsRemoteInstance` at `0x180003e03`
- `MISpace!WspInvokeRemoteMethod` at `0x180003e2f`
- `MISpace!WspInvokeRemoteMethod` at `0x180003e2f`
- `MISpace!WspProviderEnter` at `0x180003de3`
- `MISpace!WspProviderEnter` at `0x180003de3`
- `MISpace!WspProviderExit` at `0x180003e4c`
- `MISpace!WspProviderExit` at `0x180003e4c`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_DeleteObject(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  MI_Result v9; // eax
  _DWORD v11[6]; // [rsp+30h] [rbp-18h] BYREF

  v11[0] = 0;
  v9 = (unsigned int)WspProviderEnter(a2, a6[4].value, 1, v11);
  if ( v9 == MI_RESULT_OK )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(a6[4].value) )
    {
      SrSmapiDeleteReplicationGroup(a6, a2);
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
0x180003db0  mov     rax, rsp
0x180003db3  mov     [rax+8], rbx
0x180003db7  mov     [rax+10h], rsi
0x180003dbb  push    rdi
0x180003dbc  sub     rsp, 40h
0x180003dc0  mov     rdi, [rsp+48h+arg_28]
0x180003dc5  mov     rbx, rdx
0x180003dc8  mov     rsi, r9
0x180003dcb  mov     dword ptr [rax-18h], 0
0x180003dd2  lea     r9, [rax-18h]
0x180003dd6  mov     r8d, 1
0x180003ddc  mov     rcx, rbx
0x180003ddf  mov     rdx, [rdi+40h]
0x180003de3  call    cs:__imp_WspProviderEnter
0x180003dea  nop     dword ptr [rax+rax+00h]
0x180003def  test    eax, eax
0x180003df1  jz      short loc_180003DFF
0x180003df3  mov     edx, eax; result
0x180003df5  mov     rcx, rbx; context
0x180003df8  call    MI_Context_PostResult_0
0x180003dfd  jmp     short loc_180003E48
0x180003dff  mov     rcx, [rdi+40h]
0x180003e03  call    cs:__imp_WspIsRemoteInstance
0x180003e0a  nop     dword ptr [rax+rax+00h]
0x180003e0f  test    al, al
0x180003e11  jz      short loc_180003E3D
0x180003e13  mov     rax, [rsp+48h+arg_30]
0x180003e1b  mov     rdx, rsi
0x180003e1e  mov     r9, [rsp+48h+arg_20]
0x180003e23  mov     rcx, rbx
0x180003e26  mov     r8, [rdi+40h]
0x180003e2a  mov     [rsp+48h+var_28], rax
0x180003e2f  call    cs:__imp_WspInvokeRemoteMethod
0x180003e36  nop     dword ptr [rax+rax+00h]
0x180003e3b  jmp     short loc_180003DF3
0x180003e3d  mov     rdx, rbx; struct _MI_Context *
0x180003e40  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x180003e43  call    ?SrSmapiDeleteReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEAU_MI_Context@@@Z; SrSmapiDeleteReplicationGroup(_WSP_ReplicationGroup const *,_MI_Context *)
0x180003e48  mov     ecx, [rsp+48h+var_18]
0x180003e4c  call    cs:__imp_WspProviderExit
0x180003e53  nop     dword ptr [rax+rax+00h]
0x180003e58  mov     rbx, [rsp+48h+arg_0]
0x180003e5d  mov     rsi, [rsp+48h+arg_8]
0x180003e62  add     rsp, 40h
0x180003e66  pop     rdi
0x180003e67  retn
```
