# CreateNetworkAccessTokenFromCreds(ushort const *,ushort const *,void * *)

- ea: `0x18001764c`
- end: `0x1800179eb`
- name: `?CreateNetworkAccessTokenFromCreds@@YAJPEBG0PEAPEAX@Z`
- size: `927`
- prototype: `__int64 __fastcall(wchar_t *Str, LPCWSTR lpszPassword, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014184`
- `0x180017c20`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001764c`
- `0x18001c0d8`
- `0x18001c58c`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800177f1`
- `msvcrt!_wcsupr` at `0x1800177f1`
- `msvcrt!wcschr` at `0x18001775b`
- `msvcrt!wcschr` at `0x180017770`
- `msvcrt!wcschr` at `0x18001775b`
- `msvcrt!wcschr` at `0x180017770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179a3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001793c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001793c`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001786a`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001786a`
- `ext-ms-win-security-credui-l1-1-1!CredUIParseUserNameW` at `0x180017740`
- `ext-ms-win-security-credui-l1-1-1!CredUIParseUserNameW` at `0x180017740`

## string_xrefs

- `0x180017680`: `CreateNetworkAccessTokenFromCreds`
- `0x18001788e`: `SeBackupPrivilege`
- `0x1800178c1`: `SeRestorePrivilege`
- `0x1800178ea`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall CreateNetworkAccessTokenFromCreds(wchar_t *Str, LPCWSTR lpszPassword, void **a3)
{
  __int16 v6; // ax
  __int64 v7; // rsi
  signed int LastFailureAsHRESULT; // ebx
  WCHAR *p_user; // rdx
  __int64 v10; // rax
  WCHAR *v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  __int64 v14; // rcx
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v19; // [rsp+64h] [rbp-9Ch]
  __int16 v20; // [rsp+66h] [rbp-9Ah]
  wchar_t domain[344]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR user; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v23[1038]; // [rsp+352h] [rbp+252h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CreateNetworkAccessTokenFromCreds", 138, 1);
  user = 0;
  memset_0(v23, 0, 0x402u);
  domain[0] = 0;
  memset_0(&domain[1], 0, 0x2A2u);
  hObject = 0;
  DuplicateTokenHandle = 0;
  if ( a3 )
    *a3 = 0;
  v6 = 147;
  if ( !Str || (v19 = 147, v6 = 148, !lpszPassword) || (v19 = 148, v6 = 149, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v20 = v6;
    v18 = -2147024809;
    goto LABEL_38;
  }
  v7 = 514;
  v18 = 0;
  v19 = 149;
  LastFailureAsHRESULT = CredUIParseUserNameW(Str, &user, 0x202u, domain, 0x152u);
  if ( LastFailureAsHRESULT != 1315 || wcschr(Str, 0x5Cu) || wcschr(Str, 0x40u) )
  {
    _wcsupr(domain);
    if ( LastFailureAsHRESULT > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
  }
  else
  {
    wcscpy(domain, L".");
    p_user = &user;
    v10 = 2147483646;
    do
    {
      if ( !v10 )
        break;
      if ( !*Str )
        break;
      *p_user++ = *Str++;
      --v10;
      --v7;
    }
    while ( v7 );
    v11 = p_user - 1;
    v12 = 158;
    LastFailureAsHRESULT = v7 == 0 ? 0x8007007A : 0;
    v18 = LastFailureAsHRESULT;
    if ( v7 )
      v11 = p_user;
    *v11 = 0;
    if ( !v7 )
      goto LABEL_16;
    v19 = 158;
    LastFailureAsHRESULT = 0;
  }
  v18 = LastFailureAsHRESULT;
  v12 = 168;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v19 = 168;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( LogonUserExW(&user, domain, lpszPassword, 9u, 3u, &hObject, 0, 0, 0, 0) )
    {
      v18 = 0;
      v19 = 170;
      LastFailureAsHRESULT = AssertPrivilegeOnToken(hObject, L"SeBackupPrivilege");
      v18 = LastFailureAsHRESULT;
      v12 = 172;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v19 = 172;
        LastFailureAsHRESULT = AssertPrivilegeOnToken(hObject, L"SeRestorePrivilege");
        v18 = LastFailureAsHRESULT;
        v12 = 173;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v19 = 173;
          LastFailureAsHRESULT = AssertPrivilegeOnToken(hObject, L"SeSecurityPrivilege");
          v18 = LastFailureAsHRESULT;
          v12 = 174;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v19 = 174;
            if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(DuplicateTokenHandle);
              DuplicateTokenHandle = 0;
            }
            if ( DuplicateToken(hObject, SecurityImpersonation, &DuplicateTokenHandle) )
            {
              v18 = 0;
              v19 = 176;
              *a3 = DuplicateTokenHandle;
              DuplicateTokenHandle = 0;
              LastFailureAsHRESULT = 0;
              goto LABEL_33;
            }
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
            v18 = LastFailureAsHRESULT;
            v12 = 176;
          }
        }
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
      v18 = LastFailureAsHRESULT;
      v12 = 170;
    }
  }
