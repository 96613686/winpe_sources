# SsTrackShareCreationForRoleInstall

- ea: `0x18002b7b8`
- end: `0x18002b980`
- name: `SsTrackShareCreationForRoleInstall`
- size: `456`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180003f60`

## callees

- `0x18001deb0`
- `0x18001e80c`
- `0x180020de8`
- `0x180026838`
- `0x18002b7b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b926`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b882`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b873`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b873`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002b904`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002b904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b91e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b91e`

## string_xrefs

- `0x18002b89d`: `dism /online /enable-feature /featurename:File-Services /NoRestart`

## pseudocode

```c
unsigned int __fastcall SsTrackShareCreationForRoleInstall(char a1, int a2, int a3, int a4)
{
  unsigned int result; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[104]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  result = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  hKey = 0;
  if ( dword_18005CCF8 != 1 && !a3 && !a4 && !a2 )
  {
    result = _InterlockedIncrement(&UserShareCount);
    if ( result == 1 && !a1 )
    {
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey) )
      {
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        result = StringCbCopyW(pszDest, 0xC8u, L"dism /online /enable-feature /featurename:File-Services /NoRestart");
        if ( !result )
        {
          if ( CreateProcessW(0, pszDest, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            CloseHandle(ProcessInformation.hProcess);
            return CloseHandle(ProcessInformation.hThread);
          }
          else
          {
            result = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
                return WPP_SF_d(
                         *((_QWORD *)WPP_GLOBAL_Control + 2),
                         10,
                         WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids,
                         result);
            }
          }
        }
      }
      else
      {
        return RegCloseKey(hKey);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b7b8  push    rbp
0x18002b7ba  push    rbx
0x18002b7bb  push    rsi
0x18002b7bc  push    rdi
0x18002b7bd  push    r14
0x18002b7bf  lea     rbp, [rsp-0C0h]
0x18002b7c7  sub     rsp, 1C0h
0x18002b7ce  mov     rax, cs:__security_cookie
0x18002b7d5  xor     rax, rsp
0x18002b7d8  mov     [rbp+0E0h+var_30], rax
0x18002b7df  mov     ebx, edx
0x18002b7e1  mov     esi, r8d
0x18002b7e4  xor     edx, edx; Val
0x18002b7e6  mov     r14b, cl
0x18002b7e9  lea     rcx, [rsp+1E0h+StartupInfo]; void *
0x18002b7ee  mov     edi, r9d
0x18002b7f1  lea     r8d, [rdx+68h]; Size
0x18002b7f5  call    memset_0
0x18002b7fa  xor     eax, eax
0x18002b7fc  xorps   xmm0, xmm0
0x18002b7ff  cmp     cs:dword_18005CCF8, 1
0x18002b806  movups  xmmword ptr [rsp+1E0h+ProcessInformation.hProcess], xmm0
0x18002b80b  mov     qword ptr [rsp+1E0h+ProcessInformation.dwProcessId], rax
0x18002b810  mov     [rsp+1E0h+hKey], rax
0x18002b815  jz      loc_18002B963
0x18002b81b  test    esi, esi
0x18002b81d  jnz     loc_18002B963
0x18002b823  test    edi, edi
0x18002b825  jnz     loc_18002B963
0x18002b82b  test    ebx, ebx
0x18002b82d  jnz     loc_18002B963
0x18002b833  lea     eax, [rsi+1]
0x18002b836  lock xadd cs:UserShareCount, eax
0x18002b83e  inc     eax
0x18002b840  cmp     eax, 1
0x18002b843  jnz     loc_18002B963
0x18002b849  test    r14b, r14b
0x18002b84c  jnz     loc_18002B963
0x18002b852  lea     rax, [rsp+1E0h+hKey]
0x18002b857  mov     r9d, 20019h; samDesired
0x18002b85d  xor     r8d, r8d; ulOptions
0x18002b860  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002b865  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Min"...
0x18002b86c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b873  call    cs:__imp_RegOpenKeyExW
0x18002b879  test    eax, eax
0x18002b87b  jnz     short loc_18002B88D
0x18002b87d  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002b882  call    cs:__imp_RegCloseKey
0x18002b888  jmp     loc_18002B963
0x18002b88d  xor     edx, edx; Val
0x18002b88f  lea     rcx, [rsp+1E0h+StartupInfo+4]; void *
0x18002b894  lea     r8d, [rdx+64h]; Size
0x18002b898  call    memset_0
0x18002b89d  lea     r8, aDismOnlineEnab; "dism /online /enable-feature /featurena"...
0x18002b8a4  mov     [rsp+1E0h+StartupInfo.cb], 68h ; 'h'
0x18002b8ac  mov     edx, 0C8h; cbDest
0x18002b8b1  lea     rcx, [rbp+0E0h+pszDest]; pszDest
0x18002b8b5  call    StringCbCopyW
0x18002b8ba  test    eax, eax
0x18002b8bc  jnz     loc_18002B963
0x18002b8c2  lea     rax, [rsp+1E0h+ProcessInformation]
0x18002b8c7  xor     r9d, r9d; lpThreadAttributes
0x18002b8ca  mov     [rsp+1E0h+lpProcessInformation], rax; lpProcessInformation
0x18002b8cf  lea     rdx, [rbp+0E0h+pszDest]; lpCommandLine
0x18002b8d3  lea     rax, [rsp+1E0h+StartupInfo]
0x18002b8d8  xor     r8d, r8d; lpProcessAttributes
0x18002b8db  mov     [rsp+1E0h+lpStartupInfo], rax; lpStartupInfo
0x18002b8e0  xor     ecx, ecx; lpApplicationName
0x18002b8e2  mov     [rsp+1E0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002b8eb  mov     [rsp+1E0h+lpEnvironment], 0; lpEnvironment
0x18002b8f4  mov     [rsp+1E0h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002b8fc  mov     dword ptr [rsp+1E0h+phkResult], 0; bInheritHandles
0x18002b904  call    cs:__imp_CreateProcessW
0x18002b90a  test    eax, eax
0x18002b90c  jz      short loc_18002B926
0x18002b90e  mov     rcx, [rsp+1E0h+ProcessInformation.hProcess]; hObject
0x18002b913  call    cs:__imp_CloseHandle
0x18002b919  mov     rcx, [rsp+1E0h+ProcessInformation.hThread]; hObject
0x18002b91e  call    cs:__imp_CloseHandle
0x18002b924  jmp     short loc_18002B963
0x18002b926  call    cs:__imp_GetLastError
0x18002b92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b933  lea     rdx, WPP_GLOBAL_Control
0x18002b93a  cmp     rcx, rdx
0x18002b93d  jz      short loc_18002B963
0x18002b93f  test    byte ptr [rcx+1Ch], 4
0x18002b943  jz      short loc_18002B963
0x18002b945  cmp     byte ptr [rcx+19h], 1
0x18002b949  jb      short loc_18002B963
0x18002b94b  mov     rcx, [rcx+10h]
0x18002b94f  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002b956  mov     edx, 0Ah
0x18002b95b  mov     r9d, eax
0x18002b95e  call    WPP_SF_d
0x18002b963  mov     rcx, [rbp+0E0h+var_30]
0x18002b96a  xor     rcx, rsp; StackCookie
0x18002b96d  call    __security_check_cookie
0x18002b972  add     rsp, 1C0h
0x18002b979  pop     r14
0x18002b97b  pop     rdi
0x18002b97c  pop     rsi
0x18002b97d  pop     rbx
0x18002b97e  pop     rbp
0x18002b97f  retn
```
