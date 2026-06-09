# operator new(unsigned __int64)

- ea: `0x180001300`
- end: `0x180001339`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180001dec`
- `0x180004590`
- `0x1800047f0`
- `0x180004bfc`
- `0x1800056a0`
- `0x180006c30`
- `0x180011c80`

## callees

- `0x180001300`
- `0x1800018e1`
- `0x1800018ed`

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
0x180001300  mov     [rsp+arg_0], rbx
0x180001305  push    rdi
0x180001306  sub     rsp, 20h
0x18000130a  mov     rdi, rcx
0x18000130d  jmp     short loc_18000131E
0x18000130f  mov     rcx, rdi; Size
0x180001312  call    _callnewh_0
0x180001317  test    eax, eax
0x180001319  jz      short loc_18000132B
0x18000131b  mov     rcx, rdi; Size
0x18000131e  call    malloc_0
0x180001323  mov     rbx, rax
0x180001326  test    rax, rax
0x180001329  jz      short loc_18000130F
0x18000132b  mov     rax, rbx
0x18000132e  mov     rbx, [rsp+28h+arg_0]
0x180001333  add     rsp, 20h
0x180001337  pop     rdi
0x180001338  retn
```
