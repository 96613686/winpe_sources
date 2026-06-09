# CWpnIdleTaskHandlerFactory::LockServer(int)

- ea: `0x180006130`
- end: `0x180006147`
- name: `?LockServer@CWpnIdleTaskHandlerFactory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandlerFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006130`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandlerFactory::LockServer(CWpnIdleTaskHandlerFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&g_Count);
  else
    _InterlockedDecrement(&g_Count);
  return 0;
}

```

## disassembly

```asm
0x180006130  test    edx, edx
0x180006132  jz      short loc_18000613D
0x180006134  lock inc cs:?g_Count@@3JA; long g_Count
0x18000613b  jmp     short loc_180006144
0x18000613d  lock dec cs:?g_Count@@3JA; long g_Count
0x180006144  xor     eax, eax
0x180006146  retn
```
