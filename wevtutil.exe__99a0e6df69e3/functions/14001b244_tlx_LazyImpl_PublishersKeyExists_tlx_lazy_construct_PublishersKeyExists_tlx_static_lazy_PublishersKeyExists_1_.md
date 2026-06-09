# tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get(void)

- ea: `0x14001b244`
- end: `0x14001b2cb`
- name: `?get@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAAAEAVPublishersKeyExists@@XZ`
- size: `135`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a6a0`
- `0x14000adf0`
- `0x14001e0c0`

## callees

- `0x14001b244`
- `0x14001b47c`
- `0x14002a814`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001b2ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001b2ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001b277`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001b277`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get(
        __int64 a1)
{
  __int64 *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&InitOnce, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    v3 = &InitOnce;
    v1 = &qword_140042658;
    PublishersKeyExists::PublishersKeyExists((PublishersKeyExists *)&qword_140042658);
    v3 = 0;
    InitOnceComplete(&InitOnce, 0, &qword_140042658);
    tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x14001b244  mov     rax, rsp
0x14001b247  mov     [rax+18h], rbx
0x14001b24b  mov     [rax+8], rcx
0x14001b24f  push    rsi
0x14001b250  sub     rsp, 20h
0x14001b254  mov     dword ptr [rax+8], 0
0x14001b25b  mov     qword ptr [rax+10h], 0
0x14001b263  lea     r9, [rax+10h]; lpContext
0x14001b267  lea     r8, [rax+8]; fPending
0x14001b26b  xor     edx, edx; dwFlags
0x14001b26d  lea     rsi, InitOnce
0x14001b274  mov     rcx, rsi; lpInitOnce
0x14001b277  call    cs:__imp_InitOnceBeginInitialize
0x14001b27d  mov     rbx, [rsp+28h+arg_8]
0x14001b282  test    rbx, rbx
0x14001b285  jnz     short loc_14001B2BD
0x14001b287  mov     [rsp+28h+arg_0], rsi
0x14001b28c  lea     rbx, qword_140042658
0x14001b293  mov     rcx, rbx; this
0x14001b296  call    ??0PublishersKeyExists@@QEAA@XZ; PublishersKeyExists::PublishersKeyExists(void)
0x14001b29b  mov     [rsp+28h+arg_0], 0
0x14001b2a4  mov     r8, rbx; lpContext
0x14001b2a7  xor     edx, edx; dwFlags
0x14001b2a9  mov     rcx, rsi; lpInitOnce
0x14001b2ac  call    cs:__imp_InitOnceComplete
0x14001b2b2  nop
0x14001b2b3  lea     rcx, [rsp+28h+arg_0]
0x14001b2b8  call    ??1_Initializer@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(void)
0x14001b2bd  mov     rax, rbx
0x14001b2c0  mov     rbx, [rsp+28h+arg_10]
0x14001b2c5  add     rsp, 20h
0x14001b2c9  pop     rsi
0x14001b2ca  retn
```
