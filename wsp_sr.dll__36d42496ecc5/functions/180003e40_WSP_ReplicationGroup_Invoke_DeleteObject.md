# WSP_ReplicationGroup_Invoke_DeleteObject

- ea: `0x180003e40`
- end: `0x180003ef2`
- name: `WSP_ReplicationGroup_Invoke_DeleteObject`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003e40`
- `0x180009844`
- `0x18002d010`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x180003e9d`
- `MISpace!WspIsRemoteInstance` at `0x180003e9d`
- `MISpace!WspInvokeRemoteMethod` at `0x180003ec3`
- `MISpace!WspInvokeRemoteMethod` at `0x180003ec3`
- `MISpace!WspProviderEnter` at `0x180003e73`
- `MISpace!WspProviderEnter` at `0x180003e73`
- `MISpace!WspProviderExit` at `0x180003edc`
- `MISpace!WspProviderExit` at `0x180003edc`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationGroup_Invoke_DeleteObject(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
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
      SrSmapiDeleteReplicationGroup(a6, a2);
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
0x180003e40  mov     rax, rsp
0x180003e43  mov     [rax+8], rbx
0x180003e47  mov     [rax+10h], rsi
0x180003e4b  push    rdi
0x180003e4c  sub     rsp, 40h
0x180003e50  mov     rdi, [rsp+48h+arg_28]
0x180003e55  mov     rbx, rdx
0x180003e58  mov     rsi, r9
0x180003e5b  mov     dword ptr [rax-18h], 0
0x180003e62  lea     r9, [rax-18h]
0x180003e66  mov     r8d, 1
0x180003e6c  mov     rcx, rbx
0x180003e6f  mov     rdx, [rdi+40h]
0x180003e73  call    cs:__imp_WspProviderEnter
0x180003e79  mov     edx, eax
0x180003e7b  test    eax, eax
0x180003e7d  jz      short loc_180003E99
0x180003e7f  test    rbx, rbx
0x180003e82  jz      short loc_180003ED8
0x180003e84  mov     rax, [rbx]
0x180003e87  test    rax, rax
0x180003e8a  jz      short loc_180003ED8
0x180003e8c  mov     rax, [rax]
0x180003e8f  mov     rcx, rbx
0x180003e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e97  jmp     short loc_180003ED8
0x180003e99  mov     rcx, [rdi+40h]
0x180003e9d  call    cs:__imp_WspIsRemoteInstance
0x180003ea3  test    al, al
0x180003ea5  jz      short loc_180003ECD
0x180003ea7  mov     rax, [rsp+48h+arg_30]
0x180003eaf  mov     rdx, rsi
0x180003eb2  mov     r9, [rsp+48h+arg_20]
0x180003eb7  mov     rcx, rbx
0x180003eba  mov     r8, [rdi+40h]
0x180003ebe  mov     [rsp+48h+var_28], rax
0x180003ec3  call    cs:__imp_WspInvokeRemoteMethod
0x180003ec9  mov     edx, eax
0x180003ecb  jmp     short loc_180003E7F
0x180003ecd  mov     rdx, rbx; struct _MI_Context *
0x180003ed0  mov     rcx, rdi; struct _WSP_ReplicationGroup *
0x180003ed3  call    ?SrSmapiDeleteReplicationGroup@@YA?AW4_MI_Result@@PEBU_WSP_ReplicationGroup@@PEAU_MI_Context@@@Z; SrSmapiDeleteReplicationGroup(_WSP_ReplicationGroup const *,_MI_Context *)
0x180003ed8  mov     ecx, [rsp+48h+var_18]
0x180003edc  call    cs:__imp_WspProviderExit
0x180003ee2  mov     rbx, [rsp+48h+arg_0]
0x180003ee7  mov     rsi, [rsp+48h+arg_8]
0x180003eec  add     rsp, 40h
0x180003ef0  pop     rdi
0x180003ef1  retn
```
