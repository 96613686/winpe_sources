# HTTP_LOG_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x18000d820`
- end: `0x18000d858`
- name: `??_GHTTP_LOG_CONTEXT@@EEAAPEAXI@Z`
- size: `56`
- prototype: `HTTP_LOG_CONTEXT *__fastcall(HTTP_LOG_CONTEXT *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d780`
- `0x18000d820`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000d843`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000d843`

## pseudocode

```c
HTTP_LOG_CONTEXT *__fastcall HTTP_LOG_CONTEXT::`scalar deleting destructor'(HTTP_LOG_CONTEXT *this, char a2)
{
  HTTP_LOG_CONTEXT::~HTTP_LOG_CONTEXT(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)HTTP_LOG_CONTEXT::sm_pAllocCacheHandler, this);
  return this;
}

```

## disassembly

```asm
0x18000d820  mov     [rsp+arg_0], rbx
0x18000d825  push    rdi
0x18000d826  sub     rsp, 20h
0x18000d82a  mov     ebx, edx
0x18000d82c  mov     rdi, rcx
0x18000d82f  call    ??1HTTP_LOG_CONTEXT@@EEAA@XZ; HTTP_LOG_CONTEXT::~HTTP_LOG_CONTEXT(void)
0x18000d834  test    bl, 1
0x18000d837  jz      short loc_18000D84A
0x18000d839  mov     rdx, rdi
0x18000d83c  mov     rcx, cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000d843  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000d849  nop
0x18000d84a  mov     rax, rdi
0x18000d84d  mov     rbx, [rsp+28h+arg_0]
0x18000d852  add     rsp, 20h
0x18000d856  pop     rdi
0x18000d857  retn
```
