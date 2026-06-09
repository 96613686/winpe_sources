# winrt::Udwm::Transitions::implementation::TransitionState::IsWallpaperViewExisted(void)

- ea: `0x1800d7f08`
- end: `0x1800d7f9f`
- name: `?IsWallpaperViewExisted@TransitionState@implementation@Transitions@Udwm@winrt@@QEAA_NXZ`
- size: `151`
- prototype: `bool __fastcall(winrt::Udwm::Transitions::implementation::TransitionState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800d9220`

## callees

- `0x180004714`
- `0x180005948`
- `0x1800d7f08`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800d7f56`
- `USER32!SystemParametersInfoW` at `0x1800d7f56`
- `USER32!GetDesktopID` at `0x1800d7f27`
- `USER32!GetDesktopID` at `0x1800d7f6b`
- `USER32!GetDesktopID` at `0x1800d7f27`
- `USER32!GetDesktopID` at `0x1800d7f6b`

## pseudocode

```c
char __fastcall winrt::Udwm::Transitions::implementation::TransitionState::IsWallpaperViewExisted(
        winrt::Udwm::Transitions::implementation::TransitionState *this)
{
  char v1; // bl
  HWND ShellWindowForDesktop; // rax
  winrt::Udwm::Transitions::implementation::TransitionState *pvParam; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  pvParam = this;
  v1 = 1;
  v5 = 0;
  GetDesktopID(1, &v5);
  if ( CDesktopManager::IsLogonDesktop(v5) )
    return 0;
  LODWORD(pvParam) = 0;
  if ( !SystemParametersInfoW(0xAAu, 0, &pvParam, 0) )
    LODWORD(pvParam) = 0;
  GetDesktopID(1, &v5);
  ShellWindowForDesktop = CWindowList::GetShellWindowForDesktop(
                            *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                            v5);
  if ( (_DWORD)pvParam || !ShellWindowForDesktop )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x1800d7f08  mov     [rsp+pvParam], rcx
0x1800d7f0d  push    rbx
0x1800d7f0e  sub     rsp, 20h
0x1800d7f12  mov     ebx, 1
0x1800d7f17  mov     [rsp+28h+arg_8], 0
0x1800d7f20  mov     ecx, ebx
0x1800d7f22  lea     rdx, [rsp+28h+arg_8]
0x1800d7f27  call    cs:__imp_GetDesktopID
0x1800d7f2d  mov     rcx, [rsp+28h+arg_8]; unsigned __int64
0x1800d7f32  call    ?IsLogonDesktop@CDesktopManager@@SA_N_K@Z; CDesktopManager::IsLogonDesktop(unsigned __int64)
0x1800d7f37  test    al, al
0x1800d7f39  jz      short loc_1800D7F3F
0x1800d7f3b  xor     al, al
0x1800d7f3d  jmp     short loc_1800D7F99
0x1800d7f3f  xor     r9d, r9d; fWinIni
0x1800d7f42  mov     dword ptr [rsp+28h+pvParam], 0
0x1800d7f4a  lea     r8, [rsp+28h+pvParam]; pvParam
0x1800d7f4f  xor     edx, edx; uiParam
0x1800d7f51  mov     ecx, 0AAh; uiAction
0x1800d7f56  call    cs:__imp_SystemParametersInfoW
0x1800d7f5c  test    eax, eax
0x1800d7f5e  jnz     short loc_1800D7F64
0x1800d7f60  mov     dword ptr [rsp+28h+pvParam], eax
0x1800d7f64  lea     rdx, [rsp+28h+arg_8]
0x1800d7f69  mov     ecx, ebx
0x1800d7f6b  call    cs:__imp_GetDesktopID
0x1800d7f71  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800d7f78  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x1800d7f7d  mov     rcx, [rcx+1A8h]; this
0x1800d7f84  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x1800d7f89  cmp     dword ptr [rsp+28h+pvParam], 0
0x1800d7f8e  jnz     short loc_1800D7F95
0x1800d7f90  test    rax, rax
0x1800d7f93  jnz     short loc_1800D7F97
0x1800d7f95  xor     bl, bl
0x1800d7f97  mov     al, bl
0x1800d7f99  add     rsp, 20h
0x1800d7f9d  pop     rbx
0x1800d7f9e  retn
```
