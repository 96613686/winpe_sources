# operator new(unsigned __int64)

- ea: `0x180001974`
- end: `0x1800019ad`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800019b4`
- `0x180003e60`
- `0x180011860`
- `0x180013560`
- `0x1800144f0`
- `0x1800146e8`

## callees

- `0x180001974`
- `0x1800025e6`
- `0x180002654`

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
0x180001974  mov     [rsp+arg_0], rbx
0x180001979  push    rdi
0x18000197a  sub     rsp, 20h
0x18000197e  mov     rdi, rcx
0x180001981  jmp     short loc_180001992
0x180001983  mov     rcx, rdi
0x180001986  call    _o__callnewh_0
0x18000198b  test    eax, eax
0x18000198d  jz      short loc_18000199F
0x18000198f  mov     rcx, rdi; Size
0x180001992  call    _o_malloc_0
0x180001997  mov     rbx, rax
0x18000199a  test    rax, rax
0x18000199d  jz      short loc_180001983
0x18000199f  mov     rax, rbx
0x1800019a2  mov     rbx, [rsp+28h+arg_0]
0x1800019a7  add     rsp, 20h
0x1800019ab  pop     rdi
0x1800019ac  retn
```
