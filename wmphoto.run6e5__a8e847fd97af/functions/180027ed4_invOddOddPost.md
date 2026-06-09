# invOddOddPost

- ea: `0x180027ed4`
- end: `0x180027f4c`
- name: `invOddOddPost`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180027898`
- `0x180033fcc`
- `0x1800344b8`
- `0x18003f844`

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
0x180027ed4  push    rbx
0x180027ed6  push    rbp
0x180027ed7  push    rsi
0x180027ed8  push    rdi
0x180027ed9  push    r14
0x180027edb  push    r15
0x180027edd  mov     edi, [rcx]
0x180027edf  mov     rsi, rcx
0x180027ee2  mov     r10d, [rdx]
0x180027ee5  mov     r14, rdx
0x180027ee8  mov     ebp, [r9]
0x180027eeb  mov     r15, r9
0x180027eee  mov     ebx, [r8]
0x180027ef1  add     ebp, edi
0x180027ef3  sub     ebx, r10d
0x180027ef6  mov     r11d, ebp
0x180027ef9  sar     r11d, 1
0x180027efc  mov     r9d, ebx
0x180027eff  sar     r9d, 1
0x180027f02  lea     edx, [r9+r10]
0x180027f06  lea     eax, [rdx+2]
0x180027f09  lea     ecx, [rax+rax*2]
0x180027f0c  sar     ecx, 3
0x180027f0f  sub     edi, ecx
0x180027f11  sub     edi, r11d
0x180027f14  lea     ecx, [rdi+1]
0x180027f17  lea     ecx, [rdi+rcx*2]
0x180027f1a  sar     ecx, 2
0x180027f1d  add     ecx, edx
0x180027f1f  mov     edx, ecx
0x180027f21  sub     edx, r9d
0x180027f24  lea     eax, [rcx+2]
0x180027f27  lea     eax, [rcx+rax*2]
0x180027f2a  sar     eax, 3
0x180027f2d  sub     edi, eax
0x180027f2f  lea     eax, [rdx+rbx]
0x180027f32  lea     ecx, [rdi+r11]
0x180027f36  mov     [rsi], ecx
0x180027f38  sub     ebp, ecx
0x180027f3a  mov     [r14], edx
0x180027f3d  mov     [r8], eax
0x180027f40  mov     [r15], ebp
0x180027f43  pop     r15
0x180027f45  pop     r14
0x180027f47  pop     rdi
0x180027f48  pop     rsi
0x180027f49  pop     rbp
0x180027f4a  pop     rbx
0x180027f4b  retn
```
