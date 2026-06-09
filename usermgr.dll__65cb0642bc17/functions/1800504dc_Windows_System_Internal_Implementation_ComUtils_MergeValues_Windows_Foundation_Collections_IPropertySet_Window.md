# Windows::System::Internal::Implementation::ComUtils::MergeValues(Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,uchar *,std::function<bool (ushort const *)>)

- ea: `0x1800504dc`
- end: `0x180050a8b`
- name: `?MergeValues@ComUtils@Implementation@Internal@System@Windows@@SAJPEAUIPropertySet@Collections@Foundation@5@0PEAEV?$function@$$A6A_NPEBG@Z@std@@@Z`
- size: `1455`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800ba730`

## callees

- `0x18000ce48`
- `0x180019600`
- `0x180024828`
- `0x180040a04`
- `0x1800504dc`
- `0x180050c38`
- `0x180050c88`
- `0x1800510e8`
- `0x1800511c0`
- `0x180074aa0`
- `0x1800755e8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800507c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800507c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005075c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005075c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050a01`

## string_xrefs

- `0x18005055e`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800505b1`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800505f9`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050668`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800506c2`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800508b0`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800508d6`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800508fc`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x18005093e`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x180050968`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x18005098e`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800509b4`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x1800505cf`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_530)`
- `0x18005057c`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_528)`
- `0x180050686`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_537)`
- `0x180050617`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_532)`
- `0x1800509ce`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_546)`
- `0x1800506e0`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_538)`
- `0x180050982`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_548)`
- `0x1800509a8`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_547)`
- `0x1800508f0`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_561)`
- `0x180050916`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_558)`
- `0x18005095c`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_567)`
- `0x1800508ca`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_562)`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::System::Internal::Implementation::ComUtils::MergeValues(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64),
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64),
        bool *a3,
        __int64 a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  const wchar_t *v10; // r8
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, struct IInspectable **); // rbx
  int v25; // eax
  PCWSTR StringRawBuffer; // rax
  int v27; // eax
  int v28; // eax
  int IsEqualValue; // eax
  int v30; // eax
  __int64 v31; // rcx
  const wchar_t *v32; // r8
  __int64 v33; // rcx
  const wchar_t *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v38; // [rsp+20h] [rbp-49h]
  __int64 v39; // [rsp+28h] [rbp-41h] BYREF
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  struct IInspectable *v41; // [rsp+38h] [rbp-31h] BYREF
  __int64 v42; // [rsp+40h] [rbp-29h] BYREF
  int v43; // [rsp+48h] [rbp-21h] BYREF
  struct IInspectable *v44; // [rsp+50h] [rbp-19h] BYREF
  __int64 v45; // [rsp+58h] [rbp-11h] BYREF
  __int64 v46; // [rsp+60h] [rbp-9h] BYREF
  __int64 v47; // [rsp+68h] [rbp-1h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp+Fh] BYREF
  __int64 (__fastcall ***v50[8])(_QWORD, GUID *, __int64); // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  char v52; // [rsp+D0h] [rbp+67h] BYREF
  char v53; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int8 v54; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v55; // [rsp+E8h] [rbp+7Fh]

  v55 = a4;
  v50[0] = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v50);
  v49 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v49);
  v48 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v42 = 0;
  string = 0;
  v44 = 0;
  v43 = 0;
  LOBYTE(v38) = 0;
  *a3 = 0;
  v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v49,
         (__int64)&v48);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
      (const char *)(unsigned int)v7,
      v38);
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
      goto LABEL_54;
    v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_528)";
    goto LABEL_4;
  }
  v11 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          v50,
          (__int64)&v46);
  v8 = v11;
  if ( v11 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 72LL))(v48, &v45);
    v8 = v12;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 56LL))(v45, &v43);
      if ( v43 )
      {
        v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v45)(
                v45,
                &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204,
                &v47);
        v8 = v13;
        if ( v13 >= 0 )
        {
          v14 = v47;
          v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          v16 = v15(v14, &v42);
          v8 = v16;
          if ( v16 >= 0 )
          {
            v52 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 56LL))(v42, &v52);
            while ( (v8 & 0x80000000) == 0 )
            {
              if ( !v52 )
                goto LABEL_54;
              v39 = 0;
              v17 = v42;
              v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              v19 = v18(v17, &v39);
              v8 = v19;
              if ( v19 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x222,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                  (const char *)(unsigned int)v19,
                  v38);
                if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
                {
                  v34 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_546)";
LABEL_51:
                  McTemplateU0zd_EventWriteTransfer(v33, LogWarning, v34, v8);
                }
LABEL_52:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                goto LABEL_54;
              }
              v20 = v39;
              v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
              WindowsDeleteString(string);
              string = 0;
              v22 = v21(v20, &string);
              v8 = v22;
              if ( v22 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x223,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                  (const char *)(unsigned int)v22,
                  v38);
                if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
                {
                  v34 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_547)";
                  goto LABEL_51;
                }
                goto LABEL_52;
              }
              v23 = v39;
              v24 = *(__int64 (__fastcall **)(__int64, struct IInspectable **))(*(_QWORD *)v39 + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
              v25 = v24(v23, &v44);
              v8 = v25;
              if ( v25 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x224,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                  (const char *)(unsigned int)v25,
                  v38);
                if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
                {
                  v34 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_548)";
                  goto LABEL_51;
                }
                goto LABEL_52;
              }
              if ( !*(_QWORD *)(a4 + 24)
                || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
                    (unsigned __int8)std::_Func_class<bool,unsigned short const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
                                       a4,
                                       StringRawBuffer)) )
              {
                if ( !*a3 )
                {
                  v54 = 0;
                  v53 = 0;
                  v41 = 0;
                  v27 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v46 + 64LL))(v46, string, &v53);
                  v8 = v27;
                  if ( v27 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x22E,
                      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                      (const char *)(unsigned int)v27,
                      v38);
                    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
                      goto LABEL_42;
                    v32 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_558)";
                    goto LABEL_41;
                  }
                  if ( v53 )
                  {
                    v28 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<IInspectable *>(
                            v46,
                            (__int64)string,
                            &v41);
                    v8 = v28;
                    if ( v28 < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x231,
                        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                        (const char *)(unsigned int)v28,
                        v38);
                      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) == 0 )
                        goto LABEL_42;
                      v32 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_561)";
LABEL_41:
                      McTemplateU0zd_EventWriteTransfer(v31, LogWarning, v32, v8);
                      goto LABEL_42;
                    }
                    IsEqualValue = Windows::System::Internal::Implementation::ComUtils::IsEqualValue(v41, v44, &v54);
                    v8 = IsEqualValue;
                    if ( IsEqualValue < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x232,
                        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                        (const char *)(unsigned int)IsEqualValue,
                        v38);
                      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
                      {
                        v32 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_562)";
                        goto LABEL_41;
                      }
LABEL_42:
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                      goto LABEL_52;
                    }
                    *a3 = v54 == 0;
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                }
                v30 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<IInspectable *>(v46);
                v8 = v30;
                if ( v30 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x237,
                    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
                    (const char *)(unsigned int)v30,
                    v38);
                  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
                  {
                    v34 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_567)";
                    goto LABEL_51;
                  }
                  goto LABEL_52;
                }
              }
              v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 64LL))(v42, &v52);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
            }
            v8 = 0;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21A,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
              (const char *)(unsigned int)v16,
              v38);
            if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
            {
              v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_538)";
              goto LABEL_4;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x219,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v13,
            v38);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
          {
            v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_537)";
            goto LABEL_4;
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x214,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
        (const char *)(unsigned int)v12,
        v38);
      if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
      {
        v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_532)";
        goto LABEL_4;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
      (const char *)(unsigned int)v11,
      v38);
    if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
    {
      v10 = L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_530)";
LABEL_4:
      McTemplateU0zd_EventWriteTransfer(v9, LogWarning, v10, v8);
    }
  }
LABEL_54:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  v35 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v50);
  std::function<bool (unsigned short const *,IInspectable *)>::~function<bool (unsigned short const *,IInspectable *)>(a4);
  return v8;
}

```

