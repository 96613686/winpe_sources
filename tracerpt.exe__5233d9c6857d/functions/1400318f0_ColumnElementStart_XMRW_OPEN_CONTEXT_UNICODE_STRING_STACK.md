# ColumnElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x1400318f0`
- end: `0x140031c4c`
- name: `?ColumnElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `860`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140032dcc`

## callees

- `0x1400020f0`
- `0x140002730`
- `0x140016808`
- `0x140030694`
- `0x1400315c8`
- `0x1400318f0`
- `0x14003694c`
- `0x1400400d6`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ColumnElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // rdi
  int v5; // r15d
  __int64 v6; // rsi
  struct _UNICODE_STRING v7; // xmm0
  unsigned __int16 *v8; // rdx
  unsigned __int8 v9; // r12
  char v10; // al
  char *v11; // rax
  char *v12; // rbx
  char *v13; // r13
  int i; // eax
  unsigned int v15; // r15d
  _QWORD *v17; // rcx
  _DWORD *v18; // rcx
  _QWORD *v19; // rcx
  _DWORD *v20; // rcx
  int v21; // ecx
  struct _UNICODE_STRING v22; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v23; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+80h] [rbp+40h] BYREF
  int v25; // [rsp+90h] [rbp+50h] BYREF
  WCHAR *v26; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)a1 + 10);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  if ( !v2 || !a2 )
    return 0;
  v5 = *((_DWORD *)a1 + 12);
  v6 = *((_QWORD *)a1 + 3);
  if ( v5 == 5 )
  {
    v7 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
    v8 = L"EventTable";
  }
  else
  {
    if ( v5 != 6 )
      return 0;
    v7 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
    v8 = L"SubTable";
  }
  v22 = v7;
  if ( !EqualString(&v22, v8, 0) )
    return 0;
  if ( v5 == 6 && (v22 = *(struct _UNICODE_STRING *)((char *)a2 + 8), EqualString(&v22, L"SubTable", 0)) )
  {
    v9 = 1;
  }
  else
  {
    v10 = *(_BYTE *)(v2 + 681);
    if ( (v10 & 6) != 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 168LL))(v6, &v24);
      PrintMessage(0x441u, v24);
      return 3221745219LL;
    }
    v9 = 0;
    *(_BYTE *)(v2 + 681) = v10 | 1;
  }
  v11 = (char *)operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
    return 8;
  *((_QWORD *)v11 + 5) = 0;
  v11[48] = 0;
  *((_DWORD *)v11 + 4) = 31678523;
  *(_OWORD *)(v11 + 24) = 0;
  *((_DWORD *)v11 + 14) = 31678523;
  *((_QWORD *)v11 + 10) = 0;
  v11[88] = 0;
  *((_OWORD *)v11 + 4) = 0;
  *((_DWORD *)v11 + 24) = 31678523;
  *((_QWORD *)v11 + 15) = 0;
  v11[128] = 0;
  *(_OWORD *)(v11 + 104) = 0;
  *((_DWORD *)v11 + 34) = 31678523;
  *((_QWORD *)v11 + 20) = 0;
  v11[168] = 0;
  *((_OWORD *)v11 + 9) = 0;
  *((_DWORD *)v11 + 44) = 31678523;
  *((_QWORD *)v11 + 25) = 0;
  v11[208] = 0;
  v13 = v11 + 368;
  *(_OWORD *)(v11 + 184) = 0;
  *((_DWORD *)v11 + 92) = 0;
  v11[370] &= ~2u;
  v11[370] |= 2 * v9;
  *(_QWORD *)&v22.Length = v11 + 360;
  *((_DWORD *)v11 + 90) = 0;
  v11[368] = 72;
  *((_WORD *)v11 + 182) = 0;
  if ( v11 != (char *)-136LL )
  {
    *(_OWORD *)(v11 + 216) = 0;
    *((_QWORD *)v11 + 29) = 0;
    memset_0(v11 + 240, 0, 0x70u);
    *((_DWORD *)v12 + 88) = 0;
  }
  for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
        !i;
        i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 72LL))(v6) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v6 + 112LL))(v6, &v26, &v25);
    v23.Buffer = v26;
    v23.MaximumLength = 2 * v25;
    v23.Length = 2 * v25;
    v15 = ColumnAttributesCheck(a1, &v23, (struct _TRACERPT_COLUMN *)v12, v9);
    if ( v15 )
      goto LABEL_22;
  }
  if ( i >= 0 )
  {
    if ( *v13 >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 168LL))(v6, &v24);
      PrintMessage(0x3FCu, v24);
      _TRACERPT_COLUMN::~_TRACERPT_COLUMN((_TRACERPT_COLUMN *)v12);
      operator delete(v12);
      return 3221745169LL;
    }
    if ( v9 )
    {
      v17 = *(_QWORD **)(v2 + 592);
      if ( *v17 == v2 + 584 )
      {
        *((_QWORD *)v12 + 1) = v17;
        *(_QWORD *)v12 = v2 + 584;
        *v17 = v12;
        v18 = *(_DWORD **)&v22.Length;
        *(_QWORD *)(v2 + 592) = v12;
        *v18 = (*(_DWORD *)(v2 + 600))++;
LABEL_32:
        *((_QWORD *)a1 + 12) = v12;
        return 0;
      }
    }
    else
    {
      v19 = *(_QWORD **)(v2 + 24);
      if ( *v19 == v2 + 16 )
      {
        *(_QWORD *)v12 = v2 + 16;
        *((_QWORD *)v12 + 1) = v19;
        *v19 = v12;
        v20 = *(_DWORD **)&v22.Length;
        *(_QWORD *)(v2 + 24) = v12;
        *v20 = *(_DWORD *)(v2 + 32);
        v21 = *(_DWORD *)(v2 + 32);
        *(_DWORD *)(v2 + 32) = v21 + 1;
        if ( (*v13 & 0x10) != 0 )
        {
          ++*(_DWORD *)(v2 + 36);
          *(_DWORD *)(v2 + 48) = v21;
        }
        goto LABEL_32;
      }
    }
    __fastfail(3u);
  }
  v15 = i;
