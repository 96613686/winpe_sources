# wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x1800092ec`
- end: `0x18000930d`
- name: `??1?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800158a4`
- `0x1800158fe`
- `0x1800159df`

## callees

- `0x1800092ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009302`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
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
0x1800092ec  sub     rsp, 28h
0x1800092f0  mov     rax, [rcx]
0x1800092f3  mov     qword ptr [rcx], 0
0x1800092fa  test    rax, rax
0x1800092fd  jz      short loc_180009308
0x1800092ff  mov     rcx, rax; hMem
0x180009302  call    cs:__imp_LocalFree
0x180009308  add     rsp, 28h
0x18000930c  retn
```
