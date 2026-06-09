# Windows::UI::Core::WindowServer::GetProcessAppContainerSid(ulong,_TOKEN_APPCONTAINER_INFORMATION * *)

- ea: `0x180005798`
- end: `0x180005a41`
- name: `?GetProcessAppContainerSid@WindowServer@Core@UI@Windows@@QEAAJKPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z`
- size: `681`
- prototype: `int(Windows::UI::Core::WindowServer *__hidden this, unsigned int, struct _TOKEN_APPCONTAINER_INFORMATION **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005580`

## callees

- `0x180005798`
- `0x180012858`
- `0x1800582ac`
- `0x180060a08`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058cc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005825`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800057e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800057e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057bf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005913`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057bf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005913`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000581b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005874`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000581b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005874`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::GetProcessAppContainerSid(
        Windows::UI::Core::WindowServer *this,
        DWORD a2,
        struct _TOKEN_APPCONTAINER_INFORMATION **a3)
{
  HANDLE v5; // rdi
  unsigned int Error; // ebx
  DWORD v7; // ebx
  unsigned __int64 v8; // rcx
  struct _TOKEN_APPCONTAINER_INFORMATION *v9; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  Windows::UI::Core::WindowServer *TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = this;
  *a3 = 0;
  v5 = OpenProcess(0x400u, 0, a2);
  if ( v5 || (v5 = OpenProcess(0x1000u, 0, a2)) != 0 )
  {
    TokenHandle = 0;
    if ( !OpenProcessToken(v5, 0x18u, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, Error);
      }
      goto LABEL_11;
    }
    LODWORD(TokenInformationLength) = 0;
    Error = -2147418113;
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, (PDWORD)&TokenInformationLength) )
    {
      if ( GetLastError() != 122 )
      {
        Error = ResultFromKnownLastError();
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_10;
        }
        v12 = 42;
        goto LABEL_29;
      }
      v7 = (unsigned int)TokenInformationLength;
      v8 = (unsigned int)TokenInformationLength;
      LODWORD(TokenInformationLength) = 0;
      v9 = (struct _TOKEN_APPCONTAINER_INFORMATION *)operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
      *a3 = v9;
      if ( v9 )
      {
        if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v9, v7, (PDWORD)&TokenInformationLength) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, a2);
          }
          Error = 0;
          goto LABEL_10;
        }
        operator delete[](*a3);
        *a3 = 0;
        Error = ResultFromKnownLastError();
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v12 = 41;
LABEL_29:
          WPP_SF_d(v11[2], v12, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, Error);
        }
      }
      else
      {
        Error = -2147024882;
      }
    }
LABEL_10:
    CloseHandle(TokenHandle);
    TokenHandle = 0;
LABEL_11:
    CloseHandle(v5);
    return Error;
  }
  Error = ResultFromKnownLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, Error);
  }
  return Error;
}

```

## disassembly

