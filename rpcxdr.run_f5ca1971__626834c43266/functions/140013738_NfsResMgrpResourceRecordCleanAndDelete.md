# NfsResMgrpResourceRecordCleanAndDelete

- ea: `0x140013738`
- end: `0x1400137c5`
- name: `NfsResMgrpResourceRecordCleanAndDelete`
- size: `141`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140013044`
- `0x14001318c`
- `0x1400134d4`

## callees

- `0x140013738`
- `0x140014900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400137a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137a4`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140013781`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140013781`

## pseudocode

```c
__int64 __fastcall NfsResMgrpResourceRecordCleanAndDelete(struct _LOOKASIDE_LIST_EX *P)
{
  unsigned int v2; // edi

  if ( (P[4].L.TotalFrees & 1) == 0 || *(_DWORD *)&P[4].L.Depth || HIDWORD(P->L.SingleListHead.Next) )
  {
    return (unsigned int)-1068285909;
  }
  else
  {
    v2 = 0;
    if ( !*(_DWORD *)&P[4].L.Depth && ((__int64)P->L.AllocateEx & 2) != 0 && (P[4].L.ListHead.Alignment & 1) != 0 )
    {
      ExDeleteLookasideListEx(P + 3);
      LODWORD(P[4].L.ListHead.Alignment) &= ~1u;
    }
    NfsCfgMgrpResourceRegistrationCleanup(P);
    ExFreePoolWithTag(P, 0x43455252u);
  }
  return v2;
}

```

## disassembly

```asm
0x140013738  mov     [rsp+arg_0], rbx
0x14001373d  push    rdi
0x14001373e  sub     rsp, 20h
0x140013742  mov     eax, [rcx+19Ch]
0x140013748  mov     rbx, rcx
0x14001374b  test    al, 1
0x14001374d  jz      short loc_1400137B2
0x14001374f  cmp     dword ptr [rcx+190h], 0
0x140013756  jnz     short loc_1400137B2
0x140013758  mov     eax, [rcx+4]
0x14001375b  test    eax, eax
0x14001375d  jnz     short loc_1400137B2
0x14001375f  xor     edi, edi
0x140013761  cmp     [rcx+190h], edi
0x140013767  jnz     short loc_140013794
0x140013769  mov     eax, [rcx+30h]
0x14001376c  test    al, 2
0x14001376e  jz      short loc_140013794
0x140013770  mov     eax, [rcx+180h]
0x140013776  test    al, 1
0x140013778  jz      short loc_140013794
0x14001377a  add     rcx, 120h; Lookaside
0x140013781  call    cs:__imp_ExDeleteLookasideListEx
0x140013788  nop     dword ptr [rax+rax+00h]
0x14001378d  and     dword ptr [rbx+180h], 0FFFFFFFEh
0x140013794  mov     rcx, rbx
0x140013797  call    NfsCfgMgrpResourceRegistrationCleanup
0x14001379c  mov     edx, 43455252h; Tag
0x1400137a1  mov     rcx, rbx; P
0x1400137a4  call    cs:__imp_ExFreePoolWithTag
0x1400137ab  nop     dword ptr [rax+rax+00h]
0x1400137b0  jmp     short loc_1400137B7
0x1400137b2  mov     edi, 0C053402Bh
0x1400137b7  mov     rbx, [rsp+28h+arg_0]
0x1400137bc  mov     eax, edi
0x1400137be  add     rsp, 20h
0x1400137c2  pop     rdi
0x1400137c3  retn
```
