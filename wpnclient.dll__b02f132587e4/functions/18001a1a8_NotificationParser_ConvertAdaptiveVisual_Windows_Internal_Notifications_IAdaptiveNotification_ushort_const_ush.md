# NotificationParser::ConvertAdaptiveVisual(Windows::Internal::Notifications::IAdaptiveNotification *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18001a1a8`
- end: `0x18001a3ba`
- name: `?ConvertAdaptiveVisual@NotificationParser@@AEAAXPEAUIAdaptiveNotification@Notifications@Internal@Windows@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@5@@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180019d04`

## callees

- `0x180005670`
- `0x180008390`
- `0x180014500`
- `0x18001a1a8`
- `0x18001a3c0`
- `0x18001a610`
- `0x18001a65c`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## string_xrefs

- `0x18001a29b`: `template`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NotificationParser::ConvertAdaptiveVisual(
        NotificationParser *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rbx
  HSTRING *v14; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v18; // rbx
  HSTRING *v19; // rax
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v24; // rbx
  HSTRING *v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v29; // [rsp+20h] [rbp-71h]
  int v30; // [rsp+20h] [rbp-71h]
  _BYTE v31[8]; // [rsp+40h] [rbp-51h] BYREF
  __int64 v32; // [rsp+48h] [rbp-49h] BYREF
  __int64 v33; // [rsp+50h] [rbp-41h] BYREF
  __int64 v34; // [rsp+58h] [rbp-39h] BYREF
  __int64 v35; // [rsp+60h] [rbp-31h] BYREF
  __int64 v36; // [rsp+68h] [rbp-29h] BYREF
  HSTRING string[4]; // [rsp+70h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v33 = 0;
  v32 = 0;
  v36 = 0;
  v35 = 0;
  v31[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  NotificationParser::CreateValueSet(v10, &v33, &v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  NotificationParser::CreateValueSet(v11, &v36, &v35);
  v34 = 0;
  v12 = *(_QWORD *)a1;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(**(_QWORD **)a1 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v14 = Windows::Internal::StringReference::StringReference(string, L"ToastGeneric");
  v15 = v13(v12, *v14, &v34);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v29);
  v16 = v32;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v32 + 80LL);
  v18 = v34;
  v19 = Windows::Internal::StringReference::StringReference(string, L"template");
  v20 = v17(v16, *v19, v18, v31);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v20,
      v29);
  NotificationParser::ConvertAdaptiveVisualItems(a1, a2, v21, a4, a5, a6, v35);
  v22 = v32;
  v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v32 + 80LL);
  v24 = v36;
  v25 = Windows::Internal::StringReference::StringReference(string, L"items");
  v26 = v23(v22, *v25, v24, v31);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v26,
      v30);
  v27 = v33;
  v33 = 0;
  *a7 = v27;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
}

