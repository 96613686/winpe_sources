# wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x18001cff0`
- end: `0x18001d011`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180036060`
- `0x180036542`
- `0x180036622`
- `0x1800367c3`

## callees

- `0x18001cff0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d006`

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
0x18001cff0  sub     rsp, 28h
0x18001cff4  mov     rax, [rcx]
0x18001cff7  mov     qword ptr [rcx], 0
0x18001cffe  test    rax, rax
0x18001d001  jz      short loc_18001D00C
0x18001d003  mov     rcx, rax; hMem
0x18001d006  call    cs:__imp_LocalFree
0x18001d00c  add     rsp, 28h
0x18001d010  retn
```
