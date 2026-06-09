# IsVerbHandlerAppxPackagedAndNotSettings(ushort const *,ushort const *)

- ea: `0x180073718`
- end: `0x18007392d`
- name: `?IsVerbHandlerAppxPackagedAndNotSettings@@YA_NPEBG0@Z`
- size: `533`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020d68`

## callees

- `0x1800049bc`
- `0x18003d318`
- `0x180073718`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800738a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800738a3`
- `ext-ms-win-shell-shlwapi-l1-1-2!AssocCreate` at `0x180073756`
- `ext-ms-win-shell-shlwapi-l1-1-2!AssocCreate` at `0x180073756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800738f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073908`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall IsVerbHandlerAppxPackagedAndNotSettings(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  void *v3; // rdi
  int (__fastcall *v4)(void *, GUID *, __int64 *); // rbx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, __int64, _QWORD, GUID *, const unsigned __int16 **); // rbx
  const unsigned __int16 *v7; // rdi
  int (__fastcall *v8)(const unsigned __int16 *, __int64, const WCHAR *, CLSID *); // rbx
  const unsigned __int16 *v9; // rdi
  int (__fastcall *v10)(const unsigned __int16 *, __int64, _QWORD, LPCWCH *); // rbx
  bool v11; // bl
  void *ppv[2]; // [rsp+30h] [rbp-20h] BYREF
  CLSID clsid; // [rsp+40h] [rbp-10h] BYREF
  const unsigned __int16 *v15; // [rsp+78h] [rbp+28h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  LPCWCH lpString1; // [rsp+88h] [rbp+38h] BYREF

  v15 = a2;
  ppv[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv);
  clsid = CLSID_QueryAssociations;
  if ( AssocCreate(&clsid, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, ppv) < 0
    || (*(int (__fastcall **)(void *, __int64, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppv[0] + 24LL))(
         ppv[0],
         2048,
         a1,
         0,
         0) < 0 )
  {
LABEL_17:
    v11 = 0;
    goto LABEL_18;
  }
  v15 = 0;
  *(_QWORD *)&clsid.Data1 = 0;
  lpString1 = 0;
  v16 = 0;
  v3 = ppv[0];
  v4 = **(int (__fastcall ***)(void *, GUID *, __int64 *))ppv[0];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  if ( v4(v3, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &v16) < 0 )
    goto LABEL_12;
  v5 = v16;
  v6 = *(int (__fastcall **)(__int64, __int64, _QWORD, GUID *, const unsigned __int16 **))(*(_QWORD *)v16 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  if ( v6(v5, 35651598, 0, &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502, &v15) < 0
    || (v7 = v15,
        v8 = *(int (__fastcall **)(const unsigned __int16 *, __int64, const WCHAR *, CLSID *))(*(_QWORD *)v15 + 24LL),
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &clsid,
          0),
        v8(v7, 17760256, L"PackageId", &clsid) < 0)
    || (v9 = v15,
        v10 = *(int (__fastcall **)(const unsigned __int16 *, __int64, _QWORD, LPCWCH *))(*(_QWORD *)v15 + 24LL),
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &lpString1,
          0),
        v10(v9, 458757, 0, &lpString1) < 0) )
  {
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
    if ( *(_QWORD *)&clsid.Data1 )
      CoTaskMemFree(*(LPVOID *)&clsid.Data1);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    goto LABEL_17;
  }
  v11 = CompareStringOrdinal(
          lpString1,
          -1,
          L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
          -1,
          1) != 2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  if ( lpString1 )
    CoTaskMemFree((LPVOID)lpString1);
  if ( *(_QWORD *)&clsid.Data1 )
    CoTaskMemFree(*(LPVOID *)&clsid.Data1);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv);
  return v11;
}

