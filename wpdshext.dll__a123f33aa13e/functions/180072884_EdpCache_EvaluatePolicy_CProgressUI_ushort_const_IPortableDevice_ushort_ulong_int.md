# EdpCache::EvaluatePolicy(CProgressUI *,ushort const *,IPortableDevice *,ushort *,ulong,int)

- ea: `0x180072884`
- end: `0x180072bba`
- name: `?EvaluatePolicy@EdpCache@@QEAAJPEAVCProgressUI@@PEBGPEAUIPortableDevice@@PEAGKH@Z`
- size: `822`
- prototype: `__int64 __fastcall(EdpCache *__hidden this, struct CProgressUI *, const unsigned __int16 *, struct IPortableDevice *, unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800118d4`

## callees

- `0x18001f6b0`
- `0x180026ca8`
- `0x180028f0c`
- `0x18002beb8`
- `0x18002bee4`
- `0x180035590`
- `0x18007283c`
- `0x180072884`
- `0x180072e40`
- `0x18007303c`
- `0x1800731cc`
- `0x1800734f0`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800729d8`
- `SHLWAPI!PathFindFileNameW` at `0x1800729d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800729a1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800729a1`

## string_xrefs

- `0x180072905`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x18007294b`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800729b4`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180072a7b`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180072974`: `Windows.Security.EnterpriseData.ProtectionPolicyAuditInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EdpCache::EvaluatePolicy(
        EdpCache *this,
        struct CProgressUI *a2,
        const unsigned __int16 *a3,
        struct IPortableDevice *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        int a7)
{
  int FileProtectionIdentity; // eax
  EdpCache *v12; // rcx
  unsigned int v13; // ebx
  int PeerDeviceIdentity; // eax
  __int64 v16; // rbx
  int ActivationFactory; // eax
  __int64 v18; // r14
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD, __int64); // rsi
  int v20; // edi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // eax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  int v29; // ecx
  int v30; // [rsp+20h] [rbp-C1h]
  int v31; // [rsp+20h] [rbp-C1h]
  int v32; // [rsp+40h] [rbp-A1h] BYREF
  struct Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *v33; // [rsp+48h] [rbp-99h] BYREF
  __int64 v34; // [rsp+50h] [rbp-91h] BYREF
  unsigned __int16 *v35; // [rsp+58h] [rbp-89h] BYREF
  LPWSTR FileNameW; // [rsp+60h] [rbp-81h] BYREF
  struct CProgressUI *v37; // [rsp+68h] [rbp-79h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-71h] BYREF
  int v39[2]; // [rsp+88h] [rbp-59h]
  _BYTE v40[32]; // [rsp+90h] [rbp-51h] BYREF
  _BYTE v41[32]; // [rsp+B0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v37 = a2;
  if ( a2 && a3 && a4 && a5 )
  {
    FileProtectionIdentity = EdpCache::_GetFileProtectionIdentity(this, a3, a5, (__int64)a4, a7);
    v13 = FileProtectionIdentity;
    if ( FileProtectionIdentity < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
        (const char *)(unsigned int)FileProtectionIdentity,
        v30);
      return v13;
    }
    if ( !*a5 )
      return 0;
    v35 = 0;
    PeerDeviceIdentity = EdpCache::_GetPeerDeviceIdentity(v12, a4, a2, &v35);
    v13 = PeerDeviceIdentity;
    if ( PeerDeviceIdentity < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
        (const char *)(unsigned int)PeerDeviceIdentity,
        v30);
