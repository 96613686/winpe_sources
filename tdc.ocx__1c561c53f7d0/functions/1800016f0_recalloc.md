# _recalloc

- ea: `0x1800016f0`
- end: `0x180001744`
- name: `_recalloc`
- size: `84`
- prototype: `void *__cdecl(void *Block, size_t Count, size_t Size)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002108`
- `0x180002d38`
- `0x18000f1e8`

## callees

- `0x1800016f0`
- `0x180001e13`
- `0x180001e20`
- `0x180001f17`

## pseudocode

```c
void *__cdecl recalloc(void *Block, size_t Count, size_t Size)
{
  if ( Count && 0xFFFFFFFFFFFFFFE0uLL / Count < Size )
  {
    *errno_0() = 12;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  return realloc_0(Block, Size * Count);
}

```

## disassembly

```asm
0x1800016f0  sub     rsp, 38h
0x1800016f4  mov     r9, rdx
0x1800016f7  test    rdx, rdx
0x1800016fa  jz      short loc_180001734
0x1800016fc  xor     edx, edx
0x1800016fe  lea     rax, [rdx-20h]
0x180001702  div     r9
0x180001705  cmp     rax, r8
0x180001708  jnb     short loc_180001734
0x18000170a  call    _errno_0
0x18000170f  xor     r9d, r9d; LineNo
0x180001712  mov     [rsp+38h+Reserved], 0; Reserved
0x18000171b  xor     r8d, r8d; FileName
0x18000171e  xor     edx, edx; FunctionName
0x180001720  xor     ecx, ecx; Expression
0x180001722  mov     dword ptr [rax], 0Ch
0x180001728  call    _invalid_parameter
0x18000172d  xor     eax, eax
0x18000172f  add     rsp, 38h
0x180001733  retn
0x180001734  imul    r9, r8
0x180001738  mov     rdx, r9; Size
0x18000173b  add     rsp, 38h
0x18000173f  jmp     realloc_0
```
