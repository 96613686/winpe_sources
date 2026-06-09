# CSecurityAttribute::GetOwnerSid(void)

- ea: `0x140012320`
- end: `0x140012593`
- name: `?GetOwnerSid@CSecurityAttribute@@AEAAJXZ`
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
- `0x140012320`
- `0x140013490`
- `0x1400148e2`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140012360`
- `ADVAPI32!OpenProcessToken` at `0x140012360`
- `ADVAPI32!GetTokenInformation` at `0x1400123c2`
- `ADVAPI32!GetTokenInformation` at `0x14001243c`
- `ADVAPI32!GetTokenInformation` at `0x1400123c2`
- `ADVAPI32!GetTokenInformation` at `0x14001243c`
- `ADVAPI32!IsValidSid` at `0x14001248a`
- `ADVAPI32!IsValidSid` at `0x14001248a`
- `ADVAPI32!GetLengthSid` at `0x1400124bd`
- `ADVAPI32!GetLengthSid` at `0x1400124bd`
- `KERNEL32!CloseHandle` at `0x140012510`
- `KERNEL32!CloseHandle` at `0x140012510`
- `KERNEL32!LocalFree` at `0x140012580`
- `KERNEL32!LocalFree` at `0x140012580`
- `KERNEL32!GetCurrentProcess` at `0x140012350`
- `KERNEL32!GetCurrentProcess` at `0x140012350`
- `KERNEL32!GetLastError` at `0x140012371`
- `KERNEL32!GetLastError` at `0x1400123c8`
- `KERNEL32!GetLastError` at `0x1400123d8`
- `KERNEL32!GetLastError` at `0x140012446`
- `KERNEL32!GetLastError` at `0x140012494`
- `KERNEL32!GetLastError` at `0x140012371`
- `KERNEL32!GetLastError` at `0x1400123c8`
- `KERNEL32!GetLastError` at `0x1400123d8`
- `KERNEL32!GetLastError` at `0x140012446`
- `KERNEL32!GetLastError` at `0x140012494`

## string_xrefs

- `0x140012386`: `Failed: OpenProcessToken()`
- `0x1400123ed`: `Failed to get the token buffer size`
- `0x140012479`: `Failed: NULL owner sid was returned by GetTokenInformation().`
- `0x140012366`: `CSecurityAttribute::GetOwnerSid`
- `0x140012408`: `Failed to allocate memory for owner token info`
- `0x14001245b`: `Failed to get owner token`
- `0x1400124a9`: `Error: The owner sid is invalid`
- `0x1400124d6`: `Failed to allocate memory for owner sid`

## pseudocode

```c
__int64 __fastcall CSecurityAttribute::GetOwnerSid(CSecurityAttribute *this)
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

  v1 = *((_QWORD *)this + 2) == 0;
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
    v9 = 207;
