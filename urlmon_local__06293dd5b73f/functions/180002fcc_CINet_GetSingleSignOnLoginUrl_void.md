# CINet::GetSingleSignOnLoginUrl(void)

- ea: `0x180002fcc`
- end: `0x180003187`
- name: `?GetSingleSignOnLoginUrl@CINet@@IEAAPEBGXZ`
- size: `443`
- prototype: `const unsigned __int16 *__fastcall(CINet *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002b8c`
- `0x180006218`

## callees

- `0x1800028a4`
- `0x180002fcc`
- `0x180008b2c`
- `0x18001a6e0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003042`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003042`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000300c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000300c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000314a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000314a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000311a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000311a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003156`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000316b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000316b`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002feb`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180002feb`

## pseudocode

```c
const unsigned __int16 *__fastcall CINet::GetSingleSignOnLoginUrl(CINet *this)
{
  unsigned __int16 **v1; // rdx
  int LoginUrl; // ebx
  struct IEUserBroker *v3; // rdi
  __int64 (__fastcall *v4)(struct IEUserBroker *, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+58h] [rbp+28h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+30h] BYREF
  struct IEUserBroker *v11; // [rsp+68h] [rbp+38h] BYREF

  pv = this;
  if ( !g_pwszLoginUrl && CoInitialize(0) >= 0 )
  {
    pv = 0;
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870916) || (unsigned int)IsSpartanApp() )
    {
      LoginUrl = ProofOfPossessionTokenProvider::GetLoginUrl((unsigned __int16 **)&pv, v1);
    }
    else
    {
      v11 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      LoginUrl = CoCreateUserBroker(&v11);
      if ( LoginUrl >= 0 )
      {
        v3 = v11;
        v10 = 0;
        v4 = *(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v11 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        LoginUrl = v4(
                     v3,
                     &CLSID_CShdocvwBrokerNoFrameAffinity,
                     &IID_IUnknown,
                     (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v10);
        if ( LoginUrl >= 0 )
        {
          v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v10;
          v9 = 0;
          v6 = **v10;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
          LoginUrl = v6(v5, &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42, &v9);
          if ( LoginUrl >= 0 )
            LoginUrl = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v9 + 1160LL))(v9, &pv);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    }
    if ( LoginUrl >= 0 )
    {
      EnterCriticalSection(&g_mxsSession);
      if ( !g_pwszLoginUrl )
      {
        g_pwszLoginUrl = pv;
        pv = 0;
      }
      LeaveCriticalSection(&g_mxsSession);
    }
    CoUninitialize();
    if ( pv )
      CoTaskMemFree(pv);
  }
  return (const unsigned __int16 *)g_pwszLoginUrl;
}

