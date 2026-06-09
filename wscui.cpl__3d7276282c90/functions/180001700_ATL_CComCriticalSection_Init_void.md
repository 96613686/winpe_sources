# ATL::CComCriticalSection::Init(void)

- ea: `0x180001700`
- end: `0x180001720`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800014c0`
- `0x1800015a0`
- `0x180001620`
- `0x1800016c0`
- `0x180003960`

## callees

- `0x180001700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001704`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001704`

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
0x180001700  sub     rsp, 38h
0x180001704  call    cs:__imp_InitializeCriticalSection
0x18000170a  xor     eax, eax
0x18000170c  mov     [rsp+38h+var_18], eax
0x180001710  jmp     short loc_18000171B
0x180001712  mov     eax, 8007000Eh
0x180001717  mov     [rsp+38h+var_18], eax
0x18000171b  add     rsp, 38h
0x18000171f  retn
```
