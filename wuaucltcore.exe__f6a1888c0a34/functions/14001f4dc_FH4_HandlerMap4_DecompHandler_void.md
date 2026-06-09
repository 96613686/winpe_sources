# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x14001f4dc`
- end: `0x14001f664`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001dbfc`
- `0x14001e3a4`
- `0x14001ee60`

## callees

- `0x14001f4dc`

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
0x14001f4dc  xor     eax, eax
0x14001f4de  lea     r11, __ImageBase
0x14001f4e5  mov     [rcx+18h], al
0x14001f4e8  xorps   xmm0, xmm0
0x14001f4eb  mov     [rcx+1Ch], rax
0x14001f4ef  mov     r8, rcx
0x14001f4f2  mov     [rcx+24h], rax
0x14001f4f6  movups  xmmword ptr [rcx+30h], xmm0
0x14001f4fa  mov     rax, [rcx+8]
0x14001f4fe  mov     r10b, [rax]
0x14001f501  lea     rdx, [rax+1]
0x14001f505  mov     [rcx+18h], r10b
0x14001f509  mov     [rcx+8], rdx
0x14001f50d  test    r10b, 1
0x14001f511  jz      short loc_14001F53A
0x14001f513  movzx   ecx, byte ptr [rdx]
0x14001f516  and     ecx, 0Fh
0x14001f519  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001f522  mov     cl, [rcx+r11+23BA0h]
0x14001f52a  sub     rdx, rax
0x14001f52d  mov     eax, [rdx-4]
0x14001f530  shr     eax, cl
0x14001f532  mov     [r8+1Ch], eax
0x14001f536  mov     [r8+8], rdx
0x14001f53a  test    r10b, 2
0x14001f53e  jz      short loc_14001F54E
0x14001f540  mov     eax, [rdx]
0x14001f542  add     rdx, 4
0x14001f546  mov     [r8+8], rdx
0x14001f54a  mov     [r8+20h], eax
0x14001f54e  test    r10b, 4
0x14001f552  jz      short loc_14001F57B
0x14001f554  movzx   ecx, byte ptr [rdx]
0x14001f557  and     ecx, 0Fh
0x14001f55a  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001f563  mov     cl, [rcx+r11+23BA0h]
0x14001f56b  sub     rdx, rax
0x14001f56e  mov     eax, [rdx-4]
0x14001f571  shr     eax, cl
0x14001f573  mov     [r8+24h], eax
0x14001f577  mov     [r8+8], rdx
0x14001f57b  mov     eax, [rdx]
0x14001f57d  lea     r9, [rdx+4]
0x14001f581  mov     [r8+28h], eax
0x14001f585  mov     al, r10b
0x14001f588  and     al, 30h
0x14001f58a  mov     [r8+8], r9
0x14001f58e  test    r10b, 8
0x14001f592  jz      short loc_14001F5CF
0x14001f594  cmp     al, 10h
0x14001f596  jnz     short loc_14001F5A8
0x14001f598  movsxd  rcx, dword ptr [r9]
0x14001f59b  lea     rax, [r9+4]
0x14001f59f  mov     [r8+8], rax
0x14001f5a3  mov     [r8+30h], rcx
0x14001f5a7  retn
0x14001f5a8  cmp     al, 20h ; ' '
0x14001f5aa  jnz     locret_14001F663
0x14001f5b0  movsxd  rax, dword ptr [r9]
0x14001f5b3  lea     rdx, [r9+4]
0x14001f5b7  mov     [r8+8], rdx
0x14001f5bb  mov     [r8+30h], rax
0x14001f5bf  lea     rax, [rdx+4]
0x14001f5c3  movsxd  rcx, dword ptr [rdx]
0x14001f5c6  mov     [r8+8], rax
0x14001f5ca  jmp     loc_14001F65F
0x14001f5cf  cmp     al, 10h
0x14001f5d1  jnz     short loc_14001F603
0x14001f5d3  movzx   ecx, byte ptr [r9]
0x14001f5d7  and     ecx, 0Fh
0x14001f5da  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001f5e3  mov     cl, [rcx+r11+23BA0h]
0x14001f5eb  sub     r9, rax
0x14001f5ee  mov     eax, [r8+48h]
0x14001f5f2  mov     edx, [r9-4]
0x14001f5f6  shr     edx, cl
0x14001f5f8  add     eax, edx
0x14001f5fa  mov     [r8+8], r9
0x14001f5fe  mov     [r8+30h], rax
0x14001f602  retn
0x14001f603  cmp     al, 20h ; ' '
0x14001f605  jnz     short locret_14001F663
0x14001f607  movzx   ecx, byte ptr [r9]
0x14001f60b  mov     edx, [r8+48h]
0x14001f60f  and     ecx, 0Fh
0x14001f612  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001f61b  mov     cl, [rcx+r11+23BA0h]
0x14001f623  sub     r9, rax
0x14001f626  mov     eax, [r9-4]
0x14001f62a  shr     eax, cl
0x14001f62c  mov     [r8+8], r9
0x14001f630  lea     ecx, [rdx+rax]
0x14001f633  mov     [r8+30h], rcx
0x14001f637  movzx   ecx, byte ptr [r9]
0x14001f63b  and     ecx, 0Fh
0x14001f63e  movsx   rax, byte ptr [rcx+r11+23B90h]
0x14001f647  mov     cl, [rcx+r11+23BA0h]
0x14001f64f  sub     r9, rax
0x14001f652  mov     eax, [r9-4]
0x14001f656  shr     eax, cl
0x14001f658  mov     [r8+8], r9
0x14001f65c  lea     ecx, [rdx+rax]
0x14001f65f  mov     [r8+38h], rcx
0x14001f663  retn
```
