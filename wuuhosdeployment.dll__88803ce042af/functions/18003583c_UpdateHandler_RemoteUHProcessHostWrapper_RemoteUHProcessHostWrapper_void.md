# UpdateHandler::RemoteUHProcessHostWrapper::~RemoteUHProcessHostWrapper(void)

- ea: `0x18003583c`
- end: `0x180035a8b`
- name: `??1RemoteUHProcessHostWrapper@UpdateHandler@@UEAA@XZ`
- size: `591`
- prototype: `void __fastcall(UpdateHandler::RemoteUHProcessHostWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035800`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000c0b4`
- `0x18000fcfc`
- `0x180010f54`
- `0x18003100c`
- `0x180031804`
- `0x18003583c`
- `0x180036620`
- `0x180036ab4`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035a4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035a4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035886`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035922`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035886`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a5f`

## string_xrefs

- `0x180035943`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18003599b`: `UpdateHandler::RemoteUHProcessHostWrapper::Stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UpdateHandler::RemoteUHProcessHostWrapper::~RemoteUHProcessHostWrapper(
        UpdateHandler::RemoteUHProcessHostWrapper *this)
{
  void *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  int v5; // eax
  int v6; // esi
  __int64 v7; // rdx
  bool v8; // cl
  __int64 v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // ecx
  int v12; // eax
  void *v13; // rcx
  __int64 v14; // rcx
  void *v15; // rcx
  int v16; // [rsp+20h] [rbp-48h]
  UpdateHandler::RemoteUHProcessHostWrapper *v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = &UpdateHandler::RemoteUHProcessHostWrapper::`vftable'{for `CWuaSingletonClassFactory'};
  *((_QWORD *)this + 6) = &UpdateHandler::RemoteUHProcessHostWrapper::`vftable'{for `IRemoteUHProcessHostRegistrar'};
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 && v2 != (void *)-1LL && WaitForSingleObject(v2, 0) == 258 )
  {
    v18 = 1;
    v17 = this;
    v3 = *((_QWORD *)this + 17);
    if ( v3 )
    {
      if ( v3 != -1 )
      {
        v4 = *((_QWORD *)this + 16);
        if ( v4 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
          v6 = v5;
          if ( v5 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B2,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
              (const char *)(unsigned int)v5,
              v16);
            v7 = 444;
LABEL_9:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v7,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
              (const char *)(unsigned int)v6,
              v16);
            wil::details::lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___::_lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___(&v17);
            goto LABEL_17;
          }
        }
      }
    }
    if ( WaitForSingleObject(*((HANDLE *)this + 8), 1000 * *((_DWORD *)this + 80)) == 258 )
    {
      if ( (unsigned int)AreTestKeysAllowed(v8)
        && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                           v9,
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                           L"RemoteUHTimeoutNoTelAssert",
                           0) )
      {
        v6 = -2145116121;
        v7 = 452;
      }
      else
      {
        v16 = 0;
        WUTrace("UpdateHandler::RemoteUHProcessHostWrapper::Stop", 456, 32, 3);
        WUTelemetryAssertTriggered(v11, v10);
        v6 = -2145116121;
        v7 = 457;
      }
      goto LABEL_9;
    }
    LOBYTE(v18) = 0;
    wil::details::lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___::_lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___(&v17);
  }
  v6 = 0;
LABEL_17:
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v12 = UpdateHandler::RemoteUHProcessHostWrapper::ShutdownDynamicCOMServer(this);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v12,
      v16);
  v13 = (void *)*((_QWORD *)this + 17);
  if ( v13 && v13 != (void *)-1LL )
    CloseHandle(v13);
  v14 = *((_QWORD *)this + 16);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  *((_QWORD *)this + 10) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v15 = (void *)*((_QWORD *)this + 8);
  if ( v15 && v15 != (void *)-1LL )
    CloseHandle(v15);
  *(_QWORD *)this = &CWuaSingletonClassFactory::`vftable';
  CWuaClassFactoryBase::~CWuaClassFactoryBase(this);
}

```

## disassembly

