# OSDeploymentRemote::RemoteDeploymentSession::~RemoteDeploymentSession(void)

- ea: `0x140011d2c`
- end: `0x140011f25`
- name: `??1RemoteDeploymentSession@OSDeploymentRemote@@UEAA@XZ`
- size: `505`
- prototype: `void __fastcall(OSDeploymentRemote::RemoteDeploymentSession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400118f0`

## callees

- `0x140002ac0`
- `0x14000c270`
- `0x140011d2c`
- `0x140018ddc`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140011ef7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140011ef7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140011dae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140011e06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140011dae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140011e06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011dbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011ec1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011dbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011ec1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011deb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011deb`

## string_xrefs

- `0x140011ea8`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x140011ddd`: `Software\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OSDeploymentRemote::RemoteDeploymentSession::~RemoteDeploymentSession(
        OSDeploymentRemote::RemoteDeploymentSession *this)
{
  WCHAR *v2; // rbx
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rcx
  HMODULE v8; // rcx
  int phkResult; // [rsp+20h] [rbp-60h]
  _QWORD v10[3]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  *(_QWORD *)this = &OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `IRemoteDeploymentSession'};
  *((_QWORD *)this + 1) = &OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'};
  v2 = (WCHAR *)((char *)this + 40);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, v2 + 196, 0, 0);
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, v2 + 149, 0, 0);
  if ( *((_DWORD *)v2 + 10) )
  {
    if ( *((_DWORD *)v2 + 7) )
    {
      v5 = *((_QWORD *)v2 + 4);
      if ( !v5 )
      {
        v6 = 2149847039LL;
        v4 = 443;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v4,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
          (const char *)v6,
          phkResult);
        goto LABEL_17;
      }
      v10[0] = 24;
      v10[2] = 60000;
      v11[0] = 0;
      v10[1] = v2;
      v11[1] = v10;
      phkResult = 5;
      v3 = (*(__int64 (__fastcall **)(__int64, int (*)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)v5 + 24LL))(
             v5,
             CWuaClassFactoryBase::ContextCallback_Unregister,
             v11,
             &IID_IContextCallback);
      if ( v3 >= 0 )
        goto LABEL_17;
      v4 = 455;
    }
    else
    {
      v3 = CWuaClassFactoryBase::UnregisterClassFactoryImpl((LPUNKNOWN)v2);
      if ( v3 >= 0 )
        goto LABEL_17;
      v4 = 439;
    }
    v6 = (unsigned int)v3;
    goto LABEL_16;
  }
LABEL_17:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  OSDeploymentInformationFactory::~OSDeploymentInformationFactory((OSDeploymentInformationFactory *)v2);
  v7 = *((_QWORD *)this + 4);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (HMODULE)*((_QWORD *)this + 3);
  if ( v8 )
    FreeLibrary(v8);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x140011d2c  mov     [rsp-8+arg_8], rbx
