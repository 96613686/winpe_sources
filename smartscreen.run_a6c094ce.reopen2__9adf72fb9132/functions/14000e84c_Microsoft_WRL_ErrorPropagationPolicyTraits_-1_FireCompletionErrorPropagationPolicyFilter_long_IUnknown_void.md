# Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)

- ea: `0x14000e84c`
- end: `0x14000e95b`
- name: `?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z`
- size: `271`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e050`
- `0x14001b6b0`
- `0x14001c370`
- `0x14001c780`
- `0x140034b60`
- `0x140034c60`
- `0x140034d60`
- `0x140038890`
- `0x14003db00`
- `0x14003dc00`

## callees

- `0x1400061cc`
- `0x14000e84c`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e89f`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e8c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e89f`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x14000e8c8`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x14000e8fb`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x14000e8fb`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x14000e8ad`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x14000e8ad`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x14000e915`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x14000e915`

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
0x14000e84c  mov     [rsp+arg_10], rbx
0x14000e851  mov     [rsp+arg_18], rsi
0x14000e856  push    rdi
0x14000e857  sub     rsp, 40h
0x14000e85b  mov     rax, cs:__security_cookie
0x14000e862  xor     rax, rsp
0x14000e865  mov     [rsp+48h+var_18], rax
0x14000e86a  mov     rdi, r8
0x14000e86d  mov     rsi, rdx
0x14000e870  mov     ebx, ecx
0x14000e872  cmp     ecx, 80010108h
0x14000e878  jz      short loc_14000E89A
0x14000e87a  cmp     ecx, 800706BAh
0x14000e880  jz      short loc_14000E89A
0x14000e882  cmp     ecx, 89020001h
0x14000e888  jz      short loc_14000E89A
0x14000e88a  cmp     ecx, 80010007h
0x14000e890  jz      short loc_14000E89A
0x14000e892  cmp     ecx, 80010012h
0x14000e898  jnz     short loc_14000E8AD
0x14000e89a  xor     r8d, r8d
0x14000e89d  xor     edx, edx
0x14000e89f  call    cs:__imp_RoTransformError
0x14000e8a6  nop     dword ptr [rax+rax+00h]
0x14000e8ab  xor     ebx, ebx
0x14000e8ad  call    cs:__imp_IsErrorPropagationEnabled
0x14000e8b4  nop     dword ptr [rax+rax+00h]
0x14000e8b9  test    eax, eax
0x14000e8bb  jnz     short loc_14000E8D8
0x14000e8bd  test    ebx, ebx
0x14000e8bf  jns     short loc_14000E93B
0x14000e8c1  xor     r8d, r8d
0x14000e8c4  xor     edx, edx
0x14000e8c6  mov     ecx, ebx
0x14000e8c8  call    cs:__imp_RoTransformError
0x14000e8cf  nop     dword ptr [rax+rax+00h]
0x14000e8d4  xor     ebx, ebx
0x14000e8d6  jmp     short loc_14000E93B
0x14000e8d8  test    ebx, ebx
0x14000e8da  jns     short loc_14000E93B
0x14000e8dc  lea     rcx, [rsp+48h+var_20]
0x14000e8e1  mov     [rsp+48h+var_28], rdi
0x14000e8e6  mov     [rsp+48h+var_20], 0
0x14000e8ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e8f4  lea     rdx, [rsp+48h+var_20]
0x14000e8f9  mov     ecx, ebx
0x14000e8fb  call    cs:__imp_RoGetMatchingRestrictedErrorInfo
0x14000e902  nop     dword ptr [rax+rax+00h]
0x14000e907  mov     edi, eax
0x14000e909  test    eax, eax
0x14000e90b  js      short loc_14000E923
0x14000e90d  mov     rdx, [rsp+48h+var_20]
0x14000e912  mov     rcx, rsi
0x14000e915  call    cs:__imp_RoReportFailedDelegate
0x14000e91c  nop     dword ptr [rax+rax+00h]
0x14000e921  mov     edi, eax
0x14000e923  mov     rax, [rsp+48h+var_28]
0x14000e928  lea     rcx, [rsp+48h+var_20]
0x14000e92d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e932  xor     eax, eax
0x14000e934  test    edi, edi
0x14000e936  cmovs   eax, ebx
0x14000e939  mov     ebx, eax
0x14000e93b  mov     eax, ebx
0x14000e93d  mov     rcx, [rsp+48h+var_18]
0x14000e942  xor     rcx, rsp; StackCookie
0x14000e945  call    __security_check_cookie
0x14000e94a  mov     rbx, [rsp+48h+arg_10]
0x14000e94f  mov     rsi, [rsp+48h+arg_18]
0x14000e954  add     rsp, 40h
0x14000e958  pop     rdi
0x14000e959  retn
```
