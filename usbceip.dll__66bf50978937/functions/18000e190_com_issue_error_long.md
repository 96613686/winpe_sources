# _com_issue_error(long)

- ea: `0x18000e190`
- end: `0x18000e19a`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004344`
- `0x180007a54`
- `0x180007aa8`
- `0x18000e1a0`
- `0x18000e1c4`

## callees

- `0x18000e328`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x18000e190  sub     rsp, 28h
0x18000e194  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
