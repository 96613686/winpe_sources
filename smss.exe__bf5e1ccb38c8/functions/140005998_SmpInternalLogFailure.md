# SmpInternalLogFailure

- ea: `0x140005998`
- end: `0x140005abe`
- name: `SmpInternalLogFailure`
- size: `294`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010ec`
- `0x140001f60`
- `0x1400027a0`
- `0x140003114`
- `0x140003450`
- `0x1400036d0`
- `0x1400041d0`
- `0x140007420`
- `0x14000d4c0`

## callees

- `0x140005998`

## pseudocode

```c
char *__fastcall SmpInternalLogFailure(_BYTE *a1, int a2, int a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v5; // r8
  _BYTE *v6; // rdx
  _BYTE *v7; // rax
  __int64 v8; // rcx
  char *result; // rax

  *(_DWORD *)(a4 + 192) = a3;
  *(_DWORD *)(a4 + 216) = a2;
  if ( a1 )
  {
    v4 = 2147483646;
    v5 = 64;
    v6 = (_BYTE *)a4;
    do
    {
      if ( !v4 )
        break;
      if ( !*a1 )
        break;
      *v6++ = *a1++;
      --v4;
      --v5;
    }
    while ( v5 );
    v7 = v6 - 1;
    if ( v5 )
      v7 = v6;
    *v7 = 0;
  }
  v8 = 224LL * (_InterlockedIncrement(&dword_14002EE94) % 16);
  result = SmpBlackboxBuffer;
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 8] = *(_OWORD *)a4;
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 24] = *(_OWORD *)(a4 + 16);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 40] = *(_OWORD *)(a4 + 32);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 56] = *(_OWORD *)(a4 + 48);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 72] = *(_OWORD *)(a4 + 64);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 88] = *(_OWORD *)(a4 + 80);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 104] = *(_OWORD *)(a4 + 96);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 120] = *(_OWORD *)(a4 + 112);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 136] = *(_OWORD *)(a4 + 128);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 152] = *(_OWORD *)(a4 + 144);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 168] = *(_OWORD *)(a4 + 160);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 184] = *(_OWORD *)(a4 + 176);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 200] = *(_OWORD *)(a4 + 192);
  *(_OWORD *)&SmpBlackboxBuffer[v8 + 216] = *(_OWORD *)(a4 + 208);
  return result;
}

```

## disassembly

```asm
0x140005998  mov     [r9+0C0h], r8d
0x14000599f  mov     [r9+0D8h], edx
0x1400059a6  test    rcx, rcx
0x1400059a9  jz      short loc_1400059E6
0x1400059ab  mov     eax, 7FFFFFFEh
0x1400059b0  mov     r8d, 40h ; '@'
0x1400059b6  mov     rdx, r9
0x1400059b9  test    rax, rax
0x1400059bc  jz      short loc_1400059D8
0x1400059be  mov     r10b, [rcx]
0x1400059c1  test    r10b, r10b
0x1400059c4  jz      short loc_1400059D8
0x1400059c6  mov     [rdx], r10b
0x1400059c9  inc     rcx
0x1400059cc  inc     rdx
0x1400059cf  dec     rax
0x1400059d2  sub     r8, 1
0x1400059d6  jnz     short loc_1400059B9
0x1400059d8  test    r8, r8
0x1400059db  lea     rax, [rdx-1]
0x1400059df  cmovnz  rax, rdx
0x1400059e3  mov     byte ptr [rax], 0
0x1400059e6  mov     eax, 1
0x1400059eb  lock xadd cs:dword_14002EE94, eax
0x1400059f3  movups  xmm0, xmmword ptr [r9]
0x1400059f7  inc     eax
0x1400059f9  mov     ecx, 10h
0x1400059fe  cdq
0x1400059ff  idiv    ecx
0x140005a01  movsxd  rax, edx
0x140005a04  imul    rcx, rax, 0E0h
0x140005a0b  lea     rax, SmpBlackboxBuffer
0x140005a12  movups  xmmword ptr [rcx+rax+8], xmm0
0x140005a17  movups  xmm1, xmmword ptr [r9+10h]
0x140005a1c  movups  xmmword ptr [rcx+rax+18h], xmm1
0x140005a21  movups  xmm0, xmmword ptr [r9+20h]
0x140005a26  movups  xmmword ptr [rcx+rax+28h], xmm0
0x140005a2b  movups  xmm1, xmmword ptr [r9+30h]
0x140005a30  movups  xmmword ptr [rcx+rax+38h], xmm1
0x140005a35  movups  xmm0, xmmword ptr [r9+40h]
0x140005a3a  movups  xmmword ptr [rcx+rax+48h], xmm0
0x140005a3f  movups  xmm1, xmmword ptr [r9+50h]
0x140005a44  movups  xmmword ptr [rcx+rax+58h], xmm1
0x140005a49  movups  xmm0, xmmword ptr [r9+60h]
0x140005a4e  movups  xmmword ptr [rcx+rax+68h], xmm0
0x140005a53  movups  xmm1, xmmword ptr [r9+70h]
0x140005a58  movups  xmmword ptr [rcx+rax+78h], xmm1
0x140005a5d  movups  xmm0, xmmword ptr [r9+80h]
0x140005a65  movups  xmmword ptr [rcx+rax+88h], xmm0
0x140005a6d  movups  xmm1, xmmword ptr [r9+90h]
0x140005a75  movups  xmmword ptr [rcx+rax+98h], xmm1
0x140005a7d  movups  xmm0, xmmword ptr [r9+0A0h]
0x140005a85  movups  xmmword ptr [rcx+rax+0A8h], xmm0
0x140005a8d  movups  xmm1, xmmword ptr [r9+0B0h]
0x140005a95  movups  xmmword ptr [rcx+rax+0B8h], xmm1
0x140005a9d  movups  xmm0, xmmword ptr [r9+0C0h]
0x140005aa5  movups  xmmword ptr [rcx+rax+0C8h], xmm0
0x140005aad  movups  xmm1, xmmword ptr [r9+0D0h]
0x140005ab5  movups  xmmword ptr [rcx+rax+0D8h], xmm1
0x140005abd  retn
```
