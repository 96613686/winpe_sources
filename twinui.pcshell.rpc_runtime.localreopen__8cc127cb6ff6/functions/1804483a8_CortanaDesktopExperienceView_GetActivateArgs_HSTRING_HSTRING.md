# CortanaDesktopExperienceView::GetActivateArgs(HSTRING__ *,HSTRING__ * *)

- ea: `0x1804483a8`
- end: `0x18044873e`
- name: `?GetActivateArgs@CortanaDesktopExperienceView@@AEAAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `918`
- prototype: `__int64 __fastcall(CortanaDesktopExperienceView *__hidden this, HSTRING string1, HSTRING *newString)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1803490e0`
- `0x18044ae80`
- `0x18044b2c0`

## callees

- `0x1800237c8`
- `0x1802b79ac`
- `0x1802b7cbc`
- `0x180322bc8`
- `0x180356360`
- `0x180408a98`
- `0x1804483a8`
- `0x180448890`
- `0x180449324`
- `0x18044adbc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044853c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448558`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044856b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044857e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448591`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804485a6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448605`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804486bd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804486d2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044853c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448558`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044856b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18044857e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448591`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804485a6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180448605`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804486bd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804486d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180448501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180448501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044846c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804484b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804484ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044846c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804484b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804484ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180448712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1804484c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1804484c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180448520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180448520`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x180448426`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x180448426`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CortanaDesktopExperienceView::GetActivateArgs(
        CortanaDesktopExperienceView *this,
        HSTRING string1,
        HSTRING *newString)
{
  float v6; // xmm0_4
  float v7; // xmm1_4
  HMONITOR v8; // rax
  HMONITOR v9; // r14
  int SpeechTextInputHeight; // r15d
  int v12; // eax
  unsigned int v13; // edi
  HRESULT v14; // eax
  __int64 v15; // rdx
  const wchar_t *StringRawBuffer; // rax
  CortanaFlightingHelpers *v17; // rcx
  const wchar_t *v18; // rdi
  wchar_t *v19; // rsi
  wchar_t *v20; // r12
  wchar_t *v21; // r13
  wchar_t *v22; // rax
  int v23; // eax
  int v24; // esi
  HMONITOR v25; // r8
  HMONITOR v26; // r8
  __int64 v27; // rcx
  HMONITOR v28; // r8
  HSTRING newStringa; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string2; // [rsp+28h] [rbp-28h] BYREF
  UINT32 length; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v32[4]; // [rsp+34h] [rbp-1Ch] BYREF
  RECT rc; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  *newString = 0;
  *(_WORD *)((char *)this + 237) = 0;
  v6 = *((float *)this + 49);
  rc.left = (int)v6;
  v7 = *((float *)this + 50);
  rc.top = (int)v7;
  rc.right = (int)(float)(v6 + *((float *)this + 51));
  rc.bottom = (int)(float)(v7 + *((float *)this + 52));
  v8 = MonitorFromRect(&rc, 0);
  v9 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67B,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanadesktopexperienceview.cpp",
      (const char *)0x8000FFFFLL,
      (int)newStringa);
    return 2147549183LL;
  }
  SpeechTextInputHeight = CortanaDesktopExperienceView::GetSpeechTextInputHeight(this, v8);
  WindowsDeleteString(0);
  string2 = 0;
  v12 = CortanaDesktopExperienceView::BuildAdditionalArgsString(
          this,
          v9,
          (ExperienceManagerUtils *)(unsigned int)SpeechTextInputHeight,
          &string2);
  v13 = v12;
  if ( v12 >= 0 )
  {
    WindowsDeleteString(0);
    newStringa = 0;
    v14 = WindowsConcatString(string1, string2, &newStringa);
    v13 = v14;
    if ( v14 < 0 )
    {
      v15 = 1666;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanadesktopexperienceview.cpp",
        (const char *)(unsigned int)v14,
        (int)newStringa);
      WindowsDeleteString(newStringa);
LABEL_35:
      newStringa = 0;
      goto LABEL_36;
    }
    v14 = WindowsDuplicateString(newStringa, newString);
    v13 = v14;
    if ( v14 < 0 )
    {
      v15 = 1667;
      goto LABEL_7;
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(newStringa, &length);
    v18 = StringRawBuffer;
    if ( StringRawBuffer )
    {
      if ( wcsstr(StringRawBuffer, L"ForceAmbientMode=True") )
        *((_BYTE *)this + 237) = 1;
      v19 = wcsstr(v18, L"StartMode=NotificationAnimation");
      v20 = wcsstr(v18, L"StartMode=Attract");
      v21 = wcsstr(v18, L"QuerySource=LockScreen");
      if ( (wcsstr(v18, L"QuerySource=VoiceActivation")
         || (v22 = wcsstr(v18, L"QuerySource=VoiceActivationWithKeyword")) != 0)
        && (LOBYTE(v22) = 1, *((_BYTE *)this + 247))
        || *((_BYTE *)this + 237)
        || v19
        || v20
        || v21 )
      {
        *((_BYTE *)this + 238) = 1;
      }
      if ( (_BYTE)v22 && !*((_BYTE *)this + 238) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 24LL))(*((_QWORD *)this + 12));
      *((_BYTE *)this + 244) = wcsstr(v18, L"&QuerySource=StartButton") != 0;
      if ( v19 )
      {
        v23 = CortanaDesktopExperienceView::SetPositioningAnchorForNotificationAnimation(this);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6AD,
            (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanadesktopexperienceview.cpp",
            (const char *)(unsigned int)v23,
            (int)newStringa);
          WindowsDeleteString(newStringa);
          v13 = v24;
          goto LABEL_35;
        }
      }
    }
    if ( CortanaFlightingHelpers::IsImmersiveSearchEnabled(v17) && *((_DWORD *)this + 35) == 6 )
    {
      CortanaFeatureConfiguration::GetDWORD(0, v32);
      *((float *)this + 53) = (float)ExperienceManagerUtils::ScaleByPerMonitorDPI(
                                       (ExperienceManagerUtils *)0x384,
                                       (int)v9,
                                       v26);
      v27 = (unsigned int)GetCortanaHeightForImmersiveSearch() + 20;
    }
    else
    {
      *((float *)this + 53) = (float)ExperienceManagerUtils::ScaleByPerMonitorDPI(
                                       (ExperienceManagerUtils *)0x140,
                                       (int)v9,
                                       v25);
      if ( wcsstr(v18, L"StartMode=QFSearchBox") || wcsstr(v18, L"StartMode=NotificationAnimation") )
        goto LABEL_34;
      v27 = 656;
    }
    SpeechTextInputHeight = ExperienceManagerUtils::ScaleByPerMonitorDPI((ExperienceManagerUtils *)v27, (int)v9, v28);
LABEL_34:
    *((float *)this + 54) = (float)SpeechTextInputHeight;
    WindowsDeleteString(newStringa);
    v13 = 0;
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x67F,
    (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanadesktopexperienceview.cpp",
    (const char *)(unsigned int)v12,
    (int)newStringa);
LABEL_36:
  WindowsDeleteString(string2);
  return v13;
}

```

