# ChatOperationContext::GetMessageParticipants(ISmMessage *,int *,ulong *,UdmChatParticipant * *)

- ea: `0x180061a9c`
- end: `0x1800621c3`
- name: `?GetMessageParticipants@ChatOperationContext@@QEAAJPEAUISmMessage@@PEAHPEAKPEAPEAUUdmChatParticipant@@@Z`
- size: `1831`
- prototype: `__int64 __fastcall(ChatOperationContext *__hidden this, struct ISmMessage *, int *, unsigned int *, struct UdmChatParticipant **)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800cb024`
- `0x1801215b8`

## callees

- `0x1800049f0`
- `0x180007760`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000e1f8`
- `0x18003cda4`
- `0x18003ed7c`
- `0x180061a9c`
- `0x1800621cc`
- `0x180075f98`
- `0x18007b170`
- `0x18007b258`
- `0x18007d510`
- `0x180083668`
- `0x1800842dc`
- `0x1800977ac`
- `0x1800ca33c`
- `0x1800cdf9c`
- `0x1800d03f8`
- `0x1800d0b78`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180061e44`
- `msvcrt!_wcsicmp` at `0x180061e44`
- `PhoneUtil!ComparePhoneNumbers` at `0x180061e8e`
- `PhoneUtil!ComparePhoneNumbers` at `0x180061e8e`
- `MessagingDataModel2!Messaging_IsMmsMessage` at `0x180061f16`
- `MessagingDataModel2!Messaging_IsMmsMessage` at `0x180061f16`
- `MessagingDataModel2!Messaging_IsRcsMessage` at `0x180061f2f`
- `MessagingDataModel2!Messaging_IsRcsMessage` at `0x180061f2f`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x180061d3e`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x180061d3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180061be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180062172`
- `OLEAUT32!__imp_SysFreeString` at `0x180061be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180062172`

## string_xrefs

- `0x180061b7e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x180062077`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800620e3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`

## pseudocode

```c
__int64 __fastcall ChatOperationContext::GetMessageParticipants(
        ChatOperationContext *this,
        struct ISmMessage *a2,
        int *a3,
        unsigned int *a4,
        struct UdmChatParticipant **a5)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // r8
  char *v22; // r15
  unsigned int v23; // r12d
  char *v24; // rsi
  int v25; // eax
  __int64 *v26; // rdi
  char *v27; // r13
  __int64 (__fastcall *v28)(__int64 *, _QWORD *); // rbx
  _QWORD *v29; // rax
  BOOL v30; // edi
  const wchar_t *v31; // rax
  __m128i v32; // xmm6
  unsigned int v33; // r13d
  __int64 v34; // rax
  unsigned int v35; // ebx
  int v36; // edx
  __int128 v37; // xmm1
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  char *v41; // rbx
  int v42; // eax
  __int64 v43; // rcx
  unsigned int v44; // edi
  __int64 v46; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v47; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v48; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v49[4]; // [rsp+4Ch] [rbp-BCh] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B8h] BYREF
  int v51; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v52; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned int v53; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v54; // [rsp+64h] [rbp-A4h] BYREF
  int v55; // [rsp+68h] [rbp-A0h]
  int v56; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned int v57; // [rsp+70h] [rbp-98h] BYREF
  int v58; // [rsp+74h] [rbp-94h] BYREF
  unsigned int v59; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v60; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v61; // [rsp+80h] [rbp-88h] BYREF
  void *v62[3]; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+A0h] [rbp-68h] BYREF
  char *v64; // [rsp+A8h] [rbp-60h]
  char *v65; // [rsp+B0h] [rbp-58h]
  __int128 v66; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v67; // [rsp+C8h] [rbp-40h]
  int v68[4]; // [rsp+D8h] [rbp-30h] BYREF
  int *v69; // [rsp+E8h] [rbp-20h]
  _QWORD *v70; // [rsp+F0h] [rbp-18h]
  unsigned int *v71; // [rsp+F8h] [rbp-10h]
  char v72[8]; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 v73; // [rsp+108h] [rbp+0h] BYREF
  char *v74; // [rsp+110h] [rbp+8h]

  v70 = a5;
  v71 = a4;
  v69 = a3;
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      ChatOperationContextGetMessageParticipants,
      a3,
      1,
      &v73);
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Chat_GetMessageParticipants_START,
      a3,
      1,
      &v73);
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v49[1] = 1;
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&Block);
  v8 = *(_QWORD *)a2;
  v55 = 0;
  bstrString = 0;
  if ( (*(int (__fastcall **)(struct ISmMessage *, BSTR *))(v8 + 496))(a2, &bstrString) >= 0 )
  {
    v55 = 1;
    if ( !bstrString )
      Log_AssertionEvent_2(
        v9,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        1693);
  }
  v10 = *(_QWORD *)a2;
  v53 = 0;
  v11 = (*(__int64 (__fastcall **)(struct ISmMessage *, unsigned int *))(v10 + 544))(a2, &v53);
  v12 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      1697);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( Block != (void *)-1LL )
      operator delete(Block);
