# tpm12class::TPMW8_AUTH_PROVIDER::SymSign(uchar,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *,uchar,tpm12class::TPMW82B_BUFFER *)

- ea: `0x140037588`
- end: `0x140037890`
- name: `?SymSign@TPMW8_AUTH_PROVIDER@tpm12class@@AEAAJEPEAVTPMW82B_BUFFER@2@00E0@Z`
- size: `776`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_AUTH_PROVIDER *__hidden this, unsigned __int8, struct tpm12class::TPMW82B_BUFFER *, struct tpm12class::TPMW82B_BUFFER *, struct tpm12class::TPMW82B_BUFFER *, char, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1400355c4`
- `0x1400357dc`
- `0x1400378f0`

## callees

- `0x14000cb50`
- `0x14000da40`
- `0x140031090`
- `0x140031284`
- `0x140031554`
- `0x1400323b8`
- `0x140037588`
- `0x140039840`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_AUTH_PROVIDER::SymSign(
        tpm12class::TPMW8_AUTH_PROVIDER *this,
        char a2,
        struct tpm12class::TPMW82B_BUFFER *a3,
        struct tpm12class::TPMW82B_BUFFER *a4,
        struct tpm12class::TPMW82B_BUFFER *a5,
        char a6,
        struct tpm12class::TPMW82B_BUFFER *a7)
{
  int v11; // ebx
  char *v12; // rsi
  unsigned int v13; // edi
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  unsigned __int16 *v17; // r12
  int v18; // ecx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  char *v22; // rax
  __int64 v23; // rbx
  const struct tpm12class::TPMW82B_BUFFER *v24; // rdx
  int v25; // eax
  int v26; // eax
  _QWORD v27[3]; // [rsp+60h] [rbp-51h] BYREF
  int v28; // [rsp+78h] [rbp-39h]
  __int64 v29; // [rsp+80h] [rbp-31h]
  __int64 v30; // [rsp+88h] [rbp-29h]
  char v31; // [rsp+90h] [rbp-21h]
  unsigned __int16 v32; // [rsp+98h] [rbp-19h]
  unsigned __int8 *v33; // [rsp+A0h] [rbp-11h]
  unsigned int v35; // [rsp+130h] [rbp+7Fh]

  v27[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v27[1] = 0;
  v27[2] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( !a7 )
  {
    v11 = -2147024809;
    goto LABEL_29;
  }
  v12 = 0;
  if ( !a3 || !*((_WORD *)a3 + 28) )
  {
    if ( (!a4 || !*((_WORD *)a4 + 28)) && (!a5 || !*((_WORD *)a5 + 28)) && !a6 )
    {
      v11 = tpm12class::TPMW82B_BUFFER::CopyFrom(a7, (tpm12class::TPMW8_AUTH_PROVIDER *)((char *)this + 8));
      v13 = 0;
      goto LABEL_50;
    }
    if ( !a3 )
      goto LABEL_23;
  }
  if ( !a4 || !a5 )
    goto LABEL_23;
  v14 = *((unsigned __int16 *)this + 185) - 4;
  if ( v14 )
  {
    v15 = v14 - 7;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
        {
LABEL_23:
          v11 = -2147024809;
          v13 = 0;
LABEL_24:
          tpm12class::TPMW82B_BUFFER::Empty(a7);
          goto LABEL_25;
        }
        v17 = L"SHA512";
        v18 = 64;
      }
      else
      {
        v17 = L"SHA384";
        v18 = 48;
      }
    }
    else
    {
      v17 = L"SHA256";
      v18 = 32;
    }
  }
  else
  {
    v17 = L"SHA1";
    v18 = 20;
  }
  if ( *((unsigned __int16 *)a7 + 28) != v18 )
    goto LABEL_23;
  v35 = *((unsigned __int16 *)a3 + 28) + *((unsigned __int16 *)a4 + 28) + *((unsigned __int16 *)a5 + 28) + 1;
  v22 = (char *)operator new(v35);
  v12 = v22;
  if ( !v22 )
  {
    v13 = v35;
    v11 = -2147024888;
    goto LABEL_24;
  }
  memset(v22, 0, v35);
  memmove(v12, *((const void **)a3 + 8), *((unsigned __int16 *)a3 + 28));
  v23 = *((unsigned __int16 *)a3 + 28);
  memmove(&v12[v23], *((const void **)a4 + 8), *((unsigned __int16 *)a4 + 28));
  LODWORD(v23) = *((unsigned __int16 *)a4 + 28) + (_DWORD)v23;
  memmove(&v12[(unsigned int)v23], *((const void **)a5 + 8), *((unsigned __int16 *)a5 + 28));
  v12[(unsigned int)v23 + *((unsigned __int16 *)a5 + 28)] = a6;
  if ( *((_WORD *)this + 140) )
  {
    v11 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v27,
            (tpm12class::TPMW8_AUTH_PROVIDER *)((char *)this + 224));
    if ( v11 < 0 )
    {
LABEL_49:
      v13 = v35;
      goto LABEL_50;
    }
    if ( !*((_WORD *)this + 68) )
      goto LABEL_41;
    v25 = tpm12class::TPMW82B_BUFFER::Append(
            (tpm12class::TPMW82B_BUFFER *)v27,
            (tpm12class::TPMW8_AUTH_PROVIDER *)((char *)this + 80));
  }
  else
  {
    v24 = (tpm12class::TPMW8_AUTH_PROVIDER *)((char *)this + 8);
    if ( a2 && *((_BYTE *)this + 368) )
      v24 = (tpm12class::TPMW8_AUTH_PROVIDER *)((char *)this + 296);
    v25 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v27, v24);
  }
  v11 = v25;
  if ( v25 < 0 )
    goto LABEL_49;
LABEL_41:
  v13 = v35;
  v26 = PlatformHash(
          v17,
          (unsigned __int8 *)v12,
          v35,
          v33,
          v32,
          *((unsigned __int8 **)a7 + 8),
          *((unsigned __int16 *)a7 + 28),
          (unsigned int *)a7 + 14,
          8u);
  if ( v26 )
  {
    if ( (v26 & 0xFFFF000) == 0x290000 )
    {
      v11 = v26 & 0xFFF | 0x80280000;
    }
    else if ( (v26 & 0xFFF0000) == 0x70000 )
    {
      v11 = (unsigned __int16)v26;
      if ( !(_WORD)v26 )
        goto LABEL_25;
      v11 = (unsigned __int16)v26 | 0x80070000;
    }
    else
    {
      v11 = v26 | 0x10000000;
    }
  }
  else
  {
    v11 = 0;
  }
LABEL_50:
  if ( v11 )
    goto LABEL_24;
LABEL_25:
  if ( v12 )
  {
    v19 = v13;
    v20 = v12;
    if ( v13 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    TpmFree(v12);
  }
LABEL_29:
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140037588  mov     [rsp-8+arg_8], dl
0x14003758c  push    rbp
0x14003758d  push    rbx
0x14003758e  push    rsi
0x14003758f  push    rdi
0x140037590  push    r12
0x140037592  push    r13
0x140037594  push    r14
0x140037596  push    r15
0x140037598  lea     rbp, [rsp-7]
0x14003759d  sub     rsp, 0B8h
0x1400375a4  mov     r13, [rbp+3Fh+arg_30]
0x1400375a8  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x1400375af  xor     r12d, r12d
0x1400375b2  mov     [rbp+3Fh+var_90], rax
0x1400375b6  mov     [rbp+3Fh+var_88], r12
0x1400375ba  mov     r15, r9
0x1400375bd  mov     [rbp+3Fh+var_80], r12
0x1400375c1  mov     rbx, r8
0x1400375c4  mov     [rbp+3Fh+var_78], r12d
0x1400375c8  mov     rdi, rcx
0x1400375cb  mov     [rbp+3Fh+var_70], r12
0x1400375cf  mov     [rbp+3Fh+var_68], r12
0x1400375d3  mov     [rbp+3Fh+var_60], r12b
0x1400375d7  mov     [rbp+3Fh+var_58], r12w
0x1400375dc  mov     [rbp+3Fh+var_50], r12
0x1400375e0  test    r13, r13
0x1400375e3  jnz     short loc_1400375EF
0x1400375e5  mov     ebx, 80070057h
0x1400375ea  jmp     loc_1400376D2
0x1400375ef  mov     r14, [rbp+3Fh+arg_20]
0x1400375f3  mov     rsi, r12
0x1400375f6  test    rbx, rbx
0x1400375f9  jz      short loc_140037602
0x1400375fb  cmp     [r8+38h], r12w
0x140037600  jnz     short loc_14003763A
0x140037602  test    r15, r15
0x140037605  jz      short loc_14003760E
0x140037607  cmp     [r9+38h], r12w
0x14003760c  jnz     short loc_140037635
0x14003760e  test    r14, r14
0x140037611  jz      short loc_14003761A
0x140037613  cmp     [r14+38h], r12w
0x140037618  jnz     short loc_140037635
0x14003761a  cmp     [rbp+3Fh+arg_28], r12b
0x14003761e  jnz     short loc_140037635
0x140037620  lea     rdx, [rcx+8]; struct tpm12class::TPMW82B_BUFFER *
0x140037624  mov     rcx, r13; this
0x140037627  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x14003762c  mov     ebx, eax
0x14003762e  mov     edi, esi
0x140037630  jmp     loc_140037883
0x140037635  test    rbx, rbx
0x140037638  jz      short loc_1400376A1
0x14003763a  test    r15, r15
0x14003763d  jz      short loc_1400376A1
0x14003763f  test    r14, r14
0x140037642  jz      short loc_1400376A1
0x140037644  movzx   ecx, word ptr [rcx+172h]
0x14003764b  sub     ecx, 4
0x14003764e  jz      short loc_140037689
0x140037650  sub     ecx, 7
0x140037653  jz      short loc_14003767B
0x140037655  sub     ecx, 1
0x140037658  jz      short loc_14003766D
0x14003765a  cmp     ecx, 1
0x14003765d  jnz     short loc_1400376A1
0x14003765f  lea     r12, aSha512; "SHA512"
0x140037666  mov     ecx, 40h ; '@'
0x14003766b  jmp     short loc_140037695
0x14003766d  lea     r12, aSha384; "SHA384"
0x140037674  mov     ecx, 30h ; '0'
0x140037679  jmp     short loc_140037695
0x14003767b  lea     r12, aSha256; "SHA256"
0x140037682  mov     ecx, 20h ; ' '
0x140037687  jmp     short loc_140037695
0x140037689  lea     r12, aSha1; "SHA1"
0x140037690  mov     ecx, 14h
0x140037695  movzx   eax, word ptr [r13+38h]
0x14003769a  cmp     eax, ecx
0x14003769c  jz      short loc_1400376F2
0x14003769e  xor     r12d, r12d
0x1400376a1  mov     ebx, 80070057h
0x1400376a6  mov     edi, esi
0x1400376a8  mov     rcx, r13; this
0x1400376ab  call    ?Empty@TPMW82B_BUFFER@tpm12class@@QEAAJXZ; tpm12class::TPMW82B_BUFFER::Empty(void)
0x1400376b0  test    rsi, rsi
0x1400376b3  jz      short loc_1400376D2
0x1400376b5  mov     eax, edi
0x1400376b7  mov     rcx, rsi
0x1400376ba  test    edi, edi
0x1400376bc  jz      short loc_1400376CA
0x1400376be  mov     [rcx], r12b
0x1400376c1  inc     rcx
0x1400376c4  sub     rax, 1
0x1400376c8  jnz     short loc_1400376BE
0x1400376ca  mov     rcx, rsi; void *
0x1400376cd  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x1400376d2  lea     rcx, [rbp+3Fh+var_90]; this
0x1400376d6  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400376db  mov     eax, ebx
0x1400376dd  add     rsp, 0B8h
0x1400376e4  pop     r15
0x1400376e6  pop     r14
0x1400376e8  pop     r13
0x1400376ea  pop     r12
0x1400376ec  pop     rdi
0x1400376ed  pop     rsi
0x1400376ee  pop     rbx
0x1400376ef  pop     rbp
0x1400376f0  retn
0x1400376f2  movzx   eax, word ptr [r8+38h]
0x1400376f7  movzx   ecx, word ptr [r9+38h]
0x1400376fc  add     ecx, eax
0x1400376fe  movzx   eax, word ptr [r14+38h]
0x140037703  inc     eax
0x140037705  add     eax, ecx
0x140037707  mov     ecx, eax; unsigned __int64
0x140037709  mov     dword ptr [rbp+3Fh+arg_30], eax
0x14003770c  mov     [rbp+3Fh+Size], rax
0x140037710  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140037715  mov     rsi, rax
0x140037718  test    rax, rax
0x14003771b  jnz     short loc_14003772D
0x14003771d  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x140037720  mov     ebx, 80070008h
0x140037725  xor     r12d, r12d
0x140037728  jmp     loc_1400376A8
0x14003772d  mov     r8, [rbp+3Fh+Size]; Size
0x140037731  xor     edx, edx; Val
0x140037733  mov     rcx, rsi; void *
0x140037736  call    memset
0x14003773b  movzx   r8d, word ptr [rbx+38h]; Size
0x140037740  mov     rcx, rsi; void *
0x140037743  mov     rdx, [rbx+40h]; Src
0x140037747  call    memmove
0x14003774c  movzx   ebx, word ptr [rbx+38h]
0x140037750  movzx   r8d, word ptr [r15+38h]; Size
0x140037755  mov     rdx, [r15+40h]; Src
0x140037759  lea     rcx, [rsi+rbx]; void *
0x14003775d  call    memmove
0x140037762  movzx   ecx, word ptr [r15+38h]
0x140037767  movzx   r8d, word ptr [r14+38h]; Size
0x14003776c  add     ebx, ecx
0x14003776e  mov     rdx, [r14+40h]; Src
0x140037772  mov     ecx, ebx
0x140037774  add     rcx, rsi; void *
0x140037777  call    memmove
0x14003777c  movzx   eax, word ptr [r14+38h]
0x140037781  lea     rdx, [rdi+0E0h]; struct tpm12class::TPMW82B_BUFFER *
0x140037788  mov     cl, [rbp+3Fh+arg_28]
0x14003778b  add     eax, ebx
0x14003778d  xor     r14d, r14d
0x140037790  mov     [rax+rsi], cl
0x140037793  cmp     [rdx+38h], r14w
0x140037798  jnz     short loc_1400377BF
0x14003779a  lea     rdx, [rdi+8]
0x14003779e  cmp     [rbp+3Fh+arg_8], r14b
0x1400377a2  jz      short loc_1400377B4
0x1400377a4  cmp     [rdi+170h], r14b
0x1400377ab  jz      short loc_1400377B4
0x1400377ad  lea     rdx, [rdi+128h]; struct tpm12class::TPMW82B_BUFFER *
0x1400377b4  lea     rcx, [rbp+3Fh+var_90]; this
0x1400377b8  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1400377bd  jmp     short loc_1400377E6
0x1400377bf  lea     rcx, [rbp+3Fh+var_90]; this
0x1400377c3  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1400377c8  mov     ebx, eax
0x1400377ca  test    eax, eax
0x1400377cc  js      loc_14003787D
0x1400377d2  lea     rdx, [rdi+50h]; struct tpm12class::TPMW82B_BUFFER *
0x1400377d6  cmp     [rdx+38h], r14w
0x1400377db  jz      short loc_1400377F0
0x1400377dd  lea     rcx, [rbp+3Fh+var_90]; this
0x1400377e1  call    ?Append@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::Append(tpm12class::TPMW82B_BUFFER const *)
0x1400377e6  mov     ebx, eax
0x1400377e8  test    eax, eax
0x1400377ea  js      loc_14003787D
0x1400377f0  movzx   edx, [rbp+3Fh+var_58]
0x1400377f4  lea     rcx, [r13+38h]
0x1400377f8  movzx   eax, word ptr [rcx]
0x1400377fb  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x1400377fe  mov     r8d, edi; unsigned int
0x140037801  mov     r9, [rbp+3Fh+var_50]; unsigned __int8 *
0x140037805  mov     [rsp+0F0h+var_B0], 8; unsigned int
0x14003780d  mov     [rsp+0F0h+var_B8], rcx; unsigned int *
0x140037812  mov     rcx, r12; unsigned __int16 *
0x140037815  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x140037819  mov     rax, [r13+40h]
0x14003781d  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x140037822  mov     [rsp+0F0h+var_D0], edx; unsigned int
0x140037826  mov     rdx, rsi; unsigned __int8 *
0x140037829  call    ?PlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; PlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14003782e  xor     r12d, r12d
0x140037831  mov     ebx, eax
0x140037833  test    eax, eax
0x140037835  jnz     short loc_14003783C
0x140037837  mov     ebx, r12d
0x14003783a  jmp     short loc_140037883
0x14003783c  and     eax, 0FFFF000h
0x140037841  cmp     eax, 290000h
0x140037846  jnz     short loc_140037856
0x140037848  and     ebx, 0FFFh
0x14003784e  or      ebx, 80280000h
0x140037854  jmp     short loc_140037883
0x140037856  mov     eax, ebx
0x140037858  and     eax, 0FFF0000h
0x14003785d  cmp     eax, 70000h
0x140037862  jnz     short loc_140037877
0x140037864  movzx   ebx, bx
0x140037867  test    ebx, ebx
0x140037869  jz      loc_1400376B0
0x14003786f  or      ebx, 80070000h
0x140037875  jmp     short loc_140037883
0x140037877  bts     ebx, 1Ch
0x14003787b  jmp     short loc_140037883
0x14003787d  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x140037880  xor     r12d, r12d
0x140037883  test    ebx, ebx
0x140037885  jz      loc_1400376B0
0x14003788b  jmp     loc_1400376A8
```
