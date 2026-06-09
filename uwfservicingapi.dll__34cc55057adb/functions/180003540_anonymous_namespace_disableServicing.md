# _anonymous_namespace_::disableServicing

- ea: `0x180003540`
- end: `0x180003704`
- name: `_anonymous_namespace_::disableServicing`
- size: `452`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003358`
- `0x18000370c`

## callees

- `0x1800027c8`
- `0x180002a20`
- `0x180002c88`
- `0x1800030b8`
- `0x180003540`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800035f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800035f8`

## string_xrefs

- `0x1800035db`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`
- `0x18000363a`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Runtime`
- `0x18000356c`: `Exit: Failed to get write filter state`
- `0x180003611`: `Exit: Failed to query write filter state`
- `0x18000368b`: `Exit: Failed to commit device unperpping for servicing`
- `0x1800036b4`: `Exit: Failed to enable write filter`
- `0x1800036e5`: `UWF Servicing completed successfully`
- `0x180003582`: `UWF Servicing completed with errors`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::disableServicing(__int64 *a1)
{
  __int64 v1; // rax
  int v3; // eax
  signed int v4; // ebx
  const wchar_t *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  LSTATUS ValueW; // eax
  HKEY v11; // rcx
  HKEY v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // cl
  signed int v16; // eax
  char v17; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  v1 = *a1;
  v17 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, char *, _QWORD))(v1 + 8))(a1, &v17, 0);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = L"Exit: Failed to get write filter state";
LABEL_3:
    v6 = (unsigned int)v3;
LABEL_4:
    UwfServicingLog(0, 1, v6, v5);
    goto LABEL_5;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
             L"FilterState",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v4 = ValueW;
  if ( ValueW > 0 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = L"Exit: Failed to query write filter state";
LABEL_11:
    v6 = (unsigned int)v4;
    goto LABEL_4;
  }
  v13 = UwfServicingRegCopyValue(
          v11,
          L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Runtime",
          L"SavedEnableLUA",
          v12,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          L"EnableLUA");
  if ( v13 < 0 )
    UwfServicingLog(0, 1, (unsigned int)v13, L"Failed to restore LUA control");
  if ( v17 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const WCHAR *))(*a1 + 16))(
           a1,
           L"HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
           L"EnableLUA");
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = L"Exit: Failed to commit device unperpping for servicing";
      goto LABEL_3;
    }
  }
  if ( pvData == 1 )
  {
    LOBYTE(v14) = 1;
    v3 = (*(__int64 (__fastcall **)(__int64 *, __int64))*a1)(a1, v14);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = L"Exit: Failed to enable write filter";
      goto LABEL_3;
    }
  }
  v16 = UwfServicingEnableServicingUser(v15);
  v4 = 0;
  if ( v16 != -2147022675 )
    v4 = v16;
  if ( v4 < 0 )
  {
    v5 = L"Exit: Failed to disable UWF account";
    goto LABEL_11;
  }
  if ( !v4 )
  {
    UwfServicingLog(0, 0, 0, L"UWF Servicing completed successfully");
    v7 = 2;
    v8 = 0;
    return UwfServicingSetStatusEx(v7, v8);
  }