LABEL_87:
    lambda_0dd625d3762276213498069ae0a32357_::operator()();
    return v12;
  }
  v13 = *(_QWORD *)a2;
  v51 = 0;
  v14 = (*(__int64 (__fastcall **)(struct ISmMessage *, int *))(v13 + 432))(a2, &v51);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1700;
LABEL_17:
    Log_HREvent(
      (unsigned int)v14,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      v15);
    goto LABEL_77;
  }
  v16 = *(_QWORD *)a2;
  v52 = 0;
  v14 = (*(__int64 (__fastcall **)(struct ISmMessage *, unsigned int *))(v16 + 632))(a2, &v52);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1703;
    goto LABEL_17;
  }
  v57 = 0;
  v14 = SmMessageStatusToChatMessageStatus(v53, v51 == 0, v52, &v57);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1706;
    goto LABEL_17;
  }
  v17 = *(_QWORD *)a2;
  v46 = 0;
  v18 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v17 + 168))(a2, &v46);
  v12 = v18;
  if ( v18 < 0 )
  {
    v19 = 1709;
LABEL_22:
    Log_HREvent(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      v19);
LABEL_23:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v46);
    goto LABEL_77;
  }
  v48 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v48);
  v12 = v18;
  if ( v18 < 0 )
  {
    v19 = 1712;
    goto LABEL_22;
  }
  if ( !v48 )
  {
    v20 = *(_QWORD *)a2;
    v54 = -1;
    v18 = (*(__int64 (__fastcall **)(struct ISmMessage *, unsigned int *))(v20 + 560))(a2, &v54);
    v12 = v18;
    if ( v18 < 0 )
    {
      v19 = 1721;
      goto LABEL_22;
    }
    if ( !(unsigned int)Messaging_IsCustomAppProviderId(v54) )
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x4000) != 0 )
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
          ChatMessageWithoutRecipients,
          v21,
          1,
          &v73);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v46);
      v12 = 0;
      goto LABEL_77;
    }
  }
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v62);
  if ( !(unsigned __int8)utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::_Resize<,0>(v62) )
  {
    v12 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      1731);
