# writeTileHeaderDC

- ea: `0x180032738`
- end: `0x180032889`
- name: `writeTileHeaderDC`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d10`

## callees

- `0x18000285c`
- `0x180011738`
- `0x1800118d8`
- `0x180032738`

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
      LOBYTE(k) = *(_BYTE *)(v5 + 396);
      formatQuantizer(v5, k, v7, 0, 1, *(_DWORD *)(v3 + 34224));
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
0x180032738  push    rbx
0x18003273a  push    rbp
0x18003273b  push    rsi
0x18003273c  push    rdi
0x18003273d  push    r14
0x18003273f  sub     rsp, 30h
0x180032743  mov     rax, [rcx+8B50h]
0x18003274a  mov     rbp, rdx
0x18003274d  neg     rax
0x180032750  mov     rbx, rcx
0x180032753  sbb     rdi, rdi
0x180032756  neg     rdi
0x180032759  inc     rdi
0x18003275c  test    rdi, rdi
0x18003275f  jz      loc_18003287C
0x180032765  test    byte ptr [rbx+85ECh], 1
0x18003276c  jz      loc_180032868
0x180032772  imul    r14, [rbx+8658h], 1B0h
0x18003277d  add     r14, [rbx+86A0h]
0x180032784  mov     byte ptr [r14+18Ch], 2
0x18003278c  mov     rax, [rbx+8650h]
0x180032793  add     rax, [rbx+8658h]
0x18003279a  jnz     short loc_1800327D6
0x18003279c  xor     esi, esi
0x18003279e  mov     eax, [rbx+0D8h]
0x1800327a4  cmp     rsi, rax
0x1800327a7  ja      short loc_1800327D6
0x1800327a9  mov     rdx, [rbx+85C0h]
0x1800327b0  mov     r8d, 1
0x1800327b6  imul    rcx, rsi, 1B0h
0x1800327bd  add     rcx, [rbx+86A0h]
0x1800327c4  call    allocateQuantizer
0x1800327c9  test    eax, eax
0x1800327cb  jnz     loc_180032877
0x1800327d1  inc     rsi
0x1800327d4  jmp     short loc_18003279E
0x1800327d6  mov     r8, [rbx+85C0h]
0x1800327dd  xor     edx, edx
0x1800327df  test    r8, r8
0x1800327e2  jz      short loc_180032800
0x1800327e4  mov     rcx, [r14+rdx*8]
0x1800327e8  mov     al, [rbx+rdx+85F0h]
0x1800327ef  inc     rdx
0x1800327f2  mov     [rcx], al
0x1800327f4  mov     r8, [rbx+85C0h]
0x1800327fb  cmp     rdx, r8
0x1800327fe  jb      short loc_1800327E4
0x180032800  mov     eax, [rbx+85B0h]
0x180032806  xor     r9d, r9d
0x180032809  mov     dl, [r14+18Ch]
0x180032810  mov     rcx, r14
0x180032813  mov     [rsp+58h+var_30], eax
0x180032817  mov     dword ptr [rsp+58h+var_38], 1
0x18003281f  call    formatQuantizer
0x180032824  mov     r9, [rbx+85C0h]
0x18003282b  xor     edx, edx
0x18003282d  test    r9, r9
0x180032830  jz      short loc_18003284D
0x180032832  mov     rcx, [r14+rdx*8]
0x180032836  inc     rdx
0x180032839  mov     eax, [rcx+4]
0x18003283c  sar     eax, 1
0x18003283e  mov     [rcx+8], eax
0x180032841  mov     r9, [rbx+85C0h]
0x180032848  cmp     rdx, r9
0x18003284b  jb      short loc_180032832
0x18003284d  mov     r8b, [r14+18Ch]
0x180032854  mov     rdx, rbp
0x180032857  mov     rcx, r14
0x18003285a  mov     [rsp+58h+var_38], 0
0x180032863  call    writeQuantizer
0x180032868  mov     rbx, [rbx+8B50h]
0x18003286f  dec     rdi
0x180032872  jmp     loc_18003275C
0x180032877  or      eax, 0FFFFFFFFh
0x18003287a  jmp     short loc_18003287E
0x18003287c  xor     eax, eax
0x18003287e  add     rsp, 30h
0x180032882  pop     r14
0x180032884  pop     rdi
0x180032885  pop     rsi
0x180032886  pop     rbp
0x180032887  pop     rbx
0x180032888  retn
```
