# ATL::CComAggObject<CFciPropertiesShellExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800144e0`
- end: `0x180014543`
- name: `?QueryInterface@?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009bb0`
- `0x1800144e0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CFciPropertiesShellExt>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CFciPropertiesShellExt::_GetEntries'::`2'::_entries,
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
0x1800144e0  push    rbx
0x1800144e2  sub     rsp, 20h
0x1800144e6  xor     ebx, ebx
0x1800144e8  test    r8, r8
0x1800144eb  jnz     short loc_1800144F4
0x1800144ed  mov     eax, 80004003h
0x1800144f2  jmp     short loc_18001453D
0x1800144f4  mov     [r8], rbx
0x1800144f7  cmp     [rdx], ebx
0x1800144f9  jnz     short loc_180014523
0x1800144fb  cmp     [rdx+4], ebx
0x1800144fe  jnz     short loc_180014523
0x180014500  cmp     dword ptr [rdx+8], 0C0h
0x180014507  jnz     short loc_180014523
0x180014509  cmp     dword ptr [rdx+0Ch], 46000000h
0x180014510  jnz     short loc_180014523
0x180014512  mov     [r8], rcx
0x180014515  mov     rax, [rcx]
0x180014518  mov     rax, [rax+8]
0x18001451c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014521  jmp     short loc_18001453B
0x180014523  mov     r9, r8; void **
0x180014526  add     rcx, 10h; void *
0x18001452a  mov     r8, rdx; struct _GUID *
0x18001452d  lea     rdx, ?_entries@?1??_GetEntries@CFciPropertiesShellExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180014534  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180014539  mov     ebx, eax
0x18001453b  mov     eax, ebx
0x18001453d  add     rsp, 20h
0x180014541  pop     rbx
0x180014542  retn
```
