# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180005798`
- end: `0x1800057c0`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180005da0`
- `0x180005e13`
- `0x180005e28`
- `0x180006598`
- `0x180007120`
- `0x18000734f`
- `0x18000764c`
- `0x180007816`
- `0x18000830c`
- `0x18000858c`

## callees

- `0x180005798`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800057ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800057ac`

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
0x180005798  push    rbx
0x18000579a  sub     rsp, 20h
0x18000579e  mov     rbx, rcx
0x1800057a1  mov     rcx, [rcx]
0x1800057a4  jmp     short loc_1800057B5
0x1800057a6  mov     rax, [rcx]
0x1800057a9  mov     [rbx], rax
0x1800057ac  call    cs:__imp_free
0x1800057b2  mov     rcx, [rbx]; Block
0x1800057b5  test    rcx, rcx
0x1800057b8  jnz     short loc_1800057A6
0x1800057ba  add     rsp, 20h
0x1800057be  pop     rbx
0x1800057bf  retn
```
