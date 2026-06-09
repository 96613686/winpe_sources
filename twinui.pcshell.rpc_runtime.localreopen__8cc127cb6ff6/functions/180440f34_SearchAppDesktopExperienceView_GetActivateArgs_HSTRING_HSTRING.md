# SearchAppDesktopExperienceView::GetActivateArgs(HSTRING__ *,HSTRING__ * *)

- ea: `0x180440f34`
- end: `0x18044117b`
- name: `?GetActivateArgs@SearchAppDesktopExperienceView@@AEAAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `583`
- prototype: `__int64 __fastcall(SearchAppDesktopExperienceView *__hidden this, HSTRING string1, HSTRING *newString)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180347970`
- `0x180443690`
- `0x180443aa0`

## callees

- `0x1800237c8`
- `0x1802b7b34`
- `0x1802b7cbc`
- `0x180356360`
- `0x18043ff90`
- `0x180440f34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804410c8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180441100`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180441115`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1804410c8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180441100`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180441115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18044108e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18044108e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180440fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044103b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044107c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180441144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180441158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180440fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044103b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18044107c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180441144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180441158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180441054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180441054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804410b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804410b0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x180440fa6`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromRect` at `0x180440fa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SearchAppDesktopExperienceView::GetActivateArgs(
        SearchAppDesktopExperienceView *this,
        HSTRING string1,
        HSTRING *newString)
{
  float v6; // xmm0_4
  float v7; // xmm1_4
  HMONITOR v8; // rax
  HMONITOR v9; // rsi
  unsigned int v10; // ebx
  int SearchBoxHeight; // r14d
  int v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rdx
  const wchar_t *StringRawBuffer; // rax
  HMONITOR v16; // r8
  const wchar_t *v17; // rbx
  HMONITOR v18; // r8
  HSTRING newStringa; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string2; // [rsp+28h] [rbp-28h] BYREF
  UINT32 length; // [rsp+30h] [rbp-20h] BYREF
  RECT rc; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  *newString = 0;
  v6 = *((float *)this + 45);
  rc.left = (int)v6;
  v7 = *((float *)this + 46);
  rc.top = (int)v7;
  rc.right = (int)(float)(v6 + *((float *)this + 47));
  rc.bottom = (int)(float)(v7 + *((float *)this + 48));
  v8 = MonitorFromRect(&rc, 0);
  v9 = v8;
  if ( v8 )
  {
    SearchBoxHeight = SearchAppDesktopExperienceView::GetSearchBoxHeight(this, v8);
    WindowsDeleteString(0);
    string2 = 0;
    v12 = SearchAppDesktopExperienceView::BuildAdditionalArgsString(
            this,
            v9,
            (ExperienceManagerUtils *)(unsigned int)SearchBoxHeight,
            &string2);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C7,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappdesktopexperienceview.cpp",
        (const char *)(unsigned int)v12,
        (int)newStringa);
LABEL_17:
      WindowsDeleteString(string2);
      return v10;
    }
    WindowsDeleteString(0);
    newStringa = 0;
    v13 = WindowsConcatString(string1, string2, &newStringa);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v13 = WindowsDuplicateString(newStringa, newString);
      v10 = v13;
      if ( v13 >= 0 )
      {
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(newStringa, &length);
        v17 = StringRawBuffer;
        if ( StringRawBuffer )
          *((_BYTE *)this + 201) = wcsstr(StringRawBuffer, L"&QuerySource=StartButton") != 0;
        *((float *)this + 43) = (float)ExperienceManagerUtils::ScaleByPerMonitorDPI(
                                         (ExperienceManagerUtils *)0x140,
                                         (int)v9,
                                         v16);
        if ( !wcsstr(v17, L"StartMode=QFSearchBox") && !wcsstr(v17, L"StartMode=NotificationAnimation") )
          SearchBoxHeight = ExperienceManagerUtils::ScaleByPerMonitorDPI((ExperienceManagerUtils *)0x290, (int)v9, v18);
        *((float *)this + 44) = (float)SearchBoxHeight;
        WindowsDeleteString(newStringa);
        v10 = 0;
        goto LABEL_16;
      }
      v14 = 1227;
    }
    else
    {
      v14 = 1226;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappdesktopexperienceview.cpp",
      (const char *)(unsigned int)v13,
      (int)newStringa);
    WindowsDeleteString(newStringa);
