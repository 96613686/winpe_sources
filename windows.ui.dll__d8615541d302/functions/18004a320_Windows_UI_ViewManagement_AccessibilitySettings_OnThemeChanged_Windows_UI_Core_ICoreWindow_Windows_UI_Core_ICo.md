# Windows::UI::ViewManagement::AccessibilitySettings::OnThemeChanged(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::ICoreWindowEventArgs *)

- ea: `0x18004a320`
- end: `0x18004a40a`
- name: `?OnThemeChanged@AccessibilitySettings@ViewManagement@UI@Windows@@AEAAJPEAUICoreWindow@Core@34@PEAUICoreWindowEventArgs@634@@Z`
- size: `234`
- prototype: `__int64 __fastcall(Windows::UI::ViewManagement::AccessibilitySettings *__hidden this, struct Windows::UI::Core::ICoreWindow *, struct Windows::UI::Core::ICoreWindowEventArgs *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dd50`

## callees

- `0x1800151a4`
- `0x180015704`
- `0x180041160`
- `0x18004a320`
- `0x18005a334`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004a3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004a3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a3c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a3c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a3f5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004a363`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004a363`

## pseudocode

```c
__int64 __fastcall Windows::UI::ViewManagement::AccessibilitySettings::OnThemeChanged(
        HSTRING *this,
        struct Windows::UI::Core::ICoreWindow *a2,
        struct Windows::UI::Core::ICoreWindowEventArgs *a3)
{
  HSTRING v4; // rbx
  char v5; // di
  HSTRING v6; // rdx
  HRESULT v7; // eax
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF
  HSTRING result; // [rsp+80h] [rbp+48h] BYREF

  result = (HSTRING)a3;
  if ( Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(
         this + 10,
         a2) )
  {
    pvParam = 0;
    LODWORD(pvParam) = 16;
    if ( SystemParametersInfoW(0x42u, 0, &pvParam, 0) )
    {
      v4 = 0;
      result = 0;
      if ( *((_QWORD *)&pvParam + 1) )
      {
        Windows::Internal::String::_InitializeHelper(
          (Windows::Internal::String *)&result,
          *((const unsigned __int16 **)&pvParam + 1));
        v4 = result;
      }
      v5 = BYTE4(pvParam) & 1;
      if ( (BYTE4(pvParam) & 1) != *((_BYTE *)this + 112)
        || (v6 = this[13], LODWORD(result) = 0, WindowsCompareStringOrdinal(v4, v6, (INT32 *)&result), (_DWORD)result) )
      {
        result = 0;
        v7 = WindowsDuplicateString(v4, &result);
        Windows::Internal::String::FreeAndAssignOnSuccess(v7, result, this + 13);
        *((_BYTE *)this + 112) = v5;
        Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::ViewManagement::AccessibilitySettings *,std::nullptr_t>(
          this + 10,
          this);
      }
      if ( v4 )
        WindowsDeleteString(v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004a320  mov     [rsp-30h+result], r8
0x18004a325  push    rbp
0x18004a326  push    rbx
0x18004a327  push    rsi
0x18004a328  push    rdi
0x18004a329  push    r14
0x18004a32b  push    r15
0x18004a32d  mov     rbp, rsp
0x18004a330  sub     rsp, 38h
0x18004a334  mov     rsi, rcx
0x18004a337  add     rcx, 50h ; 'P'
0x18004a33b  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x18004a340  test    rax, rax
0x18004a343  jz      loc_18004A3FB
0x18004a349  xor     edx, edx; uiParam
0x18004a34b  lea     r8, [rbp+pvParam]; pvParam
0x18004a34f  xorps   xmm0, xmm0
0x18004a352  xor     r9d, r9d; fWinIni
0x18004a355  movups  [rbp+pvParam], xmm0
0x18004a359  mov     dword ptr [rbp+pvParam], 10h
0x18004a360  lea     ecx, [rdx+42h]; uiAction
0x18004a363  call    cs:__imp_SystemParametersInfoW
0x18004a369  test    eax, eax
0x18004a36b  jz      loc_18004A3FB
0x18004a371  mov     rdx, qword ptr [rbp+pvParam+8]; unsigned __int16 *
0x18004a375  xor     ebx, ebx
0x18004a377  mov     [rbp+result], rbx
0x18004a37b  test    rdx, rdx
0x18004a37e  jz      short loc_18004A38D
0x18004a380  lea     rcx, [rbp+result]; this
0x18004a384  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18004a389  mov     rbx, [rbp+result]
0x18004a38d  mov     dil, byte ptr [rbp+pvParam+4]
0x18004a391  and     dil, 1
0x18004a395  cmp     dil, [rsi+70h]
0x18004a399  jnz     short loc_18004A3B9
0x18004a39b  mov     rdx, [rsi+68h]; string2
0x18004a39f  lea     r8, [rbp+result]; result
0x18004a3a3  mov     rcx, rbx; string1
0x18004a3a6  mov     dword ptr [rbp+result], 0
0x18004a3ad  call    cs:__imp_WindowsCompareStringOrdinal
0x18004a3b3  cmp     dword ptr [rbp+result], 0
0x18004a3b7  jz      short loc_18004A3ED
0x18004a3b9  lea     rdx, [rbp+result]; newString
0x18004a3bd  mov     [rbp+result], 0
0x18004a3c5  mov     rcx, rbx; string
0x18004a3c8  call    cs:__imp_WindowsDuplicateString
0x18004a3ce  mov     rdx, [rbp+result]; HSTRING
0x18004a3d2  lea     r8, [rsi+68h]; HSTRING *
0x18004a3d6  mov     ecx, eax; int
0x18004a3d8  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18004a3dd  mov     rdx, rsi
0x18004a3e0  mov     [rsi+70h], dil
0x18004a3e4  lea     rcx, [rsi+50h]
0x18004a3e8  call    ??$InvokeAll@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@$$T@?$EventSource@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVAccessibilitySettings@ViewManagement@UI@Windows@@$$T@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::ViewManagement::AccessibilitySettings *,std::nullptr_t>(Windows::UI::ViewManagement::AccessibilitySettings *,std::nullptr_t)
0x18004a3ed  test    rbx, rbx
0x18004a3f0  jz      short loc_18004A3FB
0x18004a3f2  mov     rcx, rbx; string
0x18004a3f5  call    cs:__imp_WindowsDeleteString
0x18004a3fb  xor     eax, eax
0x18004a3fd  add     rsp, 38h
0x18004a401  pop     r15
0x18004a403  pop     r14
0x18004a405  pop     rdi
0x18004a406  pop     rsi
0x18004a407  pop     rbx
0x18004a408  pop     rbp
0x18004a409  retn
```
