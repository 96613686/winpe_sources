# Windows::Internal::Notifications::CToastActivator_Background::EnsurePresentationEndpoint(IWpnPresentationEndpoint * *)

- ea: `0x18001c5c0`
- end: `0x18001c8c3`
- name: `?EnsurePresentationEndpoint@CToastActivator_Background@Notifications@Internal@Windows@@AEAAJPEAPEAUIWpnPresentationEndpoint@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_Background *__hidden this, struct IWpnPresentationEndpoint **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c270`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x18000710c`
- `0x18001478c`
- `0x180015920`
- `0x1800167b4`
- `0x18001c5c0`
- `0x18001c8cc`
- `0x18001ff00`
- `0x180020500`
- `0x180020568`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c622`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c622`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c78f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c78f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c87c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c720`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c720`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c835`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c835`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18001c6a8`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18001c6a8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001c659`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001c659`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18001c7c7`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18001c7c7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Background::EnsurePresentationEndpoint(
        Windows::Internal::Notifications::CToastActivator_Background *this,
        struct IWpnPresentationEndpoint **a2)
{
  _QWORD *v4; // rsi
  bool v5; // bl
  bool v6; // r14
  __int64 v7; // rbx
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD *); // rbx
  HRESULT Instance; // eax
  __int64 v14; // rdx
  LPVOID *v15; // rax
  struct IWpnPresentationEndpoint *v16; // rax
  GUID *ppv; // [rsp+20h] [rbp-39h]
  __int64 v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  PSRWLOCK v21; // [rsp+40h] [rbp-19h] BYREF
  struct IWpnPresentationEndpoint *v22; // [rsp+48h] [rbp-11h] BYREF
  int v23; // [rsp+50h] [rbp-9h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v26; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 88);
  v4 = (_QWORD *)((char *)this + 72);
  Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::operator=(&v22, (char *)this + 72);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  if ( v22 )
    goto LABEL_30;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v21, (char *)this + 88);
  if ( *v4 )
  {
LABEL_28:
    Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::operator=(&v22, v4);
    if ( v21 )
      ReleaseSRWLockExclusive(v21);
LABEL_30:
    v16 = v22;
    v22 = 0;
    *a2 = v16;
    v9 = 0;
    goto LABEL_31;
  }
  v19 = 0;
  v23 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v23, 0);
  v5 = 1;
  v6 = (unsigned int)(v23 - 7) <= 1;
  if ( dword_180044910 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180044910);
    if ( dword_180044910 == -1 )
    {
      if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku() )
        v5 = v6;
      byte_180044914 = v5;
      Init_thread_footer(&dword_180044910);
    }
  }
  if ( byte_180044914 && *((_QWORD *)this + 10) )
  {
    v20 = 0;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v7 = v26;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v20);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v10 = 188;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      goto LABEL_17;
    }
    SRWLock = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, PSRWLOCK *))(*(_QWORD *)v20 + 136LL))(
                          v20,
                          *((_QWORD *)this + 10),
                          &SRWLock);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v10 = 191;
      goto LABEL_16;
    }
    IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(&v19);
    ppv = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
    ActivationFactory = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, SRWLock);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v10 = 198;
      goto LABEL_16;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  else
  {
    v15 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(&v19);
    Instance = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 0x404u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 v15);
    v9 = Instance;
    if ( Instance < 0 )
    {
      v14 = 206;
      goto LABEL_26;
    }
  }
  v11 = v19;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4);
  Instance = v12(v11, v4);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    goto LABEL_28;
  }
  v14 = 208;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
    (const char *)(unsigned int)Instance,
    (int)ppv);
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  if ( v21 )
    ReleaseSRWLockExclusive(v21);
LABEL_31:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  return v9;
}

```

## disassembly

