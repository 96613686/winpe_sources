# User::FromImpersonationToken(User &,void *)

- ea: `0x18001a8f4`
- end: `0x18001acbb`
- name: `?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z`
- size: `967`
- prototype: `__int64 __fastcall(struct User *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b218`

## callees

- `0x180003600`
- `0x180005094`
- `0x1800050d0`
- `0x1800053bc`
- `0x180007988`
- `0x180007994`
- `0x180008c4c`
- `0x180010570`
- `0x1800181ec`
- `0x180019f10`
- `0x18001a8f4`

## import_xrefs

- `msvcrt!wcschr` at `0x18001abed`
- `msvcrt!wcschr` at `0x18001abed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a93d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a93d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a91d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a91d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a99b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aa7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a99b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aa7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abb5`
- `SspiCli!GetUserNameExW` at `0x18001aac9`
- `SspiCli!GetUserNameExW` at `0x18001aba5`
- `SspiCli!GetUserNameExW` at `0x18001aac9`
- `SspiCli!GetUserNameExW` at `0x18001aba5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall User::FromImpersonationToken(struct User *a1, void *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v6; // rbx
  signed int v7; // eax
  _QWORD *v8; // rbx
  signed int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r14
  ULONG v12; // eax
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  signed int v15; // eax
  unsigned int v16; // esi
  wchar_t *v17; // rax
  wchar_t *v18; // rsi
  _QWORD *User; // rax
  void *v21; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-31h] BYREF
  char v25; // [rsp+50h] [rbp-29h]
  char *v26; // [rsp+58h] [rbp-21h]
  __int64 v27; // [rsp+60h] [rbp-19h]
  __int64 v28; // [rsp+68h] [rbp-11h]
  int v29; // [rsp+70h] [rbp-9h]
  __int64 v30; // [rsp+74h] [rbp-5h]
  _BYTE v31[8]; // [rsp+80h] [rbp+7h] BYREF
  _QWORD *v32; // [rsp+88h] [rbp+Fh]
  WCHAR *v33; // [rsp+90h] [rbp+17h]
  void *TokenInformationLength; // [rsp+E8h] [rbp+6Fh] BYREF
  ULONG nSize; // [rsp+F0h] [rbp+77h] BYREF
  void *TokenHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  TokenInformationLength = a2;
  TokenHandle = 0;
  v21 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_35;
  }
  v6 = TokenHandle;
  wmi::AutoHandle::Close((wmi::AutoHandle *)&v21);
  v21 = v6;
  LODWORD(TokenInformationLength) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) && GetLastError() != 122 )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v5 = v7;
    goto LABEL_35;
  }
  v8 = operator new[]((unsigned int)TokenInformationLength);
  v32 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
    }
    v25 = 0;
    v26 = byte_180052608;
    v27 = 0;
    v28 = 0;
    v29 = 14;
    v30 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v8, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength)
    || (v11 = *v8, nSize = 0, !GetUserNameExW(NameSamCompatible, 0, &nSize)) && GetLastError() != 234 )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    operator delete(v8);
    v5 = v10;
    goto LABEL_35;
  }
  v12 = nSize;
  if ( !nSize )
  {
LABEL_34:
    operator delete(v8);
    v5 = -2147418113;
LABEL_35:
    wmi::AutoHandle::Close((wmi::AutoHandle *)&v21);
    return v5;
  }
  ++nSize;
  v13 = (WCHAR *)operator new[](saturated_mul(v12 + 1, 2u));
  v14 = v13;
  v33 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
    }
    v25 = 0;
    v26 = byte_180052608;
    v27 = 0;
    v28 = 0;
    v29 = 14;
    v30 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !GetUserNameExW(NameSamCompatible, v13, &nSize) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    operator delete(v14);
    operator delete(v8);
    v5 = v16;
    goto LABEL_35;
  }
  v17 = wcschr(v14, 0x5Cu);
  v18 = v17;
  if ( !v17 )
  {
    operator delete(v14);
    goto LABEL_34;
  }
  *v17 = 0;
  _bstr_t::_bstr_t((_bstr_t *)v23, v14);
  _bstr_t::_bstr_t((_bstr_t *)v22, v18 + 1);
  User = (_QWORD *)User::CreateUser(v31, v22, v23, 8, v11);
  wmi::AutoRef<User::UserEntry>::operator=(a1, *User);
  wmi::AutoRef<User::UserEntry>::Release(v31);
  _bstr_t::~_bstr_t((_bstr_t *)v22);
  _bstr_t::~_bstr_t((_bstr_t *)v23);
  operator delete(v14);
  operator delete(v8);
  wmi::AutoHandle::Close((wmi::AutoHandle *)&v21);
  return 0;
}

```

