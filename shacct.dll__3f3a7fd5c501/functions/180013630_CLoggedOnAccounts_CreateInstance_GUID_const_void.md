# CLoggedOnAccounts_CreateInstance(_GUID const &,void * *)

- ea: `0x180013630`
- end: `0x1800136a1`
- name: `?CLoggedOnAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009900`

## callees

- `0x18000d740`
- `0x180013604`
- `0x180013630`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  CLoggedOnAccounts *v5; // rax
  CLoggedOnAccounts *v6; // rax
  CLoggedOnAccounts *v7; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (CLoggedOnAccounts *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = CLoggedOnAccounts::CLoggedOnAccounts(v5);
    v7 = v6;
    if ( v6 )
    {
      v4 = (**(__int64 (__fastcall ***)(CLoggedOnAccounts *, const struct _GUID *, void **))v6)(v6, a1, a2);
      (*(void (__fastcall **)(CLoggedOnAccounts *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180013630  push    rbx
0x180013632  push    rbp
0x180013633  push    rsi
0x180013634  push    rdi
0x180013635  sub     rsp, 28h
0x180013639  mov     rsi, rdx
0x18001363c  mov     qword ptr [rdx], 0
0x180013643  mov     rbp, rcx
0x180013646  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001364d  mov     ecx, 18h; unsigned __int64
0x180013652  mov     edi, 8007000Eh
0x180013657  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001365c  test    rax, rax
0x18001365f  jz      short loc_180013696
0x180013661  mov     rcx, rax; this
0x180013664  call    ??0CLoggedOnAccounts@@QEAA@XZ; CLoggedOnAccounts::CLoggedOnAccounts(void)
0x180013669  mov     rbx, rax
0x18001366c  test    rax, rax
0x18001366f  jz      short loc_180013696
0x180013671  mov     rax, [rax]
0x180013674  mov     r8, rsi
0x180013677  mov     rdx, rbp
0x18001367a  mov     rcx, rbx
0x18001367d  mov     rax, [rax]
0x180013680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013685  mov     rcx, [rbx]
0x180013688  mov     edi, eax
0x18001368a  mov     rax, [rcx+10h]
0x18001368e  mov     rcx, rbx
0x180013691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013696  mov     eax, edi
0x180013698  add     rsp, 28h
0x18001369c  pop     rdi
0x18001369d  pop     rsi
0x18001369e  pop     rbp
0x18001369f  pop     rbx
0x1800136a0  retn
```
