# XMLScrServProv::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x14000c640`
- end: `0x14000c68a`
- name: `?QueryService@XMLScrServProv@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `74`
- prototype: `__int64 __fastcall(XMLScrServProv *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task`

## callees

- `0x14000c640`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::QueryService(
        XMLScrServProv *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_ScriptletContext.Revision
    && *(_QWORD *)a2->Data4 == *(_QWORD *)SID_ScriptletContext.SubAuthority )
  {
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(
             *((_QWORD *)this + 1),
             a3,
             a4);
  }
  *a4 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x14000c640  mov     r10, r8
0x14000c643  test    r9, r9
0x14000c646  jnz     short loc_14000C64F
0x14000c648  mov     eax, 80004003h
0x14000c64d  jmp     short locret_14000C689
0x14000c64f  mov     rax, [rdx]
0x14000c652  cmp     rax, qword ptr cs:SID_ScriptletContext.Revision
0x14000c659  jnz     short loc_14000C67D
0x14000c65b  mov     rax, [rdx+8]
0x14000c65f  cmp     rax, qword ptr cs:SID_ScriptletContext.SubAuthority
0x14000c666  jnz     short loc_14000C67D
0x14000c668  mov     rcx, [rcx+8]
0x14000c66c  mov     r8, r9
0x14000c66f  mov     rdx, r10
0x14000c672  mov     rax, [rcx]
0x14000c675  mov     rax, [rax]
0x14000c678  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14000c67d  mov     qword ptr [r9], 0
0x14000c684  mov     eax, 80004002h
0x14000c689  retn
```
