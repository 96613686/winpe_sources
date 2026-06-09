# Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(ILightDismissProvider * *)

- ea: `0x18003ec3c`
- end: `0x18003ed94`
- name: `?_GetLightDismissManager@GenericLightDismissClient@Internal@Windows@@AEAAJPEAPEAUILightDismissProvider@@@Z`
- size: `344`
- prototype: `int(Windows::Internal::GenericLightDismissClient *__hidden this, struct ILightDismissProvider **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ea4c`

## callees

- `0x1800343ec`
- `0x18003ec3c`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003ecd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003ecd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ec5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ec5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed68`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18003ecb1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18003ecb1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18003ec6d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18003ec6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(
        Windows::Internal::GenericLightDismissClient *this,
        LPVOID *a2)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rcx
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+38h] [rbp-40h] BYREF
  wchar_t v9; // [rsp+48h] [rbp-30h]
  _BYTE pvInfo[16]; // [rsp+50h] [rbp-28h] BYREF
  __int16 v11; // [rsp+60h] [rbp-18h]

  *a2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop
    && (v8 = *(_OWORD *)L"Winlogon", v9 = aWinlogon[8], GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0))
    && (v11 = 0, !(unsigned int)_o__wcsicmp(pvInfo, &v8)) )
  {
    v5 = 0;
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v5 = CoCreateInstance(&CLSID_ImmersiveShellBroker, 0, 4u, &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c, &ppv);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv + 24LL))(ppv, a2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  if ( !*a2 )
    return (unsigned int)CoCreateInstance(
                           &CLSID_SimpleLightDismissProvider,
                           0,
                           1u,
                           &GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44,
                           a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ec3c  mov     [rsp+arg_0], rbx
0x18003ec41  push    rdi
0x18003ec42  sub     rsp, 70h
0x18003ec46  mov     rax, cs:__security_cookie
0x18003ec4d  xor     rax, rsp
0x18003ec50  mov     [rsp+78h+var_10], rax
0x18003ec55  mov     rdi, rdx
0x18003ec58  mov     qword ptr [rdx], 0
0x18003ec5f  call    cs:__imp_GetCurrentThreadId
0x18003ec66  nop     dword ptr [rax+rax+00h]
0x18003ec6b  mov     ecx, eax; dwThreadId
0x18003ec6d  call    cs:__imp_GetThreadDesktop
0x18003ec74  nop     dword ptr [rax+rax+00h]
0x18003ec79  mov     rcx, rax; hObj
0x18003ec7c  test    rax, rax
0x18003ec7f  jz      short loc_18003ECE6
0x18003ec81  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x18003ec88  movups  [rsp+78h+var_40], xmm0
0x18003ec8d  movzx   eax, word ptr cs:aWinlogon+10h; ""
0x18003ec94  mov     [rsp+78h+var_30], ax
0x18003ec99  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x18003eca2  mov     r9d, 12h; nLength
0x18003eca8  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x18003ecad  lea     edx, [r9-10h]; nIndex
0x18003ecb1  call    cs:__imp_GetUserObjectInformationW
0x18003ecb8  nop     dword ptr [rax+rax+00h]
0x18003ecbd  test    eax, eax
0x18003ecbf  jz      short loc_18003ECE6
0x18003ecc1  xor     eax, eax
0x18003ecc3  mov     [rsp+78h+var_18], ax
0x18003ecc8  lea     rdx, [rsp+78h+var_40]
0x18003eccd  lea     rcx, [rsp+78h+pvInfo]
0x18003ecd2  call    cs:__imp__o__wcsicmp
0x18003ecd9  nop     dword ptr [rax+rax+00h]
0x18003ecde  test    eax, eax
0x18003ece0  jnz     short loc_18003ECE6
0x18003ece2  xor     ebx, ebx
0x18003ece4  jmp     short loc_18003ED49
0x18003ece6  mov     [rsp+78h+ppv], 0
0x18003ecef  lea     rcx, [rsp+78h+ppv]
0x18003ecf4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ecf9  lea     rax, [rsp+78h+ppv]
0x18003ecfe  mov     [rsp+78h+lpnLengthNeeded], rax; ppv
0x18003ed03  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x18003ed0a  xor     edx, edx; pUnkOuter
0x18003ed0c  lea     r8d, [rdx+4]; dwClsContext
0x18003ed10  lea     rcx, CLSID_ImmersiveShellBroker; rclsid
0x18003ed17  call    cs:__imp_CoCreateInstance
0x18003ed1e  nop     dword ptr [rax+rax+00h]
0x18003ed23  mov     ebx, eax
0x18003ed25  test    eax, eax
0x18003ed27  js      short loc_18003ED3F
0x18003ed29  mov     rcx, [rsp+78h+ppv]
0x18003ed2e  mov     rax, [rcx]
0x18003ed31  mov     rdx, rdi
0x18003ed34  mov     rax, [rax+18h]
0x18003ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed3d  mov     ebx, eax
0x18003ed3f  lea     rcx, [rsp+78h+ppv]
0x18003ed44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ed49  cmp     qword ptr [rdi], 0
0x18003ed4d  jnz     short loc_18003ED76
0x18003ed4f  mov     [rsp+78h+lpnLengthNeeded], rdi; ppv
0x18003ed54  lea     r9, _GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44; riid
0x18003ed5b  xor     edx, edx; pUnkOuter
0x18003ed5d  lea     r8d, [rdx+1]; dwClsContext
0x18003ed61  lea     rcx, CLSID_SimpleLightDismissProvider; rclsid
0x18003ed68  call    cs:__imp_CoCreateInstance
0x18003ed6f  nop     dword ptr [rax+rax+00h]
0x18003ed74  mov     ebx, eax
0x18003ed76  mov     eax, ebx
0x18003ed78  mov     rcx, [rsp+78h+var_10]
0x18003ed7d  xor     rcx, rsp; StackCookie
0x18003ed80  call    __security_check_cookie
0x18003ed85  mov     rbx, [rsp+78h+arg_0]
0x18003ed8d  add     rsp, 70h
0x18003ed91  pop     rdi
0x18003ed92  retn
```
