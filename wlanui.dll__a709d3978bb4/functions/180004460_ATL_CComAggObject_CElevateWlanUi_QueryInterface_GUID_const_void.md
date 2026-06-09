# ATL::CComAggObject<CElevateWlanUi>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004460`
- end: `0x1800044c3`
- name: `?QueryInterface@?$CComAggObject@VCElevateWlanUi@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003e84`
- `0x180004460`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CElevateWlanUi>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CElevateWlanUi::_GetEntries'::`2'::_entries,
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
0x180004460  push    rbx
0x180004462  sub     rsp, 20h
0x180004466  xor     ebx, ebx
0x180004468  test    r8, r8
0x18000446b  jnz     short loc_180004474
0x18000446d  mov     eax, 80004003h
0x180004472  jmp     short loc_1800044BD
0x180004474  mov     [r8], rbx
0x180004477  cmp     [rdx], ebx
0x180004479  jnz     short loc_1800044A3
0x18000447b  cmp     [rdx+4], ebx
0x18000447e  jnz     short loc_1800044A3
0x180004480  cmp     dword ptr [rdx+8], 0C0h
0x180004487  jnz     short loc_1800044A3
0x180004489  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004490  jnz     short loc_1800044A3
0x180004492  mov     [r8], rcx
0x180004495  mov     rax, [rcx]
0x180004498  mov     rax, [rax+8]
0x18000449c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a1  jmp     short loc_1800044BB
0x1800044a3  mov     r9, r8; void **
0x1800044a6  add     rcx, 18h; void *
0x1800044aa  mov     r8, rdx; struct _GUID *
0x1800044ad  lea     rdx, ?_entries@?1??_GetEntries@CElevateWlanUi@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800044b4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800044b9  mov     ebx, eax
0x1800044bb  mov     eax, ebx
0x1800044bd  add     rsp, 20h
0x1800044c1  pop     rbx
0x1800044c2  retn
```