```asm
0x18003583c  mov     [rsp+arg_8], rbx
0x180035841  mov     [rsp+arg_10], rbp
0x180035846  push    rsi
0x180035847  push    rdi
0x180035848  push    r14
0x18003584a  sub     rsp, 50h
0x18003584e  mov     rbx, rcx
0x180035851  lea     rax, ??_7RemoteUHProcessHostWrapper@UpdateHandler@@6BCWuaSingletonClassFactory@@@; const UpdateHandler::RemoteUHProcessHostWrapper::`vftable'{for `CWuaSingletonClassFactory'}
0x180035858  mov     [rcx], rax
0x18003585b  lea     rax, ??_7RemoteUHProcessHostWrapper@UpdateHandler@@6BIRemoteUHProcessHostRegistrar@@@; const UpdateHandler::RemoteUHProcessHostWrapper::`vftable'{for `IRemoteUHProcessHostRegistrar'}
0x180035862  mov     [rcx+30h], rax
0x180035866  mov     rcx, [rcx+40h]; hHandle
0x18003586a  lea     rbp, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035871  test    rcx, rcx
0x180035874  jz      loc_1800359CA
0x18003587a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003587e  jz      loc_1800359CA
0x180035884  xor     edx, edx; dwMilliseconds
0x180035886  call    cs:__imp_WaitForSingleObject
0x18003588c  mov     edi, 102h
0x180035891  cmp     eax, edi
0x180035893  jnz     loc_1800359CA
0x180035899  xorps   xmm0, xmm0
0x18003589c  movups  [rsp+68h+var_28], xmm0
0x1800358a1  mov     qword ptr [rsp+68h+var_28], rbx
0x1800358a6  mov     byte ptr [rsp+68h+var_28+8], 1
0x1800358ab  mov     rax, [rbx+88h]
0x1800358b2  test    rax, rax
0x1800358b5  jz      short loc_180035914
0x1800358b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800358bb  jz      short loc_180035914
0x1800358bd  mov     rcx, [rbx+80h]
0x1800358c4  test    rcx, rcx
0x1800358c7  jz      short loc_180035914
0x1800358c9  mov     rax, [rcx]
0x1800358cc  mov     rax, [rax+18h]
0x1800358d0  call    _guard_dispatch_icall
0x1800358d5  mov     esi, eax
0x1800358d7  test    eax, eax
0x1800358d9  jns     short loc_180035914
0x1800358db  mov     rcx, [rsp+68h]; this
0x1800358e0  mov     r9d, eax; char *
0x1800358e3  mov     r8, rbp; unsigned int
0x1800358e6  mov     edx, 1B2h; void *
0x1800358eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358f0  mov     edx, 1BCh; void *
0x1800358f5  mov     rcx, [rsp+68h]; this
0x1800358fa  mov     r9d, esi; char *
0x1800358fd  mov     r8, rbp; unsigned int
0x180035900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035905  lea     rcx, [rsp+68h+var_28]
0x18003590a  call    wil__details__lambda_call__lambda_863f880bfefcaab31a131a31f7a29590______lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___
0x18003590f  jmp     loc_1800359CC
0x180035914  imul    edx, [rbx+140h], 3E8h; dwMilliseconds
0x18003591e  mov     rcx, [rbx+40h]; hHandle
0x180035922  call    cs:__imp_WaitForSingleObject
0x180035928  cmp     eax, edi
0x18003592a  jnz     loc_1800359BB
0x180035930  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180035935  test    eax, eax
0x180035937  jz      short loc_18003595F
0x180035939  xor     r9d, r9d
0x18003593c  lea     r8, ?c_szRegRemoteUHTimeoutNoTelAssert@@3QB_WB; "RemoteUHTimeoutNoTelAssert"
0x180035943  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003594a  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x18003594f  test    eax, eax
0x180035951  jz      short loc_18003595F
0x180035953  mov     esi, 80242027h
0x180035958  mov     edx, 1C4h
0x18003595d  jmp     short loc_1800358F5
0x18003595f  lea     rax, aRemoteuhproces; "RemoteUHProcessHostWrapper::Stop() time"...
0x180035966  mov     [rsp+68h+var_30], rax
0x18003596b  lea     rax, aFalse; "false"
0x180035972  mov     [rsp+68h+var_38], rax
0x180035977  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x18003597e  mov     [rsp+68h+var_40], rax
0x180035983  mov     [rsp+68h+var_48], 0
0x18003598c  mov     edx, 1C8h
0x180035991  mov     r9d, 3
0x180035997  lea     r8d, [r9+1Dh]
0x18003599b  lea     rcx, aUpdatehandlerR; "UpdateHandler::RemoteUHProcessHostWrapp"...
0x1800359a2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800359a7  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x1800359ac  mov     esi, 80242027h
0x1800359b1  mov     edx, 1C9h
0x1800359b6  jmp     loc_1800358F5
0x1800359bb  mov     byte ptr [rsp+68h+var_28+8], 0
0x1800359c0  lea     rcx, [rsp+68h+var_28]
0x1800359c5  call    wil__details__lambda_call__lambda_863f880bfefcaab31a131a31f7a29590______lambda_call__lambda_863f880bfefcaab31a131a31f7a29590___
0x1800359ca  xor     esi, esi
0x1800359cc  mov     r14, rbx
0x1800359cf  mov     edi, 88h
0x1800359d4  mov     rcx, [rsp+68h]; this
0x1800359d9  test    esi, esi
0x1800359db  jns     short loc_1800359EB
0x1800359dd  mov     r9d, esi; char *
0x1800359e0  mov     r8, rbp; unsigned int
0x1800359e3  lea     edx, [rdi+7Bh]; void *
0x1800359e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800359eb  mov     rcx, rbx; this
0x1800359ee  call    ?ShutdownDynamicCOMServer@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJXZ; UpdateHandler::RemoteUHProcessHostWrapper::ShutdownDynamicCOMServer(void)
0x1800359f3  mov     rcx, [rsp+68h]; this
0x1800359f8  test    eax, eax
0x1800359fa  jns     short loc_180035A0C
0x1800359fc  mov     r9d, eax; char *
0x1800359ff  mov     r8, rbp; unsigned int
0x180035a02  mov     edx, 104h; void *
0x180035a07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035a0c  mov     rcx, [r14+rdi]; hObject
0x180035a10  test    rcx, rcx
0x180035a13  jz      short loc_180035A22
0x180035a15  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035a19  jz      short loc_180035A22
0x180035a1b  call    cs:__imp_CloseHandle
0x180035a21  nop
0x180035a22  mov     rcx, [rbx+80h]
0x180035a29  test    rcx, rcx
0x180035a2c  jz      short loc_180035A3B
0x180035a2e  mov     rax, [rcx]
0x180035a31  mov     rax, [rax+10h]
0x180035a35  call    _guard_dispatch_icall
0x180035a3a  nop
0x180035a3b  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180035a42  mov     [rbx+50h], rax
0x180035a46  lea     rcx, [rbx+58h]; lpCriticalSection
0x180035a4a  call    cs:__imp_DeleteCriticalSection
0x180035a50  mov     rcx, [rbx+40h]; hObject
0x180035a54  test    rcx, rcx
0x180035a57  jz      short loc_180035A65
0x180035a59  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035a5d  jz      short loc_180035A65
0x180035a5f  call    cs:__imp_CloseHandle
0x180035a65  lea     rax, ??_7CWuaSingletonClassFactory@@6B@; const CWuaSingletonClassFactory::`vftable'
0x180035a6c  mov     [rbx], rax
0x180035a6f  mov     rcx, rbx; this
0x180035a72  lea     r11, [rsp+68h+var_18]
0x180035a77  mov     rbx, [r11+28h]
0x180035a7b  mov     rbp, [r11+30h]
0x180035a7f  mov     rsp, r11
0x180035a82  pop     r14
0x180035a84  pop     rdi
0x180035a85  pop     rsi
0x180035a86  jmp     ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
```