LABEL_30:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      return v13;
    }
    v34 = 0;
    *(_QWORD *)v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.EnterpriseData.ProtectionPolicyAuditInfo",
      0x3Au,
      0x39u);
    v16 = *(_QWORD *)v39;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    ActivationFactory = RoGetActivationFactory(v16, &GUID_7ed4180b_92e8_42d5_83d4_25440b423549, &v34);
    v13 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v30);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      goto LABEL_30;
    }
    FileNameW = PathFindFileNameW(a3);
    v33 = 0;
    v18 = v34;
    v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v34 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    *(_QWORD *)v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Device", 7u, 6u);
    v20 = v39[0];
    v21 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v40, &FileNameW) + 24);
    v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, &FileNameW);
    v31 = v20;
    v23 = v19(v18, 2, *(_QWORD *)(v22 + 24), v21);
    v13 = v23;
    if ( v23 >= 0 )
    {
      v32 = 0;
      if ( *(_DWORD *)this )
        v26 = EdpCache::_AuditAndCheckAccess(
                this,
                a5,
                v35,
                v33,
                (enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)&v32);
      else
        v26 = EdpCache::_AuditAndRequestAccess(
                (EdpCache *)&v32,
                *((HWND *)v37 + 15),
                a5,
                v35,
                v33,
                (enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)&v32);
      v13 = v26;
      if ( v26 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, (_DWORD)a3, v32, (__int64)v35);
        v29 = v32;
        if ( *(_DWORD *)this == 1 )
        {
          if ( v32 == 2 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
            v13 = 0;
            goto LABEL_30;
          }
        }
        else if ( !*(_DWORD *)this )
        {
          *(_DWORD *)this = (v32 != 0) + 1;
        }
        v13 = v29 != 0 ? 0x80070005 : 0;
        goto LABEL_18;
      }
      v24 = (unsigned int)v26;
      v25 = 110;
    }
    else
    {
      v24 = (unsigned int)v23;
      v25 = 88;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)v24,
      v31);
