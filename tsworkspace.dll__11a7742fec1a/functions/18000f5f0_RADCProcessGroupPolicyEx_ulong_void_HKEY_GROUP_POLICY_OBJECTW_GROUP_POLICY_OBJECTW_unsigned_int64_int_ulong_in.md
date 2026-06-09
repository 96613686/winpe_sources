# RADCProcessGroupPolicyEx(ulong,void *,HKEY__ *,_GROUP_POLICY_OBJECTW *,_GROUP_POLICY_OBJECTW *,unsigned __int64,int *,ulong (*)(int,ushort *),IWbemServices *,long *)

- ea: `0x18000f5f0`
- end: `0x18000fd35`
- name: `?RADCProcessGroupPolicyEx@@YAKKPEAXPEAUHKEY__@@PEAU_GROUP_POLICY_OBJECTW@@2_KPEAHP6AKHPEAG@ZPEAUIWbemServices@@PEAJ@Z`
- size: `1861`
- prototype: `unsigned int(unsigned int, void *, HKEY, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW *, unsigned __int64, int *, unsigned int (*)(int, unsigned __int16 *), struct IWbemServices *, int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004970`
- `0x180005500`
- `0x180005524`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000c3d0`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ee9c`
- `0x18000eed0`
- `0x18000efc4`
- `0x18000eff0`
- `0x18000f090`
- `0x18000f5f0`
- `0x18000fd3c`
- `0x18000feb4`
- `0x18000fed8`
- `0x18002f4f0`
- `0x18002f810`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000f92d`
- `msvcrt!_wcsicmp` at `0x18000f92d`
- `ADVAPI32!RevertToSelf` at `0x18000fc85`
- `ADVAPI32!RevertToSelf` at `0x18000fc85`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000f73f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000f73f`
- `OLEAUT32!__imp_VariantInit` at `0x18000fb84`
- `OLEAUT32!__imp_VariantInit` at `0x18000fb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc8f`

## string_xrefs

