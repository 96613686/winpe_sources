# BinXmlString::~BinXmlString(void)

- ea: `0x18001ab4c`
- end: `0x18001ab5b`
- name: `??1BinXmlString@@QEAA@XZ`
- size: `15`
- prototype: `void __fastcall(BinXmlString *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18002ebac`
- `0x180035c60`
- `0x180039110`
- `0x1800394c0`
- `0x18003ad8e`
- `0x18003affa`

## callees

- `0x18000a100`
- `0x18001ab4c`

## pseudocode

```c
void __fastcall BinXmlString::~BinXmlString(void **this)
{
  if ( !*((_BYTE *)this + 12) )
    operator delete(*this);
}

```

## disassembly

```asm
0x18001ab4c  cmp     byte ptr [rcx+0Ch], 0
0x18001ab50  jz      short loc_18001AB53
0x18001ab52  retn
0x18001ab53  mov     rcx, [rcx]; void *
0x18001ab56  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
