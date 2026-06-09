# WinLogonBootShell(int)

- ea: `0x1400505c4`
- end: `0x14005097d`
- name: `?WinLogonBootShell@@YAKH@Z`
- size: `953`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400858e0`
- `0x1400877f0`

## callees

- `0x140004f20`
- `0x1400057f4`
- `0x14001a520`
- `0x14004327c`
- `0x14004db4c`
- `0x14004f098`
- `0x1400505c4`
- `0x140050984`
- `0x140053720`
- `0x1400544e0`
- `0x140056bd8`
- `0x14005b630`
- `0x14005d698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140050903`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140050903`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400508f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400508f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140050840`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140050840`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140050739`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140050739`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140050850`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140050850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005085b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140050866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005085b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140050866`
- `ntdll!RtlSetSystemBootStatus` at `0x140050950`
- `ntdll!RtlSetSystemBootStatus` at `0x140050950`
- `ntdll!WinSqmSetDWORD` at `0x1400508d6`
- `ntdll!WinSqmSetDWORD` at `0x1400508d6`
- `ntdll!NtQuerySystemInformation` at `0x140050682`
- `ntdll!NtQuerySystemInformation` at `0x140050682`
- `ext-ms-win-composition-init-l1-1-0!DwmpStartWinlogonMouseThread` at `0x1400507c1`
- `ext-ms-win-composition-init-l1-1-0!DwmpStartWinlogonMouseThread` at `0x140050805`
- `ext-ms-win-composition-init-l1-1-0!DwmpStartWinlogonMouseThread` at `0x1400507c1`
- `ext-ms-win-composition-init-l1-1-0!DwmpStartWinlogonMouseThread` at `0x140050805`
- `ext-ms-win-composition-init-l1-1-0!DwmpShutdownWinlogonMouseThread` at `0x140050881`
- `ext-ms-win-composition-init-l1-1-0!DwmpShutdownWinlogonMouseThread` at `0x140050899`
- `ext-ms-win-composition-init-l1-1-0!DwmpShutdownWinlogonMouseThread` at `0x140050881`
- `ext-ms-win-composition-init-l1-1-0!DwmpShutdownWinlogonMouseThread` at `0x140050899`

## string_xrefs

- `0x1400507d2`: `clientcore\ds\security\umstartup\winlogon\core\winlogon.cxx`
- `0x140050816`: `clientcore\ds\security\umstartup\winlogon\core\winlogon.cxx`
- `0x1400508e7`: `Global\BootShellComplete`

## pseudocode

