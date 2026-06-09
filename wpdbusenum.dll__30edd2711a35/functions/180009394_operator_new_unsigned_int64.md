# operator new(unsigned __int64)

- ea: `0x180009394`
- end: `0x1800093cd`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800018c0`
- `0x180002c70`
- `0x180006360`
- `0x180009388`

## callees

- `0x180009394`
- `0x18000a0de`
- `0x18000a162`

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
0x180009394  mov     [rsp+arg_0], rbx
0x180009399  push    rdi
0x18000939a  sub     rsp, 20h
0x18000939e  mov     rdi, rcx
0x1800093a1  jmp     short loc_1800093B2
0x1800093a3  mov     rcx, rdi
0x1800093a6  call    _o__callnewh_0
0x1800093ab  test    eax, eax
0x1800093ad  jz      short loc_1800093BF
0x1800093af  mov     rcx, rdi; Size
0x1800093b2  call    _o_malloc_0
0x1800093b7  mov     rbx, rax
0x1800093ba  test    rax, rax
0x1800093bd  jz      short loc_1800093A3
0x1800093bf  mov     rax, rbx
0x1800093c2  mov     rbx, [rsp+28h+arg_0]
0x1800093c7  add     rsp, 20h
0x1800093cb  pop     rdi
0x1800093cc  retn
```
