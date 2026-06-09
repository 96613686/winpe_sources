# WriteImagePlaneHeader

- ea: `0x1800021c0`
- end: `0x1800024b4`
- name: `WriteImagePlaneHeader`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800033cc`
- `0x180007340`
- `0x1800309d0`

## callees

- `0x1800021c0`
- `0x18000285c`
- `0x180003760`

## pseudocode

```c
__int64 __fastcall WriteImagePlaneHeader(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned int v7; // r11d
  __int64 v8; // r8
  unsigned int v9; // r11d
  unsigned __int8 v10; // al
  __int64 v11; // rdx
  unsigned __int8 v12; // al
  _DWORD *v13; // rsi
  int v14; // r8d
  __int64 v15; // r8
  int v16; // r8d
  __int64 v17; // r8
  int v18; // r8d

  v2 = *(_QWORD *)(a1 + 34368);
  putBit16z(v2, *(_DWORD *)(a1 + 34216) & 7, 3);
  putBit16z(v2, *(_DWORD *)(a1 + 34224) & 1, 1);
  putBit16z(v2, *(_DWORD *)(a1 + 188) & 0xF, 4);
  if ( *(_DWORD *)(a1 + 34216) == 1 )
  {
    *(_WORD *)(a1 + 61) = 514;
    putBit16z(v2, 0, 1);
    putBit16z(v2, *(_BYTE *)(a1 + 61) & 7, 3);
    putBit16z(v2, 0, 1);
    v5 = 3;
    v6 = *(_BYTE *)(a1 + 62) & 7;
  }
  else
  {
    if ( *(_DWORD *)(a1 + 34216) == 2 )
    {
      *(_BYTE *)(a1 + 61) = 2;
      putBit16z(v2, 0, 1);
      putBit16z(v2, *(_BYTE *)(a1 + 61) & 7, 3);
      v5 = v7;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 34216) == 3 )
      {
        v4 = 0;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 34216) != 6 )
          goto LABEL_12;
        v4 = ((unsigned __int8)*(_DWORD *)(a1 + 34240) - 1) & 0xF;
      }
      putBit16z(v2, v4, v3);
    }
    v6 = 0;
  }
  putBit16z(v2, v6, v5);
LABEL_12:
  if ( *(_DWORD *)(a1 + 24) == 5 )
  {
    putBit16z(v2, *(_BYTE *)(a1 + 60) & 3, 2);
    putBit16z(v2, 0, v8);
    putBit16z(v2, 0, v9);
  }
  switch ( *(_DWORD *)(a1 + 28) )
  {
    case 2:
    case 3:
      v11 = *(unsigned __int8 *)(a1 + 32992);
      break;
    case 5:
    case 6:
      v12 = *(_BYTE *)(a1 + 32992);
      if ( !v12 )
      {
        v12 = 10;
        *(_BYTE *)(a1 + 32992) = 10;
      }
      v11 = v12;
      break;
    case 7:
      v10 = *(_BYTE *)(a1 + 32992);
      if ( !v10 )
      {
        v10 = 13;
        *(_BYTE *)(a1 + 32992) = 13;
      }
      putBit16z(v2, v10, 8);
      v11 = *(unsigned __int8 *)(a1 + 32993);
      break;
    default:
      goto LABEL_27;
  }
  putBit16z(v2, v11, 8);
LABEL_27:
  v13 = (_DWORD *)(a1 + 34284);
  putBit16z(v2, (*(_DWORD *)(a1 + 34284) & 1) == 0, 1);
  if ( (*(_DWORD *)(a1 + 34284) & 1) == 0 )
  {
    v14 = *(_DWORD *)(a1 + 34284) >> 3;
    LOBYTE(v14) = v14 & 3;
    writeQuantizer(*(_QWORD *)(a1 + 34464), v2, v14, *(_QWORD *)(a1 + 34240), 0);
  }
  if ( *(_DWORD *)(a1 + 188) != 3 )
  {
    putBit16z(v2, ((*v13 >> 9) & 1) == 0, 1);
    if ( (*v13 & 0x200) != 0 )
    {
      putBit16z(v2, ((*v13 >> 1) & 1) == 0, v15);
      if ( (*v13 & 2) == 0 )
      {
        v16 = *v13 >> 5;
        LOBYTE(v16) = v16 & 3;
        writeQuantizer(*(_DWORD *)(a1 + 34464) + 128, v2, v16, *(_QWORD *)(a1 + 34240), 0);
      }
    }
    if ( *(_DWORD *)(a1 + 188) != 2 )
    {
      putBit16z(v2, ((*(_DWORD *)(a1 + 34284) >> 10) & 1) == 0, 1);
      if ( (*v13 & 0x400) != 0 )
      {
        putBit16z(v2, ((*v13 >> 2) & 1) == 0, v17);
        if ( (*v13 & 4) == 0 )
        {
          v18 = *v13 >> 7;
          LOBYTE(v18) = v18 & 3;
          writeQuantizer(*(_DWORD *)(a1 + 34464) + 256, v2, v18, *(_QWORD *)(a1 + 34240), 0);
        }
      }
    }
  }
  return putBit16z(v2, 0, -*(_DWORD *)(v2 + 8) & 7);
}

