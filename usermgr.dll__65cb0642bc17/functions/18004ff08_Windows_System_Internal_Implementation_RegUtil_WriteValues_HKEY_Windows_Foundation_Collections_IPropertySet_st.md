# Windows::System::Internal::Implementation::RegUtil::WriteValues(HKEY__ *,Windows::Foundation::Collections::IPropertySet *,std::function<bool (ushort const *,IInspectable *)>)

- ea: `0x18004ff08`
- end: `0x180050259`
- name: `?WriteValues@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEAUIPropertySet@Collections@Foundation@5@V?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@@Z`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800cf450`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180019600`
- `0x180024828`
- `0x18004bfc0`
- `0x18004ff08`
- `0x180050c38`
- `0x18006baa0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800500b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005019a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800500b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005019a`

## string_xrefs

- `0x18004ff6b`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ff9c`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004fff2`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x180050032`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18005021d`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x180050232`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x180050247`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::WriteValues(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64),
        __int64 a3)
{
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rbx
  PCWSTR v22; // rax
  int v23; // ebx
  __int64 v24; // rcx
  __int64 v25; // rcx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v28; // [rsp+28h] [rbp-48h] BYREF
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  __int64 v30; // [rsp+38h] [rbp-38h] BYREF
  __int64 v31; // [rsp+40h] [rbp-30h] BYREF
  __int64 v32; // [rsp+48h] [rbp-28h] BYREF
  __int64 v33; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-18h] BYREF
  __int64 v35; // [rsp+60h] [rbp-10h] BYREF
  PCWSTR StringRawBuffer; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char v38; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v39; // [rsp+B0h] [rbp+40h]
  int v40; // [rsp+B8h] [rbp+48h] BYREF

  v39 = a3;
  v34 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v34);
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  string = 0;
  v30 = 0;
  v40 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v34,
         (__int64)&v33);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)(unsigned int)v5,
      (int)string);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 72LL))(v33, &v31);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)(unsigned int)v6,
      (int)string);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v40);
  if ( v40 )
  {
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v31)(
           v31,
           &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204,
           &v32);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v7,
        (int)string);
    v8 = v32;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v10 = v9(v8, &v28);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v10,
        (int)string);
    v38 = 0;
    if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v28 + 56LL))(v28, &v38) >= 0 )
    {
      do
      {
        if ( !v38 )
          break;
        v29 = 0;
        v11 = v28;
        v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
        v13 = v12(v11, &v29);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v13,
            (int)string);
        v14 = v29;
        v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v16 = v15(v14, &string);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x181,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v16,
            (int)string);
        v17 = v29;
        v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        v19 = v18(v17, &v30);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v19,
            (int)string);
        if ( !*(_QWORD *)(a3 + 24) )
          goto LABEL_18;
        v35 = v30;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v20 = *(_QWORD *)(a3 + 24);
        if ( !v20 )
          std::_Xbad_function_call();
        if ( (*(unsigned __int8 (__fastcall **)(__int64, PCWSTR *, __int64 *))(*(_QWORD *)v20 + 16LL))(
               v20,
               &StringRawBuffer,
               &v35) )
        {
LABEL_18:
          v21 = v30;
          v22 = WindowsGetStringRawBuffer(string, 0);
          Windows::System::Internal::Implementation::RegUtil::WriteValue<IInspectable *>(a1, v22, v21);
        }
        v23 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v28 + 64LL))(v28, &v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      }
      while ( v23 >= 0 );
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  std::function<bool (unsigned short const *,IInspectable *)>::~function<bool (unsigned short const *,IInspectable *)>(a3);
  return 0;
}

