# CWdsDeviceControllerManager::RefreshSettings(void)

- ea: `0x180002268`
- end: `0x180002594`
- name: `?RefreshSettings@CWdsDeviceControllerManager@@AEAAKXZ`
- size: `812`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180001e14`
- `0x180007670`

## callees

- `0x180002268`
- `0x18000a5e8`
- `0x18000ad40`
- `0x18000b834`
- `0x18000d494`
- `0x18000d954`
- `0x180012f34`
- `0x180013314`
- `0x1800133ec`
- `0x180013600`
- `0x180013648`
- `0x180014d58`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002351`
- `KERNEL32!EnterCriticalSection` at `0x180002484`
- `KERNEL32!EnterCriticalSection` at `0x180002351`
- `KERNEL32!EnterCriticalSection` at `0x180002484`
- `KERNEL32!LeaveCriticalSection` at `0x18000236a`
- `KERNEL32!LeaveCriticalSection` at `0x1800024d9`
- `KERNEL32!LeaveCriticalSection` at `0x180002557`
- `KERNEL32!LeaveCriticalSection` at `0x18000236a`
- `KERNEL32!LeaveCriticalSection` at `0x1800024d9`
- `KERNEL32!LeaveCriticalSection` at `0x180002557`
- `KERNEL32!FreeLibrary` at `0x18000251f`
- `KERNEL32!FreeLibrary` at `0x18000251f`
- `ADVAPI32!RegCloseKey` at `0x180002379`
- `ADVAPI32!RegCloseKey` at `0x18000252e`
- `ADVAPI32!RegCloseKey` at `0x180002541`
- `ADVAPI32!RegCloseKey` at `0x180002379`
- `ADVAPI32!RegCloseKey` at `0x18000252e`
- `ADVAPI32!RegCloseKey` at `0x180002541`
- `ADVAPI32!RegOpenKeyExW` at `0x1800022e0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800023a3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800022e0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800023a3`

## string_xrefs

- `0x1800022ab`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x180002395`: `System\CurrentControlSet\Services\WDSServer\Providers\wdsdcmgr`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::RefreshSettings(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned __int16 *v1; // r15
  int v3; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r12
  HMODULE v5; // r14
  unsigned int Value; // ebx
  const char *v7; // rdx
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  _QWORD v16[2]; // [rsp+30h] [rbp-59h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v18[18]; // [rsp+50h] [rbp-39h] BYREF
  int v19; // [rsp+F0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+F8h] [rbp+6Fh] BYREF
  HKEY phkResult; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int16 *v22; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = 0;
  v19 = 0;
  phkResult = 0;
  hKey = 0;
  v22 = 0;
  v16[0] = 0;
  v3 = 0;
  v16[1] = 0;
  DebugInfo = 0;
  v18[0] = 0;
  v5 = 0;
  v18[1] = 0;
  v18[3] = 0;
  v18[4] = 0;
  v18[6] = 0;
  v18[7] = 0;
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
            0,
            0x20119u,
            &phkResult);
  if ( !ElValidateWin32(Value, v7, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x12Du) )
  {
    Value = CRegKey::GetValue((CRegKey *)&phkResult, L"ParseKnownDUIDs", 4u, &v19, 4u);
    if ( Value == 2 )
    {
      v19 = 1;
      Value = 0;
    }
    if ( !ElValidateWin32(Value, v8, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x133u) )
    {
      EnterCriticalSection(lpCriticalSection);
      lpCriticalSection[8].LockCount = v19 != 0;
      LeaveCriticalSection(lpCriticalSection);
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      Value = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\wdsdcmgr",
                0,
                0x20119u,
                &hKey);
      if ( !ElValidateWin32(Value, v9, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x13Eu) )
      {
        Value = CRegKey::GetValueSz((CRegKey *)&hKey, L"ManagementController", &v22);
        if ( Value == 2 )
          Value = 0;
        if ( ElValidateWin32(
               Value,
               v10,
               "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
               0x147u) )
        {
          v1 = v22;
        }
        else
        {
          CMRSWLock::WriterLock(lpCriticalSection + 1);
          DebugInfo = lpCriticalSection[8].DebugInfo;
          lpCriticalSection[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v22;
          CMRSWLock::WriterRelease((CMRSWLock *)&lpCriticalSection[1]);
          Value = CWdsMetadataStoreManagementClient::Initialize((CWdsMetadataStoreManagementClient *)v16);
          if ( ElValidateWin32(
                 Value,
                 v11,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x153u)
            || (v17 = (struct _GUID)xmmword_180018730,
                Value = CWdsMetadataStoreManagementClient::GetMetadata(
                          (CWdsMetadataStoreManagementClient *)v16,
                          &v17,
                          (struct CWdsMetadata *)v18),
                ElValidateWin32(
                  Value,
                  v12,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x15Cu))
            || (EnterCriticalSection(lpCriticalSection),
                v3 = 1,
                Value = CWdsMetadata::Clear((CWdsMetadata *)&lpCriticalSection[6].LockCount),
                ElValidateWin32(
                  Value,
                  v13,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x161u))
            || (Value = CWdsMetadata::AppendAll(
                          (CWdsMetadata *)&lpCriticalSection[6].LockCount,
                          (const struct CWdsMetadata *)v18),
                ElValidateWin32(
                  Value,
                  v14,
                  "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                  0x164u)) )
          {
            v5 = (HMODULE)v16[0];
LABEL_20:
            if ( DebugInfo )
              operator delete(DebugInfo);
            goto LABEL_22;
          }
          LeaveCriticalSection(lpCriticalSection);
          v5 = (HMODULE)v16[0];
        }
        v3 = 0;
        if ( v1 )
          operator delete(v1);
        goto LABEL_20;
      }
    }
  }
LABEL_22:
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v18);
  if ( v5 )
    FreeLibrary(v5);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v3 )
    LeaveCriticalSection(lpCriticalSection);
  return Value;
}

```

