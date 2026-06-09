# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x18000a494`
- end: `0x18000a4b2`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004948`
- `0x180006048`
- `0x1800061e4`
- `0x180006380`
- `0x18000651c`
- `0x1800066b8`
- `0x18000af30`
- `0x18000c020`
- `0x18000d070`
- `0x18000e440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a4a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  __int64 result; // rax

  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  result = 0;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x18000a494  push    rbx
0x18000a496  sub     rsp, 20h
0x18000a49a  mov     rbx, rcx
0x18000a49d  mov     rcx, [rcx]; lpCriticalSection
0x18000a4a0  call    cs:__imp_EnterCriticalSection
0x18000a4a6  xor     eax, eax
0x18000a4a8  mov     byte ptr [rbx+8], 1
0x18000a4ac  add     rsp, 20h
0x18000a4b0  pop     rbx
0x18000a4b1  retn
```
