# ATL::CComAggObject<CRecoExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001b80`
- end: `0x180001c15`
- name: `?QueryInterface@?$CComAggObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001780`

## callees

- `0x1800019a0`
- `0x180001b80`
- `0x180001c20`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRecoExt>::QueryInterface(__int64 a1, __int64 a2, void **a3)
{
  void (*v4)(void); // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
    return ATL::AtlInternalQueryInterface(
             (void *)(a1 + 24),
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRecoExt::_GetEntries'::`2'::_entries,
             (const struct _GUID *)a2,
             a3);
  *a3 = (void *)a1;
  v4 = *(void (**)(void))(*(_QWORD *)a1 + 8LL);
  if ( (char *)v4 == (char *)ATL::CComAggObject<CRecoExt>::AddRef )
    ATL::CComAggObject<CRecoExt>::AddRef();
  else
    v4();
  return 0;
}

```

## disassembly

```asm
0x180001b80  sub     rsp, 28h
0x180001b84  test    r8, r8
0x180001b87  jnz     short loc_180001B93
0x180001b89  mov     eax, 80004003h
0x180001b8e  add     rsp, 28h
0x180001b92  retn
0x180001b93  mov     qword ptr [r8], 0
0x180001b9a  cmp     dword ptr [rdx], 0
0x180001b9d  mov     [rsp+28h+var_8], rbx
0x180001ba2  jnz     short loc_180001BF6
0x180001ba4  cmp     dword ptr [rdx+4], 0
0x180001ba8  jnz     short loc_180001BF6
0x180001baa  cmp     dword ptr [rdx+8], 0C0h
0x180001bb1  jnz     short loc_180001BF6
0x180001bb3  cmp     dword ptr [rdx+0Ch], 46000000h
0x180001bba  jnz     short loc_180001BF6
0x180001bbc  mov     [r8], rcx
0x180001bbf  lea     rdx, ?AddRef@?$CComAggObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComAggObject<CRecoExt>::AddRef(void)
0x180001bc6  mov     rax, [rcx]
0x180001bc9  xor     ebx, ebx
0x180001bcb  mov     rax, [rax+8]
0x180001bcf  cmp     rax, rdx
0x180001bd2  jnz     short loc_180001BE5
0x180001bd4  call    ?AddRef@?$CComAggObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComAggObject<CRecoExt>::AddRef(void)
0x180001bd9  mov     eax, ebx
0x180001bdb  mov     rbx, [rsp+28h+var_8]
0x180001be0  add     rsp, 28h
0x180001be4  retn
0x180001be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bea  mov     eax, ebx
0x180001bec  mov     rbx, [rsp+28h+var_8]
0x180001bf1  add     rsp, 28h
0x180001bf5  retn
0x180001bf6  mov     r9, r8; void **
0x180001bf9  add     rcx, 18h; void *
0x180001bfd  mov     r8, rdx; struct _GUID *
0x180001c00  lea     rdx, ?_entries@?1??_GetEntries@CRecoExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180001c07  mov     rbx, [rsp+28h+var_8]
0x180001c0c  add     rsp, 28h
0x180001c10  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
