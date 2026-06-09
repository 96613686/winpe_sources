# SectionElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140037364`
- end: `0x1400375b1`
- name: `?SectionElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x14002c4d4`
- `0x1400308a0`
- `0x14003694c`
- `0x140037214`
- `0x140037364`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall SectionElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // rdi
  __int64 v4; // r14
  char *v5; // rbx
  unsigned int v6; // eax
  int v7; // ecx
  _BYTE *v8; // r12
  int i; // eax
  unsigned int v10; // r15d
  _QWORD *v12; // rax
  struct _UNICODE_STRING v13; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v14; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+90h] [rbp+50h] BYREF
  WCHAR *v17; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)a1 + 8);
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v13 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 3 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v14 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v14, L"Sections", 0) )
    return 0;
  v5 = (char *)operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
    return 8;
  v6 = 64;
  v7 = 0;
  do
  {
    ++v7;
    v6 >>= 1;
  }
  while ( v6 );
  *((_DWORD *)v5 + 14) = v7;
  *((_QWORD *)v5 + 6) = &RptStringHashTable<256>::`vftable';
  v8 = v5 + 192;
  *((_QWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 11) = 0;
  *((_DWORD *)v5 + 26) = 31678523;
  *((_QWORD *)v5 + 16) = 0;
  v5[136] = 0;
  *((_OWORD *)v5 + 7) = 0;
  *((_DWORD *)v5 + 38) = 31678523;
  *((_QWORD *)v5 + 22) = 0;
  v5[184] = 0;
  *((_OWORD *)v5 + 10) = 0;
  v5[192] = 0;
  *((_QWORD *)v5 + 3) = v5 + 16;
  *((_QWORD *)v5 + 2) = v5 + 16;
  *((_QWORD *)v5 + 5) = v5 + 32;
  *((_QWORD *)v5 + 4) = v5 + 32;
  *((_DWORD *)v5 + 36) = 0;
  HashTable<RPT_TID,0,1>::Init(v5 + 48);
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
        !i;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v17, &v16);
    v13.Buffer = v17;
    v13.MaximumLength = 2 * v16;
    v13.Length = 2 * v16;
    v10 = SectionAttributesCheck(a1, &v13, (struct _TRACERPT_SECTION *)v5);
    if ( v10 )
      goto LABEL_14;
  }
  if ( i < 0 )
  {
    v10 = i;
LABEL_14:
    _TRACERPT_SECTION::~_TRACERPT_SECTION((_TRACERPT_SECTION *)v5);
    operator delete(v5);
    return v10;
  }
  if ( (*v8 & 3) == 3 )
  {
    v12 = *(_QWORD **)(v2 + 8);
    if ( *v12 != v2 )
      __fastfail(3u);
    *(_QWORD *)v5 = v2;
    *((_QWORD *)v5 + 1) = v12;
    *v12 = v5;
    *(_QWORD *)(v2 + 8) = v5;
    *((_QWORD *)a1 + 9) = v5;
    return 0;
  }
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v15);
  if ( (*v8 & 1) == 0 )
    PrintMessage(0x3F7u, v15);
  if ( (*v8 & 2) == 0 )
    PrintMessage(0x3FFu, v15);
  _TRACERPT_SECTION::~_TRACERPT_SECTION((_TRACERPT_SECTION *)v5);
  operator delete(v5);
  return 3221745169LL;
}

```

## disassembly

