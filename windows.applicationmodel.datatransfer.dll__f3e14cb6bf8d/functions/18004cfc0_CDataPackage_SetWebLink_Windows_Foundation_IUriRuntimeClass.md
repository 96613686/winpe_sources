# CDataPackage::SetWebLink(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x18004cfc0`
- end: `0x18004d0bf`
- name: `?SetWebLink@CDataPackage@@UEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CDataPackage *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18004cfc0`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d044`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d044`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004d01e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18004d01e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d05d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d05d`

## pseudocode

```c
__int64 __fastcall CDataPackage::SetWebLink(
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
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)DataPackage_SetUri_Start,
      a3,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&string);
  if ( a2 )
  {
    v8 = *(__int64 (__fastcall **)(char *, HSTRING, struct Windows::Foundation::IUriRuntimeClass *))(*((_QWORD *)this - 1) + 112LL);
    if ( WindowsCreateStringReference(L"UniformResourceLocatorW", 0x17u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v5 = v8((char *)this - 8, string, a2);
  }
  else
  {
    v5 = -2147467261;
    RoOriginateErrorW(2147500035LL, 5, L"value");
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v6,
      (const EVENT_DESCRIPTOR *)DataPackage_SetUri_Stop,
      v7,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&string);
  return v5;
}

```

## disassembly

```asm
0x18004cfc0  mov     r11, rsp
0x18004cfc3  mov     [r11+18h], rbx
0x18004cfc7  mov     [r11+20h], rsi
0x18004cfcb  push    rdi
0x18004cfcc  sub     rsp, 60h
0x18004cfd0  mov     rax, cs:__security_cookie
0x18004cfd7  xor     rax, rsp
0x18004cfda  mov     [rsp+68h+var_18], rax
0x18004cfdf  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18004cfe6  mov     rbx, rdx
0x18004cfe9  mov     rdi, rcx
0x18004cfec  jz      short loc_18004D008
0x18004cfee  lea     rax, [r11-38h]
0x18004cff2  mov     r9d, 1
0x18004cff8  lea     rdx, DataPackage_SetUri_Start
0x18004cfff  mov     [r11-48h], rax
0x18004d003  call    McGenEventWrite_EventWriteTransfer
0x18004d008  test    rbx, rbx
0x18004d00b  jnz     short loc_18004D026
0x18004d00d  lea     edx, [rbx+5]
0x18004d010  mov     ebx, 80004003h
0x18004d015  mov     ecx, ebx
0x18004d017  lea     r8, aValue_0; "value"
0x18004d01e  call    cs:__imp_RoOriginateErrorW
0x18004d024  jmp     short loc_18004D079
0x18004d026  mov     rax, [rdi-8]
0x18004d02a  lea     r9, [rsp+68h+string]; string
0x18004d02f  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18004d034  mov     edx, 17h; length
0x18004d039  lea     rcx, aUniformresourc_0; "UniformResourceLocatorW"
0x18004d040  mov     rsi, [rax+70h]
0x18004d044  call    cs:__imp_WindowsCreateStringReference
0x18004d04a  test    eax, eax
0x18004d04c  jns     short loc_18004D063
0x18004d04e  xor     r9d, r9d; lpArguments
0x18004d051  xor     r8d, r8d; nNumberOfArguments
0x18004d054  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d059  lea     edx, [r9+1]; dwExceptionFlags
0x18004d05d  call    cs:__imp_RaiseException
0x18004d063  mov     rdx, [rsp+68h+string]
0x18004d068  lea     rcx, [rdi-8]
0x18004d06c  mov     r8, rbx
0x18004d06f  mov     rax, rsi
0x18004d072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d077  mov     ebx, eax
0x18004d079  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18004d080  jz      short loc_18004D09E
0x18004d082  lea     rax, [rsp+68h+string]
0x18004d087  mov     r9d, 1
0x18004d08d  lea     rdx, DataPackage_SetUri_Stop
0x18004d094  mov     [rsp+68h+var_48], rax
0x18004d099  call    McGenEventWrite_EventWriteTransfer
0x18004d09e  mov     eax, ebx
0x18004d0a0  mov     rcx, [rsp+68h+var_18]
0x18004d0a5  xor     rcx, rsp; StackCookie
0x18004d0a8  call    __security_check_cookie
0x18004d0ad  lea     r11, [rsp+68h+var_8]
0x18004d0b2  mov     rbx, [r11+20h]
0x18004d0b6  mov     rsi, [r11+28h]
0x18004d0ba  mov     rsp, r11
0x18004d0bd  pop     rdi
0x18004d0be  retn
```
