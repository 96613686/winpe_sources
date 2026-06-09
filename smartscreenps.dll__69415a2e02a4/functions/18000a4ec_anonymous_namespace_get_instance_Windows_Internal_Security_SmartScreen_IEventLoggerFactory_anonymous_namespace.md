# _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_

- ea: `0x18000a4ec`
- end: `0x18000a62b`
- name: `_anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x180001590`
- `0x180008828`
- `0x18000a4ec`
- `0x18000bbb0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a54b`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000a54b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a593`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a593`

## pseudocode

```c
__int64 *__fastcall anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_(
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
         &GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188,
         a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1D, v7, (const char *)(unsigned int)v6, ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&pProxy);
  return a1;
}

```

## disassembly

```asm
0x18000a4ec  mov     r11, rsp
0x18000a4ef  mov     [r11+10h], rbx
0x18000a4f3  mov     [r11+18h], rsi
0x18000a4f7  push    rdi
0x18000a4f8  sub     rsp, 60h
0x18000a4fc  mov     rax, cs:__security_cookie
0x18000a503  xor     rax, rsp
0x18000a506  mov     [rsp+68h+var_10], rax
0x18000a50b  mov     rsi, rcx
0x18000a50e  mov     [r11-20h], rcx
0x18000a512  mov     [rsp+68h+var_28], 0
0x18000a51a  mov     qword ptr [r11-18h], 0
0x18000a522  lea     rcx, [r11-18h]
0x18000a526  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a52b  lea     rax, [rsp+68h+pProxy]
0x18000a530  mov     [rsp+68h+ppv], rax; int
0x18000a535  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000a53c  xor     r8d, r8d; pvReserved
0x18000a53f  mov     edx, 100004h; dwClsContext
0x18000a544  lea     rcx, _GUID_a463fcb9_6b1c_4e0d_a80b_a2ca7999e25d; rclsid
0x18000a54b  call    cs:__imp_CoGetClassObject
0x18000a552  nop     dword ptr [rax+rax+00h]
0x18000a557  mov     rcx, [rsp+68h]; this
0x18000a55c  test    eax, eax
0x18000a55e  js      loc_18000A61D
0x18000a564  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18000a56c  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18000a575  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18000a57d  mov     dword ptr [rsp+68h+ppv], 0; int
0x18000a585  xor     r9d, r9d; pServerPrincName
0x18000a588  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a58b  mov     r8d, edx; dwAuthzSvc
0x18000a58e  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18000a593  call    cs:__imp_CoSetProxyBlanket
0x18000a59a  nop     dword ptr [rax+rax+00h]
0x18000a59f  mov     qword ptr [rsi], 0
0x18000a5a6  mov     [rsp+68h+var_28], 1
0x18000a5ae  mov     rdi, [rsp+68h+pProxy]
0x18000a5b3  mov     rax, [rdi]
0x18000a5b6  mov     rbx, [rax+18h]
0x18000a5ba  mov     rcx, rsi
0x18000a5bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a5c2  mov     r9, rsi
0x18000a5c5  lea     r8, _GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188
0x18000a5cc  xor     edx, edx
0x18000a5ce  mov     rcx, rdi
0x18000a5d1  mov     rax, rbx
0x18000a5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d9  mov     rcx, [rsp+68h]; this
0x18000a5de  test    eax, eax
0x18000a5e0  js      short loc_18000A60F
0x18000a5e2  lea     rcx, [rsp+68h+pProxy]
0x18000a5e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a5ec  mov     rax, rsi
0x18000a5ef  mov     rcx, [rsp+68h+var_10]
0x18000a5f4  xor     rcx, rsp; StackCookie
0x18000a5f7  call    __security_check_cookie
0x18000a5fc  lea     r11, [rsp+68h+var_8]
0x18000a601  mov     rbx, [r11+18h]
0x18000a605  mov     rsi, [r11+20h]
0x18000a609  mov     rsp, r11
0x18000a60c  pop     rdi
0x18000a60d  retn
0x18000a60f  mov     r9d, eax; char *
0x18000a612  mov     edx, 1Dh; void *
0x18000a617  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a61d  mov     r9d, eax; char *
0x18000a620  mov     edx, 18h; void *
0x18000a625  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
