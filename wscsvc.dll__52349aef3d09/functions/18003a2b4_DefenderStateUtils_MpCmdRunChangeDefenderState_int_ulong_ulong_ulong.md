# DefenderStateUtils::MpCmdRunChangeDefenderState(int,ulong,ulong,ulong *)

- ea: `0x18003a2b4`
- end: `0x18003a58b`
- name: `?MpCmdRunChangeDefenderState@DefenderStateUtils@@YAJHKKPEAK@Z`
- size: `727`
- prototype: `__int64 __fastcall(DefenderStateUtils *this, __int64, unsigned int, DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002400c`

## callees

- `0x180006a70`
- `0x180008e48`
- `0x1800202e8`
- `0x180029158`
- `0x180029e74`
- `0x180031a70`
- `0x18003a040`
- `0x18003a2b4`
- `0x18003ea84`
- `0x18003fbf2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a4e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a4e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a52e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003a4f2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003a4f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003a4d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003a4d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a514`

## pseudocode

```c
__int64 __fastcall DefenderStateUtils::MpCmdRunChangeDefenderState(
        DefenderStateUtils *this,
        __int64 a2,
        unsigned int a3,
        DWORD *a4)
{
  unsigned int v6; // r13d
  int v7; // edi
  unsigned __int16 **v8; // rdx
  int inited; // eax
  unsigned int v11; // ebx
  unsigned __int16 *v12; // rbx
  const wchar_t *v13; // rax
  int v14; // eax
  unsigned int v15; // r14d
  void *v16; // rcx
  WCHAR *v17; // rdi
  DWORD LastError; // eax
  void *Block; // [rsp+50h] [rbp-79h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-71h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-59h] BYREF

  v6 = a2;
  v7 = (int)this;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::GetImpl'::`2'::impl,
    a2);
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, 2147942487LL);
    }
    return 2147942487LL;
  }
  Block = 0;
  inited = DefenderStateUtils::InitDefenderInstallLocationPath((DefenderStateUtils *)&Block, v8);
  v11 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids,
        (unsigned int)inited);
    }
    if ( Block )
      operator delete(Block);
    return v11;
  }
  *a4 = 0;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 104;
  v12 = (unsigned __int16 *)Block;
  if ( !Block )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids);
    }
    return 2147942487LL;
  }
  Block = 0;
  v13 = L"-wdenable";
  if ( !v7 )
    v13 = L"-wddisable";
  v14 = CommonUtil::NewSprintfW((CommonUtil *)&Block, (unsigned __int16 **)L"%ls\\%ls %ls", v12, L"MpCmdRun.exe", v13);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v17 = (WCHAR *)Block;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, Block);
    }
    if ( CreateProcessW(0, v17, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      GetExitCodeProcess(ProcessInformation.hProcess, a4);
      SqmWriteDefenderAction(v6, a3, *a4);
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids, LastError);
      }
      v15 = -2147467259;
    }
    if ( !v17 )
      goto LABEL_38;
    v16 = v17;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids,
        (unsigned int)v14);
    }
    v16 = Block;
    if ( !Block )
      goto LABEL_38;
  }
  operator delete(v16);
LABEL_38:
  if ( v12 )
    operator delete(v12);
  return v15;
}

