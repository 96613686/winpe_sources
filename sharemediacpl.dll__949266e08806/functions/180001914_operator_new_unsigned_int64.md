# operator new(unsigned __int64)

- ea: `0x180001914`
- end: `0x18000194d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001960`
- `0x180003a20`
- `0x180003c30`
- `0x18000822c`
- `0x1800087c0`
- `0x18000f430`
- `0x18000f660`
- `0x180010bec`
- `0x180013248`
- `0x180014eac`
- `0x1800154d4`

## callees

- `0x180001914`
- `0x180002882`
- `0x1800028fa`

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
0x180001914  mov     [rsp+arg_0], rbx
0x180001919  push    rdi
0x18000191a  sub     rsp, 20h
0x18000191e  mov     rdi, rcx
0x180001921  jmp     short loc_180001932
0x180001923  mov     rcx, rdi
0x180001926  call    _o__callnewh_0
0x18000192b  test    eax, eax
0x18000192d  jz      short loc_18000193F
0x18000192f  mov     rcx, rdi; Size
0x180001932  call    _o_malloc_0
0x180001937  mov     rbx, rax
0x18000193a  test    rax, rax
0x18000193d  jz      short loc_180001923
0x18000193f  mov     rax, rbx
0x180001942  mov     rbx, [rsp+28h+arg_0]
0x180001947  add     rsp, 20h
0x18000194b  pop     rdi
0x18000194c  retn
```
