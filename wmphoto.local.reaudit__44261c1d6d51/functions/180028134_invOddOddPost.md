# invOddOddPost

- ea: `0x180028134`
- end: `0x1800281ad`
- name: `invOddOddPost`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180027af8`
- `0x18003457c`
- `0x180034a88`
- `0x18004001c`

## pseudocode

```c
__int64 __fastcall invOddOddPost(_DWORD *a1, int *a2, _DWORD *a3, _DWORD *a4)
{
  int v5; // r10d
  int v7; // ebp
  int v8; // r9d
  int v9; // edi
  int v10; // ecx
  __int64 result; // rax
  int v12; // ecx

  v5 = *a2;
  v7 = *a1 + *a4;
  v8 = (*a3 - *a2) >> 1;
  v9 = *a1 - ((3 * (v8 + *a2 + 2)) >> 3) - (v7 >> 1);
  v10 = v8 + *a2 + ((v9 + 2 * (v9 + 1)) >> 2);
  result = (unsigned int)(((v9 + 2 * (v9 + 1)) >> 2) + *a3);
  v12 = v9 - ((v10 + 2 * (v10 + 2)) >> 3) + (v7 >> 1);
  *a1 = v12;
  *a2 = v5 + ((v9 + 2 * (v9 + 1)) >> 2);
  *a3 = result;
  *a4 = v7 - v12;
  return result;
}

```

## disassembly

```asm
0x180028134  push    rbx
0x180028136  push    rbp
0x180028137  push    rsi
0x180028138  push    rdi
0x180028139  push    r14
0x18002813b  push    r15
0x18002813d  mov     edi, [rcx]
0x18002813f  mov     rsi, rcx
0x180028142  mov     r10d, [rdx]
0x180028145  mov     r14, rdx
0x180028148  mov     ebp, [r9]
0x18002814b  mov     r15, r9
0x18002814e  mov     ebx, [r8]
0x180028151  add     ebp, edi
0x180028153  sub     ebx, r10d
0x180028156  mov     r11d, ebp
0x180028159  sar     r11d, 1
0x18002815c  mov     r9d, ebx
0x18002815f  sar     r9d, 1
0x180028162  lea     edx, [r9+r10]
0x180028166  lea     eax, [rdx+2]
0x180028169  lea     ecx, [rax+rax*2]
0x18002816c  sar     ecx, 3
0x18002816f  sub     edi, ecx
0x180028171  sub     edi, r11d
0x180028174  lea     ecx, [rdi+1]
0x180028177  lea     ecx, [rdi+rcx*2]
0x18002817a  sar     ecx, 2
0x18002817d  add     ecx, edx
0x18002817f  mov     edx, ecx
0x180028181  sub     edx, r9d
0x180028184  lea     eax, [rcx+2]
0x180028187  lea     eax, [rcx+rax*2]
0x18002818a  sar     eax, 3
0x18002818d  sub     edi, eax
0x18002818f  lea     eax, [rdx+rbx]
0x180028192  lea     ecx, [rdi+r11]
0x180028196  mov     [rsi], ecx
0x180028198  sub     ebp, ecx
0x18002819a  mov     [r14], edx
0x18002819d  mov     [r8], eax
0x1800281a0  mov     [r15], ebp
0x1800281a3  pop     r15
0x1800281a5  pop     r14
0x1800281a7  pop     rdi
0x1800281a8  pop     rsi
0x1800281a9  pop     rbp
0x1800281aa  pop     rbx
0x1800281ab  retn
```
