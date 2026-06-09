# WriteImagePlaneHeader

- ea: `0x180002214`
- end: `0x180002508`
- name: `WriteImagePlaneHeader`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800034a0`
- `0x180007400`
- `0x180030e10`

## callees

- `0x180002214`
- `0x1800028f4`
- `0x180003830`

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
0x180002214  push    rbx
0x180002216  push    rbp
0x180002217  push    rsi
0x180002218  push    rdi
0x180002219  push    r12
0x18000221b  push    r14
0x18000221d  sub     rsp, 38h
0x180002221  mov     edx, [rcx+85A8h]
0x180002227  mov     rbx, rcx
0x18000222a  mov     rdi, [rcx+8640h]
0x180002231  mov     r12d, 3
0x180002237  and     edx, 7
0x18000223a  mov     r8d, r12d
0x18000223d  mov     rcx, rdi
0x180002240  call    putBit16z
0x180002245  mov     edx, [rbx+85B0h]
0x18000224b  lea     ebp, [r12-2]
0x180002250  and     edx, ebp
0x180002252  mov     r8d, ebp
0x180002255  mov     rcx, rdi
0x180002258  call    putBit16z
0x18000225d  mov     edx, [rbx+0BCh]
0x180002263  lea     r11d, [r12+1]
0x180002268  and     edx, 0Fh
0x18000226b  mov     r8d, r11d
0x18000226e  mov     rcx, rdi
0x180002271  call    putBit16z
0x180002276  mov     eax, [rbx+85A8h]
0x18000227c  sub     eax, ebp
0x18000227e  jz      short loc_1800022D4
0x180002280  sub     eax, ebp
0x180002282  jz      short loc_1800022AC
0x180002284  sub     eax, ebp
0x180002286  jz      short loc_1800022A8
0x180002288  cmp     eax, r12d
0x18000228b  jnz     loc_180002318
0x180002291  mov     edx, [rbx+85C0h]
0x180002297  sub     edx, ebp
0x180002299  and     edx, 0Fh
0x18000229c  mov     rcx, rdi
0x18000229f  call    putBit16z
0x1800022a4  xor     edx, edx
0x1800022a6  jmp     short loc_180002310
0x1800022a8  xor     edx, edx
0x1800022aa  jmp     short loc_18000229C
0x1800022ac  mov     r8d, ebp
0x1800022af  mov     byte ptr [rbx+3Dh], 2
0x1800022b3  xor     edx, edx
0x1800022b5  mov     rcx, rdi
0x1800022b8  call    putBit16z
0x1800022bd  movzx   edx, byte ptr [rbx+3Dh]
0x1800022c1  mov     r8d, r12d
0x1800022c4  and     edx, 7
0x1800022c7  mov     rcx, rdi
0x1800022ca  call    putBit16z
0x1800022cf  mov     r8d, r11d
0x1800022d2  jmp     short loc_1800022A4
0x1800022d4  mov     r8d, ebp
0x1800022d7  mov     word ptr [rbx+3Dh], 202h
0x1800022dd  xor     edx, edx
0x1800022df  mov     rcx, rdi
0x1800022e2  call    putBit16z
0x1800022e7  movzx   edx, byte ptr [rbx+3Dh]
0x1800022eb  mov     r8d, r12d
0x1800022ee  and     edx, 7
0x1800022f1  mov     rcx, rdi
0x1800022f4  call    putBit16z
0x1800022f9  xor     edx, edx
0x1800022fb  mov     rcx, rdi
0x1800022fe  mov     r8d, ebp
0x180002301  call    putBit16z
0x180002306  movzx   edx, byte ptr [rbx+3Eh]
0x18000230a  mov     r8d, r12d
0x18000230d  and     edx, 7
0x180002310  mov     rcx, rdi
0x180002313  call    putBit16z
0x180002318  cmp     dword ptr [rbx+18h], 5
0x18000231c  jnz     short loc_18000234A
0x18000231e  movzx   edx, byte ptr [rbx+3Ch]
0x180002322  mov     r8d, 2
0x180002328  and     edx, r12d
0x18000232b  mov     rcx, rdi
0x18000232e  call    putBit16z
0x180002333  xor     edx, edx
0x180002335  mov     rcx, rdi
0x180002338  call    putBit16z
0x18000233d  xor     edx, edx
0x18000233f  mov     rcx, rdi
0x180002342  mov     r8d, r11d
0x180002345  call    putBit16z
0x18000234a  mov     ecx, [rbx+1Ch]
0x18000234d  sub     ecx, 2
0x180002350  jz      short loc_1800023AB
0x180002352  sub     ecx, ebp
0x180002354  jz      short loc_1800023AB
0x180002356  sub     ecx, 2
0x180002359  jz      short loc_180002394
0x18000235b  sub     ecx, ebp
0x18000235d  jz      short loc_180002394
0x18000235f  cmp     ecx, ebp
0x180002361  jnz     short loc_1800023C0
0x180002363  mov     al, [rbx+80E0h]
0x180002369  test    al, al
0x18000236b  jnz     short loc_180002375
0x18000236d  mov     al, 0Dh
0x18000236f  mov     [rbx+80E0h], al
0x180002375  movzx   edx, al
0x180002378  mov     r8d, 8
0x18000237e  mov     rcx, rdi
0x180002381  call    putBit16z
0x180002386  movsx   r8d, byte ptr [rbx+80E1h]
0x18000238e  movzx   edx, r8b
0x180002392  jmp     short loc_1800023B2
0x180002394  mov     al, [rbx+80E0h]
0x18000239a  test    al, al
0x18000239c  jnz     short loc_1800023A6
0x18000239e  mov     al, 0Ah
0x1800023a0  mov     [rbx+80E0h], al
0x1800023a6  movzx   edx, al
0x1800023a9  jmp     short loc_1800023B2
0x1800023ab  movzx   edx, byte ptr [rbx+80E0h]
0x1800023b2  mov     r8d, 8
0x1800023b8  mov     rcx, rdi
0x1800023bb  call    putBit16z
0x1800023c0  lea     rsi, [rbx+85ECh]
0x1800023c7  mov     r8d, ebp
0x1800023ca  mov     edx, [rsi]
0x1800023cc  mov     rcx, rdi
0x1800023cf  not     edx
0x1800023d1  and     edx, ebp
0x1800023d3  call    putBit16z
0x1800023d8  mov     r8d, [rsi]
0x1800023db  test    bpl, r8b
0x1800023de  jnz     short loc_18000240F
0x1800023e0  mov     r9, [rbx+85C0h]
0x1800023e7  mov     rdx, rdi
0x1800023ea  mov     rcx, [rbx+86A0h]
0x1800023f1  shr     r8d, 3
0x1800023f5  and     r8b, r12b
0x1800023f8  mov     [rsp+68h+var_48], 0
0x180002401  call    writeQuantizer
0x180002406  lea     r14, [rbx+85ECh]
0x18000240d  jmp     short loc_180002412
0x18000240f  mov     r14, rsi
0x180002412  cmp     [rbx+0BCh], r12d
0x180002419  jz      loc_1800024E7
0x18000241f  mov     edx, [rsi]
0x180002421  mov     r8d, ebp
0x180002424  shr     edx, 9
0x180002427  mov     rcx, rdi
0x18000242a  not     edx
0x18000242c  and     edx, ebp
0x18000242e  call    putBit16z
0x180002433  mov     edx, [rsi]
0x180002435  bt      edx, 9
0x180002439  jnb     short loc_18000247C
0x18000243b  shr     edx, 1
0x18000243d  mov     rcx, rdi
0x180002440  not     edx
0x180002442  and     edx, ebp
0x180002444  call    putBit16z
0x180002449  mov     r8d, [rsi]
0x18000244c  test    r8b, 2
0x180002450  jnz     short loc_18000247C
0x180002452  mov     rcx, [rbx+86A0h]
0x180002459  mov     rdx, rdi
0x18000245c  mov     r9, [rbx+85C0h]
0x180002463  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180002467  shr     r8d, 5
0x18000246b  and     r8b, r12b
0x18000246e  mov     [rsp+68h+var_48], 0
0x180002477  call    writeQuantizer
0x18000247c  cmp     dword ptr [rbx+0BCh], 2
0x180002483  jz      short loc_1800024E7
0x180002485  mov     edx, [r14]
0x180002488  mov     r8d, ebp
0x18000248b  shr     edx, 0Ah
0x18000248e  mov     rcx, rdi
0x180002491  not     edx
0x180002493  and     edx, ebp
0x180002495  call    putBit16z
0x18000249a  mov     edx, [rsi]
0x18000249c  bt      edx, 0Ah
0x1800024a0  jnb     short loc_1800024E7
0x1800024a2  shr     edx, 2
0x1800024a5  mov     rcx, rdi
0x1800024a8  not     edx
0x1800024aa  and     edx, ebp
0x1800024ac  call    putBit16z
0x1800024b1  mov     r8d, [rsi]
0x1800024b4  test    r8b, 4
0x1800024b8  jnz     short loc_1800024E7
0x1800024ba  mov     rcx, [rbx+86A0h]
0x1800024c1  mov     rdx, rdi
0x1800024c4  mov     r9, [rbx+85C0h]
0x1800024cb  add     rcx, 100h
0x1800024d2  shr     r8d, 7
0x1800024d6  and     r8b, r12b
0x1800024d9  mov     [rsp+68h+var_48], 0
0x1800024e2  call    writeQuantizer
0x1800024e7  mov     r8d, [rdi+8]
0x1800024eb  xor     edx, edx
0x1800024ed  neg     r8d
0x1800024f0  mov     rcx, rdi
0x1800024f3  and     r8d, 7
0x1800024f7  add     rsp, 38h
0x1800024fb  pop     r14
0x1800024fd  pop     r12
0x1800024ff  pop     rdi
0x180002500  pop     rsi
0x180002501  pop     rbp
0x180002502  pop     rbx
0x180002503  jmp     putBit16z
```
