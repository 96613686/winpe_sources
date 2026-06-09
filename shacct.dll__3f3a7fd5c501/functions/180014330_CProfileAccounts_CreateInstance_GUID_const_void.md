# CProfileAccounts_CreateInstance(_GUID const &,void * *)

- ea: `0x180014330`
- end: `0x1800143a1`
- name: `?CProfileAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009900`

## callees

- `0x18000d740`
- `0x1800141f8`
- `0x180014330`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CProfileAccounts_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  CProfileAccounts *v5; // rax
  CProfileAccounts *v6; // rax
  CProfileAccounts *v7; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (CProfileAccounts *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = CProfileAccounts::CProfileAccounts(v5);
    v7 = v6;
    if ( v6 )
    {
      v4 = (**(__int64 (__fastcall ***)(CProfileAccounts *, const struct _GUID *, void **))v6)(v6, a1, a2);
      (*(void (__fastcall **)(CProfileAccounts *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180014330  push    rbx
0x180014332  push    rbp
0x180014333  push    rsi
0x180014334  push    rdi
0x180014335  sub     rsp, 28h
0x180014339  mov     rsi, rdx
0x18001433c  mov     qword ptr [rdx], 0
0x180014343  mov     rbp, rcx
0x180014346  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001434d  mov     ecx, 20h ; ' '; unsigned __int64
0x180014352  mov     edi, 8007000Eh
0x180014357  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001435c  test    rax, rax
0x18001435f  jz      short loc_180014396
0x180014361  mov     rcx, rax; this
0x180014364  call    ??0CProfileAccounts@@QEAA@XZ; CProfileAccounts::CProfileAccounts(void)
0x180014369  mov     rbx, rax
0x18001436c  test    rax, rax
0x18001436f  jz      short loc_180014396
0x180014371  mov     rax, [rax]
0x180014374  mov     r8, rsi
0x180014377  mov     rdx, rbp
0x18001437a  mov     rcx, rbx
0x18001437d  mov     rax, [rax]
0x180014380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014385  mov     rcx, [rbx]
0x180014388  mov     edi, eax
0x18001438a  mov     rax, [rcx+10h]
0x18001438e  mov     rcx, rbx
0x180014391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014396  mov     eax, edi
0x180014398  add     rsp, 28h
0x18001439c  pop     rdi
0x18001439d  pop     rsi
0x18001439e  pop     rbp
0x18001439f  pop     rbx
0x1800143a0  retn
```