```

## disassembly

```asm
0x18003a2b4  push    rbp
0x18003a2b6  push    rbx
0x18003a2b7  push    rsi
0x18003a2b8  push    rdi
0x18003a2b9  push    r12
0x18003a2bb  push    r13
0x18003a2bd  push    r14
0x18003a2bf  push    r15
0x18003a2c1  lea     rbp, [rsp-1Fh]
0x18003a2c6  sub     rsp, 0E8h
0x18003a2cd  mov     r15, r9
0x18003a2d0  mov     r12d, r8d
0x18003a2d3  mov     r13d, edx
0x18003a2d6  mov     edi, ecx
0x18003a2d8  mov     r14b, 1
0x18003a2db  mov     dl, r14b
0x18003a2de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::GetImpl(void)'::`2'::impl
0x18003a2e5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCInvokesLatestMpCmdRun>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003a2ea  xor     esi, esi
0x18003a2ec  test    r15, r15
0x18003a2ef  jnz     short loc_18003A32E
0x18003a2f1  lea     rsi, WPP_GLOBAL_Control
0x18003a2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2ff  cmp     rcx, rsi
0x18003a302  jz      short loc_18003A324
0x18003a304  test    [rcx+1Ch], r14b
0x18003a308  jz      short loc_18003A324
0x18003a30a  lea     edx, [r15+10h]
0x18003a30e  mov     r9d, 80070057h
0x18003a314  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a31b  mov     rcx, [rcx+10h]
0x18003a31f  call    WPP_SF_d
0x18003a324  mov     eax, 80070057h
0x18003a329  jmp     loc_18003A577
0x18003a32e  mov     [rbp+57h+Block], rsi
0x18003a332  lea     rcx, [rbp+57h+Block]; this
0x18003a336  call    ?InitDefenderInstallLocationPath@DefenderStateUtils@@YAJPEAPEAG@Z; DefenderStateUtils::InitDefenderInstallLocationPath(ushort * *)
0x18003a33b  mov     ebx, eax
0x18003a33d  test    eax, eax
0x18003a33f  jns     short loc_18003A388
0x18003a341  lea     rsi, WPP_GLOBAL_Control
0x18003a348  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a34f  cmp     rcx, rsi
0x18003a352  jz      short loc_18003A373
0x18003a354  test    [rcx+1Ch], r14b
0x18003a358  jz      short loc_18003A373
0x18003a35a  mov     edx, 11h
0x18003a35f  mov     r9d, eax
0x18003a362  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a369  mov     rcx, [rcx+10h]
0x18003a36d  call    WPP_SF_d
0x18003a372  nop
0x18003a373  mov     rcx, [rbp+57h+Block]; Block
0x18003a377  test    rcx, rcx
0x18003a37a  jz      short loc_18003A381
0x18003a37c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a381  mov     eax, ebx
0x18003a383  jmp     loc_18003A577
0x18003a388  mov     [r15], esi
0x18003a38b  xor     edx, edx; Val
0x18003a38d  lea     r8d, [rdx+64h]; Size
0x18003a391  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18003a395  call    memset_0
0x18003a39a  xorps   xmm0, xmm0
0x18003a39d  xor     eax, eax
0x18003a39f  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18003a3a3  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18003a3a7  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18003a3ae  mov     rbx, [rbp+57h+Block]
0x18003a3b2  test    rbx, rbx
0x18003a3b5  jnz     short loc_18003A3E9
0x18003a3b7  lea     rsi, WPP_GLOBAL_Control
0x18003a3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3c5  cmp     rcx, rsi
0x18003a3c8  jz      short loc_18003A3E4
0x18003a3ca  test    [rcx+1Ch], r14b
0x18003a3ce  jz      short loc_18003A3E4
0x18003a3d0  lea     edx, [rax+12h]
0x18003a3d3  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a3da  mov     rcx, [rcx+10h]
0x18003a3de  call    WPP_SF_
0x18003a3e3  nop
0x18003a3e4  jmp     loc_18003A324
0x18003a3e9  mov     [rbp+57h+Block], rsi
0x18003a3ed  lea     rcx, aWddisable; "-wddisable"
0x18003a3f4  lea     rax, aWdenable; "-wdenable"
0x18003a3fb  test    edi, edi
0x18003a3fd  cmovz   rax, rcx
0x18003a401  mov     qword ptr [rsp+120h+bInheritHandles], rax
0x18003a406  lea     r9, aMpcmdrunExe; "MpCmdRun.exe"
0x18003a40d  mov     r8, rbx; unsigned __int16 *
0x18003a410  lea     rdx, aLsLsLs_0; "%ls\\%ls %ls"
0x18003a417  lea     rcx, [rbp+57h+Block]; this
0x18003a41b  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18003a420  mov     r14d, eax
0x18003a423  test    eax, eax
0x18003a425  jns     short loc_18003A46A
0x18003a427  lea     rsi, WPP_GLOBAL_Control
0x18003a42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a435  cmp     rcx, rsi
0x18003a438  jz      short loc_18003A458
0x18003a43a  test    byte ptr [rcx+1Ch], 1
0x18003a43e  jz      short loc_18003A458
0x18003a440  mov     edx, 13h
0x18003a445  mov     r9d, eax
0x18003a448  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a44f  mov     rcx, [rcx+10h]
0x18003a453  call    WPP_SF_d
0x18003a458  mov     rcx, [rbp+57h+Block]
0x18003a45c  test    rcx, rcx
0x18003a45f  jz      loc_18003A567
0x18003a465  jmp     loc_18003A561
0x18003a46a  lea     rsi, WPP_GLOBAL_Control
0x18003a471  mov     rdi, [rbp+57h+Block]
0x18003a475  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a47c  cmp     rcx, rsi
0x18003a47f  jz      short loc_18003A49F
0x18003a481  test    byte ptr [rcx+1Ch], 4
0x18003a485  jz      short loc_18003A49F
0x18003a487  mov     edx, 14h
0x18003a48c  mov     r9, rdi
0x18003a48f  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a496  mov     rcx, [rcx+10h]
0x18003a49a  call    WPP_SF_S
0x18003a49f  lea     rax, [rbp+57h+ProcessInformation]
0x18003a4a3  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x18003a4a8  lea     rax, [rbp+57h+StartupInfo]
0x18003a4ac  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x18003a4b1  xor     eax, eax
0x18003a4b3  mov     [rsp+120h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18003a4b8  mov     [rsp+120h+lpEnvironment], rax; lpEnvironment
0x18003a4bd  mov     [rsp+120h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18003a4c5  mov     [rsp+120h+bInheritHandles], eax; bInheritHandles
0x18003a4c9  xor     r9d, r9d; lpThreadAttributes
0x18003a4cc  xor     r8d, r8d; lpProcessAttributes
0x18003a4cf  mov     rdx, rdi; lpCommandLine
0x18003a4d2  xor     ecx, ecx; lpApplicationName
0x18003a4d4  call    cs:__imp_CreateProcessW
0x18003a4da  test    eax, eax
0x18003a4dc  jz      short loc_18003A51C
0x18003a4de  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a4e1  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18003a4e5  call    cs:__imp_WaitForSingleObject
0x18003a4eb  mov     rdx, r15; lpExitCode
0x18003a4ee  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18003a4f2  call    cs:__imp_GetExitCodeProcess
0x18003a4f8  mov     r8d, [r15]; unsigned int
0x18003a4fb  mov     edx, r12d; unsigned int
0x18003a4fe  mov     ecx, r13d; unsigned int
0x18003a501  call    ?SqmWriteDefenderAction@@YAXKKK@Z; SqmWriteDefenderAction(ulong,ulong,ulong)
0x18003a506  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18003a50a  call    cs:__imp_CloseHandle
0x18003a510  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18003a514  call    cs:__imp_CloseHandle
0x18003a51a  jmp     short loc_18003A559
0x18003a51c  mov     rax, cs:WPP_GLOBAL_Control
0x18003a523  cmp     rax, rsi
0x18003a526  jz      short loc_18003A553
0x18003a528  test    byte ptr [rax+1Ch], 1
0x18003a52c  jz      short loc_18003A553
0x18003a52e  call    cs:__imp_GetLastError
0x18003a534  mov     edx, 15h
0x18003a539  mov     r9d, eax
0x18003a53c  lea     r8, WPP_e31d6d5b41b63fce4d9413d7ef1fd9ec_Traceguids
0x18003a543  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a54a  mov     rcx, [rcx+10h]
0x18003a54e  call    WPP_SF_d
0x18003a553  mov     r14d, 80004005h
0x18003a559  test    rdi, rdi
0x18003a55c  jz      short loc_18003A567
0x18003a55e  mov     rcx, rdi; Block
0x18003a561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a566  nop
0x18003a567  test    rbx, rbx
0x18003a56a  jz      short loc_18003A574
0x18003a56c  mov     rcx, rbx; Block
0x18003a56f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a574  mov     eax, r14d
0x18003a577  add     rsp, 0E8h
0x18003a57e  pop     r15
0x18003a580  pop     r14
0x18003a582  pop     r13
0x18003a584  pop     r12
0x18003a586  pop     rdi
0x18003a587  pop     rsi
0x18003a588  pop     rbx
0x18003a589  pop     rbp
0x18003a58a  retn
```
