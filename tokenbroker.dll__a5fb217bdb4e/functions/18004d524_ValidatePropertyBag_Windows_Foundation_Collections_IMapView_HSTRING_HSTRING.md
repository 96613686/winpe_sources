# ValidatePropertyBag(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18004d524`
- end: `0x18004d83c`
- name: `?ValidatePropertyBag@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `792`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004d3f0`
- `0x1800d4be4`
- `0x1800d4e70`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000f8e8`
- `0x18003523c`
- `0x18003ffa0`
- `0x18004d524`
- `0x18004e850`
- `0x18004fdbc`
- `0x18005fc2c`
- `0x18007ef3c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d735`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d735`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004d6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004d708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004d6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004d708`

## string_xrefs

- `0x18004d591`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18004d5e1`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18004d7da`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ValidatePropertyBag(__int64 a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // r9d
  __int64 v12; // rdx
  int *v13; // rdx
  int *v15; // [rsp+20h] [rbp-40h]
  HSTRING v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h] BYREF
  int v20[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v22; // [rsp+80h] [rbp+20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+88h] [rbp+28h] BYREF
  __int64 v24; // [rsp+90h] [rbp+30h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &unk_180153360,
      0,
      0);
  if ( a1 )
  {
    v19 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::InternalAddRef(&v19);
    v18 = 0;
    v3 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
           &v19,
           &v18);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v22 = 0;
      v24 = 0;
      v4 = v18;
      v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 48LL);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v24);
      v6 = v5(v4, &v24);
      v2 = v6;
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 56LL))(v24, &v22);
        v2 = v6;
        if ( v6 >= 0 )
        {
          while ( 1 )
          {
            if ( !v22 )
              goto LABEL_42;
            v17 = 0;
            v16 = 0;
            string = 0;
            v8 = v24;
            v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
            Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v17);
            v10 = v9(v8, &v17);
            v2 = v10;
            if ( v10 < 0 )
            {
              v12 = 2726;
              goto LABEL_36;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 48LL))(v17, &v16);
            v2 = v10;
            if ( v10 < 0 )
              break;
            v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL))(v17, &string);
            v2 = v10;
            if ( v10 < 0 )
            {
              v12 = 2728;
LABEL_36:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v12,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
                (const char *)(unsigned int)v10,
                (int)v15);
              goto LABEL_37;
            }
            if ( (unsigned int)dword_180175000 > 5 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              *(_QWORD *)v20 = WindowsGetStringRawBuffer(v16, 0);
              v15 = v20;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                &dword_180175000,
                byte_180153283,
                0);
            }
            if ( WindowsIsStringEmpty(v16) )
            {
              v2 = -2147024809;
              if ( (unsigned int)dword_180175000 > 2 )
              {
                v13 = &dword_1801532D4;
LABEL_31:
                LODWORD(StringRawBuffer) = -2147024809;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_180175000,
                  (_DWORD)v13,
                  0,
                  v11,
                  (__int64)&StringRawBuffer);
              }
LABEL_32:
              TryOriginateError(-2147024809, 0x3E9u);
LABEL_37:
              if ( string )
                WindowsDeleteString(string);
              if ( v16 )
                WindowsDeleteString(v16);
              Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v17);
              goto LABEL_42;
            }
            if ( WindowsIsStringEmpty(string) )
            {
              v2 = -2147024809;
              if ( (unsigned int)dword_180175000 > 2 )
              {
                v13 = (int *)byte_180153319;
                goto LABEL_31;
              }
              goto LABEL_32;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 64LL))(v24, &v22);
            v2 = v10;
            if ( v10 < 0 )
            {
              v12 = 2761;
              goto LABEL_36;
            }
            if ( string )
              WindowsDeleteString(string);
            if ( v16 )
              WindowsDeleteString(v16);
            Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v17);
          }
          v12 = 2727;
          goto LABEL_36;
        }
        v7 = 2718;
      }
      else
      {
        v7 = 2717;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v6,
        (int)v15);
LABEL_42:
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v3,
        (int)v15);
    }
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  return v2;
}

```

## disassembly