LABEL_18:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    goto LABEL_14;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180072884  push    rbp
0x180072886  push    rbx
0x180072887  push    rsi
0x180072888  push    rdi
0x180072889  push    r12
0x18007288b  push    r13
0x18007288d  push    r14
0x18007288f  push    r15
0x180072891  lea     rbp, [rsp-7]
0x180072896  sub     rsp, 0E8h
0x18007289d  mov     rax, cs:__security_cookie
0x1800728a4  xor     rax, rsp
0x1800728a7  mov     [rbp+3Fh+var_50], rax
0x1800728ab  mov     rsi, r9
0x1800728ae  mov     r13, r8
0x1800728b1  mov     rdi, rdx
0x1800728b4  mov     [rbp+3Fh+var_B8], rdx
0x1800728b8  mov     r12, rcx
0x1800728bb  mov     r15, [rbp+3Fh+arg_20]
0x1800728bf  xor     r14d, r14d
0x1800728c2  test    rdx, rdx
0x1800728c5  jz      loc_180072B95
0x1800728cb  test    r8, r8
0x1800728ce  jz      loc_180072B95
0x1800728d4  test    r9, r9
0x1800728d7  jz      loc_180072B95
0x1800728dd  test    r15, r15
0x1800728e0  jz      loc_180072B95
0x1800728e6  mov     eax, [rbp+3Fh+arg_30]
0x1800728e9  mov     dword ptr [rsp+120h+var_100], eax; int
0x1800728ed  mov     r8, r15; unsigned __int16 *
0x1800728f0  mov     rdx, r13; unsigned __int16 *
0x1800728f3  call    ?_GetFileProtectionIdentity@EdpCache@@AEAAJPEBGPEAGKH@Z; EdpCache::_GetFileProtectionIdentity(ushort const *,ushort *,ulong,int)
0x1800728f8  mov     ebx, eax
0x1800728fa  test    eax, eax
0x1800728fc  jns     short loc_18007291C
0x1800728fe  mov     rcx, [rbp+47h]; this
0x180072902  mov     r9d, eax; char *
0x180072905  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x18007290c  lea     edx, [r14+38h]; void *
0x180072910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072915  mov     eax, ebx
0x180072917  jmp     loc_180072B9A
0x18007291c  cmp     [r15], r14w
0x180072920  jnz     short loc_180072929
0x180072922  xor     eax, eax
0x180072924  jmp     loc_180072B9A
0x180072929  mov     [rsp+120h+var_C8], r14
0x18007292e  lea     r9, [rsp+120h+var_C8]; unsigned __int16 **
0x180072933  mov     r8, rdi; struct CProgressUI *
0x180072936  mov     rdx, rsi; struct IPortableDevice *
0x180072939  call    ?_GetPeerDeviceIdentity@EdpCache@@AEAAJPEAUIPortableDevice@@PEAVCProgressUI@@PEAPEAG@Z; EdpCache::_GetPeerDeviceIdentity(IPortableDevice *,CProgressUI *,ushort * *)
0x18007293e  mov     ebx, eax
0x180072940  test    eax, eax
0x180072942  jns     short loc_180072961
0x180072944  mov     rcx, [rbp+47h]; this
0x180072948  mov     r9d, eax; char *
0x18007294b  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180072952  mov     edx, 45h ; 'E'; void *
0x180072957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007295c  jmp     loc_180072B60
0x180072961  mov     [rsp+120h+var_D0], r14
0x180072966  mov     qword ptr [rbp+3Fh+var_98], r14
0x18007296a  mov     r9d, 39h ; '9'; unsigned int
0x180072970  lea     r8d, [r9+1]; unsigned int
0x180072974  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyAuditInfo@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x18007297b  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x18007297f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180072984  mov     rbx, qword ptr [rbp+3Fh+var_98]
0x180072988  lea     rcx, [rsp+120h+var_D0]
0x18007298d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072992  lea     r8, [rsp+120h+var_D0]
0x180072997  lea     rdx, _GUID_7ed4180b_92e8_42d5_83d4_25440b423549
0x18007299e  mov     rcx, rbx
0x1800729a1  call    cs:__imp_RoGetActivationFactory
0x1800729a7  mov     ebx, eax
0x1800729a9  test    eax, eax
0x1800729ab  jns     short loc_1800729D5
0x1800729ad  mov     rcx, [rbp+47h]; this
0x1800729b1  mov     r9d, eax; char *
0x1800729b4  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x1800729bb  mov     edx, 4Dh ; 'M'; void *
0x1800729c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800729c5  nop
0x1800729c6  lea     rcx, [rsp+120h+var_D0]
0x1800729cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800729d0  jmp     loc_180072B60
0x1800729d5  mov     rcx, r13; pszPath
0x1800729d8  call    cs:__imp_PathFindFileNameW
0x1800729de  mov     [rsp+120h+var_C0], rax
0x1800729e3  mov     [rsp+120h+var_D8], r14
0x1800729e8  mov     r14, [rsp+120h+var_D0]
0x1800729ed  mov     rax, [r14]
0x1800729f0  mov     rsi, [rax+30h]
0x1800729f4  lea     rcx, [rsp+120h+var_D8]
0x1800729f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800729fe  mov     qword ptr [rbp+3Fh+var_98], 0
0x180072a06  mov     r9d, 6; unsigned int
0x180072a0c  lea     r8d, [r9+1]; unsigned int
0x180072a10  lea     rdx, sourceString; "Device"
0x180072a17  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x180072a1b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180072a20  nop
0x180072a21  mov     rdi, qword ptr [rbp+3Fh+var_98]
0x180072a25  lea     rdx, [rsp+120h+var_C0]
0x180072a2a  lea     rcx, [rbp+3Fh+var_90]
0x180072a2e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180072a33  nop
0x180072a34  mov     rbx, [rax+18h]
0x180072a38  lea     rdx, [rsp+120h+var_C0]
0x180072a3d  lea     rcx, [rbp+3Fh+var_70]
0x180072a41  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180072a46  nop
0x180072a47  lea     rcx, [rsp+120h+var_D8]
0x180072a4c  mov     [rsp+120h+var_F8], rcx
0x180072a51  mov     [rsp+120h+var_100], rdi; int
0x180072a56  mov     r9, rbx
0x180072a59  mov     r8, [rax+18h]
0x180072a5d  mov     edx, 2
0x180072a62  mov     rcx, r14
0x180072a65  mov     rax, rsi
0x180072a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a6d  mov     ebx, eax
0x180072a6f  xor     edi, edi
0x180072a71  test    eax, eax
0x180072a73  jns     short loc_180072A9B
0x180072a75  mov     r9d, eax; char *
0x180072a78  lea     edx, [rdi+58h]; void *
0x180072a7b  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180072a82  mov     rcx, [rbp+47h]; this
0x180072a86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072a8b  nop
0x180072a8c  lea     rcx, [rsp+120h+var_D8]
0x180072a91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072a96  jmp     loc_1800729C6
0x180072a9b  mov     [rsp+120h+var_E0], edi
0x180072a9f  cmp     [r12], edi
0x180072aa3  jnz     short loc_180072AD0
0x180072aa5  mov     rax, [rsp+120h+var_D8]
0x180072aaa  lea     rcx, [rsp+120h+var_E0]; this
0x180072aaf  mov     [rsp+120h+var_F8], rcx; enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *
0x180072ab4  mov     [rsp+120h+var_100], rax; struct Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *
0x180072ab9  mov     r9, [rsp+120h+var_C8]; unsigned __int16 *
0x180072abe  mov     r8, r15; unsigned __int16 *
0x180072ac1  mov     rdx, [rbp+3Fh+var_B8]
0x180072ac5  mov     rdx, [rdx+78h]; HWND
0x180072ac9  call    ?_AuditAndRequestAccess@EdpCache@@AEAAJPEAUHWND__@@PEBG1PEAUIProtectionPolicyAuditInfo@EnterpriseData@Security@Windows@@PEAW4ProtectionPolicyEvaluationResult@456@@Z; EdpCache::_AuditAndRequestAccess(HWND__ *,ushort const *,ushort const *,Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *,Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)
0x180072ace  jmp     short loc_180072AEF
0x180072ad0  lea     rax, [rsp+120h+var_E0]
0x180072ad5  mov     [rsp+120h+var_100], rax; enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *
0x180072ada  mov     r9, [rsp+120h+var_D8]; struct Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *
0x180072adf  mov     r8, [rsp+120h+var_C8]; unsigned __int16 *
0x180072ae4  mov     rdx, r15; unsigned __int16 *
0x180072ae7  mov     rcx, r12; this
0x180072aea  call    ?_AuditAndCheckAccess@EdpCache@@AEAAJPEBG0PEAUIProtectionPolicyAuditInfo@EnterpriseData@Security@Windows@@PEAW4ProtectionPolicyEvaluationResult@345@@Z; EdpCache::_AuditAndCheckAccess(ushort const *,ushort const *,Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *,Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)
0x180072aef  mov     ebx, eax
0x180072af1  test    eax, eax
0x180072af3  jns     short loc_180072B02
0x180072af5  mov     r9d, eax
0x180072af8  mov     edx, 6Eh ; 'n'
0x180072afd  jmp     loc_180072A7B
0x180072b02  lea     rax, WPP_GLOBAL_Control
0x180072b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b10  cmp     rcx, rax
0x180072b13  jz      short loc_180072B39
0x180072b15  test    byte ptr [rcx+1Ch], 40h
0x180072b19  jz      short loc_180072B39
0x180072b1b  mov     rax, [rsp+120h+var_C8]
0x180072b20  mov     [rsp+120h+var_F8], rax
0x180072b25  mov     eax, [rsp+120h+var_E0]
0x180072b29  mov     dword ptr [rsp+120h+var_100], eax
0x180072b2d  mov     r9, r13
0x180072b30  mov     rcx, [rcx+10h]
0x180072b34  call    WPP_SF_SDS
0x180072b39  mov     ecx, [rsp+120h+var_E0]
0x180072b3d  cmp     dword ptr [r12], 1
0x180072b42  jnz     short loc_180072B6F
0x180072b44  cmp     ecx, 2
0x180072b47  jnz     short loc_180072B82
0x180072b49  lea     rcx, [rsp+120h+var_D8]
0x180072b4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072b53  nop
0x180072b54  lea     rcx, [rsp+120h+var_D0]
0x180072b59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072b5e  mov     ebx, edi
0x180072b60  lea     rcx, [rsp+120h+var_C8]
0x180072b65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072b6a  jmp     loc_180072915
0x180072b6f  cmp     [r12], edi
0x180072b73  jnz     short loc_180072B82
0x180072b75  mov     eax, edi
0x180072b77  test    ecx, ecx
0x180072b79  setnz   al
0x180072b7c  inc     eax
0x180072b7e  mov     [r12], eax
0x180072b82  mov     eax, edi
0x180072b84  sub     eax, ecx
0x180072b86  neg     eax
0x180072b88  sbb     ebx, ebx
0x180072b8a  and     ebx, 80070005h
0x180072b90  jmp     loc_180072A8C
0x180072b95  mov     eax, 80004003h
0x180072b9a  mov     rcx, [rbp+3Fh+var_50]
0x180072b9e  xor     rcx, rsp; StackCookie
0x180072ba1  call    __security_check_cookie
0x180072ba6  add     rsp, 0E8h
0x180072bad  pop     r15
0x180072baf  pop     r14
0x180072bb1  pop     r13
0x180072bb3  pop     r12
0x180072bb5  pop     rdi
0x180072bb6  pop     rsi
0x180072bb7  pop     rbx
0x180072bb8  pop     rbp
0x180072bb9  retn
```
