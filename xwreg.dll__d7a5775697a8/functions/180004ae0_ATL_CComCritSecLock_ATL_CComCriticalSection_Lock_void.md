# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x180004ae0`
- end: `0x180004afe`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003a30`
- `0x18000478c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004aec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004aec`

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
0x180004ae0  push    rbx
0x180004ae2  sub     rsp, 20h
0x180004ae6  mov     rbx, rcx
0x180004ae9  mov     rcx, [rcx]; lpCriticalSection
0x180004aec  call    cs:__imp_EnterCriticalSection
0x180004af2  xor     eax, eax
0x180004af4  mov     byte ptr [rbx+8], 1
0x180004af8  add     rsp, 20h
0x180004afc  pop     rbx
0x180004afd  retn
```
