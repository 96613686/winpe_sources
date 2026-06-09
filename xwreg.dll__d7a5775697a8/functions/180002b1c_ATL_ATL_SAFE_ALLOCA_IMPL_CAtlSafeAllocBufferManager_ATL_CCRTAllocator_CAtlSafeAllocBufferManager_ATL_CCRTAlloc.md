# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180002b1c`
- end: `0x180002b44`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003330`
- `0x1800033ac`
- `0x180004d18`
- `0x1800053f0`
- `0x1800060fc`
- `0x180006374`
- `0x180012cae`
- `0x180012d2e`
- `0x180012d40`

## callees

- `0x180002b1c`

## import_xrefs

- `msvcrt!free` at `0x180002b30`
- `msvcrt!free` at `0x180002b30`

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
0x180002b1c  push    rbx
0x180002b1e  sub     rsp, 20h
0x180002b22  mov     rbx, rcx
0x180002b25  mov     rcx, [rcx]
0x180002b28  jmp     short loc_180002B39
0x180002b2a  mov     rax, [rcx]
0x180002b2d  mov     [rbx], rax
0x180002b30  call    cs:__imp_free
0x180002b36  mov     rcx, [rbx]; Block
0x180002b39  test    rcx, rcx
0x180002b3c  jnz     short loc_180002B2A
0x180002b3e  add     rsp, 20h
0x180002b42  pop     rbx
0x180002b43  retn
```
