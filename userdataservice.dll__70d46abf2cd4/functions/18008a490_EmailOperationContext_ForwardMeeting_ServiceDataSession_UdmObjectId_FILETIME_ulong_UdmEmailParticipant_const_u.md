# EmailOperationContext::ForwardMeeting(ServiceDataSession *,UdmObjectId,_FILETIME,ulong,UdmEmailParticipant const *,ushort const *,UdmEmailMessageBodyKind,ushort const *,ushort const *)

- ea: `0x18008a490`
- end: `0x18008aa39`
- name: `?ForwardMeeting@EmailOperationContext@@QEAAJPEAVServiceDataSession@@UUdmObjectId@@U_FILETIME@@KPEBUUdmEmailParticipant@@PEBGW4UdmEmailMessageBodyKind@@44@Z`
- size: `1449`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b6dc0`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18000bb30`
- `0x180012988`
- `0x180022fa8`
- `0x18003cda4`
- `0x18003ed7c`
- `0x180063fac`
- `0x18006f820`
- `0x18006fc80`
- `0x18007065c`
- `0x180070c10`
- `0x18007ba18`
- `0x18008a490`
- `0x18008aa40`
- `0x1800b6288`
- `0x1800c65a8`
- `0x180114890`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `CEMAPI!HrSetOneProp` at `0x18008a81c`
- `CEMAPI!HrSetOneProp` at `0x18008a97d`
- `CEMAPI!HrSetOneProp` at `0x18008a81c`
- `CEMAPI!HrSetOneProp` at `0x18008a97d`
- `CEMAPI!HrGetOneProp` at `0x18008a63a`
- `CEMAPI!HrGetOneProp` at `0x18008a942`
- `CEMAPI!HrGetOneProp` at `0x18008a63a`
- `CEMAPI!HrGetOneProp` at `0x18008a942`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a683`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a71a`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a743`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a958`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a683`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a71a`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a743`
- `CEMAPI!MAPIFreeBuffer` at `0x18008a958`

## string_xrefs

- `0x18008a540`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a609`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a660`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a701`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a787`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a82e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a881`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a90e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008a9cf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18008aa07`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`

## pseudocode

