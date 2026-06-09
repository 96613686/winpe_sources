# writeTileHeaderLP

- ea: `0x180042a84`
- end: `0x180042c7e`
- name: `writeTileHeaderLP`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004db8`

## callees

- `0x1800026ac`
- `0x1800028f4`
- `0x180003830`
- `0x18001190c`
- `0x180011ab4`
- `0x1800353cc`
- `0x18003e798`
- `0x180042a84`

## pseudocode

```c
__int64 __fastcall writeTileHeaderLP(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 i; // rbp
  __int64 v5; // rsi
  char v6; // al
  unsigned __int8 v7; // r9
  __int64 v8; // rdx
  char v9; // r8
  unsigned __int8 v10; // cl
  char v11; // cl
  unsigned __int8 j; // r15
  int v13; // r8d

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
      if ( (unsigned int)allocateQuantizer(
                           (_QWORD *)(v5 + 128),
                           *(_QWORD *)(v3 + 34240),
                           *(unsigned __int8 *)(v5 + 384)) )
        return 0xFFFFFFFFLL;
      if ( *(_DWORD *)(v5 + 388) == 1 )
      {
        useDCQuantizer(v3, *(_QWORD *)(v3 + 34392));
      }
      else
      {
        putBit16z(a2, (*(_BYTE *)(v5 + 384) - 1) & 0xF, 4);
        v6 = dquantBits(*(_BYTE *)(v5 + 384));
        v7 = 0;
        for ( *(_BYTE *)(v5 + 386) = v6;
              (unsigned __int64)v7 < *(_QWORD *)(v3 + 34240);
              *(_BYTE *)(*(_QWORD *)(v5 + 8 * v8 + 128) + 40LL) = v11 )
        {
          v8 = v7;
          v9 = 2;
          v10 = *(_BYTE *)(v7 + v3 + 34304);
          **(_BYTE **)(v5 + 8LL * v7 + 128) = v10;
          if ( v10 >= 0x12u )
            v9 = v10 - 16;
          *(_BYTE *)(*(_QWORD *)(v5 + 8LL * v7 + 128) + 20LL) = v9;
          if ( v10 <= 0xEEu )
            v11 = v10 + 16;
          else
            v11 = -1;
          ++v7;
        }
        for ( j = 0; j < *(_BYTE *)(v5 + 384); ++j )
        {
          *(_BYTE *)(j + v5 + 397) = 2;
          formatQuantizer((__int64 *)(v5 + 128), 2, *(_QWORD *)(v3 + 34240), j, 1, *(_DWORD *)(v3 + 34224));
          LOBYTE(v13) = *(_BYTE *)(j + v5 + 397);
          writeQuantizer(v5 + 128, a2, v13, *(_QWORD *)(v3 + 34240), j);
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
0x180042a84  push    rbx
0x180042a86  push    rbp
0x180042a87  push    rsi
0x180042a88  push    rdi
0x180042a89  push    r12
0x180042a8b  push    r14
0x180042a8d  push    r15
0x180042a8f  sub     rsp, 30h
0x180042a93  mov     rax, [rcx+8B50h]
0x180042a9a  mov     r12, rdx
0x180042a9d  neg     rax
0x180042aa0  mov     rdi, rcx
0x180042aa3  sbb     rbp, rbp
0x180042aa6  neg     rbp
0x180042aa9  inc     rbp
0x180042aac  test    rbp, rbp
0x180042aaf  jz      loc_180042C6C
0x180042ab5  cmp     dword ptr [rdi+0BCh], 3
0x180042abc  jz      loc_180042C58
0x180042ac2  test    byte ptr [rdi+85ECh], 2
0x180042ac9  jz      loc_180042C58
0x180042acf  imul    rsi, [rdi+8658h], 1B0h
0x180042ada  xor     edx, edx
0x180042adc  mov     rcx, r12
0x180042adf  add     rsi, [rdi+86A0h]
0x180042ae6  lea     r8d, [rdx+1]
0x180042aea  mov     dword ptr [rsi+184h], 0
0x180042af4  call    putBit16z
0x180042af9  mov     byte ptr [rsi+182h], 0
0x180042b00  lea     r14, [rsi+80h]
0x180042b07  mov     byte ptr [rsi+180h], 3
0x180042b0e  cmp     qword ptr [rdi+8650h], 0
0x180042b16  jbe     short loc_180042B20
0x180042b18  mov     rcx, r14
0x180042b1b  call    freeQuantizer
0x180042b20  movzx   r8d, byte ptr [rsi+180h]
0x180042b28  mov     rcx, r14
0x180042b2b  mov     rdx, [rdi+85C0h]
0x180042b32  call    allocateQuantizer
0x180042b37  test    eax, eax
0x180042b39  jnz     loc_180042C67
0x180042b3f  cmp     dword ptr [rsi+184h], 1
0x180042b46  jnz     short loc_180042B5C
0x180042b48  mov     rdx, [rdi+8658h]
0x180042b4f  mov     rcx, rdi
0x180042b52  call    useDCQuantizer
0x180042b57  jmp     loc_180042C58
0x180042b5c  movzx   edx, byte ptr [rsi+180h]
0x180042b63  mov     r8d, 4
0x180042b69  dec     edx
0x180042b6b  mov     rcx, r12
0x180042b6e  and     edx, 0Fh
0x180042b71  call    putBit16z
0x180042b76  mov     cl, [rsi+180h]
0x180042b7c  call    dquantBits
0x180042b81  xor     r9b, r9b
0x180042b84  mov     [rsi+182h], al
0x180042b8a  cmp     qword ptr [rdi+85C0h], 0
0x180042b92  jbe     short loc_180042BEF
0x180042b94  movzx   edx, r9b
0x180042b98  mov     r8d, 2
0x180042b9e  movzx   ecx, byte ptr [rdx+rdi+8600h]
0x180042ba6  mov     rax, [rsi+rdx*8+80h]
0x180042bae  mov     [rax], cl
0x180042bb0  cmp     cl, 12h
0x180042bb3  jb      short loc_180042BB9
0x180042bb5  lea     r8d, [rcx-10h]
0x180042bb9  mov     rax, [rsi+rdx*8+80h]
0x180042bc1  mov     [rax+14h], r8b
0x180042bc5  cmp     cl, 0EEh
0x180042bc8  jbe     short loc_180042BD1
0x180042bca  mov     ecx, 0FFh
0x180042bcf  jmp     short loc_180042BD4
0x180042bd1  add     ecx, 10h
0x180042bd4  mov     rax, [rsi+rdx*8+80h]
0x180042bdc  inc     r9b
0x180042bdf  mov     [rax+28h], cl
0x180042be2  movzx   eax, r9b
0x180042be6  cmp     rax, [rdi+85C0h]
0x180042bed  jb      short loc_180042B94
0x180042bef  xor     r15b, r15b
0x180042bf2  cmp     [rsi+180h], r15b
0x180042bf9  jbe     short loc_180042C58
0x180042bfb  movzx   ebx, r15b
0x180042bff  mov     dl, 2
0x180042c01  mov     r9d, ebx
0x180042c04  mov     rcx, r14
0x180042c07  mov     byte ptr [rbx+rsi+18Dh], 2
0x180042c0f  mov     eax, [rdi+85B0h]
0x180042c15  mov     r8, [rdi+85C0h]
0x180042c1c  mov     [rsp+68h+var_40], eax
0x180042c20  mov     dword ptr [rsp+68h+var_48], 1
0x180042c28  call    formatQuantizer
0x180042c2d  mov     r9, [rdi+85C0h]
0x180042c34  mov     rdx, r12
0x180042c37  mov     r8b, [rbx+rsi+18Dh]
0x180042c3f  mov     rcx, r14
0x180042c42  mov     [rsp+68h+var_48], rbx
0x180042c47  call    writeQuantizer
0x180042c4c  inc     r15b
0x180042c4f  cmp     r15b, [rsi+180h]
0x180042c56  jb      short loc_180042BFB
0x180042c58  mov     rdi, [rdi+8B50h]
0x180042c5f  dec     rbp
0x180042c62  jmp     loc_180042AAC
0x180042c67  or      eax, 0FFFFFFFFh
0x180042c6a  jmp     short loc_180042C6E
0x180042c6c  xor     eax, eax
0x180042c6e  add     rsp, 30h
0x180042c72  pop     r15
0x180042c74  pop     r14
0x180042c76  pop     r12
0x180042c78  pop     rdi
0x180042c79  pop     rsi
0x180042c7a  pop     rbp
0x180042c7b  pop     rbx
0x180042c7c  retn
```
