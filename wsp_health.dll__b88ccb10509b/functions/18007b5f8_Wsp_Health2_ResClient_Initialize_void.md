# Wsp::Health2::ResClient::Initialize(void)

- ea: `0x18007b5f8`
- end: `0x18007b793`
- name: `?Initialize@ResClient@Health2@Wsp@@QEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(Wsp::Health2::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b578`

## callees

- `0x180017688`
- `0x18001a470`
- `0x18007b5f8`
- `0x18007b8f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007b633`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007b633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b70b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b72c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b74d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b6ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b70b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b72c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b667`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007b76d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007b76d`

## string_xrefs

- `0x18007b62c`: `healthapi.dll`
- `0x18007b64f`: `HealthOpenConnection`
- `0x18007b6dc`: `HealthTsdbReadMulti`
- `0x18007b6fd`: `HealthTsdbReadCancel`
- `0x18007b73f`: `HealthSendPluginCommand`
- `0x18007b6a2`: `HealthTsdbRead`
- `0x18007b6bf`: `HealthTsdbReadSync`

## pseudocode

```c
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
0x18007b5f8  push    rbx
0x18007b5fa  sub     rsp, 30h
0x18007b5fe  mov     rbx, rcx
0x18007b601  lea     rdx, [rcx+68h]; struct cxl::NonReentrantRWLock *
0x18007b605  lea     rcx, [rsp+38h+var_18]; this
0x18007b60a  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18007b60f  nop
0x18007b610  cmp     qword ptr [rbx+80h], 0
0x18007b618  jz      short loc_18007B624
0x18007b61a  mov     ebx, 800704DFh
0x18007b61f  jmp     loc_18007B781
0x18007b624  xor     edx, edx; hFile
0x18007b626  mov     r8d, 800h; dwFlags
0x18007b62c  lea     rcx, aHealthapiDll; "healthapi.dll"
0x18007b633  call    cs:__imp_LoadLibraryExW
0x18007b639  mov     [rbx+80h], rax
0x18007b640  test    rax, rax
0x18007b643  jnz     short loc_18007B64F
0x18007b645  mov     ebx, 80070485h
0x18007b64a  jmp     loc_18007B781
0x18007b64f  lea     rdx, aHealthopenconn; "HealthOpenConnection"
0x18007b656  mov     rcx, rax; hModule
0x18007b659  call    cs:__imp_GetProcAddress
0x18007b65f  mov     [rbx], rax
0x18007b662  test    rax, rax
0x18007b665  jnz     short loc_18007B685
0x18007b667  call    cs:__imp_GetLastError
0x18007b66d  mov     ebx, eax
0x18007b66f  test    eax, eax
0x18007b671  jle     loc_18007B781
0x18007b677  movzx   ebx, ax
0x18007b67a  or      ebx, 80070000h
0x18007b680  jmp     loc_18007B781
0x18007b685  lea     rdx, aHealthclosecon; "HealthCloseConnection"
0x18007b68c  mov     rcx, [rbx+80h]; hModule
0x18007b693  call    cs:__imp_GetProcAddress
0x18007b699  mov     [rbx+8], rax
0x18007b69d  test    rax, rax
0x18007b6a0  jz      short loc_18007B667
0x18007b6a2  lea     rdx, aHealthtsdbread_1; "HealthTsdbRead"
0x18007b6a9  mov     rcx, [rbx+80h]; hModule
0x18007b6b0  call    cs:__imp_GetProcAddress
0x18007b6b6  mov     [rbx+10h], rax
0x18007b6ba  test    rax, rax
0x18007b6bd  jz      short loc_18007B667
0x18007b6bf  lea     rdx, aHealthtsdbread_0; "HealthTsdbReadSync"
0x18007b6c6  mov     rcx, [rbx+80h]; hModule
0x18007b6cd  call    cs:__imp_GetProcAddress
0x18007b6d3  mov     [rbx+18h], rax
0x18007b6d7  test    rax, rax
0x18007b6da  jz      short loc_18007B667
0x18007b6dc  lea     rdx, aHealthtsdbread_2; "HealthTsdbReadMulti"
0x18007b6e3  mov     rcx, [rbx+80h]; hModule
0x18007b6ea  call    cs:__imp_GetProcAddress
0x18007b6f0  mov     [rbx+20h], rax
0x18007b6f4  test    rax, rax
0x18007b6f7  jz      loc_18007B667
0x18007b6fd  lea     rdx, aHealthtsdbread; "HealthTsdbReadCancel"
0x18007b704  mov     rcx, [rbx+80h]; hModule
0x18007b70b  call    cs:__imp_GetProcAddress
0x18007b711  mov     [rbx+28h], rax
0x18007b715  test    rax, rax
0x18007b718  jz      loc_18007B667
0x18007b71e  lea     rdx, aHealthgetentit; "HealthGetEntityFaults"
0x18007b725  mov     rcx, [rbx+80h]; hModule
0x18007b72c  call    cs:__imp_GetProcAddress
0x18007b732  mov     [rbx+30h], rax
0x18007b736  test    rax, rax
0x18007b739  jz      loc_18007B667
0x18007b73f  lea     rdx, aHealthsendplug; "HealthSendPluginCommand"
0x18007b746  mov     rcx, [rbx+80h]; hModule
0x18007b74d  call    cs:__imp_GetProcAddress
0x18007b753  mov     [rbx+38h], rax
0x18007b757  test    rax, rax
0x18007b75a  jz      loc_18007B667
0x18007b760  xor     r8d, r8d; pcbe
0x18007b763  mov     rdx, rbx; pv
0x18007b766  lea     rcx, ?set_sourceUniqueId@HealthActionEventSchema@smapi@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; pfnti
0x18007b76d  call    cs:__imp_CreateThreadpoolTimer
0x18007b773  mov     [rbx+78h], rax
0x18007b777  mov     rcx, rbx; this
0x18007b77a  call    ?SetCanConnect@ResClient@Health2@Wsp@@QEAAX_N@Z; Wsp::Health2::ResClient::SetCanConnect(bool)
0x18007b77f  xor     ebx, ebx
0x18007b781  lea     rcx, [rsp+38h+var_18]
0x18007b786  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18007b78b  mov     eax, ebx
0x18007b78d  add     rsp, 30h
0x18007b791  pop     rbx
0x18007b792  retn
```
