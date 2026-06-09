# IsLogonUI(void)

- ea: `0x14000e624`
- end: `0x14000e6dd`
- name: `?IsLogonUI@@YA_NXZ`
- size: `185`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140012f54`
- `0x140018ed8`
- `0x1400206e8`

## callees

- `0x140002480`
- `0x14000e624`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000e63b`
- `KERNEL32!GetCurrentThreadId` at `0x14000e63b`
- `USER32!GetThreadDesktop` at `0x14000e649`
- `USER32!GetThreadDesktop` at `0x14000e649`
- `USER32!GetUserObjectInformationW` at `0x14000e68d`
- `USER32!GetUserObjectInformationW` at `0x14000e68d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000e6ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000e6ae`

## pseudocode

```c
char IsLogonUI(void)
{
  char v0; // bl
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  __int128 v4; // [rsp+30h] [rbp-48h] BYREF
  wchar_t v5; // [rsp+40h] [rbp-38h]
  _BYTE pvInfo[16]; // [rsp+48h] [rbp-30h] BYREF
  __int16 v7; // [rsp+58h] [rbp-20h]

  v0 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop )
  {
    v5 = aWinlogon[8];
    v4 = *(_OWORD *)L"Winlogon";
    if ( GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0) )
    {
      v7 = 0;
      return (unsigned int)_o__wcsicmp(pvInfo, &v4) == 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000e624  push    rbx
0x14000e626  sub     rsp, 70h
0x14000e62a  mov     rax, cs:__security_cookie
0x14000e631  xor     rax, rsp
0x14000e634  mov     [rsp+78h+var_18], rax
0x14000e639  xor     bl, bl
0x14000e63b  call    cs:__imp_GetCurrentThreadId
0x14000e642  nop     dword ptr [rax+rax+00h]
0x14000e647  mov     ecx, eax; dwThreadId
0x14000e649  call    cs:__imp_GetThreadDesktop
0x14000e650  nop     dword ptr [rax+rax+00h]
0x14000e655  test    rax, rax
0x14000e658  jz      short loc_14000E6C7
0x14000e65a  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x14000e661  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x14000e666  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x14000e66d  mov     r9d, 12h; nLength
0x14000e673  mov     [rsp+78h+var_38], cx
0x14000e678  mov     rcx, rax; hObj
0x14000e67b  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x14000e684  movups  [rsp+78h+var_48], xmm0
0x14000e689  lea     edx, [r9-10h]; nIndex
0x14000e68d  call    cs:__imp_GetUserObjectInformationW
0x14000e694  nop     dword ptr [rax+rax+00h]
0x14000e699  test    eax, eax
0x14000e69b  jz      short loc_14000E6C7
0x14000e69d  xor     ecx, ecx
0x14000e69f  lea     rdx, [rsp+78h+var_48]
0x14000e6a4  mov     [rsp+78h+var_20], cx
0x14000e6a9  lea     rcx, [rsp+78h+pvInfo]
0x14000e6ae  call    cs:__imp__o__wcsicmp
0x14000e6b5  nop     dword ptr [rax+rax+00h]
0x14000e6ba  movzx   ebx, bl
0x14000e6bd  mov     ecx, 1
0x14000e6c2  test    eax, eax
0x14000e6c4  cmovz   ebx, ecx
0x14000e6c7  mov     al, bl
0x14000e6c9  mov     rcx, [rsp+78h+var_18]
0x14000e6ce  xor     rcx, rsp; StackCookie
0x14000e6d1  call    __security_check_cookie
0x14000e6d6  add     rsp, 70h
0x14000e6da  pop     rbx
0x14000e6db  retn
```
