# CSecurityAttribute::GetUserSid(void)

- ea: `0x14001259c`
- end: `0x14001280f`
- name: `?GetUserSid@CSecurityAttribute@@AEAAJXZ`
- size: `627`
- prototype: `__int64 __fastcall(CSecurityAttribute *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140012818`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x14000e280`
- `0x14001259c`
- `0x140013490`
- `0x1400148e2`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1400125dc`
- `ADVAPI32!OpenProcessToken` at `0x1400125dc`
- `ADVAPI32!GetTokenInformation` at `0x14001263e`
- `ADVAPI32!GetTokenInformation` at `0x1400126b8`
- `ADVAPI32!GetTokenInformation` at `0x14001263e`
- `ADVAPI32!GetTokenInformation` at `0x1400126b8`
- `ADVAPI32!IsValidSid` at `0x140012706`
- `ADVAPI32!IsValidSid` at `0x140012706`
- `ADVAPI32!GetLengthSid` at `0x140012739`
- `ADVAPI32!GetLengthSid` at `0x140012739`
- `KERNEL32!CloseHandle` at `0x14001278c`
- `KERNEL32!CloseHandle` at `0x14001278c`
- `KERNEL32!LocalFree` at `0x1400127fc`
- `KERNEL32!LocalFree` at `0x1400127fc`
- `KERNEL32!GetCurrentProcess` at `0x1400125cc`
- `KERNEL32!GetCurrentProcess` at `0x1400125cc`
- `KERNEL32!GetLastError` at `0x1400125ed`
- `KERNEL32!GetLastError` at `0x140012644`
- `KERNEL32!GetLastError` at `0x140012654`
- `KERNEL32!GetLastError` at `0x1400126c2`
- `KERNEL32!GetLastError` at `0x140012710`
- `KERNEL32!GetLastError` at `0x1400125ed`
- `KERNEL32!GetLastError` at `0x140012644`
- `KERNEL32!GetLastError` at `0x140012654`
- `KERNEL32!GetLastError` at `0x1400126c2`
- `KERNEL32!GetLastError` at `0x140012710`

## string_xrefs

- `0x140012602`: `Failed: OpenProcessToken()`
- `0x1400125e2`: `CSecurityAttribute::GetUserSid`
- `0x140012669`: `Failed to get the token buffer size`
- `0x140012684`: `Failed to allocate memory for user token info`
- `0x1400126d7`: `Failed to get user token`
- `0x1400126f5`: `Failed: NULL owner sid was returned by GetTokenInformation().`
- `0x140012725`: `Error: The user sid is invalid`
- `0x140012752`: `Failed to allocate memory for user sid`

## pseudocode

