# CAudioOrchestrator::ThreadProc(void *,void *,void *,HWND__ *,int const volatile *)

- ea: `0x1800b56a0`
- end: `0x1800b5c6a`
- name: `?ThreadProc@CAudioOrchestrator@@EEAAJPEAX00PEAUHWND__@@PEDH@Z`
- size: `1482`
- prototype: `__int64 __fastcall(CAudioOrchestrator *__hidden this, void *, void *, void *, HWND, const volatile int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000bec4`
- `0x180013ec0`
- `0x180049bfc`
- `0x18004d460`
- `0x180052af4`
- `0x180079e30`
- `0x1800ac1a8`
- `0x1800ae1c4`
- `0x1800ae480`
- `0x1800afa24`
- `0x1800b1480`
- `0x1800b2c48`
- `0x1800b32e8`
- `0x1800b4e08`
- `0x1800b56a0`
- `0x1800b6328`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b5742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b58bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b5742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b58bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5b64`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x1800b58ab`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x1800b58ab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800b58fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x1800b58fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800b58e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800b58e7`

## string_xrefs

- `0x1800b56ea`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5926`: `CAudioOrchestrator::ThreadProc`
- `0x1800b59d3`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5a64`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5a90`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5afc`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5b2a`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5bae`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5bdd`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5c24`: `CAudioOrchestrator::ThreadProc`
- `0x1800b5b31`: `[%s] PumpStream: APC operation completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAudioOrchestrator::ThreadProc(
        CAudioOrchestrator *this,
        void *a2,
        void *a3,
        void *a4,
        HWND a5,
        const volatile int *a6)
{
  CAudioOrchestrator *v7; // r12
  unsigned int Policy_NonRealtimeThreadPumpSpeedMultiplier; // r13d
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  DWORD v10; // edi
  char *v11; // rsi
  char *v12; // r15
  struct ISpAudio *v13; // rbx
  DWORD v14; // r13d
  DWORD v15; // r15d
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rsi
  __int128 v21; // xmm6
  DWORD LastError; // eax
  CSPAutoCritSecLock *v23; // rcx
  struct ISpInputDeviceSupport *v25; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v26; // [rsp+78h] [rbp-88h]
  char *v27; // [rsp+80h] [rbp-80h]
  struct ISpAudio *v28[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v29; // [rsp+A0h] [rbp-60h]
  void *v30; // [rsp+A8h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+B0h] [rbp-50h] BYREF
  int v32; // [rsp+B8h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+C0h] [rbp-40h] BYREF
  int v34; // [rsp+C8h] [rbp-38h]
  MSG Msg; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE pHandles[7]; // [rsp+100h] [rbp+0h] BYREF

  v30 = a3;
  v7 = (CAudioOrchestrator *)((char *)this - 72);
  Policy_NonRealtimeThreadPumpSpeedMultiplier = CAudioOrchestrator::GetPolicy_NonRealtimeThreadPumpSpeedMultiplier((CAudioOrchestrator *)((char *)this - 72));
  v26 = Policy_NonRealtimeThreadPumpSpeedMultiplier;
  DoTraceMessage(8, "[%s] enter", "CAudioOrchestrator::ThreadProc");
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  while ( *a6 )
  {
    v10 = -1;
    v11 = 0;
    v29 = 0;
    v12 = 0;
    v27 = 0;
    if ( !*((_DWORD *)this + 134) )
      goto LABEL_18;
    v31 = v9;
    EnterCriticalSection(v9);
    v32 = 0;
    v28[0] = 0;
    v25 = 0;
    CAudioOrchestratorInput::GetCurrentInputFamily((CAudioOrchestrator *)((char *)this + 528), 0, v28, 0, &v25);
    v13 = v28[0];
    if ( v28[0] )
    {
      v11 = (char *)((__int64 (__fastcall *)(struct ISpAudio *))v28[0]->lpVtbl->EventHandle)(v28[0]);
      v29 = v11;
    }
    if ( v25 )
    {
      if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_10;
      v12 = (char *)(*(__int64 (**)(void))(*(_QWORD *)v25 + 32LL))();
      v27 = v12;
    }
    else
    {
      v12 = 0;
      v27 = 0;
      if ( ((unsigned __int64)(v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
LABEL_10:
        if ( *((_DWORD *)this + 184) == 3 )
        {
          v10 = !Policy_NonRealtimeThreadPumpSpeedMultiplier || v13
              ? 1
              : 0x32 / Policy_NonRealtimeThreadPumpSpeedMultiplier;
          if ( *((_DWORD *)this + 218) && (unsigned int)CAudioOrchestrator::GetPolicy_VoiceOnSet(v25) )
          {
            DoTraceMessage(
              2,
              "[%s] audio history buffer is freed while audio is in RUN state on HoloLens",
              "CAudioOrchestrator::ThreadProc");
            ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
            ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v28);
            v23 = (CSPAutoCritSecLock *)&v31;
LABEL_62:
            CSPAutoCritSecLock::~CSPAutoCritSecLock(v23);
            break;
          }
        }
      }
    }
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v28);
    CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v31);
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
LABEL_18:
    pHandles[0] = v30;
    pHandles[1] = *((HANDLE *)this + 91);
    pHandles[2] = *((HANDLE *)this + 53);
    pHandles[3] = *((HANDLE *)this + 55);
    pHandles[4] = *((HANDLE *)this + 56);
    pHandles[5] = v11;
    pHandles[6] = v12;
    if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      v14 = 5;
    else
      v14 = 7 - ((unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL);
    v15 = MsgWaitForMultipleObjectsEx(v14, pHandles, v10, 0x1CFFu, 2u);
    v33 = v9;
    EnterCriticalSection(v9);
    v34 = 0;
    if ( v15 == v14 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        DispatchMessageW(&Msg);
    }
    else
    {
      switch ( v15 )
      {
        case 0u:
          v23 = (CSPAutoCritSecLock *)&v33;
          goto LABEL_62;
        case 1u:
          DoTraceMessage(
            8,
            "[%s] PumpStream: State Change Event %i",
            "CAudioOrchestrator::ThreadProc",
            *((_DWORD *)this + 184));
          break;
        case 2u:
          if ( (unsigned int)(*((_DWORD *)this + 48) - 2) > 1 )
            goto LABEL_57;
          LODWORD(v25) = 0;
          v16 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, struct ISpInputDeviceSupport **))(**((_QWORD **)this + 23) + 56LL))(
                  *((_QWORD *)this + 23),
                  L"DebugAudioInputFile_PostMec",
                  &v25);
          if ( v16 >= 0 )
          {
            *((_BYTE *)this + 420) = (_DWORD)v25 == 1;
            if ( (_DWORD)v25 )
            {
              if ( *((_DWORD *)this + 134) == 2 )
                CAudioOrchestrator::InvalidateAudioDevices(v7, 1);
              v26 = CAudioOrchestrator::GetPolicy_NonRealtimeThreadPumpSpeedMultiplier(v7);
            }
          }
          DoTraceMessage(
            8,
            "[%s] PumpStream: WAV input available change %i - 0x%x - %i",
            "CAudioOrchestrator::ThreadProc",
            *((unsigned __int8 *)this + 420),
            v16,
            (_DWORD)v25);
          goto LABEL_58;
        case 3u:
          CAudioOrchestrator::UpdateMicrophoneMasking(v7);
          break;
        case 4u:
          DoTraceMessage(8, ">> [%s] ", "CAudioOrchestrator::HandleAarRestart");
          if ( *((_QWORD *)v7 + 37) )
          {
            CAudioOrchestrator::ReleaseConversationSession(v7);
            CAudioOrchestrator::ReleaseAllInputs(v7);
          }
          DoTraceMessage(8, "<< [%s] ", "CAudioOrchestrator::HandleAarRestart");
          break;
        case 5u:
          if ( (int)CAudioOrchestrator::PumpStream(v7) < 0 )
          {
            DoTraceMessage(8, "[%s] PumpStream: InvalidateAudioDevices", "CAudioOrchestrator::ThreadProc");
            CAudioOrchestrator::InvalidateAudioDevices(v7, 1);
          }
          break;
        case 6u:
          DoTraceMessage(
            8,
            "[%s] PumpStream: persistant input object changing internal device state",
            "CAudioOrchestrator::ThreadProc");
          CAudioOrchestrator::InvalidateAudioDevices(v7, 1);
          CAudioOrchestrator::RequestResetVAMaster(v7);
          break;
        case 0x102u:
          if ( *((_DWORD *)this + 134) != 2 || *((_DWORD *)this + 184) != 3 )
            goto LABEL_57;
          v17 = CAudioOrchestrator::PumpStream(v7);
          if ( v17 < 0 || v17 == 282725 || v17 == 282640 )
          {
            DoTraceMessage(8, "[%s] PumpStream: SwitchBackToPrimaryInput - 0x%x", "CAudioOrchestrator::ThreadProc", v17);
            CAudioOrchestrator::SwitchBackToPrimaryInput(v7);
          }
          break;
        case 0xC0u:
          DoTraceMessage(8, "[%s] PumpStream: APC operation completed", "CAudioOrchestrator::ThreadProc");
          break;
        default:
LABEL_57:
          v18 = *((_QWORD *)this + 56);
          v19 = *((_QWORD *)this + 55);
          v20 = *((_QWORD *)this + 53);
          v21 = *((_OWORD *)this + 45);
          LastError = GetLastError();
          *(_OWORD *)v28 = v21;
          DoTraceMessage(
            2,
            "[%s] PumpStream: unexpected state: %i, %i, %i, 0x%x, 0x%x, 0x%x, 0x%x, 0x%x, 0x%x, 0x%x",
            "CAudioOrchestrator::ThreadProc",
            v15,
            LastError,
            v14,
            (_DWORD)v30,
            (unsigned int)v28,
            v20,
            v19,
            v18,
            (_DWORD)v29,
            (_DWORD)v27);
LABEL_58:
          v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
          break;
      }
    }
    CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v33);
    Policy_NonRealtimeThreadPumpSpeedMultiplier = v26;
  }
  CAudioOrchestrator::EnsureInternalUpdateAudioState(v7, SPAS_CLOSED);
  DoTraceMessage(8, "[%s] return", "CAudioOrchestrator::ThreadProc");
  return 0;
}

