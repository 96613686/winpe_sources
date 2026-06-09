# ChatOperationContext::GetFilePropertyPath(UdmObjectId const &,ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)

- ea: `0x1800d19dc`
- end: `0x1800d1e59`
- name: `?GetFilePropertyPath@ChatOperationContext@@QEAAJAEBUUdmObjectId@@KPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z`
- size: `1149`
- prototype: `__int64 __fastcall(__int64 *, __int64, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a5bb0`

## callees

- `0x180002060`
- `0x1800020ec`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000c4e0`
- `0x180012988`
- `0x180018c20`
- `0x180021930`
- `0x18003307c`
- `0x180035c40`
- `0x18005646c`
- `0x18005cbe0`
- `0x18005e160`
- `0x1800669fc`
- `0x18006ce2c`
- `0x18008bebc`
- `0x18008cfbc`
- `0x1800b09bc`
- `0x1800b0ab4`
- `0x1800d19dc`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!?GetDeferredAttachmentFilePath@MessagingDeferredAttachment@@YAJPEAUISmMessage@@KPEAHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z` at `0x1800d1c82`
- `MessagingDataModel2!?GetDeferredAttachmentFilePath@MessagingDeferredAttachment@@YAJPEAUISmMessage@@KPEAHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z` at `0x1800d1c82`
- `CEMAPI!HrGetOneProp` at `0x1800d1bd2`
- `CEMAPI!HrGetOneProp` at `0x1800d1bd2`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1bfb`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1d14`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1dd3`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1bfb`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1d14`
- `CEMAPI!MAPIFreeBuffer` at `0x1800d1dd3`

## string_xrefs

- `0x1800d1a23`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1a8b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1ad2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1b08`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1be4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1c3e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1c94`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1df7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d1cdb`: `The deferred file path for the attachment could not be found.`
- `0x1800d1d9b`: `Retrieved attachment path from temporary file.`

## pseudocode

