# CounterTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140032230`
- end: `0x14003247f`
- name: `?CounterTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x14003074c`
- `0x140031fb8`
- `0x140032230`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall CounterTableElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // r13
  __int64 v4; // rsi
  char *v5; // rax
  struct _TRACERPT_COUNTER_TABLE *v6; // rbx
  _BYTE *v7; // r15
  int i; // eax
  unsigned int v9; // r14d
  __int64 result; // rax
  struct _TRACERPT_COUNTER_TABLE **v11; // rcx
  struct _UNICODE_STRING v12; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+40h] BYREF
  int v15; // [rsp+90h] [rbp+50h] BYREF
  WCHAR *v16; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)a1 + 9);
  v16 = 0;
  v15 = 0;
  v14 = 0;
  v12 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 4 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v13 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v13, L"Section", 0) )
    return 0;
  v5 = (char *)operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (struct _TRACERPT_COUNTER_TABLE *)v5;
  if ( !v5 )
    return 8;
  *((_QWORD *)v5 + 9) = 0;
  v7 = v5 + 220;
  v5[80] = 0;
  *((_DWORD *)v5 + 12) = 31678523;
  *(_OWORD *)(v5 + 56) = 0;
  *((_DWORD *)v5 + 22) = 31678523;
  *((_QWORD *)v5 + 14) = 0;
  v5[120] = 0;
  *((_OWORD *)v5 + 6) = 0;
  *((_DWORD *)v5 + 32) = 31678523;
  *((_QWORD *)v5 + 19) = 0;
  v5[160] = 0;
  *(_OWORD *)(v5 + 136) = 0;
  *((_DWORD *)v5 + 42) = 31678523;
  *((_QWORD *)v5 + 24) = 0;
  v5[200] = 0;
  *((_OWORD *)v5 + 11) = 0;
  v5[222] |= 0x3Fu;
  *((_QWORD *)v5 + 3) = v5 + 16;
  *((_QWORD *)v5 + 2) = v5 + 16;
  *((_QWORD *)v5 + 5) = v5 + 32;
  *((_QWORD *)v5 + 4) = v5 + 32;
  *(_QWORD *)(v5 + 212) = 0;
  *((_DWORD *)v5 + 52) = 0;
  *((_WORD *)v5 + 110) = 0;
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
        !i;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v16, &v15);
    v12.Buffer = v16;
    v12.MaximumLength = 2 * v15;
    v12.Length = 2 * v15;
    v9 = CounterTableAttributesCheck(a1, &v12, v6);
    if ( v9 )
      goto LABEL_12;
  }
  if ( i < 0 )
  {
    v9 = i;
LABEL_12:
    _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(v6);
    operator delete(v6);
    return v9;
  }
  if ( (*v7 & 5) == 5 )
  {
    v11 = *(struct _TRACERPT_COUNTER_TABLE ***)(v2 + 40);
    if ( *v11 != (struct _TRACERPT_COUNTER_TABLE *)(v2 + 32) )
      __fastfail(3u);
    *(_QWORD *)v6 = v2 + 32;
    *((_QWORD *)v6 + 1) = v11;
    *v11 = v6;
    *(_QWORD *)(v2 + 40) = v6;
    result = 0;
    *((_QWORD *)a1 + 11) = v6;
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v14);
    if ( (*v7 & 1) == 0 )
      PrintMessage(0x3F9u, v14);
    if ( (*v7 & 4) == 0 )
      PrintMessage(0x402u, v14);
    _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(v6);
    operator delete(v6);
    return 3221745169LL;
  }
  return result;
}

