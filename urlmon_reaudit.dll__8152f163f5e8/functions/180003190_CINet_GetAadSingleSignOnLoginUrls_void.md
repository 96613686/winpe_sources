# CINet::GetAadSingleSignOnLoginUrls(void)

- ea: `0x180003190`
- end: `0x18000334b`
- name: `?GetAadSingleSignOnLoginUrls@CINet@@IEAAPEBGXZ`
- size: `443`
- prototype: `const unsigned __int16 *__fastcall(CINet *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002b8c`
- `0x180006218`

## callees

- `0x180003190`
- `0x1800049a0`
- `0x180008b2c`
- `0x18001a6e0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003206`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003206`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800031d0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800031d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000330e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000330e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032de`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000331a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000331a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000332f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000332f`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800031af`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800031af`

## pseudocode

```c
const unsigned __int16 *__fastcall CINet::GetAadSingleSignOnLoginUrls(CINet *this)
{
  unsigned __int16 **v1; // rdx
  int AadLoginUrl; // ebx
  struct IEUserBroker *v3; // rdi
  __int64 (__fastcall *v4)(struct IEUserBroker *, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+58h] [rbp+28h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+30h] BYREF
  struct IEUserBroker *v11; // [rsp+68h] [rbp+38h] BYREF

  pv = this;
  if ( !g_pwszAadLoginUrls && CoInitialize(0) >= 0 )
  {
    pv = 0;
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870916) || (unsigned int)IsSpartanApp() )
    {
      AadLoginUrl = ProofOfPossessionTokenProvider::GetAadLoginUrl((ProofOfPossessionTokenProvider *)&pv, v1);
    }
    else
    {
      v11 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      AadLoginUrl = CoCreateUserBroker(&v11);
      if ( AadLoginUrl >= 0 )
      {
        v3 = v11;
        v10 = 0;
        v4 = *(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v11 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        AadLoginUrl = v4(
                        v3,
                        &CLSID_CShdocvwBrokerNoFrameAffinity,
                        &IID_IUnknown,
                        (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v10);
        if ( AadLoginUrl >= 0 )
        {
          v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v10;
          v9 = 0;
          v6 = **v10;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
          AadLoginUrl = v6(v5, &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42, &v9);
          if ( AadLoginUrl >= 0 )
            AadLoginUrl = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v9 + 1168LL))(v9, &pv);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    }
    if ( AadLoginUrl >= 0 )
    {
      EnterCriticalSection(&g_mxsSession);
      if ( !g_pwszAadLoginUrls )
      {
        g_pwszAadLoginUrls = pv;
        pv = 0;
      }
      LeaveCriticalSection(&g_mxsSession);
    }
    CoUninitialize();
    if ( pv )
      CoTaskMemFree(pv);
  }
  return (const unsigned __int16 *)g_pwszAadLoginUrls;
}

