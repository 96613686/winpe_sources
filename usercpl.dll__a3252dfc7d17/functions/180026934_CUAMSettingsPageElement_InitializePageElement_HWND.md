# CUAMSettingsPageElement::InitializePageElement(HWND__ *)

- ea: `0x180026934`
- end: `0x18002711c`
- name: `?InitializePageElement@CUAMSettingsPageElement@@QEAAJPEAUHWND__@@@Z`
- size: `2024`
- prototype: `__int64 __fastcall(CUAMSettingsPageElement *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027350`

## callees

- `0x180002ae4`
- `0x180004338`
- `0x1800043a8`
- `0x18000d9a4`
- `0x18000d9fc`
- `0x18000dafc`
- `0x18000eb70`
- `0x18000eccc`
- `0x1800258a8`
- `0x180025a0c`
- `0x180026934`
- `0x18002920c`
- `0x180029fec`
- `0x180063fa4`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026e25`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e2f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d10`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d48`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d80`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d10`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d48`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026d80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026ac4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026bf8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026ac4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026bf8`
- `DUI70!StrToID` at `0x180026974`
- `DUI70!StrToID` at `0x180026994`
- `DUI70!StrToID` at `0x180026fdb`
- `DUI70!StrToID` at `0x180026974`
- `DUI70!StrToID` at `0x180026994`
- `DUI70!StrToID` at `0x180026fdb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180026980`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800269a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180026fe7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180026980`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800269a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180026fe7`
- `DUser!DeleteHandle` at `0x180026b36`
- `DUser!DeleteHandle` at `0x180026c6a`
- `DUser!DeleteHandle` at `0x180026b36`
- `DUser!DeleteHandle` at `0x180026c6a`

## pseudocode

```c
__int64 __fastcall CUAMSettingsPageElement::InitializePageElement(CUAMSettingsPageElement *this, HWND a2)
{
  char *v2; // rbx
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // ax
  struct DirectUI::Element *Descendent; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  LPUNKNOWN v9; // rcx
  int NonElevatedObjects; // r14d
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  IUnknown **v14; // r12
  void **v15; // rcx
  __int64 v16; // r8
  float v17; // xmm6_4
  LSTATUS ValueW; // eax
  bool v19; // sf
  float *v20; // rax
  float *v21; // rbx
  _QWORD *v22; // rsi
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  float v26; // xmm6_4
  LSTATUS v27; // eax
  bool v28; // sf
  float *v29; // rax
  float *v30; // rbx
  _QWORD *v31; // rsi
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  IUnknown *v35; // rdx
  int v36; // ebx
  LPSTREAM v37; // rcx
  __int64 v38; // rcx
  _QWORD *v39; // rsi
  __int64 v40; // r8
  LPSTREAM v41; // rcx
  LPSTREAM v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rcx
  signed int LastError; // eax
  DirectUI::SimpleTimer *v47; // rcx
  __int64 v48; // rcx
  LPSTREAM v49; // rcx
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  _DWORD *v54; // rax
  _DWORD *v55; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v56; // rcx
  unsigned __int16 v57; // ax
  struct DirectUI::Element *v58; // rax
  const wchar_t *v59; // r8
  DWORD pcbData[2]; // [rsp+48h] [rbp-39h] BYREF
  int pvData; // [rsp+50h] [rbp-31h] BYREF
  LPSTREAM v63; // [rsp+58h] [rbp-29h] BYREF
  LPUNKNOWN v64; // [rsp+60h] [rbp-21h] BYREF
  LPUNKNOWN pUnk; // [rsp+68h] [rbp-19h] BYREF
  LPSTREAM ppStm[2]; // [rsp+70h] [rbp-11h] BYREF

  v2 = (char *)this + 240;
  *((_QWORD *)this + 30) = a2;
  v4 = StrToID(L"idPageLoadProgress");
  *((_QWORD *)this + 36) = DirectUI::Element::FindDescendent(this, v4);
  v5 = StrToID(L"idPageLoadProgressRing");
  Descendent = DirectUI::Element::FindDescendent(this, v5);
  v7 = (unsigned int)tls_index;
  *((_QWORD *)this + 37) = Descendent;
  if ( __TSS0__1__InitializePageElement_CUAMSettingsPageElement__QEAAJPEAUHWND_____Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v7) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__InitializePageElement_CUAMSettingsPageElement__QEAAJPEAUHWND_____Z_4HA);
    if ( __TSS0__1__InitializePageElement_CUAMSettingsPageElement__QEAAJPEAUHWND_____Z_4HA == -1 )
    {
      qword_1800A3458 = 0;
      qword_1800A3450 = (__int64)&IID_ILocalMachine;
      `CUAMSettingsPageElement::InitializePageElement'::`2'::s_rgInnerObjects = CLSID_ShellLocalMachine;
      byte_1800A3460 = 0;
      Init_thread_footer(&__TSS0__1__InitializePageElement_CUAMSettingsPageElement__QEAAJPEAUHWND_____Z_4HA);
    }
  }
  NonElevatedObjects = CUserCplInitializer::s_CreateNonElevatedObjects(
                         (struct INNER_OBJ_INFO *const)&`CUAMSettingsPageElement::InitializePageElement'::`2'::s_rgInnerObjects,
                         1u);
  if ( NonElevatedObjects < 0 )
    goto LABEL_96;
  v64 = 0;
  v11 = Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<CLogonEnumUsers,ILogonEnumUsers,>(&v64);
  NonElevatedObjects = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 8) == 0 )
      goto LABEL_93;
    v59 = L"CLogonEnumUsers creation";
    goto LABEL_92;
  }
  v14 = (IUnknown **)((char *)this + 216);
  v11 = Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<CUserManager,IUserManager,HWND__ * &>(
          (_QWORD *)this + 27,
          (__int64)v2);
  NonElevatedObjects = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 8) == 0 )
      goto LABEL_93;
    v59 = L"CUserManager creation";
