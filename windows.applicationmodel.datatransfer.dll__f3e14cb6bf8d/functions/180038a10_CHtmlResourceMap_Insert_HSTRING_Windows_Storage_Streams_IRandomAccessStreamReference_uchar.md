# CHtmlResourceMap::Insert(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStreamReference *,uchar *)

- ea: `0x180038a10`
- end: `0x180038ae4`
- name: `?Insert@CHtmlResourceMap@@UEAAJPEAUHSTRING__@@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAE@Z`
- size: `212`
- prototype: `int(CHtmlResourceMap *__hidden this, HSTRING, struct Windows::Storage::Streams::IRandomAccessStreamReference *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180024464`
- `0x1800387b0`
- `0x180038a10`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038a88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180038a88`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180038a3b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180038a3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHtmlResourceMap::Insert(
        CHtmlResourceMap *this,
        HSTRING a2,
        struct Windows::Storage::Streams::IRandomAccessStreamReference *a3,
        unsigned __int8 *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rbx
  BOOL IsStringEmpty; // eax
  HSTRING v11; // rdx
  struct Windows::Foundation::IUriRuntimeClass *v12; // rcx
  HSTRING string[7]; // [rsp+20h] [rbp-38h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v15; // [rsp+70h] [rbp+18h] BYREF

  if ( a3 )
  {
    string[0] = 0;
    v15 = 0;
    if ( (int)CreateUriFromText(a2, &v15) >= 0 )
      (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v15 + 48LL))(
        v15,
        string);
    v9 = *((_QWORD *)this + 9);
    IsStringEmpty = WindowsIsStringEmpty(string[0]);
    v11 = string[0];
    if ( IsStringEmpty )
      v11 = a2;
    v8 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Insert(
           v9,
           v11,
           (__int64)a3,
           a4);
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( string[0] )
      WindowsDeleteString(string[0]);
  }
  else
  {
    v8 = -2147467261;
    RoOriginateErrorW(2147500035LL, 5, L"value");
  }
  return v8;
}

```

## disassembly

```asm
0x180038a10  push    rbx
0x180038a12  push    rbp
0x180038a13  push    rsi
0x180038a14  push    rdi
0x180038a15  sub     rsp, 38h
0x180038a19  mov     rbp, r9
0x180038a1c  mov     rsi, r8
0x180038a1f  mov     rdi, rdx
0x180038a22  mov     rbx, rcx
0x180038a25  test    r8, r8
0x180038a28  jnz     short loc_180038A46
0x180038a2a  lea     r8, aValue_0; "value"
0x180038a31  lea     edx, [rsi+5]
0x180038a34  mov     ebx, 80004003h
0x180038a39  mov     ecx, ebx
0x180038a3b  call    cs:__imp_RoOriginateErrorW
0x180038a41  jmp     loc_180038AD9
0x180038a46  mov     [rsp+58h+string], 0
0x180038a4f  mov     [rsp+58h+arg_10], 0
0x180038a58  lea     rdx, [rsp+58h+arg_10]; struct Windows::Foundation::IUriRuntimeClass **
0x180038a5d  mov     rcx, rdi; HSTRING
0x180038a60  call    ?CreateUriFromText@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; CreateUriFromText(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x180038a65  test    eax, eax
0x180038a67  js      short loc_180038A7F
0x180038a69  mov     rcx, [rsp+58h+arg_10]
0x180038a6e  mov     rax, [rcx]
0x180038a71  lea     rdx, [rsp+58h+string]
0x180038a76  mov     rax, [rax+30h]
0x180038a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a7f  mov     rbx, [rbx+48h]
0x180038a83  mov     rcx, [rsp+58h+string]; string
0x180038a88  call    cs:__imp_WindowsIsStringEmpty
0x180038a8e  mov     rdx, [rsp+58h+string]
0x180038a93  test    eax, eax
0x180038a95  cmovnz  rdx, rdi
0x180038a99  mov     r9, rbp
0x180038a9c  mov     r8, rsi
0x180038a9f  mov     rcx, rbx
0x180038aa2  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIRandomAccessStreamReference@Streams@Storage@5@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Insert(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStreamReference *,uchar *)
0x180038aa7  mov     ebx, eax
0x180038aa9  mov     rcx, [rsp+58h+arg_10]
0x180038aae  test    rcx, rcx
0x180038ab1  jz      short loc_180038AC9
0x180038ab3  mov     [rsp+58h+arg_10], 0
0x180038abc  mov     rdx, [rcx]
0x180038abf  mov     rax, [rdx+10h]
0x180038ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ac8  nop
0x180038ac9  mov     rcx, [rsp+58h+string]; string
0x180038ace  test    rcx, rcx
0x180038ad1  jz      short loc_180038AD9
0x180038ad3  call    cs:__imp_WindowsDeleteString
0x180038ad9  mov     eax, ebx
0x180038adb  add     rsp, 38h
0x180038adf  pop     rdi
0x180038ae0  pop     rsi
0x180038ae1  pop     rbp
0x180038ae2  pop     rbx
0x180038ae3  retn
```
