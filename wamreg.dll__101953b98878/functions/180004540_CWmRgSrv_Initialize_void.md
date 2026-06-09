# CWmRgSrv::Initialize(void)

- ea: `0x180004540`
- end: `0x1800046b9`
- name: `?Initialize@CWmRgSrv@@UEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(CWmRgSrv *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180004540`
- `0x180004dac`
- `0x180006398`
- `0x180007010`

## import_xrefs

- `ole32!CoRevokeClassObject` at `0x180004658`
- `ole32!CoRevokeClassObject` at `0x180004658`
- `ole32!CoRegisterClassObject` at `0x1800045fe`
- `ole32!CoRegisterClassObject` at `0x1800045fe`
- `KERNEL32!GetLastError` at `0x180004586`
- `KERNEL32!GetLastError` at `0x180004617`
- `KERNEL32!GetLastError` at `0x180004586`
- `KERNEL32!GetLastError` at `0x180004617`
- `iisutil!PuDbgPrint` at `0x1800045b7`
- `iisutil!PuDbgPrint` at `0x180004648`
- `iisutil!PuDbgPrint` at `0x1800045b7`
- `iisutil!PuDbgPrint` at `0x180004648`

## string_xrefs

- `0x18000459e`: `inetsrv\iis\svcs\wam\wamreg\comobj.cpp`
- `0x18000462f`: `inetsrv\iis\svcs\wam\wamreg\comobj.cpp`

## pseudocode

```c
__int64 __fastcall CWmRgSrv::Initialize(CWmRgSrv *this)
{
  _DWORD *v2; // rax
  WamRegRegistryConfig *v3; // rcx
  DWORD v4; // eax
  HRESULT WamDllPath; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx

  v2 = operator new(0x10u);
  if ( v2 )
  {
    v3 = (WamRegRegistryConfig *)&CWamAdminFactory::`vftable';
    v2[2] = 1;
    *(_QWORD *)v2 = &CWamAdminFactory::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)&g_dwRefCount);
  }
  *((_QWORD *)this + 2) = v2;
  if ( v2 )
  {
    WamDllPath = WamRegRegistryConfig::LoadWamDllPath(v3);
    if ( WamDllPath >= 0 )
    {
      WamDllPath = WamRegMetabaseConfig::MetabaseInit();
      if ( WamDllPath >= 0 )
      {
        WamDllPath = CoRegisterClassObject(&CLSID_WamAdmin, *((LPUNKNOWN *)this + 2), 0x15u, 1u, &g_dwWamAdminRegister);
        if ( WamDllPath >= 0 )
          return (unsigned int)WamDllPath;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LastError = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\wam\\wamreg\\comobj.cpp",
            154,
            "CWmRgSrv::Initialize",
            "WamRegSrv Init failed. error %08x\n",
            LastError);
        }
      }
    }
    if ( g_dwWamAdminRegister )
    {
      CoRevokeClassObject(g_dwWamAdminRegister);
      g_dwWamAdminRegister = 0;
    }
    v7 = *((_QWORD *)this + 2);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)this + 2) = 0;
    }
    if ( WamRegMetabaseConfig::m_pMetabase )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 16LL))(WamRegMetabaseConfig::m_pMetabase);
      WamRegMetabaseConfig::m_pMetabase = 0;
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v4 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\comobj.cpp",
        132,
        "CWmRgSrv::Initialize",
        "WamRegSrv Init failed. error %08x\n",
        v4);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)WamDllPath;
}

