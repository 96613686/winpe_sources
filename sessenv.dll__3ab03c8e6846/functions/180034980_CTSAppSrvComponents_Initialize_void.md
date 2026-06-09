# CTSAppSrvComponents::Initialize(void)

- ea: `0x180034980`
- end: `0x180034b73`
- name: `?Initialize@CTSAppSrvComponents@@QEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(CTSAppSrvComponents *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180034880`

## callees

- `0x180003f30`
- `0x18001716c`
- `0x18001a2a4`
- `0x18001ec04`
- `0x180034224`
- `0x180034554`
- `0x180034980`
- `0x180034d38`
- `0x1800352bc`
- `0x18005d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180034b5f`
- `ntdll!RtlReleaseResource` at `0x180034b5f`

## string_xrefs

- `0x1800349aa`: `%SystemRoot%\system32\TSMSISrv.dll`
- `0x1800349cc`: `m_TSMSI.Start() failed 0x%x`
- `0x1800349d5`: `m_TSMSI.Initialize failed 0x%x`
- `0x1800349f1`: `%SystemRoot%\system32\TSVIPSrv.dll`
- `0x180034b3e`: `CTSAppSrvComponents::Initialize`
- `0x180034ac1`: `new CConfigChange failed: 0x%x in %s`
- `0x180034ae4`: `ITSAPPSRVConfig::GetInstanceOfObject failed: 0x%x in %s`
- `0x180034af7`: `Software\Policies\Microsoft\Windows NT\Terminal Services\TSAppSrv`
- `0x180034b0e`: `m_ptrAppSrvConfig->Initialize failed: 0x%x in %s`
- `0x180034b34`: `m_ptrAppSrvConfig->RegisterNotification failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSAppSrvComponents::Initialize(CTSAppSrvComponents *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // rbx
  int InstanceOfObject; // eax
  const char *v11; // rdx
  PRTL_RESOURCE Resource; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h]

  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (CTSAppSrvComponents *)((char *)this + 1616));
  v2 = __AppSrvComponent::Initialize(
         (CTSAppSrvComponents *)((char *)this + 1720),
         L"%SystemRoot%\\system32\\TSMSISrv.dll");
  if ( v2 < 0 )
  {
    _DbgPrintMessage(8, "m_TSMSI.Initialize failed 0x%x", (unsigned int)v2);
  }
  else
  {
    v3 = __AppSrvComponent::Start((CTSAppSrvComponents *)((char *)this + 1720));
    if ( v3 < 0 )
      _DbgPrintMessage(8, "m_TSMSI.Start() failed 0x%x", (unsigned int)v3);
  }
  v4 = __AppSrvComponent::Initialize(
         (CTSAppSrvComponents *)((char *)this + 1760),
         L"%SystemRoot%\\system32\\TSVIPSrv.dll");
  v5 = v4;
  if ( v4 < 0 )
  {
    _DbgPrintMessage(8, "m_TSVIP.Initialize failed 0x%x", (unsigned int)v4);
  }
  else
  {
    v6 = __AppSrvComponent::Start((CTSAppSrvComponents *)((char *)this + 1760));
    v5 = v6;
    if ( v6 < 0 )
      _DbgPrintMessage(8, "m_TSVIP.Start() failed 0x%x", (unsigned int)v6);
  }
  v7 = operator new(0x658u, (const struct std::nothrow_t *)std::nothrow);
  if ( v7 )
  {
    v7[1] = &CTSAppSrvComponents::CConfigChange::`vbtable';
    CTSPrivateObject<IConfigChangeSink>::CTSPrivateObject<IConfigChangeSink>(v7);
    v8 = v7[1];
    *v7 = &CTSAppSrvComponents::CConfigChange::`vftable'{for `IConfigChangeSink'};
    v5 = 0;
    *(_QWORD *)((char *)v7 + *(int *)(v8 + 4) + 8) = &CTSAppSrvComponents::CConfigChange::`vftable'{for `IUnknown'};
    *(_DWORD *)((char *)v7 + *(int *)(v7[1] + 4LL) + 4) = *(_DWORD *)(v7[1] + 4LL) - 1608;
    v7[200] = 0;
  }
  else
  {
    v7 = 0;
  }
  SmartPtr<CTSAppSrvComponents::CConfigChange>::operator=((char *)this + 1600, v7);
  if ( *((_QWORD *)this + 200) )
  {
    if ( v5 >= 0 )
    {
      v9 = (_QWORD *)((char *)this + 1592);
      *(_QWORD *)(*((_QWORD *)this + 200) + 1600LL) = this;
      InstanceOfObject = ITSAPPSRVConfig::GetInstanceOfObject((struct ITSAPPSRVConfig **)this + 199);
      if ( InstanceOfObject >= 0 )
      {
        InstanceOfObject = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v9 + 24LL))(
                             *v9,
                             L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\TSAppSrv",
                             L"System\\CurrentControlSet\\Control\\Terminal Server\\TSAppSrv");
        if ( InstanceOfObject >= 0 )
        {
          InstanceOfObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v9 + 40LL))(
                               *v9,
                               *((_QWORD *)this + 200),
                               (char *)this + 1608);
          if ( InstanceOfObject >= 0 )
            goto LABEL_23;
          v11 = "m_ptrAppSrvConfig->RegisterNotification failed: 0x%x in %s";
        }
        else
        {
          v11 = "m_ptrAppSrvConfig->Initialize failed: 0x%x in %s";
        }
      }
      else
      {
        v11 = "ITSAPPSRVConfig::GetInstanceOfObject failed: 0x%x in %s";
      }
      _DbgPrintMessage(8, v11, (unsigned int)InstanceOfObject, "CTSAppSrvComponents::Initialize");
      goto LABEL_23;
    }
  }
  else
  {
    v5 = -2147024882;
  }
  _DbgPrintMessage(8, "new CConfigChange failed: 0x%x in %s", (unsigned int)v5, "CTSAppSrvComponents::Initialize");