```asm
0x18004d524  push    rbp
0x18004d526  push    rbx
0x18004d527  push    rdi
0x18004d528  mov     rbp, rsp
0x18004d52b  sub     rsp, 60h
0x18004d52f  mov     rdi, rcx
0x18004d532  xor     ebx, ebx
0x18004d534  mov     eax, cs:dword_180175000
0x18004d53a  cmp     eax, 4
0x18004d53d  jbe     short loc_18004D558
0x18004d53f  xor     r9d, r9d
0x18004d542  xor     r8d, r8d
0x18004d545  lea     rdx, unk_180153360
0x18004d54c  lea     rcx, dword_180175000
0x18004d553  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004d558  test    rdi, rdi
0x18004d55b  jz      loc_18004D832
0x18004d561  mov     [rbp+var_18], rdi
0x18004d565  lea     rcx, [rbp+var_18]
0x18004d569  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::InternalAddRef(void)
0x18004d56e  nop
0x18004d56f  mov     [rbp+var_20], 0
0x18004d577  lea     rdx, [rbp+var_20]
0x18004d57b  lea     rcx, [rbp+var_18]
0x18004d57f  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>>)
0x18004d584  mov     ebx, eax
0x18004d586  test    eax, eax
0x18004d588  jns     short loc_18004D5A7
0x18004d58a  mov     rcx, [rbp+18h]; this
0x18004d58e  mov     r9d, eax; char *
0x18004d591  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004d598  mov     edx, 0A9Ah; void *
0x18004d59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5a2  jmp     loc_18004D81F
0x18004d5a7  mov     [rbp+arg_0], 0
0x18004d5ab  mov     [rbp+arg_10], 0
0x18004d5b3  mov     rdi, [rbp+var_20]
0x18004d5b7  mov     rax, [rdi]
0x18004d5ba  mov     rbx, [rax+30h]
0x18004d5be  lea     rcx, [rbp+arg_10]
0x18004d5c2  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d5c7  lea     rdx, [rbp+arg_10]
0x18004d5cb  mov     rcx, rdi
0x18004d5ce  mov     rax, rbx
0x18004d5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5d6  mov     ebx, eax
0x18004d5d8  test    eax, eax
0x18004d5da  jns     short loc_18004D5F9
0x18004d5dc  mov     edx, 0A9Dh; void *
0x18004d5e1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004d5e8  mov     r9d, eax; char *
0x18004d5eb  mov     rcx, [rbp+18h]; this
0x18004d5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5f4  jmp     loc_18004D815
0x18004d5f9  mov     rcx, [rbp+arg_10]
0x18004d5fd  mov     rax, [rcx]
0x18004d600  lea     rdx, [rbp+arg_0]
0x18004d604  mov     rax, [rax+38h]
0x18004d608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d60d  mov     ebx, eax
0x18004d60f  test    eax, eax
0x18004d611  jns     loc_18004D755
0x18004d617  mov     edx, 0A9Eh
0x18004d61c  jmp     short loc_18004D5E1
0x18004d61e  mov     [rbp+var_28], 0
0x18004d626  mov     [rbp+var_30], 0
0x18004d62e  mov     [rbp+string], 0
0x18004d636  mov     rdi, [rbp+arg_10]
0x18004d63a  mov     rax, [rdi]
0x18004d63d  mov     rbx, [rax+30h]
0x18004d641  lea     rcx, [rbp+var_28]
0x18004d645  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d64a  lea     rdx, [rbp+var_28]
0x18004d64e  mov     rcx, rdi
0x18004d651  mov     rax, rbx
0x18004d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d659  mov     ebx, eax
0x18004d65b  test    eax, eax
0x18004d65d  js      loc_18004D7D2
0x18004d663  mov     rcx, [rbp+var_28]
0x18004d667  mov     rax, [rcx]
0x18004d66a  lea     rdx, [rbp+var_30]
0x18004d66e  mov     rax, [rax+30h]
0x18004d672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d677  mov     ebx, eax
0x18004d679  test    eax, eax
0x18004d67b  js      loc_18004D7CB
0x18004d681  mov     rcx, [rbp+var_28]
0x18004d685  mov     rax, [rcx]
0x18004d688  lea     rdx, [rbp+string]
0x18004d68c  mov     rax, [rax+38h]
0x18004d690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d695  mov     ebx, eax
0x18004d697  test    eax, eax
0x18004d699  js      loc_18004D7C4
0x18004d69f  mov     eax, cs:dword_180175000
0x18004d6a5  cmp     eax, 5
0x18004d6a8  jbe     short loc_18004D6F2
0x18004d6aa  xor     edx, edx; length
0x18004d6ac  mov     rcx, [rbp+string]; string
0x18004d6b0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d6b6  mov     [rbp+arg_8], rax
0x18004d6ba  xor     edx, edx; length
0x18004d6bc  mov     rcx, [rbp+var_30]; string
0x18004d6c0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d6c6  mov     qword ptr [rbp+var_10], rax
0x18004d6ca  lea     rax, [rbp+arg_8]
0x18004d6ce  mov     [rsp+60h+var_38], rax
0x18004d6d3  lea     rax, [rbp+var_10]
0x18004d6d7  mov     qword ptr [rsp+60h+var_40], rax; int
0x18004d6dc  xor     r8d, r8d
0x18004d6df  lea     rdx, byte_180153283
0x18004d6e6  lea     rcx, dword_180175000
0x18004d6ed  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18004d6f2  mov     rcx, [rbp+var_30]; string
0x18004d6f6  call    cs:__imp_WindowsIsStringEmpty
0x18004d6fc  test    eax, eax
0x18004d6fe  jnz     loc_18004D784
0x18004d704  mov     rcx, [rbp+string]; string
0x18004d708  call    cs:__imp_WindowsIsStringEmpty
0x18004d70e  test    eax, eax
0x18004d710  jnz     short loc_18004D76B
0x18004d712  mov     rcx, [rbp+arg_10]
0x18004d716  mov     rax, [rcx]
0x18004d719  lea     rdx, [rbp+arg_0]
0x18004d71d  mov     rax, [rax+40h]
0x18004d721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d726  mov     ebx, eax
0x18004d728  test    eax, eax
0x18004d72a  js      short loc_18004D764
0x18004d72c  mov     rcx, [rbp+string]; string
0x18004d730  test    rcx, rcx
0x18004d733  jz      short loc_18004D73C
0x18004d735  call    cs:__imp_WindowsDeleteString
0x18004d73b  nop
0x18004d73c  mov     rcx, [rbp+var_30]; string
0x18004d740  test    rcx, rcx
0x18004d743  jz      short loc_18004D74C
0x18004d745  call    cs:__imp_WindowsDeleteString
0x18004d74b  nop
0x18004d74c  lea     rcx, [rbp+var_28]
0x18004d750  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d755  cmp     [rbp+arg_0], 0
0x18004d759  jnz     loc_18004D61E
0x18004d75f  jmp     loc_18004D815
0x18004d764  mov     edx, 0AC9h
0x18004d769  jmp     short loc_18004D7D7
0x18004d76b  mov     eax, cs:dword_180175000
0x18004d771  mov     ebx, 80070057h
0x18004d776  cmp     eax, 2
0x18004d779  jbe     short loc_18004D7B6
0x18004d77b  lea     rdx, byte_180153319
0x18004d782  jmp     short loc_18004D79B
0x18004d784  mov     eax, cs:dword_180175000
0x18004d78a  mov     ebx, 80070057h
0x18004d78f  cmp     eax, 2
0x18004d792  jbe     short loc_18004D7B6
0x18004d794  lea     rdx, dword_1801532D4
0x18004d79b  lea     rax, [rbp+arg_8]
0x18004d79f  mov     qword ptr [rsp+60h+var_40], rax
0x18004d7a4  mov     dword ptr [rbp+arg_8], ebx
0x18004d7a7  xor     r8d, r8d
0x18004d7aa  lea     rcx, dword_180175000
0x18004d7b1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004d7b6  mov     edx, 3E9h; unsigned __int16
0x18004d7bb  mov     ecx, ebx; int
0x18004d7bd  call    ?TryOriginateError@@YAXJG@Z; TryOriginateError(long,ushort)
0x18004d7c2  jmp     short loc_18004D7EB
0x18004d7c4  mov     edx, 0AA8h
0x18004d7c9  jmp     short loc_18004D7D7
0x18004d7cb  mov     edx, 0AA7h
0x18004d7d0  jmp     short loc_18004D7D7
0x18004d7d2  mov     edx, 0AA6h; void *
0x18004d7d7  mov     r9d, eax; char *
0x18004d7da  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004d7e1  mov     rcx, [rbp+18h]; this
0x18004d7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d7ea  nop
0x18004d7eb  mov     rcx, [rbp+string]; string
0x18004d7ef  test    rcx, rcx
0x18004d7f2  jz      short loc_18004D7FB
0x18004d7f4  call    cs:__imp_WindowsDeleteString
0x18004d7fa  nop
0x18004d7fb  mov     rcx, [rbp+var_30]; string
0x18004d7ff  test    rcx, rcx
0x18004d802  jz      short loc_18004D80B
0x18004d804  call    cs:__imp_WindowsDeleteString
0x18004d80a  nop
0x18004d80b  lea     rcx, [rbp+var_28]
0x18004d80f  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d814  nop
0x18004d815  lea     rcx, [rbp+arg_10]
0x18004d819  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d81e  nop
0x18004d81f  lea     rcx, [rbp+var_20]
0x18004d823  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18004d828  nop
0x18004d829  lea     rcx, [rbp+var_18]
0x18004d82d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d832  mov     eax, ebx
0x18004d834  add     rsp, 60h
0x18004d838  pop     rdi
0x18004d839  pop     rbx
0x18004d83a  pop     rbp
0x18004d83b  retn
```
