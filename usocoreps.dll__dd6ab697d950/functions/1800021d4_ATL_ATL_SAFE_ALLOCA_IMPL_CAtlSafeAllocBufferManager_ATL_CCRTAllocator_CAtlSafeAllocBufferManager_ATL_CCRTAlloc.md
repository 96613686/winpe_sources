# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x1800021d4`
- end: `0x1800021fc`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000500e`
- `0x1800050a0`

## callees

- `0x1800021d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800021e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800021e8`

## pseudocode

```c
void __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(
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
0x1800021d4  push    rbx
0x1800021d6  sub     rsp, 20h
0x1800021da  mov     rbx, rcx
0x1800021dd  mov     rcx, [rcx]
0x1800021e0  jmp     short loc_1800021F1
0x1800021e2  mov     rax, [rcx]
0x1800021e5  mov     [rbx], rax
0x1800021e8  call    cs:__imp_free
0x1800021ee  mov     rcx, [rbx]; Block
0x1800021f1  test    rcx, rcx
0x1800021f4  jnz     short loc_1800021E2
0x1800021f6  add     rsp, 20h
0x1800021fa  pop     rbx
0x1800021fb  retn
```