```asm
0x180005798  mov     [rsp+arg_8], rbx
0x18000579d  mov     [rsp+TokenInformationLength], rcx
0x1800057a2  push    rbp
0x1800057a3  push    rsi
0x1800057a4  push    rdi
0x1800057a5  sub     rsp, 30h
0x1800057a9  mov     rsi, r8
0x1800057ac  mov     qword ptr [r8], 0
0x1800057b3  mov     r8d, edx; dwProcessId
0x1800057b6  mov     ebp, edx
0x1800057b8  xor     edx, edx; bInheritHandle
0x1800057ba  mov     ecx, 400h; dwDesiredAccess
0x1800057bf  call    cs:__imp_OpenProcess
0x1800057c5  mov     rdi, rax
0x1800057c8  test    rax, rax
0x1800057cb  jz      loc_180005909
0x1800057d1  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800057d6  mov     [rsp+48h+TokenHandle], 0
0x1800057df  mov     edx, 18h; DesiredAccess
0x1800057e4  mov     rcx, rdi; ProcessHandle
0x1800057e7  call    cs:__imp_OpenProcessToken
0x1800057ed  test    eax, eax
0x1800057ef  jz      loc_1800059F2
0x1800057f5  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800057fa  lea     rax, [rsp+48h+TokenInformationLength]
0x1800057ff  xor     r9d, r9d; TokenInformationLength
0x180005802  mov     dword ptr [rsp+48h+TokenInformationLength], 0
0x18000580a  xor     r8d, r8d; TokenInformation
0x18000580d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005812  mov     ebx, 8000FFFFh
0x180005817  lea     edx, [r9+1Fh]; TokenInformationClass
0x18000581b  call    cs:__imp_GetTokenInformation
0x180005821  test    eax, eax
0x180005823  jnz     short loc_18000589D
0x180005825  call    cs:__imp_GetLastError
0x18000582b  cmp     eax, 7Ah ; 'z'
0x18000582e  jnz     loc_1800059A3
0x180005834  mov     ebx, dword ptr [rsp+48h+TokenInformationLength]
0x180005838  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000583f  mov     ecx, ebx; unsigned __int64
0x180005841  mov     dword ptr [rsp+48h+TokenInformationLength], 0
0x180005849  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000584e  mov     [rsi], rax
0x180005851  test    rax, rax
0x180005854  jz      loc_180005972
0x18000585a  lea     rcx, [rsp+48h+TokenInformationLength]
0x18000585f  mov     r9d, ebx; TokenInformationLength
0x180005862  mov     [rsp+48h+ReturnLength], rcx; ReturnLength
0x180005867  mov     r8, rax; TokenInformation
0x18000586a  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000586f  mov     edx, 1Fh; TokenInformationClass
0x180005874  call    cs:__imp_GetTokenInformation
0x18000587a  test    eax, eax
0x18000587c  jz      short loc_1800058C9
0x18000587e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005885  lea     rax, WPP_GLOBAL_Control
0x18000588c  cmp     rcx, rax
0x18000588f  jz      short loc_18000589B
0x180005891  test    byte ptr [rcx+1Ch], 2
0x180005895  jnz     loc_18000597C
0x18000589b  xor     ebx, ebx
0x18000589d  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800058a2  call    cs:__imp_CloseHandle
0x1800058a8  mov     [rsp+48h+TokenHandle], 0
0x1800058b1  mov     rcx, rdi; hObject
0x1800058b4  call    cs:__imp_CloseHandle
0x1800058ba  mov     eax, ebx
0x1800058bc  mov     rbx, [rsp+48h+arg_8]
0x1800058c1  add     rsp, 30h
0x1800058c5  pop     rdi
0x1800058c6  pop     rsi
0x1800058c7  pop     rbp
0x1800058c8  retn
0x1800058c9  mov     rcx, [rsi]
0x1800058cc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800058d2  mov     qword ptr [rsi], 0
0x1800058d9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800058de  mov     ebx, eax
0x1800058e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058e7  lea     rax, WPP_GLOBAL_Control
0x1800058ee  cmp     rcx, rax
0x1800058f1  jz      short loc_18000589D
0x1800058f3  test    byte ptr [rcx+1Ch], 2
0x1800058f7  jz      short loc_18000589D
0x1800058f9  cmp     byte ptr [rcx+19h], 4
0x1800058fd  jb      short loc_18000589D
0x1800058ff  mov     edx, 29h ; ')'
0x180005904  jmp     loc_1800059DA
0x180005909  mov     r8d, ebp; dwProcessId
0x18000590c  xor     edx, edx; bInheritHandle
0x18000590e  mov     ecx, 1000h; dwDesiredAccess
0x180005913  call    cs:__imp_OpenProcess
0x180005919  mov     rdi, rax
0x18000591c  test    rax, rax
0x18000591f  jnz     loc_1800057D1
0x180005925  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000592a  mov     ebx, eax
0x18000592c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005933  lea     rax, WPP_GLOBAL_Control
0x18000593a  cmp     rcx, rax
0x18000593d  jz      loc_1800058BA
0x180005943  test    byte ptr [rcx+1Ch], 2
0x180005947  jz      loc_1800058BA
0x18000594d  cmp     byte ptr [rcx+19h], 4
0x180005951  jb      loc_1800058BA
0x180005957  mov     rcx, [rcx+10h]
0x18000595b  lea     edx, [rdi+2Ch]
0x18000595e  mov     r9d, ebx
0x180005961  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x180005968  call    WPP_SF_d
0x18000596d  jmp     loc_1800058BA
0x180005972  mov     ebx, 8007000Eh
0x180005977  jmp     loc_18000589D
0x18000597c  cmp     byte ptr [rcx+19h], 4
0x180005980  jb      loc_18000589B
0x180005986  mov     rcx, [rcx+10h]
0x18000598a  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x180005991  mov     edx, 28h ; '('
0x180005996  mov     r9d, ebp
0x180005999  call    WPP_SF_d
0x18000599e  jmp     loc_18000589B
0x1800059a3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800059a8  mov     ebx, eax
0x1800059aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b1  lea     rax, WPP_GLOBAL_Control
0x1800059b8  cmp     rcx, rax
0x1800059bb  jz      loc_18000589D
0x1800059c1  test    byte ptr [rcx+1Ch], 2
0x1800059c5  jz      loc_18000589D
0x1800059cb  cmp     byte ptr [rcx+19h], 4
0x1800059cf  jb      loc_18000589D
0x1800059d5  mov     edx, 2Ah ; '*'
0x1800059da  mov     rcx, [rcx+10h]
0x1800059de  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x1800059e5  mov     r9d, ebx
0x1800059e8  call    WPP_SF_d
0x1800059ed  jmp     loc_18000589D
0x1800059f2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800059f7  mov     ebx, eax
0x1800059f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a00  lea     rax, WPP_GLOBAL_Control
0x180005a07  cmp     rcx, rax
0x180005a0a  jz      loc_1800058B1
0x180005a10  test    byte ptr [rcx+1Ch], 2
0x180005a14  jz      loc_1800058B1
0x180005a1a  cmp     byte ptr [rcx+19h], 4
0x180005a1e  jb      loc_1800058B1
0x180005a24  mov     rcx, [rcx+10h]
0x180005a28  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x180005a2f  mov     edx, 2Bh ; '+'
0x180005a34  mov     r9d, ebx
0x180005a37  call    WPP_SF_d
0x180005a3c  jmp     loc_1800058B1
```
