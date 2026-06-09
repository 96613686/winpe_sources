# CConnectedAccounts_CreateInstance(_GUID const &,void * *)

- ea: `0x180014910`
- end: `0x180014981`
- name: `?CConnectedAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009900`

## callees

- `0x18000d740`
- `0x180014828`
- `0x180014910`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CConnectedAccounts_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  CConnectedAccounts *v5; // rax
  CConnectedAccounts *v6; // rax
  CConnectedAccounts *v7; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (CConnectedAccounts *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = CConnectedAccounts::CConnectedAccounts(v5);
    v7 = v6;
    if ( v6 )
    {
      v4 = (**(__int64 (__fastcall ***)(CConnectedAccounts *, const struct _GUID *, void **))v6)(v6, a1, a2);
      (*(void (__fastcall **)(CConnectedAccounts *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180014910  push    rbx
0x180014912  push    rbp
0x180014913  push    rsi
0x180014914  push    rdi
0x180014915  sub     rsp, 28h
0x180014919  mov     rsi, rdx
0x18001491c  mov     qword ptr [rdx], 0
0x180014923  mov     rbp, rcx
0x180014926  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001492d  mov     ecx, 28h ; '('; unsigned __int64
0x180014932  mov     edi, 8007000Eh
0x180014937  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001493c  test    rax, rax
0x18001493f  jz      short loc_180014976
0x180014941  mov     rcx, rax; this
0x180014944  call    ??0CConnectedAccounts@@QEAA@XZ; CConnectedAccounts::CConnectedAccounts(void)
0x180014949  mov     rbx, rax
0x18001494c  test    rax, rax
0x18001494f  jz      short loc_180014976
0x180014951  mov     rax, [rax]
0x180014954  mov     r8, rsi
0x180014957  mov     rdx, rbp
0x18001495a  mov     rcx, rbx
0x18001495d  mov     rax, [rax]
0x180014960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014965  mov     rcx, [rbx]
0x180014968  mov     edi, eax
0x18001496a  mov     rax, [rcx+10h]
0x18001496e  mov     rcx, rbx
0x180014971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014976  mov     eax, edi
0x180014978  add     rsp, 28h
0x18001497c  pop     rdi
0x18001497d  pop     rsi
0x18001497e  pop     rbp
0x18001497f  pop     rbx
0x180014980  retn
```
