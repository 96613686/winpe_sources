# WSP_ReplicationGroup_Invoke_CreateReplica

- ea: `0x180003d60`
- end: `0x180003e1a`
- name: `WSP_ReplicationGroup_Invoke_CreateReplica`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003d60`
- `0x18000934c`
- `0x18002d010`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180003dbd`
- `MISpace!WspIsRemoteInstance` at `0x180003dbd`
- `MISpace!WspInvokeRemoteMethod` at `0x180003de3`
- `MISpace!WspInvokeRemoteMethod` at `0x180003de3`
- `MISpace!WspProviderEnter` at `0x180003d93`
- `MISpace!WspProviderEnter` at `0x180003d93`
- `MISpace!WspProviderExit` at `0x180003e04`
- `MISpace!WspProviderExit` at `0x180003e04`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_CreateReplica(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_ReplicationGroup_CreateReplica *a7)
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
      SrSmapiCreateReplica(a6, a7, a2);
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
0x180003d60  mov     rax, rsp
0x180003d63  mov     [rax+8], rbx
0x180003d67  mov     [rax+10h], rsi
0x180003d6b  push    rdi
0x180003d6c  sub     rsp, 40h
0x180003d70  mov     rdi, [rsp+48h+arg_28]
0x180003d75  mov     rbx, rdx
0x180003d78  mov     rsi, r9
0x180003d7b  mov     dword ptr [rax-18h], 0
0x180003d82  lea     r9, [rax-18h]
0x180003d86  mov     r8d, 1
0x180003d8c  mov     rcx, rbx
0x180003d8f  mov     rdx, [rdi+40h]
0x180003d93  call    cs:__imp_WspProviderEnter
0x180003d99  mov     edx, eax
0x180003d9b  test    eax, eax
0x180003d9d  jz      short loc_180003DB9
0x180003d9f  test    rbx, rbx
0x180003da2  jz      short loc_180003E00
0x180003da4  mov     rax, [rbx]
0x180003da7  test    rax, rax
0x180003daa  jz      short loc_180003E00
0x180003dac  mov     rax, [rax]
0x180003daf  mov     rcx, rbx
0x180003db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db7  jmp     short loc_180003E00
0x180003db9  mov     rcx, [rdi+40h]
0x180003dbd  call    cs:__imp_WspIsRemoteInstance
0x180003dc3  test    al, al
0x180003dc5  jz      short loc_180003DED
0x180003dc7  mov     rax, [rsp+48h+arg_30]
0x180003dcf  mov     rdx, rsi
0x180003dd2  mov     r9, [rsp+48h+arg_20]
0x180003dd7  mov     rcx, rbx
0x180003dda  mov     r8, [rdi+40h]
0x180003dde  mov     [rsp+48h+var_28], rax
0x180003de3  call    cs:__imp_WspInvokeRemoteMethod
0x180003de9  mov     edx, eax
0x180003deb  jmp     short loc_180003D9F
0x180003ded  mov     rdx, [rsp+48h+arg_30]; struct _WSP_ReplicationGroup_CreateReplica *
0x180003df5  mov     r8, rbx; struct _MI_Context *
0x180003df8  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x180003dfb  call    ?SrSmapiCreateReplica@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEBU_WSP_ReplicationGroup_CreateReplica@@PEAU_MI_Context@@@Z; SrSmapiCreateReplica(_WSP_ReplicationGroup const *,_WSP_ReplicationGroup_CreateReplica const *,_MI_Context *)
0x180003e00  mov     ecx, [rsp+48h+var_18]
0x180003e04  call    cs:__imp_WspProviderExit
0x180003e0a  mov     rbx, [rsp+48h+arg_0]
0x180003e0f  mov     rsi, [rsp+48h+arg_8]
0x180003e14  add     rsp, 40h
0x180003e18  pop     rdi
0x180003e19  retn
```
