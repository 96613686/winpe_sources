# tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(void)

- ea: `0x14002e75c`
- end: `0x14002e7e3`
- name: `?get@?$_LazyImpl@VLazySecurityBases@@V?$lazy_construct@VLazySecurityBases@@@tlx@@V?$static_lazy@VLazySecurityBases@@$0A@V?$lazy_construct@VLazySecurityBases@@@tlx@@@3@@tlx@@QEAAAEAVLazySecurityBases@@XZ`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400151ec`

## callees

- `0x14001b47c`
- `0x14002d688`
- `0x14002e75c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14002e7c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14002e7c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14002e78f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14002e78f`

## pseudocode

```c
__int64 *__fastcall tlx::_LazyImpl<LazySecurityBases,tlx::lazy_construct<LazySecurityBases>,tlx::static_lazy<LazySecurityBases,0,tlx::lazy_construct<LazySecurityBases>>>::get(
        __int64 a1)
{
  __int64 *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&stru_140042630, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    v3 = &stru_140042630;
    v1 = qword_140042638;
    LazySecurityBases::LazySecurityBases((LazySecurityBases *)qword_140042638);
    v3 = 0;
    InitOnceComplete(&stru_140042630, 0, qword_140042638);
    tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x14002e75c  mov     rax, rsp
0x14002e75f  mov     [rax+18h], rbx
0x14002e763  mov     [rax+8], rcx
0x14002e767  push    rsi
0x14002e768  sub     rsp, 20h
0x14002e76c  mov     dword ptr [rax+8], 0
0x14002e773  mov     qword ptr [rax+10h], 0
0x14002e77b  lea     r9, [rax+10h]; lpContext
0x14002e77f  lea     r8, [rax+8]; fPending
0x14002e783  xor     edx, edx; dwFlags
0x14002e785  lea     rsi, stru_140042630
0x14002e78c  mov     rcx, rsi; lpInitOnce
0x14002e78f  call    cs:__imp_InitOnceBeginInitialize
0x14002e795  mov     rbx, [rsp+28h+arg_8]
0x14002e79a  test    rbx, rbx
0x14002e79d  jnz     short loc_14002E7D5
0x14002e79f  mov     [rsp+28h+arg_0], rsi
0x14002e7a4  lea     rbx, qword_140042638
0x14002e7ab  mov     rcx, rbx; this
0x14002e7ae  call    ??0LazySecurityBases@@QEAA@XZ; LazySecurityBases::LazySecurityBases(void)
0x14002e7b3  mov     [rsp+28h+arg_0], 0
0x14002e7bc  mov     r8, rbx; lpContext
0x14002e7bf  xor     edx, edx; dwFlags
0x14002e7c1  mov     rcx, rsi; lpInitOnce
0x14002e7c4  call    cs:__imp_InitOnceComplete
0x14002e7ca  nop
0x14002e7cb  lea     rcx, [rsp+28h+arg_0]
0x14002e7d0  call    ??1_Initializer@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(void)
0x14002e7d5  mov     rax, rbx
0x14002e7d8  mov     rbx, [rsp+28h+arg_10]
0x14002e7dd  add     rsp, 20h
0x14002e7e1  pop     rsi
0x14002e7e2  retn
```
