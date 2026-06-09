# SIO_SPAN::BuildChildPacketsIo(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x140012ee0`
- end: `0x14001334f`
- name: `?BuildChildPacketsIo@SIO_SPAN@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `1135`
- prototype: `int(SIO_SPAN *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012eb0`

## callees

- `0x140012ee0`
- `0x140013360`
- `0x1400133a0`
- `0x14002f858`
- `0x140068150`
- `0x140068600`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14001313c`
- `ntoskrnl!IoAllocateMdl` at `0x14001313c`
- `ntoskrnl!IoBuildPartialMdl` at `0x140013177`
- `ntoskrnl!IoBuildPartialMdl` at `0x140013177`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013325`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013325`

## pseudocode

```c
__int64 __fastcall SIO_SPAN::BuildChildPacketsIo(SIO_SPAN *this, struct SC_PACKET *a2, struct SC_SEQUENTIAL *a3)
{
  __int64 v3; // r9
  unsigned int v4; // r12d
  unsigned __int64 v6; // rbp
  unsigned __int64 i; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r13
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  __int64 v14; // r9
  int j; // r8d
  __int64 v16; // r15
  char *v17; // rax
  char *v18; // rbx
  int v19; // eax
  __int64 v20; // rcx
  struct _MDL *Mdl; // rax
  int v22; // eax
  unsigned __int64 v23; // rdx
  struct SC_PACKET **v24; // rcx
  struct SC_PACKET *v25; // rbx
  __int64 v26; // rcx
  char *v27; // rax
  unsigned int v28; // r8d
  unsigned int v29; // [rsp+78h] [rbp+10h]
  unsigned int v31; // [rsp+88h] [rbp+20h]

  v3 = *((_QWORD *)a2 + 17);
  v4 = 0;
  v6 = v3 + *((unsigned int *)a2 + 36);
  for ( i = v3 + *((_QWORD *)a2 + 24); i < v6; i += (unsigned int)v11 )
  {
    v10 = *((_QWORD *)this + 14);
    v11 = v10 - i % v10;
    if ( v6 - i < v11 )
      LODWORD(v11) = v6 - i;
    v12 = i - *((_DWORD *)a2 + 34);
    v29 = v12;
    v13 = i / v10;
    if ( i / v10 >= *((_QWORD *)this + 12) )
      goto LABEL_29;
    v14 = *((_QWORD *)this + 4);
    for ( j = *((_DWORD *)this + 26);
          ;
          v14 = *(_QWORD *)(v14 + 8 * ((unsigned int)(*((_DWORD *)this + 21) - 1) & (v13 >> j)) + 24) )
    {
      j -= *((_DWORD *)this + 22);
      if ( j <= 0 )
        break;
      if ( !v14 )
        goto LABEL_29;
    }
    if ( v14
      && (v16 = *(_QWORD *)(v14 + 8LL * ((unsigned int)v13 & (*((_DWORD *)this + 21) - 1)) + 24)) != 0
      && *(char *)(v16 + 40) >= 0 )
    {
      if ( a3 )
      {
        v28 = *((_DWORD *)a3 + 10);
        v18 = *(char **)a3;
        if ( (unsigned int)v11 < v28 )
          v28 = v11;
        v31 = v28;
        if ( v28 == *((_DWORD *)a2 + 36) )
          *((_DWORD *)v18 + 19) |= *((_DWORD *)a2 + 19) & 4;
        SC_BUFFER::Split((SC_BUFFER *)(v18 + 112), (struct SC_PACKET *)((char *)a2 + 112), v29, v28);
        SC_PACKET::SetTrackedOffset((SC_PACKET *)v18, a2, v29);
        LODWORD(v11) = v31;
      }
      else
      {
        v17 = (char *)SC_PACKET::operator new(0xF8u, *((struct SC_PACKET **)a2 + 1));
        v18 = v17;
        if ( !v17 )
          return (unsigned int)-1073741670;
        *(_QWORD *)v17 = &SC_PACKET::`vftable';
        *((_DWORD *)v17 + 28) = 0;
        *((_QWORD *)v17 + 15) = 0;
        *((_QWORD *)v17 + 1) = v17;
        *((_QWORD *)v17 + 2) = 0;
        *((_QWORD *)v17 + 6) = v17 + 40;
        *((_QWORD *)v17 + 5) = v17 + 40;
        *((_QWORD *)v17 + 8) = v17 + 56;
        *((_QWORD *)v17 + 7) = v17 + 56;
        *((_DWORD *)v17 + 18) = 0;
        *((_DWORD *)v17 + 19) = 1;
        *((_QWORD *)v17 + 10) = 0;
        *((_QWORD *)v17 + 11) = 0;
        *((_QWORD *)v17 + 13) = v17 + 96;
        *((_QWORD *)v17 + 12) = v17 + 96;
        *((_QWORD *)v17 + 16) = 0;
        *((_QWORD *)v17 + 17) = 0;
        *((_DWORD *)v17 + 36) = 0;
        *(_QWORD *)(v17 + 148) = -1;
        *((_DWORD *)v17 + 39) = -1;
        *((_DWORD *)v17 + 40) = 0;
        *((_DWORD *)v17 + 41) = -1;
        *((_WORD *)v17 + 84) = 255;
        v17[170] = 0;
        v17[172] = 0;
        *((_DWORD *)v17 + 44) = 0;
        *((_DWORD *)v17 + 45) = 0;
        *((_DWORD *)v17 + 46) = 0;
        *((_QWORD *)v17 + 24) = 0;
        *((_QWORD *)v17 + 26) = v17 + 200;
        *((_QWORD *)v17 + 25) = v17 + 200;
        *((_QWORD *)v17 + 28) = v17 + 216;
        *((_QWORD *)v17 + 27) = v17 + 216;
        *((_QWORD *)v17 + 29) = 0;
        *((_QWORD *)v17 + 30) = 0;
        if ( (_DWORD)v11 == *((_DWORD *)a2 + 36) )
        {
          *((_DWORD *)v17 + 19) |= *((_DWORD *)a2 + 19) & 4;
          *((_DWORD *)v17 + 28) = 1;
          *((_QWORD *)v17 + 15) = *((_QWORD *)a2 + 15);
          v19 = *((_DWORD *)a2 + 41);
          if ( v19 != -1 )
            *((_DWORD *)v18 + 41) = v19;
          v4 = 0;
        }
        else
        {
          v20 = v29 + *(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL);
          if ( !v20 )
            v20 = 4095;
          Mdl = IoAllocateMdl((PVOID)v20, v11, 0, 0, 0);
          *((_QWORD *)v18 + 15) = Mdl;
          if ( !Mdl )
          {
            (**(void (__fastcall ***)(char *, __int64))v18)(v18, 1);
            return (unsigned int)-1073741670;
          }
          *((_DWORD *)v18 + 28) = 2;
          *((_WORD *)v18 + 58) = -1;
          IoBuildPartialMdl(
            *((PMDL *)a2 + 15),
            Mdl,
            (PVOID)(v29 + *(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL)),
            v11);
          v22 = *((_DWORD *)a2 + 41);
          if ( v22 != -1 )
            *((_DWORD *)v18 + 41) = v29 + v22;
          v4 = 0;
        }
      }
      v23 = i % *((_QWORD *)this + 14);
      *((_DWORD *)v18 + 36) = v11;
      *((_QWORD *)v18 + 17) = v23;
      *((_DWORD *)v18 + 37) = *((_DWORD *)a2 + 37);
      *((_DWORD *)v18 + 38) = *((_DWORD *)a2 + 38);
      *((_DWORD *)v18 + 39) = *((_DWORD *)a2 + 39);
      v18[168] = *((_BYTE *)a2 + 168);
      *((_QWORD *)v18 + 30) = v16;
      *((_QWORD *)v18 + 1) = *((_QWORD *)a2 + 1);
      *((_QWORD *)v18 + 2) = a2;
      v24 = (struct SC_PACKET **)*((_QWORD *)a2 + 6);
      if ( *v24 != (struct SC_PACKET *)((char *)a2 + 40) )
        __fastfail(3u);
      v25 = (struct SC_PACKET *)(v18 + 56);
      *(_QWORD *)v25 = (char *)a2 + 40;
      *((_QWORD *)v25 + 1) = v24;
      *v24 = v25;
      *((_QWORD *)a2 + 6) = v25;
      ++*((_DWORD *)a2 + 18);
      if ( a3 )
        return v4;
    }
    else
    {
LABEL_29:
      if ( *((_BYTE *)a2 + 168) == 4 )
        return (unsigned int)-1058602988;
      v26 = *((_QWORD *)a2 + 15);
      if ( (*(_BYTE *)(v26 + 10) & 5) != 0 )
        v27 = *(char **)(v26 + 24);
      else
        v27 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v26, 0, MmCached, 0, 0, 0x40000020u);
      if ( v27 )
        memset(&v27[v12], 0, (unsigned int)v11);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140012ee0  mov     [rsp+arg_10], r8