```

## disassembly

```asm
0x180073718  mov     [rsp-18h+arg_8], rdx
0x18007371d  push    rbp
0x18007371e  push    rbx
0x18007371f  push    rdi
0x180073720  mov     rbp, rsp
0x180073723  sub     rsp, 50h
0x180073727  mov     rbx, rcx
0x18007372a  mov     [rbp+ppv], 0
0x180073732  lea     rcx, [rbp+ppv]
0x180073736  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007373b  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180073742  movdqu  xmmword ptr [rbp+clsid.Data1], xmm0
0x180073747  lea     r8, [rbp+ppv]; ppv
0x18007374b  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x180073752  lea     rcx, [rbp+clsid]; clsid
0x180073756  call    cs:__imp_AssocCreate
0x18007375c  test    eax, eax
0x18007375e  js      loc_180073918
0x180073764  mov     rcx, [rbp+ppv]
0x180073768  mov     rax, [rcx]
0x18007376b  mov     qword ptr [rsp+50h+bIgnoreCase], 0
0x180073774  xor     r9d, r9d
0x180073777  mov     r8, rbx
0x18007377a  mov     edx, 800h
0x18007377f  mov     rax, [rax+18h]
0x180073783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073788  test    eax, eax
0x18007378a  js      loc_180073918
0x180073790  mov     [rbp+arg_8], 0
0x180073798  mov     qword ptr [rbp+clsid.Data1], 0
0x1800737a0  mov     [rbp+lpString1], 0
0x1800737a8  mov     [rbp+arg_10], 0
0x1800737b0  mov     rdi, [rbp+ppv]
0x1800737b4  mov     rax, [rdi]
0x1800737b7  mov     rbx, [rax]
0x1800737ba  lea     rcx, [rbp+arg_10]
0x1800737be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800737c3  lea     r8, [rbp+arg_10]
0x1800737c7  lea     rdx, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x1800737ce  mov     rcx, rdi
0x1800737d1  mov     rax, rbx
0x1800737d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737d9  test    eax, eax
0x1800737db  js      loc_1800738E5
0x1800737e1  mov     rdi, [rbp+arg_10]
0x1800737e5  mov     rax, [rdi]
0x1800737e8  mov     rbx, [rax+40h]
0x1800737ec  lea     rcx, [rbp+arg_8]
0x1800737f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800737f5  lea     rax, [rbp+arg_8]
0x1800737f9  mov     qword ptr [rsp+50h+bIgnoreCase], rax
0x1800737fe  lea     r9, _GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502
0x180073805  xor     r8d, r8d
0x180073808  mov     edx, 220000Eh
0x18007380d  mov     rcx, rdi
0x180073810  mov     rax, rbx
0x180073813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073818  test    eax, eax
0x18007381a  js      loc_1800738E5
0x180073820  mov     rdi, [rbp+arg_8]
0x180073824  mov     rax, [rdi]
0x180073827  mov     rbx, [rax+18h]
0x18007382b  xor     edx, edx
0x18007382d  lea     rcx, [rbp+clsid]
0x180073831  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180073836  lea     r9, [rbp+clsid]
0x18007383a  lea     r8, aPackageid; "PackageId"
0x180073841  mov     edx, 10F0000h
0x180073846  mov     rcx, rdi
0x180073849  mov     rax, rbx
0x18007384c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073851  test    eax, eax
0x180073853  js      loc_1800738E5
0x180073859  mov     rdi, [rbp+arg_8]
0x18007385d  mov     rax, [rdi]
0x180073860  mov     rbx, [rax+18h]
0x180073864  xor     edx, edx
0x180073866  lea     rcx, [rbp+lpString1]
0x18007386a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007386f  lea     r9, [rbp+lpString1]
0x180073873  xor     r8d, r8d
0x180073876  mov     edx, 70005h
0x18007387b  mov     rcx, rdi
0x18007387e  mov     rax, rbx
0x180073881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073886  test    eax, eax
0x180073888  js      short loc_1800738E5
0x18007388a  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180073892  or      edx, 0FFFFFFFFh; cchCount1
0x180073895  mov     r9d, edx; cchCount2
0x180073898  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18007389f  mov     rcx, [rbp+lpString1]; lpString1
0x1800738a3  call    cs:__imp_CompareStringOrdinal
0x1800738a9  nop
0x1800738aa  cmp     eax, 2
0x1800738ad  setnz   bl
0x1800738b0  lea     rcx, [rbp+arg_10]
0x1800738b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800738b9  nop
0x1800738ba  mov     rcx, [rbp+lpString1]; pv
0x1800738be  test    rcx, rcx
0x1800738c1  jz      short loc_1800738CA
0x1800738c3  call    cs:__imp_CoTaskMemFree
0x1800738c9  nop
0x1800738ca  mov     rcx, qword ptr [rbp+clsid.Data1]; pv
0x1800738ce  test    rcx, rcx
0x1800738d1  jz      short loc_1800738DA
0x1800738d3  call    cs:__imp_CoTaskMemFree
0x1800738d9  nop
0x1800738da  lea     rcx, [rbp+arg_8]
0x1800738de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800738e3  jmp     short loc_18007391A
0x1800738e5  lea     rcx, [rbp+arg_10]
0x1800738e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800738ee  nop
0x1800738ef  mov     rcx, [rbp+lpString1]; pv
0x1800738f3  test    rcx, rcx
0x1800738f6  jz      short loc_1800738FF
0x1800738f8  call    cs:__imp_CoTaskMemFree
0x1800738fe  nop
0x1800738ff  mov     rcx, qword ptr [rbp+clsid.Data1]; pv
0x180073903  test    rcx, rcx
0x180073906  jz      short loc_18007390F
0x180073908  call    cs:__imp_CoTaskMemFree
0x18007390e  nop
0x18007390f  lea     rcx, [rbp+arg_8]
0x180073913  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073918  xor     ebx, ebx
0x18007391a  lea     rcx, [rbp+ppv]
0x18007391e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073923  mov     al, bl
0x180073925  add     rsp, 50h
0x180073929  pop     rdi
0x18007392a  pop     rbx
0x18007392b  pop     rbp
0x18007392c  retn
```
