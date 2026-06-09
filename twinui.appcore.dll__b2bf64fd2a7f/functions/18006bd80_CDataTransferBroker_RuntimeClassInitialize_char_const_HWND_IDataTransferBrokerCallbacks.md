# CDataTransferBroker::RuntimeClassInitialize(char const *,HWND__ *,IDataTransferBrokerCallbacks *)

- ea: `0x18006bd80`
- end: `0x18006c2af`
- name: `?RuntimeClassInitialize@CDataTransferBroker@@QEAAJPEBDPEAUHWND__@@PEAUIDataTransferBrokerCallbacks@@@Z`
- size: `1327`
- prototype: `__int64 __fastcall(CDataTransferBroker *this, const char *, HWND, struct IDataTransferBrokerCallbacks *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005decc`

## callees

- `0x180003d24`
- `0x180018180`
- `0x180019534`
- `0x180019b14`
- `0x18001fd5c`
- `0x18002b1b0`
- `0x18002b7d0`
- `0x18004687c`
- `0x18004d1ec`
- `0x18005add0`
- `0x180066904`
- `0x1800699e4`
- `0x18006b3dc`
- `0x18006b510`
- `0x18006bd80`
- `0x18006e970`
- `0x180076a58`
- `0x180076a7c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c16c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c16c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18006c03e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18006c03e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18006bf66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18006bf66`
- `RPCRT4!UuidCreate` at `0x18006bdf1`
- `RPCRT4!UuidCreate` at `0x18006bdf1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006be56`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006be56`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18006bee8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18006bee8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18006bf81`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18006bf81`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18006bfa9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18006bfa9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataTransferBroker::RuntimeClassInitialize(
        CDataTransferBroker *this,
        const char *a2,
        HWND a3,
        struct IDataTransferBrokerCallbacks *a4)
{
  unsigned int v7; // edx
  struct TraceLoggingCorrelationVector *v8; // rbx
  TraceLoggingCorrelationVector *v9; // rcx
  int CallingProcessId; // r15d
  unsigned int *v11; // r13
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, char *); // rbx
  _QWORD *v14; // rsi
  HWND Ancestor; // rax
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, _QWORD, char *, char *); // rbx
  LPCWSTR *v18; // r12
  int v19; // ecx
  unsigned __int16 **v20; // r8
  void **v21; // r8
  __int64 v22; // rsi
  void (__fastcall *v23)(__int64, LPCWSTR, __int64, char *); // rdi
  __int64 v24; // rsi
  void (__fastcall *v25)(__int64, LPCWSTR, char *); // rdi
  __int64 v26; // rsi
  void (__fastcall *v27)(__int64, LPCWSTR, char *); // rdi
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  const unsigned __int16 *v32; // rdx
  HANDLE v34[2]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hProcess[2]; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExeName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a2 )
  {
    v8 = TraceLoggingCorrelationVector::Extend(a2, (bool)a2);
  }
  else
  {
    v8 = (struct TraceLoggingCorrelationVector *)operator new(0x90u);
    *((_BYTE *)v8 + 130) = 65;
    Uuid = 0;
    UuidCreate(&Uuid);
    *(UUID *)hProcess = Uuid;
    TraceLoggingCorrelationVector::CreateCvFromGuid<12>(v8, hProcess);
  }
  v9 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v8;
  if ( v9 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v9, v7);
  *((_BYTE *)this + 528) = IsCurrentThreadSTA();
  *((_QWORD *)this + 40) = a3;
  if ( !a3 )
  {
    CallingProcessId = -2144927164;
    LODWORD(v34[0]) = -2144927164;
    goto LABEL_38;
  }
  v11 = (unsigned int *)((char *)this + 444);
  GetWindowThreadProcessId(a3, (LPDWORD)this + 111);
  if ( *((struct IDataTransferBrokerCallbacks **)this + 17) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(struct IDataTransferBrokerCallbacks *))(*(_QWORD *)a4 + 8LL))(a4);
    hProcess[0] = *((HANDLE *)this + 17);
    *((_QWORD *)this + 17) = a4;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hProcess);
  }
  v12 = *((_QWORD *)this + 17);
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v12 + 24LL);
  v14 = (_QWORD *)((char *)this + 128);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
  CallingProcessId = v13(v12, *((_QWORD *)this + 40), *v11, (char *)this + 128);
  LODWORD(v34[0]) = CallingProcessId;
  if ( CallingProcessId >= 0 )
  {
    Ancestor = GetAncestor(*((HWND *)this + 40), 2u);
    *((_QWORD *)this + 41) = Ancestor;
    if ( !Ancestor )
      *((_QWORD *)this + 41) = *((_QWORD *)this + 40);
    *(_QWORD *)&Uuid.Data1 = 0;
    v16 = *v14;
    v17 = *(int (__fastcall **)(__int64, _QWORD, char *, char *))(*(_QWORD *)*v14 + 136LL);
    v18 = (LPCWSTR *)((char *)this + 384);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 384);
    *((_QWORD *)this + 49) = -1;
    *((_QWORD *)this + 50) = -1;
    if ( v17(v16, *((_QWORD *)this + 41), (char *)this + 384, (char *)this + 452) < 0 )
    {
      if ( *((HWND *)this + 40) == GetDesktopWindow() )
      {
        *((_DWORD *)this + 112) = 1;
        goto LABEL_30;
      }
      if ( *((HWND *)this + 40) == FindWindowW(L"ImmersiveLauncher", 0) )
      {
        *((_DWORD *)this + 112) = 3;
        goto LABEL_30;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 384);
      *((_QWORD *)this + 49) = -1;
      *((_QWORD *)this + 50) = -1;
      if ( (int)UserAwareCallerIdentity::GetAppIdFromProcessId((UserAwareCallerIdentity *)*v11, (int)this + 384, v20) < 0 )
      {
        *((_DWORD *)this + 112) = 2;
        hProcess[0] = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          hProcess,
          0);
        if ( (int)CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x400, (unsigned int)hProcess, v21) >= 0 )
        {
          HIDWORD(v34[0]) = 260;
          if ( QueryFullProcessImageNameW(hProcess[0], 0, ExeName, (PDWORD)v34 + 1) )
          {
            if ( HIDWORD(v34[0]) < 0x104 )
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (char *)this + 384,
                ExeName,
                -1);
          }
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hProcess);
        v19 = *((_DWORD *)this + 112);
      }
      else
      {
        *((_DWORD *)this + 112) = 0;
        v19 = 0;
      }
    }
    else
    {
      v19 = StrCmpCW(*v18, L"Windows.UI.Search") == 0 ? 4 : 0;
      *((_DWORD *)this + 112) = v19;
    }
    if ( !v19 )
    {
      v22 = *v14;
      v23 = *(void (__fastcall **)(__int64, LPCWSTR, __int64, char *))(*(_QWORD *)v22 + 80LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 336);
      *((_QWORD *)this + 43) = -1;
      *((_QWORD *)this + 44) = -1;
      v23(v22, *v18, 1, (char *)this + 336);
      v24 = *((_QWORD *)this + 16);
      v25 = *(void (__fastcall **)(__int64, LPCWSTR, char *))(*(_QWORD *)v24 + 88LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 360);
      *((_QWORD *)this + 46) = -1;
      *((_QWORD *)this + 47) = -1;
      v25(v24, *v18, (char *)this + 360);
      v26 = *((_QWORD *)this + 16);
      v27 = *(void (__fastcall **)(__int64, LPCWSTR, char *))(*(_QWORD *)v26 + 96LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 408);
      *((_QWORD *)this + 52) = -1;
      *((_QWORD *)this + 53) = -1;
      v27(v26, *v18, (char *)this + 408);
      v14 = (_QWORD *)((char *)this + 128);
    }
LABEL_30:
    if ( *((_BYTE *)this + 452) )
    {
      HIDWORD(v34[0]) = 0;
      CallingProcessId = CallerIdentity::GetCallingProcessId(0, (char *)v34 + 4);
      LODWORD(v34[0]) = CallingProcessId;
      if ( CallingProcessId >= 0 )
      {
        if ( HIDWORD(v34[0]) == GetCurrentProcessId() )
        {
          CallingProcessId = 0;
          LODWORD(v34[0]) = 0;
LABEL_37:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Uuid);
          goto LABEL_38;
        }
        CallingProcessId = -2147024891;
        LODWORD(v34[0]) = -2147024891;
      }
    }
    if ( CallingProcessId == -2147024891 )
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v14 + 72LL))(*v14, 12, 2147942405LL);
    goto LABEL_37;
  }
LABEL_38:
  v28 = *((_DWORD *)this + 112);
  if ( !v28 )
  {
LABEL_49:
    v32 = (const unsigned __int16 *)*((_QWORD *)this + 48);
    if ( !v32 )
      v32 = L"ImmersiveApp!NoAvailableSourceAppId";
    goto LABEL_51;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    v32 = L"Desktop";
    goto LABEL_51;
  }
  v30 = v29 - 1;
  if ( v30 )
  {
    v31 = v30 - 1;
    if ( !v31 )
    {
      v32 = L"StartScreen";
      goto LABEL_51;
    }
    if ( v31 != 1 )
    {
      v32 = L"NoAvailableSourceAppId";
      goto LABEL_51;
    }
    goto LABEL_49;
  }
  v32 = L"DesktopApp\\NoAvailableSourceAppId";
  if ( *((_QWORD *)this + 48) )
    v32 = (const unsigned __int16 *)*((_QWORD *)this + 48);
LABEL_51:
  CDataTransferBroker::ModernShareFlowStart((CDataTransferBroker *)((char *)this + 48), v32);
  if ( CallingProcessId < 0 )
    ModernShareTelemetry::ModernShareFlow::LogFail<long &,unsigned short const (&)[43]>((char *)this + 536, v34);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qdq(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      10,
      WPP_477f27c87956328522d5ba61c1bdbc13_Traceguids,
      this,
      CallingProcessId,
      *((_QWORD *)this + 40),
      v34[0]);
  }
  return (unsigned int)CallingProcessId;
}

```

