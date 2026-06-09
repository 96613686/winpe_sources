# Windows::System::Internal::UserProfile::RemoveConnectedProfile(void)

- ea: `0x1800ce554`
- end: `0x1800ce703`
- name: `?RemoveConnectedProfile@UserProfile@Internal@System@Windows@@AEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004c560`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x18004d734`
- `0x1800ce554`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ce65c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ce65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce5d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce5d9`

## string_xrefs

- `0x1800ce5b5`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800ce629`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800ce66e`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800ce6b2`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::UserProfile::RemoveConnectedProfile(
        Windows::System::Internal::UserProfile *this)
{
  void (__fastcall *v2)(void *, __int64 *); // rbx
  __int64 v3; // rdi
  unsigned int (__fastcall *v4)(__int64, PCWSTR, _QWORD, _QWORD); // rbx
  PCWSTR StringRawBuffer; // rax
  signed int LastError; // eax
  HRESULT Instance; // eax
  wil *v9; // rcx
  int v10; // eax
  struct IConnectedUserStore *v11; // rcx
  unsigned int v13; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  int ppvb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct IConnectedUserStore *v18; // [rsp+50h] [rbp+8h] BYREF
  __int64 v19; // [rsp+58h] [rbp+10h] BYREF
  struct IConnectedUser *v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = 0;
  v2 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v2(&Windows::System::Internal::Adapters::g_AdapterCollection, &v19);
  v18 = 0;
  v20 = 0;
  if ( !*((_QWORD *)this + 15) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x595,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)0x8000FFFFLL,
      ppva);
  v3 = v19;
  v4 = *(unsigned int (__fastcall **)(__int64, PCWSTR, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL);
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
  if ( !v4(v3, StringRawBuffer, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147024894 && LastError != -2147024809 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)LastError,
        ppva);
  }
  Instance = CoCreateInstance(
               &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
               0,
               0x17u,
               &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
               (LPVOID *)&v18);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)Instance,
      ppvb);
  try
  {
    Windows::System::Internal::UserProfile::FindConnectedUser(this, v18, &v20);
  }
  catch ( ... )
  {
    v13 = wil::ResultFromCaughtException(v9);
    if ( v13 != -805305819 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)v13,
        ppv);
  }
  v10 = (*(__int64 (__fastcall **)(struct IConnectedUser *))(*(_QWORD *)v20 + 32LL))(v20);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5AC,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v10,
      ppvb);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v11 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(struct IConnectedUserStore *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  return 0;
}

```

## disassembly

