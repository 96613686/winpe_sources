# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1400021e4`
- end: `0x14000233f`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `347`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400023c0`
- `0x14000550c`
- `0x140005834`

## callees

- `0x140001110`
- `0x14000115c`
- `0x1400021e4`
- `0x140005bb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400022bb`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400022d8`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400022bb`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400022d8`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  void *v7; // r12
  ATL::Checked *v8; // rdi
  __int64 v9; // rcx
  void *v10; // r15
  ATL::Checked *v11; // rax
  ATL::Checked *v12; // rbx
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  ATL::Checked **v18; // rcx
  ATL::Checked **v19; // rcx
  unsigned __int64 v21; // [rsp+20h] [rbp-48h]
  unsigned __int64 v22; // [rsp+20h] [rbp-48h]

  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = (void *)(2 * v6 + 2);
  v8 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v7, 2u));
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = (void *)(2LL * ((int)v9 + 1));
  v11 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v10, 2u));
  v12 = v11;
  if ( v8
    && v11
    && (ATL::Checked::memcpy_s(v8, v7, (unsigned __int64)a2, v7, v21),
        ATL::Checked::memcpy_s(v12, v10, (unsigned __int64)a3, v10, v22),
        v13 = 1,
        (v14 = _o__recalloc(*(_QWORD *)this, *((_DWORD *)this + 4) + 1, 8)) != 0)
    && (v15 = *((_QWORD *)this + 1), *(_QWORD *)this = v14, (v16 = _o__recalloc(v15, *((_DWORD *)this + 4) + 1, 8)) != 0) )
  {
    v17 = *((int *)this + 4);
    *((_QWORD *)this + 1) = v16;
    v18 = (ATL::Checked **)(*(_QWORD *)this + 8 * v17);
    if ( v18 )
      *v18 = v8;
    v19 = (ATL::Checked **)(*((_QWORD *)this + 1) + 8 * v17);
    if ( v19 )
      *v19 = v12;
    ++*((_DWORD *)this + 4);
    v8 = 0;
    v12 = 0;
  }
  else
  {
    v13 = 0;
  }
  operator delete(v12);
  operator delete(v8);
  return v13;
}

```

## disassembly

```asm
0x1400021e4  push    rbx
0x1400021e6  push    rbp
0x1400021e7  push    rsi
0x1400021e8  push    rdi
0x1400021e9  push    r12
0x1400021eb  push    r13
0x1400021ed  push    r14
0x1400021ef  push    r15
0x1400021f1  sub     rsp, 28h
0x1400021f5  xor     r13d, r13d
0x1400021f8  mov     rbp, r8
0x1400021fb  mov     r14, rdx
0x1400021fe  mov     rsi, rcx
0x140002201  test    rdx, rdx
0x140002204  jz      loc_14000232C
0x14000220a  test    r8, r8
0x14000220d  jz      loc_14000232C
0x140002213  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140002217  mov     rax, rbx
0x14000221a  inc     rax
0x14000221d  cmp     [rdx+rax*2], r13w
0x140002222  jnz     short loc_14000221A
0x140002224  lea     r12, ds:2[rax*2]
0x14000222c  mov     eax, 2
0x140002231  mul     r12
0x140002234  cmovb   rax, rbx
0x140002238  mov     rcx, rax; unsigned __int64
0x14000223b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002240  mov     rdi, rax
0x140002243  mov     rcx, rbx
0x140002246  inc     rcx
0x140002249  cmp     [rbp+rcx*2+0], r13w
0x14000224f  jnz     short loc_140002246
0x140002251  inc     ecx
0x140002253  mov     eax, 2
0x140002258  movsxd  r15, ecx
0x14000225b  add     r15, r15
0x14000225e  mul     r15
0x140002261  cmovb   rax, rbx
0x140002265  mov     rcx, rax; unsigned __int64
0x140002268  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000226d  mov     rbx, rax
0x140002270  test    rdi, rdi
0x140002273  jz      loc_140002315
0x140002279  test    rax, rax
0x14000227c  jz      loc_140002315
0x140002282  mov     r9, r12; void *
0x140002285  mov     r8, r14; unsigned __int64
0x140002288  mov     rdx, r12; void *
0x14000228b  mov     rcx, rdi; this
0x14000228e  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x140002293  mov     r9, r15; void *
0x140002296  mov     r8, rbp; unsigned __int64
0x140002299  mov     rdx, r15; void *
0x14000229c  mov     rcx, rbx; this
0x14000229f  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1400022a4  mov     eax, [rsi+10h]
0x1400022a7  mov     ebp, 1
0x1400022ac  mov     rcx, [rsi]
0x1400022af  add     eax, ebp
0x1400022b1  movsxd  rdx, eax
0x1400022b4  lea     r14d, [rbp+7]
0x1400022b8  mov     r8d, r14d
0x1400022bb  call    cs:__imp__o__recalloc
0x1400022c1  test    rax, rax
0x1400022c4  jz      short loc_140002315
0x1400022c6  mov     rcx, [rsi+8]
0x1400022ca  mov     r8d, r14d
0x1400022cd  mov     [rsi], rax
0x1400022d0  mov     eax, [rsi+10h]
0x1400022d3  add     eax, ebp
0x1400022d5  movsxd  rdx, eax
0x1400022d8  call    cs:__imp__o__recalloc
0x1400022de  test    rax, rax
0x1400022e1  jz      short loc_140002315
0x1400022e3  movsxd  rdx, dword ptr [rsi+10h]
0x1400022e7  mov     [rsi+8], rax
0x1400022eb  mov     rax, [rsi]
0x1400022ee  lea     rcx, [rax+rdx*8]
0x1400022f2  test    rcx, rcx
0x1400022f5  jz      short loc_1400022FA
0x1400022f7  mov     [rcx], rdi
0x1400022fa  mov     rax, [rsi+8]
0x1400022fe  lea     rcx, [rax+rdx*8]
0x140002302  test    rcx, rcx
0x140002305  jz      short loc_14000230A
0x140002307  mov     [rcx], rbx
0x14000230a  add     [rsi+10h], ebp
0x14000230d  mov     rdi, r13
0x140002310  mov     rbx, r13
0x140002313  jmp     short loc_140002318
0x140002315  mov     ebp, r13d
0x140002318  mov     rcx, rbx; Block
0x14000231b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002320  mov     rcx, rdi; Block
0x140002323  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002328  mov     eax, ebp
0x14000232a  jmp     short loc_14000232E
0x14000232c  xor     eax, eax
0x14000232e  add     rsp, 28h
0x140002332  pop     r15
0x140002334  pop     r14
0x140002336  pop     r13
0x140002338  pop     r12
0x14000233a  pop     rdi
0x14000233b  pop     rsi
0x14000233c  pop     rbp
0x14000233d  pop     rbx
0x14000233e  retn
```
