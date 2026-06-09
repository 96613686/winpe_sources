# CMDEContentServer::BeginClose(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14008c944`
- end: `0x14008cfb4`
- name: `?BeginClose@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1648`
- prototype: `__int64 __fastcall(CMDEContentServer *this, IUnknown *, IMFAsyncCallback *pCallback, IUnknown *punkState)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x140006d70`
- `0x14000b3b0`
- `0x14000c780`
- `0x14000c920`
- `0x140018df0`
- `0x140024688`
- `0x1400307dc`
- `0x140035084`
- `0x1400359f4`
- `0x14003beb8`
- `0x14003f17c`
- `0x140045f20`
- `0x1400488f4`
- `0x14004a834`
- `0x14005480c`
- `0x140057bc4`
- `0x14008c944`
- `0x140090118`
- `0x140090174`
- `0x14009e010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14008ca18`
- `KERNEL32!GetTickCount64` at `0x14008ca18`
- `ole32!PropVariantClear` at `0x14008ce0b`
- `ole32!PropVariantClear` at `0x14008ce15`
- `ole32!PropVariantClear` at `0x14008cef1`
- `ole32!PropVariantClear` at `0x14008ce0b`
- `ole32!PropVariantClear` at `0x14008ce15`
- `ole32!PropVariantClear` at `0x14008cef1`
- `MFPlat!MFCreateAsyncResult` at `0x14008ca2f`
- `MFPlat!MFCreateAsyncResult` at `0x14008ca2f`
- `MFPlat!MFInvokeCallback` at `0x14008ce9f`
- `MFPlat!MFInvokeCallback` at `0x14008ce9f`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::BeginClose(
        CMDEContentServer *this,
        IUnknown *a2,
        IMFAsyncCallback *pCallback,
        IUnknown *punkState)
{
  int v8; // ecx
  ULONGLONG TickCount64; // r12
  HRESULT v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HRESULT v19; // eax
  int v20; // ecx
  unsigned int v22; // [rsp+20h] [rbp-A9h]
  unsigned int v23; // [rsp+30h] [rbp-99h] BYREF
  __int64 v24; // [rsp+38h] [rbp-91h] BYREF
  __int64 v25; // [rsp+40h] [rbp-89h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 *v27; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-69h] BYREF
  __int64 v30; // [rsp+68h] [rbp-61h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v32; // [rsp+80h] [rbp-49h]
  PROPVARIANT v33[2]; // [rsp+88h] [rbp-41h] BYREF
  __int64 v34; // [rsp+98h] [rbp-31h]
  PROPVARIANT v35[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-19h]
  __int128 v37; // [rsp+B8h] [rbp-11h] BYREF
  int v38; // [rsp+C8h] [rbp-1h]

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    &v30,
    ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v8,
      (unsigned int)MDE_Callback_Begin_Close_Start,
      (_DWORD)a2,
      (_DWORD)pCallback,
      (char)punkState,
      0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      a2,
      pCallback,
      punkState);
  }
  ppAsyncResult = 0;
  v24 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v23 = 0;
  v25 = 0;
  TickCount64 = GetTickCount64();
  v10 = MFCreateAsyncResult(a2, pCallback, punkState, &ppAsyncResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      192,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v10);
  }
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_19006102_92b7_4263_953c_b84c24bedcce,
            &v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v10,
        v25);
    }
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 336LL))(v25, &v23);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
      {
        v22 = v23;
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          (unsigned int)v10);
      }
      if ( v10 >= 0 )
      {
        v13 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[13].QueryInterface)(
                a2,
                &IID_IPropertyStore,
                &v24);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v12 = ((v13 >> 31) & 0xFFFFFFFD) + 5;
          if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v12 )
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              195,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v13,
              v24);
        }
        if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
          McTemplateU0p_EventWriteTransfer(v12, v11, v24);
        if ( v13 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(
                  v24,
                  qword_1400BF680,
                  v35);
          v14 = (unsigned int)v15;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v15 >> 31) & 0xFFFFFFFD) + 5 )
          {
            v22 = LOWORD(v35[0]);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              196,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v15);
          }
        }
        if ( (int)(v23 + 0x80000000) >= 0 && v23 != -2147024891 && v24 )
        {
          *(_OWORD *)pvar = 0;
          v32 = 0;
          *(_OWORD *)v33 = 0;
          v34 = 0;
          v38 = 0;
          v37 = MFNETCONNECTION_REMOTEIPADDRESS;
          v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *, __int64, unsigned int))(*(_QWORD *)v24 + 40LL))(
                  v24,
                  qword_1400BF668,
                  v33,
                  v14,
                  v22);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v16 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              197,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v16);
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
            (void **)&v29,
            (char *)&Password);
          if ( LOWORD(v33[0]) == 31 && v33[1] )
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, v33[1]);
          v17 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v24 + 40LL))(v24, &v37, pvar);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v17 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v17);
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
            (void **)&v28,
            (char *)&Password);
          if ( LOWORD(pvar[0]) == 31 && pvar[1] )
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, pvar[1]);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v27);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
            &v27,
            L"0x%08x",
            v23);
          CNTService::LogEvent(g_WMCService, &WMC_W_SERVICE_MDE_FAILED_TRANSFER, v29, v28, v27);
          PropVariantClear(pvar);
          PropVariantClear(v33);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v27);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v28);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v29);
        }
        CMDEContentServer::UpdateConnectionInfo(this, (struct IMFNetEvent *)a2);
        v18 = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
                ppAsyncResult,
                (unsigned int)v10);
        v10 = v18;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v18 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            199,
            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
            (unsigned int)v18);
        }
        if ( v10 >= 0 )
        {
          v19 = MFInvokeCallback(ppAsyncResult);
          v10 = v19;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v19 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              200,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v19);
          }
        }
      }
    }
  }
  PropVariantClear(v35);
  CNTService::DecrementContentRequestsOutstandingAtTime(g_WMCService, TickCount64);
  v20 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v10);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v20,
      (unsigned int)MDE_Callback_Begin_Close_Stop,
      (_DWORD)a2,
      (_DWORD)pCallback,
      (char)punkState,
      v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppAsyncResult);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14008c944  push    rbp
