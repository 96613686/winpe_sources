# CDiagnosticXmlParser::~CDiagnosticXmlParser(void)

- ea: `0x180016c00`
- end: `0x180016c36`
- name: `??1CDiagnosticXmlParser@@UEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CDiagnosticXmlParser *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016c40`

## callees

- `0x180016c00`
- `0x180019010`

## pseudocode

```c
void __fastcall CDiagnosticXmlParser::~CDiagnosticXmlParser(CDiagnosticXmlParser *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CDiagnosticXmlParser::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180016c00  push    rbx
0x180016c02  sub     rsp, 20h
0x180016c06  mov     rbx, rcx
0x180016c09  lea     rax, ??_7CDiagnosticXmlParser@@6B@; const CDiagnosticXmlParser::`vftable'
0x180016c10  mov     [rcx], rax
0x180016c13  mov     rcx, [rcx+8]
0x180016c17  test    rcx, rcx
0x180016c1a  jz      short loc_180016C30
0x180016c1c  mov     rax, [rcx]
0x180016c1f  mov     rax, [rax+10h]
0x180016c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c28  mov     qword ptr [rbx+8], 0
0x180016c30  add     rsp, 20h
0x180016c34  pop     rbx
0x180016c35  retn
```
