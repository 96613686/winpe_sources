# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x180005afc`
- end: `0x180005c84`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004304`
- `0x180004a60`
- `0x180005488`

## callees

- `0x180005afc`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)&FH4::s_negLengthTab + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x180005afc  xor     eax, eax
0x180005afe  lea     r11, cs:180000000h
0x180005b05  mov     [rcx+18h], al
0x180005b08  xorps   xmm0, xmm0
0x180005b0b  mov     [rcx+1Ch], rax
0x180005b0f  mov     r8, rcx
0x180005b12  mov     [rcx+24h], rax
0x180005b16  movups  xmmword ptr [rcx+30h], xmm0
0x180005b1a  mov     rax, [rcx+8]
0x180005b1e  mov     r10b, [rax]
0x180005b21  lea     rdx, [rax+1]
0x180005b25  mov     [rcx+18h], r10b
0x180005b29  mov     [rcx+8], rdx
0x180005b2d  test    r10b, 1
0x180005b31  jz      short loc_180005B5A
0x180005b33  movzx   ecx, byte ptr [rdx]
0x180005b36  and     ecx, 0Fh
0x180005b39  movsx   rax, byte ptr [rcx+r11+14640h]
0x180005b42  mov     cl, [rcx+r11+14650h]
0x180005b4a  sub     rdx, rax
0x180005b4d  mov     eax, [rdx-4]
0x180005b50  shr     eax, cl
0x180005b52  mov     [r8+1Ch], eax
0x180005b56  mov     [r8+8], rdx
0x180005b5a  test    r10b, 2
0x180005b5e  jz      short loc_180005B6E
0x180005b60  mov     eax, [rdx]
0x180005b62  add     rdx, 4
0x180005b66  mov     [r8+8], rdx
0x180005b6a  mov     [r8+20h], eax
0x180005b6e  test    r10b, 4
0x180005b72  jz      short loc_180005B9B
0x180005b74  movzx   ecx, byte ptr [rdx]
0x180005b77  and     ecx, 0Fh
0x180005b7a  movsx   rax, byte ptr [rcx+r11+14640h]
0x180005b83  mov     cl, [rcx+r11+14650h]
0x180005b8b  sub     rdx, rax
0x180005b8e  mov     eax, [rdx-4]
0x180005b91  shr     eax, cl
0x180005b93  mov     [r8+24h], eax
0x180005b97  mov     [r8+8], rdx
0x180005b9b  mov     eax, [rdx]
0x180005b9d  lea     r9, [rdx+4]
0x180005ba1  mov     [r8+28h], eax
0x180005ba5  mov     al, r10b
0x180005ba8  and     al, 30h
0x180005baa  mov     [r8+8], r9
0x180005bae  test    r10b, 8
0x180005bb2  jz      short loc_180005BEF
0x180005bb4  cmp     al, 10h
0x180005bb6  jnz     short loc_180005BC8
0x180005bb8  movsxd  rcx, dword ptr [r9]
0x180005bbb  lea     rax, [r9+4]
0x180005bbf  mov     [r8+8], rax
0x180005bc3  mov     [r8+30h], rcx
0x180005bc7  retn
0x180005bc8  cmp     al, 20h ; ' '
0x180005bca  jnz     locret_180005C83
0x180005bd0  movsxd  rax, dword ptr [r9]
0x180005bd3  lea     rdx, [r9+4]
0x180005bd7  mov     [r8+8], rdx
0x180005bdb  mov     [r8+30h], rax
0x180005bdf  lea     rax, [rdx+4]
0x180005be3  movsxd  rcx, dword ptr [rdx]
0x180005be6  mov     [r8+8], rax
0x180005bea  jmp     loc_180005C7F
0x180005bef  cmp     al, 10h
0x180005bf1  jnz     short loc_180005C23
0x180005bf3  movzx   ecx, byte ptr [r9]
0x180005bf7  and     ecx, 0Fh
0x180005bfa  movsx   rax, byte ptr [rcx+r11+14640h]
0x180005c03  mov     cl, [rcx+r11+14650h]
0x180005c0b  sub     r9, rax
0x180005c0e  mov     eax, [r8+48h]
0x180005c12  mov     edx, [r9-4]
0x180005c16  shr     edx, cl
0x180005c18  add     eax, edx
0x180005c1a  mov     [r8+8], r9
0x180005c1e  mov     [r8+30h], rax
0x180005c22  retn
0x180005c23  cmp     al, 20h ; ' '
0x180005c25  jnz     short locret_180005C83
0x180005c27  movzx   ecx, byte ptr [r9]
0x180005c2b  mov     edx, [r8+48h]
0x180005c2f  and     ecx, 0Fh
0x180005c32  movsx   rax, byte ptr [rcx+r11+14640h]
0x180005c3b  mov     cl, [rcx+r11+14650h]
0x180005c43  sub     r9, rax
0x180005c46  mov     eax, [r9-4]
0x180005c4a  shr     eax, cl
0x180005c4c  mov     [r8+8], r9
0x180005c50  lea     ecx, [rdx+rax]
0x180005c53  mov     [r8+30h], rcx
0x180005c57  movzx   ecx, byte ptr [r9]
0x180005c5b  and     ecx, 0Fh
0x180005c5e  movsx   rax, byte ptr [rcx+r11+14640h]
0x180005c67  mov     cl, [rcx+r11+14650h]
0x180005c6f  sub     r9, rax
0x180005c72  mov     eax, [r9-4]
0x180005c76  shr     eax, cl
0x180005c78  mov     [r8+8], r9
0x180005c7c  lea     ecx, [rdx+rax]
0x180005c7f  mov     [r8+38h], rcx
0x180005c83  retn
```