LABEL_35:
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::_Uninit(v62);
    goto LABEL_23;
  }
  v22 = (char *)v62[0];
  v23 = 0;
  v24 = v64;
  while ( v23 < v48 )
  {
    v47 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v46 + 48LL))(v46, v23, &v47);
    v12 = v25;
    if ( v25 < 0 )
    {
      v38 = 1738;
      v39 = 1;
      goto LABEL_71;
    }
    v26 = v47;
    v27 = &v22[8 * v23];
    v28 = *(__int64 (__fastcall **)(__int64 *, _QWORD *))(*v47 + 24);
    v29 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v27);
    v25 = v28(v26, v29);
    v12 = v25;
    if ( v25 < 0 )
    {
      v38 = 1740;
LABEL_62:
      v39 = 1;
LABEL_71:
      v40 = (unsigned int)v25;
      goto LABEL_72;
    }
    v30 = 0;
    if ( v55 )
    {
      if ( _wcsicmp(bstrString, *(const wchar_t **)v27) )
      {
        v56 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v47 + 40))(v47, &v56);
        v12 = v25;
        if ( v25 < 0 )
        {
          v38 = 1751;
          goto LABEL_62;
        }
        if ( v56 == 1 )
          v30 = ComparePhoneNumbers(bstrString, *(_QWORD *)v27, 0) != 0;
      }
      else
      {
        v30 = 1;
      }
    }
    v31 = *(const wchar_t **)v27;
    v32 = 0;
    v33 = v57;
    *(_QWORD *)&v66 = v31;
    v58 = 0;
    v34 = *v47;
    *(_OWORD *)v68 = 0;
    DWORD2(v66) = v57;
    v12 = (*(__int64 (__fastcall **)(__int64 *, int *))(v34 + 72))(v47, &v58);
    if ( (v12 & 0x80000000) != 0 )
    {
      v38 = 1768;
      v39 = 1;
LABEL_68:
      v40 = v12;
LABEL_72:
      Log_HREvent(
        v40,
        v39,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v38);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
      goto LABEL_35;
    }
    if ( v58 < 0 )
    {
      v60 = 0;
      v59 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *))(*v47 + 104))(v47, &v60, &v59);
      v12 = v25;
      if ( v25 < 0 )
      {
        v38 = 1774;
        goto LABEL_62;
      }
      if ( (unsigned int)Messaging_IsMmsMessage(a2) )
      {
        v35 = 2;
      }
      else
      {
        v35 = 1;
        if ( (unsigned int)Messaging_IsRcsMessage(a2) )
          v35 = 4;
      }
      v25 = PopulateErrorProperties(v60, v59, v35, &v66);
      v12 = v25;
      if ( v25 < 0 )
      {
        v38 = 1786;
        goto LABEL_62;
      }
      v61 = 0;
      v25 = AdjustChatMessageStatus(v33, v36, v68[3], &v61);
      v12 = v25;
      if ( v25 < 0 )
      {
        v38 = 1789;
        goto LABEL_62;
      }
      v32 = _mm_loadu_si128((const __m128i *)v68);
      DWORD2(v66) = v61;
    }
    HIDWORD(v66) = v30;
    *(_QWORD *)&v67 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64 *, char *))(*v47 + 128))(v47, v72);
    *((_QWORD *)&v67 + 1) = *(_QWORD *)(*(__int64 (__fastcall **)(__int64 *, unsigned __int64 *))(*v47 + 144))(
                                         v47,
                                         &v73);
    if ( v24 == v65 )
    {
      if ( !utl::vector<ServiceAllCallsEnum::CallItemData,utl::allocator<ServiceAllCallsEnum::CallItemData>>::_PushBackOne2<ServiceAllCallsEnum::CallItemData const &>(
              (__int64 *)&Block,
              &v66) )
      {
        v38 = 1798;
        v39 = 0;
        v12 = -2147024882;
        goto LABEL_68;
      }
      v24 = v64;
    }
    else
    {
      v37 = v67;
      *(_OWORD *)v24 = v66;
      *((_OWORD *)v24 + 1) = v37;
      *((__m128i *)v24 + 2) = v32;
      v24 += 48;
      v64 = v24;
    }
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
    ++v23;
  }
  v41 = (char *)Block;
  v73 = 0;
  v74 = 0;
  *v69 = 1;
  if ( v41 != v24 )
  {
    v74 = v41;
    v73 = 0xAAAAAAAAAAAAAAABuLL * ((v24 - v41) >> 4);
  }
  v42 = FlattenItemsToSend<UdmChatParticipant>(&v73, v71, v70);
  v44 = v42;
  if ( v42 >= 0 )
  {
    if ( v22 != (char *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(
        v43,
        v22,
        ((char *)v62[1] - (char *)v22) >> 3);
      operator delete(v22);
    }
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v41 != (char *)-1LL )
      operator delete(v41);
    v12 = 0;
    goto LABEL_87;
  }
  Log_HREvent(
    (unsigned int)v42,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
    1802);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::_Uninit(v62);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v46);
  v12 = v44;
