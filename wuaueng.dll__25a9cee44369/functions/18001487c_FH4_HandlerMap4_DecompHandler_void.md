# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18001487c`
- end: `0x180014a04`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f9c`
- `0x180013744`
- `0x180014200`

## callees

- `0x18001487c`

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
0x18001487c  xor     eax, eax
0x18001487e  lea     r11, cs:180000000h
0x180014885  mov     [rcx+18h], al
0x180014888  xorps   xmm0, xmm0
0x18001488b  mov     [rcx+1Ch], rax
0x18001488f  mov     r8, rcx
0x180014892  mov     [rcx+24h], rax
0x180014896  movups  xmmword ptr [rcx+30h], xmm0
0x18001489a  mov     rax, [rcx+8]
0x18001489e  mov     r10b, [rax]
0x1800148a1  lea     rdx, [rax+1]
0x1800148a5  mov     [rcx+18h], r10b
0x1800148a9  mov     [rcx+8], rdx
0x1800148ad  test    r10b, 1
0x1800148b1  jz      short loc_1800148DA
0x1800148b3  movzx   ecx, byte ptr [rdx]
0x1800148b6  and     ecx, 0Fh
0x1800148b9  movsx   rax, byte ptr [rcx+r11+18818h]
0x1800148c2  mov     cl, [rcx+r11+18828h]
0x1800148ca  sub     rdx, rax
0x1800148cd  mov     eax, [rdx-4]
0x1800148d0  shr     eax, cl
0x1800148d2  mov     [r8+1Ch], eax
0x1800148d6  mov     [r8+8], rdx
0x1800148da  test    r10b, 2
0x1800148de  jz      short loc_1800148EE
0x1800148e0  mov     eax, [rdx]
0x1800148e2  add     rdx, 4
0x1800148e6  mov     [r8+8], rdx
0x1800148ea  mov     [r8+20h], eax
0x1800148ee  test    r10b, 4
0x1800148f2  jz      short loc_18001491B
0x1800148f4  movzx   ecx, byte ptr [rdx]
0x1800148f7  and     ecx, 0Fh
0x1800148fa  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014903  mov     cl, [rcx+r11+18828h]
0x18001490b  sub     rdx, rax
0x18001490e  mov     eax, [rdx-4]
0x180014911  shr     eax, cl
0x180014913  mov     [r8+24h], eax
0x180014917  mov     [r8+8], rdx
0x18001491b  mov     eax, [rdx]
0x18001491d  lea     r9, [rdx+4]
0x180014921  mov     [r8+28h], eax
0x180014925  mov     al, r10b
0x180014928  and     al, 30h
0x18001492a  mov     [r8+8], r9
0x18001492e  test    r10b, 8
0x180014932  jz      short loc_18001496F
0x180014934  cmp     al, 10h
0x180014936  jnz     short loc_180014948
0x180014938  movsxd  rcx, dword ptr [r9]
0x18001493b  lea     rax, [r9+4]
0x18001493f  mov     [r8+8], rax
0x180014943  mov     [r8+30h], rcx
0x180014947  retn
0x180014948  cmp     al, 20h ; ' '
0x18001494a  jnz     locret_180014A03
0x180014950  movsxd  rax, dword ptr [r9]
0x180014953  lea     rdx, [r9+4]
0x180014957  mov     [r8+8], rdx
0x18001495b  mov     [r8+30h], rax
0x18001495f  lea     rax, [rdx+4]
0x180014963  movsxd  rcx, dword ptr [rdx]
0x180014966  mov     [r8+8], rax
0x18001496a  jmp     loc_1800149FF
0x18001496f  cmp     al, 10h
0x180014971  jnz     short loc_1800149A3
0x180014973  movzx   ecx, byte ptr [r9]
0x180014977  and     ecx, 0Fh
0x18001497a  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014983  mov     cl, [rcx+r11+18828h]
0x18001498b  sub     r9, rax
0x18001498e  mov     eax, [r8+48h]
0x180014992  mov     edx, [r9-4]
0x180014996  shr     edx, cl
0x180014998  add     eax, edx
0x18001499a  mov     [r8+8], r9
0x18001499e  mov     [r8+30h], rax
0x1800149a2  retn
0x1800149a3  cmp     al, 20h ; ' '
0x1800149a5  jnz     short locret_180014A03
0x1800149a7  movzx   ecx, byte ptr [r9]
0x1800149ab  mov     edx, [r8+48h]
0x1800149af  and     ecx, 0Fh
0x1800149b2  movsx   rax, byte ptr [rcx+r11+18818h]
0x1800149bb  mov     cl, [rcx+r11+18828h]
0x1800149c3  sub     r9, rax
0x1800149c6  mov     eax, [r9-4]
0x1800149ca  shr     eax, cl
0x1800149cc  mov     [r8+8], r9
0x1800149d0  lea     ecx, [rdx+rax]
0x1800149d3  mov     [r8+30h], rcx
0x1800149d7  movzx   ecx, byte ptr [r9]
0x1800149db  and     ecx, 0Fh
0x1800149de  movsx   rax, byte ptr [rcx+r11+18818h]
0x1800149e7  mov     cl, [rcx+r11+18828h]
0x1800149ef  sub     r9, rax
0x1800149f2  mov     eax, [r9-4]
0x1800149f6  shr     eax, cl
0x1800149f8  mov     [r8+8], r9
0x1800149fc  lea     ecx, [rdx+rax]
0x1800149ff  mov     [r8+38h], rcx
0x180014a03  retn
```
