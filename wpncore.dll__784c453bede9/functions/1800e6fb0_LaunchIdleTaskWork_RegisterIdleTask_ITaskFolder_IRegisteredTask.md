# LaunchIdleTaskWork::RegisterIdleTask(ITaskFolder *,IRegisteredTask * *)

- ea: `0x1800e6fb0`
- end: `0x1800e728c`
- name: `?RegisterIdleTask@LaunchIdleTaskWork@@AEAAJPEAUITaskFolder@@PEAPEAUIRegisteredTask@@@Z`
- size: `732`
- prototype: `__int64 __fastcall(LaunchIdleTaskWork *__hidden this, struct ITaskFolder *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e6ce0`

## callees

- `0x18002ee38`
- `0x18003a184`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800e6fb0`
- `0x180118010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e7003`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e70db`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e7003`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e70db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e7262`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e7270`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e7262`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e7270`

## string_xrefs

- `0x1800e7015`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800e7093`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800e70ed`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800e7157`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800e721a`: `onecoreuap\base\diagnosis\platform\notifications\platform\infra\launchidletaskwork.cpp`
- `0x1800e7073`: `  <Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n    <RegistrationInfo>\n      <Source>Microsoft Corporation</Source>\n      <Author>Microsoft Corporation</Author>\n      <Description>This idle task reorganize tile notification data only when system is idle for better performance.</Description>\n    </RegistrationInfo>\n    <Triggers>\n      <IdleTrigger>\n        <Enabled>true</Enabled>\n      </IdleTrigger>\n    </Triggers>\n    <Principals>\n      <Principal`

## pseudocode

```c
__int64 __fastcall LaunchIdleTaskWork::RegisterIdleTask(
        LaunchIdleTaskWork *this,
        struct ITaskFolder *a2,
        struct IRegisteredTask **a3)
{
  __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  OLECHAR *v7; // r14
  unsigned int v8; // ebx
  int v9; // eax
  OLECHAR *v10; // rdi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rdx
  HRESULT (__stdcall *RegisterTask)(ITaskFolder *, BSTR, BSTR, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // rax
  int v19; // eax
  int v21; // [rsp+20h] [rbp-79h]
  _OWORD v22[2]; // [rsp+70h] [rbp-29h] BYREF
  int v23[4]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  memset(v22, 0, 18);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v5 = *((_QWORD *)this + 5);
  v6 = SysAllocStringLen(0, (int)v5 + 1757);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
      (const char *)0x8007000ELL,
      v21);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids, 2147942414LL);
    return v8;
  }
  v9 = StringCchPrintfW(
         v6,
         v5 + 1757,
         L"  <Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\r\n"
          "    <RegistrationInfo>\r\n"
          "      <Source>Microsoft Corporation</Source>\r\n"
          "      <Author>Microsoft Corporation</Author>\r\n"
          "      <Description>This idle task reorganize tile notification data only when system is idle for better perfor"
          "mance.</Description>\r\n"
          "    </RegistrationInfo>\r\n"
          "    <Triggers>\r\n"
          "      <IdleTrigger>\r\n"
          "        <Enabled>true</Enabled>\r\n"
          "      </IdleTrigger>\r\n"
          "    </Triggers>\r\n"
          "    <Principals>\r\n"
          "      <Principal id=\"AnyUser\">\r\n"
          "        <UserId>%s</UserId>\r\n"
          "        <LogonType>InteractiveToken</LogonType>\r\n"
          "      </Principal>\r\n"
          "    </Principals>\r\n"
          "    <Settings>\r\n"
          "      <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>\r\n"
          "      <DisallowStartIfOnBatteries>true</DisallowStartIfOnBatteries>\r\n"
          "      <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\r\n"
          "      <AllowHardTerminate>false</AllowHardTerminate>\r\n"
          "      <StartWhenAvailable>false</StartWhenAvailable>\r\n"
          "      <RunOnlyIfNetworkAvailable>false</RunOnlyIfNetworkAvailable>\r\n"
          "      <IdleSettings>\r\n"
          "        <Duration>PT0M</Duration>\r\n"
          "        <WaitTimeout>PT0S</WaitTimeout>\r\n"
          "        <StopOnIdleEnd>false</StopOnIdleEnd>\r\n"
          "        <RestartOnIdle>false</RestartOnIdle>\r\n"
          "      </IdleSettings>\r\n"
          "      <AllowStartOnDemand>true</AllowStartOnDemand>\r\n"
          "      <Enabled>false</Enabled>\r\n"
          "      <Hidden>false</Hidden>\r\n"
          "      <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\r\n"
          "      <RunOnlyIfIdle>true</RunOnlyIfIdle>\r\n"
          "      <WakeToRun>false</WakeToRun>\r\n"
          "      <ExecutionTimeLimit>PT0S</ExecutionTimeLimit>\r\n"
          "      <Priority>7</Priority>\r\n"
          "    </Settings>\r\n"
          "    <Actions Context=\"AnyUser\">\r\n"
          "      <ComHandler>\r\n"
          "        <ClassId>{201600d8-6eff-48ce-b842-e14d37a0682d}</ClassId>\r\n"
          "      </ComHandler>\r\n"
          "    </Actions>\r\n"
          "  </Task>\r\n",
         *((_QWORD *)this + 4));
  v8 = v9;
  if ( v9 >= 0 )
  {
    v13 = *((_QWORD *)this + 5);
    v14 = SysAllocStringLen(0, (int)v13 + 40);
    v10 = v14;
    if ( v14 )
    {
      v16 = StringCchPrintfW(v14, v13 + 40, L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FA;;;%s)", *((_QWORD *)this + 4));
      v8 = v16;
      if ( v16 >= 0 )
      {
        v17 = *((_QWORD *)this + 3);
        RegisterTask = a2->lpVtbl->RegisterTask;
        *(_OWORD *)v23 = v22[0];
        v24 = 0;
        v19 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, OLECHAR *, __int64))RegisterTask)(a2, v17, v7, 2);
        v8 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
            (const char *)(unsigned int)v19,
            (int)v23);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v12 = 28;
            goto LABEL_23;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x133,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
          (const char *)(unsigned int)v16,
          v21);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 27;
          goto LABEL_23;
        }
      }
    }
    else
    {
      v8 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
        (const char *)0x8007000ELL,
        v21);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 26;
        v15 = 2147942414LL;
