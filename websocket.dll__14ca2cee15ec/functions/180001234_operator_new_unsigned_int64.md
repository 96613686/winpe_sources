# operator new(unsigned __int64)

- ea: `0x180001234`
- end: `0x18000126d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045c0`
- `0x180005cb0`
- `0x1800093c4`
- `0x18000a00c`
- `0x18000a13c`
- `0x18000a438`
- `0x18000acac`
- `0x18000af30`
- `0x18000b0c8`
- `0x18000b194`
- `0x18000b438`
- `0x18000b4f4`
- `0x18000c300`
- `0x18000c7c0`
- `0x18000cc64`

## callees

- `0x180001234`
- `0x180001ef6`
- `0x180001f80`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001234  mov     [rsp+arg_0], rbx
0x180001239  push    rdi
0x18000123a  sub     rsp, 20h
0x18000123e  mov     rdi, rcx
0x180001241  jmp     short loc_180001252
0x180001243  mov     rcx, rdi
0x180001246  call    _o__callnewh_0
0x18000124b  test    eax, eax
0x18000124d  jz      short loc_18000125F
0x18000124f  mov     rcx, rdi; Size
0x180001252  call    _o_malloc_0
0x180001257  mov     rbx, rax
0x18000125a  test    rax, rax
0x18000125d  jz      short loc_180001243
0x18000125f  mov     rax, rbx
0x180001262  mov     rbx, [rsp+28h+arg_0]
0x180001267  add     rsp, 20h
0x18000126b  pop     rdi
0x18000126c  retn
```