```

## disassembly

```asm
0x140032230  mov     [rsp-38h+arg_8], rbx
0x140032235  push    rbp
0x140032236  push    rsi
0x140032237  push    rdi
0x140032238  push    r12
0x14003223a  push    r13
0x14003223c  push    r14
0x14003223e  push    r15
0x140032240  mov     rbp, rsp
0x140032243  sub     rsp, 40h
0x140032247  mov     r13, [rcx+48h]
0x14003224b  xor     r12d, r12d
0x14003224e  mov     [rbp+arg_18], r12
0x140032252  xorps   xmm0, xmm0
0x140032255  mov     [rbp+arg_10], r12d
0x140032259  mov     rdi, rcx
0x14003225c  mov     [rbp+arg_0], r12d
0x140032260  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140032264  test    r13, r13
0x140032267  jz      loc_140032465
0x14003226d  test    rdx, rdx
0x140032270  jz      loc_140032465
0x140032276  cmp     dword ptr [rcx+30h], 4
0x14003227a  jnz     loc_140032465
0x140032280  movups  xmm0, xmmword ptr [rdx+8]
0x140032284  mov     rsi, [rcx+18h]
0x140032288  lea     rdx, aSection_0; "Section"
0x14003228f  xor     r8d, r8d; unsigned __int8
0x140032292  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140032296  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003229b  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400322a0  test    al, al
0x1400322a2  jz      loc_140032465
0x1400322a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400322af  mov     ecx, 0E0h; unsigned __int64
0x1400322b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400322b9  mov     rbx, rax
0x1400322bc  test    rax, rax
0x1400322bf  jz      loc_14003245E
0x1400322c5  mov     [rbx+48h], r12
0x1400322c9  lea     r15, [rbx+0DCh]
0x1400322d0  mov     [rbx+50h], r12b
0x1400322d4  mov     eax, 1E3603Bh
0x1400322d9  mov     [rbx+30h], eax
0x1400322dc  xorps   xmm0, xmm0
0x1400322df  movups  xmmword ptr [rbx+38h], xmm0
0x1400322e3  mov     [rbx+58h], eax
0x1400322e6  mov     [rbx+70h], r12
0x1400322ea  mov     [rbx+78h], r12b
0x1400322ee  movups  xmmword ptr [rbx+60h], xmm0
0x1400322f2  mov     [rbx+80h], eax
0x1400322f8  mov     [rbx+98h], r12
0x1400322ff  mov     [rbx+0A0h], r12b
0x140032306  movups  xmmword ptr [rbx+88h], xmm0
0x14003230d  mov     [rbx+0A8h], eax
0x140032313  lea     rax, [rbx+10h]
0x140032317  mov     [rbx+0C0h], r12
0x14003231e  mov     [rbx+0C8h], r12b
0x140032325  movups  xmmword ptr [rbx+0B0h], xmm0
0x14003232c  or      byte ptr [rbx+0DEh], 3Fh
0x140032333  mov     [rax+8], rax
0x140032337  mov     [rax], rax
0x14003233a  lea     rax, [rbx+20h]
0x14003233e  mov     [rax+8], rax
0x140032342  mov     [rax], rax
0x140032345  mov     [rbx+0D4h], r12
0x14003234c  mov     [rbx+0D0h], r12d
0x140032353  mov     [r15], r12w
0x140032357  mov     rax, [rsi]
0x14003235a  mov     rax, [rax+40h]
0x14003235e  jmp     short loc_1400323AE
0x140032360  inc     dword ptr [rdi+2Ch]
0x140032363  lea     r8, [rbp+arg_10]
0x140032367  mov     rax, [rsi]
0x14003236a  lea     rdx, [rbp+arg_18]
0x14003236e  mov     rcx, rsi
0x140032371  mov     rax, [rax+70h]
0x140032375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003237a  mov     rax, [rbp+arg_18]
0x14003237e  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140032382  mov     [rbp+var_20.Buffer], rax
0x140032386  mov     r8, rbx; struct _TRACERPT_COUNTER_TABLE *
0x140032389  movzx   eax, word ptr [rbp+arg_10]
0x14003238d  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140032390  add     ax, ax
0x140032393  mov     [rbp+var_20.MaximumLength], ax
0x140032397  mov     [rbp+var_20.Length], ax
0x14003239b  call    ?CounterTableAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; CounterTableAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x1400323a0  mov     r14d, eax
0x1400323a3  test    eax, eax
0x1400323a5  jnz     short loc_1400323BF
0x1400323a7  mov     rax, [rsi]
0x1400323aa  mov     rax, [rax+48h]
0x1400323ae  mov     rcx, rsi
0x1400323b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400323b6  test    eax, eax
0x1400323b8  jz      short loc_140032360
0x1400323ba  jns     short loc_1400323D7
0x1400323bc  mov     r14d, eax
0x1400323bf  mov     rcx, rbx; this
0x1400323c2  call    ??1_TRACERPT_COUNTER_TABLE@@QEAA@XZ; _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(void)
0x1400323c7  mov     rcx, rbx; Block
0x1400323ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400323cf  mov     eax, r14d
0x1400323d2  jmp     loc_140032467
0x1400323d7  mov     al, [r15]
0x1400323da  and     al, 5
0x1400323dc  cmp     al, 5
0x1400323de  jnz     short loc_14003240B
0x1400323e0  lea     rax, [r13+20h]
0x1400323e4  mov     rcx, [rax+8]
0x1400323e8  cmp     [rcx], rax
0x1400323eb  jz      short loc_1400323F4
0x1400323ed  mov     ecx, 3
0x1400323f2  int     29h; Win8: RtlFailFast(ecx)
0x1400323f4  mov     [rbx], rax
0x1400323f7  mov     [rbx+8], rcx
0x1400323fb  mov     [rcx], rbx
0x1400323fe  mov     [rax+8], rbx
0x140032402  mov     eax, r12d
0x140032405  mov     [rdi+58h], rbx
0x140032409  jmp     short loc_140032467
0x14003240b  mov     rax, [rsi]
0x14003240e  lea     rdx, [rbp+arg_0]
0x140032412  mov     rcx, rsi
0x140032415  mov     rax, [rax+0A8h]
0x14003241c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032421  test    byte ptr [r15], 1
0x140032425  jnz     short loc_140032434
0x140032427  mov     edx, [rbp+arg_0]
0x14003242a  mov     ecx, 3F9h; unsigned int
0x14003242f  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140032434  test    byte ptr [r15], 4
0x140032438  jnz     short loc_140032447
0x14003243a  mov     edx, [rbp+arg_0]
0x14003243d  mov     ecx, 402h; unsigned int
0x140032442  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140032447  mov     rcx, rbx; this
0x14003244a  call    ??1_TRACERPT_COUNTER_TABLE@@QEAA@XZ; _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(void)
0x14003244f  mov     rcx, rbx; Block
0x140032452  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032457  mov     eax, 0C007EE11h
0x14003245c  jmp     short loc_140032467
0x14003245e  mov     eax, 8
0x140032463  jmp     short loc_140032467
0x140032465  xor     eax, eax
0x140032467  mov     rbx, [rsp+40h+arg_8]
0x14003246f  add     rsp, 40h
0x140032473  pop     r15
0x140032475  pop     r14
0x140032477  pop     r13
0x140032479  pop     r12
0x14003247b  pop     rdi
0x14003247c  pop     rsi
0x14003247d  pop     rbp
0x14003247e  retn
```
