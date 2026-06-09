# _DeleteExceptionPtr(__ExceptionPtr * const)

- ea: `0x18001ae00`
- end: `0x18001ae1b`
- name: `?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z`
- size: `27`
- prototype: `void __fastcall(struct __ExceptionPtr *const)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ad34`
- `0x18001c828`

## pseudocode

```c
void __fastcall _DeleteExceptionPtr(struct __ExceptionPtr *const a1)
{
  sub_18001AD34();
  sub_18001C828(a1);
}

```

## disassembly

```asm
0x18001ae00  push    rbx
0x18001ae02  sub     rsp, 20h
0x18001ae06  mov     rbx, rcx
0x18001ae09  call    sub_18001AD34
0x18001ae0e  mov     rcx, rbx
0x18001ae11  add     rsp, 20h
0x18001ae15  pop     rbx
0x18001ae16  jmp     sub_18001C828
```
