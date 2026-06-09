# WSP_ReplicationGroup_Invoke_RemoveMember

- ea: `0x180003fd0`
- end: `0x18000408a`
- name: `WSP_ReplicationGroup_Invoke_RemoveMember`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003fd0`
- `0x18000bec0`
- `0x18002d010`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x18000402d`
- `MISpace!WspIsRemoteInstance` at `0x18000402d`
- `MISpace!WspInvokeRemoteMethod` at `0x180004053`
- `MISpace!WspInvokeRemoteMethod` at `0x180004053`
- `MISpace!WspProviderEnter` at `0x180004003`
- `MISpace!WspProviderEnter` at `0x180004003`
- `MISpace!WspProviderExit` at `0x180004074`
- `MISpace!WspProviderExit` at `0x180004074`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_RemoveMember(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_ReplicationGroup_RemoveMember *a7)
{
  unsigned int v9; // eax
  __int64 v10; // rdx
  _DWORD v12[6]; // [rsp+30h] [rbp-18h] BYREF

  v12[0] = 0;
  v9 = WspProviderEnter(a2, a6[4].value, 1, v12);
  v10 = v9;
  if ( !v9 )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(a6[4].value, 0) )
    {
      SrSmapiRemoveMember(a6, a7, a2);
      return WspProviderExit(v12[0], v10);
    }
    v10 = (unsigned int)WspInvokeRemoteMethod(a2, a4, a6[4].value, a5, a7);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, __int64))a2->ft->PostResult)(a2, v10);
  return WspProviderExit(v12[0], v10);
}

```

## disassembly

```asm
0x180003fd0  mov     rax, rsp
0x180003fd3  mov     [rax+8], rbx
0x180003fd7  mov     [rax+10h], rsi
0x180003fdb  push    rdi
0x180003fdc  sub     rsp, 40h
0x180003fe0  mov     rdi, [rsp+48h+arg_28]
0x180003fe5  mov     rbx, rdx
0x180003fe8  mov     rsi, r9
0x180003feb  mov     dword ptr [rax-18h], 0
0x180003ff2  lea     r9, [rax-18h]
0x180003ff6  mov     r8d, 1
0x180003ffc  mov     rcx, rbx
0x180003fff  mov     rdx, [rdi+40h]
0x180004003  call    cs:__imp_WspProviderEnter
0x180004009  mov     edx, eax
0x18000400b  test    eax, eax
0x18000400d  jz      short loc_180004029
0x18000400f  test    rbx, rbx
0x180004012  jz      short loc_180004070
0x180004014  mov     rax, [rbx]
0x180004017  test    rax, rax
0x18000401a  jz      short loc_180004070
0x18000401c  mov     rax, [rax]
0x18000401f  mov     rcx, rbx
0x180004022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004027  jmp     short loc_180004070
0x180004029  mov     rcx, [rdi+40h]
0x18000402d  call    cs:__imp_WspIsRemoteInstance
0x180004033  test    al, al
0x180004035  jz      short loc_18000405D
0x180004037  mov     rax, [rsp+48h+arg_30]
0x18000403f  mov     rdx, rsi
0x180004042  mov     r9, [rsp+48h+arg_20]
0x180004047  mov     rcx, rbx
0x18000404a  mov     r8, [rdi+40h]
0x18000404e  mov     [rsp+48h+var_28], rax
0x180004053  call    cs:__imp_WspInvokeRemoteMethod
0x180004059  mov     edx, eax
0x18000405b  jmp     short loc_18000400F
0x18000405d  mov     rdx, [rsp+48h+arg_30]; struct _WSP_ReplicationGroup_RemoveMember *
0x180004065  mov     r8, rbx; struct _MI_Context *
0x180004068  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x18000406b  call    ?SrSmapiRemoveMember@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_RemoveMember@@PEAU_MI_Context@@@Z; SrSmapiRemoveMember(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_RemoveMember const *,_MI_Context *)
0x180004070  mov     ecx, [rsp+48h+var_18]
0x180004074  call    cs:__imp_WspProviderExit
0x18000407a  mov     rbx, [rsp+48h+arg_0]
0x18000407f  mov     rsi, [rsp+48h+arg_8]
0x180004084  add     rsp, 40h
0x180004088  pop     rdi
0x180004089  retn
```