## disassembly

```asm
0x18006bd80  mov     [rsp-8+arg_10], rbx
0x18006bd85  push    rbp
0x18006bd86  push    rsi
0x18006bd87  push    rdi
0x18006bd88  push    r12
0x18006bd8a  push    r13
0x18006bd8c  push    r14
0x18006bd8e  push    r15
0x18006bd90  lea     rbp, [rsp-180h]
0x18006bd98  sub     rsp, 280h
0x18006bd9f  mov     rax, cs:__security_cookie
0x18006bda6  xor     rax, rsp
0x18006bda9  mov     [rbp+1B0h+var_40], rax
0x18006bdb0  mov     rdi, r9
0x18006bdb3  mov     rsi, r8
0x18006bdb6  mov     r14, rcx
0x18006bdb9  test    rdx, rdx
0x18006bdbc  jz      short loc_18006BDCB
0x18006bdbe  mov     rcx, rdx; char *
0x18006bdc1  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18006bdc6  mov     rbx, rax
0x18006bdc9  jmp     short loc_18006BE0F
0x18006bdcb  mov     ecx, 90h; Size
0x18006bdd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bdd5  mov     rbx, rax
0x18006bdd8  mov     qword ptr [rsp+2B0h+Uuid.Data1], rax
0x18006bddd  mov     byte ptr [rax+82h], 41h ; 'A'
0x18006bde4  xorps   xmm0, xmm0
0x18006bde7  movups  xmmword ptr [rsp+2B0h+Uuid.Data1], xmm0
0x18006bdec  lea     rcx, [rsp+2B0h+Uuid]; Uuid
0x18006bdf1  call    cs:__imp_UuidCreate
0x18006bdf7  movaps  xmm0, xmmword ptr [rsp+2B0h+Uuid.Data1]
0x18006bdfc  movdqa  xmmword ptr [rsp+2B0h+hProcess], xmm0
0x18006be02  lea     rdx, [rsp+2B0h+hProcess]
0x18006be07  mov     rcx, rbx
0x18006be0a  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x18006be0f  mov     rcx, [r14+78h]; this
0x18006be13  mov     [r14+78h], rbx
0x18006be17  test    rcx, rcx
0x18006be1a  jz      short loc_18006BE21
0x18006be1c  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18006be21  call    ?IsCurrentThreadSTA@@YA_NXZ; IsCurrentThreadSTA(void)
0x18006be26  mov     [r14+210h], al
0x18006be2d  mov     [r14+140h], rsi
0x18006be34  test    rsi, rsi
0x18006be37  jnz     short loc_18006BE49
0x18006be39  mov     r15d, 80270244h
0x18006be3f  mov     [rsp+2B0h+var_280], r15d
0x18006be44  jmp     loc_18006C1B0
0x18006be49  lea     r13, [r14+1BCh]
0x18006be50  mov     rdx, r13; lpdwProcessId
0x18006be53  mov     rcx, rsi; hWnd
0x18006be56  call    cs:__imp_GetWindowThreadProcessId
0x18006be5c  cmp     [r14+88h], rdi
0x18006be63  jz      short loc_18006BE97
0x18006be65  test    rdi, rdi
0x18006be68  jz      short loc_18006BE7A
0x18006be6a  mov     rax, [rdi]
0x18006be6d  mov     rcx, rdi
0x18006be70  mov     rax, [rax+8]
0x18006be74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be79  nop
0x18006be7a  mov     rax, [r14+88h]
0x18006be81  mov     [rsp+2B0h+hProcess], rax
0x18006be86  mov     [r14+88h], rdi
0x18006be8d  lea     rcx, [rsp+2B0h+hProcess]
0x18006be92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006be97  mov     rdi, [r14+88h]
0x18006be9e  mov     rax, [rdi]
0x18006bea1  mov     rbx, [rax+18h]
0x18006bea5  lea     rsi, [r14+80h]
0x18006beac  mov     rcx, rsi
0x18006beaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006beb4  mov     r9, rsi
0x18006beb7  mov     r8d, [r13+0]
0x18006bebb  mov     rdx, [r14+140h]
0x18006bec2  mov     rcx, rdi
0x18006bec5  mov     rax, rbx
0x18006bec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006becd  mov     r15d, eax
0x18006bed0  mov     [rsp+2B0h+var_280], eax
0x18006bed4  test    eax, eax
0x18006bed6  js      loc_18006C1B0
0x18006bedc  mov     edx, 2; gaFlags
0x18006bee1  mov     rcx, [r14+140h]; hwnd
0x18006bee8  call    cs:__imp_GetAncestor
0x18006beee  mov     [r14+148h], rax
0x18006bef5  test    rax, rax
0x18006bef8  jnz     short loc_18006BF08
0x18006befa  mov     rax, [r14+140h]
0x18006bf01  mov     [r14+148h], rax
0x18006bf08  mov     qword ptr [rsp+2B0h+Uuid.Data1], 0
0x18006bf11  mov     rdi, [rsi]
0x18006bf14  mov     rax, [rdi]
0x18006bf17  mov     rbx, [rax+88h]
0x18006bf1e  lea     r12, [r14+180h]
0x18006bf25  mov     rcx, r12
0x18006bf28  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006bf2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bf31  mov     [r12+8], rax
0x18006bf36  mov     [r12+10h], rax
0x18006bf3b  lea     r9, [r14+1C4h]
0x18006bf42  mov     r8, r12
0x18006bf45  mov     rdx, [r14+148h]
0x18006bf4c  mov     rcx, rdi
0x18006bf4f  mov     rax, rbx
0x18006bf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf57  test    eax, eax
0x18006bf59  js      short loc_18006BF81
0x18006bf5b  lea     rdx, pszStr2; "Windows.UI.Search"
0x18006bf62  mov     rcx, [r12]; pszStr1
0x18006bf66  call    cs:__imp_StrCmpCW
0x18006bf6c  neg     eax
0x18006bf6e  sbb     ecx, ecx
0x18006bf70  not     ecx
0x18006bf72  and     ecx, 4
0x18006bf75  mov     [r14+1C0h], ecx
0x18006bf7c  jmp     loc_18006C070
0x18006bf81  call    cs:__imp_GetDesktopWindow
0x18006bf87  cmp     [r14+140h], rax
0x18006bf8e  jnz     short loc_18006BFA0
0x18006bf90  mov     dword ptr [r14+1C0h], 1
0x18006bf9b  jmp     loc_18006C13E
0x18006bfa0  xor     edx, edx; lpWindowName
0x18006bfa2  lea     rcx, aImmersivelaunc; "ImmersiveLauncher"
0x18006bfa9  call    cs:__imp_FindWindowW
0x18006bfaf  cmp     [r14+140h], rax
0x18006bfb6  jz      loc_18006C133
0x18006bfbc  mov     rcx, r12
0x18006bfbf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006bfc4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006bfc8  mov     [r12+8], rbx
0x18006bfcd  mov     [r12+10h], rbx
0x18006bfd2  mov     rdx, r12; unsigned int
0x18006bfd5  mov     ecx, [r13+0]; this
0x18006bfd9  call    ?GetAppIdFromProcessId@UserAwareCallerIdentity@@YAJKPEAPEAG@Z; UserAwareCallerIdentity::GetAppIdFromProcessId(ulong,ushort * *)
0x18006bfde  test    eax, eax
0x18006bfe0  js      short loc_18006BFF1
0x18006bfe2  mov     dword ptr [r14+1C0h], 0
0x18006bfed  xor     ecx, ecx
0x18006bfef  jmp     short loc_18006C070
0x18006bff1  mov     dword ptr [r14+1C0h], 2
0x18006bffc  mov     [rsp+2B0h+hProcess], 0
0x18006c005  xor     edx, edx
0x18006c007  lea     rcx, [rsp+2B0h+hProcess]
0x18006c00c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006c011  lea     rdx, [rsp+2B0h+hProcess]; unsigned int
0x18006c016  mov     ecx, 400h; this
0x18006c01b  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x18006c020  test    eax, eax
0x18006c022  js      short loc_18006C05F
0x18006c024  mov     edi, 104h
0x18006c029  mov     [rsp+2B0h+dwSize], edi
0x18006c02d  lea     r9, [rsp+2B0h+dwSize]; lpdwSize
0x18006c032  lea     r8, [rsp+2B0h+ExeName]; lpExeName
0x18006c037  xor     edx, edx; dwFlags
0x18006c039  mov     rcx, [rsp+2B0h+hProcess]; hProcess
0x18006c03e  call    cs:__imp_QueryFullProcessImageNameW
0x18006c044  test    eax, eax
0x18006c046  jz      short loc_18006C05F
0x18006c048  cmp     [rsp+2B0h+dwSize], edi
0x18006c04c  jnb     short loc_18006C05F
0x18006c04e  mov     r8, rbx
0x18006c051  lea     rdx, [rsp+2B0h+ExeName]
0x18006c056  mov     rcx, r12
0x18006c059  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18006c05e  nop
0x18006c05f  lea     rcx, [rsp+2B0h+hProcess]
0x18006c064  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c069  mov     ecx, [r14+1C0h]
0x18006c070  test    ecx, ecx
0x18006c072  jnz     loc_18006C13E
0x18006c078  mov     rsi, [rsi]
0x18006c07b  mov     rax, [rsi]
0x18006c07e  mov     rdi, [rax+50h]
0x18006c082  lea     rbx, [r14+150h]
0x18006c089  mov     rcx, rbx
0x18006c08c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006c091  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c095  mov     [rbx+8], rax
0x18006c099  mov     [rbx+10h], rax
0x18006c09d  mov     r9, rbx
0x18006c0a0  lea     r8d, [rax+2]
0x18006c0a4  mov     rdx, [r12]
0x18006c0a8  mov     rcx, rsi
0x18006c0ab  mov     rax, rdi
0x18006c0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0b3  lea     r13, [r14+80h]
0x18006c0ba  mov     rsi, [r13+0]
0x18006c0be  mov     rax, [rsi]
0x18006c0c1  mov     rdi, [rax+58h]
0x18006c0c5  lea     rbx, [r14+168h]
0x18006c0cc  mov     rcx, rbx
0x18006c0cf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006c0d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c0d8  mov     [rbx+8], rax
0x18006c0dc  mov     [rbx+10h], rax
0x18006c0e0  mov     r8, rbx
0x18006c0e3  mov     rdx, [r12]
0x18006c0e7  mov     rcx, rsi
0x18006c0ea  mov     rax, rdi
0x18006c0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0f2  mov     rsi, [r13+0]
0x18006c0f6  mov     rax, [rsi]
0x18006c0f9  mov     rdi, [rax+60h]
0x18006c0fd  lea     rbx, [r14+198h]
0x18006c104  mov     rcx, rbx
0x18006c107  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006c10c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c110  mov     [rbx+8], rax
0x18006c114  mov     [rbx+10h], rax
0x18006c118  mov     r8, rbx
0x18006c11b  mov     rdx, [r12]
0x18006c11f  mov     rcx, rsi
0x18006c122  mov     rax, rdi
0x18006c125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c12a  lea     rsi, [r14+80h]
0x18006c131  jmp     short loc_18006C13E
0x18006c133  mov     dword ptr [r14+1C0h], 3
0x18006c13e  mov     ebx, 80070005h
0x18006c143  cmp     byte ptr [r14+1C4h], 0
0x18006c14b  jz      short loc_18006C189
0x18006c14d  mov     [rsp+2B0h+dwSize], 0
0x18006c155  lea     rdx, [rsp+2B0h+dwSize]
0x18006c15a  xor     ecx, ecx
0x18006c15c  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x18006c161  mov     r15d, eax
0x18006c164  mov     [rsp+2B0h+var_280], eax
0x18006c168  test    eax, eax
0x18006c16a  js      short loc_18006C189
0x18006c16c  call    cs:__imp_GetCurrentProcessId
0x18006c172  cmp     [rsp+2B0h+dwSize], eax
0x18006c176  jnz     short loc_18006C182
0x18006c178  xor     r15d, r15d
0x18006c17b  mov     [rsp+2B0h+var_280], r15d
0x18006c180  jmp     short loc_18006C1A6
0x18006c182  mov     r15d, ebx
0x18006c185  mov     [rsp+2B0h+var_280], ebx
0x18006c189  cmp     r15d, ebx
0x18006c18c  jnz     short loc_18006C1A6
0x18006c18e  mov     rcx, [rsi]
0x18006c191  mov     rax, [rcx]
0x18006c194  mov     r8d, ebx
0x18006c197  mov     edx, 0Ch
0x18006c19c  mov     rax, [rax+48h]
0x18006c1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1a5  nop
0x18006c1a6  lea     rcx, [rsp+2B0h+Uuid]
0x18006c1ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c1b0  mov     ecx, [r14+1C0h]
0x18006c1b7  test    ecx, ecx
0x18006c1b9  jz      short loc_18006C201
0x18006c1bb  sub     ecx, 1
0x18006c1be  jz      short loc_18006C1F8
0x18006c1c0  sub     ecx, 1
0x18006c1c3  jz      short loc_18006C1E1
0x18006c1c5  sub     ecx, 1
0x18006c1c8  jz      short loc_18006C1D8
0x18006c1ca  cmp     ecx, 1
0x18006c1cd  jz      short loc_18006C201
0x18006c1cf  lea     rdx, aNoavailablesou; "NoAvailableSourceAppId"
0x18006c1d6  jmp     short loc_18006C214
0x18006c1d8  lea     rdx, aStartscreen; "StartScreen"
0x18006c1df  jmp     short loc_18006C214
0x18006c1e1  mov     rax, [r14+180h]
0x18006c1e8  lea     rdx, aDesktopappNoav; "DesktopApp\\NoAvailableSourceAppId"
0x18006c1ef  test    rax, rax
0x18006c1f2  cmovnz  rdx, rax
0x18006c1f6  jmp     short loc_18006C214
0x18006c1f8  lea     rdx, aDesktop; "Desktop"
0x18006c1ff  jmp     short loc_18006C214
0x18006c201  mov     rdx, [r14+180h]
0x18006c208  test    rdx, rdx
0x18006c20b  jnz     short loc_18006C214
0x18006c20d  lea     rdx, aImmersiveappNo; "ImmersiveApp!NoAvailableSourceAppId"
0x18006c214  mov     eax, 30h ; '0'
0x18006c219  mov     rcx, r14
0x18006c21c  add     rcx, rax; this
0x18006c21f  call    ?ModernShareFlowStart@CDataTransferBroker@@UEAAJPEBG@Z; CDataTransferBroker::ModernShareFlowStart(ushort const *)
0x18006c224  test    r15d, r15d
0x18006c227  jns     short loc_18006C23A
0x18006c229  lea     rcx, [r14+218h]
0x18006c230  lea     rdx, [rsp+2B0h+var_280]
0x18006c235  call    ??$LogFail@AEAJAEAY0CL@$$CBG@ModernShareFlow@ModernShareTelemetry@@QEAAXAEAJAEAY0CL@$$CBG@Z; ModernShareTelemetry::ModernShareFlow::LogFail<long &,ushort const (&)[43]>(long &,ushort const (&)[43])
0x18006c23a  lea     rax, WPP_GLOBAL_Control
0x18006c241  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c248  cmp     rcx, rax
0x18006c24b  jz      short loc_18006C282
0x18006c24d  test    byte ptr [rcx+44h], 1
0x18006c251  jz      short loc_18006C282
0x18006c253  cmp     byte ptr [rcx+41h], 4
0x18006c257  jb      short loc_18006C282
0x18006c259  mov     edx, 0Ah
0x18006c25e  mov     r8, [r14+140h]
0x18006c265  mov     [rsp+2B0h+var_288], r8
0x18006c26a  mov     [rsp+2B0h+var_290], r15d
0x18006c26f  mov     r9, r14
0x18006c272  lea     r8, WPP_477f27c87956328522d5ba61c1bdbc13_Traceguids
0x18006c279  mov     rcx, [rcx+38h]
0x18006c27d  call    WPP_SF_qdq
  ... truncated ...
```
