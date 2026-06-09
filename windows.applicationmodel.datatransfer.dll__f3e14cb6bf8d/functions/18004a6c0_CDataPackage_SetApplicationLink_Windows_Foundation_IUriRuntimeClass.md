# CDataPackage::SetApplicationLink(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x18004a6c0`
- end: `0x18004a7bf`
- name: `?SetApplicationLink@CDataPackage@@UEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CDataPackage *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18004a6c0`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a744`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004a71e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004a71e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a75d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a75d`

## string_xrefs

- `0x18004a739`: `ApplicationLink`

## pseudocode

```c
__int64 __fastcall CDataPackage::SetApplicationLink(
        CDataPackage *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 (__fastcall *v8)(char *, HSTRING, struct Windows::Foundation::IUriRuntimeClass *); // rsi
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, DataPackage_SetApplicationLink_Start, a3, 1);
  if ( a2 )
  {
    v8 = *(__int64 (__fastcall **)(char *, HSTRING, struct Windows::Foundation::IUriRuntimeClass *))(*((_QWORD *)this - 1) + 112LL);
    if ( WindowsCreateStringReference(L"ApplicationLink", 0xFu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v5 = v8((char *)this - 8, string, a2);
  }
  else
  {
    v5 = -2147467261;
    RoOriginateErrorW(2147500035LL, 5, L"value");
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, DataPackage_SetApplicationLink_Stop, v7, 1);
  return v5;
}

```

## disassembly

```asm
0x18004a6c0  mov     r11, rsp
0x18004a6c3  mov     [r11+18h], rbx
0x18004a6c7  mov     [r11+20h], rsi
0x18004a6cb  push    rdi
0x18004a6cc  sub     rsp, 60h
0x18004a6d0  mov     rax, cs:__security_cookie
0x18004a6d7  xor     rax, rsp
0x18004a6da  mov     [rsp+68h+var_18], rax
0x18004a6df  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18004a6e6  mov     rbx, rdx
0x18004a6e9  mov     rdi, rcx
0x18004a6ec  jz      short loc_18004A708
0x18004a6ee  lea     rax, [r11-38h]
0x18004a6f2  mov     r9d, 1
0x18004a6f8  lea     rdx, DataPackage_SetApplicationLink_Start
0x18004a6ff  mov     [r11-48h], rax
0x18004a703  call    McGenEventWrite_EventWriteTransfer
0x18004a708  test    rbx, rbx
0x18004a70b  jnz     short loc_18004A726
0x18004a70d  lea     edx, [rbx+5]
0x18004a710  mov     ebx, 80004003h
0x18004a715  mov     ecx, ebx
0x18004a717  lea     r8, aValue_0; "value"
0x18004a71e  call    cs:__imp_RoOriginateErrorW
0x18004a724  jmp     short loc_18004A779
0x18004a726  mov     rax, [rdi-8]
0x18004a72a  lea     r9, [rsp+68h+string]; string
0x18004a72f  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18004a734  mov     edx, 0Fh; length
0x18004a739  lea     rcx, aApplicationlin; "ApplicationLink"
0x18004a740  mov     rsi, [rax+70h]
0x18004a744  call    cs:__imp_WindowsCreateStringReference
0x18004a74a  test    eax, eax
0x18004a74c  jns     short loc_18004A763
0x18004a74e  xor     r9d, r9d; lpArguments
0x18004a751  xor     r8d, r8d; nNumberOfArguments
0x18004a754  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004a759  lea     edx, [r9+1]; dwExceptionFlags
0x18004a75d  call    cs:__imp_RaiseException
0x18004a763  mov     rdx, [rsp+68h+string]
0x18004a768  lea     rcx, [rdi-8]
0x18004a76c  mov     r8, rbx
0x18004a76f  mov     rax, rsi
0x18004a772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a777  mov     ebx, eax
0x18004a779  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18004a780  jz      short loc_18004A79E
0x18004a782  lea     rax, [rsp+68h+string]
0x18004a787  mov     r9d, 1
0x18004a78d  lea     rdx, DataPackage_SetApplicationLink_Stop
0x18004a794  mov     [rsp+68h+var_48], rax
0x18004a799  call    McGenEventWrite_EventWriteTransfer
0x18004a79e  mov     eax, ebx
0x18004a7a0  mov     rcx, [rsp+68h+var_18]
0x18004a7a5  xor     rcx, rsp; StackCookie
0x18004a7a8  call    __security_check_cookie
0x18004a7ad  lea     r11, [rsp+68h+var_8]
0x18004a7b2  mov     rbx, [r11+20h]
0x18004a7b6  mov     rsi, [r11+28h]
0x18004a7ba  mov     rsp, r11
0x18004a7bd  pop     rdi
0x18004a7be  retn
```
