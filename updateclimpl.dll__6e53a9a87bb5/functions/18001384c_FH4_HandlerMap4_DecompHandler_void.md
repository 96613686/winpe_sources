# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18001384c`
- end: `0x1800139d4`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012608`
- `0x180012b48`
- `0x1800133c4`

## callees

- `0x18001384c`

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
0x18001384c  xor     eax, eax
0x18001384e  lea     r11, cs:180000000h
0x180013855  mov     [rcx+18h], al
0x180013858  xorps   xmm0, xmm0
0x18001385b  mov     [rcx+1Ch], rax
0x18001385f  mov     r8, rcx
0x180013862  mov     [rcx+24h], rax
0x180013866  movups  xmmword ptr [rcx+30h], xmm0
0x18001386a  mov     rax, [rcx+8]
0x18001386e  mov     r10b, [rax]
0x180013871  lea     rdx, [rax+1]
0x180013875  mov     [rcx+18h], r10b
0x180013879  mov     [rcx+8], rdx
0x18001387d  test    r10b, 1
0x180013881  jz      short loc_1800138AA
0x180013883  movzx   ecx, byte ptr [rdx]
0x180013886  and     ecx, 0Fh
0x180013889  movsx   rax, byte ptr [rcx+r11+179D8h]
0x180013892  mov     cl, [rcx+r11+179E8h]
0x18001389a  sub     rdx, rax
0x18001389d  mov     eax, [rdx-4]
0x1800138a0  shr     eax, cl
0x1800138a2  mov     [r8+1Ch], eax
0x1800138a6  mov     [r8+8], rdx
0x1800138aa  test    r10b, 2
0x1800138ae  jz      short loc_1800138BE
0x1800138b0  mov     eax, [rdx]
0x1800138b2  add     rdx, 4
0x1800138b6  mov     [r8+8], rdx
0x1800138ba  mov     [r8+20h], eax
0x1800138be  test    r10b, 4
0x1800138c2  jz      short loc_1800138EB
0x1800138c4  movzx   ecx, byte ptr [rdx]
0x1800138c7  and     ecx, 0Fh
0x1800138ca  movsx   rax, byte ptr [rcx+r11+179D8h]
0x1800138d3  mov     cl, [rcx+r11+179E8h]
0x1800138db  sub     rdx, rax
0x1800138de  mov     eax, [rdx-4]
0x1800138e1  shr     eax, cl
0x1800138e3  mov     [r8+24h], eax
0x1800138e7  mov     [r8+8], rdx
0x1800138eb  mov     eax, [rdx]
0x1800138ed  lea     r9, [rdx+4]
0x1800138f1  mov     [r8+28h], eax
0x1800138f5  mov     al, r10b
0x1800138f8  and     al, 30h
0x1800138fa  mov     [r8+8], r9
0x1800138fe  test    r10b, 8
0x180013902  jz      short loc_18001393F
0x180013904  cmp     al, 10h
0x180013906  jnz     short loc_180013918
0x180013908  movsxd  rcx, dword ptr [r9]
0x18001390b  lea     rax, [r9+4]
0x18001390f  mov     [r8+8], rax
0x180013913  mov     [r8+30h], rcx
0x180013917  retn
0x180013918  cmp     al, 20h ; ' '
0x18001391a  jnz     locret_1800139D3
0x180013920  movsxd  rax, dword ptr [r9]
0x180013923  lea     rdx, [r9+4]
0x180013927  mov     [r8+8], rdx
0x18001392b  mov     [r8+30h], rax
0x18001392f  lea     rax, [rdx+4]
0x180013933  movsxd  rcx, dword ptr [rdx]
0x180013936  mov     [r8+8], rax
0x18001393a  jmp     loc_1800139CF
0x18001393f  cmp     al, 10h
0x180013941  jnz     short loc_180013973
0x180013943  movzx   ecx, byte ptr [r9]
0x180013947  and     ecx, 0Fh
0x18001394a  movsx   rax, byte ptr [rcx+r11+179D8h]
0x180013953  mov     cl, [rcx+r11+179E8h]
0x18001395b  sub     r9, rax
0x18001395e  mov     eax, [r8+48h]
0x180013962  mov     edx, [r9-4]
0x180013966  shr     edx, cl
0x180013968  add     eax, edx
0x18001396a  mov     [r8+8], r9
0x18001396e  mov     [r8+30h], rax
0x180013972  retn
0x180013973  cmp     al, 20h ; ' '
0x180013975  jnz     short locret_1800139D3
0x180013977  movzx   ecx, byte ptr [r9]
0x18001397b  mov     edx, [r8+48h]
0x18001397f  and     ecx, 0Fh
0x180013982  movsx   rax, byte ptr [rcx+r11+179D8h]
0x18001398b  mov     cl, [rcx+r11+179E8h]
0x180013993  sub     r9, rax
0x180013996  mov     eax, [r9-4]
0x18001399a  shr     eax, cl
0x18001399c  mov     [r8+8], r9
0x1800139a0  lea     ecx, [rdx+rax]
0x1800139a3  mov     [r8+30h], rcx
0x1800139a7  movzx   ecx, byte ptr [r9]
0x1800139ab  and     ecx, 0Fh
0x1800139ae  movsx   rax, byte ptr [rcx+r11+179D8h]
0x1800139b7  mov     cl, [rcx+r11+179E8h]
0x1800139bf  sub     r9, rax
0x1800139c2  mov     eax, [r9-4]
0x1800139c6  shr     eax, cl
0x1800139c8  mov     [r8+8], r9
0x1800139cc  lea     ecx, [rdx+rax]
0x1800139cf  mov     [r8+38h], rcx
0x1800139d3  retn
```