0x140012ee5  push    rbp
0x140012ee6  push    rsi
0x140012ee7  push    rdi
0x140012ee8  push    r12
0x140012eea  push    r14
0x140012eec  sub     rsp, 40h
0x140012ef0  mov     r9, [rdx+88h]
0x140012ef7  xor     r12d, r12d
0x140012efa  mov     ebp, [rdx+90h]
0x140012f00  mov     rdi, rdx
0x140012f03  mov     rsi, [rdx+0C0h]
0x140012f0a  add     rbp, r9
0x140012f0d  mov     [rsp+68h+arg_0], rbx
0x140012f12  add     rsi, r9
0x140012f15  mov     [rsp+68h+var_30], r13
0x140012f1a  mov     r14, rcx
0x140012f1d  mov     [rsp+68h+var_38], r15
0x140012f22  cmp     rsi, rbp
0x140012f25  jb      short loc_140012F46
0x140012f27  mov     r15, [rsp+68h+var_38]
0x140012f2c  mov     eax, r12d
0x140012f2f  mov     r13, [rsp+68h+var_30]
0x140012f34  mov     rbx, [rsp+68h+arg_0]
0x140012f39  add     rsp, 40h
0x140012f3d  pop     r14
0x140012f3f  pop     r12
0x140012f41  pop     rdi
0x140012f42  pop     rsi
0x140012f43  pop     rbp
0x140012f44  retn
0x140012f46  mov     rcx, [r14+70h]
0x140012f4a  xor     edx, edx
0x140012f4c  mov     rax, rsi
0x140012f4f  mov     r13, rcx
0x140012f52  div     rcx
0x140012f55  mov     rax, rbp
0x140012f58  mov     ebx, esi
0x140012f5a  sub     r13, rdx
0x140012f5d  sub     rax, rsi
0x140012f60  cmp     rax, r13
0x140012f63  cmovb   r13, rax
0x140012f67  sub     ebx, [rdi+88h]
0x140012f6d  xor     edx, edx
0x140012f6f  mov     [rsp+68h+arg_8], ebx
0x140012f73  mov     rax, rsi
0x140012f76  div     rcx
0x140012f79  cmp     rax, [r14+60h]
0x140012f7d  jnb     loc_140013254
0x140012f83  mov     r9, [r14+20h]
0x140012f87  mov     r10d, [r14+58h]
0x140012f8b  mov     r8d, [r14+68h]
0x140012f8f  sub     r8d, r10d
0x140012f92  test    r8d, r8d
0x140012f95  jg      loc_1400132E5
0x140012f9b  test    r9, r9
0x140012f9e  jz      loc_140013254
0x140012fa4  mov     ecx, [r14+54h]
0x140012fa8  dec     ecx
0x140012faa  and     rcx, rax
0x140012fad  mov     r15, [r9+rcx*8+18h]
0x140012fb2  test    r15, r15
0x140012fb5  jz      loc_140013254
0x140012fbb  movzx   eax, byte ptr [r15+28h]
0x140012fc0  test    al, al
0x140012fc2  js      loc_140013254
0x140012fc8  mov     rax, [rsp+68h+arg_10]
0x140012fd0  test    rax, rax
0x140012fd3  jnz     loc_140013289
0x140012fd9  mov     rdx, [rdi+8]; struct SC_PACKET *
0x140012fdd  mov     ecx, 0F8h; unsigned __int64
0x140012fe2  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x140012fe7  mov     rbx, rax
0x140012fea  test    rax, rax
0x140012fed  jz      loc_140013249
0x140012ff3  xor     edx, edx
0x140012ff5  lea     rax, ??_7SC_PACKET@@6B@; const SC_PACKET::`vftable'
0x140012ffc  mov     [rbx], rax
0x140012fff  lea     rax, [rbx+28h]
0x140013003  mov     [rbx+70h], edx
0x140013006  mov     [rbx+78h], rdx
0x14001300a  mov     [rbx+8], rbx
0x14001300e  mov     [rbx+10h], rdx
0x140013012  mov     [rbx+30h], rax
0x140013016  mov     [rax], rax
0x140013019  lea     rax, [rbx+38h]
0x14001301d  mov     [rbx+40h], rax
0x140013021  mov     [rax], rax
0x140013024  lea     rax, [rbx+60h]
0x140013028  mov     [rbx+48h], edx
0x14001302b  mov     dword ptr [rbx+4Ch], 1
0x140013032  mov     [rbx+50h], rdx
0x140013036  mov     [rbx+58h], rdx
0x14001303a  mov     [rbx+68h], rax
0x14001303e  mov     [rax], rax
0x140013041  lea     rax, [rbx+0C8h]
0x140013048  mov     [rbx+80h], rdx
0x14001304f  mov     [rbx+88h], rdx
0x140013056  mov     [rbx+90h], edx
0x14001305c  mov     qword ptr [rbx+94h], 0FFFFFFFFFFFFFFFFh
0x140013067  mov     dword ptr [rbx+9Ch], 0FFFFFFFFh
0x140013071  mov     [rbx+0A0h], edx
0x140013077  mov     dword ptr [rbx+0A4h], 0FFFFFFFFh
0x140013081  mov     word ptr [rbx+0A8h], 0FFh
0x14001308a  mov     [rbx+0AAh], dl
0x140013090  mov     [rbx+0ACh], dl
0x140013096  mov     [rbx+0B0h], edx
0x14001309c  mov     [rbx+0B4h], edx
0x1400130a2  mov     [rbx+0B8h], edx
0x1400130a8  mov     [rbx+0C0h], rdx
0x1400130af  mov     [rbx+0D0h], rax
0x1400130b6  mov     [rax], rax
0x1400130b9  lea     rax, [rbx+0D8h]
0x1400130c0  mov     [rbx+0E0h], rax
0x1400130c7  mov     [rax], rax
0x1400130ca  mov     [rbx+0E8h], rdx
0x1400130d1  mov     [rbx+0F0h], rdx
0x1400130d8  cmp     r13d, [rdi+90h]
0x1400130df  jnz     short loc_140013112
0x1400130e1  mov     eax, [rdi+4Ch]
0x1400130e4  and     eax, 4
0x1400130e7  or      [rbx+4Ch], eax
0x1400130ea  mov     dword ptr [rbx+70h], 1
0x1400130f1  mov     rax, [rdi+78h]
0x1400130f5  mov     [rbx+78h], rax
0x1400130f9  mov     eax, [rdi+0A4h]
0x1400130ff  cmp     eax, 0FFFFFFFFh
0x140013102  jz      short loc_14001310A
0x140013104  mov     [rbx+0A4h], eax
0x14001310a  mov     r12d, edx
0x14001310d  jmp     loc_14001319B
0x140013112  mov     rax, [rdi+78h]
0x140013116  mov     r12d, [rsp+68h+arg_8]
0x14001311b  mov     [rsp+68h+Irp], rdx; Irp
0x140013120  mov     edx, r13d; Length
0x140013123  mov     ecx, [rax+2Ch]
0x140013126  add     rcx, [rax+20h]
0x14001312a  mov     eax, 0FFFh
0x14001312f  add     rcx, r12
0x140013132  cmovz   rcx, rax; VirtualAddress
0x140013136  xor     r9d, r9d; ChargeQuota
0x140013139  xor     r8d, r8d; SecondaryBuffer
0x14001313c  call    cs:__imp_IoAllocateMdl
0x140013143  nop     dword ptr [rax+rax+00h]
0x140013148  mov     [rbx+78h], rax
0x14001314c  test    rax, rax
0x14001314f  jz      loc_140013236
0x140013155  mov     dword ptr [rbx+70h], 2
0x14001315c  mov     r9d, r13d; Length
0x14001315f  mov     word ptr [rbx+74h], 0FFFFh
0x140013165  mov     rdx, rax; TargetMdl
0x140013168  mov     rcx, [rdi+78h]; SourceMdl
0x14001316c  mov     r8d, [rcx+2Ch]
0x140013170  add     r8, [rcx+20h]
0x140013174  add     r8, r12; VirtualAddress
0x140013177  call    cs:__imp_IoBuildPartialMdl
0x14001317e  nop     dword ptr [rax+rax+00h]
0x140013183  mov     eax, [rdi+0A4h]
0x140013189  cmp     eax, 0FFFFFFFFh
0x14001318c  jz      short loc_140013198
0x14001318e  add     eax, [rsp+68h+arg_8]
0x140013192  mov     [rbx+0A4h], eax
0x140013198  xor     r12d, r12d
0x14001319b  xor     edx, edx
0x14001319d  mov     rax, rsi
0x1400131a0  div     qword ptr [r14+70h]
0x1400131a4  mov     [rbx+90h], r13d
0x1400131ab  mov     [rbx+88h], rdx
0x1400131b2  mov     eax, [rdi+94h]
0x1400131b8  mov     [rbx+94h], eax
0x1400131be  mov     eax, [rdi+98h]
0x1400131c4  mov     [rbx+98h], eax
0x1400131ca  mov     eax, [rdi+9Ch]
0x1400131d0  mov     [rbx+9Ch], eax
0x1400131d6  movzx   eax, byte ptr [rdi+0A8h]
0x1400131dd  mov     [rbx+0A8h], al
0x1400131e3  mov     [rbx+0F0h], r15
0x1400131ea  mov     rax, [rdi+8]
0x1400131ee  mov     [rbx+8], rax
0x1400131f2  lea     rax, [rdi+28h]
0x1400131f6  mov     [rbx+10h], rdi
0x1400131fa  mov     rcx, [rax+8]
0x1400131fe  cmp     [rcx], rax
0x140013201  jnz     loc_1400132DE
0x140013207  add     rbx, 38h ; '8'
0x14001320b  mov     [rbx], rax
0x14001320e  mov     [rbx+8], rcx
0x140013212  mov     [rcx], rbx
0x140013215  mov     [rax+8], rbx
0x140013219  inc     dword ptr [rdi+48h]
0x14001321c  cmp     [rsp+68h+arg_10], 0
0x140013225  jnz     loc_140012F27
0x14001322b  mov     eax, r13d
0x14001322e  add     rsi, rax
0x140013231  jmp     loc_140012F22
0x140013236  mov     rax, [rbx]
0x140013239  mov     edx, 1
0x14001323e  mov     rcx, rbx
0x140013241  mov     rax, [rax]
0x140013244  call    _guard_dispatch_icall
0x140013249  mov     r12d, 0C000009Ah
0x14001324f  jmp     loc_140012F27
0x140013254  cmp     byte ptr [rdi+0A8h], 4
0x14001325b  jz      loc_140013336
0x140013261  mov     rcx, [rdi+78h]; MemoryDescriptorList
0x140013265  test    byte ptr [rcx+0Ah], 5
0x140013269  jz      loc_14001330A
0x14001326f  mov     rax, [rcx+18h]
0x140013273  test    rax, rax
0x140013276  jz      short loc_14001322B
0x140013278  mov     ecx, ebx
0x14001327a  xor     edx, edx; Val
0x14001327c  add     rcx, rax; void *
0x14001327f  mov     r8d, r13d; Size
0x140013282  call    memset
0x140013287  jmp     short loc_14001322B
0x140013289  mov     r8d, [rax+28h]
0x14001328d  cmp     r13d, r8d
0x140013290  mov     rbx, [rax]
0x140013293  cmovb   r8d, r13d
0x140013297  mov     [rsp+68h+arg_18], r8d
0x14001329f  cmp     r8d, [rdi+90h]
0x1400132a6  jz      loc_140013341
0x1400132ac  mov     r9d, r8d; unsigned int
0x1400132af  lea     rdx, [rdi+70h]; struct SC_BUFFER *
0x1400132b3  mov     r8d, [rsp+68h+arg_8]; unsigned int
0x1400132b8  lea     rcx, [rbx+70h]; this
0x1400132bc  call    ?Split@SC_BUFFER@@QEAAXPEAV1@KK@Z; SC_BUFFER::Split(SC_BUFFER *,ulong,ulong)
0x1400132c1  mov     r8d, [rsp+68h+arg_8]; unsigned int
0x1400132c6  mov     rdx, rdi; struct SC_PACKET *
0x1400132c9  mov     rcx, rbx; this
0x1400132cc  call    ?SetTrackedOffset@SC_PACKET@@QEAAXPEAV1@K@Z; SC_PACKET::SetTrackedOffset(SC_PACKET *,ulong)
0x1400132d1  mov     r13d, [rsp+68h+arg_18]
0x1400132d9  jmp     loc_14001319B
0x1400132de  mov     ecx, 3
0x1400132e3  int     29h; Win8: RtlFailFast(ecx)
0x1400132e5  test    r9, r9
0x1400132e8  jz      loc_140013254
0x1400132ee  mov     ecx, r8d
0x1400132f1  mov     rdx, rax
0x1400132f4  shr     rdx, cl
0x1400132f7  mov     ecx, [r14+54h]
0x1400132fb  dec     ecx
0x1400132fd  and     rdx, rcx
0x140013300  mov     r9, [r9+rdx*8+18h]
0x140013305  jmp     loc_140012F8F
0x14001330a  mov     [rsp+68h+Priority], 40000020h; Priority
0x140013312  xor     r9d, r9d; RequestedAddress
0x140013315  xor     edx, edx; AccessMode
0x140013317  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x14001331f  mov     r8d, 1; CacheType
0x140013325  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001332c  nop     dword ptr [rax+rax+00h]
0x140013331  jmp     loc_140013273
0x140013336  mov     r12d, 0C0E70014h
0x14001333c  jmp     loc_140012F27
0x140013341  mov     eax, [rdi+4Ch]
0x140013344  and     eax, 4
0x140013347  or      [rbx+4Ch], eax
0x14001334a  jmp     loc_1400132AC
```
