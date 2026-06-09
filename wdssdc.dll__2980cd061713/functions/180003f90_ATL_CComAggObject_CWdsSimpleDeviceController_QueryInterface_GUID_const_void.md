# ATL::CComAggObject<CWdsSimpleDeviceController>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003f90`
- end: `0x180003ff4`
- name: `?QueryInterface@?$CComAggObject@VCWdsSimpleDeviceController@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000391c`
- `0x180003f90`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWdsSimpleDeviceController>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWdsSimpleDeviceController::_GetEntries'::`2'::_entries,
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
0x180003f90  push    rbx
0x180003f92  sub     rsp, 20h
0x180003f96  xor     ebx, ebx
0x180003f98  test    r8, r8
0x180003f9b  jnz     short loc_180003FA4
0x180003f9d  mov     eax, 80004003h
0x180003fa2  jmp     short loc_180003FED
0x180003fa4  mov     [r8], rbx
0x180003fa7  cmp     [rdx], ebx
0x180003fa9  jnz     short loc_180003FD3
0x180003fab  cmp     [rdx+4], ebx
0x180003fae  jnz     short loc_180003FD3
0x180003fb0  cmp     dword ptr [rdx+8], 0C0h
0x180003fb7  jnz     short loc_180003FD3
0x180003fb9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180003fc0  jnz     short loc_180003FD3
0x180003fc2  mov     [r8], rcx
0x180003fc5  mov     rax, [rcx]
0x180003fc8  mov     rax, [rax+8]
0x180003fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd1  jmp     short loc_180003FEB
0x180003fd3  mov     r9, r8; void **
0x180003fd6  add     rcx, 18h; void *
0x180003fda  mov     r8, rdx; struct _GUID *
0x180003fdd  lea     rdx, ?_entries@?1??_GetEntries@CWdsSimpleDeviceController@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180003fe4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180003fe9  mov     ebx, eax
0x180003feb  mov     eax, ebx
0x180003fed  add     rsp, 20h
0x180003ff1  pop     rbx
0x180003ff2  retn
```
