# Mem_Alloc

- ea: `0x1800164a0`
- end: `0x1800164d7`
- name: `Mem_Alloc`
- size: `55`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f298`
- `0x18001009c`
- `0x180010b90`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800121e4`
- `0x180012a18`
- `0x1800132ac`
- `0x180013dac`
- `0x18001400c`
- `0x1800156e8`
- `0x180016770`
- `0x180016f54`
- `0x180017694`
- `0x18001a6c4`
- `0x18001cb94`
- `0x18001cc74`
- `0x18001d5f8`
- `0x18001dc84`
- `0x180027c1c`
- `0x180027dd8`
- `0x1800281d0`
- `0x180028388`
- `0x1800285cc`
- `0x180028be8`
- `0x180028dfc`
- `0x180029228`

## callees

- `0x1800164a0`
- `0x18001e9ad`
- `0x18002a566`

## pseudocode

```c
void *__fastcall Mem_Alloc(size_t Size)
{
  void *result; // rax
  void *v3; // rbx

  result = malloc_0(Size);
  v3 = result;
  if ( result )
  {
    memset_0(result, 0, Size);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800164a0  mov     [rsp+arg_0], rbx
0x1800164a5  push    rdi
0x1800164a6  sub     rsp, 20h
0x1800164aa  mov     rdi, rcx
0x1800164ad  call    malloc_0
0x1800164b2  mov     rbx, rax
0x1800164b5  test    rax, rax
0x1800164b8  jz      short loc_1800164D5
0x1800164ba  mov     r8, rdi; Size
0x1800164bd  xor     edx, edx; Val
0x1800164bf  mov     rcx, rax; void *
0x1800164c2  call    memset_0
0x1800164c7  mov     rax, rbx
0x1800164ca  mov     rbx, [rsp+28h+arg_0]
0x1800164cf  add     rsp, 20h
0x1800164d3  pop     rdi
0x1800164d4  retn
0x1800164d5  jmp     short loc_1800164CA
```