```

## disassembly

```asm
0x180003190  mov     [rsp-18h+pv], rcx
0x180003195  push    rbp
0x180003196  push    rbx
0x180003197  push    rdi
0x180003198  mov     rbp, rsp
0x18000319b  sub     rsp, 30h
0x18000319f  cmp     cs:?g_pwszAadLoginUrls@@3PEAGEA, 0; ushort * g_pwszAadLoginUrls
0x1800031a7  jnz     loc_18000333B
0x1800031ad  xor     ecx, ecx; pvReserved
0x1800031af  call    cs:__imp_CoInitialize
0x1800031b6  nop     dword ptr [rax+rax+00h]
0x1800031bb  test    eax, eax
0x1800031bd  js      loc_18000333B
0x1800031c3  mov     ecx, 20000004h
0x1800031c8  mov     [rbp+pv], 0
0x1800031d0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800031d7  nop     dword ptr [rax+rax+00h]
0x1800031dc  test    al, al
0x1800031de  jz      loc_1800032C8
0x1800031e4  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x1800031e9  test    eax, eax
0x1800031eb  jnz     loc_1800032C8
0x1800031f1  lea     rcx, [rbp+arg_18]
0x1800031f5  mov     [rbp+arg_18], 0
0x1800031fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003202  lea     rcx, [rbp+arg_18]
0x180003206  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18000320d  nop     dword ptr [rax+rax+00h]
0x180003212  mov     ebx, eax
0x180003214  test    eax, eax
0x180003216  js      loc_1800032BD
0x18000321c  mov     rdi, [rbp+arg_18]
0x180003220  lea     rcx, [rbp+arg_10]
0x180003224  mov     [rbp+arg_10], 0
0x18000322c  mov     rax, [rdi]
0x18000322f  mov     rbx, [rax+30h]
0x180003233  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003238  lea     r9, [rbp+arg_10]
0x18000323c  mov     rcx, rdi
0x18000323f  lea     r8, IID_IUnknown
0x180003246  mov     rax, rbx
0x180003249  lea     rdx, CLSID_CShdocvwBrokerNoFrameAffinity
0x180003250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003255  mov     ebx, eax
0x180003257  test    eax, eax
0x180003259  js      short loc_1800032B4
0x18000325b  mov     rdi, [rbp+arg_10]
0x18000325f  lea     rcx, [rbp+arg_8]
0x180003263  mov     [rbp+arg_8], 0
0x18000326b  mov     rax, [rdi]
0x18000326e  mov     rbx, [rax]
0x180003271  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003276  lea     r8, [rbp+arg_8]
0x18000327a  mov     rcx, rdi
0x18000327d  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180003284  mov     rax, rbx
0x180003287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328c  mov     ebx, eax
0x18000328e  test    eax, eax
0x180003290  js      short loc_1800032AB
0x180003292  mov     rcx, [rbp+arg_8]
0x180003296  lea     rdx, [rbp+pv]
0x18000329a  mov     rax, [rcx]
0x18000329d  mov     rax, [rax+490h]
0x1800032a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a9  mov     ebx, eax
0x1800032ab  lea     rcx, [rbp+arg_8]
0x1800032af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032b4  lea     rcx, [rbp+arg_10]
0x1800032b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032bd  lea     rcx, [rbp+arg_18]
0x1800032c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032c6  jmp     short loc_1800032D3
0x1800032c8  lea     rcx, [rbp+pv]; this
0x1800032cc  call    ?GetAadLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z; ProofOfPossessionTokenProvider::GetAadLoginUrl(ushort * *)
0x1800032d1  mov     ebx, eax
0x1800032d3  test    ebx, ebx
0x1800032d5  js      short loc_18000331A
0x1800032d7  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x1800032de  call    cs:__imp_EnterCriticalSection
0x1800032e5  nop     dword ptr [rax+rax+00h]
0x1800032ea  cmp     cs:?g_pwszAadLoginUrls@@3PEAGEA, 0; ushort * g_pwszAadLoginUrls
0x1800032f2  jnz     short loc_180003307
0x1800032f4  mov     rax, [rbp+pv]
0x1800032f8  mov     cs:?g_pwszAadLoginUrls@@3PEAGEA, rax; ushort * g_pwszAadLoginUrls
0x1800032ff  mov     [rbp+pv], 0
0x180003307  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18000330e  call    cs:__imp_LeaveCriticalSection
0x180003315  nop     dword ptr [rax+rax+00h]
0x18000331a  call    cs:__imp_CoUninitialize
0x180003321  nop     dword ptr [rax+rax+00h]
0x180003326  mov     rcx, [rbp+pv]; pv
0x18000332a  test    rcx, rcx
0x18000332d  jz      short loc_18000333B
0x18000332f  call    cs:__imp_CoTaskMemFree
0x180003336  nop     dword ptr [rax+rax+00h]
0x18000333b  mov     rax, cs:?g_pwszAadLoginUrls@@3PEAGEA; ushort * g_pwszAadLoginUrls
0x180003342  add     rsp, 30h
0x180003346  pop     rdi
0x180003347  pop     rbx
0x180003348  pop     rbp
0x180003349  retn
```
