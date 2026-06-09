# CXMLLogFormatter::PreProcess(ILogContext *,int)

- ea: `0x1800242b0`
- end: `0x1800242c7`
- name: `?PreProcess@CXMLLogFormatter@@UEAAXPEAVILogContext@@H@Z`
- size: `23`
- prototype: `void __fastcall(CXMLLogFormatter *__hidden this, struct ILogContext *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800242b0`
- `0x180025108`

## pseudocode

```c
void __fastcall CXMLLogFormatter::PreProcess(CXMLLogFormatter *this, struct ILogContext *a2, int a3)
{
  if ( a3 )
    CXMLLogFormatter::WriteHeader((__int64)this, (__int64)a2, (__int64 *)a2);
}

```

## disassembly

```asm
0x1800242b0  sub     rsp, 28h
0x1800242b4  test    r8d, r8d
0x1800242b7  jz      short loc_1800242C1
0x1800242b9  mov     r8, rdx
0x1800242bc  call    ?WriteHeader@CXMLLogFormatter@@AEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CXMLLogFormatter::WriteHeader(void *,ILogContext *)
0x1800242c1  add     rsp, 28h
0x1800242c5  retn
```
