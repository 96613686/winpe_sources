# _DeleteExceptionPtr(__ExceptionPtr * const)

- ea: `0x180024358`
- end: `0x180024373`
- name: `?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z_0`
- size: `27`
- prototype: `void __fastcall(struct __ExceptionPtr *const)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025dc0`

## callees

- `0x18001b90c`
- `0x1800242b4`

## pseudocode

```c
void __fastcall _DeleteExceptionPtr(struct __ExceptionPtr *const a1)
{
  sub_18001B90C(a1);
  sub_1800242B4(a1);
}

```

## disassembly

```asm
0x180024358  push    rbx
0x18002435a  sub     rsp, 20h
0x18002435e  mov     rbx, rcx
0x180024361  call    sub_18001B90C
0x180024366  mov     rcx, rbx
0x180024369  add     rsp, 20h
0x18002436d  pop     rbx
0x18002436e  jmp     sub_1800242B4
```
