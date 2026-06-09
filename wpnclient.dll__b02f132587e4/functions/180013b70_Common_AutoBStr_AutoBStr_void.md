# Common::AutoBStr::~AutoBStr(void)

- ea: `0x180013b70`
- end: `0x180013b7a`
- name: `??1AutoBStr@Common@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Common::AutoBStr *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800308f0`
- `0x180030a70`
- `0x180030a90`
- `0x180030b20`
- `0x180030b40`
- `0x180030c00`
- `0x180030fb0`
- `0x180030fd0`
- `0x180031002`
- `0x180031020`
- `0x180031040`
- `0x180031100`
- `0x180031120`
- `0x180031c59`
- `0x180031c6b`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180013b73`

## pseudocode

```c
void __fastcall Common::AutoBStr::~AutoBStr(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180013b70  mov     rcx, [rcx]
0x180013b73  jmp     cs:__imp_SysFreeString
```
