# CUserAccounts_CreateInstance(_GUID const &,void * *)

- ea: `0x18000db20`
- end: `0x18000dbc8`
- name: `?CUserAccounts_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d740`
- `0x18000db20`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CUserAccounts_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  char *v5; // rax
  char *v6; // rbx

  *a2 = 0;
  v4 = -2147024882;
  v5 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 4) = 1;
    *(_QWORD *)v5 = &CUserAccounts::`vftable'{for `IComputerAccounts'};
    *((_QWORD *)v5 + 1) = &CUserAccounts::`vftable'{for `IComputerAccountsEnumerationOption'};
    *((_QWORD *)v5 + 3) = 0;
    *((_DWORD *)v5 + 8) = 0;
    *((_DWORD *)v5 + 18) = 0;
    _InterlockedIncrement(&g_cRefCount);
    *(_OWORD *)(v5 + 40) = 0;
    *(_OWORD *)(v5 + 56) = 0;
    v4 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v5)(v5, a1, a2);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x18000db20  push    rbx
0x18000db22  push    rbp
0x18000db23  push    rsi
0x18000db24  push    rdi
0x18000db25  sub     rsp, 28h
0x18000db29  mov     rsi, rdx
0x18000db2c  mov     qword ptr [rdx], 0
0x18000db33  mov     rbp, rcx
0x18000db36  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000db3d  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000db42  mov     edi, 8007000Eh
0x18000db47  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000db4c  mov     rbx, rax
0x18000db4f  test    rax, rax
0x18000db52  jz      short loc_18000DBBD
0x18000db54  lea     rax, ??_7CUserAccounts@@6BIComputerAccounts@@@; const CUserAccounts::`vftable'{for `IComputerAccounts'}
0x18000db5b  mov     dword ptr [rbx+10h], 1
0x18000db62  mov     [rbx], rax
0x18000db65  lea     rax, ??_7CUserAccounts@@6BIComputerAccountsEnumerationOption@@@; const CUserAccounts::`vftable'{for `IComputerAccountsEnumerationOption'}
0x18000db6c  mov     [rbx+8], rax
0x18000db70  mov     qword ptr [rbx+18h], 0
0x18000db78  mov     dword ptr [rbx+20h], 0
0x18000db7f  mov     dword ptr [rbx+48h], 0
0x18000db86  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x18000db8d  xorps   xmm0, xmm0
0x18000db90  mov     r8, rsi
0x18000db93  movups  xmmword ptr [rbx+28h], xmm0
0x18000db97  mov     rdx, rbp
0x18000db9a  mov     rcx, rbx
0x18000db9d  movups  xmmword ptr [rbx+38h], xmm0
0x18000dba1  mov     rax, [rbx]
0x18000dba4  mov     rax, [rax]
0x18000dba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbac  mov     rcx, [rbx]
0x18000dbaf  mov     edi, eax
0x18000dbb1  mov     rax, [rcx+10h]
0x18000dbb5  mov     rcx, rbx
0x18000dbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbbd  mov     eax, edi
0x18000dbbf  add     rsp, 28h
0x18000dbc3  pop     rdi
0x18000dbc4  pop     rsi
0x18000dbc5  pop     rbp
0x18000dbc6  pop     rbx
0x18000dbc7  retn
```
