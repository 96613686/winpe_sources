# PolicyManager::GetFeatureRestrictions(void)

- ea: `0x18000a1e8`
- end: `0x18000a25f`
- name: `?GetFeatureRestrictions@PolicyManager@@SA?AW4FeatureRestrictions@@XZ`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a180`

## callees

- `0x18000a1e8`
- `0x1800a9c6c`
- `0x1800aa1b4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a210`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a210`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a24d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a24d`

## pseudocode

```c
__int64 PolicyManager::GetFeatureRestrictions()
{
  void *v0; // rbx
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF
  union _RTL_RUN_ONCE *v4; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  InitOnceBeginInitialize(&InitOnce, 0, &v2, &v3);
  v0 = v3;
  if ( !v3 )
  {
    v0 = &unk_180111690;
    LazyFeatureRestrictions::LazyFeatureRestrictions((LazyFeatureRestrictions *)&unk_180111690);
    v4 = 0;
    InitOnceComplete(&InitOnce, 0, &unk_180111690);
    tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(&v4);
  }
  return *(_QWORD *)v0;
}

```

## disassembly

```asm
0x18000a1e8  mov     rax, rsp
0x18000a1eb  push    rbx
0x18000a1ec  sub     rsp, 20h
0x18000a1f0  lea     r9, [rax+10h]; lpContext
0x18000a1f4  mov     dword ptr [rax+8], 0
0x18000a1fb  lea     r8, [rax+8]; fPending
0x18000a1ff  mov     qword ptr [rax+10h], 0
0x18000a207  xor     edx, edx; dwFlags
0x18000a209  lea     rcx, InitOnce; lpInitOnce
0x18000a210  call    cs:__imp_InitOnceBeginInitialize
0x18000a216  mov     rbx, [rsp+28h+arg_8]
0x18000a21b  test    rbx, rbx
0x18000a21e  jz      short loc_18000A229
0x18000a220  mov     rax, [rbx]
0x18000a223  add     rsp, 20h
0x18000a227  pop     rbx
0x18000a228  retn
0x18000a229  lea     rbx, unk_180111690
0x18000a230  mov     rcx, rbx; this
0x18000a233  call    ??0LazyFeatureRestrictions@@QEAA@XZ; LazyFeatureRestrictions::LazyFeatureRestrictions(void)
0x18000a238  mov     r8, rbx; lpContext
0x18000a23b  mov     [rsp+28h+arg_10], 0
0x18000a244  xor     edx, edx; dwFlags
0x18000a246  lea     rcx, InitOnce; lpInitOnce
0x18000a24d  call    cs:__imp_InitOnceComplete
0x18000a253  lea     rcx, [rsp+28h+arg_10]
0x18000a258  call    ??1_Initializer@?$_LazyImpl@VLazyFeatureRestrictions@@V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@V?$static_lazy@VLazyFeatureRestrictions@@$00V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(void)
0x18000a25d  jmp     short loc_18000A220
```