## disassembly

```asm
0x180002268  push    rbp
0x18000226a  push    rbx
0x18000226b  push    rsi
0x18000226c  push    rdi
0x18000226d  push    r12
0x18000226f  push    r13
0x180002271  push    r14
0x180002273  push    r15
0x180002275  lea     rbp, [rsp-1Fh]
0x18000227a  sub     rsp, 0A8h
0x180002281  xor     r15d, r15d
0x180002284  lea     rax, [rbp+57h+arg_10]
0x180002288  mov     rsi, rcx
0x18000228b  mov     [rbp+57h+arg_0], r15d
0x18000228f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002296  mov     [rbp+57h+arg_10], r15
0x18000229a  mov     r9d, 20119h; samDesired
0x1800022a0  mov     [rbp+57h+hKey], r15
0x1800022a4  xor     r8d, r8d; ulOptions
0x1800022a7  mov     [rbp+57h+arg_18], r15
0x1800022ab  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800022b2  mov     [rbp+57h+var_B0], r15
0x1800022b6  mov     edi, r15d
0x1800022b9  mov     [rbp+57h+var_A8], r15
0x1800022bd  mov     r12d, r15d
0x1800022c0  mov     [rbp+57h+var_90], r15
0x1800022c4  mov     r14d, r15d
0x1800022c7  mov     [rbp+57h+var_88], r15
0x1800022cb  mov     [rbp+57h+var_78], r15
0x1800022cf  mov     [rbp+57h+var_70], r15
0x1800022d3  mov     [rbp+57h+var_60], r15
0x1800022d7  mov     [rbp+57h+var_58], r15
0x1800022db  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800022e0  call    cs:__imp_RegOpenKeyExW
0x1800022e6  mov     r9d, 12Dh; unsigned int
0x1800022ec  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800022f3  mov     ecx, eax; unsigned int
0x1800022f5  mov     ebx, eax
0x1800022f7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800022fc  test    eax, eax
0x1800022fe  jnz     loc_18000250E
0x180002304  lea     r8d, [r15+4]; unsigned int
0x180002308  lea     r9, [rbp+57h+arg_0]; void *
0x18000230c  mov     dword ptr [rsp+0E0h+phkResult], r8d; unsigned int
0x180002311  lea     rdx, aParseknownduid; "ParseKnownDUIDs"
0x180002318  lea     rcx, [rbp+57h+arg_10]; this
0x18000231c  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180002321  mov     ebx, eax
0x180002323  cmp     eax, 2
0x180002326  jnz     short loc_180002332
0x180002328  mov     [rbp+57h+arg_0], 1
0x18000232f  mov     ebx, r15d
0x180002332  mov     r9d, 133h; unsigned int
0x180002338  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000233f  mov     ecx, ebx; unsigned int
0x180002341  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002346  test    eax, eax
0x180002348  jnz     loc_18000250E
0x18000234e  mov     rcx, rsi; lpCriticalSection
0x180002351  call    cs:__imp_EnterCriticalSection
0x180002357  cmp     [rbp+57h+arg_0], r15d
0x18000235b  mov     eax, r15d
0x18000235e  mov     rcx, rsi; lpCriticalSection
0x180002361  setnz   al
0x180002364  mov     [rsi+148h], eax
0x18000236a  call    cs:__imp_LeaveCriticalSection
0x180002370  mov     rcx, [rbp+57h+hKey]; hKey
0x180002374  test    rcx, rcx
0x180002377  jz      short loc_180002383
0x180002379  call    cs:__imp_RegCloseKey
0x18000237f  mov     [rbp+57h+hKey], r15
0x180002383  lea     rax, [rbp+57h+hKey]
0x180002387  mov     r9d, 20119h; samDesired
0x18000238d  xor     r8d, r8d; ulOptions
0x180002390  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180002395  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x18000239c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800023a3  call    cs:__imp_RegOpenKeyExW
0x1800023a9  mov     r9d, 13Eh; unsigned int
0x1800023af  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800023b6  mov     ecx, eax; unsigned int
0x1800023b8  mov     ebx, eax
0x1800023ba  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800023bf  test    eax, eax
0x1800023c1  jnz     loc_18000250E
0x1800023c7  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x1800023cb  lea     rdx, aManagementcont; "ManagementController"
0x1800023d2  lea     rcx, [rbp+57h+hKey]; this
0x1800023d6  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x1800023db  cmp     eax, 2
0x1800023de  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800023e5  mov     ebx, eax
0x1800023e7  mov     r9d, 147h; unsigned int
0x1800023ed  cmovz   ebx, r15d
0x1800023f1  mov     ecx, ebx; unsigned int
0x1800023f3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800023f8  test    eax, eax
0x1800023fa  jnz     loc_1800024EB
0x180002400  lea     rcx, [rsi+28h]; lpCriticalSection
0x180002404  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x180002409  mov     rax, [rbp+57h+arg_18]
0x18000240d  lea     rcx, [rsi+28h]; this
0x180002411  mov     r12, [rsi+140h]
0x180002418  mov     [rsi+140h], rax
0x18000241f  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180002424  lea     rcx, [rbp+57h+var_B0]; this
0x180002428  call    ?Initialize@CWdsMetadataStoreManagementClient@@QEAAKXZ; CWdsMetadataStoreManagementClient::Initialize(void)
0x18000242d  lea     r13, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180002434  mov     r9d, 153h; unsigned int
0x18000243a  mov     r8, r13; char *
0x18000243d  mov     ecx, eax; unsigned int
0x18000243f  mov     ebx, eax
0x180002441  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002446  test    eax, eax
0x180002448  jnz     loc_1800024E5
0x18000244e  movups  xmm0, cs:xmmword_180018730
0x180002455  lea     r8, [rbp+57h+var_90]; struct CWdsMetadata *
0x180002459  lea     rdx, [rbp+57h+var_A0]; struct _GUID
0x18000245d  lea     rcx, [rbp+57h+var_B0]; this
0x180002461  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180002466  call    ?GetMetadata@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEAVCWdsMetadata@@@Z; CWdsMetadataStoreManagementClient::GetMetadata(_GUID,CWdsMetadata *)
0x18000246b  mov     r9d, 15Ch; unsigned int
0x180002471  mov     r8, r13; char *
0x180002474  mov     ecx, eax; unsigned int
0x180002476  mov     ebx, eax
0x180002478  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000247d  test    eax, eax
0x18000247f  jnz     short loc_1800024E5
0x180002481  mov     rcx, rsi; lpCriticalSection
0x180002484  call    cs:__imp_EnterCriticalSection
0x18000248a  lea     r14, [rsi+0F8h]
0x180002491  mov     edi, 1
0x180002496  mov     rcx, r14; this
0x180002499  call    ?Clear@CWdsMetadata@@QEAAKXZ; CWdsMetadata::Clear(void)
0x18000249e  mov     r9d, 161h; unsigned int
0x1800024a4  mov     r8, r13; char *
0x1800024a7  mov     ecx, eax; unsigned int
0x1800024a9  mov     ebx, eax
0x1800024ab  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800024b0  test    eax, eax
0x1800024b2  jnz     short loc_1800024E5
0x1800024b4  lea     rdx, [rbp+57h+var_90]; struct CWdsMetadata *
0x1800024b8  mov     rcx, r14; this
0x1800024bb  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x1800024c0  mov     r9d, 164h; unsigned int
0x1800024c6  mov     r8, r13; char *
0x1800024c9  mov     ecx, eax; unsigned int
0x1800024cb  mov     ebx, eax
0x1800024cd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800024d2  test    eax, eax
0x1800024d4  jnz     short loc_1800024E5
0x1800024d6  mov     rcx, rsi; lpCriticalSection
0x1800024d9  call    cs:__imp_LeaveCriticalSection
0x1800024df  mov     r14, [rbp+57h+var_B0]
0x1800024e3  jmp     short loc_1800024EF
0x1800024e5  mov     r14, [rbp+57h+var_B0]
0x1800024e9  jmp     short loc_180002501
0x1800024eb  mov     r15, [rbp+57h+arg_18]
0x1800024ef  xor     edi, edi
0x1800024f1  test    r15, r15
0x1800024f4  jz      short loc_1800024FE
0x1800024f6  mov     rcx, r15; Block
0x1800024f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024fe  xor     r15d, r15d
0x180002501  test    r12, r12
0x180002504  jz      short loc_18000250E
0x180002506  mov     rcx, r12; Block
0x180002509  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000250e  lea     rcx, [rbp+57h+var_90]; this
0x180002512  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180002517  test    r14, r14
0x18000251a  jz      short loc_180002525
0x18000251c  mov     rcx, r14; hLibModule
0x18000251f  call    cs:__imp_FreeLibrary
0x180002525  mov     rcx, [rbp+57h+hKey]; hKey
0x180002529  test    rcx, rcx
0x18000252c  jz      short loc_180002538
0x18000252e  call    cs:__imp_RegCloseKey
0x180002534  mov     [rbp+57h+hKey], r15
0x180002538  mov     rcx, [rbp+57h+arg_10]; hKey
0x18000253c  test    rcx, rcx
0x18000253f  jz      short loc_18000254B
0x180002541  call    cs:__imp_RegCloseKey
0x180002547  mov     [rbp+57h+arg_10], r15
0x18000254b  test    edi, edi
0x18000254d  jz      short loc_18000257E
0x18000254f  add     edi, 0FFFFFFFFh
0x180002552  jnz     short loc_18000255D
0x180002554  mov     rcx, rsi; lpCriticalSection
0x180002557  call    cs:__imp_LeaveCriticalSection
0x18000255d  test    edi, edi
0x18000255f  jz      short loc_18000257E
0x180002561  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180002568  mov     dword ptr [rsp+0E0h+phkResult], r15d; int
0x18000256d  mov     edx, 16Ah; unsigned int
0x180002572  lea     rcx, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x180002579  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000257e  mov     eax, ebx
0x180002580  add     rsp, 0A8h
0x180002587  pop     r15
0x180002589  pop     r14
0x18000258b  pop     r13
0x18000258d  pop     r12
0x18000258f  pop     rdi
0x180002590  pop     rsi
0x180002591  pop     rbx
0x180002592  pop     rbp
0x180002593  retn
```
