# User::FromUserSession(User &,ulong,void *)

- ea: `0x180053d9c`
- end: `0x180054100`
- name: `?FromUserSession@User@@SAJAEAV1@KPEAX@Z`
- size: `868`
- prototype: `__int64 __fastcall(struct User *this, DWORD SessionId, void *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004d704`
- `0x18004e9d0`
- `0x1800534c8`
- `0x180053748`

## callees

- `0x180002260`
- `0x18000a460`
- `0x18000cc40`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180024730`
- `0x180027910`
- `0x18003bd70`
- `0x18003c1f8`
- `0x180053d9c`
- `0x180054108`
- `0x18005a2bc`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053ed4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053f89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053ed4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053f89`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180053e12`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180053e69`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180053e12`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180053e69`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180053de5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180053de5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall User::FromUserSession(struct User *this, DWORD SessionId, void *a3)
{
  char *v5; // rdi
  signed int LastError; // eax
  unsigned int v7; // ebx
  signed int v8; // eax
  signed int v9; // eax
  _QWORD *v10; // rbx
  signed int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdi
  _QWORD *User; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR *p_ppBuffer; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pBytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR *v19; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR ppBuffer; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR v21; // [rsp+58h] [rbp-A8h] BYREF
  void *phToken; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[8]; // [rsp+78h] [rbp-88h] BYREF
  void **pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  char v27; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A8h] [rbp-58h]
  __int64 v32; // [rsp+ACh] [rbp-54h]
  _QWORD *v33; // [rsp+B8h] [rbp-48h]
  WCHAR AccountName[280]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  ppBuffer = 0;
  v21 = 0;
  pBytesReturned = 0;
  phToken = 0;
  if ( WTSQueryUserToken(SessionId, &phToken) )
    v5 = (char *)phToken;
  if ( !WTSQuerySessionInformationW(0, SessionId, WTSUserName, &ppBuffer, &pBytesReturned) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  p_ppBuffer = &ppBuffer;
  if ( !WTSQuerySessionInformationW(0, SessionId, WTSDomainName, &v21, &pBytesReturned) )
  {
    v8 = GetLastError();
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_25;
  }
  v19 = &v21;
  if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (int)StringCchPrintfW(AccountName, 0x111u, L"%s\\%s", v21, ppBuffer) < 0 )
    {
      tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&v19);
      tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&p_ppBuffer);
      v7 = -2147418113;
      goto LABEL_26;
    }
    v7 = User::FromUsername(this, AccountName);
    goto LABEL_24;
  }
  ReturnLength = 0;
  if ( !GetTokenInformation(v5, TokenUser, 0, 0, &ReturnLength) && GetLastError() != 122 )
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
LABEL_24:
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&v19);
LABEL_25:
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&p_ppBuffer);
    goto LABEL_26;
  }
  v10 = operator new(ReturnLength);
  v33 = v10;
  if ( !v10 )
  {
    v27 = 0;
    v28 = &qword_1800A8718;
    v29 = 0;
    v30 = 0;
    v31 = 14;
    v32 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( GetTokenInformation(v5, TokenUser, v10, ReturnLength, &ReturnLength) )
  {
    v13 = *v10;
    _bstr_t::_bstr_t((_bstr_t *)v24, v21);
    _bstr_t::_bstr_t((_bstr_t *)v23, ppBuffer);
    User = (_QWORD *)User::CreateUser(v25, v23, v24, 8, v13);
    wmi::AutoRef<User::UserEntry>::operator=(this, *User);
    wmi::AutoRef<User::UserEntry>::Release(v25);
    _bstr_t::~_bstr_t((_bstr_t *)v23);
    _bstr_t::~_bstr_t((_bstr_t *)v24);
    operator delete(v10);
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&v19);
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&p_ppBuffer);
    v7 = 0;
  }
  else
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    operator delete(v10);
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&v19);
    tsched::WTSFreeMe<int>::~WTSFreeMe<int>(&p_ppBuffer);
    v7 = v12;
  }
LABEL_26:
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&phToken);
  return v7;
}

