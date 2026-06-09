# Wsp::Health2::ResClient::Initialize(void)

- ea: `0x18007d7e8`
- end: `0x18007d9ca`
- name: `?Initialize@ResClient@Health2@Wsp@@QEAAJXZ`
- size: `482`
- prototype: `__int64 __fastcall(Wsp::Health2::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007d760`

## callees

- `0x180017fcc`
- `0x18001aef0`
- `0x18007d7e8`
- `0x18007db24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007d823`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007d823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d84f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d895`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d8b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d8db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d902`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d929`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d950`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d977`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d84f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d895`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d8b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d8db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d902`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d929`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d950`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d863`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007d99d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007d99d`

## string_xrefs

- `0x18007d81c`: `healthapi.dll`
- `0x18007d845`: `HealthOpenConnection`
- `0x18007d8f4`: `HealthTsdbReadMulti`
- `0x18007d91b`: `HealthTsdbReadCancel`
- `0x18007d969`: `HealthSendPluginCommand`
- `0x18007d8aa`: `HealthTsdbRead`
- `0x18007d8cd`: `HealthTsdbReadSync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Wsp::Health2::ResClient::Initialize(Wsp::Health2::ResClient *this)
{
  unsigned int v2; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  bool v13; // dl
  _BYTE v15[24]; // [rsp+20h] [rbp-18h] BYREF

  cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v15, (Wsp::Health2::ResClient *)((char *)this + 104));
  if ( *((_QWORD *)this + 16) )
  {
    v2 = -2147023649;
  }
  else
  {
    Library = LoadLibraryExW(L"healthapi.dll", 0, 0x800u);
    *((_QWORD *)this + 16) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "HealthOpenConnection");
      *(_QWORD *)this = ProcAddress;
      if ( !ProcAddress )
        goto LABEL_6;
      v6 = GetProcAddress(*((HMODULE *)this + 16), "HealthCloseConnection");
      *((_QWORD *)this + 1) = v6;
      if ( !v6 )
        goto LABEL_6;
      v7 = GetProcAddress(*((HMODULE *)this + 16), "HealthTsdbRead");
      *((_QWORD *)this + 2) = v7;
      if ( !v7 )
        goto LABEL_6;
      v8 = GetProcAddress(*((HMODULE *)this + 16), "HealthTsdbReadSync");
      *((_QWORD *)this + 3) = v8;
      if ( !v8 )
        goto LABEL_6;
      v9 = GetProcAddress(*((HMODULE *)this + 16), "HealthTsdbReadMulti");
      *((_QWORD *)this + 4) = v9;
      if ( !v9 )
        goto LABEL_6;
      v10 = GetProcAddress(*((HMODULE *)this + 16), "HealthTsdbReadCancel");
      *((_QWORD *)this + 5) = v10;
      if ( v10
        && (v11 = GetProcAddress(*((HMODULE *)this + 16), "HealthGetEntityFaults"), (*((_QWORD *)this + 6) = v11) != 0)
        && (v12 = GetProcAddress(*((HMODULE *)this + 16), "HealthSendPluginCommand"), (*((_QWORD *)this + 7) = v12) != 0) )
      {
        *((_QWORD *)this + 15) = CreateThreadpoolTimer(smapi::HealthActionEventSchema::set_sourceUniqueId, this, 0);
        Wsp::Health2::ResClient::SetCanConnect(this, v13);
        v2 = 0;
      }
      else
      {
LABEL_6:
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v2 = -2147023739;
    }
  }
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v15);
  return v2;
}

