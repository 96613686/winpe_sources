# ComTaskHost::SetOutput(ushort *)

- ea: `0x140009de0`
- end: `0x140009de6`
- name: `?SetOutput@ComTaskHost@@UEAAJPEAG@Z`
- size: `6`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ComTaskHost::SetOutput(ComTaskHost *this, unsigned __int16 *a2)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x140009de0  mov     eax, 80004001h
0x140009de5  retn
```
