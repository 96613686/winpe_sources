# SclProcessSecurityBlob

- ea: `0x1800123b4`
- end: `0x18001242c`
- name: `SclProcessSecurityBlob`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c21c`
- `0x1800121d4`

## callees

- `0x1800123b4`

## pseudocode

```c
__int64 __fastcall SclProcessSecurityBlob(__int64 a1, __int64 a2, unsigned int a3, char *a4)
{
  char v6; // cl
  __int64 v7; // rdi
  __int64 v8; // r11
  char v9; // bl
  unsigned int v10; // r9d
  unsigned __int64 v11; // rdx
  int v12; // eax

  if ( a3 >= 0xC )
  {
    v7 = *(_QWORD *)(a1 + 24);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = *(_QWORD *)(v10 + a2) - *(_QWORD *)(v8 + 12);
      if ( !v11 )
        v11 = *(unsigned int *)(v10 + a2 + 8) - (unsigned __int64)*(unsigned int *)(v8 + 20);
      if ( v11 )
      {
        v12 = 1;
      }
      else
      {
        v9 = 1;
        *(_QWORD *)(v10 + a2) = *(_QWORD *)(v7 + 12);
        *(_DWORD *)(v10 + a2 + 8) = *(_DWORD *)(v7 + 20);
        v12 = 12;
      }
      v10 += v12;
    }
    while ( v10 <= a3 - 12 );
    v6 = v9;
  }
  else
  {
    v6 = 0;
  }
  *a4 = v6;
  return 0;
}

```

## disassembly

```asm
0x1800123b4  push    rbx
0x1800123b6  push    rbp
0x1800123b7  push    rsi
0x1800123b8  push    rdi
0x1800123b9  mov     rsi, r9
0x1800123bc  mov     r10, rdx
0x1800123bf  cmp     r8d, 0Ch
0x1800123c3  jnb     short loc_1800123C9
0x1800123c5  xor     ecx, ecx
0x1800123c7  jmp     short loc_180012423
0x1800123c9  mov     rdi, [rcx+18h]
0x1800123cd  lea     ebp, [r8-0Ch]
0x1800123d1  mov     r11, [rcx+10h]
0x1800123d5  xor     ecx, ecx
0x1800123d7  mov     bl, cl
0x1800123d9  mov     r9d, ecx
0x1800123dc  mov     r8d, r9d
0x1800123df  mov     rdx, [r8+r10]
0x1800123e3  sub     rdx, [r11+0Ch]
0x1800123e7  jnz     short loc_1800123F5
0x1800123e9  mov     edx, [r8+r10+8]
0x1800123ee  mov     eax, [r11+14h]
0x1800123f2  sub     rdx, rax
0x1800123f5  test    rdx, rdx
0x1800123f8  jnz     short loc_180012414
0x1800123fa  movsd   xmm0, qword ptr [rdi+0Ch]
0x1800123ff  mov     bl, 1
0x180012401  movsd   qword ptr [r8+r10], xmm0
0x180012407  mov     eax, [rdi+14h]
0x18001240a  mov     [r8+r10+8], eax
0x18001240f  lea     eax, [rdx+0Ch]
0x180012412  jmp     short loc_180012419
0x180012414  mov     eax, 1
0x180012419  add     r9d, eax
0x18001241c  cmp     r9d, ebp
0x18001241f  jbe     short loc_1800123DC
0x180012421  mov     cl, bl
0x180012423  mov     [rsi], cl
0x180012425  xor     eax, eax
0x180012427  pop     rdi
0x180012428  pop     rsi
0x180012429  pop     rbp
0x18001242a  pop     rbx
0x18001242b  retn
```