```

## disassembly

```asm
0x18007d7e8  push    rbx
0x18007d7ea  sub     rsp, 30h
0x18007d7ee  mov     rbx, rcx
0x18007d7f1  lea     rdx, [rcx+68h]; struct cxl::NonReentrantRWLock *
0x18007d7f5  lea     rcx, [rsp+38h+var_18]; this
0x18007d7fa  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18007d7ff  nop
0x18007d800  cmp     qword ptr [rbx+80h], 0
0x18007d808  jz      short loc_18007D814
0x18007d80a  mov     ebx, 800704DFh
0x18007d80f  jmp     loc_18007D9B7
0x18007d814  xor     edx, edx; hFile
0x18007d816  mov     r8d, 800h; dwFlags
0x18007d81c  lea     rcx, aHealthapiDll; "healthapi.dll"
0x18007d823  call    cs:__imp_LoadLibraryExW
0x18007d82a  nop     dword ptr [rax+rax+00h]
0x18007d82f  mov     [rbx+80h], rax
0x18007d836  test    rax, rax
0x18007d839  jnz     short loc_18007D845
0x18007d83b  mov     ebx, 80070485h
0x18007d840  jmp     loc_18007D9B7
0x18007d845  lea     rdx, aHealthopenconn; "HealthOpenConnection"
0x18007d84c  mov     rcx, rax; hModule
0x18007d84f  call    cs:__imp_GetProcAddress
0x18007d856  nop     dword ptr [rax+rax+00h]
0x18007d85b  mov     [rbx], rax
0x18007d85e  test    rax, rax
0x18007d861  jnz     short loc_18007D887
0x18007d863  call    cs:__imp_GetLastError
0x18007d86a  nop     dword ptr [rax+rax+00h]
0x18007d86f  mov     ebx, eax
0x18007d871  test    eax, eax
0x18007d873  jle     loc_18007D9B7
0x18007d879  movzx   ebx, ax
0x18007d87c  or      ebx, 80070000h
0x18007d882  jmp     loc_18007D9B7
0x18007d887  lea     rdx, aHealthclosecon; "HealthCloseConnection"
0x18007d88e  mov     rcx, [rbx+80h]; hModule
0x18007d895  call    cs:__imp_GetProcAddress
0x18007d89c  nop     dword ptr [rax+rax+00h]
0x18007d8a1  mov     [rbx+8], rax
0x18007d8a5  test    rax, rax
0x18007d8a8  jz      short loc_18007D863
0x18007d8aa  lea     rdx, aHealthtsdbread_1; "HealthTsdbRead"
0x18007d8b1  mov     rcx, [rbx+80h]; hModule
0x18007d8b8  call    cs:__imp_GetProcAddress
0x18007d8bf  nop     dword ptr [rax+rax+00h]
0x18007d8c4  mov     [rbx+10h], rax
0x18007d8c8  test    rax, rax
0x18007d8cb  jz      short loc_18007D863
0x18007d8cd  lea     rdx, aHealthtsdbread_0; "HealthTsdbReadSync"
0x18007d8d4  mov     rcx, [rbx+80h]; hModule
0x18007d8db  call    cs:__imp_GetProcAddress
0x18007d8e2  nop     dword ptr [rax+rax+00h]
0x18007d8e7  mov     [rbx+18h], rax
0x18007d8eb  test    rax, rax
0x18007d8ee  jz      loc_18007D863
0x18007d8f4  lea     rdx, aHealthtsdbread_2; "HealthTsdbReadMulti"
0x18007d8fb  mov     rcx, [rbx+80h]; hModule
0x18007d902  call    cs:__imp_GetProcAddress
0x18007d909  nop     dword ptr [rax+rax+00h]
0x18007d90e  mov     [rbx+20h], rax
0x18007d912  test    rax, rax
0x18007d915  jz      loc_18007D863
0x18007d91b  lea     rdx, aHealthtsdbread; "HealthTsdbReadCancel"
0x18007d922  mov     rcx, [rbx+80h]; hModule
0x18007d929  call    cs:__imp_GetProcAddress
0x18007d930  nop     dword ptr [rax+rax+00h]
0x18007d935  mov     [rbx+28h], rax
0x18007d939  test    rax, rax
0x18007d93c  jz      loc_18007D863
0x18007d942  lea     rdx, aHealthgetentit; "HealthGetEntityFaults"
0x18007d949  mov     rcx, [rbx+80h]; hModule
0x18007d950  call    cs:__imp_GetProcAddress
0x18007d957  nop     dword ptr [rax+rax+00h]
0x18007d95c  mov     [rbx+30h], rax
0x18007d960  test    rax, rax
0x18007d963  jz      loc_18007D863
0x18007d969  lea     rdx, aHealthsendplug; "HealthSendPluginCommand"
0x18007d970  mov     rcx, [rbx+80h]; hModule
0x18007d977  call    cs:__imp_GetProcAddress
0x18007d97e  nop     dword ptr [rax+rax+00h]
0x18007d983  mov     [rbx+38h], rax
0x18007d987  test    rax, rax
0x18007d98a  jz      loc_18007D863
0x18007d990  xor     r8d, r8d; pcbe
0x18007d993  mov     rdx, rbx; pv
0x18007d996  lea     rcx, ?set_sourceUniqueId@HealthActionEventSchema@smapi@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; pfnti
0x18007d99d  call    cs:__imp_CreateThreadpoolTimer
0x18007d9a4  nop     dword ptr [rax+rax+00h]
0x18007d9a9  mov     [rbx+78h], rax
0x18007d9ad  mov     rcx, rbx; this
0x18007d9b0  call    ?SetCanConnect@ResClient@Health2@Wsp@@QEAAX_N@Z; Wsp::Health2::ResClient::SetCanConnect(bool)
0x18007d9b5  xor     ebx, ebx
0x18007d9b7  lea     rcx, [rsp+38h+var_18]
0x18007d9bc  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18007d9c1  mov     eax, ebx
0x18007d9c3  add     rsp, 30h
0x18007d9c7  pop     rbx
0x18007d9c8  retn
```
