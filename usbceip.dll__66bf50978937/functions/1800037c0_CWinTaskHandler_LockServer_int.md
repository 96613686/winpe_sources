# CWinTaskHandler::LockServer(int)

- ea: `0x1800037c0`
- end: `0x1800037d7`
- name: `?LockServer@CWinTaskHandler@@CAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800037b0`

## callees

- `0x1800037c0`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::LockServer(int a1)
{
  if ( a1 )
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  else
    _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  return 0;
}

```

## disassembly

```asm
0x1800037c0  test    ecx, ecx
0x1800037c2  jz      short loc_1800037CD
0x1800037c4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800037cb  jmp     short loc_1800037D4
0x1800037cd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800037d4  xor     eax, eax
0x1800037d6  retn
```
