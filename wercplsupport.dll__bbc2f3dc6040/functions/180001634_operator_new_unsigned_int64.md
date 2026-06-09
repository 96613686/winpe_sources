# operator new(unsigned __int64)

- ea: `0x180001634`
- end: `0x18000166d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180001b58`
- `0x180002470`
- `0x180002e70`
- `0x180006ce0`
- `0x180006fe0`
- `0x18000773c`
- `0x180008208`
- `0x180008420`
- `0x18000a650`
- `0x18000fb0c`
- `0x1800100b4`
- `0x1800102f8`
- `0x180010400`
- `0x180010c08`
- `0x180010e50`

## callees

- `0x180001634`
- `0x180001c5c`
- `0x180001c68`

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
0x180001634  mov     [rsp+arg_0], rbx
0x180001639  push    rdi
0x18000163a  sub     rsp, 20h
0x18000163e  mov     rdi, rcx
0x180001641  jmp     short loc_180001652
0x180001643  mov     rcx, rdi; Size
0x180001646  call    _callnewh_0
0x18000164b  test    eax, eax
0x18000164d  jz      short loc_18000165F
0x18000164f  mov     rcx, rdi; Size
0x180001652  call    malloc_0
0x180001657  mov     rbx, rax
0x18000165a  test    rax, rax
0x18000165d  jz      short loc_180001643
0x18000165f  mov     rax, rbx
0x180001662  mov     rbx, [rsp+28h+arg_0]
0x180001667  add     rsp, 20h
0x18000166b  pop     rdi
0x18000166c  retn
```