LABEL_92:
    McTemplateU0zq_EventWriteTransfer(v13, v12, v59, (unsigned int)v11);
    goto LABEL_93;
  }
  *((_BYTE *)this + 232) = 0;
  pUnk = 0;
  if ( qword_1800A3458 )
    (**(void (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))qword_1800A3458)(
      qword_1800A3458,
      &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461,
      &pUnk);
  if ( (int)CPrivateNotificationWindow::CreateInstance(
              (struct CPrivateNotificationWindowSink *)(-(__int64)(this != 0) & ((unsigned __int64)this + 200)),
              (struct CPrivateNotificationWindow **)this + 26) >= 0 )
  {
    v17 = FLOAT_0_2;
    pvData = 0;
    pcbData[0] = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Usercpl",
               L"ProgressDelay",
               0x10u,
               0,
               &pvData,
               pcbData);
    v19 = ValueW < 0;
    if ( ValueW > 0 )
      v19 = 1;
    if ( !v19 )
      v17 = (float)pvData / 1000.0;
    v20 = (float *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v20;
    if ( v20 )
    {
      v20[4] = v17;
      *(_QWORD *)v20 = 0;
      *((_QWORD *)v20 + 1) = 0;
      v20[5] = 0.0;
    }
    else
    {
      v21 = 0;
    }
    v22 = (_QWORD *)*((_QWORD *)this + 34);
    *((_QWORD *)this + 34) = 0;
    if ( v22 )
    {
      if ( *v22 )
      {
        DeleteHandle(*v22);
        *v22 = 0;
      }
      v23 = v22[1];
      if ( v23 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 1);
      operator delete(v22);
    }
    *((_QWORD *)this + 34) = v21;
    if ( v21 )
    {
      v24 = *((_QWORD *)v21 + 1);
      if ( v24 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 1);
      v25 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v25 )
      {
        v26 = FLOAT_0_80000001;
        *v25 = &DirectUI::SimpleTimer::InvokeHelper<_lambda_ca5ba48ff2b3b5e9ee8d832ebbd16844_>::`vftable';
        v25[1] = this;
        *((_QWORD *)v21 + 1) = v25;
        pcbData[0] = 4;
        v27 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Usercpl",
                L"ProgressMin",
                0x10u,
                0,
                &pvData,
                pcbData);
        v28 = v27 < 0;
        if ( v27 > 0 )
          v28 = 1;
        if ( !v28 )
          v26 = (float)pvData / 1000.0;
        v29 = (float *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        v30 = v29;
        if ( v29 )
        {
          v29[4] = v26;
          *(_QWORD *)v29 = 0;
          *((_QWORD *)v29 + 1) = 0;
          v29[5] = 0.0;
        }
        else
        {
          v30 = 0;
        }
        v31 = (_QWORD *)*((_QWORD *)this + 35);
        *((_QWORD *)this + 35) = 0;
        if ( v31 )
        {
          if ( *v31 )
          {
            DeleteHandle(*v31);
            *v31 = 0;
          }
          v32 = v31[1];
          if ( v32 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 8LL))(v32, 1);
          operator delete(v31);
        }
        *((_QWORD *)this + 35) = v30;
        if ( v30 )
        {
          v33 = *((_QWORD *)v30 + 1);
          if ( v33 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 8LL))(v33, 1);
          v34 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v34 )
          {
            v15 = &DirectUI::SimpleTimer::InvokeHelper<_lambda_fa9aee1af039da89e2ab577eed5b0cd0_>::`vftable';
            v34[1] = this;
            *v34 = &DirectUI::SimpleTimer::InvokeHelper<_lambda_fa9aee1af039da89e2ab577eed5b0cd0_>::`vftable';
          }
          else
          {
            v34 = 0;
          }
          *((_QWORD *)v30 + 1) = v34;
          if ( v34 )
          {
            v35 = *v14;
            ppStm[0] = 0;
            v63 = 0;
            *(_QWORD *)pcbData = 0;
            v36 = CoMarshalInterThreadInterfaceInStream(&GUID_73aecad8_7e70_4e21_8767_82b03c862455, v35, ppStm);
            if ( v36 >= 0 )
            {
              v37 = v63;
              if ( v63 )
              {
                v63 = 0;
                (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v37 + 16LL))(v37);
              }
              v36 = CoMarshalInterThreadInterfaceInStream(&GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461, pUnk, &v63);
              if ( v36 >= 0 )
              {
                v38 = *(_QWORD *)pcbData;
                if ( *(_QWORD *)pcbData )
                {
                  *(_QWORD *)pcbData = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                }
                v36 = CoMarshalInterThreadInterfaceInStream(
                        &GUID_3ee328ab_8f69_420a_9b86_7080f22af38b,
                        v64,
                        (LPSTREAM *)pcbData);
                if ( v36 >= 0 )
                {
                  v39 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v39 )
                  {
                    v40 = *(_QWORD *)pcbData;
                    v41 = v63;
                    v42 = ppStm[0];
                    v43 = *((_QWORD *)this + 26);
                    *v39 = &CUserMgrInitializationData::`vftable';
                    v39[1] = v43;
                    v39[2] = v42;
                    v39[3] = v41;
                    v39[4] = v40;
                    _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v39[2] + 8LL))(v39[2]);
                    v44 = v39[3];
                    if ( v44 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
                    v45 = v39[4];
                    if ( v45 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
                    if ( SHCreateThread(InitializeUserManagerAsync, v39, 0xCu, 0) )
                    {
                      v47 = (DirectUI::SimpleTimer *)*((_QWORD *)this + 34);
                      *((_DWORD *)this + 67) = 1;
                      DirectUI::SimpleTimer::Start(v47);
                      v36 = 0;
                    }
                    else
                    {
                      LastError = GetLastError();
                      v36 = LastError;
                      if ( LastError > 0 )
                        v36 = (unsigned __int16)LastError | 0x80070000;
                      if ( v36 >= 0 )
                        v36 = -2147467259;
                      (*(void (__fastcall **)(_QWORD *, __int64))*v39)(v39, 1);
                    }
                  }
                  else
                  {
                    v36 = -2147024882;
                  }
                }
              }
            }
            v48 = *(_QWORD *)pcbData;
            if ( *(_QWORD *)pcbData )
            {
              *(_QWORD *)pcbData = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            }
            v49 = v63;
            if ( v63 )
            {
              v63 = 0;
              (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v49 + 16LL))(v49);
            }
            v15 = (void **)ppStm[0];
            if ( ppStm[0] )
            {
              ppStm[0] = 0;
              (*((void (__fastcall **)(void **))*v15 + 2))(v15);
            }
            if ( v36 >= 0 )
              goto LABEL_82;
          }
        }
      }
      else
      {
        *((_QWORD *)v21 + 1) = 0;
      }
    }
  }
  *((_DWORD *)this + 67) = 5;
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v15, UserAccount_SettingsPage_DataRendering, v16, 1, ppStm);
  v50 = ((__int64 (__fastcall *)(IUnknown *, LPUNKNOWN, LPUNKNOWN, __int64, int))(*v14)->lpVtbl[1].QueryInterface)(
          *v14,
          pUnk,
          v64,
          1,
          1);
  NonElevatedObjects = v50;
  if ( v50 < 0 )
  {
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v52, v51, L"CUserManager sync initialization", (unsigned int)v50);
  }
  else
  {
    CUAMSettingsPageElement::_DisplayPageData((struct IUserManager **)this, 0);
  }
  *((_DWORD *)this + 67) = 6;
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v52, UserAccount_SettingsPage_DataRendered, v53, 1, ppStm);
LABEL_82:
  v54 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v55 = v54;
  if ( v54 )
  {
    v56 = Microsoft::WRL::Details::ModuleBase::module_;
    v54[3] = 1;
    *(_QWORD *)v54 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDuiBehavior>::`vftable';
    if ( v56 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v56 + 8LL))(v56);
    *(_QWORD *)v55 = &CTapAnimationPressedBehavior::`vftable';
    v57 = StrToID(L"idAddUserButton");
    v58 = DirectUI::Element::FindDescendent(this, v57);
    (*(void (__fastcall **)(struct DirectUI::Element *, _DWORD *))(*(_QWORD *)v58 + 176LL))(v58, v55);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v55 + 16LL))(v55);
  }
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
LABEL_93:
  CUserCplInitializer::s_CleanInnerObjectArray(
    (struct INNER_OBJ_INFO *const)&`CUAMSettingsPageElement::InitializePageElement'::`2'::s_rgInnerObjects,
    1u);
  v9 = v64;
  if ( v64 )
  {
    v64 = 0;
    ((void (__fastcall *)(LPUNKNOWN))v9->lpVtbl->Release)(v9);
  }
  if ( NonElevatedObjects < 0 )
  {
LABEL_96:
    if ( (Microsoft_Windows_User_ControlPanelEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"InitializePageElement", (unsigned int)NonElevatedObjects);
  }
  return (unsigned int)NonElevatedObjects;
}

