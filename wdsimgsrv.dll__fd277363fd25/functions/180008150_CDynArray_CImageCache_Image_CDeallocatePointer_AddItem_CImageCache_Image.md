# CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(CImageCache::Image *)

- ea: `0x180008150`
- end: `0x180008183`
- name: `?AddItem@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAKPEAUImage@CImageCache@@@Z`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000891c`
- `0x1800092ec`

## callees

- `0x180008150`
- `0x180008c70`

## pseudocode

```c
__int64 __fastcall CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow(a1);
  if ( !(_DWORD)result )
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a1 + 12))++) = a2;
  return result;
}

```

## disassembly

```asm
0x180008150  mov     [rsp+arg_0], rbx
0x180008155  push    rdi
0x180008156  sub     rsp, 20h
0x18000815a  mov     rdi, rdx
0x18000815d  mov     rbx, rcx
0x180008160  call    ?Grow@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@AEAAKXZ; CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow(void)
0x180008165  test    eax, eax
0x180008167  jnz     short loc_180008177
0x180008169  mov     r9d, [rbx+0Ch]
0x18000816d  mov     r8, [rbx]
0x180008170  mov     [r8+r9*8], rdi
0x180008174  inc     dword ptr [rbx+0Ch]
0x180008177  mov     rbx, [rsp+28h+arg_0]
0x18000817c  add     rsp, 20h
0x180008180  pop     rdi
0x180008181  retn
```