```

## disassembly

```asm
0x18004ff08  mov     [rsp-28h+arg_0], rbx
0x18004ff0d  mov     [rsp-28h+arg_10], r8
0x18004ff12  push    rbp
0x18004ff13  push    rsi
0x18004ff14  push    rdi
0x18004ff15  push    r14
0x18004ff17  push    r15
0x18004ff19  mov     rbp, rsp
0x18004ff1c  sub     rsp, 70h
0x18004ff20  mov     rsi, r8
0x18004ff23  mov     r14, rcx
0x18004ff26  mov     [rbp+var_18], rdx
0x18004ff2a  lea     rcx, [rbp+var_18]
0x18004ff2e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18004ff33  nop
0x18004ff34  xor     r15d, r15d
0x18004ff37  mov     [rbp+var_20], r15
0x18004ff3b  mov     [rbp+var_30], r15
0x18004ff3f  mov     [rbp+var_28], r15
0x18004ff43  mov     [rbp+var_48], r15
0x18004ff47  mov     [rbp+string], r15
0x18004ff4b  mov     [rbp+var_38], r15
0x18004ff4f  mov     [rbp+arg_18], r15d
0x18004ff53  lea     rdx, [rbp+var_20]
0x18004ff57  lea     rcx, [rbp+var_18]
0x18004ff5b  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18004ff60  mov     rcx, [rbp+28h]; this
0x18004ff64  test    eax, eax
0x18004ff66  jns     short loc_18004FF7D
0x18004ff68  mov     r9d, eax; char *
0x18004ff6b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ff72  mov     edx, 170h; void *
0x18004ff77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ff7d  mov     rcx, [rbp+var_20]
0x18004ff81  mov     rax, [rcx]
0x18004ff84  lea     rdx, [rbp+var_30]
0x18004ff88  mov     rax, [rax+48h]
0x18004ff8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff91  mov     rcx, [rbp+28h]; this
0x18004ff95  test    eax, eax
0x18004ff97  jns     short loc_18004FFAE
0x18004ff99  mov     r9d, eax; char *
0x18004ff9c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ffa3  mov     edx, 172h; void *
0x18004ffa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ffae  mov     rcx, [rbp+var_30]
0x18004ffb2  mov     rax, [rcx]
0x18004ffb5  lea     rdx, [rbp+arg_18]
0x18004ffb9  mov     rax, [rax+38h]
0x18004ffbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffc2  cmp     [rbp+arg_18], r15d
0x18004ffc6  jbe     loc_18005018C
0x18004ffcc  mov     rcx, [rbp+var_30]
0x18004ffd0  mov     rax, [rcx]
0x18004ffd3  lea     r8, [rbp+var_28]
0x18004ffd7  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18004ffde  mov     rax, [rax]
0x18004ffe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffe6  nop
0x18004ffe7  mov     rcx, [rbp+28h]; this
0x18004ffeb  test    eax, eax
0x18004ffed  jns     short loc_180050004
0x18004ffef  mov     r9d, eax; char *
0x18004fff2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004fff9  mov     edx, 177h; void *
0x18004fffe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050004  mov     rdi, [rbp+var_28]
0x180050008  mov     rax, [rdi]
0x18005000b  mov     rbx, [rax+30h]
0x18005000f  lea     rcx, [rbp+var_48]
0x180050013  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050018  lea     rdx, [rbp+var_48]
0x18005001c  mov     rcx, rdi
0x18005001f  mov     rax, rbx
0x180050022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050027  mov     rcx, [rbp+28h]; this
0x18005002b  test    eax, eax
0x18005002d  jns     short loc_180050044
0x18005002f  mov     r9d, eax; char *
0x180050032  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x180050039  mov     edx, 178h; void *
0x18005003e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050044  mov     [rbp+arg_8], r15b
0x180050048  mov     rcx, [rbp+var_48]
0x18005004c  mov     rax, [rcx]
0x18005004f  lea     rdx, [rbp+arg_8]
0x180050053  mov     rax, [rax+38h]
0x180050057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005005c  test    eax, eax
0x18005005e  js      loc_18005018C
0x180050064  cmp     [rbp+arg_8], r15b
0x180050068  jz      loc_18005018C
0x18005006e  mov     [rbp+var_40], r15
0x180050072  mov     rdi, [rbp+var_48]
0x180050076  mov     rax, [rdi]
0x180050079  mov     rbx, [rax+30h]
0x18005007d  lea     rcx, [rbp+var_40]
0x180050081  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050086  lea     rdx, [rbp+var_40]
0x18005008a  mov     rcx, rdi
0x18005008d  mov     rax, rbx
0x180050090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050095  mov     rcx, [rbp+28h]; this
0x180050099  test    eax, eax
0x18005009b  js      loc_180050244
0x1800500a1  mov     rdi, [rbp+var_40]
0x1800500a5  mov     rax, [rdi]
0x1800500a8  mov     rbx, [rax+30h]
0x1800500ac  mov     rcx, [rbp+string]; string
0x1800500b0  call    cs:__imp_WindowsDeleteString
0x1800500b6  mov     [rbp+string], r15
0x1800500ba  lea     rdx, [rbp+string]
0x1800500be  mov     rcx, rdi
0x1800500c1  mov     rax, rbx
0x1800500c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500c9  mov     rcx, [rbp+28h]; this
0x1800500cd  test    eax, eax
0x1800500cf  js      loc_18005022F
0x1800500d5  mov     rdi, [rbp+var_40]
0x1800500d9  mov     rax, [rdi]
0x1800500dc  mov     rbx, [rax+38h]
0x1800500e0  lea     rcx, [rbp+var_38]
0x1800500e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800500e9  lea     rdx, [rbp+var_38]
0x1800500ed  mov     rcx, rdi
0x1800500f0  mov     rax, rbx
0x1800500f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500f8  mov     rcx, [rbp+28h]; this
0x1800500fc  test    eax, eax
0x1800500fe  js      loc_18005021A
0x180050104  cmp     [rsi+18h], r15
0x180050108  jz      short loc_180050147
0x18005010a  mov     rax, [rbp+var_38]
0x18005010e  mov     [rbp+var_10], rax
0x180050112  xor     edx, edx; length
0x180050114  mov     rcx, [rbp+string]; string
0x180050118  call    cs:__imp_WindowsGetStringRawBuffer
0x18005011e  mov     [rbp+var_8], rax
0x180050122  mov     rcx, [rsi+18h]
0x180050126  test    rcx, rcx
0x180050129  jz      loc_180050214
0x18005012f  mov     rax, [rcx]
0x180050132  lea     r8, [rbp+var_10]
0x180050136  lea     rdx, [rbp+var_8]
0x18005013a  mov     rax, [rax+10h]
0x18005013e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050143  test    al, al
0x180050145  jz      short loc_180050165
0x180050147  mov     rbx, [rbp+var_38]
0x18005014b  xor     edx, edx; length
0x18005014d  mov     rcx, [rbp+string]; string
0x180050151  call    cs:__imp_WindowsGetStringRawBuffer
0x180050157  mov     r8, rbx
0x18005015a  mov     rdx, rax
0x18005015d  mov     rcx, r14
0x180050160  call    ??$WriteValue@PEAUIInspectable@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUIInspectable@@@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<IInspectable *>(HKEY__ *,ushort const *,IInspectable *)
0x180050165  mov     rcx, [rbp+var_48]
0x180050169  mov     rax, [rcx]
0x18005016c  lea     rdx, [rbp+arg_8]
0x180050170  mov     rax, [rax+40h]
0x180050174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050179  mov     ebx, eax
0x18005017b  lea     rcx, [rbp+var_40]
0x18005017f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050184  test    ebx, ebx
0x180050186  jns     loc_180050064
0x18005018c  lea     rcx, [rbp+var_38]
0x180050190  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050195  nop
0x180050196  mov     rcx, [rbp+string]; string
0x18005019a  call    cs:__imp_WindowsDeleteString
0x1800501a0  mov     [rbp+string], r15
0x1800501a4  lea     rcx, [rbp+var_48]
0x1800501a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800501ad  nop
0x1800501ae  mov     rcx, [rbp+var_28]
0x1800501b2  test    rcx, rcx
0x1800501b5  jz      short loc_1800501C8
0x1800501b7  mov     [rbp+var_28], r15
0x1800501bb  mov     rax, [rcx]
0x1800501be  mov     rax, [rax+10h]
0x1800501c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501c7  nop
0x1800501c8  mov     rcx, [rbp+var_30]
0x1800501cc  test    rcx, rcx
0x1800501cf  jz      short loc_1800501E2
0x1800501d1  mov     [rbp+var_30], r15
0x1800501d5  mov     rax, [rcx]
0x1800501d8  mov     rax, [rax+10h]
0x1800501dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501e1  nop
0x1800501e2  lea     rcx, [rbp+var_20]
0x1800501e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800501eb  nop
0x1800501ec  lea     rcx, [rbp+var_18]
0x1800501f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800501f5  nop
0x1800501f6  mov     rcx, rsi
0x1800501f9  call    ??1?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@QEAA@XZ; std::function<bool (ushort const *,IInspectable *)>::~function<bool (ushort const *,IInspectable *)>(void)
0x1800501fe  xor     eax, eax
0x180050200  mov     rbx, [rsp+70h+arg_0]
0x180050208  add     rsp, 70h
0x18005020c  pop     r15
0x18005020e  pop     r14
0x180050210  pop     rdi
0x180050211  pop     rsi
0x180050212  pop     rbp
0x180050213  retn
0x180050214  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005021a  mov     r9d, eax; char *
0x18005021d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x180050224  mov     edx, 182h; void *
0x180050229  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005022f  mov     r9d, eax; char *
0x180050232  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x180050239  mov     edx, 181h; void *
0x18005023e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050244  mov     r9d, eax; char *
0x180050247  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18005024e  mov     edx, 180h; void *
0x180050253  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
