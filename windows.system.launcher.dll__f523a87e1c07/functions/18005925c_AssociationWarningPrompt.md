# AssociationWarningPrompt

- ea: `0x18005925c`
- end: `0x1800595bf`
- name: `AssociationWarningPrompt`
- size: `867`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180058e08`
- `0x180059708`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18004966c`
- `0x18005042c`
- `0x1800550d8`
- `0x18005552c`
- `0x18005925c`
- `0x18008a030`
- `0x18008a400`
- `0x18008dee8`
- `0x1800fb0d0`
- `0x1800fb0fc`
- `0x1800fb440`
- `0x1800fbc38`
- `0x1800fbcf4`
- `0x180111010`

## import_xrefs

- `Windows.Storage!__imp_AssocCreateElement` at `0x180059316`
- `Windows.Storage!__imp_AssocCreateElement` at `0x180059316`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059444`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059469`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059444`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180059469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005952c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005952c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059554`

## string_xrefs

- `0x18005937e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\protocolwarning.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AssociationWarningPrompt(
        IUnknown *punk,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  const char *v9; // rbx
  char v10; // si
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, _QWORD); // rdi
  int v16; // eax
  void (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v19; // rbx
  int (__fastcall *v20)(__int64, __int64, _QWORD, LPCWCH *); // rdi
  __int64 v21; // rdi
  int (__fastcall *v22)(__int64, __int64, _QWORD, LPVOID *); // rbx
  CAssociationWarning *v23; // rax
  CAssociationWarning *v24; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPCWCH lpString2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v32[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v9 = *(const char **)TelemetryCorrelationVectorServiceProvider::Increment(pv, a5);
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v32);
  v32[0] = &LauncherDesktopProvider::AssociationWarningPrompt::`vftable';
  LauncherDesktopProvider::AssociationWarningPrompt::StartActivityWithCorrelationVector(
    (LauncherDesktopProvider::AssociationWarningPrompt *)v32,
    v9);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(pv);
  v10 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  if ( (int)AssocCreateElement(&CLSID_AssocProgidElement, &GUID_1bee549b_0bf4_4c81_88b3_ad5bf3ab0ac4, &v28) >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD), _QWORD))(*v28)[3])(v28, a4);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 163;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\protocolwarning.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
      goto LABEL_23;
    }
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v15 = **v28;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
    v11 = v15(v14, &GUID_3c44ba76_de0e_4049_b6e4_6b31a5262707, &v30);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 164;
      goto LABEL_6;
    }
    v16 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v30)[4])(v30, a3);
    if ( v16 < 0 )
    {
      v10 = v16 == -2147023741;
    }
    else
    {
      v17 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
      v18 = **v30;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v18(v17, &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502, &v29);
    }
  }
  v19 = v29;
  if ( v29 )
  {
    lpString2 = 0;
    v20 = *(int (__fastcall **)(__int64, __int64, _QWORD, LPCWCH *))(*(_QWORD *)v29 + 24LL);
    CoTaskMemFree(0);
    if ( v20(v19, 458756, 0, &lpString2) >= 0 )
    {
      if ( CompareStringOrdinal(L"Unknown", -1, lpString2, -1, 1) == 2
        || CompareStringOrdinal(L"Undecided", -1, lpString2, -1, 1) == 2 )
      {
        v10 = 1;
      }
      else
      {
        v10 = 0;
        pv[0] = 0;
        v21 = v29;
        v22 = *(int (__fastcall **)(__int64, __int64, _QWORD, LPVOID *))(*(_QWORD *)v29 + 24LL);
        CoTaskMemFree(0);
        if ( v22(v21, 35061768, 0, pv) >= 0 )
        {
          v23 = (CAssociationWarning *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          v24 = v23;
          if ( v23 )
          {
            *(_QWORD *)v23 = 0;
            *((_QWORD *)v23 + 1) = lpString2;
            lpString2 = 0;
            *((LPVOID *)v23 + 2) = pv[0];
            pv[0] = 0;
            *((_BYTE *)v23 + 24) = 0;
            if ( (int)CAssociationWarning::CreateAndShow(v23, punk, a2) >= 0 )
              v10 = *((_BYTE *)v24 + 24);
            CAssociationWarning::~CAssociationWarning(v24);
            operator delete(v24, (const struct std::nothrow_t *)0x20);
          }
        }
        CoTaskMemFree(pv[0]);
      }
    }
    CoTaskMemFree((LPVOID)lpString2);
  }
  LauncherDesktopProvider::AssociationWarningPrompt::Stop((LauncherDesktopProvider::AssociationWarningPrompt *)v32, v10);
  v12 = v10 == 0 ? 0x80070005 : 0;
LABEL_23:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
  LauncherDesktopProvider::AssociationWarningPrompt::~AssociationWarningPrompt((LauncherDesktopProvider::AssociationWarningPrompt *)v32);
  return v12;
}

