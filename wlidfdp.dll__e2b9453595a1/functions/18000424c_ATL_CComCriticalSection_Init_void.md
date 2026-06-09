# ATL::CComCriticalSection::Init(void)

- ea: `0x18000424c`
- end: `0x18000426c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800020c0`
- `0x1800022b0`
- `0x180002310`
- `0x180005174`
- `0x180006074`
- `0x18000618c`
- `0x1800062b0`
- `0x18000bde0`

## callees

- `0x18000424c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004250`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004250`

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
0x18000424c  sub     rsp, 38h
0x180004250  call    cs:__imp_InitializeCriticalSection
0x180004256  xor     eax, eax
0x180004258  mov     [rsp+38h+var_18], eax
0x18000425c  jmp     short loc_180004267
0x18000425e  mov     eax, 8007000Eh
0x180004263  mov     [rsp+38h+var_18], eax
0x180004267  add     rsp, 38h
0x18000426b  retn
```
