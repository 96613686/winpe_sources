# _DeleteExceptionPtr(__ExceptionPtr * const)

- ea: `0x18000a8f0`
- end: `0x18000a90b`
- name: `?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z`
- size: `27`
- prototype: `void __fastcall(struct __ExceptionPtr *const)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a824`
- `0x18000c2f8`

## pseudocode

```c
void __fastcall _DeleteExceptionPtr(struct __ExceptionPtr *const a1)
{
  sub_18000A824();
  sub_18000C2F8(a1);
}

```

## disassembly

```asm
0x18000a8f0  push    rbx
0x18000a8f2  sub     rsp, 20h
0x18000a8f6  mov     rbx, rcx
0x18000a8f9  call    sub_18000A824
0x18000a8fe  mov     rcx, rbx
0x18000a901  add     rsp, 20h
0x18000a905  pop     rbx
0x18000a906  jmp     sub_18000C2F8
```
