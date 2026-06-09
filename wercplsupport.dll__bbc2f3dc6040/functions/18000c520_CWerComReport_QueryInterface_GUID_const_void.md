# CWerComReport::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c520`
- end: `0x18000c595`
- name: `?QueryInterface@CWerComReport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c5a0`

## callees

- `0x18000c520`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReport::QueryInterface(CWerComReport *this, const struct _GUID *a2, CWerComReport **a3)
{
  CWerComReport *v3; // rax

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = this;
LABEL_7:
    *a3 = v3;
    (*(void (__fastcall **)(CWerComReport *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWerReport.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWerReport.Data4 )
  {
    v3 = (CWerComReport *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
    goto LABEL_7;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c520  sub     rsp, 28h
0x18000c524  mov     rax, [rdx]
0x18000c527  mov     r9, rcx
0x18000c52a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c531  jnz     short loc_18000C545
0x18000c533  mov     rax, [rdx+8]
0x18000c537  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c53e  jnz     short loc_18000C545
0x18000c540  mov     rax, rcx
0x18000c543  jmp     short loc_18000C56E
0x18000c545  mov     rax, [rdx]
0x18000c548  cmp     rax, qword ptr cs:IID_IWerReport.Data1
0x18000c54f  jnz     short loc_18000C584
0x18000c551  mov     rax, [rdx+8]
0x18000c555  cmp     rax, qword ptr cs:IID_IWerReport.Data4
0x18000c55c  jnz     short loc_18000C584
0x18000c55e  add     rcx, 18h
0x18000c562  mov     rax, r9
0x18000c565  neg     rax
0x18000c568  sbb     rax, rax
0x18000c56b  and     rax, rcx
0x18000c56e  mov     [r8], rax
0x18000c571  mov     rcx, r9
0x18000c574  mov     rax, [r9]
0x18000c577  mov     rax, [rax+8]
0x18000c57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c580  xor     eax, eax
0x18000c582  jmp     short loc_18000C590
0x18000c584  mov     qword ptr [r8], 0
0x18000c58b  mov     eax, 80004002h
0x18000c590  add     rsp, 28h
0x18000c594  retn
```
