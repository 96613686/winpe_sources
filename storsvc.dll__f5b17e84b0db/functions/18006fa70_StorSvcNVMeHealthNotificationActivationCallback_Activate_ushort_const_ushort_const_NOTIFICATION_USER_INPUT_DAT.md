# StorSvcNVMeHealthNotificationActivationCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x18006fa70`
- end: `0x18006fb1c`
- name: `?Activate@StorSvcNVMeHealthNotificationActivationCallback@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `172`
- prototype: `__int64 __fastcall(StorSvcNVMeHealthNotificationActivationCallback *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180014a00`
- `0x18006fa70`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fab5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fab5`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18006fac8`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18006fac8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorSvcNVMeHealthNotificationActivationCallback::Activate(
        StorSvcNVMeHealthNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  HRESULT Instance; // ebx
  int v7; // [rsp+30h] [rbp-18h] BYREF
  IUnknown *pUnk[2]; // [rsp+38h] [rbp-10h] BYREF

  pUnk[0] = 0;
  v7 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(pUnk);
  Instance = CoCreateInstance(
               &CLSID_ApplicationActivationManager,
               0,
               4u,
               &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
               (LPVOID *)pUnk);
  if ( Instance >= 0 )
  {
    Instance = CoAllowSetForegroundWindow(pUnk[0], 0);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const unsigned __int16 *, _QWORD, int *))pUnk[0]->lpVtbl[1].QueryInterface)(
                   pUnk[0],
                   L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                   a3,
                   0,
                   &v7);
      if ( Instance >= 0 )
        Instance = 0;
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(pUnk);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006fa70  mov     rax, rsp
0x18006fa73  mov     [rax+8], rbx
0x18006fa77  push    rdi
0x18006fa78  sub     rsp, 40h
0x18006fa7c  mov     rdi, r8
0x18006fa7f  mov     qword ptr [rax-10h], 0
0x18006fa87  mov     dword ptr [rax-18h], 0
0x18006fa8e  lea     rcx, [rax-10h]
0x18006fa92  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006fa97  lea     rax, [rsp+48h+pUnk]
0x18006fa9c  mov     [rsp+48h+ppv], rax; ppv
0x18006faa1  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x18006faa8  xor     edx, edx; pUnkOuter
0x18006faaa  lea     r8d, [rdx+4]; dwClsContext
0x18006faae  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x18006fab5  call    cs:__imp_CoCreateInstance
0x18006fabb  mov     ebx, eax
0x18006fabd  test    eax, eax
0x18006fabf  js      short loc_18006FB05
0x18006fac1  xor     edx, edx; lpvReserved
0x18006fac3  mov     rcx, [rsp+48h+pUnk]; pUnk
0x18006fac8  call    cs:__imp_CoAllowSetForegroundWindow
0x18006face  mov     ebx, eax
0x18006fad0  test    eax, eax
0x18006fad2  js      short loc_18006FB05
0x18006fad4  mov     rcx, [rsp+48h+pUnk]
0x18006fad9  mov     rax, [rcx]
0x18006fadc  lea     rdx, [rsp+48h+var_18]
0x18006fae1  mov     [rsp+48h+ppv], rdx
0x18006fae6  xor     r9d, r9d
0x18006fae9  mov     r8, rdi
0x18006faec  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18006faf3  mov     rax, [rax+18h]
0x18006faf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fafc  mov     ebx, eax
0x18006fafe  xor     eax, eax
0x18006fb00  test    ebx, ebx
0x18006fb02  cmovns  ebx, eax
0x18006fb05  lea     rcx, [rsp+48h+pUnk]
0x18006fb0a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006fb0f  mov     eax, ebx
0x18006fb11  mov     rbx, [rsp+48h+arg_0]
0x18006fb16  add     rsp, 40h
0x18006fb1a  pop     rdi
0x18006fb1b  retn
```
