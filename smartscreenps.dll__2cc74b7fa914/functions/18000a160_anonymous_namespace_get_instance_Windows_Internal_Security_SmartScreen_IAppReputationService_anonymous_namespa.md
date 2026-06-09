# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_

- ea: `0x18000a160`
- end: `0x18000a292`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_`
- size: `306`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180001590`
- `0x18000871c`
- `0x18000a160`
- `0x18000b8e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a1bf`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a1bf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a201`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a201`

## pseudocode

```c
_QWORD *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_(
        _QWORD *a1)
{
  HRESULT ClassObject; // eax
  unsigned int v3; // r8d
  IUnknown *v4; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  unsigned int v7; // r8d
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  IUnknown *pProxy; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pProxy = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
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
  v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, _QWORD *))QueryInterface)(
         v4,
         0,
         &GUID_d9dc3975_1062_470a_994c_409151ff8f54,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a160  mov     r11, rsp
0x18000a163  mov     [r11+10h], rbx
0x18000a167  mov     [r11+18h], rsi
0x18000a16b  push    rdi
0x18000a16c  sub     rsp, 60h
0x18000a170  mov     rax, cs:__security_cookie
0x18000a177  xor     rax, rsp
0x18000a17a  mov     [rsp+68h+var_10], rax
0x18000a17f  mov     rsi, rcx
0x18000a182  mov     [r11-20h], rcx
0x18000a186  mov     [rsp+68h+var_28], 0
0x18000a18e  mov     qword ptr [r11-18h], 0
0x18000a196  lea     rcx, [r11-18h]
0x18000a19a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a19f  lea     rax, [rsp+68h+pProxy]
0x18000a1a4  mov     [rsp+68h+ppv], rax; int
0x18000a1a9  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a1b0  xor     r8d, r8d; pvReserved
0x18000a1b3  mov     edx, 100004h; dwClsContext
0x18000a1b8  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a1bf  call    cs:__imp_CoGetClassObject
0x18000a1c5  mov     rcx, [rsp+68h]; this
0x18000a1ca  test    eax, eax
0x18000a1cc  js      loc_18000A284
0x18000a1d2  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a1da  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a1e3  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a1eb  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a1f3  xor     r9d, r9d; pServerPrincName
0x18000a1f6  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a1f9  mov     r8d, edx; dwAuthzSvc
0x18000a1fc  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a201  call    cs:__imp_CoSetProxyBlanket
0x18000a207  mov     qword ptr [rsi], 0
0x18000a20e  mov     [rsp+68h+var_28], 1
0x18000a216  mov     rdi, [rsp+68h+pProxy]
0x18000a21b  mov     rax, [rdi]
0x18000a21e  mov     rbx, [rax+18h]
0x18000a222  mov     rcx, rsi
0x18000a225  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a22a  mov     r9, rsi
0x18000a22d  lea     r8, _GUID_d9dc3975_1062_470a_994c_409151ff8f54
0x18000a234  xor     edx, edx
0x18000a236  mov     rcx, rdi
0x18000a239  mov     rax, rbx
0x18000a23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a241  mov     rcx, [rsp+68h]; this
0x18000a246  test    eax, eax
0x18000a248  js      short loc_18000A276
0x18000a24a  lea     rcx, [rsp+68h+pProxy]
0x18000a24f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a254  mov     rax, rsi
0x18000a257  mov     rcx, [rsp+68h+var_10]
0x18000a25c  xor     rcx, rsp; StackCookie
0x18000a25f  call    __security_check_cookie
0x18000a264  lea     r11, [rsp+68h+var_8]
0x18000a269  mov     rbx, [r11+18h]
0x18000a26d  mov     rsi, [r11+20h]
0x18000a271  mov     rsp, r11
0x18000a274  pop     rdi
0x18000a275  retn
0x18000a276  mov     r9d, eax; char *
0x18000a279  mov     edx, 1Dh; void *
0x18000a27e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a284  mov     r9d, eax; char *
0x18000a287  mov     edx, 18h; void *
0x18000a28c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
