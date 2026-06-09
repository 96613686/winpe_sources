# Token::Duplicate(_TOKEN_TYPE,_SECURITY_IMPERSONATION_LEVEL,Optional<IntegrityLevel>)

- ea: `0x140080f84`
- end: `0x140081218`
- name: `?Duplicate@Token@@QEBA?AV1@W4_TOKEN_TYPE@@W4_SECURITY_IMPERSONATION_LEVEL@@V?$Optional@W4IntegrityLevel@@@@@Z`
- size: `660`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x140005530`
- `0x140006338`
- `0x14000ccac`
- `0x14001f6b4`
- `0x140060f58`
- `0x14007f6c0`
- `0x140080ef8`
- `0x140080f84`
- `0x140082948`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x140081008`
- `ADVAPI32!DuplicateTokenEx` at `0x140081008`
- `ADVAPI32!SetTokenInformation` at `0x1400810c1`
- `ADVAPI32!SetTokenInformation` at `0x1400810c1`
- `ADVAPI32!GetSidLengthRequired` at `0x1400810a8`
- `ADVAPI32!GetSidLengthRequired` at `0x1400810a8`
- `KERNEL32!CloseHandle` at `0x1400810f6`
- `KERNEL32!CloseHandle` at `0x1400810f6`
- `KERNEL32!GetLastError` at `0x14008112e`
- `KERNEL32!GetLastError` at `0x140081193`
- `KERNEL32!GetLastError` at `0x14008112e`
- `KERNEL32!GetLastError` at `0x140081193`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Token::Duplicate(HANDLE *a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  BOOL v7; // ebx
  _BYTE *v8; // rdx
  __int64 v9; // rcx
  unsigned int *v10; // rdx
  DWORD SidLengthRequired; // eax
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  unsigned int v16; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD TokenInformation[3]; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h]
  void *phNewToken; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v24; // [rsp+E0h] [rbp-20h]
  _BYTE v25[72]; // [rsp+F0h] [rbp-10h] BYREF
  char *v26; // [rsp+138h] [rbp+38h] BYREF

  TokenInformation[0] = a2;
  v21 = a5;
  TokenHandle = 0;
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_OWORD *)&TokenAttributes.lpSecurityDescriptor = 0;
  stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(&phNewToken, &TokenHandle);
  v7 = DuplicateTokenEx(*a1, 0x2000000u, &TokenAttributes, SecurityIdentification, TokenPrimary, &phNewToken);
  if ( v24 )
  {
    TokenInformation[0] = phNewToken;
    (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v24 + 16LL))(v24, TokenInformation);
    if ( v24 )
    {
      v8 = v23;
      LOBYTE(v8) = v24 != v23;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v24 + 32LL))(v24, v8);
    }
  }
  if ( !v7 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v9 = a5 + 8;
  if ( a5 == -1 )
    v9 = 8;
  if ( *(_QWORD *)v9 )
  {
    v10 = *(unsigned int **)(a5 + 8);
    if ( !v10 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    Sid::FromIntegrityLevel(v25, *v10);
    TokenInformation[1] = 32;
    TokenInformation[0] = v25;
    SidLengthRequired = GetSidLengthRequired(1u);
    if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, SidLengthRequired + 16) )
    {
      v13 = GetLastError();
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v14);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::wstring::~wstring(&v26);
  }
  Token::Token(a2, (__int64 *)&TokenHandle);
  if ( TokenHandle && (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( *(_QWORD *)(a5 + 8) )
    *(_QWORD *)(a5 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x140080f84  mov     [rsp-8+arg_10], rbx
0x140080f89  push    rbp
0x140080f8a  push    rsi
0x140080f8b  push    rdi
0x140080f8c  lea     rbp, [rsp-70h]
0x140080f91  sub     rsp, 170h
0x140080f98  mov     rax, cs:__security_cookie
0x140080f9f  xor     rax, rsp
0x140080fa2  mov     [rbp+80h+var_20], rax
0x140080fa6  mov     rsi, rdx
0x140080fa9  mov     rbx, rcx
0x140080fac  mov     [rsp+180h+TokenInformation], rdx
0x140080fb1  mov     rdi, [rbp+80h+arg_20]
0x140080fb8  mov     [rbp+80h+var_F0], rdi
0x140080fbc  mov     [rsp+180h+TokenHandle], 0
0x140080fc5  mov     qword ptr [rsp+180h+TokenAttributes.nLength], 18h
0x140080fce  xorps   xmm0, xmm0
0x140080fd1  movups  xmmword ptr [rsp+180h+TokenAttributes.lpSecurityDescriptor], xmm0
0x140080fd6  lea     rdx, [rsp+180h+TokenHandle]
0x140080fdb  lea     rcx, [rbp+80h+var_E0]
0x140080fdf  call    ??$get_pointer@V?$unique_ptr@XUHandleClose@Private@@@std@@@stdext@@YA?AV?$GetPointer@PEAX@0@AEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; stdext::get_pointer<std::unique_ptr<void,Private::HandleClose>>(std::unique_ptr<void,Private::HandleClose> &)
0x140080fe4  lea     rax, [rbp+80h+var_E0]
0x140080fe8  mov     [rsp+180h+phNewToken], rax; phNewToken
0x140080fed  mov     [rsp+180h+TokenType], 1; TokenType
0x140080ff5  mov     r9d, 1; ImpersonationLevel
0x140080ffb  lea     r8, [rsp+180h+TokenAttributes]; lpTokenAttributes
0x140081000  mov     edx, 2000000h; dwDesiredAccess
0x140081005  mov     rcx, [rbx]; hExistingToken
0x140081008  call    cs:__imp_DuplicateTokenEx
0x14008100e  mov     ebx, eax
0x140081010  mov     rcx, [rbp+80h+var_A0]
0x140081014  test    rcx, rcx
0x140081017  jz      short loc_140081053
0x140081019  mov     rax, [rbp+80h+var_E0]
0x14008101d  mov     [rsp+180h+TokenInformation], rax
0x140081022  mov     rax, [rcx]
0x140081025  lea     rdx, [rsp+180h+TokenInformation]
0x14008102a  mov     rax, [rax+10h]
0x14008102e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081033  mov     rcx, [rbp+80h+var_A0]
0x140081037  test    rcx, rcx
0x14008103a  jz      short loc_140081053
0x14008103c  mov     rax, [rcx]
0x14008103f  lea     rdx, [rbp+80h+var_D8]
0x140081043  cmp     rcx, rdx
0x140081046  setnz   dl
0x140081049  mov     rax, [rax+20h]
0x14008104d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081052  nop
0x140081053  test    ebx, ebx
0x140081055  jz      loc_140081193
0x14008105b  lea     rax, [rdi+1]
0x14008105f  lea     rcx, [rax+7]
0x140081063  mov     edx, 8
0x140081068  test    rax, rax
0x14008106b  cmovz   rcx, rdx
0x14008106f  cmp     qword ptr [rcx], 0
0x140081073  jz      short loc_1400810D4
0x140081075  mov     rdx, [rdi+8]
0x140081079  test    rdx, rdx
0x14008107c  jz      loc_1400811F7
0x140081082  mov     edx, [rdx]
0x140081084  lea     rcx, [rbp+80h+var_90]
0x140081088  call    ?FromIntegrityLevel@Sid@@SA?AV1@W4IntegrityLevel@@@Z; Sid::FromIntegrityLevel(IntegrityLevel)
0x14008108d  nop
0x14008108e  xor     eax, eax
0x140081090  mov     [rsp+180h+var_140], rax
0x140081095  mov     dword ptr [rsp+180h+var_140], 20h ; ' '
0x14008109d  lea     rax, [rbp+80h+var_90]
0x1400810a1  mov     [rsp+180h+TokenInformation], rax
0x1400810a6  mov     cl, 1; nSubAuthorityCount
0x1400810a8  call    cs:__imp_GetSidLengthRequired
0x1400810ae  lea     r9d, [rax+10h]; TokenInformationLength
0x1400810b2  lea     r8, [rsp+180h+TokenInformation]; TokenInformation
0x1400810b7  mov     edx, 19h; TokenInformationClass
0x1400810bc  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x1400810c1  call    cs:__imp_SetTokenInformation
0x1400810c7  test    eax, eax
0x1400810c9  jz      short loc_14008112E
0x1400810cb  lea     rcx, [rbp+80h+var_48]
0x1400810cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400810d4  lea     rdx, [rsp+180h+TokenHandle]
0x1400810d9  mov     rcx, rsi
0x1400810dc  call    ??0Token@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Token::Token(std::unique_ptr<void,Private::HandleClose> &&)
0x1400810e1  nop
0x1400810e2  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x1400810e7  test    rcx, rcx
0x1400810ea  jz      short loc_1400810FD
0x1400810ec  lea     rax, [rcx-1]
0x1400810f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400810f4  ja      short loc_1400810FD
0x1400810f6  call    cs:__imp_CloseHandle
0x1400810fc  nop
0x1400810fd  cmp     qword ptr [rdi+8], 0
0x140081102  jz      short loc_14008110C
0x140081104  mov     qword ptr [rdi+8], 0
0x14008110c  mov     rax, rsi
0x14008110f  mov     rcx, [rbp+80h+var_20]
0x140081113  xor     rcx, rsp; StackCookie
0x140081116  call    __security_check_cookie
0x14008111b  mov     rbx, [rsp+180h+arg_10]
0x140081123  add     rsp, 170h
0x14008112a  pop     rdi
0x14008112b  pop     rsi
0x14008112c  pop     rbp
0x14008112d  retn
0x14008112e  call    cs:__imp_GetLastError
0x140081134  nop
0x140081135  mov     ebx, eax
0x140081137  test    eax, eax
0x140081139  jle     short loc_140081144
0x14008113b  movzx   ebx, ax
0x14008113e  or      ebx, 80070000h
0x140081144  lea     rax, WPP_GLOBAL_Control
0x14008114b  mov     rcx, cs:WPP_GLOBAL_Control
0x140081152  cmp     rcx, rax
0x140081155  jz      short loc_140081175
0x140081157  test    byte ptr [rcx+1Ch], 1
0x14008115b  jz      short loc_140081175
0x14008115d  mov     edx, 15h
0x140081162  mov     r9d, ebx
0x140081165  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x14008116c  mov     rcx, [rcx+10h]
0x140081170  call    WPP_SF_d
0x140081175  mov     edx, ebx; int
0x140081177  lea     rcx, [rsp+180h+pExceptionObject]; this
0x14008117c  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140081181  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140081188  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x14008118d  call    _CxxThrowException_0
0x140081193  call    cs:__imp_GetLastError
0x140081199  mov     ebx, eax
0x14008119b  test    eax, eax
0x14008119d  jle     short loc_1400811A8
0x14008119f  movzx   ebx, ax
0x1400811a2  or      ebx, 80070000h
0x1400811a8  lea     rax, WPP_GLOBAL_Control
0x1400811af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400811b6  cmp     rcx, rax
0x1400811b9  jz      short loc_1400811D9
0x1400811bb  test    byte ptr [rcx+1Ch], 1
0x1400811bf  jz      short loc_1400811D9
0x1400811c1  mov     edx, 14h
0x1400811c6  mov     r9d, ebx
0x1400811c9  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x1400811d0  mov     rcx, [rcx+10h]
0x1400811d4  call    WPP_SF_d
0x1400811d9  mov     edx, ebx; int
0x1400811db  lea     rcx, [rsp+180h+pExceptionObject]; this
0x1400811e0  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400811e5  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400811ec  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x1400811f1  call    _CxxThrowException_0
0x1400811f7  mov     edx, 80004003h; int
0x1400811fc  lea     rcx, [rsp+180h+pExceptionObject]; this
0x140081201  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140081206  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14008120d  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x140081212  call    _CxxThrowException_0
```
