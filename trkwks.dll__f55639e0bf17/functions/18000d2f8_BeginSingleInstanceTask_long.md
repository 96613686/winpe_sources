# BeginSingleInstanceTask(long *)

- ea: `0x18000d2f8`
- end: `0x18000d312`
- name: `?BeginSingleInstanceTask@@YAHPEAJ@Z`
- size: `26`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000131c`
- `0x18000747c`
- `0x18000d268`

## callees

- `0x18000d2f8`

## pseudocode

```c
__int64 __fastcall BeginSingleInstanceTask(int *a1)
{
  if ( _InterlockedIncrement(a1) <= 1 )
    return 1;
  _InterlockedDecrement(a1);
  return 0;
}

```

## disassembly

```asm
0x18000d2f8  mov     edx, 1
0x18000d2fd  mov     eax, edx
0x18000d2ff  lock xadd [rcx], eax
0x18000d303  add     eax, edx
0x18000d305  cmp     eax, edx
0x18000d307  jle     short loc_18000D30F
0x18000d309  lock dec dword ptr [rcx]
0x18000d30c  xor     eax, eax
0x18000d30e  retn
0x18000d30f  mov     eax, edx
0x18000d311  retn
```
