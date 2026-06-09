# Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18001df20`
- end: `0x18001e19d`
- name: `?ParseTitle@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUHSTRING__@@2@Z`
- size: `637`
- prototype: `void(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dccc`

## callees

- `0x180005670`
- `0x18000dc30`
- `0x180014740`
- `0x18001a610`
- `0x18001b848`
- `0x18001df20`
- `0x18001e528`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001e110`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001e110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001e12b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001e12b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(
        Windows::Internal::Notifications::AdaptiveNotification *this,
        struct Windows::Data::Json::IJsonObject *a2,
        const unsigned __int16 *a3,
        HSTRING *a4,
        HSTRING *newString)
{
  int (__fastcall *v8)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *); // rbx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64 *); // rbx
  HSTRING *v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, HSTRING, __int64 *); // rbx
  HSTRING *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // [rsp+28h] [rbp-51h] BYREF
  __int64 v23; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h] BYREF
  double v26; // [rsp+48h] [rbp-31h] BYREF
  HSTRING string[4]; // [rsp+50h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]

  v25 = 0;
  v8 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, a3);
  if ( v8(a2, string[0], &v25) >= 0 )
  {
    v22 = 0;
    v9 = v25;
    v10 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    if ( v10(v9, &v22) >= 0 )
    {
      v24 = 0;
      v11 = v22;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v22 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v13 = Windows::Internal::StringReference::StringReference(string, L"text");
      v14 = v12(v11, *v13, &v24);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
          (const char *)(unsigned int)v14,
          v22);
      v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 64LL))(v24, a4);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
          (const char *)(unsigned int)v15,
          v22);
      v23 = 0;
      v16 = v22;
      v17 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v22 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      v18 = Windows::Internal::StringReference::StringReference(string, L"maxLines");
      if ( v17(v16, *v18, &v23) >= 0 )
      {
        v26 = 0.0;
        v19 = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v23 + 72LL))(v23, &v26);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x87,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
            (const char *)(unsigned int)v19,
            v22);
        if ( v26 < 0.0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
            (const char *)0x80070057LL,
            v22);
        _o__itow_s((unsigned int)(int)v26, string, 11);
        v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (PCWSTR)string);
        v21 = WindowsDuplicateString(*(HSTRING *)(v20 + 24), newString);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8C,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
            (const char *)(unsigned int)v21,
            v22);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
}

```

## disassembly

