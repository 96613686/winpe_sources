# SetDPIinSetup(_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x14010fbd4`
- end: `0x1401101db`
- name: `?SetDPIinSetup@@YAJPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1543`
- prototype: `int(struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14009961c`

## callees

- `0x140029bf8`
- `0x14002a080`
- `0x140065ff8`
- `0x140071828`
- `0x14010fbd4`
- `0x140111140`
- `0x140111280`
- `0x140184e38`
- `0x140186f54`
- `0x1401926b0`
- `0x1401b7938`
- `0x1401bae88`
- `0x1401f4470`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140110187`
- `ntoskrnl!KeBugCheckEx` at `0x140110187`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14011003c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14011003c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140110162`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401101ba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140110162`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401101ba`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fc88`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fd67`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fd97`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fc88`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fd67`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010fd97`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14010fd15`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401101a4`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14010fd15`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401101a4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14010fcc3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14010fcf5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14010fcc3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14010fcf5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fca7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fcde`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fca7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fcde`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14011009f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14011009f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fe26`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fe65`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fea1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fed7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fe26`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fe65`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fea1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14010fed7`
- `WIN32K!W32GetUserSessionState` at `0x14010fdba`
- `WIN32K!W32GetUserSessionState` at `0x14010fe14`
- `WIN32K!W32GetUserSessionState` at `0x14010ff14`
- `WIN32K!W32GetUserSessionState` at `0x14010ffb7`
- `WIN32K!W32GetUserSessionState` at `0x14010ffd5`
- `WIN32K!W32GetUserSessionState` at `0x14010ffec`
- `WIN32K!W32GetUserSessionState` at `0x140110008`
- `WIN32K!W32GetUserSessionState` at `0x140110022`
- `WIN32K!W32GetUserSessionState` at `0x14011005c`
- `WIN32K!W32GetUserSessionState` at `0x14011007d`
- `WIN32K!W32GetUserSessionState` at `0x14011010a`
- `WIN32K!W32GetUserSessionState` at `0x14010fdba`
- `WIN32K!W32GetUserSessionState` at `0x14010fe14`
- `WIN32K!W32GetUserSessionState` at `0x14010ff14`
- `WIN32K!W32GetUserSessionState` at `0x14010ffb7`
- `WIN32K!W32GetUserSessionState` at `0x14010ffd5`
- `WIN32K!W32GetUserSessionState` at `0x14010ffec`
- `WIN32K!W32GetUserSessionState` at `0x140110008`
- `WIN32K!W32GetUserSessionState` at `0x140110022`
- `WIN32K!W32GetUserSessionState` at `0x14011005c`
- `WIN32K!W32GetUserSessionState` at `0x14011007d`
- `WIN32K!W32GetUserSessionState` at `0x14011010a`

## string_xrefs

- `0x14010fc81`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\State`
- `0x14010fd5e`: `\Registry\Machine\SYSTEM\Setup`
- `0x14010fd0e`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x14010fd87`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x14011019d`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x14010fcd3`: `IMAGE_STATE_COMPLETE`

## pseudocode