```c
__int64 __fastcall EmailOperationContext::ForwardMeeting(
        EmailOperationContext *a1,
        struct ServiceDataSession *a2,
        __int64 a3,
        struct _FILETIME a4,
        unsigned int a5,
        void *a6,
        unsigned __int64 a7,
        unsigned int a8,
        void *a9,
        unsigned __int16 *a10)
{
  int v13; // eax
  __int64 v14; // r9
  struct ServiceDataSession *v15; // rcx
  int v16; // eax
  unsigned int v17; // esi
  unsigned int v19; // ebx
  bool v20; // zf
  int ResponseMessageInStore; // eax
  struct IMessage **v22; // r9
  __int64 v23; // r9
  void **v24; // rax
  struct IMAPIProp *v25; // rbx
  HRESULT OneProp; // esi
  __int64 v27; // r9
  __int128 *v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  HRESULT v34; // eax
  HRESULT updated; // esi
  struct ServiceDataSession *v36; // r8
  unsigned __int16 **v37; // rax
  __int64 v38; // r9
  __int64 v39; // r9
  int v40; // esi
  void **v41; // rax
  int v42; // r8d
  int v43; // eax
  struct IMsgStore *v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v46; // [rsp+7Ch] [rbp-84h]
  struct ServiceDataSession *v47; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  int v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v50; // [rsp+94h] [rbp-6Ch] BYREF
  LPMAPIPROP lpMapiProp; // [rsp+98h] [rbp-68h] BYREF
  struct _SBinary v52; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v54; // [rsp+C0h] [rbp-40h]
  struct _SPropValue Prop; // [rsp+C8h] [rbp-38h] BYREF
  struct _SPropValue v56; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v57[2]; // [rsp+F8h] [rbp-8h] BYREF
  char v58; // [rsp+108h] [rbp+8h]
  __int128 v59; // [rsp+110h] [rbp+10h] BYREF
  int lpVtbl; // [rsp+120h] [rbp+20h]

  v46 = a5;
  v54 = a6;
  v53[0] = a9;
  v13 = *(_DWORD *)(a3 + 4) - 8;
  v47 = a2;
  if ( (v13 & 0xFFFFFFFB) != 0 )
  {
    v14 = 3314;
LABEL_67:
    v19 = -2147024809;
    goto LABEL_68;
  }
  v15 = (struct ServiceDataSession *)*((_QWORD *)a1 + 1);
  v49 = 0;
  v16 = ServiceDataSession::ValidateCallerSecurityForId(v15, a3, 0, 0, (enum ObjectAccess *)&v49);
  v17 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      3317);
    return v17;
  }
  if ( v49 < 1 )
  {
    v14 = 3318;
    v19 = -2147024891;
LABEL_68:
    Log_HREvent(
      v19,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      v14);
    return v19;
  }
  if ( !v46 || !v54 )
  {
    v14 = 3320;
    goto LABEL_67;
  }
  v45 = 0;
  v20 = *(_DWORD *)(a3 + 4) == 8;
  lpVtbl = 0;
  v58 = 1;
  v57[0] = &v45;
  v57[1] = &v59;
  v59 = 0;
  lpMapiProp = 0;
  v44 = 0;
  if ( !v20 )
  {
    v50 = 0;
    v30 = CreateForwardMessage(v47, (const struct UdmObjectId *)a3, a4, &v50, (unsigned __int8 **)&v44);
    v19 = v30;
    if ( v30 < 0 )
    {
      v31 = 3373;
LABEL_31:
      v32 = 1;
      v33 = (unsigned int)v30;
LABEL_32:
      Log_HREvent(
        v33,
        v32,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v31);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v44);
      goto LABEL_65;
    }
    if ( v50 != 20 )
    {
      v19 = -2147418113;
      v31 = 3375;
      v33 = 2147549183LL;
      v32 = 0;
      goto LABEL_32;
    }
    *(_QWORD *)&v52.cb = 20;
    v52.lpb = (LPBYTE)v44;
    v59 = *(_OWORD *)&v44->lpVtbl;
    lpVtbl = (int)v44[2].lpVtbl;
    v45 = 1;
    v30 = EmailOperationContext::OpenItemByMapiId(a1, &v52, (struct IUnknown **)&lpMapiProp, 0);
    v19 = v30;
    if ( v30 < 0 )
    {
      v31 = 3383;
      goto LABEL_31;
    }
    v25 = lpMapiProp;
    if ( a7 )
    {
      *(_QWORD *)&Prop.ulPropTag = 3604511;
      Prop.Value = (union _PV)a7;
      v34 = HrSetOneProp(lpMapiProp, &Prop);
      updated = v34;
      if ( v34 < 0 )
      {
        Log_HREvent(
          (unsigned int)v34,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          3390);
LABEL_40:
        auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v44);
LABEL_41:
        v19 = updated;
        goto LABEL_65;
      }
    }
    v47 = 0;
    v36 = 0;
    if ( a10 && *a10 )
    {
      v37 = (unsigned __int16 **)tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
      updated = ConvertPlainTextStringToHtmlString(a10, v37);
      if ( updated < 0 )
      {
        v38 = 3396;
LABEL_46:
        Log_HREvent(
          (unsigned int)updated,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          v38);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
        goto LABEL_40;
      }
      v36 = v47;
    }
    updated = EmailHelper::SetResponseMessageBodies(v25, a10, v36, a8, v53[0], 0, 0);
    if ( updated >= 0 )
    {
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v47);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v44);
LABEL_51:
      v53[0] = (LPVOID)v46;
      v53[1] = v54;
      updated = EmailOperationContext::UpdateRecipients(v29, v25, v53);
      if ( updated >= 0 )
      {
        v53[0] = 0;
        v40 = 0;
        v41 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(v53);
        if ( HrGetOneProp(v25, 0xE170003u, (LPSPropValue *)v41) >= 0 )
          v40 = *((_DWORD *)v53[0] + 2);
        if ( v53[0] )
          MAPIFreeBuffer(v53[0]);
        memset(&v56, 0, sizeof(v56));
        v56.ulPropTag = 236388355;
        v56.Value.l = v40 | 0x20000;
        updated = HrSetOneProp(v25, &v56);
        if ( updated >= 0 )
        {
          updated = EmailHelper::EncodeBodyForSend((EmailHelper *)v25, 0, v42);
          if ( updated >= 0 )
          {
            v43 = ((__int64 (__fastcall *)(struct IMAPIProp *, _QWORD))v25->lpVtbl[1].GetPropList)(v25, 0);
            v19 = v43;
            if ( v43 >= 0 )
            {
              v58 = 0;
              v19 = 0;
            }
            else
            {
              Log_HREvent(
                (unsigned int)v43,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
                3430);
            }
            goto LABEL_65;
          }
          v39 = 3428;
        }
        else
        {
          v39 = 3423;
        }
      }
      else
      {
        v39 = 3409;
      }
      Log_HREvent(
        (unsigned int)updated,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v39);
      goto LABEL_41;
    }
    v38 = 3406;
    goto LABEL_46;
  }
  *(_QWORD *)&v52.cb = 0;
  ResponseMessageInStore = EmailOperationContext::MapiOpenItemById(
                             a1,
                             (const struct UdmObjectId *)a3,
                             0,
                             (struct IUnknown **)&v52,
                             &v44);
  v19 = ResponseMessageInStore;
  if ( ResponseMessageInStore >= 0 )
  {
    ResponseMessageInStore = EmailHelper::CreateResponseMessageInStore(
                               (EmailHelper *)v44,
                               *(struct IMsgStore **)&v52.cb,
                               (struct IMessage *)&lpMapiProp,
                               v22);
    v19 = ResponseMessageInStore;
    if ( ResponseMessageInStore < 0 )
    {
      v23 = 3340;
      goto LABEL_14;
    }
    pv = 0;
    v24 = tlx::replace<_SPropValue,&void FreeSPropValueArray(_SPropValue *)>(&pv);
    v25 = lpMapiProp;
    OneProp = HrGetOneProp(lpMapiProp, 0xFFF0102u, (LPSPropValue *)v24);
    if ( OneProp < 0 )
    {
      v27 = 3343;
LABEL_22:
      Log_HREvent(
        (unsigned int)OneProp,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v27);
      if ( pv )
        MAPIFreeBuffer(pv);
      v19 = OneProp;
      goto LABEL_25;
    }
    if ( *((_DWORD *)pv + 2) != 20 )
    {
      v19 = -2147418113;
      Log_HREvent(
        2147549183LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        3344);
      if ( pv )
        MAPIFreeBuffer(pv);
      goto LABEL_25;
    }
    v28 = (__int128 *)*((_QWORD *)pv + 2);
    v59 = *v28;
    lpVtbl = *((_DWORD *)v28 + 4);
    v45 = 1;
    OneProp = EmailHelper::SetupResponseMessage(
                a1,
                v44,
                *(_QWORD *)&v52.cb,
                v25,
                1,
                3,
                a7,
                a10,
                a8,
                v53[0],
                v46,
                v54,
                1);
    if ( OneProp < 0 )
    {
      v27 = 3361;
      goto LABEL_22;
    }
    if ( pv )
      MAPIFreeBuffer(pv);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
    goto LABEL_51;
  }
  v23 = 3338;
LABEL_14:
  Log_HREvent(
    (unsigned int)ResponseMessageInStore,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
    v23);
LABEL_25:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
LABEL_65:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&lpMapiProp);
  tlx::_UndoSolo__lambda_42e6fbd1104eb5a4bfc2879c6ffef21e___::__UndoSolo__lambda_42e6fbd1104eb5a4bfc2879c6ffef21e___(v57);
  return v19;
}

```