LABEL_5:
  UwfServicingLog(0, 1, (unsigned int)v4, L"UWF Servicing completed with errors");
  v7 = 3;
  v8 = 2;
  return UwfServicingSetStatusEx(v7, v8);
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_18], rbx
0x180003545  push    rsi
0x180003546  sub     rsp, 40h
0x18000354a  mov     rax, [rcx]
0x18000354d  lea     rdx, [rsp+48h+arg_0]
0x180003552  xor     r8d, r8d
0x180003555  mov     [rsp+48h+arg_0], 0
0x18000355a  mov     rsi, rcx
0x18000355d  mov     rax, [rax+8]
0x180003561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003566  mov     ebx, eax
0x180003568  test    eax, eax
0x18000356a  jns     short loc_1800035B0
0x18000356c  lea     r9, aExitFailedToGe; "Exit: Failed to get write filter state"
0x180003573  mov     r8d, eax
0x180003576  mov     edx, 1
0x18000357b  xor     ecx, ecx
0x18000357d  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003582  lea     r9, aUwfServicingCo_0; "UWF Servicing completed with errors"
0x180003589  mov     r8d, ebx
0x18000358c  mov     edx, 1
0x180003591  xor     ecx, ecx
0x180003593  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003598  mov     ecx, 3
0x18000359d  lea     edx, [rcx-1]
0x1800035a0  call    ?UwfServicingSetStatusEx@@YAJW4UWFSERVICING_STATUS@@W4UWFSERVICING_STATUS_INFO@@@Z; UwfServicingSetStatusEx(UWFSERVICING_STATUS,UWFSERVICING_STATUS_INFO)
0x1800035a5  mov     rbx, [rsp+48h+arg_18]
0x1800035aa  add     rsp, 40h
0x1800035ae  pop     rsi
0x1800035af  retn
0x1800035b0  lea     rax, [rsp+48h+arg_10]
0x1800035b5  mov     [rsp+48h+arg_8], 0
0x1800035bd  mov     [rsp+48h+pcbData], rax; pcbData
0x1800035c2  lea     r8, aFilterstate; "FilterState"
0x1800035c9  lea     rax, [rsp+48h+arg_8]
0x1800035ce  mov     [rsp+48h+arg_10], 4
0x1800035d6  mov     [rsp+48h+pvData], rax; pvData
0x1800035db  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800035e2  mov     r9d, 10h; dwFlags
0x1800035e8  mov     [rsp+48h+pdwType], 0; pdwType
0x1800035f1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800035f8  call    cs:__imp_RegGetValueW
0x1800035fe  mov     ebx, eax
0x180003600  test    eax, eax
0x180003602  jle     short loc_18000360D
0x180003604  movzx   ebx, ax
0x180003607  or      ebx, 80070000h
0x18000360d  test    ebx, ebx
0x18000360f  jns     short loc_180003620
0x180003611  lea     r9, aExitFailedToQu; "Exit: Failed to query write filter stat"...
0x180003618  mov     r8d, ebx
0x18000361b  jmp     loc_180003576
0x180003620  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003627  lea     rbx, aEnablelua; "EnableLUA"
0x18000362e  mov     [rsp+48h+pvData], rbx; unsigned __int16 *
0x180003633  lea     r8, aSavedenablelua; "SavedEnableLUA"
0x18000363a  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180003641  mov     [rsp+48h+pdwType], rax; unsigned __int16 *
0x180003646  call    ?UwfServicingRegCopyValue@@YAJPEAUHKEY__@@PEBG1011@Z; UwfServicingRegCopyValue(HKEY__ *,ushort const *,ushort const *,HKEY__ *,ushort const *,ushort const *)
0x18000364b  test    eax, eax
0x18000364d  jns     short loc_180003665
0x18000364f  lea     r9, aFailedToRestor; "Failed to restore LUA control"
0x180003656  mov     r8d, eax
0x180003659  mov     edx, 1
0x18000365e  xor     ecx, ecx
0x180003660  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180003665  cmp     [rsp+48h+arg_0], 0
0x18000366a  jz      short loc_180003697
0x18000366c  mov     rax, [rsi]
0x18000366f  lea     rdx, aHklmSoftwareMi; "HKLM\\Software\\Microsoft\\Windows\\Cur"...
0x180003676  mov     r8, rbx
0x180003679  mov     rcx, rsi
0x18000367c  mov     rax, [rax+10h]
0x180003680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003685  mov     ebx, eax
0x180003687  test    eax, eax
0x180003689  jns     short loc_180003697
0x18000368b  lea     r9, aExitFailedToCo; "Exit: Failed to commit device unperppin"...
0x180003692  jmp     loc_180003573
0x180003697  cmp     [rsp+48h+arg_8], 1
0x18000369c  jnz     short loc_1800036C0
0x18000369e  mov     rax, [rsi]
0x1800036a1  mov     dl, 1
0x1800036a3  mov     rcx, rsi
0x1800036a6  mov     rax, [rax]
0x1800036a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ae  mov     ebx, eax
0x1800036b0  test    eax, eax
0x1800036b2  jns     short loc_1800036C0
0x1800036b4  lea     r9, aExitFailedToEn; "Exit: Failed to enable write filter"
0x1800036bb  jmp     loc_180003573
0x1800036c0  call    ?UwfServicingEnableServicingUser@@YAJ_N@Z; UwfServicingEnableServicingUser(bool)
0x1800036c5  xor     ebx, ebx
0x1800036c7  cmp     eax, 800708ADh
0x1800036cc  cmovnz  ebx, eax
0x1800036cf  test    ebx, ebx
0x1800036d1  jns     short loc_1800036DF
0x1800036d3  lea     r9, aExitFailedToDi; "Exit: Failed to disable UWF account"
0x1800036da  jmp     loc_180003618
0x1800036df  jnz     loc_180003582
0x1800036e5  lea     r9, aUwfServicingCo; "UWF Servicing completed successfully"
0x1800036ec  xor     r8d, r8d
0x1800036ef  xor     edx, edx
0x1800036f1  xor     ecx, ecx
0x1800036f3  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x1800036f8  mov     ecx, 2
0x1800036fd  xor     edx, edx
0x1800036ff  jmp     loc_1800035A0
```
