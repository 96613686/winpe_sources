# BalanceUpdateFlowAverageStats

- ea: `0x1400021b0`
- end: `0x1400022f6`
- name: `BalanceUpdateFlowAverageStats`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001bd0`

## callees

- `0x1400021b0`

## pseudocode

```c
__int64 __fastcall BalanceUpdateFlowAverageStats(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // r10
  __int64 v4; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // r10
  unsigned __int64 v8; // rtt
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  bool v12; // cf
  unsigned int v13; // eax
  __int64 v14; // rdx

  v2 = qword_14000D318;
  v4 = *(_QWORD *)(a1 + 328);
  result = v4 + qword_14000D318;
  if ( a2 >= v4 + qword_14000D318 )
  {
    *(_QWORD *)(a1 + 328) = a2;
    v6 = a2 - v4;
    v7 = (a2 - v4) / v2;
    v8 = (*(_QWORD *)(a1 + 232) - *(_QWORD *)(a1 + 344)) << 10;
    *(_QWORD *)(a1 + 344) = *(_QWORD *)(a1 + 232);
    *(_DWORD *)(a1 + 376) = v8 / (a2 - v4);
    v9 = qword_14000D2C0 * (*(_QWORD *)(a1 + 216) - *(_QWORD *)(a1 + 336));
    *(_QWORD *)(a1 + 336) = *(_QWORD *)(a1 + 216);
    *(_QWORD *)(a1 + 360) = v9 / (a2 - v4);
    v10 = qword_14000D2C0 * (*(_QWORD *)(a1 + 224) - *(_QWORD *)(a1 + 352));
    *(_QWORD *)(a1 + 352) = *(_QWORD *)(a1 + 224);
    v11 = 0;
    v12 = *(_DWORD *)(a1 + 376) < 0x398u;
    *(_QWORD *)(a1 + 368) = v10 / v6;
    if ( !v12 )
      v11 = *(_QWORD *)(a1 + 360) < *(_QWORD *)(a1 + 448);
    if ( (unsigned int)v7 >= 0xF )
    {
      *(_DWORD *)(a1 + 392) = 0;
      *(_QWORD *)(a1 + 384) = 0;
    }
    else
    {
      v13 = 0;
      if ( (_DWORD)v7 )
      {
        v14 = *(_QWORD *)(a1 + 384);
        do
        {
          if ( (v14 & 0x4000) != 0 )
            --*(_DWORD *)(a1 + 392);
          v14 *= 2;
          ++v13;
        }
        while ( v13 < (unsigned int)v7 );
        *(_QWORD *)(a1 + 384) = v14;
      }
    }
    result = v11 | *(_DWORD *)(a1 + 384) & 0x7FFF;
    *(_DWORD *)(a1 + 392) += v11;
    *(_QWORD *)(a1 + 384) = result;
  }
  return result;
}

```

## disassembly

```asm
0x1400021b0  mov     r10, cs:qword_14000D318
0x1400021b7  mov     r8, rdx
0x1400021ba  mov     rdx, [rcx+148h]
0x1400021c1  lea     rax, [rdx+r10]
0x1400021c5  cmp     r8, rax
0x1400021c8  jb      locret_1400022BC
0x1400021ce  mov     r9, r8
0x1400021d1  mov     [rcx+148h], r8
0x1400021d8  mov     r8, [rcx+0E8h]
0x1400021df  sub     r9, rdx
0x1400021e2  xor     edx, edx
0x1400021e4  mov     rax, r9
0x1400021e7  div     r10
0x1400021ea  xor     edx, edx
0x1400021ec  mov     r10, rax
0x1400021ef  mov     rax, r8
0x1400021f2  sub     rax, [rcx+158h]
0x1400021f9  shl     rax, 0Ah
0x1400021fd  div     r9
0x140002200  xor     edx, edx
0x140002202  mov     [rcx+158h], r8
0x140002209  mov     [rcx+178h], eax
0x14000220f  mov     r8, [rcx+0D8h]
0x140002216  mov     rax, r8
0x140002219  sub     rax, [rcx+150h]
0x140002220  imul    rax, cs:qword_14000D2C0
0x140002228  mov     [rcx+150h], r8
0x14000222f  div     r9
0x140002232  xor     edx, edx
0x140002234  mov     [rcx+168h], rax
0x14000223b  mov     r8, [rcx+0E0h]
0x140002242  mov     rax, r8
0x140002245  sub     rax, [rcx+160h]
0x14000224c  imul    rax, cs:qword_14000D2C0
0x140002254  mov     [rcx+160h], r8
0x14000225b  xor     r8d, r8d
0x14000225e  div     r9
0x140002261  cmp     dword ptr [rcx+178h], 398h
0x14000226b  mov     [rcx+170h], rax
0x140002272  jnb     short loc_1400022BE
0x140002274  cmp     r10d, 0Fh
0x140002278  jnb     short loc_1400022D7
0x14000227a  xor     eax, eax
0x14000227c  test    r10d, r10d
0x14000227f  jz      short loc_1400022A0
0x140002281  mov     rdx, [rcx+180h]
0x140002288  bt      rdx, 0Eh
0x14000228d  jb      short loc_1400022EE
0x14000228f  add     rdx, rdx
0x140002292  inc     eax
0x140002294  cmp     eax, r10d
0x140002297  jb      short loc_140002288
0x140002299  mov     [rcx+180h], rdx
0x1400022a0  mov     eax, [rcx+180h]
0x1400022a6  and     eax, 7FFFh
0x1400022ab  or      rax, r8
0x1400022ae  add     [rcx+188h], r8d
0x1400022b5  mov     [rcx+180h], rax
0x1400022bc  retn
0x1400022be  mov     rax, [rcx+1C0h]
0x1400022c5  mov     edx, 1
0x1400022ca  cmp     [rcx+168h], rax
0x1400022d1  cmovb   r8, rdx
0x1400022d5  jmp     short loc_140002274
0x1400022d7  mov     dword ptr [rcx+188h], 0
0x1400022e1  mov     qword ptr [rcx+180h], 0
0x1400022ec  jmp     short loc_1400022A0
0x1400022ee  dec     dword ptr [rcx+188h]
0x1400022f4  jmp     short loc_14000228F
```