```asm
0x140037364  push    rbp
0x140037366  push    rbx
0x140037367  push    rsi
0x140037368  push    rdi
0x140037369  push    r12
0x14003736b  push    r14
0x14003736d  push    r15
0x14003736f  mov     rbp, rsp
0x140037372  sub     rsp, 40h
0x140037376  mov     rdi, [rcx+40h]
0x14003737a  xorps   xmm0, xmm0
0x14003737d  mov     [rbp+arg_18], 0
0x140037385  mov     rsi, rcx
0x140037388  mov     [rbp+arg_10], 0
0x14003738f  mov     [rbp+arg_0], 0
0x140037396  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14003739a  test    rdi, rdi
0x14003739d  jz      loc_140037544
0x1400373a3  test    rdx, rdx
0x1400373a6  jz      loc_140037544
0x1400373ac  cmp     dword ptr [rcx+30h], 3
0x1400373b0  jnz     loc_140037544
0x1400373b6  movups  xmm0, xmmword ptr [rdx+8]
0x1400373ba  mov     r14, [rcx+18h]
0x1400373be  lea     rdx, aSections; "Sections"
0x1400373c5  xor     r8d, r8d; unsigned __int8
0x1400373c8  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400373cc  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400373d1  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400373d6  test    al, al
0x1400373d8  jz      loc_140037544
0x1400373de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400373e5  mov     ecx, 0C8h; unsigned __int64
0x1400373ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400373ef  mov     rbx, rax
0x1400373f2  test    rax, rax
0x1400373f5  jz      loc_1400375AA
0x1400373fb  mov     eax, 40h ; '@'
0x140037400  xor     ecx, ecx
0x140037402  inc     ecx
0x140037404  shr     eax, 1
0x140037406  jnz     short loc_140037402
0x140037408  mov     [rbx+38h], ecx
0x14003740b  lea     rax, ??_7?$RptStringHashTable@$0BAA@@@6B@; const RptStringHashTable<256>::`vftable'
0x140037412  mov     [rbx+30h], rax
0x140037416  lea     r12, [rbx+0C0h]
0x14003741d  mov     qword ptr [rbx+60h], 0
0x140037425  lea     rcx, [rbx+30h]
0x140037429  mov     qword ptr [rbx+58h], 0
0x140037431  mov     eax, 1E3603Bh
0x140037436  mov     [rbx+68h], eax
0x140037439  xorps   xmm0, xmm0
0x14003743c  mov     qword ptr [rbx+80h], 0
0x140037447  mov     byte ptr [rbx+88h], 0
0x14003744e  movups  xmmword ptr [rbx+70h], xmm0
0x140037452  mov     [rbx+98h], eax
0x140037458  lea     rax, [rbx+10h]
0x14003745c  mov     qword ptr [rbx+0B0h], 0
0x140037467  mov     byte ptr [rbx+0B8h], 0
0x14003746e  movups  xmmword ptr [rbx+0A0h], xmm0
0x140037475  mov     byte ptr [r12], 0
0x14003747a  mov     [rax+8], rax
0x14003747e  mov     [rax], rax
0x140037481  lea     rax, [rbx+20h]
0x140037485  mov     [rax+8], rax
0x140037489  mov     [rax], rax
0x14003748c  mov     dword ptr [rbx+90h], 0
0x140037496  call    ?Init@?$HashTable@VRPT_TID@@$0A@$00@@QEAAKXZ; HashTable<RPT_TID,0,1>::Init(void)
0x14003749b  mov     rax, [r14]
0x14003749e  mov     rax, [rax+40h]
0x1400374a2  jmp     short loc_1400374F2
0x1400374a4  inc     dword ptr [rsi+2Ch]
0x1400374a7  lea     r8, [rbp+arg_10]
0x1400374ab  mov     rax, [r14]
0x1400374ae  lea     rdx, [rbp+arg_18]
0x1400374b2  mov     rcx, r14
0x1400374b5  mov     rax, [rax+70h]
0x1400374b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374be  mov     rax, [rbp+arg_18]
0x1400374c2  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x1400374c6  mov     [rbp+var_20.Buffer], rax
0x1400374ca  mov     r8, rbx; struct _TRACERPT_SECTION *
0x1400374cd  movzx   eax, word ptr [rbp+arg_10]
0x1400374d1  mov     rcx, rsi; struct _XMRW_OPEN_CONTEXT *
0x1400374d4  add     ax, ax
0x1400374d7  mov     [rbp+var_20.MaximumLength], ax
0x1400374db  mov     [rbp+var_20.Length], ax
0x1400374df  call    ?SectionAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_SECTION@@@Z; SectionAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_SECTION *)
0x1400374e4  mov     r15d, eax
0x1400374e7  test    eax, eax
0x1400374e9  jnz     short loc_140037503
0x1400374eb  mov     rax, [r14]
0x1400374ee  mov     rax, [rax+48h]
0x1400374f2  mov     rcx, r14
0x1400374f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374fa  test    eax, eax
0x1400374fc  jz      short loc_1400374A4
0x1400374fe  jns     short loc_140037518
0x140037500  mov     r15d, eax
0x140037503  mov     rcx, rbx; this
0x140037506  call    ??1_TRACERPT_SECTION@@QEAA@XZ; _TRACERPT_SECTION::~_TRACERPT_SECTION(void)
0x14003750b  mov     rcx, rbx; Block
0x14003750e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140037513  mov     eax, r15d
0x140037516  jmp     short loc_140037546
0x140037518  mov     al, [r12]
0x14003751c  and     al, 3
0x14003751e  cmp     al, 3
0x140037520  jnz     short loc_140037555
0x140037522  mov     rax, [rdi+8]
0x140037526  cmp     [rax], rdi
0x140037529  jz      short loc_140037532
0x14003752b  mov     ecx, 3
0x140037530  int     29h; Win8: RtlFailFast(ecx)
0x140037532  mov     [rbx], rdi
0x140037535  mov     [rbx+8], rax
0x140037539  mov     [rax], rbx
0x14003753c  mov     [rdi+8], rbx
0x140037540  mov     [rsi+48h], rbx
0x140037544  xor     eax, eax
0x140037546  add     rsp, 40h
0x14003754a  pop     r15
0x14003754c  pop     r14
0x14003754e  pop     r12
0x140037550  pop     rdi
0x140037551  pop     rsi
0x140037552  pop     rbx
0x140037553  pop     rbp
0x140037554  retn
0x140037555  mov     rax, [r14]
0x140037558  lea     rdx, [rbp+arg_0]
0x14003755c  mov     rcx, r14
0x14003755f  mov     rax, [rax+0A8h]
0x140037566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003756b  test    byte ptr [r12], 1
0x140037570  jnz     short loc_14003757F
0x140037572  mov     edx, [rbp+arg_0]
0x140037575  mov     ecx, 3F7h; unsigned int
0x14003757a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003757f  test    byte ptr [r12], 2
0x140037584  jnz     short loc_140037593
0x140037586  mov     edx, [rbp+arg_0]
0x140037589  mov     ecx, 3FFh; unsigned int
0x14003758e  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140037593  mov     rcx, rbx; this
0x140037596  call    ??1_TRACERPT_SECTION@@QEAA@XZ; _TRACERPT_SECTION::~_TRACERPT_SECTION(void)
0x14003759b  mov     rcx, rbx; Block
0x14003759e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400375a3  mov     eax, 0C007EE11h
0x1400375a8  jmp     short loc_140037546
0x1400375aa  mov     eax, 8
0x1400375af  jmp     short loc_140037546
```
