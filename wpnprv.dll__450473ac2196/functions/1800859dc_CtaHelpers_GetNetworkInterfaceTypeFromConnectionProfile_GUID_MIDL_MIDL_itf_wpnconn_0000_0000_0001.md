# CtaHelpers::GetNetworkInterfaceTypeFromConnectionProfile(_GUID,__MIDL___MIDL_itf_wpnconn_0000_0000_0001 &)

- ea: `0x1800859dc`
- end: `0x180085d62`
- name: `?GetNetworkInterfaceTypeFromConnectionProfile@CtaHelpers@@YAJU_GUID@@AEAW4__MIDL___MIDL_itf_wpnconn_0000_0000_0001@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(CtaHelpers *__hidden this, struct _GUID *__struct_ptr, enum __MIDL___MIDL_itf_wpnconn_0000_0000_0001 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180056ac0`

## callees

- `0x180007440`
- `0x180008b5b`
- `0x18000ba54`
- `0x18000fe0c`
- `0x18001c06c`
- `0x180036de8`
- `0x18007f6f4`
- `0x18007f744`
- `0x1800859dc`
- `0x180085d68`
- `0x180096010`

## string_xrefs

- `0x180085a54`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085aa4`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085ae2`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085b4e`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085b9d`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085bdb`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085c2e`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085c69`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085ca4`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CtaHelpers::GetNetworkInterfaceTypeFromConnectionProfile(
        CtaHelpers *this,
        struct _GUID *a2,
        enum __MIDL___MIDL_itf_wpnconn_0000_0000_0001 *a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  wil::details::in1diag3 *v18; // rcx
  unsigned int v19; // r15d
  char v20; // r14
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64); // rbx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  int WinHttpPreferredConnection; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  int v48; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v49; // [rsp+24h] [rbp-94h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-90h] BYREF
  __int64 v51; // [rsp+30h] [rbp-88h] BYREF
  __int64 v52; // [rsp+38h] [rbp-80h] BYREF
  __int64 v53; // [rsp+40h] [rbp-78h] BYREF
  __int64 v54; // [rsp+48h] [rbp-70h] BYREF
  HSTRING_HEADER Buf1; // [rsp+50h] [rbp-68h] BYREF
  __int64 v56; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  a2->Data1 = 1;
  v54 = 0;
  v56 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &Buf1,
    L"Windows.Networking.Connectivity.NetworkInformation",
    0x33u,
    0x32u);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(
         v56,
         (__int64)&v54,
         v5,
         v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v7,
      v48);
  v51 = 0;
  v11 = v54;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, v8, v9, v10);
  v13 = v12(v11, &v51);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v13,
      v48);
  v49 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v51 + 56LL))(v51, &v49);
  v18 = retaddr;
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v14,
      v48);
  v19 = 0;
  v20 = 0;
  while ( !v20 && v19 < v49 )
  {
    v50 = 0;
    v21 = v51;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v15, v16, v17);
    v23 = v22(v21, v19, &v50);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v23,
        v48);
    v53 = 0;
    v27 = v50;
    v28 = (*v50)[11];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53, v24, v25, v26);
    v29 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))v28)(v27, &v53);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v29,
        v48);
    *(_OWORD *)&Buf1.Reserved.Reserved1 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v53 + 80LL))(v53, &Buf1);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v30,
        v48);
    if ( !memcmp_0(&Buf1, this, 0x10u) )
    {
      v52 = 0;
      v34 = Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(
              &v50,
              (__int64)&v52,
              v32,
              v33);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
          (const char *)(unsigned int)v34,
          v48);
      LOBYTE(v48) = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 56LL))(v52, &v48);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x151,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
          (const char *)(unsigned int)v35,
          v48);
      BYTE1(v48) = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v52 + 48LL))(v52, (char *)&v48 + 1);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
          (const char *)(unsigned int)v36,
          v48);
      v20 = 1;
      if ( (_BYTE)v48 )
      {
        a2->Data1 = 2;
      }
      else if ( BYTE1(v48) )
      {
        a2->Data1 = 3;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52, v37, v38, v39);
    }
    ++v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53, v31, v32, v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v40, v41, v42);
  }
  if ( a2->Data1 == 1 )
  {
    if ( !v20 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v18);
    WinHttpPreferredConnection = CtaHelpers::GetWinHttpPreferredConnection(v18);
    if ( WinHttpPreferredConnection == 1 )
    {
      a2->Data1 = 2;
    }
    else if ( !WinHttpPreferredConnection )
    {
      a2->Data1 = 3;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, v15, v16, v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54, v44, v45, v46);
  return 0;
}

