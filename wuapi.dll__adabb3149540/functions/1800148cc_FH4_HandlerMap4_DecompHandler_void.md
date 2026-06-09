# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1800148cc`
- end: `0x180014a54`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012fec`
- `0x180013794`
- `0x180014250`

## callees

- `0x1800148cc`

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
0x1800148cc  xor     eax, eax
0x1800148ce  lea     r11, cs:180000000h
0x1800148d5  mov     [rcx+18h], al
0x1800148d8  xorps   xmm0, xmm0
0x1800148db  mov     [rcx+1Ch], rax
0x1800148df  mov     r8, rcx
0x1800148e2  mov     [rcx+24h], rax
0x1800148e6  movups  xmmword ptr [rcx+30h], xmm0
0x1800148ea  mov     rax, [rcx+8]
0x1800148ee  mov     r10b, [rax]
0x1800148f1  lea     rdx, [rax+1]
0x1800148f5  mov     [rcx+18h], r10b
0x1800148f9  mov     [rcx+8], rdx
0x1800148fd  test    r10b, 1
0x180014901  jz      short loc_18001492A
0x180014903  movzx   ecx, byte ptr [rdx]
0x180014906  and     ecx, 0Fh
0x180014909  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014912  mov     cl, [rcx+r11+18828h]
0x18001491a  sub     rdx, rax
0x18001491d  mov     eax, [rdx-4]
0x180014920  shr     eax, cl
0x180014922  mov     [r8+1Ch], eax
0x180014926  mov     [r8+8], rdx
0x18001492a  test    r10b, 2
0x18001492e  jz      short loc_18001493E
0x180014930  mov     eax, [rdx]
0x180014932  add     rdx, 4
0x180014936  mov     [r8+8], rdx
0x18001493a  mov     [r8+20h], eax
0x18001493e  test    r10b, 4
0x180014942  jz      short loc_18001496B
0x180014944  movzx   ecx, byte ptr [rdx]
0x180014947  and     ecx, 0Fh
0x18001494a  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014953  mov     cl, [rcx+r11+18828h]
0x18001495b  sub     rdx, rax
0x18001495e  mov     eax, [rdx-4]
0x180014961  shr     eax, cl
0x180014963  mov     [r8+24h], eax
0x180014967  mov     [r8+8], rdx
0x18001496b  mov     eax, [rdx]
0x18001496d  lea     r9, [rdx+4]
0x180014971  mov     [r8+28h], eax
0x180014975  mov     al, r10b
0x180014978  and     al, 30h
0x18001497a  mov     [r8+8], r9
0x18001497e  test    r10b, 8
0x180014982  jz      short loc_1800149BF
0x180014984  cmp     al, 10h
0x180014986  jnz     short loc_180014998
0x180014988  movsxd  rcx, dword ptr [r9]
0x18001498b  lea     rax, [r9+4]
0x18001498f  mov     [r8+8], rax
0x180014993  mov     [r8+30h], rcx
0x180014997  retn
0x180014998  cmp     al, 20h ; ' '
0x18001499a  jnz     locret_180014A53
0x1800149a0  movsxd  rax, dword ptr [r9]
0x1800149a3  lea     rdx, [r9+4]
0x1800149a7  mov     [r8+8], rdx
0x1800149ab  mov     [r8+30h], rax
0x1800149af  lea     rax, [rdx+4]
0x1800149b3  movsxd  rcx, dword ptr [rdx]
0x1800149b6  mov     [r8+8], rax
0x1800149ba  jmp     loc_180014A4F
0x1800149bf  cmp     al, 10h
0x1800149c1  jnz     short loc_1800149F3
0x1800149c3  movzx   ecx, byte ptr [r9]
0x1800149c7  and     ecx, 0Fh
0x1800149ca  movsx   rax, byte ptr [rcx+r11+18818h]
0x1800149d3  mov     cl, [rcx+r11+18828h]
0x1800149db  sub     r9, rax
0x1800149de  mov     eax, [r8+48h]
0x1800149e2  mov     edx, [r9-4]
0x1800149e6  shr     edx, cl
0x1800149e8  add     eax, edx
0x1800149ea  mov     [r8+8], r9
0x1800149ee  mov     [r8+30h], rax
0x1800149f2  retn
0x1800149f3  cmp     al, 20h ; ' '
0x1800149f5  jnz     short locret_180014A53
0x1800149f7  movzx   ecx, byte ptr [r9]
0x1800149fb  mov     edx, [r8+48h]
0x1800149ff  and     ecx, 0Fh
0x180014a02  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014a0b  mov     cl, [rcx+r11+18828h]
0x180014a13  sub     r9, rax
0x180014a16  mov     eax, [r9-4]
0x180014a1a  shr     eax, cl
0x180014a1c  mov     [r8+8], r9
0x180014a20  lea     ecx, [rdx+rax]
0x180014a23  mov     [r8+30h], rcx
0x180014a27  movzx   ecx, byte ptr [r9]
0x180014a2b  and     ecx, 0Fh
0x180014a2e  movsx   rax, byte ptr [rcx+r11+18818h]
0x180014a37  mov     cl, [rcx+r11+18828h]
0x180014a3f  sub     r9, rax
0x180014a42  mov     eax, [r9-4]
0x180014a46  shr     eax, cl
0x180014a48  mov     [r8+8], r9
0x180014a4c  lea     ecx, [rdx+rax]
0x180014a4f  mov     [r8+38h], rcx
0x180014a53  retn
```
