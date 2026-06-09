# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_

- ea: `0x18000a298`
- end: `0x18000a3ca`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_`
- size: `306`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180001590`
- `0x18000871c`
- `0x18000a298`
- `0x18000b8e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a2f7`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a2f7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a339`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a339`

## pseudocode

```c
_QWORD *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_(
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
         &GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a298  mov     r11, rsp
0x18000a29b  mov     [r11+10h], rbx
0x18000a29f  mov     [r11+18h], rsi
0x18000a2a3  push    rdi
0x18000a2a4  sub     rsp, 60h
0x18000a2a8  mov     rax, cs:__security_cookie
0x18000a2af  xor     rax, rsp
0x18000a2b2  mov     [rsp+68h+var_10], rax
0x18000a2b7  mov     rsi, rcx
0x18000a2ba  mov     [r11-20h], rcx
0x18000a2be  mov     [rsp+68h+var_28], 0
0x18000a2c6  mov     qword ptr [r11-18h], 0
0x18000a2ce  lea     rcx, [r11-18h]
0x18000a2d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a2d7  lea     rax, [rsp+68h+pProxy]
0x18000a2dc  mov     [rsp+68h+ppv], rax; int
0x18000a2e1  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a2e8  xor     r8d, r8d; pvReserved
0x18000a2eb  mov     edx, 100004h; dwClsContext
0x18000a2f0  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a2f7  call    cs:__imp_CoGetClassObject
0x18000a2fd  mov     rcx, [rsp+68h]; this
0x18000a302  test    eax, eax
0x18000a304  js      loc_18000A3BC
0x18000a30a  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a312  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a31b  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a323  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a32b  xor     r9d, r9d; pServerPrincName
0x18000a32e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a331  mov     r8d, edx; dwAuthzSvc
0x18000a334  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a339  call    cs:__imp_CoSetProxyBlanket
0x18000a33f  mov     qword ptr [rsi], 0
0x18000a346  mov     [rsp+68h+var_28], 1
0x18000a34e  mov     rdi, [rsp+68h+pProxy]
0x18000a353  mov     rax, [rdi]
0x18000a356  mov     rbx, [rax+18h]
0x18000a35a  mov     rcx, rsi
0x18000a35d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a362  mov     r9, rsi
0x18000a365  lea     r8, _GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188
0x18000a36c  xor     edx, edx
0x18000a36e  mov     rcx, rdi
0x18000a371  mov     rax, rbx
0x18000a374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a379  mov     rcx, [rsp+68h]; this
0x18000a37e  test    eax, eax
0x18000a380  js      short loc_18000A3AE
0x18000a382  lea     rcx, [rsp+68h+pProxy]
0x18000a387  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a38c  mov     rax, rsi
0x18000a38f  mov     rcx, [rsp+68h+var_10]
0x18000a394  xor     rcx, rsp; StackCookie
0x18000a397  call    __security_check_cookie
0x18000a39c  lea     r11, [rsp+68h+var_8]
0x18000a3a1  mov     rbx, [r11+18h]
0x18000a3a5  mov     rsi, [r11+20h]
0x18000a3a9  mov     rsp, r11
0x18000a3ac  pop     rdi
0x18000a3ad  retn
0x18000a3ae  mov     r9d, eax; char *
0x18000a3b1  mov     edx, 1Dh; void *
0x18000a3b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a3bc  mov     r9d, eax; char *
0x18000a3bf  mov     edx, 18h; void *
0x18000a3c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
