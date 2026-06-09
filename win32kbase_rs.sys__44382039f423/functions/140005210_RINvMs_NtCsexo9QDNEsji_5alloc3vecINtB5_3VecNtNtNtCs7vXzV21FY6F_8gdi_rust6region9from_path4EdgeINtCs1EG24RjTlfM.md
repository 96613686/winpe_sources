# _RINvMs_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE10retain_mutNCINvB2_6retainNCNvMs_BH_NtBH_15ActiveEdgeTable7advance0E0EBL_

- ea: `0x140005210`
- end: `0x140005332`
- name: `_RINvMs_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE10retain_mutNCINvB2_6retainNCNvMs_BH_NtBH_15ActiveEdgeTable7advance0E0EBL_`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400101f0`

## callees

- `0x140005210`

## pseudocode

```c
unsigned __int64 __fastcall RINvMs_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE10retain_mutNCINvB2_6retainNCNvMs_BH_NtBH_15ActiveEdgeTable7advance0E0EBL_(
        __int64 a1)
{
  unsigned __int64 result; // rax
  __int64 v2; // rdx
  __int64 v3; // r9
  __int64 i; // r10
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r11
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  int *v10; // r10
  __int64 v11; // r9
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // r9
  __int128 v15; // xmm0
  __int128 v16; // xmm1

  result = *(_QWORD *)(a1 + 16);
  if ( result )
  {
    v2 = *(_QWORD *)(a1 + 8);
    v3 = 0;
    for ( i = v2; *(int *)(i + 24) > 0; i += 48 )
    {
      if ( ++v3 == result )
        return result;
    }
    v5 = v3 + 1;
    if ( v3 + 1 >= result )
    {
      *(_QWORD *)(a1 + 16) = v3;
    }
    else
    {
      v6 = v3 - result;
      v7 = v3 - result + 2;
      if ( (((_BYTE)v3 - (_BYTE)result) & 1) == 0 )
      {
        v6 = v3;
        if ( *(int *)(i + 72) > 0 )
        {
          v8 = *(_OWORD *)(i + 48);
          v9 = *(_OWORD *)(i + 64);
          *(_OWORD *)(i + 32) = *(_OWORD *)(i + 80);
          *(_OWORD *)(i + 16) = v9;
          *(_OWORD *)i = v8;
          v6 = v3 + 1;
        }
        v5 = v3 + 2;
        v3 = v6;
      }
      if ( v7 )
      {
        v10 = (int *)(v2 + 48 * v5);
        result -= v5;
        v6 = v3;
        do
        {
          if ( v10[6] > 0 )
          {
            v11 = 48 * v6;
            v12 = *(_OWORD *)v10;
            v13 = *((_OWORD *)v10 + 1);
            *(_OWORD *)(v2 + v11 + 32) = *((_OWORD *)v10 + 2);
            *(_OWORD *)(v2 + v11 + 16) = v13;
            *(_OWORD *)(v2 + v11) = v12;
            ++v6;
          }
          if ( v10[18] > 0 )
          {
            v14 = 48 * v6;
            v15 = *((_OWORD *)v10 + 3);
            v16 = *((_OWORD *)v10 + 4);
            *(_OWORD *)(v2 + v14 + 32) = *((_OWORD *)v10 + 5);
            *(_OWORD *)(v2 + v14 + 16) = v16;
            *(_OWORD *)(v2 + v14) = v15;
            ++v6;
          }
          v10 += 24;
          result -= 2LL;
        }
        while ( result );
      }
      *(_QWORD *)(a1 + 16) = v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005210  push    rsi
0x140005211  mov     rax, [rcx+10h]
0x140005215  test    rax, rax
0x140005218  jz      short loc_140005246
0x14000521a  mov     rdx, [rcx+8]
0x14000521e  mov     r8, rax
0x140005221  neg     r8
0x140005224  xor     r9d, r9d
0x140005227  mov     r10, rdx
0x14000522a  nop     word ptr [rax+rax+00h]
0x140005230  cmp     dword ptr [r10+18h], 0
0x140005235  jle     short loc_140005248
0x140005237  inc     r9
0x14000523a  add     r10, 30h ; '0'
0x14000523e  mov     r11, r8
0x140005241  add     r11, r9
0x140005244  jnz     short loc_140005230
0x140005246  pop     rsi
0x140005247  retn
0x140005248  lea     rsi, [r9+1]
0x14000524c  cmp     rsi, rax
0x14000524f  jnb     short loc_14000529B
0x140005251  mov     r8, r9
0x140005254  sub     r8, rax
0x140005257  lea     r11, [r8+2]
0x14000525b  test    r8b, 1
0x14000525f  jnz     short loc_1400052A1
0x140005261  cmp     dword ptr [r10+48h], 0
0x140005266  mov     r8, r9
0x140005269  jle     short loc_14000528F
0x14000526b  lea     r8, [r10+30h]
0x14000526f  movups  xmm0, xmmword ptr [r8]
0x140005273  movups  xmm1, xmmword ptr [r8+10h]
0x140005278  movups  xmm2, xmmword ptr [r8+20h]
0x14000527d  movups  xmmword ptr [r10+20h], xmm2
0x140005282  movups  xmmword ptr [r10+10h], xmm1
0x140005287  movups  xmmword ptr [r10], xmm0
0x14000528b  lea     r8, [r9+1]
0x14000528f  add     r9, 2
0x140005293  mov     rsi, r9
0x140005296  mov     r9, r8
0x140005299  jmp     short loc_1400052A1
0x14000529b  mov     [rcx+10h], r9
0x14000529f  pop     rsi
0x1400052a0  retn
0x1400052a1  test    r11, r11
0x1400052a4  jz      loc_14000532C
0x1400052aa  lea     r10, [rsi+rsi*2]
0x1400052ae  shl     r10, 4
0x1400052b2  add     r10, rdx
0x1400052b5  sub     rax, rsi
0x1400052b8  mov     r8, r9
0x1400052bb  jmp     short loc_1400052C7
0x1400052bd  add     r10, 60h ; '`'
0x1400052c1  add     rax, 0FFFFFFFFFFFFFFFEh
0x1400052c5  jz      short loc_14000532C
0x1400052c7  cmp     dword ptr [r10+18h], 0
0x1400052cc  jle     short loc_1400052F8
0x1400052ce  lea     r9, [r8+r8*2]
0x1400052d2  shl     r9, 4
0x1400052d6  movups  xmm0, xmmword ptr [r10]
0x1400052da  movups  xmm1, xmmword ptr [r10+10h]
0x1400052df  movups  xmm2, xmmword ptr [r10+20h]
0x1400052e4  movups  xmmword ptr [rdx+r9+20h], xmm2
0x1400052ea  movups  xmmword ptr [rdx+r9+10h], xmm1
0x1400052f0  movups  xmmword ptr [rdx+r9], xmm0
0x1400052f5  inc     r8
0x1400052f8  cmp     dword ptr [r10+48h], 0
0x1400052fd  jle     short loc_1400052BD
0x1400052ff  lea     r9, [r8+r8*2]
0x140005303  shl     r9, 4
0x140005307  movups  xmm0, xmmword ptr [r10+30h]
0x14000530c  movups  xmm1, xmmword ptr [r10+40h]
0x140005311  movups  xmm2, xmmword ptr [r10+50h]
0x140005316  movups  xmmword ptr [rdx+r9+20h], xmm2
0x14000531c  movups  xmmword ptr [rdx+r9+10h], xmm1
0x140005322  movups  xmmword ptr [rdx+r9], xmm0
0x140005327  inc     r8
0x14000532a  jmp     short loc_1400052BD
0x14000532c  mov     [rcx+10h], r8
0x140005330  pop     rsi
0x140005331  retn
```
