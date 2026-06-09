# tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(void)

- ea: `0x180028bbc`
- end: `0x180028c45`
- name: `?get@?$_LazyImpl@VRegistryDefaultLogFolder@@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@V?$static_lazy@VRegistryDefaultLogFolder@@$0A@V?$lazy_construct@VRegistryDefaultLogFolder@@@tlx@@@3@@tlx@@QEAAAEAVRegistryDefaultLogFolder@@XZ`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a71c`

## callees

- `0x180028bbc`
- `0x1800aa1b4`
- `0x1800be7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028bef`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028bef`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028c32`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028c32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall tlx::_LazyImpl<RegistryDefaultLogFolder,tlx::lazy_construct<RegistryDefaultLogFolder>,tlx::static_lazy<RegistryDefaultLogFolder,0,tlx::lazy_construct<RegistryDefaultLogFolder>>>::get(
        __int64 a1)
{
  __int64 *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&stru_180111420, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    v3 = &stru_180111420;
    v1 = qword_180111428;
    RegistryDefaultLogFolder::RegistryDefaultLogFolder((RegistryDefaultLogFolder *)qword_180111428);
    v3 = 0;
    InitOnceComplete(&stru_180111420, 0, qword_180111428);
    tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180028bbc  mov     rax, rsp
0x180028bbf  mov     [rax+18h], rbx
0x180028bc3  mov     [rax+8], rcx
0x180028bc7  push    rsi
0x180028bc8  sub     rsp, 20h
0x180028bcc  mov     dword ptr [rax+8], 0
0x180028bd3  mov     qword ptr [rax+10h], 0
0x180028bdb  lea     r9, [rax+10h]; lpContext
0x180028bdf  lea     r8, [rax+8]; fPending
0x180028be3  xor     edx, edx; dwFlags
0x180028be5  lea     rsi, stru_180111420
0x180028bec  mov     rcx, rsi; lpInitOnce
0x180028bef  call    cs:__imp_InitOnceBeginInitialize
0x180028bf5  mov     rbx, [rsp+28h+arg_8]
0x180028bfa  test    rbx, rbx
0x180028bfd  jz      short loc_180028C0D
0x180028bff  mov     rax, rbx
0x180028c02  mov     rbx, [rsp+28h+arg_10]
0x180028c07  add     rsp, 20h
0x180028c0b  pop     rsi
0x180028c0c  retn
0x180028c0d  mov     [rsp+28h+arg_0], rsi
0x180028c12  lea     rbx, qword_180111428
0x180028c19  mov     rcx, rbx; this
0x180028c1c  call    ??0RegistryDefaultLogFolder@@QEAA@XZ; RegistryDefaultLogFolder::RegistryDefaultLogFolder(void)
0x180028c21  mov     [rsp+28h+arg_0], 0
0x180028c2a  mov     r8, rbx; lpContext
0x180028c2d  xor     edx, edx; dwFlags
0x180028c2f  mov     rcx, rsi; lpInitOnce
0x180028c32  call    cs:__imp_InitOnceComplete
0x180028c38  nop
0x180028c39  lea     rcx, [rsp+28h+arg_0]
0x180028c3e  call    ??1_Initializer@?$_LazyImpl@VLazyFeatureRestrictions@@V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@V?$static_lazy@VLazyFeatureRestrictions@@$00V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(void)
0x180028c43  jmp     short loc_180028BFF
```
