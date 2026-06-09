# WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates

- ea: `0x1800044d0`
- end: `0x18000457c`
- name: `WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800044d0`
- `0x18001056c`
- `0x18002d010`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x18000452d`
- `MISpace!WspIsRemoteInstance` at `0x18000452d`
- `MISpace!WspInvokeRemoteMethod` at `0x180004553`
- `MISpace!WspInvokeRemoteMethod` at `0x180004553`
- `MISpace!WspProviderEnter` at `0x180004503`
- `MISpace!WspProviderEnter` at `0x180004503`
- `MISpace!WspProviderExit` at `0x180004566`
- `MISpace!WspProviderExit` at `0x180004566`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationCapabilities_Invoke_GetSupportedGroupCopyStates(
        __int64 a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v9; // eax
  __int64 v10; // rdx
  _DWORD v12[6]; // [rsp+30h] [rbp-18h] BYREF

  v12[0] = 0;
  v9 = WspProviderEnter(a2, *(_QWORD *)(a6 + 64), 1, v12);
  v10 = v9;
  if ( !v9 )
  {
    if ( !(unsigned __int8)WspIsRemoteInstance(*(_QWORD *)(a6 + 64), 0) )
    {
      SrSmapiGetSupportedGroupCopyStates(a2);
      return WspProviderExit(v12[0], v10);
    }
    v10 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(_QWORD *)(a6 + 64), a5, a7);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, __int64))a2->ft->PostResult)(a2, v10);
  return WspProviderExit(v12[0], v10);
}

```

## disassembly

```asm
0x1800044d0  mov     rax, rsp
0x1800044d3  mov     [rax+8], rbx
0x1800044d7  mov     [rax+10h], rsi
0x1800044db  push    rdi
0x1800044dc  sub     rsp, 40h
0x1800044e0  mov     rdi, [rsp+48h+arg_28]
0x1800044e5  mov     rbx, rdx
0x1800044e8  mov     rsi, r9
0x1800044eb  mov     dword ptr [rax-18h], 0
0x1800044f2  lea     r9, [rax-18h]
0x1800044f6  mov     r8d, 1
0x1800044fc  mov     rcx, rbx
0x1800044ff  mov     rdx, [rdi+40h]
0x180004503  call    cs:__imp_WspProviderEnter
0x180004509  mov     edx, eax
0x18000450b  test    eax, eax
0x18000450d  jz      short loc_180004529
0x18000450f  test    rbx, rbx
0x180004512  jz      short loc_180004562
0x180004514  mov     rax, [rbx]
0x180004517  test    rax, rax
0x18000451a  jz      short loc_180004562
0x18000451c  mov     rax, [rax]
0x18000451f  mov     rcx, rbx
0x180004522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004527  jmp     short loc_180004562
0x180004529  mov     rcx, [rdi+40h]
0x18000452d  call    cs:__imp_WspIsRemoteInstance
0x180004533  mov     rcx, rbx; struct _MI_Context *
0x180004536  test    al, al
0x180004538  jz      short loc_18000455D
0x18000453a  mov     rax, [rsp+48h+arg_30]
0x180004542  mov     rdx, rsi
0x180004545  mov     r9, [rsp+48h+arg_20]
0x18000454a  mov     r8, [rdi+40h]
0x18000454e  mov     [rsp+48h+var_28], rax
0x180004553  call    cs:__imp_WspInvokeRemoteMethod
0x180004559  mov     edx, eax
0x18000455b  jmp     short loc_18000450F
0x18000455d  call    ?SrSmapiGetSupportedGroupCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z; SrSmapiGetSupportedGroupCopyStates(_MI_Context *)
0x180004562  mov     ecx, [rsp+48h+var_18]
0x180004566  call    cs:__imp_WspProviderExit
0x18000456c  mov     rbx, [rsp+48h+arg_0]
0x180004571  mov     rsi, [rsp+48h+arg_8]
0x180004576  add     rsp, 40h
0x18000457a  pop     rdi
0x18000457b  retn
```
