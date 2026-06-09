# ATL::CComCriticalSection::Init(void)

- ea: `0x18001bf1c`
- end: `0x18001bf3c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001900`
- `0x180001960`
- `0x180026810`
- `0x180033900`

## callees

- `0x18001bf1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001bf20`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001bf20`

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
0x18001bf1c  sub     rsp, 38h
0x18001bf20  call    cs:__imp_InitializeCriticalSection
0x18001bf26  xor     eax, eax
0x18001bf28  mov     [rsp+38h+var_18], eax
0x18001bf2c  jmp     short loc_18001BF37
0x18001bf2e  mov     eax, 8007000Eh
0x18001bf33  mov     [rsp+38h+var_18], eax
0x18001bf37  add     rsp, 38h
0x18001bf3b  retn
```
