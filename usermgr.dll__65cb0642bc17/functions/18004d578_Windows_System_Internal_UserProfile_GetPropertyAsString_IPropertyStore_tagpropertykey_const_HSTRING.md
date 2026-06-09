# Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)

- ea: `0x18004d578`
- end: `0x18004d70a`
- name: `?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z`
- size: `402`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, HSTRING *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004b080`
- `0x18004b5a0`
- `0x18004cf48`
- `0x18004db44`

## callees

- `0x18000acdc`
- `0x18003322c`
- `0x180035800`
- `0x18004d578`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d6f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d6f2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004d614`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004d614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d6e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d6e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004d6b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004d6b9`

## string_xrefs

- `0x18004d5d7`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d644`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d66e`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d6a0`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d6ca`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::UserProfile::GetPropertyAsString(
        Windows::System::Internal::UserProfile *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        HSTRING *a4)
{
  int v5; // eax
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // eax
  HRESULT v9; // eax
  IID *rclsid[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HSTRING string; // [rsp+60h] [rbp+10h] BYREF
  LPOLESTR lpsz; // [rsp+68h] [rbp+18h] BYREF

  *(_OWORD *)rclsid = 0;
  v12 = 0;
  string = 0;
  v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, IID **))a2->lpVtbl->GetValue)(
         a2,
         a3,
         rclsid);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x513,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v5,
      (int)rclsid);
  switch ( LOWORD(rclsid[0]) )
  {
    case 8u:
      lpsz = (LPOLESTR)rclsid[1];
      v8 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x51A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v8,
          (int)rclsid);
      break;
    case 0x1Fu:
      v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x517,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v7,
          (int)rclsid);
      break;
    case 0x48u:
      lpsz = 0;
      v6 = StringFromCLSID(rclsid[1], &lpsz);
      if ( v6 >= 0 )
      {
        v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string);
        CoTaskMemFree(lpsz);
      }
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x525,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v6,
          (int)rclsid);
      break;
  }
  v9 = WindowsDuplicateString(string, a4);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x529,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v9,
      (int)rclsid);
  WindowsDeleteString(string);
  string = 0;
  PropVariantClear((PROPVARIANT *)rclsid);
  return 0;
}

```

## disassembly

```asm
0x18004d578  mov     [rsp-8+arg_10], rbx
0x18004d57d  mov     [rsp-8+arg_18], rdi
0x18004d582  mov     [rsp-8+string], rcx
0x18004d587  push    rbp
0x18004d588  mov     rbp, rsp
0x18004d58b  sub     rsp, 50h
0x18004d58f  mov     rdi, r9
0x18004d592  mov     r10, r8
0x18004d595  mov     rcx, rdx
0x18004d598  xorps   xmm0, xmm0
0x18004d59b  xor     eax, eax
0x18004d59d  movups  xmmword ptr [rbp+rclsid], xmm0
0x18004d5a1  mov     [rbp+var_10], rax
0x18004d5a5  lea     rax, [rbp+rclsid]
0x18004d5a9  mov     [rbp+var_30], rax
0x18004d5ad  mov     [rbp+var_28], 1
0x18004d5b1  mov     [rbp+string], 0
0x18004d5b9  mov     rax, [rdx]
0x18004d5bc  lea     r8, [rbp+rclsid]
0x18004d5c0  mov     rdx, r10
0x18004d5c3  mov     rax, [rax+28h]
0x18004d5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5cc  mov     rcx, [rbp+8]; this
0x18004d5d0  test    eax, eax
0x18004d5d2  jns     short loc_18004D5E9
0x18004d5d4  mov     r9d, eax; char *
0x18004d5d7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d5de  mov     edx, 513h; void *
0x18004d5e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d5e9  movzx   eax, word ptr [rbp+rclsid]
0x18004d5ed  cmp     eax, 8
0x18004d5f0  jz      loc_18004D680
0x18004d5f6  cmp     eax, 1Fh
0x18004d5f9  jz      short loc_18004D656
0x18004d5fb  cmp     eax, 48h ; 'H'
0x18004d5fe  jnz     loc_18004D6B2
0x18004d604  mov     [rbp+lpsz], 0
0x18004d60c  lea     rdx, [rbp+lpsz]; lplpsz
0x18004d610  mov     rcx, [rbp+rclsid+8]; rclsid
0x18004d614  call    cs:__imp_StringFromCLSID
0x18004d61a  mov     ebx, eax
0x18004d61c  test    eax, eax
0x18004d61e  js      short loc_18004D639
0x18004d620  lea     rdx, [rbp+lpsz]
0x18004d624  lea     rcx, [rbp+string]; string
0x18004d628  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004d62d  mov     ebx, eax
0x18004d62f  mov     rcx, [rbp+lpsz]; pv
0x18004d633  call    cs:__imp_CoTaskMemFree
0x18004d639  mov     rcx, [rbp+8]; this
0x18004d63d  test    ebx, ebx
0x18004d63f  jns     short loc_18004D6B2
0x18004d641  mov     r9d, ebx; char *
0x18004d644  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d64b  mov     edx, 525h; void *
0x18004d650  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d656  lea     rdx, [rbp+rclsid+8]
0x18004d65a  lea     rcx, [rbp+string]; string
0x18004d65e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004d663  mov     rcx, [rbp+8]; this
0x18004d667  test    eax, eax
0x18004d669  jns     short loc_18004D6B2
0x18004d66b  mov     r9d, eax; char *
0x18004d66e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d675  mov     edx, 517h; void *
0x18004d67a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d680  mov     rax, [rbp+rclsid+8]
0x18004d684  mov     [rbp+lpsz], rax
0x18004d688  lea     rdx, [rbp+lpsz]
0x18004d68c  lea     rcx, [rbp+string]; string
0x18004d690  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d695  mov     rcx, [rbp+8]; this
0x18004d699  test    eax, eax
0x18004d69b  jns     short loc_18004D6B2
0x18004d69d  mov     r9d, eax; char *
0x18004d6a0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d6a7  mov     edx, 51Ah; void *
0x18004d6ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d6b2  mov     rdx, rdi; newString
0x18004d6b5  mov     rcx, [rbp+string]; string
0x18004d6b9  call    cs:__imp_WindowsDuplicateString
0x18004d6bf  mov     rcx, [rbp+8]; this
0x18004d6c3  test    eax, eax
0x18004d6c5  jns     short loc_18004D6DC
0x18004d6c7  mov     r9d, eax; char *
0x18004d6ca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d6d1  mov     edx, 529h; void *
0x18004d6d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d6dc  mov     rcx, [rbp+string]; string
0x18004d6e0  call    cs:__imp_WindowsDeleteString
0x18004d6e6  mov     [rbp+string], 0
0x18004d6ee  lea     rcx, [rbp+rclsid]; pvar
0x18004d6f2  call    cs:__imp_PropVariantClear
0x18004d6f8  xor     eax, eax
0x18004d6fa  mov     rbx, [rsp+50h+arg_10]
0x18004d6ff  mov     rdi, [rsp+50h+arg_18]
0x18004d704  add     rsp, 50h
0x18004d708  pop     rbp
0x18004d709  retn
```
