# _ComTaskHost::ComTaskHost_::_1_::dtor$5

- ea: `0x14000aec0`
- end: `0x14000aece`
- name: `_ComTaskHost::ComTaskHost_::_1_::dtor$5`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000aec7`

## pseudocode

```c
void __fastcall ComTaskHost::ComTaskHost_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x14000aec0  mov     rcx, [rdx+68h]
0x14000aec7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