LABEL_24:
        WPP_SF_d(v11[2], v12, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids, v15);
      }
    }
  }
  else
  {
    v10 = 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\launchidletaskwork.cpp",
      (const char *)(unsigned int)v9,
      v21);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 25;
LABEL_23:
      v15 = v8;
      goto LABEL_24;
    }
  }
  SysFreeString(v7);
  if ( v10 )
    SysFreeString(v10);
  return v8;
}

```

## disassembly

```asm
0x1800e6fb0  push    rbp
0x1800e6fb2  push    rbx
0x1800e6fb3  push    rsi
0x1800e6fb4  push    rdi
0x1800e6fb5  push    r12
0x1800e6fb7  push    r13
0x1800e6fb9  push    r14
0x1800e6fbb  push    r15
0x1800e6fbd  lea     rbp, [rsp-1Fh]
0x1800e6fc2  sub     rsp, 0B8h
0x1800e6fc9  xor     eax, eax
0x1800e6fcb  xor     r13d, r13d
0x1800e6fce  mov     word ptr [rbp+57h+var_80], ax
0x1800e6fd2  xorps   xmm0, xmm0
0x1800e6fd5  mov     [rbp+57h+arg_0], rax
0x1800e6fd9  xorps   xmm1, xmm1
0x1800e6fdc  mov     r12, r8
0x1800e6fdf  mov     r15, rdx
0x1800e6fe2  mov     rsi, rcx
0x1800e6fe5  movups  [rbp+57h+var_80+2], xmm0
0x1800e6fe9  movups  [rbp+57h+var_A0], xmm1
0x1800e6fed  test    rdx, rdx
0x1800e6ff0  jnz     short loc_1800E6FF7
0x1800e6ff2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "TaskFolder != NULL")
0x1800e6ff7  mov     rbx, [rsi+28h]
0x1800e6ffb  xor     ecx, ecx; strIn
0x1800e6ffd  lea     edx, [rbx+6DDh]; ui
0x1800e7003  call    cs:__imp_SysAllocStringLen
0x1800e7009  mov     r14, rax
0x1800e700c  test    rax, rax
0x1800e700f  jnz     short loc_1800E706F
0x1800e7011  mov     rcx, [rbp+5Fh]; this
0x1800e7015  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e701c  mov     r9d, 8007000Eh; char *
0x1800e7022  mov     edx, 11Eh; void *
0x1800e7027  mov     ebx, r9d
0x1800e702a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e702f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e7036  lea     rax, WPP_GLOBAL_Control
0x1800e703d  cmp     rcx, rax
0x1800e7040  jz      loc_1800E7276
0x1800e7046  test    byte ptr [rcx+1Ch], 80h
0x1800e704a  jz      loc_1800E7276
0x1800e7050  mov     rcx, [rcx+10h]
0x1800e7054  lea     edx, [r14+18h]
0x1800e7058  mov     r9d, 8007000Eh
0x1800e705e  lea     r8, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids
0x1800e7065  call    WPP_SF_d
0x1800e706a  jmp     loc_1800E7276
0x1800e706f  mov     r9, [rsi+20h]
0x1800e7073  lea     r8, aTaskXmlnsHttpS; "  <Task xmlns=\"http://schemas.microsof"...
0x1800e707a  lea     rdx, [rbx+6DDh]; unsigned __int64
0x1800e7081  mov     rcx, r14; unsigned __int16 *
0x1800e7084  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e7089  mov     ebx, eax
0x1800e708b  test    eax, eax
0x1800e708d  jns     short loc_1800E70D2
0x1800e708f  mov     rcx, [rbp+5Fh]; this
0x1800e7093  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e709a  xor     edi, edi
0x1800e709c  mov     r9d, eax; char *
0x1800e709f  mov     edx, 126h; void *
0x1800e70a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e70a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e70b0  lea     rax, WPP_GLOBAL_Control
0x1800e70b7  cmp     rcx, rax
0x1800e70ba  jz      loc_1800E725F
0x1800e70c0  test    byte ptr [rcx+1Ch], 80h
0x1800e70c4  jz      loc_1800E725F
0x1800e70ca  lea     edx, [rdi+19h]
0x1800e70cd  jmp     loc_1800E724C
0x1800e70d2  mov     rbx, [rsi+28h]
0x1800e70d6  xor     ecx, ecx; strIn
0x1800e70d8  lea     edx, [rbx+28h]; ui
0x1800e70db  call    cs:__imp_SysAllocStringLen
0x1800e70e1  mov     rdi, rax
0x1800e70e4  test    rax, rax
0x1800e70e7  jnz     short loc_1800E7136
0x1800e70e9  mov     rcx, [rbp+5Fh]; this
0x1800e70ed  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e70f4  mov     r9d, 8007000Eh; char *
0x1800e70fa  mov     edx, 12Bh; void *
0x1800e70ff  mov     ebx, r9d
0x1800e7102  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e7107  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e710e  lea     rax, WPP_GLOBAL_Control
0x1800e7115  cmp     rcx, rax
0x1800e7118  jz      loc_1800E725F
0x1800e711e  test    byte ptr [rcx+1Ch], 80h
0x1800e7122  jz      loc_1800E725F
0x1800e7128  lea     edx, [rdi+1Ah]
0x1800e712b  mov     r9d, 8007000Eh
0x1800e7131  jmp     loc_1800E724F
0x1800e7136  mov     r9, [rsi+20h]
0x1800e713a  lea     r8, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FA;;;%s)"
0x1800e7141  lea     rdx, [rbx+28h]; unsigned __int64
0x1800e7145  mov     rcx, rdi; unsigned __int16 *
0x1800e7148  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e714d  mov     ebx, eax
0x1800e714f  test    eax, eax
0x1800e7151  jns     short loc_1800E7196
0x1800e7153  mov     rcx, [rbp+5Fh]; this
0x1800e7157  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e715e  mov     r9d, eax; char *
0x1800e7161  mov     edx, 133h; void *
0x1800e7166  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e716b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e7172  lea     rax, WPP_GLOBAL_Control
0x1800e7179  cmp     rcx, rax
0x1800e717c  jz      loc_1800E725F
0x1800e7182  test    byte ptr [rcx+1Ch], 80h
0x1800e7186  jz      loc_1800E725F
0x1800e718c  mov     edx, 1Bh
0x1800e7191  jmp     loc_1800E724C
0x1800e7196  movups  xmm2, [rbp+57h+var_80]
0x1800e719a  lea     rcx, [rbp+57h+var_A0]
0x1800e719e  mov     rdx, [rsi+18h]
0x1800e71a2  movsd   xmm1, [rbp+57h+arg_0]
0x1800e71a7  mov     eax, 8
0x1800e71ac  mov     word ptr [rbp+57h+var_A0], ax
0x1800e71b0  mov     r9d, 2
0x1800e71b6  mov     rax, [r15]
0x1800e71b9  mov     r8, r14
0x1800e71bc  mov     [rsp+0F0h+var_B0], r12
0x1800e71c1  mov     [rsp+0F0h+var_B8], rcx
0x1800e71c6  lea     rcx, [rbp+57h+var_80]
0x1800e71ca  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x1800e71ce  movups  xmm0, [rbp+57h+var_A0]
0x1800e71d2  mov     rax, [rax+80h]
0x1800e71d9  mov     [rsp+0F0h+var_C0], 3
0x1800e71e1  mov     [rsp+0F0h+var_C8], rcx
0x1800e71e6  lea     rcx, [rbp+57h+var_60]
0x1800e71ea  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x1800e71ef  mov     rcx, r15
0x1800e71f2  movaps  [rbp+57h+var_A0], xmm0
0x1800e71f6  movsd   [rbp+57h+var_90], xmm1
0x1800e71fb  movaps  [rbp+57h+var_80], xmm2
0x1800e71ff  mov     [rbp+57h+var_70], r13
0x1800e7203  movaps  xmmword ptr [rbp+57h+var_60], xmm2
0x1800e7207  mov     [rbp+57h+var_50], r13
0x1800e720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7210  mov     ebx, eax
0x1800e7212  test    eax, eax
0x1800e7214  jns     short loc_1800E725F
0x1800e7216  mov     rcx, [rbp+5Fh]; this
0x1800e721a  lea     r8, aOnecoreuapBase_146; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e7221  mov     r9d, eax; char *
0x1800e7224  mov     edx, 142h; void *
0x1800e7229  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e722e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e7235  lea     rax, WPP_GLOBAL_Control
0x1800e723c  cmp     rcx, rax
0x1800e723f  jz      short loc_1800E725F
0x1800e7241  test    byte ptr [rcx+1Ch], 80h
0x1800e7245  jz      short loc_1800E725F
0x1800e7247  mov     edx, 1Ch
0x1800e724c  mov     r9d, ebx
0x1800e724f  mov     rcx, [rcx+10h]
0x1800e7253  lea     r8, WPP_51c9c895e5963bbc29cf904f7338ca21_Traceguids
0x1800e725a  call    WPP_SF_d
0x1800e725f  mov     rcx, r14; bstrString
0x1800e7262  call    cs:__imp_SysFreeString
0x1800e7268  test    rdi, rdi
0x1800e726b  jz      short loc_1800E7276
0x1800e726d  mov     rcx, rdi; bstrString
0x1800e7270  call    cs:__imp_SysFreeString
0x1800e7276  mov     eax, ebx
0x1800e7278  add     rsp, 0B8h
0x1800e727f  pop     r15
0x1800e7281  pop     r14
0x1800e7283  pop     r13
0x1800e7285  pop     r12
0x1800e7287  pop     rdi
0x1800e7288  pop     rsi
0x1800e7289  pop     rbx
0x1800e728a  pop     rbp
0x1800e728b  retn
```
