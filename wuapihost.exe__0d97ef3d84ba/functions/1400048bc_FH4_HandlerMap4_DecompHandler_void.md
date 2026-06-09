# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1400048bc`
- end: `0x140004a44`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003624`
- `0x140003b64`
- `0x1400043e0`

## callees

- `0x1400048bc`

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
0x1400048bc  xor     eax, eax
0x1400048be  lea     r11, cs:140000000h
0x1400048c5  mov     [rcx+18h], al
0x1400048c8  xorps   xmm0, xmm0
0x1400048cb  mov     [rcx+1Ch], rax
0x1400048cf  mov     r8, rcx
0x1400048d2  mov     [rcx+24h], rax
0x1400048d6  movups  xmmword ptr [rcx+30h], xmm0
0x1400048da  mov     rax, [rcx+8]
0x1400048de  mov     r10b, [rax]
0x1400048e1  lea     rdx, [rax+1]
0x1400048e5  mov     [rcx+18h], r10b
0x1400048e9  mov     [rcx+8], rdx
0x1400048ed  test    r10b, 1
0x1400048f1  jz      short loc_14000491A
0x1400048f3  movzx   ecx, byte ptr [rdx]
0x1400048f6  and     ecx, 0Fh
0x1400048f9  movsx   rax, byte ptr [rcx+r11+7460h]
0x140004902  mov     cl, [rcx+r11+7470h]
0x14000490a  sub     rdx, rax
0x14000490d  mov     eax, [rdx-4]
0x140004910  shr     eax, cl
0x140004912  mov     [r8+1Ch], eax
0x140004916  mov     [r8+8], rdx
0x14000491a  test    r10b, 2
0x14000491e  jz      short loc_14000492E
0x140004920  mov     eax, [rdx]
0x140004922  add     rdx, 4
0x140004926  mov     [r8+8], rdx
0x14000492a  mov     [r8+20h], eax
0x14000492e  test    r10b, 4
0x140004932  jz      short loc_14000495B
0x140004934  movzx   ecx, byte ptr [rdx]
0x140004937  and     ecx, 0Fh
0x14000493a  movsx   rax, byte ptr [rcx+r11+7460h]
0x140004943  mov     cl, [rcx+r11+7470h]
0x14000494b  sub     rdx, rax
0x14000494e  mov     eax, [rdx-4]
0x140004951  shr     eax, cl
0x140004953  mov     [r8+24h], eax
0x140004957  mov     [r8+8], rdx
0x14000495b  mov     eax, [rdx]
0x14000495d  lea     r9, [rdx+4]
0x140004961  mov     [r8+28h], eax
0x140004965  mov     al, r10b
0x140004968  and     al, 30h
0x14000496a  mov     [r8+8], r9
0x14000496e  test    r10b, 8
0x140004972  jz      short loc_1400049AF
0x140004974  cmp     al, 10h
0x140004976  jnz     short loc_140004988
0x140004978  movsxd  rcx, dword ptr [r9]
0x14000497b  lea     rax, [r9+4]
0x14000497f  mov     [r8+8], rax
0x140004983  mov     [r8+30h], rcx
0x140004987  retn
0x140004988  cmp     al, 20h ; ' '
0x14000498a  jnz     locret_140004A43
0x140004990  movsxd  rax, dword ptr [r9]
0x140004993  lea     rdx, [r9+4]
0x140004997  mov     [r8+8], rdx
0x14000499b  mov     [r8+30h], rax
0x14000499f  lea     rax, [rdx+4]
0x1400049a3  movsxd  rcx, dword ptr [rdx]
0x1400049a6  mov     [r8+8], rax
0x1400049aa  jmp     loc_140004A3F
0x1400049af  cmp     al, 10h
0x1400049b1  jnz     short loc_1400049E3
0x1400049b3  movzx   ecx, byte ptr [r9]
0x1400049b7  and     ecx, 0Fh
0x1400049ba  movsx   rax, byte ptr [rcx+r11+7460h]
0x1400049c3  mov     cl, [rcx+r11+7470h]
0x1400049cb  sub     r9, rax
0x1400049ce  mov     eax, [r8+48h]
0x1400049d2  mov     edx, [r9-4]
0x1400049d6  shr     edx, cl
0x1400049d8  add     eax, edx
0x1400049da  mov     [r8+8], r9
0x1400049de  mov     [r8+30h], rax
0x1400049e2  retn
0x1400049e3  cmp     al, 20h ; ' '
0x1400049e5  jnz     short locret_140004A43
0x1400049e7  movzx   ecx, byte ptr [r9]
0x1400049eb  mov     edx, [r8+48h]
0x1400049ef  and     ecx, 0Fh
0x1400049f2  movsx   rax, byte ptr [rcx+r11+7460h]
0x1400049fb  mov     cl, [rcx+r11+7470h]
0x140004a03  sub     r9, rax
0x140004a06  mov     eax, [r9-4]
0x140004a0a  shr     eax, cl
0x140004a0c  mov     [r8+8], r9
0x140004a10  lea     ecx, [rdx+rax]
0x140004a13  mov     [r8+30h], rcx
0x140004a17  movzx   ecx, byte ptr [r9]
0x140004a1b  and     ecx, 0Fh
0x140004a1e  movsx   rax, byte ptr [rcx+r11+7460h]
0x140004a27  mov     cl, [rcx+r11+7470h]
0x140004a2f  sub     r9, rax
0x140004a32  mov     eax, [r9-4]
0x140004a36  shr     eax, cl
0x140004a38  mov     [r8+8], r9
0x140004a3c  lea     ecx, [rdx+rax]
0x140004a3f  mov     [r8+38h], rcx
0x140004a43  retn
```
