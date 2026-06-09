# writeTileHeaderHP

- ea: `0x180042878`
- end: `0x180042a7e`
- name: `writeTileHeaderHP`
- size: `518`
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
- `0x180035318`
- `0x18003e798`
- `0x180042878`

## pseudocode

```c
__int64 __fastcall writeTileHeaderHP(__int64 a1, __int64 a2)
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
    if ( (unsigned int)(*(_DWORD *)(v3 + 188) - 2) > 1 && (*(_BYTE *)(v3 + 34284) & 4) != 0 )
    {
      v5 = *(_QWORD *)(v3 + 34464) + 432LL * *(_QWORD *)(v3 + 34392);
      *(_DWORD *)(v5 + 392) = 0;
      putBit16z(a2, 0, 1);
      *(_BYTE *)(v5 + 387) = 0;
      *(_BYTE *)(v5 + 385) = 3;
      if ( *(_QWORD *)(v3 + 34384) )
        freeQuantizer(v5 + 256);
      if ( (unsigned int)allocateQuantizer(
                           (_QWORD *)(v5 + 256),
                           *(_QWORD *)(v3 + 34240),
                           *(unsigned __int8 *)(v5 + 385)) )
        return 0xFFFFFFFFLL;
      if ( *(_DWORD *)(v5 + 392) == 1 )
      {
        useLPQuantizer(v3, *(unsigned __int8 *)(v5 + 385), *(_QWORD *)(v3 + 34392));
      }
      else
      {
        putBit16z(a2, (*(_BYTE *)(v5 + 385) - 1) & 0xF, 4);
        v6 = dquantBits(*(_BYTE *)(v5 + 385));
        v7 = 0;
        for ( *(_BYTE *)(v5 + 387) = v6;
              (unsigned __int64)v7 < *(_QWORD *)(v3 + 34240);
              *(_BYTE *)(*(_QWORD *)(v5 + 8 * v8 + 256) + 40LL) = v11 )
        {
          v8 = v7;
          v9 = 2;
          v10 = *(_BYTE *)(v7 + v3 + 34320);
          **(_BYTE **)(v5 + 8LL * v7 + 256) = v10;
          if ( v10 >= 0x12u )
            v9 = v10 - 16;
          *(_BYTE *)(*(_QWORD *)(v5 + 8LL * v7 + 256) + 20LL) = v9;
          if ( v10 <= 0xEEu )
            v11 = v10 + 16;
          else
            v11 = -1;
          ++v7;
        }
        for ( j = 0; j < *(_BYTE *)(v5 + 385); ++j )
        {
          *(_BYTE *)(j + v5 + 413) = 2;
          formatQuantizer((__int64 *)(v5 + 256), 2, *(_QWORD *)(v3 + 34240), j, 0, *(_DWORD *)(v3 + 34224));
          LOBYTE(v13) = *(_BYTE *)(j + v5 + 413);
          writeQuantizer(v5 + 256, a2, v13, *(_QWORD *)(v3 + 34240), j);
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
0x180042878  push    rbx
0x18004287a  push    rbp
0x18004287b  push    rsi
0x18004287c  push    rdi
0x18004287d  push    r12
0x18004287f  push    r14
0x180042881  push    r15
0x180042883  sub     rsp, 30h
0x180042887  mov     rax, [rcx+8B50h]
0x18004288e  mov     r12, rdx
0x180042891  neg     rax
0x180042894  mov     rdi, rcx
0x180042897  sbb     rbp, rbp
0x18004289a  neg     rbp
0x18004289d  inc     rbp
0x1800428a0  test    rbp, rbp
0x1800428a3  jz      loc_180042A6C
0x1800428a9  mov     eax, [rdi+0BCh]
0x1800428af  sub     eax, 2
0x1800428b2  cmp     eax, 1
0x1800428b5  jbe     loc_180042A58
0x1800428bb  test    byte ptr [rdi+85ECh], 4
0x1800428c2  jz      loc_180042A58
0x1800428c8  imul    rsi, [rdi+8658h], 1B0h
0x1800428d3  xor     edx, edx
0x1800428d5  mov     rcx, r12
0x1800428d8  add     rsi, [rdi+86A0h]
0x1800428df  lea     r8d, [rdx+1]
0x1800428e3  mov     dword ptr [rsi+188h], 0
0x1800428ed  call    putBit16z
0x1800428f2  mov     byte ptr [rsi+183h], 0
0x1800428f9  lea     r14, [rsi+100h]
0x180042900  mov     byte ptr [rsi+181h], 3
0x180042907  cmp     qword ptr [rdi+8650h], 0
0x18004290f  jbe     short loc_180042919
0x180042911  mov     rcx, r14
0x180042914  call    freeQuantizer
0x180042919  movzx   r8d, byte ptr [rsi+181h]
0x180042921  mov     rcx, r14
0x180042924  mov     rdx, [rdi+85C0h]
0x18004292b  call    allocateQuantizer
0x180042930  test    eax, eax
0x180042932  jnz     loc_180042A67
0x180042938  cmp     dword ptr [rsi+188h], 1
0x18004293f  jnz     short loc_18004295C
0x180042941  movzx   edx, byte ptr [rsi+181h]
0x180042948  mov     rcx, rdi
0x18004294b  mov     r8, [rdi+8658h]
0x180042952  call    useLPQuantizer
0x180042957  jmp     loc_180042A58
0x18004295c  movzx   edx, byte ptr [rsi+181h]
0x180042963  mov     r8d, 4
0x180042969  dec     edx
0x18004296b  mov     rcx, r12
0x18004296e  and     edx, 0Fh
0x180042971  call    putBit16z
0x180042976  mov     cl, [rsi+181h]
0x18004297c  call    dquantBits
0x180042981  xor     r9b, r9b
0x180042984  mov     [rsi+183h], al
0x18004298a  cmp     qword ptr [rdi+85C0h], 0
0x180042992  jbe     short loc_1800429EF
0x180042994  movzx   edx, r9b
0x180042998  mov     r8d, 2
0x18004299e  movzx   ecx, byte ptr [rdx+rdi+8610h]
0x1800429a6  mov     rax, [rsi+rdx*8+100h]
0x1800429ae  mov     [rax], cl
0x1800429b0  cmp     cl, 12h
0x1800429b3  jb      short loc_1800429B9
0x1800429b5  lea     r8d, [rcx-10h]
0x1800429b9  mov     rax, [rsi+rdx*8+100h]
0x1800429c1  mov     [rax+14h], r8b
0x1800429c5  cmp     cl, 0EEh
0x1800429c8  jbe     short loc_1800429D1
0x1800429ca  mov     ecx, 0FFh
0x1800429cf  jmp     short loc_1800429D4
0x1800429d1  add     ecx, 10h
0x1800429d4  mov     rax, [rsi+rdx*8+100h]
0x1800429dc  inc     r9b
0x1800429df  mov     [rax+28h], cl
0x1800429e2  movzx   eax, r9b
0x1800429e6  cmp     rax, [rdi+85C0h]
0x1800429ed  jb      short loc_180042994
0x1800429ef  xor     r15b, r15b
0x1800429f2  cmp     [rsi+181h], r15b
0x1800429f9  jbe     short loc_180042A58
0x1800429fb  movzx   ebx, r15b
0x1800429ff  mov     dl, 2
0x180042a01  mov     r9d, ebx
0x180042a04  mov     rcx, r14
0x180042a07  mov     byte ptr [rbx+rsi+19Dh], 2
0x180042a0f  mov     eax, [rdi+85B0h]
0x180042a15  mov     r8, [rdi+85C0h]
0x180042a1c  mov     [rsp+68h+var_40], eax
0x180042a20  mov     dword ptr [rsp+68h+var_48], 0
0x180042a28  call    formatQuantizer
0x180042a2d  mov     r9, [rdi+85C0h]
0x180042a34  mov     rdx, r12
0x180042a37  mov     r8b, [rbx+rsi+19Dh]
0x180042a3f  mov     rcx, r14
0x180042a42  mov     [rsp+68h+var_48], rbx
0x180042a47  call    writeQuantizer
0x180042a4c  inc     r15b
0x180042a4f  cmp     r15b, [rsi+181h]
0x180042a56  jb      short loc_1800429FB
0x180042a58  mov     rdi, [rdi+8B50h]
0x180042a5f  dec     rbp
0x180042a62  jmp     loc_1800428A0
0x180042a67  or      eax, 0FFFFFFFFh
0x180042a6a  jmp     short loc_180042A6E
0x180042a6c  xor     eax, eax
0x180042a6e  add     rsp, 30h
0x180042a72  pop     r15
0x180042a74  pop     r14
0x180042a76  pop     r12
0x180042a78  pop     rdi
0x180042a79  pop     rsi
0x180042a7a  pop     rbp
0x180042a7b  pop     rbx
0x180042a7c  retn
```