```asm
0x18001df20  mov     rax, rsp
0x18001df23  mov     [rax+8], rbx
0x18001df27  push    rbp
0x18001df28  push    rsi
0x18001df29  push    rdi
0x18001df2a  push    r14
0x18001df2c  push    r15
0x18001df2e  lea     rbp, [rax-57h]
0x18001df32  sub     rsp, 0A0h
0x18001df39  movaps  xmmword ptr [rax-38h], xmm6
0x18001df3d  mov     rax, cs:__security_cookie
0x18001df44  xor     rax, rsp
0x18001df47  mov     [rbp+4Fh+var_38], rax
0x18001df4b  mov     r14, r9
0x18001df4e  mov     rdi, r8
0x18001df51  mov     rsi, rdx
0x18001df54  mov     r15, [rbp+4Fh+newString]
0x18001df58  mov     [rbp+4Fh+var_88], 0
0x18001df60  mov     rax, [rdx]
0x18001df63  mov     rbx, [rax+30h]
0x18001df67  lea     rcx, [rbp+4Fh+var_88]
0x18001df6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001df70  mov     rdx, rdi; unsigned __int16 *
0x18001df73  lea     rcx, [rbp+4Fh+string]; this
0x18001df77  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001df7c  lea     r8, [rbp+4Fh+var_88]
0x18001df80  mov     rdx, [rbp+4Fh+string]
0x18001df84  mov     rcx, rsi
0x18001df87  mov     rax, rbx
0x18001df8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df8f  test    eax, eax
0x18001df91  js      loc_18001E16C
0x18001df97  mov     [rbp+4Fh+var_A0], 0
0x18001df9f  mov     rdi, [rbp+4Fh+var_88]
0x18001dfa3  mov     rax, [rdi]
0x18001dfa6  mov     rbx, [rax+60h]
0x18001dfaa  lea     rcx, [rbp+4Fh+var_A0]
0x18001dfae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dfb3  lea     rdx, [rbp+4Fh+var_A0]
0x18001dfb7  mov     rcx, rdi
0x18001dfba  mov     rax, rbx
0x18001dfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc2  test    eax, eax
0x18001dfc4  js      loc_18001E162
0x18001dfca  mov     [rbp+4Fh+var_90], 0
0x18001dfd2  mov     rdi, [rbp+4Fh+var_A0]
0x18001dfd6  mov     rax, [rdi]
0x18001dfd9  mov     rbx, [rax+30h]
0x18001dfdd  lea     rcx, [rbp+4Fh+var_90]
0x18001dfe1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dfe6  lea     rdx, aText; "text"
0x18001dfed  lea     rcx, [rbp+4Fh+string]; string
0x18001dff1  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18001dff6  lea     r8, [rbp+4Fh+var_90]
0x18001dffa  mov     rdx, [rax]
0x18001dffd  mov     rcx, rdi
0x18001e000  mov     rax, rbx
0x18001e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e008  mov     rcx, [rbp+57h]; this
0x18001e00c  test    eax, eax
0x18001e00e  jns     short loc_18001E025
0x18001e010  mov     r9d, eax; char *
0x18001e013  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e01a  mov     edx, 7Fh; void *
0x18001e01f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e025  mov     rcx, [rbp+4Fh+var_90]
0x18001e029  mov     rax, [rcx]
0x18001e02c  mov     rdx, r14
0x18001e02f  mov     rax, [rax+40h]
0x18001e033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e038  mov     rcx, [rbp+57h]; this
0x18001e03c  test    eax, eax
0x18001e03e  jns     short loc_18001E055
0x18001e040  mov     r9d, eax; char *
0x18001e043  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e04a  mov     edx, 81h; void *
0x18001e04f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e055  mov     [rbp+4Fh+var_98], 0
0x18001e05d  mov     rdi, [rbp+4Fh+var_A0]
0x18001e061  mov     rax, [rdi]
0x18001e064  mov     rbx, [rax+30h]
0x18001e068  lea     rcx, [rbp+4Fh+var_98]
0x18001e06c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e071  lea     rdx, aMaxlines; "maxLines"
0x18001e078  lea     rcx, [rbp+4Fh+string]; string
0x18001e07c  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x18001e081  lea     r8, [rbp+4Fh+var_98]
0x18001e085  mov     rdx, [rax]
0x18001e088  mov     rcx, rdi
0x18001e08b  mov     rax, rbx
0x18001e08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e093  test    eax, eax
0x18001e095  js      loc_18001E14E
0x18001e09b  xorps   xmm6, xmm6
0x18001e09e  movsd   [rbp+4Fh+var_80], xmm6
0x18001e0a3  mov     rcx, [rbp+4Fh+var_98]
0x18001e0a7  mov     rax, [rcx]
0x18001e0aa  lea     rdx, [rbp+4Fh+var_80]
0x18001e0ae  mov     rax, [rax+48h]
0x18001e0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b7  mov     rcx, [rbp+57h]; this
0x18001e0bb  test    eax, eax
0x18001e0bd  jns     short loc_18001E0D4
0x18001e0bf  mov     r9d, eax; char *
0x18001e0c2  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e0c9  mov     edx, 87h; void *
0x18001e0ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e0d4  comisd  xmm6, [rbp+4Fh+var_80]
0x18001e0d9  setnbe  al
0x18001e0dc  mov     rcx, [rbp+57h]; this
0x18001e0e0  test    al, al
0x18001e0e2  jz      short loc_18001E0FC
0x18001e0e4  mov     r9d, 80070057h; char *
0x18001e0ea  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e0f1  mov     edx, 88h; void *
0x18001e0f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e0fc  cvttsd2si rcx, [rbp+4Fh+var_80]
0x18001e102  mov     r9d, 0Ah
0x18001e108  lea     r8d, [r9+1]
0x18001e10c  lea     rdx, [rbp+4Fh+string]
0x18001e110  call    cs:__imp__o__itow_s
0x18001e116  lea     rdx, [rbp+4Fh+string]; sourceString
0x18001e11a  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18001e11e  call    ??$?0$0L@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0L@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[11])
0x18001e123  nop
0x18001e124  mov     rdx, r15; newString
0x18001e127  mov     rcx, [rax+18h]; string
0x18001e12b  call    cs:__imp_WindowsDuplicateString
0x18001e131  mov     rcx, [rbp+57h]; this
0x18001e135  test    eax, eax
0x18001e137  jns     short loc_18001E14E
0x18001e139  mov     r9d, eax; char *
0x18001e13c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e143  mov     edx, 8Ch; void *
0x18001e148  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e14e  lea     rcx, [rbp+4Fh+var_98]
0x18001e152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e157  nop
0x18001e158  lea     rcx, [rbp+4Fh+var_90]
0x18001e15c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e161  nop
0x18001e162  lea     rcx, [rbp+4Fh+var_A0]
0x18001e166  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e16b  nop
0x18001e16c  lea     rcx, [rbp+4Fh+var_88]
0x18001e170  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e175  mov     rcx, [rbp+4Fh+var_38]
0x18001e179  xor     rcx, rsp; StackCookie
0x18001e17c  call    __security_check_cookie
0x18001e181  lea     r11, [rsp+0C0h+var_20]
0x18001e189  mov     rbx, [r11+30h]
0x18001e18d  movaps  xmm6, xmmword ptr [r11-10h]
0x18001e192  mov     rsp, r11
0x18001e195  pop     r15
0x18001e197  pop     r14
0x18001e199  pop     rdi
0x18001e19a  pop     rsi
0x18001e19b  pop     rbp
0x18001e19c  retn
```
