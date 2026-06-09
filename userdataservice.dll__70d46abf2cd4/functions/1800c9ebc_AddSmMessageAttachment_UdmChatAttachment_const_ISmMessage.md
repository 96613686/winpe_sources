# AddSmMessageAttachment(UdmChatAttachment const *,ISmMessage *)

- ea: `0x1800c9ebc`
- end: `0x1800ca333`
- name: `?AddSmMessageAttachment@@YAJPEBUUdmChatAttachment@@PEAUISmMessage@@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(const struct UdmChatAttachment *, struct ISmMessage *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d51a0`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035040`
- `0x180035c40`
- `0x18003cda4`
- `0x18003ed7c`
- `0x180049f80`
- `0x180075f98`
- `0x18009e71c`
- `0x1800c9ebc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_GetFileExtensionFromContentType` at `0x1800c9fb9`
- `MessagingDataModel2!Messaging_GetFileExtensionFromContentType` at `0x1800c9fb9`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800ca131`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800ca1a3`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800ca131`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800ca1a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca1fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca23b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca1fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca23b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c9f6b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c9f6b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c9f27`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c9f27`

## string_xrefs

- `0x1800c9eff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800c9f39`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800c9f7d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800c9fcb`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca022`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca0ac`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca105`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca17d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca1b5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca271`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800ca2d8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`

## pseudocode

