# CAudioOrchestrator::HandleAARDetectionEvent(void)

- ea: `0x18006a7f8`
- end: `0x18006ac9a`
- name: `?HandleAARDetectionEvent@CAudioOrchestrator@@AEAAJXZ`
- size: `1186`
- prototype: `__int64 __fastcall(CAudioOrchestrator *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a7a0`

## callees

- `0x180013ec0`
- `0x180021944`
- `0x180026508`
- `0x180049bfc`
- `0x18006a7f8`
- `0x180079e30`
- `0x18007aae4`
- `0x1800ab0d0`
- `0x1800adcdc`
- `0x1800ae480`
- `0x1800b6dc8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a82e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a82e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a95a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ab32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a939`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a95a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ab32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a99b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a99b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ac65`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006ac65`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAudioOrchestrator::HandleAARDetectionEvent(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // ebx
  CAudioOrchestrator *v3; // rcx
  HANDLE OwningThread; // rdi
  __int64 (__fastcall *v5)(HANDLE, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  const wchar_t *StringRawBuffer; // rax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  CAudioOrchestrator *v20; // rcx
  int Policy_VoiceOnSet; // eax
  __int64 v22; // rdx
  int v23; // eax
  HWND v24; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  _BYTE *v27; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v34 = this + 4;
  EnterCriticalSection(this + 4);
  v35 = 0;
  if ( this[7].OwningThread )
  {
    if ( (unsigned int)CAudioOrchestrator::CanVAStart((CAudioOrchestrator *)this) )
    {
      DoTraceMessage(8, "[%s] VA can start", "CAudioOrchestrator::HandleAARDetectionEvent");
      goto LABEL_8;
    }
    if ( LODWORD(this[23].LockSemaphore) )
    {
      if ( (unsigned int)CAudioOrchestrator::GetPolicy_VoiceOnSet(v3) )
      {
        DoTraceMessage(8, "[%s] Voice onset enabled", "CAudioOrchestrator::HandleAARDetectionEvent");
LABEL_8:
        if ( LOBYTE(this[24].RecursionCount) )
        {
          DoTraceMessage(
            8,
            "[%s] AAR current session is active, ignore the new event",
            "CAudioOrchestrator::HandleAARDetectionEvent");
LABEL_37:
          v2 = 0;
          goto LABEL_38;
        }
        string = 0;
        v29 = 0;
        OwningThread = this[7].OwningThread;
        v5 = *(__int64 (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)OwningThread + 112LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        v6 = v5(OwningThread, &v29);
        v2 = v6;
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23D8,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
            (const char *)(unsigned int)v6,
            v26);
LABEL_12:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_38;
        }
        v7 = v29;
        v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 80LL);
        WindowsDeleteString(string);
        string = 0;
        v9 = v8(v7, &string);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x23DB,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
            (const char *)(unsigned int)v9,
            v26);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        DoTraceMessage(
          8,
          "[%s] AAR detected signal name %S",
          "CAudioOrchestrator::HandleAARDetectionEvent",
          StringRawBuffer);
        LOBYTE(this[24].RecursionCount) = 1;
        v31 = 0;
        v30 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        CAudioOrchestratorInput::GetInputFamily(&this[15], 3, &v31, 0, 0, 0);
        v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
        if ( v31 )
        {
          v14 = **v31;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          v15 = v14(v11, &GUID_251ab6f7_5ffa_42d8_a2e9_5b05f617a03b, &v30);
          v2 = v15;
          if ( v15 >= 0 )
          {
            v32 = 0;
            v33 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 112LL))(v29, &v32);
            v2 = v16;
            if ( v16 >= 0 )
            {
              v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 128LL))(v29, &v33);
              v2 = v17;
              if ( v17 >= 0 )
              {
                v36 = 0;
                v37 = 0;
                v18 = (*(__int64 (__fastcall **)(HANDLE, __int128 *))(*(_QWORD *)this[7].OwningThread + 304LL))(
                        this[7].OwningThread,
                        &v36);
                v2 = v18;
                if ( v18 >= 0 )
                {
                  if ( (_BYTE)v37 )
                  {
                    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 56LL))(
                            v30,
                            (unsigned int)v36,
                            *((_QWORD *)&v36 + 1));
                    v2 = v19;
                    if ( v19 < 0 )
                    {
                      v12 = (unsigned int)v19;
                      v13 = 9197;
                      goto LABEL_17;
                    }
                    DoTraceMessage(
                      8,
                      "[%s] AAR detected signal start time %lld, end time %lld, audio stream time %lld",
                      "CAudioOrchestrator::HandleAARDetectionEvent",
                      v32,
                      v33,
                      *((_QWORD *)&v36 + 1));
                    memset_0(v38, 0, 0x78u);
                    v39 = 1;
                    v40 = v32;
                    v41 = v33;
                    if ( !LODWORD(this[23].LockSemaphore)
                      || (Policy_VoiceOnSet = CAudioOrchestrator::GetPolicy_VoiceOnSet(v20),
                          v22 = 501,
                          !Policy_VoiceOnSet) )
                    {
                      v22 = 213;
                    }
                    v27 = v38;
                    v23 = (*(__int64 (__fastcall **)(ULONG_PTR *, __int64, _QWORD, __int64))(this->SpinCount + 32))(
                            &this->SpinCount,
                            v22,
                            0,
                            2);
                    v2 = v23;
                    if ( v23 < 0 )
                    {
                      v12 = (unsigned int)v23;
                      v13 = 9212;
                      goto LABEL_17;
                    }
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
                  WindowsDeleteString(string);
                  string = 0;
                  goto LABEL_37;
                }
                v12 = (unsigned int)v18;
                v13 = 9195;
              }
              else
              {
                v12 = (unsigned int)v17;
                v13 = 9192;
              }
            }
            else
            {
              v12 = (unsigned int)v16;
              v13 = 9191;
            }
          }
          else
          {
            v12 = (unsigned int)v15;
            v13 = 9188;
          }
        }
        else
        {
          v2 = -2147024809;
          v12 = 2147942487LL;
          v13 = 9187;
        }
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
          (const char *)v12,
          (int)v27);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        goto LABEL_12;
      }
      DoTraceMessage(8, "[%s] Voice onset NOT enabled", "CAudioOrchestrator::HandleAARDetectionEvent");
    }
    DoTraceMessage(8, "[%s] Ignoring event", "CAudioOrchestrator::HandleAARDetectionEvent");
    v24 = (HWND)(*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[6].DebugInfo + 80LL))(this[6].DebugInfo);
    PostMessageW(v24, 0x8000u, 1u, 6);
    goto LABEL_37;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23B1,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
    (const char *)0x80070057LL,
    v26);
