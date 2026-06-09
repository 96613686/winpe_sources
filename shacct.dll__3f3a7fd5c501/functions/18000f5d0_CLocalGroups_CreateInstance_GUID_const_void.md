# CLocalGroups_CreateInstance(_GUID const &,void * *)

- ea: `0x18000f5d0`
- end: `0x18000f643`
- name: `?CLocalGroups_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `115`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d740`
- `0x18000f080`
- `0x18000f5d0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CLocalGroups_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  CLocalAccounts *v5; // rax
  CLocalAccounts *v6; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (CLocalAccounts *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    CLocalAccounts::CLocalAccounts(v5);
    *(_QWORD *)v6 = &CLocalGroups::`vftable';
    v4 = ((__int64 (__fastcall *)(CLocalAccounts *, const struct _GUID *, void **))CLocalGroups::`vftable')(v6, a1, a2);
    (*(void (__fastcall **)(CLocalAccounts *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f5d0  push    rbx
0x18000f5d2  push    rbp
0x18000f5d3  push    rsi
0x18000f5d4  push    rdi
0x18000f5d5  sub     rsp, 28h
0x18000f5d9  mov     rsi, rdx
0x18000f5dc  mov     qword ptr [rdx], 0
0x18000f5e3  mov     rbp, rcx
0x18000f5e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f5ed  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000f5f2  mov     edi, 8007000Eh
0x18000f5f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f5fc  mov     rbx, rax
0x18000f5ff  test    rax, rax
0x18000f602  jz      short loc_18000F638
0x18000f604  mov     rcx, rax; this
0x18000f607  call    ??0CLocalAccounts@@QEAA@XZ; CLocalAccounts::CLocalAccounts(void)
0x18000f60c  lea     rax, ??_7CLocalGroups@@6B@; const CLocalGroups::`vftable'
0x18000f613  mov     r8, rsi
0x18000f616  mov     [rbx], rax
0x18000f619  mov     rdx, rbp
0x18000f61c  mov     rax, [rax]
0x18000f61f  mov     rcx, rbx
0x18000f622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f627  mov     rcx, [rbx]
0x18000f62a  mov     edi, eax
0x18000f62c  mov     rax, [rcx+10h]
0x18000f630  mov     rcx, rbx
0x18000f633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f638  mov     eax, edi
0x18000f63a  add     rsp, 28h
0x18000f63e  pop     rdi
0x18000f63f  pop     rsi
0x18000f640  pop     rbp
0x18000f641  pop     rbx
0x18000f642  retn
```
