# CiCreateImageHashContext

- ea: `0x180046350`
- end: `0x180046406`
- name: `CiCreateImageHashContext`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046610`

## callees

- `0x180046350`
- `0x18004c134`
- `0x18004c1ac`

## pseudocode

```c
__int64 __fastcall CiCreateImageHashContext(__int64 a1, int a2, __int64 a3, int a4, _DWORD *a5)
{
  __int16 v5; // ax
  __int64 v9; // rdi
  _DWORD *v10; // r14
  _DWORD *v11; // rcx
  int inited; // esi
  __int64 v13; // rdi
  char v15; // [rsp+50h] [rbp+8h] BYREF

  v5 = *(_WORD *)(a1 + 24);
  if ( v5 == 523 )
  {
    v9 = 168;
  }
  else
  {
    if ( v5 != 267 )
      return (unsigned int)-1073741701;
    v9 = 152;
  }
  v10 = a5;
  v11 = a5;
  *a5 = a4;
  inited = HashpInitHash(v11, &v15);
  if ( inited >= 0 )
  {
    v13 = a1 + v9;
    HashpHashBytes(v10, a3, (unsigned int)(a1 + 88 - a3));
    HashpHashBytes(v10, a1 + 92, (unsigned int)(v13 - (a1 + 92)));
    HashpHashBytes(v10, v13 + 8, (unsigned int)(a2 + a3 - (v13 + 8)));
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180046350  mov     [rsp+arg_8], rbx
0x180046355  mov     [rsp+arg_10], rbp
0x18004635a  push    rsi
0x18004635b  push    rdi
0x18004635c  push    r12
0x18004635e  push    r14
0x180046360  push    r15
0x180046362  sub     rsp, 20h
0x180046366  movzx   eax, word ptr [rcx+18h]
0x18004636a  mov     r15, rcx
0x18004636d  mov     ecx, 20Bh
0x180046372  mov     rbp, r8
0x180046375  mov     r12d, edx
0x180046378  cmp     ax, cx
0x18004637b  jnz     short loc_180046384
0x18004637d  mov     edi, 0A8h
0x180046382  jmp     short loc_180046391
0x180046384  mov     ecx, 10Bh
0x180046389  cmp     ax, cx
0x18004638c  jnz     short loc_1800463E7
0x18004638e  lea     edi, [rcx-73h]
0x180046391  mov     r14, [rsp+48h+arg_20]
0x180046396  lea     rdx, [rsp+48h+arg_0]
0x18004639b  mov     rcx, r14
0x18004639e  mov     [r14], r9d
0x1800463a1  call    HashpInitHash
0x1800463a6  mov     esi, eax
0x1800463a8  test    eax, eax
0x1800463aa  js      short loc_1800463EC
0x1800463ac  lea     r8d, [r15+58h]
0x1800463b0  mov     rdx, rbp
0x1800463b3  sub     r8d, ebp
0x1800463b6  mov     rcx, r14
0x1800463b9  add     rdi, r15
0x1800463bc  call    HashpHashBytes
0x1800463c1  lea     rdx, [r15+5Ch]
0x1800463c5  mov     r8d, edi
0x1800463c8  sub     r8d, edx
0x1800463cb  mov     rcx, r14
0x1800463ce  call    HashpHashBytes
0x1800463d3  lea     rdx, [rdi+8]
0x1800463d7  mov     rcx, r14
0x1800463da  sub     ebp, edx
0x1800463dc  lea     r8d, [r12+rbp]
0x1800463e0  call    HashpHashBytes
0x1800463e5  jmp     short loc_1800463EC
0x1800463e7  mov     esi, 0C000007Bh
0x1800463ec  mov     rbx, [rsp+48h+arg_8]
0x1800463f1  mov     eax, esi
0x1800463f3  mov     rbp, [rsp+48h+arg_10]
0x1800463f8  add     rsp, 20h
0x1800463fc  pop     r15
0x1800463fe  pop     r14
0x180046400  pop     r12
0x180046402  pop     rdi
0x180046403  pop     rsi
0x180046404  retn
```
