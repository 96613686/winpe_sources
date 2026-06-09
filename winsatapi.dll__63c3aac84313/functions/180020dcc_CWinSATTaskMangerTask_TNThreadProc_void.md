# CWinSATTaskMangerTask::TNThreadProc(void)

- ea: `0x180020dcc`
- end: `0x1800211a0`
- name: `?TNThreadProc@CWinSATTaskMangerTask@@AEAAKXZ`
- size: `980`
- prototype: `unsigned int __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800211b0`

## callees

- `0x18000e6ac`
- `0x18001c414`
- `0x18001d79c`
- `0x180020428`
- `0x180020830`
- `0x1800209fc`
- `0x180020dcc`
- `0x1800211f8`
- `0x180021294`
- `0x1800213d0`
- `0x1800214fc`
- `0x1800216b0`
- `0x18002177c`
- `0x180023a94`
- `0x180024d48`
- `0x18002be4c`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180020f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f3e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020f08`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020f08`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020eb4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180020eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ee7`
- `ntdll!ShipAssert` at `0x180020fb7`
- `ntdll!ShipAssert` at `0x180020fb7`

## string_xrefs

- `0x180020df6`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020dea`: `Starting task thread`
- `0x180020e49`: `Task     thread is running as ADMIN`
- `0x180020e6b`: `Task     thread is *NOT* running as ADMIN`
- `0x180020e9f`: `Starting task thread`
- `0x18002115d`: `The TaskScheduler Task unexpectedly terminated on last run.  WinSAT has possibly bluescreened the machine.`
- `0x180021085`: `cannot write %s to the registry`
- `0x1800210a4`: `WinSAT was cancelled in the idle task`
- `0x1800210ce`: `WinSAT completed with an errror`
- `0x180020f15`: `complted successfully`
- `0x180020f22`: `WinSAT Task Manger task  %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinSATTaskMangerTask::TNThreadProc(CWinSATTaskMangerTask *this)
{
  void *v2; // rdx
  char v3; // r15
  void (__fastcall *v4)(__int64 *, __int64, __int64); // rax
  __int64 v5; // r8
  HRESULT v6; // eax
  CWinSATTaskMangerTask *v7; // rcx
  int ShouldTryRunWinSAT; // edi
  const char *v9; // r9
  unsigned int *v11; // r14
  CWinSATTaskMangerTask *v12; // rcx
  unsigned int v13; // edx
  CWinSATTaskMangerTask *v14; // rcx
  CWinSATTaskMangerTask *v15; // rcx
  __int64 v16; // rcx
  CWinSATTaskMangerTask *v17; // rcx
  void (__fastcall *v18)(__int64 *, __int64, __int64); // rax
  unsigned int v19; // edx
  bool updated; // cl
  int v21; // eax
  char v22; // cl
  void (__fastcall *v23)(__int64 *, __int64, __int64); // rax
  bool v24; // [rsp+80h] [rbp+40h] BYREF
  bool v25; // [rsp+88h] [rbp+48h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+58h] BYREF

  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 338, "Starting task thread");
  v24 = 0;
  v3 = 1;
  if ( (unsigned int)IsUserAdmin(&v24, v2) )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 344, "Cannot determine if running as admin...");
    v4 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 0;
  }
  else if ( v24 )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 348, "Task     thread is running as ADMIN");
    v4 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 1;
  }
  else
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 351, "Task     thread is *NOT* running as ADMIN");
    v4 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
    if ( !v4 )
      goto LABEL_10;
    v5 = 2;
  }
  v4(qword_1800487B0, 10268, v5);
LABEL_10:
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Starting task thread");
  v6 = CoInitializeEx(0, 0);
  ShouldTryRunWinSAT = v6;
  if ( v6 < 0 )
  {
    v3 = 0;
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 360, "CoInitializeEx failed: %x\n", v6);
LABEL_12:
    ShouldTryRunWinSAT = -2147467259;
    goto LABEL_13;
  }
  if ( !bstrString
    || (ShouldTryRunWinSAT = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR))(**((_QWORD **)this + 9) + 24LL))(
                               *((_QWORD *)this + 9),
                               0,
                               bstrString),
        ShouldTryRunWinSAT >= 0) )
  {
    ExitCode = 0;
    v24 = 0;
    v25 = 0;
    v11 = (unsigned int *)((char *)this + 108);
    if ( !CWinSATTaskMangerTask::ReadErrorCountRegKey(v7, (unsigned int *)this + 27) )
      goto LABEL_12;
    if ( *v11 != 4 )
    {
      v13 = *v11 + 1;
      *v11 = v13;
      if ( v13 > 3 )
        ShipAssert(96257);
      if ( !CWinSATTaskMangerTask::UpdateErrorCountRegKey(v12, 4u) )
        goto LABEL_12;
      ShouldTryRunWinSAT = CWinSATTaskMangerTask::NeedToRunWinSAT(this, &v24);
      if ( ShouldTryRunWinSAT >= 0 )
      {
        if ( !v24 )
        {
          v24 = 0;
          if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v24) && !v24 )
            CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(this);
          goto LABEL_46;
        }
        ShouldTryRunWinSAT = CWinSATTaskMangerTask::ShouldTryRunWinSAT(v14, &v25);
        if ( ShouldTryRunWinSAT >= 0 )
        {
          if ( !v25 )
          {
LABEL_46:
            if ( *v11 )
              v19 = *v11 - 1;
            else
              v19 = 0;
            updated = CWinSATTaskMangerTask::UpdateErrorCountRegKey(v15, v19);
            v21 = ShouldTryRunWinSAT;
            if ( !updated )
              v21 = -2147467259;
            ShouldTryRunWinSAT = v21;
            goto LABEL_13;
          }
          ShouldTryRunWinSAT = CWinSATTaskMangerTask::DoRunWinSAT(this, &ExitCode);
          if ( ShouldTryRunWinSAT >= 0 )
          {
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 435, "WinSatExitValue = %u", ExitCode);
            if ( (unsigned int)RegHelper::WriteDWORDValue(v16, L"LastWinSATIdleRunExitValue", ExitCode) )
              Record_Win32Error_w(
                "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
                (char)L"LastWinSATIdleRunExitValue");
            if ( ExitCode == 3 )
            {
              Log_Text_F(
                "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
                449,
                "WinSAT was cancelled in the idle task");
              v24 = 0;
              CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v24);
LABEL_45:
              *v11 = 0;
              goto LABEL_46;
            }
            if ( !ExitCode )
            {
              CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(v17);
              goto LABEL_45;
            }
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 469, "WinSAT completed with an errror");
            v24 = 0;
            if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v24) && !v24 )
            {
              v18 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 20);
              if ( v18 )
                v18(qword_1800487B0, 6438, 1);
            }
            ShouldTryRunWinSAT = -2147467259;
          }
        }
      }
      CWinSATTaskMangerTask::CommitErrorCount(this);
      goto LABEL_13;
    }
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      390,
      "The TaskScheduler Task unexpectedly terminated on last run.  WinSAT has possibly bluescreened the machine.");
    EnableDisableWinSATTask(v22);
    v23 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
    if ( v23 )
      v23(qword_1800487B0, 10270, 1);
  }
LABEL_13:
  CloseHandle(*((HANDLE *)this + 14));
  *((_QWORD *)this + 14) = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
    *((_QWORD *)this + 9),
    (unsigned int)ShouldTryRunWinSAT);
  if ( v3 )
    CoUninitialize();
  v9 = "complted successfully";
  if ( ShouldTryRunWinSAT < 0 )
    v9 = "failed";
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 515, "WinSAT Task Manger task  %s", v9);
  SysFreeString(bstrString);
  return (unsigned int)ShouldTryRunWinSAT >> 31;
}

```

