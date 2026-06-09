# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_

- ea: `0x18000a3a4`
- end: `0x18000a4e3`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x180001590`
- `0x180008828`
- `0x18000a3a4`
- `0x18000bbb0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a403`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a403`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a44b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a44b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_(
        __int64 *a1)
{
  HRESULT ClassObject; // eax
  __int64 v3; // r8
  IUnknown *v4; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  __int64 v7; // r8
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  IUnknown *pProxy; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pProxy = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&pProxy);
  ClassObject = CoGetClassObject(
                  &GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d,
                  0x100004u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  (LPVOID *)&pProxy);
  if ( ClassObject < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x18, v3, (const char *)(unsigned int)ClassObject, ppv);
  CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x800u);
  *a1 = 0;
  v4 = pProxy;
  QueryInterface = pProxy->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, __int64 *))QueryInterface)(
         v4,
         0,
         &GUID_d9dc3975_1062_470a_994c_409151ff8f54,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a3a4  mov     r11, rsp
0x18000a3a7  mov     [r11+10h], rbx
0x18000a3ab  mov     [r11+18h], rsi
0x18000a3af  push    rdi
0x18000a3b0  sub     rsp, 60h
0x18000a3b4  mov     rax, cs:__security_cookie
0x18000a3bb  xor     rax, rsp
0x18000a3be  mov     [rsp+68h+var_10], rax
0x18000a3c3  mov     rsi, rcx
0x18000a3c6  mov     [r11-20h], rcx
0x18000a3ca  mov     [rsp+68h+var_28], 0
0x18000a3d2  mov     qword ptr [r11-18h], 0
0x18000a3da  lea     rcx, [r11-18h]
0x18000a3de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a3e3  lea     rax, [rsp+68h+pProxy]
0x18000a3e8  mov     [rsp+68h+ppv], rax; int
0x18000a3ed  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a3f4  xor     r8d, r8d; pvReserved
0x18000a3f7  mov     edx, 100004h; dwClsContext
0x18000a3fc  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a403  call    cs:__imp_CoGetClassObject
0x18000a40a  nop     dword ptr [rax+rax+00h]
0x18000a40f  mov     rcx, [rsp+68h]; this
0x18000a414  test    eax, eax
0x18000a416  js      loc_18000A4D5
0x18000a41c  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a424  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a42d  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a435  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a43d  xor     r9d, r9d; pServerPrincName
0x18000a440  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a443  mov     r8d, edx; dwAuthzSvc
0x18000a446  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a44b  call    cs:__imp_CoSetProxyBlanket
0x18000a452  nop     dword ptr [rax+rax+00h]
0x18000a457  mov     qword ptr [rsi], 0
0x18000a45e  mov     [rsp+68h+var_28], 1
0x18000a466  mov     rdi, [rsp+68h+pProxy]
0x18000a46b  mov     rax, [rdi]
0x18000a46e  mov     rbx, [rax+18h]
0x18000a472  mov     rcx, rsi
0x18000a475  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a47a  mov     r9, rsi
0x18000a47d  lea     r8, _GUID_d9dc3975_1062_470a_994c_409151ff8f54
0x18000a484  xor     edx, edx
0x18000a486  mov     rcx, rdi
0x18000a489  mov     rax, rbx
0x18000a48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a491  mov     rcx, [rsp+68h]; this
0x18000a496  test    eax, eax
0x18000a498  js      short loc_18000A4C7
0x18000a49a  lea     rcx, [rsp+68h+pProxy]
0x18000a49f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a4a4  mov     rax, rsi
0x18000a4a7  mov     rcx, [rsp+68h+var_10]
0x18000a4ac  xor     rcx, rsp; StackCookie
0x18000a4af  call    __security_check_cookie
0x18000a4b4  lea     r11, [rsp+68h+var_8]
0x18000a4b9  mov     rbx, [r11+18h]
0x18000a4bd  mov     rsi, [r11+20h]
0x18000a4c1  mov     rsp, r11
0x18000a4c4  pop     rdi
0x18000a4c5  retn
0x18000a4c7  mov     r9d, eax; char *
0x18000a4ca  mov     edx, 1Dh; void *
0x18000a4cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a4d5  mov     r9d, eax; char *
0x18000a4d8  mov     edx, 18h; void *
0x18000a4dd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
