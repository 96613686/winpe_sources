# BtPanHandler::Start(bool)

- ea: `0x180025c88`
- end: `0x180026215`
- name: `?Start@BtPanHandler@@QEAAJ_N@Z`
- size: `1421`
- prototype: `__int64 __fastcall(BtPanHandler *__hidden this, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e4a4`

## callees

- `0x180002590`
- `0x18000299c`
- `0x1800067c8`
- `0x18000a21c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180024180`
- `0x180024a40`
- `0x1800256cc`
- `0x1800256e4`
- `0x180025bfc`
- `0x180025c88`
- `0x18002638c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025d75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025d75`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180025d08`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180025d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025dc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025dfc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025dfc`

## string_xrefs

- `0x180025d6e`: `TetheringService.dll`

## pseudocode

```c
__int64 __fastcall BtPanHandler::Start(BtPanHandler *this, bool a2)
{
  signed int ActivationFactory; // ebx
  TetheringServiceTelemetry *v5; // rcx
  wil::details *v6; // rcx
  HANDLE Event; // rsi
  void *v8; // rbx
  DWORD LastError; // r14d
  BOOL v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  wil::details::in1diag3 *v13; // rcx
  HMODULE Library; // rax
  signed int v15; // eax
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // esi
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v42; // [rsp+20h] [rbp-50h] BYREF
  __int64 v43; // [rsp+28h] [rbp-48h] BYREF
  __int64 v44; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v45; // [rsp+38h] [rbp-38h] BYREF
  int v46; // [rsp+3Ch] [rbp-34h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  ActivationFactory = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 97) )
  {
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      v8 = *(void **)this;
      if ( *(_QWORD *)this )
      {
        LastError = GetLastError();
        v10 = CloseHandle(v8);
        v13 = retaddr;
        if ( !v10 )
          goto LABEL_90;
        SetLastError(LastError);
      }
      *(_QWORD *)this = Event;
    }
    else if ( (int)wil::details::GetLastErrorFailHr(v6) < 0 )
    {
      goto LABEL_14;
    }
    if ( !*((_QWORD *)this + 5) )
    {
      Library = LoadLibraryExW(L"TetheringService.dll", 0, 0x802u);
      *((_QWORD *)this + 5) = Library;
      if ( !Library )
      {
LABEL_14:
        v15 = GetLastError();
        ActivationFactory = v15;
        if ( v15 > 0 )
          ActivationFactory = (unsigned __int16)v15 | 0x80070000;
        if ( ActivationFactory >= 0 )
          goto LABEL_84;
        goto LABEL_47;
      }
    }
    v42 = 0;
    string = 0;
    v16 = WindowsCreateStringReference(L"Windows.Devices.Radios.Radio", 0x1Cu, &hstringHeader, &string);
    if ( v16 >= 0 )
    {
      ActivationFactory = RoGetActivationFactory(string, &GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4, &v42);
      string = 0;
      if ( ActivationFactory >= 0 )
      {
        v43 = 0;
        hstringHeader.Reserved.Reserved1 = &v43;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v42;
        ActivationFactory = wil::ResultFromException__lambda_ab5e9adf3cb0abd65d116aaa87d17a75___(&hstringHeader);
        if ( ActivationFactory >= 0 )
        {
          v45 = 0;
          if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 56LL))(v43, &v45) < 0 )
          {
            v22 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            v23 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            goto LABEL_84;
          }
          v24 = 0;
          if ( v45 )
          {
            while ( 1 )
            {
              v44 = 0;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 48LL))(
                                    v43,
                                    v24,
                                    &v44);
              if ( ActivationFactory < 0 )
                break;
              v46 = 0;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 88LL))(v44, &v46);
              if ( ActivationFactory < 0 )
              {
                v33 = v44;
                if ( v44 )
                {
                  v44 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                }
                v34 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
                v35 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                }
                goto LABEL_47;
              }
              if ( v46 == 3 )
              {
                v28 = v44;
                if ( *((_QWORD *)this + 6) != v44 )
                {
                  if ( v44 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
                  v29 = *((_QWORD *)this + 6);
                  *((_QWORD *)this + 6) = v28;
                  if ( v29 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                }
                v30 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                v31 = v30;
                if ( v30 )
                {
                  *v30 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
                  *((_DWORD *)v30 + 3) = 1;
                  *v30 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Radios::Radio *,IInspectable *>>::`vftable';
                  if ( Microsoft::WRL::Details::ModuleBase::module_ )
                    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
                  v31[2] = this;
                  *v31 = off_180034330;
                }
                else
                {
                  v31 = 0;
                }
                hstringHeader.Reserved.Reserved1 = v31;
                (*(void (__fastcall **)(__int64, _QWORD *, char *))(*(_QWORD *)v44 + 56LL))(v44, v31, (char *)this + 16);
                if ( v31 )
                  (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
                v32 = v44;
                if ( v44 )
                {
                  v44 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
                goto LABEL_42;
              }
              v25 = v44;
              if ( v44 )
              {
                v44 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
              if ( ++v24 >= v45 )
                goto LABEL_42;
            }
            v36 = v44;
            if ( v44 )
            {
              v44 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
            v37 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            }
            v38 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            }
          }
          else
          {
LABEL_42:
            ActivationFactory = BtPanHandler::UpdateBluetoothState(this, a2);
            if ( ActivationFactory >= 0 )
            {
              BtPanHandler::RegisterBTNotification(this);
              *((_BYTE *)this + 97) = 1;
              BtPanHandler::BtInitializeHelper(this);
              v39 = v43;
              if ( v43 )
              {
                v43 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              }
              v40 = v42;
              if ( v42 )
              {
                v42 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              }
              goto LABEL_84;
            }
            v26 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            v27 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
          }
        }
        else
        {
          v20 = v43;
          if ( v43 )
          {
            v43 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v21 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
      }
      else
      {
        v19 = v42;
        if ( v42 )
        {
          v42 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
LABEL_47:
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids,
          (unsigned int)ActivationFactory);
      }
      BtPanHandler::Shutdown(this);
LABEL_84:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_85;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
LABEL_90:
    wil::details::in1diag3::_FailFast_GetLastError(v13, (void *)0xA0B, v11, v12);
  }