```asm
0x1800ce554  push    rbx
0x1800ce556  push    rsi
0x1800ce557  push    rdi
0x1800ce558  sub     rsp, 30h
0x1800ce55c  mov     rsi, rcx
0x1800ce55f  mov     [rsp+48h+arg_8], 0
0x1800ce568  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800ce56f  mov     rbx, [rax+18h]
0x1800ce573  lea     rcx, [rsp+48h+arg_8]
0x1800ce578  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ce57d  lea     rdx, [rsp+48h+arg_8]
0x1800ce582  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800ce589  mov     rax, rbx
0x1800ce58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce591  mov     [rsp+48h+arg_0], 0
0x1800ce59a  mov     [rsp+48h+arg_10], 0
0x1800ce5a3  mov     rcx, [rsp+48h]; this
0x1800ce5a8  cmp     qword ptr [rsi+78h], 0
0x1800ce5ad  jnz     short loc_1800CE5C7
0x1800ce5af  mov     r9d, 8000FFFFh; char *
0x1800ce5b5  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800ce5bc  mov     edx, 595h; void *
0x1800ce5c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce5c7  mov     rdi, [rsp+48h+arg_8]
0x1800ce5cc  mov     rax, [rdi]
0x1800ce5cf  mov     rbx, [rax+30h]
0x1800ce5d3  xor     edx, edx; length
0x1800ce5d5  mov     rcx, [rsi+78h]; string
0x1800ce5d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ce5df  xor     r9d, r9d
0x1800ce5e2  xor     r8d, r8d
0x1800ce5e5  mov     rdx, rax
0x1800ce5e8  mov     rcx, rdi
0x1800ce5eb  mov     rax, rbx
0x1800ce5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce5f3  test    eax, eax
0x1800ce5f5  jnz     short loc_1800CE63E
0x1800ce5f7  call    cs:__imp_GetLastError
0x1800ce5fd  test    eax, eax
0x1800ce5ff  jle     short loc_1800CE609
0x1800ce601  movzx   eax, ax
0x1800ce604  or      eax, 80070000h
0x1800ce609  cmp     eax, 80070002h
0x1800ce60e  jz      short loc_1800CE61B
0x1800ce610  cmp     eax, 80070057h
0x1800ce615  jz      short loc_1800CE61B
0x1800ce617  xor     cl, cl
0x1800ce619  jmp     short loc_1800CE61D
0x1800ce61b  mov     cl, 1
0x1800ce61d  mov     r10, [rsp+48h]
0x1800ce622  test    cl, cl
0x1800ce624  jnz     short loc_1800CE63E
0x1800ce626  mov     r9d, eax; char *
0x1800ce629  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800ce630  mov     edx, 59Ah; void *
0x1800ce635  mov     rcx, r10; this
0x1800ce638  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce63e  lea     rax, [rsp+48h+arg_0]
0x1800ce643  mov     qword ptr [rsp+48h+ppv], rax; int
0x1800ce648  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x1800ce64f  xor     edx, edx; pUnkOuter
0x1800ce651  lea     r8d, [rdx+17h]; dwClsContext
0x1800ce655  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x1800ce65c  call    cs:__imp_CoCreateInstance
0x1800ce662  mov     rcx, [rsp+48h]; this
0x1800ce667  test    eax, eax
0x1800ce669  jns     short loc_1800CE680
0x1800ce66b  mov     r9d, eax; char *
0x1800ce66e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800ce675  mov     edx, 5A1h; void *
0x1800ce67a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce680  lea     r8, [rsp+48h+arg_10]; struct IConnectedUser **
0x1800ce685  mov     rdx, [rsp+48h+arg_0]; struct IConnectedUserStore *
0x1800ce68a  mov     rcx, rsi; this
0x1800ce68d  call    ?FindConnectedUser@UserProfile@Internal@System@Windows@@AEAAJPEAUIConnectedUserStore@@PEAPEAUIConnectedUser@@@Z; Windows::System::Internal::UserProfile::FindConnectedUser(IConnectedUserStore *,IConnectedUser * *)
0x1800ce692  nop
0x1800ce693  jmp     short $+2
0x1800ce695  mov     rcx, [rsp+48h+arg_10]
0x1800ce69a  mov     rax, [rcx]
0x1800ce69d  mov     rax, [rax+20h]
0x1800ce6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce6a6  mov     rcx, [rsp+48h]; this
0x1800ce6ab  test    eax, eax
0x1800ce6ad  jns     short loc_1800CE6C4
0x1800ce6af  mov     r9d, eax; char *
0x1800ce6b2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800ce6b9  mov     edx, 5ACh; void *
0x1800ce6be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce6c4  lea     rcx, [rsp+48h+arg_10]
0x1800ce6c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ce6ce  nop
0x1800ce6cf  mov     rcx, [rsp+48h+arg_0]
0x1800ce6d4  test    rcx, rcx
0x1800ce6d7  jz      short loc_1800CE6EF
0x1800ce6d9  mov     [rsp+48h+arg_0], 0
0x1800ce6e2  mov     rax, [rcx]
0x1800ce6e5  mov     rax, [rax+10h]
0x1800ce6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce6ee  nop
0x1800ce6ef  lea     rcx, [rsp+48h+arg_8]
0x1800ce6f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ce6f9  xor     eax, eax
0x1800ce6fb  add     rsp, 30h
0x1800ce6ff  pop     rdi
0x1800ce700  pop     rsi
0x1800ce701  pop     rbx
0x1800ce702  retn
```
