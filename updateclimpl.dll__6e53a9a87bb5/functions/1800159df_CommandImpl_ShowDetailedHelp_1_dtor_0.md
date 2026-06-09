# _CommandImpl::ShowDetailedHelp_::_1_::dtor$0

- ea: `0x1800159df`
- end: `0x1800159eb`
- name: `_CommandImpl::ShowDetailedHelp_::_1_::dtor$0`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800092ec`

## pseudocode

```c
HLOCAL __fastcall CommandImpl::ShowDetailedHelp_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 56));
}

```

## disassembly

```asm
0x1800159df  lea     rcx, [rdx+38h]
0x1800159e6  jmp     ??1?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
