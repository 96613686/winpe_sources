# CXMLLogFormatter::CreateObject(void)

- ea: `0x180020560`
- end: `0x180020588`
- name: `?CreateObject@CXMLLogFormatter@@SAPEAVILogProvider@@XZ`
- size: `40`
- prototype: `struct ILogProvider *(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001144`
- `0x180020560`

## pseudocode

```c
struct ILogProvider *CXMLLogFormatter::CreateObject(void)
{
  struct ILogProvider *result; // rax

  result = (struct ILogProvider *)operator new(8u);
  if ( result )
    *(_QWORD *)result = &CXMLLogFormatter::`vftable';
  return result;
}

```

## disassembly

```asm
0x180020560  sub     rsp, 28h
0x180020564  mov     ecx, 8; Size
0x180020569  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002056e  mov     [rsp+28h+arg_0], rax
0x180020573  test    rax, rax
0x180020576  jz      short loc_180020582
0x180020578  lea     rcx, ??_7CXMLLogFormatter@@6B@; const CXMLLogFormatter::`vftable'
0x18002057f  mov     [rax], rcx
0x180020582  add     rsp, 28h
0x180020586  retn
```
