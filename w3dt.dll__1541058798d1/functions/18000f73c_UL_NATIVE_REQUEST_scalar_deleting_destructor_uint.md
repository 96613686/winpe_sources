# UL_NATIVE_REQUEST::`scalar deleting destructor'(uint)

- ea: `0x18000f73c`
- end: `0x18000f763`
- name: `??_GUL_NATIVE_REQUEST@@QEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(UL_NATIVE_REQUEST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000eef0`

## callees

- `0x18000f7f0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f754`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f754`

## pseudocode

```c
UL_NATIVE_REQUEST *__fastcall UL_NATIVE_REQUEST::`scalar deleting destructor'(UL_NATIVE_REQUEST *this)
{
  UL_NATIVE_REQUEST::~UL_NATIVE_REQUEST(this);
  ALLOC_CACHE_HANDLER::Free(UL_NATIVE_REQUEST::sm_pachNativeRequests, this);
  return this;
}

```

## disassembly

```asm
0x18000f73c  push    rbx
0x18000f73e  sub     rsp, 20h
0x18000f742  mov     rbx, rcx
0x18000f745  call    ??1UL_NATIVE_REQUEST@@QEAA@XZ; UL_NATIVE_REQUEST::~UL_NATIVE_REQUEST(void)
0x18000f74a  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000f751  mov     rdx, rbx
0x18000f754  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f75a  mov     rax, rbx
0x18000f75d  add     rsp, 20h
0x18000f761  pop     rbx
0x18000f762  retn
```
