# writeTileHeaderLP

- ea: `0x180042294`
- end: `0x18004248d`
- name: `writeTileHeaderLP`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004d10`

## callees

- `0x180002644`
- `0x18000285c`
- `0x180003760`
- `0x180011738`
- `0x1800118d8`
- `0x180034df4`
- `0x18003dfe0`
- `0x180042294`

## pseudocode

```c
__int64 __fastcall writeTileHeaderLP(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 i; // rbp
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rcx
  char v8; // al
  __int64 v9; // rdx
  unsigned __int8 v10; // r9
  char v11; // r8
  unsigned __int8 v12; // cl
  char v13; // cl
  unsigned __int8 j; // r15
  int v15; // r8d

  v3 = a1;
  for ( i = (*(_QWORD *)(a1 + 35664) != 0) + 1LL; i; --i )
  {
    if ( *(_DWORD *)(v3 + 188) != 3 && (*(_BYTE *)(v3 + 34284) & 2) != 0 )
    {
      v5 = *(_QWORD *)(v3 + 34464) + 432LL * *(_QWORD *)(v3 + 34392);
      *(_DWORD *)(v5 + 388) = 0;
      putBit16z(a2, 0, 1);
      *(_BYTE *)(v5 + 386) = 0;
      *(_BYTE *)(v5 + 384) = 3;
      if ( *(_QWORD *)(v3 + 34384) )
        freeQuantizer(v5 + 128);
      if ( (unsigned int)allocateQuantizer(v5 + 128, *(_QWORD *)(v3 + 34240), *(unsigned __int8 *)(v5 + 384)) )
        return 0xFFFFFFFFLL;
      if ( *(_DWORD *)(v5 + 388) == 1 )
      {
        useDCQuantizer(v3, *(_QWORD *)(v3 + 34392), v6);
      }
      else
      {
        putBit16z(a2, (*(_BYTE *)(v5 + 384) - 1) & 0xF, 4);
        LOBYTE(v7) = *(_BYTE *)(v5 + 384);
        v8 = dquantBits(v7);
        v10 = 0;
        for ( *(_BYTE *)(v5 + 386) = v8;
              (unsigned __int64)v10 < *(_QWORD *)(v3 + 34240);
              *(_BYTE *)(*(_QWORD *)(v5 + 8 * v9 + 128) + 40LL) = v13 )
        {
          v9 = v10;
          v11 = 2;
          v12 = *(_BYTE *)(v10 + v3 + 34304);
          **(_BYTE **)(v5 + 8LL * v10 + 128) = v12;
          if ( v12 >= 0x12u )
            v11 = v12 - 16;
          *(_BYTE *)(*(_QWORD *)(v5 + 8LL * v10 + 128) + 20LL) = v11;
          if ( v12 <= 0xEEu )
            v13 = v12 + 16;
          else
            v13 = -1;
          ++v10;
        }
        for ( j = 0; j < *(_BYTE *)(v5 + 384); ++j )
        {
          LOBYTE(v9) = 2;
          *(_BYTE *)(j + v5 + 397) = 2;
          formatQuantizer(v5 + 128, v9, *(_QWORD *)(v3 + 34240), j, 1, *(_DWORD *)(v3 + 34224));
          LOBYTE(v15) = *(_BYTE *)(j + v5 + 397);
          writeQuantizer(v5 + 128, a2, v15, *(_QWORD *)(v3 + 34240), j);
        }
      }
    }
    v3 = *(_QWORD *)(v3 + 35664);
  }
  return 0;
}