```asm
0x18001c5c0  mov     [rsp-8+arg_10], rbx
0x18001c5c5  mov     [rsp-8+arg_18], rsi
0x18001c5ca  push    rbp
0x18001c5cb  push    rdi
0x18001c5cc  push    r12
0x18001c5ce  push    r14
0x18001c5d0  push    r15
0x18001c5d2  lea     rbp, [rsp-37h]
0x18001c5d7  sub     rsp, 90h
0x18001c5de  mov     rax, cs:__security_cookie
0x18001c5e5  xor     rax, rsp
0x18001c5e8  mov     [rbp+57h+var_30], rax
0x18001c5ec  mov     r15, rdx
0x18001c5ef  mov     rdi, rcx
0x18001c5f2  xor     r12d, r12d
0x18001c5f5  mov     [rdx], r12
0x18001c5f8  mov     [rbp+57h+var_68], r12
0x18001c5fc  lea     rdx, [rcx+58h]
0x18001c600  lea     rcx, [rbp+57h+SRWLock]
0x18001c604  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18001c609  lea     rsi, [rdi+48h]
0x18001c60d  mov     rdx, rsi
0x18001c610  lea     rcx, [rbp+57h+var_68]
0x18001c614  call    ??4?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::operator=(Microsoft::WRL::ComPtr<IWpnPresentationEndpoint> const &)
0x18001c619  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c61d  test    rcx, rcx
0x18001c620  jz      short loc_18001C628
0x18001c622  call    cs:__imp_ReleaseSRWLockShared
0x18001c628  cmp     [rbp+57h+var_68], r12
0x18001c62c  jnz     loc_18001C882
0x18001c632  lea     rdx, [rdi+58h]
0x18001c636  lea     rcx, [rbp+57h+var_70]
0x18001c63a  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001c63f  cmp     [rsi], r12
0x18001c642  jnz     loc_18001C867
0x18001c648  mov     [rbp+57h+var_80], r12
0x18001c64c  mov     [rbp+57h+var_60], r12d
0x18001c650  xor     r8d, r8d
0x18001c653  lea     rdx, [rbp+57h+var_60]
0x18001c657  xor     ecx, ecx
0x18001c659  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001c65f  mov     eax, [rbp+57h+var_60]
0x18001c662  add     eax, 0FFFFFFF9h
0x18001c665  mov     ebx, 1
0x18001c66a  cmp     eax, ebx
0x18001c66c  setbe   r14b
0x18001c670  mov     ecx, cs:_tls_index
0x18001c676  mov     rax, gs:58h
0x18001c67f  mov     edx, 4
0x18001c684  mov     rax, [rax+rcx*8]
0x18001c688  mov     ecx, [rdx+rax]
0x18001c68b  cmp     cs:dword_180044910, ecx
0x18001c691  jle     short loc_18001C6CC
0x18001c693  lea     rcx, dword_180044910
0x18001c69a  call    _Init_thread_header
0x18001c69f  cmp     cs:dword_180044910, 0FFFFFFFFh
0x18001c6a6  jnz     short loc_18001C6CC
0x18001c6a8  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18001c6ae  test    al, al
0x18001c6b0  jnz     short loc_18001C6BA
0x18001c6b2  test    r14b, r14b
0x18001c6b5  jnz     short loc_18001C6BA
0x18001c6b7  mov     bl, r12b
0x18001c6ba  mov     cs:byte_180044914, bl
0x18001c6c0  lea     rcx, dword_180044910
0x18001c6c7  call    _Init_thread_footer
0x18001c6cc  cmp     cs:byte_180044914, r12b
0x18001c6d3  jz      loc_18001C811
0x18001c6d9  cmp     [rdi+50h], r12
0x18001c6dd  jz      loc_18001C811
0x18001c6e3  mov     [rbp+57h+var_78], r12
0x18001c6e7  mov     [rbp+57h+var_38], r12
0x18001c6eb  mov     r9d, 23h ; '#'; unsigned int
0x18001c6f1  lea     r8d, [r9+1]; unsigned int
0x18001c6f5  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18001c6fc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001c700  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c705  mov     rbx, [rbp+57h+var_38]
0x18001c709  lea     rcx, [rbp+57h+var_78]
0x18001c70d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c712  lea     r8, [rbp+57h+var_78]
0x18001c716  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18001c71d  mov     rcx, rbx
0x18001c720  call    cs:__imp_RoGetActivationFactory
0x18001c726  mov     ebx, eax
0x18001c728  test    eax, eax
0x18001c72a  jns     short loc_18001C733
0x18001c72c  mov     edx, 0BCh
0x18001c731  jmp     short loc_18001C75D
0x18001c733  mov     [rbp+57h+SRWLock], r12
0x18001c737  mov     rcx, [rbp+57h+var_78]
0x18001c73b  mov     rax, [rcx]
0x18001c73e  lea     r8, [rbp+57h+SRWLock]
0x18001c742  mov     rdx, [rdi+50h]
0x18001c746  mov     rax, [rax+88h]
0x18001c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c752  mov     ebx, eax
0x18001c754  test    eax, eax
0x18001c756  jns     short loc_18001C79A
0x18001c758  mov     edx, 0BFh; void *
0x18001c75d  mov     rcx, [rbp+5Fh]; this
0x18001c761  mov     r9d, eax; char *
0x18001c764  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c76b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c770  lea     rcx, [rbp+57h+var_78]
0x18001c774  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c779  lea     rcx, [rbp+57h+var_80]
0x18001c77d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c782  mov     rcx, [rbp+57h+var_70]; SRWLock
0x18001c786  test    rcx, rcx
0x18001c789  jz      loc_18001C890
0x18001c78f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c795  jmp     loc_18001C890
0x18001c79a  lea     rcx, [rbp+57h+var_80]
0x18001c79e  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatform>>)
0x18001c7a3  mov     [rsp+0B0h+var_88], rax
0x18001c7a8  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18001c7af  mov     [rsp+0B0h+ppv], r9
0x18001c7b4  mov     r9, [rbp+57h+SRWLock]
0x18001c7b8  xor     edx, edx
0x18001c7ba  mov     r8d, 404h
0x18001c7c0  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x18001c7c7  call    cs:__imp_CoCreateInstanceAsUser
0x18001c7cd  mov     ebx, eax
0x18001c7cf  test    eax, eax
0x18001c7d1  jns     short loc_18001C7DA
0x18001c7d3  mov     edx, 0C6h
0x18001c7d8  jmp     short loc_18001C75D
0x18001c7da  lea     rcx, [rbp+57h+var_78]
0x18001c7de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c7e3  mov     rdi, [rbp+57h+var_80]
0x18001c7e7  mov     rax, [rdi]
0x18001c7ea  mov     rbx, [rax+20h]
0x18001c7ee  mov     rcx, rsi
0x18001c7f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c7f6  mov     rdx, rsi
0x18001c7f9  mov     rcx, rdi
0x18001c7fc  mov     rax, rbx
0x18001c7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c804  mov     ebx, eax
0x18001c806  test    eax, eax
0x18001c808  jns     short loc_18001C85E
0x18001c80a  mov     edx, 0D0h
0x18001c80f  jmp     short loc_18001C846
0x18001c811  lea     rcx, [rbp+57h+var_80]
0x18001c815  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatform>>)
0x18001c81a  mov     [rsp+0B0h+ppv], rax; int
0x18001c81f  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18001c826  xor     edx, edx; pUnkOuter
0x18001c828  mov     r8d, 404h; dwClsContext
0x18001c82e  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18001c835  call    cs:__imp_CoCreateInstance
0x18001c83b  mov     ebx, eax
0x18001c83d  test    eax, eax
0x18001c83f  jns     short loc_18001C7E3
0x18001c841  mov     edx, 0CEh; void *
0x18001c846  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c84d  mov     r9d, eax; char *
0x18001c850  mov     rcx, [rbp+5Fh]; this
0x18001c854  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c859  jmp     loc_18001C779
0x18001c85e  lea     rcx, [rbp+57h+var_80]
0x18001c862  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c867  mov     rdx, rsi
0x18001c86a  lea     rcx, [rbp+57h+var_68]
0x18001c86e  call    ??4?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::operator=(Microsoft::WRL::ComPtr<IWpnPresentationEndpoint> const &)
0x18001c873  mov     rcx, [rbp+57h+var_70]; SRWLock
0x18001c877  test    rcx, rcx
0x18001c87a  jz      short loc_18001C882
0x18001c87c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c882  mov     rax, [rbp+57h+var_68]
0x18001c886  mov     [rbp+57h+var_68], r12
0x18001c88a  mov     [r15], rax
0x18001c88d  mov     ebx, r12d
0x18001c890  lea     rcx, [rbp+57h+var_68]
0x18001c894  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c899  mov     eax, ebx
0x18001c89b  mov     rcx, [rbp+57h+var_30]
0x18001c89f  xor     rcx, rsp; StackCookie
0x18001c8a2  call    __security_check_cookie
0x18001c8a7  lea     r11, [rsp+0B0h+var_20]
0x18001c8af  mov     rbx, [r11+40h]
0x18001c8b3  mov     rsi, [r11+48h]
0x18001c8b7  mov     rsp, r11
0x18001c8ba  pop     r15
0x18001c8bc  pop     r14
0x18001c8be  pop     r12
0x18001c8c0  pop     rdi
0x18001c8c1  pop     rbp
0x18001c8c2  retn
```