```

## disassembly

```asm
0x180004540  mov     [rsp+arg_0], rbx
0x180004545  push    rdi
0x180004546  sub     rsp, 30h
0x18000454a  mov     rdi, rcx
0x18000454d  mov     ecx, 10h; Size
0x180004552  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004557  test    rax, rax
0x18000455a  jz      short loc_180004574
0x18000455c  lea     rcx, ??_7CWamAdminFactory@@6B@; this
0x180004563  mov     dword ptr [rax+8], 1
0x18000456a  mov     [rax], rcx
0x18000456d  lock inc cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180004574  mov     [rdi+10h], rax
0x180004578  test    rax, rax
0x18000457b  jnz     short loc_1800045C7
0x18000457d  test    byte ptr cs:g_dwDebugFlags, 3
0x180004584  jz      short loc_1800045BD
0x180004586  call    cs:__imp_GetLastError
0x18000458c  mov     rcx, cs:g_pDebug
0x180004593  lea     r9, aCwmrgsrvInitia; "CWmRgSrv::Initialize"
0x18000459a  mov     [rsp+38h+var_10], eax
0x18000459e  lea     rdx, aInetsrvIisSvcs_0; "inetsrv\\iis\\svcs\\wam\\wamreg\\comobj"...
0x1800045a5  lea     rax, aWamregsrvInitF; "WamRegSrv Init failed. error %08x\n"
0x1800045ac  mov     r8d, 84h
0x1800045b2  mov     [rsp+38h+lpdwRegister], rax
0x1800045b7  call    cs:__imp_PuDbgPrint
0x1800045bd  mov     ebx, 8007000Eh
0x1800045c2  jmp     loc_1800046AC
0x1800045c7  call    ?LoadWamDllPath@WamRegRegistryConfig@@QEAAJXZ; WamRegRegistryConfig::LoadWamDllPath(void)
0x1800045cc  mov     ebx, eax
0x1800045ce  test    eax, eax
0x1800045d0  js      short loc_18000464E
0x1800045d2  call    ?MetabaseInit@WamRegMetabaseConfig@@SAJXZ; WamRegMetabaseConfig::MetabaseInit(void)
0x1800045d7  mov     ebx, eax
0x1800045d9  test    eax, eax
0x1800045db  js      short loc_18000464E
0x1800045dd  mov     rdx, [rdi+10h]; pUnk
0x1800045e1  lea     rax, ?g_dwWamAdminRegister@@3KA; ulong g_dwWamAdminRegister
0x1800045e8  mov     r9d, 1; flags
0x1800045ee  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x1800045f3  lea     rcx, CLSID_WamAdmin; rclsid
0x1800045fa  lea     r8d, [r9+14h]; dwClsContext
0x1800045fe  call    cs:__imp_CoRegisterClassObject
0x180004604  mov     ebx, eax
0x180004606  test    eax, eax
0x180004608  jns     loc_1800046AC
0x18000460e  test    byte ptr cs:g_dwDebugFlags, 3
0x180004615  jz      short loc_18000464E
0x180004617  call    cs:__imp_GetLastError
0x18000461d  mov     rcx, cs:g_pDebug
0x180004624  lea     r9, aCwmrgsrvInitia; "CWmRgSrv::Initialize"
0x18000462b  mov     [rsp+38h+var_10], eax
0x18000462f  lea     rdx, aInetsrvIisSvcs_0; "inetsrv\\iis\\svcs\\wam\\wamreg\\comobj"...
0x180004636  lea     rax, aWamregsrvInitF; "WamRegSrv Init failed. error %08x\n"
0x18000463d  mov     r8d, 9Ah
0x180004643  mov     [rsp+38h+lpdwRegister], rax
0x180004648  call    cs:__imp_PuDbgPrint
0x18000464e  mov     ecx, cs:?g_dwWamAdminRegister@@3KA; dwRegister
0x180004654  test    ecx, ecx
0x180004656  jz      short loc_180004668
0x180004658  call    cs:__imp_CoRevokeClassObject
0x18000465e  mov     cs:?g_dwWamAdminRegister@@3KA, 0; ulong g_dwWamAdminRegister
0x180004668  mov     rcx, [rdi+10h]
0x18000466c  test    rcx, rcx
0x18000466f  jz      short loc_180004685
0x180004671  mov     rax, [rcx]
0x180004674  mov     rax, [rax+10h]
0x180004678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467d  mov     qword ptr [rdi+10h], 0
0x180004685  test    ebx, ebx
0x180004687  jns     short loc_1800046AC
0x180004689  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180004690  test    rcx, rcx
0x180004693  jz      short loc_1800046AC
0x180004695  mov     rax, [rcx]
0x180004698  mov     rax, [rax+10h]
0x18000469c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a1  mov     cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA, 0; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800046ac  mov     eax, ebx
0x1800046ae  mov     rbx, [rsp+38h+arg_0]
0x1800046b3  add     rsp, 30h
0x1800046b7  pop     rdi
0x1800046b8  retn
```