LABEL_23:
  if ( v14 && LODWORD(Resource[1].Lock.DebugInfo) )
    RtlReleaseResource(Resource);
  return 0;
}

```

## disassembly

```asm
0x180034980  push    rbx
0x180034982  push    rsi
0x180034983  push    rdi
0x180034984  push    r14
0x180034986  push    r15
0x180034988  sub     rsp, 30h
0x18003498c  mov     rsi, rcx
0x18003498f  lea     rdx, [rcx+650h]; struct CResource *
0x180034996  lea     rcx, [rsp+58h+Resource]; this
0x18003499b  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800349a0  lea     rbx, [rsi+6B8h]
0x1800349a7  mov     rcx, rbx; this
0x1800349aa  lea     rdx, Src; "%SystemRoot%\\system32\\TSMSISrv.dll"
0x1800349b1  call    ?Initialize@__AppSrvComponent@@QEAAJPEBG@Z; __AppSrvComponent::Initialize(ushort const *)
0x1800349b6  mov     r15d, 8
0x1800349bc  test    eax, eax
0x1800349be  js      short loc_1800349D5
0x1800349c0  mov     rcx, rbx; this
0x1800349c3  call    ?Start@__AppSrvComponent@@QEAAJXZ; __AppSrvComponent::Start(void)
0x1800349c8  test    eax, eax
0x1800349ca  jns     short loc_1800349E7
0x1800349cc  lea     rdx, aMTsmsiStartFai; "m_TSMSI.Start() failed 0x%x"
0x1800349d3  jmp     short loc_1800349DC
0x1800349d5  lea     rdx, aMTsmsiInitiali; "m_TSMSI.Initialize failed 0x%x"
0x1800349dc  mov     r8d, eax
0x1800349df  mov     ecx, r15d; int
0x1800349e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800349e7  lea     rdi, [rsi+6E0h]
0x1800349ee  mov     rcx, rdi; this
0x1800349f1  lea     rdx, aSystemrootSyst_0; "%SystemRoot%\\system32\\TSVIPSrv.dll"
0x1800349f8  call    ?Initialize@__AppSrvComponent@@QEAAJPEBG@Z; __AppSrvComponent::Initialize(ushort const *)
0x1800349fd  mov     ebx, eax
0x1800349ff  test    eax, eax
0x180034a01  js      short loc_180034A1A
0x180034a03  mov     rcx, rdi; this
0x180034a06  call    ?Start@__AppSrvComponent@@QEAAJXZ; __AppSrvComponent::Start(void)
0x180034a0b  mov     ebx, eax
0x180034a0d  test    eax, eax
0x180034a0f  jns     short loc_180034A2C
0x180034a11  lea     rdx, aMTsvipStartFai; "m_TSVIP.Start() failed 0x%x"
0x180034a18  jmp     short loc_180034A21
0x180034a1a  lea     rdx, aMTsvipInitiali; "m_TSVIP.Initialize failed 0x%x"
0x180034a21  mov     r8d, eax
0x180034a24  mov     ecx, r15d; int
0x180034a27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180034a2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034a33  mov     ecx, 658h; unsigned __int64
0x180034a38  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034a3d  mov     rdi, rax
0x180034a40  test    rax, rax
0x180034a43  jz      short loc_180034A97
0x180034a45  lea     rax, ??_8CConfigChange@CTSAppSrvComponents@@7B@; const CTSAppSrvComponents::CConfigChange::`vbtable'
0x180034a4c  mov     rcx, rdi
0x180034a4f  mov     [rdi+8], rax
0x180034a53  call    ??0?$CTSPrivateObject@VIConfigChangeSink@@@@QEAA@PEBD@Z; CTSPrivateObject<IConfigChangeSink>::CTSPrivateObject<IConfigChangeSink>(char const *)
0x180034a58  mov     rcx, [rdi+8]
0x180034a5c  lea     rax, ??_7CConfigChange@CTSAppSrvComponents@@6BIConfigChangeSink@@@; const CTSAppSrvComponents::CConfigChange::`vftable'{for `IConfigChangeSink'}
0x180034a63  mov     [rdi], rax
0x180034a66  xor     ebx, ebx
0x180034a68  lea     rax, ??_7CConfigChange@CTSAppSrvComponents@@6BIUnknown@@@; const CTSAppSrvComponents::CConfigChange::`vftable'{for `IUnknown'}
0x180034a6f  movsxd  rdx, dword ptr [rcx+4]
0x180034a73  mov     [rdx+rdi+8], rax
0x180034a78  mov     rax, [rdi+8]
0x180034a7c  movsxd  rcx, dword ptr [rax+4]
0x180034a80  lea     edx, [rcx-648h]
0x180034a86  mov     [rcx+rdi+4], edx
0x180034a8a  mov     qword ptr [rdi+640h], 0
0x180034a95  jmp     short loc_180034A99
0x180034a97  xor     edi, edi
0x180034a99  lea     r14, [rsi+640h]
0x180034aa0  mov     rdx, rdi
0x180034aa3  mov     rcx, r14
0x180034aa6  call    ??4?$SmartPtr@VCConfigChange@CTSAppSrvComponents@@@@QEAAAEAV0@PEAVCConfigChange@CTSAppSrvComponents@@@Z; SmartPtr<CTSAppSrvComponents::CConfigChange>::operator=(CTSAppSrvComponents::CConfigChange *)
0x180034aab  mov     rax, [r14]
0x180034aae  test    rax, rax
0x180034ab1  jnz     short loc_180034ABA
0x180034ab3  mov     ebx, 8007000Eh
0x180034ab8  jmp     short loc_180034ABE
0x180034aba  test    ebx, ebx
0x180034abc  jns     short loc_180034ACA
0x180034abe  mov     r8d, ebx
0x180034ac1  lea     rdx, aNewCconfigchan; "new CConfigChange failed: 0x%x in %s"
0x180034ac8  jmp     short loc_180034B3E
0x180034aca  lea     rbx, [rsi+638h]
0x180034ad1  mov     [rax+640h], rsi
0x180034ad8  mov     rcx, rbx; struct ITSAPPSRVConfig **
0x180034adb  call    ?GetInstanceOfObject@ITSAPPSRVConfig@@SAJPEAPEAV1@@Z; ITSAPPSRVConfig::GetInstanceOfObject(ITSAPPSRVConfig * *)
0x180034ae0  test    eax, eax
0x180034ae2  jns     short loc_180034AED
0x180034ae4  lea     rdx, aItsappsrvconfi_0; "ITSAPPSRVConfig::GetInstanceOfObject fa"...
0x180034aeb  jmp     short loc_180034B3B
0x180034aed  mov     rcx, [rbx]
0x180034af0  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ter"...
0x180034af7  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x180034afe  mov     rax, [rcx]
0x180034b01  mov     rax, [rax+18h]
0x180034b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b0a  test    eax, eax
0x180034b0c  jns     short loc_180034B17
0x180034b0e  lea     rdx, aMPtrappsrvconf; "m_ptrAppSrvConfig->Initialize failed: 0"...
0x180034b15  jmp     short loc_180034B3B
0x180034b17  mov     rcx, [rbx]
0x180034b1a  lea     r8, [rsi+648h]
0x180034b21  mov     rdx, [r14]
0x180034b24  mov     rax, [rcx]
0x180034b27  mov     rax, [rax+28h]
0x180034b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b30  test    eax, eax
0x180034b32  jns     short loc_180034B4D
0x180034b34  lea     rdx, aMPtrappsrvconf_0; "m_ptrAppSrvConfig->RegisterNotification"...
0x180034b3b  mov     r8d, eax
0x180034b3e  lea     r9, aCtsappsrvcompo_0; "CTSAppSrvComponents::Initialize"
0x180034b45  mov     ecx, r15d; int
0x180034b48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180034b4d  cmp     [rsp+58h+var_30], 0
0x180034b52  jz      short loc_180034B65
0x180034b54  mov     rcx, [rsp+58h+Resource]; Resource
0x180034b59  cmp     dword ptr [rcx+60h], 0
0x180034b5d  jz      short loc_180034B65
0x180034b5f  call    cs:__imp_RtlReleaseResource
0x180034b65  xor     eax, eax
0x180034b67  add     rsp, 30h
0x180034b6b  pop     r15
0x180034b6d  pop     r14
0x180034b6f  pop     rdi
0x180034b70  pop     rsi
0x180034b71  pop     rbx
0x180034b72  retn
```