```

## disassembly

```asm
0x1800859dc  push    rbx
0x1800859de  push    rsi
0x1800859df  push    rdi
0x1800859e0  push    r12
0x1800859e2  push    r14
0x1800859e4  push    r15
0x1800859e6  sub     rsp, 88h
0x1800859ed  mov     rax, cs:__security_cookie
0x1800859f4  xor     rax, rsp
0x1800859f7  mov     [rsp+0B8h+var_48], rax
0x1800859fc  mov     rsi, rdx
0x1800859ff  mov     r12, rcx
0x180085a02  mov     dword ptr [rdx], 1
0x180085a08  mov     [rsp+0B8h+var_70], 0
0x180085a11  mov     [rsp+0B8h+var_50], 0
0x180085a1a  mov     r9d, 32h ; '2'; unsigned int
0x180085a20  lea     r8d, [r9+1]; unsigned int
0x180085a24  lea     rdx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x180085a2b  lea     rcx, [rsp+0B8h+Buf1]; hstringHeader
0x180085a30  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085a35  nop
0x180085a36  lea     rdx, [rsp+0B8h+var_70]
0x180085a3b  mov     rcx, [rsp+0B8h+var_50]
0x180085a40  call    ??$GetActivationFactory@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>)
0x180085a45  mov     rcx, [rsp+0B8h]; this
0x180085a4d  test    eax, eax
0x180085a4f  jns     short loc_180085A66
0x180085a51  mov     r9d, eax; char *
0x180085a54  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085a5b  mov     edx, 136h; void *
0x180085a60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085a66  mov     [rsp+0B8h+var_88], 0
0x180085a6f  mov     rdi, [rsp+0B8h+var_70]
0x180085a74  mov     rax, [rdi]
0x180085a77  mov     rbx, [rax+30h]
0x180085a7b  lea     rcx, [rsp+0B8h+var_88]
0x180085a80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085a85  lea     rdx, [rsp+0B8h+var_88]
0x180085a8a  mov     rcx, rdi
0x180085a8d  mov     rax, rbx
0x180085a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a95  mov     rcx, [rsp+0B8h]; this
0x180085a9d  test    eax, eax
0x180085a9f  jns     short loc_180085AB5
0x180085aa1  mov     r9d, eax; char *
0x180085aa4  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085aab  mov     edx, 139h; void *
0x180085ab0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085ab5  mov     [rsp+0B8h+var_94], 0
0x180085abd  mov     rcx, [rsp+0B8h+var_88]
0x180085ac2  mov     rax, [rcx]
0x180085ac5  lea     rdx, [rsp+0B8h+var_94]
0x180085aca  mov     rax, [rax+38h]
0x180085ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ad3  mov     rcx, [rsp+0B8h]; this
0x180085adb  test    eax, eax
0x180085add  jns     short loc_180085AF3
0x180085adf  mov     r9d, eax; char *
0x180085ae2  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085ae9  mov     edx, 13Ch; void *
0x180085aee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085af3  xor     r15d, r15d
0x180085af6  xor     r14b, r14b
0x180085af9  test    r14b, r14b
0x180085afc  jnz     loc_180085CFB
0x180085b02  cmp     r15d, [rsp+0B8h+var_94]
0x180085b07  jnb     loc_180085CFB
0x180085b0d  mov     [rsp+0B8h+var_90], 0
0x180085b16  mov     rdi, [rsp+0B8h+var_88]
0x180085b1b  mov     rax, [rdi]
0x180085b1e  mov     rbx, [rax+30h]
0x180085b22  lea     rcx, [rsp+0B8h+var_90]
0x180085b27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085b2c  lea     r8, [rsp+0B8h+var_90]
0x180085b31  mov     edx, r15d
0x180085b34  mov     rcx, rdi
0x180085b37  mov     rax, rbx
0x180085b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b3f  mov     rcx, [rsp+0B8h]; this
0x180085b47  test    eax, eax
0x180085b49  jns     short loc_180085B5F
0x180085b4b  mov     r9d, eax; char *
0x180085b4e  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085b55  mov     edx, 143h; void *
0x180085b5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085b5f  mov     [rsp+0B8h+var_78], 0
0x180085b68  mov     rdi, [rsp+0B8h+var_90]
0x180085b6d  mov     rax, [rdi]
0x180085b70  mov     rbx, [rax+58h]
0x180085b74  lea     rcx, [rsp+0B8h+var_78]
0x180085b79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085b7e  lea     rdx, [rsp+0B8h+var_78]
0x180085b83  mov     rcx, rdi
0x180085b86  mov     rax, rbx
0x180085b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b8e  mov     rcx, [rsp+0B8h]; this
0x180085b96  test    eax, eax
0x180085b98  jns     short loc_180085BAE
0x180085b9a  mov     r9d, eax; char *
0x180085b9d  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085ba4  mov     edx, 146h; void *
0x180085ba9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085bae  xorps   xmm0, xmm0
0x180085bb1  movups  xmmword ptr [rsp+0B8h+Buf1], xmm0
0x180085bb6  mov     rcx, [rsp+0B8h+var_78]
0x180085bbb  mov     rax, [rcx]
0x180085bbe  lea     rdx, [rsp+0B8h+Buf1]
0x180085bc3  mov     rax, [rax+50h]
0x180085bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bcc  mov     rcx, [rsp+0B8h]; this
0x180085bd4  test    eax, eax
0x180085bd6  jns     short loc_180085BEC
0x180085bd8  mov     r9d, eax; char *
0x180085bdb  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085be2  mov     edx, 149h; void *
0x180085be7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085bec  mov     r8d, 10h; Size
0x180085bf2  mov     rdx, r12; Buf2
0x180085bf5  lea     rcx, [rsp+0B8h+Buf1]; Buf1
0x180085bfa  call    memcmp_0
0x180085bff  test    eax, eax
0x180085c01  jnz     loc_180085CDE
0x180085c07  mov     [rsp+0B8h+var_80], 0
0x180085c10  lea     rdx, [rsp+0B8h+var_80]
0x180085c15  lea     rcx, [rsp+0B8h+var_90]
0x180085c1a  call    ??$As@UIConnectionProfile2@Connectivity@Networking@Windows@@@?$ComPtr@UIConnectionProfile@Connectivity@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIConnectionProfile2@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile2>>)
0x180085c1f  mov     rcx, [rsp+0B8h]; this
0x180085c27  test    eax, eax
0x180085c29  jns     short loc_180085C3F
0x180085c2b  mov     r9d, eax; char *
0x180085c2e  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085c35  mov     edx, 14Fh; void *
0x180085c3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085c3f  mov     byte ptr [rsp+0B8h+var_98], 0; int
0x180085c44  mov     rcx, [rsp+0B8h+var_80]
0x180085c49  mov     rax, [rcx]
0x180085c4c  lea     rdx, [rsp+0B8h+var_98]
0x180085c51  mov     rax, [rax+38h]
0x180085c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c5a  mov     rcx, [rsp+0B8h]; this
0x180085c62  test    eax, eax
0x180085c64  jns     short loc_180085C7A
0x180085c66  mov     r9d, eax; char *
0x180085c69  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085c70  mov     edx, 151h; void *
0x180085c75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085c7a  mov     byte ptr [rsp+0B8h+var_98+1], 0
0x180085c7f  mov     rcx, [rsp+0B8h+var_80]
0x180085c84  mov     rax, [rcx]
0x180085c87  lea     rdx, [rsp+0B8h+var_98+1]
0x180085c8c  mov     rax, [rax+30h]
0x180085c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c95  mov     rcx, [rsp+0B8h]; this
0x180085c9d  test    eax, eax
0x180085c9f  jns     short loc_180085CB5
0x180085ca1  mov     r9d, eax; char *
0x180085ca4  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085cab  mov     edx, 153h; void *
0x180085cb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085cb5  mov     r14b, 1
0x180085cb8  cmp     byte ptr [rsp+0B8h+var_98], 0
0x180085cbd  jz      short loc_180085CC7
0x180085cbf  mov     dword ptr [rsi], 2
0x180085cc5  jmp     short loc_180085CD4
0x180085cc7  cmp     byte ptr [rsp+0B8h+var_98+1], 0
0x180085ccc  jz      short loc_180085CD4
0x180085cce  mov     dword ptr [rsi], 3
0x180085cd4  lea     rcx, [rsp+0B8h+var_80]
0x180085cd9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085cde  inc     r15d
0x180085ce1  lea     rcx, [rsp+0B8h+var_78]
0x180085ce6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085ceb  nop
0x180085cec  lea     rcx, [rsp+0B8h+var_90]
0x180085cf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085cf6  jmp     loc_180085AF9
0x180085cfb  cmp     dword ptr [rsi], 1
0x180085cfe  jnz     short loc_180085D26
0x180085d00  test    r14b, r14b
0x180085d03  jnz     short loc_180085D0A
0x180085d05  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180085d0a  call    ?GetWinHttpPreferredConnection@CtaHelpers@@YA?AW4CTAConnectionType@1@XZ; CtaHelpers::GetWinHttpPreferredConnection(void)
0x180085d0f  cmp     eax, 1
0x180085d12  jnz     short loc_180085D1C
0x180085d14  mov     dword ptr [rsi], 2
0x180085d1a  jmp     short loc_180085D26
0x180085d1c  test    eax, eax
0x180085d1e  jnz     short loc_180085D26
0x180085d20  mov     dword ptr [rsi], 3
0x180085d26  lea     rcx, [rsp+0B8h+var_88]
0x180085d2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085d30  nop
0x180085d31  lea     rcx, [rsp+0B8h+var_70]
0x180085d36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085d3b  xor     eax, eax
0x180085d3d  jmp     short loc_180085D43
0x180085d3f  mov     eax, [rsp+0B8h+var_94]
0x180085d43  mov     rcx, [rsp+0B8h+var_48]
0x180085d48  xor     rcx, rsp; StackCookie
0x180085d4b  call    __security_check_cookie
0x180085d50  add     rsp, 88h
0x180085d57  pop     r15
0x180085d59  pop     r14
0x180085d5b  pop     r12
0x180085d5d  pop     rdi
0x180085d5e  pop     rsi
0x180085d5f  pop     rbx
0x180085d60  retn
```
