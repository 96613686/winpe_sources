# ?ApplySettings@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x1800493b0`
- end: `0x18004986d`
- name: `?ApplySettings@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `1213`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180022c60`
- `0x180026120`
- `0x18003c5c0`
- `0x18003d728`
- `0x1800493b0`
- `0x18004ae50`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004948c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800494e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049655`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049781`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004948c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800494e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049655`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049781`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049411`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049411`
- `ntdll!WinSqmAddToStream` at `0x180049761`
- `ntdll!WinSqmAddToStream` at `0x180049761`
- `ntdll!WinSqmIsOptedIn` at `0x18004966b`
- `ntdll!WinSqmIsOptedIn` at `0x18004966b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049831`
- `OLEAUT32!__imp_SysFreeString` at `0x180049771`
- `OLEAUT32!__imp_SysFreeString` at `0x180049771`
- `OLEAUT32!__imp_SysStringLen` at `0x1800496e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1800496e2`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18004951c`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1800497ce`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18004951c`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1800497ce`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800495d8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180049803`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800495d8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180049803`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180049468`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180049468`
- `POWRPROF!PowerReadACValueIndex` at `0x1800494c1`
- `POWRPROF!PowerReadACValueIndex` at `0x1800494c1`
- `POWRPROF!PowerReadDCValueIndex` at `0x18004957d`
- `POWRPROF!PowerReadDCValueIndex` at `0x18004957d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
  unsigned __int16 *v15; // rbx
  UINT v16; // eax
  struct _SYSTEMTIME *v17; // rax
  int v18; // ecx
  char v20; // [rsp+30h] [rbp-B8h]
  GUID *ActivePolicyGuid; // [rsp+38h] [rbp-B0h] BYREF
  DWORD AcValueIndex; // [rsp+40h] [rbp-A8h] BYREF
  DWORD DcValueIndex; // [rsp+44h] [rbp-A4h] BYREF
  int v24; // [rsp+48h] [rbp-A0h]
  int v25; // [rsp+4Ch] [rbp-9Ch]
  BOOL v26; // [rsp+50h] [rbp-98h]
  BSTR pbstr; // [rsp+58h] [rbp-90h] BYREF
  _BYTE *v28; // [rsp+60h] [rbp-88h]
  int v29; // [rsp+68h] [rbp-80h] BYREF
  __int128 v30; // [rsp+70h] [rbp-78h]
  _BOOL8 v31; // [rsp+80h] [rbp-68h]
  _BYTE v32[16]; // [rsp+88h] [rbp-60h] BYREF
  __int64 v33; // [rsp+98h] [rbp-50h]
  struct _SYSTEMTIME v34; // [rsp+A0h] [rbp-48h] BYREF

  v2 = 0;
  ActivePolicyGuid = 0;
  AcValueIndex = 0;
  DcValueIndex = 0;
  v3 = 0;
  v24 = 0;
  v4 = 0;
  v25 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 248);
  v33 = a1 + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  v28 = (_BYTE *)(a1 + 218);
  v20 = *(_BYTE *)(a1 + 218);
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
      v24 = 1;
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
      v25 = 1;
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
    TSTime::TSTime((TSTime *)v32, v14);
    v15 = 0;
    pbstr = 0;
    if ( *(_WORD *)(a1 + 144) == 8 )
    {
      if ( *(_QWORD *)(a1 + 152) )
      {
        if ( *(_WORD *)(a1 + 192) == 11 )
        {
          ATL::CComBSTR::operator=(&pbstr);
          v26 = *(_WORD *)(a1 + 200) == 0xFFFF;
          v15 = pbstr;
          v16 = SysStringLen(pbstr);
          if ( (int)TSParser::ParseDateTime(v15, v16, (struct TSTime *)v32) >= 0 )
          {
            v17 = TSTime::ToSYSTEMTIME((TSTime *)v32, &v34);
            v18 = v17->wMinute + 60 * v17->wHour;
            v30 = 0;
            LODWORD(v30) = v18;
            v29 = 1;
            v31 = v26;
            DWORD2(v30) = 1;
            WinSqmAddToStream(0, 8082, 2, &v29);
          }
        }
      }
    }
    SysFreeString(v15);
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
      *v28 = v20;
  }
  if ( ActivePolicyGuid )
    LocalFree(ActivePolicyGuid);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800493b0  mov     r11, rsp
0x1800493b3  mov     [r11+10h], rbx
0x1800493b7  mov     [r11+18h], rsi
0x1800493bb  push    rdi
0x1800493bc  push    r12
0x1800493be  push    r13
0x1800493c0  push    r14
0x1800493c2  push    r15
0x1800493c4  sub     rsp, 0C0h
0x1800493cb  mov     rax, cs:__security_cookie
0x1800493d2  xor     rax, rsp
0x1800493d5  mov     [rsp+0E8h+var_38], rax
0x1800493dd  mov     rsi, rcx
0x1800493e0  xor     edi, edi
0x1800493e2  mov     [rsp+0E8h+var_B4], edi
0x1800493e6  mov     [rsp+0E8h+ActivePolicyGuid], rdi
0x1800493eb  mov     [rsp+0E8h+var_A8], edi
0x1800493ef  mov     [rsp+0E8h+DcValueIndex], edi
0x1800493f3  xor     r13d, r13d
0x1800493f6  mov     [rsp+0E8h+var_A0], r13d
0x1800493fb  xor     r12d, r12d
0x1800493fe  mov     [rsp+0E8h+var_9C], r12d
0x180049403  lea     r15, [rcx+0F8h]
0x18004940a  mov     [r11-50h], r15
0x18004940e  mov     rcx, r15; lpCriticalSection
0x180049411  call    cs:__imp_EnterCriticalSection
0x180049418  nop     dword ptr [rax+rax+00h]
0x18004941d  nop
0x18004941e  lea     rbx, [rsi+0DAh]
0x180049425  mov     [rsp+0E8h+var_88], rbx
0x18004942a  mov     al, [rbx]
0x18004942c  mov     [rsp+0E8h+var_B8], al
0x180049430  lea     r14d, [rdi+1]
0x180049434  cmp     [rsi+0D9h], r14b
0x18004943b  jnz     loc_18004977E
0x180049441  lea     rax, [rsi+90h]
0x180049448  cmp     word ptr [rax+30h], 0Bh
0x18004944d  jnz     loc_180049624
0x180049453  cmp     word ptr [rsi+0C8h], 0FFFFh
0x18004945b  jnz     loc_180049624
0x180049461  lea     rdx, [rsp+0E8h+ActivePolicyGuid]; ActivePolicyGuid
0x180049466  xor     ecx, ecx; UserRootPowerKey
0x180049468  call    cs:__imp_PowerGetActiveScheme
0x18004946f  nop     dword ptr [rax+rax+00h]
0x180049474  mov     edi, eax
0x180049476  test    eax, eax
0x180049478  jz      short loc_1800494A2
0x18004947a  jle     short loc_180049485
0x18004947c  movzx   edi, ax
0x18004947f  or      edi, 80070000h
0x180049485  mov     [rsp+0E8h+var_B4], edi
0x180049489  mov     rcx, r15; lpCriticalSection
0x18004948c  call    cs:__imp_LeaveCriticalSection
0x180049493  nop     dword ptr [rax+rax+00h]
0x180049498  nop
0x180049499  mov     bl, [rsp+0E8h+var_B8]
0x18004949d  jmp     loc_1800497A8
0x1800494a2  lea     rax, [rsp+0E8h+var_A8]
0x1800494a7  mov     [rsp+0E8h+AcValueIndex], rax; AcValueIndex
0x1800494ac  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x1800494b3  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800494ba  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x1800494bf  xor     ecx, ecx; RootPowerKey
0x1800494c1  call    cs:__imp_PowerReadACValueIndex
0x1800494c8  nop     dword ptr [rax+rax+00h]
0x1800494cd  mov     edi, eax
0x1800494cf  test    eax, eax
0x1800494d1  jz      short loc_1800494FB
0x1800494d3  jle     short loc_1800494DE
0x1800494d5  movzx   edi, ax
0x1800494d8  or      edi, 80070000h
0x1800494de  mov     [rsp+0E8h+var_B4], edi
0x1800494e2  mov     rcx, r15; lpCriticalSection
0x1800494e5  call    cs:__imp_LeaveCriticalSection
0x1800494ec  nop     dword ptr [rax+rax+00h]
0x1800494f1  nop
0x1800494f2  mov     bl, [rsp+0E8h+var_B8]
0x1800494f6  jmp     loc_1800497A8
0x1800494fb  cmp     [rsp+0E8h+var_A8], r14d
0x180049500  jz      short loc_18004955E
0x180049502  mov     dword ptr [rsp+0E8h+AcValueIndex], r14d; AcValueIndex
0x180049507  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x18004950e  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180049515  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x18004951a  xor     ecx, ecx; RootPowerKey
0x18004951c  call    cs:__imp_PowerWriteACValueIndex
0x180049523  nop     dword ptr [rax+rax+00h]
0x180049528  mov     edi, eax
0x18004952a  test    eax, eax
0x18004952c  jz      short loc_180049556
0x18004952e  jle     short loc_180049539
0x180049530  movzx   edi, ax
0x180049533  or      edi, 80070000h
0x180049539  mov     [rsp+0E8h+var_B4], edi
0x18004953d  mov     rcx, r15; lpCriticalSection
0x180049540  call    cs:__imp_LeaveCriticalSection
0x180049547  nop     dword ptr [rax+rax+00h]
0x18004954c  nop
0x18004954d  mov     bl, [rsp+0E8h+var_B8]
0x180049551  jmp     loc_1800497A8
0x180049556  mov     r13d, r14d
0x180049559  mov     [rsp+0E8h+var_A0], r14d
0x18004955e  lea     rax, [rsp+0E8h+DcValueIndex]
0x180049563  mov     [rsp+0E8h+AcValueIndex], rax; DcValueIndex
0x180049568  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x18004956f  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180049576  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x18004957b  xor     ecx, ecx; RootPowerKey
0x18004957d  call    cs:__imp_PowerReadDCValueIndex
0x180049584  nop     dword ptr [rax+rax+00h]
0x180049589  mov     edi, eax
0x18004958b  test    eax, eax
0x18004958d  jz      short loc_1800495B7
0x18004958f  jle     short loc_18004959A
0x180049591  movzx   edi, ax
0x180049594  or      edi, 80070000h
0x18004959a  mov     [rsp+0E8h+var_B4], edi
0x18004959e  mov     rcx, r15; lpCriticalSection
0x1800495a1  call    cs:__imp_LeaveCriticalSection
0x1800495a8  nop     dword ptr [rax+rax+00h]
0x1800495ad  nop
0x1800495ae  mov     bl, [rsp+0E8h+var_B8]
0x1800495b2  jmp     loc_1800497A8
0x1800495b7  cmp     [rsp+0E8h+DcValueIndex], r14d
0x1800495bc  jz      short loc_18004961A
0x1800495be  mov     dword ptr [rsp+0E8h+AcValueIndex], r14d; DcValueIndex
0x1800495c3  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x1800495ca  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800495d1  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x1800495d6  xor     ecx, ecx; RootPowerKey
0x1800495d8  call    cs:__imp_PowerWriteDCValueIndex
0x1800495df  nop     dword ptr [rax+rax+00h]
0x1800495e4  mov     edi, eax
0x1800495e6  test    eax, eax
0x1800495e8  jz      short loc_180049612
0x1800495ea  jle     short loc_1800495F5
0x1800495ec  movzx   edi, ax
0x1800495ef  or      edi, 80070000h
0x1800495f5  mov     [rsp+0E8h+var_B4], edi
0x1800495f9  mov     rcx, r15; lpCriticalSection
0x1800495fc  call    cs:__imp_LeaveCriticalSection
0x180049603  nop     dword ptr [rax+rax+00h]
0x180049608  nop
0x180049609  mov     bl, [rsp+0E8h+var_B8]
0x18004960d  jmp     loc_1800497A8
0x180049612  mov     r12d, r14d
0x180049615  mov     [rsp+0E8h+var_9C], r14d
0x18004961a  mov     [rbx], r14b
0x18004961d  lea     rax, [rsi+90h]
0x180049624  xor     edi, edi
0x180049626  cmp     [rsi+0D9h], r14b
0x18004962d  jnz     short loc_18004964A
0x18004962f  mov     rdx, rax; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x180049632  call    ?StoreMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::StoreMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x180049637  mov     edi, eax
0x180049639  test    eax, eax
0x18004963b  js      short loc_18004964A
0x18004963d  mov     [rsi+0D9h], r14b
0x180049644  mov     [rsp+0E8h+var_B4], eax
0x180049648  jmp     short loc_18004966B
0x18004964a  mov     [rsp+0E8h+var_B4], edi
0x18004964e  test    edi, edi
0x180049650  jns     short loc_18004966B
0x180049652  mov     rcx, r15; lpCriticalSection
0x180049655  call    cs:__imp_LeaveCriticalSection
0x18004965c  nop     dword ptr [rax+rax+00h]
0x180049661  nop
0x180049662  mov     bl, [rsp+0E8h+var_B8]
0x180049666  jmp     loc_1800497A8
0x18004966b  call    cs:__imp_WinSqmIsOptedIn
0x180049672  nop     dword ptr [rax+rax+00h]
0x180049677  test    eax, eax
0x180049679  jz      loc_18004977E
0x18004967f  lea     rcx, [rsp+0E8h+var_60]; this
0x180049687  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18004968c  xor     ebx, ebx
0x18004968e  mov     [rsp+0E8h+pbstr], rbx
0x180049693  cmp     word ptr [rsi+90h], 8
0x18004969b  jnz     loc_18004976E
0x1800496a1  mov     rdx, [rsi+98h]
0x1800496a8  test    rdx, rdx
0x1800496ab  jz      loc_18004976E
0x1800496b1  cmp     word ptr [rsi+0C0h], 0Bh
0x1800496b9  jnz     loc_18004976E
0x1800496bf  lea     rcx, [rsp+0E8h+pbstr]
0x1800496c4  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800496c9  xor     eax, eax
0x1800496cb  cmp     word ptr [rsi+0C8h], 0FFFFh
0x1800496d3  setz    al
0x1800496d6  mov     [rsp+0E8h+var_98], eax
0x1800496da  mov     rbx, [rsp+0E8h+pbstr]
0x1800496df  mov     rcx, rbx; pbstr
0x1800496e2  call    cs:__imp_SysStringLen
0x1800496e9  nop     dword ptr [rax+rax+00h]
0x1800496ee  mov     edx, eax; unsigned __int64
0x1800496f0  lea     r8, [rsp+0E8h+var_60]; struct TSTime *
0x1800496f8  mov     rcx, rbx; unsigned __int16 *
0x1800496fb  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x180049700  test    eax, eax
0x180049702  js      short loc_18004976E
0x180049704  lea     rdx, [rsp+0E8h+var_48]; retstr
0x18004970c  lea     rcx, [rsp+0E8h+var_60]; this
0x180049714  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180049719  movzx   ecx, word ptr [rax+8]
0x18004971d  imul    ecx, 3Ch ; '<'
0x180049720  movzx   eax, word ptr [rax+0Ah]
0x180049724  add     ecx, eax
0x180049726  xorps   xmm0, xmm0
0x180049729  xor     eax, eax
0x18004972b  movups  [rsp+0E8h+var_78], xmm0
0x180049730  mov     [rsp+0E8h+var_68], rax
0x180049738  mov     dword ptr [rsp+0E8h+var_78], ecx
0x18004973c  mov     [rsp+0E8h+var_80], r14d
0x180049741  mov     eax, [rsp+0E8h+var_98]
0x180049745  mov     dword ptr [rsp+0E8h+var_68], eax
0x18004974c  mov     dword ptr [rsp+0E8h+var_78+8], r14d
0x180049751  lea     r9, [rsp+0E8h+var_80]
0x180049756  mov     edx, 1F92h
0x18004975b  xor     ecx, ecx
0x18004975d  lea     r8d, [rcx+2]
0x180049761  call    cs:__imp_WinSqmAddToStream
0x180049768  nop     dword ptr [rax+rax+00h]
0x18004976d  nop
0x18004976e  mov     rcx, rbx; bstrString
0x180049771  call    cs:__imp_SysFreeString
0x180049778  nop     dword ptr [rax+rax+00h]
0x18004977d  nop
0x18004977e  mov     rcx, r15; lpCriticalSection
0x180049781  call    cs:__imp_LeaveCriticalSection
0x180049788  nop     dword ptr [rax+rax+00h]
0x18004978d  nop
0x18004978e  jmp     short loc_1800497A4
0x180049790  mov     r14d, 1
0x180049796  mov     edi, [rsp+0E8h+var_B4]
0x18004979a  mov     r13d, [rsp+0E8h+var_A0]
0x18004979f  mov     r12d, [rsp+0E8h+var_9C]
0x1800497a4  mov     bl, [rsp+0E8h+var_B8]
0x1800497a8  test    edi, edi
0x1800497aa  jns     short loc_180049827
0x1800497ac  cmp     r13d, r14d
0x1800497af  jnz     short loc_1800497E1
0x1800497b1  mov     eax, [rsp+0E8h+var_A8]
0x1800497b5  mov     dword ptr [rsp+0E8h+AcValueIndex], eax; AcValueIndex
0x1800497b9  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x1800497c0  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800497c7  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x1800497cc  xor     ecx, ecx; RootPowerKey
0x1800497ce  call    cs:__imp_PowerWriteACValueIndex
0x1800497d5  nop     dword ptr [rax+rax+00h]
0x1800497da  neg     eax
0x1800497dc  sbb     ecx, ecx
0x1800497de  and     r13d, ecx
0x1800497e1  cmp     r12d, r14d
0x1800497e4  jnz     short loc_180049816
0x1800497e6  mov     eax, [rsp+0E8h+DcValueIndex]
0x1800497ea  mov     dword ptr [rsp+0E8h+AcValueIndex], eax; DcValueIndex
0x1800497ee  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x1800497f5  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800497fc  mov     rdx, [rsp+0E8h+ActivePolicyGuid]; SchemeGuid
0x180049801  xor     ecx, ecx; RootPowerKey
0x180049803  call    cs:__imp_PowerWriteDCValueIndex
0x18004980a  nop     dword ptr [rax+rax+00h]
0x18004980f  neg     eax
0x180049811  sbb     ecx, ecx
0x180049813  and     r12d, ecx
0x180049816  test    r13d, r13d
0x180049819  jz      short loc_180049820
0x18004981b  test    r12d, r12d
0x18004981e  jnz     short loc_180049827
0x180049820  mov     rax, [rsp+0E8h+var_88]
0x180049825  mov     [rax], bl
0x180049827  mov     rcx, [rsp+0E8h+ActivePolicyGuid]; hMem
0x18004982c  test    rcx, rcx
0x18004982f  jz      short loc_18004983D
0x180049831  call    cs:__imp_LocalFree
0x180049838  nop     dword ptr [rax+rax+00h]
0x18004983d  mov     eax, edi
0x18004983f  mov     rcx, [rsp+0E8h+var_38]
0x180049847  xor     rcx, rsp; StackCookie
0x18004984a  call    __security_check_cookie
0x18004984f  lea     r11, [rsp+0E8h+var_28]
0x180049857  mov     rbx, [r11+38h]
0x18004985b  mov     rsi, [r11+40h]
0x18004985f  mov     rsp, r11
0x180049862  pop     r15
0x180049864  pop     r14
0x180049866  pop     r13
0x180049868  pop     r12
0x18004986a  pop     rdi
0x18004986b  retn
```
