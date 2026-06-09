# VsmmPhuStorepHvPartitionDeserialize

- ea: `0x1400b6088`
- end: `0x1400b635a`
- name: `VsmmPhuStorepHvPartitionDeserialize`
- size: `722`
- prototype: `__int64 __fastcall(int, __int64 *, int, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400b909c`

## callees

- `0x140021650`
- `0x140021800`
- `0x14002f524`
- `0x1400b6088`
- `0x1400b6360`
- `0x1400b8974`
- `0x1400b8c94`

## import_xrefs

- `winhvr!WinHvGetPartitionProperty` at `0x1400b62b4`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b62b4`

## string_xrefs

- `0x1400b612c`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b617a`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b61c8`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b61f4`: `VsmmPhuStorepHvPartitionDeserialize`
- `0x1400b6283`: `VsmmPhuStorepHvPartitionDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepHvPartitionDeserialize(int a1, __int64 *a2, int a3, __int64 a4, _OWORD *a5)
{
  int Structure; // ebx
  __int64 v10; // rax
  char v11; // bl
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  bool v15; // sf
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v21; // [rsp+30h] [rbp-71h] BYREF
  int v22[4]; // [rsp+38h] [rbp-69h] BYREF
  int v23; // [rsp+48h] [rbp-59h] BYREF
  _OWORD v24[4]; // [rsp+50h] [rbp-51h] BYREF
  __int128 v25; // [rsp+90h] [rbp-11h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-1h]
  __int128 v27; // [rsp+B0h] [rbp+Fh]

  v21 = 0;
  v23 = 0;
  *(_OWORD *)v22 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  memset(v24, 0, sizeof(v24));
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, a3, (int)v22, 20, v22, 0);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7037);
    return (unsigned int)Structure;
  }
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v22[1], (int)&v22[2], 48, &v25, 0);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7050);
    return (unsigned int)Structure;
  }
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v22[3], (int)&v23, 64, v24, 0);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7071);
    return (unsigned int)Structure;
  }
  if ( !LOBYTE(v24[0]) )
  {
    Structure = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepHvPartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7078);
    return (unsigned int)Structure;
  }
  v10 = *a2;
  v11 = 0;
  v12 = *a2 & 1;
  if ( (*a2 & 2) != 0 )
  {
    if ( v12 )
    {
      v13 = *((_QWORD *)&v24[3] + 1);
      if ( *((_QWORD *)&v24[3] + 1) )
      {
        if ( (v10 & 4) != 0 )
        {
          BYTE1(v24[0]) &= 0xFCu;
          *((_QWORD *)&v24[0] + 1) = *((_QWORD *)&v24[3] + 1);
          memset(&v24[1], 0, 48);
          LODWORD(v24[1]) = 1;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    if ( (v10 & 4) != 0 )
    {
      v13 = *((_QWORD *)&v24[0] + 1);
      v11 = 1;
      if ( v12 )
        v13 = 0;
      *((_QWORD *)&v24[0] + 1) = v13;
      goto LABEL_21;
    }
    if ( v12 )
    {
      Structure = -1073741713;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepHvPartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        7140);
      return (unsigned int)Structure;
    }
  }
  v13 = *((_QWORD *)&v24[0] + 1);
LABEL_21:
  v14 = *((_QWORD *)&v27 + 1);
  if ( (*((_QWORD *)&v27 + 1) & 0x10000LL) == 0 )
  {
    if ( v13 )
    {
      v15 = (int)WinHvGetPartitionProperty(v13, 524289, &v21) < 0;
      v14 = *((_QWORD *)&v27 + 1);
      if ( !v15 )
        v14 = *((_QWORD *)&v27 + 1) & 0xFFFFFFFFFFFF3FFFuLL | 0x4000;
    }
  }
  *((_QWORD *)&v27 + 1) = v14 | 0x10000;
  VsmmPhuStorepSerializationChargeIncrease(a4, 144, 1);
  v16 = v26;
  *a5 = v25;
  v17 = v27;
  a5[1] = v16;
  a5[3] = v24[0];
  v18 = v24[2];
  a5[2] = v17;
  a5[4] = v24[1];
  v19 = v24[3];
  a5[5] = v18;
  a5[6] = v19;
  if ( v11 )
    VsmmPhuStorepHvPartitionFree(a4, a5);
  return 0;
}

```

## disassembly

