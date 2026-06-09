# SearchInTable

- ea: `0x180002560`
- end: `0x18000269a`
- name: `SearchInTable`
- size: `314`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001de0`
- `0x180002150`
- `0x180002380`
- `0x180008868`
- `0x18000a370`
- `0x18000a450`
- `0x18000a670`
- `0x18000b2d8`
- `0x18000b440`

## callees

- `0x180002560`

## pseudocode

```c
__int64 __fastcall SearchInTable(__int64 *a1, unsigned __int16 a2, _BYTE *a3, __int64 a4, _QWORD *a5)
{
  __int64 *v5; // r11
  __int64 *v6; // rbp
  int v7; // edi
  __int64 *v8; // r10
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  _BYTE *v15; // rcx
  _BYTE *v16; // rdx
  bool v17; // cc
  unsigned __int16 v18; // dx
  _BYTE *v19; // r9
  _BYTE *v20; // r8
  int v21; // ecx
  int v22; // edx
  int v23; // r9d
  int v24; // eax
  __int64 v25; // rcx

  v5 = (__int64 *)*a1;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  if ( *a1 )
  {
    v12 = *((_DWORD *)a1 + 2);
    while ( v12 )
    {
      v14 = v12 - 1;
      v15 = a3;
      v16 = (char *)v5 + 46;
      if ( v12 != 1 )
      {
        do
        {
          if ( *v15 != *v16 )
            break;
          ++v15;
          ++v16;
          --v14;
        }
        while ( v14 );
      }
      v13 = (unsigned __int8)*v15 - (unsigned __int8)*v16;
      if ( v13 < 0 )
      {
LABEL_15:
        v7 = -1;
        goto LABEL_16;
      }
      v17 = v13 <= 0;
      if ( !v13 )
        goto LABEL_10;
LABEL_12:
      if ( v17 && a2 <= *((_WORD *)v5 + 22) )
      {
        v8 = v5;
        if ( !v5 )
          goto LABEL_28;
        goto LABEL_29;
      }
      v7 = 1;
      v8 = v5;
LABEL_16:
      v6 = v5;
      v5 = (__int64 *)v5[v7 + 3];
      if ( !v5 )
        goto LABEL_28;
    }
    v13 = 0;
LABEL_10:
    if ( a2 < *((_WORD *)v5 + 22) )
      goto LABEL_15;
    v17 = v13 <= 0;
    goto LABEL_12;
  }
LABEL_28:
  while ( v8 )
  {
    if ( *((_WORD *)v8 + 22) <= a2 )
    {
      v18 = *((_WORD *)v8 + 22);
      v19 = (char *)v8 + 46;
      v20 = a3;
      v21 = v18 >> 3;
      if ( v21 )
      {
        while ( *v19 == *v20 )
        {
          ++v19;
          ++v20;
          if ( !--v21 )
            goto LABEL_24;
        }
        v24 = (unsigned __int8)*v20;
        v23 = (unsigned __int8)*v19;
      }
      else
      {
LABEL_24:
        v22 = v18 & 7;
        if ( !v22 )
          break;
        v23 = (unsigned __int8)*v19 >> (8 - v22);
        v24 = (unsigned __int8)*v20 >> (8 - v22);
      }
      if ( v23 == v24 )
        break;
    }
    v8 = (__int64 *)*v8;
  }
LABEL_29:
  if ( a4 )
  {
    *(_QWORD *)a4 = v8;
    *(_QWORD *)(a4 + 8) = v6;
    *(_DWORD *)(a4 + 16) = v7;
  }
  if ( v8 )
    v25 = v8[3];
  else
    v25 = 0;
  *a5 = v25;
  return v5 == 0 ? 0x490 : 0;
}

