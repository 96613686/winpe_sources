# wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::get(void)

- ea: `0x1800092e0`
- end: `0x1800092e4`
- name: `?get@?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEBAPEA_WXZ`
- size: `4`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180015922`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::get(
        __int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1800092e0  mov     rax, [rcx]
0x1800092e3  retn
```