## disassembly

```asm
0x18001a8f4  mov     [rsp-8+TokenInformationLength], rdx
0x18001a8f9  push    rbp
0x18001a8fa  push    rbx
0x18001a8fb  push    rsi
0x18001a8fc  push    rdi
0x18001a8fd  push    r12
0x18001a8ff  push    r14
0x18001a901  push    r15
0x18001a903  lea     rbp, [rsp-27h]
0x18001a908  sub     rsp, 0A0h
0x18001a90f  mov     r15, rcx
0x18001a912  xor     r12d, r12d
0x18001a915  mov     [rbp+57h+TokenHandle], r12
0x18001a919  mov     [rbp+57h+var_A0], r12
0x18001a91d  call    cs:__imp_GetCurrentThread
0x18001a924  nop     dword ptr [rax+rax+00h]
0x18001a929  mov     rcx, rax; ThreadHandle
0x18001a92c  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001a930  lea     edi, [r12+1]
0x18001a935  mov     r8d, edi; OpenAsSelf
0x18001a938  mov     edx, 20008h; DesiredAccess
0x18001a93d  call    cs:__imp_OpenThreadToken
0x18001a944  nop     dword ptr [rax+rax+00h]
0x18001a949  test    eax, eax
0x18001a94b  jnz     short loc_18001A971
0x18001a94d  call    cs:__imp_GetLastError
0x18001a954  nop     dword ptr [rax+rax+00h]
0x18001a959  mov     ebx, eax
0x18001a95b  test    eax, eax
0x18001a95d  jle     loc_18001AC17
0x18001a963  movzx   ebx, ax
0x18001a966  or      ebx, 80070000h
0x18001a96c  jmp     loc_18001AC17
0x18001a971  mov     rbx, [rbp+57h+TokenHandle]
0x18001a975  lea     rcx, [rbp+57h+var_A0]; this
0x18001a979  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001a97e  mov     [rbp+57h+var_A0], rbx
0x18001a982  mov     dword ptr [rbp+57h+TokenInformationLength], r12d
0x18001a986  lea     rax, [rbp+57h+TokenInformationLength]
0x18001a98a  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18001a98f  xor     r9d, r9d; TokenInformationLength
0x18001a992  xor     r8d, r8d; TokenInformation
0x18001a995  mov     edx, edi; TokenInformationClass
0x18001a997  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001a99b  call    cs:__imp_GetTokenInformation
0x18001a9a2  nop     dword ptr [rax+rax+00h]
0x18001a9a7  test    eax, eax
0x18001a9a9  jnz     short loc_18001A9DB
0x18001a9ab  call    cs:__imp_GetLastError
0x18001a9b2  nop     dword ptr [rax+rax+00h]
0x18001a9b7  cmp     eax, 7Ah ; 'z'
0x18001a9ba  jz      short loc_18001A9DB
0x18001a9bc  call    cs:__imp_GetLastError
0x18001a9c3  nop     dword ptr [rax+rax+00h]
0x18001a9c8  test    eax, eax
0x18001a9ca  jle     short loc_18001A9D4
0x18001a9cc  movzx   eax, ax
0x18001a9cf  or      eax, 80070000h
0x18001a9d4  mov     ebx, eax
0x18001a9d6  jmp     loc_18001AC17
0x18001a9db  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; unsigned __int64
0x18001a9de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a9e3  mov     rbx, rax
0x18001a9e6  mov     [rbp+57h+var_48], rax
0x18001a9ea  test    rax, rax
0x18001a9ed  jnz     short loc_18001AA69
0x18001a9ef  lea     rax, WPP_GLOBAL_Control
0x18001a9f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9fd  cmp     rcx, rax
0x18001aa00  jz      short loc_18001AA21
0x18001aa02  test    byte ptr [rcx+1Ch], 80h
0x18001aa06  jz      short loc_18001AA21
0x18001aa08  cmp     byte ptr [rcx+19h], 2
0x18001aa0c  jb      short loc_18001AA21
0x18001aa0e  lea     edx, [rbx+13h]
0x18001aa11  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001aa18  mov     rcx, [rcx+10h]
0x18001aa1c  call    WPP_SF_
0x18001aa21  mov     [rbp+57h+var_80], r12b
0x18001aa25  lea     rax, byte_180052608
0x18001aa2c  mov     [rbp+57h+var_78], rax
0x18001aa30  mov     [rbp+57h+var_70], r12
0x18001aa34  mov     [rbp+57h+var_68], r12
0x18001aa38  mov     [rbp+57h+var_60], 0Eh
0x18001aa3f  mov     dword ptr [rbp+57h+var_5C], 0FFFFFFFFh
0x18001aa46  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001aa4a  mov     dword ptr [rbp+57h+var_5C+4], esi
0x18001aa4d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001aa54  mov     [rbp+57h+pExceptionObject], rax
0x18001aa58  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001aa5f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001aa63  call    _CxxThrowException_0
0x18001aa69  lea     rax, [rbp+57h+TokenInformationLength]
0x18001aa6d  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18001aa72  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18001aa76  mov     r8, rbx; TokenInformation
0x18001aa79  mov     edx, edi; TokenInformationClass
0x18001aa7b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001aa7f  call    cs:__imp_GetTokenInformation
0x18001aa86  nop     dword ptr [rax+rax+00h]
0x18001aa8b  test    eax, eax
0x18001aa8d  jnz     short loc_18001AAB9
0x18001aa8f  call    cs:__imp_GetLastError
0x18001aa96  nop     dword ptr [rax+rax+00h]
0x18001aa9b  test    eax, eax
0x18001aa9d  mov     edi, eax
0x18001aa9f  jle     short loc_18001AAAA
0x18001aaa1  movzx   edi, ax
0x18001aaa4  or      edi, 80070000h
0x18001aaaa  mov     rcx, rbx; Block
0x18001aaad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aab2  mov     ebx, edi
0x18001aab4  jmp     loc_18001AC17
0x18001aab9  mov     r14, [rbx]
0x18001aabc  mov     [rbp+57h+nSize], r12d
0x18001aac0  lea     r8, [rbp+57h+nSize]; nSize
0x18001aac4  xor     edx, edx; lpNameBuffer
0x18001aac6  lea     ecx, [rdx+2]; NameFormat
0x18001aac9  call    cs:__imp_GetUserNameExW
0x18001aad0  nop     dword ptr [rax+rax+00h]
0x18001aad5  test    al, al
0x18001aad7  jnz     short loc_18001AAEC
0x18001aad9  call    cs:__imp_GetLastError
0x18001aae0  nop     dword ptr [rax+rax+00h]
0x18001aae5  cmp     eax, 0EAh
0x18001aaea  jnz     short loc_18001AA8F
0x18001aaec  mov     eax, [rbp+57h+nSize]
0x18001aaef  test    eax, eax
0x18001aaf1  jz      loc_18001AC0A
0x18001aaf7  add     eax, edi
0x18001aaf9  mov     [rbp+57h+nSize], eax
0x18001aafc  mov     ecx, eax
0x18001aafe  mov     eax, 2
0x18001ab03  mul     rcx
0x18001ab06  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001ab0d  cmovb   rax, rsi
0x18001ab11  mov     rcx, rax; unsigned __int64
0x18001ab14  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ab19  mov     rdi, rax
0x18001ab1c  mov     [rbp+57h+var_40], rax
0x18001ab20  test    rax, rax
0x18001ab23  jnz     short loc_18001AB99
0x18001ab25  lea     rax, WPP_GLOBAL_Control
0x18001ab2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab33  cmp     rcx, rax
0x18001ab36  jz      short loc_18001AB57
0x18001ab38  test    byte ptr [rcx+1Ch], 80h
0x18001ab3c  jz      short loc_18001AB57
0x18001ab3e  cmp     byte ptr [rcx+19h], 2
0x18001ab42  jb      short loc_18001AB57
0x18001ab44  lea     edx, [rsi+15h]
0x18001ab47  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001ab4e  mov     rcx, [rcx+10h]
0x18001ab52  call    WPP_SF_
0x18001ab57  mov     [rbp+57h+var_80], r12b
0x18001ab5b  lea     rax, byte_180052608
0x18001ab62  mov     [rbp+57h+var_78], rax
0x18001ab66  mov     [rbp+57h+var_70], r12
0x18001ab6a  mov     [rbp+57h+var_68], r12
0x18001ab6e  mov     [rbp+57h+var_60], 0Eh
0x18001ab75  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x18001ab7d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ab84  mov     [rbp+57h+pExceptionObject], rax
0x18001ab88  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001ab8f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001ab93  call    _CxxThrowException_0
0x18001ab99  lea     r8, [rbp+57h+nSize]; nSize
0x18001ab9d  mov     rdx, rdi; lpNameBuffer
0x18001aba0  mov     ecx, 2; NameFormat
0x18001aba5  call    cs:__imp_GetUserNameExW
0x18001abac  nop     dword ptr [rax+rax+00h]
0x18001abb1  test    al, al
0x18001abb3  jnz     short loc_18001ABE5
0x18001abb5  call    cs:__imp_GetLastError
0x18001abbc  nop     dword ptr [rax+rax+00h]
0x18001abc1  mov     esi, eax
0x18001abc3  test    eax, eax
0x18001abc5  jle     short loc_18001ABD0
0x18001abc7  movzx   esi, ax
0x18001abca  or      esi, 80070000h
0x18001abd0  mov     rcx, rdi; Block
0x18001abd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001abd8  nop
0x18001abd9  mov     rcx, rbx; Block
0x18001abdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001abe1  mov     ebx, esi
0x18001abe3  jmp     short loc_18001AC17
0x18001abe5  mov     edx, 5Ch ; '\'; Ch
0x18001abea  mov     rcx, rdi; Str
0x18001abed  call    cs:__imp_wcschr
0x18001abf4  nop     dword ptr [rax+rax+00h]
0x18001abf9  mov     rsi, rax
0x18001abfc  test    rax, rax
0x18001abff  jnz     short loc_18001AC27
0x18001ac01  mov     rcx, rdi; Block
0x18001ac04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac09  nop
0x18001ac0a  mov     rcx, rbx; Block
0x18001ac0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac12  mov     ebx, 8000FFFFh
0x18001ac17  lea     rcx, [rbp+57h+var_A0]; this
0x18001ac1b  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001ac20  mov     eax, ebx
0x18001ac22  jmp     loc_18001ACA8
0x18001ac27  mov     [rax], r12w
0x18001ac2b  mov     rdx, rdi; unsigned __int16 *
0x18001ac2e  lea     rcx, [rbp+57h+var_90]; this
0x18001ac32  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001ac37  nop
0x18001ac38  lea     rdx, [rsi+2]; unsigned __int16 *
0x18001ac3c  lea     rcx, [rbp+57h+var_98]; this
0x18001ac40  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001ac45  nop
0x18001ac46  mov     [rsp+0D0h+ReturnLength], r14
0x18001ac4b  mov     r9d, 8
0x18001ac51  lea     r8, [rbp+57h+var_90]
0x18001ac55  lea     rdx, [rbp+57h+var_98]
0x18001ac59  lea     rcx, [rbp+57h+var_50]
0x18001ac5d  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001ac62  mov     rdx, [rax]
0x18001ac65  mov     rcx, r15
0x18001ac68  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001ac6d  lea     rcx, [rbp+57h+var_50]
0x18001ac71  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001ac76  nop
0x18001ac77  lea     rcx, [rbp+57h+var_98]; this
0x18001ac7b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ac80  nop
0x18001ac81  lea     rcx, [rbp+57h+var_90]; this
0x18001ac85  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ac8a  nop
0x18001ac8b  mov     rcx, rdi; Block
0x18001ac8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac93  nop
0x18001ac94  mov     rcx, rbx; Block
0x18001ac97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac9c  nop
0x18001ac9d  lea     rcx, [rbp+57h+var_A0]; this
0x18001aca1  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001aca6  xor     eax, eax
0x18001aca8  add     rsp, 0A0h
0x18001acaf  pop     r15
0x18001acb1  pop     r14
0x18001acb3  pop     r12
0x18001acb5  pop     rdi
0x18001acb6  pop     rsi
0x18001acb7  pop     rbx
0x18001acb8  pop     rbp
0x18001acb9  retn
```
