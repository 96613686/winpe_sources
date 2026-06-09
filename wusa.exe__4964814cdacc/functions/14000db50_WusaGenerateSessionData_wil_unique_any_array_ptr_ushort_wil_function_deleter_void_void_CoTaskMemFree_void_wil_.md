# WusaGenerateSessionData(wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &,ushort * *)

- ea: `0x14000db50`
- end: `0x14000e279`
- name: `?WusaGenerateSessionData@@YAJAEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@PEAPEAG@Z`
- size: `1833`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f294`

## callees

- `0x140004d6c`
- `0x14000d434`
- `0x14000db50`
- `0x140013490`
- `0x1400148d6`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000e110`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e110`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000dc77`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000dd31`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000dc77`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000dd31`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000dc0b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000dc0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dd13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000de1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000de77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000df30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e00d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dc59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000dd13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000de1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000de77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000df30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000e00d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e15b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e15b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e107`

## string_xrefs

- `0x14000dc17`: `Failed to get activation factory for Windows.Data.Json.JsonValue`
- `0x14000e13f`: `Failed to activate instance of Windows.Data.Json.JsonObject`
- `0x14000e131`: `Failed to activate instance of Windows.Data.Json.JsonArray`
- `0x14000ddd2`: `Failed to query msu file path array as vector`
- `0x14000de43`: `Failed to create string value for ModuleId`
- `0x14000e05a`: `Failed to create string value for path %ls`
- `0x14000e049`: `Failed to append string value for path %ls`
- `0x14000dfd9`: `Failed to query msu file path array as value`
- `0x14000dd0c`: `Windows.Data.Json.JsonArray`
- `0x14000dc52`: `Windows.Data.Json.JsonObject`
- `0x14000dbe7`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall WusaGenerateSessionData(__int64 *a1, BSTR *a2)
{
  int ActivationFactory; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  __int64 (__fastcall ***v11)(__int64, GUID *, __int64 *); // rcx
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rcx
  __int64 *v16; // rbx
  __int64 v17; // rdi
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 (__fastcall ***v21)(__int64, GUID *, __int64 *); // rbx
  __int64 *v22; // r14
  __int64 (__fastcall **v23)(__int64, GUID *, __int64 *); // rdi
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  __int64 *v28; // rcx
  unsigned __int64 v29; // rdi
  __int64 *v30; // rcx
  __int64 *v31; // rbx
  __int64 v32; // r14
  __int64 v33; // rax
  unsigned __int64 v34; // rdx
  const WCHAR *v35; // rcx
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 *v39; // rcx
  _QWORD *v40; // rcx
  __int64 (__fastcall ***v41)(__int64, GUID *, __int64 *); // rbx
  __int64 *v42; // rsi
  __int64 (__fastcall **v43)(__int64, GUID *, __int64 *); // rdi
  HRESULT v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  __int64 v47; // rcx
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, HSTRING *); // rbx
  const OLECHAR *StringRawBuffer; // rax
  BSTR v51; // rax
  __int64 *v53; // [rsp+20h] [rbp-49h] BYREF
  __int64 (__fastcall ***v54)(__int64, GUID *, __int64 *); // [rsp+28h] [rbp-41h] BYREF
  __int64 (__fastcall ***v55)(__int64, GUID *, __int64 *); // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v56)(__int64, GUID *, __int64 *); // [rsp+38h] [rbp-31h] BYREF
  HSTRING v57; // [rsp+40h] [rbp-29h] BYREF
  __int64 v58; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v59; // [rsp+50h] [rbp-19h] BYREF
  __int64 v60; // [rsp+58h] [rbp-11h] BYREF
  __int64 *v61; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v62[2]; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF

  v61 = 0;
  v54 = 0;
  v60 = 0;
  v53 = 0;
  v59 = 0;
  v56 = 0;
  v58 = 0;
  v62[0] = 0;
  v62[1] = 0;
  v57 = 0;
  if ( !a2 )
  {
    WusaLogDebugEventA(L"WusaGenerateSessionData", 810, "sessionData cannot be null");
LABEL_3:
    ActivationFactory = -2147024882;
    goto LABEL_65;
  }
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v61);
  if ( ActivationFactory < 0 )
  {
    WusaLogDebugEventA(
      L"WusaGenerateSessionData",
      813,
      "Failed to get activation factory for Windows.Data.Json.JsonValue");
    goto LABEL_65;
  }
  v54 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  v54 = 0;
  v55 = 0;
  ActivationFactory = RoActivateInstance(string, &v55);
  if ( ActivationFactory < 0 )
    goto LABEL_64;
  if ( memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
  {
    ActivationFactory = (**v55)((__int64)v55, &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, (__int64 *)&v54);
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v55)[2])(v55);
    if ( ActivationFactory >= 0 )
      goto LABEL_12;
