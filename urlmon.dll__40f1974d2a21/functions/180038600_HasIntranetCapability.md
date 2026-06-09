# HasIntranetCapability

- ea: `0x180038600`
- end: `0x1800387c4`
- name: `HasIntranetCapability`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180037060`

## callees

- `0x180038600`
- `0x180108820`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038646`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800387ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038646`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800387ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800386dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800386dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038662`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003873f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003873f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038763`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038683`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038683`

## string_xrefs

- `0x180038705`: `onecoreuap\inetcore\lib\appprotocols\securitymanager.cpp`
- `0x18003878d`: `onecoreuap\inetcore\lib\appprotocols\securitymanager.cpp`
- `0x18003863d`: `api-ms-win-security-base-l1-2-0.dll`
- `0x180038658`: `CheckTokenCapability`
- `0x1800387a4`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall HasIntranetCapability(_DWORD *a1)
{
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rbx
  signed int v4; // ebx
  signed int v6; // eax
  signed int v7; // eax
  __int64 v8; // rdx
  signed int v9; // eax
  signed int LastError; // eax
  DWORD cbSid[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *a1 = 0;
  cbSid[0] = 68;
  Library = LoadLibraryExW(L"api-ms-win-security-base-l1-2-0.dll", 0, 0x800u);
  if ( Library || (Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u)) != 0 )
  {
    ProcAddress = GetProcAddress(Library, "CheckTokenCapability");
    if ( ProcAddress )
    {
      if ( CreateWellKnownSid(WinCapabilityPrivateNetworkClientServerSid, 0, pSid, cbSid) )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, _BYTE *, _DWORD *))ProcAddress)(0, pSid, a1) )
        {
          v4 = 0;
LABEL_6:
          FreeLibrary(Library);
          return (unsigned int)v4;
        }
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          goto LABEL_6;
        v8 = 84;
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        if ( v4 >= 0 )
          goto LABEL_6;
        v8 = 78;
      }
    }
    else
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_6;
      v8 = 71;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\securitymanager.cpp",
      (const char *)(unsigned int)v4,
      cbSid[0]);
    goto LABEL_6;
  }
  v6 = GetLastError();
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\inetcore\\lib\\appprotocols\\securitymanager.cpp",
      (const char *)(unsigned int)v4,
      cbSid[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038600  mov     [rsp+arg_8], rbx
0x180038605  mov     [rsp+arg_10], rsi
0x18003860a  push    rdi
0x18003860b  sub     rsp, 90h
0x180038612  mov     rax, cs:__security_cookie
0x180038619  xor     rax, rsp
0x18003861c  mov     [rsp+98h+var_18], rax
0x180038624  mov     rsi, rcx
0x180038627  mov     dword ptr [rcx], 0
0x18003862d  mov     ebx, 800h
0x180038632  mov     [rsp+98h+cbSid], 44h ; 'D'; int
0x18003863a  mov     r8d, ebx; dwFlags
0x18003863d  lea     rcx, aApiMsWinSecuri_3; "api-ms-win-security-base-l1-2-0.dll"
0x180038644  xor     edx, edx; hFile
0x180038646  call    cs:__imp_LoadLibraryExW
0x18003864c  mov     rdi, rax
0x18003864f  test    rax, rax
0x180038652  jz      loc_1800387A1
0x180038658  lea     rdx, aChecktokencapa; "CheckTokenCapability"
0x18003865f  mov     rcx, rdi; hModule
0x180038662  call    cs:__imp_GetProcAddress
0x180038668  mov     rbx, rax
0x18003866b  test    rax, rax
0x18003866e  jz      loc_18003871B
0x180038674  xor     edx, edx; DomainSid
0x180038676  lea     r9, [rsp+98h+cbSid]; cbSid
0x18003867b  lea     r8, [rsp+98h+pSid]; pSid
0x180038680  lea     ecx, [rdx+57h]; WellKnownSidType
0x180038683  call    cs:__imp_CreateWellKnownSid
0x180038689  test    eax, eax
0x18003868b  jz      loc_18003873F
0x180038691  mov     r8, rsi
0x180038694  lea     rdx, [rsp+98h+pSid]
0x180038699  xor     ecx, ecx
0x18003869b  mov     rax, rbx
0x18003869e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a3  test    eax, eax
0x1800386a5  jz      loc_180038763
0x1800386ab  xor     ebx, ebx
0x1800386ad  test    rdi, rdi
0x1800386b0  jnz     short loc_1800386D9
0x1800386b2  mov     eax, ebx
0x1800386b4  mov     rcx, [rsp+98h+var_18]
0x1800386bc  xor     rcx, rsp; StackCookie
0x1800386bf  call    __security_check_cookie
0x1800386c4  lea     r11, [rsp+98h+var_8]
0x1800386cc  mov     rbx, [r11+18h]
0x1800386d0  mov     rsi, [r11+20h]
0x1800386d4  mov     rsp, r11
0x1800386d7  pop     rdi
0x1800386d8  retn
0x1800386d9  mov     rcx, rdi; hLibModule
0x1800386dc  call    cs:__imp_FreeLibrary
0x1800386e2  jmp     short loc_1800386B2
0x1800386e4  call    cs:__imp_GetLastError
0x1800386ea  mov     ebx, eax
0x1800386ec  test    eax, eax
0x1800386ee  jle     short loc_1800386F9
0x1800386f0  movzx   ebx, ax
0x1800386f3  or      ebx, 80070000h
0x1800386f9  test    ebx, ebx
0x1800386fb  jns     short loc_1800386B2
0x1800386fd  mov     rcx, [rsp+98h]; this
0x180038705  lea     r8, aOnecoreuapInet_30; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x18003870c  mov     r9d, ebx; char *
0x18003870f  mov     edx, 42h ; 'B'; void *
0x180038714  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038719  jmp     short loc_1800386B2
0x18003871b  call    cs:__imp_GetLastError
0x180038721  mov     ebx, eax
0x180038723  test    eax, eax
0x180038725  jle     short loc_180038730
0x180038727  movzx   ebx, ax
0x18003872a  or      ebx, 80070000h
0x180038730  test    ebx, ebx
0x180038732  jns     loc_1800386AD
0x180038738  mov     edx, 47h ; 'G'
0x18003873d  jmp     short loc_180038785
0x18003873f  call    cs:__imp_GetLastError
0x180038745  mov     ebx, eax
0x180038747  test    eax, eax
0x180038749  jle     short loc_180038754
0x18003874b  movzx   ebx, ax
0x18003874e  or      ebx, 80070000h
0x180038754  test    ebx, ebx
0x180038756  jns     loc_1800386AD
0x18003875c  mov     edx, 4Eh ; 'N'
0x180038761  jmp     short loc_180038785
0x180038763  call    cs:__imp_GetLastError
0x180038769  mov     ebx, eax
0x18003876b  test    eax, eax
0x18003876d  jle     short loc_180038778
0x18003876f  movzx   ebx, ax
0x180038772  or      ebx, 80070000h
0x180038778  test    ebx, ebx
0x18003877a  jns     loc_1800386AD
0x180038780  mov     edx, 54h ; 'T'; void *
0x180038785  mov     rcx, [rsp+98h]; this
0x18003878d  lea     r8, aOnecoreuapInet_30; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180038794  mov     r9d, ebx; char *
0x180038797  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003879c  jmp     loc_1800386AD
0x1800387a1  mov     r8d, ebx; dwFlags
0x1800387a4  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800387ab  xor     edx, edx; hFile
0x1800387ad  call    cs:__imp_LoadLibraryExW
0x1800387b3  mov     rdi, rax
0x1800387b6  test    rax, rax
0x1800387b9  jnz     loc_180038658
0x1800387bf  jmp     loc_1800386E4
```
