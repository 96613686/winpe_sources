# EdpHelpers::GetEdpContextFromShellItemsDefaultVerbHandler(IShellItem *,EDP_CONTEXT * *)

- ea: `0x180087338`
- end: `0x180087531`
- name: `?GetEdpContextFromShellItemsDefaultVerbHandler@EdpHelpers@@YAJPEAUIShellItem@@PEAPEAUEDP_CONTEXT@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(EdpHelpers *__hidden this, struct IShellItem *, struct EDP_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180055d2c`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18003d318`
- `0x180087338`
- `0x180105038`
- `0x180111010`

## import_xrefs

- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180087417`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180087417`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x1800874d8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForBinaryPath` at `0x1800874d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087513`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EdpHelpers::GetEdpContextFromShellItemsDefaultVerbHandler(
        EdpHelpers *this,
        struct IShellItem *a2,
        struct EDP_CONTEXT **a3)
{
  __int64 (__fastcall *v5)(EdpHelpers *, _QWORD, const GUID *, GUID *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rbx
  __int64 v9; // rsi
  int (__fastcall *v10)(__int64, __int64, _QWORD, CallerIdentity **); // rdi
  unsigned __int16 **v11; // r8
  int PackageFullNameFromAppId; // eax
  int ContextForPackageFullName; // eax
  int ContextForBinaryPath; // edi
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD, LPVOID *); // rdi
  __int64 v17; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  CallerIdentity *v20; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v21; // [rsp+68h] [rbp+38h] BYREF
  __int64 v22; // [rsp+70h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+48h] BYREF

  a2->lpVtbl = 0;
  v22 = 0;
  v5 = *(__int64 (__fastcall **)(EdpHelpers *, _QWORD, const GUID *, GUID *))(*(_QWORD *)this + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v6 = v5(this, 0, &BHID_AssociationArray, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
      (const char *)(unsigned int)v6,
      (int)&v22);
    goto LABEL_25;
  }
  v20 = 0;
  v8 = 0;
  pv = 0;
  v9 = v22;
  v10 = *(int (__fastcall **)(__int64, __int64, _QWORD, CallerIdentity **))(*(_QWORD *)v22 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v20,
    0);
  if ( v10(v9, 458757, 0, &v20) < 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0),
        PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(v20, (const unsigned __int16 *)&pv, v11),
        v8 = pv,
        PackageFullNameFromAppId < 0) )
  {
    v21 = 0;
    v15 = v22;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *))(*(_QWORD *)v22 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v21,
      0);
    ContextForBinaryPath = v16(v15, 34013210, 0, &v21);
    if ( ContextForBinaryPath >= 0 )
    {
      ContextForBinaryPath = EdpGetContextForBinaryPath(v21, a2);
      if ( ContextForBinaryPath >= 0 )
      {
        if ( v21 )
          CoTaskMemFree(v21);
        goto LABEL_20;
      }
      v17 = 635;
    }
    else
    {
      v17 = 634;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
      (const char *)(unsigned int)ContextForBinaryPath,
      (int)&v22);
    if ( v21 )
      CoTaskMemFree(v21);
    goto LABEL_7;
  }
  ContextForPackageFullName = EdpGetContextForPackageFullName(pv, a2);
  ContextForBinaryPath = ContextForPackageFullName;
  if ( ContextForPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
      (const char *)(unsigned int)ContextForPackageFullName,
      (int)&v22);
LABEL_7:
    if ( v8 )
      CoTaskMemFree(v8);
    if ( v20 )
      CoTaskMemFree(v20);
    v7 = ContextForBinaryPath;
    goto LABEL_25;
  }
LABEL_20:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v20 )
    CoTaskMemFree(v20);
  v7 = 0;
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return v7;
}

