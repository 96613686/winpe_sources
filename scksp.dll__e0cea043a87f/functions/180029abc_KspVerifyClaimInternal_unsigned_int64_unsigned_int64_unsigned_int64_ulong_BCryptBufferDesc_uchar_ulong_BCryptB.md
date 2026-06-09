# KspVerifyClaimInternal(unsigned __int64,unsigned __int64,unsigned __int64,ulong,_BCryptBufferDesc *,uchar *,ulong,_BCryptBufferDesc *,ulong)

- ea: `0x180029abc`
- end: `0x18002a4ba`
- name: `?KspVerifyClaimInternal@@YAJ_K00KPEAU_BCryptBufferDesc@@PEAEK1K@Z`
- size: `2558`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64, unsigned int, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, struct _BCryptBufferDesc *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18002b090`

## callees

- `0x180001178`
- `0x1800011c4`
- `0x180001238`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x1800135dc`
- `0x180013734`
- `0x180013aac`
- `0x180016624`
- `0x180029abc`
- `0x18002b140`
- `0x18003af5c`
- `0x18003c240`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029b55`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029b62`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029dfe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a33c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a34b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029b55`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029b62`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180029dfe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a33c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a34b`
- `ncrypt!NCryptFreeObject` at `0x180029d72`
- `ncrypt!NCryptFreeObject` at `0x180029d81`
- `ncrypt!NCryptFreeObject` at `0x180029dab`
- `ncrypt!NCryptFreeObject` at `0x180029d72`
- `ncrypt!NCryptFreeObject` at `0x180029d81`
- `ncrypt!NCryptFreeObject` at `0x180029dab`
- `ncrypt!NCryptImportKey` at `0x18002a26b`
- `ncrypt!NCryptImportKey` at `0x18002a2e1`
- `ncrypt!NCryptImportKey` at `0x18002a26b`
- `ncrypt!NCryptImportKey` at `0x18002a2e1`
- `ncrypt!NCryptVerifyClaim` at `0x18002a3a3`
- `ncrypt!NCryptVerifyClaim` at `0x18002a3a3`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a1f5`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a1f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KspVerifyClaimInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        struct _BCryptBufferDesc *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        struct _BCryptBufferDesc *a8,
        unsigned int a9)
{
  unsigned int v9; // edi
  BYTE *v13; // rsi
  __int64 v14; // rcx
  unsigned int Handle; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  BYTE *pbData; // r12
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // r14
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // rcx
  DWORD dwFlags; // edi
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-99h] BYREF
  BYTE *v44; // [rsp+50h] [rbp-91h]
  size_t size; // [rsp+58h] [rbp-89h] BYREF
  NCRYPT_HANDLE phProvider; // [rsp+60h] [rbp-81h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+68h] [rbp-79h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+70h] [rbp-71h] BYREF
  __int64 v49; // [rsp+78h] [rbp-69h] BYREF
  __int64 v50; // [rsp+80h] [rbp-61h] BYREF
  _QWORD v51[2]; // [rsp+88h] [rbp-59h] BYREF
  struct _BCryptBufferDesc *v52; // [rsp+98h] [rbp-49h]
  GUID v53; // [rsp+A0h] [rbp-41h] BYREF
  GUID v54; // [rsp+B0h] [rbp-31h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-21h] BYREF

  v9 = a4;
  v42 = a4;
  v52 = a8;
  v49 = 0;
  v51[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v51[1] = 0;
  phProvider = 0;
  phKey = 0;
  hObject = 0;
  *(_QWORD *)&v53.Data1 = 0;
  size = 0;
  v50 = 0;
  v13 = 0;
  v44 = 0;
  ActivityId = 0;
  v54 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v54);
  if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v14,
      &word_18004554E,
      &v54,
      &ActivityId);
  if ( !a3 || !a2 || v9 != 2 )
  {
    WppTraceIndent(v14, 2);
    Handle = -2146893785;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v17 = 491;
    goto LABEL_13;
  }
  if ( a5 )
  {
    if ( a5->ulVersion )
    {
      WppTraceIndent(v14, 2);
      Handle = -2146893785;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v17 = 492;
LABEL_13:
      WPP_SF_d(v16[2], v17, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
LABEL_14:
      pbData = 0;
      goto LABEL_38;
    }
    if ( a5->cBuffers > 1 )
    {
      WppTraceIndent(v14, 2);
      Handle = -2146893785;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v17 = 493;
      goto LABEL_13;
    }
    if ( a5->cBuffers == 1 && a5->pBuffers->BufferType != 49 )
    {
      WppTraceIndent(v14, 2);
      Handle = -2146893785;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      v17 = 494;
      goto LABEL_13;
    }
  }
  Handle = HtGetHandle(a1, 3, &v49);
  if ( Handle )
  {
    WppTraceIndent(v19, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        495,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle);
    }
    goto LABEL_14;
  }
  v20 = v49;
  Handle = KspEnterCriticalSection(v49 + 16);
  if ( Handle )
  {
    WppTraceIndent(v21, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        496,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle);
    }
    goto LABEL_36;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v51, v20 + 16);
  Handle = HtGetHandle(a2, 2, &v50);
  if ( Handle )
  {
    WppTraceIndent(v24, 2);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    v26 = 497;
LABEL_57:
    WPP_SF_sd(
      v25[2],
      v26,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
LABEL_58:
    v13 = 0;
LABEL_36:
    pbData = 0;
    goto LABEL_37;
  }
  Handle = HtGetHandle(a3, 2, &v53);
  if ( Handle )
  {
    WppTraceIndent(v27, 2);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    v26 = 498;
    goto LABEL_57;
  }
  v28 = v50;
  if ( !*(_DWORD *)(v50 + 1048) || (v29 = *(_QWORD *)&v53.Data1, !*(_DWORD *)(*(_QWORD *)&v53.Data1 + 1048LL)) )
  {
    WppTraceIndent(v27, 2);
    Handle = -2146893813;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 499, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073483LL);
    }
    goto LABEL_58;
  }
  Handle = KsppExportKey(v20, *(_QWORD *)&v53.Data1, L"RSAPUBLICBLOB", 0, 0, 0, &size, 0);
  if ( Handle )
  {
    WppTraceIndent(v30, 2);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    v26 = 500;
    goto LABEL_57;
  }
  pbData = (BYTE *)MIDL_user_allocate((unsigned int)size);
  if ( !pbData )
  {
    Handle = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        501,
        &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        WPP_pszIndent);
    }
    v13 = v44;
    goto LABEL_37;
  }
  Handle = KsppExportKey(v20, v29, L"RSAPUBLICBLOB", 0, pbData, size, &size, 0);
  v13 = 0;
  if ( Handle )
  {
    WppTraceIndent(v31, 2);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v33 = 502;
  }
  else
  {
    Handle = KsppExportKey(v20, v28, L"RSAPUBLICBLOB", 0, 0, 0, (char *)&size + 4, 0);
    if ( Handle )
    {
      WppTraceIndent(v34, 2);
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_37;
      }
      v33 = 503;
    }
    else
    {
      v13 = (BYTE *)MIDL_user_allocate(HIDWORD(size));
      if ( !v13 )
      {
        Handle = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            504,
            &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
            WPP_pszIndent);
        }
        goto LABEL_37;
      }
      Handle = KsppExportKey(v20, v28, L"RSAPUBLICBLOB", 0, v13, HIDWORD(size), (char *)&size + 4, 0);
      if ( Handle )
      {
        WppTraceIndent(v35, 2);
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_37;
        }
        v33 = 505;
      }
      else
      {
        dwFlags = a9 | 0x1000;
        Handle = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", a9 | 0x1000);
        if ( Handle )
        {
          WppTraceIndent(v37, 2);
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_37;
          }
          v33 = 506;
        }
        else
        {
          Handle = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &phKey, pbData, size, dwFlags);
          if ( Handle )
          {
            WppTraceIndent(v38, 2);
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_37;
            }
            v33 = 507;
          }
          else
          {
            Handle = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &hObject, v13, HIDWORD(size), dwFlags);
            if ( Handle )
            {
              WppTraceIndent(v39, 2);
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_37;
              }
              v33 = 508;
            }
            else
            {
              v53 = 0;
              EventActivityIdControl(3u, &v53);
              EventActivityIdControl(2u, &v53);
              if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v40,
                  byte_180045579,
                  &v53,
                  &v54);
              Handle = NCryptVerifyClaim(hObject, phKey, 2, a5, a6, a7, v52, dwFlags);
              if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v41,
                  qword_180045530,
                  &v53,
                  &v54);
              if ( !Handle )
                goto LABEL_37;
              WppTraceIndent(v41, 2);
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_37;
              }
              v33 = 509;
            }
          }
        }
      }
    }
  }
  WPP_SF_sd(v32[2], v33, (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, (_DWORD)WPP_pszIndent, Handle);
LABEL_37:
  v9 = v42;
LABEL_38:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( v13 )
    CspFreeH(v13);
  if ( pbData )
    CspFreeH(pbData);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( (unsigned int)dword_18004B100 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v42 = Handle;
    v43 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&dword_1800454F4,
      (unsigned int)&v54,
      (unsigned int)&ActivityId,
      (__int64)&v43,
      (__int64)&v42);
  }
  EventActivityIdControl(2u, &ActivityId);
  v51[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v51);
  return Handle;
}