```

## disassembly

```asm
0x180002560  push    rbx
0x180002562  push    rbp
0x180002563  push    rsi
0x180002564  push    rdi
0x180002565  push    r14
0x180002567  mov     r11, [rcx]
0x18000256a  xor     ebp, ebp
0x18000256c  or      edi, 0FFFFFFFFh
0x18000256f  xor     r10d, r10d
0x180002572  mov     rbx, r9
0x180002575  mov     r14, r8
0x180002578  movzx   esi, dx
0x18000257b  test    r11, r11
0x18000257e  jz      loc_180002654
0x180002584  mov     r9d, [rcx+8]
0x180002588  test    r9d, r9d
0x18000258b  jnz     short loc_180002591
0x18000258d  xor     ecx, ecx
0x18000258f  jmp     short loc_1800025C1
0x180002591  lea     r8d, [r9-1]
0x180002595  mov     rcx, r14
0x180002598  lea     rdx, [r11+2Eh]
0x18000259c  test    r8d, r8d
0x18000259f  jz      short loc_1800025B3
0x1800025a1  mov     al, [rdx]
0x1800025a3  cmp     [rcx], al
0x1800025a5  jnz     short loc_1800025B3
0x1800025a7  inc     rcx
0x1800025aa  inc     rdx
0x1800025ad  add     r8d, 0FFFFFFFFh
0x1800025b1  jnz     short loc_1800025A1
0x1800025b3  movzx   ecx, byte ptr [rcx]
0x1800025b6  movzx   eax, byte ptr [rdx]
0x1800025b9  sub     ecx, eax
0x1800025bb  js      short loc_1800025DD
0x1800025bd  test    ecx, ecx
0x1800025bf  jnz     short loc_1800025CA
0x1800025c1  cmp     si, [r11+2Ch]
0x1800025c6  jb      short loc_1800025DD
0x1800025c8  test    ecx, ecx
0x1800025ca  jg      short loc_1800025D3
0x1800025cc  cmp     si, [r11+2Ch]
0x1800025d1  jbe     short loc_1800025F2
0x1800025d3  mov     edi, 1
0x1800025d8  mov     r10, r11
0x1800025db  jmp     short loc_1800025E0
0x1800025dd  or      edi, 0FFFFFFFFh
0x1800025e0  movsxd  rax, edi
0x1800025e3  mov     rbp, r11
0x1800025e6  mov     r11, [r11+rax*8+18h]
0x1800025eb  test    r11, r11
0x1800025ee  jnz     short loc_180002588
0x1800025f0  jmp     short loc_180002654
0x1800025f2  mov     r10, r11
0x1800025f5  test    r11, r11
0x1800025f8  jnz     short loc_180002659
0x1800025fa  jmp     short loc_180002654
0x1800025fc  cmp     [r10+2Ch], si
0x180002601  ja      short loc_180002651
0x180002603  movzx   edx, word ptr [r10+2Ch]
0x180002608  lea     r9, [r10+2Eh]
0x18000260c  mov     ecx, edx
0x18000260e  mov     r8, r14
0x180002611  shr     ecx, 3
0x180002614  test    ecx, ecx
0x180002616  jz      short loc_18000262B
0x180002618  mov     al, [r8]
0x18000261b  cmp     [r9], al
0x18000261e  jnz     short loc_180002673
0x180002620  inc     r9
0x180002623  inc     r8
0x180002626  add     ecx, 0FFFFFFFFh
0x180002629  jnz     short loc_180002618
0x18000262b  and     edx, 7
0x18000262e  jz      short loc_180002659
0x180002630  movzx   r9d, byte ptr [r9]
0x180002634  mov     eax, 8
0x180002639  sub     al, dl
0x18000263b  movzx   edx, al
0x18000263e  movzx   eax, byte ptr [r8]
0x180002642  mov     cl, dl
0x180002644  shr     r9d, cl
0x180002647  shr     eax, cl
0x180002649  sub     r9d, eax
0x18000264c  test    r9d, r9d
0x18000264f  jz      short loc_180002659
0x180002651  mov     r10, [r10]
0x180002654  test    r10, r10
0x180002657  jnz     short loc_1800025FC
0x180002659  test    rbx, rbx
0x18000265c  jz      short loc_180002668
0x18000265e  mov     [rbx], r10
0x180002661  mov     [rbx+8], rbp
0x180002665  mov     [rbx+10h], edi
0x180002668  test    r10, r10
0x18000266b  jz      short loc_18000267D
0x18000266d  mov     rcx, [r10+18h]
0x180002671  jmp     short loc_18000267F
0x180002673  movzx   eax, byte ptr [r8]
0x180002677  movzx   r9d, byte ptr [r9]
0x18000267b  jmp     short loc_180002649
0x18000267d  xor     ecx, ecx
0x18000267f  mov     rax, [rsp+28h+arg_20]
0x180002684  neg     r11
0x180002687  mov     [rax], rcx
0x18000268a  sbb     eax, eax
0x18000268c  not     eax
0x18000268e  and     eax, 490h
0x180002693  pop     r14
0x180002695  pop     rdi
0x180002696  pop     rsi
0x180002697  pop     rbp
0x180002698  pop     rbx
0x180002699  retn
```