```asm
0x1400b6088  mov     [rsp-8+arg_8], rbx
0x1400b608d  push    rbp
0x1400b608e  push    rsi
0x1400b608f  push    rdi
0x1400b6090  push    r14
0x1400b6092  push    r15
0x1400b6094  lea     rbp, [rsp-2Fh]
0x1400b6099  sub     rsp, 0D0h
0x1400b60a0  mov     rax, cs:__security_cookie
0x1400b60a7  xor     rax, rsp
0x1400b60aa  mov     [rbp+4Fh+var_30], rax
0x1400b60ae  mov     rdi, [rbp+4Fh+arg_20]
0x1400b60b2  xorps   xmm1, xmm1
0x1400b60b5  xor     eax, eax
0x1400b60b7  mov     [rbp+4Fh+var_C0], 0
0x1400b60bf  mov     ebx, r8d
0x1400b60c2  mov     [rbp+4Fh+var_A8], eax
0x1400b60c5  mov     r15, rdx
0x1400b60c8  mov     rsi, rcx
0x1400b60cb  xorps   xmm0, xmm0
0x1400b60ce  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1400b60d2  lea     r8d, [rax+40h]; Size
0x1400b60d6  xor     edx, edx; Val
0x1400b60d8  mov     r14, r9
0x1400b60db  movups  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x1400b60df  movups  [rbp+4Fh+var_60], xmm1
0x1400b60e3  movups  [rbp+4Fh+var_50], xmm1
0x1400b60e7  movups  [rbp+4Fh+var_40], xmm1
0x1400b60eb  call    memset
0x1400b60f0  lea     rax, [rbp+4Fh+var_B8]
0x1400b60f4  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b60fd  mov     r9d, 14h; int
0x1400b6103  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b6108  lea     r8, [rbp+4Fh+var_B8]; int
0x1400b610c  mov     edx, ebx; int
0x1400b610e  mov     rcx, rsi; int
0x1400b6111  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b6116  mov     ebx, eax
0x1400b6118  test    eax, eax
0x1400b611a  jns     short loc_1400B613D
0x1400b611c  mov     r9d, eax
0x1400b611f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6126  mov     r8d, 1B7Dh
0x1400b612c  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b6133  call    VidTraceErrorStatusInternal0
0x1400b6138  jmp     loc_1400B6334
0x1400b613d  mov     edx, [rbp+4Fh+var_B8+4]; int
0x1400b6140  lea     rax, [rbp+4Fh+var_60]
0x1400b6144  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b614d  lea     r8, [rbp+4Fh+var_B8+8]; int
0x1400b6151  mov     r9d, 30h ; '0'; int
0x1400b6157  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b615c  mov     rcx, rsi; int
0x1400b615f  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b6164  mov     ebx, eax
0x1400b6166  test    eax, eax
0x1400b6168  jns     short loc_1400B618B
0x1400b616a  mov     r9d, eax
0x1400b616d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6174  mov     r8d, 1B8Ah
0x1400b617a  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b6181  call    VidTraceErrorStatusInternal0
0x1400b6186  jmp     loc_1400B6334
0x1400b618b  mov     edx, [rbp+4Fh+var_B8+0Ch]; int
0x1400b618e  lea     rax, [rbp+4Fh+var_A0]
0x1400b6192  mov     [rsp+0F0h+var_C8], 0; __int64
0x1400b619b  lea     r8, [rbp+4Fh+var_A8]; int
0x1400b619f  mov     r9d, 40h ; '@'; int
0x1400b61a5  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b61aa  mov     rcx, rsi; int
0x1400b61ad  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b61b2  mov     ebx, eax
0x1400b61b4  test    eax, eax
0x1400b61b6  jns     short loc_1400B61D9
0x1400b61b8  mov     r9d, eax
0x1400b61bb  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b61c2  mov     r8d, 1B9Fh
0x1400b61c8  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b61cf  call    VidTraceErrorStatusInternal0
0x1400b61d4  jmp     loc_1400B6334
0x1400b61d9  cmp     byte ptr [rbp+4Fh+var_A0], 0
0x1400b61dd  jnz     short loc_1400B6205
0x1400b61df  mov     ebx, 0C000090Bh
0x1400b61e4  mov     r9d, ebx
0x1400b61e7  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b61ee  mov     r8d, 1BA6h
0x1400b61f4  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b61fb  call    VidTraceErrorStatusInternal0
0x1400b6200  jmp     loc_1400B6334
0x1400b6205  mov     rax, [r15]
0x1400b6208  xor     bl, bl
0x1400b620a  mov     rdx, rax
0x1400b620d  and     edx, 1
0x1400b6210  test    al, 2
0x1400b6212  jz      short loc_1400B6250
0x1400b6214  test    rdx, rdx
0x1400b6217  jz      short loc_1400B6294
0x1400b6219  mov     rcx, qword ptr [rbp+4Fh+var_70+8]
0x1400b621d  test    rcx, rcx
0x1400b6220  jz      short loc_1400B6294
0x1400b6222  test    al, 4
0x1400b6224  jz      short loc_1400B6294
0x1400b6226  and     byte ptr [rbp+4Fh+var_A0+1], 0FCh
0x1400b622a  xorps   xmm0, xmm0
0x1400b622d  xor     eax, eax
0x1400b622f  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1400b6233  movups  [rbp+4Fh+var_90], xmm0
0x1400b6237  mov     qword ptr [rbp+4Fh+var_70], rax
0x1400b623b  mov     qword ptr [rbp+4Fh+var_70+8], 0
0x1400b6243  movups  [rbp+4Fh+var_80], xmm0
0x1400b6247  mov     dword ptr [rbp+4Fh+var_90], 1
0x1400b624e  jmp     short loc_1400B6298
0x1400b6250  test    al, 4
0x1400b6252  jz      short loc_1400B6269
0x1400b6254  mov     rcx, qword ptr [rbp+4Fh+var_A0+8]
0x1400b6258  xor     eax, eax
0x1400b625a  test    rdx, rdx
0x1400b625d  mov     bl, 1
0x1400b625f  cmovnz  rcx, rax
0x1400b6263  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1400b6267  jmp     short loc_1400B6298
0x1400b6269  test    rdx, rdx
0x1400b626c  jz      short loc_1400B6294
0x1400b626e  mov     ebx, 0C000006Fh
0x1400b6273  mov     r9d, ebx
0x1400b6276  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b627d  mov     r8d, 1BE4h
0x1400b6283  lea     rcx, aVsmmphustoreph; "VsmmPhuStorepHvPartitionDeserialize"
0x1400b628a  call    VidTraceErrorStatusInternal0
0x1400b628f  jmp     loc_1400B6334
0x1400b6294  mov     rcx, qword ptr [rbp+4Fh+var_A0+8]
0x1400b6298  mov     rax, qword ptr [rbp+4Fh+var_40+8]
0x1400b629c  mov     esi, 10000h
0x1400b62a1  test    rsi, rax
0x1400b62a4  jnz     short loc_1400B62D2
0x1400b62a6  test    rcx, rcx
0x1400b62a9  jz      short loc_1400B62D2
0x1400b62ab  lea     r8, [rbp+4Fh+var_C0]
0x1400b62af  mov     edx, 80001h
0x1400b62b4  call    cs:__imp_WinHvGetPartitionProperty
0x1400b62bb  nop     dword ptr [rax+rax+00h]
0x1400b62c0  test    eax, eax
0x1400b62c2  mov     rax, qword ptr [rbp+4Fh+var_40+8]
0x1400b62c6  js      short loc_1400B62D2
0x1400b62c8  btr     rax, 0Fh
0x1400b62cd  bts     rax, 0Eh
0x1400b62d2  or      rax, rsi
0x1400b62d5  mov     edx, 90h
0x1400b62da  mov     r8d, 1
0x1400b62e0  mov     qword ptr [rbp+4Fh+var_40+8], rax
0x1400b62e4  mov     rcx, r14
0x1400b62e7  call    VsmmPhuStorepSerializationChargeIncrease
0x1400b62ec  movups  xmm0, [rbp+4Fh+var_60]
0x1400b62f0  movups  xmm1, [rbp+4Fh+var_50]
0x1400b62f4  movups  xmmword ptr [rdi], xmm0
0x1400b62f7  movups  xmm0, [rbp+4Fh+var_40]
0x1400b62fb  movups  xmmword ptr [rdi+10h], xmm1
0x1400b62ff  movaps  xmm1, [rbp+4Fh+var_A0]
0x1400b6303  movups  xmmword ptr [rdi+30h], xmm1
0x1400b6307  movaps  xmm1, [rbp+4Fh+var_80]
0x1400b630b  movups  xmmword ptr [rdi+20h], xmm0
0x1400b630f  movaps  xmm0, [rbp+4Fh+var_90]
0x1400b6313  movups  xmmword ptr [rdi+40h], xmm0
0x1400b6317  movaps  xmm0, [rbp+4Fh+var_70]
0x1400b631b  movups  xmmword ptr [rdi+50h], xmm1
0x1400b631f  movups  xmmword ptr [rdi+60h], xmm0
0x1400b6323  test    bl, bl
0x1400b6325  jz      short loc_1400B6332
0x1400b6327  mov     rdx, rdi
0x1400b632a  mov     rcx, r14
0x1400b632d  call    VsmmPhuStorepHvPartitionFree
0x1400b6332  xor     ebx, ebx
0x1400b6334  mov     eax, ebx
0x1400b6336  mov     rcx, [rbp+4Fh+var_30]
0x1400b633a  xor     rcx, rsp; StackCookie
0x1400b633d  call    __security_check_cookie
0x1400b6342  mov     rbx, [rsp+0F0h+arg_8]
0x1400b634a  add     rsp, 0D0h
0x1400b6351  pop     r15
0x1400b6353  pop     r14
0x1400b6355  pop     rdi
0x1400b6356  pop     rsi
0x1400b6357  pop     rbp
0x1400b6358  retn
```
