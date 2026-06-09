# ATL::CComAggObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)

- ea: `0x180012100`
- end: `0x180012163`
- name: `?QueryInterface@?$CComAggObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011b14`
- `0x180012100`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComAggObject<CXmlContentFilter>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CXmlContentFilter::_GetEntries'::`2'::_entries,
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
0x180012100  push    rbx
0x180012102  sub     rsp, 20h
0x180012106  xor     ebx, ebx
0x180012108  test    r8, r8
0x18001210b  jnz     short loc_180012114
0x18001210d  mov     eax, 80004003h
0x180012112  jmp     short loc_18001215D
0x180012114  mov     [r8], rbx
0x180012117  cmp     [rdx], ebx
0x180012119  jnz     short loc_180012143
0x18001211b  cmp     [rdx+4], ebx
0x18001211e  jnz     short loc_180012143
0x180012120  cmp     dword ptr [rdx+8], 0C0h
0x180012127  jnz     short loc_180012143
0x180012129  cmp     dword ptr [rdx+0Ch], 46000000h
0x180012130  jnz     short loc_180012143
0x180012132  mov     [r8], rcx
0x180012135  mov     rax, [rcx]
0x180012138  mov     rax, [rax+8]
0x18001213c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012141  jmp     short loc_18001215B
0x180012143  mov     r9, r8; void **
0x180012146  add     rcx, 18h; void *
0x18001214a  mov     r8, rdx; struct _GUID *
0x18001214d  lea     rdx, ?_entries@?1??_GetEntries@CXmlContentFilter@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180012154  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180012159  mov     ebx, eax
0x18001215b  mov     eax, ebx
0x18001215d  add     rsp, 20h
0x180012161  pop     rbx
0x180012162  retn
```
