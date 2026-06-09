# ATL::CComAggObject<TpmVCardManagerImpl>::QueryInterface(_GUID const &,void * *)

- ea: `0x180026a00`
- end: `0x180026a5a`
- name: `?QueryInterface@?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800260d8`
- `0x18002698c`
- `0x180026a00`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<TpmVCardManagerImpl>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  void **v6; // r8
  __int64 v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = (void *)v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           (void *)(v7 + 16),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`TpmVCardManagerImpl::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180026a00  push    rbx
0x180026a02  sub     rsp, 20h
0x180026a06  xor     ebx, ebx
0x180026a08  mov     r9, rcx
0x180026a0b  test    r8, r8
0x180026a0e  jnz     short loc_180026A17
0x180026a10  mov     eax, 80004003h
0x180026a15  jmp     short loc_180026A54
0x180026a17  mov     rcx, rdx; struct _GUID *
0x180026a1a  mov     [r8], rbx
0x180026a1d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180026a22  test    eax, eax
0x180026a24  jz      short loc_180026A3A
0x180026a26  mov     [r8], r9
0x180026a29  mov     rcx, r9
0x180026a2c  mov     rax, [r9]
0x180026a2f  mov     rax, [rax+8]
0x180026a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a38  jmp     short loc_180026A52
0x180026a3a  lea     rcx, [r9+10h]; void *
0x180026a3e  mov     r9, r8; void **
0x180026a41  mov     r8, rdx; struct _GUID *
0x180026a44  lea     rdx, ?_entries@?1??_GetEntries@TpmVCardManagerImpl@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180026a4b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180026a50  mov     ebx, eax
0x180026a52  mov     eax, ebx
0x180026a54  add     rsp, 20h
0x180026a58  pop     rbx
0x180026a59  retn
```
