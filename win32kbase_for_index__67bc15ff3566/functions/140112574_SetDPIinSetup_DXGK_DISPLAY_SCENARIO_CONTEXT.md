# SetDPIinSetup(_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x140112574`
- end: `0x140112b7b`
- name: `?SetDPIinSetup@@YAJPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1543`
- prototype: `int(struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14009ed0c`

## callees

- `0x140049df8`
- `0x14006fce8`
- `0x140070170`
- `0x14009fc4c`
- `0x140112574`
- `0x140113ae0`
- `0x140113c20`
- `0x140187e08`
- `0x140189a34`
- `0x140195510`
- `0x1401b8558`
- `0x1401bba58`
- `0x1401f4510`
- `0x1402389c0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140112b27`
- `ntoskrnl!KeBugCheckEx` at `0x140112b27`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401129dc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401129dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140112b02`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140112b5a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140112b02`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140112b5a`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112628`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112707`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112737`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112628`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112707`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140112737`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401126b5`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140112b44`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401126b5`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140112b44`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140112663`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140112695`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140112663`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140112695`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401125fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140112647`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011267e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401125fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140112647`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011267e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140112a3f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140112a3f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401127c6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112805`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112841`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112877`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401127c6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112805`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112841`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140112877`
- `WIN32K!W32GetUserSessionState` at `0x14011275a`
- `WIN32K!W32GetUserSessionState` at `0x1401127b4`
- `WIN32K!W32GetUserSessionState` at `0x1401128b4`
- `WIN32K!W32GetUserSessionState` at `0x140112957`
- `WIN32K!W32GetUserSessionState` at `0x140112975`
- `WIN32K!W32GetUserSessionState` at `0x14011298c`
- `WIN32K!W32GetUserSessionState` at `0x1401129a8`
- `WIN32K!W32GetUserSessionState` at `0x1401129c2`
- `WIN32K!W32GetUserSessionState` at `0x1401129fc`
- `WIN32K!W32GetUserSessionState` at `0x140112a1d`
- `WIN32K!W32GetUserSessionState` at `0x140112aaa`
- `WIN32K!W32GetUserSessionState` at `0x14011275a`
- `WIN32K!W32GetUserSessionState` at `0x1401127b4`
- `WIN32K!W32GetUserSessionState` at `0x1401128b4`
- `WIN32K!W32GetUserSessionState` at `0x140112957`
- `WIN32K!W32GetUserSessionState` at `0x140112975`
- `WIN32K!W32GetUserSessionState` at `0x14011298c`
- `WIN32K!W32GetUserSessionState` at `0x1401129a8`
- `WIN32K!W32GetUserSessionState` at `0x1401129c2`
- `WIN32K!W32GetUserSessionState` at `0x1401129fc`
- `WIN32K!W32GetUserSessionState` at `0x140112a1d`
- `WIN32K!W32GetUserSessionState` at `0x140112aaa`

## string_xrefs

- `0x140112621`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\State`
- `0x1401126fe`: `\Registry\Machine\SYSTEM\Setup`
- `0x1401126ae`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x140112727`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x140112b3d`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x140112673`: `IMAGE_STATE_COMPLETE`

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
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int (*v18)(void); // rax
  int (*v19)(void); // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int (*v23)(void); // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int (__fastcall *v26)(__int64, bool); // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  struct _MDEV *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 CurrentThreadWin32Thread; // rbx
  int updated; // eax
  __int64 v64; // rcx
  __int64 v65; // r8
  bool v66; // bl
  __int64 v67; // rax
  int v68; // r8d
  int v69; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+A0h] [rbp-70h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-28h]
  int v74; // [rsp+F0h] [rbp-20h]
  __int64 v75; // [rsp+F8h] [rbp-18h]
  __int64 v76; // [rsp+100h] [rbp-10h]
  int v77; // [rsp+108h] [rbp-8h]
  __int64 v78; // [rsp+110h] [rbp+0h]
  int v79; // [rsp+118h] [rbp+8h]
  _DWORD v80[36]; // [rsp+120h] [rbp+10h] BYREF
  __int64 p_DestinationString; // [rsp+1C8h] [rbp+B8h] BYREF
  int v82; // [rsp+1D0h] [rbp+C0h] BYREF
  struct _MDEV *v83; // [rsp+1D8h] [rbp+C8h] BYREF

  QueryTable.Flags = 292;
  v82 = 0;
  QueryTable.Name = L"ImageState";
  v83 = 0;
  QueryTable.EntryContext = &DestinationString;
  QueryTable.QueryRoutine = 0;
  QueryTable.DefaultType = 16777217;
  QueryTable.DefaultData = 0;
  DestinationString = 0;
  QueryTable.DefaultLength = 0;
  String2 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
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
    QueryTable.EntryContext = &v82;
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
    memset(v80, 0, 0x60u);
    UserSessionState = W32GetUserSessionState(v6, v5, v7);
    if ( (int)DrvGetCurrentDpiInfoFromHDev(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 96LL) + 80LL),
                v80) < 0 )
      goto LABEL_5;
    if ( !(unsigned int)PreAllocateForPrimaryMonitorChange() )
    {
      v3 = -1073741823;
      goto LABEL_6;
    }
    v11 = 0;
    v12 = (unsigned int)(96 * v80[2] + 50);
    LODWORD(v9) = (1374389535 * (unsigned __int64)(unsigned int)v12) >> 32;
    v13 = (unsigned int)v12 / 0x64;
    *(_DWORD *)(W32GetUserSessionState(v12, v9, v10) + 68396) = 1;
    v17 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v15, v14) + 48);
    v18 = *(int (**)(void))(v17 + 2704);
    if ( v18 && v18() >= 0 )
      GetDpiSetting(1, &v82);
    if ( v82 != v13 )
    {
      v19 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v17, v16) + 48) + 2736LL);
      if ( v19 )
      {
        if ( v19() >= 0 && (int)SetDpiSetting(v20, v13) >= 0 )
        {
          v23 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v22, v21) + 48) + 2720LL);
          if ( v23 )
          {
            if ( v23() >= 0 )
            {
              v26 = *(int (__fastcall **)(__int64, bool))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v25, v24) + 48)
                                                        + 2728LL);
              if ( v26 )
              {
                if ( v26(1, v13 > 0x78) >= 0 )
                {
                  LOBYTE(p_DestinationString) = 0;
                  GreReinitializeDpiSetting();
                  v30 = W32GetUserSessionState(v28, v27, v29);
                  if ( (int)DrvSetDisplayConfig(
                              0,
                              0,
                              2191,
                              0,
                              0,
                              0,
                              0,
                              0,
                              *(struct _MDEV **)(*(_QWORD *)(v30 + 56744) + 16LL),
                              &v83,
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
                      v34 = *(_QWORD *)v83;
                      v38 = *(_QWORD *)(W32GetUserSessionState(v36, v35, v37) + 56744);
                      *(_QWORD *)(v38 + 40) = v34;
                      v39 = v83;
                      v42 = *(_QWORD *)(W32GetUserSessionState(v38, v40, v41) + 56744);
                      *(_QWORD *)(v42 + 16) = v39;
                      v45 = W32GetUserSessionState(v42, v43, v44);
                      GreUpdateSharedDevCaps(*(_QWORD *)(*(_QWORD *)(v45 + 56744) + 40LL));
                      v49 = *(_QWORD *)(W32GetUserSessionState(v47, v46, v48) + 19704);
                      *(_WORD *)(v49 + 6998) = v13;
                      v52 = W32GetUserSessionState(v49, v50, v51);
                      ++*(_WORD *)(*(_QWORD *)(v52 + 19704) + 7014LL);
                      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
                      v57 = CurrentProcessWin32Process;
                      if ( CurrentProcessWin32Process )
                      {
                        v55 = -*(_QWORD *)CurrentProcessWin32Process;
                        v54 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
                        v57 = v54 & CurrentProcessWin32Process;
                      }
                      v32 = *(_QWORD *)(W32GetUserSessionState(v55, v54, v56) + 19704);
                      *(_WORD *)(v57 + 272) = *(_WORD *)(v32 + 6998);
                    }
                    if ( !*(_QWORD *)W32GetUserSessionState(v32, v31, v33) || !IS_USERCRIT_OWNED_AT_ALL() )
                      KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
                    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v59, v58, v60, v61);
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
                      v66 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        v67 = W32GetUserSessionState(v64, WPP_GLOBAL_Control, v65);
                        LOBYTE(v68) = v66;
                        LOBYTE(v69) = v2;
                        WPP_RECORDER_AND_TRACE_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v69,
                          v68,
                          *(_QWORD *)(v67 + 69136),
                          2,
                          14,
                          22,
                          (__int64)WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids,
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
0x140112574  push    rbp
0x140112576  push    rbx
0x140112577  push    rsi
0x140112578  push    rdi
0x140112579  push    r12
0x14011257b  push    r14
0x14011257d  push    r15
0x14011257f  lea     rbp, [rsp-70h]
0x140112584  sub     rsp, 180h
0x14011258b  xor     r12d, r12d
0x14011258e  mov     [rbp+0A0h+QueryTable.Flags], 124h
0x140112595  lea     rax, aImagestate; "ImageState"
0x14011259c  mov     [rbp+0A0h+arg_10], r12d
0x1401125a3  mov     [rbp+0A0h+QueryTable.Name], rax
0x1401125a7  mov     r15, rcx
0x1401125aa  lea     rax, [rbp+0A0h+DestinationString]
0x1401125ae  mov     [rbp+0A0h+arg_18], r12
0x1401125b5  xorps   xmm0, xmm0
0x1401125b8  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x1401125bc  xorps   xmm1, xmm1
0x1401125bf  mov     [rbp+0A0h+QueryTable.QueryRoutine], r12
0x1401125c3  xor     edx, edx; SourceString
0x1401125c5  mov     [rbp+0A0h+QueryTable.DefaultType], 1000001h
0x1401125cc  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1401125d0  mov     [rbp+0A0h+QueryTable.DefaultData], r12
0x1401125d4  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1401125d8  mov     [rbp+0A0h+QueryTable.DefaultLength], r12d
0x1401125dc  movups  xmmword ptr [rbp+0A0h+String2.Length], xmm1
0x1401125e0  mov     [rbp+0A0h+var_C8], r12
0x1401125e4  mov     [rbp+0A0h+var_C0], r12d
0x1401125e8  mov     [rbp+0A0h+var_B8], r12
0x1401125ec  mov     [rbp+0A0h+var_B0], r12
0x1401125f0  mov     [rbp+0A0h+var_A8], r12d
0x1401125f4  mov     [rbp+0A0h+var_A0], r12
0x1401125f8  mov     [rbp+0A0h+var_98], r12d
0x1401125fc  call    cs:__imp_RtlInitUnicodeString
0x140112603  nop     dword ptr [rax+rax+00h]
0x140112608  lea     rax, [rbp+0A0h+DestinationString]
0x14011260c  mov     [rsp+1B0h+Environment], r12; Environment
0x140112611  xor     r9d, r9d; Context
0x140112614  mov     [rbp+0A0h+arg_8], rax
0x14011261b  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x14011261f  xor     ecx, ecx; RelativeTo
0x140112621  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x140112628  call    cs:__imp_RtlQueryRegistryValues
0x14011262f  nop     dword ptr [rax+rax+00h]
0x140112634  test    eax, eax
0x140112636  js      loc_140112B34
0x14011263c  lea     rdx, aImageStateSpec; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE"
0x140112643  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x140112647  call    cs:__imp_RtlInitUnicodeString
0x14011264e  nop     dword ptr [rax+rax+00h]
0x140112653  lea     edi, [r12+1]
0x140112658  mov     r8b, dil; CaseInSensitive
0x14011265b  lea     rdx, [rbp+0A0h+String2]; String2
0x14011265f  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x140112663  call    cs:__imp_RtlCompareUnicodeString
0x14011266a  nop     dword ptr [rax+rax+00h]
0x14011266f  test    eax, eax
0x140112671  jz      short loc_1401126D7
0x140112673  lea     rdx, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x14011267a  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x14011267e  call    cs:__imp_RtlInitUnicodeString
0x140112685  nop     dword ptr [rax+rax+00h]
0x14011268a  mov     r8b, dil; CaseInSensitive
0x14011268d  lea     rdx, [rbp+0A0h+String2]; String2
0x140112691  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x140112695  call    cs:__imp_RtlCompareUnicodeString
0x14011269c  nop     dword ptr [rax+rax+00h]
0x1401126a1  test    eax, eax
0x1401126a3  jnz     short loc_1401126C1
0x1401126a5  lea     r8, ValueName; "Overrode"
0x1401126ac  xor     ecx, ecx; RelativeTo
0x1401126ae  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1401126b5  call    cs:__imp_RtlDeleteRegistryValue
0x1401126bc  nop     dword ptr [rax+rax+00h]
0x1401126c1  mov     ebx, r12d
0x1401126c4  lea     rcx, [rbp+0A0h+arg_8]
0x1401126cb  call    _SetDPIinSetup____2___CleanupUnicodeString___CleanupUnicodeString
0x1401126d0  mov     eax, ebx
0x1401126d2  jmp     loc_140112B68
0x1401126d7  bts     [rbp+0A0h+QueryTable.Flags], 7
0x1401126dc  lea     rax, aUpgrade; "Upgrade"
0x1401126e3  mov     [rbp+0A0h+QueryTable.Name], rax
0x1401126e7  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x1401126eb  lea     rax, [rbp+0A0h+arg_10]
0x1401126f2  mov     [rsp+1B0h+Environment], r12; Environment
0x1401126f7  xor     r9d, r9d; Context
0x1401126fa  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x1401126fe  lea     rdx, aRegistryMachin_16; "\\Registry\\Machine\\SYSTEM\\Setup"
0x140112705  xor     ecx, ecx; RelativeTo
0x140112707  call    cs:__imp_RtlQueryRegistryValues
0x14011270e  nop     dword ptr [rax+rax+00h]
0x140112713  test    eax, eax
0x140112715  jns     short loc_1401126C1
0x140112717  lea     r8, ValueName; "Overrode"
0x14011271e  mov     [rsp+1B0h+Environment], r12; Environment
0x140112723  mov     [rbp+0A0h+QueryTable.Name], r8
0x140112727  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14011272e  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x140112732  xor     r9d, r9d; Context
0x140112735  xor     ecx, ecx; RelativeTo
0x140112737  call    cs:__imp_RtlQueryRegistryValues
0x14011273e  nop     dword ptr [rax+rax+00h]
0x140112743  test    eax, eax
0x140112745  jns     loc_1401126C1
0x14011274b  xor     edx, edx; Val
0x14011274d  lea     rcx, [rbp+0A0h+var_90]; void *
0x140112751  lea     r8d, [rdx+60h]; Size
0x140112755  call    memset
0x14011275a  call    cs:__imp_W32GetUserSessionState
0x140112761  nop     dword ptr [rax+rax+00h]
0x140112766  lea     rdx, [rbp+0A0h+var_90]
0x14011276a  mov     rcx, [rax+0DDA8h]
0x140112771  mov     rcx, [rcx+60h]
0x140112775  mov     rcx, [rcx+50h]
0x140112779  call    DrvGetCurrentDpiInfoFromHDev
0x14011277e  test    eax, eax
0x140112780  js      loc_1401126C1
0x140112786  call    ?PreAllocateForPrimaryMonitorChange@@YAHXZ; PreAllocateForPrimaryMonitorChange(void)
0x14011278b  test    eax, eax
0x14011278d  jnz     short loc_140112799
0x14011278f  mov     ebx, 0C0000001h
0x140112794  jmp     loc_1401126C4
0x140112799  mov     eax, [rbp+0A0h+var_88]
0x14011279c  mov     r14d, r12d
0x14011279f  lea     ecx, [rax+rax*2]
0x1401127a2  mov     eax, 51EB851Fh
0x1401127a7  shl     ecx, 5
0x1401127aa  add     ecx, 32h ; '2'
0x1401127ad  mul     ecx
0x1401127af  mov     esi, edx
0x1401127b1  shr     esi, 5
0x1401127b4  call    cs:__imp_W32GetUserSessionState
0x1401127bb  nop     dword ptr [rax+rax+00h]
0x1401127c0  mov     [rax+10B2Ch], edi
0x1401127c6  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401127cd  nop     dword ptr [rax+rax+00h]
0x1401127d2  mov     rcx, [rax+30h]
0x1401127d6  mov     rax, [rcx+0A90h]
0x1401127dd  test    rax, rax
0x1401127e0  jz      short loc_1401127F9
0x1401127e2  call    _guard_dispatch_icall
0x1401127e7  test    eax, eax
0x1401127e9  js      short loc_1401127F9
0x1401127eb  lea     rdx, [rbp+0A0h+arg_10]
0x1401127f2  mov     ecx, edi
0x1401127f4  call    GetDpiSetting
0x1401127f9  cmp     [rbp+0A0h+arg_10], esi
0x1401127ff  jz      loc_140112AF8
0x140112805  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14011280c  nop     dword ptr [rax+rax+00h]
0x140112811  mov     rcx, [rax+30h]
0x140112815  mov     rax, [rcx+0AB0h]
0x14011281c  test    rax, rax
0x14011281f  jz      loc_140112AF8
0x140112825  call    _guard_dispatch_icall
0x14011282a  test    eax, eax
0x14011282c  js      loc_140112AF8
0x140112832  mov     edx, esi
0x140112834  call    SetDpiSetting
0x140112839  test    eax, eax
0x14011283b  js      loc_140112AF8
0x140112841  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140112848  nop     dword ptr [rax+rax+00h]
0x14011284d  mov     rcx, [rax+30h]
0x140112851  mov     rax, [rcx+0AA0h]
0x140112858  test    rax, rax
0x14011285b  jz      loc_140112AF8
0x140112861  call    _guard_dispatch_icall
0x140112866  test    eax, eax
0x140112868  js      loc_140112AF8
0x14011286e  cmp     esi, 78h ; 'x'
0x140112871  mov     ebx, r12d
0x140112874  setnbe  bl
0x140112877  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14011287e  nop     dword ptr [rax+rax+00h]
0x140112883  mov     rcx, [rax+30h]
0x140112887  mov     rax, [rcx+0AA8h]
0x14011288e  test    rax, rax
0x140112891  jz      loc_140112AF8
0x140112897  mov     edx, ebx
0x140112899  mov     ecx, edi
0x14011289b  call    _guard_dispatch_icall
0x1401128a0  test    eax, eax
0x1401128a2  js      loc_140112AF8
0x1401128a8  mov     byte ptr [rbp+0A0h+arg_8], r12b
0x1401128af  call    GreReinitializeDpiSetting
0x1401128b4  call    cs:__imp_W32GetUserSessionState
0x1401128bb  nop     dword ptr [rax+rax+00h]
0x1401128c0  mov     [rsp+1B0h+var_130], r12; __int64
0x1401128c8  lea     rcx, [rbp+0A0h+arg_8]
0x1401128cf  mov     [rsp+1B0h+var_138], r15; __int64
0x1401128d4  xor     r9d, r9d; int
0x1401128d7  mov     [rsp+1B0h+var_140], r12; __int64
0x1401128dc  xor     edx, edx; int
0x1401128de  mov     rax, [rax+0DDA8h]
0x1401128e5  mov     r8d, 88Fh; int
0x1401128eb  mov     [rsp+1B0h+var_148], r12; __int64
0x1401128f0  mov     [rsp+1B0h+var_150], rcx; __int64
0x1401128f5  lea     rcx, [rbp+0A0h+arg_18]
0x1401128fc  mov     [rsp+1B0h+var_158], r12; __int64
0x140112901  mov     rax, [rax+10h]
0x140112905  mov     [rsp+1B0h+var_160], r12; __int64
0x14011290a  mov     [rsp+1B0h+var_168], rcx; struct _MDEV **
0x14011290f  xor     ecx, ecx; int
0x140112911  mov     [rsp+1B0h+var_170], rax; struct _MDEV *
0x140112916  mov     [rsp+1B0h+var_178], r12; __int64
0x14011291b  mov     [rsp+1B0h+var_180], r12; __int64
0x140112920  mov     [rsp+1B0h+var_188], r12b; char
0x140112925  mov     [rsp+1B0h+Environment], r12; __int64
0x14011292a  call    DrvSetDisplayConfig
0x14011292f  test    eax, eax
0x140112931  js      loc_140112AF8
0x140112937  cmp     byte ptr [rbp+0A0h+arg_8], r12b
0x14011293e  jnz     loc_140112A1D
0x140112944  mov     edx, edi
0x140112946  mov     ecx, esi
0x140112948  call    GreReinitializeStockFonts
0x14011294d  mov     rax, [rbp+0A0h+arg_18]
0x140112954  mov     rbx, [rax]
0x140112957  call    cs:__imp_W32GetUserSessionState
0x14011295e  nop     dword ptr [rax+rax+00h]
0x140112963  mov     rcx, [rax+0DDA8h]
0x14011296a  mov     [rcx+28h], rbx
0x14011296e  mov     rbx, [rbp+0A0h+arg_18]
0x140112975  call    cs:__imp_W32GetUserSessionState
0x14011297c  nop     dword ptr [rax+rax+00h]
0x140112981  mov     rcx, [rax+0DDA8h]
0x140112988  mov     [rcx+10h], rbx
0x14011298c  call    cs:__imp_W32GetUserSessionState
0x140112993  nop     dword ptr [rax+rax+00h]
0x140112998  mov     rcx, [rax+0DDA8h]
0x14011299f  mov     rcx, [rcx+28h]; P4
0x1401129a3  call    GreUpdateSharedDevCaps
0x1401129a8  call    cs:__imp_W32GetUserSessionState
0x1401129af  nop     dword ptr [rax+rax+00h]
0x1401129b4  mov     rcx, [rax+4CF8h]
0x1401129bb  mov     [rcx+1B56h], si
0x1401129c2  call    cs:__imp_W32GetUserSessionState
0x1401129c9  nop     dword ptr [rax+rax+00h]
0x1401129ce  mov     rcx, [rax+4CF8h]
0x1401129d5  add     [rcx+1B66h], di
0x1401129dc  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401129e3  nop     dword ptr [rax+rax+00h]
0x1401129e8  mov     rbx, rax
0x1401129eb  test    rax, rax
0x1401129ee  jz      short loc_1401129FC
0x1401129f0  mov     rcx, [rax]
0x1401129f3  neg     rcx
0x1401129f6  sbb     rdx, rdx
0x1401129f9  and     rbx, rdx
0x1401129fc  call    cs:__imp_W32GetUserSessionState
0x140112a03  nop     dword ptr [rax+rax+00h]
0x140112a08  mov     rcx, [rax+4CF8h]
0x140112a0f  movzx   eax, word ptr [rcx+1B56h]
0x140112a16  mov     [rbx+110h], ax
0x140112a1d  call    cs:__imp_W32GetUserSessionState
0x140112a24  nop     dword ptr [rax+rax+00h]
0x140112a29  cmp     [rax], r12
0x140112a2c  jz      loc_140112B13
0x140112a32  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x140112a37  test    al, al
0x140112a39  jz      loc_140112B13
0x140112a3f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140112a46  nop     dword ptr [rax+rax+00h]
0x140112a4b  mov     rbx, rax
0x140112a4e  add     [rax+1Ch], edi
0x140112a51  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x140112a56  dec     dword ptr [rbx+1Ch]
0x140112a59  mov     r14d, eax
0x140112a5c  mov     cs:?gbSetDPIinSetupChangedDisplaySettings@@3_NA, dil; bool gbSetDPIinSetupChangedDisplaySettings
0x140112a63  test    eax, eax
0x140112a65  jns     loc_140112AF8
0x140112a6b  mov     rdx, cs:WPP_GLOBAL_Control
0x140112a72  lea     rax, WPP_GLOBAL_Control
0x140112a79  cmp     rdx, rax
0x140112a7c  jz      short loc_140112A8D
0x140112a7e  test    dword ptr [rdx+2Ch], 2000h
0x140112a85  jz      short loc_140112A8D
0x140112a87  cmp     byte ptr [rdx+29h], 2
0x140112a8b  jnb     short loc_140112A90
0x140112a8d  mov     dil, r12b
0x140112a90  lea     rax, WPP_RECORDER_INITIALIZED
0x140112a97  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140112a9e  setnz   bl
0x140112aa1  test    dil, dil
0x140112aa4  jnz     short loc_140112AAA
0x140112aa6  test    bl, bl
0x140112aa8  jz      short loc_140112AF8
0x140112aaa  call    cs:__imp_W32GetUserSessionState
0x140112ab1  nop     dword ptr [rax+rax+00h]
0x140112ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140112abd  mov     r8b, bl
0x140112ac0  mov     dword ptr [rsp+1B0h+var_170], r14d
0x140112ac5  mov     dl, dil
0x140112ac8  mov     r9, [rax+10E10h]
0x140112acf  lea     rax, WPP_7c021adfd3c4379129fdac45d58d5e06_Traceguids
0x140112ad6  mov     rcx, [rcx+18h]
0x140112ada  mov     [rsp+1B0h+var_178], rax
  ... truncated ...
```