LABEL_38:
  CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v34);
  return v2;
}

```

## disassembly

```asm
0x18006a7f8  push    rbp
0x18006a7fa  push    rbx
0x18006a7fb  push    rsi
0x18006a7fc  push    rdi
0x18006a7fd  push    r12
0x18006a7ff  push    r13
0x18006a801  push    r14
0x18006a803  push    r15
0x18006a805  lea     rbp, [rsp-38h]
0x18006a80a  sub     rsp, 138h
0x18006a811  mov     rax, cs:__security_cookie
0x18006a818  xor     rax, rsp
0x18006a81b  mov     [rbp+70h+var_50], rax
0x18006a81f  mov     r14, rcx
0x18006a822  add     rcx, 0A0h; lpCriticalSection
0x18006a829  mov     [rsp+170h+var_100], rcx
0x18006a82e  call    cs:__imp_EnterCriticalSection
0x18006a834  xor     r13d, r13d
0x18006a837  mov     [rsp+170h+var_F8], r13d
0x18006a83c  cmp     [r14+128h], r13
0x18006a843  jnz     short loc_18006A867
0x18006a845  mov     rcx, [rbp+78h]; this
0x18006a849  mov     ebx, 80070057h
0x18006a84e  mov     r9d, ebx; char *
0x18006a851  lea     r8, aOnecoreuapEndu_136; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18006a858  mov     edx, 23B1h; void *
0x18006a85d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a862  jmp     loc_18006AC6E
0x18006a867  mov     rcx, r14; this
0x18006a86a  call    ?CanVAStart@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::CanVAStart(void)
0x18006a86f  mov     r15d, 8
0x18006a875  lea     r12, aCaudioorchestr_62; "CAudioOrchestrator::HandleAARDetectionE"...
0x18006a87c  test    eax, eax
0x18006a87e  jz      short loc_18006A889
0x18006a880  lea     rdx, aSVaCanStart; "[%s] VA can start"
0x18006a887  jmp     short loc_18006A8AA
0x18006a889  cmp     [r14+3B0h], r13d
0x18006a890  jz      loc_18006AC2E
0x18006a896  call    ?GetPolicy_VoiceOnSet@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_VoiceOnSet(void)
0x18006a89b  test    eax, eax
0x18006a89d  jz      loc_18006AC1C
0x18006a8a3  lea     rdx, aSVoiceOnsetEna; "[%s] Voice onset enabled"
0x18006a8aa  mov     r8, r12
0x18006a8ad  mov     ecx, r15d; int
0x18006a8b0  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006a8b5  mov     al, [r14+3CCh]
0x18006a8bc  nop
0x18006a8bd  test    al, al
0x18006a8bf  jz      short loc_18006A8D8
0x18006a8c1  mov     r8, r12
0x18006a8c4  lea     rdx, aSAarCurrentSes; "[%s] AAR current session is active, ign"...
0x18006a8cb  mov     ecx, r15d; int
0x18006a8ce  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006a8d3  jmp     loc_18006AC6B
0x18006a8d8  mov     [rsp+170h+string], r13
0x18006a8dd  mov     [rsp+170h+var_128], r13
0x18006a8e2  mov     rdi, [r14+128h]
0x18006a8e9  mov     rax, [rdi]
0x18006a8ec  mov     rbx, [rax+70h]
0x18006a8f0  lea     rcx, [rsp+170h+var_128]
0x18006a8f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a8fa  lea     rdx, [rsp+170h+var_128]
0x18006a8ff  mov     rcx, rdi
0x18006a902  mov     rax, rbx
0x18006a905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a90a  mov     ebx, eax
0x18006a90c  test    eax, eax
0x18006a90e  jns     short loc_18006A949
0x18006a910  mov     rcx, [rbp+78h]; this
0x18006a914  mov     r9d, eax; char *
0x18006a917  lea     r8, aOnecoreuapEndu_136; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18006a91e  mov     edx, 23D8h; void *
0x18006a923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a928  nop
0x18006a929  lea     rcx, [rsp+170h+var_128]
0x18006a92e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a933  nop
0x18006a934  mov     rcx, [rsp+170h+string]; string
0x18006a939  call    cs:__imp_WindowsDeleteString
0x18006a93f  mov     [rsp+170h+string], r13
0x18006a944  jmp     loc_18006AC6E
0x18006a949  mov     rdi, [rsp+170h+var_128]
0x18006a94e  mov     rax, [rdi]
0x18006a951  mov     rbx, [rax+50h]
0x18006a955  mov     rcx, [rsp+170h+string]; string
0x18006a95a  call    cs:__imp_WindowsDeleteString
0x18006a960  mov     [rsp+170h+string], r13
0x18006a965  lea     rdx, [rsp+170h+string]
0x18006a96a  mov     rcx, rdi
0x18006a96d  mov     rax, rbx
0x18006a970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a975  mov     rcx, [rbp+78h]; this
0x18006a979  lea     rsi, aOnecoreuapEndu_136; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18006a980  test    eax, eax
0x18006a982  jns     short loc_18006A994
0x18006a984  mov     r9d, eax; char *
0x18006a987  mov     r8, rsi; unsigned int
0x18006a98a  mov     edx, 23DBh; void *
0x18006a98f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a994  xor     edx, edx; length
0x18006a996  mov     rcx, [rsp+170h+string]; string
0x18006a99b  call    cs:__imp_WindowsGetStringRawBuffer
0x18006a9a1  mov     r9, rax
0x18006a9a4  mov     r8, r12
0x18006a9a7  lea     rdx, aSAarDetectedSi; "[%s] AAR detected signal name %S"
0x18006a9ae  mov     ecx, r15d; int
0x18006a9b1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006a9b6  mov     eax, 1
0x18006a9bb  xchg    al, [r14+3CCh]
0x18006a9c2  mov     [rsp+170h+var_118], r13
0x18006a9c7  mov     [rsp+170h+var_120], r13
0x18006a9cc  lea     rcx, [rsp+170h+var_118]
0x18006a9d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a9d6  lea     rcx, [r14+258h]
0x18006a9dd  mov     [rsp+170h+var_148], r13
0x18006a9e2  mov     qword ptr [rsp+170h+var_150], r13; int
0x18006a9e7  xor     r9d, r9d
0x18006a9ea  lea     r8, [rsp+170h+var_118]
0x18006a9ef  lea     edx, [r9+3]
0x18006a9f3  call    ?GetInputFamily@CAudioOrchestratorInput@@QEAAJW4SPSTREAMSOURCE@@PEAPEAUISpStreamFormat@@PEAPEAUISpAudio@@PEAPEAUISpAudioStream@@PEAPEAUISpInputDeviceSupport@@@Z; CAudioOrchestratorInput::GetInputFamily(SPSTREAMSOURCE,ISpStreamFormat * *,ISpAudio * *,ISpAudioStream * *,ISpInputDeviceSupport * *)
0x18006a9f8  mov     rbx, [rsp+170h+var_118]
0x18006a9fd  test    rbx, rbx
0x18006aa00  jnz     short loc_18006AA36
0x18006aa02  mov     ebx, 80070057h
0x18006aa07  mov     r9d, ebx; char *
0x18006aa0a  mov     edx, 23E3h; void *
0x18006aa0f  mov     rcx, [rbp+78h]; this
0x18006aa13  mov     r8, rsi; unsigned int
0x18006aa16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006aa1b  nop
0x18006aa1c  lea     rcx, [rsp+170h+var_120]
0x18006aa21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006aa26  nop
0x18006aa27  lea     rcx, [rsp+170h+var_118]
0x18006aa2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006aa31  jmp     loc_18006A929
0x18006aa36  mov     rax, [rbx]
0x18006aa39  mov     rdi, [rax]
0x18006aa3c  lea     rcx, [rsp+170h+var_120]
0x18006aa41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006aa46  lea     r8, [rsp+170h+var_120]
0x18006aa4b  lea     rdx, _GUID_251ab6f7_5ffa_42d8_a2e9_5b05f617a03b
0x18006aa52  mov     rcx, rbx
0x18006aa55  mov     rax, rdi
0x18006aa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa5d  mov     ebx, eax
0x18006aa5f  test    eax, eax
0x18006aa61  jns     short loc_18006AA6D
0x18006aa63  mov     r9d, eax
0x18006aa66  mov     edx, 23E4h
0x18006aa6b  jmp     short loc_18006AA0F
0x18006aa6d  mov     [rsp+170h+var_110], r13
0x18006aa72  mov     [rsp+170h+var_108], r13
0x18006aa77  mov     rcx, [rsp+170h+var_128]
0x18006aa7c  mov     rax, [rcx]
0x18006aa7f  lea     rdx, [rsp+170h+var_110]
0x18006aa84  mov     rax, [rax+70h]
0x18006aa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa8d  mov     ebx, eax
0x18006aa8f  test    eax, eax
0x18006aa91  jns     short loc_18006AAA0
0x18006aa93  mov     r9d, eax
0x18006aa96  mov     edx, 23E7h
0x18006aa9b  jmp     loc_18006AA0F
0x18006aaa0  mov     rcx, [rsp+170h+var_128]
0x18006aaa5  mov     rax, [rcx]
0x18006aaa8  lea     rdx, [rsp+170h+var_108]
0x18006aaad  mov     rax, [rax+80h]
0x18006aab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aab9  mov     ebx, eax
0x18006aabb  test    eax, eax
0x18006aabd  jns     short loc_18006AACC
0x18006aabf  mov     r9d, eax
0x18006aac2  mov     edx, 23E8h
0x18006aac7  jmp     loc_18006AA0F
0x18006aacc  xorps   xmm0, xmm0
0x18006aacf  xor     eax, eax
0x18006aad1  movups  [rbp+70h+var_F0], xmm0
0x18006aad5  mov     [rbp+70h+var_E0], rax
0x18006aad9  mov     rcx, [r14+128h]
0x18006aae0  mov     rax, [rcx]
0x18006aae3  lea     rdx, [rbp+70h+var_F0]
0x18006aae7  mov     rax, [rax+130h]
0x18006aaee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaf3  mov     ebx, eax
0x18006aaf5  test    eax, eax
0x18006aaf7  jns     short loc_18006AB06
0x18006aaf9  mov     r9d, eax
0x18006aafc  mov     edx, 23EBh
0x18006ab01  jmp     loc_18006AA0F
0x18006ab06  cmp     byte ptr [rbp+70h+var_E0], r13b
0x18006ab0a  jnz     short loc_18006AB42
0x18006ab0c  lea     rcx, [rsp+170h+var_120]
0x18006ab11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ab16  nop
0x18006ab17  lea     rcx, [rsp+170h+var_118]
0x18006ab1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ab21  nop
0x18006ab22  lea     rcx, [rsp+170h+var_128]
0x18006ab27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ab2c  nop
0x18006ab2d  mov     rcx, [rsp+170h+string]; string
0x18006ab32  call    cs:__imp_WindowsDeleteString
0x18006ab38  mov     [rsp+170h+string], r13
0x18006ab3d  jmp     loc_18006AC6B
0x18006ab42  mov     rcx, [rsp+170h+var_120]
0x18006ab47  mov     rax, [rcx]
0x18006ab4a  mov     r8, qword ptr [rbp+70h+var_F0+8]
0x18006ab4e  mov     edx, dword ptr [rbp+70h+var_F0]
0x18006ab51  mov     rax, [rax+38h]
0x18006ab55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab5a  mov     ebx, eax
0x18006ab5c  test    eax, eax
0x18006ab5e  jns     short loc_18006AB6D
0x18006ab60  mov     r9d, eax
0x18006ab63  mov     edx, 23EDh
0x18006ab68  jmp     loc_18006AA0F
0x18006ab6d  mov     rax, qword ptr [rbp+70h+var_F0+8]
0x18006ab71  mov     [rsp+170h+var_148], rax
0x18006ab76  mov     rax, [rsp+170h+var_108]
0x18006ab7b  mov     qword ptr [rsp+170h+var_150], rax
0x18006ab80  mov     r9, [rsp+170h+var_110]
0x18006ab85  mov     r8, r12
0x18006ab88  lea     rdx, aSAarDetectedSi_0; "[%s] AAR detected signal start time %ll"...
0x18006ab8f  mov     ecx, r15d; int
0x18006ab92  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006ab97  mov     ebx, 78h ; 'x'
0x18006ab9c  mov     r8d, ebx; Size
0x18006ab9f  xor     edx, edx; Val
0x18006aba1  lea     rcx, [rbp+70h+var_D0]; void *
0x18006aba5  call    memset_0
0x18006abaa  mov     [rbp+70h+var_C8], 1
0x18006abb1  mov     rax, [rsp+170h+var_110]
0x18006abb6  mov     [rbp+70h+var_B0], rax
0x18006abba  mov     rax, [rsp+170h+var_108]
0x18006abbf  mov     [rbp+70h+var_A8], rax
0x18006abc3  cmp     [r14+3B0h], r13d
0x18006abca  jz      short loc_18006ABDA
0x18006abcc  call    ?GetPolicy_VoiceOnSet@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_VoiceOnSet(void)
0x18006abd1  test    eax, eax
0x18006abd3  mov     edx, 1F5h
0x18006abd8  jnz     short loc_18006ABDF
0x18006abda  mov     edx, 0D5h
0x18006abdf  lea     rcx, [r14+20h]
0x18006abe3  mov     rax, [rcx]
0x18006abe6  mov     dword ptr [rsp+170h+var_148], ebx
0x18006abea  lea     r8, [rbp+70h+var_D0]
0x18006abee  mov     qword ptr [rsp+170h+var_150], r8
0x18006abf3  mov     r9d, 2
0x18006abf9  xor     r8d, r8d
0x18006abfc  mov     rax, [rax+20h]
0x18006ac00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac05  mov     ebx, eax
0x18006ac07  test    eax, eax
0x18006ac09  jns     loc_18006AB0C
0x18006ac0f  mov     r9d, eax
0x18006ac12  mov     edx, 23FCh
0x18006ac17  jmp     loc_18006AA0F
0x18006ac1c  mov     r8, r12
0x18006ac1f  lea     rdx, aSVoiceOnsetNot; "[%s] Voice onset NOT enabled"
0x18006ac26  mov     ecx, r15d; int
0x18006ac29  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006ac2e  mov     r8, r12
0x18006ac31  lea     rdx, aSIgnoringEvent; "[%s] Ignoring event"
0x18006ac38  mov     ecx, r15d; int
0x18006ac3b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18006ac40  mov     rcx, [r14+0F0h]
0x18006ac47  mov     rax, [rcx]
0x18006ac4a  mov     rax, [rax+50h]
0x18006ac4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac53  mov     rcx, rax; hWnd
0x18006ac56  mov     edx, 8000h; Msg
0x18006ac5b  mov     r9d, 6; lParam
0x18006ac61  lea     r8d, [r9-5]; wParam
0x18006ac65  call    cs:__imp_PostMessageW
0x18006ac6b  mov     ebx, r13d
0x18006ac6e  lea     rcx, [rsp+170h+var_100]; this
0x18006ac73  call    ??1CSPAutoCritSecLock@@QEAA@XZ; CSPAutoCritSecLock::~CSPAutoCritSecLock(void)
0x18006ac78  mov     eax, ebx
0x18006ac7a  mov     rcx, [rbp+70h+var_50]
0x18006ac7e  xor     rcx, rsp; StackCookie
0x18006ac81  call    __security_check_cookie
0x18006ac86  add     rsp, 138h
0x18006ac8d  pop     r15
0x18006ac8f  pop     r14
0x18006ac91  pop     r13
0x18006ac93  pop     r12
0x18006ac95  pop     rdi
0x18006ac96  pop     rsi
0x18006ac97  pop     rbx
0x18006ac98  pop     rbp
0x18006ac99  retn
```
