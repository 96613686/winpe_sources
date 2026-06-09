# _CommandImpl::GetExternalCommandFunction_::_1_::catch$32

- ea: `0x180015922`
- end: `0x18001598b`
- name: `_CommandImpl::GetExternalCommandFunction_::_1_::catch$32`
- size: `105`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000884c`
- `0x180008f78`
- `0x1800092e0`
- `0x180009314`
- `0x18000bfb4`
- `0x18001440c`
- `0x180015922`

## pseudocode

```c
void __fastcall __noreturn CommandImpl::GetExternalCommandFunction_::_1_::catch_32(__int64 a1, __int64 a2)
{
  DWORD ErrorCode; // eax
  __int64 v4; // rax
  __int64 v5; // rax

  ErrorCode = wil::ResultException::GetErrorCode(*(wil::ResultException **)(a2 + 128));
  CommandImpl::GetMessageW((_QWORD *)(a2 + 136), ErrorCode, 1u);
  if ( wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::get(a2 + 136) )
  {
    v4 = wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::get(a2 + 136);
    v5 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcerr, v4);
    std::wostream::operator<<(v5);
  }
  throw;
}

```

## disassembly

```asm
0x180015922  mov     [rsp+arg_8], rdx
0x180015927  push    rbp
0x180015928  sub     rsp, 30h
0x18001592c  mov     rbp, rdx
0x18001592f  mov     rcx, [rbp+80h]; this
0x180015936  call    ?GetErrorCode@ResultException@wil@@QEBAJXZ; wil::ResultException::GetErrorCode(void)
0x18001593b  mov     edx, eax
0x18001593d  mov     r8b, 1
0x180015940  lea     rcx, [rbp+88h]
0x180015947  call    ?GetMessageW@CommandImpl@@CA?AV?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K_N@Z; CommandImpl::GetMessageW(ulong,bool)
0x18001594c  nop
0x18001594d  lea     rcx, [rbp+88h]
0x180015954  call    ?get@?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEBAPEA_WXZ; wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::get(void)
0x180015959  test    rax, rax
0x18001595c  jz      short loc_180015981
0x18001595e  lea     rcx, [rbp+88h]
0x180015965  call    ?get@?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEBAPEA_WXZ; wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::get(void)
0x18001596a  mov     rdx, rax
0x18001596d  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x180015974  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180015979  mov     rcx, rax
0x18001597c  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::wostream::operator<<(std::wostream & (*)(std::wostream &))
0x180015981  xor     edx, edx; pThrowInfo
0x180015983  xor     ecx, ecx; pExceptionObject
0x180015985  call    _CxxThrowException
```
