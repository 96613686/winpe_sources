# tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(void)

- ea: `0x14001b47c`
- end: `0x14001b49a`
- name: `??1_Initializer@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001b244`
- `0x14001e0c0`
- `0x14002d5f8`
- `0x14002e75c`
- `0x140032bdf`
- `0x140032d75`

## callees

- `0x14001b47c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001b48f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001b48f`

## pseudocode

```c
BOOL __fastcall tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(
        union _RTL_RUN_ONCE **a1)
{
  union _RTL_RUN_ONCE *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return InitOnceComplete(v1, 4u, 0);
  return result;
}

```

## disassembly

```asm
0x14001b47c  sub     rsp, 28h
0x14001b480  mov     rcx, [rcx]; lpInitOnce
0x14001b483  test    rcx, rcx
0x14001b486  jz      short loc_14001B495
0x14001b488  xor     r8d, r8d; lpContext
0x14001b48b  lea     edx, [r8+4]; dwFlags
0x14001b48f  call    cs:__imp_InitOnceComplete
0x14001b495  add     rsp, 28h
0x14001b499  retn
```
