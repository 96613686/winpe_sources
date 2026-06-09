# operator new(unsigned __int64)

- ea: `0x140001264`
- end: `0x14000129d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ab54`
- `0x14000afc0`
- `0x14000fdf8`
- `0x140010c94`
- `0x14001181c`
- `0x140011c10`
- `0x140011dcc`
- `0x140012320`
- `0x14001259c`
- `0x140012818`
- `0x140012b00`
- `0x140013020`

## callees

- `0x140001264`
- `0x140001764`
- `0x140001770`

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
0x140001264  mov     [rsp+arg_0], rbx
0x140001269  push    rdi
0x14000126a  sub     rsp, 20h
0x14000126e  mov     rdi, rcx
0x140001271  jmp     short loc_140001282
0x140001273  mov     rcx, rdi; Size
0x140001276  call    _callnewh_0
0x14000127b  test    eax, eax
0x14000127d  jz      short loc_14000128F
0x14000127f  mov     rcx, rdi; Size
0x140001282  call    malloc_0
0x140001287  mov     rbx, rax
0x14000128a  test    rax, rax
0x14000128d  jz      short loc_140001273
0x14000128f  mov     rax, rbx
0x140001292  mov     rbx, [rsp+28h+arg_0]
0x140001297  add     rsp, 20h
0x14000129b  pop     rdi
0x14000129c  retn
```
