# CApplicationPreLaunchNotifications::NotifyDefaultAppForProtocol(ushort const *,bool)

- ea: `0x18002433c`
- end: `0x18002472e`
- name: `?NotifyDefaultAppForProtocol@CApplicationPreLaunchNotifications@@AEAAJPEBG_N@Z`
- size: `1010`
- prototype: `int(CApplicationPreLaunchNotifications *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024274`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x18002433c`
- `0x180052980`
- `0x1800a5cbc`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002451f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002451f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800243a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800243a0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002441f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002441f`

## string_xrefs

- `0x1800243f4`: `Windows.Internal.StateRepository.Protocol`

## pseudocode

```c
__int64 __fastcall CApplicationPreLaunchNotifications::NotifyDefaultAppForProtocol(
        CApplicationPreLaunchNotifications *this,
        unsigned __int16 *a2,
        bool a3)
{
  HRESULT ActivationFactory; // edi
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rdi
  int v14; // r14d
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int16 *v17; // rcx
  signed __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v31; // rbx
  const unsigned __int16 *v32; // rax
  CApplicationPreLaunchNotifications *v33; // rcx
  unsigned int v34; // eax
  unsigned int v36; // [rsp+30h] [rbp-59h] BYREF
  __int64 v37; // [rsp+38h] [rbp-51h] BYREF
  HSTRING string; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  __int64 v40; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v41; // [rsp+58h] [rbp-31h] BYREF
  __int64 v42; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v43; // [rsp+68h] [rbp-21h] BYREF
  __int64 v44; // [rsp+70h] [rbp-19h] BYREF
  __int64 v45; // [rsp+78h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  __int64 v49; // [rsp+A8h] [rbp+1Fh]

  string = (HSTRING)a2;
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  ActivationFactory = CoCreateInstance(
                        &GUID_591209c7_767b_42b2_9fba_44ee4615f2c7,
                        0,
                        3u,
                        &GUID_4e530b0a_e611_4c77_a3ac_9031d022281b,
                        &ppv);
  if ( ActivationFactory >= 0 )
  {
    pv = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          a2,
                          1);
    if ( ActivationFactory >= 0 )
    {
      v45 = 0;
      v49 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.StateRepository.Protocol",
        0x2Au,
        0x29u);
      v6 = v49;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
      ActivationFactory = RoGetActivationFactory(v6, &GUID_0f2f217e_7957_4262_a74c_df03d9e9e9c1, &v45);
      if ( ActivationFactory >= 0 )
      {
        v7 = v45;
        v40 = 0;
        v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v45 + 200LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
        v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
        ActivationFactory = v8(v7, 0, *(_QWORD *)(v9 + 24), &v40);
        if ( ActivationFactory >= 0 )
        {
          v36 = 0;
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 56LL))(v40, &v36);
          if ( ActivationFactory >= 0 )
          {
            if ( v36 )
            {
              v10 = 0;
              while ( 1 )
              {
                v11 = v40;
                v37 = 0;
                v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 48LL);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
                ActivationFactory = v12(v11, v10, &v37);
                if ( ActivationFactory < 0 )
                  break;
                v13 = v37;
                string = 0;
                v14 = 0;
                v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 112LL);
                WindowsDeleteString(0);
                string = 0;
                ActivationFactory = v15(v13, &string);
                if ( ActivationFactory >= 0 )
                {
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  v17 = (unsigned __int16 *)pv;
                  v18 = (char *)StringRawBuffer - (_BYTE *)pv;
                  do
                  {
                    v19 = *(unsigned __int16 *)((char *)v17 + v18);
                    v20 = *v17 - v19;
                    if ( v20 )
                      break;
                    ++v17;
                  }
                  while ( v19 );
                  if ( !v20 )
                  {
                    v21 = v37;
                    v44 = 0;
                    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 88LL);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                    ActivationFactory = v22(v21, &v44);
                    if ( ActivationFactory >= 0 )
                    {
                      v23 = v44;
                      v39 = 0;
                      v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 72LL);
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v39);
                      ActivationFactory = v24(v23, &v39);
                      if ( ActivationFactory >= 0 )
                      {
                        v25 = v39;
                        v43 = 0;
                        v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 232LL);
                        WindowsDeleteString(0);
                        v43 = 0;
                        ActivationFactory = v26(v25, &v43);
                        if ( ActivationFactory >= 0 )
                        {
                          v27 = v39;
                          v42 = 0;
                          v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 72LL);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                          ActivationFactory = v28(v27, &v42);
                          if ( ActivationFactory >= 0 )
                          {
                            v29 = v42;
                            v41 = 0;
                            v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 112LL);
                            WindowsDeleteString(0);
                            v41 = 0;
                            ActivationFactory = v30(v29, &v41);
                            if ( ActivationFactory >= 0 )
                            {
                              v31 = WindowsGetStringRawBuffer(v41, 0);
                              v32 = WindowsGetStringRawBuffer(v43, 0);
                              CApplicationPreLaunchNotifications::NotifyDefaultApp(v33, v32, v31, a3);
                              v14 = 1;
                            }
                            WindowsDeleteString(v41);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
                        }
                        WindowsDeleteString(v43);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v39);
                    }
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                  }
                }
                WindowsDeleteString(string);
                if ( ActivationFactory < 0 || v14 )
                  break;
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
                v34 = v36;
                if ( ++v10 >= v36 )
                  goto LABEL_30;
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
              v34 = v36;
LABEL_30:
              if ( v10 == v34 )
                ActivationFactory = -2147024846;
            }
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002433c  mov     [rsp-8+arg_0], rbx
0x180024341  mov     [rsp-8+arg_18], rsi
0x180024346  push    rbp
0x180024347  push    rdi
0x180024348  push    r12
0x18002434a  push    r14
0x18002434c  push    r15
0x18002434e  lea     rbp, [rsp-37h]
0x180024353  sub     rsp, 0C0h
0x18002435a  mov     rax, cs:__security_cookie
0x180024361  xor     rax, rsp
0x180024364  mov     [rbp+57h+var_30], rax
0x180024368  xor     r12d, r12d
0x18002436b  mov     [rbp+57h+string], rdx
0x18002436f  lea     rcx, [rbp+57h+var_60]
0x180024373  mov     [rbp+57h+var_60], r12
0x180024377  mov     r15b, r8b
0x18002437a  mov     rbx, rdx
0x18002437d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024382  lea     rax, [rbp+57h+var_60]
0x180024386  xor     edx, edx; pUnkOuter
0x180024388  lea     r9, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x18002438f  mov     [rsp+0E0h+ppv], rax; ppv
0x180024394  lea     r8d, [r12+3]; dwClsContext
0x180024399  lea     rcx, _GUID_591209c7_767b_42b2_9fba_44ee4615f2c7; rclsid
0x1800243a0  call    cs:__imp_CoCreateInstance
0x1800243a6  mov     edi, eax
0x1800243a8  test    eax, eax
0x1800243aa  js      loc_1800246FB
0x1800243b0  mov     rcx, [rbp+57h+var_60]
0x1800243b4  lea     rdx, [rbp+57h+pv]
0x1800243b8  mov     [rbp+57h+pv], r12
0x1800243bc  lea     r9d, [r12+1]
0x1800243c1  mov     [rsp+0E0h+ppv], rdx
0x1800243c6  mov     r8d, r9d
0x1800243c9  mov     rdx, rbx
0x1800243cc  mov     rax, [rcx]
0x1800243cf  mov     rax, [rax+18h]
0x1800243d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243d8  mov     edi, eax
0x1800243da  test    eax, eax
0x1800243dc  js      loc_1800246FB
0x1800243e2  lea     r9d, [r12+29h]; unsigned int
0x1800243e7  mov     [rbp+57h+var_68], r12
0x1800243eb  lea     r8d, [r12+2Ah]; unsigned int
0x1800243f0  mov     [rbp+57h+var_38], r12
0x1800243f4  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Protocol@@3QBGB; "Windows.Internal.StateRepository.Protoc"...
0x1800243fb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800243ff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024404  mov     rbx, [rbp+57h+var_38]
0x180024408  lea     rcx, [rbp+57h+var_68]
0x18002440c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024411  lea     r8, [rbp+57h+var_68]
0x180024415  mov     rcx, rbx
0x180024418  lea     rdx, _GUID_0f2f217e_7957_4262_a74c_df03d9e9e9c1
0x18002441f  call    cs:__imp_RoGetActivationFactory
0x180024425  mov     edi, eax
0x180024427  test    eax, eax
0x180024429  js      loc_1800246E8
0x18002442f  mov     rdi, [rbp+57h+var_68]
0x180024433  lea     rcx, [rbp+57h+var_90]
0x180024437  mov     [rbp+57h+var_90], r12
0x18002443b  mov     rax, [rdi]
0x18002443e  mov     rbx, [rax+0C8h]
0x180024445  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18002444a  lea     rdx, [rbp+57h+string]
0x18002444e  lea     rcx, [rbp+57h+hstringHeader]
0x180024452  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180024457  lea     r9, [rbp+57h+var_90]
0x18002445b  xor     edx, edx
0x18002445d  mov     rcx, rdi
0x180024460  mov     r8, [rax+18h]
0x180024464  mov     rax, rbx
0x180024467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002446c  mov     edi, eax
0x18002446e  test    eax, eax
0x180024470  js      loc_1800246DF
0x180024476  mov     rcx, [rbp+57h+var_90]
0x18002447a  lea     rdx, [rbp+57h+var_B0]
0x18002447e  mov     [rbp+57h+var_B0], r12d
0x180024482  mov     rax, [rcx]
0x180024485  mov     rax, [rax+38h]
0x180024489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002448e  mov     edi, eax
0x180024490  test    eax, eax
0x180024492  js      loc_1800246DF
0x180024498  mov     eax, [rbp+57h+var_B0]
0x18002449b  cmp     eax, 1
0x18002449e  jb      loc_1800246DF
0x1800244a4  mov     esi, r12d
0x1800244a7  test    eax, eax
0x1800244a9  jz      loc_1800246D5
0x1800244af  mov     rdi, [rbp+57h+var_90]
0x1800244b3  lea     rcx, [rbp+57h+var_A8]
0x1800244b7  mov     [rbp+57h+var_A8], r12
0x1800244bb  mov     rax, [rdi]
0x1800244be  mov     rbx, [rax+30h]
0x1800244c2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800244c7  lea     r8, [rbp+57h+var_A8]
0x1800244cb  mov     edx, esi
0x1800244cd  mov     rcx, rdi
0x1800244d0  mov     rax, rbx
0x1800244d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d8  mov     edi, eax
0x1800244da  test    eax, eax
0x1800244dc  js      loc_1800246C9
0x1800244e2  mov     rdi, [rbp+57h+var_A8]
0x1800244e6  xor     ecx, ecx; string
0x1800244e8  mov     [rbp+57h+string], r12
0x1800244ec  mov     r14d, r12d
0x1800244ef  mov     rax, [rdi]
0x1800244f2  mov     rbx, [rax+70h]
0x1800244f6  call    cs:__imp_WindowsDeleteString
0x1800244fc  lea     rdx, [rbp+57h+string]
0x180024500  mov     [rbp+57h+string], r12
0x180024504  mov     rcx, rdi
0x180024507  mov     rax, rbx
0x18002450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002450f  mov     edi, eax
0x180024511  test    eax, eax
0x180024513  js      loc_18002469E
0x180024519  mov     rcx, [rbp+57h+string]; string
0x18002451d  xor     edx, edx; length
0x18002451f  call    cs:__imp_WindowsGetStringRawBuffer
0x180024525  mov     rcx, [rbp+57h+pv]
0x180024529  sub     rax, rcx
0x18002452c  movzx   edx, word ptr [rcx]
0x18002452f  movzx   r8d, word ptr [rcx+rax]
0x180024534  sub     edx, r8d
0x180024537  jnz     short loc_180024542
0x180024539  add     rcx, 2
0x18002453d  test    r8d, r8d
0x180024540  jnz     short loc_18002452C
0x180024542  test    edx, edx
0x180024544  jnz     loc_18002469E
0x18002454a  mov     rdi, [rbp+57h+var_A8]
0x18002454e  lea     rcx, [rbp+57h+var_70]
0x180024552  mov     [rbp+57h+var_70], r12
0x180024556  mov     rax, [rdi]
0x180024559  mov     rbx, [rax+58h]
0x18002455d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024562  lea     rdx, [rbp+57h+var_70]
0x180024566  mov     rcx, rdi
0x180024569  mov     rax, rbx
0x18002456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024571  mov     edi, eax
0x180024573  test    eax, eax
0x180024575  js      loc_180024695
0x18002457b  mov     rdi, [rbp+57h+var_70]
0x18002457f  lea     rcx, [rbp+57h+var_98]
0x180024583  mov     [rbp+57h+var_98], r12
0x180024587  mov     rax, [rdi]
0x18002458a  mov     rbx, [rax+48h]
0x18002458e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024593  lea     rdx, [rbp+57h+var_98]
0x180024597  mov     rcx, rdi
0x18002459a  mov     rax, rbx
0x18002459d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245a2  mov     edi, eax
0x1800245a4  test    eax, eax
0x1800245a6  js      loc_18002468C
0x1800245ac  mov     rdi, [rbp+57h+var_98]
0x1800245b0  xor     ecx, ecx; string
0x1800245b2  mov     [rbp+57h+var_78], r12
0x1800245b6  mov     rax, [rdi]
0x1800245b9  mov     rbx, [rax+0E8h]
0x1800245c0  call    cs:__imp_WindowsDeleteString
0x1800245c6  lea     rdx, [rbp+57h+var_78]
0x1800245ca  mov     [rbp+57h+var_78], r12
0x1800245ce  mov     rcx, rdi
0x1800245d1  mov     rax, rbx
0x1800245d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245d9  mov     edi, eax
0x1800245db  test    eax, eax
0x1800245dd  js      loc_180024682
0x1800245e3  mov     rdi, [rbp+57h+var_98]
0x1800245e7  lea     rcx, [rbp+57h+var_80]
0x1800245eb  mov     [rbp+57h+var_80], r12
0x1800245ef  mov     rax, [rdi]
0x1800245f2  mov     rbx, [rax+48h]
0x1800245f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800245fb  lea     rdx, [rbp+57h+var_80]
0x1800245ff  mov     rcx, rdi
0x180024602  mov     rax, rbx
0x180024605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002460a  mov     edi, eax
0x18002460c  test    eax, eax
0x18002460e  js      short loc_180024679
0x180024610  mov     rdi, [rbp+57h+var_80]
0x180024614  xor     ecx, ecx; string
0x180024616  mov     [rbp+57h+var_88], r12
0x18002461a  mov     rax, [rdi]
0x18002461d  mov     rbx, [rax+70h]
0x180024621  call    cs:__imp_WindowsDeleteString
0x180024627  lea     rdx, [rbp+57h+var_88]
0x18002462b  mov     [rbp+57h+var_88], r12
0x18002462f  mov     rcx, rdi
0x180024632  mov     rax, rbx
0x180024635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463a  mov     edi, eax
0x18002463c  test    eax, eax
0x18002463e  js      short loc_18002466F
0x180024640  mov     rcx, [rbp+57h+var_88]; string
0x180024644  xor     edx, edx; length
0x180024646  call    cs:__imp_WindowsGetStringRawBuffer
0x18002464c  mov     rcx, [rbp+57h+var_78]; string
0x180024650  xor     edx, edx; length
0x180024652  mov     rbx, rax
0x180024655  call    cs:__imp_WindowsGetStringRawBuffer
0x18002465b  mov     r9b, r15b; bool
0x18002465e  mov     r8, rbx; unsigned __int16 *
0x180024661  mov     rdx, rax; unsigned __int16 *
0x180024664  call    ?NotifyDefaultApp@CApplicationPreLaunchNotifications@@AEAAXPEBG0_N@Z; CApplicationPreLaunchNotifications::NotifyDefaultApp(ushort const *,ushort const *,bool)
0x180024669  mov     r14d, 1
0x18002466f  mov     rcx, [rbp+57h+var_88]; string
0x180024673  call    cs:__imp_WindowsDeleteString
0x180024679  lea     rcx, [rbp+57h+var_80]
0x18002467d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024682  mov     rcx, [rbp+57h+var_78]; string
0x180024686  call    cs:__imp_WindowsDeleteString
0x18002468c  lea     rcx, [rbp+57h+var_98]
0x180024690  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024695  lea     rcx, [rbp+57h+var_70]
0x180024699  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18002469e  mov     rcx, [rbp+57h+string]; string
0x1800246a2  call    cs:__imp_WindowsDeleteString
0x1800246a8  test    edi, edi
0x1800246aa  js      short loc_1800246C9
0x1800246ac  test    r14d, r14d
0x1800246af  jnz     short loc_1800246C9
0x1800246b1  lea     rcx, [rbp+57h+var_A8]
0x1800246b5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800246ba  mov     eax, [rbp+57h+var_B0]
0x1800246bd  inc     esi
0x1800246bf  cmp     esi, eax
0x1800246c1  jb      loc_1800244AF
0x1800246c7  jmp     short loc_1800246D5
0x1800246c9  lea     rcx, [rbp+57h+var_A8]
0x1800246cd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800246d2  mov     eax, [rbp+57h+var_B0]
0x1800246d5  cmp     esi, eax
0x1800246d7  mov     ecx, 80070032h
0x1800246dc  cmovz   edi, ecx
0x1800246df  lea     rcx, [rbp+57h+var_90]
0x1800246e3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800246e8  mov     rcx, [rbp+57h+pv]; pv
0x1800246ec  call    cs:__imp_CoTaskMemFree
0x1800246f2  lea     rcx, [rbp+57h+var_68]
0x1800246f6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800246fb  lea     rcx, [rbp+57h+var_60]
0x1800246ff  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180024704  mov     eax, edi
0x180024706  mov     rcx, [rbp+57h+var_30]
0x18002470a  xor     rcx, rsp; StackCookie
0x18002470d  call    __security_check_cookie
0x180024712  lea     r11, [rsp+0E0h+var_20]
0x18002471a  mov     rbx, [r11+30h]
0x18002471e  mov     rsi, [r11+48h]
0x180024722  mov     rsp, r11
0x180024725  pop     r15
0x180024727  pop     r14
0x180024729  pop     r12
0x18002472b  pop     rdi
0x18002472c  pop     rbp
0x18002472d  retn
```