```

## disassembly

```asm
0x180042294  push    rbx
0x180042296  push    rbp
0x180042297  push    rsi
0x180042298  push    rdi
0x180042299  push    r12
0x18004229b  push    r14
0x18004229d  push    r15
0x18004229f  sub     rsp, 30h
0x1800422a3  mov     rax, [rcx+8B50h]
0x1800422aa  mov     r12, rdx
0x1800422ad  neg     rax
0x1800422b0  mov     rdi, rcx
0x1800422b3  sbb     rbp, rbp
0x1800422b6  neg     rbp
0x1800422b9  inc     rbp
0x1800422bc  test    rbp, rbp
0x1800422bf  jz      loc_18004247C
0x1800422c5  cmp     dword ptr [rdi+0BCh], 3
0x1800422cc  jz      loc_180042468
0x1800422d2  test    byte ptr [rdi+85ECh], 2
0x1800422d9  jz      loc_180042468
0x1800422df  imul    rsi, [rdi+8658h], 1B0h
0x1800422ea  xor     edx, edx
0x1800422ec  mov     rcx, r12
0x1800422ef  add     rsi, [rdi+86A0h]
0x1800422f6  lea     r8d, [rdx+1]
0x1800422fa  mov     dword ptr [rsi+184h], 0
0x180042304  call    putBit16z
0x180042309  mov     byte ptr [rsi+182h], 0
0x180042310  lea     r14, [rsi+80h]
0x180042317  mov     byte ptr [rsi+180h], 3
0x18004231e  cmp     qword ptr [rdi+8650h], 0
0x180042326  jbe     short loc_180042330
0x180042328  mov     rcx, r14
0x18004232b  call    freeQuantizer
0x180042330  movzx   r8d, byte ptr [rsi+180h]
0x180042338  mov     rcx, r14
0x18004233b  mov     rdx, [rdi+85C0h]
0x180042342  call    allocateQuantizer
0x180042347  test    eax, eax
0x180042349  jnz     loc_180042477
0x18004234f  cmp     dword ptr [rsi+184h], 1
0x180042356  jnz     short loc_18004236C
0x180042358  mov     rdx, [rdi+8658h]
0x18004235f  mov     rcx, rdi
0x180042362  call    useDCQuantizer
0x180042367  jmp     loc_180042468
0x18004236c  movzx   edx, byte ptr [rsi+180h]
0x180042373  mov     r8d, 4
0x180042379  dec     edx
0x18004237b  mov     rcx, r12
0x18004237e  and     edx, 0Fh
0x180042381  call    putBit16z
0x180042386  mov     cl, [rsi+180h]
0x18004238c  call    dquantBits
0x180042391  xor     r9b, r9b
0x180042394  mov     [rsi+182h], al
0x18004239a  cmp     qword ptr [rdi+85C0h], 0
0x1800423a2  jbe     short loc_1800423FF
0x1800423a4  movzx   edx, r9b
0x1800423a8  mov     r8d, 2
0x1800423ae  movzx   ecx, byte ptr [rdx+rdi+8600h]
0x1800423b6  mov     rax, [rsi+rdx*8+80h]
0x1800423be  mov     [rax], cl
0x1800423c0  cmp     cl, 12h
0x1800423c3  jb      short loc_1800423C9
0x1800423c5  lea     r8d, [rcx-10h]
0x1800423c9  mov     rax, [rsi+rdx*8+80h]
0x1800423d1  mov     [rax+14h], r8b
0x1800423d5  cmp     cl, 0EEh
0x1800423d8  jbe     short loc_1800423E1
0x1800423da  mov     ecx, 0FFh
0x1800423df  jmp     short loc_1800423E4
0x1800423e1  add     ecx, 10h
0x1800423e4  mov     rax, [rsi+rdx*8+80h]
0x1800423ec  inc     r9b
0x1800423ef  mov     [rax+28h], cl
0x1800423f2  movzx   eax, r9b
0x1800423f6  cmp     rax, [rdi+85C0h]
0x1800423fd  jb      short loc_1800423A4
0x1800423ff  xor     r15b, r15b
0x180042402  cmp     [rsi+180h], r15b
0x180042409  jbe     short loc_180042468
0x18004240b  movzx   ebx, r15b
0x18004240f  mov     dl, 2
0x180042411  mov     r9d, ebx
0x180042414  mov     rcx, r14
0x180042417  mov     byte ptr [rbx+rsi+18Dh], 2
0x18004241f  mov     eax, [rdi+85B0h]
0x180042425  mov     r8, [rdi+85C0h]
0x18004242c  mov     [rsp+68h+var_40], eax
0x180042430  mov     dword ptr [rsp+68h+var_48], 1
0x180042438  call    formatQuantizer
0x18004243d  mov     r9, [rdi+85C0h]
0x180042444  mov     rdx, r12
0x180042447  mov     r8b, [rbx+rsi+18Dh]
0x18004244f  mov     rcx, r14
0x180042452  mov     [rsp+68h+var_48], rbx
0x180042457  call    writeQuantizer
0x18004245c  inc     r15b
0x18004245f  cmp     r15b, [rsi+180h]
0x180042466  jb      short loc_18004240B
0x180042468  mov     rdi, [rdi+8B50h]
0x18004246f  dec     rbp
0x180042472  jmp     loc_1800422BC
0x180042477  or      eax, 0FFFFFFFFh
0x18004247a  jmp     short loc_18004247E
0x18004247c  xor     eax, eax
0x18004247e  add     rsp, 30h
0x180042482  pop     r15
0x180042484  pop     r14
0x180042486  pop     r12
0x180042488  pop     rdi
0x180042489  pop     rsi
0x18004248a  pop     rbp
0x18004248b  pop     rbx
0x18004248c  retn
```
