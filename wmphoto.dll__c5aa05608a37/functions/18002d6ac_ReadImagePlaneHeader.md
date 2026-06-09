# ReadImagePlaneHeader

- ea: `0x18002d6ac`
- end: `0x18002d9e0`
- name: `ReadImagePlaneHeader`
- size: `820`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007340`
- `0x180010148`
- `0x1800106f0`

## callees

- `0x18002d614`
- `0x18002d6ac`
- `0x18002d9e8`

## pseudocode

```c
__int64 __fastcall ReadImagePlaneHeader(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int Bit32_SB; // eax
  int v9; // ecx
  int v10; // edx
  bool v11; // zf
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  bool v19; // cc
  unsigned __int64 *v20; // rsi
  int v21; // eax

  Bit32_SB = getBit32_SB(a4, 3);
  *(_DWORD *)(a3 + 8) = Bit32_SB;
  if ( (unsigned int)Bit32_SB > 6 )
    goto LABEL_2;
  v10 = *(_DWORD *)(a1 + 16);
  if ( v10 )
  {
    if ( v10 == 4 || v10 == 6 )
    {
      v11 = v10 == Bit32_SB;
LABEL_9:
      if ( v11 )
        goto LABEL_10;
LABEL_2:
      v9 = -106;
      return (unsigned int)-(v9 != 0);
    }
    if ( v10 != 7 )
    {
      if ( v10 != 8 )
        goto LABEL_2;
      goto LABEL_8;
    }
    if ( *(_DWORD *)(a1 + 20) == 7 || *(_DWORD *)(a1 + 20) == 4 )
    {
LABEL_8:
      v11 = Bit32_SB == 3;
      goto LABEL_9;
    }
    v19 = Bit32_SB <= 3;
  }
  else
  {
    v19 = Bit32_SB <= 0;
  }
  if ( !v19 )
    goto LABEL_2;
LABEL_10:
  *(_DWORD *)(a2 + 8) = Bit32_SB;
  *(_DWORD *)(a3 + 16) = getBit32_SB(a4, 1);
  v12 = getBit32_SB(a4, 4);
  *(_DWORD *)(a2 + 52) = v12;
  if ( v12 >= 4 )
    goto LABEL_2;
  v13 = *(_DWORD *)(a3 + 8);
  if ( !v13 )
  {
    *(_QWORD *)(a3 + 32) = 1;
    goto LABEL_32;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 53) = getBit32_SB(a4, 3);
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 54) = getBit32_SB(a4, 3);
    goto LABEL_32;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 1);
    *(_BYTE *)(a1 + 53) = getBit32_SB(a4, 3);
    goto LABEL_29;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    *(_QWORD *)(a3 + 32) = 3;
    getBit32_SB(a4, 4);
    goto LABEL_29;
  }
  v17 = v16 - 1;
  if ( v17 && (v18 = v17 - 1) != 0 )
  {
    if ( v18 == 1 )
    {
      *(_QWORD *)(a3 + 32) = (int)(getBit32_SB(a4, 4) + 1);
LABEL_29:
      getBit32_SB(a4, 4);
    }
  }
  else
  {
    *(_QWORD *)(a3 + 32) = 4;
  }
LABEL_32:
  if ( *(_DWORD *)(a1 + 20) == 2 || *(_DWORD *)(a1 + 20) == 3 || *(_DWORD *)(a1 + 20) == 5 || *(_DWORD *)(a1 + 20) == 6 )
  {
    *(_BYTE *)(a2 + 32856) = getBit32_SB(a4, 8);
  }
  else if ( *(_DWORD *)(a1 + 20) == 7 )
  {
    *(_BYTE *)(a2 + 32856) = getBit32_SB(a4, 8);
    *(_BYTE *)(a2 + 32857) = getBit32_SB(a4, 8);
  }
  *(_DWORD *)(a3 + 76) = 0;
  v20 = (unsigned __int64 *)(a3 + 32);
  if ( (unsigned int)getBit32_SB(a4, 1) == 1 )
    *(_DWORD *)(a3 + 76) += 8 * (unsigned __int8)readQuantizerSB((_BYTE *)(a3 + 80), a4, *v20);
  else
    ++*(_DWORD *)(a3 + 76);
  v21 = *(_DWORD *)(a3 + 76);
  if ( *(_DWORD *)(a2 + 52) == 3 )
    goto LABEL_57;
  if ( (unsigned int)getBit32_SB(a4, 1) )
  {
    v21 = *(_DWORD *)(a3 + 76) + 2 * ((*(_DWORD *)(a3 + 76) & 1) + 2 * (*(_DWORD *)(a3 + 76) & 0x18));
    *(_DWORD *)(a3 + 76) = v21;
  }
  else
  {
    *(_DWORD *)(a3 + 76) += 512;
    *(_DWORD *)(a3 + 76) += (unsigned int)getBit32_SB(a4, 1) == 1
                          ? 32 * (unsigned __int8)readQuantizerSB((_BYTE *)(a3 + 96), a4, *v20)
                          : 2;
    v21 = *(_DWORD *)(a3 + 76);
  }
  if ( *(_DWORD *)(a2 + 52) != 2 )
  {
    if ( (unsigned int)getBit32_SB(a4, 1) )
    {
      v21 = *(_DWORD *)(a3 + 76) + 2 * ((*(_DWORD *)(a3 + 76) & 2) + 2 * (*(_DWORD *)(a3 + 76) & 0x60));
      *(_DWORD *)(a3 + 76) = v21;
    }
    else
    {
      *(_DWORD *)(a3 + 76) += 1024;
      if ( (unsigned int)getBit32_SB(a4, 1) == 1 )
        *(_DWORD *)(a3 + 76) += (unsigned __int8)readQuantizerSB((_BYTE *)(a3 + 112), a4, *v20) << 7;
      else
        *(_DWORD *)(a3 + 76) += 4;
      v21 = *(_DWORD *)(a3 + 76);
    }
  }
  if ( *(_DWORD *)(a2 + 52) == 3 )
  {
LABEL_57:
    v21 |= 0x200u;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 52) != 2 )
      goto LABEL_61;
    v21 |= 0x400u;
  }
  *(_DWORD *)(a3 + 76) = v21;
