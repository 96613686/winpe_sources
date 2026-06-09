# SetDPIinSetup(_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x140106768`
- end: `0x140106d6f`
- name: `?SetDPIinSetup@@YAJPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1543`
- prototype: `int(struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14009041c`

## callees

- `0x140032e78`
- `0x140033300`
- `0x1400729c8`
- `0x1401066e0`
- `0x140106768`
- `0x140107cd0`
- `0x140108438`
- `0x140185f98`
- `0x1401880b4`
- `0x140192530`
- `0x1401b73d8`
- `0x1401ba928`
- `0x1401f3cb0`
- `0x140238240`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140106d1b`
- `ntoskrnl!KeBugCheckEx` at `0x140106d1b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140106bd0`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140106bd0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140106cf6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140106d4e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140106cf6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140106d4e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010681c`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1401068fb`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010692b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010681c`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1401068fb`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14010692b`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401068a9`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140106d38`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1401068a9`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140106d38`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140106857`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140106889`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140106857`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140106889`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401067f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010683b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140106872`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401067f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010683b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140106872`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140106c33`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140106c33`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401069ba`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401069f9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140106a35`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140106a6b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401069ba`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401069f9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140106a35`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140106a6b`
- `WIN32K!W32GetUserSessionState` at `0x14010694e`
- `WIN32K!W32GetUserSessionState` at `0x1401069a8`
- `WIN32K!W32GetUserSessionState` at `0x140106aa8`
- `WIN32K!W32GetUserSessionState` at `0x140106b4b`
- `WIN32K!W32GetUserSessionState` at `0x140106b69`
- `WIN32K!W32GetUserSessionState` at `0x140106b80`
- `WIN32K!W32GetUserSessionState` at `0x140106b9c`
- `WIN32K!W32GetUserSessionState` at `0x140106bb6`
- `WIN32K!W32GetUserSessionState` at `0x140106bf0`
- `WIN32K!W32GetUserSessionState` at `0x140106c11`
- `WIN32K!W32GetUserSessionState` at `0x140106c9e`
- `WIN32K!W32GetUserSessionState` at `0x14010694e`
- `WIN32K!W32GetUserSessionState` at `0x1401069a8`
- `WIN32K!W32GetUserSessionState` at `0x140106aa8`
- `WIN32K!W32GetUserSessionState` at `0x140106b4b`
- `WIN32K!W32GetUserSessionState` at `0x140106b69`
- `WIN32K!W32GetUserSessionState` at `0x140106b80`
- `WIN32K!W32GetUserSessionState` at `0x140106b9c`
- `WIN32K!W32GetUserSessionState` at `0x140106bb6`
- `WIN32K!W32GetUserSessionState` at `0x140106bf0`
- `WIN32K!W32GetUserSessionState` at `0x140106c11`
- `WIN32K!W32GetUserSessionState` at `0x140106c9e`

## string_xrefs

- `0x140106815`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\State`
- `0x1401068f2`: `\Registry\Machine\SYSTEM\Setup`
- `0x1401068a2`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x14010691b`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x140106d31`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\DPI`
- `0x140106867`: `IMAGE_STATE_COMPLETE`

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
  int (*v14)(void); // rax
  int (*v15)(void); // rax
  __int64 v16; // rcx
  int (*v17)(void); // rax
  int (__fastcall *v18)(__int64, bool); // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  struct _MDEV *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rbx
  __int64 CurrentThreadWin32Thread; // rbx
  int updated; // eax
  __int64 v52; // rcx
  __int64 v53; // r8
  bool v54; // bl
  __int64 v55; // rax
  int v56; // r8d
  int v57; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+A0h] [rbp-70h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-28h]
  int v62; // [rsp+F0h] [rbp-20h]
  __int64 v63; // [rsp+F8h] [rbp-18h]
  __int64 v64; // [rsp+100h] [rbp-10h]
  int v65; // [rsp+108h] [rbp-8h]
  __int64 v66; // [rsp+110h] [rbp+0h]
  int v67; // [rsp+118h] [rbp+8h]
  _DWORD v68[36]; // [rsp+120h] [rbp+10h] BYREF
  __int64 p_DestinationString; // [rsp+1C8h] [rbp+B8h] BYREF
  int v70; // [rsp+1D0h] [rbp+C0h] BYREF
  struct _MDEV *v71; // [rsp+1D8h] [rbp+C8h] BYREF

  QueryTable.Flags = 292;
  v70 = 0;
  QueryTable.Name = L"ImageState";
  v71 = 0;
  QueryTable.EntryContext = &DestinationString;
  QueryTable.QueryRoutine = 0;
  QueryTable.DefaultType = 16777217;
  QueryTable.DefaultData = 0;
  DestinationString = 0;
  QueryTable.DefaultLength = 0;
  String2 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
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
    QueryTable.EntryContext = &v70;
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
    memset(v68, 0, 0x60u);
    UserSessionState = W32GetUserSessionState(v6, v5, v7);
    if ( (int)DrvGetCurrentDpiInfoFromHDev(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 96LL) + 80LL),
                v68) < 0 )
      goto LABEL_5;
    if ( !(unsigned int)PreAllocateForPrimaryMonitorChange() )
    {
      v3 = -1073741823;
      goto LABEL_6;
    }
    v11 = 0;
    v12 = (unsigned int)(96 * v68[2] + 50);
    LODWORD(v9) = (1374389535 * (unsigned __int64)(unsigned int)v12) >> 32;
    v13 = (unsigned int)v12 / 0x64;
    *(_DWORD *)(W32GetUserSessionState(v12, v9, v10) + 68396) = 1;
    v14 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 2704LL);
    if ( v14 && v14() >= 0 )
      GetDpiSetting(1, &v70);
    if ( v70 != v13 )
    {
      v15 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 2736LL);
      if ( v15 )
      {
        if ( v15() >= 0 && (int)SetDpiSetting(v16, v13) >= 0 )
        {
          v17 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 2720LL);
          if ( v17 )
          {
            if ( v17() >= 0 )
            {
              v18 = *(int (__fastcall **)(__int64, bool))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 2728LL);
              if ( v18 )
              {
                if ( v18(1, v13 > 0x78) >= 0 )
                {
                  LOBYTE(p_DestinationString) = 0;
                  GreReinitializeDpiSetting();
                  v22 = W32GetUserSessionState(v20, v19, v21);
                  if ( (int)DrvSetDisplayConfig(
                              0,
                              0,
                              2191,
                              0,
                              0,
                              0,
                              0,
                              0,
                              *(struct _MDEV **)(*(_QWORD *)(v22 + 56744) + 16LL),
                              &v71,
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
                      v26 = *(_QWORD *)v71;
                      v30 = *(_QWORD *)(W32GetUserSessionState(v28, v27, v29) + 56744);
                      *(_QWORD *)(v30 + 40) = v26;
                      v31 = v71;
                      v34 = *(_QWORD *)(W32GetUserSessionState(v30, v32, v33) + 56744);
                      *(_QWORD *)(v34 + 16) = v31;
                      v37 = W32GetUserSessionState(v34, v35, v36);
                      GreUpdateSharedDevCaps(*(_QWORD *)(*(_QWORD *)(v37 + 56744) + 40LL));
                      v41 = *(_QWORD *)(W32GetUserSessionState(v39, v38, v40) + 19704);
                      *(_WORD *)(v41 + 6998) = v13;
                      v44 = W32GetUserSessionState(v41, v42, v43);
                      ++*(_WORD *)(*(_QWORD *)(v44 + 19704) + 7014LL);
                      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
                      v49 = CurrentProcessWin32Process;
                      if ( CurrentProcessWin32Process )
                      {
                        v47 = -*(_QWORD *)CurrentProcessWin32Process;
                        v46 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
                        v49 = v46 & CurrentProcessWin32Process;
                      }
                      v24 = *(_QWORD *)(W32GetUserSessionState(v47, v46, v48) + 19704);
                      *(_WORD *)(v49 + 272) = *(_WORD *)(v24 + 6998);
                    }
                    if ( !*(_QWORD *)W32GetUserSessionState(v24, v23, v25) || !IS_USERCRIT_OWNED_AT_ALL() )
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
                      v54 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        v55 = W32GetUserSessionState(v52, WPP_GLOBAL_Control, v53);
                        LOBYTE(v56) = v54;
                        LOBYTE(v57) = v2;
                        WPP_RECORDER_AND_TRACE_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v57,
                          v56,
                          *(_QWORD *)(v55 + 69136),
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
0x140106768  push    rbp
0x14010676a  push    rbx
0x14010676b  push    rsi
0x14010676c  push    rdi
0x14010676d  push    r12
0x14010676f  push    r14
0x140106771  push    r15
0x140106773  lea     rbp, [rsp-70h]
0x140106778  sub     rsp, 180h
0x14010677f  xor     r12d, r12d
0x140106782  mov     [rbp+0A0h+QueryTable.Flags], 124h
0x140106789  lea     rax, aImagestate; "ImageState"
0x140106790  mov     [rbp+0A0h+arg_10], r12d
0x140106797  mov     [rbp+0A0h+QueryTable.Name], rax
0x14010679b  mov     r15, rcx
0x14010679e  lea     rax, [rbp+0A0h+DestinationString]
0x1401067a2  mov     [rbp+0A0h+arg_18], r12
0x1401067a9  xorps   xmm0, xmm0
0x1401067ac  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x1401067b0  xorps   xmm1, xmm1
0x1401067b3  mov     [rbp+0A0h+QueryTable.QueryRoutine], r12
0x1401067b7  xor     edx, edx; SourceString
0x1401067b9  mov     [rbp+0A0h+QueryTable.DefaultType], 1000001h
0x1401067c0  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1401067c4  mov     [rbp+0A0h+QueryTable.DefaultData], r12
0x1401067c8  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1401067cc  mov     [rbp+0A0h+QueryTable.DefaultLength], r12d
0x1401067d0  movups  xmmword ptr [rbp+0A0h+String2.Length], xmm1
0x1401067d4  mov     [rbp+0A0h+var_C8], r12
0x1401067d8  mov     [rbp+0A0h+var_C0], r12d
0x1401067dc  mov     [rbp+0A0h+var_B8], r12
0x1401067e0  mov     [rbp+0A0h+var_B0], r12
0x1401067e4  mov     [rbp+0A0h+var_A8], r12d
0x1401067e8  mov     [rbp+0A0h+var_A0], r12
0x1401067ec  mov     [rbp+0A0h+var_98], r12d
0x1401067f0  call    cs:__imp_RtlInitUnicodeString
0x1401067f7  nop     dword ptr [rax+rax+00h]
0x1401067fc  lea     rax, [rbp+0A0h+DestinationString]
0x140106800  mov     [rsp+1B0h+Environment], r12; Environment
0x140106805  xor     r9d, r9d; Context
0x140106808  mov     [rbp+0A0h+arg_8], rax
0x14010680f  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x140106813  xor     ecx, ecx; RelativeTo
0x140106815  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x14010681c  call    cs:__imp_RtlQueryRegistryValues
0x140106823  nop     dword ptr [rax+rax+00h]
0x140106828  test    eax, eax
0x14010682a  js      loc_140106D28
0x140106830  lea     rdx, aImageStateSpec; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE"
0x140106837  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x14010683b  call    cs:__imp_RtlInitUnicodeString
0x140106842  nop     dword ptr [rax+rax+00h]
0x140106847  lea     edi, [r12+1]
0x14010684c  mov     r8b, dil; CaseInSensitive
0x14010684f  lea     rdx, [rbp+0A0h+String2]; String2
0x140106853  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x140106857  call    cs:__imp_RtlCompareUnicodeString
0x14010685e  nop     dword ptr [rax+rax+00h]
0x140106863  test    eax, eax
0x140106865  jz      short loc_1401068CB
0x140106867  lea     rdx, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x14010686e  lea     rcx, [rbp+0A0h+String2]; DestinationString
0x140106872  call    cs:__imp_RtlInitUnicodeString
0x140106879  nop     dword ptr [rax+rax+00h]
0x14010687e  mov     r8b, dil; CaseInSensitive
0x140106881  lea     rdx, [rbp+0A0h+String2]; String2
0x140106885  lea     rcx, [rbp+0A0h+DestinationString]; String1
0x140106889  call    cs:__imp_RtlCompareUnicodeString
0x140106890  nop     dword ptr [rax+rax+00h]
0x140106895  test    eax, eax
0x140106897  jnz     short loc_1401068B5
0x140106899  lea     r8, aOverrode; "Overrode"
0x1401068a0  xor     ecx, ecx; RelativeTo
0x1401068a2  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1401068a9  call    cs:__imp_RtlDeleteRegistryValue
0x1401068b0  nop     dword ptr [rax+rax+00h]
0x1401068b5  mov     ebx, r12d
0x1401068b8  lea     rcx, [rbp+0A0h+arg_8]
0x1401068bf  call    _SetDPIinSetup____2___CleanupUnicodeString___CleanupUnicodeString
0x1401068c4  mov     eax, ebx
0x1401068c6  jmp     loc_140106D5C
0x1401068cb  bts     [rbp+0A0h+QueryTable.Flags], 7
0x1401068d0  lea     rax, aUpgrade; "Upgrade"
0x1401068d7  mov     [rbp+0A0h+QueryTable.Name], rax
0x1401068db  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x1401068df  lea     rax, [rbp+0A0h+arg_10]
0x1401068e6  mov     [rsp+1B0h+Environment], r12; Environment
0x1401068eb  xor     r9d, r9d; Context
0x1401068ee  mov     [rbp+0A0h+QueryTable.EntryContext], rax
0x1401068f2  lea     rdx, aRegistryMachin_16; "\\Registry\\Machine\\SYSTEM\\Setup"
0x1401068f9  xor     ecx, ecx; RelativeTo
0x1401068fb  call    cs:__imp_RtlQueryRegistryValues
0x140106902  nop     dword ptr [rax+rax+00h]
0x140106907  test    eax, eax
0x140106909  jns     short loc_1401068B5
0x14010690b  lea     r8, aOverrode; "Overrode"
0x140106912  mov     [rsp+1B0h+Environment], r12; Environment
0x140106917  mov     [rbp+0A0h+QueryTable.Name], r8
0x14010691b  lea     rdx, aRegistryMachin_28; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x140106922  lea     r8, [rbp+0A0h+QueryTable]; QueryTable
0x140106926  xor     r9d, r9d; Context
0x140106929  xor     ecx, ecx; RelativeTo
0x14010692b  call    cs:__imp_RtlQueryRegistryValues
0x140106932  nop     dword ptr [rax+rax+00h]
0x140106937  test    eax, eax
0x140106939  jns     loc_1401068B5
0x14010693f  xor     edx, edx; Val
0x140106941  lea     rcx, [rbp+0A0h+var_90]; void *
0x140106945  lea     r8d, [rdx+60h]; Size
0x140106949  call    memset
0x14010694e  call    cs:__imp_W32GetUserSessionState
0x140106955  nop     dword ptr [rax+rax+00h]
0x14010695a  lea     rdx, [rbp+0A0h+var_90]
0x14010695e  mov     rcx, [rax+0DDA8h]
0x140106965  mov     rcx, [rcx+60h]
0x140106969  mov     rcx, [rcx+50h]
0x14010696d  call    DrvGetCurrentDpiInfoFromHDev
0x140106972  test    eax, eax
0x140106974  js      loc_1401068B5
0x14010697a  call    ?PreAllocateForPrimaryMonitorChange@@YAHXZ; PreAllocateForPrimaryMonitorChange(void)
0x14010697f  test    eax, eax
0x140106981  jnz     short loc_14010698D
0x140106983  mov     ebx, 0C0000001h
0x140106988  jmp     loc_1401068B8
0x14010698d  mov     eax, [rbp+0A0h+var_88]
0x140106990  mov     r14d, r12d
0x140106993  lea     ecx, [rax+rax*2]
0x140106996  mov     eax, 51EB851Fh
0x14010699b  shl     ecx, 5
0x14010699e  add     ecx, 32h ; '2'
0x1401069a1  mul     ecx
0x1401069a3  mov     esi, edx
0x1401069a5  shr     esi, 5
0x1401069a8  call    cs:__imp_W32GetUserSessionState
0x1401069af  nop     dword ptr [rax+rax+00h]
0x1401069b4  mov     [rax+10B2Ch], edi
0x1401069ba  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401069c1  nop     dword ptr [rax+rax+00h]
0x1401069c6  mov     rcx, [rax+30h]
0x1401069ca  mov     rax, [rcx+0A90h]
0x1401069d1  test    rax, rax
0x1401069d4  jz      short loc_1401069ED
0x1401069d6  call    _guard_dispatch_icall
0x1401069db  test    eax, eax
0x1401069dd  js      short loc_1401069ED
0x1401069df  lea     rdx, [rbp+0A0h+arg_10]
0x1401069e6  mov     ecx, edi
0x1401069e8  call    GetDpiSetting
0x1401069ed  cmp     [rbp+0A0h+arg_10], esi
0x1401069f3  jz      loc_140106CEC
0x1401069f9  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140106a00  nop     dword ptr [rax+rax+00h]
0x140106a05  mov     rcx, [rax+30h]
0x140106a09  mov     rax, [rcx+0AB0h]
0x140106a10  test    rax, rax
0x140106a13  jz      loc_140106CEC
0x140106a19  call    _guard_dispatch_icall
0x140106a1e  test    eax, eax
0x140106a20  js      loc_140106CEC
0x140106a26  mov     edx, esi
0x140106a28  call    SetDpiSetting
0x140106a2d  test    eax, eax
0x140106a2f  js      loc_140106CEC
0x140106a35  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140106a3c  nop     dword ptr [rax+rax+00h]
0x140106a41  mov     rcx, [rax+30h]
0x140106a45  mov     rax, [rcx+0AA0h]
0x140106a4c  test    rax, rax
0x140106a4f  jz      loc_140106CEC
0x140106a55  call    _guard_dispatch_icall
0x140106a5a  test    eax, eax
0x140106a5c  js      loc_140106CEC
0x140106a62  cmp     esi, 78h ; 'x'
0x140106a65  mov     ebx, r12d
0x140106a68  setnbe  bl
0x140106a6b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140106a72  nop     dword ptr [rax+rax+00h]
0x140106a77  mov     rcx, [rax+30h]
0x140106a7b  mov     rax, [rcx+0AA8h]
0x140106a82  test    rax, rax
0x140106a85  jz      loc_140106CEC
0x140106a8b  mov     edx, ebx
0x140106a8d  mov     ecx, edi
0x140106a8f  call    _guard_dispatch_icall
0x140106a94  test    eax, eax
0x140106a96  js      loc_140106CEC
0x140106a9c  mov     byte ptr [rbp+0A0h+arg_8], r12b
0x140106aa3  call    GreReinitializeDpiSetting
0x140106aa8  call    cs:__imp_W32GetUserSessionState
0x140106aaf  nop     dword ptr [rax+rax+00h]
0x140106ab4  mov     [rsp+1B0h+var_130], r12; __int64
0x140106abc  lea     rcx, [rbp+0A0h+arg_8]
0x140106ac3  mov     [rsp+1B0h+var_138], r15; __int64
0x140106ac8  xor     r9d, r9d; int
0x140106acb  mov     [rsp+1B0h+var_140], r12; __int64
0x140106ad0  xor     edx, edx; int
0x140106ad2  mov     rax, [rax+0DDA8h]
0x140106ad9  mov     r8d, 88Fh; int
0x140106adf  mov     [rsp+1B0h+var_148], r12; __int64
0x140106ae4  mov     [rsp+1B0h+var_150], rcx; __int64
0x140106ae9  lea     rcx, [rbp+0A0h+arg_18]
0x140106af0  mov     [rsp+1B0h+var_158], r12; __int64
0x140106af5  mov     rax, [rax+10h]
0x140106af9  mov     [rsp+1B0h+var_160], r12; __int64
0x140106afe  mov     [rsp+1B0h+var_168], rcx; struct _MDEV **
0x140106b03  xor     ecx, ecx; int
0x140106b05  mov     [rsp+1B0h+var_170], rax; struct _MDEV *
0x140106b0a  mov     [rsp+1B0h+var_178], r12; __int64
0x140106b0f  mov     [rsp+1B0h+var_180], r12; __int64
0x140106b14  mov     [rsp+1B0h+var_188], r12b; char
0x140106b19  mov     [rsp+1B0h+Environment], r12; __int64
0x140106b1e  call    DrvSetDisplayConfig
0x140106b23  test    eax, eax
0x140106b25  js      loc_140106CEC
0x140106b2b  cmp     byte ptr [rbp+0A0h+arg_8], r12b
0x140106b32  jnz     loc_140106C11
0x140106b38  mov     edx, edi
0x140106b3a  mov     ecx, esi
0x140106b3c  call    GreReinitializeStockFonts
0x140106b41  mov     rax, [rbp+0A0h+arg_18]
0x140106b48  mov     rbx, [rax]
0x140106b4b  call    cs:__imp_W32GetUserSessionState
0x140106b52  nop     dword ptr [rax+rax+00h]
0x140106b57  mov     rcx, [rax+0DDA8h]
0x140106b5e  mov     [rcx+28h], rbx
0x140106b62  mov     rbx, [rbp+0A0h+arg_18]
0x140106b69  call    cs:__imp_W32GetUserSessionState
0x140106b70  nop     dword ptr [rax+rax+00h]
0x140106b75  mov     rcx, [rax+0DDA8h]
0x140106b7c  mov     [rcx+10h], rbx
0x140106b80  call    cs:__imp_W32GetUserSessionState
0x140106b87  nop     dword ptr [rax+rax+00h]
0x140106b8c  mov     rcx, [rax+0DDA8h]
0x140106b93  mov     rcx, [rcx+28h]; P4
0x140106b97  call    GreUpdateSharedDevCaps
0x140106b9c  call    cs:__imp_W32GetUserSessionState
0x140106ba3  nop     dword ptr [rax+rax+00h]
0x140106ba8  mov     rcx, [rax+4CF8h]
0x140106baf  mov     [rcx+1B56h], si
0x140106bb6  call    cs:__imp_W32GetUserSessionState
0x140106bbd  nop     dword ptr [rax+rax+00h]
0x140106bc2  mov     rcx, [rax+4CF8h]
0x140106bc9  add     [rcx+1B66h], di
0x140106bd0  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140106bd7  nop     dword ptr [rax+rax+00h]
0x140106bdc  mov     rbx, rax
0x140106bdf  test    rax, rax
0x140106be2  jz      short loc_140106BF0
0x140106be4  mov     rcx, [rax]
0x140106be7  neg     rcx
0x140106bea  sbb     rdx, rdx
0x140106bed  and     rbx, rdx
0x140106bf0  call    cs:__imp_W32GetUserSessionState
0x140106bf7  nop     dword ptr [rax+rax+00h]
0x140106bfc  mov     rcx, [rax+4CF8h]
0x140106c03  movzx   eax, word ptr [rcx+1B56h]
0x140106c0a  mov     [rbx+110h], ax
0x140106c11  call    cs:__imp_W32GetUserSessionState
0x140106c18  nop     dword ptr [rax+rax+00h]
0x140106c1d  cmp     [rax], r12
0x140106c20  jz      loc_140106D07
0x140106c26  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x140106c2b  test    al, al
0x140106c2d  jz      loc_140106D07
0x140106c33  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140106c3a  nop     dword ptr [rax+rax+00h]
0x140106c3f  mov     rbx, rax
0x140106c42  add     [rax+1Ch], edi
0x140106c45  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x140106c4a  dec     dword ptr [rbx+1Ch]
0x140106c4d  mov     r14d, eax
0x140106c50  mov     cs:?gbSetDPIinSetupChangedDisplaySettings@@3_NA, dil; bool gbSetDPIinSetupChangedDisplaySettings
0x140106c57  test    eax, eax
0x140106c59  jns     loc_140106CEC
0x140106c5f  mov     rdx, cs:WPP_GLOBAL_Control
0x140106c66  lea     rax, WPP_GLOBAL_Control
0x140106c6d  cmp     rdx, rax
0x140106c70  jz      short loc_140106C81
0x140106c72  test    dword ptr [rdx+2Ch], 2000h
0x140106c79  jz      short loc_140106C81
0x140106c7b  cmp     byte ptr [rdx+29h], 2
0x140106c7f  jnb     short loc_140106C84
0x140106c81  mov     dil, r12b
0x140106c84  lea     rax, WPP_RECORDER_INITIALIZED
0x140106c8b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140106c92  setnz   bl
0x140106c95  test    dil, dil
0x140106c98  jnz     short loc_140106C9E
0x140106c9a  test    bl, bl
0x140106c9c  jz      short loc_140106CEC
0x140106c9e  call    cs:__imp_W32GetUserSessionState
0x140106ca5  nop     dword ptr [rax+rax+00h]
0x140106caa  mov     rcx, cs:WPP_GLOBAL_Control
0x140106cb1  mov     r8b, bl
0x140106cb4  mov     dword ptr [rsp+1B0h+var_170], r14d
0x140106cb9  mov     dl, dil
0x140106cbc  mov     r9, [rax+10E10h]
0x140106cc3  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x140106cca  mov     rcx, [rcx+18h]
0x140106cce  mov     [rsp+1B0h+var_178], rax
  ... truncated ...
```
