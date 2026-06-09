# CINetEdge::GetSingleSignOnLoginUrl(void)

- ea: `0x180003be0`
- end: `0x180003d85`
- name: `?GetSingleSignOnLoginUrl@CINetEdge@@IEAAPEBGXZ`
- size: `421`
- prototype: `const unsigned __int16 *__fastcall(CINetEdge *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000367c`
- `0x18009c70c`

## callees

- `0x1800028a4`
- `0x180003be0`
- `0x18001a6e0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003c48`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180003c48`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003c1b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180003c1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003cd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ca2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c5c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c71`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180003bfe`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180003bfe`

## pseudocode

```c
const unsigned __int16 *__fastcall CINetEdge::GetSingleSignOnLoginUrl(CINetEdge *this)
{
  unsigned __int16 **v1; // rdx
  int LoginUrl; // ebx
  int v4; // ebx
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF
  __int64 v6; // [rsp+58h] [rbp+20h] BYREF
  struct IEUserBroker *v7; // [rsp+60h] [rbp+28h] BYREF
  __int64 v8; // [rsp+68h] [rbp+30h] BYREF

  pv = this;
  if ( g_pwszLoginUrl || CoInitialize(0) < 0 )
    return (const unsigned __int16 *)g_pwszLoginUrl;
  pv = 0;
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870916) || (unsigned int)IsSpartanApp() )
  {
    LoginUrl = ProofOfPossessionTokenProvider::GetLoginUrl((unsigned __int16 **)&pv, v1);
  }
  else
  {
    v8 = 0;
    v7 = 0;
    if ( (int)CoCreateUserBroker(&v7) < 0 )
      goto LABEL_6;
    v6 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v7 + 48LL))(
           v7,
           &CLSID_CShdocvwBroker,
           &IID_IUnknown,
           &v6);
    if ( v4 >= 0 )
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
             &v8);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v4 < 0 )
      goto LABEL_6;
    LoginUrl = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 1160LL))(v8, &pv);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
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
LABEL_6:
  CoUninitialize();
  if ( pv )
    CoTaskMemFree(pv);
  return (const unsigned __int16 *)g_pwszLoginUrl;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp-10h+pv], rcx
0x180003be5  push    rbp
0x180003be6  push    rbx
0x180003be7  mov     rbp, rsp
0x180003bea  sub     rsp, 38h
0x180003bee  cmp     cs:?g_pwszLoginUrl@@3PEAGEA, 0; ushort * g_pwszLoginUrl
0x180003bf6  jnz     loc_180003C7D
0x180003bfc  xor     ecx, ecx; pvReserved
0x180003bfe  call    cs:__imp_CoInitialize
0x180003c05  nop     dword ptr [rax+rax+00h]
0x180003c0a  test    eax, eax
0x180003c0c  js      short loc_180003C7D
0x180003c0e  mov     ecx, 20000004h
0x180003c13  mov     [rbp+pv], 0
0x180003c1b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180003c22  nop     dword ptr [rax+rax+00h]
0x180003c27  test    al, al
0x180003c29  jz      short loc_180003C8C
0x180003c2b  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x180003c30  test    eax, eax
0x180003c32  jnz     short loc_180003C8C
0x180003c34  lea     rcx, [rbp+arg_10]
0x180003c38  mov     [rbp+arg_18], 0
0x180003c40  mov     [rbp+arg_10], 0
0x180003c48  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180003c4f  nop     dword ptr [rax+rax+00h]
0x180003c54  test    eax, eax
0x180003c56  jns     loc_180003CE3
0x180003c5c  call    cs:__imp_CoUninitialize
0x180003c63  nop     dword ptr [rax+rax+00h]
0x180003c68  mov     rcx, [rbp+pv]; pv
0x180003c6c  test    rcx, rcx
0x180003c6f  jz      short loc_180003C7D
0x180003c71  call    cs:__imp_CoTaskMemFree
0x180003c78  nop     dword ptr [rax+rax+00h]
0x180003c7d  mov     rax, cs:?g_pwszLoginUrl@@3PEAGEA; ushort * g_pwszLoginUrl
0x180003c84  add     rsp, 38h
0x180003c88  pop     rbx
0x180003c89  pop     rbp
0x180003c8a  retn
0x180003c8c  lea     rcx, [rbp+pv]; this
0x180003c90  call    ?GetLoginUrl@ProofOfPossessionTokenProvider@@YAJPEAPEAG@Z; ProofOfPossessionTokenProvider::GetLoginUrl(ushort * *)
0x180003c95  mov     ebx, eax
0x180003c97  test    ebx, ebx
0x180003c99  js      short loc_180003C5C
0x180003c9b  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x180003ca2  call    cs:__imp_EnterCriticalSection
0x180003ca9  nop     dword ptr [rax+rax+00h]
0x180003cae  cmp     cs:?g_pwszLoginUrl@@3PEAGEA, 0; ushort * g_pwszLoginUrl
0x180003cb6  jnz     short loc_180003CCB
0x180003cb8  mov     rax, [rbp+pv]
0x180003cbc  mov     cs:?g_pwszLoginUrl@@3PEAGEA, rax; ushort * g_pwszLoginUrl
0x180003cc3  mov     [rbp+pv], 0
0x180003ccb  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x180003cd2  call    cs:__imp_LeaveCriticalSection
0x180003cd9  nop     dword ptr [rax+rax+00h]
0x180003cde  jmp     loc_180003C5C
0x180003ce3  mov     rcx, [rbp+arg_10]
0x180003ce7  lea     r9, [rbp+arg_8]
0x180003ceb  mov     [rbp+arg_8], 0
0x180003cf3  lea     r8, IID_IUnknown
0x180003cfa  lea     rdx, CLSID_CShdocvwBroker
0x180003d01  mov     rax, [rcx]
0x180003d04  mov     rax, [rax+30h]
0x180003d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0d  mov     ebx, eax
0x180003d0f  test    eax, eax
0x180003d11  js      short loc_180003D3F
0x180003d13  mov     rcx, [rbp+arg_8]
0x180003d17  lea     r8, [rbp+arg_18]
0x180003d1b  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180003d22  mov     rax, [rcx]
0x180003d25  mov     rax, [rax]
0x180003d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2d  mov     rcx, [rbp+arg_8]
0x180003d31  mov     ebx, eax
0x180003d33  mov     rax, [rcx]
0x180003d36  mov     rax, [rax+10h]
0x180003d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d3f  mov     rcx, [rbp+arg_10]
0x180003d43  mov     rax, [rcx]
0x180003d46  mov     rax, [rax+10h]
0x180003d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4f  test    ebx, ebx
0x180003d51  js      loc_180003C5C
0x180003d57  mov     rcx, [rbp+arg_18]
0x180003d5b  lea     rdx, [rbp+pv]
0x180003d5f  mov     rax, [rcx]
0x180003d62  mov     rax, [rax+488h]
0x180003d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6e  mov     rcx, [rbp+arg_18]
0x180003d72  mov     ebx, eax
0x180003d74  mov     rdx, [rcx]
0x180003d77  mov     rax, [rdx+10h]
0x180003d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d80  jmp     loc_180003C97
```