LABEL_7:
    if ( v7 >= 0 )
      v7 = -2147467259;
    WusaLogDebugEventA(L"CSecurityAttribute::GetOwnerSid", v9, v8);
    goto LABEL_31;
  }
  GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &TokenInformationLength);
  TokenInformationLength = GetLastError();
  if ( TokenInformationLength != 122 )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    v8 = "Failed to get the token buffer size";
    v9 = 213;
    goto LABEL_7;
  }
  v4 = (PSID *)operator new(0x7Au);
  if ( v4 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenOwner, v4, TokenInformationLength, &TokenInformationLength) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v8 = "Failed to get owner token";
      v9 = 220;
      goto LABEL_7;
    }
    if ( !*v4 )
    {
      v7 = -2147024885;
      WusaLogDebugEventA(
        L"CSecurityAttribute::GetOwnerSid",
        224,
        "Failed: NULL owner sid was returned by GetTokenInformation().");
      goto LABEL_31;
    }
    if ( !IsValidSid(*v4) )
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      v8 = "Error: The owner sid is invalid";
      v9 = 236;
      goto LABEL_7;
    }
    TokenInformationLength = GetLengthSid(*v4);
    v13 = operator new(TokenInformationLength);
    *((_QWORD *)this + 2) = v13;
    if ( v13 )
    {
      memset_0(v13, 0, TokenInformationLength);
      memcpy_0(*((void **)this + 2), *v4, TokenInformationLength);
      v7 = 0;
      goto LABEL_31;
    }
    WusaLogDebugEventA(L"CSecurityAttribute::GetOwnerSid", 241, "Failed to allocate memory for owner sid");
  }
  else
  {
    WusaLogDebugEventA(L"CSecurityAttribute::GetOwnerSid", 217, "Failed to allocate memory for owner token info");
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
    v14 = (void *)*((_QWORD *)this + 2);
    if ( v14 )
    {
      operator delete(v14);
      *((_QWORD *)this + 2) = 0;
    }
    hMem = 0;
    WusaGetErrorMessage(v7, (unsigned __int16 **)&hMem);
    v15 = hMem;
    WusaLogDebugEventA(
      L"CSecurityAttribute::GetOwnerSid",
      253,
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
0x140012320  push    rbp
0x140012322  push    rbx
0x140012323  push    rsi
0x140012324  push    rdi
0x140012325  push    r15
0x140012327  mov     rbp, rsp
0x14001232a  sub     rsp, 30h
0x14001232e  cmp     qword ptr [rcx+10h], 0
0x140012333  mov     rsi, rcx
0x140012336  mov     [rbp+TokenHandle], 0
0x14001233e  mov     [rbp+TokenInformationLength], 0
0x140012345  jz      short loc_14001234E
0x140012347  xor     eax, eax
0x140012349  jmp     loc_140012588
0x14001234e  xor     edi, edi
0x140012350  call    cs:__imp_GetCurrentProcess
0x140012356  mov     rcx, rax; ProcessHandle
0x140012359  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001235d  lea     edx, [rdi+28h]; DesiredAccess
0x140012360  call    cs:__imp_OpenProcessToken
0x140012366  lea     r15, aCsecurityattri; "CSecurityAttribute::GetOwnerSid"
0x14001236d  test    eax, eax
0x14001236f  jnz     short loc_1400123A9
0x140012371  call    cs:__imp_GetLastError
0x140012377  mov     ebx, eax
0x140012379  test    eax, eax
0x14001237b  jle     short loc_140012386
0x14001237d  movzx   ebx, ax
0x140012380  or      ebx, 80070000h
0x140012386  lea     r8, aFailedOpenproc; "Failed: OpenProcessToken()"
0x14001238d  mov     edx, 0CFh
0x140012392  test    ebx, ebx
0x140012394  mov     eax, 80004005h
0x140012399  cmovns  ebx, eax
0x14001239c  mov     rcx, r15
0x14001239f  call    WusaLogDebugEventA
0x1400123a4  jmp     loc_140012507
0x1400123a9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400123ad  lea     rax, [rbp+TokenInformationLength]
0x1400123b1  xor     r9d, r9d; TokenInformationLength
0x1400123b4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400123b9  xor     r8d, r8d; TokenInformation
0x1400123bc  lea     ebx, [r9+4]
0x1400123c0  mov     edx, ebx; TokenInformationClass
0x1400123c2  call    cs:__imp_GetTokenInformation
0x1400123c8  call    cs:__imp_GetLastError
0x1400123ce  lea     ecx, [rbx+76h]; Size
0x1400123d1  mov     [rbp+TokenInformationLength], eax
0x1400123d4  cmp     eax, ecx
0x1400123d6  jz      short loc_1400123FB
0x1400123d8  call    cs:__imp_GetLastError
0x1400123de  mov     ebx, eax
0x1400123e0  test    eax, eax
0x1400123e2  jle     short loc_1400123ED
0x1400123e4  movzx   ebx, ax
0x1400123e7  or      ebx, 80070000h
0x1400123ed  lea     r8, aFailedToGetThe_0; "Failed to get the token buffer size"
0x1400123f4  mov     edx, 0D5h
0x1400123f9  jmp     short loc_140012392
0x1400123fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012400  mov     rdi, rax
0x140012403  test    rax, rax
0x140012406  jnz     short loc_140012426
0x140012408  lea     r8, aFailedToAlloca; "Failed to allocate memory for owner tok"...
0x14001240f  mov     edx, 0D9h
0x140012414  mov     rcx, r15
0x140012417  call    WusaLogDebugEventA
0x14001241c  mov     ebx, 8007000Eh
0x140012421  jmp     loc_140012507
0x140012426  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14001242a  lea     rax, [rbp+TokenInformationLength]
0x14001242e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140012432  mov     r8, rdi; TokenInformation
0x140012435  mov     edx, ebx; TokenInformationClass
0x140012437  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14001243c  call    cs:__imp_GetTokenInformation
0x140012442  test    eax, eax
0x140012444  jnz     short loc_14001246C
0x140012446  call    cs:__imp_GetLastError
0x14001244c  mov     ebx, eax
0x14001244e  test    eax, eax
0x140012450  jle     short loc_14001245B
0x140012452  movzx   ebx, ax
0x140012455  or      ebx, 80070000h
0x14001245b  lea     r8, aFailedToGetOwn; "Failed to get owner token"
0x140012462  mov     edx, 0DCh
0x140012467  jmp     loc_140012392
0x14001246c  mov     rcx, [rdi]; pSid
0x14001246f  test    rcx, rcx
0x140012472  jnz     short loc_14001248A
0x140012474  mov     ebx, 8007000Bh
0x140012479  lea     r8, aFailedNullOwne; "Failed: NULL owner sid was returned by "...
0x140012480  mov     edx, 0E0h
0x140012485  jmp     loc_14001239C
0x14001248a  call    cs:__imp_IsValidSid
0x140012490  test    eax, eax
0x140012492  jnz     short loc_1400124BA
0x140012494  call    cs:__imp_GetLastError
0x14001249a  mov     ebx, eax
0x14001249c  test    eax, eax
0x14001249e  jle     short loc_1400124A9
0x1400124a0  movzx   ebx, ax
0x1400124a3  or      ebx, 80070000h
0x1400124a9  lea     r8, aErrorTheOwnerS; "Error: The owner sid is invalid"
0x1400124b0  mov     edx, 0ECh
0x1400124b5  jmp     loc_140012392
0x1400124ba  mov     rcx, [rdi]; pSid
0x1400124bd  call    cs:__imp_GetLengthSid
0x1400124c3  mov     ecx, eax; Size
0x1400124c5  mov     [rbp+TokenInformationLength], ecx
0x1400124c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400124cd  mov     [rsi+10h], rax
0x1400124d1  test    rax, rax
0x1400124d4  jnz     short loc_1400124E7
0x1400124d6  lea     r8, aFailedToAlloca_5; "Failed to allocate memory for owner sid"
0x1400124dd  mov     edx, 0F1h
0x1400124e2  jmp     loc_140012414
0x1400124e7  mov     r8d, [rbp+TokenInformationLength]; Size
0x1400124eb  xor     edx, edx; Val
0x1400124ed  mov     rcx, rax; void *
0x1400124f0  call    memset_0
0x1400124f5  mov     r8d, [rbp+TokenInformationLength]; Size
0x1400124f9  mov     rdx, [rdi]; Src
0x1400124fc  mov     rcx, [rsi+10h]; void *
0x140012500  call    memcpy_0
0x140012505  xor     ebx, ebx
0x140012507  mov     rcx, [rbp+TokenHandle]; hObject
0x14001250b  test    rcx, rcx
0x14001250e  jz      short loc_14001251E
0x140012510  call    cs:__imp_CloseHandle
0x140012516  mov     [rbp+TokenHandle], 0
0x14001251e  test    rdi, rdi
0x140012521  jz      short loc_14001252B
0x140012523  mov     rcx, rdi; Block
0x140012526  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001252b  test    ebx, ebx
0x14001252d  jns     short loc_140012586
0x14001252f  mov     rcx, [rsi+10h]; Block
0x140012533  test    rcx, rcx
0x140012536  jz      short loc_140012545
0x140012538  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001253d  mov     qword ptr [rsi+10h], 0
0x140012545  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x140012549  mov     [rbp+hMem], 0
0x140012551  mov     ecx, ebx; dwMessageId
0x140012553  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140012558  mov     rdi, [rbp+hMem]
0x14001255c  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140012563  mov     r9d, ebx
0x140012566  mov     [rsp+30h+ReturnLength], rdi
0x14001256b  mov     edx, 0FDh
0x140012570  mov     rcx, r15
0x140012573  call    WusaLogDebugEventA
0x140012578  test    rdi, rdi
0x14001257b  jz      short loc_140012586
0x14001257d  mov     rcx, rdi; hMem
0x140012580  call    cs:__imp_LocalFree
0x140012586  mov     eax, ebx
0x140012588  add     rsp, 30h
0x14001258c  pop     r15
0x14001258e  pop     rdi
0x14001258f  pop     rsi
0x140012590  pop     rbx
0x140012591  pop     rbp
0x140012592  retn
```