LABEL_16:
  v20 = v12;
LABEL_33:
  if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_38:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001764c  push    rbp
0x18001764e  push    rbx
0x18001764f  push    rsi
0x180017650  push    rdi
0x180017651  push    r12
0x180017653  push    r14
0x180017655  push    r15
0x180017657  lea     rbp, [rsp-670h]
0x18001765f  sub     rsp, 770h
0x180017666  mov     rax, cs:__security_cookie
0x18001766d  xor     rax, rsp
0x180017670  mov     [rbp+6A0h+var_40], rax
0x180017677  mov     r14, r8
0x18001767a  mov     r15, rdx
0x18001767d  mov     rdi, rcx
0x180017680  lea     rdx, aCreatenetworka; "CreateNetworkAccessTokenFromCreds"
0x180017687  mov     r8d, 8Ah; unsigned __int16
0x18001768d  lea     rcx, [rsp+7A0h+var_740]; this
0x180017692  mov     r9d, 1; unsigned __int16
0x180017698  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001769d  xor     r12d, r12d
0x1800176a0  lea     rcx, [rbp+6A0h+var_44E]; void *
0x1800176a7  xor     edx, edx; Val
0x1800176a9  mov     [rbp+6A0h+user], r12w
0x1800176b1  mov     r8d, 402h; Size
0x1800176b7  call    memset_0
0x1800176bc  xor     edx, edx; Val
0x1800176be  mov     [rbp+6A0h+domain], r12w
0x1800176c3  mov     r8d, 2A2h; Size
0x1800176c9  lea     rcx, [rbp+6A0h+domain+2]; void *
0x1800176cd  call    memset_0
0x1800176d2  mov     [rsp+7A0h+hObject], r12
0x1800176d7  mov     [rsp+7A0h+DuplicateTokenHandle], r12
0x1800176dc  test    r14, r14
0x1800176df  jz      short loc_1800176E4
0x1800176e1  mov     [r14], r12
0x1800176e4  mov     eax, 93h
0x1800176e9  test    rdi, rdi
0x1800176ec  jz      loc_1800179B0
0x1800176f2  mov     [rsp+7A0h+var_73C], ax
0x1800176f7  mov     eax, 94h
0x1800176fc  test    r15, r15
0x1800176ff  jz      loc_1800179B0
0x180017705  mov     [rsp+7A0h+var_73C], ax
0x18001770a  mov     eax, 95h
0x18001770f  test    r14, r14
0x180017712  jz      loc_1800179B0
0x180017718  mov     esi, 202h
0x18001771d  mov     [rsp+7A0h+var_740], r12d
0x180017722  mov     r8d, esi; userBufferSize
0x180017725  mov     [rsp+7A0h+var_73C], ax
0x18001772a  lea     r9, [rbp+6A0h+domain]; domain
0x18001772e  mov     [rsp+7A0h+domainBufferSize], 152h; domainBufferSize
0x180017736  lea     rdx, [rbp+6A0h+user]; user
0x18001773d  mov     rcx, rdi; UserName
0x180017740  call    cs:__imp_CredUIParseUserNameW
0x180017746  mov     ebx, eax
0x180017748  cmp     eax, 523h
0x18001774d  jnz     loc_1800177ED
0x180017753  mov     edx, 5Ch ; '\'; Ch
0x180017758  mov     rcx, rdi; Str
0x18001775b  call    cs:__imp_wcschr
0x180017761  test    rax, rax
0x180017764  jnz     loc_1800177ED
0x18001776a  lea     edx, [rax+40h]; Ch
0x18001776d  mov     rcx, rdi; Str
0x180017770  call    cs:__imp_wcschr
0x180017776  test    rax, rax
0x180017779  jnz     short loc_1800177ED
0x18001777b  mov     dword ptr [rbp+6A0h+domain], 2Eh ; '.'
0x180017782  lea     rdx, [rbp+6A0h+user]
0x180017789  mov     eax, 7FFFFFFEh
0x18001778e  test    rax, rax
0x180017791  jz      short loc_1800177AF
0x180017793  movzx   ecx, word ptr [rdi]
0x180017796  test    cx, cx
0x180017799  jz      short loc_1800177AF
0x18001779b  mov     [rdx], cx
0x18001779e  add     rdi, 2
0x1800177a2  add     rdx, 2
0x1800177a6  dec     rax
0x1800177a9  sub     rsi, 1
0x1800177ad  jnz     short loc_18001778E
0x1800177af  mov     rax, rsi
0x1800177b2  lea     rcx, [rdx-2]
0x1800177b6  neg     rax
0x1800177b9  mov     eax, 9Eh
0x1800177be  sbb     ebx, ebx
0x1800177c0  not     ebx
0x1800177c2  and     ebx, 8007007Ah
0x1800177c8  test    rsi, rsi
0x1800177cb  mov     [rsp+7A0h+var_740], ebx
0x1800177cf  cmovnz  rcx, rdx
0x1800177d3  mov     [rcx], r12w
0x1800177d7  jnz     short loc_1800177E3
0x1800177d9  mov     [rsp+7A0h+var_73A], ax
0x1800177de  jmp     loc_18001797A
0x1800177e3  mov     [rsp+7A0h+var_73C], ax
0x1800177e8  mov     ebx, r12d
0x1800177eb  jmp     short loc_180017804
0x1800177ed  lea     rcx, [rbp+6A0h+domain]; String
0x1800177f1  call    cs:__imp__wcsupr
0x1800177f7  test    ebx, ebx
0x1800177f9  jle     short loc_180017804
0x1800177fb  movzx   ebx, bx
0x1800177fe  or      ebx, 80070000h
0x180017804  mov     [rsp+7A0h+var_740], ebx
0x180017808  mov     eax, 0A8h
0x18001780d  test    ebx, ebx
0x18001780f  js      short loc_1800177D9
0x180017811  mov     rcx, [rsp+7A0h+hObject]; hObject
0x180017816  mov     [rsp+7A0h+var_73C], ax
0x18001781b  lea     rax, [rcx-1]
0x18001781f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017823  ja      short loc_180017830
0x180017825  call    cs:__imp_CloseHandle
0x18001782b  mov     [rsp+7A0h+hObject], r12
0x180017830  mov     [rsp+7A0h+pQuotaLimits], r12; pQuotaLimits
0x180017835  lea     rax, [rsp+7A0h+hObject]
0x18001783a  mov     [rsp+7A0h+pdwProfileLength], r12; pdwProfileLength
0x18001783f  lea     rdx, [rbp+6A0h+domain]; lpszDomain
0x180017843  mov     [rsp+7A0h+ppProfileBuffer], r12; ppProfileBuffer
0x180017848  lea     rcx, [rbp+6A0h+user]; lpszUsername
0x18001784f  mov     [rsp+7A0h+ppLogonSid], r12; ppLogonSid
0x180017854  mov     r9d, 9; dwLogonType
0x18001785a  mov     [rsp+7A0h+phToken], rax; phToken
0x18001785f  mov     r8, r15; lpszPassword
0x180017862  mov     [rsp+7A0h+domainBufferSize], 3; dwLogonProvider
0x18001786a  call    cs:__imp_LogonUserExW
0x180017870  test    eax, eax
0x180017872  jnz     short loc_180017889
0x180017874  call    GetLastFailureAsHRESULT
0x180017879  mov     ebx, eax
0x18001787b  mov     [rsp+7A0h+var_740], eax
0x18001787f  mov     eax, 0AAh
0x180017884  jmp     loc_1800177D9
0x180017889  mov     rcx, [rsp+7A0h+hObject]; TokenHandle
0x18001788e  lea     rdx, Name; "SeBackupPrivilege"
0x180017895  mov     eax, 0AAh
0x18001789a  mov     [rsp+7A0h+var_740], r12d
0x18001789f  mov     [rsp+7A0h+var_73C], ax
0x1800178a4  call    ?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z; AssertPrivilegeOnToken(void *,ushort const *)
0x1800178a9  mov     ebx, eax
0x1800178ab  mov     [rsp+7A0h+var_740], eax
0x1800178af  test    eax, eax
0x1800178b1  mov     eax, 0ACh
0x1800178b6  js      loc_1800177D9
0x1800178bc  mov     rcx, [rsp+7A0h+hObject]; TokenHandle
0x1800178c1  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x1800178c8  mov     [rsp+7A0h+var_73C], ax
0x1800178cd  call    ?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z; AssertPrivilegeOnToken(void *,ushort const *)
0x1800178d2  mov     ebx, eax
0x1800178d4  mov     [rsp+7A0h+var_740], eax
0x1800178d8  test    eax, eax
0x1800178da  mov     eax, 0ADh
0x1800178df  js      loc_1800177D9
0x1800178e5  mov     rcx, [rsp+7A0h+hObject]; TokenHandle
0x1800178ea  lea     rdx, aSesecuritypriv; "SeSecurityPrivilege"
0x1800178f1  mov     [rsp+7A0h+var_73C], ax
0x1800178f6  call    ?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z; AssertPrivilegeOnToken(void *,ushort const *)
0x1800178fb  mov     ebx, eax
0x1800178fd  mov     [rsp+7A0h+var_740], eax
0x180017901  test    eax, eax
0x180017903  mov     eax, 0AEh
0x180017908  js      loc_1800177D9
0x18001790e  mov     rcx, [rsp+7A0h+DuplicateTokenHandle]; hObject
0x180017913  mov     [rsp+7A0h+var_73C], ax
0x180017918  lea     rax, [rcx-1]
0x18001791c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017920  ja      short loc_18001792D
0x180017922  call    cs:__imp_CloseHandle
0x180017928  mov     [rsp+7A0h+DuplicateTokenHandle], r12
0x18001792d  mov     rcx, [rsp+7A0h+hObject]; ExistingTokenHandle
0x180017932  lea     r8, [rsp+7A0h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180017937  mov     edx, 2; ImpersonationLevel
0x18001793c  call    cs:__imp_DuplicateToken
0x180017942  test    eax, eax
0x180017944  jnz     short loc_18001795B
0x180017946  call    GetLastFailureAsHRESULT
0x18001794b  mov     ebx, eax
0x18001794d  mov     [rsp+7A0h+var_740], eax
0x180017951  mov     eax, 0B0h
0x180017956  jmp     loc_1800177D9
0x18001795b  mov     eax, 0B0h
0x180017960  mov     [rsp+7A0h+var_740], r12d
0x180017965  mov     [rsp+7A0h+var_73C], ax
0x18001796a  mov     rax, [rsp+7A0h+DuplicateTokenHandle]
0x18001796f  mov     [r14], rax
0x180017972  mov     [rsp+7A0h+DuplicateTokenHandle], r12
0x180017977  mov     ebx, r12d
0x18001797a  mov     rcx, [rsp+7A0h+DuplicateTokenHandle]; hObject
0x18001797f  lea     rax, [rcx-1]
0x180017983  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017987  ja      short loc_180017994
0x180017989  call    cs:__imp_CloseHandle
0x18001798f  mov     [rsp+7A0h+DuplicateTokenHandle], r12
0x180017994  mov     rcx, [rsp+7A0h+hObject]; hObject
0x180017999  lea     rax, [rcx-1]
0x18001799d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800179a1  ja      short loc_1800179BE
0x1800179a3  call    cs:__imp_CloseHandle
0x1800179a9  mov     [rsp+7A0h+hObject], r12
0x1800179ae  jmp     short loc_1800179BE
0x1800179b0  mov     ebx, 80070057h
0x1800179b5  mov     [rsp+7A0h+var_73A], ax
0x1800179ba  mov     [rsp+7A0h+var_740], ebx
0x1800179be  lea     rcx, [rsp+7A0h+var_740]; this
0x1800179c3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800179c8  mov     eax, ebx
0x1800179ca  mov     rcx, [rbp+6A0h+var_40]
0x1800179d1  xor     rcx, rsp; StackCookie
0x1800179d4  call    __security_check_cookie
0x1800179d9  add     rsp, 770h
0x1800179e0  pop     r15
0x1800179e2  pop     r14
0x1800179e4  pop     r12
0x1800179e6  pop     rdi
0x1800179e7  pop     rsi
0x1800179e8  pop     rbx
0x1800179e9  pop     rbp
0x1800179ea  retn
```