LABEL_22:
  _TRACERPT_COLUMN::~_TRACERPT_COLUMN((_TRACERPT_COLUMN *)v12);
  operator delete(v12);
  return v15;
}

```

## disassembly

```asm
0x1400318f0  mov     [rsp-38h+arg_8], rbx
0x1400318f5  push    rbp
0x1400318f6  push    rsi
0x1400318f7  push    rdi
0x1400318f8  push    r12
0x1400318fa  push    r13
0x1400318fc  push    r14
0x1400318fe  push    r15
0x140031900  mov     rbp, rsp
0x140031903  sub     rsp, 40h
0x140031907  mov     rdi, [rcx+50h]
0x14003190b  xor     r13d, r13d
0x14003190e  mov     [rbp+arg_18], r13
0x140031912  xorps   xmm0, xmm0
0x140031915  mov     [rbp+arg_10], r13d
0x140031919  mov     rbx, rdx
0x14003191c  mov     [rbp+arg_0], r13d
0x140031920  mov     r14, rcx
0x140031923  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x140031927  test    rdi, rdi
0x14003192a  jz      loc_140031C01
0x140031930  test    rdx, rdx
0x140031933  jz      loc_140031C01
0x140031939  mov     r15d, [rcx+30h]
0x14003193d  mov     rsi, [rcx+18h]
0x140031941  cmp     r15d, 5
0x140031945  jnz     short loc_140031954
0x140031947  movups  xmm0, xmmword ptr [rdx+8]
0x14003194b  lea     rdx, aEventtable; "EventTable"
0x140031952  jmp     short loc_140031969
0x140031954  cmp     r15d, 6
0x140031958  jnz     loc_140031C01
0x14003195e  movups  xmm0, xmmword ptr [rdx+8]
0x140031962  lea     rdx, aSubtable; "SubTable"
0x140031969  xor     r8d, r8d; unsigned __int8
0x14003196c  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x140031970  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x140031975  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003197a  test    al, al
0x14003197c  jz      loc_140031C01
0x140031982  cmp     r15d, 6
0x140031986  jnz     short loc_1400319AD
0x140031988  movups  xmm0, xmmword ptr [rbx+8]
0x14003198c  xor     r8d, r8d; unsigned __int8
0x14003198f  lea     rdx, aSubtable; "SubTable"
0x140031996  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x14003199a  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x14003199f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400319a4  test    al, al
0x1400319a6  jz      short loc_1400319AD
0x1400319a8  mov     r12b, 1
0x1400319ab  jmp     short loc_1400319C6
0x1400319ad  mov     al, [rdi+2A9h]
0x1400319b3  test    al, 6
0x1400319b5  jnz     loc_140031C22
0x1400319bb  or      al, 1
0x1400319bd  mov     r12b, r13b
0x1400319c0  mov     [rdi+2A9h], al
0x1400319c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400319cd  mov     ecx, 178h; unsigned __int64
0x1400319d2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400319d7  mov     rbx, rax
0x1400319da  test    rax, rax
0x1400319dd  jz      loc_140031C1B
0x1400319e3  mov     [rbx+28h], r13
0x1400319e7  lea     r15, [rbx+88h]
0x1400319ee  mov     [rbx+30h], r13b
0x1400319f2  mov     eax, 1E3603Bh
0x1400319f7  mov     [rbx+10h], eax
0x1400319fa  xorps   xmm0, xmm0
0x1400319fd  movups  xmmword ptr [rbx+18h], xmm0
0x140031a01  mov     [rbx+38h], eax
0x140031a04  mov     [rbx+50h], r13
0x140031a08  mov     [rbx+58h], r13b
0x140031a0c  movups  xmmword ptr [rbx+40h], xmm0
0x140031a10  mov     [rbx+60h], eax
0x140031a13  mov     [rbx+78h], r13
0x140031a17  mov     [rbx+80h], r13b
0x140031a1e  movups  xmmword ptr [rbx+68h], xmm0
0x140031a22  mov     [rbx+88h], eax
0x140031a28  mov     [rbx+0A0h], r13
0x140031a2f  mov     [rbx+0A8h], r13b
0x140031a36  movups  xmmword ptr [rbx+90h], xmm0
0x140031a3d  mov     [rbx+0B0h], eax
0x140031a43  mov     al, r12b
0x140031a46  mov     [rbx+0C8h], r13
0x140031a4d  add     al, al
0x140031a4f  mov     [rbx+0D0h], r13b
0x140031a56  lea     r13, [rbx+170h]
0x140031a5d  movups  xmmword ptr [rbx+0B8h], xmm0
0x140031a64  mov     dword ptr [r13+0], 0
0x140031a6c  and     byte ptr [rbx+172h], 0FDh
0x140031a73  or      [rbx+172h], al
0x140031a79  lea     rax, [rbx+168h]
0x140031a80  mov     qword ptr [rbp+var_20.Length], rax
0x140031a84  mov     dword ptr [rax], 0
0x140031a8a  xor     eax, eax
0x140031a8c  mov     byte ptr [r13+0], 48h ; 'H'
0x140031a91  mov     [rbx+16Ch], ax
0x140031a98  test    r15, r15
0x140031a9b  jz      short loc_140031AC0
0x140031a9d  movups  xmmword ptr [r15+50h], xmm0
0x140031aa2  lea     rcx, [r15+68h]; void *
0x140031aa6  mov     [r15+60h], rax
0x140031aaa  xor     edx, edx; Val
0x140031aac  lea     r8d, [rax+70h]; Size
0x140031ab0  call    memset_0
0x140031ab5  mov     dword ptr [r15+0D8h], 0
0x140031ac0  mov     rax, [rsi]
0x140031ac3  mov     rax, [rax+40h]
0x140031ac7  jmp     short loc_140031B1B
0x140031ac9  inc     dword ptr [r14+2Ch]
0x140031acd  lea     r8, [rbp+arg_10]
0x140031ad1  mov     rax, [rsi]
0x140031ad4  lea     rdx, [rbp+arg_18]
0x140031ad8  mov     rcx, rsi
0x140031adb  mov     rax, [rax+70h]
0x140031adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031ae4  mov     rax, [rbp+arg_18]
0x140031ae8  lea     rdx, [rbp+var_10]; struct _UNICODE_STRING *
0x140031aec  mov     [rbp+var_10.Buffer], rax
0x140031af0  mov     r9b, r12b; unsigned __int8
0x140031af3  movzx   eax, word ptr [rbp+arg_10]
0x140031af7  mov     r8, rbx; struct _TRACERPT_COLUMN *
0x140031afa  add     ax, ax
0x140031afd  mov     rcx, r14; struct _XMRW_OPEN_CONTEXT *
0x140031b00  mov     [rbp+var_10.MaximumLength], ax
0x140031b04  mov     [rbp+var_10.Length], ax
0x140031b08  call    ?ColumnAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@E@Z; ColumnAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *,uchar)
0x140031b0d  mov     r15d, eax
0x140031b10  test    eax, eax
0x140031b12  jnz     short loc_140031B2C
0x140031b14  mov     rax, [rsi]
0x140031b17  mov     rax, [rax+48h]
0x140031b1b  mov     rcx, rsi
0x140031b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031b23  test    eax, eax
0x140031b25  jz      short loc_140031AC9
0x140031b27  jns     short loc_140031B44
0x140031b29  mov     r15d, eax
0x140031b2c  mov     rcx, rbx; this
0x140031b2f  call    ??1_TRACERPT_COLUMN@@QEAA@XZ; _TRACERPT_COLUMN::~_TRACERPT_COLUMN(void)
0x140031b34  mov     rcx, rbx; Block
0x140031b37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140031b3c  mov     eax, r15d
0x140031b3f  jmp     loc_140031C03
0x140031b44  cmp     byte ptr [r13+0], 0
0x140031b49  jl      short loc_140031B85
0x140031b4b  mov     rax, [rsi]
0x140031b4e  lea     rdx, [rbp+arg_0]
0x140031b52  mov     rcx, rsi
0x140031b55  mov     rax, [rax+0A8h]
0x140031b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031b61  mov     edx, [rbp+arg_0]
0x140031b64  mov     ecx, 3FCh; unsigned int
0x140031b69  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031b6e  mov     rcx, rbx; this
0x140031b71  call    ??1_TRACERPT_COLUMN@@QEAA@XZ; _TRACERPT_COLUMN::~_TRACERPT_COLUMN(void)
0x140031b76  mov     rcx, rbx; Block
0x140031b79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140031b7e  mov     eax, 0C007EE11h
0x140031b83  jmp     short loc_140031C03
0x140031b85  test    r12b, r12b
0x140031b88  jz      short loc_140031BBC
0x140031b8a  lea     rax, [rdi+248h]
0x140031b91  mov     rcx, [rax+8]
0x140031b95  cmp     [rcx], rax
0x140031b98  jnz     short loc_140031BC9
0x140031b9a  mov     [rbx+8], rcx
0x140031b9e  mov     [rbx], rax
0x140031ba1  mov     [rcx], rbx
0x140031ba4  mov     rcx, qword ptr [rbp+var_20.Length]
0x140031ba8  mov     [rax+8], rbx
0x140031bac  mov     eax, [rdi+258h]
0x140031bb2  mov     [rcx], eax
0x140031bb4  inc     dword ptr [rdi+258h]
0x140031bba  jmp     short loc_140031BFD
0x140031bbc  lea     rax, [rdi+10h]
0x140031bc0  mov     rcx, [rax+8]
0x140031bc4  cmp     [rcx], rax
0x140031bc7  jz      short loc_140031BD0
0x140031bc9  mov     ecx, 3
0x140031bce  int     29h; Win8: RtlFailFast(ecx)
0x140031bd0  mov     [rbx], rax
0x140031bd3  mov     [rbx+8], rcx
0x140031bd7  mov     [rcx], rbx
0x140031bda  mov     rcx, qword ptr [rbp+var_20.Length]
0x140031bde  mov     [rax+8], rbx
0x140031be2  mov     eax, [rdi+20h]
0x140031be5  mov     [rcx], eax
0x140031be7  mov     ecx, [rdi+20h]
0x140031bea  lea     eax, [rcx+1]
0x140031bed  mov     [rdi+20h], eax
0x140031bf0  test    byte ptr [r13+0], 10h
0x140031bf5  jz      short loc_140031BFD
0x140031bf7  inc     dword ptr [rdi+24h]
0x140031bfa  mov     [rdi+30h], ecx
0x140031bfd  mov     [r14+60h], rbx
0x140031c01  xor     eax, eax
0x140031c03  mov     rbx, [rsp+40h+arg_8]
0x140031c0b  add     rsp, 40h
0x140031c0f  pop     r15
0x140031c11  pop     r14
0x140031c13  pop     r13
0x140031c15  pop     r12
0x140031c17  pop     rdi
0x140031c18  pop     rsi
0x140031c19  pop     rbp
0x140031c1a  retn
0x140031c1b  mov     eax, 8
0x140031c20  jmp     short loc_140031C03
0x140031c22  mov     rax, [rsi]
0x140031c25  lea     rdx, [rbp+arg_0]
0x140031c29  mov     rcx, rsi
0x140031c2c  mov     rax, [rax+0A8h]
0x140031c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031c38  mov     edx, [rbp+arg_0]
0x140031c3b  mov     ecx, 441h; unsigned int
0x140031c40  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031c45  mov     eax, 0C007EE43h
0x140031c4a  jmp     short loc_140031C03
```
