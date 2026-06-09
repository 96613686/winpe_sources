# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_

- ea: `0x18000a634`
- end: `0x18000a773`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_`
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
- `0x18000a634`
- `0x18000bbb0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a693`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a693`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a6db`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a6db`

## pseudocode

```c
__int64 *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_(
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
         &GUID_29a3ab33_0fd7_44f5_9bff_c0b6c081fbfb,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a634  mov     r11, rsp
0x18000a637  mov     [r11+10h], rbx
0x18000a63b  mov     [r11+18h], rsi
0x18000a63f  push    rdi
0x18000a640  sub     rsp, 60h
0x18000a644  mov     rax, cs:__security_cookie
0x18000a64b  xor     rax, rsp
0x18000a64e  mov     [rsp+68h+var_10], rax
0x18000a653  mov     rsi, rcx
0x18000a656  mov     [r11-20h], rcx
0x18000a65a  mov     [rsp+68h+var_28], 0
0x18000a662  mov     qword ptr [r11-18h], 0
0x18000a66a  lea     rcx, [r11-18h]
0x18000a66e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a673  lea     rax, [rsp+68h+pProxy]
0x18000a678  mov     [rsp+68h+ppv], rax; int
0x18000a67d  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a684  xor     r8d, r8d; pvReserved
0x18000a687  mov     edx, 100004h; dwClsContext
0x18000a68c  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a693  call    cs:__imp_CoGetClassObject
0x18000a69a  nop     dword ptr [rax+rax+00h]
0x18000a69f  mov     rcx, [rsp+68h]; this
0x18000a6a4  test    eax, eax
0x18000a6a6  js      loc_18000A765
0x18000a6ac  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a6b4  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a6bd  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a6c5  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a6cd  xor     r9d, r9d; pServerPrincName
0x18000a6d0  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a6d3  mov     r8d, edx; dwAuthzSvc
0x18000a6d6  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a6db  call    cs:__imp_CoSetProxyBlanket
0x18000a6e2  nop     dword ptr [rax+rax+00h]
0x18000a6e7  mov     qword ptr [rsi], 0
0x18000a6ee  mov     [rsp+68h+var_28], 1
0x18000a6f6  mov     rdi, [rsp+68h+pProxy]
0x18000a6fb  mov     rax, [rdi]
0x18000a6fe  mov     rbx, [rax+18h]
0x18000a702  mov     rcx, rsi
0x18000a705  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a70a  mov     r9, rsi
0x18000a70d  lea     r8, _GUID_29a3ab33_0fd7_44f5_9bff_c0b6c081fbfb
0x18000a714  xor     edx, edx
0x18000a716  mov     rcx, rdi
0x18000a719  mov     rax, rbx
0x18000a71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a721  mov     rcx, [rsp+68h]; this
0x18000a726  test    eax, eax
0x18000a728  js      short loc_18000A757
0x18000a72a  lea     rcx, [rsp+68h+pProxy]
0x18000a72f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a734  mov     rax, rsi
0x18000a737  mov     rcx, [rsp+68h+var_10]
0x18000a73c  xor     rcx, rsp; StackCookie
0x18000a73f  call    __security_check_cookie
0x18000a744  lea     r11, [rsp+68h+var_8]
0x18000a749  mov     rbx, [r11+18h]
0x18000a74d  mov     rsi, [r11+20h]
0x18000a751  mov     rsp, r11
0x18000a754  pop     rdi
0x18000a755  retn
0x18000a757  mov     r9d, eax; char *
0x18000a75a  mov     edx, 1Dh; void *
0x18000a75f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a765  mov     r9d, eax; char *
0x18000a768  mov     edx, 18h; void *
0x18000a76d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
