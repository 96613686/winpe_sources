# CXMLLogFormatter::DestroyObject(void)

- ea: `0x1800205f0`
- end: `0x18002060e`
- name: `?DestroyObject@CXMLLogFormatter@@UEAAXXZ`
- size: `30`
- prototype: `void __fastcall(CXMLLogFormatter *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001184`
- `0x1800205f0`

## pseudocode

```c
void __fastcall CXMLLogFormatter::DestroyObject(CXMLLogFormatter *this)
{
  if ( this )
  {
    *(_QWORD *)this = &CXMLLogFormatter::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800205f0  sub     rsp, 28h
0x1800205f4  test    rcx, rcx
0x1800205f7  jz      short loc_180020608
0x1800205f9  lea     rax, ??_7CXMLLogFormatter@@6B@; const CXMLLogFormatter::`vftable'
0x180020600  mov     [rcx], rax
0x180020603  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020608  add     rsp, 28h
0x18002060c  retn
```
