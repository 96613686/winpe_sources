# CopySamples

- ea: `0x180079c5c`
- end: `0x180079caf`
- name: `CopySamples`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007b490`

## callees

- `0x180016ac1`
- `0x180079c5c`

## pseudocode

```c
void *__fastcall CopySamples(unsigned int a1, int a2, float a3, void *a4, void *Src, unsigned int a6)
{
  unsigned int v6; // ecx
  __int64 i; // rdx
  void *result; // rax

  if ( !a2 )
    return memcpy_0(a4, Src, 4 * a6 * (unsigned __int64)a1);
  v6 = a6 * a1;
  for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    *((float *)a4 + i) = a3 * *((float *)Src + i);
  return result;
}

```

## disassembly

```asm
0x180079c5c  sub     rsp, 28h
0x180079c60  test    edx, edx
0x180079c62  jz      short loc_180079C8E
0x180079c64  imul    ecx, [rsp+28h+arg_28]
0x180079c69  xor     edx, edx
0x180079c6b  mov     r8, [rsp+28h+Src]
0x180079c70  test    ecx, ecx
0x180079c72  jz      short loc_180079CAA
0x180079c74  movaps  xmm0, xmm2
0x180079c77  mulss   xmm0, dword ptr [r8+rdx*4]
0x180079c7d  movss   dword ptr [r9+rdx*4], xmm0
0x180079c83  inc     edx
0x180079c85  cmp     edx, ecx
0x180079c87  jb      short loc_180079C74
0x180079c89  add     rsp, 28h
0x180079c8d  retn
0x180079c8e  mov     eax, [rsp+28h+arg_28]
0x180079c92  mov     rdx, [rsp+28h+Src]; Src
0x180079c97  mov     r8d, ecx
0x180079c9a  mov     rcx, r9; void *
0x180079c9d  imul    r8, rax
0x180079ca1  shl     r8, 2; Size
0x180079ca5  call    memcpy_0
0x180079caa  add     rsp, 28h
0x180079cae  retn
```
