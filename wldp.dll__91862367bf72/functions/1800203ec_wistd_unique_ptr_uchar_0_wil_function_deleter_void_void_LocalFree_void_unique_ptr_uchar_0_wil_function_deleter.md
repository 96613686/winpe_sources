# wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x1800203ec`
- end: `0x18002040e`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800203e0`
- `0x180027fd0`
- `0x180028670`
- `0x180028740`
- `0x1800339f8`
- `0x180033d40`
- `0x18003f412`
- `0x18003f424`
- `0x18003f448`
- `0x18003f7a0`
- `0x18003f7b2`
- `0x1800404c7`
- `0x1800404d9`
- `0x1800412de`
- `0x18004131c`
- `0x180041340`

## callees

- `0x1800203ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020402`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
        HLOCAL *a1)
{
  HLOCAL result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return LocalFree(result);
  return result;
}

```

## disassembly

```asm
0x1800203ec  sub     rsp, 28h
0x1800203f0  mov     rax, [rcx]
0x1800203f3  mov     qword ptr [rcx], 0
0x1800203fa  test    rax, rax
0x1800203fd  jz      short loc_180020409
0x1800203ff  mov     rcx, rax; hMem
0x180020402  call    cs:__imp_LocalFree
0x180020408  nop
0x180020409  add     rsp, 28h
0x18002040d  retn
```
