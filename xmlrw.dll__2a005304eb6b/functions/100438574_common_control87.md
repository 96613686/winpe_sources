# common_control87

- ea: `0x100438574`
- end: `0x10043880e`
- name: `common_control87`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100438568`

## callees

- `0x100438574`
- `0x100438bf0`
- `0x100438c00`
- `0x100438fe0`

## pseudocode

```c
__int64 __fastcall common_control87(int a1, int a2)
{
  int v3; // r12d
  unsigned int fpsr; // eax
  __int16 v5; // r10
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // edx
  int v11; // eax
  int v12; // r10d
  int v13; // r10d
  int v14; // r8d
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // r8d
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  int v27; // ebx
  int v28; // ebx

  v3 = a2 & 0x308031F;
  fpsr = get_fpsr();
  v5 = fpsr;
  v6 = (fpsr >> 3) & 0x10 | 8;
  if ( (fpsr & 0x200) == 0 )
    v6 = (fpsr >> 3) & 0x10;
  v7 = v6 | 4;
  if ( (fpsr & 0x400) == 0 )
    v7 = v6;
  v8 = v7 | 2;
  if ( (fpsr & 0x800) == 0 )
    v8 = v7;
  v9 = v8 | 1;
  if ( (fpsr & 0x1000) == 0 )
    v9 = v8;
  v10 = v9 | 0x80000;
  if ( (fpsr & 0x100) == 0 )
    v10 = v9;
  v11 = fpsr & 0x6000;
  if ( v11 )
  {
    switch ( v11 )
    {
      case 8192:
        v10 |= 0x100u;
        break;
      case 16384:
        v10 |= 0x200u;
        break;
      case 24576:
        v10 |= 0x300u;
        break;
    }
  }
  v12 = (v5 & 0x8040) - 64;
  if ( v12 )
  {
    v13 = v12 - 32704;
    if ( v13 )
    {
      if ( v13 == 64 )
        v10 |= 0x1000000u;
    }
    else
    {
      v10 |= 0x3000000u;
    }
  }
  else
  {
    v10 |= 0x2000000u;
  }
  v14 = v3 & a1 | v10 & ~v3;
  if ( v14 != v10 )
  {
    v15 = (8 * (v14 & 0x10)) | 0x200;
    if ( (v14 & 8) == 0 )
      v15 = 8 * (v14 & 0x10);
    v16 = v15 | 0x400;
    if ( (v14 & 4) == 0 )
      v16 = v15;
    v17 = v16 | 0x800;
    if ( (v14 & 2) == 0 )
      v17 = v16;
    v18 = v17 | 0x1000;
    if ( (v14 & 1) == 0 )
      v18 = v17;
    v19 = v18 | 0x100;
    if ( (v14 & 0x80000) == 0 )
      v19 = v18;
    v20 = v14 & 0x300;
    if ( (v14 & 0x300) != 0 )
    {
      switch ( v20 )
      {
        case 256:
          v19 |= 0x2000u;
          break;
        case 512:
          v19 |= 0x4000u;
          break;
        case 768:
          v19 |= 0x6000u;
          break;
      }
    }
    v21 = v14 & 0x3000000;
    switch ( v21 )
    {
      case 16777216:
        v19 |= 0x8040u;
        break;
      case 33554432:
        v19 |= 0x40u;
        break;
      case 50331648:
        v19 |= 0x8000u;
        break;
    }
    if ( byte_10044E9D8 && (v19 & 0x40) != 0 )
    {
      set_fpsr(v19);
    }
    else
    {
      v19 &= ~0x40u;
      set_fpsr(v19);
    }
    v22 = (v19 >> 3) & 0x10 | 8;
    if ( (v19 & 0x200) == 0 )
      v22 = (v19 >> 3) & 0x10;
    v23 = v22 | 4;
    if ( (v19 & 0x400) == 0 )
      v23 = v22;
    v24 = v23 | 2;
    if ( (v19 & 0x800) == 0 )
      v24 = v23;
    v25 = v24 | 1;
    if ( (v19 & 0x1000) == 0 )
      v25 = v24;
    v10 = v25 | 0x80000;
    if ( (v19 & 0x100) == 0 )
      v10 = v25;
    v26 = v19 & 0x6000;
    if ( (v19 & 0x6000) != 0 )
    {
      switch ( v26 )
      {
        case 8192:
          v10 |= 0x100u;
          break;
        case 16384:
          v10 |= 0x200u;
          break;
        case 24576:
          v10 |= 0x300u;
          break;
      }
    }
    v27 = (v19 & 0x8040) - 64;
    if ( v27 )
    {
      v28 = v27 - 32704;
      if ( v28 )
      {
        if ( v28 == 64 )
          v10 |= 0x1000000u;
      }
      else
      {
        v10 |= 0x3000000u;
      }
    }
    else
    {
      v10 |= 0x2000000u;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x100438574  mov     [rsp+arg_8], rbx
0x100438579  mov     [rsp+arg_10], rsi
0x10043857e  push    r12
0x100438580  push    r14
0x100438582  push    r15
0x100438584  sub     rsp, 20h
0x100438588  mov     r12d, edx
0x10043858b  mov     ebx, ecx
0x10043858d  and     r12d, 308031Fh
0x100438594  call    _get_fpsr
0x100438599  mov     r10d, eax
0x10043859c  mov     r9d, eax
0x10043859f  shr     r9d, 3
0x1004385a3  and     r9d, 10h
0x1004385a7  mov     r14d, 200h
0x1004385ad  mov     edx, r9d
0x1004385b0  or      edx, 8
0x1004385b3  test    r14d, eax
0x1004385b6  cmovz   edx, r9d
0x1004385ba  mov     ecx, edx
0x1004385bc  or      ecx, 4
0x1004385bf  bt      eax, 0Ah
0x1004385c3  cmovnb  ecx, edx
0x1004385c6  mov     r9d, 800h
0x1004385cc  mov     edx, ecx
0x1004385ce  or      edx, 2
0x1004385d1  test    r9d, eax
0x1004385d4  cmovz   edx, ecx
0x1004385d7  mov     r11d, 1000h
0x1004385dd  mov     ecx, edx
0x1004385df  or      ecx, 1
0x1004385e2  test    r11d, eax
0x1004385e5  cmovz   ecx, edx
0x1004385e8  mov     esi, 100h
0x1004385ed  mov     edx, ecx
0x1004385ef  bts     edx, 13h
0x1004385f3  test    esi, eax
0x1004385f5  cmovz   edx, ecx
0x1004385f8  mov     r15d, 6000h
0x1004385fe  and     eax, r15d
0x100438601  jz      short loc_100438625
0x100438603  cmp     eax, 2000h
0x100438608  jz      short loc_100438623
0x10043860a  cmp     eax, 4000h
0x10043860f  jz      short loc_10043861E
0x100438611  cmp     eax, r15d
0x100438614  jnz     short loc_100438625
0x100438616  or      edx, 300h
0x10043861c  jmp     short loc_100438625
0x10043861e  or      edx, r14d
0x100438621  jmp     short loc_100438625
0x100438623  or      edx, esi
0x100438625  and     r10d, 8040h
0x10043862c  sub     r10d, 40h ; '@'
0x100438630  jz      short loc_10043864F
0x100438632  sub     r10d, 7FC0h
0x100438639  jz      short loc_100438647
0x10043863b  cmp     r10d, 40h ; '@'
0x10043863f  jnz     short loc_100438653
0x100438641  bts     edx, 18h
0x100438645  jmp     short loc_100438653
0x100438647  or      edx, 3000000h
0x10043864d  jmp     short loc_100438653
0x10043864f  bts     edx, 19h
0x100438653  mov     r8d, r12d
0x100438656  not     r8d
0x100438659  and     r8d, edx
0x10043865c  and     ebx, r12d
0x10043865f  or      r8d, ebx
0x100438662  cmp     r8d, edx
0x100438665  jz      loc_1004387F7
0x10043866b  mov     ecx, r8d
0x10043866e  and     ecx, 10h
0x100438671  shl     ecx, 3
0x100438674  mov     edx, ecx
0x100438676  or      edx, r14d
0x100438679  test    r8b, 8
0x10043867d  cmovz   edx, ecx
0x100438680  mov     ecx, edx
0x100438682  bts     ecx, 0Ah
0x100438686  test    r8b, 4
0x10043868a  cmovz   ecx, edx
0x10043868d  mov     edx, ecx
0x10043868f  or      edx, r9d
0x100438692  test    r8b, 2
0x100438696  cmovz   edx, ecx
0x100438699  mov     ecx, edx
0x10043869b  or      ecx, r11d
0x10043869e  test    r8b, 1
0x1004386a2  cmovz   ecx, edx
0x1004386a5  mov     ebx, ecx
0x1004386a7  or      ebx, esi
0x1004386a9  bt      r8d, 13h
0x1004386ae  cmovnb  ebx, ecx
0x1004386b1  mov     eax, r8d
0x1004386b4  and     eax, 300h
0x1004386b9  jz      short loc_1004386DE
0x1004386bb  cmp     eax, esi
0x1004386bd  jz      short loc_1004386DA
0x1004386bf  cmp     eax, r14d
0x1004386c2  jz      short loc_1004386D4
0x1004386c4  mov     [rsp+38h+arg_0], ebx
0x1004386c8  cmp     eax, 300h
0x1004386cd  jnz     short loc_1004386E2
0x1004386cf  or      ebx, r15d
0x1004386d2  jmp     short loc_1004386DE
0x1004386d4  bts     ebx, 0Eh
0x1004386d8  jmp     short loc_1004386DE
0x1004386da  bts     ebx, 0Dh
0x1004386de  mov     [rsp+38h+arg_0], ebx
0x1004386e2  and     r8d, 3000000h
0x1004386e9  cmp     r8d, 1000000h
0x1004386f0  jz      short loc_10043870F
0x1004386f2  cmp     r8d, 2000000h
0x1004386f9  jz      short loc_10043870A
0x1004386fb  cmp     r8d, 3000000h
0x100438702  jnz     short loc_100438719
0x100438704  bts     ebx, 0Fh
0x100438708  jmp     short loc_100438715
0x10043870a  or      ebx, 40h
0x10043870d  jmp     short loc_100438715
0x10043870f  or      ebx, 8040h
0x100438715  mov     [rsp+38h+arg_0], ebx
0x100438719  cmp     cs:byte_10044E9D8, 0
0x100438720  jz      short loc_100438758
0x100438722  test    bl, 40h
0x100438725  jz      short loc_100438758
0x100438727  mov     ecx, ebx
0x100438729  call    _set_fpsr
0x10043872e  jmp     short loc_100438762
0x100438730  mov     cs:byte_10044E9D8, 0
0x100438737  mov     ebx, [rsp+38h+arg_0]
0x10043873b  and     ebx, 0FFFFFFBFh
0x10043873e  mov     ecx, ebx
0x100438740  call    _set_fpsr
0x100438745  mov     esi, 100h
0x10043874a  mov     r14d, 200h
0x100438750  mov     r15d, 6000h
0x100438756  jmp     short loc_100438762
0x100438758  and     ebx, 0FFFFFFBFh
0x10043875b  mov     ecx, ebx
0x10043875d  call    _set_fpsr
0x100438762  mov     ecx, ebx
0x100438764  shr     ecx, 3
0x100438767  and     ecx, 10h
0x10043876a  mov     edx, ecx
0x10043876c  or      edx, 8
0x10043876f  test    r14d, ebx
0x100438772  cmovz   edx, ecx
0x100438775  mov     ecx, edx
0x100438777  or      ecx, 4
0x10043877a  bt      ebx, 0Ah
0x10043877e  cmovnb  ecx, edx
0x100438781  mov     edx, ecx
0x100438783  or      edx, 2
0x100438786  bt      ebx, 0Bh
0x10043878a  cmovnb  edx, ecx
0x10043878d  mov     ecx, edx
0x10043878f  or      ecx, 1
0x100438792  bt      ebx, 0Ch
0x100438796  cmovnb  ecx, edx
0x100438799  mov     edx, ecx
0x10043879b  bts     edx, 13h
0x10043879f  test    esi, ebx
0x1004387a1  cmovz   edx, ecx
0x1004387a4  mov     eax, ebx
0x1004387a6  and     eax, r15d
0x1004387a9  jz      short loc_1004387CD
0x1004387ab  cmp     eax, 2000h
0x1004387b0  jz      short loc_1004387CB
0x1004387b2  cmp     eax, 4000h
0x1004387b7  jz      short loc_1004387C6
0x1004387b9  cmp     eax, r15d
0x1004387bc  jnz     short loc_1004387CD
0x1004387be  or      edx, 300h
0x1004387c4  jmp     short loc_1004387CD
0x1004387c6  or      edx, r14d
0x1004387c9  jmp     short loc_1004387CD
0x1004387cb  or      edx, esi
0x1004387cd  and     ebx, 8040h
0x1004387d3  sub     ebx, 40h ; '@'
0x1004387d6  jz      short loc_1004387F3
0x1004387d8  sub     ebx, 7FC0h
0x1004387de  jz      short loc_1004387EB
0x1004387e0  cmp     ebx, 40h ; '@'
0x1004387e3  jnz     short loc_1004387F7
0x1004387e5  bts     edx, 18h
0x1004387e9  jmp     short loc_1004387F7
0x1004387eb  or      edx, 3000000h
0x1004387f1  jmp     short loc_1004387F7
0x1004387f3  bts     edx, 19h
0x1004387f7  mov     eax, edx
0x1004387f9  mov     rbx, [rsp+38h+arg_8]
0x1004387fe  mov     rsi, [rsp+38h+arg_10]
0x100438803  add     rsp, 20h
0x100438807  pop     r15
0x100438809  pop     r14
0x10043880b  pop     r12
0x10043880d  retn
0x10043ad10  push    rbp
0x10043ad12  sub     rsp, 20h
0x10043ad16  mov     rbp, rdx
0x10043ad19  mov     rax, [rcx]
0x10043ad1c  cmp     dword ptr [rax], 0C0000005h
0x10043ad22  jz      short loc_10043AD30
0x10043ad24  cmp     dword ptr [rax], 0C000001Dh
0x10043ad2a  jz      short loc_10043AD30
0x10043ad2c  xor     eax, eax
0x10043ad2e  jmp     short loc_10043AD35
0x10043ad30  mov     eax, 1
0x10043ad35  add     rsp, 20h
0x10043ad39  pop     rbp
0x10043ad3a  retn
```
