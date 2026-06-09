# User::FromImpersonationToken(User &,void *)

- ea: `0x180019690`
- end: `0x180019a08`
- name: `?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z`
- size: `888`
- prototype: `__int64 __fastcall(struct User *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ac28`

## callees

- `0x180003470`
- `0x180004e1c`
- `0x180004e50`
- `0x1800050fc`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000878c`
- `0x18000fbb8`
- `0x180017210`
- `0x180018d00`
- `0x180019690`

## import_xrefs

- `msvcrt!wcschr` at `0x180019941`
- `msvcrt!wcschr` at `0x180019941`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800196d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800196d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800196b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800196b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019725`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800197f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019725`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800197f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001972f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001983f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001990f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001972f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001983f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001990f`
- `SspiCli!GetUserNameExW` at `0x180019835`
- `SspiCli!GetUserNameExW` at `0x180019905`
- `SspiCli!GetUserNameExW` at `0x180019835`
- `SspiCli!GetUserNameExW` at `0x180019905`

## pseudocode

```c
__int64 __fastcall User::FromImpersonationToken(struct User *a1, void *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v6; // rbx
  signed int v7; // eax
  void **v8; // rbx
  signed int v9; // eax
  unsigned int v10; // edi
  void *v11; // r14
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
  void **v32; // [rsp+88h] [rbp+Fh]
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
  wmi::AutoHandle::Close(&v21);
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
  v8 = (void **)operator new[]((unsigned int)TokenInformationLength);
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
    v26 = byte_1800505F8;
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
    wmi::AutoHandle::Close(&v21);
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
    v26 = byte_1800505F8;
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
  User = (_QWORD *)User::CreateUser(
                     (__int64)v31,
                     (const struct _bstr_t *)v22,
                     (const struct _bstr_t *)v23,
                     SidTypeUnknown,
                     v11);
  wmi::AutoRef<User::UserEntry>::operator=(a1, *User);
  wmi::AutoRef<User::UserEntry>::Release(v31);
  _bstr_t::~_bstr_t((_bstr_t *)v22);
  _bstr_t::~_bstr_t((_bstr_t *)v23);
  operator delete(v14);
  operator delete(v8);
  wmi::AutoHandle::Close(&v21);
  return 0;
}

```

## disassembly

