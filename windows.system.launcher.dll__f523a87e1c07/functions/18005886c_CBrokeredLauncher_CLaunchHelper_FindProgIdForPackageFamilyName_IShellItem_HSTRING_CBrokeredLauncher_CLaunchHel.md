# CBrokeredLauncher::CLaunchHelper::_FindProgIdForPackageFamilyName(IShellItem *,HSTRING__ *,CBrokeredLauncher::CLaunchHelper::AssocStatus *)

- ea: `0x18005886c`
- end: `0x180058c68`
- name: `?_FindProgIdForPackageFamilyName@CLaunchHelper@CBrokeredLauncher@@AEAA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEAUIShellItem@@PEAUHSTRING__@@PEAW4AssocStatus@12@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053f18`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18002cec0`
- `0x18003f59c`
- `0x18004966c`
- `0x18005863c`
- `0x18005886c`
- `0x180058c70`
- `0x180065128`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058aa6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058b67`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058b67`

## string_xrefs

- `0x180058921`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058b78`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058bb5`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058bd7`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180058c07`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall CBrokeredLauncher::CLaunchHelper::_FindProgIdForPackageFamilyName(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        HSTRING a4,
        _DWORD *a5)
{
  __int64 (__fastcall *v8)(__int64, _QWORD, const GUID *, GUID *); // rbx
  unsigned int v9; // eax
  CBrokeredLauncher::CLaunchHelper *v10; // rcx
  char v11; // al
  char ShouldRedirectLegacyBrowserRequest; // r15
  __int64 v13; // rdi
  unsigned int (__fastcall *v14)(__int64, __int64, _QWORD); // rbx
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v17; // rbx
  int (__fastcall *v18)(__int64, HSTRING_HEADER *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  CBrokeredLauncher::CLaunchHelper *v20; // rcx
  int (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v23; // rdi
  int (__fastcall *v24)(__int64, _QWORD *); // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v28; // rbx
  int ActivationFactory; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  _BYTE v34[8]; // [rsp+30h] [rbp-41h] BYREF
  int (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-39h] BYREF
  __int64 v36; // [rsp+40h] [rbp-31h] BYREF
  __int64 v37; // [rsp+48h] [rbp-29h] BYREF
  int v38[2]; // [rsp+50h] [rbp-21h] BYREF
  int v39; // [rsp+58h] [rbp-19h]
  _QWORD *v40; // [rsp+60h] [rbp-11h]
  HSTRING_HEADER pv; // [rsp+68h] [rbp-9h] BYREF
  __int64 v42; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v40 = a2;
  *a5 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v39 = 1;
  *(_QWORD *)v38 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)a3 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
  v9 = v8(a3, 0, &BHID_EnumAssocHandlers, &GUID_973810ae_9599_4b88_9e4d_6ee98c9552da);
  v10 = (CBrokeredLauncher::CLaunchHelper *)v9;
  if ( (int)(v9 + 0x80000000) < 0 || (v11 = 1, (_DWORD)v10 == -2147023741) )
    v11 = 0;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA7F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v10,
      (int)v38);
  if ( (int)v10 >= 0 )
  {
    ShouldRedirectLegacyBrowserRequest = CBrokeredLauncher::CLaunchHelper::ShouldRedirectLegacyBrowserRequest(v10, a4);
    v35 = 0;
    while ( 1 )
    {
      v13 = *(_QWORD *)v38;
      v14 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(**(_QWORD **)v38 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      if ( v14(v13, 1, &v35) )
        break;
      v37 = 0;
      memset(&pv, 0, sizeof(pv));
      v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
      v16 = **v35;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
      if ( v16(v15, &GUID_36db0196_9665_46d1_9ba7_d3709eecf9ed, &v37) >= 0 )
      {
        v17 = v37;
        v18 = *(int (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v37 + 32LL);
        if ( pv.Reserved.Reserved1 )
        {
          CoTaskMemFree(pv.Reserved.Reserved1);
          pv.Reserved.Reserved1 = 0;
        }
        *(_QWORD *)&pv.Reserved.Reserved2[8] = -1;
        *(_QWORD *)&pv.Reserved.Reserved2[16] = -1;
        if ( v18(v17, &pv) >= 0 )
        {
          v36 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
          if ( CBrokeredLauncher::CLaunchHelper::IsAumIdForPackageFamily(
                 v20,
                 (const unsigned __int16 *)pv.Reserved.Reserved1,
                 StringRawBuffer,
                 ShouldRedirectLegacyBrowserRequest) )
          {
            v21 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
            v22 = **v35;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
            if ( v22(v21, &GUID_71e806fb_8dee_46fc_bf8c_7748a8a1ae13, &v36) >= 0 )
            {
              v23 = v36;
              v24 = *(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v36 + 32LL);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a2);
              a2[1] = -1;
              a2[2] = -1;
              if ( v24(v23, a2) >= 0 )
              {
                *a5 = 3;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
                Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
                break;
              }
            }
          }
          v25 = v36;
          if ( v36 )
          {
            v36 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
      }
      if ( pv.Reserved.Reserved1 )
      {
        CoTaskMemFree(pv.Reserved.Reserved1);
        pv.Reserved.Reserved1 = 0;
      }
      *(_OWORD *)&pv.Reserved.Reserved2[8] = 0u;
      v26 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
    }
    v27 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
    }
  }
  if ( !*a2 || !*(_WORD *)*a2 )
  {
    v35 = 0;
    v42 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &pv,
      L"Windows.Internal.StateRepository.PackageFamily",
      0x2Fu,
      0x2Eu);
    v28 = v42;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
    ActivationFactory = RoGetActivationFactory(v28, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v35);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA2,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v38);
    v34[0] = 0;
    v30 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, HSTRING, _BYTE *))(*v35)[23])(
            v35,
            0,
            a4,
            v34);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v30,
        (int)v38);
    if ( v34[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAAC,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)0x80070483LL,
        (int)v38);
    v31 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            a2,
            L"Unknown",
            -1);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v31,
        (int)v38);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
  }
  v32 = *(_QWORD *)v38;
  if ( *(_QWORD *)v38 )
  {
    *(_QWORD *)v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return a2;
}

```

