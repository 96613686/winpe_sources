# SymCryptWipeAsm

- ea: `0x180009780`
- end: `0x180009831`
- name: `SymCryptWipeAsm`
- size: `177`
- prototype: ``
- caller_count: `65`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028c0`
- `0x180005610`
- `0x180006dd0`
- `0x180007150`
- `0x1800071f0`
- `0x180007338`
- `0x180013ac0`
- `0x180013b40`
- `0x180013ea4`
- `0x180021e4c`
- `0x1800229e0`
- `0x180022b78`
- `0x180022c8c`
- `0x180023030`
- `0x180023390`
- `0x180023cc8`
- `0x180023d70`
- `0x180023e5c`
- `0x180023e94`
- `0x180024a7c`
- `0x180024be8`
- `0x180025380`
- `0x180025578`
- `0x180025888`
- `0x180026108`
- `0x18002697c`
- `0x180026bf8`
- `0x1800270d4`
- `0x180027518`
- `0x180027604`
- `0x180027c78`
- `0x180027f10`
- `0x180028034`
- `0x1800282c0`
- `0x180028464`
- `0x18002859c`
- `0x180028790`
- `0x18002aee8`
- `0x18002af7c`
- `0x18002afc4`
- `0x18002b440`
- `0x18002b4e0`
- `0x18002b780`
- `0x18002b8e0`
- `0x18002bcd0`
- `0x18002be40`
- `0x18002bf50`
- `0x18002c15c`
- `0x18002c35c`
- `0x18002c424`

## callees

- `0x180009780`

## pseudocode

```c
__int64 __fastcall SymCryptWipeAsm(__int64 a1, unsigned __int64 a2)
{
  bool v2; // cf
  unsigned __int64 i; // rdx
  unsigned int v4; // edx
  __int64 result; // rax

  if ( a2 < 0x10 )
  {
    result = 0;
    if ( (unsigned int)a2 < 8 )
    {
      if ( (unsigned int)a2 < 4 )
      {
        if ( (unsigned int)a2 < 2 )
        {
          if ( (_DWORD)a2 )
            *(_BYTE *)a1 = 0;
        }
        else
        {
          *(_WORD *)a1 = 0;
          *(_WORD *)(a1 + a2 - 2) = 0;
        }
      }
      else
      {
        *(_DWORD *)a1 = 0;
        *(_DWORD *)(a1 + a2 - 4) = 0;
      }
    }
    else
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + a2 - 8) = 0;
    }
  }
  else if ( (a1 & 0xF) != 0
         && (*(_QWORD *)a1 = 0, *(_QWORD *)(a1 + 8) = 0, result = -(int)a1 & 0xF, a1 += result, a2 -= result, a2 < 0x10) )
  {
    result = 0;
    *(_QWORD *)(a1 + a2 - 16) = 0;
    *(_QWORD *)(a1 + a2 - 8) = 0;
  }
  else
  {
    *(_OWORD *)a1 = 0;
    if ( (a2 & 0x10) != 0 )
      a1 += 16;
    v2 = a2 < 0x20;
    for ( i = a2 - 32; !v2; i -= 32LL )
    {
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      a1 += 32;
      v2 = i < 0x20;
    }
    v4 = i & 0xF;
    if ( v4 )
    {
      result = 0;
      *(_QWORD *)(a1 + v4 - 16) = 0;
      *(_QWORD *)(a1 + v4 - 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009780  xorps   xmm0, xmm0
0x180009783  cmp     rdx, 10h
0x180009787  jb      loc_180009800
0x18000978d  test    rcx, 0Fh
0x180009794  jnz     short loc_1800097D4
0x180009796  test    rdx, 10h
0x18000979d  movaps  xmmword ptr [rcx], xmm0
0x1800097a0  lea     r8, [rcx+10h]
0x1800097a4  cmovnz  rcx, r8
0x1800097a8  sub     rdx, 20h ; ' '
0x1800097ac  jb      short loc_1800097C1
0x1800097ae  xchg    ax, ax
0x1800097b0  movaps  xmmword ptr [rcx], xmm0
0x1800097b3  movaps  xmmword ptr [rcx+10h], xmm0
0x1800097b7  add     rcx, 20h ; ' '
0x1800097bb  sub     rdx, 20h ; ' '
0x1800097bf  jnb     short loc_1800097B0
0x1800097c1  and     edx, 0Fh
0x1800097c4  jnz     short loc_1800097C7
0x1800097c6  retn
0x1800097c7  xor     eax, eax
0x1800097c9  mov     [rcx+rdx-10h], rax
0x1800097ce  mov     [rcx+rdx-8], rax
0x1800097d3  retn
0x1800097d4  xor     eax, eax
0x1800097d6  mov     [rcx], rax
0x1800097d9  mov     [rcx+8], rax
0x1800097dd  mov     eax, ecx
0x1800097df  neg     eax
0x1800097e1  and     eax, 0Fh
0x1800097e4  add     rcx, rax
0x1800097e7  sub     rdx, rax
0x1800097ea  cmp     rdx, 10h
0x1800097ee  jnb     short loc_180009796
0x1800097f0  xor     eax, eax
0x1800097f2  mov     [rcx+rdx-10h], rax
0x1800097f7  mov     [rcx+rdx-8], rax
0x1800097fc  retn
0x180009800  xor     eax, eax
0x180009802  cmp     edx, 8
0x180009805  jb      short loc_180009810
0x180009807  mov     [rcx], rax
0x18000980a  mov     [rcx+rdx-8], rax
0x18000980f  retn
0x180009810  cmp     edx, 4
0x180009813  jb      short loc_18000981C
0x180009815  mov     [rcx], eax
0x180009817  mov     [rcx+rdx-4], eax
0x18000981b  retn
0x18000981c  cmp     edx, 2
0x18000981f  jb      short loc_18000982A
0x180009821  mov     [rcx], ax
0x180009824  mov     [rcx+rdx-2], ax
0x180009829  retn
0x18000982a  or      edx, edx
0x18000982c  jz      short locret_180009830
0x18000982e  mov     [rcx], al
0x180009830  retn
```