```c
__int64 __fastcall CSecurityAttribute::GetUserSid(CSecurityAttribute *this)
{
  bool v1; // zf
  PSID *v4; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  const char *v8; // r8
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  void *v13; // rax
  void *v14; // rcx
  HLOCAL v15; // rdi
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+40h] BYREF

  v1 = *((_QWORD *)this + 3) == 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !v1 )
    return 0;
  v4 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = "Failed: OpenProcessToken()";
    v9 = 146;
LABEL_7:
    if ( v7 >= 0 )
      v7 = -2147467259;
    WusaLogDebugEventA(L"CSecurityAttribute::GetUserSid", v9, v8);
    goto LABEL_31;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  TokenInformationLength = GetLastError();
  if ( TokenInformationLength != 122 )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    v8 = "Failed to get the token buffer size";
    v9 = 153;
    goto LABEL_7;
  }
  v4 = (PSID *)operator new(0x7Au);
  if ( v4 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v8 = "Failed to get user token";
      v9 = 160;
      goto LABEL_7;
    }
    if ( !*v4 )
    {
      v7 = -2147024885;
      WusaLogDebugEventA(
        L"CSecurityAttribute::GetUserSid",
        164,
        "Failed: NULL owner sid was returned by GetTokenInformation().");
      goto LABEL_31;
    }
    if ( !IsValidSid(*v4) )
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      v8 = "Error: The user sid is invalid";
      v9 = 168;
      goto LABEL_7;
    }
    TokenInformationLength = GetLengthSid(*v4);
    v13 = operator new(TokenInformationLength);
    *((_QWORD *)this + 3) = v13;
    if ( v13 )
    {
      memset_0(v13, 0, TokenInformationLength);
      memcpy_0(*((void **)this + 3), *v4, TokenInformationLength);
      v7 = 0;
      goto LABEL_31;
    }
    WusaLogDebugEventA(L"CSecurityAttribute::GetUserSid", 174, "Failed to allocate memory for user sid");
  }
  else
  {
    WusaLogDebugEventA(L"CSecurityAttribute::GetUserSid", 157, "Failed to allocate memory for user token info");
  }
  v7 = -2147024882;
LABEL_31:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v4 )
    operator delete(v4);
  if ( v7 < 0 )
  {
    v14 = (void *)*((_QWORD *)this + 3);
    if ( v14 )
    {
      operator delete(v14);
      *((_QWORD *)this + 3) = 0;
    }
    hMem = 0;
    WusaGetErrorMessage(v7, (unsigned __int16 **)&hMem);
    v15 = hMem;
    WusaLogDebugEventA(
      L"CSecurityAttribute::GetUserSid",
      187,
      "Exit with error code 0X%x (%ls)",
      v7,
      (const wchar_t *)hMem);
    if ( v15 )
      LocalFree(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001259c  push    rbp
0x14001259e  push    rbx
0x14001259f  push    rsi
0x1400125a0  push    rdi
0x1400125a1  push    r15
0x1400125a3  mov     rbp, rsp
0x1400125a6  sub     rsp, 30h
0x1400125aa  cmp     qword ptr [rcx+18h], 0
0x1400125af  mov     rsi, rcx
0x1400125b2  mov     [rbp+TokenHandle], 0
0x1400125ba  mov     [rbp+TokenInformationLength], 0
0x1400125c1  jz      short loc_1400125CA
0x1400125c3  xor     eax, eax
0x1400125c5  jmp     loc_140012804
0x1400125ca  xor     edi, edi
0x1400125cc  call    cs:__imp_GetCurrentProcess
0x1400125d2  mov     rcx, rax; ProcessHandle
0x1400125d5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400125d9  lea     edx, [rdi+28h]; DesiredAccess
0x1400125dc  call    cs:__imp_OpenProcessToken
0x1400125e2  lea     r15, aCsecurityattri_2; "CSecurityAttribute::GetUserSid"
0x1400125e9  test    eax, eax
0x1400125eb  jnz     short loc_140012625
0x1400125ed  call    cs:__imp_GetLastError
0x1400125f3  mov     ebx, eax
0x1400125f5  test    eax, eax
0x1400125f7  jle     short loc_140012602
0x1400125f9  movzx   ebx, ax
0x1400125fc  or      ebx, 80070000h
0x140012602  lea     r8, aFailedOpenproc; "Failed: OpenProcessToken()"
0x140012609  mov     edx, 92h
0x14001260e  test    ebx, ebx
0x140012610  mov     eax, 80004005h
0x140012615  cmovns  ebx, eax
0x140012618  mov     rcx, r15
0x14001261b  call    WusaLogDebugEventA
0x140012620  jmp     loc_140012783
0x140012625  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140012629  lea     rax, [rbp+TokenInformationLength]
0x14001262d  xor     r9d, r9d; TokenInformationLength
0x140012630  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140012635  xor     r8d, r8d; TokenInformation
0x140012638  lea     ebx, [r9+1]
0x14001263c  mov     edx, ebx; TokenInformationClass
0x14001263e  call    cs:__imp_GetTokenInformation
0x140012644  call    cs:__imp_GetLastError
0x14001264a  lea     ecx, [rbx+79h]; Size
0x14001264d  mov     [rbp+TokenInformationLength], eax
0x140012650  cmp     eax, ecx
0x140012652  jz      short loc_140012677
0x140012654  call    cs:__imp_GetLastError
0x14001265a  mov     ebx, eax
0x14001265c  test    eax, eax
0x14001265e  jle     short loc_140012669
0x140012660  movzx   ebx, ax
0x140012663  or      ebx, 80070000h
0x140012669  lea     r8, aFailedToGetThe_0; "Failed to get the token buffer size"
0x140012670  mov     edx, 99h
0x140012675  jmp     short loc_14001260E
0x140012677  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001267c  mov     rdi, rax
0x14001267f  test    rax, rax
0x140012682  jnz     short loc_1400126A2
0x140012684  lea     r8, aFailedToAlloca_23; "Failed to allocate memory for user toke"...
0x14001268b  mov     edx, 9Dh
0x140012690  mov     rcx, r15
0x140012693  call    WusaLogDebugEventA
0x140012698  mov     ebx, 8007000Eh
0x14001269d  jmp     loc_140012783
0x1400126a2  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400126a6  lea     rax, [rbp+TokenInformationLength]
0x1400126aa  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400126ae  mov     r8, rdi; TokenInformation
0x1400126b1  mov     edx, ebx; TokenInformationClass
0x1400126b3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400126b8  call    cs:__imp_GetTokenInformation
0x1400126be  test    eax, eax
0x1400126c0  jnz     short loc_1400126E8
0x1400126c2  call    cs:__imp_GetLastError
0x1400126c8  mov     ebx, eax
0x1400126ca  test    eax, eax
0x1400126cc  jle     short loc_1400126D7
0x1400126ce  movzx   ebx, ax
0x1400126d1  or      ebx, 80070000h
0x1400126d7  lea     r8, aFailedToGetUse_0; "Failed to get user token"
0x1400126de  mov     edx, 0A0h
0x1400126e3  jmp     loc_14001260E
0x1400126e8  mov     rcx, [rdi]; pSid
0x1400126eb  test    rcx, rcx
0x1400126ee  jnz     short loc_140012706
0x1400126f0  mov     ebx, 8007000Bh
0x1400126f5  lea     r8, aFailedNullOwne; "Failed: NULL owner sid was returned by "...
0x1400126fc  mov     edx, 0A4h
0x140012701  jmp     loc_140012618
0x140012706  call    cs:__imp_IsValidSid
0x14001270c  test    eax, eax
0x14001270e  jnz     short loc_140012736
0x140012710  call    cs:__imp_GetLastError
0x140012716  mov     ebx, eax
0x140012718  test    eax, eax
0x14001271a  jle     short loc_140012725
0x14001271c  movzx   ebx, ax
0x14001271f  or      ebx, 80070000h
0x140012725  lea     r8, aErrorTheUserSi; "Error: The user sid is invalid"
0x14001272c  mov     edx, 0A8h
0x140012731  jmp     loc_14001260E
0x140012736  mov     rcx, [rdi]; pSid
0x140012739  call    cs:__imp_GetLengthSid
0x14001273f  mov     ecx, eax; Size
0x140012741  mov     [rbp+TokenInformationLength], ecx
0x140012744  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012749  mov     [rsi+18h], rax
0x14001274d  test    rax, rax
0x140012750  jnz     short loc_140012763
0x140012752  lea     r8, aFailedToAlloca_22; "Failed to allocate memory for user sid"
0x140012759  mov     edx, 0AEh
0x14001275e  jmp     loc_140012690
0x140012763  mov     r8d, [rbp+TokenInformationLength]; Size
0x140012767  xor     edx, edx; Val
0x140012769  mov     rcx, rax; void *
0x14001276c  call    memset_0
0x140012771  mov     r8d, [rbp+TokenInformationLength]; Size
0x140012775  mov     rdx, [rdi]; Src
0x140012778  mov     rcx, [rsi+18h]; void *
0x14001277c  call    memcpy_0
0x140012781  xor     ebx, ebx
0x140012783  mov     rcx, [rbp+TokenHandle]; hObject
0x140012787  test    rcx, rcx
0x14001278a  jz      short loc_14001279A
0x14001278c  call    cs:__imp_CloseHandle
0x140012792  mov     [rbp+TokenHandle], 0
0x14001279a  test    rdi, rdi
0x14001279d  jz      short loc_1400127A7
0x14001279f  mov     rcx, rdi; Block
0x1400127a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400127a7  test    ebx, ebx
0x1400127a9  jns     short loc_140012802
0x1400127ab  mov     rcx, [rsi+18h]; Block
0x1400127af  test    rcx, rcx
0x1400127b2  jz      short loc_1400127C1
0x1400127b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400127b9  mov     qword ptr [rsi+18h], 0
0x1400127c1  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x1400127c5  mov     [rbp+hMem], 0
0x1400127cd  mov     ecx, ebx; dwMessageId
0x1400127cf  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x1400127d4  mov     rdi, [rbp+hMem]
0x1400127d8  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x1400127df  mov     r9d, ebx
0x1400127e2  mov     [rsp+30h+ReturnLength], rdi
0x1400127e7  mov     edx, 0BBh
0x1400127ec  mov     rcx, r15
0x1400127ef  call    WusaLogDebugEventA
0x1400127f4  test    rdi, rdi
0x1400127f7  jz      short loc_140012802
0x1400127f9  mov     rcx, rdi; hMem
0x1400127fc  call    cs:__imp_LocalFree
0x140012802  mov     eax, ebx
0x140012804  add     rsp, 30h
0x140012808  pop     r15
0x14001280a  pop     rdi
0x14001280b  pop     rsi
0x14001280c  pop     rbx
0x14001280d  pop     rbp
0x14001280e  retn
```
