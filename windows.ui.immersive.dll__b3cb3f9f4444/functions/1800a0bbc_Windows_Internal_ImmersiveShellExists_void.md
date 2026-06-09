# Windows::Internal::ImmersiveShellExists(void)

- ea: `0x1800a0bbc`
- end: `0x1800a0c9a`
- name: `?ImmersiveShellExists@Internal@Windows@@YA_NXZ`
- size: `222`
- prototype: `bool __fastcall(Windows::Internal *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180047c3c`
- `0x1800a0a20`

## callees

- `0x180054130`
- `0x1800a0bbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a0c44`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a0c44`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800a0c62`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800a0c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0c74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800a0c23`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800a0c23`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800a0bdf`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x1800a0bdf`

## pseudocode

```c
bool __fastcall Windows::Internal::ImmersiveShellExists(Windows::Internal *this)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  int v3; // eax
  HANDLE v4; // rbx
  __int128 v6; // [rsp+30h] [rbp-48h] BYREF
  wchar_t v7; // [rsp+40h] [rbp-38h]
  _BYTE pvInfo[16]; // [rsp+48h] [rbp-30h] BYREF
  __int16 v9; // [rsp+58h] [rbp-20h]

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( !ThreadDesktop
    || (v7 = aWinlogon[8], v6 = *(_OWORD *)L"Winlogon", !GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0))
    || (v9 = 0, (v3 = _o__wcsicmp(pvInfo, &v6)) != 0) )
  {
    v4 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    CloseHandle(v4);
    LOBYTE(v3) = v4 == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1800a0bbc  push    rbx
0x1800a0bbe  sub     rsp, 70h
0x1800a0bc2  mov     rax, cs:__security_cookie
0x1800a0bc9  xor     rax, rsp
0x1800a0bcc  mov     [rsp+78h+var_18], rax
0x1800a0bd1  call    cs:__imp_GetCurrentThreadId
0x1800a0bd8  nop     dword ptr [rax+rax+00h]
0x1800a0bdd  mov     ecx, eax; dwThreadId
0x1800a0bdf  call    cs:__imp_GetThreadDesktop
0x1800a0be6  nop     dword ptr [rax+rax+00h]
0x1800a0beb  test    rax, rax
0x1800a0bee  jz      short loc_1800A0C54
0x1800a0bf0  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x1800a0bf7  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x1800a0bfc  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x1800a0c03  mov     r9d, 12h; nLength
0x1800a0c09  mov     [rsp+78h+var_38], cx
0x1800a0c0e  mov     rcx, rax; hObj
0x1800a0c11  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x1800a0c1a  movups  [rsp+78h+var_48], xmm0
0x1800a0c1f  lea     edx, [r9-10h]; nIndex
0x1800a0c23  call    cs:__imp_GetUserObjectInformationW
0x1800a0c2a  nop     dword ptr [rax+rax+00h]
0x1800a0c2f  test    eax, eax
0x1800a0c31  jz      short loc_1800A0C54
0x1800a0c33  xor     eax, eax
0x1800a0c35  lea     rdx, [rsp+78h+var_48]
0x1800a0c3a  lea     rcx, [rsp+78h+pvInfo]
0x1800a0c3f  mov     [rsp+78h+var_20], ax
0x1800a0c44  call    cs:__imp__o__wcsicmp
0x1800a0c4b  nop     dword ptr [rax+rax+00h]
0x1800a0c50  test    eax, eax
0x1800a0c52  jz      short loc_1800A0C86
0x1800a0c54  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x1800a0c5b  xor     edx, edx; bInheritHandle
0x1800a0c5d  mov     ecx, 100000h; dwDesiredAccess
0x1800a0c62  call    cs:__imp_OpenMutexW
0x1800a0c69  nop     dword ptr [rax+rax+00h]
0x1800a0c6e  mov     rcx, rax; hObject
0x1800a0c71  mov     rbx, rax
0x1800a0c74  call    cs:__imp_CloseHandle
0x1800a0c7b  nop     dword ptr [rax+rax+00h]
0x1800a0c80  test    rbx, rbx
0x1800a0c83  setz    al
0x1800a0c86  mov     rcx, [rsp+78h+var_18]
0x1800a0c8b  xor     rcx, rsp; StackCookie
0x1800a0c8e  call    __security_check_cookie
0x1800a0c93  add     rsp, 70h
0x1800a0c97  pop     rbx
0x1800a0c98  retn
```
