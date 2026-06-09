# Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsWin32Error(Windows::Rtl::IRtlFormattedOutputStream *,void const *)

- ea: `0x1800182dc`
- end: `0x180018744`
- name: `?RtlTraceFormat_PCULONG_AsWin32Error@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z`
- size: `1128`
- prototype: `void __fastcall(Windows::WCP::Rtl *__hidden this, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020c0`
- `0x180016be8`
- `0x1800173f4`

## callees

- `0x1800182dc`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsWin32Error(
        Windows::WCP::Rtl *this,
        struct Windows::Rtl::IRtlFormattedOutputStream *a2,
        const void *a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rax
  _BYTE v6[24]; // [rsp+20h] [rbp-20h] BYREF

  if ( !a2 )
  {
    (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64 *, const void *))(*(_QWORD *)this + 96LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
      a3);
    return;
  }
  memset(v6, 0, sizeof(v6));
  if ( *(_DWORD *)a2 > 0x54Fu )
  {
    if ( *(_DWORD *)a2 > 0x36CCu )
    {
      switch ( *(_DWORD *)a2 )
      {
        case 0x3701:
          v5 = 26;
          *(_QWORD *)v6 = 26;
          *(_OWORD *)&v6[8] = *(_OWORD *)byte_18001E6E0;
LABEL_78:
          if ( !v5 )
            return;
          goto LABEL_79;
        case 0x3712:
          v4 = *(_OWORD *)byte_18001E7A0;
          *(_QWORD *)v6 = 33;
          goto LABEL_16;
        case 0x3713:
          v4 = *(_OWORD *)&qword_18001E4B8;
          *(_QWORD *)v6 = 31;
          goto LABEL_16;
        case 0x3715:
          v4 = *(_OWORD *)&qword_18001E758;
          *(_QWORD *)v6 = 55;
          goto LABEL_16;
        case 0x3716:
          v4 = *(_OWORD *)byte_18001E740;
          *(_QWORD *)v6 = 30;
          goto LABEL_16;
        case 0x3717:
          v4 = *(_OWORD *)&qword_18001E6C8;
          *(_QWORD *)v6 = 38;
          goto LABEL_16;
        case 0x3718:
          v4 = *(_OWORD *)&qword_18001E728;
          *(_QWORD *)v6 = 35;
          goto LABEL_16;
        case 0x371B:
          v4 = *(_OWORD *)&qword_18001E788;
          *(_QWORD *)v6 = 40;
          goto LABEL_16;
      }
    }
    else
    {
      switch ( *(_DWORD *)a2 )
      {
        case 0x36CC:
          v4 = *(_OWORD *)byte_18001E710;
          *(_QWORD *)v6 = 28;
          goto LABEL_16;
        case 0x570:
          v4 = *(_OWORD *)byte_18001E7D0;
          *(_QWORD *)v6 = 18;
          goto LABEL_16;
        case 0x669:
          v4 = *(_OWORD *)&qword_18001E698;
          *(_QWORD *)v6 = 30;
          goto LABEL_16;
        case 0x70C:
          v4 = *(_OWORD *)byte_18001E5C0;
          *(_QWORD *)v6 = 22;
          goto LABEL_16;
        case 0xBC2:
          v4 = *(_OWORD *)byte_18001E6B0;
          *(_QWORD *)v6 = 29;
          goto LABEL_16;
        case 0xBC9:
          v4 = *(_OWORD *)&qword_18001E548;
          *(_QWORD *)v6 = 26;
          goto LABEL_16;
        case 0xBCA:
          v4 = *(_OWORD *)byte_18001E530;
          *(_QWORD *)v6 = 27;
          goto LABEL_16;
        case 0x36B3:
          v4 = *(_OWORD *)&qword_18001E6F8;
          *(_QWORD *)v6 = 28;
          goto LABEL_16;
        case 0x36B5:
          v4 = *(_OWORD *)byte_18001E770;
          *(_QWORD *)v6 = 30;
          goto LABEL_16;
      }
    }
LABEL_69:
    (*(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD, const void *))(*(_QWORD *)this + 344LL))(
      this,
      *(unsigned int *)a2,
      a3);
    v5 = *(_QWORD *)v6;
    goto LABEL_78;
  }
  if ( *(_DWORD *)a2 == 1359 )
  {
    v4 = *(_OWORD *)byte_18001E590;
    *(_QWORD *)v6 = 20;
    goto LABEL_16;
  }
  if ( *(_DWORD *)a2 > 0x7Au )
  {
    switch ( *(_DWORD *)a2 )
    {
      case 0x7E:
        v4 = *(_OWORD *)&qword_18001E608;
        *(_QWORD *)v6 = 19;
        goto LABEL_16;
      case 0xB7:
        v4 = *(_OWORD *)byte_18001E4D0;
        *(_QWORD *)v6 = 20;
        goto LABEL_16;
      case 0x15E:
        v4 = *(_OWORD *)&qword_18001E518;
        *(_QWORD *)v6 = 26;
        goto LABEL_16;
      case 0x306:
        v4 = *(_OWORD *)&qword_18001E7B8;
        *(_QWORD *)v6 = 24;
        goto LABEL_16;
      case 0x308:
        v4 = *(_OWORD *)&qword_18001E638;
        *(_QWORD *)v6 = 29;
        goto LABEL_16;
      case 0x3EC:
        v4 = *(_OWORD *)&qword_18001E5D8;
        *(_QWORD *)v6 = 19;
        goto LABEL_16;
      case 0x424:
        v4 = *(_OWORD *)&qword_18001E668;
        *(_QWORD *)v6 = 28;
        goto LABEL_16;
      case 0x42C:
        v4 = *(_OWORD *)byte_18001E650;
        *(_QWORD *)v6 = 29;
        goto LABEL_16;
    }
    goto LABEL_69;
  }
  switch ( *(_DWORD *)a2 )
  {
    case 0x7A:
      v4 = *(_OWORD *)&qword_18001E578;
      *(_QWORD *)v6 = 25;
      goto LABEL_16;
    case 2:
      v4 = *(_OWORD *)byte_18001E560;
      *(_QWORD *)v6 = 20;
      goto LABEL_16;
    case 3:
      v4 = *(_OWORD *)byte_18001E620;
      *(_QWORD *)v6 = 20;
      goto LABEL_16;
    case 5:
      v4 = *(_OWORD *)byte_18001E4A0;
      *(_QWORD *)v6 = 19;
      goto LABEL_16;
    case 6:
      v4 = *(_OWORD *)byte_18001E5F0;
      *(_QWORD *)v6 = 20;
      goto LABEL_16;
    case 0xA:
      v4 = *(_OWORD *)&qword_18001E4E8;
      *(_QWORD *)v6 = 21;
      goto LABEL_16;
    case 0xD:
      v4 = *(_OWORD *)&qword_18001E5A8;
      *(_QWORD *)v6 = 18;
      goto LABEL_16;
    case 0x20:
      v4 = *(_OWORD *)byte_18001E680;
      *(_QWORD *)v6 = 23;
      goto LABEL_16;
  }
  if ( *(_DWORD *)a2 != 112 )
    goto LABEL_69;
  v4 = *(_OWORD *)byte_18001E500;
  *(_QWORD *)v6 = 15;