LABEL_64:
    WusaLogDebugEventA(L"WusaGenerateSessionData", 816, "Failed to activate instance of Windows.Data.Json.JsonObject");
    goto LABEL_65;
  }
  v54 = v55;
LABEL_12:
  v11 = v56;
  v56 = 0;
  if ( v11 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v11)[2])(v11);
  string = 0;
  v12 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  v56 = 0;
  v55 = 0;
  ActivationFactory = RoActivateInstance(string, &v55);
  if ( ActivationFactory < 0 )
    goto LABEL_63;
  if ( !memcmp_0(&GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
  {
    v56 = v55;
    goto LABEL_19;
  }
  ActivationFactory = (**v55)((__int64)v55, &GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81, (__int64 *)&v56);
  ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v55)[2])(v55);
  if ( ActivationFactory < 0 )
  {
LABEL_63:
    WusaLogDebugEventA(L"WusaGenerateSessionData", 819, "Failed to activate instance of Windows.Data.Json.JsonArray");
    goto LABEL_65;
  }
LABEL_19:
  v15 = v58;
  v58 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  ActivationFactory = (**v56)((__int64)v56, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v58);
  if ( ActivationFactory >= 0 )
  {
    v16 = v61;
    v17 = *v61;
    v53 = 0;
    string = 0;
    v18 = WindowsCreateStringReference(L"LocalServicingOffline", 0x15u, &hstringHeader, &string);
    if ( v18 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v17 + 80))(v16, string, &v53);
    if ( ActivationFactory >= 0 )
    {
      v21 = v54;
      v22 = v53;
      v23 = *v54;
      string = 0;
      v24 = WindowsCreateStringReference(L"ModuleId", 8u, &hstringHeader, &string);
      if ( v24 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
        __debugbreak();
      }
      ActivationFactory = v23[7]((__int64)v21, (GUID *)string, v22);
      if ( ActivationFactory >= 0 )
      {
        v28 = v53;
        v53 = 0;
        if ( v28 )
          (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
        if ( a1[1] )
        {
          v29 = 0;
          do
          {
            v30 = v53;
            v31 = v61;
            v32 = *v61;
            v53 = 0;
            if ( v30 )
              (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
            v33 = *a1;
            v34 = -1;
            string = 0;
            v35 = *(const WCHAR **)(v33 + 8 * v29);
            do
              ++v34;
            while ( v35[v34] );
            if ( v34 > 0xFFFFFFFF )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v34, v27);
              __debugbreak();
            }
            if ( (int)v34 + 1 < (unsigned int)v34 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v34, v27);
              JUMPOUT(0x14000E278LL);
            }
            v36 = WindowsCreateStringReference(v35, v34, &hstringHeader, &string);
            if ( v36 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
              __debugbreak();
            }
            ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v32 + 80))(
                                  v31,
                                  string,
                                  &v53);
            if ( ActivationFactory < 0 )
            {
              WusaLogDebugEventA(
                L"WusaGenerateSessionData",
                838,
                "Failed to create string value for path %ls",
                *(_QWORD *)(*a1 + 8 * v29));
              goto LABEL_65;
            }
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 104LL))(v58, v53);
            if ( ActivationFactory < 0 )
            {
              WusaLogDebugEventA(L"WusaGenerateSessionData", 841, "Failed to append string value for path %ls", v53);
              goto LABEL_65;
            }
            v39 = v53;
            v53 = 0;
            if ( v39 )
              (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
            ++v29;
          }
          while ( v29 < a1[1] );
          v40 = v59;
          v59 = 0;
          if ( v40 )
            (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
          ActivationFactory = (**v56)((__int64)v56, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64 *)&v59);
          if ( ActivationFactory < 0 )
          {
            WusaLogDebugEventA(L"WusaGenerateSessionData", 847, "Failed to query msu file path array as value");
            goto LABEL_65;
          }
          v41 = v54;
          v42 = v59;
          v43 = *v54;
          string = 0;
          v44 = WindowsCreateStringReference(L"LocalSources", 0xCu, &hstringHeader, &string);
          if ( v44 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
            __debugbreak();
          }
          ActivationFactory = v43[7]((__int64)v41, (GUID *)string, v42);
          if ( ActivationFactory < 0 )
          {
            WusaLogDebugEventA(L"WusaGenerateSessionData", 851, "Failed to set LocalSources in session data");
            goto LABEL_65;
          }
        }
        v47 = v60;
        v60 = 0;
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        ActivationFactory = (**v54)((__int64)v54, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v60);
        if ( ActivationFactory >= 0 )
        {
          v48 = v60;
          v49 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v60 + 56LL);
          WindowsDeleteString(v57);
          v57 = 0;
          ActivationFactory = v49(v48, &v57);
          if ( ActivationFactory >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v57, 0);
            v51 = SysAllocString(StringRawBuffer);
            if ( !v51 )
            {
              WusaLogDebugEventA(L"WusaGenerateSessionData", 871, "Failed to allocate BSTR for session data");
              goto LABEL_3;
            }
            *a2 = v51;
          }
          else
          {
            WusaLogDebugEventA(L"WusaGenerateSessionData", 858, "Failed to stringify session data");
          }
        }
        else
        {
          WusaLogDebugEventA(L"WusaGenerateSessionData", 855, "Failed to query session data object as value");
        }
      }
      else
      {
        WusaLogDebugEventA(L"WusaGenerateSessionData", 829, "Failed to set ModuleId in session data");
      }
    }
    else
    {
      WusaLogDebugEventA(L"WusaGenerateSessionData", 826, "Failed to create string value for ModuleId");
    }
  }
  else
  {
    WusaLogDebugEventA(L"WusaGenerateSessionData", 822, "Failed to query msu file path array as vector");
  }