0x140011d31  mov     [rsp-8+arg_10], rdi
0x140011d36  push    rbp
0x140011d37  mov     rbp, rsp
0x140011d3a  sub     rsp, 80h
0x140011d41  mov     rax, cs:__security_cookie
0x140011d48  xor     rax, rsp
0x140011d4b  mov     [rbp+var_10], rax
0x140011d4f  mov     rdi, rcx
0x140011d52  lea     rax, ??_7RemoteDeploymentSession@OSDeploymentRemote@@6BIRemoteDeploymentSession@@@; const OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `IRemoteDeploymentSession'}
0x140011d59  mov     [rcx], rax
0x140011d5c  lea     rax, ??_7RemoteDeploymentSession@OSDeploymentRemote@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICancelMethodCalls@@@Details@WRL@Microsoft@@@; const OSDeploymentRemote::RemoteDeploymentSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICancelMethodCalls>'}
0x140011d63  mov     [rcx+8], rax
0x140011d67  lea     rbx, [rcx+28h]
0x140011d6b  mov     [rbp+hKey], 0
0x140011d73  lea     rax, [rbp+hKey]
0x140011d77  mov     [rsp+80h+phkResult], rax; phkResult
0x140011d7c  mov     r9d, 20006h; samDesired
0x140011d82  xor     r8d, r8d; ulOptions
0x140011d85  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\AppID"
0x140011d8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011d93  call    cs:__imp_RegOpenKeyExW
0x140011d99  test    eax, eax
0x140011d9b  js      short loc_140011DB4
0x140011d9d  lea     rdx, [rbx+188h]; lpSubKey
0x140011da4  xor     r9d, r9d; Reserved
0x140011da7  xor     r8d, r8d; samDesired
0x140011daa  mov     rcx, [rbp+hKey]; hKey
0x140011dae  call    cs:__imp_RegDeleteKeyExW
0x140011db4  mov     rcx, [rbp+hKey]; hKey
0x140011db8  test    rcx, rcx
0x140011dbb  jz      short loc_140011DC3
0x140011dbd  call    cs:__imp_RegCloseKey
0x140011dc3  mov     [rbp+hKey], 0
0x140011dcb  lea     rax, [rbp+hKey]
0x140011dcf  mov     [rsp+80h+phkResult], rax; phkResult
0x140011dd4  mov     r9d, 20006h; samDesired
0x140011dda  xor     r8d, r8d; ulOptions
0x140011ddd  lea     rdx, SubKey; "Software\\Classes\\CLSID"
0x140011de4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011deb  call    cs:__imp_RegOpenKeyExW
0x140011df1  test    eax, eax
0x140011df3  js      short loc_140011E0C
0x140011df5  lea     rdx, [rbx+12Ah]; lpSubKey
0x140011dfc  xor     r9d, r9d; Reserved
0x140011dff  xor     r8d, r8d; samDesired
0x140011e02  mov     rcx, [rbp+hKey]; hKey
0x140011e06  call    cs:__imp_RegDeleteKeyExW
0x140011e0c  cmp     dword ptr [rbx+28h], 0
0x140011e10  jz      loc_140011EB8
0x140011e16  cmp     dword ptr [rbx+1Ch], 0
0x140011e1a  jnz     short loc_140011E33
0x140011e1c  mov     rcx, rbx; pUnk
0x140011e1f  call    ?UnregisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::UnregisterClassFactoryImpl(void)
0x140011e24  test    eax, eax
0x140011e26  jns     loc_140011EB8
0x140011e2c  mov     edx, 1B7h
0x140011e31  jmp     short loc_140011EA5
0x140011e33  mov     rcx, [rbx+20h]
0x140011e37  test    rcx, rcx
0x140011e3a  jnz     short loc_140011E49
0x140011e3c  mov     r9d, 80240FFFh
0x140011e42  mov     edx, 1BBh
0x140011e47  jmp     short loc_140011EA8
0x140011e49  mov     [rbp+var_40], 18h
0x140011e51  mov     [rbp+var_30], 0EA60h
0x140011e59  mov     [rbp+var_28], 0
0x140011e61  mov     [rbp+var_38], rbx
0x140011e65  lea     rax, [rbp+var_40]
0x140011e69  mov     [rbp+var_20], rax
0x140011e6d  mov     rax, [rcx]
0x140011e70  mov     [rsp+80h+var_58], 0
0x140011e79  mov     dword ptr [rsp+80h+phkResult], 5; int
0x140011e81  lea     r9, IID_IContextCallback
0x140011e88  lea     r8, [rbp+var_28]
0x140011e8c  lea     rdx, ?ContextCallback_Unregister@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z; CWuaClassFactoryBase::ContextCallback_Unregister(tagComCallData *)
0x140011e93  mov     rax, [rax+18h]
0x140011e97  call    _guard_dispatch_icall
0x140011e9c  test    eax, eax
0x140011e9e  jns     short loc_140011EB8
0x140011ea0  mov     edx, 1C7h; void *
0x140011ea5  mov     r9d, eax; char *
0x140011ea8  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140011eaf  mov     rcx, [rbp+8]; this
0x140011eb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011eb8  mov     rcx, [rbp+hKey]; hKey
0x140011ebc  test    rcx, rcx
0x140011ebf  jz      short loc_140011ECF
0x140011ec1  call    cs:__imp_RegCloseKey
0x140011ec7  mov     [rbp+hKey], 0
0x140011ecf  mov     rcx, rbx; this
0x140011ed2  call    ??1OSDeploymentInformationFactory@@UEAA@XZ; OSDeploymentInformationFactory::~OSDeploymentInformationFactory(void)
0x140011ed7  nop
0x140011ed8  mov     rcx, [rdi+20h]
0x140011edc  test    rcx, rcx
0x140011edf  jz      short loc_140011EEE
0x140011ee1  mov     rax, [rcx]
0x140011ee4  mov     rax, [rax+10h]
0x140011ee8  call    _guard_dispatch_icall
0x140011eed  nop
0x140011eee  mov     rcx, [rdi+18h]; hLibModule
0x140011ef2  test    rcx, rcx
0x140011ef5  jz      short loc_140011EFD
0x140011ef7  call    cs:__imp_FreeLibrary
0x140011efd  mov     dword ptr [rdi+14h], 0C0000001h
0x140011f04  mov     rcx, [rbp+var_10]
0x140011f08  xor     rcx, rsp; StackCookie
0x140011f0b  call    __security_check_cookie
0x140011f10  lea     r11, [rsp+80h+var_s0]
0x140011f18  mov     rbx, [r11+18h]
0x140011f1c  mov     rdi, [r11+20h]
0x140011f20  mov     rsp, r11
0x140011f23  pop     rbp
0x140011f24  retn
```
