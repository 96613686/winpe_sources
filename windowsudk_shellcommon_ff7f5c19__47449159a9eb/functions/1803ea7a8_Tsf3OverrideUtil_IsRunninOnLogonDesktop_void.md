# Tsf3OverrideUtil::IsRunninOnLogonDesktop(void)

- ea: `0x1803ea7a8`
- end: `0x1803ea836`
- name: `?IsRunninOnLogonDesktop@Tsf3OverrideUtil@@YA_NXZ`
- size: `142`
- prototype: `bool __fastcall(Tsf3OverrideUtil *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c31d8`

## callees

- `0x18015cb00`
- `0x1803ea7a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ea80f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ea80f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803ea7c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803ea7c1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1803ea7c9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1803ea7c9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1803ea7f9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1803ea7f9`

## pseudocode

```c
bool __fastcall Tsf3OverrideUtil::IsRunninOnLogonDesktop(Tsf3OverrideUtil *this)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  DWORD nLengthNeeded[4]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE pvInfo[528]; // [rsp+40h] [rbp-228h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  nLengthNeeded[0] = 0;
  return ThreadDesktop
      && GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, nLengthNeeded)
      && (unsigned int)_o__wcsicmp(pvInfo, L"winlogon") == 0;
}

```

## disassembly

```asm
0x1803ea7a8  sub     rsp, 268h
0x1803ea7af  mov     rax, cs:__security_cookie
0x1803ea7b6  xor     rax, rsp
0x1803ea7b9  mov     [rsp+268h+var_18], rax
0x1803ea7c1  call    cs:__imp_GetCurrentThreadId
0x1803ea7c7  mov     ecx, eax; dwThreadId
0x1803ea7c9  call    cs:__imp_GetThreadDesktop
0x1803ea7cf  mov     [rsp+268h+nLengthNeeded], 0
0x1803ea7d7  test    rax, rax
0x1803ea7da  jz      short loc_1803EA81C
0x1803ea7dc  lea     rcx, [rsp+268h+nLengthNeeded]
0x1803ea7e1  mov     r9d, 208h; nLength
0x1803ea7e7  mov     [rsp+268h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x1803ea7ec  lea     r8, [rsp+268h+pvInfo]; pvInfo
0x1803ea7f1  mov     rcx, rax; hObj
0x1803ea7f4  mov     edx, 2; nIndex
0x1803ea7f9  call    cs:__imp_GetUserObjectInformationW
0x1803ea7ff  test    eax, eax
0x1803ea801  jz      short loc_1803EA81C
0x1803ea803  lea     rdx, aWinlogon; "winlogon"
0x1803ea80a  lea     rcx, [rsp+268h+pvInfo]
0x1803ea80f  call    cs:__imp__o__wcsicmp
0x1803ea815  test    eax, eax
0x1803ea817  setz    al
0x1803ea81a  jmp     short loc_1803EA81E
0x1803ea81c  xor     al, al
0x1803ea81e  mov     rcx, [rsp+268h+var_18]
0x1803ea826  xor     rcx, rsp; StackCookie
0x1803ea829  call    __security_check_cookie
0x1803ea82e  add     rsp, 268h
0x1803ea835  retn
```
