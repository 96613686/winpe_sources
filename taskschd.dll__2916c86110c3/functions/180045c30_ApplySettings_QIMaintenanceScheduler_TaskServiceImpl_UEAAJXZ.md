# ?ApplySettings@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x180045c30`
- end: `0x180046074`
- name: `?ApplySettings@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `1092`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180021240`
- `0x180024460`
- `0x1800394b4`
- `0x18003a264`
- `0x180045c30`
- `0x180047458`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045fa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045fa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c91`
- `ntdll!WinSqmAddToStream` at `0x180045f8d`
- `ntdll!WinSqmAddToStream` at `0x180045f8d`
- `ntdll!WinSqmIsOptedIn` at `0x180045ea3`
- `ntdll!WinSqmIsOptedIn` at `0x180045ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004603f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004603f`
- `OLEAUT32!__imp_SysFreeString` at `0x180045f97`
- `OLEAUT32!__imp_SysFreeString` at `0x180045f97`
- `OLEAUT32!__imp_SysStringLen` at `0x180045f14`
- `OLEAUT32!__imp_SysStringLen` at `0x180045f14`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180045d7e`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180045fe8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180045d7e`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180045fe8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180045e22`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180046017`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180045e22`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180046017`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180045ce2`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180045ce2`
- `POWRPROF!PowerReadACValueIndex` at `0x180045d2f`
- `POWRPROF!PowerReadACValueIndex` at `0x180045d2f`
- `POWRPROF!PowerReadDCValueIndex` at `0x180045dd3`
- `POWRPROF!PowerReadDCValueIndex` at `0x180045dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall _ApplySettings__QIMaintenanceScheduler__TaskServiceImpl__UEAAJXZ(__int64 a1)
{
  signed int v2; // edi
  BOOL v3; // r13d
  BOOL v4; // r12d
  struct _RTL_CRITICAL_SECTION *v5; // r15
  TaskServiceImpl *v6; // rcx
  unsigned __int16 *v7; // r8
  struct TaskServiceImpl::_MAINTENANCE_POLICY *v8; // rax
  signed int ActiveScheme; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  bool v14; // dl
  __int64 v15; // r8
  unsigned __int16 *v16; // rbx
  __int64 v17; // rdx
  UINT v18; // eax
  struct _SYSTEMTIME *v19; // rax
  int v20; // ecx
  char v22; // [rsp+30h] [rbp-B8h]
  GUID *ActivePolicyGuid; // [rsp+38h] [rbp-B0h] BYREF
  DWORD AcValueIndex; // [rsp+40h] [rbp-A8h] BYREF
  DWORD DcValueIndex; // [rsp+44h] [rbp-A4h] BYREF
  int v26; // [rsp+48h] [rbp-A0h]
  int v27; // [rsp+4Ch] [rbp-9Ch]
  BOOL v28; // [rsp+50h] [rbp-98h]
  BSTR pbstr; // [rsp+58h] [rbp-90h] BYREF
  _BYTE *v30; // [rsp+60h] [rbp-88h]
  int v31; // [rsp+68h] [rbp-80h] BYREF
  __int128 v32; // [rsp+70h] [rbp-78h]
  _BOOL8 v33; // [rsp+80h] [rbp-68h]
  _BYTE v34[16]; // [rsp+88h] [rbp-60h] BYREF
  __int64 v35; // [rsp+98h] [rbp-50h]
  struct _SYSTEMTIME v36; // [rsp+A0h] [rbp-48h] BYREF

  v2 = 0;
  ActivePolicyGuid = 0;
  AcValueIndex = 0;
  DcValueIndex = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v27 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 248);
  v35 = a1 + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  v30 = (_BYTE *)(a1 + 218);
  v22 = *(_BYTE *)(a1 + 218);
  if ( *(_BYTE *)(a1 + 217) != 1 )
    goto LABEL_40;
  v8 = (struct TaskServiceImpl::_MAINTENANCE_POLICY *)(a1 + 144);
  if ( *(_WORD *)(a1 + 192) == 11 && *(_WORD *)(a1 + 200) == 0xFFFF )
  {
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
    v2 = ActiveScheme;
    if ( ActiveScheme )
    {
      if ( ActiveScheme > 0 )
        v2 = (unsigned __int16)ActiveScheme | 0x80070000;
      goto LABEL_40;
    }
    v10 = PowerReadACValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, &AcValueIndex);
    v2 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_40;
    }
    if ( AcValueIndex != 1 )
    {
      v11 = PowerWriteACValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, 1u);
      v2 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v2 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_40;
      }
      v3 = 1;
      v26 = 1;
    }
    v12 = PowerReadDCValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, &DcValueIndex);
    v2 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v2 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_40;
    }
    if ( DcValueIndex != 1 )
    {
      v13 = PowerWriteDCValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, 1u);
      v2 = v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v2 = (unsigned __int16)v13 | 0x80070000;
        goto LABEL_40;
      }
      v4 = 1;
      v27 = 1;
    }
    *(_BYTE *)(a1 + 218) = 1;
    v8 = (struct TaskServiceImpl::_MAINTENANCE_POLICY *)(a1 + 144);
  }
  v2 = 0;
  if ( *(_BYTE *)(a1 + 217) == 1 && (v2 = TaskServiceImpl::StoreMaintenanceLaunchPolicy(v6, v8, v7), v2 >= 0) )
  {
    *(_BYTE *)(a1 + 217) = 1;
  }
  else if ( v2 < 0 )
  {
    goto LABEL_40;
  }
  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    TSTime::TSTime((TSTime *)v34, v14);
    v16 = 0;
    pbstr = 0;
    if ( *(_WORD *)(a1 + 144) == 8 )
    {
      v17 = *(_QWORD *)(a1 + 152);
      if ( v17 )
      {
        if ( *(_WORD *)(a1 + 192) == 11 )
        {
          ATL::CComBSTR::operator=(&pbstr, v17, v15);
          v28 = *(_WORD *)(a1 + 200) == 0xFFFF;
          v16 = pbstr;
          v18 = SysStringLen(pbstr);
          if ( (int)TSParser::ParseDateTime(v16, v18, (struct TSTime *)v34) >= 0 )
          {
            v19 = TSTime::ToSYSTEMTIME((TSTime *)v34, &v36);
            v20 = v19->wMinute + 60 * v19->wHour;
            v32 = 0;
            LODWORD(v32) = v20;
            v31 = 1;
            v33 = v28;
            DWORD2(v32) = 1;
            WinSqmAddToStream(0, 8082, 2, &v31);
          }
        }
      }
    }
    SysFreeString(v16);
  }
