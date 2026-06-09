# CMDEContentServer::BeginAuthenticate(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14003fc9c`
- end: `0x1400400f8`
- name: `?BeginAuthenticate@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1116`
- prototype: `__int64 __fastcall(CMDEContentServer *this, IUnknown *, IMFAsyncCallback *pCallback, IUnknown *punkState)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x14000b3b0`
- `0x14000c920`
- `0x140024688`
- `0x1400307dc`
- `0x140035084`
- `0x1400359f4`
- `0x14003db54`
- `0x14003f17c`
- `0x14003fc9c`
- `0x140040100`
- `0x14005480c`
- `0x140057bc4`
- `0x140090118`
- `0x140090174`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x14004003e`
- `ole32!PropVariantClear` at `0x140040048`
- `ole32!PropVariantClear` at `0x14004003e`
- `ole32!PropVariantClear` at `0x140040048`
- `MFPlat!MFCreateAsyncResult` at `0x14003fd8e`
- `MFPlat!MFCreateAsyncResult` at `0x14003fd8e`
- `MFPlat!MFInvokeCallback` at `0x14003fff9`
- `MFPlat!MFInvokeCallback` at `0x14003fff9`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::BeginAuthenticate(
        CMDEContentServer *this,
        IUnknown *a2,
        IMFAsyncCallback *pCallback,
        IUnknown *punkState)
{
  int v8; // ecx
  CNTService *v9; // rcx
  HRESULT MACAddress; // ebx
  __int64 v11; // rdx
  PVOID v12; // rcx
  int v13; // esi
  int v14; // eax
  HRESULT v15; // eax
  int v16; // ecx
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp-39h] BYREF
  __int64 v19; // [rsp+38h] [rbp-31h] BYREF
  __int64 v20; // [rsp+40h] [rbp-29h] BYREF
  __int64 v21; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v22[3]; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v24; // [rsp+78h] [rbp+Fh]
  PROPVARIANT v25[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v26; // [rsp+90h] [rbp+27h]
  __int64 v27; // [rsp+D0h] [rbp+67h] BYREF

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    &v21,
    ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v8,
      (unsigned int)MDE_Callback_Begin_Authenticate_Start,
      (_DWORD)a2,
      (_DWORD)pCallback,
      (char)punkState,
      0);
  v9 = (CNTService *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      a2,
      pCallback,
      punkState);
  }
  CNTService::IncrementContentRequestsOutstanding(v9);
  ppAsyncResult = 0;
  v27 = 0;
  v20 = 0;
  *(_OWORD *)pvar = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  MACAddress = MFCreateAsyncResult(a2, pCallback, punkState, &ppAsyncResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((MACAddress >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)MACAddress);
  }
  if ( MACAddress >= 0 )
  {
    MACAddress = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[13].QueryInterface)(
                   a2,
                   &IID_IPropertyStore,
                   &v27);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = ((MACAddress >> 31) & 0xFFFFFFFD) + 5;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v11 )
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          (unsigned int)MACAddress,
          v27);
    }
    if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
      McTemplateU0p_EventWriteTransfer(v12, v11, v27);
    if ( MACAddress >= 0 )
    {
      MACAddress = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[12].Release)(
                     a2,
                     &IID_IPropertyStore,
                     &v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((MACAddress >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          132,
          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          (unsigned int)MACAddress,
          v20);
      }
      if ( MACAddress >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v19);
        MACAddress = CMDEContentServer::GetMACAddress(this, v27, &v19);
        if ( *(_DWORD *)(v19 - 16) )
        {
          v22[0] = 31;
          v22[2] = 0;
          v22[1] = v19;
          v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v27 + 48LL))(
                  v27,
                  qword_1400BF680,
                  v22);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v13 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v13);
          }
          if ( MACAddress >= 0 )
            MACAddress = v13;
        }
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v19);
        if ( MACAddress >= 0 )
        {
          CMDEContentServer::UpdateConnectionInfo(this, (struct IMFNetEvent *)a2);
          v14 = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
                  ppAsyncResult,
                  (unsigned int)MACAddress);
          MACAddress = v14;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v14 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              134,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v14);
          }
          if ( MACAddress >= 0 )
          {
            v15 = MFInvokeCallback(ppAsyncResult);
            MACAddress = v15;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v15 >> 31) & 0xFFFFFFFD) + 5 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                135,
                &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                (unsigned int)v15);
            }
          }
        }
      }
    }
  }
  PropVariantClear(pvar);
  PropVariantClear(v25);
  v16 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((MACAddress >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      136,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)MACAddress);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v16,
      (unsigned int)MDE_Callback_Begin_Authenticate_Stop,
      (_DWORD)a2,
      (_DWORD)pCallback,
      (char)punkState,
      MACAddress);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppAsyncResult);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v21);
  return (unsigned int)MACAddress;
}

```