```c
__int64 __fastcall ChatOperationContext::GetFilePropertyPath(__int64 *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  _WORD *v5; // r10
  _DWORD *v6; // r15
  bool v11; // zf
  unsigned int v12; // ebx
  struct ServiceDataSession *v13; // rdx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, __int64); // rdi
  __int64 v18; // rax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  LPSPropValue *v24; // rax
  HRESULT OneProp; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int DeferredAttachmentFilePath; // eax
  const struct _tlgProvider_t *v32; // rax
  int v33; // r8d
  int v34; // r9d
  const struct _tlgProvider_t *v35; // rax
  int v36; // r8d
  int v37; // r9d
  struct IUnknown *v39; // [rsp+30h] [rbp-91h] BYREF
  __int64 v40; // [rsp+38h] [rbp-89h] BYREF
  __int64 v41; // [rsp+40h] [rbp-81h] BYREF
  __int64 v42; // [rsp+48h] [rbp-79h] BYREF
  const char *v43; // [rsp+50h] [rbp-71h] BYREF
  _QWORD v44[2]; // [rsp+58h] [rbp-69h] BYREF
  _WORD v45[8]; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v46[2]; // [rsp+78h] [rbp-49h] BYREF
  _WORD v47[8]; // [rsp+88h] [rbp-39h] BYREF
  const char *v48; // [rsp+98h] [rbp-29h] BYREF
  void **v49; // [rsp+A0h] [rbp-21h] BYREF
  _QWORD v50[3]; // [rsp+A8h] [rbp-19h] BYREF
  int v51; // [rsp+C0h] [rbp-1h]
  __int64 v52; // [rsp+C8h] [rbp+7h]
  __int64 v53; // [rsp+D0h] [rbp+Fh]
  __int64 v54; // [rsp+D8h] [rbp+17h]
  LPVOID pv; // [rsp+128h] [rbp+67h] BYREF
  LPMAPIPROP lpMapiProp; // [rsp+138h] [rbp+77h] BYREF

  v5 = *(_WORD **)a4;
  v6 = a5;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v5 = 0;
  v11 = *(_DWORD *)(a2 + 4) == 35;
  *v6 = 0;
  if ( v11 )
  {
    v50[0] = 0;
    v49 = &UnistoreOperationContext::`vftable';
    v52 = 0;
    v51 = 0;
    ATL::CComPtr<ServiceDataSession>::operator=(v50, 0);
    v13 = (struct ServiceDataSession *)a1[1];
    v49 = &EmailOperationContext::`vftable';
    v53 = 0;
    v54 = 0;
    v14 = EmailOperationContext::Initialize((EmailOperationContext *)&v49, v13);
    v12 = v14;
    if ( v14 < 0 )
    {
      Log_HREvent(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1844);
LABEL_40:
      EmailOperationContext::~EmailOperationContext((EmailOperationContext *)&v49);
      return v12;
    }
    v39 = 0;
    lpMapiProp = 0;
    v15 = EmailOperationContext::OpenAttachItemById(
            (EmailOperationContext *)&v49,
            (const struct UdmObjectId *)a2,
            &v39,
            (struct IMessage **)&lpMapiProp,
            0);
    v12 = v15;
    if ( v15 < 0 )
    {
      Log_HREvent(
        (unsigned int)v15,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1848);
LABEL_39:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&lpMapiProp);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
      goto LABEL_40;
    }
    ATL::CComQIPtr<ICEMAPIStreamPropQuery,&__s_GUID const _GUID_24a38aca_32a7_4225_973e_38ebe9cec42c>::CComQIPtr<ICEMAPIStreamPropQuery,&__s_GUID const _GUID_24a38aca_32a7_4225_973e_38ebe9cec42c>(
      &v41,
      v39);
    v16 = v41;
    if ( !v41 )
    {
      v12 = -2147467262;
      Log_HREvent(
        2147500034LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1851);
LABEL_38:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v41);
      goto LABEL_39;
    }
    v45[0] = 0;
    v44[0] = v45;
    v40 = 0;
    v44[1] = v45;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v41 + 24LL);
    v18 = tlx::replace<_USRestriction,&void _LocalFreer<_USRestriction>(_USRestriction *)>(&v40);
    v19 = 2195194114LL;
    if ( a3 != 303824902 )
      v19 = 922812674;
    v20 = v17(v16, v19, v18);
    v12 = v20;
    if ( v20 >= 0 )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v44,
                               v40) )
      {
        v12 = -2147024882;
        v21 = 1861;
        v22 = 2147942414LL;
        v23 = 0;
LABEL_36:
        Log_HREvent(
          v22,
          v23,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          v21);
        goto LABEL_37;
      }
      goto LABEL_34;
    }
    if ( v20 != -2147023728 || a3 == 303824902 )
    {
      v21 = 1903;
      v23 = 1;
      v22 = (unsigned int)v20;
      goto LABEL_36;
    }
    pv = 0;
    v24 = (LPSPropValue *)CMapiProps::operator&(&pv);
    OneProp = HrGetOneProp(lpMapiProp, 0xFFF0102u, v24);
    v12 = OneProp;
    if ( OneProp >= 0 )
    {
      v26 = CMapiProps::operator->(&pv);
      v27 = *a1;
      v28 = *(_QWORD *)(v26 + 16);
      v42 = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 104LL))(
              v27,
              *(unsigned int *)(v28 + 4),
              &v42);
      v12 = v29;
      if ( v29 >= 0 )
      {
        v30 = *(unsigned int *)(a2 + 8);
        v46[0] = v47;
        LODWORD(a5) = 0;
        v46[1] = v47;
        v47[0] = 0;
        DeferredAttachmentFilePath = MessagingDeferredAttachment::GetDeferredAttachmentFilePath(v42, v30, &a5, v46);
        v12 = DeferredAttachmentFilePath;
        if ( DeferredAttachmentFilePath >= 0 )
        {
          if ( !(_DWORD)a5 )
          {
            v32 = UserDataServiceProvider::Provider();
            if ( *(_DWORD *)v32 > 5u && (unsigned __int8)tlgKeywordOn(v32, 4, v32) )
            {
              v43 = "The deferred file path for the attachment could not be found.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v33,
                (unsigned int)word_18014A5AA,
                v33,
                v34,
                (__int64)&v43);
            }
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
            MAPIFreeBuffer(pv);
            pv = 0;
            goto LABEL_29;
          }
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
            v44,
            v46);
          *v6 = 1;
          v35 = UserDataServiceProvider::Provider();
          if ( *(_DWORD *)v35 > 5u && (unsigned __int8)tlgKeywordOn(v35, 4, v35) )
          {
            v43 = (const char *)v44[0];
            v48 = "Retrieved attachment path from temporary file.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              v36,
              (unsigned int)&dword_18014A5EC,
              v36,
              v37,
              (__int64)&v48,
              (__int64)&v43);
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
          MAPIFreeBuffer(pv);
LABEL_34:
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::swap(
            a4,
            v44);
LABEL_29:
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v40);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v44);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v41);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&lpMapiProp);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
          v12 = 0;
          goto LABEL_40;
        }
        Log_HREvent(
          (unsigned int)DeferredAttachmentFilePath,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          1877);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
      }
      else
      {
        Log_HREvent(
          (unsigned int)v29,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          1873);
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
    }
    else
    {
      Log_HREvent(
        (unsigned int)OneProp,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1868);
    }
    MAPIFreeBuffer(pv);
    pv = 0;
LABEL_37:
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v40);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v44);
    goto LABEL_38;
  }
  v12 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
    1840);
  return v12;
}

```