LABEL_40:
  LeaveCriticalSection(v5);
  if ( v2 < 0 )
  {
    if ( v3 )
      v3 = PowerWriteACValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, AcValueIndex) != 0;
    if ( v4 )
      v4 = PowerWriteDCValueIndex(0, ActivePolicyGuid, &GUID_SLEEP_SUBGROUP, &GUID_ALLOW_RTC_WAKE, DcValueIndex) != 0;
    if ( !v3 || !v4 )
      *v30 = v22;
  }
  if ( ActivePolicyGuid )
    LocalFree(ActivePolicyGuid);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180045c30  mov     r11, rsp
0x180045c33  mov     [r11+10h], rbx
0x180045c37  mov     [r11+18h], rsi
0x180045c3b  push    rdi
0x180045c3c  push    r12
0x180045c3e  push    r13
0x180045c40  push    r14
0x180045c42  push    r15
0x180045c44  sub     rsp, 0C0h
0x180045c4b  mov     rax, cs:__security_cookie
0x180045c52  xor     rax, rsp
0x180045c55  mov     [rsp+0E8h+var_38], rax
0x180045c5d  mov     rsi, rcx
0x180045c60  xor     edi, edi
0x180045c62  mov     [rsp+0E8h+var_B4], edi
0x180045c66  mov     [rsp+0E8h+ActivePolicyGuid], rdi
0x180045c6b  mov     [rsp+0E8h+var_A8], edi
0x180045c6f  mov     [rsp+0E8h+DcValueIndex], edi
0x180045c73  xor     r13d, r13d
0x180045c76  mov     [rsp+0E8h+var_A0], r13d
0x180045c7b  xor     r12d, r12d
0x180045c7e  mov     [rsp+0E8h+var_9C], r12d
0x180045c83  lea     r15, [rcx+0F8h]
0x180045c8a  mov     [r11-50h], r15
0x180045c8e  mov     rcx, r15; lpCriticalSection
0x180045c91  call    cs:__imp_EnterCriticalSection
0x180045c97  nop
0x180045c98  lea     rbx, [rsi+0DAh]
0x180045c9f  mov     [rsp+0E8h+var_88], rbx
0x180045ca4  mov     al, [rbx]
0x180045ca6  mov     [rsp+0E8h+var_B8], al
0x180045caa  lea     r14d, [rdi+1]
0x180045cae  cmp     [rsi+0D9h], r14b
0x180045cb5  jnz     loc_180045F9E
0x180045cbb  lea     rax, [rsi+90h]
0x180045cc2  cmp     word ptr [rax+30h], 0Bh
0x180045cc7  jnz     loc_180045E62
0x180045ccd  cmp     word ptr [rsi+0C8h], 0FFFFh
0x180045cd5  jnz     loc_180045E62
0x180045cdb  lea     rdx, [rsp+0E8h+ActivePolicyGuid]; ActivePolicyGuid
0x180045ce0  xor     ecx, ecx; UserRootPowerKey
0x180045ce2  call    cs:__imp_PowerGetActiveScheme
0x180045ce8  mov     edi, eax
0x180045cea  test    eax, eax
0x180045cec  jz      short loc_180045D10
0x180045cee  jle     short loc_180045CF9
0x180045cf0  movzx   edi, ax
0x180045cf3  or      edi, 80070000h
0x180045cf9  mov     [rsp+0E8h+var_B4], edi
0x180045cfd  mov     rcx, r15; lpCriticalSection
0x180045d00  call    cs:__imp_LeaveCriticalSection
0x180045d06  nop
0x180045d07  mov     bl, [rsp+0E8h+var_B8]
0x180045d0b  jmp     loc_180045FC2
0x180045d10  lea     rax, [rsp+0E8h+var_A8]
0x180045d15  mov     [rsp+0E8h+AcValueIndex], rax; AcValueIndex
0x180045d1a  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180045d21  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180045d28  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180045d2d  xor     ecx, ecx; RootPowerKey
0x180045d2f  call    cs:__imp_PowerReadACValueIndex
0x180045d35  mov     edi, eax
0x180045d37  test    eax, eax
0x180045d39  jz      short loc_180045D5D
0x180045d3b  jle     short loc_180045D46
0x180045d3d  movzx   edi, ax
0x180045d40  or      edi, 80070000h
0x180045d46  mov     [rsp+0E8h+var_B4], edi
0x180045d4a  mov     rcx, r15; lpCriticalSection
0x180045d4d  call    cs:__imp_LeaveCriticalSection
0x180045d53  nop
0x180045d54  mov     bl, [rsp+0E8h+var_B8]
0x180045d58  jmp     loc_180045FC2
0x180045d5d  cmp     [rsp+0E8h+var_A8], r14d
0x180045d62  jz      short loc_180045DB4
0x180045d64  mov     dword ptr [rsp+0E8h+AcValueIndex], r14d; AcValueIndex
0x180045d69  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180045d70  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180045d77  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180045d7c  xor     ecx, ecx; RootPowerKey
0x180045d7e  call    cs:__imp_PowerWriteACValueIndex
0x180045d84  mov     edi, eax
0x180045d86  test    eax, eax
0x180045d88  jz      short loc_180045DAC
0x180045d8a  jle     short loc_180045D95
0x180045d8c  movzx   edi, ax
0x180045d8f  or      edi, 80070000h
0x180045d95  mov     [rsp+0E8h+var_B4], edi
0x180045d99  mov     rcx, r15; lpCriticalSection
0x180045d9c  call    cs:__imp_LeaveCriticalSection
0x180045da2  nop
0x180045da3  mov     bl, [rsp+0E8h+var_B8]
0x180045da7  jmp     loc_180045FC2
0x180045dac  mov     r13d, r14d
0x180045daf  mov     [rsp+0E8h+var_A0], r14d
0x180045db4  lea     rax, [rsp+0E8h+DcValueIndex]
0x180045db9  mov     [rsp+0E8h+AcValueIndex], rax; DcValueIndex
0x180045dbe  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180045dc5  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180045dcc  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180045dd1  xor     ecx, ecx; RootPowerKey
0x180045dd3  call    cs:__imp_PowerReadDCValueIndex
0x180045dd9  mov     edi, eax
0x180045ddb  test    eax, eax
0x180045ddd  jz      short loc_180045E01
0x180045ddf  jle     short loc_180045DEA
0x180045de1  movzx   edi, ax
0x180045de4  or      edi, 80070000h
0x180045dea  mov     [rsp+0E8h+var_B4], edi
0x180045dee  mov     rcx, r15; lpCriticalSection
0x180045df1  call    cs:__imp_LeaveCriticalSection
0x180045df7  nop
0x180045df8  mov     bl, [rsp+0E8h+var_B8]
0x180045dfc  jmp     loc_180045FC2
0x180045e01  cmp     [rsp+0E8h+DcValueIndex], r14d
0x180045e06  jz      short loc_180045E58
0x180045e08  mov     dword ptr [rsp+0E8h+AcValueIndex], r14d; DcValueIndex
0x180045e0d  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180045e14  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180045e1b  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180045e20  xor     ecx, ecx; RootPowerKey
0x180045e22  call    cs:__imp_PowerWriteDCValueIndex
0x180045e28  mov     edi, eax
0x180045e2a  test    eax, eax
0x180045e2c  jz      short loc_180045E50
0x180045e2e  jle     short loc_180045E39
0x180045e30  movzx   edi, ax
0x180045e33  or      edi, 80070000h
0x180045e39  mov     [rsp+0E8h+var_B4], edi
0x180045e3d  mov     rcx, r15; lpCriticalSection
0x180045e40  call    cs:__imp_LeaveCriticalSection
0x180045e46  nop
0x180045e47  mov     bl, [rsp+0E8h+var_B8]
0x180045e4b  jmp     loc_180045FC2
0x180045e50  mov     r12d, r14d
0x180045e53  mov     [rsp+0E8h+var_9C], r14d
0x180045e58  mov     [rbx], r14b
0x180045e5b  lea     rax, [rsi+90h]
0x180045e62  xor     edi, edi
0x180045e64  cmp     [rsi+0D9h], r14b
0x180045e6b  jnz     short loc_180045E88
0x180045e6d  mov     rdx, rax; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x180045e70  call    ?StoreMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::StoreMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x180045e75  mov     edi, eax
0x180045e77  test    eax, eax
0x180045e79  js      short loc_180045E88
0x180045e7b  mov     [rsi+0D9h], r14b
0x180045e82  mov     [rsp+0E8h+var_B4], eax
0x180045e86  jmp     short loc_180045EA3
0x180045e88  mov     [rsp+0E8h+var_B4], edi
0x180045e8c  test    edi, edi
0x180045e8e  jns     short loc_180045EA3
0x180045e90  mov     rcx, r15; lpCriticalSection
0x180045e93  call    cs:__imp_LeaveCriticalSection
0x180045e99  nop
0x180045e9a  mov     bl, [rsp+0E8h+var_B8]
0x180045e9e  jmp     loc_180045FC2
0x180045ea3  call    cs:__imp_WinSqmIsOptedIn
0x180045ea9  test    eax, eax
0x180045eab  jz      loc_180045F9E
0x180045eb1  lea     rcx, [rsp+0E8h+var_60]; this
0x180045eb9  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x180045ebe  xor     ebx, ebx
0x180045ec0  mov     [rsp+0E8h+pbstr], rbx
0x180045ec5  cmp     word ptr [rsi+90h], 8
0x180045ecd  jnz     loc_180045F94
0x180045ed3  mov     rdx, [rsi+98h]
0x180045eda  test    rdx, rdx
0x180045edd  jz      loc_180045F94
0x180045ee3  cmp     word ptr [rsi+0C0h], 0Bh
0x180045eeb  jnz     loc_180045F94
0x180045ef1  lea     rcx, [rsp+0E8h+pbstr]
0x180045ef6  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180045efb  xor     eax, eax
0x180045efd  cmp     word ptr [rsi+0C8h], 0FFFFh
0x180045f05  setz    al
0x180045f08  mov     [rsp+0E8h+var_98], eax
0x180045f0c  mov     rbx, [rsp+0E8h+pbstr]
0x180045f11  mov     rcx, rbx; pbstr
0x180045f14  call    cs:__imp_SysStringLen
0x180045f1a  mov     edx, eax; unsigned __int64
0x180045f1c  lea     r8, [rsp+0E8h+var_60]; struct TSTime *
0x180045f24  mov     rcx, rbx; unsigned __int16 *
0x180045f27  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x180045f2c  test    eax, eax
0x180045f2e  js      short loc_180045F94
0x180045f30  lea     rdx, [rsp+0E8h+var_48]; retstr
0x180045f38  lea     rcx, [rsp+0E8h+var_60]; this
0x180045f40  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180045f45  movzx   ecx, word ptr [rax+8]
0x180045f49  imul    ecx, 3Ch ; '<'
0x180045f4c  movzx   eax, word ptr [rax+0Ah]
0x180045f50  add     ecx, eax
0x180045f52  xorps   xmm0, xmm0
0x180045f55  xor     eax, eax
0x180045f57  movups  [rsp+0E8h+var_78], xmm0
0x180045f5c  mov     [rsp+0E8h+var_68], rax
0x180045f64  mov     dword ptr [rsp+0E8h+var_78], ecx
0x180045f68  mov     [rsp+0E8h+var_80], r14d
0x180045f6d  mov     eax, [rsp+0E8h+var_98]
0x180045f71  mov     dword ptr [rsp+0E8h+var_68], eax
0x180045f78  mov     dword ptr [rsp+0E8h+var_78+8], r14d
0x180045f7d  lea     r9, [rsp+0E8h+var_80]
0x180045f82  mov     edx, 1F92h
0x180045f87  xor     ecx, ecx
0x180045f89  lea     r8d, [rcx+2]
0x180045f8d  call    cs:__imp_WinSqmAddToStream
0x180045f93  nop
0x180045f94  mov     rcx, rbx; bstrString
0x180045f97  call    cs:__imp_SysFreeString
0x180045f9d  nop
0x180045f9e  mov     rcx, r15; lpCriticalSection
0x180045fa1  call    cs:__imp_LeaveCriticalSection
0x180045fa7  nop
0x180045fa8  jmp     short loc_180045FBE
0x180045faa  mov     r14d, 1
0x180045fb0  mov     edi, [rsp+0E8h+var_B4]
0x180045fb4  mov     r13d, [rsp+0E8h+var_A0]
0x180045fb9  mov     r12d, [rsp+0E8h+var_9C]
0x180045fbe  mov     bl, [rsp+0E8h+var_B8]
0x180045fc2  test    edi, edi
0x180045fc4  jns     short loc_180046035
0x180045fc6  cmp     r13d, r14d
0x180045fc9  jnz     short loc_180045FF5
0x180045fcb  mov     eax, [rsp+0E8h+var_A8]
0x180045fcf  mov     dword ptr [rsp+0E8h+AcValueIndex], eax; AcValueIndex
0x180045fd3  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180045fda  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180045fe1  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180045fe6  xor     ecx, ecx; RootPowerKey
0x180045fe8  call    cs:__imp_PowerWriteACValueIndex
0x180045fee  neg     eax
0x180045ff0  sbb     ecx, ecx
0x180045ff2  and     r13d, ecx
0x180045ff5  cmp     r12d, r14d
0x180045ff8  jnz     short loc_180046024
0x180045ffa  mov     eax, [rsp+0E8h+DcValueIndex]
0x180045ffe  mov     dword ptr [rsp+0E8h+AcValueIndex], eax; DcValueIndex
0x180046002  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180046009  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180046010  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180046015  xor     ecx, ecx; RootPowerKey
0x180046017  call    cs:__imp_PowerWriteDCValueIndex
0x18004601d  neg     eax
0x18004601f  sbb     ecx, ecx
0x180046021  and     r12d, ecx
0x180046024  test    r13d, r13d
0x180046027  jz      short loc_18004602E
0x180046029  test    r12d, r12d
0x18004602c  jnz     short loc_180046035
0x18004602e  mov     rax, [rsp+0E8h+var_88]
0x180046033  mov     [rax], bl
0x180046035  mov     rcx, [rsp+0E8h+ActivePolicyGuid]; hMem
0x18004603a  test    rcx, rcx
0x18004603d  jz      short loc_180046045
0x18004603f  call    cs:__imp_LocalFree
0x180046045  mov     eax, edi
0x180046047  mov     rcx, [rsp+0E8h+var_38]
0x18004604f  xor     rcx, rsp; StackCookie
0x180046052  call    __security_check_cookie
0x180046057  lea     r11, [rsp+0E8h+var_28]
0x18004605f  mov     rbx, [r11+38h]
0x180046063  mov     rsi, [r11+40h]
0x180046067  mov     rsp, r11
0x18004606a  pop     r15
0x18004606c  pop     r14
0x18004606e  pop     r13
0x180046070  pop     r12
0x180046072  pop     rdi
0x180046073  retn
```
