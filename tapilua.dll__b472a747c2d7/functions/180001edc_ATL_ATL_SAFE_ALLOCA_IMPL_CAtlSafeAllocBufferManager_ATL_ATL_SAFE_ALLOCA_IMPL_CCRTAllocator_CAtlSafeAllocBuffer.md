# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)

- ea: `0x180001edc`
- end: `0x180001f04`
- name: `??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005111`
- `0x180005123`
- `0x180005159`
- `0x18000517d`

## callees

- `0x180001edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001ef0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001ef0`

## pseudocode

```c
void __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(
        _QWORD **a1)
{
  _QWORD *i; // rcx

  for ( i = *a1; i; i = *a1 )
  {
    *a1 = (_QWORD *)*i;
    free(i);
  }
}

```

## disassembly

```asm
0x180001edc  push    rbx
0x180001ede  sub     rsp, 20h
0x180001ee2  mov     rbx, rcx
0x180001ee5  mov     rcx, [rcx]
0x180001ee8  jmp     short loc_180001EF9
0x180001eea  mov     rax, [rcx]
0x180001eed  mov     [rbx], rax
0x180001ef0  call    cs:__imp_free
0x180001ef6  mov     rcx, [rbx]; Block
0x180001ef9  test    rcx, rcx
0x180001efc  jnz     short loc_180001EEA
0x180001efe  add     rsp, 20h
0x180001f02  pop     rbx
0x180001f03  retn
```
