# ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000b5c0`
- end: `0x14000b616`
- name: `?QueryInterface@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b620`
- `0x14000b630`
- `0x14000b640`

## callees

- `0x1400059b4`
- `0x14000b5c0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 4))(*((_QWORD *)a1 + 4));
  if ( (int)result < 0 && a1 != *((char **)a1 + 4) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWMPRichPreviewExt::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x14000b5c0  mov     [rsp+arg_0], rbx
0x14000b5c5  mov     [rsp+arg_8], rsi
0x14000b5ca  push    rdi
0x14000b5cb  sub     rsp, 20h
0x14000b5cf  mov     rbx, rcx
0x14000b5d2  mov     rdi, r8
0x14000b5d5  mov     rcx, [rcx+20h]
0x14000b5d9  mov     rsi, rdx
0x14000b5dc  mov     rax, [rcx]
0x14000b5df  mov     rax, [rax]
0x14000b5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5e7  test    eax, eax
0x14000b5e9  jns     short loc_14000B606
0x14000b5eb  cmp     rbx, [rbx+20h]
0x14000b5ef  jz      short loc_14000B606
0x14000b5f1  mov     r9, rdi; void **
0x14000b5f4  lea     rdx, ?_entries@?1??_GetEntries@CWMPRichPreviewExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000b5fb  mov     r8, rsi; struct _GUID *
0x14000b5fe  mov     rcx, rbx; void *
0x14000b601  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x14000b606  mov     rbx, [rsp+28h+arg_0]
0x14000b60b  mov     rsi, [rsp+28h+arg_8]
0x14000b610  add     rsp, 20h
0x14000b614  pop     rdi
0x14000b615  retn
```
