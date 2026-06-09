# ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(_GUID const &,void * *)

- ea: `0x140007540`
- end: `0x14000759e`
- name: `?QueryInterface@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `94`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400075b0`
- `0x1400075c0`
- `0x1400075d0`
- `0x1400075e0`
- `0x1400075f0`
- `0x140007600`
- `0x140007610`
- `0x140007620`
- `0x140007630`

## callees

- `0x1400059b4`
- `0x140007540`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  __int64 result; // rax

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 88))(*(_QWORD *)(a1 + 88));
  if ( (int)result < 0 && a1 + 80 != *(_QWORD *)(a1 - 64 + 152) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             (char *)(a1 - 64),
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CAxHostWindow::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x140007540  mov     [rsp+arg_0], rbx
0x140007545  mov     [rsp+arg_8], rsi
0x14000754a  push    rdi
0x14000754b  sub     rsp, 20h
0x14000754f  mov     rbx, rcx
0x140007552  mov     rdi, r8
0x140007555  mov     rcx, [rcx+58h]
0x140007559  mov     rsi, rdx
0x14000755c  mov     rax, [rcx]
0x14000755f  mov     rax, [rax]
0x140007562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007567  test    eax, eax
0x140007569  jns     short loc_14000758E
0x14000756b  lea     rcx, [rbx-40h]; void *
0x14000756f  lea     rdx, [rbx+50h]
0x140007573  cmp     rdx, [rcx+98h]
0x14000757a  jz      short loc_14000758E
0x14000757c  mov     r9, rdi; void **
0x14000757f  lea     rdx, ?_entries@?1??_GetEntries@CAxHostWindow@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140007586  mov     r8, rsi; struct _GUID *
0x140007589  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x14000758e  mov     rbx, [rsp+28h+arg_0]
0x140007593  mov     rsi, [rsp+28h+arg_8]
0x140007598  add     rsp, 20h
0x14000759c  pop     rdi
0x14000759d  retn
```
