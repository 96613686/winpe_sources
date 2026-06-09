# User::FromUserSession(User &,ulong,void *)

- ea: `0x1800517ec`
- end: `0x180051b13`
- name: `?FromUserSession@User@@SAJAEAV1@KPEAX@Z`
- size: `807`
- prototype: `__int64 __fastcall(struct User *this, DWORD SessionId, void *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004b2b4`
- `0x18004c6d0`
- `0x180050f58`
- `0x1800511b8`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x180015740`
- `0x18001a260`
- `0x1800290f0`
- `0x180029508`
- `0x18002ab90`
- `0x18002b1d0`
- `0x180030f80`
- `0x180039d00`
- `0x1800517ec`
- `0x180051b1c`
- `0x18005790c`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005191b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800519b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005191b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800519b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051906`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800519a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051906`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800519a9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005185c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800518a7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005185c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800518a7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180051835`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180051835`

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
    v28 = &qword_1800A4718;
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
0x1800517ec  mov     [rsp-8+arg_10], rbx
0x1800517f1  push    rbp
0x1800517f2  push    rsi
0x1800517f3  push    rdi
0x1800517f4  lea     rbp, [rsp-200h]
0x1800517fc  sub     rsp, 300h
0x180051803  mov     rax, cs:__security_cookie
0x18005180a  xor     rax, rsp
0x18005180d  mov     [rbp+210h+var_20], rax
0x180051814  mov     ebx, edx
0x180051816  mov     rsi, rcx
0x180051819  xor     edi, edi
0x18005181b  mov     [rsp+310h+ppBuffer], rdi
0x180051820  mov     [rsp+310h+var_2B8], rdi
0x180051825  mov     [rsp+310h+var_2D0], edi
0x180051829  mov     [rsp+310h+phToken], rdi
0x18005182e  lea     rdx, [rsp+310h+phToken]; phToken
0x180051833  mov     ecx, ebx; SessionId
0x180051835  call    cs:__imp_WTSQueryUserToken
0x18005183b  test    eax, eax
0x18005183d  cmovnz  rdi, [rsp+310h+phToken]
0x180051843  lea     rax, [rsp+310h+var_2D0]
0x180051848  mov     [rsp+310h+pBytesReturned], rax; pBytesReturned
0x18005184d  lea     r9, [rsp+310h+ppBuffer]; ppBuffer
0x180051852  mov     r8d, 5; WTSInfoClass
0x180051858  mov     edx, ebx; SessionId
0x18005185a  xor     ecx, ecx; hServer
0x18005185c  call    cs:__imp_WTSQuerySessionInformationW
0x180051862  test    eax, eax
0x180051864  jnz     short loc_180051884
0x180051866  call    cs:__imp_GetLastError
0x18005186c  mov     ebx, eax
0x18005186e  test    eax, eax
0x180051870  jle     loc_180051AE5
0x180051876  movzx   ebx, ax
0x180051879  or      ebx, 80070000h
0x18005187f  jmp     loc_180051AE5
0x180051884  lea     rax, [rsp+310h+ppBuffer]
0x180051889  mov     [rsp+310h+var_2D8], rax
0x18005188e  lea     rax, [rsp+310h+var_2D0]
0x180051893  mov     [rsp+310h+pBytesReturned], rax; pBytesReturned
0x180051898  lea     r9, [rsp+310h+var_2B8]; ppBuffer
0x18005189d  mov     r8d, 7; WTSInfoClass
0x1800518a3  mov     edx, ebx; SessionId
0x1800518a5  xor     ecx, ecx; hServer
0x1800518a7  call    cs:__imp_WTSQuerySessionInformationW
0x1800518ad  test    eax, eax
0x1800518af  jnz     short loc_1800518CF
0x1800518b1  call    cs:__imp_GetLastError
0x1800518b7  mov     ebx, eax
0x1800518b9  test    eax, eax
0x1800518bb  jle     loc_180051ADA
0x1800518c1  movzx   ebx, ax
0x1800518c4  or      ebx, 80070000h
0x1800518ca  jmp     loc_180051ADA
0x1800518cf  lea     rax, [rsp+310h+var_2B8]
0x1800518d4  mov     [rsp+310h+var_2C8], rax
0x1800518d9  lea     rax, [rdi-1]
0x1800518dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800518e1  ja      loc_180051A7D
0x1800518e7  mov     [rsp+310h+ReturnLength], 0
0x1800518ef  lea     rax, [rsp+310h+ReturnLength]
0x1800518f4  mov     [rsp+310h+pBytesReturned], rax; ReturnLength
0x1800518f9  xor     r9d, r9d; TokenInformationLength
0x1800518fc  xor     r8d, r8d; TokenInformation
0x1800518ff  lea     edx, [r9+1]; TokenInformationClass
0x180051903  mov     rcx, rdi; TokenHandle
0x180051906  call    cs:__imp_GetTokenInformation
0x18005190c  test    eax, eax
0x18005190e  jnz     short loc_180051939
0x180051910  call    cs:__imp_GetLastError
0x180051916  cmp     eax, 7Ah ; 'z'
0x180051919  jz      short loc_180051939
0x18005191b  call    cs:__imp_GetLastError
0x180051921  mov     ebx, eax
0x180051923  test    eax, eax
0x180051925  jle     loc_180051ACF
0x18005192b  movzx   ebx, ax
0x18005192e  or      ebx, 80070000h
0x180051934  jmp     loc_180051ACF
0x180051939  mov     ecx, [rsp+310h+ReturnLength]; dwBytes
0x18005193d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051942  mov     rbx, rax
0x180051945  mov     [rbp+210h+var_258], rax
0x180051949  test    rax, rax
0x18005194c  jnz     short loc_18005198F
0x18005194e  mov     [rbp+210h+var_288], al
0x180051951  lea     rax, qword_1800A4718
0x180051958  mov     [rbp+210h+var_280], rax
0x18005195c  mov     [rbp+210h+var_278], rbx
0x180051960  mov     [rbp+210h+var_270], rbx
0x180051964  mov     [rbp+210h+var_268], 0Eh
0x18005196b  mov     [rbp+210h+var_264], 0FFFFFFFFFFFFFFFFh
0x180051973  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18005197a  mov     [rbp+210h+pExceptionObject], rax
0x18005197e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180051985  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x180051989  call    _CxxThrowException_0
0x18005198f  lea     rax, [rsp+310h+ReturnLength]
0x180051994  mov     [rsp+310h+pBytesReturned], rax; ReturnLength
0x180051999  mov     r9d, [rsp+310h+ReturnLength]; TokenInformationLength
0x18005199e  mov     r8, rbx; TokenInformation
0x1800519a1  mov     edx, 1; TokenInformationClass
0x1800519a6  mov     rcx, rdi; TokenHandle
0x1800519a9  call    cs:__imp_GetTokenInformation
0x1800519af  test    eax, eax
0x1800519b1  jnz     short loc_1800519ED
0x1800519b3  call    cs:__imp_GetLastError
0x1800519b9  mov     edi, eax
0x1800519bb  test    eax, eax
0x1800519bd  jle     short loc_1800519C8
0x1800519bf  movzx   edi, ax
0x1800519c2  or      edi, 80070000h
0x1800519c8  mov     rcx, rbx; void *
0x1800519cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800519d0  nop
0x1800519d1  lea     rcx, [rsp+310h+var_2C8]
0x1800519d6  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x1800519db  nop
0x1800519dc  lea     rcx, [rsp+310h+var_2D8]
0x1800519e1  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x1800519e6  mov     ebx, edi
0x1800519e8  jmp     loc_180051AE5
0x1800519ed  mov     rdi, [rbx]
0x1800519f0  mov     rdx, [rsp+310h+var_2B8]; unsigned __int16 *
0x1800519f5  lea     rcx, [rsp+310h+var_2A0]; this
0x1800519fa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800519ff  nop
0x180051a00  mov     rdx, [rsp+310h+ppBuffer]; unsigned __int16 *
0x180051a05  lea     rcx, [rsp+310h+var_2A8]; this
0x180051a0a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180051a0f  nop
0x180051a10  mov     [rsp+310h+pBytesReturned], rdi
0x180051a15  mov     r9d, 8
0x180051a1b  lea     r8, [rsp+310h+var_2A0]
0x180051a20  lea     rdx, [rsp+310h+var_2A8]
0x180051a25  lea     rcx, [rsp+310h+var_298]
0x180051a2a  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@0W4_SID_NAME_USE@@PEAX@Z; User::CreateUser(_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180051a2f  mov     rdx, [rax]
0x180051a32  mov     rcx, rsi
0x180051a35  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180051a3a  lea     rcx, [rsp+310h+var_298]
0x180051a3f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180051a44  nop
0x180051a45  lea     rcx, [rsp+310h+var_2A8]; this
0x180051a4a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180051a4f  nop
0x180051a50  lea     rcx, [rsp+310h+var_2A0]; this
0x180051a55  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180051a5a  nop
0x180051a5b  mov     rcx, rbx; void *
0x180051a5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180051a63  nop
0x180051a64  lea     rcx, [rsp+310h+var_2C8]
0x180051a69  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051a6e  nop
0x180051a6f  lea     rcx, [rsp+310h+var_2D8]
0x180051a74  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051a79  xor     ebx, ebx
0x180051a7b  jmp     short loc_180051AE5
0x180051a7d  mov     rax, [rsp+310h+ppBuffer]
0x180051a82  mov     [rsp+310h+pBytesReturned], rax
0x180051a87  mov     r9, [rsp+310h+var_2B8]
0x180051a8c  lea     r8, aSS; "%s\\%s"
0x180051a93  mov     edx, 111h; unsigned __int64
0x180051a98  lea     rcx, [rbp+210h+AccountName]; unsigned __int16 *
0x180051a9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051aa1  test    eax, eax
0x180051aa3  jns     short loc_180051AC1
0x180051aa5  lea     rcx, [rsp+310h+var_2C8]
0x180051aaa  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051aaf  nop
0x180051ab0  lea     rcx, [rsp+310h+var_2D8]
0x180051ab5  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051aba  mov     ebx, 8000FFFFh
0x180051abf  jmp     short loc_180051AE5
0x180051ac1  lea     rdx, [rbp+210h+AccountName]; lpAccountName
0x180051ac5  mov     rcx, rsi; this
0x180051ac8  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180051acd  mov     ebx, eax
0x180051acf  lea     rcx, [rsp+310h+var_2C8]
0x180051ad4  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051ad9  nop
0x180051ada  lea     rcx, [rsp+310h+var_2D8]
0x180051adf  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x180051ae4  nop
0x180051ae5  lea     rcx, [rsp+310h+phToken]; this
0x180051aea  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180051aef  mov     eax, ebx
0x180051af1  mov     rcx, [rbp+210h+var_20]
0x180051af8  xor     rcx, rsp; StackCookie
0x180051afb  call    __security_check_cookie
0x180051b00  mov     rbx, [rsp+310h+arg_10]
0x180051b08  add     rsp, 300h
0x180051b0f  pop     rdi
0x180051b10  pop     rsi
0x180051b11  pop     rbp
0x180051b12  retn
```