```

## disassembly

```asm
0x180002fcc  mov     [rsp-18h+pv], rcx
0x180002fd1  push    rbp
0x180002fd2  push    rbx
0x180002fd3  push    rdi
0x180002fd4  mov     rbp, rsp
0x180002fd7  sub     rsp, 30h
0x180002fdb  cmp     cs:?g_pwszLoginUrl@@3PEAGEA, 0; ushort * g_pwszLoginUrl
0x180002fe3  jnz     loc_180003177
0x180002fe9  xor     ecx, ecx; pvReserved
0x180002feb  call    cs:__imp_CoInitialize
0x180002ff2  nop     dword ptr [rax+rax+00h]
0x180002ff7  test    eax, eax
0x180002ff9  js      loc_180003177
0x180002fff  mov     ecx, 20000004h
0x180003004  mov     [rbp+pv], 0
0x18000300c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180003013  nop     dword ptr [rax+rax+00h]
0x180003018  test    al, al
0x18000301a  jz      loc_180003104
0x180003020  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x180003025  test    eax, eax
0x180003027  jnz     loc_180003104
0x18000302d  lea     rcx, [rbp+arg_18]
0x180003031  mov     [rbp+arg_18], 0
0x180003039  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000303e  lea     rcx, [rbp+arg_18]
0x180003042  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003049  nop     dword ptr [rax+rax+00h]
0x18000304e  mov     ebx, eax
0x180003050  test    eax, eax
0x180003052  js      loc_1800030F9
0x180003058  mov     rdi, [rbp+arg_18]
0x18000305c  lea     rcx, [rbp+arg_10]
0x180003060  mov     [rbp+arg_10], 0
0x180003068  mov     rax, [rdi]
0x18000306b  mov     rbx, [rax+30h]
0x18000306f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003074  lea     r9, [rbp+arg_10]
0x180003078  mov     rcx, rdi
0x18000307b  lea     r8, IID_IUnknown
0x180003082  mov     rax, rbx
0x180003085  lea     rdx, CLSID_CShdocvwBrokerNoFrameAffinity
0x18000308c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003091  mov     ebx, eax
0x180003093  test    eax, eax
0x180003095  js      short loc_1800030F0
0x180003097  mov     rdi, [rbp+arg_10]
0x18000309b  lea     rcx, [rbp+arg_8]
0x18000309f  mov     [rbp+arg_8], 0
0x1800030a7  mov     rax, [rdi]
0x1800030aa  mov     rbx, [rax]
0x1800030ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800030b2  lea     r8, [rbp+arg_8]
0x1800030b6  mov     rcx, rdi
0x1800030b9  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1800030c0  mov     rax, rbx
0x1800030c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c8  mov     ebx, eax
0x1800030ca  test    eax, eax
0x1800030cc  js      short loc_1800030E7
0x1800030ce  mov     rcx, [rbp+arg_8]
0x1800030d2  lea     rdx, [rbp+pv]
0x1800030d6  mov     rax, [rcx]
0x1800030d9  mov     rax, [rax+488h]
0x1800030e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e5  mov     ebx, eax
0x1800030e7  lea     rcx, [rbp+arg_8]
0x1800030eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800030f0  lea     rcx, [rbp+arg_10]
0x1800030f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800030f9  lea     rcx, [rbp+arg_18]
0x1800030fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003102  jmp     short loc_18000310F
0x180003104  lea     rcx, [rbp+pv]; this
0x180003108  call    ?GetLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z; ProofOfPossessionTokenProvider::GetLoginUrl(ushort * *)
0x18000310d  mov     ebx, eax
0x18000310f  test    ebx, ebx
0x180003111  js      short loc_180003156
0x180003113  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18000311a  call    cs:__imp_EnterCriticalSection
0x180003121  nop     dword ptr [rax+rax+00h]
0x180003126  cmp     cs:?g_pwszLoginUrl@@3PEAGEA, 0; ushort * g_pwszLoginUrl
0x18000312e  jnz     short loc_180003143
0x180003130  mov     rax, [rbp+pv]
0x180003134  mov     cs:?g_pwszLoginUrl@@3PEAGEA, rax; ushort * g_pwszLoginUrl
0x18000313b  mov     [rbp+pv], 0
0x180003143  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18000314a  call    cs:__imp_LeaveCriticalSection
0x180003151  nop     dword ptr [rax+rax+00h]
0x180003156  call    cs:__imp_CoUninitialize
0x18000315d  nop     dword ptr [rax+rax+00h]
0x180003162  mov     rcx, [rbp+pv]; pv
0x180003166  test    rcx, rcx
0x180003169  jz      short loc_180003177
0x18000316b  call    cs:__imp_CoTaskMemFree
0x180003172  nop     dword ptr [rax+rax+00h]
0x180003177  mov     rax, cs:?g_pwszLoginUrl@@3PEAGEA; ushort * g_pwszLoginUrl
0x18000317e  add     rsp, 30h
0x180003182  pop     rdi
0x180003183  pop     rbx
0x180003184  pop     rbp
0x180003185  retn
```