LABEL_85:
  if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 27, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids, (unsigned int)ActivationFactory);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180025c88  mov     [rsp-28h+arg_10], rbx
0x180025c8d  mov     [rsp-28h+arg_18], rsi
0x180025c92  push    rbp
0x180025c93  push    rdi
0x180025c94  push    r12
0x180025c96  push    r14
0x180025c98  push    r15
0x180025c9a  mov     rbp, rsp
0x180025c9d  sub     rsp, 70h
0x180025ca1  mov     rax, cs:__security_cookie
0x180025ca8  xor     rax, rsp
0x180025cab  mov     [rbp+var_10], rax
0x180025caf  mov     r15b, dl
0x180025cb2  mov     rdi, rcx
0x180025cb5  xor     r12d, r12d
0x180025cb8  mov     ebx, r12d
0x180025cbb  lea     r14, WPP_GLOBAL_Control
0x180025cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cc9  cmp     rcx, r14
0x180025ccc  jz      short loc_180025CF0
0x180025cce  test    byte ptr [rcx+1Ch], 4
0x180025cd2  jz      short loc_180025CF0
0x180025cd4  lea     edx, [r12+15h]
0x180025cd9  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x180025ce0  mov     rcx, [rcx+10h]
0x180025ce4  call    WPP_SF_
0x180025ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cf0  cmp     [rdi+61h], r12b
0x180025cf4  jnz     loc_1800261B8
0x180025cfa  xor     edx, edx; lpName
0x180025cfc  xor     ecx, ecx; lpEventAttributes
0x180025cfe  mov     r9d, 1F0003h; dwDesiredAccess
0x180025d04  lea     r8d, [rdx+1]; dwFlags
0x180025d08  call    cs:__imp_CreateEventExW
0x180025d0e  mov     rsi, rax
0x180025d11  test    rax, rax
0x180025d14  jnz     short loc_180025D21
0x180025d16  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025d1b  test    eax, eax
0x180025d1d  jns     short loc_180025D60
0x180025d1f  jmp     short loc_180025D84
0x180025d21  call    cs:__imp_GetLastError
0x180025d27  mov     rbx, [rdi]
0x180025d2a  test    rbx, rbx
0x180025d2d  jz      short loc_180025D5D
0x180025d2f  call    cs:__imp_GetLastError
0x180025d35  mov     r14d, eax
0x180025d38  mov     rcx, rbx; hObject
0x180025d3b  call    cs:__imp_CloseHandle
0x180025d41  mov     rcx, [rbp+28h]
0x180025d45  test    eax, eax
0x180025d47  jz      loc_18002620A
0x180025d4d  mov     ecx, r14d; dwErrCode
0x180025d50  call    cs:__imp_SetLastError
0x180025d56  lea     r14, WPP_GLOBAL_Control
0x180025d5d  mov     [rdi], rsi
0x180025d60  cmp     [rdi+28h], r12
0x180025d64  jnz     short loc_180025DA6
0x180025d66  xor     edx, edx; hFile
0x180025d68  mov     r8d, 802h; dwFlags
0x180025d6e  lea     rcx, LibFileName; "TetheringService.dll"
0x180025d75  call    cs:__imp_LoadLibraryExW
0x180025d7b  mov     [rdi+28h], rax
0x180025d7f  test    rax, rax
0x180025d82  jnz     short loc_180025DA6
0x180025d84  call    cs:__imp_GetLastError
0x180025d8a  test    eax, eax
0x180025d8c  mov     ebx, eax
0x180025d8e  jle     short loc_180025D99
0x180025d90  movzx   ebx, ax
0x180025d93  or      ebx, 80070000h
0x180025d99  test    ebx, ebx
0x180025d9b  js      loc_180025FA2
0x180025da1  jmp     loc_1800261B1
0x180025da6  mov     [rbp+var_50], r12
0x180025daa  mov     [rbp+string], r12
0x180025dae  lea     r9, [rbp+string]; string
0x180025db2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180025db6  mov     edx, 1Ch; length
0x180025dbb  lea     rcx, ?RuntimeClass_Windows_Devices_Radios_Radio@@3QBGB; "Windows.Devices.Radios.Radio"
0x180025dc2  call    cs:__imp_WindowsCreateStringReference
0x180025dc8  test    eax, eax
0x180025dca  js      loc_180026202
0x180025dd0  mov     rbx, [rbp+string]
0x180025dd4  mov     rcx, [rbp+var_50]
0x180025dd8  test    rcx, rcx
0x180025ddb  jz      short loc_180025DEE
0x180025ddd  mov     [rbp+var_50], r12
0x180025de1  mov     rax, [rcx]
0x180025de4  mov     rax, [rax+10h]
0x180025de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ded  nop
0x180025dee  lea     r8, [rbp+var_50]
0x180025df2  lea     rdx, _GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4
0x180025df9  mov     rcx, rbx
0x180025dfc  call    cs:__imp_RoGetActivationFactory
0x180025e02  mov     ebx, eax
0x180025e04  mov     [rbp+string], r12
0x180025e08  test    eax, eax
0x180025e0a  jns     short loc_180025E2E
0x180025e0c  mov     rdx, [rbp+var_50]
0x180025e10  test    rdx, rdx
0x180025e13  jz      short loc_180025E29
0x180025e15  mov     [rbp+var_50], r12
0x180025e19  mov     rcx, [rdx]
0x180025e1c  mov     rax, [rcx+10h]
0x180025e20  mov     rcx, rdx
0x180025e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e28  nop
0x180025e29  jmp     loc_180025FA2
0x180025e2e  mov     [rbp+var_48], r12
0x180025e32  lea     rax, [rbp+var_48]
0x180025e36  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180025e3a  lea     rax, [rbp+var_50]
0x180025e3e  mov     qword ptr [rbp+hstringHeader.Reserved+8], rax
0x180025e42  lea     rcx, [rbp+hstringHeader]
0x180025e46  call    wil__ResultFromException__lambda_ab5e9adf3cb0abd65d116aaa87d17a75___
0x180025e4b  mov     ebx, eax
0x180025e4d  test    eax, eax
0x180025e4f  jns     short loc_180025E8A
0x180025e51  mov     rcx, [rbp+var_48]
0x180025e55  test    rcx, rcx
0x180025e58  jz      short loc_180025E6B
0x180025e5a  mov     [rbp+var_48], r12
0x180025e5e  mov     rax, [rcx]
0x180025e61  mov     rax, [rax+10h]
0x180025e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e6a  nop
0x180025e6b  mov     rcx, [rbp+var_50]
0x180025e6f  test    rcx, rcx
0x180025e72  jz      short loc_180025E85
0x180025e74  mov     [rbp+var_50], r12
0x180025e78  mov     rax, [rcx]
0x180025e7b  mov     rax, [rax+10h]
0x180025e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e84  nop
0x180025e85  jmp     loc_180025FA2
0x180025e8a  mov     [rbp+var_38], r12d
0x180025e8e  mov     rcx, [rbp+var_48]
0x180025e92  mov     rax, [rcx]
0x180025e95  lea     rdx, [rbp+var_38]
0x180025e99  mov     rax, [rax+38h]
0x180025e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ea2  test    eax, eax
0x180025ea4  jns     short loc_180025EDF
0x180025ea6  mov     rcx, [rbp+var_48]
0x180025eaa  test    rcx, rcx
0x180025ead  jz      short loc_180025EC0
0x180025eaf  mov     [rbp+var_48], r12
0x180025eb3  mov     rax, [rcx]
0x180025eb6  mov     rax, [rax+10h]
0x180025eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ebf  nop
0x180025ec0  mov     rcx, [rbp+var_50]
0x180025ec4  test    rcx, rcx
0x180025ec7  jz      short loc_180025EDA
0x180025ec9  mov     [rbp+var_50], r12
0x180025ecd  mov     rax, [rcx]
0x180025ed0  mov     rax, [rax+10h]
0x180025ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ed9  nop
0x180025eda  jmp     loc_1800261B1
0x180025edf  mov     esi, r12d
0x180025ee2  cmp     [rbp+var_38], r12d
0x180025ee6  jbe     short loc_180025F59
0x180025ee8  mov     [rbp+var_40], r12
0x180025eec  mov     rcx, [rbp+var_48]
0x180025ef0  mov     rax, [rcx]
0x180025ef3  lea     r8, [rbp+var_40]
0x180025ef7  mov     edx, esi
0x180025ef9  mov     rax, [rax+30h]
0x180025efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f02  mov     ebx, eax
0x180025f04  test    eax, eax
0x180025f06  js      loc_180026115
0x180025f0c  mov     [rbp+var_34], r12d
0x180025f10  mov     rcx, [rbp+var_40]
0x180025f14  mov     rax, [rcx]
0x180025f17  lea     rdx, [rbp+var_34]
0x180025f1b  mov     rax, [rax+58h]
0x180025f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f24  mov     ebx, eax
0x180025f26  test    eax, eax
0x180025f28  js      loc_1800260C2
0x180025f2e  cmp     [rbp+var_34], 3
0x180025f32  jz      loc_180025FD9
0x180025f38  mov     rcx, [rbp+var_40]
0x180025f3c  test    rcx, rcx
0x180025f3f  jz      short loc_180025F52
0x180025f41  mov     [rbp+var_40], r12
0x180025f45  mov     rax, [rcx]
0x180025f48  mov     rax, [rax+10h]
0x180025f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f51  nop
0x180025f52  inc     esi
0x180025f54  cmp     esi, [rbp+var_38]
0x180025f57  jb      short loc_180025EE8
0x180025f59  mov     dl, r15b; bool
0x180025f5c  mov     rcx, rdi; this
0x180025f5f  call    ?UpdateBluetoothState@BtPanHandler@@AEAAJ_N@Z; BtPanHandler::UpdateBluetoothState(bool)
0x180025f64  mov     ebx, eax
0x180025f66  test    eax, eax
0x180025f68  jns     loc_180026168
0x180025f6e  mov     rcx, [rbp+var_48]
0x180025f72  test    rcx, rcx
0x180025f75  jz      short loc_180025F88
0x180025f77  mov     [rbp+var_48], r12
0x180025f7b  mov     rax, [rcx]
0x180025f7e  mov     rax, [rax+10h]
0x180025f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f87  nop
0x180025f88  mov     rcx, [rbp+var_50]
0x180025f8c  test    rcx, rcx
0x180025f8f  jz      short loc_180025FA2
0x180025f91  mov     [rbp+var_50], r12
0x180025f95  mov     rax, [rcx]
0x180025f98  mov     rax, [rax+10h]
0x180025f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fa1  nop
0x180025fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fa9  cmp     rcx, r14
0x180025fac  jz      short loc_180025FCC
0x180025fae  test    byte ptr [rcx+1Ch], 1
0x180025fb2  jz      short loc_180025FCC
0x180025fb4  mov     edx, 1Ah
0x180025fb9  mov     r9d, ebx
0x180025fbc  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x180025fc3  mov     rcx, [rcx+10h]
0x180025fc7  call    WPP_SF_d
0x180025fcc  mov     rcx, rdi; this
0x180025fcf  call    ?Shutdown@BtPanHandler@@QEAAJXZ; BtPanHandler::Shutdown(void)
0x180025fd4  jmp     loc_1800261B1
0x180025fd9  mov     rbx, [rbp+var_40]
0x180025fdd  cmp     [rdi+30h], rbx
0x180025fe1  jz      short loc_180026012
0x180025fe3  test    rbx, rbx
0x180025fe6  jz      short loc_180025FF8
0x180025fe8  mov     rax, [rbx]
0x180025feb  mov     rcx, rbx
0x180025fee  mov     rax, [rax+8]
0x180025ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ff7  nop
0x180025ff8  mov     rcx, [rdi+30h]
0x180025ffc  mov     [rdi+30h], rbx
0x180026000  test    rcx, rcx
0x180026003  jz      short loc_180026012
0x180026005  mov     rax, [rcx]
0x180026008  mov     rax, [rax+10h]
0x18002600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026011  nop
0x180026012  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026019  mov     ecx, 18h; unsigned __int64
0x18002601e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026023  mov     rbx, rax
0x180026026  test    rax, rax
0x180026029  jz      short loc_18002606F
0x18002602b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180026032  mov     [rbx], rax
0x180026035  mov     dword ptr [rbx+0Ch], 1
0x18002603c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVRadio@Radios@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Devices::Radios::Radio *,IInspectable *>>::`vftable'
0x180026043  mov     [rbx], rax
0x180026046  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002604d  test    rcx, rcx
0x180026050  jz      short loc_18002605F
0x180026052  mov     rax, [rcx]
0x180026055  mov     rax, [rax+8]
0x180026059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002605e  nop
0x18002605f  mov     [rbx+10h], rdi
0x180026063  lea     rax, off_180034330
0x18002606a  mov     [rbx], rax
0x18002606d  jmp     short loc_180026072
0x18002606f  mov     rbx, r12
0x180026072  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x180026076  mov     rcx, [rbp+var_40]
0x18002607a  mov     rax, [rcx]
0x18002607d  lea     r8, [rdi+10h]
0x180026081  mov     rdx, rbx
0x180026084  mov     rax, [rax+38h]
0x180026088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002608d  nop
0x18002608e  test    rbx, rbx
0x180026091  jz      short loc_1800260A3
0x180026093  mov     rax, [rbx]
0x180026096  mov     rcx, rbx
0x180026099  mov     rax, [rax+10h]
0x18002609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260a2  nop
0x1800260a3  mov     rcx, [rbp+var_40]
0x1800260a7  test    rcx, rcx
0x1800260aa  jz      short loc_1800260BD
0x1800260ac  mov     [rbp+var_40], r12
0x1800260b0  mov     rax, [rcx]
0x1800260b3  mov     rax, [rax+10h]
0x1800260b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260bc  nop
0x1800260bd  jmp     loc_180025F59
0x1800260c2  mov     rcx, [rbp+var_40]
0x1800260c6  test    rcx, rcx
0x1800260c9  jz      short loc_1800260DC
  ... truncated ...
```