```c
__int64 __fastcall SetDPIinSetup(struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a1)
{
  char v2; // di
  unsigned int v3; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 UserSessionState; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r14d
  __int64 v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // rcx
  int (*v16)(void); // rax
  int (*v17)(void); // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int (*v20)(void); // rax
  __int64 v21; // rcx
  int (__fastcall *v22)(__int64, bool); // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rcx
  struct _MDEV *v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rbx
  __int64 CurrentThreadWin32Thread; // rbx
  int updated; // eax
  __int64 v56; // rcx
  __int64 v57; // r8
  bool v58; // bl
  __int64 v59; // rax
  int v60; // r8d
  int v61; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+A0h] [rbp-70h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+E8h] [rbp-28h]
  int v66; // [rsp+F0h] [rbp-20h]
  __int64 v67; // [rsp+F8h] [rbp-18h]
  __int64 v68; // [rsp+100h] [rbp-10h]
  int v69; // [rsp+108h] [rbp-8h]
  __int64 v70; // [rsp+110h] [rbp+0h]
  int v71; // [rsp+118h] [rbp+8h]
  _DWORD v72[36]; // [rsp+120h] [rbp+10h] BYREF
  __int64 p_DestinationString; // [rsp+1C8h] [rbp+B8h] BYREF
  int v74; // [rsp+1D0h] [rbp+C0h] BYREF
  struct _MDEV *v75; // [rsp+1D8h] [rbp+C8h] BYREF

  QueryTable.Flags = 292;
  v74 = 0;
  QueryTable.Name = L"ImageState";
  v75 = 0;
  QueryTable.EntryContext = &DestinationString;
  QueryTable.QueryRoutine = 0;
  QueryTable.DefaultType = 16777217;
  QueryTable.DefaultData = 0;
  DestinationString = 0;
  QueryTable.DefaultLength = 0;
  String2 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  p_DestinationString = (__int64)&DestinationString;
  if ( RtlQueryRegistryValues(
         0,
         L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
         &QueryTable,
         0,
         0) < 0 )
  {
    RtlDeleteRegistryValue(
      0,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\DPI",
      L"Overrode");
    if ( DestinationString.Buffer )
      RtlFreeUnicodeString(&DestinationString);
    return 0;
  }
  else
  {
    RtlInitUnicodeString(&String2, L"IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE");
    v2 = 1;
    if ( RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
    {
      RtlInitUnicodeString(&String2, L"IMAGE_STATE_COMPLETE");
      if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
        RtlDeleteRegistryValue(
          0,
          L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\DPI",
          L"Overrode");
LABEL_5:
      v3 = 0;
LABEL_6:
      SetDPIinSetup_::_2_::CleanupUnicodeString::_CleanupUnicodeString(&p_DestinationString);
      return v3;
    }
    QueryTable.Flags |= 0x80u;
    QueryTable.Name = L"Upgrade";
    QueryTable.EntryContext = &v74;
    if ( RtlQueryRegistryValues(0, L"\\Registry\\Machine\\SYSTEM\\Setup", &QueryTable, 0, 0) >= 0 )
      goto LABEL_5;
    QueryTable.Name = L"Overrode";
    if ( RtlQueryRegistryValues(
           0,
           L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\DPI",
           &QueryTable,
           0,
           0) >= 0 )
      goto LABEL_5;
    memset(v72, 0, 0x60u);
    UserSessionState = W32GetUserSessionState(v6, v5, v7);
    if ( (int)DrvGetCurrentDpiInfoFromHDev(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 96LL) + 80LL),
                v72) < 0 )
      goto LABEL_5;
    if ( !(unsigned int)PreAllocateForPrimaryMonitorChange() )
    {
      v3 = -1073741823;
      goto LABEL_6;
    }
    v11 = 0;
    v12 = (unsigned int)(96 * v72[2] + 50);
    LODWORD(v9) = (1374389535 * (unsigned __int64)(unsigned int)v12) >> 32;
    v13 = (unsigned int)v12 / 0x64;
    *(_DWORD *)(W32GetUserSessionState(v12, v9, v10) + 68396) = 1;
    v15 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v14) + 48);
    v16 = *(int (**)(void))(v15 + 2704);
    if ( v16 && v16() >= 0 )
      GetDpiSetting(1, &v74);
    if ( v74 != v13 )
    {
      v17 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v15) + 48) + 2736LL);
      if ( v17 )
      {
        if ( v17() >= 0 && (int)SetDpiSetting(v18, v13) >= 0 )
        {
          v20 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v19) + 48) + 2720LL);
          if ( v20 )
          {
            if ( v20() >= 0 )
            {
              v22 = *(int (__fastcall **)(__int64, bool))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 48) + 2728LL);
              if ( v22 )
              {
                if ( v22(1, v13 > 0x78) >= 0 )
                {
                  LOBYTE(p_DestinationString) = 0;
                  GreReinitializeDpiSetting();
                  v26 = W32GetUserSessionState(v24, v23, v25);
                  if ( (int)DrvSetDisplayConfig(
                              0,
                              0,
                              2191,
                              0,
                              0,
                              0,
                              0,
                              0,
                              *(struct _MDEV **)(*(_QWORD *)(v26 + 56744) + 16LL),
                              &v75,
                              0,
                              0,
                              (__int64)&p_DestinationString,
                              0,
                              0,
                              (__int64)a1,
                              0) >= 0 )
                  {
                    if ( !(_BYTE)p_DestinationString )
                    {
                      GreReinitializeStockFonts(v13, 1);
                      v30 = *(_QWORD *)v75;
                      v34 = *(_QWORD *)(W32GetUserSessionState(v32, v31, v33) + 56744);
                      *(_QWORD *)(v34 + 40) = v30;
                      v35 = v75;
                      v38 = *(_QWORD *)(W32GetUserSessionState(v34, v36, v37) + 56744);
                      *(_QWORD *)(v38 + 16) = v35;
                      v41 = W32GetUserSessionState(v38, v39, v40);
                      GreUpdateSharedDevCaps(*(_QWORD *)(*(_QWORD *)(v41 + 56744) + 40LL));
                      v45 = *(_QWORD *)(W32GetUserSessionState(v43, v42, v44) + 19704);
                      *(_WORD *)(v45 + 6998) = v13;
                      v48 = W32GetUserSessionState(v45, v46, v47);
                      ++*(_WORD *)(*(_QWORD *)(v48 + 19704) + 7014LL);
                      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
                      v53 = CurrentProcessWin32Process;
                      if ( CurrentProcessWin32Process )
                      {
                        v51 = -*(_QWORD *)CurrentProcessWin32Process;
                        v50 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
                        v53 = v50 & CurrentProcessWin32Process;
                      }
                      v28 = *(_QWORD *)(W32GetUserSessionState(v51, v50, v52) + 19704);
                      *(_WORD *)(v53 + 272) = *(_WORD *)(v28 + 6998);
                    }
                    if ( !*(_QWORD *)W32GetUserSessionState(v28, v27, v29) || !IS_USERCRIT_OWNED_AT_ALL() )
                      KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
                    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread();
                    ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
                    updated = zzzUpdateUserScreen();
                    --*(_DWORD *)(CurrentThreadWin32Thread + 28);
                    v11 = updated;
                    gbSetDPIinSetupChangedDisplaySettings = 1;
                    if ( updated < 0 )
                    {
                      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
                      {
                        v2 = 0;
                      }
                      v58 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        v59 = W32GetUserSessionState(v56, WPP_GLOBAL_Control, v57);
                        LOBYTE(v60) = v58;
                        LOBYTE(v61) = v2;
                        WPP_RECORDER_AND_TRACE_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v61,
                          v60,
                          *(_QWORD *)(v59 + 69136),
                          2,
                          14,
                          22,
                          (__int64)WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids,
                          v11);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( DestinationString.Buffer )
      RtlFreeUnicodeString(&DestinationString);
    return v11;
  }
}

```

