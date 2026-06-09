# CWpnIdleTaskHandler::Stop(long *)

- ea: `0x180006560`
- end: `0x18000656e`
- name: `?Stop@CWpnIdleTaskHandler@@UEAAJPEAJ@Z`
- size: `14`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006560`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::Stop(CWpnIdleTaskHandler *this, int *a2)
{
  if ( a2 )
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180006560  test    rdx, rdx
0x180006563  jz      short loc_18000656B
0x180006565  mov     dword ptr [rdx], 0
0x18000656b  xor     eax, eax
0x18000656d  retn
```
