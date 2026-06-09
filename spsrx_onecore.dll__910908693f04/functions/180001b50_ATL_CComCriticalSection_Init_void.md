# ATL::CComCriticalSection::Init(void)

- ea: `0x180001b50`
- end: `0x180001b70`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010f0`
- `0x180001360`
- `0x1800013e0`
- `0x180001470`
- `0x1800014e0`
- `0x180001780`
- `0x180004dd0`
- `0x180006b88`
- `0x18000830c`
- `0x18000858c`
- `0x18000ad18`
- `0x18000ae6c`

## callees

- `0x180001b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001b54`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180001b50  sub     rsp, 38h
0x180001b54  call    cs:__imp_InitializeCriticalSection
0x180001b5a  xor     eax, eax
0x180001b5c  mov     [rsp+38h+var_18], eax
0x180001b60  jmp     short loc_180001B6B
0x180001b62  mov     eax, 8007000Eh
0x180001b67  mov     [rsp+38h+var_18], eax
0x180001b6b  add     rsp, 38h
0x180001b6f  retn
```
