# writeTileHeaderDC

- ea: `0x180032cb4`
- end: `0x180032e06`
- name: `writeTileHeaderDC`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004db8`

## callees

- `0x1800028f4`
- `0x18001190c`
- `0x180011ab4`
- `0x180032cb4`

## pseudocode

```c
__int64 __fastcall writeTileHeaderDC(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 i; // rdi
  __int64 v5; // r14
  unsigned __int64 j; // rsi
  unsigned __int64 v7; // r8
  unsigned __int64 k; // rdx
  _BYTE *v9; // rcx
  char v10; // al
  unsigned __int64 v11; // r9
  unsigned __int64 m; // rdx
  __int64 v13; // rcx

  v3 = a1;
  for ( i = (*(_QWORD *)(a1 + 35664) != 0) + 1LL; i; --i )
  {
    if ( (*(_BYTE *)(v3 + 34284) & 1) != 0 )
    {
      v5 = *(_QWORD *)(v3 + 34464) + 432LL * *(_QWORD *)(v3 + 34392);
      *(_BYTE *)(v5 + 396) = 2;
      if ( !(*(_QWORD *)(v3 + 34392) + *(_QWORD *)(v3 + 34384)) )
      {
        for ( j = 0; j <= *(unsigned int *)(v3 + 216); ++j )
        {
          if ( (unsigned int)allocateQuantizer(
                               (_QWORD *)(*(_QWORD *)(v3 + 34464) + 432 * j),
                               *(_QWORD *)(v3 + 34240),
                               1u) )
            return 0xFFFFFFFFLL;
        }
      }
      v7 = *(_QWORD *)(v3 + 34240);
      for ( k = 0; k < v7; v7 = *(_QWORD *)(v3 + 34240) )
      {
        v9 = *(_BYTE **)(v5 + 8 * k);
        v10 = *(_BYTE *)(v3 + k++ + 34288);
        *v9 = v10;
      }
      formatQuantizer((__int64 *)v5, *(_BYTE *)(v5 + 396), v7, 0, 1, *(_DWORD *)(v3 + 34224));
      v11 = *(_QWORD *)(v3 + 34240);
      for ( m = 0; m < v11; v11 = *(_QWORD *)(v3 + 34240) )
      {
        v13 = *(_QWORD *)(v5 + 8 * m++);
        *(_DWORD *)(v13 + 8) = *(int *)(v13 + 4) >> 1;
      }
      writeQuantizer((_QWORD *)v5, a2, *(_BYTE *)(v5 + 396), v11, 0);
    }
    v3 = *(_QWORD *)(v3 + 35664);
  }
  return 0;
}

```

## disassembly

```asm
0x180032cb4  push    rbx
0x180032cb6  push    rbp
0x180032cb7  push    rsi
0x180032cb8  push    rdi
0x180032cb9  push    r14
0x180032cbb  sub     rsp, 30h
0x180032cbf  mov     rax, [rcx+8B50h]
0x180032cc6  mov     rbp, rdx
0x180032cc9  neg     rax
0x180032ccc  mov     rbx, rcx
0x180032ccf  sbb     rdi, rdi
0x180032cd2  neg     rdi
0x180032cd5  inc     rdi
0x180032cd8  test    rdi, rdi
0x180032cdb  jz      loc_180032DF8
0x180032ce1  test    byte ptr [rbx+85ECh], 1
0x180032ce8  jz      loc_180032DE4
0x180032cee  imul    r14, [rbx+8658h], 1B0h
0x180032cf9  add     r14, [rbx+86A0h]
0x180032d00  mov     byte ptr [r14+18Ch], 2
0x180032d08  mov     rax, [rbx+8650h]
0x180032d0f  add     rax, [rbx+8658h]
0x180032d16  jnz     short loc_180032D52
0x180032d18  xor     esi, esi
0x180032d1a  mov     eax, [rbx+0D8h]
0x180032d20  cmp     rsi, rax
0x180032d23  ja      short loc_180032D52
0x180032d25  mov     rdx, [rbx+85C0h]
0x180032d2c  mov     r8d, 1
0x180032d32  imul    rcx, rsi, 1B0h
0x180032d39  add     rcx, [rbx+86A0h]
0x180032d40  call    allocateQuantizer
0x180032d45  test    eax, eax
0x180032d47  jnz     loc_180032DF3
0x180032d4d  inc     rsi
0x180032d50  jmp     short loc_180032D1A
0x180032d52  mov     r8, [rbx+85C0h]
0x180032d59  xor     edx, edx
0x180032d5b  test    r8, r8
0x180032d5e  jz      short loc_180032D7C
0x180032d60  mov     rcx, [r14+rdx*8]
0x180032d64  mov     al, [rbx+rdx+85F0h]
0x180032d6b  inc     rdx
0x180032d6e  mov     [rcx], al
0x180032d70  mov     r8, [rbx+85C0h]
0x180032d77  cmp     rdx, r8
0x180032d7a  jb      short loc_180032D60
0x180032d7c  mov     eax, [rbx+85B0h]
0x180032d82  xor     r9d, r9d
0x180032d85  mov     dl, [r14+18Ch]
0x180032d8c  mov     rcx, r14
0x180032d8f  mov     [rsp+58h+var_30], eax
0x180032d93  mov     dword ptr [rsp+58h+var_38], 1
0x180032d9b  call    formatQuantizer
0x180032da0  mov     r9, [rbx+85C0h]
0x180032da7  xor     edx, edx
0x180032da9  test    r9, r9
0x180032dac  jz      short loc_180032DC9
0x180032dae  mov     rcx, [r14+rdx*8]
0x180032db2  inc     rdx
0x180032db5  mov     eax, [rcx+4]
0x180032db8  sar     eax, 1
0x180032dba  mov     [rcx+8], eax
0x180032dbd  mov     r9, [rbx+85C0h]
0x180032dc4  cmp     rdx, r9
0x180032dc7  jb      short loc_180032DAE
0x180032dc9  mov     r8b, [r14+18Ch]
0x180032dd0  mov     rdx, rbp
0x180032dd3  mov     rcx, r14
0x180032dd6  mov     [rsp+58h+var_38], 0
0x180032ddf  call    writeQuantizer
0x180032de4  mov     rbx, [rbx+8B50h]
0x180032deb  dec     rdi
0x180032dee  jmp     loc_180032CD8
0x180032df3  or      eax, 0FFFFFFFFh
0x180032df6  jmp     short loc_180032DFA
0x180032df8  xor     eax, eax
0x180032dfa  add     rsp, 30h
0x180032dfe  pop     r14
0x180032e00  pop     rdi
0x180032e01  pop     rsi
0x180032e02  pop     rbp
0x180032e03  pop     rbx
0x180032e04  retn
```
