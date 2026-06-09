# Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)

- ea: `0x14000e118`
- end: `0x14000e208`
- name: `?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z`
- size: `240`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d930`
- `0x14001a890`
- `0x14001b410`
- `0x14001b760`
- `0x1400336f0`
- `0x1400337f0`
- `0x1400338f0`
- `0x140037340`
- `0x14003c430`
- `0x14003c530`

## callees

- `0x140005e4c`
- `0x14000e118`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e16b`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e188`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e16b`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e188`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x14000e1b5`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x14000e1b5`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x14000e173`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x14000e173`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x14000e1c9`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x14000e1c9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
        __int64 a1,
        __int64 a2)
{
  int v3; // ebx
  int MatchingRestrictedErrorInfo; // edi
  unsigned int v5; // eax
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF

  v3 = a1;
  if ( (_DWORD)a1 == -2147417848
    || (_DWORD)a1 == -2147023174
    || (_DWORD)a1 == -1996357631
    || (_DWORD)a1 == -2147418105
    || (_DWORD)a1 == -2147418094 )
  {
    RoTransformError(a1, 0, 0);
    v3 = 0;
  }
  if ( (unsigned int)IsErrorPropagationEnabled() )
  {
    if ( v3 < 0 )
    {
      v7 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      MatchingRestrictedErrorInfo = RoGetMatchingRestrictedErrorInfo((unsigned int)v3, &v7);
      if ( MatchingRestrictedErrorInfo >= 0 )
        MatchingRestrictedErrorInfo = RoReportFailedDelegate(a2, v7);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v5 = 0;
      if ( MatchingRestrictedErrorInfo < 0 )
        return (unsigned int)v3;
      return v5;
    }
  }
  else if ( v3 < 0 )
  {
    RoTransformError((unsigned int)v3, 0, 0);
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e118  mov     [rsp+arg_10], rbx
0x14000e11d  mov     [rsp+arg_18], rsi
0x14000e122  push    rdi
0x14000e123  sub     rsp, 40h
0x14000e127  mov     rax, cs:__security_cookie
0x14000e12e  xor     rax, rsp
0x14000e131  mov     [rsp+48h+var_18], rax
0x14000e136  mov     rdi, r8
0x14000e139  mov     rsi, rdx
0x14000e13c  mov     ebx, ecx
0x14000e13e  cmp     ecx, 80010108h
0x14000e144  jz      short loc_14000E166
0x14000e146  cmp     ecx, 800706BAh
0x14000e14c  jz      short loc_14000E166
0x14000e14e  cmp     ecx, 89020001h
0x14000e154  jz      short loc_14000E166
0x14000e156  cmp     ecx, 80010007h
0x14000e15c  jz      short loc_14000E166
0x14000e15e  cmp     ecx, 80010012h
0x14000e164  jnz     short loc_14000E173
0x14000e166  xor     r8d, r8d
0x14000e169  xor     edx, edx
0x14000e16b  call    cs:__imp_RoTransformError
0x14000e171  xor     ebx, ebx
0x14000e173  call    cs:__imp_IsErrorPropagationEnabled
0x14000e179  test    eax, eax
0x14000e17b  jnz     short loc_14000E192
0x14000e17d  test    ebx, ebx
0x14000e17f  jns     short loc_14000E1E9
0x14000e181  xor     r8d, r8d
0x14000e184  xor     edx, edx
0x14000e186  mov     ecx, ebx
0x14000e188  call    cs:__imp_RoTransformError
0x14000e18e  xor     ebx, ebx
0x14000e190  jmp     short loc_14000E1E9
0x14000e192  test    ebx, ebx
0x14000e194  jns     short loc_14000E1E9
0x14000e196  lea     rcx, [rsp+48h+var_20]
0x14000e19b  mov     [rsp+48h+var_28], rdi
0x14000e1a0  mov     [rsp+48h+var_20], 0
0x14000e1a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e1ae  lea     rdx, [rsp+48h+var_20]
0x14000e1b3  mov     ecx, ebx
0x14000e1b5  call    cs:__imp_RoGetMatchingRestrictedErrorInfo
0x14000e1bb  mov     edi, eax
0x14000e1bd  test    eax, eax
0x14000e1bf  js      short loc_14000E1D1
0x14000e1c1  mov     rdx, [rsp+48h+var_20]
0x14000e1c6  mov     rcx, rsi
0x14000e1c9  call    cs:__imp_RoReportFailedDelegate
0x14000e1cf  mov     edi, eax
0x14000e1d1  mov     rax, [rsp+48h+var_28]
0x14000e1d6  lea     rcx, [rsp+48h+var_20]
0x14000e1db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e1e0  xor     eax, eax
0x14000e1e2  test    edi, edi
0x14000e1e4  cmovs   eax, ebx
0x14000e1e7  mov     ebx, eax
0x14000e1e9  mov     eax, ebx
0x14000e1eb  mov     rcx, [rsp+48h+var_18]
0x14000e1f0  xor     rcx, rsp; StackCookie
0x14000e1f3  call    __security_check_cookie
0x14000e1f8  mov     rbx, [rsp+48h+arg_10]
0x14000e1fd  mov     rsi, [rsp+48h+arg_18]
0x14000e202  add     rsp, 40h
0x14000e206  pop     rdi
0x14000e207  retn
```
