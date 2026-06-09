# CPxeRogueDetection::_RogueThread(void *)

- ea: `0x180010a90`
- end: `0x180010a95`
- name: `?_RogueThread@CPxeRogueDetection@@SAKPEAX@Z`
- size: `5`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ea3c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CPxeRogueDetection::_RogueThread(struct _RTL_CRITICAL_SECTION *lpThreadParameter)
{
  return CPxeRogueDetection::RogueThread(lpThreadParameter);
}

```

## disassembly

```asm
0x180010a90  jmp     ?RogueThread@CPxeRogueDetection@@QEAAKXZ; CPxeRogueDetection::RogueThread(void)
```