LABEL_77:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&bstrString);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&Block);
  tlx::_UndoSolo__lambda_0dd625d3762276213498069ae0a32357___::__UndoSolo__lambda_0dd625d3762276213498069ae0a32357___(v49);
  return v12;
}

```

## disassembly

```asm
0x180061a9c  mov     rax, rsp
0x180061a9f  mov     [rax+8], rbx
0x180061aa3  push    rbp
0x180061aa4  push    rsi
0x180061aa5  push    rdi
0x180061aa6  push    r12
0x180061aa8  push    r13
0x180061aaa  push    r14
0x180061aac  push    r15
0x180061aae  lea     rbp, [rax-68h]
0x180061ab2  sub     rsp, 130h
0x180061ab9  movaps  xmmword ptr [rax-48h], xmm6
0x180061abd  mov     rax, cs:__security_cookie
0x180061ac4  xor     rax, rsp
0x180061ac7  mov     [rbp+60h+var_50], rax
0x180061acb  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x180061ad2  lea     r15, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x180061ad9  mov     rbx, [rbp+60h+arg_20]
0x180061ae0  mov     r13, r9
0x180061ae3  mov     [rbp+60h+var_78], rbx
0x180061ae7  mov     rdi, r8
0x180061aea  mov     [rbp+60h+var_70], r9
0x180061aee  mov     r14, rdx
0x180061af1  mov     [rbp+60h+var_80], r8
0x180061af5  mov     esi, 1
0x180061afa  jz      short loc_180061B17
0x180061afc  lea     rax, [rbp+60h+var_60]
0x180061b00  mov     r9d, esi
0x180061b03  lea     rdx, ChatOperationContextGetMessageParticipants
0x180061b0a  mov     [rsp+160h+var_140], rax
0x180061b0f  mov     rcx, r15
0x180061b12  call    McGenEventWrite_EventWriteTransfer
0x180061b17  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, sil
0x180061b1e  jz      short loc_180061B3B
0x180061b20  lea     rax, [rbp+60h+var_60]
0x180061b24  mov     r9d, esi
0x180061b27  lea     rdx, Chat_GetMessageParticipants_START
0x180061b2e  mov     [rsp+160h+var_140], rax
0x180061b33  mov     rcx, r15
0x180061b36  call    McGenEventWrite_EventWriteTransfer
0x180061b3b  mov     dword ptr [rdi], 0
0x180061b41  lea     rcx, [rbp+60h+Block]
0x180061b45  mov     dword ptr [r13+0], 0
0x180061b4d  xor     r13d, r13d
0x180061b50  mov     [rbx], r13
0x180061b53  mov     byte ptr [rsp+160h+var_120+5], sil
0x180061b58  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180061b5d  mov     rax, [r14]
0x180061b60  lea     rdx, [rsp+160h+bstrString]
0x180061b65  mov     rcx, r14
0x180061b68  mov     [rsp+160h+var_100], r13d
0x180061b6d  mov     [rsp+160h+bstrString], r13
0x180061b72  mov     rax, [rax+1F0h]
0x180061b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b7e  lea     rdi, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180061b85  test    eax, eax
0x180061b87  js      short loc_180061BA2
0x180061b89  mov     [rsp+160h+var_100], esi
0x180061b8d  cmp     [rsp+160h+bstrString], r13
0x180061b92  jnz     short loc_180061BA2
0x180061b94  mov     r8d, 69Dh
0x180061b9a  mov     rdx, rdi
0x180061b9d  call    Log_AssertionEvent_2
0x180061ba2  mov     rax, [r14]
0x180061ba5  lea     rdx, [rsp+160h+var_108]
0x180061baa  mov     rcx, r14
0x180061bad  mov     [rsp+160h+var_108], r13d
0x180061bb2  mov     rax, [rax+220h]
0x180061bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bbe  mov     ebx, eax
0x180061bc0  test    eax, eax
0x180061bc2  jns     short loc_180061C05
0x180061bc4  mov     r9d, 6A1h
0x180061bca  mov     r8, rdi
0x180061bcd  mov     edx, esi
0x180061bcf  mov     ecx, eax
0x180061bd1  call    Log_HREvent
0x180061bd6  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180061bdb  test    rcx, rcx
0x180061bde  jz      short loc_180061BE6
0x180061be0  call    cs:__imp_SysFreeString
0x180061be6  mov     rcx, [rbp+60h+Block]; Block
0x180061bea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061bee  jz      loc_180062190
0x180061bf4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180061bfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061c00  jmp     loc_180062190
0x180061c05  mov     rax, [r14]
0x180061c08  lea     rdx, [rsp+160h+var_110]
0x180061c0d  mov     rcx, r14
0x180061c10  mov     [rsp+160h+var_110], r13d
0x180061c15  mov     rax, [rax+1B0h]
0x180061c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c21  mov     ebx, eax
0x180061c23  test    eax, eax
0x180061c25  jns     short loc_180061C2F
0x180061c27  mov     r9d, 6A4h
0x180061c2d  jmp     short loc_180061C57
0x180061c2f  mov     rax, [r14]
0x180061c32  lea     rdx, [rsp+160h+var_10C]
0x180061c37  mov     rcx, r14
0x180061c3a  mov     [rsp+160h+var_10C], r13d
0x180061c3f  mov     rax, [rax+278h]
0x180061c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c4b  mov     ebx, eax
0x180061c4d  test    eax, eax
0x180061c4f  jns     short loc_180061C68
0x180061c51  mov     r9d, 6A7h
0x180061c57  mov     r8, rdi
0x180061c5a  mov     edx, esi
0x180061c5c  mov     ecx, eax
0x180061c5e  call    Log_HREvent
0x180061c63  jmp     loc_18006210B
0x180061c68  cmp     [rsp+160h+var_110], r13d
0x180061c6d  lea     r9, [rsp+160h+var_F8]
0x180061c72  mov     r8d, [rsp+160h+var_10C]
0x180061c77  mov     edx, r13d
0x180061c7a  mov     ecx, [rsp+160h+var_108]
0x180061c7e  setz    dl
0x180061c81  mov     [rsp+160h+var_F8], r13d
0x180061c86  call    ?SmMessageStatusToChatMessageStatus@@YAJW4SmMessageStatus@@HW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0003@@PEAK@Z; SmMessageStatusToChatMessageStatus(SmMessageStatus,int,__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0003,ulong *)
0x180061c8b  mov     ebx, eax
0x180061c8d  test    eax, eax
0x180061c8f  jns     short loc_180061C99
0x180061c91  mov     r9d, 6AAh
0x180061c97  jmp     short loc_180061C57
0x180061c99  mov     rax, [r14]
0x180061c9c  lea     rdx, [rsp+160h+var_130]
0x180061ca1  mov     rcx, r14
0x180061ca4  mov     [rsp+160h+var_130], r13
0x180061ca9  mov     rax, [rax+0A8h]
0x180061cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061cb5  mov     ebx, eax
0x180061cb7  test    eax, eax
0x180061cb9  jns     short loc_180061CDC
0x180061cbb  mov     r9d, 6ADh
0x180061cc1  mov     r8, rdi
0x180061cc4  mov     edx, esi
0x180061cc6  mov     ecx, eax
0x180061cc8  call    Log_HREvent
0x180061ccd  lea     rcx, [rsp+160h+var_130]
0x180061cd2  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180061cd7  jmp     loc_18006210B
0x180061cdc  mov     rcx, [rsp+160h+var_130]
0x180061ce1  lea     rdx, [rsp+160h+var_120]
0x180061ce6  mov     dword ptr [rsp+160h+var_120], r13d
0x180061ceb  mov     rax, [rcx]
0x180061cee  mov     rax, [rax+38h]
0x180061cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061cf7  mov     ebx, eax
0x180061cf9  test    eax, eax
0x180061cfb  jns     short loc_180061D05
0x180061cfd  mov     r9d, 6B0h
0x180061d03  jmp     short loc_180061CC1
0x180061d05  mov     edx, dword ptr [rsp+160h+var_120]
0x180061d09  test    edx, edx
0x180061d0b  jnz     short loc_180061D82
0x180061d0d  mov     rax, [r14]
0x180061d10  lea     rdx, [rsp+160h+var_104]
0x180061d15  mov     rcx, r14
0x180061d18  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x180061d20  mov     rax, [rax+230h]
0x180061d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d2c  mov     ebx, eax
0x180061d2e  test    eax, eax
0x180061d30  jns     short loc_180061D3A
0x180061d32  mov     r9d, 6B9h
0x180061d38  jmp     short loc_180061CC1
0x180061d3a  mov     ecx, [rsp+160h+var_104]
0x180061d3e  call    cs:__imp_Messaging_IsCustomAppProviderId
0x180061d44  test    eax, eax
0x180061d46  jnz     short loc_180061D7E
0x180061d48  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+1, 40h
0x180061d4f  jz      short loc_180061D6C
0x180061d51  lea     rax, [rbp+60h+var_60]
0x180061d55  mov     r9d, esi
0x180061d58  lea     rdx, ChatMessageWithoutRecipients
0x180061d5f  mov     [rsp+160h+var_140], rax
0x180061d64  mov     rcx, r15
0x180061d67  call    McGenEventWrite_EventWriteTransfer
0x180061d6c  lea     rcx, [rsp+160h+var_130]
0x180061d71  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180061d76  mov     ebx, r13d
0x180061d79  jmp     loc_18006210B
0x180061d7e  mov     edx, dword ptr [rsp+160h+var_120]
0x180061d82  lea     rcx, [rbp+60h+var_E0]
0x180061d86  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180061d8b  lea     rcx, [rbp+60h+var_E0]
0x180061d8f  call    ??$_Resize@$$V$0A@@?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::_Resize<,0>(unsigned __int64)
0x180061d94  test    al, al
0x180061d96  jnz     short loc_180061DBD
0x180061d98  mov     ebx, 8007000Eh
0x180061d9d  mov     r9d, 6C3h
0x180061da3  mov     ecx, ebx
0x180061da5  mov     r8, rdi
0x180061da8  xor     edx, edx
0x180061daa  call    Log_HREvent
0x180061daf  lea     rcx, [rbp+60h+var_E0]
0x180061db3  call    ?_Uninit@?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@AEAAXXZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::_Uninit(void)
0x180061db8  jmp     loc_180061CCD
0x180061dbd  mov     r15, [rbp+60h+var_E0]
0x180061dc1  mov     r12d, r13d
0x180061dc4  mov     rsi, [rbp+60h+var_C0]
0x180061dc8  mov     edi, 1
0x180061dcd  cmp     r12d, dword ptr [rsp+160h+var_120]
0x180061dd2  jnb     loc_180062092
0x180061dd8  mov     rcx, [rsp+160h+var_130]
0x180061ddd  lea     r8, [rsp+160h+var_128]
0x180061de2  mov     [rsp+160h+var_128], r13
0x180061de7  mov     edx, r12d
0x180061dea  mov     rax, [rcx]
0x180061ded  mov     rax, [rax+30h]
0x180061df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061df6  mov     ebx, eax
0x180061df8  test    eax, eax
0x180061dfa  js      loc_18006206D
0x180061e00  mov     rdi, [rsp+160h+var_128]
0x180061e05  mov     edx, r12d
0x180061e08  mov     rax, [rdi]
0x180061e0b  lea     r13, [r15+rdx*8]
0x180061e0f  mov     rcx, r13
0x180061e12  mov     rbx, [rax+18h]
0x180061e16  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x180061e1b  mov     rdx, rax
0x180061e1e  mov     rcx, rdi
0x180061e21  mov     rax, rbx
0x180061e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e29  mov     ebx, eax
0x180061e2b  test    eax, eax
0x180061e2d  js      loc_180062065
0x180061e33  xor     edi, edi
0x180061e35  cmp     [rsp+160h+var_100], edi
0x180061e39  jz      short loc_180061E99
0x180061e3b  mov     rdx, [r13+0]; String2
0x180061e3f  mov     rcx, [rsp+160h+bstrString]; String1
0x180061e44  call    cs:__imp__wcsicmp
0x180061e4a  test    eax, eax
0x180061e4c  jnz     short loc_180061E53
0x180061e4e  lea     edi, [rax+1]
0x180061e51  jmp     short loc_180061E99
0x180061e53  mov     rcx, [rsp+160h+var_128]
0x180061e58  lea     rdx, [rsp+160h+var_FC]
0x180061e5d  mov     [rsp+160h+var_FC], edi
0x180061e61  mov     rax, [rcx]
0x180061e64  mov     rax, [rax+28h]
0x180061e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e6d  mov     ebx, eax
0x180061e6f  test    eax, eax
0x180061e71  js      loc_180062022
0x180061e77  mov     ebx, 1
0x180061e7c  cmp     [rsp+160h+var_FC], ebx
0x180061e80  jnz     short loc_180061E99
0x180061e82  mov     rdx, [r13+0]
0x180061e86  xor     r8d, r8d
0x180061e89  mov     rcx, [rsp+160h+bstrString]
0x180061e8e  call    cs:__imp_ComparePhoneNumbers
0x180061e94  test    eax, eax
0x180061e96  cmovnz  edi, ebx
0x180061e99  mov     rax, [r13+0]
0x180061e9d  lea     rdx, [rsp+160h+var_F4]
0x180061ea2  mov     rcx, [rsp+160h+var_128]
0x180061ea7  xorps   xmm6, xmm6
0x180061eaa  mov     r13d, [rsp+160h+var_F8]
0x180061eaf  mov     qword ptr [rbp+60h+var_B0], rax
0x180061eb3  mov     [rsp+160h+var_F4], 0
0x180061ebb  mov     rax, [rcx]
0x180061ebe  movdqu  xmmword ptr [rbp+60h+var_90], xmm6
0x180061ec3  mov     dword ptr [rbp+60h+var_B0+8], r13d
0x180061ec7  mov     rax, [rax+48h]
0x180061ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ed0  mov     ebx, eax
0x180061ed2  xor     eax, eax
0x180061ed4  test    ebx, ebx
0x180061ed6  js      loc_180062056
0x180061edc  cmp     [rsp+160h+var_F4], eax
0x180061ee0  jge     loc_180061F8F
0x180061ee6  mov     rcx, [rsp+160h+var_128]
0x180061eeb  lea     r8, [rsp+160h+var_F0]
0x180061ef0  mov     [rsp+160h+var_EC], eax
0x180061ef4  lea     rdx, [rsp+160h+var_EC]
0x180061ef9  mov     [rsp+160h+var_F0], eax
0x180061efd  mov     rax, [rcx]
0x180061f00  mov     rax, [rax+68h]
0x180061f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f09  mov     ebx, eax
0x180061f0b  test    eax, eax
0x180061f0d  js      loc_18006203F
0x180061f13  mov     rcx, r14
0x180061f16  call    cs:__imp_Messaging_IsMmsMessage
0x180061f1c  test    eax, eax
0x180061f1e  jz      short loc_180061F27
0x180061f20  mov     ebx, 2
0x180061f25  jmp     short loc_180061F3D
0x180061f27  mov     rcx, r14
0x180061f2a  mov     ebx, 1
0x180061f2f  call    cs:__imp_Messaging_IsRcsMessage
0x180061f35  test    eax, eax
0x180061f37  lea     ecx, [rbx+3]
0x180061f3a  cmovnz  ebx, ecx
0x180061f3d  mov     edx, [rsp+160h+var_F0]
  ... truncated ...
```
