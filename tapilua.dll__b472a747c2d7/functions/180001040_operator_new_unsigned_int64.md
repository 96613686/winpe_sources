# operator new(unsigned __int64)

- ea: `0x180001040`
- end: `0x180001079`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000200c`
- `0x180002a70`
- `0x180002b40`

## callees

- `0x180001040`
- `0x180001ca2`
- `0x180001d02`

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
0x180001040  mov     [rsp+arg_0], rbx
0x180001045  push    rdi
0x180001046  sub     rsp, 20h
0x18000104a  mov     rdi, rcx
0x18000104d  jmp     short loc_18000105E
0x18000104f  mov     rcx, rdi
0x180001052  call    _o__callnewh_0
0x180001057  test    eax, eax
0x180001059  jz      short loc_18000106B
0x18000105b  mov     rcx, rdi; Size
0x18000105e  call    _o_malloc_0
0x180001063  mov     rbx, rax
0x180001066  test    rax, rax
0x180001069  jz      short loc_18000104F
0x18000106b  mov     rax, rbx
0x18000106e  mov     rbx, [rsp+28h+arg_0]
0x180001073  add     rsp, 20h
0x180001077  pop     rdi
0x180001078  retn
```