```

## disassembly

```asm
0x180053d9c  mov     [rsp-8+arg_10], rbx
0x180053da1  push    rbp
0x180053da2  push    rsi
0x180053da3  push    rdi
0x180053da4  lea     rbp, [rsp-200h]
0x180053dac  sub     rsp, 300h
0x180053db3  mov     rax, cs:__security_cookie
0x180053dba  xor     rax, rsp
0x180053dbd  mov     [rbp+210h+var_20], rax
0x180053dc4  mov     ebx, edx
0x180053dc6  mov     rsi, rcx
0x180053dc9  xor     edi, edi
0x180053dcb  mov     [rsp+310h+ppBuffer], rdi
0x180053dd0  mov     [rsp+310h+var_2B8], rdi
0x180053dd5  mov     [rsp+310h+var_2D0], edi
0x180053dd9  mov     [rsp+310h+phToken], rdi
0x180053dde  lea     rdx, [rsp+310h+phToken]; phToken
0x180053de3  mov     ecx, ebx; SessionId
0x180053de5  call    cs:__imp_WTSQueryUserToken
0x180053dec  nop     dword ptr [rax+rax+00h]
0x180053df1  test    eax, eax
0x180053df3  cmovnz  rdi, [rsp+310h+phToken]
0x180053df9  lea     rax, [rsp+310h+var_2D0]
0x180053dfe  mov     [rsp+310h+pBytesReturned], rax; pBytesReturned
0x180053e03  lea     r9, [rsp+310h+ppBuffer]; ppBuffer
0x180053e08  mov     r8d, 5; WTSInfoClass
0x180053e0e  mov     edx, ebx; SessionId
0x180053e10  xor     ecx, ecx; hServer
0x180053e12  call    cs:__imp_WTSQuerySessionInformationW
0x180053e19  nop     dword ptr [rax+rax+00h]
0x180053e1e  test    eax, eax
0x180053e20  jnz     short loc_180053E46
0x180053e22  call    cs:__imp_GetLastError
0x180053e29  nop     dword ptr [rax+rax+00h]
0x180053e2e  mov     ebx, eax
0x180053e30  test    eax, eax
0x180053e32  jle     loc_1800540D1
0x180053e38  movzx   ebx, ax
0x180053e3b  or      ebx, 80070000h
0x180053e41  jmp     loc_1800540D1
0x180053e46  lea     rax, [rsp+310h+ppBuffer]
0x180053e4b  mov     [rsp+310h+var_2D8], rax
0x180053e50  lea     rax, [rsp+310h+var_2D0]
0x180053e55  mov     [rsp+310h+pBytesReturned], rax; pBytesReturned
0x180053e5a  lea     r9, [rsp+310h+var_2B8]; ppBuffer
0x180053e5f  mov     r8d, 7; WTSInfoClass
0x180053e65  mov     edx, ebx; SessionId
0x180053e67  xor     ecx, ecx; hServer
0x180053e69  call    cs:__imp_WTSQuerySessionInformationW
0x180053e70  nop     dword ptr [rax+rax+00h]
0x180053e75  test    eax, eax
0x180053e77  jnz     short loc_180053E9D
0x180053e79  call    cs:__imp_GetLastError
0x180053e80  nop     dword ptr [rax+rax+00h]
0x180053e85  mov     ebx, eax
0x180053e87  test    eax, eax
0x180053e89  jle     loc_1800540C6
0x180053e8f  movzx   ebx, ax
0x180053e92  or      ebx, 80070000h
0x180053e98  jmp     loc_1800540C6
0x180053e9d  lea     rax, [rsp+310h+var_2B8]
0x180053ea2  mov     [rsp+310h+var_2C8], rax
0x180053ea7  lea     rax, [rdi-1]
0x180053eab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180053eaf  ja      loc_180054069
0x180053eb5  mov     [rsp+310h+ReturnLength], 0
0x180053ebd  lea     rax, [rsp+310h+ReturnLength]
0x180053ec2  mov     [rsp+310h+pBytesReturned], rax; ReturnLength
0x180053ec7  xor     r9d, r9d; TokenInformationLength
0x180053eca  xor     r8d, r8d; TokenInformation
0x180053ecd  lea     edx, [r9+1]; TokenInformationClass
0x180053ed1  mov     rcx, rdi; TokenHandle
0x180053ed4  call    cs:__imp_GetTokenInformation
0x180053edb  nop     dword ptr [rax+rax+00h]
0x180053ee0  test    eax, eax
0x180053ee2  jnz     short loc_180053F19
0x180053ee4  call    cs:__imp_GetLastError
0x180053eeb  nop     dword ptr [rax+rax+00h]
0x180053ef0  cmp     eax, 7Ah ; 'z'
0x180053ef3  jz      short loc_180053F19
0x180053ef5  call    cs:__imp_GetLastError
0x180053efc  nop     dword ptr [rax+rax+00h]
0x180053f01  mov     ebx, eax
0x180053f03  test    eax, eax
0x180053f05  jle     loc_1800540BB
0x180053f0b  movzx   ebx, ax
0x180053f0e  or      ebx, 80070000h
0x180053f14  jmp     loc_1800540BB
0x180053f19  mov     ecx, [rsp+310h+ReturnLength]; dwBytes
0x180053f1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053f22  mov     rbx, rax
0x180053f25  mov     [rbp+210h+var_258], rax
0x180053f29  test    rax, rax
0x180053f2c  jnz     short loc_180053F6F
0x180053f2e  mov     [rbp+210h+var_288], al
0x180053f31  lea     rax, qword_1800A8718
0x180053f38  mov     [rbp+210h+var_280], rax
0x180053f3c  mov     [rbp+210h+var_278], rbx
0x180053f40  mov     [rbp+210h+var_270], rbx
0x180053f44  mov     [rbp+210h+var_268], 0Eh
0x180053f4b  mov     [rbp+210h+var_264], 0FFFFFFFFFFFFFFFFh
0x180053f53  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180053f5a  mov     [rbp+210h+pExceptionObject], rax
0x180053f5e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180053f65  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x180053f69  call    _CxxThrowException_0
0x180053f6f  lea     rax, [rsp+310h+ReturnLength]
0x180053f74  mov     [rsp+310h+pBytesReturned], rax; ReturnLength
0x180053f79  mov     r9d, [rsp+310h+ReturnLength]; TokenInformationLength
0x180053f7e  mov     r8, rbx; TokenInformation
0x180053f81  mov     edx, 1; TokenInformationClass
0x180053f86  mov     rcx, rdi; TokenHandle
0x180053f89  call    cs:__imp_GetTokenInformation
0x180053f90  nop     dword ptr [rax+rax+00h]
0x180053f95  test    eax, eax
0x180053f97  jnz     short loc_180053FD9
0x180053f99  call    cs:__imp_GetLastError
0x180053fa0  nop     dword ptr [rax+rax+00h]
0x180053fa5  mov     edi, eax
0x180053fa7  test    eax, eax
0x180053fa9  jle     short loc_180053FB4
0x180053fab  movzx   edi, ax
0x180053fae  or      edi, 80070000h
0x180053fb4  mov     rcx, rbx; void *
0x180053fb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053fbc  nop
0x180053fbd  lea     rcx, [rsp+310h+var_2C8]
0x180053fc2  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180053fc7  nop
0x180053fc8  lea     rcx, [rsp+310h+var_2D8]
0x180053fcd  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180053fd2  mov     ebx, edi
0x180053fd4  jmp     loc_1800540D1
0x180053fd9  mov     rdi, [rbx]
0x180053fdc  mov     rdx, [rsp+310h+var_2B8]; unsigned __int16 *
0x180053fe1  lea     rcx, [rsp+310h+var_2A0]; this
0x180053fe6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053feb  nop
0x180053fec  mov     rdx, [rsp+310h+ppBuffer]; unsigned __int16 *
0x180053ff1  lea     rcx, [rsp+310h+var_2A8]; this
0x180053ff6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053ffb  nop
0x180053ffc  mov     [rsp+310h+pBytesReturned], rdi
0x180054001  mov     r9d, 8
0x180054007  lea     r8, [rsp+310h+var_2A0]
0x18005400c  lea     rdx, [rsp+310h+var_2A8]
0x180054011  lea     rcx, [rsp+310h+var_298]
0x180054016  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18005401b  mov     rdx, [rax]
0x18005401e  mov     rcx, rsi
0x180054021  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180054026  lea     rcx, [rsp+310h+var_298]
0x18005402b  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180054030  nop
0x180054031  lea     rcx, [rsp+310h+var_2A8]; this
0x180054036  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18005403b  nop
0x18005403c  lea     rcx, [rsp+310h+var_2A0]; this
0x180054041  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180054046  nop
0x180054047  mov     rcx, rbx; void *
0x18005404a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005404f  nop
0x180054050  lea     rcx, [rsp+310h+var_2C8]
0x180054055  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x18005405a  nop
0x18005405b  lea     rcx, [rsp+310h+var_2D8]
0x180054060  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180054065  xor     ebx, ebx
0x180054067  jmp     short loc_1800540D1
0x180054069  mov     rax, [rsp+310h+ppBuffer]
0x18005406e  mov     [rsp+310h+pBytesReturned], rax
0x180054073  mov     r9, [rsp+310h+var_2B8]
0x180054078  lea     r8, aSS; "%s\\%s"
0x18005407f  mov     edx, 111h; unsigned __int64
0x180054084  lea     rcx, [rbp+210h+AccountName]; unsigned __int16 *
0x180054088  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005408d  test    eax, eax
0x18005408f  jns     short loc_1800540AD
0x180054091  lea     rcx, [rsp+310h+var_2C8]
0x180054096  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x18005409b  nop
0x18005409c  lea     rcx, [rsp+310h+var_2D8]
0x1800540a1  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x1800540a6  mov     ebx, 8000FFFFh
0x1800540ab  jmp     short loc_1800540D1
0x1800540ad  lea     rdx, [rbp+210h+AccountName]; lpAccountName
0x1800540b1  mov     rcx, rsi; this
0x1800540b4  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x1800540b9  mov     ebx, eax
0x1800540bb  lea     rcx, [rsp+310h+var_2C8]
0x1800540c0  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x1800540c5  nop
0x1800540c6  lea     rcx, [rsp+310h+var_2D8]
0x1800540cb  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x1800540d0  nop
0x1800540d1  lea     rcx, [rsp+310h+phToken]; this
0x1800540d6  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800540db  mov     eax, ebx
0x1800540dd  mov     rcx, [rbp+210h+var_20]
0x1800540e4  xor     rcx, rsp; StackCookie
0x1800540e7  call    __security_check_cookie
0x1800540ec  mov     rbx, [rsp+310h+arg_10]
0x1800540f4  add     rsp, 300h
0x1800540fb  pop     rdi
0x1800540fc  pop     rsi
0x1800540fd  pop     rbp
0x1800540fe  retn
```
