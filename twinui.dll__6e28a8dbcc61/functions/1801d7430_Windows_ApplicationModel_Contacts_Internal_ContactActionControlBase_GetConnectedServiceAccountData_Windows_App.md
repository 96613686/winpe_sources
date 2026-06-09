# Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1801d7430`
- end: `0x1801d76b7`
- name: `?_GetConnectedServiceAccountData@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAPEAUHSTRING__@@33@Z`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801d6880`
- `0x1801d6a00`

## callees

- `0x18000b7e8`
- `0x180027ee4`
- `0x180036250`
- `0x1800b5e48`
- `0x1801c2540`
- `0x1801d7430`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1801d74e0`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1801d74e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d75e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d765e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d75e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d765e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d74b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d74b0`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(
        __int64 *a1,
        int a2,
        __int64 *a3,
        HSTRING *a4,
        HSTRING *a5,
        HSTRING *a6)
{
  HSTRING *v6; // r12
  HSTRING *v7; // r13
  __int64 (__fastcall *v12)(__int64 *, HSTRING *); // rbx
  int v13; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64 *, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64 *, HSTRING *); // rbx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  HSTRING v24; // rcx
  HSTRING v26; // [rsp+20h] [rbp-40h] BYREF
  __int64 v27; // [rsp+28h] [rbp-38h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR lpsz; // [rsp+40h] [rbp-20h] BYREF
  DWORD cchLength[2]; // [rsp+48h] [rbp-18h]
  __int64 v32; // [rsp+50h] [rbp-10h]
  HSTRING v33; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING v34; // [rsp+B8h] [rbp+58h] BYREF

  v6 = a5;
  v7 = a6;
  *a4 = 0;
  string = 0;
  *v6 = 0;
  *v7 = 0;
  v12 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a1 + 64);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(a1, &string);
  if ( v13 >= 0 )
  {
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v32 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &lpsz,
            StringRawBuffer,
            -1);
    if ( v13 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      CharLowerBuffW(lpsz, cchLength[0]);
      v33 = 0;
      v13 = Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(
              &v33,
              &lpsz);
      if ( v13 >= 0 )
      {
        v15 = *a3;
        LOBYTE(a5) = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING **))(v15 + 64))(a3, v33, &a5);
        if ( v13 >= 0 )
        {
          if ( (_BYTE)a5 )
          {
            v16 = *a3;
            v28 = 0;
            v17 = *(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v16 + 48);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
            v13 = v17(a3, v33, &v28);
            if ( v13 >= 0 )
            {
              v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
              v27 = 0;
              v19 = **v28;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v27);
              v13 = v19(v18, &GUID_d703fff4_f2eb_4ee0_9178_42dacf97375f, &v27);
              if ( v13 >= 0 )
              {
                LODWORD(a6) = 0;
                v13 = (*(__int64 (__fastcall **)(__int64, HSTRING **))(*(_QWORD *)v27 + 64LL))(v27, &a6);
                if ( v13 >= 0 && (a2 & (unsigned int)a6) != 0 )
                {
                  v20 = *a1;
                  v26 = 0;
                  v21 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v20 + 48);
                  WindowsDeleteString(0);
                  v26 = 0;
                  v13 = v21(a1, &v26);
                  if ( v13 >= 0 )
                  {
                    v22 = v27;
                    v34 = 0;
                    v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 56LL);
                    WindowsDeleteString(0);
                    v34 = 0;
                    v13 = v23(v22, &v34);
                    if ( v13 < 0 )
                    {
                      v24 = v34;
                    }
                    else
                    {
                      v24 = 0;
                      *a4 = v33;
                      *v6 = v26;
                      *v7 = v34;
                      v33 = 0;
                      v26 = 0;
                      v34 = 0;
                    }
                    WindowsDeleteString(v24);
                  }
                  WindowsDeleteString(v26);
                }
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v27);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
          }
        }
      }
      WindowsDeleteString(v33);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  WindowsDeleteString(string);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801d7430  mov     [rsp-38h+arg_8], rbx
0x1801d7435  push    rbp
0x1801d7436  push    rsi
0x1801d7437  push    rdi
0x1801d7438  push    r12
0x1801d743a  push    r13
0x1801d743c  push    r14
0x1801d743e  push    r15
0x1801d7440  mov     rbp, rsp
0x1801d7443  sub     rsp, 60h
0x1801d7447  mov     r12, [rbp+arg_20]
0x1801d744b  xor     eax, eax
0x1801d744d  mov     r13, [rbp+arg_28]
0x1801d7451  mov     rsi, rcx
0x1801d7454  mov     [r9], rax
0x1801d7457  mov     r15, r9
0x1801d745a  mov     [rbp+string], rax
0x1801d745e  mov     rdi, r8
0x1801d7461  mov     [r12], rax
0x1801d7465  mov     r14d, edx
0x1801d7468  mov     [r13+0], rax
0x1801d746c  mov     rax, [rcx]
0x1801d746f  xor     ecx, ecx; string
0x1801d7471  mov     rbx, [rax+40h]
0x1801d7475  call    cs:__imp_WindowsDeleteString
0x1801d747b  lea     rdx, [rbp+string]
0x1801d747f  mov     [rbp+string], 0
0x1801d7487  mov     rcx, rsi
0x1801d748a  mov     rax, rbx
0x1801d748d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7492  mov     ebx, eax
0x1801d7494  xor     eax, eax
0x1801d7496  test    ebx, ebx
0x1801d7498  js      loc_1801D7693
0x1801d749e  mov     rcx, [rbp+string]; string
0x1801d74a2  xor     edx, edx; length
0x1801d74a4  mov     [rbp+lpsz], rax
0x1801d74a8  mov     qword ptr [rbp+cchLength], rax
0x1801d74ac  mov     [rbp+var_10], rax
0x1801d74b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d74b6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801d74ba  lea     rcx, [rbp+lpsz]
0x1801d74be  mov     rdx, rax
0x1801d74c1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801d74c6  mov     ebx, eax
0x1801d74c8  test    eax, eax
0x1801d74ca  js      loc_1801D768A
0x1801d74d0  lea     rcx, [rbp+lpsz]
0x1801d74d4  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1801d74d9  mov     edx, [rbp+cchLength]; cchLength
0x1801d74dc  mov     rcx, [rbp+lpsz]; lpsz
0x1801d74e0  call    cs:__imp_CharLowerBuffW
0x1801d74e6  lea     rdx, [rbp+lpsz]
0x1801d74ea  mov     [rbp+arg_0], 0
0x1801d74f2  lea     rcx, [rbp+arg_0]
0x1801d74f6  call    ??$Set@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x1801d74fb  mov     ebx, eax
0x1801d74fd  test    eax, eax
0x1801d74ff  js      loc_1801D7680
0x1801d7505  mov     rax, [rdi]
0x1801d7508  lea     r8, [rbp+arg_20]
0x1801d750c  mov     rdx, [rbp+arg_0]
0x1801d7510  mov     rcx, rdi
0x1801d7513  mov     byte ptr [rbp+arg_20], 0
0x1801d7517  mov     rax, [rax+40h]
0x1801d751b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7520  mov     ebx, eax
0x1801d7522  test    eax, eax
0x1801d7524  js      loc_1801D7680
0x1801d752a  cmp     byte ptr [rbp+arg_20], 0
0x1801d752e  jz      loc_1801D7680
0x1801d7534  mov     rax, [rdi]
0x1801d7537  lea     rcx, [rbp+var_30]
0x1801d753b  mov     [rbp+var_30], 0
0x1801d7543  mov     rbx, [rax+30h]
0x1801d7547  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d754c  mov     rdx, [rbp+arg_0]
0x1801d7550  lea     r8, [rbp+var_30]
0x1801d7554  mov     rcx, rdi
0x1801d7557  mov     rax, rbx
0x1801d755a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d755f  mov     ebx, eax
0x1801d7561  test    eax, eax
0x1801d7563  js      loc_1801D7677
0x1801d7569  mov     rbx, [rbp+var_30]
0x1801d756d  lea     rcx, [rbp+var_38]
0x1801d7571  mov     [rbp+var_38], 0
0x1801d7579  mov     rax, [rbx]
0x1801d757c  mov     rdi, [rax]
0x1801d757f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d7584  lea     r8, [rbp+var_38]
0x1801d7588  mov     rcx, rbx
0x1801d758b  lea     rdx, _GUID_d703fff4_f2eb_4ee0_9178_42dacf97375f
0x1801d7592  mov     rax, rdi
0x1801d7595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d759a  mov     ebx, eax
0x1801d759c  test    eax, eax
0x1801d759e  js      loc_1801D766E
0x1801d75a4  mov     rcx, [rbp+var_38]
0x1801d75a8  lea     rdx, [rbp+arg_28]
0x1801d75ac  mov     dword ptr [rbp+arg_28], 0
0x1801d75b3  mov     rax, [rcx]
0x1801d75b6  mov     rax, [rax+40h]
0x1801d75ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d75bf  mov     ebx, eax
0x1801d75c1  test    eax, eax
0x1801d75c3  js      loc_1801D766E
0x1801d75c9  test    dword ptr [rbp+arg_28], r14d
0x1801d75cd  jbe     loc_1801D766E
0x1801d75d3  mov     rax, [rsi]
0x1801d75d6  xor     r14d, r14d
0x1801d75d9  xor     ecx, ecx; string
0x1801d75db  mov     [rbp+var_40], r14
0x1801d75df  mov     rbx, [rax+30h]
0x1801d75e3  call    cs:__imp_WindowsDeleteString
0x1801d75e9  lea     rdx, [rbp+var_40]
0x1801d75ed  mov     [rbp+var_40], r14
0x1801d75f1  mov     rcx, rsi
0x1801d75f4  mov     rax, rbx
0x1801d75f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d75fc  mov     ebx, eax
0x1801d75fe  test    eax, eax
0x1801d7600  js      short loc_1801D7664
0x1801d7602  mov     rdi, [rbp+var_38]
0x1801d7606  xor     ecx, ecx; string
0x1801d7608  mov     [rbp+arg_18], r14
0x1801d760c  mov     rax, [rdi]
0x1801d760f  mov     rbx, [rax+38h]
0x1801d7613  call    cs:__imp_WindowsDeleteString
0x1801d7619  lea     rdx, [rbp+arg_18]
0x1801d761d  mov     [rbp+arg_18], r14
0x1801d7621  mov     rcx, rdi
0x1801d7624  mov     rax, rbx
0x1801d7627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d762c  mov     ebx, eax
0x1801d762e  test    eax, eax
0x1801d7630  js      short loc_1801D765A
0x1801d7632  mov     rax, [rbp+arg_0]
0x1801d7636  mov     ecx, r14d
0x1801d7639  mov     [r15], rax
0x1801d763c  mov     rax, [rbp+var_40]
0x1801d7640  mov     [r12], rax
0x1801d7644  mov     rax, [rbp+arg_18]
0x1801d7648  mov     [r13+0], rax
0x1801d764c  mov     [rbp+arg_0], r14
0x1801d7650  mov     [rbp+var_40], r14
0x1801d7654  mov     [rbp+arg_18], rcx
0x1801d7658  jmp     short loc_1801D765E
0x1801d765a  mov     rcx, [rbp+arg_18]; string
0x1801d765e  call    cs:__imp_WindowsDeleteString
0x1801d7664  mov     rcx, [rbp+var_40]; string
0x1801d7668  call    cs:__imp_WindowsDeleteString
0x1801d766e  lea     rcx, [rbp+var_38]
0x1801d7672  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d7677  lea     rcx, [rbp+var_30]
0x1801d767b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d7680  mov     rcx, [rbp+arg_0]; string
0x1801d7684  call    cs:__imp_WindowsDeleteString
0x1801d768a  lea     rcx, [rbp+lpsz]
0x1801d768e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801d7693  mov     rcx, [rbp+string]; string
0x1801d7697  call    cs:__imp_WindowsDeleteString
0x1801d769d  mov     eax, ebx
0x1801d769f  mov     rbx, [rsp+60h+arg_8]
0x1801d76a7  add     rsp, 60h
0x1801d76ab  pop     r15
0x1801d76ad  pop     r14
0x1801d76af  pop     r13
0x1801d76b1  pop     r12
0x1801d76b3  pop     rdi
0x1801d76b4  pop     rsi
0x1801d76b5  pop     rbp
0x1801d76b6  retn
```
