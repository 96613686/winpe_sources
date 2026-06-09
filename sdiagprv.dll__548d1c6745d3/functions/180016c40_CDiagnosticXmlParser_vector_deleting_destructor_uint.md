# CDiagnosticXmlParser::`vector deleting destructor'(uint)

- ea: `0x180016c40`
- end: `0x180016c6f`
- name: `??_ECDiagnosticXmlParser@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CDiagnosticXmlParser *__fastcall(CDiagnosticXmlParser *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800010b4`
- `0x180016c00`
- `0x180016c40`

## pseudocode

```c
CDiagnosticXmlParser *__fastcall CDiagnosticXmlParser::`vector deleting destructor'(
        CDiagnosticXmlParser *this,
        char a2)
{
  CDiagnosticXmlParser::~CDiagnosticXmlParser(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180016c40  mov     [rsp+arg_0], rbx
0x180016c45  push    rdi
0x180016c46  sub     rsp, 20h
0x180016c4a  mov     ebx, edx
0x180016c4c  mov     rdi, rcx
0x180016c4f  call    ??1CDiagnosticXmlParser@@UEAA@XZ; CDiagnosticXmlParser::~CDiagnosticXmlParser(void)
0x180016c54  test    bl, 1
0x180016c57  jz      short loc_180016C61
0x180016c59  mov     rcx, rdi; Block
0x180016c5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c61  mov     rbx, [rsp+28h+arg_0]
0x180016c66  mov     rax, rdi
0x180016c69  add     rsp, 20h
0x180016c6d  pop     rdi
0x180016c6e  retn
```