```

## disassembly

```asm
0x1800b56a0  mov     rax, rsp
0x1800b56a3  mov     [rax+10h], rbx
0x1800b56a7  push    rbp
0x1800b56a8  push    rsi
0x1800b56a9  push    rdi
0x1800b56aa  push    r12
0x1800b56ac  push    r13
0x1800b56ae  push    r14
0x1800b56b0  push    r15
0x1800b56b2  lea     rbp, [rsp-50h]
0x1800b56b7  sub     rsp, 150h
0x1800b56be  movaps  xmmword ptr [rax-48h], xmm6
0x1800b56c2  mov     rax, cs:__security_cookie
0x1800b56c9  xor     rax, rsp
0x1800b56cc  mov     [rbp+80h+var_48], rax
0x1800b56d0  mov     [rbp+80h+var_D8], r8
0x1800b56d4  mov     r14, rcx
0x1800b56d7  lea     r12, [rcx-48h]
0x1800b56db  mov     rcx, r12; this
0x1800b56de  call    ?GetPolicy_NonRealtimeThreadPumpSpeedMultiplier@CAudioOrchestrator@@AEAAKXZ; CAudioOrchestrator::GetPolicy_NonRealtimeThreadPumpSpeedMultiplier(void)
0x1800b56e3  mov     r13d, eax
0x1800b56e6  mov     [rsp+180h+var_108], eax
0x1800b56ea  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b56f1  lea     rdx, aSEnter; "[%s] enter"
0x1800b56f8  mov     ecx, 8; int
0x1800b56fd  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5702  lea     rbx, [r14+58h]
0x1800b5706  mov     rcx, 0FFFFFFFFFFFFFFFDh
0x1800b570d  mov     rax, [rbp+80h+arg_28]
0x1800b5714  mov     eax, [rax]
0x1800b5716  test    eax, eax
0x1800b5718  jz      loc_1800B5C1A
0x1800b571e  or      edi, 0FFFFFFFFh
0x1800b5721  xor     esi, esi
0x1800b5723  mov     [rbp+80h+var_E0], rsi
0x1800b5727  xor     r15d, r15d
0x1800b572a  mov     [rbp+80h+var_100], r15
0x1800b572e  cmp     [r14+218h], esi
0x1800b5735  jz      loc_1800B5838
0x1800b573b  mov     [rbp+80h+var_D0], rbx
0x1800b573f  mov     rcx, rbx; lpCriticalSection
0x1800b5742  call    cs:__imp_EnterCriticalSection
0x1800b5748  xor     eax, eax
0x1800b574a  mov     [rbp+80h+var_C8], eax
0x1800b574d  mov     [rbp+80h+var_F0], rax
0x1800b5751  mov     [rsp+180h+var_110], rax
0x1800b5756  lea     rcx, [r14+210h]; this
0x1800b575d  lea     rax, [rsp+180h+var_110]
0x1800b5762  mov     qword ptr [rsp+180h+dwFlags], rax; struct ISpInputDeviceSupport **
0x1800b5767  xor     r9d, r9d; struct ISpAudioStream **
0x1800b576a  lea     r8, [rbp+80h+var_F0]; struct ISpAudio **
0x1800b576e  xor     edx, edx; struct ISpStreamFormat **
0x1800b5770  call    ?GetCurrentInputFamily@CAudioOrchestratorInput@@QEAAJPEAPEAUISpStreamFormat@@PEAPEAUISpAudio@@PEAPEAUISpAudioStream@@PEAPEAUISpInputDeviceSupport@@@Z; CAudioOrchestratorInput::GetCurrentInputFamily(ISpStreamFormat * *,ISpAudio * *,ISpAudioStream * *,ISpInputDeviceSupport * *)
0x1800b5775  mov     rbx, [rbp+80h+var_F0]
0x1800b5779  test    rbx, rbx
0x1800b577c  jz      short loc_1800B5797
0x1800b577e  mov     rax, [rbx]
0x1800b5781  mov     rcx, rbx
0x1800b5784  mov     rax, [rax+0A8h]
0x1800b578b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5790  mov     rsi, rax
0x1800b5793  mov     [rbp+80h+var_E0], rax
0x1800b5797  mov     rcx, [rsp+180h+var_110]; this
0x1800b579c  test    rcx, rcx
0x1800b579f  jz      short loc_1800B57C0
0x1800b57a1  lea     rdx, [rsi-1]
0x1800b57a5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800b57a9  ja      short loc_1800B57D3
0x1800b57ab  mov     rdx, [rcx]
0x1800b57ae  mov     rax, [rdx+20h]
0x1800b57b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b57b7  mov     r15, rax
0x1800b57ba  mov     [rbp+80h+var_100], rax
0x1800b57be  jmp     short loc_1800B580F
0x1800b57c0  xor     r15d, r15d
0x1800b57c3  mov     [rbp+80h+var_100], r15
0x1800b57c7  lea     rax, [rsi+1]
0x1800b57cb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b57d1  jnz     short loc_1800B580F
0x1800b57d3  cmp     dword ptr [r14+2E0h], 3
0x1800b57db  jnz     short loc_1800B580F
0x1800b57dd  test    r13d, r13d
0x1800b57e0  jz      short loc_1800B57F3
0x1800b57e2  test    rbx, rbx
0x1800b57e5  jnz     short loc_1800B57F3
0x1800b57e7  xor     edx, edx
0x1800b57e9  lea     eax, [rbx+32h]
0x1800b57ec  div     r13d
0x1800b57ef  mov     edi, eax
0x1800b57f1  jmp     short loc_1800B57F8
0x1800b57f3  mov     edi, 1
0x1800b57f8  cmp     dword ptr [r14+368h], 0
0x1800b5800  jz      short loc_1800B580F
0x1800b5802  call    ?GetPolicy_VoiceOnSet@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_VoiceOnSet(void)
0x1800b5807  test    eax, eax
0x1800b5809  jnz     loc_1800B5BDD
0x1800b580f  lea     rcx, [rsp+180h+var_110]
0x1800b5814  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800b5819  nop
0x1800b581a  lea     rcx, [rbp+80h+var_F0]
0x1800b581e  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800b5823  nop
0x1800b5824  lea     rcx, [rbp+80h+var_D0]; this
0x1800b5828  call    ??1CSPAutoCritSecLock@@QEAA@XZ; CSPAutoCritSecLock::~CSPAutoCritSecLock(void)
0x1800b582d  lea     rbx, [r14+58h]
0x1800b5831  mov     rcx, 0FFFFFFFFFFFFFFFDh
0x1800b5838  mov     rax, [rbp+80h+var_D8]
0x1800b583c  mov     [rbp+80h+pHandles], rax
0x1800b5840  mov     rax, [r14+2D8h]
0x1800b5847  mov     [rbp+80h+var_78], rax
0x1800b584b  mov     rax, [r14+1A8h]
0x1800b5852  mov     [rbp+80h+var_70], rax
0x1800b5856  mov     rax, [r14+1B8h]
0x1800b585d  mov     [rbp+80h+var_68], rax
0x1800b5861  mov     rax, [r14+1C0h]
0x1800b5868  mov     [rbp+80h+var_60], rax
0x1800b586c  mov     [rbp+80h+var_58], rsi
0x1800b5870  mov     [rbp+80h+var_50], r15
0x1800b5874  lea     rax, [rsi-1]
0x1800b5878  cmp     rax, rcx
0x1800b587b  ja      short loc_1800B588D
0x1800b587d  lea     rax, [r15-1]
0x1800b5881  cmp     rcx, rax
0x1800b5884  sbb     r13d, r13d
0x1800b5887  add     r13d, 7
0x1800b588b  jmp     short loc_1800B5893
0x1800b588d  mov     r13d, 5
0x1800b5893  mov     [rsp+180h+dwFlags], 2; dwFlags
0x1800b589b  mov     r9d, 1CFFh; dwWakeMask
0x1800b58a1  mov     r8d, edi; dwMilliseconds
0x1800b58a4  lea     rdx, [rbp+80h+pHandles]; pHandles
0x1800b58a8  mov     ecx, r13d; nCount
0x1800b58ab  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x1800b58b1  mov     r15d, eax
0x1800b58b4  mov     [rbp+80h+var_C0], rbx
0x1800b58b8  mov     rcx, rbx; lpCriticalSection
0x1800b58bb  call    cs:__imp_EnterCriticalSection
0x1800b58c1  mov     [rbp+80h+var_B8], 0
0x1800b58c8  cmp     r15d, r13d
0x1800b58cb  jnz     short loc_1800B590C
0x1800b58cd  xorps   xmm0, xmm0
0x1800b58d0  movups  xmmword ptr [rbp+80h+Msg.hwnd], xmm0
0x1800b58d4  movups  xmmword ptr [rbp+80h+Msg.wParam], xmm0
0x1800b58d8  movups  xmmword ptr [rbp+80h+Msg.time], xmm0
0x1800b58dc  mov     edi, 1
0x1800b58e1  jmp     short loc_1800B58ED
0x1800b58e3  lea     rcx, [rbp+80h+Msg]; lpMsg
0x1800b58e7  call    cs:__imp_DispatchMessageW
0x1800b58ed  mov     [rsp+180h+dwFlags], edi; wRemoveMsg
0x1800b58f1  xor     r9d, r9d; wMsgFilterMax
0x1800b58f4  xor     r8d, r8d; wMsgFilterMin
0x1800b58f7  xor     edx, edx; hWnd
0x1800b58f9  lea     rcx, [rbp+80h+Msg]; lpMsg
0x1800b58fd  call    cs:__imp_PeekMessageW
0x1800b5903  test    eax, eax
0x1800b5905  jnz     short loc_1800B58E3
0x1800b5907  jmp     loc_1800B5BCA
0x1800b590c  test    r15d, r15d
0x1800b590f  jz      loc_1800B5C11
0x1800b5915  mov     edi, 1
0x1800b591a  cmp     r15d, edi
0x1800b591d  jnz     short loc_1800B5941
0x1800b591f  mov     r9d, [r14+2E0h]
0x1800b5926  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b592d  lea     rdx, aSPumpstreamSta; "[%s] PumpStream: State Change Event %i"
0x1800b5934  lea     ecx, [rdi+7]; int
0x1800b5937  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b593c  jmp     loc_1800B5BCA
0x1800b5941  cmp     r15d, 2
0x1800b5945  jnz     loc_1800B59F0
0x1800b594b  mov     eax, [r14+0C0h]
0x1800b5952  sub     eax, r15d
0x1800b5955  cmp     eax, edi
0x1800b5957  ja      loc_1800B5B47
0x1800b595d  mov     dword ptr [rsp+180h+var_110], 0
0x1800b5965  mov     rcx, [r14+0B8h]
0x1800b596c  mov     rax, [rcx]
0x1800b596f  lea     r8, [rsp+180h+var_110]
0x1800b5974  lea     rdx, aDebugaudioinpu_0; "DebugAudioInputFile_PostMec"
0x1800b597b  mov     rax, [rax+38h]
0x1800b597f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5984  mov     ebx, eax
0x1800b5986  test    eax, eax
0x1800b5988  js      short loc_1800B59BE
0x1800b598a  cmp     dword ptr [rsp+180h+var_110], edi
0x1800b598e  setz    cl
0x1800b5991  xchg    cl, [r14+1A4h]
0x1800b5998  cmp     dword ptr [rsp+180h+var_110], 0
0x1800b599d  jz      short loc_1800B59BE
0x1800b599f  cmp     [r14+218h], r15d
0x1800b59a6  jnz     short loc_1800B59B2
0x1800b59a8  mov     edx, edi; int
0x1800b59aa  mov     rcx, r12; this
0x1800b59ad  call    ?InvalidateAudioDevices@CAudioOrchestrator@@AEAAXH@Z; CAudioOrchestrator::InvalidateAudioDevices(int)
0x1800b59b2  mov     rcx, r12; this
0x1800b59b5  call    ?GetPolicy_NonRealtimeThreadPumpSpeedMultiplier@CAudioOrchestrator@@AEAAKXZ; CAudioOrchestrator::GetPolicy_NonRealtimeThreadPumpSpeedMultiplier(void)
0x1800b59ba  mov     [rsp+180h+var_108], eax
0x1800b59be  mov     ecx, dword ptr [rsp+180h+var_110]
0x1800b59c2  movzx   r9d, byte ptr [r14+1A4h]
0x1800b59ca  nop
0x1800b59cb  mov     [rsp+180h+var_158], ecx
0x1800b59cf  mov     [rsp+180h+dwFlags], ebx
0x1800b59d3  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b59da  lea     rdx, aSPumpstreamWav; "[%s] PumpStream: WAV input available ch"...
0x1800b59e1  mov     ecx, 8; int
0x1800b59e6  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b59eb  jmp     loc_1800B5BC6
0x1800b59f0  cmp     r15d, 3
0x1800b59f4  jnz     short loc_1800B5A03
0x1800b59f6  mov     rcx, r12; this
0x1800b59f9  call    ?UpdateMicrophoneMasking@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::UpdateMicrophoneMasking(void)
0x1800b59fe  jmp     loc_1800B5BCA
0x1800b5a03  cmp     r15d, 4
0x1800b5a07  jnz     short loc_1800B5A4E
0x1800b5a09  lea     r8, aCaudioorchestr_66; "CAudioOrchestrator::HandleAarRestart"
0x1800b5a10  lea     rdx, aS_7; ">> [%s] "
0x1800b5a17  lea     ecx, [r15+4]; int
0x1800b5a1b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5a20  cmp     qword ptr [r12+128h], 0
0x1800b5a29  jz      short loc_1800B5A3B
0x1800b5a2b  mov     rcx, r12; this
0x1800b5a2e  call    ?ReleaseConversationSession@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::ReleaseConversationSession(void)
0x1800b5a33  mov     rcx, r12; this
0x1800b5a36  call    ?ReleaseAllInputs@CAudioOrchestrator@@AEAAXXZ; CAudioOrchestrator::ReleaseAllInputs(void)
0x1800b5a3b  lea     r8, aCaudioorchestr_66; "CAudioOrchestrator::HandleAarRestart"
0x1800b5a42  lea     rdx, aS_5; "<< [%s] "
0x1800b5a49  jmp     loc_1800B5B38
0x1800b5a4e  cmp     r15d, 5
0x1800b5a52  jnz     short loc_1800B5A8A
0x1800b5a54  mov     rcx, r12; this
0x1800b5a57  call    ?PumpStream@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::PumpStream(void)
0x1800b5a5c  test    eax, eax
0x1800b5a5e  jns     loc_1800B5BCA
0x1800b5a64  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b5a6b  lea     rdx, aSPumpstreamInv; "[%s] PumpStream: InvalidateAudioDevices"
0x1800b5a72  lea     ecx, [r15+3]; int
0x1800b5a76  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5a7b  mov     edx, edi; int
0x1800b5a7d  mov     rcx, r12; this
0x1800b5a80  call    ?InvalidateAudioDevices@CAudioOrchestrator@@AEAAXH@Z; CAudioOrchestrator::InvalidateAudioDevices(int)
0x1800b5a85  jmp     loc_1800B5BCA
0x1800b5a8a  cmp     r15d, 6
0x1800b5a8e  jnz     short loc_1800B5ABE
0x1800b5a90  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b5a97  lea     rdx, aSPumpstreamPer; "[%s] PumpStream: persistant input objec"...
0x1800b5a9e  lea     ecx, [r15+2]; int
0x1800b5aa2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5aa7  mov     edx, edi; int
0x1800b5aa9  mov     rcx, r12; this
0x1800b5aac  call    ?InvalidateAudioDevices@CAudioOrchestrator@@AEAAXH@Z; CAudioOrchestrator::InvalidateAudioDevices(int)
0x1800b5ab1  mov     rcx, r12; this
0x1800b5ab4  call    ?RequestResetVAMaster@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::RequestResetVAMaster(void)
0x1800b5ab9  jmp     loc_1800B5BCA
0x1800b5abe  cmp     r15d, 102h
0x1800b5ac5  jnz     short loc_1800B5B21
0x1800b5ac7  cmp     dword ptr [r14+218h], 2
0x1800b5acf  jnz     short loc_1800B5B47
0x1800b5ad1  cmp     dword ptr [r14+2E0h], 3
0x1800b5ad9  jnz     short loc_1800B5B47
0x1800b5adb  mov     rcx, r12; this
0x1800b5ade  call    ?PumpStream@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::PumpStream(void)
0x1800b5ae3  test    eax, eax
0x1800b5ae5  js      short loc_1800B5AF9
0x1800b5ae7  cmp     eax, 45065h
0x1800b5aec  jz      short loc_1800B5AF9
0x1800b5aee  cmp     eax, 45010h
0x1800b5af3  jnz     loc_1800B5BCA
0x1800b5af9  mov     r9d, eax
0x1800b5afc  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b5b03  lea     rdx, aSPumpstreamSwi; "[%s] PumpStream: SwitchBackToPrimaryInp"...
0x1800b5b0a  mov     ecx, 8; int
0x1800b5b0f  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5b14  mov     rcx, r12; this
0x1800b5b17  call    ?SwitchBackToPrimaryInput@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::SwitchBackToPrimaryInput(void)
0x1800b5b1c  jmp     loc_1800B5BCA
0x1800b5b21  cmp     r15d, 0C0h
0x1800b5b28  jnz     short loc_1800B5B47
0x1800b5b2a  lea     r8, aCaudioorchestr_9; "CAudioOrchestrator::ThreadProc"
0x1800b5b31  lea     rdx, aSPumpstreamApc; "[%s] PumpStream: APC operation complete"...
0x1800b5b38  mov     ecx, 8; int
0x1800b5b3d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800b5b42  jmp     loc_1800B5BCA
0x1800b5b47  mov     rbx, [r14+1C0h]
0x1800b5b4e  mov     rdi, [r14+1B8h]
0x1800b5b55  mov     rsi, [r14+1A8h]
0x1800b5b5c  movups  xmm6, xmmword ptr [r14+2D0h]
0x1800b5b64  call    cs:__imp_GetLastError
0x1800b5b6a  movdqu  xmmword ptr [rbp+80h+var_F0], xmm6
0x1800b5b6f  mov     rcx, [rbp+80h+var_100]
0x1800b5b73  mov     [rsp+180h+var_120], rcx
0x1800b5b78  mov     rcx, [rbp+80h+var_E0]
0x1800b5b7c  mov     [rsp+180h+var_128], rcx
0x1800b5b81  mov     [rsp+180h+var_130], rbx
0x1800b5b86  mov     [rsp+180h+var_138], rdi
0x1800b5b8b  mov     [rsp+180h+var_140], rsi
0x1800b5b90  lea     rcx, [rbp+80h+var_F0]
0x1800b5b94  mov     [rsp+180h+var_148], rcx
0x1800b5b99  mov     rcx, [rbp+80h+var_D8]
0x1800b5b9d  mov     [rsp+180h+var_150], rcx
0x1800b5ba2  mov     [rsp+180h+var_158], r13d
  ... truncated ...
```
