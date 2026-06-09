# RdpWinRadcHttpRequest::InitializeInstance(void *,ushort const *,ushort const *,_RDPX_RADC_HTTP_METHOD,bool,ushort const *,ushort const *,RdpXInterfaceRadcHttpRequestEventHandler *,RdpXInterfaceUInt8Buffer *,uint,_RDPX_RADC_HTTP_REQUEST_BODY_CONTENT_TYPE,RdpXInterfaceTaskScheduler *,_XGUID,ushort const *,RdpXInterfaceCertificateHandler *)

- ea: `0x180090580`
- end: `0x180090b85`
- name: `?InitializeInstance@RdpWinRadcHttpRequest@@QEAAJPEAXPEBG1W4_RDPX_RADC_HTTP_METHOD@@_N11PEAURdpXInterfaceRadcHttpRequestEventHandler@@PEAURdpXInterfaceUInt8Buffer@@IW4_RDPX_RADC_HTTP_REQUEST_BODY_CONTENT_TYPE@@PEAURdpXInterfaceTaskScheduler@@U_XGUID@@1PEAURdpXInterfaceCertificateHandler@@@Z`
- size: `1541`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008e740`

## callees

- `0x18000ec94`
- `0x18000ece0`
- `0x180017fcc`
- `0x18001a008`
- `0x180034f90`
- `0x180062a08`
- `0x18008e5f8`
- `0x180090580`
- `0x1800921dc`
- `0x180093fd4`
- `0x180094348`
- `0x18009a520`
- `0x18009a5e0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090afd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090b0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090b0f`
- `WINHTTP!WinHttpCrackUrl` at `0x1800907d4`
- `WINHTTP!WinHttpCrackUrl` at `0x1800907d4`

## string_xrefs

- `0x18009071d`: `RadcValidateAndCreateActualUrl failed`
- `0x1800908f7`: `m_bstrClaimsToken.Append failed`
- `0x18009094a`: `m_bstrClaimsToken.Append(empty string) failed`
- `0x180090b4a`: `CreateEvent() failed.`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::InitializeInstance(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        __int64 a9,
        void (__fastcall ***a10)(_QWORD),
        int a11,
        int a12,
        __int64 a13,
        _OWORD *a14,
        unsigned __int16 *a15)
{
  __int64 v16; // rcx
  PVOID *v18; // rax
  __int64 v19; // rbx
  unsigned int ActivityIdPrefix; // eax
  unsigned int v21; // eax
  __int64 v22; // rdx
  signed int ActualUrl; // ebx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // edx
  const char *v27; // rcx
  const WCHAR **v28; // r14
  __int64 v29; // rcx
  const WCHAR *v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rcx
  ATL::CComBSTR *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rdi
  __int64 v42; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v45; // rcx
  __int64 v47; // [rsp+28h] [rbp-10E0h]
  __int64 v48; // [rsp+58h] [rbp-10B0h]
  unsigned __int16 v50[2088]; // [rsp+70h] [rbp-1098h] BYREF

  v16 = a13;
  v48 = (__int64)a4;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v19 = *(_QWORD *)(a1 + 16);
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(a13);
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      ActivityIdPrefix,
      v19);
    v18 = (PVOID *)WPP_GLOBAL_Control;
    v16 = a13;
    a4 = (const unsigned __int16 *)v48;
  }
  if ( !a3 )
  {
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 8) == 0 || *((_BYTE *)v18 + 25) < 2u )
      return (unsigned int)-2147024809;
    v21 = RdpX_GetActivityIdPrefix(v16);
    v22 = 27;
LABEL_10:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      v21,
      -2147024809);
    return (unsigned int)-2147024809;
  }
  if ( !a9 )
  {
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 8) == 0 || *((_BYTE *)v18 + 25) < 2u )
      return (unsigned int)-2147024809;
    v21 = RdpX_GetActivityIdPrefix(v16);
    v22 = 28;
    goto LABEL_10;
  }
  if ( !v16 )
  {
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 8) == 0 || *((_BYTE *)v18 + 25) < 2u )
      return (unsigned int)-2147024809;
    v21 = RdpX_GetActivityIdPrefix(0);
    v22 = 29;
    goto LABEL_10;
  }
  ActualUrl = RadcValidateAndCreateActualUrl(a3, a4, v50, (unsigned int)a4);
  if ( ActualUrl >= 0 )
  {
    v28 = (const WCHAR **)(a1 + 56);
    ActualUrl = ATL::CComBSTR::Append((ATL::CComBSTR *)(a1 + 56), v50);
    if ( ActualUrl >= 0 )
    {
      v30 = *v28;
      *(_DWORD *)(a1 + 64) = 104;
      *(_DWORD *)(a1 + 80) = 1;
      *(_DWORD *)(a1 + 96) = 1;
      *(_DWORD *)(a1 + 112) = 1;
      *(_DWORD *)(a1 + 128) = 1;
      *(_DWORD *)(a1 + 144) = 1;
      *(_DWORD *)(a1 + 160) = 1;
      if ( !WinHttpCrackUrl(v30, 0, 0, (LPURL_COMPONENTS)(a1 + 64)) )
      {
        ActualUrl = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v32 = RdpX_GetActivityIdPrefix(v31);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v32,
            ActualUrl);
        }
        if ( ActualUrl > 0 )
          ActualUrl = (unsigned __int16)ActualUrl | 0x80070000;
        if ( ActualUrl >= 0 )
          return (unsigned int)-2147467259;
        return (unsigned int)ActualUrl;
      }
      if ( !a7 || (ActualUrl = ATL::CComBSTR::Append((ATL::CComBSTR *)(a1 + 168), a7), ActualUrl >= 0) )
      {
        v34 = (ATL::CComBSTR *)(a1 + 176);
        if ( a8 )
        {
          ActualUrl = ATL::CComBSTR::Append(v34, a8);
          if ( ActualUrl < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpX_GetActivityIdPrefix(v35);
              v26 = 34;
              v27 = "m_bstrClaimsToken.Append failed";
              goto LABEL_27;
            }
            return (unsigned int)ActualUrl;
          }
        }
        else
        {
          ActualUrl = ATL::CComBSTR::Append(v34, &LocaleName);
          if ( ActualUrl < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpX_GetActivityIdPrefix(v36);
              v26 = 35;
              v27 = "m_bstrClaimsToken.Append(empty string) failed";
              goto LABEL_27;
            }
            return (unsigned int)ActualUrl;
          }
        }
        if ( a15 && (ActualUrl = ATL::CComBSTR::Append((ATL::CComBSTR *)(a1 + 256), a15), ActualUrl < 0) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = RdpX_GetActivityIdPrefix(v37);
            v26 = 36;
            v27 = "m_bstrPreviousETag.Append failed";
            goto LABEL_27;
          }
        }
        else
        {
          ActualUrl = RdpWinRadcHttpRequest::ProcessHttpMethod(a1, a5);
          if ( ActualUrl >= 0 )
          {
            *(_QWORD *)(a1 + 200) = a9;
            *(_QWORD *)(a1 + 24) = a2;
            *(_BYTE *)(a1 + 184) = 1;
            if ( a10 != *(void (__fastcall ****)(_QWORD))(a1 + 208) )
            {
              RdpXSPtr<RdpXPlatKeyValuePair<unsigned __int64,RdpWinDiagnosticsHttpManager::HostMessage *>>::SafeRelease(a1 + 208);
              *(_QWORD *)(a1 + 208) = a10;
              if ( a10 )
                (**a10)(a10);
            }
            *(_DWORD *)(a1 + 216) = a11;
            *(_DWORD *)(a1 + 220) = a12;
            RdpXSPtr<RdpXInterfaceTaskScheduler>::operator=(a1 + 232, a13);
            *(_OWORD *)(a1 + 240) = *a14;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v40 = (__int64)*v28;
              v41 = *(_QWORD *)(a1 + 48);
              v42 = *(_QWORD *)(a1 + 16);
              RdpX_GetActivityIdPrefix(v39);
              WPP_SF_DISSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, v41, (__int64)a3, v48, v40);
            }
            EventW = CreateEventW(0, 1, 0, 0);
            *(_QWORD *)(a1 + 224) = EventW;
            if ( EventW )
              return 0;
            LastError = GetLastError();
            ActualUrl = LastError;
            if ( LastError > 0 )
              ActualUrl = (unsigned __int16)LastError | 0x80070000;
            if ( ActualUrl >= 0 )
              return 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpX_GetActivityIdPrefix(v45);
              v26 = 39;
              v27 = "CreateEvent() failed.";
              goto LABEL_27;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = RdpX_GetActivityIdPrefix(v38);
            v26 = 37;
            v27 = "ProcessHttpMethod failed";
            goto LABEL_27;
          }
        }
        return (unsigned int)ActualUrl;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpX_GetActivityIdPrefix(v33);
        v26 = 33;
        v27 = "m_bstrAuthCookie.Append failed";
        goto LABEL_27;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpX_GetActivityIdPrefix(v29);
      v26 = 31;
      v27 = "m_bstrUrl.Append failed";
      goto LABEL_27;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = RdpX_GetActivityIdPrefix(v24);
    v26 = 30;
    v27 = "RadcValidateAndCreateActualUrl failed";
LABEL_27:
    LODWORD(v47) = ActualUrl;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      v25,
      (__int64)v27,
      v47);
  }
  return (unsigned int)ActualUrl;
}

```

