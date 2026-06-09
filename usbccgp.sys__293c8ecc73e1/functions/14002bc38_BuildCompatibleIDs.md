# BuildCompatibleIDs

- ea: `0x14002bc38`
- end: `0x14002bef5`
- name: `BuildCompatibleIDs`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400249d4`

## callees

- `0x14002231c`
- `0x14002bc38`

## string_xrefs

- `0x14002bd20`: `USB\COMPAT_VID_nnnn&Class_nn&SubClass_nn&Prot_nn`

## pseudocode

```c
__int64 __fastcall BuildCompatibleIDs(
        _BYTE *a1,
        _BYTE *a2,
        unsigned __int16 a3,
        unsigned __int8 a4,
        wchar_t a5,
        wchar_t a6)
{
  wchar_t v6; // r14
  wchar_t v7; // r15
  wchar_t v8; // r12
  wchar_t v9; // r13
  wchar_t v10; // di
  wchar_t v11; // bx
  wchar_t v12; // bp
  wchar_t v13; // si
  wchar_t v14; // ax
  __int64 v15; // rax
  __int64 v16; // r9
  unsigned int v17; // r10d
  wchar_t *v18; // r8
  _WORD *v19; // rdx
  __int64 v20; // rax
  _OWORD *v21; // rcx
  __int128 v22; // xmm1
  wchar_t v23; // ax
  __int16 v24; // ax
  unsigned int v26; // [rsp+88h] [rbp+20h] BYREF

  v26 = 0;
  v6 = NibbleW[a3 & 0xF];
  v7 = NibbleW[(unsigned __int8)a3 >> 4];
  v8 = NibbleW[HIBYTE(a3) & 0xF];
  v9 = NibbleW[(unsigned __int64)a3 >> 12];
  v10 = NibbleW[a4 & 0xF];
  v11 = NibbleW[(unsigned __int64)a4 >> 4];
  v12 = NibbleW[a5 & 0xF];
  v13 = NibbleW[(unsigned __int64)(unsigned __int8)a5 >> 4];
  v14 = NibbleW[a6 & 0xF];
  a5 = NibbleW[(unsigned __int64)(unsigned __int8)a6 >> 4];
  a6 = v14;
  v15 = BuildMSOSCompatibleIDs(a1, a2, 382, &v26);
  v16 = v15;
  if ( v15 )
  {
    v17 = v26;
    v18 = aUsbCompatVidNn;
    v19 = (_WORD *)(v15 + 2 * ((unsigned __int64)v26 >> 1));
    v20 = 2;
    v21 = v19;
    do
    {
      *v21 = *(_OWORD *)v18;
      v21[1] = *((_OWORD *)v18 + 1);
      v21[2] = *((_OWORD *)v18 + 2);
      v21[3] = *((_OWORD *)v18 + 3);
      v21[4] = *((_OWORD *)v18 + 4);
      v21[5] = *((_OWORD *)v18 + 5);
      v21[6] = *((_OWORD *)v18 + 6);
      v22 = *((_OWORD *)v18 + 7);
      v18 += 64;
      v21[7] = v22;
      v21 += 8;
      --v20;
    }
    while ( v20 );
    v23 = a5;
    *v21 = *(_OWORD *)v18;
    v21[1] = *((_OWORD *)v18 + 1);
    v21[2] = *((_OWORD *)v18 + 2);
    v21[3] = *((_OWORD *)v18 + 3);
    v21[4] = *((_OWORD *)v18 + 4);
    v21[5] = *((_OWORD *)v18 + 5);
    v21[6] = *((_OWORD *)v18 + 6);
    *(_OWORD *)((char *)v21 + 110) = *(_OWORD *)(v18 + 55);
    v19[149] = v23;
    v19[46] = v23;
    v24 = a6;
    v19[150] = a6;
    v19[47] = v24;
    v19[105] = v9;
    v19[64] = v9;
    v19[15] = v9;
    v19[106] = v8;
    v19[65] = v8;
    v19[16] = v8;
    v19[107] = v7;
    v19[66] = v7;
    v19[17] = v7;
    v19[108] = v6;
    v19[67] = v6;
    v19[18] = v6;
    v19[187] = v11;
    v19[162] = v11;
    v19[129] = v11;
    v19[116] = v11;
    v19[75] = v11;
    v19[26] = v11;
    v19[188] = v10;
    v19[163] = v10;
    v19[130] = v10;
    v19[117] = v10;
    v19[76] = v10;
    v19[27] = v10;
    v19[174] = v13;
    v19[141] = v13;
    v19[87] = v13;
    v19[38] = v13;
    v19[175] = v12;
    v19[142] = v12;
    v19[88] = v12;
    v19[39] = v12;
    *(_WORD *)(v16 + 2 * ((unsigned __int64)(v17 + 382) >> 1)) = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x14002bc38  mov     rax, rsp
0x14002bc3b  push    rbx
0x14002bc3c  push    rbp
0x14002bc3d  push    rsi
0x14002bc3e  push    rdi
0x14002bc3f  push    r12
0x14002bc41  push    r13
0x14002bc43  push    r14
0x14002bc45  push    r15
0x14002bc47  sub     rsp, 28h
0x14002bc4b  mov     dword ptr [rax+20h], 0
0x14002bc52  mov     r11, rcx
0x14002bc55  movzx   r10d, r8w
0x14002bc59  lea     r8, NibbleW; "0123456789abcdef"
0x14002bc60  movzx   ecx, r9b
0x14002bc64  mov     eax, r10d
0x14002bc67  and     eax, 0Fh
0x14002bc6a  lea     r9, [rsp+68h+arg_18]
0x14002bc72  movzx   r14d, word ptr [r8+rax*2]
0x14002bc77  mov     eax, r10d
0x14002bc7a  shr     rax, 4
0x14002bc7e  and     eax, 0Fh
0x14002bc81  movzx   r15d, word ptr [r8+rax*2]
0x14002bc86  mov     eax, r10d
0x14002bc89  shr     rax, 8
0x14002bc8d  and     eax, 0Fh
0x14002bc90  shr     r10, 0Ch
0x14002bc94  movzx   r12d, word ptr [r8+rax*2]
0x14002bc99  mov     eax, ecx
0x14002bc9b  movzx   r13d, word ptr [r8+r10*2]
0x14002bca0  and     ecx, 0Fh
0x14002bca3  shr     rax, 4
0x14002bca7  movzx   edi, word ptr [r8+rcx*2]
0x14002bcac  movzx   ebx, word ptr [r8+rax*2]
0x14002bcb1  movzx   ecx, byte ptr [rsp+68h+arg_20]
0x14002bcb9  mov     eax, ecx
0x14002bcbb  and     ecx, 0Fh
0x14002bcbe  shr     rax, 4
0x14002bcc2  movzx   ebp, word ptr [r8+rcx*2]
0x14002bcc7  movzx   esi, word ptr [r8+rax*2]
0x14002bccc  movzx   ecx, byte ptr [rsp+68h+arg_28]
0x14002bcd4  mov     eax, ecx
0x14002bcd6  and     ecx, 0Fh
0x14002bcd9  shr     rax, 4
0x14002bcdd  movzx   r8d, word ptr [r8+rax*2]
0x14002bce2  lea     rax, NibbleW; "0123456789abcdef"
0x14002bce9  movzx   eax, word ptr [rax+rcx*2]
0x14002bced  mov     rcx, r11
0x14002bcf0  mov     [rsp+68h+arg_20], r8w
0x14002bcf9  mov     r8d, 17Eh
0x14002bcff  mov     [rsp+68h+arg_28], ax
0x14002bd07  call    BuildMSOSCompatibleIDs
0x14002bd0c  mov     r9, rax
0x14002bd0f  test    rax, rax
0x14002bd12  jz      loc_14002BEE0
0x14002bd18  mov     r10d, [rsp+68h+arg_18]
0x14002bd20  lea     r8, aUsbCompatVidNn; "USB\\COMPAT_VID_nnnn&Class_nn&SubClass_"...
0x14002bd27  mov     ecx, r10d
0x14002bd2a  shr     rcx, 1
0x14002bd2d  lea     rdx, [rax+rcx*2]
0x14002bd31  mov     eax, 2
0x14002bd36  mov     rcx, rdx
0x14002bd39  lea     r11d, [rax+7Eh]
0x14002bd3d  movups  xmm0, xmmword ptr [r8]
0x14002bd41  movups  xmmword ptr [rcx], xmm0
0x14002bd44  movups  xmm1, xmmword ptr [r8+10h]
0x14002bd49  movups  xmmword ptr [rcx+10h], xmm1
0x14002bd4d  movups  xmm0, xmmword ptr [r8+20h]
0x14002bd52  movups  xmmword ptr [rcx+20h], xmm0
0x14002bd56  movups  xmm1, xmmword ptr [r8+30h]
0x14002bd5b  movups  xmmword ptr [rcx+30h], xmm1
0x14002bd5f  movups  xmm0, xmmword ptr [r8+40h]
0x14002bd64  movups  xmmword ptr [rcx+40h], xmm0
0x14002bd68  movups  xmm1, xmmword ptr [r8+50h]
0x14002bd6d  movups  xmmword ptr [rcx+50h], xmm1
0x14002bd71  movups  xmm0, xmmword ptr [r8+60h]
0x14002bd76  movups  xmmword ptr [rcx+60h], xmm0
0x14002bd7a  movups  xmm1, xmmword ptr [r8+70h]
0x14002bd7f  add     r8, r11
0x14002bd82  movups  xmmword ptr [rcx+70h], xmm1
0x14002bd86  add     rcx, r11
0x14002bd89  sub     rax, 1
0x14002bd8d  jnz     short loc_14002BD3D
0x14002bd8f  movups  xmm0, xmmword ptr [r8]
0x14002bd93  movzx   eax, [rsp+68h+arg_20]
0x14002bd9b  movups  xmmword ptr [rcx], xmm0
0x14002bd9e  movups  xmm1, xmmword ptr [r8+10h]
0x14002bda3  movups  xmmword ptr [rcx+10h], xmm1
0x14002bda7  movups  xmm0, xmmword ptr [r8+20h]
0x14002bdac  movups  xmmword ptr [rcx+20h], xmm0
0x14002bdb0  movups  xmm1, xmmword ptr [r8+30h]
0x14002bdb5  movups  xmmword ptr [rcx+30h], xmm1
0x14002bdb9  movups  xmm0, xmmword ptr [r8+40h]
0x14002bdbe  movups  xmmword ptr [rcx+40h], xmm0
0x14002bdc2  movups  xmm1, xmmword ptr [r8+50h]
0x14002bdc7  movups  xmmword ptr [rcx+50h], xmm1
0x14002bdcb  movups  xmm0, xmmword ptr [r8+60h]
0x14002bdd0  movups  xmmword ptr [rcx+60h], xmm0
0x14002bdd4  movups  xmm1, xmmword ptr [r8+6Eh]
0x14002bdd9  movups  xmmword ptr [rcx+6Eh], xmm1
0x14002bddd  mov     [rdx+12Ah], ax
0x14002bde4  lea     ecx, [r10+17Eh]
0x14002bdeb  mov     [rdx+5Ch], ax
0x14002bdef  movzx   eax, [rsp+68h+arg_28]
0x14002bdf7  shr     rcx, 1
0x14002bdfa  mov     [rdx+12Ch], ax
0x14002be01  mov     [rdx+5Eh], ax
0x14002be05  xor     eax, eax
0x14002be07  mov     [rdx+0D2h], r13w
0x14002be0f  mov     [rdx+80h], r13w
0x14002be17  mov     [rdx+1Eh], r13w
0x14002be1c  mov     [rdx+0D4h], r12w
0x14002be24  mov     [rdx+82h], r12w
0x14002be2c  mov     [rdx+20h], r12w
0x14002be31  mov     [rdx+0D6h], r15w
0x14002be39  mov     [rdx+84h], r15w
0x14002be41  mov     [rdx+22h], r15w
0x14002be46  mov     [rdx+0D8h], r14w
0x14002be4e  mov     [rdx+86h], r14w
0x14002be56  mov     [rdx+24h], r14w
0x14002be5b  mov     [rdx+176h], bx
0x14002be62  mov     [rdx+144h], bx
0x14002be69  mov     [rdx+102h], bx
0x14002be70  mov     [rdx+0E8h], bx
0x14002be77  mov     [rdx+96h], bx
0x14002be7e  mov     [rdx+34h], bx
0x14002be82  mov     [rdx+178h], di
0x14002be89  mov     [rdx+146h], di
0x14002be90  mov     [rdx+104h], di
0x14002be97  mov     [rdx+0EAh], di
0x14002be9e  mov     [rdx+98h], di
0x14002bea5  mov     [rdx+36h], di
0x14002bea9  mov     [rdx+15Ch], si
0x14002beb0  mov     [rdx+11Ah], si
0x14002beb7  mov     [rdx+0AEh], si
0x14002bebe  mov     [rdx+4Ch], si
0x14002bec2  mov     [rdx+15Eh], bp
0x14002bec9  mov     [rdx+11Ch], bp
0x14002bed0  mov     [rdx+0B0h], bp
0x14002bed7  mov     [rdx+4Eh], bp
0x14002bedb  mov     [r9+rcx*2], ax
0x14002bee0  mov     rax, r9
0x14002bee3  add     rsp, 28h
0x14002bee7  pop     r15
0x14002bee9  pop     r14
0x14002beeb  pop     r13
0x14002beed  pop     r12
0x14002beef  pop     rdi
0x14002bef0  pop     rsi
0x14002bef1  pop     rbp
0x14002bef2  pop     rbx
0x14002bef3  retn
```