```c
__int64 __fastcall WinLogonBootShell(int a1)
{
  int v2; // r12d
  int v3; // r14d
  BOOL v4; // edi
  NTSTATUS v5; // r15d
  CUser *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  int started; // eax
  __int64 result; // rax
  HANDLE EventW; // rax
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ReturnLength; // [rsp+54h] [rbp-ACh] BYREF
  int v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[32]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD SystemInformation[8]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR ApplicationName[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  memset_0(ApplicationName, 0, 0x208u);
  *(_QWORD *)&StartupInfo.cb = 104;
  ExitCode = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  StartupInfo.lpDesktop = (LPWSTR)L"Default";
  ReturnLength = 0;
  StartupInfo.lpReserved = 0;
  memset(&StartupInfo.lpTitle, 0, 80);
  v2 = 0;
  v3 = 0;
  v4 = a1 != 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v5 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, &ReturnLength);
  if ( v5 >= 0 )
  {
    if ( (SystemInformation[6] & 1) != 0 && (int)StringCchCopyW(ApplicationName, 0x104u, L"bootim.exe") >= 0 )
    {
      if ( CreateProcessW(ApplicationName, 0, 0, 0, 0, 0x400u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        if ( !a1 )
        {
          bInheritHandles = 0;
          CSession::SwitchDesktop(qword_1400D2550, 2, 0);
          v4 = 1;
        }
        LOBYTE(v2) = (unsigned int)LaunchUmfdHostWithCurrentToken() != 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(v18, 0);
          if ( !a1 && (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
          {
            started = DwmpStartWinlogonMouseThread();
            if ( started >= 0 )
              v3 = 1;
            else
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x856,
                (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\winlogon.cxx",
                (const char *)(unsigned int)started,
                bInheritHandles);
          }
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v18);
        }
        else if ( !a1 && (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
        {
          v8 = DwmpStartWinlogonMouseThread();
          if ( v8 >= 0 )
            v3 = 1;
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x85F,
              (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\winlogon.cxx",
              (const char *)(unsigned int)v8,
              bInheritHandles);
        }
        WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
        GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
        CloseHandle(ProcessInformation.hThread);
        CloseHandle(ProcessInformation.hProcess);
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v7 = 58;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v7 = 57;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids, (unsigned int)v5);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl'::`2'::impl) )
  {
    CallWithHangTimeout::CallWithHangTimeout(v18, 0);
    if ( v3 )
      DwmpShutdownWinlogonMouseThread();
    CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v18);
  }
  else if ( v3 )
  {
    DwmpShutdownWinlogonMouseThread();
  }
  if ( v2 )
    TerminateUmfdHost(1);
  result = ExitCode;
  if ( ExitCode != 3010 && ExitCode != 641 )
  {
    WinSqmSetDWORD(0, 10742, ExitCode);
    result = 0;
    ExitCode = 0;
  }
  if ( !(_DWORD)result )
  {
    EventW = CreateEventW(0, 1, 0, L"Global\\BootShellComplete");
    if ( EventW )
    {
      SetEvent(EventW);
      if ( v4 )
        CSession::SwitchDesktop(qword_1400D2550, 0, 0);
      return 0;
    }
    result = 14;
    ExitCode = 14;
  }
  if ( (_DWORD)result == 3010 || (_DWORD)result == 641 )
  {
    v15 = 1;
    RtlSetSystemBootStatus(4, &v15, 4);
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x1400505c4  push    rbp
0x1400505c6  push    rbx
0x1400505c7  push    rsi
0x1400505c8  push    rdi
0x1400505c9  push    r12
0x1400505cb  push    r13
0x1400505cd  push    r14
0x1400505cf  push    r15
0x1400505d1  lea     rbp, [rsp-258h]
0x1400505d9  sub     rsp, 358h
0x1400505e0  mov     rax, cs:__security_cookie
0x1400505e7  xor     rax, rsp
0x1400505ea  mov     [rbp+290h+var_50], rax
0x1400505f1  mov     esi, ecx
0x1400505f3  xor     edx, edx; Val
0x1400505f5  lea     rcx, [rbp+290h+ApplicationName]; void *
0x1400505f9  mov     r8d, 208h; Size
0x1400505ff  call    memset_0
0x140050604  xor     r13d, r13d
0x140050607  mov     qword ptr [rbp+290h+StartupInfo.cb], 68h ; 'h'
0x14005060f  xorps   xmm0, xmm0
0x140050612  mov     [rsp+390h+ExitCode], r13d
0x140050617  lea     rax, aDefault_0; "Default"
0x14005061e  mov     [rbp+290h+SystemInformation], r13d
0x140050622  mov     [rbp+290h+StartupInfo.lpDesktop], rax
0x140050626  lea     r9, [rsp+390h+ReturnLength]; ReturnLength
0x14005062b  xor     eax, eax
0x14005062d  mov     [rsp+390h+ReturnLength], r13d
0x140050632  xorps   xmm1, xmm1
0x140050635  mov     [rbp+290h+StartupInfo.lpReserved], r13
0x140050639  movups  [rbp+290h+var_27C], xmm0
0x14005063d  test    esi, esi
0x14005063f  mov     [rbp+290h+StartupInfo.lpTitle], r13
0x140050643  mov     edi, r13d
0x140050646  mov     qword ptr [rbp+290h+StartupInfo.wShowWindow], r13
0x14005064a  lea     ecx, [rax+5Ah]; SystemInformationClass
0x14005064d  mov     [rbp+290h+StartupInfo.lpReserved2], r13
0x140050651  lea     r8d, [r13+20h]; SystemInformationLength
0x140050655  movdqa  xmmword ptr [rbp+290h+StartupInfo.hStdInput], xmm0
0x14005065a  lea     rdx, [rbp+290h+SystemInformation]; SystemInformation
0x14005065e  mov     [rbp+290h+StartupInfo.hStdError], r13
0x140050662  movups  [rbp+290h+var_27C+0Ch], xmm0
0x140050666  mov     r12d, r13d
0x140050669  mov     qword ptr [rsp+390h+ProcessInformation.dwProcessId], rax
0x14005066e  mov     r14d, r13d
0x140050671  setnz   dil
0x140050675  movups  xmmword ptr [rbp+290h+StartupInfo.dwX], xmm0
0x140050679  movups  xmmword ptr [rbp+290h+StartupInfo.dwXCountChars], xmm0
0x14005067d  movups  xmmword ptr [rsp+390h+ProcessInformation.hProcess], xmm1
0x140050682  call    cs:__imp_NtQuerySystemInformation
0x140050688  mov     r15d, eax
0x14005068b  test    eax, eax
0x14005068d  jns     short loc_1400506D8
0x14005068f  mov     rcx, cs:WPP_GLOBAL_Control
0x140050696  lea     rdx, WPP_GLOBAL_Control
0x14005069d  lea     ebx, [r13+1]
0x1400506a1  cmp     rcx, rdx
0x1400506a4  jz      loc_14005086C
0x1400506aa  test    [rcx+1Ch], bl
0x1400506ad  jz      loc_14005086C
0x1400506b3  cmp     byte ptr [rcx+19h], 3
0x1400506b7  jb      loc_14005086C
0x1400506bd  lea     edx, [rbx+38h]
0x1400506c0  mov     rcx, [rcx+10h]
0x1400506c4  lea     r8, WPP_ea968c137b9e31d540c842f1a896af1c_Traceguids
0x1400506cb  mov     r9d, r15d
0x1400506ce  call    WPP_SF_d
0x1400506d3  jmp     loc_14005086C
0x1400506d8  mov     ebx, 1
0x1400506dd  test    [rbp+290h+var_268], bl
0x1400506e0  jz      loc_14005086C
0x1400506e6  lea     r8, aBootimExe; "bootim.exe"
0x1400506ed  mov     edx, 104h; unsigned __int64
0x1400506f2  lea     rcx, [rbp+290h+ApplicationName]; unsigned __int16 *
0x1400506f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400506fb  test    eax, eax
0x1400506fd  js      loc_14005086C
0x140050703  lea     rax, [rsp+390h+ProcessInformation]
0x140050708  xor     r9d, r9d; lpThreadAttributes
0x14005070b  mov     [rsp+390h+lpProcessInformation], rax; lpProcessInformation
0x140050710  lea     rcx, [rbp+290h+ApplicationName]; lpApplicationName
0x140050714  lea     rax, [rbp+290h+StartupInfo]
0x140050718  xor     r8d, r8d; lpProcessAttributes
0x14005071b  mov     [rsp+390h+lpStartupInfo], rax; lpStartupInfo
0x140050720  xor     edx, edx; lpCommandLine
0x140050722  mov     [rsp+390h+lpCurrentDirectory], r13; lpCurrentDirectory
0x140050727  mov     [rsp+390h+lpEnvironment], r13; lpEnvironment
0x14005072c  mov     [rsp+390h+dwCreationFlags], 400h; dwCreationFlags
0x140050734  mov     [rsp+390h+bInheritHandles], r13d; bInheritHandles
0x140050739  call    cs:__imp_CreateProcessW
0x14005073f  test    eax, eax
0x140050741  jnz     short loc_140050775
0x140050743  mov     rcx, cs:WPP_GLOBAL_Control
0x14005074a  lea     rdx, WPP_GLOBAL_Control
0x140050751  cmp     rcx, rdx
0x140050754  jz      loc_14005086C
0x14005075a  test    [rcx+1Ch], bl
0x14005075d  jz      loc_14005086C
0x140050763  cmp     byte ptr [rcx+19h], 3
0x140050767  jb      loc_14005086C
0x14005076d  lea     edx, [rbx+39h]
0x140050770  jmp     loc_1400506C0
0x140050775  test    esi, esi
0x140050777  jnz     short loc_140050795
0x140050779  mov     rcx, cs:qword_1400D2550
0x140050780  lea     edx, [rsi+2]
0x140050783  xor     r9d, r9d
0x140050786  mov     [rsp+390h+bInheritHandles], r13d; int
0x14005078b  xor     r8d, r8d
0x14005078e  call    ?SwitchDesktop@CSession@@QEAAXW4_DESKTOPID@@PEAHKK@Z; CSession::SwitchDesktop(_DESKTOPID,int *,ulong,ulong)
0x140050793  mov     edi, ebx
0x140050795  call    LaunchUmfdHostWithCurrentToken
0x14005079a  test    eax, eax
0x14005079c  setnz   r12b
0x1400507a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl(void)'::`2'::impl
0x1400507a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(void)
0x1400507ac  test    al, al
0x1400507ae  jnz     short loc_1400507ED
0x1400507b0  test    esi, esi
0x1400507b2  jnz     loc_140050838
0x1400507b8  call    IsDwmpStartWinlogonMouseThreadPresent
0x1400507bd  test    al, al
0x1400507bf  jz      short loc_140050838
0x1400507c1  call    cs:__imp_DwmpStartWinlogonMouseThread
0x1400507c7  test    eax, eax
0x1400507c9  jns     short loc_1400507E8
0x1400507cb  mov     rcx, [rbp+298h]; this
0x1400507d2  lea     r8, aClientcoreDsSe; "clientcore\\ds\\security\\umstartup\\wi"...
0x1400507d9  mov     r9d, eax; char *
0x1400507dc  mov     edx, 85Fh; void *
0x1400507e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400507e6  jmp     short loc_140050838
0x1400507e8  mov     r14d, ebx
0x1400507eb  jmp     short loc_140050838
0x1400507ed  xor     edx, edx
0x1400507ef  lea     rcx, [rbp+290h+var_2A0]
0x1400507f3  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x1400507f8  test    esi, esi
0x1400507fa  jnz     short loc_14005082F
0x1400507fc  call    IsDwmpStartWinlogonMouseThreadPresent
0x140050801  test    al, al
0x140050803  jz      short loc_14005082F
0x140050805  call    cs:__imp_DwmpStartWinlogonMouseThread
0x14005080b  test    eax, eax
0x14005080d  jns     short loc_14005082C
0x14005080f  mov     rcx, [rbp+298h]; this
0x140050816  lea     r8, aClientcoreDsSe; "clientcore\\ds\\security\\umstartup\\wi"...
0x14005081d  mov     r9d, eax; char *
0x140050820  mov     edx, 856h; void *
0x140050825  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005082a  jmp     short loc_14005082F
0x14005082c  mov     r14d, ebx
0x14005082f  lea     rcx, [rbp+290h+var_2A0]; this
0x140050833  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x140050838  mov     rcx, [rsp+390h+ProcessInformation.hProcess]; hHandle
0x14005083d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140050840  call    cs:__imp_WaitForSingleObject
0x140050846  mov     rcx, [rsp+390h+ProcessInformation.hProcess]; hProcess
0x14005084b  lea     rdx, [rsp+390h+ExitCode]; lpExitCode
0x140050850  call    cs:__imp_GetExitCodeProcess
0x140050856  mov     rcx, [rsp+390h+ProcessInformation.hThread]; hObject
0x14005085b  call    cs:__imp_CloseHandle
0x140050861  mov     rcx, [rsp+390h+ProcessInformation.hProcess]; hObject
0x140050866  call    cs:__imp_CloseHandle
0x14005086c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl(void)'::`2'::impl
0x140050873  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(void)
0x140050878  test    al, al
0x14005087a  jnz     short loc_140050889
0x14005087c  test    r14d, r14d
0x14005087f  jz      short loc_1400508A8
0x140050881  call    cs:__imp_DwmpShutdownWinlogonMouseThread
0x140050887  jmp     short loc_1400508A8
0x140050889  xor     edx, edx
0x14005088b  lea     rcx, [rbp+290h+var_2A0]
0x14005088f  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140050894  test    r14d, r14d
0x140050897  jz      short loc_14005089F
0x140050899  call    cs:__imp_DwmpShutdownWinlogonMouseThread
0x14005089f  lea     rcx, [rbp+290h+var_2A0]; this
0x1400508a3  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x1400508a8  test    r12d, r12d
0x1400508ab  jz      short loc_1400508B4
0x1400508ad  mov     ecx, ebx
0x1400508af  call    TerminateUmfdHost
0x1400508b4  mov     eax, [rsp+390h+ExitCode]
0x1400508b8  mov     r14d, 0BC2h
0x1400508be  mov     esi, 281h
0x1400508c3  cmp     eax, r14d
0x1400508c6  jz      short loc_1400508E3
0x1400508c8  cmp     eax, esi
0x1400508ca  jz      short loc_1400508E3
0x1400508cc  mov     r8d, eax
0x1400508cf  mov     edx, 29F6h
0x1400508d4  xor     ecx, ecx
0x1400508d6  call    cs:__imp_WinSqmSetDWORD
0x1400508dc  mov     eax, r13d
0x1400508df  mov     [rsp+390h+ExitCode], eax
0x1400508e3  test    eax, eax
0x1400508e5  jnz     short loc_140050934
0x1400508e7  lea     r9, aGlobalBootshel; "Global\\BootShellComplete"
0x1400508ee  xor     r8d, r8d; bInitialState
0x1400508f1  mov     edx, ebx; bManualReset
0x1400508f3  xor     ecx, ecx; lpEventAttributes
0x1400508f5  call    cs:__imp_CreateEventW
0x1400508fb  test    rax, rax
0x1400508fe  jz      short loc_14005092B
0x140050900  mov     rcx, rax; hEvent
0x140050903  call    cs:__imp_SetEvent
0x140050909  test    edi, edi
0x14005090b  jz      short loc_140050926
0x14005090d  mov     rcx, cs:qword_1400D2550
0x140050914  xor     r9d, r9d
0x140050917  xor     r8d, r8d
0x14005091a  mov     [rsp+390h+bInheritHandles], r13d
0x14005091f  xor     edx, edx
0x140050921  call    ?SwitchDesktop@CSession@@QEAAXW4_DESKTOPID@@PEAHKK@Z; CSession::SwitchDesktop(_DESKTOPID,int *,ulong,ulong)
0x140050926  mov     eax, r13d
0x140050929  jmp     short loc_14005095A
0x14005092b  mov     eax, 0Eh
0x140050930  mov     [rsp+390h+ExitCode], eax
0x140050934  cmp     eax, r14d
0x140050937  jz      short loc_14005093D
0x140050939  cmp     eax, esi
0x14005093b  jnz     short loc_14005095A
0x14005093d  xor     r9d, r9d
0x140050940  mov     [rsp+390h+var_338], ebx
0x140050944  lea     rdx, [rsp+390h+var_338]
0x140050949  lea     ecx, [r9+4]
0x14005094d  mov     r8d, ecx
0x140050950  call    cs:__imp_RtlSetSystemBootStatus
0x140050956  mov     eax, [rsp+390h+ExitCode]
0x14005095a  mov     rcx, [rbp+290h+var_50]
0x140050961  xor     rcx, rsp; StackCookie
0x140050964  call    __security_check_cookie
0x140050969  add     rsp, 358h
0x140050970  pop     r15
0x140050972  pop     r14
0x140050974  pop     r13
0x140050976  pop     r12
0x140050978  pop     rdi
0x140050979  pop     rsi
0x14005097a  pop     rbx
0x14005097b  pop     rbp
0x14005097c  retn
```