LABEL_16:
  *(_OWORD *)&v6[8] = v4;
LABEL_79:
  (*(void (__fastcall **)(Windows::WCP::Rtl *, _BYTE *, const void *))(*(_QWORD *)this + 200LL))(this, v6, a3);
}

```

## disassembly

```asm
0x1800182dc  mov     [rsp-8+arg_10], rbx
0x1800182e1  push    rbp
0x1800182e2  mov     rbp, rsp
0x1800182e5  sub     rsp, 40h
0x1800182e9  mov     rax, cs:__security_cookie
0x1800182f0  xor     rax, rsp
0x1800182f3  mov     [rbp+var_8], rax
0x1800182f7  mov     rbx, rcx
0x1800182fa  test    rdx, rdx
0x1800182fd  jnz     short loc_180018312
0x1800182ff  mov     rax, [rcx]
0x180018302  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180018309  mov     rax, [rax+60h]
0x18001830d  jmp     loc_180018728
0x180018312  xor     eax, eax
0x180018314  xorps   xmm0, xmm0
0x180018317  mov     [rbp+var_10], rax
0x18001831b  mov     eax, 54Fh
0x180018320  movups  [rbp+var_20], xmm0
0x180018324  cmp     [rdx], eax
0x180018326  ja      loc_180018513
0x18001832c  jz      loc_1800184FF
0x180018332  cmp     dword ptr [rdx], 7Ah ; 'z'
0x180018335  ja      loc_18001841E
0x18001833b  jz      loc_18001840A
0x180018341  mov     eax, [rdx]
0x180018343  sub     eax, 2
0x180018346  jz      loc_1800183F6
0x18001834c  sub     eax, 1
0x18001834f  jz      loc_1800183E5
0x180018355  sub     eax, 2
0x180018358  jz      short loc_1800183D4
0x18001835a  sub     eax, 1
0x18001835d  jz      short loc_1800183C3
0x18001835f  sub     eax, 4
0x180018362  jz      short loc_1800183B2
0x180018364  sub     eax, 3
0x180018367  jz      short loc_1800183A1
0x180018369  sub     eax, 13h
0x18001836c  jz      short loc_180018390
0x18001836e  cmp     eax, 50h ; 'P'
0x180018371  jnz     loc_180018657
0x180018377  movups  xmm0, xmmword ptr cs:byte_18001E500
0x18001837e  mov     qword ptr [rbp+var_20], 0Fh
0x180018386  movdqu  [rbp+var_20+8], xmm0
0x18001838b  jmp     loc_180018717
0x180018390  movups  xmm0, xmmword ptr cs:byte_18001E680
0x180018397  mov     qword ptr [rbp+var_20], 17h
0x18001839f  jmp     short loc_180018386
0x1800183a1  movups  xmm0, xmmword ptr cs:qword_18001E5A8
0x1800183a8  mov     qword ptr [rbp+var_20], 12h
0x1800183b0  jmp     short loc_180018386
0x1800183b2  movups  xmm0, xmmword ptr cs:qword_18001E4E8
0x1800183b9  mov     qword ptr [rbp+var_20], 15h
0x1800183c1  jmp     short loc_180018386
0x1800183c3  movups  xmm0, xmmword ptr cs:byte_18001E5F0
0x1800183ca  mov     qword ptr [rbp+var_20], 14h
0x1800183d2  jmp     short loc_180018386
0x1800183d4  movups  xmm0, xmmword ptr cs:byte_18001E4A0
0x1800183db  mov     qword ptr [rbp+var_20], 13h
0x1800183e3  jmp     short loc_180018386
0x1800183e5  movups  xmm0, xmmword ptr cs:byte_18001E620
0x1800183ec  mov     qword ptr [rbp+var_20], 14h
0x1800183f4  jmp     short loc_180018386
0x1800183f6  movups  xmm0, xmmword ptr cs:byte_18001E560
0x1800183fd  mov     qword ptr [rbp+var_20], 14h
0x180018405  jmp     loc_180018386
0x18001840a  movups  xmm0, xmmword ptr cs:qword_18001E578
0x180018411  mov     qword ptr [rbp+var_20], 19h
0x180018419  jmp     loc_180018386
0x18001841e  mov     eax, [rdx]
0x180018420  sub     eax, 7Eh ; '~'
0x180018423  jz      loc_1800184EB
0x180018429  sub     eax, 39h ; '9'
0x18001842c  jz      loc_1800184D7
0x180018432  sub     eax, 0A7h
0x180018437  jz      loc_1800184C2
0x18001843d  sub     eax, 1A8h
0x180018442  jz      short loc_1800184AE
0x180018444  sub     eax, 2
0x180018447  jz      short loc_18001849A
0x180018449  sub     eax, 0E4h
0x18001844e  jz      short loc_180018486
0x180018450  sub     eax, 38h ; '8'
0x180018453  jz      short loc_180018472
0x180018455  cmp     eax, 8
0x180018458  jnz     loc_180018657
0x18001845e  movups  xmm0, xmmword ptr cs:byte_18001E650
0x180018465  mov     qword ptr [rbp+var_20], 1Dh
0x18001846d  jmp     loc_180018386
0x180018472  movups  xmm0, xmmword ptr cs:qword_18001E668
0x180018479  mov     qword ptr [rbp+var_20], 1Ch
0x180018481  jmp     loc_180018386
0x180018486  movups  xmm0, xmmword ptr cs:qword_18001E5D8
0x18001848d  mov     qword ptr [rbp+var_20], 13h
0x180018495  jmp     loc_180018386
0x18001849a  movups  xmm0, xmmword ptr cs:qword_18001E638
0x1800184a1  mov     qword ptr [rbp+var_20], 1Dh
0x1800184a9  jmp     loc_180018386
0x1800184ae  movups  xmm0, xmmword ptr cs:qword_18001E7B8
0x1800184b5  mov     qword ptr [rbp+var_20], 18h
0x1800184bd  jmp     loc_180018386
0x1800184c2  movups  xmm0, xmmword ptr cs:qword_18001E518
0x1800184c9  mov     eax, 1Ah
0x1800184ce  mov     qword ptr [rbp+var_20], rax
0x1800184d2  jmp     loc_180018386
0x1800184d7  movups  xmm0, xmmword ptr cs:byte_18001E4D0
0x1800184de  mov     qword ptr [rbp+var_20], 14h
0x1800184e6  jmp     loc_180018386
0x1800184eb  movups  xmm0, xmmword ptr cs:qword_18001E608
0x1800184f2  mov     qword ptr [rbp+var_20], 13h
0x1800184fa  jmp     loc_180018386
0x1800184ff  movups  xmm0, xmmword ptr cs:byte_18001E590
0x180018506  mov     qword ptr [rbp+var_20], 14h
0x18001850e  jmp     loc_180018386
0x180018513  mov     eax, 36CCh
0x180018518  cmp     [rdx], eax
0x18001851a  ja      loc_18001861F
0x180018520  jz      loc_18001860B
0x180018526  mov     eax, [rdx]
0x180018528  sub     eax, 570h
0x18001852d  jz      loc_1800185F7
0x180018533  sub     eax, 0F9h
0x180018538  jz      loc_1800185E3
0x18001853e  sub     eax, 0A3h
0x180018543  jz      loc_1800185CF
0x180018549  sub     eax, 4B6h
0x18001854e  jz      short loc_1800185BB
0x180018550  sub     eax, 7
0x180018553  jz      short loc_1800185A6
0x180018555  sub     eax, 1
0x180018558  jz      short loc_180018592
0x18001855a  sub     eax, 2AE9h
0x18001855f  jz      short loc_18001857E
0x180018561  cmp     eax, 2
0x180018564  jnz     loc_180018657
0x18001856a  movups  xmm0, xmmword ptr cs:byte_18001E770
0x180018571  mov     qword ptr [rbp+var_20], 1Eh
0x180018579  jmp     loc_180018386
0x18001857e  movups  xmm0, xmmword ptr cs:qword_18001E6F8
0x180018585  mov     qword ptr [rbp+var_20], 1Ch
0x18001858d  jmp     loc_180018386
0x180018592  movups  xmm0, xmmword ptr cs:byte_18001E530
0x180018599  mov     qword ptr [rbp+var_20], 1Bh
0x1800185a1  jmp     loc_180018386
0x1800185a6  movups  xmm0, xmmword ptr cs:qword_18001E548
0x1800185ad  mov     eax, 1Ah
0x1800185b2  mov     qword ptr [rbp+var_20], rax
0x1800185b6  jmp     loc_180018386
0x1800185bb  movups  xmm0, xmmword ptr cs:byte_18001E6B0
0x1800185c2  mov     qword ptr [rbp+var_20], 1Dh
0x1800185ca  jmp     loc_180018386
0x1800185cf  movups  xmm0, xmmword ptr cs:byte_18001E5C0
0x1800185d6  mov     qword ptr [rbp+var_20], 16h
0x1800185de  jmp     loc_180018386
0x1800185e3  movups  xmm0, xmmword ptr cs:qword_18001E698
0x1800185ea  mov     qword ptr [rbp+var_20], 1Eh
0x1800185f2  jmp     loc_180018386
0x1800185f7  movups  xmm0, xmmword ptr cs:byte_18001E7D0
0x1800185fe  mov     qword ptr [rbp+var_20], 12h
0x180018606  jmp     loc_180018386
0x18001860b  movups  xmm0, xmmword ptr cs:byte_18001E710
0x180018612  mov     qword ptr [rbp+var_20], 1Ch
0x18001861a  jmp     loc_180018386
0x18001861f  mov     eax, [rdx]
0x180018621  sub     eax, 3701h
0x180018626  jz      loc_1800186FD
0x18001862c  sub     eax, 11h
0x18001862f  jz      loc_1800186E9
0x180018635  sub     eax, 1
0x180018638  jz      loc_1800186D5
0x18001863e  sub     eax, 2
0x180018641  jz      short loc_1800186C1
0x180018643  sub     eax, 1
0x180018646  jz      short loc_1800186AD
0x180018648  sub     eax, 1
0x18001864b  jz      short loc_180018699
0x18001864d  sub     eax, 1
0x180018650  jz      short loc_180018685
0x180018652  cmp     eax, 3
0x180018655  jz      short loc_180018671
0x180018657  mov     rax, [rcx]
0x18001865a  mov     edx, [rdx]
0x18001865c  mov     rax, [rax+158h]
0x180018663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018668  mov     rax, qword ptr [rbp+var_20]
0x18001866c  jmp     loc_180018712
0x180018671  movups  xmm0, xmmword ptr cs:qword_18001E788
0x180018678  mov     qword ptr [rbp+var_20], 28h ; '('
0x180018680  jmp     loc_180018386
0x180018685  movups  xmm0, xmmword ptr cs:qword_18001E728
0x18001868c  mov     qword ptr [rbp+var_20], 23h ; '#'
0x180018694  jmp     loc_180018386
0x180018699  movups  xmm0, xmmword ptr cs:qword_18001E6C8
0x1800186a0  mov     qword ptr [rbp+var_20], 26h ; '&'
0x1800186a8  jmp     loc_180018386
0x1800186ad  movups  xmm0, xmmword ptr cs:byte_18001E740
0x1800186b4  mov     qword ptr [rbp+var_20], 1Eh
0x1800186bc  jmp     loc_180018386
0x1800186c1  movups  xmm0, xmmword ptr cs:qword_18001E758
0x1800186c8  mov     qword ptr [rbp+var_20], 37h ; '7'
0x1800186d0  jmp     loc_180018386
0x1800186d5  movups  xmm0, xmmword ptr cs:qword_18001E4B8
0x1800186dc  mov     qword ptr [rbp+var_20], 1Fh
0x1800186e4  jmp     loc_180018386
0x1800186e9  movups  xmm0, xmmword ptr cs:byte_18001E7A0
0x1800186f0  mov     qword ptr [rbp+var_20], 21h ; '!'
0x1800186f8  jmp     loc_180018386
0x1800186fd  movups  xmm0, xmmword ptr cs:byte_18001E6E0
0x180018704  mov     eax, 1Ah
0x180018709  mov     qword ptr [rbp+var_20], rax
0x18001870d  movdqu  [rbp+var_20+8], xmm0
0x180018712  test    rax, rax
0x180018715  jz      short loc_18001872D
0x180018717  mov     rax, [rbx]
0x18001871a  lea     rdx, [rbp+var_20]
0x18001871e  mov     rcx, rbx
0x180018721  mov     rax, [rax+0C8h]
0x180018728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001872d  mov     rcx, [rbp+var_8]
0x180018731  xor     rcx, rsp; StackCookie
0x180018734  call    __security_check_cookie
0x180018739  mov     rbx, [rsp+40h+arg_10]
0x18001873e  add     rsp, 40h
0x180018742  pop     rbp
0x180018743  retn
```