```

## disassembly

```asm
0x18001a1a8  mov     [rsp-8+arg_10], rbx
0x18001a1ad  push    rbp
0x18001a1ae  push    rsi
0x18001a1af  push    rdi
0x18001a1b0  push    r12
0x18001a1b2  push    r13
0x18001a1b4  push    r14
0x18001a1b6  push    r15
0x18001a1b8  lea     rbp, [rsp-0Fh]
0x18001a1bd  sub     rsp, 0A0h
0x18001a1c4  mov     rax, cs:__security_cookie
0x18001a1cb  xor     rax, rsp
0x18001a1ce  mov     [rbp+3Fh+var_40], rax
0x18001a1d2  mov     r13, r9
0x18001a1d5  mov     r12, rdx
0x18001a1d8  mov     r15, rcx
0x18001a1db  mov     r14, [rbp+3Fh+arg_30]
0x18001a1df  xor     esi, esi
0x18001a1e1  mov     [rbp+3Fh+var_80], rsi
0x18001a1e5  mov     [rbp+3Fh+var_88], rsi
0x18001a1e9  mov     [rbp+3Fh+var_68], rsi
0x18001a1ed  mov     [rbp+3Fh+var_70], rsi
0x18001a1f1  mov     [rbp+3Fh+var_90], sil
0x18001a1f5  lea     rcx, [rbp+3Fh+var_88]
0x18001a1f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a1fe  lea     rcx, [rbp+3Fh+var_80]
0x18001a202  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a207  lea     r8, [rbp+3Fh+var_88]
0x18001a20b  lea     rdx, [rbp+3Fh+var_80]
0x18001a20f  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18001a214  lea     rcx, [rbp+3Fh+var_70]
0x18001a218  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a21d  lea     rcx, [rbp+3Fh+var_68]
0x18001a221  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a226  lea     r8, [rbp+3Fh+var_70]
0x18001a22a  lea     rdx, [rbp+3Fh+var_68]
0x18001a22e  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18001a233  mov     [rbp+3Fh+var_78], rsi
0x18001a237  mov     rdi, [r15]
0x18001a23a  mov     rax, [rdi]
0x18001a23d  mov     rbx, [rax+90h]
0x18001a244  lea     rcx, [rbp+3Fh+var_78]
0x18001a248  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a24d  lea     rdx, aToastgeneric; "ToastGeneric"
0x18001a254  lea     rcx, [rbp+3Fh+string]; string
0x18001a258  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x18001a25d  lea     r8, [rbp+3Fh+var_78]
0x18001a261  mov     rdx, [rax]
0x18001a264  mov     rcx, rdi
0x18001a267  mov     rax, rbx
0x18001a26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a26f  mov     rcx, [rbp+47h]; this
0x18001a273  test    eax, eax
0x18001a275  jns     short loc_18001A28C
0x18001a277  mov     r9d, eax; char *
0x18001a27a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a281  mov     edx, 0CBh; void *
0x18001a286  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a28c  mov     rsi, [rbp+3Fh+var_88]
0x18001a290  mov     rax, [rsi]
0x18001a293  mov     rdi, [rax+50h]
0x18001a297  mov     rbx, [rbp+3Fh+var_78]
0x18001a29b  lea     rdx, aTemplate; "template"
0x18001a2a2  lea     rcx, [rbp+3Fh+string]; string
0x18001a2a6  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x18001a2ab  lea     r9, [rbp+3Fh+var_90]
0x18001a2af  mov     r8, rbx
0x18001a2b2  mov     rdx, [rax]
0x18001a2b5  mov     rcx, rsi
0x18001a2b8  mov     rax, rdi
0x18001a2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c0  mov     rcx, [rbp+47h]; this
0x18001a2c4  test    eax, eax
0x18001a2c6  jns     short loc_18001A2DD
0x18001a2c8  mov     r9d, eax; char *
0x18001a2cb  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a2d2  mov     edx, 0CDh; void *
0x18001a2d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a2dd  mov     rax, [rbp+3Fh+var_70]
0x18001a2e1  mov     [rsp+0D0h+var_A0], rax
0x18001a2e6  mov     eax, [rbp+3Fh+arg_28]
0x18001a2e9  mov     [rsp+0D0h+var_A8], eax
0x18001a2ed  mov     eax, [rbp+3Fh+arg_20]
0x18001a2f0  mov     [rsp+0D0h+var_B0], eax; int
0x18001a2f4  mov     r9, r13
0x18001a2f7  mov     rdx, r12
0x18001a2fa  mov     rcx, r15
0x18001a2fd  call    ?ConvertAdaptiveVisualItems@NotificationParser@@AEAAXPEAUIAdaptiveNotification@Notifications@Internal@Windows@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@@Z; NotificationParser::ConvertAdaptiveVisualItems(Windows::Internal::Notifications::IAdaptiveNotification *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18001a302  mov     rsi, [rbp+3Fh+var_88]
0x18001a306  mov     rax, [rsi]
0x18001a309  mov     rdi, [rax+50h]
0x18001a30d  mov     rbx, [rbp+3Fh+var_68]
0x18001a311  lea     rdx, aItems; "items"
0x18001a318  lea     rcx, [rbp+3Fh+string]; string
0x18001a31c  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18001a321  lea     r9, [rbp+3Fh+var_90]
0x18001a325  mov     r8, rbx
0x18001a328  mov     rdx, [rax]
0x18001a32b  mov     rcx, rsi
0x18001a32e  mov     rax, rdi
0x18001a331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a336  mov     rcx, [rbp+47h]; this
0x18001a33a  test    eax, eax
0x18001a33c  jns     short loc_18001A353
0x18001a33e  mov     r9d, eax; char *
0x18001a341  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001a348  mov     edx, 0D3h; void *
0x18001a34d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a353  mov     rax, [rbp+3Fh+var_80]
0x18001a357  mov     [rbp+3Fh+var_80], 0
0x18001a35f  mov     [r14], rax
0x18001a362  lea     rcx, [rbp+3Fh+var_78]
0x18001a366  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a36b  nop
0x18001a36c  lea     rcx, [rbp+3Fh+var_70]
0x18001a370  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a375  nop
0x18001a376  lea     rcx, [rbp+3Fh+var_68]
0x18001a37a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a37f  nop
0x18001a380  lea     rcx, [rbp+3Fh+var_88]
0x18001a384  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a389  nop
0x18001a38a  lea     rcx, [rbp+3Fh+var_80]
0x18001a38e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a393  mov     rcx, [rbp+3Fh+var_40]
0x18001a397  xor     rcx, rsp; StackCookie
0x18001a39a  call    __security_check_cookie
0x18001a39f  mov     rbx, [rsp+0D0h+arg_10]
0x18001a3a7  add     rsp, 0A0h
0x18001a3ae  pop     r15
0x18001a3b0  pop     r14
0x18001a3b2  pop     r13
0x18001a3b4  pop     r12
0x18001a3b6  pop     rdi
0x18001a3b7  pop     rsi
0x18001a3b8  pop     rbp
0x18001a3b9  retn
```