```asm
0x180019690  mov     [rsp-8+TokenInformationLength], rdx
0x180019695  push    rbp
0x180019696  push    rbx
0x180019697  push    rsi
0x180019698  push    rdi
0x180019699  push    r12
0x18001969b  push    r14
0x18001969d  push    r15
0x18001969f  lea     rbp, [rsp-27h]
0x1800196a4  sub     rsp, 0A0h
0x1800196ab  mov     r15, rcx
0x1800196ae  xor     r12d, r12d
0x1800196b1  mov     [rbp+57h+TokenHandle], r12
0x1800196b5  mov     [rbp+57h+var_A0], r12
0x1800196b9  call    cs:__imp_GetCurrentThread
0x1800196bf  mov     rcx, rax; ThreadHandle
0x1800196c2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800196c6  lea     edi, [r12+1]
0x1800196cb  mov     r8d, edi; OpenAsSelf
0x1800196ce  mov     edx, 20008h; DesiredAccess
0x1800196d3  call    cs:__imp_OpenThreadToken
0x1800196d9  test    eax, eax
0x1800196db  jnz     short loc_1800196FB
0x1800196dd  call    cs:__imp_GetLastError
0x1800196e3  mov     ebx, eax
0x1800196e5  test    eax, eax
0x1800196e7  jle     loc_180019965
0x1800196ed  movzx   ebx, ax
0x1800196f0  or      ebx, 80070000h
0x1800196f6  jmp     loc_180019965
0x1800196fb  mov     rbx, [rbp+57h+TokenHandle]
0x1800196ff  lea     rcx, [rbp+57h+var_A0]; this
0x180019703  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180019708  mov     [rbp+57h+var_A0], rbx
0x18001970c  mov     dword ptr [rbp+57h+TokenInformationLength], r12d
0x180019710  lea     rax, [rbp+57h+TokenInformationLength]
0x180019714  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180019719  xor     r9d, r9d; TokenInformationLength
0x18001971c  xor     r8d, r8d; TokenInformation
0x18001971f  mov     edx, edi; TokenInformationClass
0x180019721  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180019725  call    cs:__imp_GetTokenInformation
0x18001972b  test    eax, eax
0x18001972d  jnz     short loc_180019753
0x18001972f  call    cs:__imp_GetLastError
0x180019735  cmp     eax, 7Ah ; 'z'
0x180019738  jz      short loc_180019753
0x18001973a  call    cs:__imp_GetLastError
0x180019740  test    eax, eax
0x180019742  jle     short loc_18001974C
0x180019744  movzx   eax, ax
0x180019747  or      eax, 80070000h
0x18001974c  mov     ebx, eax
0x18001974e  jmp     loc_180019965
0x180019753  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; unsigned __int64
0x180019756  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001975b  mov     rbx, rax
0x18001975e  mov     [rbp+57h+var_48], rax
0x180019762  test    rax, rax
0x180019765  jnz     short loc_1800197E1
0x180019767  lea     rax, WPP_GLOBAL_Control
0x18001976e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019775  cmp     rcx, rax
0x180019778  jz      short loc_180019799
0x18001977a  test    byte ptr [rcx+1Ch], 80h
0x18001977e  jz      short loc_180019799
0x180019780  cmp     byte ptr [rcx+19h], 2
0x180019784  jb      short loc_180019799
0x180019786  lea     edx, [rbx+13h]
0x180019789  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019790  mov     rcx, [rcx+10h]
0x180019794  call    WPP_SF_
0x180019799  mov     [rbp+57h+var_80], r12b
0x18001979d  lea     rax, byte_1800505F8
0x1800197a4  mov     [rbp+57h+var_78], rax
0x1800197a8  mov     [rbp+57h+var_70], r12
0x1800197ac  mov     [rbp+57h+var_68], r12
0x1800197b0  mov     [rbp+57h+var_60], 0Eh
0x1800197b7  mov     dword ptr [rbp+57h+var_5C], 0FFFFFFFFh
0x1800197be  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800197c2  mov     dword ptr [rbp+57h+var_5C+4], esi
0x1800197c5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800197cc  mov     [rbp+57h+pExceptionObject], rax
0x1800197d0  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800197d7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800197db  call    _CxxThrowException_0
0x1800197e1  lea     rax, [rbp+57h+TokenInformationLength]
0x1800197e5  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800197ea  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800197ee  mov     r8, rbx; TokenInformation
0x1800197f1  mov     edx, edi; TokenInformationClass
0x1800197f3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800197f7  call    cs:__imp_GetTokenInformation
0x1800197fd  test    eax, eax
0x1800197ff  jnz     short loc_180019825
0x180019801  call    cs:__imp_GetLastError
0x180019807  test    eax, eax
0x180019809  mov     edi, eax
0x18001980b  jle     short loc_180019816
0x18001980d  movzx   edi, ax
0x180019810  or      edi, 80070000h
0x180019816  mov     rcx, rbx; Block
0x180019819  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001981e  mov     ebx, edi
0x180019820  jmp     loc_180019965
0x180019825  mov     r14, [rbx]
0x180019828  mov     [rbp+57h+nSize], r12d
0x18001982c  lea     r8, [rbp+57h+nSize]; nSize
0x180019830  xor     edx, edx; lpNameBuffer
0x180019832  lea     ecx, [rdx+2]; NameFormat
0x180019835  call    cs:__imp_GetUserNameExW
0x18001983b  test    al, al
0x18001983d  jnz     short loc_18001984C
0x18001983f  call    cs:__imp_GetLastError
0x180019845  cmp     eax, 0EAh
0x18001984a  jnz     short loc_180019801
0x18001984c  mov     eax, [rbp+57h+nSize]
0x18001984f  test    eax, eax
0x180019851  jz      loc_180019958
0x180019857  add     eax, edi
0x180019859  mov     [rbp+57h+nSize], eax
0x18001985c  mov     ecx, eax
0x18001985e  mov     eax, 2
0x180019863  mul     rcx
0x180019866  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001986d  cmovb   rax, rsi
0x180019871  mov     rcx, rax; unsigned __int64
0x180019874  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019879  mov     rdi, rax
0x18001987c  mov     [rbp+57h+var_40], rax
0x180019880  test    rax, rax
0x180019883  jnz     short loc_1800198F9
0x180019885  lea     rax, WPP_GLOBAL_Control
0x18001988c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019893  cmp     rcx, rax
0x180019896  jz      short loc_1800198B7
0x180019898  test    byte ptr [rcx+1Ch], 80h
0x18001989c  jz      short loc_1800198B7
0x18001989e  cmp     byte ptr [rcx+19h], 2
0x1800198a2  jb      short loc_1800198B7
0x1800198a4  lea     edx, [rsi+15h]
0x1800198a7  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800198ae  mov     rcx, [rcx+10h]
0x1800198b2  call    WPP_SF_
0x1800198b7  mov     [rbp+57h+var_80], r12b
0x1800198bb  lea     rax, byte_1800505F8
0x1800198c2  mov     [rbp+57h+var_78], rax
0x1800198c6  mov     [rbp+57h+var_70], r12
0x1800198ca  mov     [rbp+57h+var_68], r12
0x1800198ce  mov     [rbp+57h+var_60], 0Eh
0x1800198d5  mov     [rbp+57h+var_5C], 0FFFFFFFFFFFFFFFFh
0x1800198dd  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800198e4  mov     [rbp+57h+pExceptionObject], rax
0x1800198e8  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800198ef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800198f3  call    _CxxThrowException_0
0x1800198f9  lea     r8, [rbp+57h+nSize]; nSize
0x1800198fd  mov     rdx, rdi; lpNameBuffer
0x180019900  mov     ecx, 2; NameFormat
0x180019905  call    cs:__imp_GetUserNameExW
0x18001990b  test    al, al
0x18001990d  jnz     short loc_180019939
0x18001990f  call    cs:__imp_GetLastError
0x180019915  mov     esi, eax
0x180019917  test    eax, eax
0x180019919  jle     short loc_180019924
0x18001991b  movzx   esi, ax
0x18001991e  or      esi, 80070000h
0x180019924  mov     rcx, rdi; Block
0x180019927  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001992c  nop
0x18001992d  mov     rcx, rbx; Block
0x180019930  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019935  mov     ebx, esi
0x180019937  jmp     short loc_180019965
0x180019939  mov     edx, 5Ch ; '\'; Ch
0x18001993e  mov     rcx, rdi; Str
0x180019941  call    cs:__imp_wcschr
0x180019947  mov     rsi, rax
0x18001994a  test    rax, rax
0x18001994d  jnz     short loc_180019975
0x18001994f  mov     rcx, rdi; Block
0x180019952  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019957  nop
0x180019958  mov     rcx, rbx; Block
0x18001995b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019960  mov     ebx, 8000FFFFh
0x180019965  lea     rcx, [rbp+57h+var_A0]; this
0x180019969  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001996e  mov     eax, ebx
0x180019970  jmp     loc_1800199F6
0x180019975  mov     [rax], r12w
0x180019979  mov     rdx, rdi; unsigned __int16 *
0x18001997c  lea     rcx, [rbp+57h+var_90]; this
0x180019980  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180019985  nop
0x180019986  lea     rdx, [rsi+2]; unsigned __int16 *
0x18001998a  lea     rcx, [rbp+57h+var_98]; this
0x18001998e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180019993  nop
0x180019994  mov     [rsp+0D0h+ReturnLength], r14
0x180019999  mov     r9d, 8
0x18001999f  lea     r8, [rbp+57h+var_90]
0x1800199a3  lea     rdx, [rbp+57h+var_98]
0x1800199a7  lea     rcx, [rbp+57h+var_50]
0x1800199ab  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x1800199b0  mov     rdx, [rax]
0x1800199b3  mov     rcx, r15
0x1800199b6  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800199bb  lea     rcx, [rbp+57h+var_50]
0x1800199bf  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800199c4  nop
0x1800199c5  lea     rcx, [rbp+57h+var_98]; this
0x1800199c9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800199ce  nop
0x1800199cf  lea     rcx, [rbp+57h+var_90]; this
0x1800199d3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800199d8  nop
0x1800199d9  mov     rcx, rdi; Block
0x1800199dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800199e1  nop
0x1800199e2  mov     rcx, rbx; Block
0x1800199e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800199ea  nop
0x1800199eb  lea     rcx, [rbp+57h+var_A0]; this
0x1800199ef  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x1800199f4  xor     eax, eax
0x1800199f6  add     rsp, 0A0h
0x1800199fd  pop     r15
0x1800199ff  pop     r14
0x180019a01  pop     r12
0x180019a03  pop     rdi
0x180019a04  pop     rsi
0x180019a05  pop     rbx
0x180019a06  pop     rbp
0x180019a07  retn
```