## disassembly

```asm
0x180020dcc  push    rbp
0x180020dce  push    rsi
0x180020dcf  push    rdi
0x180020dd0  push    r12
0x180020dd2  push    r13
0x180020dd4  push    r14
0x180020dd6  push    r15
0x180020dd8  mov     rbp, rsp
0x180020ddb  sub     rsp, 40h
0x180020ddf  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180020de7  mov     rsi, rcx
0x180020dea  lea     r8, aStartingTaskTh; "Starting task thread"
0x180020df1  mov     edx, 152h
0x180020df6  lea     r13, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020dfd  mov     rcx, r13
0x180020e00  call    Log_Text_F
0x180020e05  xor     r12d, r12d
0x180020e08  mov     [rbp+arg_0], r12b
0x180020e0c  lea     rcx, [rbp+arg_0]; bool *
0x180020e10  call    ?IsUserAdmin@@YAKAEA_NPEAX@Z; IsUserAdmin(bool &,void *)
0x180020e15  lea     r15d, [r12+1]
0x180020e1a  mov     rcx, r13
0x180020e1d  test    eax, eax
0x180020e1f  jz      short loc_180020E43
0x180020e21  lea     r8, aCannotDetermin_1; "Cannot determine if running as admin..."
0x180020e28  mov     edx, 158h
0x180020e2d  call    Log_Text_F
0x180020e32  mov     rax, [rsi+88h]
0x180020e39  test    rax, rax
0x180020e3c  jz      short loc_180020E9F
0x180020e3e  xor     r8d, r8d
0x180020e41  jmp     short loc_180020E8E
0x180020e43  cmp     [rbp+arg_0], r12b
0x180020e47  jz      short loc_180020E6B
0x180020e49  lea     r8, aTaskThreadIsRu; "Task     thread is running as ADMIN"
0x180020e50  mov     edx, 15Ch
0x180020e55  call    Log_Text_F
0x180020e5a  mov     rax, [rsi+88h]
0x180020e61  test    rax, rax
0x180020e64  jz      short loc_180020E9F
0x180020e66  mov     r8d, r15d
0x180020e69  jmp     short loc_180020E8E
0x180020e6b  lea     r8, aTaskThreadIsNo; "Task     thread is *NOT* running as ADM"...
0x180020e72  mov     edx, 15Fh
0x180020e77  call    Log_Text_F
0x180020e7c  mov     rax, [rsi+88h]
0x180020e83  test    rax, rax
0x180020e86  jz      short loc_180020E9F
0x180020e88  mov     r8d, 2
0x180020e8e  mov     edx, 281Ch
0x180020e93  lea     rcx, qword_1800487B0
0x180020e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e9f  lea     rdx, aStartingTaskTh_0; "Starting task thread"
0x180020ea6  lea     rcx, [rbp+bstrString]; this
0x180020eaa  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180020eaf  nop
0x180020eb0  xor     edx, edx; dwCoInit
0x180020eb2  xor     ecx, ecx; pvReserved
0x180020eb4  call    cs:__imp_CoInitializeEx
0x180020eba  mov     edi, eax
0x180020ebc  test    eax, eax
0x180020ebe  jns     loc_180020F56
0x180020ec4  mov     r15b, r12b
0x180020ec7  mov     r9d, eax
0x180020eca  lea     r8, aCoinitializeex; "CoInitializeEx failed: %x\n"
0x180020ed1  mov     edx, 168h
0x180020ed6  mov     rcx, r13
0x180020ed9  call    Log_Text_F
0x180020ede  mov     edi, 80004005h
0x180020ee3  mov     rcx, [rsi+70h]; hObject
0x180020ee7  call    cs:__imp_CloseHandle
0x180020eed  mov     [rsi+70h], r12
0x180020ef1  mov     rcx, [rsi+48h]
0x180020ef5  mov     rax, [rcx]
0x180020ef8  mov     edx, edi
0x180020efa  mov     rax, [rax+20h]
0x180020efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f03  test    r15b, r15b
0x180020f06  jz      short loc_180020F0E
0x180020f08  call    cs:__imp_CoUninitialize
0x180020f0e  lea     rax, aFailed; "failed"
0x180020f15  lea     r9, aCompltedSucces; "complted successfully"
0x180020f1c  test    edi, edi
0x180020f1e  cmovs   r9, rax
0x180020f22  lea     r8, aWinsatTaskMang; "WinSAT Task Manger task  %s"
0x180020f29  mov     edx, 203h
0x180020f2e  mov     rcx, r13
0x180020f31  call    Log_Text_F
0x180020f36  nop
0x180020f37  shr     edi, 1Fh
0x180020f3a  mov     rcx, [rbp+bstrString]; bstrString
0x180020f3e  call    cs:__imp_SysFreeString
0x180020f44  mov     eax, edi
0x180020f46  add     rsp, 40h
0x180020f4a  pop     r15
0x180020f4c  pop     r14
0x180020f4e  pop     r13
0x180020f50  pop     r12
0x180020f52  pop     rdi
0x180020f53  pop     rsi
0x180020f54  pop     rbp
0x180020f55  retn
0x180020f56  cmp     [rbp+bstrString], r12
0x180020f5a  jz      short loc_180020F7C
0x180020f5c  mov     rcx, [rsi+48h]
0x180020f60  mov     rax, [rcx]
0x180020f63  xor     edx, edx
0x180020f65  mov     r8, [rbp+bstrString]
0x180020f69  mov     rax, [rax+18h]
0x180020f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f72  mov     edi, eax
0x180020f74  test    eax, eax
0x180020f76  js      loc_180020EE3
0x180020f7c  mov     [rbp+ExitCode], r12d
0x180020f80  mov     [rbp+arg_0], r12b
0x180020f84  mov     [rbp+arg_8], r12b
0x180020f88  lea     r14, [rsi+6Ch]
0x180020f8c  mov     rdx, r14; unsigned int *
0x180020f8f  call    ?ReadErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NAEAK@Z; CWinSATTaskMangerTask::ReadErrorCountRegKey(ulong &)
0x180020f94  test    al, al
0x180020f96  jz      loc_180020EDE
0x180020f9c  mov     edx, [r14]
0x180020f9f  cmp     edx, 4
0x180020fa2  jz      loc_18002115D
0x180020fa8  inc     edx
0x180020faa  mov     [r14], edx
0x180020fad  cmp     edx, 3
0x180020fb0  jbe     short loc_180020FBD
0x180020fb2  mov     ecx, 17801h
0x180020fb7  call    cs:__imp_ShipAssert
0x180020fbd  mov     edx, 4; unsigned int
0x180020fc2  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x180020fc7  test    al, al
0x180020fc9  jz      loc_180020EDE
0x180020fcf  lea     rdx, [rbp+arg_0]; bool *
0x180020fd3  mov     rcx, rsi; this
0x180020fd6  call    ?NeedToRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z; CWinSATTaskMangerTask::NeedToRunWinSAT(bool &)
0x180020fdb  mov     edi, eax
0x180020fdd  test    eax, eax
0x180020fdf  js      loc_180021121
0x180020fe5  cmp     [rbp+arg_0], r12b
0x180020fe9  jnz     short loc_18002101A
0x180020feb  mov     [rbp+arg_0], r12b
0x180020fef  lea     rdx, [rbp+arg_0]; bool *
0x180020ff3  mov     rcx, rsi; this
0x180020ff6  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x180020ffb  test    al, al
0x180020ffd  jz      loc_180021136
0x180021003  cmp     [rbp+arg_0], r12b
0x180021007  jnz     loc_180021136
0x18002100d  mov     rcx, rsi; this
0x180021010  call    ?DoMarkAsCompleteOnDemdand@CWinSATTaskMangerTask@@AEAAXXZ; CWinSATTaskMangerTask::DoMarkAsCompleteOnDemdand(void)
0x180021015  jmp     loc_180021136
0x18002101a  lea     rdx, [rbp+arg_8]; bool *
0x18002101e  call    ?ShouldTryRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z; CWinSATTaskMangerTask::ShouldTryRunWinSAT(bool &)
0x180021023  mov     edi, eax
0x180021025  test    eax, eax
0x180021027  js      loc_180021121
0x18002102d  cmp     [rbp+arg_8], r12b
0x180021031  jz      loc_180021136
0x180021037  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18002103b  mov     rcx, rsi; this
0x18002103e  call    ?DoRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEAK@Z; CWinSATTaskMangerTask::DoRunWinSAT(ulong &)
0x180021043  mov     edi, eax
0x180021045  test    eax, eax
0x180021047  js      loc_180021121
0x18002104d  mov     r9d, [rbp+ExitCode]
0x180021051  lea     r8, aWinsatexitvalu; "WinSatExitValue = %u"
0x180021058  mov     edx, 1B3h
0x18002105d  mov     rcx, r13
0x180021060  call    Log_Text_F
0x180021065  mov     r8d, [rbp+ExitCode]
0x180021069  lea     rdx, aLastwinsatidle; "LastWinSATIdleRunExitValue"
0x180021070  call    ?WriteDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGK@Z; RegHelper::WriteDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong)
0x180021075  test    eax, eax
0x180021077  jz      short loc_18002109C
0x180021079  lea     rcx, aLastwinsatidle; "LastWinSATIdleRunExitValue"
0x180021080  mov     qword ptr [rsp+40h+var_20], rcx; char
0x180021085  lea     r9, aCannotWriteSTo_0; "cannot write %s to the registry"
0x18002108c  mov     r8d, eax
0x18002108f  mov     edx, 1BAh
0x180021094  mov     rcx, r13; char *
0x180021097  call    Record_Win32Error_w
0x18002109c  mov     eax, [rbp+ExitCode]
0x18002109f  cmp     eax, 3
0x1800210a2  jnz     short loc_1800210CA
0x1800210a4  lea     r8, aWinsatWasCance; "WinSAT was cancelled in the idle task"
0x1800210ab  mov     edx, 1C1h
0x1800210b0  mov     rcx, r13
0x1800210b3  call    Log_Text_F
0x1800210b8  mov     [rbp+arg_0], r12b
0x1800210bc  lea     rdx, [rbp+arg_0]; bool *
0x1800210c0  mov     rcx, rsi; this
0x1800210c3  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800210c8  jmp     short loc_180021133
0x1800210ca  test    eax, eax
0x1800210cc  jz      short loc_18002112E
0x1800210ce  lea     r8, aWinsatComplete; "WinSAT completed with an errror"
0x1800210d5  mov     edx, 1D5h
0x1800210da  mov     rcx, r13
0x1800210dd  call    Log_Text_F
0x1800210e2  mov     [rbp+arg_0], r12b
0x1800210e6  lea     rdx, [rbp+arg_0]; bool *
0x1800210ea  mov     rcx, rsi; this
0x1800210ed  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x1800210f2  test    al, al
0x1800210f4  jz      short loc_18002111C
0x1800210f6  cmp     [rbp+arg_0], r12b
0x1800210fa  jnz     short loc_18002111C
0x1800210fc  mov     rax, [rsi+0A0h]
0x180021103  test    rax, rax
0x180021106  jz      short loc_18002111C
0x180021108  mov     r8d, r15d
0x18002110b  mov     edx, 1926h
0x180021110  lea     rcx, qword_1800487B0
0x180021117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111c  mov     edi, 80004005h
0x180021121  mov     rcx, rsi; this
0x180021124  call    ?CommitErrorCount@CWinSATTaskMangerTask@@AEAA_NXZ; CWinSATTaskMangerTask::CommitErrorCount(void)
0x180021129  jmp     loc_180020EE3
0x18002112e  call    ?DoSuccesfulCompletionRegistryAndSQMWork@CWinSATTaskMangerTask@@AEAAXXZ; CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(void)
0x180021133  mov     [r14], r12d
0x180021136  mov     edx, [r14]
0x180021139  test    edx, edx
0x18002113b  jz      short loc_180021141
0x18002113d  dec     edx
0x18002113f  jmp     short loc_180021143
0x180021141  xor     edx, edx; unsigned int
0x180021143  call    ?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z; CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)
0x180021148  mov     cl, al
0x18002114a  mov     eax, edi
0x18002114c  mov     edi, 80004005h
0x180021151  test    cl, cl
0x180021153  cmovz   eax, edi
0x180021156  mov     edi, eax
0x180021158  jmp     loc_180020EE3
0x18002115d  lea     r8, aTheTaskschedul; "The TaskScheduler Task unexpectedly ter"...
0x180021164  mov     edx, 186h
0x180021169  mov     rcx, r13
0x18002116c  call    Log_Text_F
0x180021171  call    ?EnableDisableWinSATTask@@YAJ_N@Z; EnableDisableWinSATTask(bool)
0x180021176  mov     rax, [rsi+88h]
0x18002117d  test    rax, rax
0x180021180  jz      loc_180020EE3
0x180021186  mov     r8d, r15d
0x180021189  mov     edx, 281Eh
0x18002118e  lea     rcx, qword_1800487B0
0x180021195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002119a  jmp     loc_180020EE3
```
