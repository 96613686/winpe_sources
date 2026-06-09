# CTokenActivation::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x18001dd70`
- end: `0x18001de24`
- name: `?_InternalQueryInterface@CTokenActivation@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003520`
- `0x18001dd70`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CTokenActivation::_InternalQueryInterface(
        CTokenActivation *this,
        const struct _GUID *a2,
        CTokenActivation **a3)
{
  CTokenActivation *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // ecx

  v4 = this;
  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v7;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00020400_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00020400_0000_0000_c000_000000000046.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_978d0509_97ae_4ee2_9e90_6844b213ab85.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_978d0509_97ae_4ee2_9e90_6844b213ab85.Data4 )
  {
    v6 = *(_QWORD *)this;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_cce718ce_6d82_4d79_a753_8768b9fcb00d.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_cce718ce_6d82_4d79_a753_8768b9fcb00d.Data4 )
    {
      v5 = 2147500034LL;
      *a3 = 0;
      goto LABEL_13;
    }
    v4 = (CTokenActivation *)(((unsigned __int64)this + 136) & -(__int64)(this != 0));
    v6 = *(_QWORD *)v4;
  }
  (*(void (**)(void))(v6 + 8))();
  v7 = 0;
  *a3 = v4;
  return v7;
}

```

## disassembly

```asm
0x18001dd70  mov     [rsp+arg_0], rbx
0x18001dd75  push    rdi
0x18001dd76  sub     rsp, 20h
0x18001dd7a  mov     rdi, r8
0x18001dd7d  mov     rbx, rcx
0x18001dd80  test    r8, r8
0x18001dd83  jnz     short loc_18001DD8F
0x18001dd85  mov     ecx, 80004003h
0x18001dd8a  jmp     loc_18001DE11
0x18001dd8f  mov     rax, [rdx]
0x18001dd92  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data1
0x18001dd99  jnz     short loc_18001DDBB
0x18001dd9b  mov     rax, [rdx+8]
0x18001dd9f  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data4
0x18001dda6  jnz     short loc_18001DDBB
0x18001dda8  mov     rax, [rcx]
0x18001ddab  mov     rax, [rax+8]
0x18001ddaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb4  xor     ecx, ecx
0x18001ddb6  mov     [rdi], rbx
0x18001ddb9  jmp     short loc_18001DE16
0x18001ddbb  mov     rax, [rdx]
0x18001ddbe  cmp     rax, qword ptr cs:_GUID_978d0509_97ae_4ee2_9e90_6844b213ab85.Data1
0x18001ddc5  jnz     short loc_18001DDD4
0x18001ddc7  mov     rax, [rdx+8]
0x18001ddcb  cmp     rax, qword ptr cs:_GUID_978d0509_97ae_4ee2_9e90_6844b213ab85.Data4
0x18001ddd2  jz      short loc_18001DDA8
0x18001ddd4  mov     rax, [rdx]
0x18001ddd7  cmp     rax, qword ptr cs:_GUID_cce718ce_6d82_4d79_a753_8768b9fcb00d.Data1
0x18001ddde  jnz     short loc_18001DE05
0x18001dde0  mov     rax, [rdx+8]
0x18001dde4  cmp     rax, qword ptr cs:_GUID_cce718ce_6d82_4d79_a753_8768b9fcb00d.Data4
0x18001ddeb  jnz     short loc_18001DE05
0x18001dded  lea     rax, [rcx+88h]
0x18001ddf4  neg     rbx
0x18001ddf7  sbb     rbx, rbx
0x18001ddfa  and     rbx, rax
0x18001ddfd  mov     rcx, rbx
0x18001de00  mov     rax, [rbx]
0x18001de03  jmp     short loc_18001DDAB
0x18001de05  mov     ecx, 80004002h
0x18001de0a  mov     qword ptr [r8], 0
0x18001de11  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001de16  mov     rbx, [rsp+28h+arg_0]
0x18001de1b  mov     eax, ecx
0x18001de1d  add     rsp, 20h
0x18001de21  pop     rdi
0x18001de22  retn
```
