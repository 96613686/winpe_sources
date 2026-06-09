# CThemeManager2::_GetInstallThemeMutex(void * *)

- ea: `0x180055e38`
- end: `0x180055ef7`
- name: `?_GetInstallThemeMutex@CThemeManager2@@AEAAJPEAPEAX@Z`
- size: `191`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800547c0`
- `0x180054ad0`

## callees

- `0x1800089c0`
- `0x180030f64`
- `0x1800358c0`
- `0x180055e38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180055ebb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180055ebb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055ee9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180055ee9`
- `SspiCli!GetUserNameExW` at `0x180055e79`
- `SspiCli!GetUserNameExW` at `0x180055e79`

## pseudocode

```c
__int64 __fastcall CThemeManager2::_GetInstallThemeMutex(CThemeManager2 *this, void **a2)
{
  __int64 result; // rax
  HANDLE MutexW; // rax
  ULONG nSize[4]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR NameBuffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Name[264]; // [rsp+240h] [rbp-228h] BYREF

  if ( *a2 )
  {
    if ( WaitForSingleObject(*a2, 0) )
      return ResultFromKnownLastError();
    return 0;
  }
  nSize[0] = 260;
  if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, nSize) )
    NameBuffer[0] = 0;
  result = StringCchPrintfW(Name, 0x104u, L"Local\\%s{A82C030A-ED47-42FA-97A6-00186F63438A}", NameBuffer);
  if ( (int)result >= 0 )
  {
    MutexW = CreateMutexW(0, 1, Name);
    *a2 = MutexW;
    if ( !MutexW )
      return ResultFromKnownLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180055e38  push    rbx
0x180055e3a  sub     rsp, 460h
0x180055e41  mov     rax, cs:__security_cookie
0x180055e48  xor     rax, rsp
0x180055e4b  mov     [rsp+468h+var_18], rax
0x180055e53  mov     rcx, [rdx]; hHandle
0x180055e56  mov     rbx, rdx
0x180055e59  test    rcx, rcx
0x180055e5c  jnz     loc_180055EE7
0x180055e62  lea     r8, [rsp+468h+nSize]; nSize
0x180055e67  mov     [rsp+468h+nSize], 104h
0x180055e6f  lea     rdx, [rsp+468h+NameBuffer]; lpNameBuffer
0x180055e74  mov     ecx, 10002h; NameFormat
0x180055e79  call    cs:__imp_GetUserNameExW
0x180055e7f  test    al, al
0x180055e81  jnz     short loc_180055E8A
0x180055e83  xor     eax, eax
0x180055e85  mov     [rsp+468h+NameBuffer], ax
0x180055e8a  lea     r9, [rsp+468h+NameBuffer]
0x180055e8f  mov     edx, 104h; unsigned __int64
0x180055e94  lea     r8, aLocalSA82c030a; "Local\\%s{A82C030A-ED47-42FA-97A6-00186"...
0x180055e9b  lea     rcx, [rsp+468h+Name]; unsigned __int16 *
0x180055ea3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055ea8  test    eax, eax
0x180055eaa  js      short loc_180055ECE
0x180055eac  lea     r8, [rsp+468h+Name]; lpName
0x180055eb4  mov     edx, 1; bInitialOwner
0x180055eb9  xor     ecx, ecx; lpMutexAttributes
0x180055ebb  call    cs:__imp_CreateMutexW
0x180055ec1  mov     [rbx], rax
0x180055ec4  test    rax, rax
0x180055ec7  jnz     short loc_180055EF3
0x180055ec9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055ece  mov     rcx, [rsp+468h+var_18]
0x180055ed6  xor     rcx, rsp; StackCookie
0x180055ed9  call    __security_check_cookie
0x180055ede  add     rsp, 460h
0x180055ee5  pop     rbx
0x180055ee6  retn
0x180055ee7  xor     edx, edx; dwMilliseconds
0x180055ee9  call    cs:__imp_WaitForSingleObject
0x180055eef  test    eax, eax
0x180055ef1  jnz     short loc_180055EC9
0x180055ef3  xor     eax, eax
0x180055ef5  jmp     short loc_180055ECE
```
