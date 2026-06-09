# CAudioOrchestrator::ReaderStartStream(ulong,int *,unsigned __int64 *,int *)

- ea: `0x18004f5c0`
- end: `0x18004fa38`
- name: `?ReaderStartStream@CAudioOrchestrator@@UEAAJKPEAHPEA_K0@Z`
- size: `1144`
- prototype: `int(CAudioOrchestrator *__hidden this, unsigned int, int *, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180013ec0`
- `0x18003d7c4`
- `0x1800484f0`
- `0x180049bfc`
- `0x18004d460`
- `0x18004f5c0`
- `0x18004ff60`
- `0x180079e30`
- `0x1800a9e90`
- `0x1800a9fbc`
- `0x1800ab1a0`
- `0x1800abc1c`
- `0x1800abf58`
- `0x1800abfc4`
- `0x1800ac304`
- `0x1800acd3c`
- `0x1800ae480`
- `0x1800af250`
- `0x1800af2f4`
- `0x1800afa24`
- `0x1800afb7c`
- `0x1800afca8`
- `0x1800b03e8`
- `0x1800b1270`
- `0x1800b32e8`
- `0x1800b46c4`
- `0x1800b4edc`
- `0x1800b4f7c`
- `0x1800b6328`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f612`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18004f747`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18004f747`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18004f7d0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x18004f7d0`

## string_xrefs

