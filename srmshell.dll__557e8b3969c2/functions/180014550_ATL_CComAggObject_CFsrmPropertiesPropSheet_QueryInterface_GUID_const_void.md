# ATL::CComAggObject<CFsrmPropertiesPropSheet>::QueryInterface(_GUID const &,void * *)

- ea: `0x180014550`
- end: `0x1800145b3`
- name: `?QueryInterface@?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009bb0`
- `0x180014550`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CFsrmPropertiesPropSheet>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CFsrmPropertiesPropSheet::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180014550  push    rbx
0x180014552  sub     rsp, 20h
0x180014556  xor     ebx, ebx
0x180014558  test    r8, r8
0x18001455b  jnz     short loc_180014564
0x18001455d  mov     eax, 80004003h
0x180014562  jmp     short loc_1800145AD
0x180014564  mov     [r8], rbx
0x180014567  cmp     [rdx], ebx
0x180014569  jnz     short loc_180014593
0x18001456b  cmp     [rdx+4], ebx
0x18001456e  jnz     short loc_180014593
0x180014570  cmp     dword ptr [rdx+8], 0C0h
0x180014577  jnz     short loc_180014593
0x180014579  cmp     dword ptr [rdx+0Ch], 46000000h
0x180014580  jnz     short loc_180014593
0x180014582  mov     [r8], rcx
0x180014585  mov     rax, [rcx]
0x180014588  mov     rax, [rax+8]
0x18001458c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014591  jmp     short loc_1800145AB
0x180014593  mov     r9, r8; void **
0x180014596  add     rcx, 10h; void *
0x18001459a  mov     r8, rdx; struct _GUID *
0x18001459d  lea     rdx, ?_entries@?1??_GetEntries@CFsrmPropertiesPropSheet@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800145a4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800145a9  mov     ebx, eax
0x1800145ab  mov     eax, ebx
0x1800145ad  add     rsp, 20h
0x1800145b1  pop     rbx
0x1800145b2  retn
```