LABEL_61:
  if ( (v21 & 0x600) != 0 )
  {
    v9 = 0;
    *(_BYTE *)(a4 + 12) = 0;
    *(_DWORD *)(a4 + 16) = 0;
  }
  else
  {
    v9 = -104;
  }
  return (unsigned int)-(v9 != 0);
}

```

## disassembly

```asm
0x18002d6ac  push    rbx
0x18002d6ae  push    rbp
0x18002d6af  push    rsi
0x18002d6b0  push    rdi
0x18002d6b1  push    r12
0x18002d6b3  push    r13
0x18002d6b5  push    r14
0x18002d6b7  sub     rsp, 20h
0x18002d6bb  mov     rbp, rdx
0x18002d6be  mov     rsi, rcx
0x18002d6c1  mov     r13d, 3
0x18002d6c7  mov     rcx, r9
0x18002d6ca  mov     edx, r13d
0x18002d6cd  mov     rdi, r9
0x18002d6d0  mov     rbx, r8
0x18002d6d3  call    getBit32_SB
0x18002d6d8  mov     [rbx+8], eax
0x18002d6db  cmp     eax, 6
0x18002d6de  jbe     short loc_18002D6EA
0x18002d6e0  mov     ecx, 0FFFFFF96h
0x18002d6e5  jmp     loc_18002D9C9
0x18002d6ea  mov     edx, [rsi+10h]
0x18002d6ed  mov     r12d, 4
0x18002d6f3  mov     ecx, edx
0x18002d6f5  test    edx, edx
0x18002d6f7  jz      loc_18002D7B4
0x18002d6fd  sub     ecx, r12d
0x18002d700  jz      loc_18002D7AD
0x18002d706  sub     ecx, 2
0x18002d709  jz      loc_18002D7AD
0x18002d70f  sub     ecx, 1
0x18002d712  jz      short loc_18002D78F
0x18002d714  cmp     ecx, 1
0x18002d717  jnz     short loc_18002D6E0
0x18002d719  cmp     eax, r13d
0x18002d71c  jnz     short loc_18002D6E0
0x18002d71e  mov     r14d, 1
0x18002d724  mov     [rbp+8], eax
0x18002d727  mov     edx, r14d
0x18002d72a  mov     rcx, rdi
0x18002d72d  call    getBit32_SB
0x18002d732  mov     edx, r12d
0x18002d735  mov     [rbx+10h], eax
0x18002d738  mov     rcx, rdi
0x18002d73b  call    getBit32_SB
0x18002d740  mov     [rbp+34h], eax
0x18002d743  cmp     eax, r12d
0x18002d746  jge     short loc_18002D6E0
0x18002d748  mov     ecx, [rbx+8]
0x18002d74b  test    ecx, ecx
0x18002d74d  jz      loc_18002D831
0x18002d753  sub     ecx, r14d
0x18002d756  jz      loc_18002D7F9
0x18002d75c  sub     ecx, r14d
0x18002d75f  jz      short loc_18002D7CF
0x18002d761  sub     ecx, r14d
0x18002d764  jz      short loc_18002D7BE
0x18002d766  sub     ecx, r14d
0x18002d769  jz      short loc_18002D7B8
0x18002d76b  sub     ecx, r14d
0x18002d76e  jz      short loc_18002D7B8
0x18002d770  cmp     ecx, r14d
0x18002d773  jnz     loc_18002D835
0x18002d779  mov     edx, r12d
0x18002d77c  mov     rcx, rdi
0x18002d77f  call    getBit32_SB
0x18002d784  add     eax, r14d
0x18002d787  cdqe
0x18002d789  mov     [rbx+20h], rax
0x18002d78d  jmp     short loc_18002D7EC
0x18002d78f  cmp     dword ptr [rsi+14h], 7
0x18002d793  jz      short loc_18002D719
0x18002d795  cmp     [rsi+14h], r12d
0x18002d799  jz      loc_18002D719
0x18002d79f  cmp     eax, r13d
0x18002d7a2  jle     loc_18002D71E
0x18002d7a8  jmp     loc_18002D6E0
0x18002d7ad  cmp     edx, eax
0x18002d7af  jmp     loc_18002D71C
0x18002d7b4  cmp     eax, edx
0x18002d7b6  jmp     short loc_18002D7A2
0x18002d7b8  mov     [rbx+20h], r12
0x18002d7bc  jmp     short loc_18002D835
0x18002d7be  mov     edx, r12d
0x18002d7c1  mov     [rbx+20h], r13
0x18002d7c5  mov     rcx, rdi
0x18002d7c8  call    getBit32_SB
0x18002d7cd  jmp     short loc_18002D7EC
0x18002d7cf  mov     edx, r14d
0x18002d7d2  mov     [rbx+20h], r13
0x18002d7d6  mov     rcx, rdi
0x18002d7d9  call    getBit32_SB
0x18002d7de  mov     edx, r13d
0x18002d7e1  mov     rcx, rdi
0x18002d7e4  call    getBit32_SB
0x18002d7e9  mov     [rsi+35h], al
0x18002d7ec  mov     edx, r12d
0x18002d7ef  mov     rcx, rdi
0x18002d7f2  call    getBit32_SB
0x18002d7f7  jmp     short loc_18002D835
0x18002d7f9  mov     edx, r14d
0x18002d7fc  mov     [rbx+20h], r13
0x18002d800  mov     rcx, rdi
0x18002d803  call    getBit32_SB
0x18002d808  mov     edx, r13d
0x18002d80b  mov     rcx, rdi
0x18002d80e  call    getBit32_SB
0x18002d813  mov     edx, r14d
0x18002d816  mov     [rsi+35h], al
0x18002d819  mov     rcx, rdi
0x18002d81c  call    getBit32_SB
0x18002d821  mov     edx, r13d
0x18002d824  mov     rcx, rdi
0x18002d827  call    getBit32_SB
0x18002d82c  mov     [rsi+36h], al
0x18002d82f  jmp     short loc_18002D835
0x18002d831  mov     [rbx+20h], r14
0x18002d835  mov     ecx, [rsi+14h]
0x18002d838  sub     ecx, 2
0x18002d83b  jz      short loc_18002D879
0x18002d83d  sub     ecx, r14d
0x18002d840  jz      short loc_18002D879
0x18002d842  sub     ecx, 2
0x18002d845  jz      short loc_18002D879
0x18002d847  sub     ecx, r14d
0x18002d84a  jz      short loc_18002D879
0x18002d84c  cmp     ecx, r14d
0x18002d84f  jnz     short loc_18002D88C
0x18002d851  mov     edx, 8
0x18002d856  mov     rcx, rdi
0x18002d859  call    getBit32_SB
0x18002d85e  mov     edx, 8
0x18002d863  mov     [rbp+8058h], al
0x18002d869  mov     rcx, rdi
0x18002d86c  call    getBit32_SB
0x18002d871  mov     [rbp+8059h], al
0x18002d877  jmp     short loc_18002D88C
0x18002d879  mov     edx, 8
0x18002d87e  mov     rcx, rdi
0x18002d881  call    getBit32_SB
0x18002d886  mov     [rbp+8058h], al
0x18002d88c  mov     edx, r14d
0x18002d88f  mov     dword ptr [rbx+4Ch], 0
0x18002d896  mov     rcx, rdi
0x18002d899  lea     rsi, [rbx+20h]
0x18002d89d  call    getBit32_SB
0x18002d8a2  cmp     eax, r14d
0x18002d8a5  jnz     short loc_18002D8C1
0x18002d8a7  mov     r8, [rsi]
0x18002d8aa  lea     rcx, [rbx+50h]
0x18002d8ae  mov     rdx, rdi
0x18002d8b1  call    readQuantizerSB
0x18002d8b6  movzx   eax, al
0x18002d8b9  shl     eax, 3
0x18002d8bc  add     [rbx+4Ch], eax
0x18002d8bf  jmp     short loc_18002D8C5
0x18002d8c1  add     [rbx+4Ch], r14d
0x18002d8c5  mov     eax, [rbx+4Ch]
0x18002d8c8  cmp     [rbp+34h], r13d
0x18002d8cc  jz      loc_18002D9A0
0x18002d8d2  mov     edx, r14d
0x18002d8d5  mov     rcx, rdi
0x18002d8d8  call    getBit32_SB
0x18002d8dd  mov     edx, [rbx+4Ch]
0x18002d8e0  test    eax, eax
0x18002d8e2  jnz     short loc_18002D920
0x18002d8e4  lea     eax, [rdx+200h]
0x18002d8ea  mov     rcx, rdi
0x18002d8ed  mov     edx, r14d
0x18002d8f0  mov     [rbx+4Ch], eax
0x18002d8f3  call    getBit32_SB
0x18002d8f8  cmp     eax, r14d
0x18002d8fb  jnz     short loc_18002D917
0x18002d8fd  mov     r8, [rsi]
0x18002d900  lea     rcx, [rbx+60h]
0x18002d904  mov     rdx, rdi
0x18002d907  call    readQuantizerSB
0x18002d90c  movzx   eax, al
0x18002d90f  shl     eax, 5
0x18002d912  add     [rbx+4Ch], eax
0x18002d915  jmp     short loc_18002D91B
0x18002d917  add     dword ptr [rbx+4Ch], 2
0x18002d91b  mov     eax, [rbx+4Ch]
0x18002d91e  jmp     short loc_18002D933
0x18002d920  mov     ecx, edx
0x18002d922  mov     eax, edx
0x18002d924  and     ecx, 18h
0x18002d927  and     eax, r14d
0x18002d92a  lea     eax, [rax+rcx*2]
0x18002d92d  lea     eax, [rdx+rax*2]
0x18002d930  mov     [rbx+4Ch], eax
0x18002d933  cmp     dword ptr [rbp+34h], 2
0x18002d937  jz      short loc_18002D99A
0x18002d939  mov     edx, r14d
0x18002d93c  mov     rcx, rdi
0x18002d93f  call    getBit32_SB
0x18002d944  mov     edx, [rbx+4Ch]
0x18002d947  test    eax, eax
0x18002d949  jnz     short loc_18002D987
0x18002d94b  lea     eax, [rdx+400h]
0x18002d951  mov     rcx, rdi
0x18002d954  mov     edx, r14d
0x18002d957  mov     [rbx+4Ch], eax
0x18002d95a  call    getBit32_SB
0x18002d95f  cmp     eax, r14d
0x18002d962  jnz     short loc_18002D97E
0x18002d964  mov     r8, [rsi]
0x18002d967  lea     rcx, [rbx+70h]
0x18002d96b  mov     rdx, rdi
0x18002d96e  call    readQuantizerSB
0x18002d973  movzx   eax, al
0x18002d976  shl     eax, 7
0x18002d979  add     [rbx+4Ch], eax
0x18002d97c  jmp     short loc_18002D982
0x18002d97e  add     [rbx+4Ch], r12d
0x18002d982  mov     eax, [rbx+4Ch]
0x18002d985  jmp     short loc_18002D99A
0x18002d987  mov     ecx, edx
0x18002d989  mov     eax, edx
0x18002d98b  and     ecx, 60h
0x18002d98e  and     eax, 2
0x18002d991  lea     eax, [rax+rcx*2]
0x18002d994  lea     eax, [rdx+rax*2]
0x18002d997  mov     [rbx+4Ch], eax
0x18002d99a  cmp     [rbp+34h], r13d
0x18002d99e  jnz     short loc_18002D9A6
0x18002d9a0  bts     eax, 9
0x18002d9a4  jmp     short loc_18002D9B0
0x18002d9a6  cmp     dword ptr [rbp+34h], 2
0x18002d9aa  jnz     short loc_18002D9B3
0x18002d9ac  bts     eax, 0Ah
0x18002d9b0  mov     [rbx+4Ch], eax
0x18002d9b3  test    eax, 600h
0x18002d9b8  jnz     short loc_18002D9C1
0x18002d9ba  mov     ecx, 0FFFFFF98h
0x18002d9bf  jmp     short loc_18002D9C9
0x18002d9c1  xor     ecx, ecx
0x18002d9c3  mov     [rdi+0Ch], cl
0x18002d9c6  mov     [rdi+10h], ecx
0x18002d9c9  xor     eax, eax
0x18002d9cb  sub     eax, ecx
0x18002d9cd  neg     eax
0x18002d9cf  sbb     eax, eax
0x18002d9d1  add     rsp, 20h
0x18002d9d5  pop     r14
0x18002d9d7  pop     r13
0x18002d9d9  pop     r12
0x18002d9db  pop     rdi
0x18002d9dc  pop     rsi
0x18002d9dd  pop     rbp
0x18002d9de  pop     rbx
0x18002d9df  retn
```
