# Windows::UI::Core::CDispatcher::EnqueueAsyncWork(long (*)(uint,Windows::UI::Core::ICoreAsyncInfo * *),Windows::UI::Core::CoreDispatcherPriority,Windows::UI::Core::IDispatchedHandler *,Windows::UI::Core::IIdleDispatchedHandler *,Windows::UI::Core::ICoreAsyncInfo * *)

- ea: `0x180009260`
- end: `0x180009c75`
- name: `?EnqueueAsyncWork@CDispatcher@Core@UI@Windows@@AEAAJP6AJIPEAPEAUICoreAsyncInfo@234@@ZW4CoreDispatcherPriority@234@PEAUIDispatchedHandler@234@PEAUIIdleDispatchedHandler@234@0@Z`
- size: `2581`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008670`
- `0x1800088e0`
- `0x180008c60`
- `0x180008f70`

## callees

- `0x180009260`
- `0x1800127ec`
- `0x180012858`
- `0x180056d3c`
- `0x18005f1a4`
- `0x180071c60`
- `0x18008a5b0`
- `0x18008aa80`
- `0x18008ab6c`
- `0x18008abdc`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009522`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009522`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009512`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000949d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000949d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009398`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009398`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180009702`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180009702`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 Windows::UI::Core::CDispatcher::EnqueueAsyncWork(
        __int64 a1,
        __int64 (__fastcall *a2)(__int64, __int64 *),
        int a3,
        _QWORD *a4,
        ...)
{
  _QWORD *v4; // r13
  IUnknown *v8; // r12
  int v9; // eax
  unsigned __int16 v10; // r8
  __int64 v11; // rcx
  int Error; // r14d
  _OWORD *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 **v17; // rcx
  int v18; // edx
  __int64 *i; // rax
  int v20; // ecx
  IUnknown *v21; // rax
  IUnknown *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // rcx
  __int64 v27; // r12
  __int64 v28; // r14
  _QWORD *v29; // rdi
  IUnknown *v30; // r13
  _QWORD *v31; // rax
  _QWORD *v32; // rbx
  LPUNKNOWN v33; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  __int64 v35; // rcx
  LPUNKNOWN v36; // rcx
  unsigned int v37; // edi
  int v38; // eax
  LPUNKNOWN v39; // rax
  LPUNKNOWN v40; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v42; // r8
  DWORD v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  unsigned __int16 v46; // r8
  unsigned __int16 v47; // r8
  __int64 v48; // [rsp+28h] [rbp-71h]
  __int64 v49; // [rsp+30h] [rbp-69h]
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp-59h] BYREF
  __int64 v51; // [rsp+48h] [rbp-51h] BYREF
  __int64 v52; // [rsp+50h] [rbp-49h] BYREF
  _QWORD *v53; // [rsp+58h] [rbp-41h]
  HRESULT (__stdcall *v54)(IUnknown *, const IID *const, void **); // [rsp+60h] [rbp-39h]
  _QWORD *v55; // [rsp+68h] [rbp-31h]
  IUnknown *v56; // [rsp+70h] [rbp-29h]
  __int64 v57; // [rsp+78h] [rbp-21h]
  char v58; // [rsp+80h] [rbp-19h] BYREF
  char v59; // [rsp+88h] [rbp-11h] BYREF
  char v60; // [rsp+90h] [rbp-9h] BYREF
  char v61; // [rsp+98h] [rbp-1h] BYREF
  char v62; // [rsp+100h] [rbp+67h] BYREF
  _QWORD *v63; // [rsp+108h] [rbp+6Fh]
  IUnknown *v64; // [rsp+110h] [rbp+77h] BYREF
  va_list va; // [rsp+110h] [rbp+77h]
  LPUNKNOWN *v66; // [rsp+118h] [rbp+7Fh]
  va_list va1; // [rsp+120h] [rbp+87h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v64 = va_arg(va1, IUnknown *);
  v66 = va_arg(va1, LPUNKNOWN *);
  v63 = a4;
  v4 = a4;
  *v66 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v42, a1, *(_DWORD *)(a1 + 120), a3, CurrentThreadId);
  }
  v52 = 0;
  v55 = v4;
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
  v8 = v64;
  v56 = v64;
  if ( v64 )
    ((void (__fastcall *)(IUnknown *))v64->lpVtbl->AddRef)(v64);
  if ( a3 == -2 )
    v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v8->lpVtbl->QueryInterface)(
           v8,
           &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90,
           &v52);
  else
    v9 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v4)(
           v4,
           &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90,
           &v52);
  if ( v9 >= 0 )
  {
    v51 = 0;
    v11 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 180));
    if ( !(_DWORD)v11 )
      v11 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 180));
    Error = a2(v11, &v51);
    if ( Error < 0 )
      goto LABEL_45;
    if ( !*(_BYTE *)(a1 + 800) )
    {
      v13 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      if ( v13 )
      {
        *v13 = 0;
        v13[1] = 0;
        *((_QWORD *)v13 + 4) = 0;
        *((_DWORD *)v13 + 3) = a3;
        *((_DWORD *)v13 + 2) = GetTickCount();
        if ( *((_QWORD **)v13 + 2) != v4 )
        {
          if ( v4 )
            (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
          v14 = *((_QWORD *)v13 + 2);
          *((_QWORD *)v13 + 2) = v4;
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        if ( *((IUnknown **)v13 + 3) != v8 )
        {
          if ( v8 )
            ((void (__fastcall *)(IUnknown *))v8->lpVtbl->AddRef)(v8);
          v26 = *((_QWORD *)v13 + 3);
          *((_QWORD *)v13 + 3) = v8;
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v15 = v51;
        if ( *((_QWORD *)v13 + 4) != v51 )
        {
          if ( v51 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
          v16 = *((_QWORD *)v13 + 4);
          *((_QWORD *)v13 + 4) = v15;
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v15 = v51;
        }
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v15 + 48LL))(v15, 0, 1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v43 = GetCurrentThreadId();
          WPP_SF_qDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, v45, a1, *(_DWORD *)(a1 + 120), v13, v43);
        }
        v64 = 0;
        Error = (**(__int64 (__fastcall ***)(__int64, GUID *, IUnknown **))v51)(
                  v51,
                  &GUID_a5122520_cdcf_4732_aa55_2b72eca3875c,
                  (IUnknown **)va);
        if ( Error >= 0 )
        {
          Error = ((__int64 (__fastcall *)(IUnknown *))v64->lpVtbl[3].AddRef)(v64);
          if ( Error >= 0 )
          {
            AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
            v17 = *(__int64 ***)(a1 + 160);
            if ( v17 && (v18 = *((_DWORD *)v13 + 3), v18 <= *((_DWORD *)v17 + 3)) )
            {
              for ( i = *v17; i; i = (__int64 *)*i )
              {
                if ( v18 > *((_DWORD *)i + 3) )
                  break;
                v17 = (__int64 **)i;
              }
              *(_QWORD *)v13 = *v17;
              *v17 = (__int64 *)v13;
              v20 = ++*(_DWORD *)(a1 + 176);
            }
            else
            {
              *(_QWORD *)v13 = v17;
              *(_QWORD *)(a1 + 160) = v13;
              v20 = ++*(_DWORD *)(a1 + 176);
              if ( !*((_DWORD *)v13 + 3) )
                *(_DWORD *)(a1 + 184) = *((_DWORD *)v13 + 2);
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              LODWORD(v49) = v20;
              WPP_SF_qDqd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
                a1,
                *(_DWORD *)(a1 + 120),
                v13,
                v49);
            }
            if ( a1 != -168 )
              ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
            Error = 0;
            if ( !SetEvent(*(HANDLE *)(a1 + 776)) )
              Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              ((void (__fastcall *)(IUnknown *, __int64, __int64))v64->lpVtbl[2].QueryInterface)(v64, 1, 5);
              ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))v64->lpVtbl[2].AddRef)(v64, (unsigned int)Error, 0);
              Windows::UI::Core::CDispatcher::RemoveInvokeItem(
                (Windows::UI::Core::CDispatcher *)a1,
                (struct Windows::UI::Core::_InvokeEntry *)v13);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LODWORD(v48) = Error;
                WPP_SF_qDD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
                  a1,
                  *(_DWORD *)(a1 + 120),
                  v48);
              }
              Windows::UI::Core::OriginateError((Windows::UI::Core *)(unsigned int)Error, 1012, v47);
            }
            else
            {
              v21 = v64;
              v64 = 0;
              *v66 = v21;
            }
          }
        }
        v22 = v64;
        if ( v64 )
        {
          v64 = 0;
          ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
        }
      }
      else
      {
        Error = -2147024882;
      }
