# operator new(unsigned __int64)

- ea: `0x140001008`
- end: `0x140001041`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140001564`
- `0x140002064`
- `0x140002310`
- `0x140005d74`
- `0x140006004`
- `0x1400067c4`
- `0x140006c88`
- `0x14000919c`
- `0x14000a568`
- `0x14000a974`
- `0x14000ab60`
- `0x14000b184`
- `0x14000b4c8`
- `0x14000c740`
- `0x14000d298`
- `0x14000d6f0`
- `0x14000e384`
- `0x14000ed84`
- `0x14000eedc`
- `0x140010710`
- `0x1400110dc`
- `0x140011954`
- `0x140012d54`
- `0x140012f20`
- `0x140013218`
- `0x14001665c`

## callees

- `0x140001008`
- `0x140001464`
- `0x140001470`

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
0x140001008  mov     [rsp+arg_0], rbx
0x14000100d  push    rdi
0x14000100e  sub     rsp, 20h
0x140001012  mov     rdi, rcx
0x140001015  jmp     short loc_140001026
0x140001017  mov     rcx, rdi; Size
0x14000101a  call    _callnewh_0
0x14000101f  test    eax, eax
0x140001021  jz      short loc_140001033
0x140001023  mov     rcx, rdi; Size
0x140001026  call    malloc_0
0x14000102b  mov     rbx, rax
0x14000102e  test    rax, rax
0x140001031  jz      short loc_140001017
0x140001033  mov     rax, rbx
0x140001036  mov     rbx, [rsp+28h+arg_0]
0x14000103b  add     rsp, 20h
0x14000103f  pop     rdi
0x140001040  retn
```