## disassembly

```asm
0x1804483a8  mov     [rsp-38h+arg_18], rbx
0x1804483ad  push    rbp
0x1804483ae  push    rsi
0x1804483af  push    rdi
0x1804483b0  push    r12
0x1804483b2  push    r13
0x1804483b4  push    r14
0x1804483b6  push    r15
0x1804483b8  mov     rbp, rsp
0x1804483bb  sub     rsp, 50h
0x1804483bf  mov     rax, cs:__security_cookie
0x1804483c6  xor     rax, rsp
0x1804483c9  mov     [rbp+var_8], rax
0x1804483cd  mov     rsi, r8
0x1804483d0  mov     r12, rdx
0x1804483d3  mov     rbx, rcx
0x1804483d6  xor     r13d, r13d
0x1804483d9  mov     [r8], r13
0x1804483dc  mov     [rcx+0EDh], r13w
0x1804483e4  movss   xmm0, dword ptr [rcx+0C4h]
0x1804483ec  cvttss2si eax, xmm0
0x1804483f0  mov     [rbp+rc.left], eax
0x1804483f3  movss   xmm1, dword ptr [rcx+0C8h]
0x1804483fb  cvttss2si eax, xmm1
0x1804483ff  mov     [rbp+rc.top], eax
0x180448402  addss   xmm0, dword ptr [rcx+0CCh]
0x18044840a  cvttss2si eax, xmm0
0x18044840e  mov     [rbp+rc.right], eax
0x180448411  addss   xmm1, dword ptr [rcx+0D0h]
0x180448419  cvttss2si eax, xmm1
0x18044841d  mov     [rbp+rc.bottom], eax
0x180448420  xor     edx, edx; dwFlags
0x180448422  lea     rcx, [rbp+rc]; lprc
0x180448426  call    cs:__imp_MonitorFromRect
0x18044842c  mov     r14, rax
0x18044842f  test    rax, rax
0x180448432  jnz     short loc_180448458
0x180448434  mov     rcx, [rbp+38h]; this
0x180448438  mov     ebx, 8000FFFFh
0x18044843d  mov     r9d, ebx; char *
0x180448440  lea     r8, aPcshellTwinuiE_13; "pcshell\\twinui\\experiencemanagers\\li"...
0x180448447  mov     edx, 67Bh; void *
0x18044844c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180448451  mov     eax, ebx
0x180448453  jmp     loc_18044871A
0x180448458  mov     rdx, r14; HMONITOR
0x18044845b  mov     rcx, rbx; this
0x18044845e  call    ?GetSpeechTextInputHeight@CortanaDesktopExperienceView@@AEAAHPEAUHMONITOR__@@@Z; CortanaDesktopExperienceView::GetSpeechTextInputHeight(HMONITOR__ *)
0x180448463  mov     r15d, eax
0x180448466  mov     [rbp+string2], r13
0x18044846a  xor     ecx, ecx; string
0x18044846c  call    cs:__imp_WindowsDeleteString
0x180448472  mov     [rbp+string2], r13
0x180448476  lea     r9, [rbp+string2]; newString
0x18044847a  mov     r8d, r15d; ExperienceManagerUtils *
0x18044847d  mov     rdx, r14; HMONITOR
0x180448480  mov     rcx, rbx; this
0x180448483  call    ?BuildAdditionalArgsString@CortanaDesktopExperienceView@@AEAAJPEAUHMONITOR__@@HPEAPEAUHSTRING__@@@Z; CortanaDesktopExperienceView::BuildAdditionalArgsString(HMONITOR__ *,int,HSTRING__ * *)
0x180448488  mov     edi, eax
0x18044848a  test    eax, eax
0x18044848c  jns     short loc_1804484AB
0x18044848e  mov     rcx, [rbp+38h]; this
0x180448492  mov     r9d, eax; char *
0x180448495  lea     r8, aPcshellTwinuiE_13; "pcshell\\twinui\\experiencemanagers\\li"...
0x18044849c  mov     edx, 67Fh; void *
0x1804484a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804484a6  jmp     loc_18044870E
0x1804484ab  mov     [rbp+newString], r13
0x1804484af  xor     ecx, ecx; string
0x1804484b1  call    cs:__imp_WindowsDeleteString
0x1804484b7  mov     [rbp+newString], r13
0x1804484bb  lea     r8, [rbp+newString]; newString
0x1804484bf  mov     rdx, [rbp+string2]; string2
0x1804484c3  mov     rcx, r12; string1
0x1804484c6  call    cs:__imp_WindowsConcatString
0x1804484cc  mov     edi, eax
0x1804484ce  test    eax, eax
0x1804484d0  jns     short loc_1804484FA
0x1804484d2  mov     edx, 682h; void *
0x1804484d7  lea     r8, aPcshellTwinuiE_13; "pcshell\\twinui\\experiencemanagers\\li"...
0x1804484de  mov     r9d, eax; char *
0x1804484e1  mov     rcx, [rbp+38h]; this
0x1804484e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804484ea  nop
0x1804484eb  mov     rcx, [rbp+newString]; string
0x1804484ef  call    cs:__imp_WindowsDeleteString
0x1804484f5  jmp     loc_18044870A
0x1804484fa  mov     rdx, rsi; newString
0x1804484fd  mov     rcx, [rbp+newString]; string
0x180448501  call    cs:__imp_WindowsDuplicateString
0x180448507  mov     edi, eax
0x180448509  test    eax, eax
0x18044850b  jns     short loc_180448514
0x18044850d  mov     edx, 683h
0x180448512  jmp     short loc_1804484D7
0x180448514  mov     [rbp+length], r13d
0x180448518  lea     rdx, [rbp+length]; length
0x18044851c  mov     rcx, [rbp+newString]; string
0x180448520  call    cs:__imp_WindowsGetStringRawBuffer
0x180448526  mov     rdi, rax
0x180448529  test    rax, rax
0x18044852c  jz      loc_180448654
0x180448532  lea     rdx, aForceambientmo; "ForceAmbientMode=True"
0x180448539  mov     rcx, rax; Str
0x18044853c  call    cs:__imp_wcsstr
0x180448542  test    rax, rax
0x180448545  jz      short loc_18044854E
0x180448547  mov     byte ptr [rbx+0EDh], 1
0x18044854e  lea     rdx, aStartmodeNotif; "StartMode=NotificationAnimation"
0x180448555  mov     rcx, rdi; Str
0x180448558  call    cs:__imp_wcsstr
0x18044855e  mov     rsi, rax
0x180448561  lea     rdx, aStartmodeAttra; "StartMode=Attract"
0x180448568  mov     rcx, rdi; Str
0x18044856b  call    cs:__imp_wcsstr
0x180448571  mov     r12, rax
0x180448574  lea     rdx, aQuerysourceLoc; "QuerySource=LockScreen"
0x18044857b  mov     rcx, rdi; Str
0x18044857e  call    cs:__imp_wcsstr
0x180448584  mov     r13, rax
0x180448587  lea     rdx, aQuerysourceVoi_0; "QuerySource=VoiceActivation"
0x18044858e  mov     rcx, rdi; Str
0x180448591  call    cs:__imp_wcsstr
0x180448597  test    rax, rax
0x18044859a  jnz     short loc_1804485B1
0x18044859c  lea     rdx, aQuerysourceVoi; "QuerySource=VoiceActivationWithKeyword"
0x1804485a3  mov     rcx, rdi; Str
0x1804485a6  call    cs:__imp_wcsstr
0x1804485ac  test    rax, rax
0x1804485af  jz      short loc_1804485BC
0x1804485b1  mov     al, 1
0x1804485b3  cmp     byte ptr [rbx+0F7h], 0
0x1804485ba  jnz     short loc_1804485D4
0x1804485bc  cmp     byte ptr [rbx+0EDh], 0
0x1804485c3  jnz     short loc_1804485D4
0x1804485c5  test    rsi, rsi
0x1804485c8  jnz     short loc_1804485D4
0x1804485ca  test    r12, r12
0x1804485cd  jnz     short loc_1804485D4
0x1804485cf  test    r13, r13
0x1804485d2  jz      short loc_1804485DB
0x1804485d4  mov     byte ptr [rbx+0EEh], 1
0x1804485db  xor     r13d, r13d
0x1804485de  test    al, al
0x1804485e0  jz      short loc_1804485FB
0x1804485e2  cmp     [rbx+0EEh], r13b
0x1804485e9  jnz     short loc_1804485FB
0x1804485eb  mov     rcx, [rbx+60h]
0x1804485ef  mov     rax, [rcx]
0x1804485f2  mov     rax, [rax+18h]
0x1804485f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804485fb  lea     rdx, aQuerysourceSta; "&QuerySource=StartButton"
0x180448602  mov     rcx, rdi; Str
0x180448605  call    cs:__imp_wcsstr
0x18044860b  test    rax, rax
0x18044860e  setnz   al
0x180448611  mov     [rbx+0F4h], al
0x180448617  test    rsi, rsi
0x18044861a  jz      short loc_180448654
0x18044861c  mov     rcx, rbx; this
0x18044861f  call    ?SetPositioningAnchorForNotificationAnimation@CortanaDesktopExperienceView@@AEAAJXZ; CortanaDesktopExperienceView::SetPositioningAnchorForNotificationAnimation(void)
0x180448624  mov     esi, eax
0x180448626  test    eax, eax
0x180448628  jns     short loc_180448654
0x18044862a  mov     rcx, [rbp+38h]; this
0x18044862e  mov     r9d, eax; char *
0x180448631  lea     r8, aPcshellTwinuiE_13; "pcshell\\twinui\\experiencemanagers\\li"...
0x180448638  mov     edx, 6ADh; void *
0x18044863d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180448642  nop
0x180448643  mov     rcx, [rbp+newString]; string
0x180448647  call    cs:__imp_WindowsDeleteString
0x18044864d  mov     edi, esi
0x18044864f  jmp     loc_18044870A
0x180448654  call    ?IsImmersiveSearchEnabled@CortanaFlightingHelpers@@YAEXZ; CortanaFlightingHelpers::IsImmersiveSearchEnabled(void)
0x180448659  test    al, al
0x18044865b  jz      short loc_180448697
0x18044865d  cmp     dword ptr [rbx+8Ch], 6
0x180448664  jnz     short loc_180448697
0x180448666  lea     rdx, [rbp+var_1C]
0x18044866a  xor     ecx, ecx
0x18044866c  call    ?GetDWORD@CortanaFeatureConfiguration@@YAJW4FeatureId@1@PEAK@Z; CortanaFeatureConfiguration::GetDWORD(CortanaFeatureConfiguration::FeatureId,ulong *)
0x180448671  mov     rdx, r14; int
0x180448674  mov     ecx, 384h; this
0x180448679  call    ?ScaleByPerMonitorDPI@ExperienceManagerUtils@@YAHHPEAUHMONITOR__@@@Z; ExperienceManagerUtils::ScaleByPerMonitorDPI(int,HMONITOR__ *)
0x18044867e  movd    xmm0, eax
0x180448682  cvtdq2ps xmm0, xmm0
0x180448685  movss   dword ptr [rbx+0D4h], xmm0
0x18044868d  call    ?GetCortanaHeightForImmersiveSearch@@YAHXZ; GetCortanaHeightForImmersiveSearch(void)
0x180448692  lea     ecx, [rax+14h]
0x180448695  jmp     short loc_1804486E2
0x180448697  mov     rdx, r14; int
0x18044869a  mov     ecx, 140h; this
0x18044869f  call    ?ScaleByPerMonitorDPI@ExperienceManagerUtils@@YAHHPEAUHMONITOR__@@@Z; ExperienceManagerUtils::ScaleByPerMonitorDPI(int,HMONITOR__ *)
0x1804486a4  movd    xmm0, eax
0x1804486a8  cvtdq2ps xmm0, xmm0
0x1804486ab  movss   dword ptr [rbx+0D4h], xmm0
0x1804486b3  lea     rdx, aStartmodeQfsea; "StartMode=QFSearchBox"
0x1804486ba  mov     rcx, rdi; Str
0x1804486bd  call    cs:__imp_wcsstr
0x1804486c3  test    rax, rax
0x1804486c6  jnz     short loc_1804486ED
0x1804486c8  lea     rdx, aStartmodeNotif; "StartMode=NotificationAnimation"
0x1804486cf  mov     rcx, rdi; Str
0x1804486d2  call    cs:__imp_wcsstr
0x1804486d8  test    rax, rax
0x1804486db  jnz     short loc_1804486ED
0x1804486dd  mov     ecx, 290h; this
0x1804486e2  mov     rdx, r14; int
0x1804486e5  call    ?ScaleByPerMonitorDPI@ExperienceManagerUtils@@YAHHPEAUHMONITOR__@@@Z; ExperienceManagerUtils::ScaleByPerMonitorDPI(int,HMONITOR__ *)
0x1804486ea  mov     r15d, eax
0x1804486ed  movd    xmm0, r15d
0x1804486f2  cvtdq2ps xmm0, xmm0
0x1804486f5  movss   dword ptr [rbx+0D8h], xmm0
0x1804486fd  mov     rcx, [rbp+newString]; string
0x180448701  call    cs:__imp_WindowsDeleteString
0x180448707  mov     edi, r13d
0x18044870a  mov     [rbp+newString], r13
0x18044870e  mov     rcx, [rbp+string2]; string
0x180448712  call    cs:__imp_WindowsDeleteString
0x180448718  mov     eax, edi
0x18044871a  mov     rcx, [rbp+var_8]
0x18044871e  xor     rcx, rsp; StackCookie
0x180448721  call    __security_check_cookie
0x180448726  mov     rbx, [rsp+50h+arg_18]
0x18044872e  add     rsp, 50h
0x180448732  pop     r15
0x180448734  pop     r14
0x180448736  pop     r13
0x180448738  pop     r12
0x18044873a  pop     rdi
0x18044873b  pop     rsi
0x18044873c  pop     rbp
0x18044873d  retn
```
