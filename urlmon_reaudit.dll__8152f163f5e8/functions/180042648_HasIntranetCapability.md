# HasIntranetCapability

- ea: `0x180042648`
- end: `0x180042843`
- name: `HasIntranetCapability`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040f60`

## callees

- `0x180042648`
- `0x180113e30`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004268e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042826`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004268e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042826`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042737`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800426b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800426b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427d6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800426d7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800426d7`

## string_xrefs

- `0x18004276c`: `onecoreuap\inetcore\lib\appprotocols\securitymanager.cpp`
- `0x180042806`: `onecoreuap\inetcore\lib\appprotocols\securitymanager.cpp`
- `0x180042685`: `api-ms-win-security-base-l1-2-0.dll`
- `0x1800426a6`: `CheckTokenCapability`
- `0x18004281d`: `kernel32.dll`

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
0x180042648  mov     [rsp+arg_8], rbx
0x18004264d  mov     [rsp+arg_10], rsi
0x180042652  push    rdi
0x180042653  sub     rsp, 90h
0x18004265a  mov     rax, cs:__security_cookie
0x180042661  xor     rax, rsp
0x180042664  mov     [rsp+98h+var_18], rax
0x18004266c  mov     rsi, rcx
0x18004266f  mov     dword ptr [rcx], 0
0x180042675  mov     ebx, 800h
0x18004267a  mov     [rsp+98h+cbSid], 44h ; 'D'; int
0x180042682  mov     r8d, ebx; dwFlags
0x180042685  lea     rcx, aApiMsWinSecuri_3; "api-ms-win-security-base-l1-2-0.dll"
0x18004268c  xor     edx, edx; hFile
0x18004268e  call    cs:__imp_LoadLibraryExW
0x180042695  nop     dword ptr [rax+rax+00h]
0x18004269a  mov     rdi, rax
0x18004269d  test    rax, rax
0x1800426a0  jz      loc_18004281A
0x1800426a6  lea     rdx, aChecktokencapa; "CheckTokenCapability"
0x1800426ad  mov     rcx, rdi; hModule
0x1800426b0  call    cs:__imp_GetProcAddress
0x1800426b7  nop     dword ptr [rax+rax+00h]
0x1800426bc  mov     rbx, rax
0x1800426bf  test    rax, rax
0x1800426c2  jz      loc_180042782
0x1800426c8  xor     edx, edx; DomainSid
0x1800426ca  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800426cf  lea     r8, [rsp+98h+pSid]; pSid
0x1800426d4  lea     ecx, [rdx+57h]; WellKnownSidType
0x1800426d7  call    cs:__imp_CreateWellKnownSid
0x1800426de  nop     dword ptr [rax+rax+00h]
0x1800426e3  test    eax, eax
0x1800426e5  jz      loc_1800427AC
0x1800426eb  mov     r8, rsi
0x1800426ee  lea     rdx, [rsp+98h+pSid]
0x1800426f3  xor     ecx, ecx
0x1800426f5  mov     rax, rbx
0x1800426f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426fd  test    eax, eax
0x1800426ff  jz      loc_1800427D6
0x180042705  xor     ebx, ebx
0x180042707  test    rdi, rdi
0x18004270a  jnz     short loc_180042734
0x18004270c  mov     eax, ebx
0x18004270e  mov     rcx, [rsp+98h+var_18]
0x180042716  xor     rcx, rsp; StackCookie
0x180042719  call    __security_check_cookie
0x18004271e  lea     r11, [rsp+98h+var_8]
0x180042726  mov     rbx, [r11+18h]
0x18004272a  mov     rsi, [r11+20h]
0x18004272e  mov     rsp, r11
0x180042731  pop     rdi
0x180042732  retn
0x180042734  mov     rcx, rdi; hLibModule
0x180042737  call    cs:__imp_FreeLibrary
0x18004273e  nop     dword ptr [rax+rax+00h]
0x180042743  jmp     short loc_18004270C
0x180042745  call    cs:__imp_GetLastError
0x18004274c  nop     dword ptr [rax+rax+00h]
0x180042751  mov     ebx, eax
0x180042753  test    eax, eax
0x180042755  jle     short loc_180042760
0x180042757  movzx   ebx, ax
0x18004275a  or      ebx, 80070000h
0x180042760  test    ebx, ebx
0x180042762  jns     short loc_18004270C
0x180042764  mov     rcx, [rsp+98h]; this
0x18004276c  lea     r8, aOnecoreuapInet_30; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x180042773  mov     r9d, ebx; char *
0x180042776  mov     edx, 42h ; 'B'; void *
0x18004277b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042780  jmp     short loc_18004270C
0x180042782  call    cs:__imp_GetLastError
0x180042789  nop     dword ptr [rax+rax+00h]
0x18004278e  mov     ebx, eax
0x180042790  test    eax, eax
0x180042792  jle     short loc_18004279D
0x180042794  movzx   ebx, ax
0x180042797  or      ebx, 80070000h
0x18004279d  test    ebx, ebx
0x18004279f  jns     loc_180042707
0x1800427a5  mov     edx, 47h ; 'G'
0x1800427aa  jmp     short loc_1800427FE
0x1800427ac  call    cs:__imp_GetLastError
0x1800427b3  nop     dword ptr [rax+rax+00h]
0x1800427b8  mov     ebx, eax
0x1800427ba  test    eax, eax
0x1800427bc  jle     short loc_1800427C7
0x1800427be  movzx   ebx, ax
0x1800427c1  or      ebx, 80070000h
0x1800427c7  test    ebx, ebx
0x1800427c9  jns     loc_180042707
0x1800427cf  mov     edx, 4Eh ; 'N'
0x1800427d4  jmp     short loc_1800427FE
0x1800427d6  call    cs:__imp_GetLastError
0x1800427dd  nop     dword ptr [rax+rax+00h]
0x1800427e2  mov     ebx, eax
0x1800427e4  test    eax, eax
0x1800427e6  jle     short loc_1800427F1
0x1800427e8  movzx   ebx, ax
0x1800427eb  or      ebx, 80070000h
0x1800427f1  test    ebx, ebx
0x1800427f3  jns     loc_180042707
0x1800427f9  mov     edx, 54h ; 'T'; void *
0x1800427fe  mov     rcx, [rsp+98h]; this
0x180042806  lea     r8, aOnecoreuapInet_30; "onecoreuap\\inetcore\\lib\\appprotocols"...
0x18004280d  mov     r9d, ebx; char *
0x180042810  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042815  jmp     loc_180042707
0x18004281a  mov     r8d, ebx; dwFlags
0x18004281d  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180042824  xor     edx, edx; hFile
0x180042826  call    cs:__imp_LoadLibraryExW
0x18004282d  nop     dword ptr [rax+rax+00h]
0x180042832  mov     rdi, rax
0x180042835  test    rax, rax
0x180042838  jnz     loc_1800426A6
0x18004283e  jmp     loc_180042745
```
