# wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x18001cfa8`
- end: `0x18001cfd2`
- name: `??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ec10`

## callees

- `0x18001cfa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cfc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cfc7`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
        __int64 a1)
{
  HLOCAL result; // rax
  void *v2; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    result = *(HLOCAL *)(a1 + 8);
    v2 = **(void ***)a1;
    **(_QWORD **)a1 = result;
    if ( v2 )
      return LocalFree(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001cfa8  sub     rsp, 28h
0x18001cfac  cmp     byte ptr [rcx+10h], 0
0x18001cfb0  jz      short loc_18001CFCD
0x18001cfb2  mov     rdx, [rcx]
0x18001cfb5  mov     rax, [rcx+8]
0x18001cfb9  mov     r8, [rdx]
0x18001cfbc  mov     [rdx], rax
0x18001cfbf  test    r8, r8
0x18001cfc2  jz      short loc_18001CFCD
0x18001cfc4  mov     rcx, r8; hMem
0x18001cfc7  call    cs:__imp_LocalFree
0x18001cfcd  add     rsp, 28h
0x18001cfd1  retn
```