## disassembly

```asm
0x1800504dc  mov     [rsp-8+arg_18], r9
0x1800504e1  push    rbp
0x1800504e2  push    rbx
0x1800504e3  push    rsi
0x1800504e4  push    rdi
0x1800504e5  push    r14
0x1800504e7  push    r15
0x1800504e9  lea     rbp, [rsp-2Fh]
0x1800504ee  sub     rsp, 98h
0x1800504f5  mov     r14, r9
0x1800504f8  mov     rsi, r8
0x1800504fb  mov     rbx, rdx
0x1800504fe  mov     [rbp+57h+var_40], rcx
0x180050502  lea     rcx, [rbp+57h+var_40]
0x180050506  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005050b  nop
0x18005050c  mov     [rbp+57h+var_48], rbx
0x180050510  lea     rcx, [rbp+57h+var_48]
0x180050514  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180050519  nop
0x18005051a  xor     r15d, r15d
0x18005051d  mov     [rbp+57h+var_50], r15
0x180050521  mov     [rbp+57h+var_60], r15
0x180050525  mov     [rbp+57h+var_68], r15
0x180050529  mov     [rbp+57h+var_58], r15
0x18005052d  mov     [rbp+57h+var_80], r15
0x180050531  mov     [rbp+57h+string], r15
0x180050535  mov     [rbp+57h+var_70], r15
0x180050539  mov     [rbp+57h+var_78], r15d
0x18005053d  mov     [rbp+57h+var_A0], r15b
0x180050541  mov     [rsi], r15b
0x180050544  lea     rdx, [rbp+57h+var_50]
0x180050548  lea     rcx, [rbp+57h+var_48]
0x18005054c  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180050551  mov     ebx, eax
0x180050553  mov     rcx, [rbp+5Fh]; this
0x180050557  test    eax, eax
0x180050559  jns     short loc_180050597
0x18005055b  mov     r9d, eax; char *
0x18005055e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050565  mov     edx, 210h; void *
0x18005056a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005056f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050576  jz      loc_1800509F3
0x18005057c  lea     r8, aIfcOnecoreDsSe_21; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050583  mov     r9d, ebx
0x180050586  lea     rdx, LogWarning
0x18005058d  call    McTemplateU0zd_EventWriteTransfer
0x180050592  jmp     loc_1800509F3
0x180050597  lea     rdx, [rbp+57h+var_60]
0x18005059b  lea     rcx, [rbp+57h+var_40]
0x18005059f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800505a4  mov     ebx, eax
0x1800505a6  mov     rcx, [rbp+5Fh]; this
0x1800505aa  test    eax, eax
0x1800505ac  jns     short loc_1800505D8
0x1800505ae  mov     r9d, eax; char *
0x1800505b1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x1800505b8  mov     edx, 212h; void *
0x1800505bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800505c2  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x1800505c9  jz      loc_1800509F3
0x1800505cf  lea     r8, aIfcOnecoreDsSe_52; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800505d6  jmp     short loc_180050583
0x1800505d8  mov     rcx, [rbp+57h+var_50]
0x1800505dc  mov     rax, [rcx]
0x1800505df  lea     rdx, [rbp+57h+var_68]
0x1800505e3  mov     rax, [rax+48h]
0x1800505e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505ec  mov     ebx, eax
0x1800505ee  mov     rcx, [rbp+5Fh]; this
0x1800505f2  test    eax, eax
0x1800505f4  jns     short loc_180050623
0x1800505f6  mov     r9d, eax; char *
0x1800505f9  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050600  mov     edx, 214h; void *
0x180050605  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005060a  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050611  jz      loc_1800509F3
0x180050617  lea     r8, aIfcOnecoreDsSe_19; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18005061e  jmp     loc_180050583
0x180050623  mov     rcx, [rbp+57h+var_68]
0x180050627  mov     rax, [rcx]
0x18005062a  lea     rdx, [rbp+57h+var_78]
0x18005062e  mov     rax, [rax+38h]
0x180050632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050637  cmp     [rbp+57h+var_78], r15d
0x18005063b  jbe     loc_1800509F3
0x180050641  mov     rcx, [rbp+57h+var_68]
0x180050645  mov     rax, [rcx]
0x180050648  lea     r8, [rbp+57h+var_58]
0x18005064c  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x180050653  mov     rax, [rax]
0x180050656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005065b  mov     ebx, eax
0x18005065d  mov     rcx, [rbp+5Fh]; this
0x180050661  test    eax, eax
0x180050663  jns     short loc_180050692
0x180050665  mov     r9d, eax; char *
0x180050668  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x18005066f  mov     edx, 219h; void *
0x180050674  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050679  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050680  jz      loc_1800509F3
0x180050686  lea     r8, aIfcOnecoreDsSe_56; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18005068d  jmp     loc_180050583
0x180050692  mov     rdi, [rbp+57h+var_58]
0x180050696  mov     rax, [rdi]
0x180050699  mov     rbx, [rax+30h]
0x18005069d  lea     rcx, [rbp+57h+var_80]
0x1800506a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800506a6  lea     rdx, [rbp+57h+var_80]
0x1800506aa  mov     rcx, rdi
0x1800506ad  mov     rax, rbx
0x1800506b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506b5  mov     ebx, eax
0x1800506b7  mov     rcx, [rbp+5Fh]; this
0x1800506bb  test    eax, eax
0x1800506bd  jns     short loc_1800506EC
0x1800506bf  mov     r9d, eax; char *
0x1800506c2  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x1800506c9  mov     edx, 21Ah; void *
0x1800506ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800506d3  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x1800506da  jz      loc_1800509F3
0x1800506e0  lea     r8, aIfcOnecoreDsSe_54; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800506e7  jmp     loc_180050583
0x1800506ec  mov     [rbp+57h+arg_0], r15b
0x1800506f0  mov     rcx, [rbp+57h+var_80]
0x1800506f4  mov     rax, [rcx]
0x1800506f7  lea     rdx, [rbp+57h+arg_0]
0x1800506fb  mov     rax, [rax+38h]
0x1800506ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050704  mov     ebx, eax
0x180050706  test    ebx, ebx
0x180050708  js      loc_1800509F0
0x18005070e  cmp     [rbp+57h+arg_0], r15b
0x180050712  jz      loc_1800509F3
0x180050718  mov     [rbp+57h+var_98], r15
0x18005071c  mov     rdi, [rbp+57h+var_80]
0x180050720  mov     rax, [rdi]
0x180050723  mov     rbx, [rax+30h]
0x180050727  lea     rcx, [rbp+57h+var_98]
0x18005072b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050730  lea     rdx, [rbp+57h+var_98]
0x180050734  mov     rcx, rdi
0x180050737  mov     rax, rbx
0x18005073a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005073f  mov     ebx, eax
0x180050741  mov     rcx, [rbp+5Fh]; this
0x180050745  test    eax, eax
0x180050747  js      loc_1800509B1
0x18005074d  mov     rdi, [rbp+57h+var_98]
0x180050751  mov     rax, [rdi]
0x180050754  mov     rbx, [rax+30h]
0x180050758  mov     rcx, [rbp+57h+string]; string
0x18005075c  call    cs:__imp_WindowsDeleteString
0x180050762  mov     [rbp+57h+string], r15
0x180050766  lea     rdx, [rbp+57h+string]
0x18005076a  mov     rcx, rdi
0x18005076d  mov     rax, rbx
0x180050770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050775  mov     ebx, eax
0x180050777  mov     rcx, [rbp+5Fh]; this
0x18005077b  test    eax, eax
0x18005077d  js      loc_18005098B
0x180050783  mov     rdi, [rbp+57h+var_98]
0x180050787  mov     rax, [rdi]
0x18005078a  mov     rbx, [rax+38h]
0x18005078e  lea     rcx, [rbp+57h+var_70]
0x180050792  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050797  lea     rdx, [rbp+57h+var_70]
0x18005079b  mov     rcx, rdi
0x18005079e  mov     rax, rbx
0x1800507a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507a6  mov     ebx, eax
0x1800507a8  mov     rcx, [rbp+5Fh]; this
0x1800507ac  test    eax, eax
0x1800507ae  js      loc_180050965
0x1800507b4  cmp     [r14+18h], r15
0x1800507b8  jz      short loc_1800507D9
0x1800507ba  xor     edx, edx; length
0x1800507bc  mov     rcx, [rbp+57h+string]; string
0x1800507c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800507c6  mov     rdx, rax
0x1800507c9  mov     rcx, r14
0x1800507cc  call    ??R?$_Func_class@_NPEBGU_Nil@std@@U12@U12@U12@U12@U12@@std@@QEBA_NPEBG@Z; std::_Func_class<bool,ushort const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(ushort const *)
0x1800507d1  test    al, al
0x1800507d3  jz      loc_180050889
0x1800507d9  cmp     [rsi], r15b
0x1800507dc  jnz     loc_180050866
0x1800507e2  mov     [rbp+57h+arg_10], r15b
0x1800507e6  mov     [rbp+57h+arg_8], r15b
0x1800507ea  mov     [rbp+57h+var_88], r15
0x1800507ee  mov     rcx, [rbp+57h+var_60]
0x1800507f2  mov     rax, [rcx]
0x1800507f5  lea     r8, [rbp+57h+arg_8]
0x1800507f9  mov     rdx, [rbp+57h+string]
0x1800507fd  mov     rax, [rax+40h]
0x180050801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050806  mov     ebx, eax
0x180050808  mov     rcx, [rbp+5Fh]; this
0x18005080c  test    eax, eax
0x18005080e  js      loc_1800508F9
0x180050814  cmp     [rbp+57h+arg_8], r15b
0x180050818  jz      short loc_18005085D
0x18005081a  lea     r8, [rbp+57h+var_88]
0x18005081e  mov     rdx, [rbp+57h+string]
0x180050822  mov     rcx, [rbp+57h+var_60]
0x180050826  call    ??$FromPropertyMap@PEAUIInspectable@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAUIInspectable@@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<IInspectable *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,IInspectable * *)
0x18005082b  mov     ebx, eax
0x18005082d  mov     rcx, [rbp+5Fh]; this
0x180050831  test    eax, eax
0x180050833  js      loc_1800508D3
0x180050839  lea     r8, [rbp+57h+arg_10]; unsigned __int8 *
0x18005083d  mov     rdx, [rbp+57h+var_70]; struct IInspectable *
0x180050841  mov     rcx, [rbp+57h+var_88]; struct IInspectable *
0x180050845  call    ?IsEqualValue@ComUtils@Implementation@Internal@System@Windows@@SAJPEAUIInspectable@@0PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IsEqualValue(IInspectable *,IInspectable *,uchar *)
0x18005084a  mov     ebx, eax
0x18005084c  mov     rcx, [rbp+5Fh]; this
0x180050850  test    eax, eax
0x180050852  js      short loc_1800508AD
0x180050854  cmp     [rbp+57h+arg_10], r15b
0x180050858  setz    al
0x18005085b  mov     [rsi], al
0x18005085d  lea     rcx, [rbp+57h+var_88]
0x180050861  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050866  lea     r9, [rbp+57h+var_A0]
0x18005086a  mov     r8, [rbp+57h+var_70]
0x18005086e  mov     rdx, [rbp+57h+string]
0x180050872  mov     rcx, [rbp+57h+var_60]
0x180050876  call    ??$IntoPropertyMap@PEAUIInspectable@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<IInspectable *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,IInspectable *,uchar *)
0x18005087b  mov     ebx, eax
0x18005087d  mov     rcx, [rbp+5Fh]; this
0x180050881  test    eax, eax
0x180050883  js      loc_18005093B
0x180050889  mov     rcx, [rbp+57h+var_80]
0x18005088d  mov     rax, [rcx]
0x180050890  lea     rdx, [rbp+57h+arg_0]
0x180050894  mov     rax, [rax+40h]
0x180050898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005089d  mov     ebx, eax
0x18005089f  lea     rcx, [rbp+57h+var_98]
0x1800508a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800508a8  jmp     loc_180050706
0x1800508ad  mov     r9d, ebx; char *
0x1800508b0  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x1800508b7  mov     edx, 232h; void *
0x1800508bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800508c1  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x1800508c8  jz      short loc_18005092D
0x1800508ca  lea     r8, aIfcOnecoreDsSe_2; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800508d1  jmp     short loc_18005091D
0x1800508d3  mov     r9d, ebx; char *
0x1800508d6  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x1800508dd  mov     edx, 231h; void *
0x1800508e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800508e7  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x1800508ee  jz      short loc_18005092D
0x1800508f0  lea     r8, aIfcOnecoreDsSe_34; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800508f7  jmp     short loc_18005091D
0x1800508f9  mov     r9d, ebx; char *
0x1800508fc  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050903  mov     edx, 22Eh; void *
0x180050908  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005090d  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050914  jz      short loc_18005092D
0x180050916  lea     r8, aIfcOnecoreDsSe_40; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18005091d  mov     r9d, ebx
0x180050920  lea     rdx, LogWarning
0x180050927  call    McTemplateU0zd_EventWriteTransfer
0x18005092c  nop
0x18005092d  lea     rcx, [rbp+57h+var_88]
0x180050931  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050936  jmp     loc_1800509E5
0x18005093b  mov     r9d, ebx; char *
0x18005093e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050945  mov     edx, 237h; void *
0x18005094a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005094f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050956  jz      loc_1800509E5
0x18005095c  lea     r8, aIfcOnecoreDsSe_47; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050963  jmp     short loc_1800509D5
0x180050965  mov     r9d, ebx; char *
0x180050968  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x18005096f  mov     edx, 224h; void *
0x180050974  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050979  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x180050980  jz      short loc_1800509E5
0x180050982  lea     r8, aIfcOnecoreDsSe_4; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x180050989  jmp     short loc_1800509D5
0x18005098b  mov     r9d, ebx; char *
0x18005098e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x180050995  mov     edx, 223h; void *
0x18005099a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005099f  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x1800509a6  jz      short loc_1800509E5
0x1800509a8  lea     r8, aIfcOnecoreDsSe_20; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x1800509af  jmp     short loc_1800509D5
0x1800509b1  mov     r9d, ebx; char *
  ... truncated ...
```