LABEL_45:
      v23 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      goto LABEL_47;
    }
    v57 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v27 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v28 = v51;
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
    v29 = v4;
    v53 = v4;
    if ( v4 )
      (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    v30 = v64;
    if ( v64 )
      ((void (__fastcall *)(IUnknown *))v64->lpVtbl->AddRef)(v64);
    v31 = operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
    v32 = v31;
    if ( v31 )
    {
      v31[1] = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      v31[4] = 0;
      ppunkMarshal = 0;
      if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
      {
        v33 = ppunkMarshal;
        QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
        v54 = QueryInterface;
        v35 = v32[4];
        if ( v35 )
        {
          v32[4] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          QueryInterface = v54;
        }
        ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
          v33,
          &GUID_00000003_0000_0000_c000_000000000046,
          v32 + 4);
        v29 = v53;
      }
      v36 = ppunkMarshal;
      if ( ppunkMarshal )
      {
        ppunkMarshal = 0;
        ((void (__fastcall *)(LPUNKNOWN))v36->lpVtbl->Release)(v36);
      }
      *((_DWORD *)v32 + 15) = 1;
      *v32 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::`vftable'{for `Windows::System::IDispatcherQueueHandler'};
      v32[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      v32[8] = 0;
      if ( v32 + 8 == (_QWORD *)&v58 )
      {
        v27 = a1;
      }
      else
      {
        v32[8] = a1;
        v27 = 0;
      }
      v32[9] = 0;
      if ( v32 + 9 != (_QWORD *)&v59 )
      {
        v32[9] = v28;
        v28 = 0;
      }
      v32[10] = 0;
      if ( v32 + 10 != (_QWORD *)&v60 )
      {
        v32[10] = v63;
        v29 = 0;
      }
      v32[11] = 0;
      if ( v32 + 11 != (_QWORD *)&v61 )
      {
        v32[11] = v64;
        v30 = 0;
      }
      *((_DWORD *)v32 + 24) = a3;
      *v32 = off_1800CF0A0;
      v32[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    }
    else
    {
      v32 = 0;
    }
    v53 = v32;
    if ( v30 )
      ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
    if ( v29 )
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v62 = 0;
    if ( (unsigned int)(a3 + 2) <= 1 )
    {
      v37 = -10;
    }
    else if ( a3 )
    {
      if ( a3 != 1 )
      {
        Error = -2147418113;
LABEL_105:
        if ( v32 )
          (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
        v4 = v63;
        v8 = v64;
        goto LABEL_45;
      }
      v37 = 10;
    }
    else
    {
      v37 = 0;
    }
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v51 + 48LL))(v51, 0, 1);
    ppunkMarshal = 0;
    Error = (**(__int64 (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))v51)(
              v51,
              &GUID_a5122520_cdcf_4732_aa55_2b72eca3875c,
              &ppunkMarshal);
    if ( Error >= 0 )
    {
      Error = ((__int64 (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl[3].AddRef)(ppunkMarshal);
      if ( Error >= 0 )
      {
        v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, char *))(**(_QWORD **)(a1 + 784) + 64LL))(
                *(_QWORD *)(a1 + 784),
                v37,
                v32,
                &v62);
        Error = v38;
        if ( v62 )
        {
          if ( v38 >= 0 )
          {
            v39 = ppunkMarshal;
            ppunkMarshal = 0;
            *v66 = v39;
            goto LABEL_103;
          }
        }
        else
        {
          Error = -2147467259;
        }
        ((void (__fastcall *)(LPUNKNOWN, __int64, __int64))ppunkMarshal->lpVtbl[2].QueryInterface)(ppunkMarshal, 1, 5);
        ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD))ppunkMarshal->lpVtbl[2].AddRef)(
          ppunkMarshal,
          (unsigned int)Error,
          0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LODWORD(v48) = Error;
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
            a1,
            *(_DWORD *)(a1 + 120),
            v48);
        }
        Windows::UI::Core::OriginateError((Windows::UI::Core *)(unsigned int)Error, 1012, v46);
      }
    }
