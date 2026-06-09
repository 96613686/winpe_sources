# CWinTaskClassFactoryT<CUsbCeipTask,1>::LockServer(int)

- ea: `0x1800037b0`
- end: `0x1800037b7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@UEAAJH@Z`
- size: `7`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800037c0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CUsbCeipTask,1>::LockServer(__int64 a1, int a2)
{
  return CWinTaskHandler::LockServer(a2);
}

```

## disassembly

```asm
0x1800037b0  mov     ecx, edx; int
0x1800037b2  jmp     ?LockServer@CWinTaskHandler@@CAJH@Z; CWinTaskHandler::LockServer(int)
```
