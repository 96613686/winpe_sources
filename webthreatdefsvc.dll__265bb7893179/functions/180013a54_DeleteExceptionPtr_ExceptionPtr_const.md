# _DeleteExceptionPtr(__ExceptionPtr * const)

- ea: `0x180013a54`
- end: `0x180013a6f`
- name: `?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z_0`
- size: `27`
- prototype: `void __fastcall(struct __ExceptionPtr *const)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001443c`

## callees

- `0x18000b3fc`
- `0x180013948`

## pseudocode

```c
void __fastcall _DeleteExceptionPtr(struct __ExceptionPtr *const a1)
{
  sub_18000B3FC(a1);
  sub_180013948(a1);
}

```

## disassembly

```asm
0x180013a54  push    rbx
0x180013a56  sub     rsp, 20h
0x180013a5a  mov     rbx, rcx
0x180013a5d  call    sub_18000B3FC
0x180013a62  mov     rcx, rbx
0x180013a65  add     rsp, 20h
0x180013a69  pop     rbx
0x180013a6a  jmp     sub_180013948
```