- `0x18000fa36`: `Failed to disable the policy task`
- `0x18000fada`: `Failed to enable the policy task`
- `0x18000fb41`: `Policy task creation failed`
- `0x18000fc08`: `Policy task execution failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall RADCProcessGroupPolicyEx(
        int a1,
        void *a2,
        HKEY a3,
        struct _GROUP_POLICY_OBJECTW *a4,
        struct _GROUP_POLICY_OBJECTW *a5,
        unsigned __int64 a6,
        int *a7,
        unsigned int (*a8)(int, unsigned __int16 *),
        struct IWbemServices *a9,
        int *a10)
{
  PVOID *v12; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v14; // eax
  signed int DefaultWorkspace; // ebx
  unsigned int v16; // eax
  signed int LastError; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  signed int v20; // eax
  CWorkspaceManager *Instance; // rbx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  const wchar_t *v25; // rbx
  const wchar_t *v26; // rax
  PVOID *v27; // rax
  unsigned int v28; // eax
  struct IRegisteredTask *v29; // rbx
  unsigned int v30; // eax
  HRESULT (__stdcall *put_Enabled)(IRegisteredTask *, VARIANT_BOOL); // rdi
  unsigned __int16 v32; // ax
  int v33; // ebx
  unsigned int v34; // eax
  struct IRegisteredTask *v35; // rbx
  HRESULT (__stdcall *v36)(IRegisteredTask *, VARIANT_BOOL); // rdi
  unsigned __int16 v37; // ax
  unsigned int v38; // eax
  unsigned int v39; // eax
  struct IRegisteredTask *v40; // rdi
  HRESULT (__stdcall *Run)(IRegisteredTask *, VARIANT, IRunningTask **); // rbx
  unsigned int v42; // eax
  signed int v43; // eax
  unsigned int v44; // eax
  __int64 v46; // [rsp+28h] [rbp-F0h]
  struct IRegisteredTask *v47; // [rsp+38h] [rbp-E0h] BYREF
  struct CWorkspace *v48; // [rsp+40h] [rbp-D8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-D0h] BYREF
  VARIANTARG pvarSrc; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+78h] [rbp-A0h]
  _BYTE v52[56]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v53[16]; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-50h]

  v51 = -2;
  ComPlainSmartPtr<CWorkspace>::ComPlainSmartPtr<CWorkspace>(&v48, 0);
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v47);
  std::wstring::wstring(v53);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
      CurrentThreadActivityIdPrefix,
      a1);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (a1 & 1) != 0 )
  {
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 8) == 0 || *((_BYTE *)v12 + 25) < 2u )
    {
      LOWORD(DefaultWorkspace) = 87;
    }
    else
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      LOWORD(DefaultWorkspace) = 87;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids, v14, 87);
    }
    goto LABEL_80;
  }
  if ( !a2 )
  {
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 8) == 0 || *((_BYTE *)v12 + 25) < 2u )
    {
      LOWORD(DefaultWorkspace) = 87;
    }
    else
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      LOWORD(DefaultWorkspace) = 87;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids, v16, 87);
    }
    goto LABEL_80;
  }
  if ( !ImpersonateLoggedOnUser(a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids, v19, v18);
    }
    v20 = GetLastError();
    LOWORD(DefaultWorkspace) = v20;
    if ( v20 > 0 )
      LOWORD(DefaultWorkspace) = v20;
    goto LABEL_80;
  }
  Instance = CWorkspaceManager::GetInstance();
  if ( !Instance )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
        v22,
        -2147024882);
    }
    LOWORD(DefaultWorkspace) = 14;
    goto LABEL_80;
  }
  GetPolicyTask(&v47, 0);
  DefaultWorkspace = CWorkspaceManager::GetDefaultWorkspace(Instance, &v48);
  if ( (int)(DefaultWorkspace + 0x80000000) >= 0 && DefaultWorkspace != -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
        v23,
        DefaultWorkspace);
    }
    goto LABEL_80;
  }
  DefaultWorkspace = ReadRADCPolicyDefaultWorkspaceURL(v53);
  if ( ((DefaultWorkspace + 0x80000000) & 0x80000000) == 0 && DefaultWorkspace != -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
        v24,
        DefaultWorkspace);
    }
    goto LABEL_80;
  }
  if ( v48 )
  {
    v25 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v48 + 296);
    v26 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
    if ( _wcsicmp(v26, v25) )
      goto LABEL_62;
LABEL_48:
    v27 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids, v28);
      v27 = (PVOID *)WPP_GLOBAL_Control;
    }
    v29 = v47;
    if ( v47 )
    {
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids, v30);
        v29 = v47;
      }
      put_Enabled = v29->lpVtbl->put_Enabled;
      pvarSrc.vt = 11;
      pvarSrc.iVal = 0;
      v32 = _variant_t::operator short(&pvarSrc);
      v33 = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))put_Enabled)(v29, v32);
      _variant_t::~_variant_t((_variant_t *)&pvarSrc);
      if ( v33 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
          v34,
          (__int64)"Failed to disable the policy task",
          v33,
          v33);
      }
    }
    goto LABEL_79;
  }
  if ( !v54 )
    goto LABEL_48;
LABEL_62:
  v35 = v47;
  if ( v47 )
  {
    v36 = v47->lpVtbl->put_Enabled;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v37 = _variant_t::operator short(&pvarg);
    DefaultWorkspace = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v36)(v35, v37);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( DefaultWorkspace < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
          v38,
          (__int64)"Failed to enable the policy task",
          DefaultWorkspace,
          DefaultWorkspace);
      }
      goto LABEL_80;
    }
LABEL_73:
    if ( (a1 & 0x10) != 0 )
    {
      v40 = v47;
      Run = v47->lpVtbl->Run;
      VariantInit(&pvarg);
      *(VARIANTARG *)&v52[32] = pvarg;
      *(VARIANTARG *)v52 = pvarg;
      DefaultWorkspace = ((__int64 (__fastcall *)(struct IRegisteredTask *, _BYTE *, _QWORD))Run)(v40, v52, 0);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      if ( DefaultWorkspace < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v42 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
            v42,
            (__int64)"Policy task execution failed",
            DefaultWorkspace,
            DefaultWorkspace);
        }
        goto LABEL_80;
      }
    }
LABEL_79:
    LOWORD(DefaultWorkspace) = 0;
    goto LABEL_80;
  }
  DefaultWorkspace = GetPolicyTask(&v47, 1);
  if ( DefaultWorkspace >= 0 )
    goto LABEL_73;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v39 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
      v39,
      (__int64)"Policy task creation failed",
      DefaultWorkspace,
      DefaultWorkspace);
  }
LABEL_80:
  if ( v48 )
  {
    TCntPtr<CConfigManager>::SafeRelease(&v48);
    v48 = 0;
    TCntPtr<CConfigManager>::SafeAddRef(&v48);
  }
  if ( v47 )
  {
    TCntPtr<ITSThread>::SafeRelease(&v47);
    v47 = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v47);
  }
  if ( !RevertToSelf() )
  {
    v43 = GetLastError();
    DefaultWorkspace = v43;
    if ( v43 > 0 )
      DefaultWorkspace = (unsigned __int16)v43 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v46) = DefaultWorkspace;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
        v44,
        (__int64)"RevertToSelf failed",
        v46);
    }
  }
  std::wstring::~wstring(v53);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v47);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v48);
  return (unsigned __int16)DefaultWorkspace;
}

```