```c
__int64 __fastcall AddSmMessageAttachment(const struct UdmChatAttachment *a1, struct ISmMessage *a2)
{
  __int64 v2; // r15
  __int64 v4; // r14
  HRESULT v7; // eax
  int v8; // esi
  void **v9; // rax
  HRESULT v10; // eax
  _QWORD *v11; // rax
  int FileExtensionFromContentType; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(struct ISmMessage *, __int64, _QWORD, _QWORD, __int64, __int64 *); // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r9
  int v20; // eax
  int v21; // eax
  int v22; // edi
  const unsigned __int16 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // [rsp+20h] [rbp-59h]
  LPVOID pv; // [rsp+40h] [rbp-39h] BYREF
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  __int64 v29; // [rsp+50h] [rbp-29h] BYREF
  __int64 v30; // [rsp+58h] [rbp-21h] BYREF
  __int64 v31; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v32[4]; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v33; // [rsp+88h] [rbp+Fh] BYREF
  GUID pguid; // [rsp+90h] [rbp+17h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  v4 = *((_QWORD *)a1 + 6);
  if ( !v2 && !v4 )
  {
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      328);
    return 2147942487LL;
  }
  pguid = 0;
  v7 = CoCreateGuid(&pguid);
  v8 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      331);
    return (unsigned int)v8;
  }
  pv = 0;
  v9 = tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
  v10 = StringFromCLSID(&pguid, (LPOLESTR *)v9);
  v8 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      334);
    goto LABEL_9;
  }
  v28 = 0;
  v11 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v28);
  FileExtensionFromContentType = Messaging_GetFileExtensionFromContentType(*((_QWORD *)a1 + 5), v11);
  v8 = FileExtensionFromContentType;
  if ( FileExtensionFromContentType < 0 )
  {
    Log_HREvent(
      (unsigned int)FileExtensionFromContentType,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      337);
LABEL_13:
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v28);
LABEL_9:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v8;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v32,
                           pv) )
  {
    v13 = 340;
LABEL_18:
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v13);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v28);
    if ( pv )
      CoTaskMemFree(pv);
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v32,
                           v28) )
  {
    v13 = 341;
    goto LABEL_18;
  }
  v14 = v32[0];
  if ( *((_QWORD *)a1 + 7) )
    v14 = *((_QWORD *)a1 + 7);
  v26 = v14;
  v15 = *((_QWORD *)a1 + 5);
  v16 = *(__int64 (__fastcall **)(struct ISmMessage *, __int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)a2 + 456LL);
  v30 = 0;
  v17 = v16(a2, v15, v32[0], v32[0], v26, &v30);
  v8 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent(
      (unsigned int)v17,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      349);
LABEL_25:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
    goto LABEL_13;
  }
  v29 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 24LL))(v30, 1, &v29);
  if ( v8 < 0 )
  {
    v19 = 353;
LABEL_28:
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v19);
LABEL_29:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
    goto LABEL_25;
  }
  if ( !v2 )
  {
    if ( !v4 )
      Log_AssertionEvent_2(
        v18,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        370);
    v23 = (const unsigned __int16 *)*((_QWORD *)a1 + 6);
    v33 = 0;
    v8 = StringCbLengthW(v23, 0xFFFFFFFE, &v33);
    if ( v8 < 0 )
    {
      v19 = 374;
      goto LABEL_28;
    }
    v24 = *((_QWORD *)a1 + 6);
    v31 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 32LL))(
            v29,
            v24,
            (unsigned int)v33,
            &v31);
    if ( v22 >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 48LL))(v29, v31);
      if ( v22 >= 0 )
      {
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 64LL))(v29, 0);
        if ( v22 >= 0 )
          goto LABEL_42;
        v25 = 384;
      }
      else
      {
        v25 = 381;
      }
    }
    else
    {
      v25 = 378;
    }
    Log_HREvent(
      (unsigned int)v22,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v25);
    goto LABEL_38;
  }
  v8 = CopyStream(*((_QWORD *)a1 + 2), v29);
  if ( v8 < 0 )
  {
    v19 = 357;
    goto LABEL_28;
  }
  if ( *((_QWORD *)a1 + 3) )
  {
    v31 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 160LL))(v30, 1, &v31);
    v8 = v20;
    if ( v20 < 0 )
    {
      Log_HREvent(
        (unsigned int)v20,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        363);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v31);
      goto LABEL_29;
    }
    v21 = CopyStream(*((_QWORD *)a1 + 3), v31);
    v22 = v21;
    if ( v21 < 0 )
    {
      Log_HREvent(
        (unsigned int)v21,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        365);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v31);
LABEL_38:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v28);
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v22;
    }
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v31);
  }
LABEL_42:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v28);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x1800c9ebc  mov     [rsp-8+arg_10], rbx
0x1800c9ec1  push    rbp
0x1800c9ec2  push    rsi
0x1800c9ec3  push    rdi
0x1800c9ec4  push    r14
0x1800c9ec6  push    r15
0x1800c9ec8  lea     rbp, [rsp-37h]
0x1800c9ecd  sub     rsp, 0B0h
0x1800c9ed4  mov     rax, cs:__security_cookie
0x1800c9edb  xor     rax, rsp
0x1800c9ede  mov     [rbp+57h+var_30], rax
0x1800c9ee2  mov     r15, [rcx+10h]
0x1800c9ee6  mov     rbx, rdx
0x1800c9ee9  mov     r14, [rcx+30h]
0x1800c9eed  mov     rdi, rcx
0x1800c9ef0  test    r15, r15
0x1800c9ef3  jnz     short loc_1800C9F1C
0x1800c9ef5  test    r14, r14
0x1800c9ef8  jnz     short loc_1800C9F1C
0x1800c9efa  mov     ebx, 80070057h
0x1800c9eff  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c9f06  mov     ecx, ebx
0x1800c9f08  mov     r9d, 148h
0x1800c9f0e  xor     edx, edx
0x1800c9f10  call    Log_HREvent
0x1800c9f15  mov     eax, ebx
0x1800c9f17  jmp     loc_1800CA243
0x1800c9f1c  xorps   xmm0, xmm0
0x1800c9f1f  lea     rcx, [rbp+57h+pguid]; pguid
0x1800c9f23  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800c9f27  call    cs:__imp_CoCreateGuid
0x1800c9f2d  mov     esi, eax
0x1800c9f2f  test    eax, eax
0x1800c9f31  jns     short loc_1800C9F53
0x1800c9f33  mov     r9d, 14Bh
0x1800c9f39  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c9f40  mov     edx, 1
0x1800c9f45  mov     ecx, eax
0x1800c9f47  call    Log_HREvent
0x1800c9f4c  mov     eax, esi
0x1800c9f4e  jmp     loc_1800CA243
0x1800c9f53  lea     rcx, [rbp+57h+pv]
0x1800c9f57  mov     [rbp+57h+pv], 0
0x1800c9f5f  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800c9f64  mov     rdx, rax; lplpsz
0x1800c9f67  lea     rcx, [rbp+57h+pguid]; rclsid
0x1800c9f6b  call    cs:__imp_StringFromCLSID
0x1800c9f71  mov     esi, eax
0x1800c9f73  test    eax, eax
0x1800c9f75  jns     short loc_1800C9FA1
0x1800c9f77  mov     r9d, 14Eh
0x1800c9f7d  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c9f84  mov     edx, 1
0x1800c9f89  mov     ecx, eax
0x1800c9f8b  call    Log_HREvent
0x1800c9f90  mov     rcx, [rbp+57h+pv]; pv
0x1800c9f94  test    rcx, rcx
0x1800c9f97  jz      short loc_1800C9F4C
0x1800c9f99  call    cs:__imp_CoTaskMemFree
0x1800c9f9f  jmp     short loc_1800C9F4C
0x1800c9fa1  lea     rcx, [rbp+57h+var_88]
0x1800c9fa5  mov     [rbp+57h+var_88], 0
0x1800c9fad  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800c9fb2  mov     rcx, [rdi+28h]
0x1800c9fb6  mov     rdx, rax
0x1800c9fb9  call    cs:__imp_Messaging_GetFileExtensionFromContentType
0x1800c9fbf  mov     esi, eax
0x1800c9fc1  test    eax, eax
0x1800c9fc3  jns     short loc_1800C9FE9
0x1800c9fc5  mov     r9d, 151h
0x1800c9fcb  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c9fd2  mov     edx, 1
0x1800c9fd7  mov     ecx, eax
0x1800c9fd9  call    Log_HREvent
0x1800c9fde  lea     rcx, [rbp+57h+var_88]
0x1800c9fe2  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800c9fe7  jmp     short loc_1800C9F90
0x1800c9fe9  lea     rcx, [rbp+57h+var_68]; void *
0x1800c9fed  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800c9ff2  mov     rdx, [rbp+57h+pv]
0x1800c9ff6  lea     rcx, [rbp+57h+var_68]
0x1800c9ffa  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800c9fff  test    al, al
0x1800ca001  jnz     short loc_1800CA00B
0x1800ca003  mov     r9d, 154h
0x1800ca009  jmp     short loc_1800CA022
0x1800ca00b  mov     rdx, [rbp+57h+var_88]
0x1800ca00f  lea     rcx, [rbp+57h+var_68]
0x1800ca013  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800ca018  test    al, al
0x1800ca01a  jnz     short loc_1800CA060
0x1800ca01c  mov     r9d, 155h
0x1800ca022  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca029  xor     edx, edx
0x1800ca02b  mov     ecx, 8007000Eh
0x1800ca030  call    Log_HREvent
0x1800ca035  lea     rcx, [rbp+57h+var_68]; void *
0x1800ca039  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ca03e  lea     rcx, [rbp+57h+var_88]
0x1800ca042  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800ca047  mov     rcx, [rbp+57h+pv]; pv
0x1800ca04b  test    rcx, rcx
0x1800ca04e  jz      short loc_1800CA056
0x1800ca050  call    cs:__imp_CoTaskMemFree
0x1800ca056  mov     eax, 8007000Eh
0x1800ca05b  jmp     loc_1800CA243
0x1800ca060  mov     r8, [rbp+57h+var_68]
0x1800ca064  lea     rcx, [rbp+57h+var_78]
0x1800ca068  cmp     qword ptr [rdi+38h], 0
0x1800ca06d  mov     rdx, r8
0x1800ca070  mov     rax, [rbx]
0x1800ca073  mov     r9, r8
0x1800ca076  cmovnz  rdx, [rdi+38h]
0x1800ca07b  mov     [rsp+0D0h+var_A8], rcx
0x1800ca080  mov     rcx, rbx
0x1800ca083  mov     [rsp+0D0h+var_B0], rdx
0x1800ca088  mov     rdx, [rdi+28h]
0x1800ca08c  mov     rax, [rax+1C8h]
0x1800ca093  mov     [rbp+57h+var_78], 0
0x1800ca09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca0a0  mov     esi, eax
0x1800ca0a2  test    eax, eax
0x1800ca0a4  jns     short loc_1800CA0D6
0x1800ca0a6  mov     r9d, 15Dh
0x1800ca0ac  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca0b3  mov     edx, 1
0x1800ca0b8  mov     ecx, eax
0x1800ca0ba  call    Log_HREvent
0x1800ca0bf  lea     rcx, [rbp+57h+var_78]
0x1800ca0c3  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca0c8  lea     rcx, [rbp+57h+var_68]; void *
0x1800ca0cc  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ca0d1  jmp     loc_1800C9FDE
0x1800ca0d6  mov     rcx, [rbp+57h+var_78]
0x1800ca0da  lea     r8, [rbp+57h+var_80]
0x1800ca0de  mov     [rbp+57h+var_80], 0
0x1800ca0e6  mov     ebx, 1
0x1800ca0eb  mov     edx, ebx
0x1800ca0ed  mov     rax, [rcx]
0x1800ca0f0  mov     rax, [rax+18h]
0x1800ca0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca0f9  mov     esi, eax
0x1800ca0fb  test    eax, eax
0x1800ca0fd  jns     short loc_1800CA120
0x1800ca0ff  mov     r9d, 161h
0x1800ca105  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca10c  mov     edx, ebx
0x1800ca10e  mov     ecx, esi
0x1800ca110  call    Log_HREvent
0x1800ca115  lea     rcx, [rbp+57h+var_80]
0x1800ca119  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca11e  jmp     short loc_1800CA0BF
0x1800ca120  test    r15, r15
0x1800ca123  jz      loc_1800CA266
0x1800ca129  mov     rdx, [rbp+57h+var_80]
0x1800ca12d  mov     rcx, [rdi+10h]
0x1800ca131  call    cs:__imp_CopyStream
0x1800ca137  mov     esi, eax
0x1800ca139  test    eax, eax
0x1800ca13b  jns     short loc_1800CA145
0x1800ca13d  mov     r9d, 165h
0x1800ca143  jmp     short loc_1800CA105
0x1800ca145  cmp     qword ptr [rdi+18h], 0
0x1800ca14a  jz      loc_1800CA20E
0x1800ca150  mov     rcx, [rbp+57h+var_78]
0x1800ca154  lea     r8, [rbp+57h+var_70]
0x1800ca158  mov     [rbp+57h+var_70], 0
0x1800ca160  mov     edx, ebx
0x1800ca162  mov     rax, [rcx]
0x1800ca165  mov     rax, [rax+0A0h]
0x1800ca16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca171  mov     esi, eax
0x1800ca173  test    eax, eax
0x1800ca175  jns     short loc_1800CA19B
0x1800ca177  mov     r9d, 16Bh
0x1800ca17d  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca184  mov     edx, ebx
0x1800ca186  mov     ecx, eax
0x1800ca188  call    Log_HREvent
0x1800ca18d  lea     rcx, [rbp+57h+var_70]
0x1800ca191  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca196  jmp     loc_1800CA115
0x1800ca19b  mov     rdx, [rbp+57h+var_70]
0x1800ca19f  mov     rcx, [rdi+18h]
0x1800ca1a3  call    cs:__imp_CopyStream
0x1800ca1a9  mov     edi, eax
0x1800ca1ab  test    eax, eax
0x1800ca1ad  jns     short loc_1800CA205
0x1800ca1af  mov     r9d, 16Dh
0x1800ca1b5  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca1bc  mov     edx, ebx
0x1800ca1be  mov     ecx, eax
0x1800ca1c0  call    Log_HREvent
0x1800ca1c5  lea     rcx, [rbp+57h+var_70]
0x1800ca1c9  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca1ce  lea     rcx, [rbp+57h+var_80]
0x1800ca1d2  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca1d7  lea     rcx, [rbp+57h+var_78]
0x1800ca1db  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca1e0  lea     rcx, [rbp+57h+var_68]; void *
0x1800ca1e4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ca1e9  lea     rcx, [rbp+57h+var_88]
0x1800ca1ed  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800ca1f2  mov     rcx, [rbp+57h+pv]; pv
0x1800ca1f6  test    rcx, rcx
0x1800ca1f9  jz      short loc_1800CA201
0x1800ca1fb  call    cs:__imp_CoTaskMemFree
0x1800ca201  mov     eax, edi
0x1800ca203  jmp     short loc_1800CA243
0x1800ca205  lea     rcx, [rbp+57h+var_70]
0x1800ca209  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca20e  lea     rcx, [rbp+57h+var_80]
0x1800ca212  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca217  lea     rcx, [rbp+57h+var_78]
0x1800ca21b  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800ca220  lea     rcx, [rbp+57h+var_68]; void *
0x1800ca224  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ca229  lea     rcx, [rbp+57h+var_88]
0x1800ca22d  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800ca232  mov     rcx, [rbp+57h+pv]; pv
0x1800ca236  test    rcx, rcx
0x1800ca239  jz      short loc_1800CA241
0x1800ca23b  call    cs:__imp_CoTaskMemFree
0x1800ca241  xor     eax, eax
0x1800ca243  mov     rcx, [rbp+57h+var_30]
0x1800ca247  xor     rcx, rsp; StackCookie
0x1800ca24a  call    __security_check_cookie
0x1800ca24f  mov     rbx, [rsp+0D0h+arg_10]
0x1800ca257  add     rsp, 0B0h
0x1800ca25e  pop     r15
0x1800ca260  pop     r14
0x1800ca262  pop     rdi
0x1800ca263  pop     rsi
0x1800ca264  pop     rbp
0x1800ca265  retn
0x1800ca266  test    r14, r14
0x1800ca269  jnz     short loc_1800CA27D
0x1800ca26b  mov     r8d, 172h
0x1800ca271  lea     rdx, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca278  call    Log_AssertionEvent_2
0x1800ca27d  mov     rcx, [rdi+30h]; unsigned __int16 *
0x1800ca281  lea     r8, [rbp+57h+var_48]; unsigned __int64 *
0x1800ca285  mov     edx, 0FFFFFFFEh; unsigned __int64
0x1800ca28a  mov     [rbp+57h+var_48], 0
0x1800ca292  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800ca297  mov     esi, eax
0x1800ca299  test    eax, eax
0x1800ca29b  jns     short loc_1800CA2A8
0x1800ca29d  mov     r9d, 176h
0x1800ca2a3  jmp     loc_1800CA105
0x1800ca2a8  mov     rcx, [rbp+57h+var_80]
0x1800ca2ac  lea     r9, [rbp+57h+var_70]
0x1800ca2b0  mov     r8d, dword ptr [rbp+57h+var_48]
0x1800ca2b4  mov     rdx, [rdi+30h]
0x1800ca2b8  mov     [rbp+57h+var_70], 0
0x1800ca2c0  mov     rax, [rcx]
0x1800ca2c3  mov     rax, [rax+20h]
0x1800ca2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca2cc  mov     edi, eax
0x1800ca2ce  test    eax, eax
0x1800ca2d0  jns     short loc_1800CA2ED
0x1800ca2d2  mov     r9d, 17Ah
0x1800ca2d8  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ca2df  mov     edx, ebx
0x1800ca2e1  mov     ecx, edi
0x1800ca2e3  call    Log_HREvent
0x1800ca2e8  jmp     loc_1800CA1CE
0x1800ca2ed  mov     rcx, [rbp+57h+var_80]
0x1800ca2f1  mov     rdx, [rbp+57h+var_70]
0x1800ca2f5  mov     rax, [rcx]
0x1800ca2f8  mov     rax, [rax+30h]
0x1800ca2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca301  mov     edi, eax
0x1800ca303  test    eax, eax
0x1800ca305  jns     short loc_1800CA30F
0x1800ca307  mov     r9d, 17Dh
0x1800ca30d  jmp     short loc_1800CA2D8
0x1800ca30f  mov     rcx, [rbp+57h+var_80]
0x1800ca313  xor     edx, edx
0x1800ca315  mov     rax, [rcx]
0x1800ca318  mov     rax, [rax+40h]
0x1800ca31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca321  mov     edi, eax
0x1800ca323  test    eax, eax
0x1800ca325  jns     loc_1800CA20E
0x1800ca32b  mov     r9d, 180h
0x1800ca331  jmp     short loc_1800CA2D8
```
