# CEventBroker::GetReadyState(long *)

- ea: `0x18000e780`
- end: `0x18000e788`
- name: `?GetReadyState@CEventBroker@@UEAAJPEAJ@Z`
- size: `8`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CEventBroker::GetReadyState(CEventBroker *this, int *a2)
{
  *a2 = *((_DWORD *)this + 12);
  return 0;
}

```

## disassembly

```asm
0x18000e780  mov     eax, [rcx+30h]
0x18000e783  mov     [rdx], eax
0x18000e785  xor     eax, eax
0x18000e787  retn
```
