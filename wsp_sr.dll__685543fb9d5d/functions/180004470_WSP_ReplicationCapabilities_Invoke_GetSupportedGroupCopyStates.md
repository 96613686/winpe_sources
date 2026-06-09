# WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates

- ea: `0x180004470`
- end: `0x180004523`
- name: `WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800039a4`
- `0x180004470`
- `0x1800104f0`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x1800044c3`
- `MISpace!WspIsRemoteInstance` at `0x1800044c3`
- `MISpace!WspInvokeRemoteMethod` at `0x1800044ef`
- `MISpace!WspInvokeRemoteMethod` at `0x1800044ef`
- `MISpace!WspProviderEnter` at `0x1800044a3`
- `MISpace!WspProviderEnter` at `0x1800044a3`
- `MISpace!WspProviderExit` at `0x180004506`
- `MISpace!WspProviderExit` at `0x180004506`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates(
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
      SrSmapiGetSupportedGroupCopyStates(a2);
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
0x180004470  mov     rax, rsp
0x180004473  mov     [rax+8], rbx
0x180004477  mov     [rax+10h], rsi
0x18000447b  push    rdi
0x18000447c  sub     rsp, 40h
0x180004480  mov     rdi, [rsp+48h+arg_28]
0x180004485  mov     rbx, rdx
0x180004488  mov     rsi, r9
0x18000448b  mov     dword ptr [rax-18h], 0
0x180004492  lea     r9, [rax-18h]
0x180004496  mov     r8d, 1
0x18000449c  mov     rcx, rbx
0x18000449f  mov     rdx, [rdi+40h]
0x1800044a3  call    cs:__imp_WspProviderEnter
0x1800044aa  nop     dword ptr [rax+rax+00h]
0x1800044af  test    eax, eax
0x1800044b1  jz      short loc_1800044BF
0x1800044b3  mov     edx, eax; result
0x1800044b5  mov     rcx, rbx; context
0x1800044b8  call    MI_Context_PostResult_0
0x1800044bd  jmp     short loc_180004502
0x1800044bf  mov     rcx, [rdi+40h]
0x1800044c3  call    cs:__imp_WspIsRemoteInstance
0x1800044ca  nop     dword ptr [rax+rax+00h]
0x1800044cf  mov     rcx, rbx; struct _MI_Context *
0x1800044d2  test    al, al
0x1800044d4  jz      short loc_1800044FD
0x1800044d6  mov     rax, [rsp+48h+arg_30]
0x1800044de  mov     rdx, rsi
0x1800044e1  mov     r9, [rsp+48h+arg_20]
0x1800044e6  mov     r8, [rdi+40h]
0x1800044ea  mov     [rsp+48h+var_28], rax
0x1800044ef  call    cs:__imp_WspInvokeRemoteMethod
0x1800044f6  nop     dword ptr [rax+rax+00h]
0x1800044fb  jmp     short loc_1800044B3
0x1800044fd  call    ?SrSmapiGetSupportedGroupCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z; SrSmapiGetSupportedGroupCopyStates(_MI_Context *)
0x180004502  mov     ecx, [rsp+48h+var_18]
0x180004506  call    cs:__imp_WspProviderExit
0x18000450d  nop     dword ptr [rax+rax+00h]
0x180004512  mov     rbx, [rsp+48h+arg_0]
0x180004517  mov     rsi, [rsp+48h+arg_8]
0x18000451c  add     rsp, 40h
0x180004520  pop     rdi
0x180004521  retn
```