LABEL_65:
  WindowsDeleteString(v57);
  v57 = 0;
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(v62);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v56 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v56)[2])(v56);
  if ( v59 )
    (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
  if ( v53 )
    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v54 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v54)[2])(v54);
  if ( v61 )
    (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x14000db50  mov     [rsp-8+arg_10], rbx
0x14000db55  mov     [rsp-8+arg_18], rsi
0x14000db5a  push    rbp
0x14000db5b  push    rdi
0x14000db5c  push    r12
0x14000db5e  push    r14
0x14000db60  push    r15
0x14000db62  lea     rbp, [rsp-37h]
0x14000db67  sub     rsp, 0A0h
0x14000db6e  mov     rax, cs:__security_cookie
0x14000db75  xor     rax, rsp
0x14000db78  mov     [rbp+57h+var_28], rax
0x14000db7c  xor     r12d, r12d
0x14000db7f  mov     r15, rdx
0x14000db82  mov     [rbp+57h+var_60], r12
0x14000db86  mov     rsi, rcx
0x14000db89  mov     [rbp+57h+var_98], r12
0x14000db8d  mov     [rbp+57h+var_68], r12
0x14000db91  mov     [rbp+57h+var_A0], r12
0x14000db95  mov     [rbp+57h+var_70], r12
0x14000db99  mov     [rbp+57h+var_88], r12
0x14000db9d  mov     [rbp+57h+var_78], r12
0x14000dba1  mov     [rbp+57h+var_58], r12
0x14000dba5  mov     [rbp+57h+var_50], r12
0x14000dba9  mov     [rbp+57h+var_80], r12
0x14000dbad  test    rdx, rdx
0x14000dbb0  jnz     short loc_14000DBD4
0x14000dbb2  lea     r8, aSessiondataCan; "sessionData cannot be null"
0x14000dbb9  mov     edx, 32Ah
0x14000dbbe  lea     rcx, aWusageneratese; "WusaGenerateSessionData"
0x14000dbc5  call    WusaLogDebugEventA
0x14000dbca  mov     ebx, 8007000Eh
0x14000dbcf  jmp     loc_14000E157
0x14000dbd4  mov     edi, 1Bh
0x14000dbd9  mov     [rbp+57h+string], r12
0x14000dbdd  mov     edx, edi; length
0x14000dbdf  lea     r9, [rbp+57h+string]; string
0x14000dbe3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000dbe7  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x14000dbee  call    cs:__imp_WindowsCreateStringReference
0x14000dbf4  test    eax, eax
0x14000dbf6  js      loc_14000E236
0x14000dbfc  mov     rcx, [rbp+57h+string]
0x14000dc00  lea     r8, [rbp+57h+var_60]
0x14000dc04  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x14000dc0b  call    cs:__imp_RoGetActivationFactory
0x14000dc11  mov     ebx, eax
0x14000dc13  test    eax, eax
0x14000dc15  jns     short loc_14000DC28
0x14000dc17  lea     r8, aFailedToGetAct; "Failed to get activation factory for Wi"...
0x14000dc1e  mov     edx, 32Dh
0x14000dc23  jmp     loc_14000E14B
0x14000dc28  mov     rcx, [rbp+57h+var_98]
0x14000dc2c  mov     [rbp+57h+var_98], r12
0x14000dc30  test    rcx, rcx
0x14000dc33  jz      short loc_14000DC41
0x14000dc35  mov     rax, [rcx]
0x14000dc38  mov     rax, [rax+10h]
0x14000dc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc41  lea     r9, [rbp+57h+string]; string
0x14000dc45  mov     [rbp+57h+string], r12
0x14000dc49  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000dc4d  mov     edx, 1Ch; length
0x14000dc52  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x14000dc59  call    cs:__imp_WindowsCreateStringReference
0x14000dc5f  test    eax, eax
0x14000dc61  js      loc_14000E23E
0x14000dc67  mov     rcx, [rbp+57h+string]
0x14000dc6b  lea     rdx, [rbp+57h+var_90]
0x14000dc6f  mov     [rbp+57h+var_98], r12
0x14000dc73  mov     [rbp+57h+var_90], r12
0x14000dc77  call    cs:__imp_RoActivateInstance
0x14000dc7d  mov     ebx, eax
0x14000dc7f  test    eax, eax
0x14000dc81  js      loc_14000E13F
0x14000dc87  mov     r14d, 10h
0x14000dc8d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14000dc94  mov     r8d, r14d; Size
0x14000dc97  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x14000dc9e  call    memcmp_0
0x14000dca3  test    eax, eax
0x14000dca5  jnz     short loc_14000DCB1
0x14000dca7  mov     rax, [rbp+57h+var_90]
0x14000dcab  mov     [rbp+57h+var_98], rax
0x14000dcaf  jmp     short loc_14000DCE5
0x14000dcb1  mov     rcx, [rbp+57h+var_90]
0x14000dcb5  lea     r8, [rbp+57h+var_98]
0x14000dcb9  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x14000dcc0  mov     rax, [rcx]
0x14000dcc3  mov     rax, [rax]
0x14000dcc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dccb  mov     rcx, [rbp+57h+var_90]
0x14000dccf  mov     ebx, eax
0x14000dcd1  mov     rax, [rcx]
0x14000dcd4  mov     rax, [rax+10h]
0x14000dcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcdd  test    ebx, ebx
0x14000dcdf  js      loc_14000E13F
0x14000dce5  mov     rcx, [rbp+57h+var_88]
0x14000dce9  mov     [rbp+57h+var_88], r12
0x14000dced  test    rcx, rcx
0x14000dcf0  jz      short loc_14000DCFE
0x14000dcf2  mov     rax, [rcx]
0x14000dcf5  mov     rax, [rax+10h]
0x14000dcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcfe  lea     r9, [rbp+57h+string]; string
0x14000dd02  mov     [rbp+57h+string], r12
0x14000dd06  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000dd0a  mov     edx, edi; length
0x14000dd0c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x14000dd13  call    cs:__imp_WindowsCreateStringReference
0x14000dd19  test    eax, eax
0x14000dd1b  js      loc_14000E246
0x14000dd21  mov     rcx, [rbp+57h+string]
0x14000dd25  lea     rdx, [rbp+57h+var_90]
0x14000dd29  mov     [rbp+57h+var_88], r12
0x14000dd2d  mov     [rbp+57h+var_90], r12
0x14000dd31  call    cs:__imp_RoActivateInstance
0x14000dd37  mov     ebx, eax
0x14000dd39  test    eax, eax
0x14000dd3b  js      loc_14000E131
0x14000dd41  mov     r8, r14; Size
0x14000dd44  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14000dd4b  lea     rcx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81; Buf1
0x14000dd52  call    memcmp_0
0x14000dd57  test    eax, eax
0x14000dd59  jnz     short loc_14000DD65
0x14000dd5b  mov     rax, [rbp+57h+var_90]
0x14000dd5f  mov     [rbp+57h+var_88], rax
0x14000dd63  jmp     short loc_14000DD99
0x14000dd65  mov     rcx, [rbp+57h+var_90]
0x14000dd69  lea     r8, [rbp+57h+var_88]
0x14000dd6d  lea     rdx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81
0x14000dd74  mov     rax, [rcx]
0x14000dd77  mov     rax, [rax]
0x14000dd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd7f  mov     rcx, [rbp+57h+var_90]
0x14000dd83  mov     ebx, eax
0x14000dd85  mov     rax, [rcx]
0x14000dd88  mov     rax, [rax+10h]
0x14000dd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd91  test    ebx, ebx
0x14000dd93  js      loc_14000E131
0x14000dd99  mov     rcx, [rbp+57h+var_78]
0x14000dd9d  mov     [rbp+57h+var_78], r12
0x14000dda1  test    rcx, rcx
0x14000dda4  jz      short loc_14000DDB2
0x14000dda6  mov     rax, [rcx]
0x14000dda9  mov     rax, [rax+10h]
0x14000ddad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddb2  mov     rcx, [rbp+57h+var_88]
0x14000ddb6  lea     r8, [rbp+57h+var_78]
0x14000ddba  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x14000ddc1  mov     rax, [rcx]
0x14000ddc4  mov     rax, [rax]
0x14000ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddcc  mov     ebx, eax
0x14000ddce  test    eax, eax
0x14000ddd0  jns     short loc_14000DDE3
0x14000ddd2  lea     r8, aFailedToQueryM; "Failed to query msu file path array as "...
0x14000ddd9  mov     edx, 336h
0x14000ddde  jmp     loc_14000E14B
0x14000dde3  mov     rcx, [rbp+57h+var_A0]
0x14000dde7  mov     rbx, [rbp+57h+var_60]
0x14000ddeb  mov     rdi, [rbx]
0x14000ddee  mov     [rbp+57h+var_A0], r12
0x14000ddf2  test    rcx, rcx
0x14000ddf5  jz      short loc_14000DE03
0x14000ddf7  mov     rax, [rcx]
0x14000ddfa  mov     rax, [rax+10h]
0x14000ddfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de03  lea     r9, [rbp+57h+string]; string
0x14000de07  mov     [rbp+57h+string], r12
0x14000de0b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000de0f  mov     edx, 15h; length
0x14000de14  lea     rcx, sourceString; "LocalServicingOffline"
0x14000de1b  call    cs:__imp_WindowsCreateStringReference
0x14000de21  test    eax, eax
0x14000de23  js      loc_14000E24E
0x14000de29  mov     rdx, [rbp+57h+string]
0x14000de2d  lea     r8, [rbp+57h+var_A0]
0x14000de31  mov     rax, [rdi+50h]
0x14000de35  mov     rcx, rbx
0x14000de38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de3d  mov     ebx, eax
0x14000de3f  test    eax, eax
0x14000de41  jns     short loc_14000DE54
0x14000de43  lea     r8, aFailedToCreate_7; "Failed to create string value for Modul"...
0x14000de4a  mov     edx, 33Ah
0x14000de4f  jmp     loc_14000E14B
0x14000de54  mov     rbx, [rbp+57h+var_98]
0x14000de58  lea     r9, [rbp+57h+string]; string
0x14000de5c  mov     r14, [rbp+57h+var_A0]
0x14000de60  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000de64  mov     edx, 8; length
0x14000de69  lea     rcx, aModuleid; "ModuleId"
0x14000de70  mov     rdi, [rbx]
0x14000de73  mov     [rbp+57h+string], r12
0x14000de77  call    cs:__imp_WindowsCreateStringReference
0x14000de7d  test    eax, eax
0x14000de7f  js      loc_14000E256
0x14000de85  mov     rdx, [rbp+57h+string]
0x14000de89  mov     r8, r14
0x14000de8c  mov     rax, [rdi+38h]
0x14000de90  mov     rcx, rbx
0x14000de93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de98  mov     ebx, eax
0x14000de9a  test    eax, eax
0x14000de9c  jns     short loc_14000DEAF
0x14000de9e  lea     r8, aFailedToSetMod; "Failed to set ModuleId in session data"
0x14000dea5  mov     edx, 33Dh
0x14000deaa  jmp     loc_14000E14B
0x14000deaf  mov     rcx, [rbp+57h+var_A0]
0x14000deb3  mov     [rbp+57h+var_A0], r12
0x14000deb7  test    rcx, rcx
0x14000deba  jz      short loc_14000DEC8
0x14000debc  mov     rax, [rcx]
0x14000debf  mov     rax, [rax+10h]
0x14000dec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dec8  cmp     qword ptr [rsi+8], 1
0x14000decd  jb      loc_14000E07B
0x14000ded3  mov     rdi, r12
0x14000ded6  mov     rcx, [rbp+57h+var_A0]
0x14000deda  mov     rbx, [rbp+57h+var_60]
0x14000dede  mov     r14, [rbx]
0x14000dee1  mov     [rbp+57h+var_A0], r12
0x14000dee5  test    rcx, rcx
0x14000dee8  jz      short loc_14000DEF6
0x14000deea  mov     rax, [rcx]
0x14000deed  mov     rax, [rax+10h]
0x14000def1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000def6  mov     rax, [rsi]
0x14000def9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000defd  mov     [rbp+57h+string], r12
0x14000df01  mov     rcx, [rax+rdi*8]; sourceString
0x14000df05  inc     rdx; int
0x14000df08  cmp     [rcx+rdx*2], r12w
0x14000df0d  jnz     short loc_14000DF05
0x14000df0f  mov     eax, 0FFFFFFFFh
0x14000df14  cmp     rdx, rax
0x14000df17  ja      loc_14000E22B
0x14000df1d  lea     eax, [rdx+1]
0x14000df20  cmp     eax, edx
0x14000df22  jb      loc_14000E26E
0x14000df28  lea     r9, [rbp+57h+string]; string
0x14000df2c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000df30  call    cs:__imp_WindowsCreateStringReference
0x14000df36  test    eax, eax
0x14000df38  js      loc_14000E266
0x14000df3e  mov     rdx, [rbp+57h+string]
0x14000df42  lea     r8, [rbp+57h+var_A0]
0x14000df46  mov     rax, [r14+50h]
0x14000df4a  mov     rcx, rbx
0x14000df4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df52  mov     ebx, eax
0x14000df54  test    eax, eax
0x14000df56  js      loc_14000E057
0x14000df5c  mov     rcx, [rbp+57h+var_78]
0x14000df60  mov     rdx, [rbp+57h+var_A0]
0x14000df64  mov     rax, [rcx]
0x14000df67  mov     rax, [rax+68h]
0x14000df6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df70  mov     ebx, eax
0x14000df72  test    eax, eax
0x14000df74  js      loc_14000E045
0x14000df7a  mov     rcx, [rbp+57h+var_A0]
0x14000df7e  mov     [rbp+57h+var_A0], r12
0x14000df82  test    rcx, rcx
0x14000df85  jz      short loc_14000DF93
0x14000df87  mov     rax, [rcx]
0x14000df8a  mov     rax, [rax+10h]
0x14000df8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df93  inc     rdi
0x14000df96  cmp     rdi, [rsi+8]
0x14000df9a  jb      loc_14000DED6
0x14000dfa0  mov     rcx, [rbp+57h+var_70]
0x14000dfa4  mov     [rbp+57h+var_70], r12
0x14000dfa8  test    rcx, rcx
0x14000dfab  jz      short loc_14000DFB9
0x14000dfad  mov     rax, [rcx]
0x14000dfb0  mov     rax, [rax+10h]
0x14000dfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfb9  mov     rcx, [rbp+57h+var_88]
0x14000dfbd  lea     r8, [rbp+57h+var_70]
0x14000dfc1  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x14000dfc8  mov     rax, [rcx]
0x14000dfcb  mov     rax, [rax]
0x14000dfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfd3  mov     ebx, eax
0x14000dfd5  test    eax, eax
0x14000dfd7  jns     short loc_14000DFEA
0x14000dfd9  lea     r8, aFailedToQueryM_0; "Failed to query msu file path array as "...
0x14000dfe0  mov     edx, 34Fh
0x14000dfe5  jmp     loc_14000E14B
0x14000dfea  mov     rbx, [rbp+57h+var_98]
0x14000dfee  lea     r9, [rbp+57h+string]; string
0x14000dff2  mov     rsi, [rbp+57h+var_70]
0x14000dff6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000dffa  mov     edx, 0Ch; length
0x14000dfff  lea     rcx, aLocalsources; "LocalSources"
  ... truncated ...
```