## disassembly

```asm
0x18008a490  push    rbp
0x18008a492  push    rbx
0x18008a493  push    rsi
0x18008a494  push    rdi
0x18008a495  push    r12
0x18008a497  push    r13
0x18008a499  push    r14
0x18008a49b  push    r15
0x18008a49d  lea     rbp, [rsp-38h]
0x18008a4a2  sub     rsp, 138h
0x18008a4a9  mov     rax, cs:__security_cookie
0x18008a4b0  xor     rax, rsp
0x18008a4b3  mov     [rbp+70h+var_48], rax
0x18008a4b7  mov     eax, [rbp+70h+arg_20]
0x18008a4bd  mov     rbx, r9
0x18008a4c0  mov     r12, [rbp+70h+arg_30]
0x18008a4c7  mov     r15, r8
0x18008a4ca  mov     r14, [rbp+70h+arg_48]
0x18008a4d1  mov     r13, rcx
0x18008a4d4  mov     [rsp+170h+var_F4], eax
0x18008a4d8  mov     rax, [rbp+70h+arg_28]
0x18008a4df  mov     [rbp+70h+var_B0], rax
0x18008a4e3  mov     rax, [rbp+70h+arg_40]
0x18008a4ea  mov     [rbp+70h+var_C0], rax
0x18008a4ee  mov     eax, [r8+4]
0x18008a4f2  sub     eax, 8
0x18008a4f5  mov     [rbp+70h+var_F0], rdx
0x18008a4f9  test    eax, 0FFFFFFFBh
0x18008a4fe  jz      short loc_18008A50B
0x18008a500  mov     r9d, 0CF2h
0x18008a506  jmp     loc_18008AA02
0x18008a50b  mov     rcx, [rcx+8]
0x18008a50f  lea     rax, [rbp+70h+var_E0]
0x18008a513  xor     r9d, r9d
0x18008a516  mov     [rsp+170h+var_150], rax
0x18008a51b  xor     r8d, r8d
0x18008a51e  mov     [rbp+70h+var_E0], 0
0x18008a525  mov     rdx, r15
0x18008a528  call    ?ValidateCallerSecurityForId@ServiceDataSession@@QEAAJAEBUUdmObjectId@@W4DataSessionAccessType@@PEAW4ObjectAccess@@2@Z; ServiceDataSession::ValidateCallerSecurityForId(UdmObjectId const &,DataSessionAccessType,ObjectAccess *,ObjectAccess *)
0x18008a52d  xor     ecx, ecx
0x18008a52f  mov     esi, eax
0x18008a531  test    eax, eax
0x18008a533  jns     short loc_18008A553
0x18008a535  lea     edx, [rcx+1]
0x18008a538  mov     r9d, 0CF5h
0x18008a53e  mov     ecx, eax
0x18008a540  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a547  call    Log_HREvent
0x18008a54c  mov     eax, esi
0x18008a54e  jmp     loc_18008AA19
0x18008a553  mov     edi, 1
0x18008a558  cmp     [rbp+70h+var_E0], edi
0x18008a55b  jge     short loc_18008A56D
0x18008a55d  mov     r9d, 0CF6h
0x18008a563  mov     ebx, 80070005h
0x18008a568  jmp     loc_18008AA07
0x18008a56d  cmp     [rsp+170h+var_F4], ecx
0x18008a571  jz      loc_18008A9FC
0x18008a577  cmp     [rbp+70h+var_B0], rcx
0x18008a57b  jz      loc_18008A9FC
0x18008a581  xor     eax, eax
0x18008a583  mov     [rsp+170h+var_F8], ecx
0x18008a587  cmp     dword ptr [r15+4], 8
0x18008a58c  xorps   xmm0, xmm0
0x18008a58f  mov     [rbp+70h+var_50], eax
0x18008a592  mov     rdx, r15; struct UdmObjectId *
0x18008a595  lea     rax, [rsp+170h+var_F8]
0x18008a59a  mov     [rbp+70h+var_68], dil
0x18008a59e  mov     [rbp+70h+var_78], rax
0x18008a5a2  lea     rax, [rbp+70h+var_60]
0x18008a5a6  mov     [rbp+70h+var_70], rax
0x18008a5aa  lea     rax, [rsp+170h+var_100]
0x18008a5af  mov     [rsp+170h+var_150], rax; unsigned __int8 **
0x18008a5b4  movups  [rbp+70h+var_60], xmm0
0x18008a5b8  mov     [rbp+70h+lpMapiProp], rcx
0x18008a5bc  mov     [rsp+170h+var_100], rcx
0x18008a5c1  jnz     loc_18008A761
0x18008a5c7  mov     qword ptr [rbp+70h+var_D0.cb], rcx
0x18008a5cb  lea     r9, [rbp+70h+var_D0]; struct IUnknown **
0x18008a5cf  mov     rcx, r13; this
0x18008a5d2  xor     r8d, r8d; int
0x18008a5d5  call    ?MapiOpenItemById@EmailOperationContext@@QEAAJAEBUUdmObjectId@@HPEAPEAUIUnknown@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::MapiOpenItemById(UdmObjectId const &,int,IUnknown * *,IMsgStore * *)
0x18008a5da  xor     r15d, r15d
0x18008a5dd  mov     ebx, eax
0x18008a5df  test    eax, eax
0x18008a5e1  jns     short loc_18008A5EB
0x18008a5e3  mov     r9d, 0D0Ah
0x18008a5e9  jmp     short loc_18008A609
0x18008a5eb  mov     rdx, qword ptr [rbp+70h+var_D0.cb]; struct IMsgStore *
0x18008a5ef  lea     r8, [rbp+70h+lpMapiProp]; struct IMessage *
0x18008a5f3  mov     rcx, [rsp+170h+var_100]; this
0x18008a5f8  call    ?CreateResponseMessageInStore@EmailHelper@@YAJPEAUIMsgStore@@PEAUIMessage@@PEAPEAU3@@Z; EmailHelper::CreateResponseMessageInStore(IMsgStore *,IMessage *,IMessage * *)
0x18008a5fd  mov     ebx, eax
0x18008a5ff  test    eax, eax
0x18008a601  jns     short loc_18008A61E
0x18008a603  mov     r9d, 0D0Ch
0x18008a609  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a610  mov     edx, edi
0x18008a612  mov     ecx, eax
0x18008a614  call    Log_HREvent
0x18008a619  jmp     loc_18008A722
0x18008a61e  lea     rcx, [rbp+70h+pv]
0x18008a622  mov     [rbp+70h+pv], r15
0x18008a626  call    ??$replace@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_array_ptr@U_SPropValue@@$1?FreeSPropValueArray@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SPropValue,&FreeSPropValueArray(_SPropValue *)>(tlx::auto_array_ptr<_SPropValue,&FreeSPropValueArray(_SPropValue *)> &)
0x18008a62b  mov     rbx, [rbp+70h+lpMapiProp]
0x18008a62f  mov     r8, rax; lppProp
0x18008a632  mov     rcx, rbx; lpMapiProp
0x18008a635  mov     edx, 0FFF0102h; ulPropTag
0x18008a63a  call    cs:__imp_HrGetOneProp
0x18008a640  mov     esi, eax
0x18008a642  test    eax, eax
0x18008a644  jns     short loc_18008A651
0x18008a646  mov     r9d, 0D0Fh
0x18008a64c  jmp     loc_18008A701
0x18008a651  mov     rax, [rbp+70h+pv]
0x18008a655  cmp     dword ptr [rax+8], 14h
0x18008a659  jz      short loc_18008A68E
0x18008a65b  mov     ebx, 8000FFFFh
0x18008a660  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a667  mov     ecx, ebx
0x18008a669  mov     r9d, 0D10h
0x18008a66f  xor     edx, edx
0x18008a671  call    Log_HREvent
0x18008a676  mov     rcx, [rbp+70h+pv]; pv
0x18008a67a  test    rcx, rcx
0x18008a67d  jz      loc_18008A722
0x18008a683  call    cs:__imp_MAPIFreeBuffer
0x18008a689  jmp     loc_18008A722
0x18008a68e  mov     rax, [rax+10h]
0x18008a692  mov     r9, rbx
0x18008a695  mov     r8, qword ptr [rbp+70h+var_D0.cb]
0x18008a699  mov     rcx, r13
0x18008a69c  mov     rdx, [rsp+170h+var_100]
0x18008a6a1  mov     [rsp+170h+var_110], edi
0x18008a6a5  movups  xmm0, xmmword ptr [rax]
0x18008a6a8  movups  [rbp+70h+var_60], xmm0
0x18008a6ac  mov     eax, [rax+10h]
0x18008a6af  mov     [rbp+70h+var_50], eax
0x18008a6b2  mov     rax, [rbp+70h+var_B0]
0x18008a6b6  mov     [rsp+170h+var_118], rax
0x18008a6bb  mov     eax, [rsp+170h+var_F4]
0x18008a6bf  mov     [rsp+170h+var_120], eax
0x18008a6c3  mov     rax, [rbp+70h+var_C0]
0x18008a6c7  mov     [rsp+170h+var_128], rax
0x18008a6cc  mov     eax, [rbp+70h+arg_38]
0x18008a6d2  mov     [rsp+170h+var_130], eax
0x18008a6d6  mov     [rsp+170h+var_138], r14
0x18008a6db  mov     [rsp+170h+var_140], r12
0x18008a6e0  mov     dword ptr [rsp+170h+var_148], 3
0x18008a6e8  mov     dword ptr [rsp+170h+var_150], edi
0x18008a6ec  mov     [rsp+170h+var_F8], edi
0x18008a6f0  call    ?SetupResponseMessage@EmailHelper@@YAJPEAVEmailOperationContext@@PEAUIMsgStore@@PEAUIMessage@@2HW4UdmEmailMessageResponseKind@@PEBG4W4UdmEmailMessageBodyKind@@4KPEBUUdmEmailParticipant@@H@Z; EmailHelper::SetupResponseMessage(EmailOperationContext *,IMsgStore *,IMessage *,IMessage *,int,UdmEmailMessageResponseKind,ushort const *,ushort const *,UdmEmailMessageBodyKind,ushort const *,ulong,UdmEmailParticipant const *,int)
0x18008a6f5  mov     esi, eax
0x18008a6f7  test    eax, eax
0x18008a6f9  jns     short loc_18008A73A
0x18008a6fb  mov     r9d, 0D21h
0x18008a701  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a708  mov     edx, edi
0x18008a70a  mov     ecx, esi
0x18008a70c  call    Log_HREvent
0x18008a711  mov     rcx, [rbp+70h+pv]; pv
0x18008a715  test    rcx, rcx
0x18008a718  jz      short loc_18008A720
0x18008a71a  call    cs:__imp_MAPIFreeBuffer
0x18008a720  mov     ebx, esi
0x18008a722  lea     rcx, [rsp+170h+var_100]
0x18008a727  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008a72c  lea     rcx, [rbp+70h+var_D0]
0x18008a730  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008a735  jmp     loc_18008A9E8
0x18008a73a  mov     rcx, [rbp+70h+pv]; pv
0x18008a73e  test    rcx, rcx
0x18008a741  jz      short loc_18008A749
0x18008a743  call    cs:__imp_MAPIFreeBuffer
0x18008a749  lea     rcx, [rsp+170h+var_100]
0x18008a74e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008a753  lea     rcx, [rbp+70h+var_D0]
0x18008a757  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008a75c  jmp     loc_18008A8E6
0x18008a761  mov     [rbp+70h+var_DC], ecx
0x18008a764  lea     r9, [rbp+70h+var_DC]; unsigned int *
0x18008a768  mov     rcx, [rbp+70h+var_F0]; struct ServiceDataSession *
0x18008a76c  mov     r8, rbx; struct _FILETIME
0x18008a76f  call    ?CreateForwardMessage@@YAJPEAVServiceDataSession@@AEBUUdmObjectId@@U_FILETIME@@PEAKPEAPEAE@Z; CreateForwardMessage(ServiceDataSession *,UdmObjectId const &,_FILETIME,ulong *,uchar * *)
0x18008a774  xor     r15d, r15d
0x18008a777  mov     ebx, eax
0x18008a779  test    eax, eax
0x18008a77b  jns     short loc_18008A7A2
0x18008a77d  mov     r9d, 0D2Dh
0x18008a783  mov     edx, edi
0x18008a785  mov     ecx, eax
0x18008a787  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a78e  call    Log_HREvent
0x18008a793  lea     rcx, [rsp+170h+var_100]
0x18008a798  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18008a79d  jmp     loc_18008A9E8
0x18008a7a2  cmp     [rbp+70h+var_DC], 14h
0x18008a7a6  jz      short loc_18008A7B9
0x18008a7a8  mov     ebx, 8000FFFFh
0x18008a7ad  mov     r9d, 0D2Fh
0x18008a7b3  mov     ecx, ebx
0x18008a7b5  xor     edx, edx
0x18008a7b7  jmp     short loc_18008A787
0x18008a7b9  mov     rax, [rsp+170h+var_100]
0x18008a7be  lea     r8, [rbp+70h+lpMapiProp]; struct IUnknown **
0x18008a7c2  xor     r9d, r9d; struct IMsgStore **
0x18008a7c5  mov     qword ptr [rbp+70h+var_D0.cb], 14h
0x18008a7cd  lea     rdx, [rbp+70h+var_D0]; struct _SBinary *
0x18008a7d1  mov     [rbp+70h+var_D0.lpb], rax
0x18008a7d5  movups  xmm0, xmmword ptr [rax]
0x18008a7d8  movups  [rbp+70h+var_60], xmm0
0x18008a7dc  mov     ecx, [rax+10h]
0x18008a7df  mov     [rbp+70h+var_50], ecx
0x18008a7e2  mov     rcx, r13; this
0x18008a7e5  mov     [rsp+170h+var_F8], edi
0x18008a7e9  call    ?OpenItemByMapiId@EmailOperationContext@@QEAAJAEBU_SBinary@@PEAPEAUIUnknown@@PEAPEAUIMsgStore@@@Z; EmailOperationContext::OpenItemByMapiId(_SBinary const &,IUnknown * *,IMsgStore * *)
0x18008a7ee  mov     ebx, eax
0x18008a7f0  test    eax, eax
0x18008a7f2  jns     short loc_18008A7FC
0x18008a7f4  mov     r9d, 0D37h
0x18008a7fa  jmp     short loc_18008A783
0x18008a7fc  mov     rbx, [rbp+70h+lpMapiProp]
0x18008a800  test    r12, r12
0x18008a803  jz      short loc_18008A84F
0x18008a805  lea     rdx, [rbp+70h+Prop]; lpProp
0x18008a809  mov     qword ptr [rbp+70h+Prop.ulPropTag], 37001Fh
0x18008a811  mov     rcx, rbx; lpMapiProp
0x18008a814  mov     qword ptr [rbp+70h+Prop.Value+8], r15
0x18008a818  mov     qword ptr [rbp+70h+Prop.Value], r12
0x18008a81c  call    cs:__imp_HrSetOneProp
0x18008a822  mov     esi, eax
0x18008a824  test    eax, eax
0x18008a826  jns     short loc_18008A84F
0x18008a828  mov     r9d, 0D3Eh
0x18008a82e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a835  mov     edx, edi
0x18008a837  mov     ecx, eax
0x18008a839  call    Log_HREvent
0x18008a83e  lea     rcx, [rsp+170h+var_100]
0x18008a843  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18008a848  mov     ebx, esi
0x18008a84a  jmp     loc_18008A9E8
0x18008a84f  mov     [rbp+70h+var_F0], r15
0x18008a853  mov     r8, r15
0x18008a856  test    r14, r14
0x18008a859  jz      short loc_18008A8A0
0x18008a85b  cmp     [r14], r15w
0x18008a85f  jz      short loc_18008A8A0
0x18008a861  lea     rcx, [rbp+70h+var_F0]
0x18008a865  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18008a86a  mov     rdx, rax; unsigned __int16 **
0x18008a86d  mov     rcx, r14; unsigned __int16 *
0x18008a870  call    ?ConvertPlainTextStringToHtmlString@@YAJPEBGPEAPEAG@Z; ConvertPlainTextStringToHtmlString(ushort const *,ushort * *)
0x18008a875  mov     esi, eax
0x18008a877  test    eax, eax
0x18008a879  jns     short loc_18008A89C
0x18008a87b  mov     r9d, 0D44h
0x18008a881  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a888  mov     edx, edi
0x18008a88a  mov     ecx, esi
0x18008a88c  call    Log_HREvent
0x18008a891  lea     rcx, [rbp+70h+var_F0]
0x18008a895  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x18008a89a  jmp     short loc_18008A83E
0x18008a89c  mov     r8, [rbp+70h+var_F0]
0x18008a8a0  mov     rax, [rbp+70h+var_C0]
0x18008a8a4  mov     rdx, r14
0x18008a8a7  mov     r9d, [rbp+70h+arg_38]
0x18008a8ae  mov     rcx, rbx
0x18008a8b1  mov     [rsp+170h+var_140], r15
0x18008a8b6  mov     [rsp+170h+var_148], r15
0x18008a8bb  mov     [rsp+170h+var_150], rax
0x18008a8c0  call    ?SetResponseMessageBodies@EmailHelper@@YAJPEAUIMessage@@PEBG1W4UdmEmailMessageBodyKind@@111@Z; EmailHelper::SetResponseMessageBodies(IMessage *,ushort const *,ushort const *,UdmEmailMessageBodyKind,ushort const *,ushort const *,ushort const *)
0x18008a8c5  mov     esi, eax
0x18008a8c7  test    eax, eax
0x18008a8c9  jns     short loc_18008A8D3
0x18008a8cb  mov     r9d, 0D4Eh
0x18008a8d1  jmp     short loc_18008A881
0x18008a8d3  lea     rcx, [rbp+70h+var_F0]
0x18008a8d7  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x18008a8dc  lea     rcx, [rsp+170h+var_100]
0x18008a8e1  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18008a8e6  mov     eax, [rsp+170h+var_F4]
0x18008a8ea  lea     r8, [rbp+70h+var_C0]
0x18008a8ee  mov     [rbp+70h+var_C0], rax
0x18008a8f2  mov     rdx, rbx
0x18008a8f5  mov     rax, [rbp+70h+var_B0]
0x18008a8f9  mov     [rbp+70h+var_B8], rax
0x18008a8fd  call    ?UpdateRecipients@EmailOperationContext@@QEAAJPEAUIMessage@@AEBV?$Vector@$$CBUUdmEmailParticipant@@@Udm@@@Z; EmailOperationContext::UpdateRecipients(IMessage *,Udm::Vector<UdmEmailParticipant const> const &)
0x18008a902  mov     esi, eax
0x18008a904  test    eax, eax
0x18008a906  jns     short loc_18008A923
0x18008a908  mov     r9d, 0D51h
0x18008a90e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008a915  mov     edx, edi
0x18008a917  mov     ecx, esi
0x18008a919  call    Log_HREvent
0x18008a91e  jmp     loc_18008A848
0x18008a923  lea     rcx, [rbp+70h+var_C0]
0x18008a927  mov     [rbp+70h+var_C0], r15
  ... truncated ...
```
