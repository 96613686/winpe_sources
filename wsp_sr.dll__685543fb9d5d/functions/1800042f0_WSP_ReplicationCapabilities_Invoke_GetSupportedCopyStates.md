# WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates

- ea: `0x1800042f0`
- end: `0x1800043a3`
- name: `WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800039a4`
- `0x1800042f0`
- `0x1800100a8`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180004343`
- `MISpace!WspIsRemoteInstance` at `0x180004343`
- `MISpace!WspInvokeRemoteMethod` at `0x18000436f`
- `MISpace!WspInvokeRemoteMethod` at `0x18000436f`
- `MISpace!WspProviderEnter` at `0x180004323`
- `MISpace!WspProviderEnter` at `0x180004323`
- `MISpace!WspProviderExit` at `0x180004386`
- `MISpace!WspProviderExit` at `0x180004386`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  MI_Result v9; // eax
  _DWORD v11[6]; // [rsp+30h] [rbp-18h] BYREF

  v11[0] = 0;
  v9 = (unsigned int)WspProviderEnter(a2, *(_QWORD *)(a6 + 64), 1, v11);
  if ( v9 == MI_RESULT_OK )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(*(_QWORD *)(a6 + 64)) )
    {
      SrSmapiGetSupportedCopyStates(a2);
      return WspProviderExit(v11[0]);
    }
    v9 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(_QWORD *)(a6 + 64), a5, a7);
  }
  MI_Context_PostResult_0(a2, v9);
  return WspProviderExit(v11[0]);
}

```

## disassembly

```asm
0x1800042f0  mov     rax, rsp
0x1800042f3  mov     [rax+8], rbx
0x1800042f7  mov     [rax+10h], rsi
0x1800042fb  push    rdi
0x1800042fc  sub     rsp, 40h
0x180004300  mov     rdi, [rsp+48h+arg_28]
0x180004305  mov     rbx, rdx
0x180004308  mov     rsi, r9
0x18000430b  mov     dword ptr [rax-18h], 0
0x180004312  lea     r9, [rax-18h]
0x180004316  mov     r8d, 1
0x18000431c  mov     rcx, rbx
0x18000431f  mov     rdx, [rdi+40h]
0x180004323  call    cs:__imp_WspProviderEnter
0x18000432a  nop     dword ptr [rax+rax+00h]
0x18000432f  test    eax, eax
0x180004331  jz      short loc_18000433F
0x180004333  mov     edx, eax; result
0x180004335  mov     rcx, rbx; context
0x180004338  call    MI_Context_PostResult_0
0x18000433d  jmp     short loc_180004382
0x18000433f  mov     rcx, [rdi+40h]
0x180004343  call    cs:__imp_WspIsRemoteInstance
0x18000434a  nop     dword ptr [rax+rax+00h]
0x18000434f  mov     rcx, rbx; struct _MI_Context *
0x180004352  test    al, al
0x180004354  jz      short loc_18000437D
0x180004356  mov     rax, [rsp+48h+arg_30]
0x18000435e  mov     rdx, rsi
0x180004361  mov     r9, [rsp+48h+arg_20]
0x180004366  mov     r8, [rdi+40h]
0x18000436a  mov     [rsp+48h+var_28], rax
0x18000436f  call    cs:__imp_WspInvokeRemoteMethod
0x180004376  nop     dword ptr [rax+rax+00h]
0x18000437b  jmp     short loc_180004333
0x18000437d  call    ?SrSmapiGetSupportedCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z; SrSmapiGetSupportedCopyStates(_MI_Context *)
0x180004382  mov     ecx, [rsp+48h+var_18]
0x180004386  call    cs:__imp_WspProviderExit
0x18000438d  nop     dword ptr [rax+rax+00h]
0x180004392  mov     rbx, [rsp+48h+arg_0]
0x180004397  mov     rsi, [rsp+48h+arg_8]
0x18000439c  add     rsp, 40h
0x1800043a0  pop     rdi
0x1800043a1  retn
```