```

## disassembly

```asm
0x18005925c  push    rbp
0x18005925e  push    rbx
0x18005925f  push    rsi
0x180059260  push    rdi
0x180059261  push    r12
0x180059263  push    r14
0x180059265  push    r15
0x180059267  lea     rbp, [rsp-0C0h]
0x18005926f  sub     rsp, 1C0h
0x180059276  mov     rax, cs:__security_cookie
0x18005927d  xor     rax, rsp
0x180059280  mov     [rbp+0F0h+var_40], rax
0x180059287  mov     edi, r9d
0x18005928a  mov     r14, r8
0x18005928d  mov     r12, rdx
0x180059290  mov     r15, rcx
0x180059293  mov     rdx, [rbp+0F0h+arg_20]
0x18005929a  lea     rcx, [rsp+1F0h+pv]
0x18005929f  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x1800592a4  mov     rbx, [rax]
0x1800592a7  lea     rdx, aAssociationwar; "AssociationWarningPrompt"
0x1800592ae  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x1800592b3  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800592b8  lea     rax, ??_7AssociationWarningPrompt@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::AssociationWarningPrompt::`vftable'
0x1800592bf  mov     [rsp+1F0h+var_190], rax
0x1800592c4  mov     rdx, rbx; char *
0x1800592c7  lea     rcx, [rsp+1F0h+var_190]; this
0x1800592cc  call    ?StartActivityWithCorrelationVector@AssociationWarningPrompt@LauncherDesktopProvider@@QEAAXPEBD@Z; LauncherDesktopProvider::AssociationWarningPrompt::StartActivityWithCorrelationVector(char const *)
0x1800592d1  lea     rcx, [rsp+1F0h+pv]
0x1800592d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800592db  xor     sil, sil
0x1800592de  mov     [rsp+1F0h+var_1A8], 0
0x1800592e7  mov     [rsp+1F0h+var_1B0], 0
0x1800592f0  mov     [rsp+1F0h+var_1B8], 0
0x1800592f9  lea     rcx, [rsp+1F0h+var_1B8]
0x1800592fe  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180059303  lea     r8, [rsp+1F0h+var_1B8]
0x180059308  lea     rdx, _GUID_1bee549b_0bf4_4c81_88b3_ad5bf3ab0ac4
0x18005930f  lea     rcx, CLSID_AssocProgidElement
0x180059316  call    cs:__imp_AssocCreateElement
0x18005931c  test    eax, eax
0x18005931e  js      loc_1800593DF
0x180059324  mov     rcx, [rsp+1F0h+var_1B8]
0x180059329  mov     rax, [rcx]
0x18005932c  mov     edx, edi
0x18005932e  mov     rax, [rax+18h]
0x180059332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059337  mov     ebx, eax
0x180059339  test    eax, eax
0x18005933b  jns     short loc_180059344
0x18005933d  mov     edx, 0A3h
0x180059342  jmp     short loc_18005937B
0x180059344  mov     rbx, [rsp+1F0h+var_1B8]
0x180059349  mov     rax, [rbx]
0x18005934c  mov     rdi, [rax]
0x18005934f  lea     rcx, [rsp+1F0h+var_1A8]
0x180059354  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180059359  lea     r8, [rsp+1F0h+var_1A8]
0x18005935e  lea     rdx, _GUID_3c44ba76_de0e_4049_b6e4_6b31a5262707
0x180059365  mov     rcx, rbx
0x180059368  mov     rax, rdi
0x18005936b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059370  mov     ebx, eax
0x180059372  test    eax, eax
0x180059374  jns     short loc_180059396
0x180059376  mov     edx, 0A4h; void *
0x18005937b  mov     r9d, eax; char *
0x18005937e  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\windows.system.launc"...
0x180059385  mov     rcx, [rbp+0F8h]; this
0x18005938c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059391  jmp     loc_180059574
0x180059396  mov     rcx, [rsp+1F0h+var_1A8]
0x18005939b  mov     rax, [rcx]
0x18005939e  mov     rdx, r14
0x1800593a1  mov     rax, [rax+20h]
0x1800593a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593aa  test    eax, eax
0x1800593ac  js      loc_180059534
0x1800593b2  mov     rbx, [rsp+1F0h+var_1A8]
0x1800593b7  mov     rax, [rbx]
0x1800593ba  mov     rdi, [rax]
0x1800593bd  lea     rcx, [rsp+1F0h+var_1B0]
0x1800593c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800593c7  lea     r8, [rsp+1F0h+var_1B0]
0x1800593cc  lea     rdx, _GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502
0x1800593d3  mov     rcx, rbx
0x1800593d6  mov     rax, rdi
0x1800593d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593de  nop
0x1800593df  mov     r14d, 1
0x1800593e5  mov     rbx, [rsp+1F0h+var_1B0]
0x1800593ea  test    rbx, rbx
0x1800593ed  jz      loc_18005955A
0x1800593f3  mov     [rsp+1F0h+lpString2], 0
0x1800593fc  mov     rax, [rbx]
0x1800593ff  mov     rdi, [rax+18h]
0x180059403  xor     ecx, ecx; pv
0x180059405  call    cs:__imp_CoTaskMemFree
0x18005940b  lea     r9, [rsp+1F0h+lpString2]
0x180059410  xor     r8d, r8d
0x180059413  mov     edx, 70004h
0x180059418  mov     rcx, rbx
0x18005941b  mov     rax, rdi
0x18005941e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059423  test    eax, eax
0x180059425  js      loc_18005954F
0x18005942b  mov     [rsp+1F0h+bIgnoreCase], r14d; bIgnoreCase
0x180059430  or      ebx, 0FFFFFFFFh
0x180059433  mov     r9d, ebx; cchCount2
0x180059436  mov     r8, [rsp+1F0h+lpString2]; lpString2
0x18005943b  mov     edx, ebx; cchCount1
0x18005943d  lea     rcx, String1; "Unknown"
0x180059444  call    cs:__imp_CompareStringOrdinal
0x18005944a  cmp     eax, 2
0x18005944d  jz      loc_18005954C
0x180059453  mov     [rsp+1F0h+bIgnoreCase], r14d; bIgnoreCase
0x180059458  mov     r9d, ebx; cchCount2
0x18005945b  mov     r8, [rsp+1F0h+lpString2]; lpString2
0x180059460  mov     edx, ebx; cchCount1
0x180059462  lea     rcx, aUndecided; "Undecided"
0x180059469  call    cs:__imp_CompareStringOrdinal
0x18005946f  cmp     eax, 2
0x180059472  jz      loc_18005954C
0x180059478  xor     sil, sil
0x18005947b  mov     [rsp+1F0h+pv], 0
0x180059484  mov     rdi, [rsp+1F0h+var_1B0]
0x180059489  mov     rax, [rdi]
0x18005948c  mov     rbx, [rax+18h]
0x180059490  xor     ecx, ecx; pv
0x180059492  call    cs:__imp_CoTaskMemFree
0x180059498  lea     r9, [rsp+1F0h+pv]
0x18005949d  xor     r8d, r8d
0x1800594a0  mov     edx, 2170008h
0x1800594a5  mov     rcx, rdi
0x1800594a8  mov     rax, rbx
0x1800594ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594b0  test    eax, eax
0x1800594b2  js      short loc_180059527
0x1800594b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800594bb  mov     edi, 20h ; ' '
0x1800594c0  mov     ecx, edi; unsigned __int64
0x1800594c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800594c7  mov     rbx, rax
0x1800594ca  test    rax, rax
0x1800594cd  jz      short loc_180059527
0x1800594cf  mov     qword ptr [rax], 0
0x1800594d6  mov     rcx, [rsp+1F0h+lpString2]
0x1800594db  mov     [rax+8], rcx
0x1800594df  mov     [rsp+1F0h+lpString2], 0
0x1800594e8  mov     rcx, [rsp+1F0h+pv]
0x1800594ed  mov     [rax+10h], rcx
0x1800594f1  mov     [rsp+1F0h+pv], 0
0x1800594fa  mov     [rax+18h], sil
0x1800594fe  mov     r8, r12; unsigned __int16 *
0x180059501  mov     rdx, r15; punk
0x180059504  mov     rcx, rax; this
0x180059507  call    ?CreateAndShow@CAssociationWarning@@QEAAJPEAUIDisableWindow@@PEBG@Z; CAssociationWarning::CreateAndShow(IDisableWindow *,ushort const *)
0x18005950c  test    eax, eax
0x18005950e  js      short loc_180059514
0x180059510  mov     sil, [rbx+18h]
0x180059514  mov     rcx, rbx; this
0x180059517  call    ??1CAssociationWarning@@QEAA@XZ; CAssociationWarning::~CAssociationWarning(void)
0x18005951c  mov     rdx, rdi; struct std::nothrow_t *
0x18005951f  mov     rcx, rbx; void *
0x180059522  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180059527  mov     rcx, [rsp+1F0h+pv]; pv
0x18005952c  call    cs:__imp_CoTaskMemFree
0x180059532  jmp     short loc_18005954F
0x180059534  movzx   esi, sil
0x180059538  cmp     eax, 80070483h
0x18005953d  mov     r14d, 1
0x180059543  cmovz   esi, r14d
0x180059547  jmp     loc_1800593E5
0x18005954c  mov     sil, r14b
0x18005954f  mov     rcx, [rsp+1F0h+lpString2]; pv
0x180059554  call    cs:__imp_CoTaskMemFree
0x18005955a  mov     dl, sil; bool
0x18005955d  lea     rcx, [rsp+1F0h+var_190]; this
0x180059562  call    ?Stop@AssociationWarningPrompt@LauncherDesktopProvider@@QEAAX_N@Z; LauncherDesktopProvider::AssociationWarningPrompt::Stop(bool)
0x180059567  neg     sil
0x18005956a  sbb     ebx, ebx
0x18005956c  not     ebx
0x18005956e  and     ebx, 80070005h
0x180059574  lea     rcx, [rsp+1F0h+var_1B8]
0x180059579  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005957e  lea     rcx, [rsp+1F0h+var_1B0]
0x180059583  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059588  lea     rcx, [rsp+1F0h+var_1A8]
0x18005958d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180059592  lea     rcx, [rsp+1F0h+var_190]; this
0x180059597  call    ??1AssociationWarningPrompt@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::AssociationWarningPrompt::~AssociationWarningPrompt(void)
0x18005959c  mov     eax, ebx
0x18005959e  mov     rcx, [rbp+0F0h+var_40]
0x1800595a5  xor     rcx, rsp; StackCookie
0x1800595a8  call    __security_check_cookie
0x1800595ad  add     rsp, 1C0h
0x1800595b4  pop     r15
0x1800595b6  pop     r14
0x1800595b8  pop     r12
0x1800595ba  pop     rdi
0x1800595bb  pop     rsi
0x1800595bc  pop     rbx
0x1800595bd  pop     rbp
0x1800595be  retn
```