- `0x18004f70e`: `[%s] Power Event: Failing ReaderStartStream for reader: %i\n`
- `0x18004f5f7`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f623`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f6ac`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f707`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f819`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f85b`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f8f4`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f91f`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f9c7`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f9e6`: `CAudioOrchestrator::ReaderStartStream`
- `0x18004f62a`: `[%s] enter, dwReaderCookie: %d`
- `0x18004f6b3`: `[%s] XBox: Failing ReaderStartStream - Kinect is disconnected`
- `0x18004f8fb`: `[%s] On hololens, Release conversation session when reader %i start streaming`
- `0x18004f926`: `[%s] On hololens, Set 10sec timer when reader %i start streaming`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAudioOrchestrator::ReaderStartStream(
        CAudioOrchestrator *this,
        unsigned int a2,
        int *a3,
        unsigned __int64 *a4,
        int *a5)
{
  int started; // edi
  unsigned int v10; // eax
  __int64 v11; // rcx
  CAudioOrchestrator *v12; // rcx
  CAudioOrchestrator *v13; // rcx
  int v14; // eax
  int v16; // [rsp+30h] [rbp-A8h] BYREF
  char *v17; // [rsp+38h] [rbp-A0h] BYREF
  int v18; // [rsp+40h] [rbp-98h]
  _BYTE pv[64]; // [rsp+50h] [rbp-88h] BYREF

  WatchdogTimer::WatchdogTimer(pv, "CAudioOrchestrator::ReaderStartStream");
  v17 = (char *)this + 120;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v18 = 0;
  DoTraceMessage(8, "[%s] enter, dwReaderCookie: %d", "CAudioOrchestrator::ReaderStartStream", a2);
  if ( *((_DWORD *)this + 211) )
  {
    *((_DWORD *)this + 211) = 0;
    CAudioOrchestrator::InvalidateAudioDevices((CAudioOrchestrator *)((char *)this - 40), 1);
  }
  started = CAudioOrchestrator::EnsureSetInput((struct _RTL_CRITICAL_SECTION *)this - 1);
  if ( *((_QWORD *)this + 30) && a2 == *((_DWORD *)this + 286) && (*((_BYTE *)this + 488) & 8) != 0 )
    CAudioOrchestrator::RequestResetVAMaster((CAudioOrchestrator *)((char *)this - 40));
  if ( started >= 0 )
  {
    if ( a3 )
    {
      if ( (*((_BYTE *)this + 488) & 0x20) != 0 )
      {
        DoTraceMessage(
          8,
          "[%s] XBox: Failing ReaderStartStream - Kinect is disconnected",
          "CAudioOrchestrator::ReaderStartStream");
        started = -2147200965;
      }
      else if ( *((_BYTE *)this + 865)
             || *((_QWORD *)this + 78)
             && *((_DWORD *)this + 142) == 3
             && ((unsigned int)CAudioOrchestrator::CanVAStartInLowPower((CAudioOrchestrator *)((char *)this - 40))
              || (unsigned int)CAudioOrchestrator::IsHWKWSOnS3SystemScreenOff((CAudioOrchestrator *)((char *)this - 40))) )
      {
        v10 = *((_DWORD *)this + 371);
        if ( v10 < 3 )
        {
          if ( a2 != *((_DWORD *)this + 287) && a2 != *((_DWORD *)this + 290)
            || !(unsigned int)CAudioOrchestrator::IsBurstReadSupported((CAudioOrchestrator *)((char *)this - 40))
            || (started = CAudioOrchestrator::EnsureVAMasterSwitchToSoftware(v11, 0, 0), started >= 0) )
          {
            if ( a2 == *((_DWORD *)this + 286) || a2 == *((_DWORD *)this + 289) )
            {
              DoTraceMessage(
                8,
                "[%s] Legacy Cortana has been disabled - MVA enabled",
                "CAudioOrchestrator::ReaderStartStream");
              started = -2147467259;
            }
            else
            {
              if ( a2 == *((_DWORD *)this + 287) || a2 == *((_DWORD *)this + 288) )
                CAudioOrchestrator::UpdateMicrophoneMasking((CAudioOrchestrator *)((char *)this - 40));
              if ( a2 == *((_DWORD *)this + 286) || a2 == *((_DWORD *)this + 290) )
                SendNotifyMessageW(HWND_BROADCAST, *((_DWORD *)this + 295), 5u, 0);
              if ( !(unsigned int)CAudioOrchestrator::ShouldSwitchToDebugInputByReader(
                                    (CAudioOrchestrator *)((char *)this - 40),
                                    a2,
                                    1)
                || (started = CAudioOrchestrator::SwitchToDebugInput((CAudioOrchestrator *)((char *)this - 40)),
                    started >= 0) )
              {
                started = CAudioOrchestrator::AdjustReadersFromCachedPosition(
                            (CAudioOrchestrator *)((char *)this - 40),
                            a2);
                if ( started >= 0 )
                  started = CAudioOrchestrator::AdjustReadersBeforeThisStreamStarts(
                              (CAudioOrchestrator *)((char *)this - 40),
                              a2,
                              a4);
              }
            }
          }
        }
        else
        {
          started = -2147200948;
          if ( v10 >= 0x64 )
            ExitProcess(0x8004504C);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "[%s] Power Event: Failing ReaderStartStream for reader: %i\n",
          "CAudioOrchestrator::ReaderStartStream",
          a2);
        started = -2147200869;
      }
    }
    else
    {
      started = -2147467261;
    }
  }
  v16 = 0;
  (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this - 4) + 152LL))((char *)this - 32, &v16);
  DoTraceMessage(8, "[%s] Audio is currently gated %i", "CAudioOrchestrator::ReaderStartStream", v16);
  if ( started < 0 )
    goto LABEL_59;
  if ( v16 && a2 != *((_DWORD *)this + 288) )
    CAudioOrchestratorInput::SwitchToMic((CAudioOrchestrator *)((char *)this + 560));
  started = CAudioOrchestrator::InternalReaderStartStream((CAudioOrchestrator *)((char *)this - 40), a2, a3);
  if ( started < 0
    || (started = CAudioOrchestrator::AdjustReadersAfterThisStreamStarts((CAudioOrchestrator *)((char *)this - 40), a2),
        started < 0) )
  {
LABEL_59:
    v14 = CAudioOrchestrator::InternalReaderStopOnError((CAudioOrchestrator *)((char *)this - 40), a2);
    if ( v14 < 0 )
      DoTraceMessage(
        8,
        "[%s] AudioOrchestrator: StartStream failed - hr: 0x%x - unable to stop tream: hr: 0x%x",
        "CAudioOrchestrator::ReaderStartStream",
        started,
        v14);
    DoTraceMessage(8, "[%s] failed, hr: 0x%x", "CAudioOrchestrator::ReaderStartStream", started);
  }
  else
  {
    if ( (unsigned int)CAudioOrchestrator::IsSystemCookie((CAudioOrchestrator *)((char *)this - 40), a2) )
    {
      CAudioOrchestrator::EnsureCancelAudioStateTransitionTimer(v12);
      if ( *((_DWORD *)this + 226) && (unsigned int)CAudioOrchestrator::GetPolicy_VoiceOnSet(v13) )
      {
        if ( *((_BYTE *)this + 933) )
        {
          DoTraceMessage(
            8,
            "[%s] On hololens, Release conversation session when reader %i start streaming",
            "CAudioOrchestrator::ReaderStartStream",
            a2);
          CAudioOrchestrator::EnsureAARSessionInactive((CAudioOrchestrator *)((char *)this - 40));
          CAudioOrchestrator::ReleaseConversationSession((CAudioOrchestrator *)((char *)this - 40));
        }
        DoTraceMessage(
          8,
          "[%s] On hololens, Set 10sec timer when reader %i start streaming",
          "CAudioOrchestrator::ReaderStartStream",
          a2);
        CAudioOrchestrator::ProcessAudioStateTransitionTimer(
          (CAudioOrchestrator *)((char *)this - 40),
          SPAS_CLOSED,
          0x2710u);
      }
    }
    else if ( a2 == *((_DWORD *)this + 288) )
    {
      _InterlockedExchange((volatile __int32 *)this + 67, 0);
    }
    if ( *((_DWORD *)this + 391) == 4 && (a2 != *((_DWORD *)this + 288) || *((_DWORD *)this + 212)) )
    {
      CAudioOrchestrator::EnsureCancelVAEngineTypeTransitionTimer((CAudioOrchestrator *)((char *)this - 40));
      *((_DWORD *)this + 391) = 1;
    }
    if ( a5 )
    {
      *a5 = *((_DWORD *)this + 232);
      if ( ((*((_QWORD *)this + 92) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        *((_DWORD *)this + 232) = 0;
    }
  }
  CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v17);
  WatchdogTimer::~WatchdogTimer((WatchdogTimer *)pv);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004f5c0  push    rbx
0x18004f5c2  push    rbp
0x18004f5c3  push    rsi
0x18004f5c4  push    rdi
0x18004f5c5  push    r12
0x18004f5c7  push    r14
0x18004f5c9  push    r15
0x18004f5cb  sub     rsp, 0A0h
0x18004f5d2  mov     rax, cs:__security_cookie
0x18004f5d9  xor     rax, rsp
0x18004f5dc  mov     [rsp+0D8h+var_48], rax
0x18004f5e4  mov     r15, r9
0x18004f5e7  mov     r14, r8
0x18004f5ea  mov     esi, edx
0x18004f5ec  mov     rbx, rcx
0x18004f5ef  mov     r12, [rsp+0D8h+arg_20]
0x18004f5f7  lea     rdx, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f5fe  lea     rcx, [rsp+0D8h+pv]; pv
0x18004f603  call    ??0WatchdogTimer@@QEAA@PEBD@Z; WatchdogTimer::WatchdogTimer(char const *)
0x18004f608  nop
0x18004f609  lea     rcx, [rbx+78h]; lpCriticalSection
0x18004f60d  mov     [rsp+0D8h+var_A0], rcx
0x18004f612  call    cs:__imp_EnterCriticalSection
0x18004f618  mov     [rsp+0D8h+var_98], 0
0x18004f620  mov     r9d, esi
0x18004f623  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f62a  lea     rdx, aSEnterDwreader; "[%s] enter, dwReaderCookie: %d"
0x18004f631  mov     ecx, 8; int
0x18004f636  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f63b  lea     rbp, [rbx-28h]
0x18004f63f  cmp     dword ptr [rbp+374h], 0
0x18004f646  jz      short loc_18004F65F
0x18004f648  mov     dword ptr [rbx+34Ch], 0
0x18004f652  mov     edx, 1; int
0x18004f657  mov     rcx, rbp; this
0x18004f65a  call    ?InvalidateAudioDevices@CAudioOrchestrator@@AEAAXH@Z; CAudioOrchestrator::InvalidateAudioDevices(int)
0x18004f65f  mov     rcx, rbp; this
0x18004f662  call    ?EnsureSetInput@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::EnsureSetInput(void)
0x18004f667  mov     edi, eax
0x18004f669  cmp     qword ptr [rbx+0F0h], 0
0x18004f671  jz      short loc_18004F68C
0x18004f673  cmp     esi, [rbx+478h]
0x18004f679  jnz     short loc_18004F68C
0x18004f67b  test    byte ptr [rbx+1E8h], 8
0x18004f682  jz      short loc_18004F68C
0x18004f684  mov     rcx, rbp; this
0x18004f687  call    ?RequestResetVAMaster@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::RequestResetVAMaster(void)
0x18004f68c  test    edi, edi
0x18004f68e  js      loc_18004F836
0x18004f694  test    r14, r14
0x18004f697  jnz     short loc_18004F6A3
0x18004f699  mov     edi, 80004003h
0x18004f69e  jmp     loc_18004F836
0x18004f6a3  test    byte ptr [rbx+1E8h], 20h
0x18004f6aa  jz      short loc_18004F6CE
0x18004f6ac  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f6b3  lea     rdx, aSXboxFailingRe; "[%s] XBox: Failing ReaderStartStream - "...
0x18004f6ba  mov     ecx, 8; int
0x18004f6bf  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f6c4  mov     edi, 8004503Bh
0x18004f6c9  jmp     loc_18004F836
0x18004f6ce  mov     al, [rbx+361h]
0x18004f6d4  nop
0x18004f6d5  test    al, al
0x18004f6d7  jnz     short loc_18004F729
0x18004f6d9  cmp     qword ptr [rbx+270h], 0
0x18004f6e1  jz      short loc_18004F704
0x18004f6e3  cmp     dword ptr [rbx+238h], 3
0x18004f6ea  jnz     short loc_18004F704
0x18004f6ec  mov     rcx, rbp; this
0x18004f6ef  call    ?CanVAStartInLowPower@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::CanVAStartInLowPower(void)
0x18004f6f4  test    eax, eax
0x18004f6f6  jnz     short loc_18004F729
0x18004f6f8  mov     rcx, rbp; this
0x18004f6fb  call    ?IsHWKWSOnS3SystemScreenOff@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::IsHWKWSOnS3SystemScreenOff(void)
0x18004f700  test    eax, eax
0x18004f702  jnz     short loc_18004F729
0x18004f704  mov     r9d, esi
0x18004f707  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f70e  lea     rdx, aSPowerEventFai; "[%s] Power Event: Failing ReaderStartSt"...
0x18004f715  mov     ecx, 2; int
0x18004f71a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f71f  mov     edi, 8004509Bh
0x18004f724  jmp     loc_18004F836
0x18004f729  mov     eax, [rbx+5CCh]
0x18004f72f  cmp     eax, 3
0x18004f732  jb      short loc_18004F74E
0x18004f734  mov     edi, 8004504Ch
0x18004f739  cmp     eax, 64h ; 'd'
0x18004f73c  jb      loc_18004F836
0x18004f742  mov     ecx, 8004504Ch; uExitCode
0x18004f747  call    cs:__imp_ExitProcess
0x18004f74e  cmp     esi, [rbx+47Ch]
0x18004f754  jz      short loc_18004F75E
0x18004f756  cmp     esi, [rbx+488h]
0x18004f75c  jnz     short loc_18004F77E
0x18004f75e  mov     rcx, rbp; this
0x18004f761  call    ?IsBurstReadSupported@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::IsBurstReadSupported(void)
0x18004f766  test    eax, eax
0x18004f768  jz      short loc_18004F77E
0x18004f76a  xor     r8d, r8d
0x18004f76d  xor     edx, edx
0x18004f76f  call    ?EnsureVAMasterSwitchToSoftware@CAudioOrchestrator@@AEAAJW4AUDIO_SCENARIO@1@K@Z; CAudioOrchestrator::EnsureVAMasterSwitchToSoftware(CAudioOrchestrator::AUDIO_SCENARIO,ulong)
0x18004f774  mov     edi, eax
0x18004f776  test    eax, eax
0x18004f778  js      loc_18004F836
0x18004f77e  cmp     esi, [rbx+478h]
0x18004f784  jz      loc_18004F819
0x18004f78a  cmp     esi, [rbx+484h]
0x18004f790  jz      loc_18004F819
0x18004f796  cmp     esi, [rbx+47Ch]
0x18004f79c  jz      short loc_18004F7A6
0x18004f79e  cmp     esi, [rbx+480h]
0x18004f7a4  jnz     short loc_18004F7AE
0x18004f7a6  mov     rcx, rbp; this
0x18004f7a9  call    ?UpdateMicrophoneMasking@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::UpdateMicrophoneMasking(void)
0x18004f7ae  cmp     esi, [rbx+478h]
0x18004f7b4  jz      short loc_18004F7BE
0x18004f7b6  cmp     esi, [rbx+488h]
0x18004f7bc  jnz     short loc_18004F7D6
0x18004f7be  xor     r9d, r9d; lParam
0x18004f7c1  lea     r8d, [r9+5]; wParam
0x18004f7c5  mov     edx, [rbx+49Ch]; Msg
0x18004f7cb  mov     ecx, 0FFFFh; hWnd
0x18004f7d0  call    cs:__imp_SendNotifyMessageW
0x18004f7d6  mov     r8d, 1; int
0x18004f7dc  mov     edx, esi; unsigned int
0x18004f7de  mov     rcx, rbp; this
0x18004f7e1  call    ?ShouldSwitchToDebugInputByReader@CAudioOrchestrator@@AEAAHKH@Z; CAudioOrchestrator::ShouldSwitchToDebugInputByReader(ulong,int)
0x18004f7e6  test    eax, eax
0x18004f7e8  jz      short loc_18004F7F8
0x18004f7ea  mov     rcx, rbp; this
0x18004f7ed  call    ?SwitchToDebugInput@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::SwitchToDebugInput(void)
0x18004f7f2  mov     edi, eax
0x18004f7f4  test    eax, eax
0x18004f7f6  js      short loc_18004F836
0x18004f7f8  mov     edx, esi; unsigned int
0x18004f7fa  mov     rcx, rbp; this
0x18004f7fd  call    ?AdjustReadersFromCachedPosition@CAudioOrchestrator@@AEAAJK@Z; CAudioOrchestrator::AdjustReadersFromCachedPosition(ulong)
0x18004f802  mov     edi, eax
0x18004f804  test    eax, eax
0x18004f806  js      short loc_18004F836
0x18004f808  mov     r8, r15; unsigned __int64 *
0x18004f80b  mov     edx, esi; unsigned int
0x18004f80d  mov     rcx, rbp; this
0x18004f810  call    ?AdjustReadersBeforeThisStreamStarts@CAudioOrchestrator@@AEAAJKPEA_K@Z; CAudioOrchestrator::AdjustReadersBeforeThisStreamStarts(ulong,unsigned __int64 *)
0x18004f815  mov     edi, eax
0x18004f817  jmp     short loc_18004F836
0x18004f819  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f820  lea     rdx, aSLegacyCortana; "[%s] Legacy Cortana has been disabled -"...
0x18004f827  mov     ecx, 8; int
0x18004f82c  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f831  mov     edi, 80004005h
0x18004f836  mov     [rsp+0D8h+var_A8], 0
0x18004f83e  lea     rcx, [rbx-20h]
0x18004f842  mov     rax, [rcx]
0x18004f845  lea     rdx, [rsp+0D8h+var_A8]
0x18004f84a  mov     rax, [rax+98h]
0x18004f851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f856  mov     r9d, [rsp+0D8h+var_A8]
0x18004f85b  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f862  lea     rdx, aSAudioIsCurren; "[%s] Audio is currently gated %i"
0x18004f869  mov     ecx, 8; int
0x18004f86e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f873  test    edi, edi
0x18004f875  js      loc_18004F9B2
0x18004f87b  cmp     [rsp+0D8h+var_A8], 0
0x18004f880  jz      short loc_18004F896
0x18004f882  cmp     esi, [rbx+480h]
0x18004f888  jz      short loc_18004F896
0x18004f88a  lea     rcx, [rbx+230h]; this
0x18004f891  call    ?SwitchToMic@CAudioOrchestratorInput@@QEAAHXZ; CAudioOrchestratorInput::SwitchToMic(void)
0x18004f896  mov     r8, r14; int *
0x18004f899  mov     edx, esi; unsigned int
0x18004f89b  mov     rcx, rbp; this
0x18004f89e  call    ?InternalReaderStartStream@CAudioOrchestrator@@AEAAJKPEAH@Z; CAudioOrchestrator::InternalReaderStartStream(ulong,int *)
0x18004f8a3  mov     edi, eax
0x18004f8a5  test    eax, eax
0x18004f8a7  js      loc_18004F9B2
0x18004f8ad  mov     edx, esi; unsigned int
0x18004f8af  mov     rcx, rbp; this
0x18004f8b2  call    ?AdjustReadersAfterThisStreamStarts@CAudioOrchestrator@@AEAAJK@Z; CAudioOrchestrator::AdjustReadersAfterThisStreamStarts(ulong)
0x18004f8b7  mov     edi, eax
0x18004f8b9  test    eax, eax
0x18004f8bb  js      loc_18004F9B2
0x18004f8c1  mov     edx, esi; unsigned int
0x18004f8c3  mov     rcx, rbp; this
0x18004f8c6  call    ?IsSystemCookie@CAudioOrchestrator@@AEAAHK@Z; CAudioOrchestrator::IsSystemCookie(ulong)
0x18004f8cb  test    eax, eax
0x18004f8cd  jz      short loc_18004F949
0x18004f8cf  call    ?EnsureCancelAudioStateTransitionTimer@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::EnsureCancelAudioStateTransitionTimer(void)
0x18004f8d4  cmp     dword ptr [rbx+388h], 0
0x18004f8db  jz      short loc_18004F959
0x18004f8dd  call    ?GetPolicy_VoiceOnSet@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_VoiceOnSet(void)
0x18004f8e2  test    eax, eax
0x18004f8e4  jz      short loc_18004F959
0x18004f8e6  mov     al, [rbx+3A5h]
0x18004f8ec  nop
0x18004f8ed  test    al, al
0x18004f8ef  jz      short loc_18004F91C
0x18004f8f1  mov     r9d, esi
0x18004f8f4  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f8fb  lea     rdx, aSOnHololensRel; "[%s] On hololens, Release conversation "...
0x18004f902  mov     ecx, 8; int
0x18004f907  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f90c  mov     rcx, rbp; this
0x18004f90f  call    ?EnsureAARSessionInactive@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::EnsureAARSessionInactive(void)
0x18004f914  mov     rcx, rbp; this
0x18004f917  call    ?ReleaseConversationSession@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::ReleaseConversationSession(void)
0x18004f91c  mov     r9d, esi
0x18004f91f  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f926  lea     rdx, aSOnHololensSet; "[%s] On hololens, Set 10sec timer when "...
0x18004f92d  mov     ecx, 8; int
0x18004f932  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f937  xor     edx, edx; enum _SPAUDIOSTATE
0x18004f939  mov     r8d, 2710h; unsigned int
0x18004f93f  mov     rcx, rbp; this
0x18004f942  call    ?ProcessAudioStateTransitionTimer@CAudioOrchestrator@@AEAAJW4_SPAUDIOSTATE@@K@Z; CAudioOrchestrator::ProcessAudioStateTransitionTimer(_SPAUDIOSTATE,ulong)
0x18004f947  jmp     short loc_18004F959
0x18004f949  cmp     esi, [rbp+4A8h]
0x18004f94f  jnz     short loc_18004F959
0x18004f951  xor     eax, eax
0x18004f953  xchg    eax, [rbx+10Ch]
0x18004f959  cmp     dword ptr [rbx+61Ch], 4
0x18004f960  jnz     short loc_18004F985
0x18004f962  cmp     esi, [rbx+480h]
0x18004f968  jnz     short loc_18004F973
0x18004f96a  cmp     dword ptr [rbx+350h], 0
0x18004f971  jz      short loc_18004F985
0x18004f973  mov     rcx, rbp; this
0x18004f976  call    ?EnsureCancelVAEngineTypeTransitionTimer@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::EnsureCancelVAEngineTypeTransitionTimer(void)
0x18004f97b  mov     dword ptr [rbx+61Ch], 1
0x18004f985  test    r12, r12
0x18004f988  jz      short loc_18004F9FF
0x18004f98a  mov     eax, [rbx+3A0h]
0x18004f990  mov     [r12], eax
0x18004f994  mov     rax, [rbx+2E0h]
0x18004f99b  inc     rax
0x18004f99e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004f9a4  jnz     short loc_18004F9FF
0x18004f9a6  mov     dword ptr [rbx+3A0h], 0
0x18004f9b0  jmp     short loc_18004F9FF
0x18004f9b2  mov     edx, esi; unsigned int
0x18004f9b4  mov     rcx, rbp; this
0x18004f9b7  call    ?InternalReaderStopOnError@CAudioOrchestrator@@AEAAJK@Z; CAudioOrchestrator::InternalReaderStopOnError(ulong)
0x18004f9bc  test    eax, eax
0x18004f9be  jns     short loc_18004F9DF
0x18004f9c0  mov     [rsp+0D8h+var_B8], eax
0x18004f9c4  mov     r9d, edi
0x18004f9c7  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f9ce  lea     rdx, aSAudioorchestr; "[%s] AudioOrchestrator: StartStream fai"...
0x18004f9d5  mov     ecx, 8; int
0x18004f9da  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f9df  test    edi, edi
0x18004f9e1  jns     short loc_18004F9FF
0x18004f9e3  mov     r9d, edi
0x18004f9e6  lea     r8, aCaudioorchestr_59; "CAudioOrchestrator::ReaderStartStream"
0x18004f9ed  lea     rdx, aSFailedHr0xX; "[%s] failed, hr: 0x%x"
0x18004f9f4  mov     ecx, 8; int
0x18004f9f9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18004f9fe  nop
0x18004f9ff  lea     rcx, [rsp+0D8h+var_A0]; this
0x18004fa04  call    ??1CSPAutoCritSecLock@@QEAA@XZ; CSPAutoCritSecLock::~CSPAutoCritSecLock(void)
0x18004fa09  nop
0x18004fa0a  lea     rcx, [rsp+0D8h+pv]; this
0x18004fa0f  call    ??1WatchdogTimer@@QEAA@XZ; WatchdogTimer::~WatchdogTimer(void)
0x18004fa14  mov     eax, edi
0x18004fa16  mov     rcx, [rsp+0D8h+var_48]
0x18004fa1e  xor     rcx, rsp; StackCookie
0x18004fa21  call    __security_check_cookie
0x18004fa26  add     rsp, 0A0h
0x18004fa2d  pop     r15
0x18004fa2f  pop     r14
0x18004fa31  pop     r12
0x18004fa33  pop     rdi
0x18004fa34  pop     rsi
0x18004fa35  pop     rbp
0x18004fa36  pop     rbx
0x18004fa37  retn
```
