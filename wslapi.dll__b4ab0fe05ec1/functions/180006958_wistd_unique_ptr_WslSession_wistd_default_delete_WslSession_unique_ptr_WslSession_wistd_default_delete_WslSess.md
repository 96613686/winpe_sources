# wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::~unique_ptr<WslSession,wistd::default_delete<WslSession>>(void)

- ea: `0x180006958`
- end: `0x18000695f`
- name: `??1?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@QEAA@XZ`
- size: `7`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf57`
- `0x18000bf69`
- `0x18000bf9f`
- `0x18000bfc3`

## callees

- `0x180006bd4`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::~unique_ptr<WslSession,wistd::default_delete<WslSession>>(
        __int64 a1)
{
  return wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(a1, 0);
}

```

## disassembly

```asm
0x180006958  xor     edx, edx
0x18000695a  jmp     ?reset@?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@QEAAXPEAVWslSession@@@Z; wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(WslSession *)
```