```

## disassembly

```asm
0x180029abc  push    rbp
0x180029abe  push    rbx
0x180029abf  push    rsi
0x180029ac0  push    rdi
0x180029ac1  push    r12
0x180029ac3  push    r13
0x180029ac5  push    r14
0x180029ac7  push    r15
0x180029ac9  lea     rbp, [rsp-7]
0x180029ace  sub     rsp, 0E8h
0x180029ad5  mov     rax, cs:__security_cookie
0x180029adc  xor     rax, rsp
0x180029adf  mov     [rbp+3Fh+var_50], rax
0x180029ae3  mov     edi, r9d
0x180029ae6  mov     [rsp+120h+var_E0], r9d
0x180029aeb  mov     r14, r8
0x180029aee  mov     r12, rdx
0x180029af1  mov     rbx, rcx
0x180029af4  mov     r15, [rbp+3Fh+arg_20]
0x180029af8  mov     r13, [rbp+3Fh+arg_28]
0x180029afc  mov     rax, [rbp+3Fh+arg_38]
0x180029b03  mov     [rbp+3Fh+var_88], rax
0x180029b07  xor     eax, eax
0x180029b09  mov     [rbp+3Fh+var_A8], rax
0x180029b0d  lea     rcx, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180029b14  mov     [rbp+3Fh+var_98], rcx
0x180029b18  mov     [rbp+3Fh+var_90], rax
0x180029b1c  mov     [rsp+120h+phProvider], rax
0x180029b21  mov     [rbp+3Fh+var_B0], rax
0x180029b25  mov     [rbp+3Fh+hObject], rax
0x180029b29  mov     qword ptr [rbp+3Fh+var_80.Data1], rax
0x180029b2d  mov     dword ptr [rsp+120h+size], eax
0x180029b31  mov     [rbp+3Fh+var_A0], rax
0x180029b35  mov     esi, eax
0x180029b37  mov     [rsp+120h+var_D0], rax
0x180029b3c  mov     dword ptr [rsp+120h+size+4], eax
0x180029b40  xorps   xmm0, xmm0
0x180029b43  movups  xmmword ptr [rbp+3Fh+ActivityId.Data1], xmm0
0x180029b47  xorps   xmm1, xmm1
0x180029b4a  movups  xmmword ptr [rbp+3Fh+var_70.Data1], xmm1
0x180029b4e  lea     rdx, [rbp+3Fh+ActivityId]; ActivityId
0x180029b52  lea     ecx, [rax+5]; ControlCode
0x180029b55  call    cs:__imp_EventActivityIdControl
0x180029b5b  lea     rdx, [rbp+3Fh+var_70]; ActivityId
0x180029b5f  lea     ecx, [rsi+1]; ControlCode
0x180029b62  call    cs:__imp_EventActivityIdControl
0x180029b68  mov     eax, cs:dword_18004B100
0x180029b6e  cmp     eax, 5
0x180029b71  jbe     short loc_180029B90
0x180029b73  call    _tlgKeywordOn
0x180029b78  test    al, al
0x180029b7a  jz      short loc_180029B90
0x180029b7c  lea     r9, [rbp+3Fh+ActivityId]
0x180029b80  lea     r8, [rbp+3Fh+var_70]
0x180029b84  lea     rdx, word_18004554E
0x180029b8b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180029b90  test    r14, r14
0x180029b93  jz      loc_18002A471
0x180029b99  test    r12, r12
0x180029b9c  jz      loc_18002A471
0x180029ba2  cmp     edi, 2
0x180029ba5  jnz     loc_18002A471
0x180029bab  test    r15, r15
0x180029bae  jz      loc_180029C91
0x180029bb4  cmp     [r15], esi
0x180029bb7  jz      short loc_180029C05
0x180029bb9  mov     edx, edi
0x180029bbb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029bc0  mov     r9d, 80090027h
0x180029bc6  mov     ebx, r9d
0x180029bc9  lea     rax, WPP_GLOBAL_Control
0x180029bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bd7  cmp     rcx, rax
0x180029bda  jz      short loc_180029BFD
0x180029bdc  test    byte ptr [rcx+1Ch], 1
0x180029be0  jz      short loc_180029BFD
0x180029be2  cmp     [rcx+19h], dil
0x180029be6  jb      short loc_180029BFD
0x180029be8  mov     edx, 1ECh
0x180029bed  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180029bf4  mov     rcx, [rcx+10h]
0x180029bf8  call    WPP_SF_d
0x180029bfd  mov     r12, rsi
0x180029c00  jmp     loc_180029D69
0x180029c05  cmp     dword ptr [r15+4], 1
0x180029c0a  jbe     short loc_180029C45
0x180029c0c  mov     edx, 2
0x180029c11  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029c16  mov     r9d, 80090027h
0x180029c1c  mov     ebx, r9d
0x180029c1f  lea     rax, WPP_GLOBAL_Control
0x180029c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c2d  cmp     rcx, rax
0x180029c30  jz      short loc_180029BFD
0x180029c32  test    byte ptr [rcx+1Ch], 1
0x180029c36  jz      short loc_180029BFD
0x180029c38  cmp     byte ptr [rcx+19h], 2
0x180029c3c  jb      short loc_180029BFD
0x180029c3e  mov     edx, 1EDh
0x180029c43  jmp     short loc_180029BED
0x180029c45  jnz     short loc_180029C91
0x180029c47  mov     rax, [r15+8]
0x180029c4b  cmp     dword ptr [rax+4], 31h ; '1'
0x180029c4f  jz      short loc_180029C91
0x180029c51  mov     edx, 2
0x180029c56  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029c5b  mov     r9d, 80090027h
0x180029c61  mov     ebx, r9d
0x180029c64  lea     rax, WPP_GLOBAL_Control
0x180029c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c72  cmp     rcx, rax
0x180029c75  jz      short loc_180029BFD
0x180029c77  test    byte ptr [rcx+1Ch], 1
0x180029c7b  jz      short loc_180029BFD
0x180029c7d  cmp     byte ptr [rcx+19h], 2
0x180029c81  jb      loc_180029BFD
0x180029c87  mov     edx, 1EEh
0x180029c8c  jmp     loc_180029BED
0x180029c91  lea     r8, [rbp+3Fh+var_A8]
0x180029c95  mov     edx, 3
0x180029c9a  mov     rcx, rbx
0x180029c9d  call    HtGetHandle
0x180029ca2  mov     ebx, eax
0x180029ca4  test    eax, eax
0x180029ca6  jz      short loc_180029D02
0x180029ca8  mov     edx, 2
0x180029cad  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029cb2  lea     rax, WPP_GLOBAL_Control
0x180029cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cc0  cmp     rcx, rax
0x180029cc3  jz      loc_180029BFD
0x180029cc9  test    byte ptr [rcx+1Ch], 1
0x180029ccd  jz      loc_180029BFD
0x180029cd3  cmp     byte ptr [rcx+19h], 2
0x180029cd7  jb      loc_180029BFD
0x180029cdd  mov     edx, 1EFh
0x180029ce2  mov     dword ptr [rsp+120h+phKey], ebx
0x180029ce6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180029ced  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180029cf4  mov     rcx, [rcx+10h]
0x180029cf8  call    WPP_SF_sd
0x180029cfd  jmp     loc_180029BFD
0x180029d02  mov     rdi, [rbp+3Fh+var_A8]
0x180029d06  lea     rcx, [rdi+10h]
0x180029d0a  call    KspEnterCriticalSection
0x180029d0f  mov     ebx, eax
0x180029d11  test    eax, eax
0x180029d13  jz      loc_180029E3B
0x180029d19  mov     edx, 2
0x180029d1e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029d23  lea     rax, WPP_GLOBAL_Control
0x180029d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d31  cmp     rcx, rax
0x180029d34  jz      short loc_180029D62
0x180029d36  test    byte ptr [rcx+1Ch], 1
0x180029d3a  jz      short loc_180029D62
0x180029d3c  cmp     byte ptr [rcx+19h], 2
0x180029d40  jb      short loc_180029D62
0x180029d42  mov     edx, 1F0h
0x180029d47  mov     dword ptr [rsp+120h+phKey], ebx
0x180029d4b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180029d52  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180029d59  mov     rcx, [rcx+10h]
0x180029d5d  call    WPP_SF_sd
0x180029d62  mov     r12, rsi
0x180029d65  mov     edi, [rsp+120h+var_E0]
0x180029d69  mov     rcx, [rbp+3Fh+hObject]; hObject
0x180029d6d  test    rcx, rcx
0x180029d70  jz      short loc_180029D78
0x180029d72  call    cs:__imp_NCryptFreeObject
0x180029d78  mov     rcx, [rbp+3Fh+var_B0]; hObject
0x180029d7c  test    rcx, rcx
0x180029d7f  jz      short loc_180029D87
0x180029d81  call    cs:__imp_NCryptFreeObject
0x180029d87  test    rsi, rsi
0x180029d8a  jz      short loc_180029D94
0x180029d8c  mov     rcx, rsi
0x180029d8f  call    CspFreeH
0x180029d94  test    r12, r12
0x180029d97  jz      short loc_180029DA1
0x180029d99  mov     rcx, r12
0x180029d9c  call    CspFreeH
0x180029da1  mov     rcx, [rsp+120h+phProvider]; hObject
0x180029da6  test    rcx, rcx
0x180029da9  jz      short loc_180029DB1
0x180029dab  call    cs:__imp_NCryptFreeObject
0x180029db1  mov     eax, cs:dword_18004B100
0x180029db7  cmp     eax, 5
0x180029dba  jbe     short loc_180029DF5
0x180029dbc  call    _tlgKeywordOn
0x180029dc1  test    al, al
0x180029dc3  jz      short loc_180029DF5
0x180029dc5  mov     [rsp+120h+var_E0], ebx
0x180029dc9  mov     [rsp+120h+var_D8], edi
0x180029dcd  lea     rax, [rsp+120h+var_E0]
0x180029dd2  mov     [rsp+120h+pbData], rax
0x180029dd7  lea     rax, [rsp+120h+var_D8]
0x180029ddc  mov     [rsp+120h+phKey], rax
0x180029de1  lea     r9, [rbp+3Fh+ActivityId]
0x180029de5  lea     r8, [rbp+3Fh+var_70]
0x180029de9  lea     rdx, dword_1800454F4
0x180029df0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029df5  lea     rdx, [rbp+3Fh+ActivityId]; ActivityId
0x180029df9  mov     ecx, 2; ControlCode
0x180029dfe  call    cs:__imp_EventActivityIdControl
0x180029e04  nop
0x180029e05  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180029e0c  mov     [rbp+3Fh+var_98], rax
0x180029e10  lea     rcx, [rbp+3Fh+var_98]
0x180029e14  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180029e19  mov     eax, ebx
0x180029e1b  mov     rcx, [rbp+3Fh+var_50]
0x180029e1f  xor     rcx, rsp; StackCookie
0x180029e22  call    __security_check_cookie
0x180029e27  add     rsp, 0E8h
0x180029e2e  pop     r15
0x180029e30  pop     r14
0x180029e32  pop     r13
0x180029e34  pop     r12
0x180029e36  pop     rdi
0x180029e37  pop     rsi
0x180029e38  pop     rbx
0x180029e39  pop     rbp
0x180029e3a  retn
0x180029e3b  lea     rdx, [rdi+10h]
0x180029e3f  lea     rcx, [rbp+3Fh+var_98]
0x180029e43  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180029e48  lea     r8, [rbp+3Fh+var_A0]
0x180029e4c  mov     esi, 2
0x180029e51  mov     edx, esi
0x180029e53  mov     rcx, r12
0x180029e56  call    HtGetHandle
0x180029e5b  mov     ebx, eax
0x180029e5d  xor     r12d, r12d
0x180029e60  mov     edx, esi
0x180029e62  test    eax, eax
0x180029e64  jz      short loc_180029EB2
0x180029e66  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029e6b  lea     rax, WPP_GLOBAL_Control
0x180029e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e79  cmp     rcx, rax
0x180029e7c  jz      short loc_180029EAA
0x180029e7e  test    byte ptr [rcx+1Ch], 1
0x180029e82  jz      short loc_180029EAA
0x180029e84  cmp     [rcx+19h], sil
0x180029e88  jb      short loc_180029EAA
0x180029e8a  mov     edx, 1F1h
0x180029e8f  mov     dword ptr [rsp+120h+phKey], ebx
0x180029e93  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180029e9a  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180029ea1  mov     rcx, [rcx+10h]
0x180029ea5  call    WPP_SF_sd
0x180029eaa  mov     rsi, r12
0x180029ead  jmp     loc_180029D62
0x180029eb2  lea     r8, [rbp+3Fh+var_80]
0x180029eb6  mov     rcx, r14
0x180029eb9  call    HtGetHandle
0x180029ebe  mov     ebx, eax
0x180029ec0  test    eax, eax
0x180029ec2  jz      short loc_180029EF1
0x180029ec4  mov     edx, esi
0x180029ec6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029ecb  lea     rax, WPP_GLOBAL_Control
0x180029ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ed9  cmp     rcx, rax
0x180029edc  jz      short loc_180029EAA
0x180029ede  test    byte ptr [rcx+1Ch], 1
0x180029ee2  jz      short loc_180029EAA
0x180029ee4  cmp     [rcx+19h], sil
0x180029ee8  jb      short loc_180029EAA
0x180029eea  mov     edx, 1F2h
0x180029eef  jmp     short loc_180029E8F
0x180029ef1  mov     r14, [rbp+3Fh+var_A0]
0x180029ef5  cmp     [r14+418h], r12d
0x180029efc  jz      loc_18002A41A
0x180029f02  mov     rsi, qword ptr [rbp+3Fh+var_80.Data1]
0x180029f06  cmp     [rsi+418h], r12d
0x180029f0d  jz      loc_18002A41A
0x180029f13  mov     [rsp+120h+dwFlags], r12d
0x180029f18  lea     rax, [rsp+120h+size]
0x180029f1d  mov     qword ptr [rsp+120h+cbData], rax
0x180029f22  mov     dword ptr [rsp+120h+pbData], r12d
0x180029f27  mov     [rsp+120h+phKey], r12
0x180029f2c  xor     r9d, r9d
0x180029f2f  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180029f36  mov     rdx, rsi
0x180029f39  mov     rcx, rdi
0x180029f3c  call    KsppExportKey
0x180029f41  mov     ebx, eax
0x180029f43  test    eax, eax
0x180029f45  jz      short loc_180029F86
0x180029f47  mov     edx, 2
0x180029f4c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029f51  lea     rax, WPP_GLOBAL_Control
0x180029f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f5f  cmp     rcx, rax
0x180029f62  jz      loc_180029EAA
0x180029f68  test    byte ptr [rcx+1Ch], 1
0x180029f6c  jz      loc_180029EAA
0x180029f72  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
