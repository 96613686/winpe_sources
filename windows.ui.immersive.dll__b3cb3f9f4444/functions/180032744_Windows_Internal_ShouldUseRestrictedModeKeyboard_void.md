# Windows::Internal::ShouldUseRestrictedModeKeyboard(void)

- ea: `0x180032744`
- end: `0x180032826`
- name: `?ShouldUseRestrictedModeKeyboard@Internal@Windows@@YA_NXZ`
- size: `226`
- prototype: `bool __fastcall(Windows::Internal *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180047c3c`
- `0x180048928`
- `0x1800ad5cc`

## callees

- `0x180032744`
- `0x180054130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800327cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800327cc`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800327ee`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800327ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032800`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800327ab`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800327ab`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180032767`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180032767`

## pseudocode

```c
bool __fastcall Windows::Internal::ShouldUseRestrictedModeKeyboard(Windows::Internal *this)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HANDLE v4; // rbx
  __int128 v5; // [rsp+30h] [rbp-48h] BYREF
  wchar_t v6; // [rsp+40h] [rbp-38h]
  _BYTE pvInfo[16]; // [rsp+48h] [rbp-30h] BYREF
  __int16 v8; // [rsp+58h] [rbp-20h]

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop )
  {
    v6 = aWinlogon[8];
    v5 = *(_OWORD *)L"Winlogon";
    if ( GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0) )
    {
      v8 = 0;
      if ( !(unsigned int)_o__wcsicmp(pvInfo, &v5) )
        return 1;
    }
  }
  v4 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
  CloseHandle(v4);
  return v4 != 0;
}

```

## disassembly

```asm
0x180032744  push    rbx
0x180032746  sub     rsp, 70h
0x18003274a  mov     rax, cs:__security_cookie
0x180032751  xor     rax, rsp
0x180032754  mov     [rsp+78h+var_18], rax
0x180032759  call    cs:__imp_GetCurrentThreadId
0x180032760  nop     dword ptr [rax+rax+00h]
0x180032765  mov     ecx, eax; dwThreadId
0x180032767  call    cs:__imp_GetThreadDesktop
0x18003276e  nop     dword ptr [rax+rax+00h]
0x180032773  test    rax, rax
0x180032776  jz      short loc_1800327E0
0x180032778  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x18003277f  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x180032784  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x18003278b  mov     r9d, 12h; nLength
0x180032791  mov     [rsp+78h+var_38], cx
0x180032796  mov     rcx, rax; hObj
0x180032799  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x1800327a2  movups  [rsp+78h+var_48], xmm0
0x1800327a7  lea     edx, [r9-10h]; nIndex
0x1800327ab  call    cs:__imp_GetUserObjectInformationW
0x1800327b2  nop     dword ptr [rax+rax+00h]
0x1800327b7  test    eax, eax
0x1800327b9  jz      short loc_1800327E0
0x1800327bb  xor     eax, eax
0x1800327bd  lea     rdx, [rsp+78h+var_48]
0x1800327c2  lea     rcx, [rsp+78h+pvInfo]
0x1800327c7  mov     [rsp+78h+var_20], ax
0x1800327cc  call    cs:__imp__o__wcsicmp
0x1800327d3  nop     dword ptr [rax+rax+00h]
0x1800327d8  test    eax, eax
0x1800327da  jnz     short loc_1800327E0
0x1800327dc  mov     al, 1
0x1800327de  jmp     short loc_180032812
0x1800327e0  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x1800327e7  xor     edx, edx; bInheritHandle
0x1800327e9  mov     ecx, 100000h; dwDesiredAccess
0x1800327ee  call    cs:__imp_OpenMutexW
0x1800327f5  nop     dword ptr [rax+rax+00h]
0x1800327fa  mov     rcx, rax; hObject
0x1800327fd  mov     rbx, rax
0x180032800  call    cs:__imp_CloseHandle
0x180032807  nop     dword ptr [rax+rax+00h]
0x18003280c  test    rbx, rbx
0x18003280f  setnz   al
0x180032812  mov     rcx, [rsp+78h+var_18]
0x180032817  xor     rcx, rsp; StackCookie
0x18003281a  call    __security_check_cookie
0x18003281f  add     rsp, 70h
0x180032823  pop     rbx
0x180032824  retn
```
