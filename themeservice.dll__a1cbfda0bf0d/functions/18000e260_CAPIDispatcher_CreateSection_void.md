# CAPIDispatcher::CreateSection(void)

- ea: `0x18000e260`
- end: `0x18000e266`
- name: `?CreateSection@CAPIDispatcher@@MEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CAPIDispatcher *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CAPIDispatcher::CreateSection(CAPIDispatcher *this)
{
  return 3221225474LL;
}

```

## disassembly

```asm
0x18000e260  mov     eax, 0C0000002h
0x18000e265  retn
```