0x14008c946  push    rbx
0x14008c947  push    rsi
0x14008c948  push    rdi
0x14008c949  push    r12
0x14008c94b  push    r13
0x14008c94d  push    r14
0x14008c94f  push    r15
0x14008c951  lea     rbp, [rsp-1Fh]
0x14008c956  sub     rsp, 0E8h
0x14008c95d  mov     rax, cs:__security_cookie
0x14008c964  xor     rax, rsp
0x14008c967  mov     [rbp+57h+var_50], rax
0x14008c96b  mov     r15, r9
0x14008c96e  mov     r14, r8
0x14008c971  mov     rsi, rdx
0x14008c974  mov     r13, rcx
0x14008c977  mov     rax, rcx
0x14008c97a  add     rcx, 8
0x14008c97e  neg     rax
0x14008c981  sbb     rdx, rdx
0x14008c984  and     rdx, rcx
0x14008c987  lea     rcx, [rbp+57h+var_B8]
0x14008c98b  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14008c990  nop
0x14008c991  xor     edi, edi
0x14008c993  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008c99a  jz      short loc_14008C9B7
0x14008c99c  mov     dword ptr [rsp+120h+var_F8], edi
0x14008c9a0  mov     [rsp+120h+var_100], r15
0x14008c9a5  mov     r9, r14
0x14008c9a8  mov     r8, rsi
0x14008c9ab  lea     rdx, MDE_Callback_Begin_Close_Start
0x14008c9b2  call    McTemplateU0pppq_EventWriteTransfer
0x14008c9b7  lea     rax, WPP_GLOBAL_Control
0x14008c9be  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c9c5  cmp     rcx, rax
0x14008c9c8  jz      short loc_14008C9F8
0x14008c9ca  test    byte ptr [rcx+1Ch], 1
0x14008c9ce  jz      short loc_14008C9F8
0x14008c9d0  cmp     byte ptr [rcx+19h], 5
0x14008c9d4  jb      short loc_14008C9F8
0x14008c9d6  mov     edx, 0BFh
0x14008c9db  mov     [rsp+120h+var_F8], r15
0x14008c9e0  mov     [rsp+120h+var_100], r14
0x14008c9e5  mov     r9, rsi
0x14008c9e8  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008c9ef  mov     rcx, [rcx+10h]
0x14008c9f3  call    WPP_SF_qqq
0x14008c9f8  mov     [rsp+120h+ppAsyncResult], rdi
0x14008c9fd  mov     [rsp+120h+var_E8], rdi
0x14008ca02  xorps   xmm0, xmm0
0x14008ca05  xor     eax, eax
0x14008ca07  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x14008ca0b  mov     [rbp+57h+var_70], rax
0x14008ca0f  mov     [rsp+120h+var_F0], edi
0x14008ca13  mov     [rsp+120h+var_E0], rdi
0x14008ca18  call    cs:__imp_GetTickCount64
0x14008ca1e  mov     r12, rax
0x14008ca21  lea     r9, [rsp+120h+ppAsyncResult]; ppAsyncResult
0x14008ca26  mov     r8, r15; punkState
0x14008ca29  mov     rdx, r14; pCallback
0x14008ca2c  mov     rcx, rsi; punkObject
0x14008ca2f  call    cs:__imp_MFCreateAsyncResult
0x14008ca35  mov     ebx, eax
0x14008ca37  mov     r10, cs:WPP_GLOBAL_Control
0x14008ca3e  lea     rax, WPP_GLOBAL_Control
0x14008ca45  cmp     r10, rax
0x14008ca48  jz      short loc_14008CA7D
0x14008ca4a  test    byte ptr [r10+1Ch], 2
0x14008ca4f  jz      short loc_14008CA7D
0x14008ca51  mov     ecx, ebx
0x14008ca53  sar     ecx, 1Fh
0x14008ca56  and     ecx, 0FFFFFFFDh
0x14008ca59  add     ecx, 5
0x14008ca5c  movzx   eax, byte ptr [r10+19h]
0x14008ca61  cmp     eax, ecx
0x14008ca63  jb      short loc_14008CA7D
0x14008ca65  mov     edx, 0C0h
0x14008ca6a  mov     r9d, ebx
0x14008ca6d  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008ca74  mov     rcx, [r10+10h]
0x14008ca78  call    WPP_SF_d
0x14008ca7d  test    ebx, ebx
0x14008ca7f  js      loc_14008CEE6
0x14008ca85  mov     rax, [rsi]
0x14008ca88  lea     r8, [rsp+120h+var_E0]
0x14008ca8d  lea     rdx, _GUID_19006102_92b7_4263_953c_b84c24bedcce
0x14008ca94  mov     rcx, rsi
0x14008ca97  mov     rax, [rax]
0x14008ca9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ca9f  mov     ebx, eax
0x14008caa1  mov     r10, cs:WPP_GLOBAL_Control
0x14008caa8  lea     rax, WPP_GLOBAL_Control
0x14008caaf  cmp     r10, rax
0x14008cab2  jz      short loc_14008CAF1
0x14008cab4  test    byte ptr [r10+1Ch], 2
0x14008cab9  jz      short loc_14008CAF1
0x14008cabb  mov     ecx, ebx
0x14008cabd  sar     ecx, 1Fh
0x14008cac0  and     ecx, 0FFFFFFFDh
0x14008cac3  add     ecx, 5
0x14008cac6  movzx   eax, byte ptr [r10+19h]
0x14008cacb  cmp     eax, ecx
0x14008cacd  jb      short loc_14008CAF1
0x14008cacf  mov     edx, 0C1h
0x14008cad4  mov     rax, [rsp+120h+var_E0]
0x14008cad9  mov     [rsp+120h+var_100], rax
0x14008cade  mov     r9d, ebx
0x14008cae1  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cae8  mov     rcx, [r10+10h]
0x14008caec  call    WPP_SF_dq
0x14008caf1  test    ebx, ebx
0x14008caf3  js      loc_14008CEE6
0x14008caf9  mov     rcx, [rsp+120h+var_E0]
0x14008cafe  mov     rax, [rcx]
0x14008cb01  lea     rdx, [rsp+120h+var_F0]
0x14008cb06  mov     rax, [rax+150h]
0x14008cb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cb12  mov     ebx, eax
0x14008cb14  mov     r10, cs:WPP_GLOBAL_Control
0x14008cb1b  lea     rax, WPP_GLOBAL_Control
0x14008cb22  cmp     r10, rax
0x14008cb25  jz      short loc_14008CB62
0x14008cb27  test    byte ptr [r10+1Ch], 2
0x14008cb2c  jz      short loc_14008CB62
0x14008cb2e  mov     ecx, ebx
0x14008cb30  sar     ecx, 1Fh
0x14008cb33  and     ecx, 0FFFFFFFDh
0x14008cb36  add     ecx, 5
0x14008cb39  movzx   eax, byte ptr [r10+19h]
0x14008cb3e  cmp     eax, ecx
0x14008cb40  jb      short loc_14008CB62
0x14008cb42  mov     edx, 0C2h
0x14008cb47  mov     eax, [rsp+120h+var_F0]
0x14008cb4b  mov     dword ptr [rsp+120h+var_100], eax
0x14008cb4f  mov     r9d, ebx
0x14008cb52  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cb59  mov     rcx, [r10+10h]
0x14008cb5d  call    WPP_SF_Dd
0x14008cb62  test    ebx, ebx
0x14008cb64  js      loc_14008CEE6
0x14008cb6a  mov     rax, [rsi]
0x14008cb6d  lea     r8, [rsp+120h+var_E8]
0x14008cb72  lea     rdx, IID_IPropertyStore
0x14008cb79  mov     rcx, rsi
0x14008cb7c  mov     rax, [rax+138h]
0x14008cb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cb88  mov     edi, eax
0x14008cb8a  mov     r10, cs:WPP_GLOBAL_Control
0x14008cb91  lea     rax, WPP_GLOBAL_Control
0x14008cb98  cmp     r10, rax
0x14008cb9b  jz      short loc_14008CBDA
0x14008cb9d  test    byte ptr [r10+1Ch], 2
0x14008cba2  jz      short loc_14008CBDA
0x14008cba4  mov     ecx, edi
0x14008cba6  sar     ecx, 1Fh
0x14008cba9  and     ecx, 0FFFFFFFDh
0x14008cbac  add     ecx, 5
0x14008cbaf  movzx   eax, byte ptr [r10+19h]
0x14008cbb4  cmp     eax, ecx
0x14008cbb6  jb      short loc_14008CBDA
0x14008cbb8  mov     edx, 0C3h
0x14008cbbd  mov     rax, [rsp+120h+var_E8]
0x14008cbc2  mov     [rsp+120h+var_100], rax
0x14008cbc7  mov     r9d, edi
0x14008cbca  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cbd1  mov     rcx, [r10+10h]
0x14008cbd5  call    WPP_SF_dq
0x14008cbda  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008cbe1  jz      short loc_14008CBED
0x14008cbe3  mov     r8, [rsp+120h+var_E8]
0x14008cbe8  call    McTemplateU0p_EventWriteTransfer
0x14008cbed  test    edi, edi
0x14008cbef  js      short loc_14008CC5D
0x14008cbf1  mov     rcx, [rsp+120h+var_E8]
0x14008cbf6  mov     rax, [rcx]
0x14008cbf9  lea     r8, [rbp+57h+var_80]
0x14008cbfd  lea     rdx, qword_1400BF680
0x14008cc04  mov     rax, [rax+28h]
0x14008cc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cc0d  mov     r9d, eax
0x14008cc10  mov     r10, cs:WPP_GLOBAL_Control
0x14008cc17  lea     rdi, WPP_GLOBAL_Control
0x14008cc1e  cmp     r10, rdi
0x14008cc21  jz      short loc_14008CC64
0x14008cc23  test    byte ptr [r10+1Ch], 2
0x14008cc28  jz      short loc_14008CC64
0x14008cc2a  mov     ecx, eax
0x14008cc2c  sar     ecx, 1Fh
0x14008cc2f  and     ecx, 0FFFFFFFDh
0x14008cc32  add     ecx, 5
0x14008cc35  movzx   eax, byte ptr [r10+19h]
0x14008cc3a  cmp     eax, ecx
0x14008cc3c  jb      short loc_14008CC64
0x14008cc3e  movzx   eax, word ptr [rbp+57h+var_80]
0x14008cc42  mov     edx, 0C4h
0x14008cc47  mov     dword ptr [rsp+120h+var_100], eax
0x14008cc4b  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cc52  mov     rcx, [r10+10h]
0x14008cc56  call    WPP_SF_Dd
0x14008cc5b  jmp     short loc_14008CC64
0x14008cc5d  lea     rdi, WPP_GLOBAL_Control
0x14008cc64  mov     edx, 80000000h
0x14008cc69  mov     ecx, [rsp+120h+var_F0]
0x14008cc6d  lea     eax, [rcx+rdx]
0x14008cc70  test    edx, eax
0x14008cc72  jnz     loc_14008CE39
0x14008cc78  cmp     ecx, 80070005h
0x14008cc7e  jz      loc_14008CE39
0x14008cc84  mov     rcx, [rsp+120h+var_E8]
0x14008cc89  test    rcx, rcx
0x14008cc8c  jz      loc_14008CE39
0x14008cc92  xorps   xmm0, xmm0
0x14008cc95  xor     eax, eax
0x14008cc97  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x14008cc9b  mov     [rbp+57h+var_A0], rax
0x14008cc9f  xorps   xmm1, xmm1
0x14008cca2  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x14008cca6  mov     [rbp+57h+var_88], rax
0x14008ccaa  movups  xmmword ptr [rbp+57h+var_64], xmm0
0x14008ccae  movups  xmm1, cs:MFNETCONNECTION_REMOTEIPADDRESS
0x14008ccb5  movdqu  xmmword ptr [rbp-11h], xmm1
0x14008ccba  mov     rax, [rcx]
0x14008ccbd  lea     r8, [rbp+57h+var_98]
0x14008ccc1  lea     rdx, qword_1400BF668
0x14008ccc8  mov     rax, [rax+28h]
0x14008cccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ccd1  mov     r9d, eax
0x14008ccd4  mov     r10, cs:WPP_GLOBAL_Control
0x14008ccdb  cmp     r10, rdi
0x14008ccde  jz      short loc_14008CD10
0x14008cce0  test    byte ptr [r10+1Ch], 2
0x14008cce5  jz      short loc_14008CD10
0x14008cce7  mov     ecx, eax
0x14008cce9  sar     ecx, 1Fh
0x14008ccec  and     ecx, 0FFFFFFFDh
0x14008ccef  add     ecx, 5
0x14008ccf2  movzx   eax, byte ptr [r10+19h]
0x14008ccf7  cmp     eax, ecx
0x14008ccf9  jb      short loc_14008CD10
0x14008ccfb  mov     edx, 0C5h
0x14008cd00  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cd07  mov     rcx, [r10+10h]
0x14008cd0b  call    WPP_SF_d
0x14008cd10  lea     rdx, Password
0x14008cd17  lea     rcx, [rbp+57h+var_C0]
0x14008cd1b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008cd20  nop
0x14008cd21  mov     eax, 1Fh
0x14008cd26  cmp     ax, word ptr [rbp+57h+var_98]
0x14008cd2a  jnz     short loc_14008CD3E
0x14008cd2c  mov     rdx, [rbp+57h+var_98+8]
0x14008cd30  test    rdx, rdx
0x14008cd33  jz      short loc_14008CD3E
0x14008cd35  lea     rcx, [rbp+57h+var_C0]
0x14008cd39  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14008cd3e  mov     rcx, [rsp+120h+var_E8]
0x14008cd43  mov     rax, [rcx]
0x14008cd46  lea     r8, [rbp+57h+pvar]
0x14008cd4a  lea     rdx, [rbp+57h+var_68]
0x14008cd4e  mov     rax, [rax+28h]
0x14008cd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cd57  mov     r9d, eax
0x14008cd5a  mov     r10, cs:WPP_GLOBAL_Control
0x14008cd61  cmp     r10, rdi
0x14008cd64  jz      short loc_14008CD96
0x14008cd66  test    byte ptr [r10+1Ch], 2
0x14008cd6b  jz      short loc_14008CD96
0x14008cd6d  mov     ecx, eax
0x14008cd6f  sar     ecx, 1Fh
0x14008cd72  and     ecx, 0FFFFFFFDh
0x14008cd75  add     ecx, 5
0x14008cd78  movzx   eax, byte ptr [r10+19h]
0x14008cd7d  cmp     eax, ecx
0x14008cd7f  jb      short loc_14008CD96
0x14008cd81  mov     edx, 0C6h
0x14008cd86  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008cd8d  mov     rcx, [r10+10h]
0x14008cd91  call    WPP_SF_d
0x14008cd96  lea     rdx, Password
0x14008cd9d  lea     rcx, [rbp+57h+var_C8]
0x14008cda1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008cda6  nop
0x14008cda7  mov     eax, 1Fh
0x14008cdac  cmp     ax, word ptr [rbp+57h+pvar]
0x14008cdb0  jnz     short loc_14008CDC4
0x14008cdb2  mov     rdx, [rbp+57h+pvar+8]
0x14008cdb6  test    rdx, rdx
0x14008cdb9  jz      short loc_14008CDC4
0x14008cdbb  lea     rcx, [rbp+57h+var_C8]
0x14008cdbf  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14008cdc4  lea     rcx, [rbp+57h+var_D0]
0x14008cdc8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14008cdcd  nop
0x14008cdce  mov     r8d, [rsp+120h+var_F0]
0x14008cdd3  lea     rdx, a0x08x; "0x%08x"
0x14008cdda  lea     rcx, [rbp+57h+var_D0]
0x14008cdde  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14008cde3  mov     rax, [rbp+57h+var_D0]
  ... truncated ...
```
