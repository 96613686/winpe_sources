# pSpUtilsSetLogPath

- ea: `0x180016424`
- end: `0x1800164d7`
- name: `pSpUtilsSetLogPath`
- size: `179`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180016110`
- `0x18001621c`

## callees

- `0x18000cab0`
- `0x18000fe68`
- `0x180010384`
- `0x180016424`
- `0x180017708`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800164b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164a7`

## pseudocode

```c
_BOOL8 pSpUtilsSetLogPath()
{
  DWORD LastError; // ebx
  unsigned int v1; // r11d
  int v2; // ebx
  wchar_t pszDest[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( g_sputils_WindowsDirectory && StringCchCopyW(pszDest, 0x104u, g_sputils_WindowsDirectory) >= 0 )
  {
    v2 = g_sputils_IsOnlineWindowsDirectory;
    if ( !pSetupConcatenatePaths((__int64)pszDest, L"INF", v1)
      || !(unsigned int)pSpUtilsSetTextLogPath((__int64)pszDest, v2)
      || (LastError = 0, !(unsigned int)pSpUtilsLogSetPath((__int64)pszDest)) )
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180016424  push    rbx
0x180016426  sub     rsp, 240h
0x18001642d  mov     rax, cs:__security_cookie
0x180016434  xor     rax, rsp
0x180016437  mov     [rsp+248h+var_18], rax
0x18001643f  mov     r8, cs:g_sputils_WindowsDirectory; pszSrc
0x180016446  test    r8, r8
0x180016449  jnz     short loc_180016452
0x18001644b  mov     ebx, 57h ; 'W'
0x180016450  jmp     short loc_1800164AF
0x180016452  mov     r11d, 104h
0x180016458  lea     rcx, [rsp+248h+pszDest]; pszDest
0x18001645d  mov     edx, r11d; cchDest
0x180016460  call    StringCchCopyW
0x180016465  test    eax, eax
0x180016467  js      short loc_18001644B
0x180016469  mov     ebx, cs:g_sputils_IsOnlineWindowsDirectory
0x18001646f  lea     rdx, aInf; "INF"
0x180016476  mov     r8d, r11d
0x180016479  lea     rcx, [rsp+248h+pszDest]
0x18001647e  call    pSetupConcatenatePaths
0x180016483  test    eax, eax
0x180016485  jz      short loc_1800164A7
0x180016487  mov     edx, ebx
0x180016489  lea     rcx, [rsp+248h+pszDest]
0x18001648e  call    _pSpUtilsSetTextLogPath
0x180016493  test    eax, eax
0x180016495  jz      short loc_1800164A7
0x180016497  lea     rcx, [rsp+248h+pszDest]
0x18001649c  xor     ebx, ebx
0x18001649e  call    _pSpUtilsLogSetPath
0x1800164a3  test    eax, eax
0x1800164a5  jnz     short loc_1800164AF
0x1800164a7  call    cs:__imp_GetLastError
0x1800164ad  mov     ebx, eax
0x1800164af  mov     ecx, ebx; dwErrCode
0x1800164b1  call    cs:__imp_SetLastError
0x1800164b7  xor     eax, eax
0x1800164b9  test    ebx, ebx
0x1800164bb  setz    al
0x1800164be  mov     rcx, [rsp+248h+var_18]
0x1800164c6  xor     rcx, rsp; StackCookie
0x1800164c9  call    __security_check_cookie
0x1800164ce  add     rsp, 240h
0x1800164d5  pop     rbx
0x1800164d6  retn
```