## disassembly

```asm
0x1800d19dc  mov     [rsp-8+arg_0], rbx
0x1800d19e1  push    rbp
0x1800d19e2  push    rsi
0x1800d19e3  push    rdi
0x1800d19e4  push    r12
0x1800d19e6  push    r13
0x1800d19e8  push    r14
0x1800d19ea  push    r15
0x1800d19ec  lea     rbp, [rsp-1Fh]
0x1800d19f1  sub     rsp, 0E0h
0x1800d19f8  mov     r10, [r9]
0x1800d19fb  xor     edi, edi
0x1800d19fd  mov     r15, [rbp+4Fh+arg_20]
0x1800d1a01  mov     r14, r9
0x1800d1a04  mov     [r9+8], r10
0x1800d1a08  mov     r12d, r8d
0x1800d1a0b  mov     rsi, rdx
0x1800d1a0e  mov     r13, rcx
0x1800d1a11  mov     [r10], di
0x1800d1a15  cmp     dword ptr [rdx+4], 23h ; '#'
0x1800d1a19  mov     [r15], edi
0x1800d1a1c  jz      short loc_1800D1A3E
0x1800d1a1e  mov     ebx, 80070057h
0x1800d1a23  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1a2a  mov     ecx, ebx
0x1800d1a2c  mov     r9d, 730h
0x1800d1a32  xor     edx, edx
0x1800d1a34  call    Log_HREvent
0x1800d1a39  jmp     loc_1800D1E3C
0x1800d1a3e  lea     rax, ??_7UnistoreOperationContext@@6B@; const UnistoreOperationContext::`vftable'
0x1800d1a45  mov     [rbp+4Fh+var_68], rdi
0x1800d1a49  xor     edx, edx
0x1800d1a4b  mov     [rbp+4Fh+var_70], rax
0x1800d1a4f  lea     rcx, [rbp+4Fh+var_68]
0x1800d1a53  mov     [rbp+4Fh+var_48], rdi
0x1800d1a57  mov     [rbp+4Fh+var_50], edi
0x1800d1a5a  call    ??4?$CComPtr@VServiceDataSession@@@ATL@@QEAAPEAVServiceDataSession@@PEAV2@@Z; ATL::CComPtr<ServiceDataSession>::operator=(ServiceDataSession *)
0x1800d1a5f  mov     rdx, [r13+8]; struct ServiceDataSession *
0x1800d1a63  lea     rax, ??_7EmailOperationContext@@6B@; const EmailOperationContext::`vftable'
0x1800d1a6a  lea     rcx, [rbp+4Fh+var_70]; this
0x1800d1a6e  mov     [rbp+4Fh+var_70], rax
0x1800d1a72  mov     [rbp+4Fh+var_40], rdi
0x1800d1a76  mov     [rbp+4Fh+var_38], rdi
0x1800d1a7a  call    ?Initialize@EmailOperationContext@@UEAAJPEAVServiceDataSession@@@Z; EmailOperationContext::Initialize(ServiceDataSession *)
0x1800d1a7f  mov     ebx, eax
0x1800d1a81  test    eax, eax
0x1800d1a83  jns     short loc_1800D1AA3
0x1800d1a85  mov     r9d, 734h
0x1800d1a8b  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1a92  mov     edx, 1
0x1800d1a97  mov     ecx, eax
0x1800d1a99  call    Log_HREvent
0x1800d1a9e  jmp     loc_1800D1E33
0x1800d1aa3  lea     r9, [rbp+4Fh+lpMapiProp]; struct IMessage **
0x1800d1aa7  mov     [rsp+110h+var_E0], rdi
0x1800d1aac  lea     r8, [rsp+110h+var_E0]; struct IUnknown **
0x1800d1ab1  mov     [rbp+4Fh+lpMapiProp], rdi
0x1800d1ab5  mov     rdx, rsi; struct UdmObjectId *
0x1800d1ab8  mov     [rsp+110h+var_F0], rdi; struct IMsgStore **
0x1800d1abd  lea     rcx, [rbp+4Fh+var_70]; this
0x1800d1ac1  call    ?OpenAttachItemById@EmailOperationContext@@QEAAJAEBUUdmObjectId@@PEAPEAUIUnknown@@PEAPEAUIMessage@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::OpenAttachItemById(UdmObjectId const &,IUnknown * *,IMessage * *,IMsgStore * *)
0x1800d1ac6  mov     ebx, eax
0x1800d1ac8  test    eax, eax
0x1800d1aca  jns     short loc_1800D1AEA
0x1800d1acc  mov     r9d, 738h
0x1800d1ad2  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1ad9  mov     edx, 1
0x1800d1ade  mov     ecx, eax
0x1800d1ae0  call    Log_HREvent
0x1800d1ae5  jmp     loc_1800D1E20
0x1800d1aea  mov     rdx, [rsp+110h+var_E0]
0x1800d1aef  lea     rcx, [rsp+110h+var_D0]
0x1800d1af4  call    ??0?$CComQIPtr@UICEMAPIStreamPropQuery@@$1?_GUID_24a38aca_32a7_4225_973e_38ebe9cec42c@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ICEMAPIStreamPropQuery,&__s_GUID const _GUID_24a38aca_32a7_4225_973e_38ebe9cec42c>::CComQIPtr<ICEMAPIStreamPropQuery,&__s_GUID const _GUID_24a38aca_32a7_4225_973e_38ebe9cec42c>(IUnknown *)
0x1800d1af9  mov     rbx, [rsp+110h+var_D0]
0x1800d1afe  test    rbx, rbx
0x1800d1b01  jnz     short loc_1800D1B23
0x1800d1b03  mov     ebx, 80004002h
0x1800d1b08  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1b0f  mov     ecx, ebx
0x1800d1b11  mov     r9d, 73Bh
0x1800d1b17  xor     edx, edx
0x1800d1b19  call    Log_HREvent
0x1800d1b1e  jmp     loc_1800D1E16
0x1800d1b23  mov     [rbp+4Fh+var_A8], di
0x1800d1b27  lea     rax, [rbp+4Fh+var_A8]
0x1800d1b2b  mov     [rbp+4Fh+var_B8], rax
0x1800d1b2f  lea     rcx, [rsp+110h+var_D8]
0x1800d1b34  mov     [rsp+110h+var_D8], rdi
0x1800d1b39  lea     rax, [rbp+4Fh+var_A8]
0x1800d1b3d  mov     [rbp+4Fh+var_B0], rax
0x1800d1b41  mov     rax, [rbx]
0x1800d1b44  mov     rdi, [rax+18h]
0x1800d1b48  call    ??$replace@U_USRestriction@@$1??$_LocalFreer@U_USRestriction@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USRestriction@@AEAV?$auto_array_ptr@U_USRestriction@@$1??$_LocalFreer@U_USRestriction@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USRestriction,&_LocalFreer<_USRestriction>(_USRestriction *)>(tlx::auto_array_ptr<_USRestriction,&_LocalFreer<_USRestriction>(_USRestriction *)> &)
0x1800d1b4d  mov     edx, 82D80102h
0x1800d1b52  mov     ecx, 37010102h
0x1800d1b57  mov     r8, rax
0x1800d1b5a  cmp     r12d, 121C0006h
0x1800d1b61  mov     rax, rdi
0x1800d1b64  cmovnz  edx, ecx
0x1800d1b67  mov     rcx, rbx
0x1800d1b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1b6f  xor     edi, edi
0x1800d1b71  mov     ebx, eax
0x1800d1b73  test    eax, eax
0x1800d1b75  js      short loc_1800D1BA1
0x1800d1b77  mov     rdx, [rsp+110h+var_D8]
0x1800d1b7c  lea     rcx, [rbp+4Fh+var_B8]
0x1800d1b80  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800d1b85  test    al, al
0x1800d1b87  jnz     loc_1800D1DD9
0x1800d1b8d  mov     ebx, 8007000Eh
0x1800d1b92  mov     r9d, 745h
0x1800d1b98  mov     ecx, ebx
0x1800d1b9a  xor     edx, edx
0x1800d1b9c  jmp     loc_1800D1DF7
0x1800d1ba1  cmp     eax, 80070490h
0x1800d1ba6  jnz     loc_1800D1DEA
0x1800d1bac  cmp     r12d, 121C0006h
0x1800d1bb3  jz      loc_1800D1DEA
0x1800d1bb9  lea     rcx, [rbp+4Fh+pv]
0x1800d1bbd  mov     [rbp+4Fh+pv], rdi
0x1800d1bc1  call    ??ICMapiProps@@QEAAPEAPEAU_SPropValue@@XZ; CMapiProps::operator&(void)
0x1800d1bc6  mov     rcx, [rbp+4Fh+lpMapiProp]; lpMapiProp
0x1800d1bca  mov     r8, rax; lppProp
0x1800d1bcd  mov     edx, 0FFF0102h; ulPropTag
0x1800d1bd2  call    cs:__imp_HrGetOneProp
0x1800d1bd8  mov     ebx, eax
0x1800d1bda  test    eax, eax
0x1800d1bdc  jns     short loc_1800D1C0A
0x1800d1bde  mov     r9d, 74Ch
0x1800d1be4  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1beb  mov     edx, 1
0x1800d1bf0  mov     ecx, eax
0x1800d1bf2  call    Log_HREvent
0x1800d1bf7  mov     rcx, [rbp+4Fh+pv]; pv
0x1800d1bfb  call    cs:__imp_MAPIFreeBuffer
0x1800d1c01  mov     [rbp+4Fh+pv], rdi
0x1800d1c05  jmp     loc_1800D1E03
0x1800d1c0a  lea     rcx, [rbp+4Fh+pv]
0x1800d1c0e  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x1800d1c13  mov     rcx, [r13+0]
0x1800d1c17  lea     r8, [rbp+4Fh+var_C8]
0x1800d1c1b  mov     rdx, [rax+10h]
0x1800d1c1f  mov     [rbp+4Fh+var_C8], rdi
0x1800d1c23  mov     rax, [rcx]
0x1800d1c26  mov     edx, [rdx+4]
0x1800d1c29  mov     rax, [rax+68h]
0x1800d1c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c32  mov     ebx, eax
0x1800d1c34  test    eax, eax
0x1800d1c36  jns     short loc_1800D1C5C
0x1800d1c38  mov     r9d, 751h
0x1800d1c3e  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1c45  mov     edx, 1
0x1800d1c4a  mov     ecx, eax
0x1800d1c4c  call    Log_HREvent
0x1800d1c51  lea     rcx, [rbp+4Fh+var_C8]
0x1800d1c55  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1c5a  jmp     short loc_1800D1BF7
0x1800d1c5c  mov     edx, [rsi+8]
0x1800d1c5f  lea     rax, [rbp+4Fh+var_88]
0x1800d1c63  mov     rcx, [rbp+4Fh+var_C8]
0x1800d1c67  lea     r9, [rbp+4Fh+var_98]
0x1800d1c6b  mov     [rbp+4Fh+var_98], rax
0x1800d1c6f  lea     r8, [rbp+4Fh+arg_20]
0x1800d1c73  lea     rax, [rbp+4Fh+var_88]
0x1800d1c77  mov     dword ptr [rbp+4Fh+arg_20], edi
0x1800d1c7a  mov     [rbp+4Fh+var_90], rax
0x1800d1c7e  mov     [rbp+4Fh+var_88], di
0x1800d1c82  call    cs:__imp_?GetDeferredAttachmentFilePath@MessagingDeferredAttachment@@YAJPEAUISmMessage@@KPEAHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; MessagingDeferredAttachment::GetDeferredAttachmentFilePath(ISmMessage *,ulong,int *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800d1c88  mov     ebx, eax
0x1800d1c8a  test    eax, eax
0x1800d1c8c  jns     short loc_1800D1CB2
0x1800d1c8e  mov     r9d, 755h
0x1800d1c94  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1c9b  mov     edx, 1
0x1800d1ca0  mov     ecx, eax
0x1800d1ca2  call    Log_HREvent
0x1800d1ca7  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800d1cab  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d1cb0  jmp     short loc_1800D1C51
0x1800d1cb2  cmp     dword ptr [rbp+4Fh+arg_20], edi
0x1800d1cb5  jnz     loc_1800D1D55
0x1800d1cbb  call    ?Provider@UserDataServiceProvider@@SAPEBU_tlgProvider_t@@XZ; UserDataServiceProvider::Provider(void)
0x1800d1cc0  mov     r8, rax
0x1800d1cc3  mov     ecx, [rax]
0x1800d1cc5  cmp     ecx, 5
0x1800d1cc8  jbe     short loc_1800D1CFE
0x1800d1cca  mov     edx, 4
0x1800d1ccf  mov     rcx, rax
0x1800d1cd2  call    _tlgKeywordOn
0x1800d1cd7  test    al, al
0x1800d1cd9  jz      short loc_1800D1CFE
0x1800d1cdb  lea     rax, aTheDeferredFil; "The deferred file path for the attachme"...
0x1800d1ce2  mov     rcx, r8
0x1800d1ce5  mov     [rbp+4Fh+var_C0], rax
0x1800d1ce9  lea     rdx, word_18014A5AA
0x1800d1cf0  lea     rax, [rbp+4Fh+var_C0]
0x1800d1cf4  mov     [rsp+110h+var_F0], rax
0x1800d1cf9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800d1cfe  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800d1d02  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d1d07  lea     rcx, [rbp+4Fh+var_C8]
0x1800d1d0b  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1d10  mov     rcx, [rbp+4Fh+pv]; pv
0x1800d1d14  call    cs:__imp_MAPIFreeBuffer
0x1800d1d1a  mov     [rbp+4Fh+pv], rdi
0x1800d1d1e  lea     rcx, [rsp+110h+var_D8]
0x1800d1d23  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800d1d28  lea     rcx, [rbp+4Fh+var_B8]; void *
0x1800d1d2c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d1d31  lea     rcx, [rsp+110h+var_D0]
0x1800d1d36  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1d3b  lea     rcx, [rbp+4Fh+lpMapiProp]
0x1800d1d3f  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1d44  lea     rcx, [rsp+110h+var_E0]
0x1800d1d49  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1d4e  mov     ebx, edi
0x1800d1d50  jmp     loc_1800D1E33
0x1800d1d55  lea     rdx, [rbp+4Fh+var_98]
0x1800d1d59  lea     rcx, [rbp+4Fh+var_B8]
0x1800d1d5d  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800d1d62  mov     dword ptr [r15], 1
0x1800d1d69  call    ?Provider@UserDataServiceProvider@@SAPEBU_tlgProvider_t@@XZ; UserDataServiceProvider::Provider(void)
0x1800d1d6e  mov     r8, rax
0x1800d1d71  mov     ecx, [rax]
0x1800d1d73  cmp     ecx, 5
0x1800d1d76  jbe     short loc_1800D1DBD
0x1800d1d78  mov     edx, 4
0x1800d1d7d  mov     rcx, rax
0x1800d1d80  call    _tlgKeywordOn
0x1800d1d85  test    al, al
0x1800d1d87  jz      short loc_1800D1DBD
0x1800d1d89  mov     rax, [rbp+4Fh+var_B8]
0x1800d1d8d  lea     rdx, dword_18014A5EC
0x1800d1d94  mov     [rbp+4Fh+var_C0], rax
0x1800d1d98  mov     rcx, r8
0x1800d1d9b  lea     rax, aRetrievedAttac; "Retrieved attachment path from temporar"...
0x1800d1da2  mov     [rbp+4Fh+var_78], rax
0x1800d1da6  lea     rax, [rbp+4Fh+var_C0]
0x1800d1daa  mov     [rsp+110h+var_E8], rax
0x1800d1daf  lea     rax, [rbp+4Fh+var_78]
0x1800d1db3  mov     [rsp+110h+var_F0], rax
0x1800d1db8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800d1dbd  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800d1dc1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d1dc6  lea     rcx, [rbp+4Fh+var_C8]
0x1800d1dca  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1dcf  mov     rcx, [rbp+4Fh+pv]; pv
0x1800d1dd3  call    cs:__imp_MAPIFreeBuffer
0x1800d1dd9  lea     rdx, [rbp+4Fh+var_B8]
0x1800d1ddd  mov     rcx, r14
0x1800d1de0  call    ?swap@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::swap(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800d1de5  jmp     loc_1800D1D1E
0x1800d1dea  mov     r9d, 76Fh
0x1800d1df0  mov     edx, 1
0x1800d1df5  mov     ecx, eax
0x1800d1df7  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d1dfe  call    Log_HREvent
0x1800d1e03  lea     rcx, [rsp+110h+var_D8]
0x1800d1e08  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800d1e0d  lea     rcx, [rbp+4Fh+var_B8]; void *
0x1800d1e11  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d1e16  lea     rcx, [rsp+110h+var_D0]
0x1800d1e1b  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1e20  lea     rcx, [rbp+4Fh+lpMapiProp]
0x1800d1e24  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1e29  lea     rcx, [rsp+110h+var_E0]
0x1800d1e2e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d1e33  lea     rcx, [rbp+4Fh+var_70]; this
0x1800d1e37  call    ??1EmailOperationContext@@QEAA@XZ; EmailOperationContext::~EmailOperationContext(void)
0x1800d1e3c  mov     eax, ebx
0x1800d1e3e  mov     rbx, [rsp+110h+arg_0]
0x1800d1e46  add     rsp, 0E0h
0x1800d1e4d  pop     r15
0x1800d1e4f  pop     r14
0x1800d1e51  pop     r13
0x1800d1e53  pop     r12
0x1800d1e55  pop     rdi
0x1800d1e56  pop     rsi
0x1800d1e57  pop     rbp
0x1800d1e58  retn
```
