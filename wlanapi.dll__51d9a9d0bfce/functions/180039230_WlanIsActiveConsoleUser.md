# WlanIsActiveConsoleUser

- ea: `0x180039230`
- end: `0x180039335`
- name: `WlanIsActiveConsoleUser`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180019a20`
- `0x18001a5bc`
- `0x180039230`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003926b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003926b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180039278`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180039278`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180039286`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180039286`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x1800392a7`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x1800392a7`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1800392d8`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18003930a`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1800392d8`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x18003930a`

## pseudocode

```c
__int64 WlanIsActiveConsoleUser()
{
  unsigned int v0; // ebx
  DWORD CurrentProcessId; // eax
  ULONGLONG v2; // rdi
  BOOL v3; // ebx
  DWORD pSessionId[4]; // [rsp+20h] [rbp-E0h] BYREF
  _OSVERSIONINFOEXW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF

  v0 = 0;
  pSessionId[0] = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) )
  {
    if ( pSessionId[0] == WTSGetActiveConsoleSessionId() )
    {
      return 1;
    }
    else if ( !pSessionId[0] )
    {
      v2 = VerSetConditionMask(0, 0x40u, 7u);
      memset_0(&VersionInformation, 0, sizeof(VersionInformation));
      VersionInformation.dwOSVersionInfoSize = 284;
      VersionInformation.wSuiteMask = 16;
      v3 = VerifyVersionInfoW(&VersionInformation, 0x40u, v2);
      memset_0(&VersionInformation, 0, sizeof(VersionInformation));
      VersionInformation.dwOSVersionInfoSize = 284;
      VersionInformation.wSuiteMask = 256;
      return (v3 | VerifyVersionInfoW(&VersionInformation, 0x40u, v2)) == 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180039230  push    rbp
0x180039232  push    rbx
0x180039233  push    rdi
0x180039234  push    r14
0x180039236  lea     rbp, [rsp-68h]
0x18003923b  sub     rsp, 168h
0x180039242  mov     rax, cs:__security_cookie
0x180039249  xor     rax, rsp
0x18003924c  mov     [rbp+80h+var_30], rax
0x180039250  mov     r14d, 11Ch
0x180039256  lea     rcx, [rsp+180h+VersionInformation]; void *
0x18003925b  xor     ebx, ebx
0x18003925d  mov     r8d, r14d; Size
0x180039260  xor     edx, edx; Val
0x180039262  mov     [rsp+180h+pSessionId], ebx
0x180039266  call    memset_0
0x18003926b  call    cs:__imp_GetCurrentProcessId
0x180039271  mov     ecx, eax; dwProcessId
0x180039273  lea     rdx, [rsp+180h+pSessionId]; pSessionId
0x180039278  call    cs:__imp_ProcessIdToSessionId
0x18003927e  test    eax, eax
0x180039280  jz      loc_18003931A
0x180039286  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18003928c  mov     ecx, [rsp+180h+pSessionId]
0x180039290  cmp     ecx, eax
0x180039292  jnz     short loc_18003929B
0x180039294  mov     ebx, 1
0x180039299  jmp     short loc_18003931A
0x18003929b  test    ecx, ecx
0x18003929d  jnz     short loc_18003931A
0x18003929f  lea     edx, [rcx+40h]; TypeMask
0x1800392a2  mov     r8b, 7; Condition
0x1800392a5  xor     ecx, ecx; ConditionMask
0x1800392a7  call    cs:__imp_VerSetConditionMask
0x1800392ad  mov     r8, r14; Size
0x1800392b0  lea     rcx, [rsp+180h+VersionInformation]; void *
0x1800392b5  xor     edx, edx; Val
0x1800392b7  mov     rdi, rax
0x1800392ba  call    memset_0
0x1800392bf  mov     eax, 10h
0x1800392c4  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], r14d
0x1800392c9  mov     r8, rdi; dwlConditionMask
0x1800392cc  mov     [rbp+80h+VersionInformation.wSuiteMask], ax
0x1800392d0  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x1800392d5  lea     edx, [rax+30h]; dwTypeMask
0x1800392d8  call    cs:__imp_VerifyVersionInfoW
0x1800392de  mov     r8, r14; Size
0x1800392e1  lea     rcx, [rsp+180h+VersionInformation]; void *
0x1800392e6  xor     edx, edx; Val
0x1800392e8  mov     ebx, eax
0x1800392ea  call    memset_0
0x1800392ef  mov     eax, 100h
0x1800392f4  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], r14d
0x1800392f9  mov     r8, rdi; dwlConditionMask
0x1800392fc  mov     [rbp+80h+VersionInformation.wSuiteMask], ax
0x180039300  mov     edx, 40h ; '@'; dwTypeMask
0x180039305  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x18003930a  call    cs:__imp_VerifyVersionInfoW
0x180039310  or      eax, ebx
0x180039312  mov     ebx, 0
0x180039317  setz    bl
0x18003931a  mov     eax, ebx
0x18003931c  mov     rcx, [rbp+80h+var_30]
0x180039320  xor     rcx, rsp; StackCookie
0x180039323  call    __security_check_cookie
0x180039328  add     rsp, 168h
0x18003932f  pop     r14
0x180039331  pop     rdi
0x180039332  pop     rbx
0x180039333  pop     rbp
0x180039334  retn
```
