# MULTI_WORK_ITEM::`scalar deleting destructor'(uint)

- ea: `0x18000e810`
- end: `0x18000e848`
- name: `??_GMULTI_WORK_ITEM@@UEAAPEAXI@Z`
- size: `56`
- prototype: `MULTI_WORK_ITEM *__fastcall(MULTI_WORK_ITEM *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e7cc`
- `0x18000e810`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e833`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e833`

## pseudocode

```c
MULTI_WORK_ITEM *__fastcall MULTI_WORK_ITEM::`scalar deleting destructor'(MULTI_WORK_ITEM *this, char a2)
{
  MULTI_WORK_ITEM::~MULTI_WORK_ITEM(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler, this);
  return this;
}

```

## disassembly

```asm
0x18000e810  mov     [rsp+arg_0], rbx
0x18000e815  push    rdi
0x18000e816  sub     rsp, 20h
0x18000e81a  mov     ebx, edx
0x18000e81c  mov     rdi, rcx
0x18000e81f  call    ??1MULTI_WORK_ITEM@@UEAA@XZ; MULTI_WORK_ITEM::~MULTI_WORK_ITEM(void)
0x18000e824  test    bl, 1
0x18000e827  jz      short loc_18000E83A
0x18000e829  mov     rdx, rdi
0x18000e82c  mov     rcx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000e833  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000e839  nop
0x18000e83a  mov     rax, rdi
0x18000e83d  mov     rbx, [rsp+28h+arg_0]
0x18000e842  add     rsp, 20h
0x18000e846  pop     rdi
0x18000e847  retn
```
