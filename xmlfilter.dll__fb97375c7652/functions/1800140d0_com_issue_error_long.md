# _com_issue_error(long)

- ea: `0x1800140d0`
- end: `0x1800140e1`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `17`
- prototype: `void __fastcall __noreturn()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800082e0`
- `0x180008b40`

## callees

- `0x180014208`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn _com_issue_error()
{
  _com_raise_error(-2147467261, 0);
}

```

## disassembly

```asm
0x1800140d0  sub     rsp, 28h
0x1800140d4  xor     edx, edx; struct IErrorInfo *
0x1800140d6  mov     ecx, 80004003h; int
0x1800140db  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
