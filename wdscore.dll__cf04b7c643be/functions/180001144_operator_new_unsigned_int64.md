# operator new(unsigned __int64)

- ea: `0x180001144`
- end: `0x18000117d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180001190`
- `0x1800107c4`
- `0x1800114e4`
- `0x180011578`
- `0x180013068`
- `0x18001558c`
- `0x1800188e0`
- `0x18001bb80`
- `0x18001bc90`
- `0x18001e114`
- `0x18001e9d0`
- `0x180020210`
- `0x1800202e0`
- `0x180020370`
- `0x1800203c0`
- `0x180020410`
- `0x180020490`
- `0x1800204d0`
- `0x180020520`
- `0x180020560`
- `0x1800208a0`
- `0x180021f44`
- `0x18002209c`
- `0x180022300`
- `0x180025630`
- `0x1800258fc`
- `0x180026ba0`

## callees

- `0x180001144`
- `0x180001c0e`
- `0x180001c1a`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001144  mov     [rsp+arg_0], rbx
0x180001149  push    rdi
0x18000114a  sub     rsp, 20h
0x18000114e  mov     rdi, rcx
0x180001151  jmp     short loc_180001162
0x180001153  mov     rcx, rdi; Size
0x180001156  call    _callnewh_0
0x18000115b  test    eax, eax
0x18000115d  jz      short loc_18000116F
0x18000115f  mov     rcx, rdi; Size
0x180001162  call    malloc_0
0x180001167  mov     rbx, rax
0x18000116a  test    rax, rax
0x18000116d  jz      short loc_180001153
0x18000116f  mov     rax, rbx
0x180001172  mov     rbx, [rsp+28h+arg_0]
0x180001177  add     rsp, 20h
0x18000117b  pop     rdi
0x18000117c  retn
```
