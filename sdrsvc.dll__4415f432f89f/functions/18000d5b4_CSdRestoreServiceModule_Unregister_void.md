# CSdRestoreServiceModule::Unregister(void)

- ea: `0x18000d5b4`
- end: `0x18000d78b`
- name: `?Unregister@CSdRestoreServiceModule@@QEAAJXZ`
- size: `471`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e800`
- `0x18000e890`

## callees

- `0x180009930`
- `0x18000d5b4`
- `0x18000d7ec`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d73b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d73b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d62d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d62d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d614`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d614`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d6f9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d6f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d755`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d763`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d755`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d763`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d717`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d717`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18000d728`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18000d728`

## string_xrefs

- `0x18000d5ce`: `CSdRestoreServiceModule::Unregister`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::Unregister(CSdRestoreServiceModule *this)
{
  SC_HANDLE v1; // rdi
  __int64 v2; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbx
  SC_HANDLE v10; // rax
  unsigned int v11; // ebx
  _DWORD v13[16]; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v13, "CSdRestoreServiceModule::Unregister", 950, 1);
  hKey = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost", 0, 2u, &hKey) )
    RegDeleteValueW(hKey, L"SDRSVC");
  ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, 0, 0);
  v2 = qword_18002E1D8;
  if ( qword_18002E1D8 )
  {
    while ( *(_QWORD *)v2 )
    {
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v3, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v2 + 8))(0) < 0 )
      {
        goto LABEL_18;
      }
      v2 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v4 = off_18002D3B0[0];
    v5 = off_18002D3B8;
    while ( v4 < v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v6 + 8))(0) < 0 )
        {
          break;
        }
        v5 = off_18002D3B8;
      }
      ++v4;
    }
  }
LABEL_18:
  v8 = OpenSCManagerW(0, 0, 2u);
  v9 = v8;
  if ( v8 )
  {
    v10 = OpenServiceW(v8, L"SDRSVC", 0x10000u);
    v1 = v10;
    if ( v10 )
      DeleteService(v10);
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v9 )
    CloseServiceHandle(v9);
  v11 = v13[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v13);
  return v11;
}

```

## disassembly

