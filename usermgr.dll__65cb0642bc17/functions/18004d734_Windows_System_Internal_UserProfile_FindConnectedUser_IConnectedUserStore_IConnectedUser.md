# Windows::System::Internal::UserProfile::FindConnectedUser(IConnectedUserStore *,IConnectedUser * *)

- ea: `0x18004d734`
- end: `0x18004d9fc`
- name: `?FindConnectedUser@UserProfile@Internal@System@Windows@@AEAAJPEAUIConnectedUserStore@@PEAPEAUIConnectedUser@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserProfile *__hidden this, struct IConnectedUserStore *, struct IConnectedUser **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004cf48`
- `0x1800ce554`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x18004d734`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d7d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d8c7`

## string_xrefs

- `0x18004d79d`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d7e4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d815`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004d98e`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::System::Internal::UserProfile::FindConnectedUser(
        HSTRING *this,
        struct IConnectedUserStore *a2,
        struct IConnectedUser **a3)
{
  HRESULT v6; // eax
  int v7; // eax
  unsigned int i; // esi
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, __int128 *, __int64 *); // rbx
  int v11; // eax
  int (__fastcall *v12)(struct IConnectedUserStore *, PCWSTR, _QWORD, __int128 *, struct IConnectedUser **); // rbx
  PCWSTR StringRawBuffer; // rax
  int (__fastcall *v14)(struct IConnectedUserStore *, PCWSTR, _QWORD, __int128 *); // rbx
  PCWSTR v15; // rax
  struct IConnectedUser *v16; // rcx
  LPVOID v17; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID *ppva; // [rsp+20h] [rbp-60h]
  struct IConnectedUser *v21; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-40h] BYREF
  __int64 v24; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  __int128 v27; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v22 = 0;
  v21 = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  v27 = 0;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)0x80004003LL,
      ppv);
  *a3 = 0;
  v6 = CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         0x17u,
         &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
         &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x435,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v6,
      (int)ppva);
  v7 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x437,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v7,
      (int)ppva);
  for ( i = 0; i < v23; ++i )
  {
    v24 = 0;
    v9 = v22;
    v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *, __int64 *))(*(_QWORD *)v22 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v11 = v10(v9, i, &v27, &v24);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v11,
        (int)ppva);
    v12 = *(int (__fastcall **)(struct IConnectedUserStore *, PCWSTR, _QWORD, __int128 *, struct IConnectedUser **))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    StringRawBuffer = WindowsGetStringRawBuffer(this[11], 0);
    if ( v12(a2, StringRawBuffer, 0, &v27, &v21) >= 0 )
    {
      v16 = v21;
      if ( v21 )
      {
        (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v21 + 8LL))(v21);
        v16 = v21;
      }
      goto LABEL_15;
    }
    v14 = *(int (__fastcall **)(struct IConnectedUserStore *, PCWSTR, _QWORD, __int128 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v15 = WindowsGetStringRawBuffer(this[12], 0);
    ppva = (LPVOID *)&v21;
    if ( v14(a2, v15, 0, &v27) >= 0 )
    {
      v16 = v21;
      if ( v21 )
      {
        (*(void (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v21 + 8LL))(v21);
        v16 = v21;
      }
LABEL_15:
      *a3 = v16;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      goto LABEL_21;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
LABEL_21:
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18004d734  push    rbp
0x18004d736  push    rbx
0x18004d737  push    rsi
0x18004d738  push    rdi
0x18004d739  push    r13
0x18004d73b  push    r14
0x18004d73d  push    r15
0x18004d73f  mov     rbp, rsp
0x18004d742  sub     rsp, 80h
0x18004d749  mov     rax, cs:__security_cookie
0x18004d750  xor     rax, rsp
0x18004d753  mov     [rbp+var_10], rax
0x18004d757  mov     r14, r8
0x18004d75a  mov     r15, rdx
0x18004d75d  mov     r13, rcx
0x18004d760  mov     [rbp+var_48], 0
0x18004d768  mov     [rbp+var_50], 0
0x18004d770  mov     [rbp+var_28], 0
0x18004d778  mov     [rbp+var_30], 0
0x18004d780  mov     [rbp+var_40], 0
0x18004d787  xorps   xmm0, xmm0
0x18004d78a  movups  [rbp+var_20], xmm0
0x18004d78e  mov     rcx, [rbp+38h]; this
0x18004d792  test    r8, r8
0x18004d795  jnz     short loc_18004D7AF
0x18004d797  mov     r9d, 80004003h; char *
0x18004d79d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d7a4  mov     edx, 42Fh; void *
0x18004d7a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d7af  mov     qword ptr [r8], 0
0x18004d7b6  lea     rax, [rbp+var_48]
0x18004d7ba  mov     [rsp+80h+ppv], rax; int
0x18004d7bf  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18004d7c6  xor     edx, edx; pUnkOuter
0x18004d7c8  lea     r8d, [rdx+17h]; dwClsContext
0x18004d7cc  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18004d7d3  call    cs:__imp_CoCreateInstance
0x18004d7d9  mov     rcx, [rbp+38h]; this
0x18004d7dd  test    eax, eax
0x18004d7df  jns     short loc_18004D7F6
0x18004d7e1  mov     r9d, eax; char *
0x18004d7e4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d7eb  mov     edx, 435h; void *
0x18004d7f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d7f6  mov     rcx, [rbp+var_48]
0x18004d7fa  mov     rax, [rcx]
0x18004d7fd  lea     rdx, [rbp+var_40]
0x18004d801  mov     rax, [rax+18h]
0x18004d805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d80a  mov     rcx, [rbp+38h]; this
0x18004d80e  test    eax, eax
0x18004d810  jns     short loc_18004D827
0x18004d812  mov     r9d, eax; char *
0x18004d815  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d81c  mov     edx, 437h; void *
0x18004d821  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d827  xor     esi, esi
0x18004d829  cmp     esi, [rbp+var_40]
0x18004d82c  jnb     loc_18004D9A0
0x18004d832  mov     [rbp+var_38], 0
0x18004d83a  mov     rdi, [rbp+var_48]
0x18004d83e  mov     rax, [rdi]
0x18004d841  mov     rbx, [rax+20h]
0x18004d845  lea     rcx, [rbp+var_38]
0x18004d849  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d84e  lea     r9, [rbp+var_38]
0x18004d852  lea     r8, [rbp+var_20]
0x18004d856  mov     edx, esi
0x18004d858  mov     rcx, rdi
0x18004d85b  mov     rax, rbx
0x18004d85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d863  mov     rcx, [rbp+38h]; this
0x18004d867  test    eax, eax
0x18004d869  js      loc_18004D98B
0x18004d86f  mov     rax, [r15]
0x18004d872  mov     rbx, [rax+30h]
0x18004d876  lea     rcx, [rbp+var_50]
0x18004d87a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d87f  xor     edx, edx; length
0x18004d881  mov     rcx, [r13+58h]; string
0x18004d885  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d88b  lea     rcx, [rbp+var_50]
0x18004d88f  mov     [rsp+80h+ppv], rcx
0x18004d894  lea     r9, [rbp+var_20]
0x18004d898  xor     r8d, r8d
0x18004d89b  mov     rdx, rax
0x18004d89e  mov     rcx, r15
0x18004d8a1  mov     rax, rbx
0x18004d8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8a9  test    eax, eax
0x18004d8ab  jns     loc_18004D945
0x18004d8b1  mov     rax, [r15]
0x18004d8b4  mov     rbx, [rax+30h]
0x18004d8b8  lea     rcx, [rbp+var_50]
0x18004d8bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8c1  xor     edx, edx; length
0x18004d8c3  mov     rcx, [r13+60h]; string
0x18004d8c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d8cd  lea     rcx, [rbp+var_50]
0x18004d8d1  mov     [rsp+80h+ppv], rcx
0x18004d8d6  lea     r9, [rbp+var_20]
0x18004d8da  xor     r8d, r8d
0x18004d8dd  mov     rdx, rax
0x18004d8e0  mov     rcx, r15
0x18004d8e3  mov     rax, rbx
0x18004d8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8eb  test    eax, eax
0x18004d8ed  jns     short loc_18004D8FF
0x18004d8ef  lea     rcx, [rbp+var_38]
0x18004d8f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8f8  inc     esi
0x18004d8fa  jmp     loc_18004D829
0x18004d8ff  mov     rcx, [rbp+var_50]
0x18004d903  test    rcx, rcx
0x18004d906  jz      short loc_18004D918
0x18004d908  mov     rax, [rcx]
0x18004d90b  mov     rax, [rax+8]
0x18004d90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d914  mov     rcx, [rbp+var_50]
0x18004d918  mov     [r14], rcx
0x18004d91b  lea     rcx, [rbp+var_38]
0x18004d91f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d924  nop
0x18004d925  lea     rcx, [rbp+var_30]
0x18004d929  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d92e  nop
0x18004d92f  lea     rcx, [rbp+var_28]
0x18004d933  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d938  nop
0x18004d939  lea     rcx, [rbp+var_50]
0x18004d93d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d942  nop
0x18004d943  jmp     short loc_18004D9BE
0x18004d945  mov     rcx, [rbp+var_50]
0x18004d949  test    rcx, rcx
0x18004d94c  jz      short loc_18004D95E
0x18004d94e  mov     rax, [rcx]
0x18004d951  mov     rax, [rax+8]
0x18004d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d95a  mov     rcx, [rbp+var_50]
0x18004d95e  mov     [r14], rcx
0x18004d961  lea     rcx, [rbp+var_38]
0x18004d965  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d96a  nop
0x18004d96b  lea     rcx, [rbp+var_30]
0x18004d96f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d974  nop
0x18004d975  lea     rcx, [rbp+var_28]
0x18004d979  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d97e  nop
0x18004d97f  lea     rcx, [rbp+var_50]
0x18004d983  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d988  nop
0x18004d989  jmp     short loc_18004D9BE
0x18004d98b  mov     r9d, eax; char *
0x18004d98e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004d995  mov     edx, 43Dh; void *
0x18004d99a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d9a0  lea     rcx, [rbp+var_30]
0x18004d9a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9a9  nop
0x18004d9aa  lea     rcx, [rbp+var_28]
0x18004d9ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9b3  nop
0x18004d9b4  lea     rcx, [rbp+var_50]
0x18004d9b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9bd  nop
0x18004d9be  mov     rcx, [rbp+var_48]
0x18004d9c2  test    rcx, rcx
0x18004d9c5  jz      short loc_18004D9DC
0x18004d9c7  mov     [rbp+var_48], 0
0x18004d9cf  mov     rax, [rcx]
0x18004d9d2  mov     rax, [rax+10h]
0x18004d9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9db  nop
0x18004d9dc  xor     eax, eax
0x18004d9de  mov     rcx, [rbp+var_10]
0x18004d9e2  xor     rcx, rsp; StackCookie
0x18004d9e5  call    __security_check_cookie
0x18004d9ea  add     rsp, 80h
0x18004d9f1  pop     r15
0x18004d9f3  pop     r14
0x18004d9f5  pop     r13
0x18004d9f7  pop     rdi
0x18004d9f8  pop     rsi
0x18004d9f9  pop     rbx
0x18004d9fa  pop     rbp
0x18004d9fb  retn
```
