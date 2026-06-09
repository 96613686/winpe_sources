# operator new(unsigned __int64)

- ea: `0x1800017e0`
- end: `0x180001819`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001510`
- `0x180002110`

## callees

- `0x1800017e0`
- `0x180001d02`
- `0x180001d0e`

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
0x1800017e0  mov     [rsp+arg_0], rbx
0x1800017e5  push    rdi
0x1800017e6  sub     rsp, 20h
0x1800017ea  mov     rdi, rcx
0x1800017ed  jmp     short loc_1800017FE
0x1800017ef  mov     rcx, rdi; Size
0x1800017f2  call    _callnewh_0
0x1800017f7  test    eax, eax
0x1800017f9  jz      short loc_18000180B
0x1800017fb  mov     rcx, rdi; Size
0x1800017fe  call    malloc_0
0x180001803  mov     rbx, rax
0x180001806  test    rax, rax
0x180001809  jz      short loc_1800017EF
0x18000180b  mov     rax, rbx
0x18000180e  mov     rbx, [rsp+28h+arg_0]
0x180001813  add     rsp, 20h
0x180001817  pop     rdi
0x180001818  retn
```