## disassembly

```asm
0x180090580  mov     [rsp+arg_8], rbx
0x180090585  push    rbp
0x180090586  push    rsi
0x180090587  push    rdi
0x180090588  push    r12
0x18009058a  push    r13
0x18009058c  push    r14
0x18009058e  push    r15
0x180090590  mov     eax, 10D0h
0x180090595  call    _alloca_probe
0x18009059a  sub     rsp, rax
0x18009059d  mov     rax, cs:__security_cookie
0x1800905a4  xor     rax, rsp
0x1800905a7  mov     [rsp+1108h+var_48], rax
0x1800905af  mov     rsi, [rsp+1108h+arg_30]
0x1800905b7  mov     rbp, rcx
0x1800905ba  mov     rcx, [rsp+1108h+arg_60]
0x1800905c2  mov     r13, r8
0x1800905c5  mov     r15, [rsp+1108h+arg_38]
0x1800905cd  mov     r12, [rsp+1108h+arg_70]
0x1800905d5  mov     [rsp+1108h+var_10B8], rcx
0x1800905da  mov     qword ptr [rsp+1108h+var_10B0], r9
0x1800905df  mov     [rsp+1108h+var_10A8], rdx
0x1800905e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800905eb  lea     r14, WPP_GLOBAL_Control
0x1800905f2  cmp     rax, r14
0x1800905f5  jz      short loc_180090644
0x1800905f7  test    dword ptr [rax+1Ch], 10000h
0x1800905fe  jz      short loc_180090644
0x180090600  cmp     byte ptr [rax+19h], 5
0x180090604  jb      short loc_180090644
0x180090606  mov     rbx, [rbp+10h]
0x18009060a  call    RdpX_GetActivityIdPrefix
0x18009060f  mov     rcx, cs:WPP_GLOBAL_Control
0x180090616  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18009061d  mov     edx, 1Ah
0x180090622  mov     qword ptr [rsp+1108h+var_10E8], rbx
0x180090627  mov     r9d, eax
0x18009062a  mov     rcx, [rcx+10h]
0x18009062e  call    WPP_SF_Dq
0x180090633  mov     rax, cs:WPP_GLOBAL_Control
0x18009063a  mov     rcx, [rsp+1108h+var_10B8]
0x18009063f  mov     r9, qword ptr [rsp+1108h+var_10B0]; unsigned int
0x180090644  test    r13, r13
0x180090647  jnz     short loc_18009068F
0x180090649  cmp     rax, r14
0x18009064c  jz      short loc_180090685
0x18009064e  test    byte ptr [rax+1Ch], 8
0x180090652  jz      short loc_180090685
0x180090654  cmp     byte ptr [rax+19h], 2
0x180090658  jb      short loc_180090685
0x18009065a  call    RdpX_GetActivityIdPrefix
0x18009065f  lea     edx, [r13+1Bh]
0x180090663  mov     rcx, cs:WPP_GLOBAL_Control
0x18009066a  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180090671  mov     r9d, eax
0x180090674  mov     dword ptr [rsp+1108h+var_10E8], 80070057h
0x18009067c  mov     rcx, [rcx+10h]
0x180090680  call    WPP_SF_Dd
0x180090685  mov     ebx, 80070057h
0x18009068a  jmp     loc_180090B58
0x18009068f  mov     rdi, [rsp+1108h+arg_40]
0x180090697  test    rdi, rdi
0x18009069a  jnz     short loc_1800906B7
0x18009069c  cmp     rax, r14
0x18009069f  jz      short loc_180090685
0x1800906a1  test    byte ptr [rax+1Ch], 8
0x1800906a5  jz      short loc_180090685
0x1800906a7  cmp     byte ptr [rax+19h], 2
0x1800906ab  jb      short loc_180090685
0x1800906ad  call    RdpX_GetActivityIdPrefix
0x1800906b2  lea     edx, [rdi+1Ch]
0x1800906b5  jmp     short loc_180090663
0x1800906b7  test    rcx, rcx
0x1800906ba  jnz     short loc_1800906D9
0x1800906bc  cmp     rax, r14
0x1800906bf  jz      short loc_180090685
0x1800906c1  test    byte ptr [rax+1Ch], 8
0x1800906c5  jz      short loc_180090685
0x1800906c7  cmp     byte ptr [rax+19h], 2
0x1800906cb  jb      short loc_180090685
0x1800906cd  call    RdpX_GetActivityIdPrefix
0x1800906d2  mov     edx, 1Dh
0x1800906d7  jmp     short loc_180090663
0x1800906d9  lea     r8, [rsp+1108h+var_1098]; unsigned __int16 *
0x1800906de  mov     rdx, r9; unsigned __int16 *
0x1800906e1  mov     rcx, r13; unsigned __int16 *
0x1800906e4  call    ?RadcValidateAndCreateActualUrl@@YAJPEBG0PEAGK@Z; RadcValidateAndCreateActualUrl(ushort const *,ushort const *,ushort *,ulong)
0x1800906e9  mov     ebx, eax
0x1800906eb  test    eax, eax
0x1800906ed  jns     short loc_18009074C
0x1800906ef  mov     rax, cs:WPP_GLOBAL_Control
0x1800906f6  cmp     rax, r14
0x1800906f9  jz      loc_180090B58
0x1800906ff  test    byte ptr [rax+1Ch], 8
0x180090703  jz      loc_180090B58
0x180090709  cmp     byte ptr [rax+19h], 2
0x18009070d  jb      loc_180090B58
0x180090713  call    RdpX_GetActivityIdPrefix
0x180090718  mov     edx, 1Eh
0x18009071d  lea     rcx, aRadcvalidatean; "RadcValidateAndCreateActualUrl failed"
0x180090724  mov     dword ptr [rsp+1108h+var_10E0], ebx
0x180090728  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18009072f  mov     qword ptr [rsp+1108h+var_10E8], rcx
0x180090734  mov     r9d, eax
0x180090737  mov     rcx, cs:WPP_GLOBAL_Control
0x18009073e  mov     rcx, [rcx+10h]
0x180090742  call    WPP_SF_DsD
0x180090747  jmp     loc_180090B58
0x18009074c  lea     r14, [rbp+38h]
0x180090750  mov     rcx, r14; this
0x180090753  lea     rdx, [rsp+1108h+var_1098]; unsigned __int16 *
0x180090758  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009075d  mov     ebx, eax
0x18009075f  test    eax, eax
0x180090761  jns     short loc_1800907A1
0x180090763  mov     rax, cs:WPP_GLOBAL_Control
0x18009076a  lea     r15, WPP_GLOBAL_Control
0x180090771  cmp     rax, r15
0x180090774  jz      loc_180090B58
0x18009077a  test    byte ptr [rax+1Ch], 8
0x18009077e  jz      loc_180090B58
0x180090784  cmp     byte ptr [rax+19h], 2
0x180090788  jb      loc_180090B58
0x18009078e  call    RdpX_GetActivityIdPrefix
0x180090793  mov     edx, 1Fh
0x180090798  lea     rcx, aMBstrurlAppend; "m_bstrUrl.Append failed"
0x18009079f  jmp     short loc_180090724
0x1800907a1  mov     rcx, [r14]; pwszUrl
0x1800907a4  lea     r9, [rbp+40h]; lpUrlComponents
0x1800907a8  mov     eax, 1
0x1800907ad  mov     dword ptr [r9], 68h ; 'h'
0x1800907b4  xor     r8d, r8d; dwFlags
0x1800907b7  mov     [rbp+50h], eax
0x1800907ba  xor     edx, edx; dwUrlLength
0x1800907bc  mov     [rbp+60h], eax
0x1800907bf  mov     [rbp+70h], eax
0x1800907c2  mov     [rbp+80h], eax
0x1800907c8  mov     [rbp+90h], eax
0x1800907ce  mov     [rbp+0A0h], eax
0x1800907d4  call    cs:__imp_WinHttpCrackUrl
0x1800907da  test    eax, eax
0x1800907dc  jnz     short loc_180090849
0x1800907de  call    cs:__imp_GetLastError
0x1800907e4  mov     ebx, eax
0x1800907e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800907ed  lea     r15, WPP_GLOBAL_Control
0x1800907f4  cmp     rax, r15
0x1800907f7  jz      short loc_18009082D
0x1800907f9  test    byte ptr [rax+1Ch], 8
0x1800907fd  jz      short loc_18009082D
0x1800907ff  cmp     byte ptr [rax+19h], 2
0x180090803  jb      short loc_18009082D
0x180090805  call    RdpX_GetActivityIdPrefix
0x18009080a  mov     rcx, cs:WPP_GLOBAL_Control
0x180090811  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180090818  mov     edx, 20h ; ' '
0x18009081d  mov     dword ptr [rsp+1108h+var_10E8], ebx
0x180090821  mov     r9d, eax
0x180090824  mov     rcx, [rcx+10h]
0x180090828  call    WPP_SF_Dd
0x18009082d  test    ebx, ebx
0x18009082f  jle     short loc_18009083A
0x180090831  movzx   ebx, bx
0x180090834  or      ebx, 80070000h
0x18009083a  test    ebx, ebx
0x18009083c  mov     eax, 80004005h
0x180090841  cmovns  ebx, eax
0x180090844  jmp     loc_180090B58
0x180090849  test    rsi, rsi
0x18009084c  jz      short loc_1800908A4
0x18009084e  lea     rcx, [rbp+0A8h]; this
0x180090855  mov     rdx, rsi; unsigned __int16 *
0x180090858  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009085d  mov     ebx, eax
0x18009085f  test    eax, eax
0x180090861  jns     short loc_1800908A4
0x180090863  mov     rax, cs:WPP_GLOBAL_Control
0x18009086a  lea     r15, WPP_GLOBAL_Control
0x180090871  cmp     rax, r15
0x180090874  jz      loc_180090B58
0x18009087a  test    byte ptr [rax+1Ch], 8
0x18009087e  jz      loc_180090B58
0x180090884  cmp     byte ptr [rax+19h], 2
0x180090888  jb      loc_180090B58
0x18009088e  call    RdpX_GetActivityIdPrefix
0x180090893  mov     edx, 21h ; '!'
0x180090898  lea     rcx, aMBstrauthcooki; "m_bstrAuthCookie.Append failed"
0x18009089f  jmp     loc_180090724
0x1800908a4  lea     rcx, [rbp+0B0h]; this
0x1800908ab  test    r15, r15
0x1800908ae  jz      short loc_180090903
0x1800908b0  mov     rdx, r15; unsigned __int16 *
0x1800908b3  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800908b8  mov     ebx, eax
0x1800908ba  test    eax, eax
0x1800908bc  jns     loc_180090956
0x1800908c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800908c9  lea     r15, WPP_GLOBAL_Control
0x1800908d0  cmp     rax, r15
0x1800908d3  jz      loc_180090B58
0x1800908d9  test    byte ptr [rax+1Ch], 8
0x1800908dd  jz      loc_180090B58
0x1800908e3  cmp     byte ptr [rax+19h], 2
0x1800908e7  jb      loc_180090B58
0x1800908ed  call    RdpX_GetActivityIdPrefix
0x1800908f2  mov     edx, 22h ; '"'
0x1800908f7  lea     rcx, aMBstrclaimstok_0; "m_bstrClaimsToken.Append failed"
0x1800908fe  jmp     loc_180090724
0x180090903  lea     rdx, LocaleName; unsigned __int16 *
0x18009090a  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009090f  mov     ebx, eax
0x180090911  test    eax, eax
0x180090913  jns     short loc_180090956
0x180090915  mov     rax, cs:WPP_GLOBAL_Control
0x18009091c  lea     r15, WPP_GLOBAL_Control
0x180090923  cmp     rax, r15
0x180090926  jz      loc_180090B58
0x18009092c  test    byte ptr [rax+1Ch], 8
0x180090930  jz      loc_180090B58
0x180090936  cmp     byte ptr [rax+19h], 2
0x18009093a  jb      loc_180090B58
0x180090940  call    RdpX_GetActivityIdPrefix
0x180090945  mov     edx, 23h ; '#'
0x18009094a  lea     rcx, aMBstrclaimstok; "m_bstrClaimsToken.Append(empty string) "...
0x180090951  jmp     loc_180090724
0x180090956  test    r12, r12
0x180090959  jz      short loc_1800909B1
0x18009095b  lea     rcx, [rbp+100h]; this
0x180090962  mov     rdx, r12; unsigned __int16 *
0x180090965  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009096a  mov     ebx, eax
0x18009096c  test    eax, eax
0x18009096e  jns     short loc_1800909B1
0x180090970  mov     rax, cs:WPP_GLOBAL_Control
0x180090977  lea     r15, WPP_GLOBAL_Control
0x18009097e  cmp     rax, r15
0x180090981  jz      loc_180090B58
0x180090987  test    byte ptr [rax+1Ch], 8
0x18009098b  jz      loc_180090B58
0x180090991  cmp     byte ptr [rax+19h], 2
0x180090995  jb      loc_180090B58
0x18009099b  call    RdpX_GetActivityIdPrefix
0x1800909a0  mov     edx, 24h ; '$'
0x1800909a5  lea     rcx, aMBstrpreviouse; "m_bstrPreviousETag.Append failed"
0x1800909ac  jmp     loc_180090724
0x1800909b1  mov     edx, [rsp+1108h+arg_20]
0x1800909b8  mov     rcx, rbp
0x1800909bb  call    ?ProcessHttpMethod@RdpWinRadcHttpRequest@@AEAAJW4_RDPX_RADC_HTTP_METHOD@@@Z; RdpWinRadcHttpRequest::ProcessHttpMethod(_RDPX_RADC_HTTP_METHOD)
0x1800909c0  mov     ebx, eax
0x1800909c2  test    eax, eax
0x1800909c4  jns     short loc_180090A07
0x1800909c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800909cd  lea     r15, WPP_GLOBAL_Control
0x1800909d4  cmp     rax, r15
0x1800909d7  jz      loc_180090B58
0x1800909dd  test    byte ptr [rax+1Ch], 8
0x1800909e1  jz      loc_180090B58
0x1800909e7  cmp     byte ptr [rax+19h], 2
0x1800909eb  jb      loc_180090B58
0x1800909f1  call    RdpX_GetActivityIdPrefix
0x1800909f6  mov     edx, 25h ; '%'
0x1800909fb  lea     rcx, aProcesshttpmet; "ProcessHttpMethod failed"
0x180090a02  jmp     loc_180090724
0x180090a07  mov     rax, [rsp+1108h+var_10A8]
0x180090a0c  mov     rbx, [rsp+1108h+arg_48]
0x180090a14  mov     [rbp+0C8h], rdi
0x180090a1b  lea     rdi, [rbp+0D0h]
0x180090a22  mov     [rbp+18h], rax
0x180090a26  mov     byte ptr [rbp+0B8h], 1
0x180090a2d  cmp     rbx, [rdi]
0x180090a30  jz      short loc_180090A50
0x180090a32  mov     rcx, rdi
0x180090a35  call    ?SafeRelease@?$RdpXSPtr@V?$RdpXPlatKeyValuePair@_KPEAUHostMessage@RdpWinDiagnosticsHttpManager@@@@@@AEAAXXZ; RdpXSPtr<RdpXPlatKeyValuePair<unsigned __int64,RdpWinDiagnosticsHttpManager::HostMessage *>>::SafeRelease(void)
0x180090a3a  mov     [rdi], rbx
0x180090a3d  test    rbx, rbx
0x180090a40  jz      short loc_180090A50
0x180090a42  mov     rax, [rbx]
0x180090a45  mov     rcx, rbx
0x180090a48  mov     rax, [rax]
0x180090a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a50  mov     eax, [rsp+1108h+arg_50]
0x180090a57  lea     rcx, [rbp+0E8h]
0x180090a5e  mov     rdx, [rsp+1108h+var_10B8]
0x180090a63  mov     [rbp+0D8h], eax
0x180090a69  mov     eax, [rsp+1108h+arg_58]
0x180090a70  mov     [rbp+0DCh], eax
0x180090a76  call    ??4?$RdpXSPtr@URdpXInterfaceTaskScheduler@@@@QEAAPEAURdpXInterfaceTaskScheduler@@PEAU1@@Z; RdpXSPtr<RdpXInterfaceTaskScheduler>::operator=(RdpXInterfaceTaskScheduler *)
0x180090a7b  mov     rax, [rsp+1108h+arg_68]
0x180090a83  movaps  xmm0, xmmword ptr [rax]
0x180090a86  movdqu  xmmword ptr [rbp+0F0h], xmm0
0x180090a8e  mov     rax, cs:WPP_GLOBAL_Control
0x180090a95  lea     r15, WPP_GLOBAL_Control
0x180090a9c  cmp     rax, r15
0x180090a9f  jz      short loc_180090AF1
0x180090aa1  test    dword ptr [rax+1Ch], 10000h
0x180090aa8  jz      short loc_180090AF1
0x180090aaa  cmp     byte ptr [rax+19h], 4
0x180090aae  jb      short loc_180090AF1
0x180090ab0  mov     rbx, [r14]
  ... truncated ...
```