```

## disassembly

```asm
0x180087338  push    rbp
0x18008733a  push    rbx
0x18008733b  push    rsi
0x18008733c  push    rdi
0x18008733d  push    r14
0x18008733f  mov     rbp, rsp
0x180087342  sub     rsp, 30h
0x180087346  mov     r14, rdx
0x180087349  mov     rdi, rcx
0x18008734c  mov     qword ptr [rdx], 0
0x180087353  mov     [rbp+arg_10], 0
0x18008735b  mov     rax, [rcx]
0x18008735e  mov     rbx, [rax+18h]
0x180087362  lea     rcx, [rbp+arg_10]
0x180087366  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008736b  lea     rax, [rbp+arg_10]
0x18008736f  mov     qword ptr [rsp+30h+var_10], rax; int
0x180087374  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x18008737b  lea     r8, BHID_AssociationArray
0x180087382  xor     edx, edx
0x180087384  mov     rcx, rdi
0x180087387  mov     rax, rbx
0x18008738a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008738f  mov     ebx, eax
0x180087391  test    eax, eax
0x180087393  jns     short loc_1800873B2
0x180087395  mov     rcx, [rbp+28h]; this
0x180087399  mov     r9d, eax; char *
0x18008739c  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800873a3  mov     edx, 26Bh; void *
0x1800873a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800873ad  jmp     loc_18008751B
0x1800873b2  mov     [rbp+arg_0], 0
0x1800873ba  xor     ebx, ebx
0x1800873bc  mov     [rbp+pv], rbx
0x1800873c0  mov     rsi, [rbp+arg_10]
0x1800873c4  mov     rax, [rsi]
0x1800873c7  mov     rdi, [rax+18h]
0x1800873cb  xor     edx, edx
0x1800873cd  lea     rcx, [rbp+arg_0]
0x1800873d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800873d6  lea     r9, [rbp+arg_0]
0x1800873da  xor     r8d, r8d
0x1800873dd  mov     edx, 70005h
0x1800873e2  mov     rcx, rsi
0x1800873e5  mov     rax, rdi
0x1800873e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873ed  test    eax, eax
0x1800873ef  js      short loc_180087465
0x1800873f1  xor     edx, edx
0x1800873f3  lea     rcx, [rbp+pv]
0x1800873f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800873fc  lea     rdx, [rbp+pv]; unsigned __int16 *
0x180087400  mov     rcx, [rbp+arg_0]; this
0x180087404  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x180087409  mov     rbx, [rbp+pv]
0x18008740d  test    eax, eax
0x18008740f  js      short loc_180087465
0x180087411  mov     rdx, r14
0x180087414  mov     rcx, rbx
0x180087417  call    cs:__imp_EdpGetContextForPackageFullName
0x18008741d  mov     edi, eax
0x18008741f  test    eax, eax
0x180087421  jns     loc_1800874FB
0x180087427  mov     rcx, [rbp+28h]; this
0x18008742b  mov     r9d, eax; char *
0x18008742e  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180087435  mov     edx, 273h; void *
0x18008743a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008743f  nop
0x180087440  test    rbx, rbx
0x180087443  jz      short loc_18008744F
0x180087445  mov     rcx, rbx; pv
0x180087448  call    cs:__imp_CoTaskMemFree
0x18008744e  nop
0x18008744f  mov     rcx, [rbp+arg_0]; pv
0x180087453  test    rcx, rcx
0x180087456  jz      short loc_18008745E
0x180087458  call    cs:__imp_CoTaskMemFree
0x18008745e  mov     ebx, edi
0x180087460  jmp     loc_18008751B
0x180087465  mov     [rbp+arg_8], 0
0x18008746d  mov     rsi, [rbp+arg_10]
0x180087471  mov     rax, [rsi]
0x180087474  mov     rdi, [rax+18h]
0x180087478  xor     edx, edx
0x18008747a  lea     rcx, [rbp+arg_8]
0x18008747e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180087483  lea     r9, [rbp+arg_8]
0x180087487  xor     r8d, r8d
0x18008748a  mov     edx, 207001Ah
0x18008748f  mov     rcx, rsi
0x180087492  mov     rax, rdi
0x180087495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008749a  mov     edi, eax
0x18008749c  test    eax, eax
0x18008749e  jns     short loc_1800874D1
0x1800874a0  mov     edx, 27Ah; void *
0x1800874a5  mov     r9d, edi; char *
0x1800874a8  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800874af  mov     rcx, [rbp+28h]; this
0x1800874b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800874b8  nop
0x1800874b9  mov     rcx, [rbp+arg_8]; pv
0x1800874bd  test    rcx, rcx
0x1800874c0  jz      loc_180087440
0x1800874c6  call    cs:__imp_CoTaskMemFree
0x1800874cc  jmp     loc_180087440
0x1800874d1  mov     rdx, r14
0x1800874d4  mov     rcx, [rbp+arg_8]
0x1800874d8  call    cs:__imp_EdpGetContextForBinaryPath
0x1800874de  mov     edi, eax
0x1800874e0  test    eax, eax
0x1800874e2  jns     short loc_1800874EB
0x1800874e4  mov     edx, 27Bh
0x1800874e9  jmp     short loc_1800874A5
0x1800874eb  mov     rcx, [rbp+arg_8]; pv
0x1800874ef  test    rcx, rcx
0x1800874f2  jz      short loc_1800874FB
0x1800874f4  call    cs:__imp_CoTaskMemFree
0x1800874fa  nop
0x1800874fb  test    rbx, rbx
0x1800874fe  jz      short loc_18008750A
0x180087500  mov     rcx, rbx; pv
0x180087503  call    cs:__imp_CoTaskMemFree
0x180087509  nop
0x18008750a  mov     rcx, [rbp+arg_0]; pv
0x18008750e  test    rcx, rcx
0x180087511  jz      short loc_180087519
0x180087513  call    cs:__imp_CoTaskMemFree
0x180087519  xor     ebx, ebx
0x18008751b  lea     rcx, [rbp+arg_10]
0x18008751f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087524  mov     eax, ebx
0x180087526  add     rsp, 30h
0x18008752a  pop     r14
0x18008752c  pop     rdi
0x18008752d  pop     rsi
0x18008752e  pop     rbx
0x18008752f  pop     rbp
0x180087530  retn
```