## disassembly

```asm
0x18000f5f0  push    rbx
0x18000f5f2  push    rsi
0x18000f5f3  push    rdi
0x18000f5f4  push    r12
0x18000f5f6  push    r14
0x18000f5f8  push    r15
0x18000f5fa  sub     rsp, 0E8h
0x18000f601  mov     [rsp+118h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18000f60a  mov     rax, cs:__security_cookie
0x18000f611  xor     rax, rsp
0x18000f614  mov     [rsp+118h+var_40], rax
0x18000f61c  mov     rbx, rdx
0x18000f61f  mov     r12d, ecx
0x18000f622  xor     edx, edx
0x18000f624  lea     rcx, [rsp+118h+var_D8]
0x18000f629  call    ??0?$ComPlainSmartPtr@VCWorkspace@@@@QEAA@PEAVCWorkspace@@@Z; ComPlainSmartPtr<CWorkspace>::ComPlainSmartPtr<CWorkspace>(CWorkspace *)
0x18000f62e  nop
0x18000f62f  lea     rcx, [rsp+118h+var_E0]
0x18000f634  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18000f639  nop
0x18000f63a  lea     rcx, [rsp+118h+var_60]
0x18000f642  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f647  nop
0x18000f648  lea     r15, WPP_GLOBAL_Control
0x18000f64f  mov     rax, cs:WPP_GLOBAL_Control
0x18000f656  cmp     rax, r15
0x18000f659  jz      short loc_18000F69C
0x18000f65b  test    byte ptr [rax+1Ch], 1
0x18000f65f  jz      short loc_18000F69C
0x18000f661  cmp     byte ptr [rax+19h], 4
0x18000f665  jb      short loc_18000F69C
0x18000f667  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f66c  mov     edx, 0Ch
0x18000f671  mov     dword ptr [rsp+118h+var_F8], r12d
0x18000f676  mov     r9d, eax
0x18000f679  lea     r14, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids
0x18000f680  mov     r8, r14
0x18000f683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f68a  mov     rcx, [rcx+10h]
0x18000f68e  call    WPP_SF_Dd
0x18000f693  mov     rax, cs:WPP_GLOBAL_Control
0x18000f69a  jmp     short loc_18000F6A3
0x18000f69c  lea     r14, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids
0x18000f6a3  test    r12b, 1
0x18000f6a7  jz      short loc_18000F6F0
0x18000f6a9  cmp     rax, r15
0x18000f6ac  jz      short loc_18000F6E6
0x18000f6ae  test    byte ptr [rax+1Ch], 8
0x18000f6b2  jz      short loc_18000F6E6
0x18000f6b4  cmp     byte ptr [rax+19h], 2
0x18000f6b8  jb      short loc_18000F6E6
0x18000f6ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f6bf  mov     edx, 0Dh
0x18000f6c4  lea     ebx, [rdx+4Ah]
0x18000f6c7  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000f6cb  mov     r9d, eax
0x18000f6ce  mov     r8, r14
0x18000f6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6d8  mov     rcx, [rcx+10h]
0x18000f6dc  call    WPP_SF_Dd
0x18000f6e1  jmp     loc_18000FC43
0x18000f6e6  mov     ebx, 57h ; 'W'
0x18000f6eb  jmp     loc_18000FC43
0x18000f6f0  xor     esi, esi
0x18000f6f2  test    rbx, rbx
0x18000f6f5  jnz     short loc_18000F73C
0x18000f6f7  cmp     rax, r15
0x18000f6fa  jz      short loc_18000F732
0x18000f6fc  test    byte ptr [rax+1Ch], 8
0x18000f700  jz      short loc_18000F732
0x18000f702  cmp     byte ptr [rax+19h], 2
0x18000f706  jb      short loc_18000F732
0x18000f708  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f70d  lea     edx, [rsi+0Eh]
0x18000f710  lea     ebx, [rsi+57h]
0x18000f713  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000f717  mov     r9d, eax
0x18000f71a  mov     r8, r14
0x18000f71d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f724  mov     rcx, [rcx+10h]
0x18000f728  call    WPP_SF_Dd
0x18000f72d  jmp     loc_18000FC45
0x18000f732  mov     ebx, 57h ; 'W'
0x18000f737  jmp     loc_18000FC45
0x18000f73c  mov     rcx, rbx; hToken
0x18000f73f  call    cs:__imp_ImpersonateLoggedOnUser
0x18000f745  test    eax, eax
0x18000f747  jnz     short loc_18000F7B8
0x18000f749  mov     rax, cs:WPP_GLOBAL_Control
0x18000f750  cmp     rax, r15
0x18000f753  jz      short loc_18000F79A
0x18000f755  test    byte ptr [rax+1Ch], 8
0x18000f759  jz      short loc_18000F79A
0x18000f75b  cmp     byte ptr [rax+19h], 2
0x18000f75f  jb      short loc_18000F79A
0x18000f761  call    cs:__imp_GetLastError
0x18000f767  mov     ebx, eax
0x18000f769  test    eax, eax
0x18000f76b  jle     short loc_18000F776
0x18000f76d  movzx   ebx, ax
0x18000f770  or      ebx, 80070000h
0x18000f776  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f77b  mov     edx, 0Fh
0x18000f780  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000f784  mov     r9d, eax
0x18000f787  mov     r8, r14
0x18000f78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f791  mov     rcx, [rcx+10h]
0x18000f795  call    WPP_SF_Dd
0x18000f79a  call    cs:__imp_GetLastError
0x18000f7a0  mov     ebx, eax
0x18000f7a2  test    eax, eax
0x18000f7a4  jle     loc_18000FC45
0x18000f7aa  movzx   ebx, ax
0x18000f7ad  or      ebx, 80070000h
0x18000f7b3  jmp     loc_18000FC45
0x18000f7b8  call    ?GetInstance@CWorkspaceManager@@SAPEAV1@XZ; CWorkspaceManager::GetInstance(void)
0x18000f7bd  mov     rbx, rax
0x18000f7c0  test    rax, rax
0x18000f7c3  jnz     short loc_18000F811
0x18000f7c5  mov     rax, cs:WPP_GLOBAL_Control
0x18000f7cc  cmp     rax, r15
0x18000f7cf  jz      short loc_18000F803
0x18000f7d1  test    byte ptr [rax+1Ch], 8
0x18000f7d5  jz      short loc_18000F803
0x18000f7d7  cmp     byte ptr [rax+19h], 2
0x18000f7db  jb      short loc_18000F803
0x18000f7dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f7e2  lea     edx, [rbx+10h]
0x18000f7e5  mov     dword ptr [rsp+118h+var_F8], 8007000Eh
0x18000f7ed  mov     r9d, eax
0x18000f7f0  mov     r8, r14
0x18000f7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7fa  mov     rcx, [rcx+10h]
0x18000f7fe  call    WPP_SF_Dd
0x18000f803  mov     ebx, 8007000Eh
0x18000f808  mov     [rsp+118h+var_E8], ebx
0x18000f80c  jmp     loc_18000FC45
0x18000f811  xor     edx, edx; int
0x18000f813  lea     rcx, [rsp+118h+var_E0]; struct IRegisteredTask **
0x18000f818  call    ?GetPolicyTask@@YAJPEAPEAUIRegisteredTask@@H@Z; GetPolicyTask(IRegisteredTask * *,int)
0x18000f81d  lea     rdx, [rsp+118h+var_D8]; struct CWorkspace **
0x18000f822  mov     rcx, rbx; this
0x18000f825  call    ?GetDefaultWorkspace@CWorkspaceManager@@QEAAJPEAPEAVCWorkspace@@@Z; CWorkspaceManager::GetDefaultWorkspace(CWorkspace * *)
0x18000f82a  mov     ebx, eax
0x18000f82c  mov     [rsp+118h+var_E8], eax
0x18000f830  mov     edi, 80000000h
0x18000f835  add     eax, edi
0x18000f837  test    edi, eax
0x18000f839  jnz     short loc_18000F888
0x18000f83b  cmp     ebx, 80070002h
0x18000f841  jz      short loc_18000F888
0x18000f843  mov     rax, cs:WPP_GLOBAL_Control
0x18000f84a  cmp     rax, r15
0x18000f84d  jz      short loc_18000F87F
0x18000f84f  test    byte ptr [rax+1Ch], 8
0x18000f853  jz      short loc_18000F87F
0x18000f855  cmp     byte ptr [rax+19h], 2
0x18000f859  jb      short loc_18000F87F
0x18000f85b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f860  mov     edx, 11h
0x18000f865  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000f869  mov     r9d, eax
0x18000f86c  mov     r8, r14
0x18000f86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f876  mov     rcx, [rcx+10h]
0x18000f87a  call    WPP_SF_Dd
0x18000f87f  mov     [rsp+118h+var_E8], ebx
0x18000f883  jmp     loc_18000FC45
0x18000f888  lea     rcx, [rsp+118h+var_60]
0x18000f890  call    ?ReadRADCPolicyDefaultWorkspaceURL@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadRADCPolicyDefaultWorkspaceURL(std::wstring &)
0x18000f895  mov     ebx, eax
0x18000f897  mov     [rsp+118h+var_E8], eax
0x18000f89b  add     eax, edi
0x18000f89d  test    edi, eax
0x18000f89f  jnz     short loc_18000F8EE
0x18000f8a1  cmp     ebx, 80070002h
0x18000f8a7  jz      short loc_18000F8EE
0x18000f8a9  mov     rax, cs:WPP_GLOBAL_Control
0x18000f8b0  cmp     rax, r15
0x18000f8b3  jz      short loc_18000F8E5
0x18000f8b5  test    byte ptr [rax+1Ch], 8
0x18000f8b9  jz      short loc_18000F8E5
0x18000f8bb  cmp     byte ptr [rax+19h], 2
0x18000f8bf  jb      short loc_18000F8E5
0x18000f8c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f8c6  mov     edx, 12h
0x18000f8cb  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000f8cf  mov     r9d, eax
0x18000f8d2  mov     r8, r14
0x18000f8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8dc  mov     rcx, [rcx+10h]
0x18000f8e0  call    WPP_SF_Dd
0x18000f8e5  mov     [rsp+118h+var_E8], ebx
0x18000f8e9  jmp     loc_18000FC45
0x18000f8ee  mov     rcx, [rsp+118h+var_D8]
0x18000f8f3  test    rcx, rcx
0x18000f8f6  jnz     short loc_18000F90B
0x18000f8f8  cmp     [rsp+118h+var_50], rsi
0x18000f900  jz      short loc_18000F93B
0x18000f902  test    rcx, rcx
0x18000f905  jz      loc_18000FA5D
0x18000f90b  add     rcx, 128h
0x18000f912  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f917  mov     rbx, rax
0x18000f91a  lea     rcx, [rsp+118h+var_60]
0x18000f922  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f927  mov     rcx, rax; String1
0x18000f92a  mov     rdx, rbx; String2
0x18000f92d  call    cs:__imp__wcsicmp
0x18000f933  test    eax, eax
0x18000f935  jnz     loc_18000FA5D
0x18000f93b  mov     rax, cs:WPP_GLOBAL_Control
0x18000f942  cmp     rax, r15
0x18000f945  jz      short loc_18000F97A
0x18000f947  test    byte ptr [rax+1Ch], 1
0x18000f94b  jz      short loc_18000F97A
0x18000f94d  cmp     byte ptr [rax+19h], 4
0x18000f951  jb      short loc_18000F97A
0x18000f953  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f958  mov     edx, 13h
0x18000f95d  mov     r9d, eax
0x18000f960  mov     r8, r14
0x18000f963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f96a  mov     rcx, [rcx+10h]
0x18000f96e  call    WPP_SF_D
0x18000f973  mov     rax, cs:WPP_GLOBAL_Control
0x18000f97a  mov     rbx, [rsp+118h+var_E0]
0x18000f97f  test    rbx, rbx
0x18000f982  jz      loc_18000FC2D
0x18000f988  cmp     rax, r15
0x18000f98b  jz      short loc_18000F9BE
0x18000f98d  test    byte ptr [rax+1Ch], 1
0x18000f991  jz      short loc_18000F9BE
0x18000f993  cmp     byte ptr [rax+19h], 4
0x18000f997  jb      short loc_18000F9BE
0x18000f999  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f99e  mov     edx, 14h
0x18000f9a3  mov     r9d, eax
0x18000f9a6  mov     r8, r14
0x18000f9a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9b0  mov     rcx, [rcx+10h]
0x18000f9b4  call    WPP_SF_D
0x18000f9b9  mov     rbx, [rsp+118h+var_E0]
0x18000f9be  mov     rax, [rbx]
0x18000f9c1  mov     rdi, [rax+58h]
0x18000f9c5  mov     eax, 0Bh
0x18000f9ca  mov     word ptr [rsp+118h+pvarSrc], ax
0x18000f9cf  mov     word ptr [rsp+118h+pvarSrc+8], si
0x18000f9d4  lea     rcx, [rsp+118h+pvarSrc]; pvarSrc
0x18000f9d9  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x18000f9de  movzx   edx, ax
0x18000f9e1  mov     rcx, rbx
0x18000f9e4  mov     rax, rdi
0x18000f9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ec  mov     ebx, eax
0x18000f9ee  mov     [rsp+118h+var_E8], eax
0x18000f9f2  lea     rcx, [rsp+118h+pvarSrc]; this
0x18000f9f7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f9fc  test    ebx, ebx
0x18000f9fe  jns     loc_18000FC2D
0x18000fa04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa0b  cmp     rcx, r15
0x18000fa0e  jz      loc_18000FC2D
0x18000fa14  test    byte ptr [rcx+1Ch], 8
0x18000fa18  jz      loc_18000FC2D
0x18000fa1e  cmp     byte ptr [rcx+19h], 2
0x18000fa22  jb      loc_18000FC2D
0x18000fa28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000fa2d  mov     edx, 15h
0x18000fa32  mov     dword ptr [rsp+118h+var_F0], ebx
0x18000fa36  lea     rcx, aFailedToDisabl; "Failed to disable the policy task"
0x18000fa3d  mov     [rsp+118h+var_F8], rcx
0x18000fa42  mov     r9d, eax
0x18000fa45  mov     r8, r14
0x18000fa48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa4f  mov     rcx, [rcx+10h]
0x18000fa53  call    WPP_SF_DsD
0x18000fa58  jmp     loc_18000FC2D
0x18000fa5d  mov     rbx, [rsp+118h+var_E0]
0x18000fa62  test    rbx, rbx
0x18000fa65  jz      loc_18000FB02
0x18000fa6b  mov     rax, [rbx]
0x18000fa6e  mov     rdi, [rax+58h]
0x18000fa72  mov     eax, 0Bh
0x18000fa77  mov     word ptr [rsp+118h+pvarg], ax
0x18000fa7c  or      eax, 0FFFFFFFFh
0x18000fa7f  mov     word ptr [rsp+118h+pvarg+8], ax
0x18000fa84  lea     rcx, [rsp+118h+pvarg]; pvarSrc
0x18000fa89  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x18000fa8e  movzx   edx, ax
0x18000fa91  mov     rcx, rbx
0x18000fa94  mov     rax, rdi
0x18000fa97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa9c  mov     ebx, eax
0x18000fa9e  mov     [rsp+118h+var_E8], eax
0x18000faa2  lea     rcx, [rsp+118h+pvarg]; this
0x18000faa7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000faac  test    ebx, ebx
0x18000faae  jns     loc_18000FB69
  ... truncated ...
```