## disassembly

```asm
0x14010fbd4  push    rbp
0x14010fbd6  push    rbx
0x14010fbd7  push    rsi
0x14010fbd8  push    rdi
0x14010fbd9  push    r12
0x14010fbdb  push    r14
0x14010fbdd  push    r15
0x14010fbdf  lea     rbp, [rsp-70h]
0x14010fbe4  sub     rsp, 180h
0x14010fbeb  xor     r12d, r12d
0x14010fbee  mov     [rbp+0A0h+QueryTable.Flags], 124h
0x14010fbf5  lea     rax, aImagestate; "ImageState"
0x14010fbfc  mov     [rbp+0A0h+arg_10], r12d
0x14010fc03  mov     [rbp+0A0h+QueryTable.Name], rax
0x14010fc07  mov     r15, rcx
0x14010fc0a  lea     rax, [rbp+0A0h+DestinationString]
0x14010fc0e  mov     [rbp+0A0h+arg_18], r12
0x14010fc15  xorps   xmm0, xmm0
0x14010fc18  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x14010fc1c  xorps   xmm1, xmm1
0x14010fc1f  mov     [rbp+0A0h+QueryTable.QueryRoutine], r12
0x14010fc23  xor     edx, edx; SourceString
0x14010fc25  mov     [rbp+0A0h+QueryTable.DefaultType], 1000001h
0x14010fc2c  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x14010fc30  mov     [rbp+0A0h+QueryTable.DefaultData], r12
0x14010fc34  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x14010fc38  mov     [rbp+0A0h+QueryTable.DefaultLength], r12d
0x14010fc3c  movups  xmmword ptr [rbp+0A0h+String2.Length], xmm1
0x14010fc40  mov     [rbp+0A0h+var_C8], r12
0x14010fc44  mov     [rbp+0A0h+var_C0], r12d
0x14010fc48  mov     [rbp+0A0h+var_B8], r12
0x14010fc4c  mov     [rbp+0A0h+var_B0], r12
0x14010fc50  mov     [rbp+0A0h+var_A8], r12d
0x14010fc54  mov     [rbp+0A0h+var_A0], r12
0x14010fc58  mov     [rbp+0A0h+var_98], r12d
0x14010fc5c  call    cs:__imp_RtlInitUnicodeString
0x14010fc63  nop     dword ptr [rax+rax+00h]
0x14010fc68  lea     rax, [rbp+0A0h+DestinationString]
0x14010fc6c  mov     [rsp+1B0h+Environment], r12; Environment
0x14010fc71  xor     r9d, r9d; Context
0x14010fc74  mov     [rbp+0A0h+arg_8], rax
0x14010fc7b  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x14010fc7f  xor     ecx, ecx; RelativeTo
0x14010fc81  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14010fc88  call    cs:__imp_RtlQueryRegistryValues
0x14010fc8f  nop     dword ptr [rax+rax+00h]
0x14010fc94  test    eax, eax
0x14010fc96  js      loc_140110194
0x14010fc9c  lea     rdx, aImageStateSpec; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE"
0x14010fca3  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x14010fca7  call    cs:__imp_RtlInitUnicodeString
0x14010fcae  nop     dword ptr [rax+rax+00h]
0x14010fcb3  lea     edi, [r12+1]
0x14010fcb8  mov     r8b, dil; CaseInSensitive
0x14010fcbb  lea     rdx, [rbp+0A0h+String2]; String2
0x14010fcbf  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x14010fcc3  call    cs:__imp_RtlCompareUnicodeString
0x14010fcca  nop     dword ptr [rax+rax+00h]
0x14010fccf  test    eax, eax
0x14010fcd1  jz      short loc_14010FD37
0x14010fcd3  lea     rdx, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x14010fcda  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x14010fcde  call    cs:__imp_RtlInitUnicodeString
0x14010fce5  nop     dword ptr [rax+rax+00h]
0x14010fcea  mov     r8b, dil; CaseInSensitive
0x14010fced  lea     rdx, [rbp+0A0h+String2]; String2
0x14010fcf1  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x14010fcf5  call    cs:__imp_RtlCompareUnicodeString
0x14010fcfc  nop     dword ptr [rax+rax+00h]
0x14010fd01  test    eax, eax
0x14010fd03  jnz     short loc_14010FD21
0x14010fd05  lea     r8, aOverrode; "Overrode"
0x14010fd0c  xor     ecx, ecx; RelativeTo
0x14010fd0e  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14010fd15  call    cs:__imp_RtlDeleteRegistryValue
0x14010fd1c  nop     dword ptr [rax+rax+00h]
0x14010fd21  mov     ebx, r12d
0x14010fd24  lea     rcx, [rbp+0A0h+arg_8]
0x14010fd2b  call    _SetDPIinSetup____2___CleanupUnicodeString___CleanupUnicodeString
0x14010fd30  mov     eax, ebx
0x14010fd32  jmp     loc_1401101C8
0x14010fd37  bts     [rbp+0A0h+QueryTable.Flags], 7
0x14010fd3c  lea     rax, aUpgrade; "Upgrade"
0x14010fd43  mov     [rbp+0A0h+QueryTable.Name], rax
0x14010fd47  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x14010fd4b  lea     rax, [rbp+0A0h+arg_10]
0x14010fd52  mov     [rsp+1B0h+Environment], r12; Environment
0x14010fd57  xor     r9d, r9d; Context
0x14010fd5a  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x14010fd5e  lea     rdx, aRegistryMachin_16; "\\Registry\\Machine\\SYSTEM\\Setup"
0x14010fd65  xor     ecx, ecx; RelativeTo
0x14010fd67  call    cs:__imp_RtlQueryRegistryValues
0x14010fd6e  nop     dword ptr [rax+rax+00h]
0x14010fd73  test    eax, eax
0x14010fd75  jns     short loc_14010FD21
0x14010fd77  lea     r8, aOverrode; "Overrode"
0x14010fd7e  mov     [rsp+1B0h+Environment], r12; Environment
0x14010fd83  mov     [rbp+0A0h+QueryTable.Name], r8
0x14010fd87  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14010fd8e  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x14010fd92  xor     r9d, r9d; Context
0x14010fd95  xor     ecx, ecx; RelativeTo
0x14010fd97  call    cs:__imp_RtlQueryRegistryValues
0x14010fd9e  nop     dword ptr [rax+rax+00h]
0x14010fda3  test    eax, eax
0x14010fda5  jns     loc_14010FD21
0x14010fdab  xor     edx, edx; Val
0x14010fdad  lea     rcx, [rbp+0A0h+var_90]; void *
0x14010fdb1  lea     r8d, [rdx+60h]; Size
0x14010fdb5  call    memset
0x14010fdba  call    cs:__imp_W32GetUserSessionState
0x14010fdc1  nop     dword ptr [rax+rax+00h]
0x14010fdc6  lea     rdx, [rbp+0A0h+var_90]
0x14010fdca  mov     rcx, [rax+0DDA8h]
0x14010fdd1  mov     rcx, [rcx+60h]
0x14010fdd5  mov     rcx, [rcx+50h]
0x14010fdd9  call    DrvGetCurrentDpiInfoFromHDev
0x14010fdde  test    eax, eax
0x14010fde0  js      loc_14010FD21
0x14010fde6  call    ?PreAllocateForPrimaryMonitorChange@@YAHXZ; PreAllocateForPrimaryMonitorChange(void)
0x14010fdeb  test    eax, eax
0x14010fded  jnz     short loc_14010FDF9
0x14010fdef  mov     ebx, 0C0000001h
0x14010fdf4  jmp     loc_14010FD24
0x14010fdf9  mov     eax, [rbp+0A0h+var_88]
0x14010fdfc  mov     r14d, r12d
0x14010fdff  lea     ecx, [rax+rax*2]
0x14010fe02  mov     eax, 51EB851Fh
0x14010fe07  shl     ecx, 5
0x14010fe0a  add     ecx, 32h ; '2'
0x14010fe0d  mul     ecx
0x14010fe0f  mov     esi, edx
0x14010fe11  shr     esi, 5
0x14010fe14  call    cs:__imp_W32GetUserSessionState
0x14010fe1b  nop     dword ptr [rax+rax+00h]
0x14010fe20  mov     [rax+10B2Ch], edi
0x14010fe26  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14010fe2d  nop     dword ptr [rax+rax+00h]
0x14010fe32  mov     rcx, [rax+30h]
0x14010fe36  mov     rax, [rcx+0A90h]
0x14010fe3d  test    rax, rax
0x14010fe40  jz      short loc_14010FE59
0x14010fe42  call    _guard_dispatch_icall
0x14010fe47  test    eax, eax
0x14010fe49  js      short loc_14010FE59
0x14010fe4b  lea     rdx, [rbp+0A0h+arg_10]
0x14010fe52  mov     ecx, edi
0x14010fe54  call    GetDpiSetting
0x14010fe59  cmp     [rbp+0A0h+arg_10], esi
0x14010fe5f  jz      loc_140110158
0x14010fe65  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14010fe6c  nop     dword ptr [rax+rax+00h]
0x14010fe71  mov     rcx, [rax+30h]
0x14010fe75  mov     rax, [rcx+0AB0h]
0x14010fe7c  test    rax, rax
0x14010fe7f  jz      loc_140110158
0x14010fe85  call    _guard_dispatch_icall
0x14010fe8a  test    eax, eax
0x14010fe8c  js      loc_140110158
0x14010fe92  mov     edx, esi
0x14010fe94  call    SetDpiSetting
0x14010fe99  test    eax, eax
0x14010fe9b  js      loc_140110158
0x14010fea1  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14010fea8  nop     dword ptr [rax+rax+00h]
0x14010fead  mov     rcx, [rax+30h]
0x14010feb1  mov     rax, [rcx+0AA0h]
0x14010feb8  test    rax, rax
0x14010febb  jz      loc_140110158
0x14010fec1  call    _guard_dispatch_icall
0x14010fec6  test    eax, eax
0x14010fec8  js      loc_140110158
0x14010fece  cmp     esi, 78h ; 'x'
0x14010fed1  mov     ebx, r12d
0x14010fed4  setnbe  bl
0x14010fed7  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14010fede  nop     dword ptr [rax+rax+00h]
0x14010fee3  mov     rcx, [rax+30h]
0x14010fee7  mov     rax, [rcx+0AA8h]
0x14010feee  test    rax, rax
0x14010fef1  jz      loc_140110158
0x14010fef7  mov     edx, ebx
0x14010fef9  mov     ecx, edi
0x14010fefb  call    _guard_dispatch_icall
0x14010ff00  test    eax, eax
0x14010ff02  js      loc_140110158
0x14010ff08  mov     byte ptr [rbp+0A0h+arg_8], r12b
0x14010ff0f  call    GreReinitializeDpiSetting
0x14010ff14  call    cs:__imp_W32GetUserSessionState
0x14010ff1b  nop     dword ptr [rax+rax+00h]
0x14010ff20  mov     [rsp+1B0h+var_130], r12; __int64
0x14010ff28  lea     rcx, [rbp+0A0h+arg_8]
0x14010ff2f  mov     [rsp+1B0h+var_138], r15; __int64
0x14010ff34  xor     r9d, r9d; int
0x14010ff37  mov     [rsp+1B0h+var_140], r12; __int64
0x14010ff3c  xor     edx, edx; int
0x14010ff3e  mov     rax, [rax+0DDA8h]
0x14010ff45  mov     r8d, 88Fh; int
0x14010ff4b  mov     [rsp+1B0h+var_148], r12; __int64
0x14010ff50  mov     [rsp+1B0h+var_150], rcx; __int64
0x14010ff55  lea     rcx, [rbp+0A0h+arg_18]
0x14010ff5c  mov     [rsp+1B0h+var_158], r12; __int64
0x14010ff61  mov     rax, [rax+10h]
0x14010ff65  mov     [rsp+1B0h+var_160], r12; __int64
0x14010ff6a  mov     [rsp+1B0h+var_168], rcx; struct _MDEV **
0x14010ff6f  xor     ecx, ecx; int
0x14010ff71  mov     [rsp+1B0h+var_170], rax; struct _MDEV *
0x14010ff76  mov     [rsp+1B0h+var_178], r12; __int64
0x14010ff7b  mov     [rsp+1B0h+var_180], r12; __int64
0x14010ff80  mov     [rsp+1B0h+var_188], r12b; char
0x14010ff85  mov     [rsp+1B0h+Environment], r12; __int64
0x14010ff8a  call    DrvSetDisplayConfig
0x14010ff8f  test    eax, eax
0x14010ff91  js      loc_140110158
0x14010ff97  cmp     byte ptr [rbp+0A0h+arg_8], r12b
0x14010ff9e  jnz     loc_14011007D
0x14010ffa4  mov     edx, edi
0x14010ffa6  mov     ecx, esi
0x14010ffa8  call    GreReinitializeStockFonts
0x14010ffad  mov     rax, [rbp+0A0h+arg_18]
0x14010ffb4  mov     rbx, [rax]
0x14010ffb7  call    cs:__imp_W32GetUserSessionState
0x14010ffbe  nop     dword ptr [rax+rax+00h]
0x14010ffc3  mov     rcx, [rax+0DDA8h]
0x14010ffca  mov     [rcx+28h], rbx
0x14010ffce  mov     rbx, [rbp+0A0h+arg_18]
0x14010ffd5  call    cs:__imp_W32GetUserSessionState
0x14010ffdc  nop     dword ptr [rax+rax+00h]
0x14010ffe1  mov     rcx, [rax+0DDA8h]
0x14010ffe8  mov     [rcx+10h], rbx
0x14010ffec  call    cs:__imp_W32GetUserSessionState
0x14010fff3  nop     dword ptr [rax+rax+00h]
0x14010fff8  mov     rcx, [rax+0DDA8h]
0x14010ffff  mov     rcx, [rcx+28h]; P4
0x140110003  call    GreUpdateSharedDevCaps
0x140110008  call    cs:__imp_W32GetUserSessionState
0x14011000f  nop     dword ptr [rax+rax+00h]
0x140110014  mov     rcx, [rax+4CF8h]
0x14011001b  mov     [rcx+1B56h], si
0x140110022  call    cs:__imp_W32GetUserSessionState
0x140110029  nop     dword ptr [rax+rax+00h]
0x14011002e  mov     rcx, [rax+4CF8h]
0x140110035  add     [rcx+1B66h], di
0x14011003c  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140110043  nop     dword ptr [rax+rax+00h]
0x140110048  mov     rbx, rax
0x14011004b  test    rax, rax
0x14011004e  jz      short loc_14011005C
0x140110050  mov     rcx, [rax]
0x140110053  neg     rcx
0x140110056  sbb     rdx, rdx
0x140110059  and     rbx, rdx
0x14011005c  call    cs:__imp_W32GetUserSessionState
0x140110063  nop     dword ptr [rax+rax+00h]
0x140110068  mov     rcx, [rax+4CF8h]
0x14011006f  movzx   eax, word ptr [rcx+1B56h]
0x140110076  mov     [rbx+110h], ax
0x14011007d  call    cs:__imp_W32GetUserSessionState
0x140110084  nop     dword ptr [rax+rax+00h]
0x140110089  cmp     [rax], r12
0x14011008c  jz      loc_140110173
0x140110092  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x140110097  test    al, al
0x140110099  jz      loc_140110173
0x14011009f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1401100a6  nop     dword ptr [rax+rax+00h]
0x1401100ab  mov     rbx, rax
0x1401100ae  add     [rax+1Ch], edi
0x1401100b1  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x1401100b6  dec     dword ptr [rbx+1Ch]
0x1401100b9  mov     r14d, eax
0x1401100bc  mov     cs:?gbSetDPIinSetupChangedDisplaySettings@@3_NA, dil; bool gbSetDPIinSetupChangedDisplaySettings
0x1401100c3  test    eax, eax
0x1401100c5  jns     loc_140110158
0x1401100cb  mov     rdx, cs:WPP_GLOBAL_Control
0x1401100d2  lea     rax, WPP_GLOBAL_Control
0x1401100d9  cmp     rdx, rax
0x1401100dc  jz      short loc_1401100ED
0x1401100de  test    dword ptr [rdx+2Ch], 2000h
0x1401100e5  jz      short loc_1401100ED
0x1401100e7  cmp     byte ptr [rdx+29h], 2
0x1401100eb  jnb     short loc_1401100F0
0x1401100ed  mov     dil, r12b
0x1401100f0  lea     rax, WPP_RECORDER_INITIALIZED
0x1401100f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401100fe  setnz   bl
0x140110101  test    dil, dil
0x140110104  jnz     short loc_14011010A
0x140110106  test    bl, bl
0x140110108  jz      short loc_140110158
0x14011010a  call    cs:__imp_W32GetUserSessionState
0x140110111  nop     dword ptr [rax+rax+00h]
0x140110116  mov     rcx, cs:WPP_GLOBAL_Control
0x14011011d  mov     r8b, bl
0x140110120  mov     dword ptr [rsp+1B0h+var_170], r14d
0x140110125  mov     dl, dil
0x140110128  mov     r9, [rax+10E10h]
0x14011012f  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x140110136  mov     rcx, [rcx+18h]
0x14011013a  mov     [rsp+1B0h+var_178], rax
  ... truncated ...
```
