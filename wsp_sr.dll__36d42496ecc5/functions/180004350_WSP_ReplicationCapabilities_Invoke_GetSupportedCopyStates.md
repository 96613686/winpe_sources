# WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates

- ea: `0x180004350`
- end: `0x1800043fc`
- name: `WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004350`
- `0x1800100d0`
- `0x18002d010`

## import_xrefs

- `MISpace!WspIsRemoteInstance` at `0x1800043ad`
- `MISpace!WspIsRemoteInstance` at `0x1800043ad`
- `MISpace!WspInvokeRemoteMethod` at `0x1800043d3`
- `MISpace!WspInvokeRemoteMethod` at `0x1800043d3`
- `MISpace!WspProviderEnter` at `0x180004383`
- `MISpace!WspProviderEnter` at `0x180004383`
- `MISpace!WspProviderExit` at `0x1800043e6`
- `MISpace!WspProviderExit` at `0x1800043e6`

## pseudocode

```c
__int64 __fastcall WSP_ReplicationCapabilities_Invoke_GetSupportedCopyStates(
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
      SrSmapiGetSupportedCopyStates(a2);
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
0x180004350  mov     rax, rsp
0x180004353  mov     [rax+8], rbx
0x180004357  mov     [rax+10h], rsi
0x18000435b  push    rdi
0x18000435c  sub     rsp, 40h
0x180004360  mov     rdi, [rsp+48h+arg_28]
0x180004365  mov     rbx, rdx
0x180004368  mov     rsi, r9
0x18000436b  mov     dword ptr [rax-18h], 0
0x180004372  lea     r9, [rax-18h]
0x180004376  mov     r8d, 1
0x18000437c  mov     rcx, rbx
0x18000437f  mov     rdx, [rdi+40h]
0x180004383  call    cs:__imp_WspProviderEnter
0x180004389  mov     edx, eax
0x18000438b  test    eax, eax
0x18000438d  jz      short loc_1800043A9
0x18000438f  test    rbx, rbx
0x180004392  jz      short loc_1800043E2
0x180004394  mov     rax, [rbx]
0x180004397  test    rax, rax
0x18000439a  jz      short loc_1800043E2
0x18000439c  mov     rax, [rax]
0x18000439f  mov     rcx, rbx
0x1800043a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a7  jmp     short loc_1800043E2
0x1800043a9  mov     rcx, [rdi+40h]
0x1800043ad  call    cs:__imp_WspIsRemoteInstance
0x1800043b3  mov     rcx, rbx; struct _MI_Context *
0x1800043b6  test    al, al
0x1800043b8  jz      short loc_1800043DD
0x1800043ba  mov     rax, [rsp+48h+arg_30]
0x1800043c2  mov     rdx, rsi
0x1800043c5  mov     r9, [rsp+48h+arg_20]
0x1800043ca  mov     r8, [rdi+40h]
0x1800043ce  mov     [rsp+48h+var_28], rax
0x1800043d3  call    cs:__imp_WspInvokeRemoteMethod
0x1800043d9  mov     edx, eax
0x1800043db  jmp     short loc_18000438F
0x1800043dd  call    ?SrSmapiGetSupportedCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z; SrSmapiGetSupportedCopyStates(_MI_Context *)
0x1800043e2  mov     ecx, [rsp+48h+var_18]
0x1800043e6  call    cs:__imp_WspProviderExit
0x1800043ec  mov     rbx, [rsp+48h+arg_0]
0x1800043f1  mov     rsi, [rsp+48h+arg_8]
0x1800043f6  add     rsp, 40h
0x1800043fa  pop     rdi
0x1800043fb  retn
```