## disassembly

```asm
0x14003fc9c  mov     [rsp-8+arg_8], rbx
0x14003fca1  mov     [rsp-8+arg_10], rsi
0x14003fca6  push    rbp
0x14003fca7  push    rdi
0x14003fca8  push    r12
0x14003fcaa  push    r14
0x14003fcac  push    r15
0x14003fcae  lea     rbp, [rsp-37h]
0x14003fcb3  sub     rsp, 0A0h
0x14003fcba  mov     r15, r9
0x14003fcbd  mov     r12, r8
0x14003fcc0  mov     rdi, rdx
0x14003fcc3  mov     r14, rcx
0x14003fcc6  mov     rax, rcx
0x14003fcc9  lea     r10, [rcx+8]
0x14003fccd  neg     rax
0x14003fcd0  sbb     rdx, rdx
0x14003fcd3  and     rdx, r10
0x14003fcd6  lea     rcx, [rbp+57h+var_78]
0x14003fcda  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14003fcdf  nop
0x14003fce0  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14003fce7  jz      short loc_14003FD08
0x14003fce9  mov     dword ptr [rsp+0C0h+var_98], 0
0x14003fcf1  mov     [rsp+0C0h+var_A0], r15
0x14003fcf6  mov     r9, r12
0x14003fcf9  mov     r8, rdi
0x14003fcfc  lea     rdx, MDE_Callback_Begin_Authenticate_Start
0x14003fd03  call    McTemplateU0pppq_EventWriteTransfer
0x14003fd08  lea     rax, WPP_GLOBAL_Control
0x14003fd0f  lea     rsi, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14003fd16  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd1d  cmp     rcx, rax
0x14003fd20  jz      short loc_14003FD4C
0x14003fd22  test    byte ptr [rcx+1Ch], 1
0x14003fd26  jz      short loc_14003FD4C
0x14003fd28  cmp     byte ptr [rcx+19h], 5
0x14003fd2c  jb      short loc_14003FD4C
0x14003fd2e  mov     edx, 81h
0x14003fd33  mov     [rsp+0C0h+var_98], r15
0x14003fd38  mov     [rsp+0C0h+var_A0], r12
0x14003fd3d  mov     r9, rdi
0x14003fd40  mov     r8, rsi
0x14003fd43  mov     rcx, [rcx+10h]
0x14003fd47  call    WPP_SF_qqq
0x14003fd4c  call    ?IncrementContentRequestsOutstanding@CNTService@@QEAAXXZ; CNTService::IncrementContentRequestsOutstanding(void)
0x14003fd51  mov     [rbp+57h+ppAsyncResult], 0
0x14003fd59  mov     [rbp+57h+arg_0], 0
0x14003fd61  mov     [rbp+57h+var_80], 0
0x14003fd69  xorps   xmm0, xmm0
0x14003fd6c  xor     eax, eax
0x14003fd6e  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x14003fd72  mov     [rbp+57h+var_48], rax
0x14003fd76  xorps   xmm1, xmm1
0x14003fd79  movups  xmmword ptr [rbp+57h+var_40], xmm1
0x14003fd7d  mov     [rbp+57h+var_30], rax
0x14003fd81  lea     r9, [rbp+57h+ppAsyncResult]; ppAsyncResult
0x14003fd85  mov     r8, r15; punkState
0x14003fd88  mov     rdx, r12; pCallback
0x14003fd8b  mov     rcx, rdi; punkObject
0x14003fd8e  call    cs:__imp_MFCreateAsyncResult
0x14003fd94  mov     ebx, eax
0x14003fd96  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd9d  lea     rax, WPP_GLOBAL_Control
0x14003fda4  cmp     rcx, rax
0x14003fda7  jz      short loc_14003FDD6
0x14003fda9  test    byte ptr [rcx+1Ch], 2
0x14003fdad  jz      short loc_14003FDD6
0x14003fdaf  mov     edx, ebx
0x14003fdb1  sar     edx, 1Fh
0x14003fdb4  and     edx, 0FFFFFFFDh
0x14003fdb7  add     edx, 5
0x14003fdba  movzx   eax, byte ptr [rcx+19h]
0x14003fdbe  cmp     eax, edx
0x14003fdc0  jb      short loc_14003FDD6
0x14003fdc2  mov     edx, 82h
0x14003fdc7  mov     r9d, ebx
0x14003fdca  mov     r8, rsi
0x14003fdcd  mov     rcx, [rcx+10h]
0x14003fdd1  call    WPP_SF_d
0x14003fdd6  test    ebx, ebx
0x14003fdd8  js      loc_14004003A
0x14003fdde  mov     rax, [rdi]
0x14003fde1  lea     r8, [rbp+57h+arg_0]
0x14003fde5  lea     rdx, IID_IPropertyStore
0x14003fdec  mov     rcx, rdi
0x14003fdef  mov     rax, [rax+138h]
0x14003fdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fdfb  mov     ebx, eax
0x14003fdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fe04  lea     rax, WPP_GLOBAL_Control
0x14003fe0b  cmp     rcx, rax
0x14003fe0e  jz      short loc_14003FE46
0x14003fe10  test    byte ptr [rcx+1Ch], 2
0x14003fe14  jz      short loc_14003FE46
0x14003fe16  mov     edx, ebx
0x14003fe18  sar     edx, 1Fh
0x14003fe1b  and     edx, 0FFFFFFFDh
0x14003fe1e  add     edx, 5
0x14003fe21  movzx   eax, byte ptr [rcx+19h]
0x14003fe25  cmp     eax, edx
0x14003fe27  jb      short loc_14003FE46
0x14003fe29  mov     edx, 83h
0x14003fe2e  mov     rax, [rbp+57h+arg_0]
0x14003fe32  mov     [rsp+0C0h+var_A0], rax
0x14003fe37  mov     r9d, ebx
0x14003fe3a  mov     r8, rsi
0x14003fe3d  mov     rcx, [rcx+10h]
0x14003fe41  call    WPP_SF_dq
0x14003fe46  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14003fe4d  jz      short loc_14003FE58
0x14003fe4f  mov     r8, [rbp+57h+arg_0]
0x14003fe53  call    McTemplateU0p_EventWriteTransfer
0x14003fe58  test    ebx, ebx
0x14003fe5a  js      loc_14004003A
0x14003fe60  mov     rax, [rdi]
0x14003fe63  lea     r8, [rbp+57h+var_80]
0x14003fe67  lea     rdx, IID_IPropertyStore
0x14003fe6e  mov     rcx, rdi
0x14003fe71  mov     rax, [rax+130h]
0x14003fe78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fe7d  mov     ebx, eax
0x14003fe7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fe86  lea     rax, WPP_GLOBAL_Control
0x14003fe8d  cmp     rcx, rax
0x14003fe90  jz      short loc_14003FEC8
0x14003fe92  test    byte ptr [rcx+1Ch], 2
0x14003fe96  jz      short loc_14003FEC8
0x14003fe98  mov     edx, ebx
0x14003fe9a  sar     edx, 1Fh
0x14003fe9d  and     edx, 0FFFFFFFDh
0x14003fea0  add     edx, 5
0x14003fea3  movzx   eax, byte ptr [rcx+19h]
0x14003fea7  cmp     eax, edx
0x14003fea9  jb      short loc_14003FEC8
0x14003feab  mov     edx, 84h
0x14003feb0  mov     rax, [rbp+57h+var_80]
0x14003feb4  mov     [rsp+0C0h+var_A0], rax
0x14003feb9  mov     r9d, ebx
0x14003febc  mov     r8, rsi
0x14003febf  mov     rcx, [rcx+10h]
0x14003fec3  call    WPP_SF_dq
0x14003fec8  test    ebx, ebx
0x14003feca  js      loc_14004003A
0x14003fed0  lea     rcx, [rbp+57h+var_88]
0x14003fed4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14003fed9  nop
0x14003feda  lea     r8, [rbp+57h+var_88]
0x14003fede  mov     rdx, [rbp+57h+arg_0]
0x14003fee2  mov     rcx, r14
0x14003fee5  call    ?GetMACAddress@CMDEContentServer@@AEAAJPEAUIPropertyStore@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CMDEContentServer::GetMACAddress(IPropertyStore *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14003feea  mov     ebx, eax
0x14003feec  mov     rcx, [rbp+57h+var_88]
0x14003fef0  cmp     dword ptr [rcx-10h], 0
0x14003fef4  jz      loc_14003FF81
0x14003fefa  xorps   xmm0, xmm0
0x14003fefd  xor     eax, eax
0x14003feff  movups  [rbp+57h+var_70], xmm0
0x14003ff03  mov     [rbp+57h+var_60], rax
0x14003ff07  mov     eax, 1Fh
0x14003ff0c  mov     word ptr [rbp+57h+var_70], ax
0x14003ff10  mov     qword ptr [rbp+57h+var_70+8], rcx
0x14003ff14  mov     rcx, [rbp+57h+arg_0]
0x14003ff18  mov     rdx, [rcx]
0x14003ff1b  mov     rax, [rdx+30h]
0x14003ff1f  lea     r8, [rbp+57h+var_70]
0x14003ff23  lea     rdx, qword_1400BF680
0x14003ff2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ff2f  mov     esi, eax
0x14003ff31  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ff38  lea     rax, WPP_GLOBAL_Control
0x14003ff3f  cmp     rcx, rax
0x14003ff42  jz      short loc_14003FF75
0x14003ff44  test    byte ptr [rcx+1Ch], 2
0x14003ff48  jz      short loc_14003FF75
0x14003ff4a  mov     edx, esi
0x14003ff4c  sar     edx, 1Fh
0x14003ff4f  and     edx, 0FFFFFFFDh
0x14003ff52  add     edx, 5
0x14003ff55  movzx   eax, byte ptr [rcx+19h]
0x14003ff59  cmp     eax, edx
0x14003ff5b  jb      short loc_14003FF75
0x14003ff5d  mov     edx, 85h
0x14003ff62  mov     r9d, esi
0x14003ff65  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14003ff6c  mov     rcx, [rcx+10h]
0x14003ff70  call    WPP_SF_d
0x14003ff75  test    ebx, ebx
0x14003ff77  cmovns  ebx, esi
0x14003ff7a  lea     rsi, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14003ff81  lea     rcx, [rbp+57h+var_88]
0x14003ff85  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14003ff8a  test    ebx, ebx
0x14003ff8c  js      loc_14004003A
0x14003ff92  mov     rdx, rdi; struct IMFNetEvent *
0x14003ff95  mov     rcx, r14; this
0x14003ff98  call    ?UpdateConnectionInfo@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@@Z; CMDEContentServer::UpdateConnectionInfo(IMFNetEvent *)
0x14003ff9d  mov     rcx, [rbp+57h+ppAsyncResult]
0x14003ffa1  mov     rax, [rcx]
0x14003ffa4  mov     edx, ebx
0x14003ffa6  mov     rax, [rax+28h]
0x14003ffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ffaf  mov     ebx, eax
0x14003ffb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ffb8  lea     r14, WPP_GLOBAL_Control
0x14003ffbf  cmp     rcx, r14
0x14003ffc2  jz      short loc_14003FFF1
0x14003ffc4  test    byte ptr [rcx+1Ch], 2
0x14003ffc8  jz      short loc_14003FFF1
0x14003ffca  mov     edx, eax
0x14003ffcc  sar     edx, 1Fh
0x14003ffcf  and     edx, 0FFFFFFFDh
0x14003ffd2  add     edx, 5
0x14003ffd5  movzx   eax, byte ptr [rcx+19h]
0x14003ffd9  cmp     eax, edx
0x14003ffdb  jb      short loc_14003FFF1
0x14003ffdd  mov     edx, 86h
0x14003ffe2  mov     r9d, ebx
0x14003ffe5  mov     r8, rsi
0x14003ffe8  mov     rcx, [rcx+10h]
0x14003ffec  call    WPP_SF_d
0x14003fff1  test    ebx, ebx
0x14003fff3  js      short loc_14004003A
0x14003fff5  mov     rcx, [rbp+57h+ppAsyncResult]; pAsyncResult
0x14003fff9  call    cs:__imp_MFInvokeCallback
0x14003ffff  mov     ebx, eax
0x140040001  mov     rcx, cs:WPP_GLOBAL_Control
0x140040008  cmp     rcx, r14
0x14004000b  jz      short loc_14004003A
0x14004000d  test    byte ptr [rcx+1Ch], 2
0x140040011  jz      short loc_14004003A
0x140040013  mov     edx, eax
0x140040015  sar     edx, 1Fh
0x140040018  and     edx, 0FFFFFFFDh
0x14004001b  add     edx, 5
0x14004001e  movzx   eax, byte ptr [rcx+19h]
0x140040022  cmp     eax, edx
0x140040024  jb      short loc_14004003A
0x140040026  mov     edx, 87h
0x14004002b  mov     r9d, ebx
0x14004002e  mov     r8, rsi
0x140040031  mov     rcx, [rcx+10h]
0x140040035  call    WPP_SF_d
0x14004003a  lea     rcx, [rbp+57h+pvar]; pvar
0x14004003e  call    cs:__imp_PropVariantClear
0x140040044  lea     rcx, [rbp+57h+var_40]; pvar
0x140040048  call    cs:__imp_PropVariantClear
0x14004004e  mov     rcx, cs:WPP_GLOBAL_Control
0x140040055  lea     rax, WPP_GLOBAL_Control
0x14004005c  cmp     rcx, rax
0x14004005f  jz      short loc_14004008E
0x140040061  test    byte ptr [rcx+1Ch], 1
0x140040065  jz      short loc_14004008E
0x140040067  mov     edx, ebx
0x140040069  sar     edx, 1Fh
0x14004006c  and     edx, 0FFFFFFFDh
0x14004006f  add     edx, 5
0x140040072  movzx   eax, byte ptr [rcx+19h]
0x140040076  cmp     eax, edx
0x140040078  jb      short loc_14004008E
0x14004007a  mov     edx, 88h
0x14004007f  mov     r9d, ebx
0x140040082  mov     r8, rsi
0x140040085  mov     rcx, [rcx+10h]
0x140040089  call    WPP_SF_d
0x14004008e  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x140040095  jz      short loc_1400400B3
0x140040097  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14004009b  mov     [rsp+0C0h+var_A0], r15
0x1400400a0  mov     r9, r12
0x1400400a3  mov     r8, rdi
0x1400400a6  lea     rdx, MDE_Callback_Begin_Authenticate_Stop
0x1400400ad  call    McTemplateU0pppq_EventWriteTransfer
0x1400400b2  nop
0x1400400b3  lea     rcx, [rbp+57h+var_80]
0x1400400b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400400bc  nop
0x1400400bd  lea     rcx, [rbp+57h+arg_0]
0x1400400c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400400c6  nop
0x1400400c7  lea     rcx, [rbp+57h+ppAsyncResult]
0x1400400cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400400d0  nop
0x1400400d1  lea     rcx, [rbp+57h+var_78]
0x1400400d5  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x1400400da  mov     eax, ebx
0x1400400dc  lea     r11, [rsp+0C0h+var_20]
0x1400400e4  mov     rbx, [r11+38h]
0x1400400e8  mov     rsi, [r11+40h]
0x1400400ec  mov     rsp, r11
0x1400400ef  pop     r15
0x1400400f1  pop     r14
0x1400400f3  pop     r12
0x1400400f5  pop     rdi
0x1400400f6  pop     rbp
0x1400400f7  retn
```