LABEL_103:
    v40 = ppunkMarshal;
    if ( ppunkMarshal )
    {
      ppunkMarshal = 0;
      ((void (__fastcall *)(LPUNKNOWN))v40->lpVtbl->Release)(v40);
    }
    goto LABEL_105;
  }
  Error = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_dc6e14072aed37fd872e19d675f14eb7_Traceguids,
      a1,
      *(_DWORD *)(a1 + 120));
  }
  Windows::UI::Core::OriginateError((Windows::UI::Core *)0x80070057LL, 1009, v10);
LABEL_47:
  if ( v8 )
    ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  v24 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180009260  mov     [rsp-8+arg_0], rbx
0x180009265  mov     [rsp-8+arg_18], r9
0x18000926a  push    rbp
0x18000926b  push    rsi
0x18000926c  push    rdi
0x18000926d  push    r12
0x18000926f  push    r13
0x180009271  push    r14
0x180009273  push    r15
0x180009275  lea     rbp, [rsp-17h]
0x18000927a  sub     rsp, 0B0h
0x180009281  mov     r13, r9
0x180009284  mov     r15d, r8d
0x180009287  mov     rdi, rdx
0x18000928a  mov     rsi, rcx
0x18000928d  xor     r14d, r14d
0x180009290  mov     rax, [rbp+47h+arg_28]
0x180009294  mov     [rax], r14
0x180009297  lea     rcx, WPP_GLOBAL_Control
0x18000929e  mov     rax, cs:WPP_GLOBAL_Control
0x1800092a5  cmp     rax, rcx
0x1800092a8  jnz     loc_180009980
0x1800092ae  mov     rcx, r14
0x1800092b1  mov     [rbp+47h+var_90], rcx
0x1800092b5  mov     [rbp+47h+var_78], r13
0x1800092b9  test    r13, r13
0x1800092bc  jz      short loc_1800092D2
0x1800092be  mov     rax, [r13+0]
0x1800092c2  mov     rcx, r13
0x1800092c5  mov     rax, [rax+8]
0x1800092c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ce  mov     rcx, [rbp+47h+var_90]
0x1800092d2  mov     r12, [rbp+47h+arg_20]
0x1800092d6  mov     [rbp+47h+var_70], r12
0x1800092da  test    r12, r12
0x1800092dd  jnz     loc_1800095E0
0x1800092e3  cmp     r15d, 0FFFFFFFEh
0x1800092e7  jz      loc_180009A3C
0x1800092ed  mov     rax, [r13+0]
0x1800092f1  mov     rbx, [rax]
0x1800092f4  test    rcx, rcx
0x1800092f7  jz      short loc_18000930A
0x1800092f9  mov     [rbp+47h+var_90], r14
0x1800092fd  mov     rdx, [rcx]
0x180009300  mov     rax, [rdx+10h]
0x180009304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009309  nop
0x18000930a  lea     r8, [rbp+47h+var_90]
0x18000930e  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180009315  mov     rcx, r13
0x180009318  mov     rax, rbx
0x18000931b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009320  nop
0x180009321  test    eax, eax
0x180009323  js      loc_180009C1B
0x180009329  mov     [rbp+47h+var_98], r14
0x18000932d  mov     ecx, 1
0x180009332  lock xadd [rsi+0B4h], ecx
0x18000933a  add     ecx, 1
0x18000933d  jz      loc_180009A88
0x180009343  lea     rdx, [rbp+47h+var_98]
0x180009347  mov     rax, rdi
0x18000934a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934f  mov     r14d, eax
0x180009352  test    eax, eax
0x180009354  js      loc_18000962D
0x18000935a  cmp     byte ptr [rsi+320h], 0
0x180009361  jnz     loc_18000965D
0x180009367  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000936e  mov     ecx, 28h ; '('; unsigned __int64
0x180009373  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009378  mov     rdi, rax
0x18000937b  test    rax, rax
0x18000937e  jz      loc_180009627
0x180009384  xorps   xmm0, xmm0
0x180009387  xor     eax, eax
0x180009389  movups  xmmword ptr [rdi], xmm0
0x18000938c  movups  xmmword ptr [rdi+10h], xmm0
0x180009390  mov     [rdi+20h], rax
0x180009394  mov     [rdi+0Ch], r15d
0x180009398  call    cs:__imp_GetTickCount
0x18000939e  mov     [rdi+8], eax
0x1800093a1  cmp     [rdi+10h], r13
0x1800093a5  jz      short loc_1800093D7
0x1800093a7  test    r13, r13
0x1800093aa  jz      short loc_1800093BD
0x1800093ac  mov     rax, [r13+0]
0x1800093b0  mov     rcx, r13
0x1800093b3  mov     rax, [rax+8]
0x1800093b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093bc  nop
0x1800093bd  mov     rcx, [rdi+10h]
0x1800093c1  mov     [rdi+10h], r13
0x1800093c5  test    rcx, rcx
0x1800093c8  jz      short loc_1800093D7
0x1800093ca  mov     rax, [rcx]
0x1800093cd  mov     rax, [rax+10h]
0x1800093d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d6  nop
0x1800093d7  cmp     [rdi+18h], r12
0x1800093db  jnz     loc_180009635
0x1800093e1  mov     rbx, [rbp+47h+var_98]
0x1800093e5  cmp     [rdi+20h], rbx
0x1800093e9  jz      short loc_18000941E
0x1800093eb  test    rbx, rbx
0x1800093ee  jz      short loc_180009400
0x1800093f0  mov     rax, [rbx]
0x1800093f3  mov     rcx, rbx
0x1800093f6  mov     rax, [rax+8]
0x1800093fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ff  nop
0x180009400  mov     rcx, [rdi+20h]
0x180009404  mov     [rdi+20h], rbx
0x180009408  test    rcx, rcx
0x18000940b  jz      short loc_18000941A
0x18000940d  mov     rax, [rcx]
0x180009410  mov     rax, [rax+10h]
0x180009414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009419  nop
0x18000941a  mov     rbx, [rbp+47h+var_98]
0x18000941e  mov     rax, [rbx]
0x180009421  xor     edx, edx
0x180009423  mov     r8d, 1
0x180009429  mov     rcx, rbx
0x18000942c  mov     rax, [rax+30h]
0x180009430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009435  mov     rax, cs:WPP_GLOBAL_Control
0x18000943c  lea     rdx, WPP_GLOBAL_Control
0x180009443  cmp     rax, rdx
0x180009446  jnz     loc_1800099ED
0x18000944c  xor     r15d, r15d
0x18000944f  mov     [rbp+47h+arg_20], r15
0x180009453  mov     rcx, [rbp+47h+var_98]
0x180009457  mov     rax, [rcx]
0x18000945a  lea     r8, [rbp+47h+arg_20]
0x18000945e  lea     rdx, _GUID_a5122520_cdcf_4732_aa55_2b72eca3875c
0x180009465  mov     rax, [rax]
0x180009468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000946d  mov     r14d, eax
0x180009470  test    eax, eax
0x180009472  js      loc_180009548
0x180009478  mov     rcx, [rbp+47h+arg_20]
0x18000947c  mov     rax, [rcx]
0x18000947f  mov     rax, [rax+50h]
0x180009483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009488  mov     r14d, eax
0x18000948b  test    eax, eax
0x18000948d  js      loc_180009548
0x180009493  lea     rbx, [rsi+0A8h]
0x18000949a  mov     rcx, rbx; SRWLock
0x18000949d  call    cs:__imp_AcquireSRWLockExclusive
0x1800094a3  mov     rcx, [rsi+0A0h]
0x1800094aa  test    rcx, rcx
0x1800094ad  jz      loc_1800095F9
0x1800094b3  mov     edx, [rdi+0Ch]
0x1800094b6  cmp     edx, [rcx+0Ch]
0x1800094b9  jg      loc_1800095F9
0x1800094bf  mov     rax, [rcx]
0x1800094c2  test    rax, rax
0x1800094c5  jz      short loc_1800094D7
0x1800094c7  cmp     edx, [rax+0Ch]
0x1800094ca  jg      short loc_1800094D7
0x1800094cc  mov     rcx, rax
0x1800094cf  mov     rax, [rax]
0x1800094d2  test    rax, rax
0x1800094d5  jnz     short loc_1800094C7
0x1800094d7  mov     rax, [rcx]
0x1800094da  mov     [rdi], rax
0x1800094dd  mov     [rcx], rdi
0x1800094e0  inc     dword ptr [rsi+0B0h]
0x1800094e6  mov     ecx, [rsi+0B0h]
0x1800094ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800094f3  lea     rax, WPP_GLOBAL_Control
0x1800094fa  cmp     r10, rax
0x1800094fd  jz      short loc_18000950A
0x1800094ff  test    byte ptr [r10+1Ch], 4
0x180009504  jnz     loc_180009B45
0x18000950a  test    rbx, rbx
0x18000950d  jz      short loc_180009518
0x18000950f  mov     rcx, rbx; SRWLock
0x180009512  call    cs:__imp_ReleaseSRWLockExclusive
0x180009518  mov     r14d, r15d
0x18000951b  mov     rcx, [rsi+308h]; hEvent
0x180009522  call    cs:__imp_SetEvent
0x180009528  test    eax, eax
0x18000952a  jz      loc_180009B7D
0x180009530  test    r14d, r14d
0x180009533  js      loc_180009B8A
0x180009539  mov     rax, [rbp+47h+arg_20]
0x18000953d  mov     [rbp+47h+arg_20], r15
0x180009541  mov     rcx, [rbp+47h+arg_28]
0x180009545  mov     [rcx], rax
0x180009548  mov     rcx, [rbp+47h+arg_20]
0x18000954c  test    rcx, rcx
0x18000954f  jz      short loc_180009562
0x180009551  mov     [rbp+47h+arg_20], r15
0x180009555  mov     rax, [rcx]
0x180009558  mov     rax, [rax+10h]
0x18000955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009561  nop
0x180009562  mov     rcx, [rbp+47h+var_98]
0x180009566  test    rcx, rcx
0x180009569  jz      short loc_18000957C
0x18000956b  mov     [rbp+47h+var_98], r15
0x18000956f  mov     rax, [rcx]
0x180009572  mov     rax, [rax+10h]
0x180009576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957b  nop
0x18000957c  test    r12, r12
0x18000957f  jz      short loc_180009592
0x180009581  mov     rax, [r12]
0x180009585  mov     rcx, r12
0x180009588  mov     rax, [rax+10h]
0x18000958c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009591  nop
0x180009592  test    r13, r13
0x180009595  jz      short loc_1800095A8
0x180009597  mov     rax, [r13+0]
0x18000959b  mov     rcx, r13
0x18000959e  mov     rax, [rax+10h]
0x1800095a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a7  nop
0x1800095a8  mov     rcx, [rbp+47h+var_90]
0x1800095ac  test    rcx, rcx
0x1800095af  jz      short loc_1800095C2
0x1800095b1  mov     [rbp+47h+var_90], r15
0x1800095b5  mov     rax, [rcx]
0x1800095b8  mov     rax, [rax+10h]
0x1800095bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c1  nop
0x1800095c2  mov     eax, r14d
0x1800095c5  mov     rbx, [rsp+0E0h+arg_0]
0x1800095cd  add     rsp, 0B0h
0x1800095d4  pop     r15
0x1800095d6  pop     r14
0x1800095d8  pop     r13
0x1800095da  pop     r12
0x1800095dc  pop     rdi
0x1800095dd  pop     rsi
0x1800095de  pop     rbp
0x1800095df  retn
0x1800095e0  mov     rax, [r12]
0x1800095e4  mov     rcx, r12
0x1800095e7  mov     rax, [rax+8]
0x1800095eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f0  mov     rcx, [rbp+47h+var_90]
0x1800095f4  jmp     loc_1800092E3
0x1800095f9  mov     [rdi], rcx
0x1800095fc  mov     [rsi+0A0h], rdi
0x180009603  inc     dword ptr [rsi+0B0h]
0x180009609  mov     ecx, [rsi+0B0h]
0x18000960f  cmp     dword ptr [rdi+0Ch], 0
0x180009613  jnz     loc_1800094EC
0x180009619  mov     eax, [rdi+8]
0x18000961c  mov     [rsi+0B8h], eax
0x180009622  jmp     loc_1800094EC
0x180009627  mov     r14d, 8007000Eh
0x18000962d  xor     r15d, r15d
0x180009630  jmp     loc_180009562
0x180009635  test    r12, r12
0x180009638  jnz     loc_1800099C7
0x18000963e  mov     rcx, [rdi+18h]
0x180009642  mov     [rdi+18h], r12
0x180009646  test    rcx, rcx
0x180009649  jz      short loc_180009658
0x18000964b  mov     rax, [rcx]
0x18000964e  mov     rax, [rax+10h]
0x180009652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009657  nop
0x180009658  jmp     loc_1800093E1
0x18000965d  mov     [rbp+47h+var_68], rsi
0x180009661  mov     rax, [rsi]
0x180009664  mov     rcx, rsi
0x180009667  mov     rax, [rax+8]
0x18000966b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009670  nop
0x180009671  mov     r12, rsi
0x180009674  mov     rax, [rsi]
0x180009677  mov     rcx, rsi
0x18000967a  mov     rax, [rax+8]
0x18000967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009683  nop
0x180009684  mov     r14, [rbp+47h+var_98]
0x180009688  test    r14, r14
0x18000968b  jz      short loc_18000969D
0x18000968d  mov     rax, [r14]
0x180009690  mov     rcx, r14
0x180009693  mov     rax, [rax+8]
0x180009697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969c  nop
0x18000969d  mov     rdi, r13
0x1800096a0  mov     [rbp+47h+var_88], r13
0x1800096a4  test    r13, r13
0x1800096a7  jz      short loc_1800096BA
0x1800096a9  mov     rax, [r13+0]
0x1800096ad  mov     rcx, r13
0x1800096b0  mov     rax, [rax+8]
0x1800096b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b9  nop
0x1800096ba  mov     rcx, [rbp+47h+arg_20]
  ... truncated ...
```