```

## disassembly

```asm
0x1800021c0  push    rbx
0x1800021c2  push    rbp
0x1800021c3  push    rsi
0x1800021c4  push    rdi
0x1800021c5  push    r12
0x1800021c7  push    r14
0x1800021c9  sub     rsp, 38h
0x1800021cd  mov     edx, [rcx+85A8h]
0x1800021d3  mov     rbx, rcx
0x1800021d6  mov     rdi, [rcx+8640h]
0x1800021dd  mov     r12d, 3
0x1800021e3  and     edx, 7
0x1800021e6  mov     r8d, r12d
0x1800021e9  mov     rcx, rdi
0x1800021ec  call    putBit16z
0x1800021f1  mov     edx, [rbx+85B0h]
0x1800021f7  lea     ebp, [r12-2]
0x1800021fc  and     edx, ebp
0x1800021fe  mov     r8d, ebp
0x180002201  mov     rcx, rdi
0x180002204  call    putBit16z
0x180002209  mov     edx, [rbx+0BCh]
0x18000220f  lea     r11d, [r12+1]
0x180002214  and     edx, 0Fh
0x180002217  mov     r8d, r11d
0x18000221a  mov     rcx, rdi
0x18000221d  call    putBit16z
0x180002222  mov     eax, [rbx+85A8h]
0x180002228  sub     eax, ebp
0x18000222a  jz      short loc_180002280
0x18000222c  sub     eax, ebp
0x18000222e  jz      short loc_180002258
0x180002230  sub     eax, ebp
0x180002232  jz      short loc_180002254
0x180002234  cmp     eax, r12d
0x180002237  jnz     loc_1800022C4
0x18000223d  mov     edx, [rbx+85C0h]
0x180002243  sub     edx, ebp
0x180002245  and     edx, 0Fh
0x180002248  mov     rcx, rdi
0x18000224b  call    putBit16z
0x180002250  xor     edx, edx
0x180002252  jmp     short loc_1800022BC
0x180002254  xor     edx, edx
0x180002256  jmp     short loc_180002248
0x180002258  mov     r8d, ebp
0x18000225b  mov     byte ptr [rbx+3Dh], 2
0x18000225f  xor     edx, edx
0x180002261  mov     rcx, rdi
0x180002264  call    putBit16z
0x180002269  movzx   edx, byte ptr [rbx+3Dh]
0x18000226d  mov     r8d, r12d
0x180002270  and     edx, 7
0x180002273  mov     rcx, rdi
0x180002276  call    putBit16z
0x18000227b  mov     r8d, r11d
0x18000227e  jmp     short loc_180002250
0x180002280  mov     r8d, ebp
0x180002283  mov     word ptr [rbx+3Dh], 202h
0x180002289  xor     edx, edx
0x18000228b  mov     rcx, rdi
0x18000228e  call    putBit16z
0x180002293  movzx   edx, byte ptr [rbx+3Dh]
0x180002297  mov     r8d, r12d
0x18000229a  and     edx, 7
0x18000229d  mov     rcx, rdi
0x1800022a0  call    putBit16z
0x1800022a5  xor     edx, edx
0x1800022a7  mov     rcx, rdi
0x1800022aa  mov     r8d, ebp
0x1800022ad  call    putBit16z
0x1800022b2  movzx   edx, byte ptr [rbx+3Eh]
0x1800022b6  mov     r8d, r12d
0x1800022b9  and     edx, 7
0x1800022bc  mov     rcx, rdi
0x1800022bf  call    putBit16z
0x1800022c4  cmp     dword ptr [rbx+18h], 5
0x1800022c8  jnz     short loc_1800022F6
0x1800022ca  movzx   edx, byte ptr [rbx+3Ch]
0x1800022ce  mov     r8d, 2
0x1800022d4  and     edx, r12d
0x1800022d7  mov     rcx, rdi
0x1800022da  call    putBit16z
0x1800022df  xor     edx, edx
0x1800022e1  mov     rcx, rdi
0x1800022e4  call    putBit16z
0x1800022e9  xor     edx, edx
0x1800022eb  mov     rcx, rdi
0x1800022ee  mov     r8d, r11d
0x1800022f1  call    putBit16z
0x1800022f6  mov     ecx, [rbx+1Ch]
0x1800022f9  sub     ecx, 2
0x1800022fc  jz      short loc_180002357
0x1800022fe  sub     ecx, ebp
0x180002300  jz      short loc_180002357
0x180002302  sub     ecx, 2
0x180002305  jz      short loc_180002340
0x180002307  sub     ecx, ebp
0x180002309  jz      short loc_180002340
0x18000230b  cmp     ecx, ebp
0x18000230d  jnz     short loc_18000236C
0x18000230f  mov     al, [rbx+80E0h]
0x180002315  test    al, al
0x180002317  jnz     short loc_180002321
0x180002319  mov     al, 0Dh
0x18000231b  mov     [rbx+80E0h], al
0x180002321  movzx   edx, al
0x180002324  mov     r8d, 8
0x18000232a  mov     rcx, rdi
0x18000232d  call    putBit16z
0x180002332  movsx   r8d, byte ptr [rbx+80E1h]
0x18000233a  movzx   edx, r8b
0x18000233e  jmp     short loc_18000235E
0x180002340  mov     al, [rbx+80E0h]
0x180002346  test    al, al
0x180002348  jnz     short loc_180002352
0x18000234a  mov     al, 0Ah
0x18000234c  mov     [rbx+80E0h], al
0x180002352  movzx   edx, al
0x180002355  jmp     short loc_18000235E
0x180002357  movzx   edx, byte ptr [rbx+80E0h]
0x18000235e  mov     r8d, 8
0x180002364  mov     rcx, rdi
0x180002367  call    putBit16z
0x18000236c  lea     rsi, [rbx+85ECh]
0x180002373  mov     r8d, ebp
0x180002376  mov     edx, [rsi]
0x180002378  mov     rcx, rdi
0x18000237b  not     edx
0x18000237d  and     edx, ebp
0x18000237f  call    putBit16z
0x180002384  mov     r8d, [rsi]
0x180002387  test    bpl, r8b
0x18000238a  jnz     short loc_1800023BB
0x18000238c  mov     r9, [rbx+85C0h]
0x180002393  mov     rdx, rdi
0x180002396  mov     rcx, [rbx+86A0h]
0x18000239d  shr     r8d, 3
0x1800023a1  and     r8b, r12b
0x1800023a4  mov     [rsp+68h+var_48], 0
0x1800023ad  call    writeQuantizer
0x1800023b2  lea     r14, [rbx+85ECh]
0x1800023b9  jmp     short loc_1800023BE
0x1800023bb  mov     r14, rsi
0x1800023be  cmp     [rbx+0BCh], r12d
0x1800023c5  jz      loc_180002493
0x1800023cb  mov     edx, [rsi]
0x1800023cd  mov     r8d, ebp
0x1800023d0  shr     edx, 9
0x1800023d3  mov     rcx, rdi
0x1800023d6  not     edx
0x1800023d8  and     edx, ebp
0x1800023da  call    putBit16z
0x1800023df  mov     edx, [rsi]
0x1800023e1  bt      edx, 9
0x1800023e5  jnb     short loc_180002428
0x1800023e7  shr     edx, 1
0x1800023e9  mov     rcx, rdi
0x1800023ec  not     edx
0x1800023ee  and     edx, ebp
0x1800023f0  call    putBit16z
0x1800023f5  mov     r8d, [rsi]
0x1800023f8  test    r8b, 2
0x1800023fc  jnz     short loc_180002428
0x1800023fe  mov     rcx, [rbx+86A0h]
0x180002405  mov     rdx, rdi
0x180002408  mov     r9, [rbx+85C0h]
0x18000240f  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180002413  shr     r8d, 5
0x180002417  and     r8b, r12b
0x18000241a  mov     [rsp+68h+var_48], 0
0x180002423  call    writeQuantizer
0x180002428  cmp     dword ptr [rbx+0BCh], 2
0x18000242f  jz      short loc_180002493
0x180002431  mov     edx, [r14]
0x180002434  mov     r8d, ebp
0x180002437  shr     edx, 0Ah
0x18000243a  mov     rcx, rdi
0x18000243d  not     edx
0x18000243f  and     edx, ebp
0x180002441  call    putBit16z
0x180002446  mov     edx, [rsi]
0x180002448  bt      edx, 0Ah
0x18000244c  jnb     short loc_180002493
0x18000244e  shr     edx, 2
0x180002451  mov     rcx, rdi
0x180002454  not     edx
0x180002456  and     edx, ebp
0x180002458  call    putBit16z
0x18000245d  mov     r8d, [rsi]
0x180002460  test    r8b, 4
0x180002464  jnz     short loc_180002493
0x180002466  mov     rcx, [rbx+86A0h]
0x18000246d  mov     rdx, rdi
0x180002470  mov     r9, [rbx+85C0h]
0x180002477  add     rcx, 100h
0x18000247e  shr     r8d, 7
0x180002482  and     r8b, r12b
0x180002485  mov     [rsp+68h+var_48], 0
0x18000248e  call    writeQuantizer
0x180002493  mov     r8d, [rdi+8]
0x180002497  xor     edx, edx
0x180002499  neg     r8d
0x18000249c  mov     rcx, rdi
0x18000249f  and     r8d, 7
0x1800024a3  add     rsp, 38h
0x1800024a7  pop     r14
0x1800024a9  pop     r12
0x1800024ab  pop     rdi
0x1800024ac  pop     rsi
0x1800024ad  pop     rbp
0x1800024ae  pop     rbx
0x1800024af  jmp     putBit16z
```