LABEL_16:
    newStringa = 0;
    goto LABEL_17;
  }
  v10 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C3,
    (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappdesktopexperienceview.cpp",
    (const char *)0x8000FFFFLL,
    (int)newStringa);
  return v10;
}

```

## disassembly

```asm
0x180440f34  push    rbp
0x180440f36  push    rbx
0x180440f37  push    rsi
0x180440f38  push    rdi
0x180440f39  push    r12
0x180440f3b  push    r14
0x180440f3d  push    r15
0x180440f3f  mov     rbp, rsp
0x180440f42  sub     rsp, 50h
0x180440f46  mov     rax, cs:__security_cookie
0x180440f4d  xor     rax, rsp
0x180440f50  mov     [rbp+var_8], rax
0x180440f54  mov     r15, r8
0x180440f57  mov     r12, rdx
0x180440f5a  mov     rdi, rcx
0x180440f5d  mov     qword ptr [r8], 0
0x180440f64  movss   xmm0, dword ptr [rcx+0B4h]
0x180440f6c  cvttss2si eax, xmm0
0x180440f70  mov     [rbp+rc.left], eax
0x180440f73  movss   xmm1, dword ptr [rcx+0B8h]
0x180440f7b  cvttss2si eax, xmm1
0x180440f7f  mov     [rbp+rc.top], eax
0x180440f82  addss   xmm0, dword ptr [rcx+0BCh]
0x180440f8a  cvttss2si eax, xmm0
0x180440f8e  mov     [rbp+rc.right], eax
0x180440f91  addss   xmm1, dword ptr [rcx+0C0h]
0x180440f99  cvttss2si eax, xmm1
0x180440f9d  mov     [rbp+rc.bottom], eax
0x180440fa0  xor     edx, edx; dwFlags
0x180440fa2  lea     rcx, [rbp+rc]; lprc
0x180440fa6  call    cs:__imp_MonitorFromRect
0x180440fac  mov     rsi, rax
0x180440faf  test    rax, rax
0x180440fb2  jnz     short loc_180440FD6
0x180440fb4  mov     rcx, [rbp+38h]; this
0x180440fb8  mov     ebx, 8000FFFFh
0x180440fbd  mov     r9d, ebx; char *
0x180440fc0  lea     r8, aPcshellTwinuiE_28; "pcshell\\twinui\\experiencemanagers\\li"...
0x180440fc7  mov     edx, 4C3h; void *
0x180440fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180440fd1  jmp     loc_18044115E
0x180440fd6  mov     rdx, rsi; HMONITOR
0x180440fd9  mov     rcx, rdi; this
0x180440fdc  call    ?GetSearchBoxHeight@SearchAppDesktopExperienceView@@AEAAHPEAUHMONITOR__@@@Z; SearchAppDesktopExperienceView::GetSearchBoxHeight(HMONITOR__ *)
0x180440fe1  mov     r14d, eax
0x180440fe4  mov     [rbp+string2], 0
0x180440fec  xor     ecx, ecx; string
0x180440fee  call    cs:__imp_WindowsDeleteString
0x180440ff4  mov     [rbp+string2], 0
0x180440ffc  lea     r9, [rbp+string2]; newString
0x180441000  mov     r8d, r14d; ExperienceManagerUtils *
0x180441003  mov     rdx, rsi; HMONITOR
0x180441006  mov     rcx, rdi; this
0x180441009  call    ?BuildAdditionalArgsString@SearchAppDesktopExperienceView@@AEAAJPEAUHMONITOR__@@HPEAPEAUHSTRING__@@@Z; SearchAppDesktopExperienceView::BuildAdditionalArgsString(HMONITOR__ *,int,HSTRING__ * *)
0x18044100e  mov     ebx, eax
0x180441010  test    eax, eax
0x180441012  jns     short loc_180441031
0x180441014  mov     rcx, [rbp+38h]; this
0x180441018  mov     r9d, eax; char *
0x18044101b  lea     r8, aPcshellTwinuiE_28; "pcshell\\twinui\\experiencemanagers\\li"...
0x180441022  mov     edx, 4C7h; void *
0x180441027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18044102c  jmp     loc_180441154
0x180441031  mov     [rbp+newString], 0
0x180441039  xor     ecx, ecx; string
0x18044103b  call    cs:__imp_WindowsDeleteString
0x180441041  mov     [rbp+newString], 0
0x180441049  lea     r8, [rbp+newString]; newString
0x18044104d  mov     rdx, [rbp+string2]; string2
0x180441051  mov     rcx, r12; string1
0x180441054  call    cs:__imp_WindowsConcatString
0x18044105a  mov     ebx, eax
0x18044105c  test    eax, eax
0x18044105e  jns     short loc_180441087
0x180441060  mov     edx, 4CAh; void *
0x180441065  lea     r8, aPcshellTwinuiE_28; "pcshell\\twinui\\experiencemanagers\\li"...
0x18044106c  mov     r9d, eax; char *
0x18044106f  mov     rcx, [rbp+38h]; this
0x180441073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180441078  mov     rcx, [rbp+newString]; string
0x18044107c  call    cs:__imp_WindowsDeleteString
0x180441082  jmp     loc_18044114C
0x180441087  mov     rdx, r15; newString
0x18044108a  mov     rcx, [rbp+newString]; string
0x18044108e  call    cs:__imp_WindowsDuplicateString
0x180441094  mov     ebx, eax
0x180441096  test    eax, eax
0x180441098  jns     short loc_1804410A1
0x18044109a  mov     edx, 4CBh
0x18044109f  jmp     short loc_180441065
0x1804410a1  mov     [rbp+length], 0
0x1804410a8  lea     rdx, [rbp+length]; length
0x1804410ac  mov     rcx, [rbp+newString]; string
0x1804410b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1804410b6  mov     rbx, rax
0x1804410b9  test    rax, rax
0x1804410bc  jz      short loc_1804410DA
0x1804410be  lea     rdx, aQuerysourceSta; "&QuerySource=StartButton"
0x1804410c5  mov     rcx, rax; Str
0x1804410c8  call    cs:__imp_wcsstr
0x1804410ce  test    rax, rax
0x1804410d1  setnz   cl
0x1804410d4  mov     [rdi+0C9h], cl
0x1804410da  mov     rdx, rsi; int
0x1804410dd  mov     ecx, 140h; this
0x1804410e2  call    ?ScaleByPerMonitorDPI@ExperienceManagerUtils@@YAHHPEAUHMONITOR__@@@Z; ExperienceManagerUtils::ScaleByPerMonitorDPI(int,HMONITOR__ *)
0x1804410e7  movd    xmm0, eax
0x1804410eb  cvtdq2ps xmm0, xmm0
0x1804410ee  movss   dword ptr [rdi+0ACh], xmm0
0x1804410f6  lea     rdx, aStartmodeQfsea; "StartMode=QFSearchBox"
0x1804410fd  mov     rcx, rbx; Str
0x180441100  call    cs:__imp_wcsstr
0x180441106  test    rax, rax
0x180441109  jnz     short loc_180441130
0x18044110b  lea     rdx, aStartmodeNotif; "StartMode=NotificationAnimation"
0x180441112  mov     rcx, rbx; Str
0x180441115  call    cs:__imp_wcsstr
0x18044111b  test    rax, rax
0x18044111e  jnz     short loc_180441130
0x180441120  mov     rdx, rsi; int
0x180441123  mov     ecx, 290h; this
0x180441128  call    ?ScaleByPerMonitorDPI@ExperienceManagerUtils@@YAHHPEAUHMONITOR__@@@Z; ExperienceManagerUtils::ScaleByPerMonitorDPI(int,HMONITOR__ *)
0x18044112d  mov     r14d, eax
0x180441130  movd    xmm0, r14d
0x180441135  cvtdq2ps xmm0, xmm0
0x180441138  movss   dword ptr [rdi+0B0h], xmm0
0x180441140  mov     rcx, [rbp+newString]; string
0x180441144  call    cs:__imp_WindowsDeleteString
0x18044114a  xor     ebx, ebx
0x18044114c  mov     [rbp+newString], 0
0x180441154  mov     rcx, [rbp+string2]; string
0x180441158  call    cs:__imp_WindowsDeleteString
0x18044115e  mov     eax, ebx
0x180441160  mov     rcx, [rbp+var_8]
0x180441164  xor     rcx, rsp; StackCookie
0x180441167  call    __security_check_cookie
0x18044116c  add     rsp, 50h
0x180441170  pop     r15
0x180441172  pop     r14
0x180441174  pop     r12
0x180441176  pop     rdi
0x180441177  pop     rsi
0x180441178  pop     rbx
0x180441179  pop     rbp
0x18044117a  retn
```