```asm
0x18000d5b4  mov     rax, rsp
0x18000d5b7  mov     [rax+10h], rbx
0x18000d5bb  mov     [rax+18h], rsi
0x18000d5bf  mov     [rax+8], rcx
0x18000d5c3  push    rdi
0x18000d5c4  sub     rsp, 70h
0x18000d5c8  mov     r9d, 1; unsigned __int16
0x18000d5ce  lea     rdx, aCsdrestoreserv_9; "CSdRestoreServiceModule::Unregister"
0x18000d5d5  mov     r8d, 3B6h; unsigned __int16
0x18000d5db  lea     rcx, [rax-48h]; this
0x18000d5df  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d5e4  lea     rax, [rsp+78h+hKey]
0x18000d5ec  mov     [rsp+78h+hKey], 0
0x18000d5f8  xor     edi, edi
0x18000d5fa  mov     [rsp+78h+phkResult], rax; phkResult
0x18000d5ff  xor     r8d, r8d; ulOptions
0x18000d602  lea     rdx, ?s_wszSvchostKey@CSdRestoreServiceModule@@0QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000d609  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d610  lea     r9d, [rdi+2]; samDesired
0x18000d614  call    cs:__imp_RegOpenKeyExW
0x18000d61a  test    eax, eax
0x18000d61c  jnz     short loc_18000D633
0x18000d61e  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d626  lea     rdx, ?s_wszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000d62d  call    cs:__imp_RegDeleteValueW
0x18000d633  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000d636  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000d63d  xor     r8d, r8d; int
0x18000d640  lea     edx, [r9+65h]; unsigned int
0x18000d644  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000d649  mov     rbx, cs:qword_18002E1D8
0x18000d650  test    rbx, rbx
0x18000d653  jz      short loc_18000D68A
0x18000d655  jmp     short loc_18000D685
0x18000d657  mov     rax, [rbx+38h]
0x18000d65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d660  mov     rcx, [rbx]; rguid
0x18000d663  xor     r8d, r8d; int
0x18000d666  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000d669  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000d66e  test    eax, eax
0x18000d670  js      short loc_18000D6F1
0x18000d672  mov     rax, [rbx+8]
0x18000d676  xor     ecx, ecx
0x18000d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d67d  test    eax, eax
0x18000d67f  js      short loc_18000D6F1
0x18000d681  add     rbx, 48h ; 'H'
0x18000d685  cmp     [rbx], rdi
0x18000d688  jnz     short loc_18000D657
0x18000d68a  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000d691  test    rax, rax
0x18000d694  jz      short loc_18000D69F
0x18000d696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d69b  test    eax, eax
0x18000d69d  js      short loc_18000D6F1
0x18000d69f  mov     rbx, cs:off_18002D3B0
0x18000d6a6  mov     rax, cs:off_18002D3B8
0x18000d6ad  jmp     short loc_18000D6EC
0x18000d6af  mov     rsi, [rbx]
0x18000d6b2  test    rsi, rsi
0x18000d6b5  jz      short loc_18000D6E8
0x18000d6b7  mov     rax, [rsi+38h]
0x18000d6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c0  mov     rcx, [rsi]; rguid
0x18000d6c3  xor     r8d, r8d; int
0x18000d6c6  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000d6c9  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000d6ce  test    eax, eax
0x18000d6d0  js      short loc_18000D6F1
0x18000d6d2  mov     rax, [rsi+8]
0x18000d6d6  xor     ecx, ecx
0x18000d6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6dd  test    eax, eax
0x18000d6df  js      short loc_18000D6F1
0x18000d6e1  mov     rax, cs:off_18002D3B8
0x18000d6e8  add     rbx, 8
0x18000d6ec  cmp     rbx, rax
0x18000d6ef  jb      short loc_18000D6AF
0x18000d6f1  xor     edx, edx; lpDatabaseName
0x18000d6f3  xor     ecx, ecx; lpMachineName
0x18000d6f5  lea     r8d, [rdx+2]; dwDesiredAccess
0x18000d6f9  call    cs:__imp_OpenSCManagerW
0x18000d6ff  mov     rbx, rax
0x18000d702  test    rax, rax
0x18000d705  jz      short loc_18000D72E
0x18000d707  mov     r8d, 10000h; dwDesiredAccess
0x18000d70d  lea     rdx, ?s_wszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000d714  mov     rcx, rax; hSCManager
0x18000d717  call    cs:__imp_OpenServiceW
0x18000d71d  mov     rdi, rax
0x18000d720  test    rax, rax
0x18000d723  jz      short loc_18000D72E
0x18000d725  mov     rcx, rax; hService
0x18000d728  call    cs:__imp_DeleteService
0x18000d72e  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d736  test    rcx, rcx
0x18000d739  jz      short loc_18000D74D
0x18000d73b  call    cs:__imp_RegCloseKey
0x18000d741  mov     [rsp+78h+hKey], 0
0x18000d74d  test    rdi, rdi
0x18000d750  jz      short loc_18000D75B
0x18000d752  mov     rcx, rdi; hSCObject
0x18000d755  call    cs:__imp_CloseServiceHandle
0x18000d75b  test    rbx, rbx
0x18000d75e  jz      short loc_18000D769
0x18000d760  mov     rcx, rbx; hSCObject
0x18000d763  call    cs:__imp_CloseServiceHandle
0x18000d769  mov     ebx, [rsp+78h+var_48]
0x18000d76d  lea     rcx, [rsp+78h+var_48]; this
0x18000d772  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d777  lea     r11, [rsp+78h+var_8]
0x18000d77c  mov     eax, ebx
0x18000d77e  mov     rbx, [r11+18h]
0x18000d782  mov     rsi, [r11+20h]
0x18000d786  mov     rsp, r11
0x18000d789  pop     rdi
0x18000d78a  retn
```
