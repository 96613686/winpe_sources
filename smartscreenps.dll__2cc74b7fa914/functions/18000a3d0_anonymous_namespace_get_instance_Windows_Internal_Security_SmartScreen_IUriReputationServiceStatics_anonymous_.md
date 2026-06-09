# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_

- ea: `0x18000a3d0`
- end: `0x18000a502`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_`
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
- `0x18000a3d0`
- `0x18000b8e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a42f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a42f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a471`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a471`

## pseudocode

```c
_QWORD *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_(
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
         &GUID_29a3ab33_0fd7_44f5_9bff_c0b6c081fbfb,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a3d0  mov     r11, rsp
0x18000a3d3  mov     [r11+10h], rbx
0x18000a3d7  mov     [r11+18h], rsi
0x18000a3db  push    rdi
0x18000a3dc  sub     rsp, 60h
0x18000a3e0  mov     rax, cs:__security_cookie
0x18000a3e7  xor     rax, rsp
0x18000a3ea  mov     [rsp+68h+var_10], rax
0x18000a3ef  mov     rsi, rcx
0x18000a3f2  mov     [r11-20h], rcx
0x18000a3f6  mov     [rsp+68h+var_28], 0
0x18000a3fe  mov     qword ptr [r11-18h], 0
0x18000a406  lea     rcx, [r11-18h]
0x18000a40a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a40f  lea     rax, [rsp+68h+pProxy]
0x18000a414  mov     [rsp+68h+ppv], rax; int
0x18000a419  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a420  xor     r8d, r8d; pvReserved
0x18000a423  mov     edx, 100004h; dwClsContext
0x18000a428  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a42f  call    cs:__imp_CoGetClassObject
0x18000a435  mov     rcx, [rsp+68h]; this
0x18000a43a  test    eax, eax
0x18000a43c  js      loc_18000A4F4
0x18000a442  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a44a  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a453  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a45b  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a463  xor     r9d, r9d; pServerPrincName
0x18000a466  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a469  mov     r8d, edx; dwAuthzSvc
0x18000a46c  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a471  call    cs:__imp_CoSetProxyBlanket
0x18000a477  mov     qword ptr [rsi], 0
0x18000a47e  mov     [rsp+68h+var_28], 1
0x18000a486  mov     rdi, [rsp+68h+pProxy]
0x18000a48b  mov     rax, [rdi]
0x18000a48e  mov     rbx, [rax+18h]
0x18000a492  mov     rcx, rsi
0x18000a495  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a49a  mov     r9, rsi
0x18000a49d  lea     r8, _GUID_29a3ab33_0fd7_44f5_9bff_c0b6c081fbfb
0x18000a4a4  xor     edx, edx
0x18000a4a6  mov     rcx, rdi
0x18000a4a9  mov     rax, rbx
0x18000a4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b1  mov     rcx, [rsp+68h]; this
0x18000a4b6  test    eax, eax
0x18000a4b8  js      short loc_18000A4E6
0x18000a4ba  lea     rcx, [rsp+68h+pProxy]
0x18000a4bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a4c4  mov     rax, rsi
0x18000a4c7  mov     rcx, [rsp+68h+var_10]
0x18000a4cc  xor     rcx, rsp; StackCookie
0x18000a4cf  call    __security_check_cookie
0x18000a4d4  lea     r11, [rsp+68h+var_8]
0x18000a4d9  mov     rbx, [r11+18h]
0x18000a4dd  mov     rsi, [r11+20h]
0x18000a4e1  mov     rsp, r11
0x18000a4e4  pop     rdi
0x18000a4e5  retn
0x18000a4e6  mov     r9d, eax; char *
0x18000a4e9  mov     edx, 1Dh; void *
0x18000a4ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a4f4  mov     r9d, eax; char *
0x18000a4f7  mov     edx, 18h; void *
0x18000a4fc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
