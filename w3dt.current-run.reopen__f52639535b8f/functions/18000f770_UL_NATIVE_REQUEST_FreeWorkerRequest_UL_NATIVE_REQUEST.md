# UL_NATIVE_REQUEST::FreeWorkerRequest(UL_NATIVE_REQUEST *)

- ea: `0x18000f770`
- end: `0x18000f7e8`
- name: `?FreeWorkerRequest@UL_NATIVE_REQUEST@@SAXPEAV1@@Z`
- size: `120`
- prototype: `void __fastcall(struct UL_NATIVE_REQUEST *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ecb0`
- `0x18000eef0`

## callees

- `0x18000f770`
- `0x18000f840`
- `0x18000f8c8`

## import_xrefs

- `iisutil!?DisableFreeList@ALLOC_CACHE_HANDLER@@QEAAXXZ` at `0x18000f7e0`
- `iisutil!?DisableFreeList@ALLOC_CACHE_HANDLER@@QEAAXXZ` at `0x18000f7e0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000f7b7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000f7b7`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f7cc`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::FreeWorkerRequest(struct UL_NATIVE_REQUEST *this)
{
  if ( *((_DWORD *)g_pwpContext + 194) )
    ALLOC_CACHE_HANDLER::DisableFreeList(UL_NATIVE_REQUEST::sm_pachNativeRequests);
  if ( this )
  {
    *(_DWORD *)this = 1902473838;
    if ( *((struct UL_NATIVE_REQUEST **)this + 379) != (struct UL_NATIVE_REQUEST *)((char *)this + 3032) )
      UL_NATIVE_REQUEST::RemoveFromRequestList(this);
    UL_NATIVE_REQUEST::Cleanup(this);
    BUFFER::~BUFFER((struct UL_NATIVE_REQUEST *)((char *)this + 2960));
    ALLOC_CACHE_HANDLER::Free(UL_NATIVE_REQUEST::sm_pachNativeRequests, this);
  }
}

```

## disassembly

```asm
0x18000f770  push    rbx
0x18000f772  sub     rsp, 20h
0x18000f776  mov     rax, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18000f77d  mov     rbx, rcx
0x18000f780  cmp     dword ptr [rax+308h], 0
0x18000f787  jnz     short loc_18000F7D9
0x18000f789  test    rbx, rbx
0x18000f78c  jz      short loc_18000F7D3
0x18000f78e  lea     rax, [rbx+0BD8h]
0x18000f795  mov     dword ptr [rbx], 7165726Eh
0x18000f79b  cmp     [rax], rax
0x18000f79e  jz      short loc_18000F7A8
0x18000f7a0  mov     rcx, rbx; this
0x18000f7a3  call    ?RemoveFromRequestList@UL_NATIVE_REQUEST@@QEAAXXZ; UL_NATIVE_REQUEST::RemoveFromRequestList(void)
0x18000f7a8  mov     rcx, rbx; this
0x18000f7ab  call    ?Cleanup@UL_NATIVE_REQUEST@@AEAAXXZ; UL_NATIVE_REQUEST::Cleanup(void)
0x18000f7b0  lea     rcx, [rbx+0B90h]
0x18000f7b7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f7bd  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000f7c4  mov     rdx, rbx
0x18000f7c7  add     rsp, 20h
0x18000f7cb  pop     rbx
0x18000f7cc  jmp     cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f7d3  add     rsp, 20h
0x18000f7d7  pop     rbx
0x18000f7d8  retn
0x18000f7d9  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000f7e0  call    cs:__imp_?DisableFreeList@ALLOC_CACHE_HANDLER@@QEAAXXZ; ALLOC_CACHE_HANDLER::DisableFreeList(void)
0x18000f7e6  jmp     short loc_18000F789
```
