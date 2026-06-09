# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180004274`
- end: `0x180004292`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800037c0`
- `0x18000bfd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004280`

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
0x180004274  push    rbx
0x180004276  sub     rsp, 20h
0x18000427a  mov     rbx, rcx
0x18000427d  mov     rcx, [rcx]; lpCriticalSection
0x180004280  call    cs:__imp_EnterCriticalSection
0x180004286  xor     eax, eax
0x180004288  mov     byte ptr [rbx+8], 1
0x18000428c  add     rsp, 20h
0x180004290  pop     rbx
0x180004291  retn
```
