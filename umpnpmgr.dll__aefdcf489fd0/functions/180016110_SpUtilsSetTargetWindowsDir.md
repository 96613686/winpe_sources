# SpUtilsSetTargetWindowsDir

- ea: `0x180016110`
- end: `0x1800161ca`
- name: `SpUtilsSetTargetWindowsDir`
- size: `186`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000fccc`

## callees

- `0x180016110`
- `0x180016424`
- `0x1800164e0`
- `0x1800180b0`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016163`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016163`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016142`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016142`

## pseudocode

```c
__int64 SpUtilsSetTargetWindowsDir()
{
  unsigned int v0; // ebx
  WCHAR Buffer[296]; // [rsp+20h] [rbp-268h] BYREF

  v0 = 0;
  if ( g_sputils_WindowsDirectory )
  {
    HeapFree(hHeap, 0, (LPVOID)g_sputils_WindowsDirectory);
    g_sputils_WindowsDirectory = 0;
  }
  g_sputils_IsOnlineWindowsDirectory = 1;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x103 )
  {
    g_sputils_WindowsDirectory = (STRSAFE_LPCWSTR)pSetupDuplicateString(Buffer);
    if ( g_sputils_WindowsDirectory )
    {
      if ( !g_sputils_LogInitialized
        || g_sputils_IsOnlineWindowsDirectory && pSpUtilsSetLogPathFromRegKey()
        || pSpUtilsSetLogPath() )
      {
        return 1;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180016110  push    rbx
0x180016112  sub     rsp, 280h
0x180016119  mov     rax, cs:__security_cookie
0x180016120  xor     rax, rsp
0x180016123  mov     [rsp+288h+var_18], rax
0x18001612b  mov     r8, cs:g_sputils_WindowsDirectory; lpMem
0x180016132  xor     ebx, ebx
0x180016134  test    r8, r8
0x180016137  jz      short loc_18001614F
0x180016139  mov     rcx, cs:hHeap; hHeap
0x180016140  xor     edx, edx; dwFlags
0x180016142  call    cs:__imp_HeapFree
0x180016148  mov     cs:g_sputils_WindowsDirectory, rbx
0x18001614f  mov     edx, 104h; uSize
0x180016154  mov     cs:g_sputils_IsOnlineWindowsDirectory, 1
0x18001615e  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x180016163  call    cs:__imp_GetSystemWindowsDirectoryW
0x180016169  dec     eax
0x18001616b  cmp     eax, 103h
0x180016170  ja      short loc_1800161AF
0x180016172  lea     rcx, [rsp+288h+Buffer]; pszSrc
0x180016177  call    pSetupDuplicateString
0x18001617c  mov     cs:g_sputils_WindowsDirectory, rax
0x180016183  test    rax, rax
0x180016186  jz      short loc_1800161AF
0x180016188  cmp     cs:g_sputils_LogInitialized, ebx
0x18001618e  jz      short loc_1800161AA
0x180016190  cmp     cs:g_sputils_IsOnlineWindowsDirectory, ebx
0x180016196  jz      short loc_1800161A1
0x180016198  call    pSpUtilsSetLogPathFromRegKey
0x18001619d  test    eax, eax
0x18001619f  jnz     short loc_1800161AA
0x1800161a1  call    pSpUtilsSetLogPath
0x1800161a6  test    eax, eax
0x1800161a8  jz      short loc_1800161AF
0x1800161aa  mov     ebx, 1
0x1800161af  mov     eax, ebx
0x1800161b1  mov     rcx, [rsp+288h+var_18]
0x1800161b9  xor     rcx, rsp; StackCookie
0x1800161bc  call    __security_check_cookie
0x1800161c1  add     rsp, 280h
0x1800161c8  pop     rbx
0x1800161c9  retn
```
