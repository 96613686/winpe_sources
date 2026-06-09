# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18000246c`
- end: `0x180002667`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `507`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800026b0`
- `0x1800043ec`
- `0x180004714`

## callees

- `0x180001534`
- `0x18000190c`
- `0x18000246c`
- `0x180004a94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800025df`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800025fe`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800025df`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800025fe`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r12
  const unsigned __int16 *v4; // r13
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  ATL::Checked *v8; // r15
  __int64 v9; // rcx
  ATL::Checked *v10; // rbx
  unsigned int v11; // r12d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  ATL::Checked **v15; // rcx
  ATL::Checked **v16; // rcx
  ATL::Checked *v17; // rdi
  unsigned __int64 v19; // [rsp+20h] [rbp-58h]
  unsigned __int64 v21; // [rsp+20h] [rbp-58h]
  void *v22; // [rsp+28h] [rbp-50h]
  ATL::Checked *v23; // [rsp+30h] [rbp-48h]
  unsigned __int64 v25; // [rsp+38h] [rbp-40h]
  ATL::Checked *v35; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v25 = 2 * v6 + 2;
  v7 = 2 * v25;
  if ( !is_mul_ok(v25, 2u) )
    v7 = -1;
  try
  {
    v8 = (ATL::Checked *)operator new[](v7);
    v35 = v8;
  }
  catch ( ... )
  {
    v5 = this;
    v3 = a3;
    v4 = a2;
    v8 = v35;
  }
  try
  {
    v17 = v8;
    v23 = v8;
    v9 = -1;
    do
      ++v9;
    while ( v3[v9] );
    v22 = (void *)(2LL * ((int)v9 + 1));
    v10 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v22, 2u));
    v19 = (unsigned __int64)v10;
  }
  catch ( ... )
  {
    v5 = this;
    v3 = a3;
    v4 = a2;
    v8 = v35;
    v17 = v23;
    v10 = (ATL::Checked *)v19;
  }
  if ( v8
    && v10
    && (ATL::Checked::memcpy_s(v8, (void *)v25, (unsigned __int64)v4, (const void *)v25, v19),
        ATL::Checked::memcpy_s(v10, v22, (unsigned __int64)v3, v22, v21),
        v11 = 1,
        (v12 = _o__recalloc(*(_QWORD *)v5, *((_DWORD *)v5 + 4) + 1, 8)) != 0)
    && (*(_QWORD *)v5 = v12, (v13 = _o__recalloc(*((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8)) != 0) )
  {
    *((_QWORD *)v5 + 1) = v13;
    v14 = *((int *)v5 + 4);
    v15 = (ATL::Checked **)(*(_QWORD *)v5 + 8 * v14);
    if ( v15 )
      *v15 = v8;
    v16 = (ATL::Checked **)(*((_QWORD *)v5 + 1) + 8 * v14);
    if ( v16 )
      *v16 = v10;
    ++*((_DWORD *)v5 + 4);
    v17 = 0;
    v10 = 0;
  }
  else
  {
    v11 = 0;
  }
  operator delete(v10);
  operator delete(v17);
  return v11;
}

```

## disassembly

```asm
0x18000246c  mov     [rsp+arg_10], r8
0x180002471  mov     [rsp+arg_8], rdx
0x180002476  mov     [rsp+arg_0], rcx
0x18000247b  push    rbx
0x18000247c  push    rsi
0x18000247d  push    rdi
0x18000247e  push    r12
0x180002480  push    r13
0x180002482  push    r14
0x180002484  push    r15
0x180002486  sub     rsp, 40h
0x18000248a  mov     r12, r8
0x18000248d  mov     r13, rdx
0x180002490  mov     r14, rcx
0x180002493  xor     esi, esi
0x180002495  test    rdx, rdx
0x180002498  jz      loc_180002655
0x18000249e  test    r8, r8
0x1800024a1  jz      loc_180002655
0x1800024a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800024ab  mov     rax, rbx
0x1800024ae  inc     rax
0x1800024b1  cmp     [rdx+rax*2], si
0x1800024b5  jnz     short loc_1800024AE
0x1800024b7  lea     rcx, ds:2[rax*2]
0x1800024bf  mov     [rsp+78h+var_40], rcx
0x1800024c4  mov     [rsp+78h+arg_18], rsi
0x1800024cc  mov     eax, 2
0x1800024d1  mul     rcx
0x1800024d4  cmovb   rax, rbx
0x1800024d8  mov     rcx, rax; unsigned __int64
0x1800024db  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800024e0  mov     r15, rax
0x1800024e3  mov     [rsp+78h+arg_18], rax
0x1800024eb  jmp     short loc_180002513
0x1800024ed  xor     esi, esi
0x1800024ef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800024f3  mov     r14, [rsp+78h+arg_0]
0x1800024fb  mov     r12, [rsp+78h+arg_10]
0x180002503  mov     r13, [rsp+78h+arg_8]
0x18000250b  mov     r15, [rsp+78h+arg_18]
0x180002513  mov     rdi, r15
0x180002516  mov     [rsp+78h+var_48], r15
0x18000251b  mov     rcx, rbx
0x18000251e  inc     rcx
0x180002521  cmp     [r12+rcx*2], si
0x180002526  jnz     short loc_18000251E
0x180002528  inc     ecx
0x18000252a  movsxd  rcx, ecx
0x18000252d  add     rcx, rcx
0x180002530  mov     [rsp+78h+var_50], rcx
0x180002535  mov     [rsp+78h+var_58], rsi
0x18000253a  mov     eax, 2
0x18000253f  mul     rcx
0x180002542  cmovb   rax, rbx
0x180002546  mov     rcx, rax; unsigned __int64
0x180002549  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000254e  mov     rbx, rax
0x180002551  mov     [rsp+78h+var_58], rax
0x180002556  jmp     short loc_180002584
0x180002558  xor     esi, esi
0x18000255a  mov     r14, [rsp+78h+arg_0]
0x180002562  mov     r12, [rsp+78h+arg_10]
0x18000256a  mov     r13, [rsp+78h+arg_8]
0x180002572  mov     r15, [rsp+78h+arg_18]
0x18000257a  mov     rdi, [rsp+78h+var_48]
0x18000257f  mov     rbx, [rsp+78h+var_58]
0x180002584  mov     [rsp+78h+arg_8], rbx
0x18000258c  test    r15, r15
0x18000258f  jz      loc_18000263C
0x180002595  test    rbx, rbx
0x180002598  jz      loc_18000263C
0x18000259e  mov     rdx, [rsp+78h+var_40]; void *
0x1800025a3  mov     r9, rdx; void *
0x1800025a6  mov     r8, r13; unsigned __int64
0x1800025a9  mov     rcx, r15; this
0x1800025ac  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800025b1  mov     r9, [rsp+78h+var_50]; void *
0x1800025b6  mov     r8, r12; unsigned __int64
0x1800025b9  mov     rdx, r9; void *
0x1800025bc  mov     rcx, rbx; this
0x1800025bf  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800025c4  mov     eax, [r14+10h]
0x1800025c8  mov     r12d, 1
0x1800025ce  add     eax, r12d
0x1800025d1  movsxd  rdx, eax
0x1800025d4  lea     r13d, [r12+7]
0x1800025d9  mov     r8d, r13d
0x1800025dc  mov     rcx, [r14]
0x1800025df  call    cs:__imp__o__recalloc
0x1800025e5  test    rax, rax
0x1800025e8  jz      short loc_18000263C
0x1800025ea  mov     [r14], rax
0x1800025ed  mov     eax, [r14+10h]
0x1800025f1  add     eax, r12d
0x1800025f4  movsxd  rdx, eax
0x1800025f7  mov     r8d, r13d
0x1800025fa  mov     rcx, [r14+8]
0x1800025fe  call    cs:__imp__o__recalloc
0x180002604  test    rax, rax
0x180002607  jz      short loc_18000263C
0x180002609  mov     [r14+8], rax
0x18000260d  movsxd  rdx, dword ptr [r14+10h]
0x180002611  mov     rax, [r14]
0x180002614  lea     rcx, [rax+rdx*8]
0x180002618  test    rcx, rcx
0x18000261b  jz      short loc_180002620
0x18000261d  mov     [rcx], r15
0x180002620  mov     rax, [r14+8]
0x180002624  lea     rcx, [rax+rdx*8]
0x180002628  test    rcx, rcx
0x18000262b  jz      short loc_180002630
0x18000262d  mov     [rcx], rbx
0x180002630  add     [r14+10h], r12d
0x180002634  mov     rdi, rsi
0x180002637  mov     rbx, rsi
0x18000263a  jmp     short loc_18000263F
0x18000263c  mov     r12d, esi
0x18000263f  mov     rcx, rbx; Block
0x180002642  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002647  nop
0x180002648  mov     rcx, rdi; Block
0x18000264b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002650  mov     eax, r12d
0x180002653  jmp     short loc_180002657
0x180002655  xor     eax, eax
0x180002657  add     rsp, 40h
0x18000265b  pop     r15
0x18000265d  pop     r14
0x18000265f  pop     r13
0x180002661  pop     r12
0x180002663  pop     rdi
0x180002664  pop     rsi
0x180002665  pop     rbx
0x180002666  retn
```
