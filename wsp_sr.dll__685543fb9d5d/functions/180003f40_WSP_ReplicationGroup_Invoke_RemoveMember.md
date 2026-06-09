# WSP_ReplicationGroup_Invoke_RemoveMember

- ea: `0x180003f40`
- end: `0x180004001`
- name: `WSP_ReplicationGroup_Invoke_RemoveMember`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800039a4`
- `0x180003f40`
- `0x18000bf54`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180003f93`
- `MISpace!WspIsRemoteInstance` at `0x180003f93`
- `MISpace!WspInvokeRemoteMethod` at `0x180003fbf`
- `MISpace!WspInvokeRemoteMethod` at `0x180003fbf`
- `MISpace!WspProviderEnter` at `0x180003f73`
- `MISpace!WspProviderEnter` at `0x180003f73`
- `MISpace!WspProviderExit` at `0x180003fe4`
- `MISpace!WspProviderExit` at `0x180003fe4`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_RemoveMember(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_ReplicationGroup_RemoveMember *a7)
{
  MI_Result v9; // eax
  _DWORD v11[6]; // [rsp+30h] [rbp-18h] BYREF

  v11[0] = 0;
  v9 = (unsigned int)WspProviderEnter(a2, a6[4].value, 1, v11);
  if ( v9 == MI_RESULT_OK )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(a6[4].value) )
    {
      SrSmapiRemoveMember(a6, a7, a2);
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
0x180003f40  mov     rax, rsp
0x180003f43  mov     [rax+8], rbx
0x180003f47  mov     [rax+10h], rsi
0x180003f4b  push    rdi
0x180003f4c  sub     rsp, 40h
0x180003f50  mov     rdi, [rsp+48h+arg_28]
0x180003f55  mov     rbx, rdx
0x180003f58  mov     rsi, r9
0x180003f5b  mov     dword ptr [rax-18h], 0
0x180003f62  lea     r9, [rax-18h]
0x180003f66  mov     r8d, 1
0x180003f6c  mov     rcx, rbx
0x180003f6f  mov     rdx, [rdi+40h]
0x180003f73  call    cs:__imp_WspProviderEnter
0x180003f7a  nop     dword ptr [rax+rax+00h]
0x180003f7f  test    eax, eax
0x180003f81  jz      short loc_180003F8F
0x180003f83  mov     edx, eax; result
0x180003f85  mov     rcx, rbx; context
0x180003f88  call    MI_Context_PostResult_0
0x180003f8d  jmp     short loc_180003FE0
0x180003f8f  mov     rcx, [rdi+40h]
0x180003f93  call    cs:__imp_WspIsRemoteInstance
0x180003f9a  nop     dword ptr [rax+rax+00h]
0x180003f9f  test    al, al
0x180003fa1  jz      short loc_180003FCD
0x180003fa3  mov     rax, [rsp+48h+arg_30]
0x180003fab  mov     rdx, rsi
0x180003fae  mov     r9, [rsp+48h+arg_20]
0x180003fb3  mov     rcx, rbx
0x180003fb6  mov     r8, [rdi+40h]
0x180003fba  mov     [rsp+48h+var_28], rax
0x180003fbf  call    cs:__imp_WspInvokeRemoteMethod
0x180003fc6  nop     dword ptr [rax+rax+00h]
0x180003fcb  jmp     short loc_180003F83
0x180003fcd  mov     rdx, [rsp+48h+arg_30]; struct _WSP_ReplicationGroup_RemoveMember *
0x180003fd5  mov     r8, rbx; struct _MI_Context *
0x180003fd8  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x180003fdb  call    ?SrSmapiRemoveMember@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_RemoveMember@@PEAU_MI_Context@@@Z; SrSmapiRemoveMember(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_RemoveMember const *,_MI_Context *)
0x180003fe0  mov     ecx, [rsp+48h+var_18]
0x180003fe4  call    cs:__imp_WspProviderExit
0x180003feb  nop     dword ptr [rax+rax+00h]
0x180003ff0  mov     rbx, [rsp+48h+arg_0]
0x180003ff5  mov     rsi, [rsp+48h+arg_8]
0x180003ffa  add     rsp, 40h
0x180003ffe  pop     rdi
0x180003fff  retn
```
