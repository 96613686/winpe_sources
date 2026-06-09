# ATL::CComPolyObject<ATL::CAxHostWindow>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400076e0`
- end: `0x140007743`
- name: `?QueryInterface@?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400059b4`
- `0x1400076e0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<ATL::CAxHostWindow>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CAxHostWindow::_GetEntries'::`2'::_entries,
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
0x1400076e0  push    rbx
0x1400076e2  sub     rsp, 20h
0x1400076e6  xor     ebx, ebx
0x1400076e8  test    r8, r8
0x1400076eb  jnz     short loc_1400076F4
0x1400076ed  mov     eax, 80004003h
0x1400076f2  jmp     short loc_14000773D
0x1400076f4  mov     [r8], rbx
0x1400076f7  cmp     [rdx], ebx
0x1400076f9  jnz     short loc_140007723
0x1400076fb  cmp     [rdx+4], ebx
0x1400076fe  jnz     short loc_140007723
0x140007700  cmp     dword ptr [rdx+8], 0C0h
0x140007707  jnz     short loc_140007723
0x140007709  cmp     dword ptr [rdx+0Ch], 46000000h
0x140007710  jnz     short loc_140007723
0x140007712  mov     [r8], rcx
0x140007715  mov     rax, [rcx]
0x140007718  mov     rax, [rax+8]
0x14000771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007721  jmp     short loc_14000773B
0x140007723  mov     r9, r8; void **
0x140007726  add     rcx, 10h; void *
0x14000772a  mov     r8, rdx; struct _GUID *
0x14000772d  lea     rdx, ?_entries@?1??_GetEntries@CAxHostWindow@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140007734  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140007739  mov     ebx, eax
0x14000773b  mov     eax, ebx
0x14000773d  add     rsp, 20h
0x140007741  pop     rbx
0x140007742  retn
```
