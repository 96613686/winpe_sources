# tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(void)

- ea: `0x14002d5f8`
- end: `0x14002d67f`
- name: `?get@?$_LazyImpl@VRegistryDefaultLogFolder@@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@V?$static_lazy@VRegistryDefaultLogFolder@@$0A@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@@3@@tlx@@QEAAAEAVRegistryDefaultLogFolder@@XZ`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002d1c0`

## callees

- `0x14001b47c`
- `0x14002cc9c`
- `0x14002d5f8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14002d660`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14002d660`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14002d62b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14002d62b`

## pseudocode

```c
__int64 *__fastcall tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(
        __int64 a1)
{
  __int64 *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&stru_1400425F8, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    v3 = &stru_1400425F8;
    v1 = qword_140042600;
    RegistryDefaultLogFolder::RegistryDefaultLogFolder((RegistryDefaultLogFolder *)qword_140042600);
    v3 = 0;
    InitOnceComplete(&stru_1400425F8, 0, qword_140042600);
    tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x14002d5f8  mov     rax, rsp
0x14002d5fb  mov     [rax+18h], rbx
0x14002d5ff  mov     [rax+8], rcx
0x14002d603  push    rsi
0x14002d604  sub     rsp, 20h
0x14002d608  mov     dword ptr [rax+8], 0
0x14002d60f  mov     qword ptr [rax+10h], 0
0x14002d617  lea     r9, [rax+10h]; lpContext
0x14002d61b  lea     r8, [rax+8]; fPending
0x14002d61f  xor     edx, edx; dwFlags
0x14002d621  lea     rsi, stru_1400425F8
0x14002d628  mov     rcx, rsi; lpInitOnce
0x14002d62b  call    cs:__imp_InitOnceBeginInitialize
0x14002d631  mov     rbx, [rsp+28h+arg_8]
0x14002d636  test    rbx, rbx
0x14002d639  jnz     short loc_14002D671
0x14002d63b  mov     [rsp+28h+arg_0], rsi
0x14002d640  lea     rbx, qword_140042600
0x14002d647  mov     rcx, rbx; this
0x14002d64a  call    ??0RegistryDefaultLogFolder@@QEAA@XZ; RegistryDefaultLogFolder::RegistryDefaultLogFolder(void)
0x14002d64f  mov     [rsp+28h+arg_0], 0
0x14002d658  mov     r8, rbx; lpContext
0x14002d65b  xor     edx, edx; dwFlags
0x14002d65d  mov     rcx, rsi; lpInitOnce
0x14002d660  call    cs:__imp_InitOnceComplete
0x14002d666  nop
0x14002d667  lea     rcx, [rsp+28h+arg_0]
0x14002d66c  call    ??1_Initializer@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(void)
0x14002d671  mov     rax, rbx
0x14002d674  mov     rbx, [rsp+28h+arg_10]
0x14002d679  add     rsp, 20h
0x14002d67d  pop     rsi
0x14002d67e  retn
```