```

## disassembly

```asm
0x180026934  mov     rax, rsp
0x180026937  push    rbp
0x180026938  push    rbx
0x180026939  push    rsi
0x18002693a  push    rdi
0x18002693b  push    r12
0x18002693d  push    r13
0x18002693f  push    r14
0x180026941  push    r15
0x180026943  lea     rbp, [rax-5Fh]
0x180026947  sub     rsp, 98h
0x18002694e  movaps  xmmword ptr [rax-58h], xmm6
0x180026952  mov     rax, cs:__security_cookie
0x180026959  xor     rax, rsp
0x18002695c  mov     qword ptr [rbp+57h+var_58], rax
0x180026960  lea     rbx, [rcx+0F0h]
0x180026967  mov     rdi, rcx
0x18002696a  lea     rcx, aIdpageloadprog; "idPageLoadProgress"
0x180026971  mov     [rbx], rdx
0x180026974  call    cs:__imp_StrToID
0x18002697a  movzx   edx, ax
0x18002697d  mov     rcx, rdi
0x180026980  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180026986  lea     rcx, aIdpageloadprog_0; "idPageLoadProgressRing"
0x18002698d  mov     [rdi+120h], rax
0x180026994  call    cs:__imp_StrToID
0x18002699a  movzx   edx, ax
0x18002699d  mov     rcx, rdi
0x1800269a0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800269a6  mov     ecx, cs:_tls_index
0x1800269ac  xor     r13d, r13d
0x1800269af  mov     [rdi+128h], rax
0x1800269b6  mov     rax, gs:58h
0x1800269bf  mov     edx, 4
0x1800269c4  mov     rax, [rax+rcx*8]
0x1800269c8  mov     eax, [rdx+rax]
0x1800269cb  cmp     cs:?$TSS0@?1??InitializePageElement@CUAMSettingsPageElement@@QEAAJPEAUHWND__@@@Z@4HA, eax
0x1800269d1  jg      loc_1800270C7
0x1800269d7  mov     edx, 1; unsigned __int64
0x1800269dc  lea     rcx, ?s_rgInnerObjects@?1??InitializePageElement@CUAMSettingsPageElement@@QEAAJPEAUHWND__@@@Z@4PAUINNER_OBJ_INFO@@A; struct INNER_OBJ_INFO *
0x1800269e3  call    ?s_CreateNonElevatedObjects@CUserCplInitializer@@SAJQEAUINNER_OBJ_INFO@@_K@Z; CUserCplInitializer::s_CreateNonElevatedObjects(INNER_OBJ_INFO * const,unsigned __int64)
0x1800269e8  mov     r14d, eax
0x1800269eb  test    eax, eax
0x1800269ed  js      loc_180027084
0x1800269f3  lea     rcx, [rbp+57h+var_78]
0x1800269f7  mov     [rbp+57h+var_78], r13
0x1800269fb  call    ??$MakeAndInitializeOnSharedSTAThread@VCLogonEnumUsers@@UILogonEnumUsers@@$$V@ComTaskPool@Internal@Windows@@SAJPEAPEAUILogonEnumUsers@@@Z; Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<CLogonEnumUsers,ILogonEnumUsers,>(ILogonEnumUsers * *)
0x180026a00  mov     r14d, eax
0x180026a03  test    eax, eax
0x180026a05  js      loc_18002703D
0x180026a0b  lea     r12, [rdi+0D8h]
0x180026a12  mov     rdx, rbx
0x180026a15  mov     rcx, r12
0x180026a18  call    ??$MakeAndInitializeOnSharedSTAThread@VCUserManager@@UIUserManager@@AEAPEAUHWND__@@@ComTaskPool@Internal@Windows@@SAJPEAPEAUIUserManager@@AEAPEAUHWND__@@@Z; Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<CUserManager,IUserManager,HWND__ * &>(IUserManager * *,HWND__ * &)
0x180026a1d  mov     r14d, eax
0x180026a20  test    eax, eax
0x180026a22  js      loc_18002702B
0x180026a28  mov     [rdi+0E8h], r13b
0x180026a2f  mov     rcx, cs:qword_1800A3458
0x180026a36  mov     [rbp+57h+pUnk], r13
0x180026a3a  test    rcx, rcx
0x180026a3d  jz      short loc_180026A55
0x180026a3f  mov     rax, [rcx]
0x180026a42  lea     r8, [rbp+57h+pUnk]
0x180026a46  lea     rdx, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461
0x180026a4d  mov     rax, [rax]
0x180026a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a55  mov     rax, rdi
0x180026a58  lea     r15, [rdi+0D0h]
0x180026a5f  neg     rax
0x180026a62  lea     rcx, [rdi+0C8h]
0x180026a69  mov     rdx, r15; struct CPrivateNotificationWindow **
0x180026a6c  sbb     r8, r8
0x180026a6f  and     rcx, r8; struct CPrivateNotificationWindowSink *
0x180026a72  call    ?CreateInstance@CPrivateNotificationWindow@@SAJPEAVCPrivateNotificationWindowSink@@PEAPEAV1@@Z; CPrivateNotificationWindow::CreateInstance(CPrivateNotificationWindowSink *,CPrivateNotificationWindow * *)
0x180026a77  test    eax, eax
0x180026a79  js      loc_180026EDB
0x180026a7f  movss   xmm6, cs:__real@3e4ccccd
0x180026a87  lea     rax, [rbp+57h+pcbData]
0x180026a8b  mov     [rsp+30h], rax; pcbData
0x180026a90  lea     r8, Value; "ProgressDelay"
0x180026a97  lea     rax, [rbp+57h+var_88]
0x180026a9b  mov     [rbp+57h+var_88], r13d
0x180026a9f  mov     [rsp+0D0h+pvData], rax; pvData
0x180026aa4  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180026aab  mov     r9d, 10h; dwFlags
0x180026ab1  mov     [rsp+0D0h+pdwType], r13; pdwType
0x180026ab6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180026abd  mov     [rbp+57h+pcbData], 4
0x180026ac4  call    cs:__imp_RegGetValueW
0x180026aca  test    eax, eax
0x180026acc  jle     short loc_180026AD8
0x180026ace  movzx   eax, ax
0x180026ad1  or      eax, 80070000h
0x180026ad6  test    eax, eax
0x180026ad8  js      short loc_180026AED
0x180026ada  mov     eax, [rbp+57h+var_88]
0x180026add  xorps   xmm6, xmm6
0x180026ae0  cvtsi2ss xmm6, rax
0x180026ae5  divss   xmm6, cs:__real@447a0000
0x180026aed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026af4  mov     ecx, 18h; unsigned __int64
0x180026af9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026afe  mov     rbx, rax
0x180026b01  test    rax, rax
0x180026b04  jz      short loc_180026B18
0x180026b06  movss   dword ptr [rax+10h], xmm6
0x180026b0b  mov     [rax], r13
0x180026b0e  mov     [rax+8], r13
0x180026b12  mov     [rax+14h], r13d
0x180026b16  jmp     short loc_180026B1B
0x180026b18  mov     rbx, r13
0x180026b1b  mov     rsi, [rdi+110h]
0x180026b22  mov     [rdi+110h], r13
0x180026b29  test    rsi, rsi
0x180026b2c  jz      short loc_180026B61
0x180026b2e  mov     rcx, [rsi]
0x180026b31  test    rcx, rcx
0x180026b34  jz      short loc_180026B3F
0x180026b36  call    cs:__imp_DeleteHandle
0x180026b3c  mov     [rsi], r13
0x180026b3f  mov     rcx, [rsi+8]
0x180026b43  test    rcx, rcx
0x180026b46  jz      short loc_180026B59
0x180026b48  mov     rax, [rcx]
0x180026b4b  mov     edx, 1
0x180026b50  mov     rax, [rax+8]
0x180026b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b59  mov     rcx, rsi; lpMem
0x180026b5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026b61  mov     [rdi+110h], rbx
0x180026b68  test    rbx, rbx
0x180026b6b  jz      loc_180026EDB
0x180026b71  mov     rcx, [rbx+8]
0x180026b75  test    rcx, rcx
0x180026b78  jz      short loc_180026B8B
0x180026b7a  mov     rax, [rcx]
0x180026b7d  mov     edx, 1
0x180026b82  mov     rax, [rax+8]
0x180026b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026b92  mov     ecx, 10h; unsigned __int64
0x180026b97  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026b9c  test    rax, rax
0x180026b9f  jz      loc_180026ED7
0x180026ba5  movss   xmm6, cs:__real@3f4ccccd
0x180026bad  lea     rcx, ??_7?$InvokeHelper@V_lambda_ca5ba48ff2b3b5e9ee8d832ebbd16844_@@@SimpleTimer@DirectUI@@6B@; const DirectUI::SimpleTimer::InvokeHelper<_lambda_ca5ba48ff2b3b5e9ee8d832ebbd16844_>::`vftable'
0x180026bb4  mov     [rax], rcx
0x180026bb7  lea     r8, aProgressmin; "ProgressMin"
0x180026bbe  mov     [rax+8], rdi
0x180026bc2  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180026bc9  mov     [rbx+8], rax
0x180026bcd  mov     r9d, 10h; dwFlags
0x180026bd3  lea     rax, [rbp+57h+pcbData]
0x180026bd7  mov     [rbp+57h+pcbData], 4
0x180026bde  mov     [rsp+30h], rax; pcbData
0x180026be3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180026bea  lea     rax, [rbp+57h+var_88]
0x180026bee  mov     [rsp+0D0h+pvData], rax; pvData
0x180026bf3  mov     [rsp+0D0h+pdwType], r13; pdwType
0x180026bf8  call    cs:__imp_RegGetValueW
0x180026bfe  test    eax, eax
0x180026c00  jle     short loc_180026C0C
0x180026c02  movzx   eax, ax
0x180026c05  or      eax, 80070000h
0x180026c0a  test    eax, eax
0x180026c0c  js      short loc_180026C21
0x180026c0e  mov     eax, [rbp+57h+var_88]
0x180026c11  xorps   xmm6, xmm6
0x180026c14  cvtsi2ss xmm6, rax
0x180026c19  divss   xmm6, cs:__real@447a0000
0x180026c21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026c28  mov     ecx, 18h; unsigned __int64
0x180026c2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026c32  mov     rbx, rax
0x180026c35  test    rax, rax
0x180026c38  jz      short loc_180026C4C
0x180026c3a  movss   dword ptr [rax+10h], xmm6
0x180026c3f  mov     [rax], r13
0x180026c42  mov     [rax+8], r13
0x180026c46  mov     [rax+14h], r13d
0x180026c4a  jmp     short loc_180026C4F
0x180026c4c  mov     rbx, r13
0x180026c4f  mov     rsi, [rdi+118h]
0x180026c56  mov     [rdi+118h], r13
0x180026c5d  test    rsi, rsi
0x180026c60  jz      short loc_180026C95
0x180026c62  mov     rcx, [rsi]
0x180026c65  test    rcx, rcx
0x180026c68  jz      short loc_180026C73
0x180026c6a  call    cs:__imp_DeleteHandle
0x180026c70  mov     [rsi], r13
0x180026c73  mov     rcx, [rsi+8]
0x180026c77  test    rcx, rcx
0x180026c7a  jz      short loc_180026C8D
0x180026c7c  mov     rax, [rcx]
0x180026c7f  mov     edx, 1
0x180026c84  mov     rax, [rax+8]
0x180026c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c8d  mov     rcx, rsi; lpMem
0x180026c90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026c95  mov     [rdi+118h], rbx
0x180026c9c  test    rbx, rbx
0x180026c9f  jz      loc_180026EDB
0x180026ca5  mov     rcx, [rbx+8]
0x180026ca9  test    rcx, rcx
0x180026cac  jz      short loc_180026CBF
0x180026cae  mov     rax, [rcx]
0x180026cb1  mov     edx, 1
0x180026cb6  mov     rax, [rax+8]
0x180026cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cbf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026cc6  mov     ecx, 10h; unsigned __int64
0x180026ccb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026cd0  test    rax, rax
0x180026cd3  jz      short loc_180026CE5
0x180026cd5  lea     rcx, ??_7?$InvokeHelper@V_lambda_fa9aee1af039da89e2ab577eed5b0cd0_@@@SimpleTimer@DirectUI@@6B@; const DirectUI::SimpleTimer::InvokeHelper<_lambda_fa9aee1af039da89e2ab577eed5b0cd0_>::`vftable'
0x180026cdc  mov     [rax+8], rdi
0x180026ce0  mov     [rax], rcx
0x180026ce3  jmp     short loc_180026CE8
0x180026ce5  mov     rax, r13
0x180026ce8  mov     [rbx+8], rax
0x180026cec  test    rax, rax
0x180026cef  jz      loc_180026EDB
0x180026cf5  mov     rdx, [r12]; pUnk
0x180026cf9  lea     r8, [rbp+57h+ppStm]; ppStm
0x180026cfd  lea     rcx, _GUID_73aecad8_7e70_4e21_8767_82b03c862455; riid
0x180026d04  mov     [rbp+57h+ppStm], r13
0x180026d08  mov     [rbp+57h+var_80], r13
0x180026d0c  mov     qword ptr [rbp+57h+pcbData], r13
0x180026d10  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180026d16  mov     ebx, eax
0x180026d18  test    eax, eax
0x180026d1a  js      loc_180026E82
0x180026d20  mov     rcx, [rbp+57h+var_80]
0x180026d24  test    rcx, rcx
0x180026d27  jz      short loc_180026D39
0x180026d29  mov     [rbp+57h+var_80], r13
0x180026d2d  mov     rax, [rcx]
0x180026d30  mov     rax, [rax+10h]
0x180026d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d39  mov     rdx, [rbp+57h+pUnk]; pUnk
0x180026d3d  lea     r8, [rbp+57h+var_80]; ppStm
0x180026d41  lea     rcx, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461; riid
0x180026d48  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180026d4e  mov     ebx, eax
0x180026d50  test    eax, eax
0x180026d52  js      loc_180026E82
0x180026d58  mov     rcx, qword ptr [rbp+57h+pcbData]
0x180026d5c  test    rcx, rcx
0x180026d5f  jz      short loc_180026D71
0x180026d61  mov     qword ptr [rbp+57h+pcbData], r13
0x180026d65  mov     rax, [rcx]
0x180026d68  mov     rax, [rax+10h]
0x180026d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d71  mov     rdx, [rbp+57h+var_78]; pUnk
0x180026d75  lea     r8, [rbp+57h+pcbData]; ppStm
0x180026d79  lea     rcx, _GUID_3ee328ab_8f69_420a_9b86_7080f22af38b; riid
0x180026d80  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180026d86  mov     ebx, eax
0x180026d88  test    eax, eax
0x180026d8a  js      loc_180026E82
0x180026d90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026d97  mov     ecx, 28h ; '('; unsigned __int64
0x180026d9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026da1  mov     rsi, rax
0x180026da4  test    rax, rax
0x180026da7  jz      loc_180026E7D
0x180026dad  mov     r8, qword ptr [rbp+57h+pcbData]
0x180026db1  lea     r9, ??_7CUserMgrInitializationData@@6B@; const CUserMgrInitializationData::`vftable'
0x180026db8  mov     rcx, [rbp+57h+var_80]
0x180026dbc  mov     rax, [rbp+57h+ppStm]
0x180026dc0  mov     rdx, [r15]
0x180026dc3  mov     [rsi], r9
0x180026dc6  mov     [rsi+8], rdx
0x180026dca  mov     [rsi+10h], rax
0x180026dce  mov     [rsi+18h], rcx
0x180026dd2  mov     [rsi+20h], r8
0x180026dd6  lock inc dword ptr [rdx+8]
0x180026dda  mov     rcx, [rsi+10h]
0x180026dde  mov     rax, [rcx]
0x180026de1  mov     rax, [rax+8]
0x180026de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dea  mov     rcx, [rsi+18h]
0x180026dee  test    rcx, rcx
0x180026df1  jz      short loc_180026DFF
0x180026df3  mov     rax, [rcx]
0x180026df6  mov     rax, [rax+8]
0x180026dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dff  mov     rcx, [rsi+20h]
0x180026e03  test    rcx, rcx
0x180026e06  jz      short loc_180026E14
0x180026e08  mov     rax, [rcx]
0x180026e0b  mov     rax, [rax+8]
0x180026e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e14  xor     r9d, r9d; pfnCallback
0x180026e17  lea     rcx, ?InitializeUserManagerAsync@@YAKPEAX@Z; pfnThreadProc
0x180026e1e  mov     rdx, rsi; pData
0x180026e21  lea     r8d, [r9+0Ch]; flags
0x180026e25  call    cs:__imp_SHCreateThread
  ... truncated ...
```
