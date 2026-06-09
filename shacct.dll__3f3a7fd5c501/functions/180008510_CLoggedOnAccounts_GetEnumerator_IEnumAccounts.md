# CLoggedOnAccounts::GetEnumerator(IEnumAccounts * *)

- ea: `0x180008510`
- end: `0x18000862b`
- name: `?GetEnumerator@CLoggedOnAccounts@@UEAAJPEAPEAUIEnumAccounts@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CLoggedOnAccounts *__hidden this, struct IEnumAccounts **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008510`
- `0x180008640`
- `0x18000d740`
- `0x1800135d8`
- `0x180016ce9`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085a4`

## pseudocode

```c
__int64 __fastcall CLoggedOnAccounts::GetEnumerator(CLoggedOnAccounts *this, struct IEnumAccounts **a2)
{
  unsigned int v4; // r14d
  __int64 result; // rax
  CEnumLogonAccounts *v6; // rax
  CEnumLogonAccounts *v7; // rbx
  const void *v8; // rbp
  __int64 v9; // rax
  size_t v10; // rsi
  void *v11; // rax

  v4 = -2147024809;
  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  result = CLoggedOnAccounts::_Init(this);
  if ( (int)result >= 0 )
  {
    v6 = (CEnumLogonAccounts *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v6 )
      return 2147942414LL;
    v7 = CEnumLogonAccounts::CEnumLogonAccounts(v6);
    if ( !v7 )
      return 2147942414LL;
    v8 = (const void *)*((_QWORD *)this + 2);
    if ( !v8 )
      goto LABEL_10;
    v9 = *((unsigned int *)this + 3);
    *((_DWORD *)v7 + 3) = v9;
    if ( (_DWORD)v9 )
    {
      v10 = 528 * v9;
      v4 = -2147024882;
      v11 = CoTaskMemAlloc(528 * v9);
      *((_QWORD *)v7 + 2) = v11;
      if ( !v11 )
      {
LABEL_10:
        (*(void (__fastcall **)(CEnumLogonAccounts *))(*(_QWORD *)v7 + 16LL))(v7);
        return v4;
      }
      memcpy_0(v11, v8, v10);
    }
    v4 = (**(__int64 (__fastcall ***)(CEnumLogonAccounts *, GUID *, struct IEnumAccounts **))v7)(
           v7,
           &GUID_50c852b0_c95f_4fee_be00_87dc18b2661b,
           a2);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x180008510  mov     [rsp+arg_10], rsi
0x180008515  mov     [rsp+arg_18], rdi
0x18000851a  push    r14
0x18000851c  sub     rsp, 20h
0x180008520  mov     rdi, rdx
0x180008523  mov     rsi, rcx
0x180008526  mov     r14d, 80070057h
0x18000852c  test    rdx, rdx
0x18000852f  jz      loc_180008626
0x180008535  mov     qword ptr [rdx], 0
0x18000853c  call    ?_Init@CLoggedOnAccounts@@AEAAJXZ; CLoggedOnAccounts::_Init(void)
0x180008541  test    eax, eax
0x180008543  js      loc_1800085F8
0x180008549  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008550  mov     ecx, 20h ; ' '; unsigned __int64
0x180008555  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000855a  test    rax, rax
0x18000855d  jz      loc_180008610
0x180008563  mov     rcx, rax; this
0x180008566  mov     [rsp+28h+arg_0], rbx
0x18000856b  call    ??0CEnumLogonAccounts@@QEAA@XZ; CEnumLogonAccounts::CEnumLogonAccounts(void)
0x180008570  mov     rbx, rax
0x180008573  test    rax, rax
0x180008576  jz      loc_180008609
0x18000857c  mov     [rsp+28h+arg_8], rbp
0x180008581  mov     rbp, [rsi+10h]
0x180008585  test    rbp, rbp
0x180008588  jz      short loc_1800085DC
0x18000858a  mov     eax, [rsi+0Ch]
0x18000858d  mov     [rbx+0Ch], eax
0x180008590  test    eax, eax
0x180008592  jz      short loc_1800085C1
0x180008594  imul    rsi, rax, 210h
0x18000859b  mov     r14d, 8007000Eh
0x1800085a1  mov     rcx, rsi; cb
0x1800085a4  call    cs:__imp_CoTaskMemAlloc
0x1800085aa  mov     [rbx+10h], rax
0x1800085ae  test    rax, rax
0x1800085b1  jz      short loc_1800085DC
0x1800085b3  mov     r8, rsi; Size
0x1800085b6  mov     rdx, rbp; Src
0x1800085b9  mov     rcx, rax; void *
0x1800085bc  call    memcpy_0
0x1800085c1  mov     rax, [rbx]
0x1800085c4  lea     rdx, _GUID_50c852b0_c95f_4fee_be00_87dc18b2661b
0x1800085cb  mov     r8, rdi
0x1800085ce  mov     rcx, rbx
0x1800085d1  mov     rax, [rax]
0x1800085d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085d9  mov     r14d, eax
0x1800085dc  mov     rax, [rbx]
0x1800085df  mov     rcx, rbx
0x1800085e2  mov     rax, [rax+10h]
0x1800085e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085eb  mov     rbp, [rsp+28h+arg_8]
0x1800085f0  mov     eax, r14d
0x1800085f3  mov     rbx, [rsp+28h+arg_0]
0x1800085f8  mov     rsi, [rsp+28h+arg_10]
0x1800085fd  mov     rdi, [rsp+28h+arg_18]
0x180008602  add     rsp, 20h
0x180008606  pop     r14
0x180008608  retn
0x180008609  mov     eax, 8007000Eh
0x18000860e  jmp     short loc_1800085F3
0x180008610  mov     rsi, [rsp+28h+arg_10]
0x180008615  mov     eax, 8007000Eh
0x18000861a  mov     rdi, [rsp+28h+arg_18]
0x18000861f  add     rsp, 20h
0x180008623  pop     r14
0x180008625  retn
0x180008626  mov     eax, r14d
0x180008629  jmp     short loc_1800085F8
```
