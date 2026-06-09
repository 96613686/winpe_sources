# _CommandImpl::GetExternalCommandFunction_::_1_::dtor$5

- ea: `0x1800158fe`
- end: `0x18001590a`
- name: `_CommandImpl::GetExternalCommandFunction_::_1_::dtor$5`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800092ec`

## pseudocode

```c
HLOCAL __fastcall CommandImpl::GetExternalCommandFunction_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 136));
}

```

## disassembly

```asm
0x1800158fe  lea     rcx, [rdx+88h]
0x180015905  jmp     ??1?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
