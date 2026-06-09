# KvpEncoderBase_CoTaskMemNativeString::FinalizeCreateString(HSTRING__ * *)

- ea: `0x1800506e0`
- end: `0x180050754`
- name: `?FinalizeCreateString@KvpEncoderBase_CoTaskMemNativeString@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `116`
- prototype: `int(KvpEncoderBase_CoTaskMemNativeString *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000e5ac`
- `0x180010130`
- `0x180019c58`
- `0x1800506e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180050733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180050733`

## string_xrefs

- `0x18005070d`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
__int64 __fastcall KvpEncoderBase_CoTaskMemNativeString::FinalizeCreateString(
        KvpEncoderBase_CoTaskMemNativeString *this,
        HSTRING *a2)
{
  char *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // r9
  HSTRING *v5; // r10
  HRESULT String; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char *)this + 8;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 8);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v3);
  if ( v4 == *((_QWORD *)v2 + 1) )
  {
    String = WindowsCreateString(*(PCNZWCH *)v2, v4, v5);
    if ( String >= 0 )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v2);
    return (unsigned int)String;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)0x80070216LL,
      v8);
    return 2147942934LL;
  }
}

```

## disassembly

```asm
0x1800506e0  mov     [rsp+arg_0], rbx
0x1800506e5  push    rdi; int
0x1800506e6  sub     rsp, 20h
0x1800506ea  lea     rbx, [rcx+8]
0x1800506ee  mov     r10, rdx
0x1800506f1  mov     rcx, rbx
0x1800506f4  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800506f9  mov     r9d, [rbx+8]
0x1800506fd  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180050702  cmp     r9, [rbx+8]
0x180050706  jz      short loc_18005072A
0x180050708  mov     rcx, [rsp+28h]; this
0x18005070d  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x180050714  mov     ebx, 80070216h
0x180050719  mov     edx, 30h ; '0'; void *
0x18005071e  mov     r9d, ebx; char *
0x180050721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050726  mov     eax, ebx
0x180050728  jmp     short loc_180050749
0x18005072a  mov     rcx, [rbx]; sourceString
0x18005072d  mov     r8, r10; string
0x180050730  mov     edx, r9d; length
0x180050733  call    cs:__imp_WindowsCreateString
0x180050739  mov     edi, eax
0x18005073b  test    eax, eax
0x18005073d  js      short loc_180050747
0x18005073f  mov     rcx, rbx
0x180050742  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180050747  mov     eax, edi
0x180050749  mov     rbx, [rsp+28h+arg_0]
0x18005074e  add     rsp, 20h
0x180050752  pop     rdi
0x180050753  retn
```