## disassembly

```asm
0x18005886c  mov     [rsp-8+arg_0], rbx
0x180058871  push    rbp
0x180058872  push    rsi
0x180058873  push    rdi
0x180058874  push    r12
0x180058876  push    r13
0x180058878  push    r14
0x18005887a  push    r15
0x18005887c  lea     rbp, [rsp-1Fh]
0x180058881  sub     rsp, 90h
0x180058888  mov     rax, cs:__security_cookie
0x18005888f  xor     rax, rsp
0x180058892  mov     [rbp+4Fh+var_38], rax
0x180058896  mov     r14, r9
0x180058899  mov     rdi, r8
0x18005889c  mov     rsi, rdx
0x18005889f  mov     [rbp+4Fh+var_60], rdx
0x1800588a3  mov     r12, [rbp+4Fh+arg_20]
0x1800588a7  xor     r13d, r13d
0x1800588aa  mov     [rbp+4Fh+var_68], r13d
0x1800588ae  mov     [r12], r13d
0x1800588b2  mov     [rdx], r13
0x1800588b5  mov     [rdx+8], r13
0x1800588b9  mov     [rdx+10h], r13
0x1800588bd  mov     [rbp+4Fh+var_68], 1
0x1800588c4  mov     qword ptr [rbp+4Fh+var_70], r13
0x1800588c8  mov     rax, [r8]
0x1800588cb  mov     rbx, [rax+18h]
0x1800588cf  lea     rcx, [rbp+4Fh+var_70]
0x1800588d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800588d8  lea     rax, [rbp+4Fh+var_70]
0x1800588dc  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800588e1  lea     r9, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da
0x1800588e8  lea     r8, BHID_EnumAssocHandlers
0x1800588ef  xor     edx, edx
0x1800588f1  mov     rcx, rdi
0x1800588f4  mov     rax, rbx
0x1800588f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588fc  mov     ecx, eax; this
0x1800588fe  mov     edx, 80000000h
0x180058903  add     eax, edx
0x180058905  test    edx, eax
0x180058907  jnz     short loc_180058913
0x180058909  cmp     ecx, 80070483h
0x18005890f  mov     al, 1
0x180058911  jnz     short loc_180058916
0x180058913  mov     al, r13b
0x180058916  mov     r10, [rbp+57h]
0x18005891a  test    al, al
0x18005891c  jz      short loc_180058936
0x18005891e  mov     r9d, ecx; char *
0x180058921  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058928  mov     edx, 0A7Fh; void *
0x18005892d  mov     rcx, r10; this
0x180058930  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058936  test    ecx, ecx
0x180058938  js      loc_180058B17
0x18005893e  mov     rdx, r14; HSTRING
0x180058941  call    ?ShouldRedirectLegacyBrowserRequest@CLaunchHelper@CBrokeredLauncher@@AEAA_NPEAUHSTRING__@@@Z; CBrokeredLauncher::CLaunchHelper::ShouldRedirectLegacyBrowserRequest(HSTRING__ *)
0x180058946  mov     r15b, al
0x180058949  mov     [rbp+4Fh+var_88], r13
0x18005894d  mov     rdi, qword ptr [rbp+4Fh+var_70]
0x180058951  mov     rax, [rdi]
0x180058954  mov     rbx, [rax+18h]
0x180058958  lea     rcx, [rbp+4Fh+var_88]
0x18005895c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058961  xor     r9d, r9d
0x180058964  lea     r8, [rbp+4Fh+var_88]
0x180058968  lea     edx, [r9+1]
0x18005896c  mov     rcx, rdi
0x18005896f  mov     rax, rbx
0x180058972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058977  test    eax, eax
0x180058979  jnz     loc_180058AFD
0x18005897f  mov     [rbp+4Fh+var_78], r13
0x180058983  mov     [rbp+4Fh+pv], r13
0x180058987  mov     [rbp+4Fh+var_50], r13
0x18005898b  mov     [rbp+4Fh+var_48], r13
0x18005898f  mov     rbx, [rbp+4Fh+var_88]
0x180058993  mov     rax, [rbx]
0x180058996  mov     rdi, [rax]
0x180058999  lea     rcx, [rbp+4Fh+var_78]
0x18005899d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800589a2  lea     r8, [rbp+4Fh+var_78]
0x1800589a6  lea     rdx, _GUID_36db0196_9665_46d1_9ba7_d3709eecf9ed
0x1800589ad  mov     rcx, rbx
0x1800589b0  mov     rax, rdi
0x1800589b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589b8  nop
0x1800589b9  test    eax, eax
0x1800589bb  js      loc_180058A9D
0x1800589c1  mov     rbx, [rbp+4Fh+var_78]
0x1800589c5  mov     rax, [rbx]
0x1800589c8  mov     rdi, [rax+20h]
0x1800589cc  mov     rcx, [rbp+4Fh+pv]; pv
0x1800589d0  test    rcx, rcx
0x1800589d3  jz      short loc_1800589DF
0x1800589d5  call    cs:__imp_CoTaskMemFree
0x1800589db  mov     [rbp+4Fh+pv], r13
0x1800589df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800589e3  mov     [rbp+4Fh+var_50], rax
0x1800589e7  mov     [rbp+4Fh+var_48], rax
0x1800589eb  lea     rdx, [rbp+4Fh+pv]
0x1800589ef  mov     rcx, rbx
0x1800589f2  mov     rax, rdi
0x1800589f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589fa  test    eax, eax
0x1800589fc  js      loc_180058A9D
0x180058a02  mov     [rbp+4Fh+var_80], r13
0x180058a06  xor     edx, edx; length
0x180058a08  mov     rcx, r14; string
0x180058a0b  call    cs:__imp_WindowsGetStringRawBuffer
0x180058a11  mov     r9b, r15b; bool
0x180058a14  mov     r8, rax; unsigned __int16 *
0x180058a17  mov     rdx, [rbp+4Fh+pv]; unsigned __int16 *
0x180058a1b  call    ?IsAumIdForPackageFamily@CLaunchHelper@CBrokeredLauncher@@AEAA_NPEBG0_N@Z; CBrokeredLauncher::CLaunchHelper::IsAumIdForPackageFamily(ushort const *,ushort const *,bool)
0x180058a20  test    al, al
0x180058a22  jz      short loc_180058A83
0x180058a24  mov     rbx, [rbp+4Fh+var_88]
0x180058a28  mov     rax, [rbx]
0x180058a2b  mov     rdi, [rax]
0x180058a2e  lea     rcx, [rbp+4Fh+var_80]
0x180058a32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058a37  lea     r8, [rbp+4Fh+var_80]
0x180058a3b  lea     rdx, _GUID_71e806fb_8dee_46fc_bf8c_7748a8a1ae13
0x180058a42  mov     rcx, rbx
0x180058a45  mov     rax, rdi
0x180058a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a4d  nop
0x180058a4e  test    eax, eax
0x180058a50  js      short loc_180058A83
0x180058a52  mov     rdi, [rbp+4Fh+var_80]
0x180058a56  mov     rax, [rdi]
0x180058a59  mov     rbx, [rax+20h]
0x180058a5d  mov     rcx, rsi
0x180058a60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180058a65  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058a69  mov     [rsi+8], rax
0x180058a6d  mov     [rsi+10h], rax
0x180058a71  mov     rdx, rsi
0x180058a74  mov     rcx, rdi
0x180058a77  mov     rax, rbx
0x180058a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a7f  test    eax, eax
0x180058a81  jns     short loc_180058AD7
0x180058a83  mov     rcx, [rbp+4Fh+var_80]
0x180058a87  test    rcx, rcx
0x180058a8a  jz      short loc_180058A9D
0x180058a8c  mov     [rbp+4Fh+var_80], r13
0x180058a90  mov     rax, [rcx]
0x180058a93  mov     rax, [rax+10h]
0x180058a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a9c  nop
0x180058a9d  mov     rcx, [rbp+4Fh+pv]; pv
0x180058aa1  test    rcx, rcx
0x180058aa4  jz      short loc_180058AB0
0x180058aa6  call    cs:__imp_CoTaskMemFree
0x180058aac  mov     [rbp+4Fh+pv], r13
0x180058ab0  mov     [rbp+4Fh+var_50], r13
0x180058ab4  mov     [rbp+4Fh+var_48], r13
0x180058ab8  mov     rcx, [rbp+4Fh+var_78]
0x180058abc  test    rcx, rcx
0x180058abf  jz      short loc_180058AD2
0x180058ac1  mov     [rbp+4Fh+var_78], r13
0x180058ac5  mov     rax, [rcx]
0x180058ac8  mov     rax, [rax+10h]
0x180058acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ad1  nop
0x180058ad2  jmp     loc_18005894D
0x180058ad7  mov     dword ptr [r12], 3
0x180058adf  lea     rcx, [rbp+4Fh+var_80]
0x180058ae3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058ae8  nop
0x180058ae9  lea     rcx, [rbp+4Fh+pv]
0x180058aed  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180058af2  nop
0x180058af3  lea     rcx, [rbp+4Fh+var_78]
0x180058af7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180058afc  nop
0x180058afd  mov     rcx, [rbp+4Fh+var_88]
0x180058b01  test    rcx, rcx
0x180058b04  jz      short loc_180058B17
0x180058b06  mov     [rbp+4Fh+var_88], r13
0x180058b0a  mov     rax, [rcx]
0x180058b0d  mov     rax, [rax+10h]
0x180058b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b16  nop
0x180058b17  mov     rax, [rsi]
0x180058b1a  test    rax, rax
0x180058b1d  jz      short loc_180058B29
0x180058b1f  cmp     [rax], r13w
0x180058b23  jnz     loc_180058C23
0x180058b29  mov     [rbp+4Fh+var_88], r13
0x180058b2d  mov     [rbp+4Fh+var_40], r13
0x180058b31  mov     r9d, 2Eh ; '.'; unsigned int
0x180058b37  lea     r8d, [r9+1]; unsigned int
0x180058b3b  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180058b42  lea     rcx, [rbp+4Fh+pv]; hstringHeader
0x180058b46  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180058b4b  nop
0x180058b4c  mov     rbx, [rbp+4Fh+var_40]
0x180058b50  lea     rcx, [rbp+4Fh+var_88]
0x180058b54  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180058b59  lea     r8, [rbp+4Fh+var_88]
0x180058b5d  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x180058b64  mov     rcx, rbx
0x180058b67  call    cs:__imp_RoGetActivationFactory
0x180058b6d  mov     rcx, [rbp+57h]; this
0x180058b71  test    eax, eax
0x180058b73  jns     short loc_180058B8A
0x180058b75  mov     r9d, eax; char *
0x180058b78  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058b7f  mov     edx, 0AA2h; void *
0x180058b84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058b8a  mov     [rbp+4Fh+var_90], r13b
0x180058b8e  mov     rcx, [rbp+4Fh+var_88]
0x180058b92  mov     rax, [rcx]
0x180058b95  lea     r9, [rbp+4Fh+var_90]
0x180058b99  mov     r8, r14
0x180058b9c  xor     edx, edx
0x180058b9e  mov     rax, [rax+0B8h]
0x180058ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058baa  mov     rcx, [rbp+57h]; this
0x180058bae  test    eax, eax
0x180058bb0  jns     short loc_180058BC7
0x180058bb2  mov     r9d, eax; char *
0x180058bb5  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058bbc  mov     edx, 0AA5h; void *
0x180058bc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058bc7  cmp     [rbp+4Fh+var_90], r13b
0x180058bcb  jz      short loc_180058BE9
0x180058bcd  mov     rcx, [rbp+57h]; this
0x180058bd1  mov     r9d, 80070483h; char *
0x180058bd7  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058bde  mov     edx, 0AACh; void *
0x180058be3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058be9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180058bed  lea     rdx, String1; "Unknown"
0x180058bf4  mov     rcx, rsi
0x180058bf7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180058bfc  mov     rcx, [rbp+57h]; this
0x180058c00  test    eax, eax
0x180058c02  jns     short loc_180058C19
0x180058c04  mov     r9d, eax; char *
0x180058c07  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180058c0e  mov     edx, 0AB1h; void *
0x180058c13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058c19  lea     rcx, [rbp+4Fh+var_88]
0x180058c1d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180058c22  nop
0x180058c23  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x180058c27  test    rcx, rcx
0x180058c2a  jz      short loc_180058C3D
0x180058c2c  mov     qword ptr [rbp+4Fh+var_70], r13
0x180058c30  mov     rdx, [rcx]
0x180058c33  mov     rax, [rdx+10h]
0x180058c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c3c  nop
0x180058c3d  mov     rax, rsi
0x180058c40  mov     rcx, [rbp+4Fh+var_38]
0x180058c44  xor     rcx, rsp; StackCookie
0x180058c47  call    __security_check_cookie
0x180058c4c  mov     rbx, [rsp+0C0h+arg_0]
0x180058c54  add     rsp, 90h
0x180058c5b  pop     r15
0x180058c5d  pop     r14
0x180058c5f  pop     r13
0x180058c61  pop     r12
0x180058c63  pop     rdi
0x180058c64  pop     rsi
0x180058c65  pop     rbp
0x180058c66  retn
```
