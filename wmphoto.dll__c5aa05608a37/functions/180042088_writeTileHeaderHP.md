# writeTileHeaderHP

- ea: `0x180042088`
- end: `0x18004228d`
- name: `writeTileHeaderHP`
- size: `517`
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
- `0x180034d3c`
- `0x18003dfe0`
- `0x180042088`

## pseudocode

```c
__int64 __fastcall writeTileHeaderHP(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 i; // rbp
  __int64 v5; // rsi
  __int64 v6; // rcx
  char v7; // al
  __int64 v8; // rdx
  unsigned __int8 v9; // r9
  char v10; // r8
  unsigned __int8 v11; // cl
  char v12; // cl
  unsigned __int8 j; // r15
  int v14; // r8d

  v3 = a1;
  for ( i = (*(_QWORD *)(a1 + 35664) != 0) + 1LL; i; --i )
  {
    if ( (unsigned int)(*(_DWORD *)(v3 + 188) - 2) > 1 && (*(_BYTE *)(v3 + 34284) & 4) != 0 )
    {
      v5 = *(_QWORD *)(v3 + 34464) + 432LL * *(_QWORD *)(v3 + 34392);
      *(_DWORD *)(v5 + 392) = 0;
      putBit16z(a2, 0, 1);
      *(_BYTE *)(v5 + 387) = 0;
      *(_BYTE *)(v5 + 385) = 3;
      if ( *(_QWORD *)(v3 + 34384) )
        freeQuantizer(v5 + 256);
      if ( (unsigned int)allocateQuantizer(v5 + 256, *(_QWORD *)(v3 + 34240), *(unsigned __int8 *)(v5 + 385)) )
        return 0xFFFFFFFFLL;
      if ( *(_DWORD *)(v5 + 392) == 1 )
      {
        useLPQuantizer(v3, *(unsigned __int8 *)(v5 + 385), *(_QWORD *)(v3 + 34392));
      }
      else
      {
        putBit16z(a2, (*(_BYTE *)(v5 + 385) - 1) & 0xF, 4);
        LOBYTE(v6) = *(_BYTE *)(v5 + 385);
        v7 = dquantBits(v6);
        v9 = 0;
        for ( *(_BYTE *)(v5 + 387) = v7;
              (unsigned __int64)v9 < *(_QWORD *)(v3 + 34240);
              *(_BYTE *)(*(_QWORD *)(v5 + 8 * v8 + 256) + 40LL) = v12 )
        {
          v8 = v9;
          v10 = 2;
          v11 = *(_BYTE *)(v9 + v3 + 34320);
          **(_BYTE **)(v5 + 8LL * v9 + 256) = v11;
          if ( v11 >= 0x12u )
            v10 = v11 - 16;
          *(_BYTE *)(*(_QWORD *)(v5 + 8LL * v9 + 256) + 20LL) = v10;
          if ( v11 <= 0xEEu )
            v12 = v11 + 16;
          else
            v12 = -1;
          ++v9;
        }
        for ( j = 0; j < *(_BYTE *)(v5 + 385); ++j )
        {
          LOBYTE(v8) = 2;
          *(_BYTE *)(j + v5 + 413) = 2;
          formatQuantizer(v5 + 256, v8, *(_QWORD *)(v3 + 34240), j, 0, *(_DWORD *)(v3 + 34224));
          LOBYTE(v14) = *(_BYTE *)(j + v5 + 413);
          writeQuantizer(v5 + 256, a2, v14, *(_QWORD *)(v3 + 34240), j);
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
0x180042088  push    rbx
0x18004208a  push    rbp
0x18004208b  push    rsi
0x18004208c  push    rdi
0x18004208d  push    r12
0x18004208f  push    r14
0x180042091  push    r15
0x180042093  sub     rsp, 30h
0x180042097  mov     rax, [rcx+8B50h]
0x18004209e  mov     r12, rdx
0x1800420a1  neg     rax
0x1800420a4  mov     rdi, rcx
0x1800420a7  sbb     rbp, rbp
0x1800420aa  neg     rbp
0x1800420ad  inc     rbp
0x1800420b0  test    rbp, rbp
0x1800420b3  jz      loc_18004227C
0x1800420b9  mov     eax, [rdi+0BCh]
0x1800420bf  sub     eax, 2
0x1800420c2  cmp     eax, 1
0x1800420c5  jbe     loc_180042268
0x1800420cb  test    byte ptr [rdi+85ECh], 4
0x1800420d2  jz      loc_180042268
0x1800420d8  imul    rsi, [rdi+8658h], 1B0h
0x1800420e3  xor     edx, edx
0x1800420e5  mov     rcx, r12
0x1800420e8  add     rsi, [rdi+86A0h]
0x1800420ef  lea     r8d, [rdx+1]
0x1800420f3  mov     dword ptr [rsi+188h], 0
0x1800420fd  call    putBit16z
0x180042102  mov     byte ptr [rsi+183h], 0
0x180042109  lea     r14, [rsi+100h]
0x180042110  mov     byte ptr [rsi+181h], 3
0x180042117  cmp     qword ptr [rdi+8650h], 0
0x18004211f  jbe     short loc_180042129
0x180042121  mov     rcx, r14
0x180042124  call    freeQuantizer
0x180042129  movzx   r8d, byte ptr [rsi+181h]
0x180042131  mov     rcx, r14
0x180042134  mov     rdx, [rdi+85C0h]
0x18004213b  call    allocateQuantizer
0x180042140  test    eax, eax
0x180042142  jnz     loc_180042277
0x180042148  cmp     dword ptr [rsi+188h], 1
0x18004214f  jnz     short loc_18004216C
0x180042151  movzx   edx, byte ptr [rsi+181h]
0x180042158  mov     rcx, rdi
0x18004215b  mov     r8, [rdi+8658h]
0x180042162  call    useLPQuantizer
0x180042167  jmp     loc_180042268
0x18004216c  movzx   edx, byte ptr [rsi+181h]
0x180042173  mov     r8d, 4
0x180042179  dec     edx
0x18004217b  mov     rcx, r12
0x18004217e  and     edx, 0Fh
0x180042181  call    putBit16z
0x180042186  mov     cl, [rsi+181h]
0x18004218c  call    dquantBits
0x180042191  xor     r9b, r9b
0x180042194  mov     [rsi+183h], al
0x18004219a  cmp     qword ptr [rdi+85C0h], 0
0x1800421a2  jbe     short loc_1800421FF
0x1800421a4  movzx   edx, r9b
0x1800421a8  mov     r8d, 2
0x1800421ae  movzx   ecx, byte ptr [rdx+rdi+8610h]
0x1800421b6  mov     rax, [rsi+rdx*8+100h]
0x1800421be  mov     [rax], cl
0x1800421c0  cmp     cl, 12h
0x1800421c3  jb      short loc_1800421C9
0x1800421c5  lea     r8d, [rcx-10h]
0x1800421c9  mov     rax, [rsi+rdx*8+100h]
0x1800421d1  mov     [rax+14h], r8b
0x1800421d5  cmp     cl, 0EEh
0x1800421d8  jbe     short loc_1800421E1
0x1800421da  mov     ecx, 0FFh
0x1800421df  jmp     short loc_1800421E4
0x1800421e1  add     ecx, 10h
0x1800421e4  mov     rax, [rsi+rdx*8+100h]
0x1800421ec  inc     r9b
0x1800421ef  mov     [rax+28h], cl
0x1800421f2  movzx   eax, r9b
0x1800421f6  cmp     rax, [rdi+85C0h]
0x1800421fd  jb      short loc_1800421A4
0x1800421ff  xor     r15b, r15b
0x180042202  cmp     [rsi+181h], r15b
0x180042209  jbe     short loc_180042268
0x18004220b  movzx   ebx, r15b
0x18004220f  mov     dl, 2
0x180042211  mov     r9d, ebx
0x180042214  mov     rcx, r14
0x180042217  mov     byte ptr [rbx+rsi+19Dh], 2
0x18004221f  mov     eax, [rdi+85B0h]
0x180042225  mov     r8, [rdi+85C0h]
0x18004222c  mov     [rsp+68h+var_40], eax
0x180042230  mov     dword ptr [rsp+68h+var_48], 0
0x180042238  call    formatQuantizer
0x18004223d  mov     r9, [rdi+85C0h]
0x180042244  mov     rdx, r12
0x180042247  mov     r8b, [rbx+rsi+19Dh]
0x18004224f  mov     rcx, r14
0x180042252  mov     [rsp+68h+var_48], rbx
0x180042257  call    writeQuantizer
0x18004225c  inc     r15b
0x18004225f  cmp     r15b, [rsi+181h]
0x180042266  jb      short loc_18004220B
0x180042268  mov     rdi, [rdi+8B50h]
0x18004226f  dec     rbp
0x180042272  jmp     loc_1800420B0
0x180042277  or      eax, 0FFFFFFFFh
0x18004227a  jmp     short loc_18004227E
0x18004227c  xor     eax, eax
0x18004227e  add     rsp, 30h
0x180042282  pop     r15
0x180042284  pop     r14
0x180042286  pop     r12
0x180042288  pop     rdi
0x180042289  pop     rsi
0x18004228a  pop     rbp
0x18004228b  pop     rbx
0x18004228c  retn
```
