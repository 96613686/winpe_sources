# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000deb0`
- end: `0x18000df14`
- name: `?QueryInterface@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ce10`
- `0x18000deb0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(
        char *a1,
        __int64 a2,
        char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`Microsoft::Windows::Performance::CEventTraceRelogger::_GetEntries'::`2'::_entries,
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
0x18000deb0  push    rbx
0x18000deb2  sub     rsp, 20h
0x18000deb6  xor     ebx, ebx
0x18000deb8  test    r8, r8
0x18000debb  jnz     short loc_18000DEC4
0x18000debd  mov     eax, 80004003h
0x18000dec2  jmp     short loc_18000DF0D
0x18000dec4  mov     [r8], rbx
0x18000dec7  cmp     [rdx], ebx
0x18000dec9  jnz     short loc_18000DEF3
0x18000decb  cmp     [rdx+4], ebx
0x18000dece  jnz     short loc_18000DEF3
0x18000ded0  cmp     dword ptr [rdx+8], 0C0h
0x18000ded7  jnz     short loc_18000DEF3
0x18000ded9  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000dee0  jnz     short loc_18000DEF3
0x18000dee2  mov     [r8], rcx
0x18000dee5  mov     rax, [rcx]
0x18000dee8  mov     rax, [rax+8]
0x18000deec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def1  jmp     short loc_18000DF0B
0x18000def3  mov     r9, r8; void **
0x18000def6  add     rcx, 10h; void *
0x18000defa  mov     r8, rdx; struct _GUID *
0x18000defd  lea     rdx, ?_entries@?1??_GetEntries@CEventTraceRelogger@Performance@Windows@Microsoft@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000df04  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000df09  mov     ebx, eax
0x18000df0b  mov     eax, ebx
0x18000df0d  add     rsp, 20h
0x18000df11  pop     rbx
0x18000df12  retn
```
