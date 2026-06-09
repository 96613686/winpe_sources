# ComTaskMgrBase::InitSingleton(HINSTANCE__ *)

- ea: `0x140007170`
- end: `0x140007173`
- name: `?InitSingleton@ComTaskMgrBase@@EEAAJPEAUHINSTANCE__@@@Z`
- size: `3`
- prototype: `__int64 __fastcall(struct _exception *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007490`

## pseudocode

```c
__int64 __fastcall ComTaskMgrBase::InitSingleton(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140007170  xor     eax, eax
0x140007172  retn
```
