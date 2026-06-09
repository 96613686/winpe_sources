# CElevationConfig::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x18001da30`
- end: `0x18001dab0`
- name: `?_InternalQueryInterface@CElevationConfig@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x18001da30`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CElevationConfig::_InternalQueryInterface(CElevationConfig *this, const struct _GUID *a2, void **a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ecx

  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v6;
  }
  if ( (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_00020400_0000_0000_c000_000000000046.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_00020400_0000_0000_c000_000000000046.Data4)
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_0d599e27_34c7_41a5_973e_b820d42783ec.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_0d599e27_34c7_41a5_973e_b820d42783ec.Data4) )
  {
    v5 = 2147500034LL;
    *a3 = 0;
    goto LABEL_9;
  }
  (*(void (__fastcall **)(CElevationConfig *))(*(_QWORD *)this + 8LL))(this);
  v6 = 0;
  *a3 = this;
  return v6;
}

```

## disassembly

```asm
0x18001da30  mov     [rsp+arg_0], rbx
0x18001da35  push    rdi
0x18001da36  sub     rsp, 20h
0x18001da3a  mov     rdi, r8
0x18001da3d  mov     rbx, rcx
0x18001da40  test    r8, r8
0x18001da43  jnz     short loc_18001DA4C
0x18001da45  mov     ecx, 80004003h
0x18001da4a  jmp     short loc_18001DA9D
0x18001da4c  mov     rax, [rdx]
0x18001da4f  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data1
0x18001da56  jnz     short loc_18001DA78
0x18001da58  mov     rax, [rdx+8]
0x18001da5c  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data4
0x18001da63  jnz     short loc_18001DA78
0x18001da65  mov     rax, [rcx]
0x18001da68  mov     rax, [rax+8]
0x18001da6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da71  xor     ecx, ecx
0x18001da73  mov     [rdi], rbx
0x18001da76  jmp     short loc_18001DAA2
0x18001da78  mov     rax, [rdx]
0x18001da7b  cmp     rax, qword ptr cs:_GUID_0d599e27_34c7_41a5_973e_b820d42783ec.Data1
0x18001da82  jnz     short loc_18001DA91
0x18001da84  mov     rax, [rdx+8]
0x18001da88  cmp     rax, qword ptr cs:_GUID_0d599e27_34c7_41a5_973e_b820d42783ec.Data4
0x18001da8f  jz      short loc_18001DA65
0x18001da91  mov     ecx, 80004002h
0x18001da96  mov     qword ptr [r8], 0
0x18001da9d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001daa2  mov     rbx, [rsp+28h+arg_0]
0x18001daa7  mov     eax, ecx
0x18001daa9  add     rsp, 20h
0x18001daad  pop     rdi
0x18001daae  retn
```
