# _anonymous_namespace_::enableServicing

- ea: `0x18000370c`
- end: `0x18000395d`
- name: `_anonymous_namespace_::enableServicing`
- size: `593`
- prototype: `__int64 __fastcall(struct UWF_CONFIG_INTERFACE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003358`

## callees

- `0x180002a20`
- `0x1800030b8`
- `0x1800032c4`
- `0x18000348c`
- `0x180003540`
- `0x18000370c`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800037a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800037a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000374e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000374e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180003873`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180003873`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000372f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000372f`

## string_xrefs

- `0x180003741`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`
- `0x18000376f`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`
- `0x18000384f`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`
- `0x18000371e`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime\ShellSem`
- `0x180003837`: `Entry: Failed to get write filter state`
- `0x18000388c`: `Entry: Failed to save write filter state`
- `0x1800038d5`: `Entry: Failed to commit device perpping for servicing`
- `0x1800038f7`: `Entry: Failed to disable write filter`
- `0x18000392a`: `Entry: Failed to enable helper service`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::enableServicing(struct UWF_CONFIG_INTERFACE *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  bool v4; // cc
  const wchar_t *v5; // r9
  __int64 v6; // r8
  __int64 v8; // rax
  int v9; // eax
  LSTATUS v10; // eax
  int v11; // eax
  bool v12; // dl
  int v13; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  bool v15; // [rsp+98h] [rbp+38h] BYREF
  char v16; // [rsp+A0h] [rbp+40h] BYREF
  BOOL Data; // [rsp+A8h] [rbp+48h] BYREF

  v2 = RegDeleteKeyW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime\\ShellSem");
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0
    || (v2 = RegDeleteKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
               0,
               0),
        v3 = v2,
        (v2 & 0xFFFFFFFD) != 0) )
  {
    v4 = v2 <= 0;
  }
  else
  {
    hKey = 0;
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           0);
    v3 = v2;
    v4 = v2 <= 0;
    if ( !v2 )
    {
      RegCloseKey(hKey);
      goto LABEL_8;
    }
  }
  if ( !v4 )
    v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_8:
  if ( v3 < 0 )
  {
    v5 = L"Entry: Failed to clean transition run-time data";
LABEL_10:
    v6 = (unsigned int)v3;
LABEL_11:
    UwfServicingLog(0, 1, v6, v5);
    goto LABEL_12;
  }
  v8 = *(_QWORD *)a1;
  v15 = 0;
  v16 = 0;
  v9 = (*(__int64 (__fastcall **)(struct UWF_CONFIG_INTERFACE *, bool *, char *))(v8 + 8))(a1, &v15, &v16);
  v3 = v9;
  if ( v9 < 0 )
  {
    v5 = L"Entry: Failed to get write filter state";
LABEL_16:
    v6 = (unsigned int)v9;
    goto LABEL_11;
  }
  Data = v16 != 0;
  v10 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
          L"FilterState",
          4u,
          &Data,
          4u);
  v3 = v10;
  if ( v10 > 0 )
    v3 = (unsigned __int16)v10 | 0x80070000;
  if ( v3 < 0 )
  {
    v5 = L"Entry: Failed to save write filter state";
    goto LABEL_10;
  }
  v9 = anonymous_namespace_::configureServicingPrep();
  v3 = v9;
  if ( v9 < 0 )
  {
    v5 = L"Entry: Failed to prep the device for servicing";
    goto LABEL_16;
  }
  if ( v15 )
  {
    v9 = (*(__int64 (__fastcall **)(struct UWF_CONFIG_INTERFACE *, const wchar_t *, const WCHAR *))(*(_QWORD *)a1 + 16LL))(
           a1,
           L"HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
           L"EnableLUA");
    v3 = v9;
    if ( v9 < 0 )
    {
      v5 = L"Entry: Failed to commit device perpping for servicing";
      goto LABEL_16;
    }
  }
  v11 = (**(__int64 (__fastcall ***)(struct UWF_CONFIG_INTERFACE *, _QWORD))a1)(a1, 0);
  v3 = v11;
  if ( v11 < 0 )
  {
    UwfServicingLog(0, 1, (unsigned int)v11, L"Entry: Failed to disable write filter");
LABEL_28:
    anonymous_namespace_::disableServicing(a1);
    goto LABEL_12;
  }
  v13 = UwfServicingEnableHelperService(a1, v12, v15);
  v3 = v13;
  if ( v13 < 0 )
  {
    UwfServicingLog(0, 1, (unsigned int)v13, L"Entry: Failed to enable helper service");
    goto LABEL_28;
  }
  if ( !v13 )
  {
    UwfServicingLog(0, 0, 0, L"UWF Servicing started successfully");
    return (unsigned int)UwfServicingSetStatusEx(1, 0);
  }
LABEL_12:
  UwfServicingLog(0, 1, (unsigned int)v3, L"UWF Servicing failed to start");
  UwfServicingSetStatusEx(3, 1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000370c  push    rbp
0x18000370e  push    rbx
0x18000370f  push    rsi
0x180003710  push    r12
0x180003712  push    r15
0x180003714  mov     rbp, rsp
0x180003717  sub     rsp, 60h
0x18000371b  mov     rsi, rcx
0x18000371e  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003725  mov     r12, 0FFFFFFFF80000002h
0x18000372c  mov     rcx, r12; hKey
0x18000372f  call    cs:__imp_RegDeleteKeyW
0x180003735  mov     ebx, eax
0x180003737  test    eax, 0FFFFFFFDh
0x18000373c  jnz     short loc_1800037B8
0x18000373e  xor     r9d, r9d; Reserved
0x180003741  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003748  xor     r8d, r8d; samDesired
0x18000374b  mov     rcx, r12; hKey
0x18000374e  call    cs:__imp_RegDeleteKeyExW
0x180003754  mov     ebx, eax
0x180003756  test    eax, 0FFFFFFFDh
0x18000375b  jnz     short loc_1800037B8
0x18000375d  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180003766  lea     rax, [rbp+hKey]
0x18000376a  mov     [rsp+60h+phkResult], rax; phkResult
0x18000376f  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003776  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000377f  xor     r9d, r9d; lpClass
0x180003782  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18000378a  xor     r8d, r8d; Reserved
0x18000378d  mov     rcx, r12; hKey
0x180003790  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180003798  mov     [rbp+hKey], 0
0x1800037a0  call    cs:__imp_RegCreateKeyExW
0x1800037a6  mov     ebx, eax
0x1800037a8  test    eax, eax
0x1800037aa  jnz     short loc_1800037BA
0x1800037ac  mov     rcx, [rbp+hKey]; hKey
0x1800037b0  call    cs:__imp_RegCloseKey
0x1800037b6  jmp     short loc_1800037C5
0x1800037b8  test    eax, eax
0x1800037ba  jle     short loc_1800037C5
0x1800037bc  movzx   ebx, ax
0x1800037bf  or      ebx, 80070000h
0x1800037c5  mov     r15d, 1
0x1800037cb  test    ebx, ebx
0x1800037cd  jns     short loc_180003812
0x1800037cf  lea     r9, aEntryFailedToC_0; "Entry: Failed to clean transition run-t"...
0x1800037d6  mov     r8d, ebx
0x1800037d9  mov     edx, r15d
0x1800037dc  xor     ecx, ecx
0x1800037de  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x1800037e3  lea     r9, aUwfServicingFa; "UWF Servicing failed to start"
0x1800037ea  mov     r8d, ebx
0x1800037ed  mov     edx, r15d
0x1800037f0  xor     ecx, ecx
0x1800037f2  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x1800037f7  mov     edx, r15d
0x1800037fa  mov     ecx, 3
0x1800037ff  call    ?UwfServicingSetStatusEx@@YAJW4UWFSERVICING_STATUS@@W4UWFSERVICING_STATUS_INFO@@@Z; UwfServicingSetStatusEx(UWFSERVICING_STATUS,UWFSERVICING_STATUS_INFO)
0x180003804  mov     eax, ebx
0x180003806  add     rsp, 60h
0x18000380a  pop     r15
0x18000380c  pop     r12
0x18000380e  pop     rsi
0x18000380f  pop     rbx
0x180003810  pop     rbp
0x180003811  retn
0x180003812  mov     rax, [rsi]
0x180003815  lea     r8, [rbp+arg_10]
0x180003819  lea     rdx, [rbp+arg_8]
0x18000381d  mov     [rbp+arg_8], 0
0x180003821  mov     rcx, rsi
0x180003824  mov     [rbp+arg_10], 0
0x180003828  mov     rax, [rax+8]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  mov     ebx, eax
0x180003833  test    eax, eax
0x180003835  jns     short loc_180003843
0x180003837  lea     r9, aEntryFailedToG; "Entry: Failed to get write filter state"
0x18000383e  mov     r8d, eax
0x180003841  jmp     short loc_1800037D9
0x180003843  xor     eax, eax
0x180003845  lea     r8, aFilterstate; "FilterState"
0x18000384c  cmp     [rbp+arg_10], al
0x18000384f  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003856  mov     r9d, 4; dwType
0x18000385c  mov     rcx, r12; hKey
0x18000385f  setnz   al
0x180003862  mov     [rsp+60h+samDesired], r9d; cbData
0x180003867  mov     [rbp+Data], eax
0x18000386a  lea     rax, [rbp+Data]
0x18000386e  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180003873  call    cs:__imp_RegSetKeyValueW
0x180003879  mov     ebx, eax
0x18000387b  test    eax, eax
0x18000387d  jle     short loc_180003888
0x18000387f  movzx   ebx, ax
0x180003882  or      ebx, 80070000h
0x180003888  test    ebx, ebx
0x18000388a  jns     short loc_180003898
0x18000388c  lea     r9, aEntryFailedToS; "Entry: Failed to save write filter stat"...
0x180003893  jmp     loc_1800037D6
0x180003898  call    _anonymous_namespace___configureServicingPrep
0x18000389d  mov     ebx, eax
0x18000389f  test    eax, eax
0x1800038a1  jns     short loc_1800038AC
0x1800038a3  lea     r9, aEntryFailedToP; "Entry: Failed to prep the device for se"...
0x1800038aa  jmp     short loc_18000383E
0x1800038ac  cmp     [rbp+arg_8], 0
0x1800038b0  jz      short loc_1800038E1
0x1800038b2  mov     rax, [rsi]
0x1800038b5  lea     r8, aEnablelua; "EnableLUA"
0x1800038bc  lea     rdx, aHklmSoftwareMi; "HKLM\\Software\\Microsoft\\Windows\\Cur"...
0x1800038c3  mov     rcx, rsi
0x1800038c6  mov     rax, [rax+10h]
0x1800038ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038cf  mov     ebx, eax
0x1800038d1  test    eax, eax
0x1800038d3  jns     short loc_1800038E1
0x1800038d5  lea     r9, aEntryFailedToC; "Entry: Failed to commit device perpping"...
0x1800038dc  jmp     loc_18000383E
0x1800038e1  mov     rax, [rsi]
0x1800038e4  xor     edx, edx
0x1800038e6  mov     rcx, rsi
0x1800038e9  mov     rax, [rax]
0x1800038ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f1  mov     ebx, eax
0x1800038f3  test    eax, eax
0x1800038f5  jns     short loc_180003918
0x1800038f7  lea     r9, aEntryFailedToD; "Entry: Failed to disable write filter"
0x1800038fe  mov     r8d, eax
0x180003901  mov     edx, r15d
0x180003904  xor     ecx, ecx
0x180003906  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x18000390b  mov     rcx, rsi
0x18000390e  call    _anonymous_namespace___disableServicing
0x180003913  jmp     loc_1800037E3
0x180003918  mov     r8b, [rbp+arg_8]; bool
0x18000391c  mov     rcx, rsi; struct UWF_CONFIG_INTERFACE *
0x18000391f  call    ?UwfServicingEnableHelperService@@YAJPEAUUWF_CONFIG_INTERFACE@@_N1@Z; UwfServicingEnableHelperService(UWF_CONFIG_INTERFACE *,bool,bool)
0x180003924  mov     ebx, eax
0x180003926  test    eax, eax
0x180003928  jns     short loc_180003933
0x18000392a  lea     r9, aEntryFailedToE; "Entry: Failed to enable helper service"
0x180003931  jmp     short loc_1800038FE
0x180003933  jnz     loc_1800037E3
0x180003939  lea     r9, aUwfServicingSt; "UWF Servicing started successfully"
0x180003940  xor     r8d, r8d
0x180003943  xor     edx, edx
0x180003945  xor     ecx, ecx
0x180003947  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x18000394c  xor     edx, edx
0x18000394e  mov     ecx, r15d
0x180003951  call    ?UwfServicingSetStatusEx@@YAJW4UWFSERVICING_STATUS@@W4UWFSERVICING_STATUS_INFO@@@Z; UwfServicingSetStatusEx(UWFSERVICING_STATUS,UWFSERVICING_STATUS_INFO)
0x180003956  mov     ebx, eax
0x180003958  jmp     loc_180003804
```
