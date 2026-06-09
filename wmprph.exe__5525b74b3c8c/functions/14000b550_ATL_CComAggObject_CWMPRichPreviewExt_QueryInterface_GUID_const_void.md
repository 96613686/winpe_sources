# ATL::CComAggObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000b550`
- end: `0x14000b5b0`
- name: `?QueryInterface@?$CComAggObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400059b4`
- `0x14000b550`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWMPRichPreviewExt>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWMPRichPreviewExt::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x14000b550  push    rbx
0x14000b552  sub     rsp, 20h
0x14000b556  xor     ebx, ebx
0x14000b558  cmp     [rdx], ebx
0x14000b55a  jnz     short loc_14000B590
0x14000b55c  cmp     [rdx+4], ebx
0x14000b55f  jnz     short loc_14000B590
0x14000b561  cmp     dword ptr [rdx+8], 0C0h
0x14000b568  jnz     short loc_14000B590
0x14000b56a  cmp     dword ptr [rdx+0Ch], 46000000h
0x14000b571  jnz     short loc_14000B590
0x14000b573  test    r8, r8
0x14000b576  jnz     short loc_14000B57F
0x14000b578  mov     eax, 80004003h
0x14000b57d  jmp     short loc_14000B5AA
0x14000b57f  mov     [r8], rcx
0x14000b582  mov     rax, [rcx]
0x14000b585  mov     rax, [rax+8]
0x14000b589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b58e  jmp     short loc_14000B5A8
0x14000b590  mov     r9, r8; void **
0x14000b593  add     rcx, 10h; void *
0x14000b597  mov     r8, rdx; struct _GUID *
0x14000b59a  lea     rdx, ?_entries@?1??_GetEntries@CWMPRichPreviewExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000b5a1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x14000b5a6  mov     ebx, eax
0x14000b5a8  mov     eax, ebx
0x14000b5aa  add     rsp, 20h
0x14000b5ae  pop     rbx
0x14000b5af  retn
```
