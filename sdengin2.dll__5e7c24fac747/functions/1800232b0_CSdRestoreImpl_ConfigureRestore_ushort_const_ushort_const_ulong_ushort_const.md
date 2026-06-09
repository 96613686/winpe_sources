# CSdRestoreImpl::ConfigureRestore(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x1800232b0`
- end: `0x180023438`
- name: `?ConfigureRestore@CSdRestoreImpl@@UEAAJPEBG0K0@Z`
- size: `392`
- prototype: `__int64 __fastcall(CSdRestoreImpl *this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003430`
- `0x180021b2c`
- `0x180021f98`
- `0x180021fc0`
- `0x1800232b0`
- `0x180028300`
- `0x180029e88`
- `0x180030b10`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180099bf4`
- `0x1800b6568`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800233ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800233ca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180023353`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180023353`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002333c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002333c`

## string_xrefs

- `0x1800232de`: `CSdRestoreImpl::ConfigureRestore`
- `0x180023368`: `%windir%\Temp`
- `0x18002341b`: `%temp%`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::ConfigureRestore(
        CSdRestoreImpl *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  int token_information; // ebx
  __int16 v9; // ax
  PSID *v10; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  CBsString *v13; // rcx
  bool v14; // sf
  char *v16; // [rsp+20h] [rbp-58h] BYREF
  int v17; // [rsp+28h] [rbp-50h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  __int16 v19; // [rsp+34h] [rbp-44h]
  __int16 v20; // [rsp+36h] [rbp-42h]
  PSID *v21; // [rsp+C0h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CSdRestoreImpl::ConfigureRestore", 0x12F9u, 1u);
  v16 = (char *)this + 64;
  CSdCriticalSection::Lock((CSdRestoreImpl *)((char *)this + 64));
  v17 = 1;
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v21);
  token_information = wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(&v21, -4);
  v18 = token_information;
  v9 = 4871;
  if ( token_information < 0 )
    goto LABEL_2;
  v19 = 4871;
  v10 = v21;
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v21);
  SidSubAuthority = GetSidSubAuthority(*v10, (unsigned __int8)(*SidSubAuthorityCount - 1));
  v13 = (CSdRestoreImpl *)((char *)this + 136);
  if ( *SidSubAuthority <= 0x2000 )
  {
    token_information = CBsString::ExpandEnvironmentStringsW(v13, L"%temp%");
    v18 = token_information;
    v14 = token_information < 0;
    v9 = 4879;
  }
  else
  {
    token_information = CBsString::ExpandEnvironmentStringsW(v13, L"%windir%\\Temp");
    v18 = token_information;
    v14 = token_information < 0;
    v9 = 4875;
  }
  if ( v14 )
    goto LABEL_2;
  v19 = v9;
  token_information = CSdRestoreImpl::_InitializeRestoreLog(this);
  v18 = token_information;
  v9 = 4882;
  if ( token_information < 0
    || (v19 = 4882,
        token_information = CSdRestoreImpl::_ConfigureRestoreHelper(this, a2, a3, a4),
        v18 = token_information,
        v9 = 4883,
        token_information < 0) )
  {
LABEL_2:
    v20 = v9;
  }
  else
  {
    v19 = 4883;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    v17 = 0;
    token_information = v18;
  }
  if ( token_information < 0 )
  {
    CSdRestoreImpl::_SetInternalLastError(this, (struct CSxFunctionTracer *)&v18);
    token_information = v18;
  }
  wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(&v21);
  CSdAutomaticLock::~CSdAutomaticLock((CSdAutomaticLock *)&v16);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)token_information;
}

```

## disassembly

```asm
0x1800232b0  push    rbp
0x1800232b2  push    rbx
0x1800232b3  push    rsi
0x1800232b4  push    rdi
0x1800232b5  push    r12
0x1800232b7  push    r13
0x1800232b9  push    r14
0x1800232bb  push    r15
0x1800232bd  mov     rbp, rsp
0x1800232c0  sub     rsp, 78h
0x1800232c4  mov     r15d, r9d
0x1800232c7  mov     r12, r8
0x1800232ca  mov     r13, rdx
0x1800232cd  mov     rdi, rcx
0x1800232d0  mov     ebx, 1
0x1800232d5  mov     r9d, ebx; unsigned __int16
0x1800232d8  mov     r8d, 12F9h; unsigned __int16
0x1800232de  lea     rdx, aCsdrestoreimpl_53; "CSdRestoreImpl::ConfigureRestore"
0x1800232e5  lea     rcx, [rbp+var_48]; this
0x1800232e9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800232ee  lea     r14, [rdi+40h]
0x1800232f2  mov     [rbp+var_58], r14
0x1800232f6  mov     rcx, r14; this
0x1800232f9  call    ?Lock@CSdCriticalSection@@QEAAXXZ; CSdCriticalSection::Lock(void)
0x1800232fe  mov     [rbp+var_50], ebx
0x180023301  lea     rcx, [rbp+arg_0]; void *
0x180023305  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18002330a  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180023311  lea     rcx, [rbp+arg_0]
0x180023315  call    ??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)
0x18002331a  mov     ebx, eax
0x18002331c  mov     [rbp+var_48], eax
0x18002331f  test    eax, eax
0x180023321  mov     eax, 1307h
0x180023326  jns     short loc_180023331
0x180023328  mov     [rbp+var_42], ax
0x18002332c  jmp     loc_1800233DA
0x180023331  mov     [rbp+var_44], ax
0x180023335  mov     rbx, [rbp+arg_0]
0x180023339  mov     rcx, [rbx]; pSid
0x18002333c  call    cs:__imp_GetSidSubAuthorityCount
0x180023342  lea     rsi, [rdi+88h]
0x180023349  mov     dl, [rax]
0x18002334b  dec     dl
0x18002334d  movzx   edx, dl; nSubAuthority
0x180023350  mov     rcx, [rbx]; pSid
0x180023353  call    cs:__imp_GetSidSubAuthority
0x180023359  mov     rcx, rsi; this
0x18002335c  cmp     dword ptr [rax], 2000h
0x180023362  jbe     loc_18002341B
0x180023368  lea     rdx, aWindirTemp; "%windir%\\Temp"
0x18002336f  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180023374  mov     ebx, eax
0x180023376  mov     [rbp+var_48], eax
0x180023379  test    eax, eax
0x18002337b  mov     eax, 130Bh
0x180023380  js      short loc_180023328
0x180023382  mov     [rbp+var_44], ax
0x180023386  mov     rcx, rdi; this
0x180023389  call    ?_InitializeRestoreLog@CSdRestoreImpl@@AEAAJXZ; CSdRestoreImpl::_InitializeRestoreLog(void)
0x18002338e  mov     ebx, eax
0x180023390  mov     [rbp+var_48], eax
0x180023393  test    eax, eax
0x180023395  mov     eax, 1312h
0x18002339a  js      short loc_180023328
0x18002339c  mov     [rbp+var_44], ax
0x1800233a0  mov     r9d, r15d; unsigned int
0x1800233a3  mov     r8, r12; unsigned __int16 *
0x1800233a6  mov     rdx, r13; unsigned __int16 *
0x1800233a9  mov     rcx, rdi; this
0x1800233ac  call    ?_ConfigureRestoreHelper@CSdRestoreImpl@@AEAAJPEBG0K@Z; CSdRestoreImpl::_ConfigureRestoreHelper(ushort const *,ushort const *,ulong)
0x1800233b1  mov     ebx, eax
0x1800233b3  mov     [rbp+var_48], eax
0x1800233b6  test    eax, eax
0x1800233b8  mov     eax, 1313h
0x1800233bd  js      loc_180023328
0x1800233c3  mov     [rbp+var_44], ax
0x1800233c7  mov     rcx, r14; lpCriticalSection
0x1800233ca  call    cs:__imp_LeaveCriticalSection
0x1800233d0  mov     [rbp+var_50], 0
0x1800233d7  mov     ebx, [rbp+var_48]
0x1800233da  test    ebx, ebx
0x1800233dc  jns     short loc_1800233ED
0x1800233de  lea     rdx, [rbp+var_48]; struct CSxFunctionTracer *
0x1800233e2  mov     rcx, rdi; this
0x1800233e5  call    ?_SetInternalLastError@CSdRestoreImpl@@AEAAJPEAVCSxFunctionTracer@@@Z; CSdRestoreImpl::_SetInternalLastError(CSxFunctionTracer *)
0x1800233ea  mov     ebx, [rbp+var_48]
0x1800233ed  lea     rcx, [rbp+arg_0]
0x1800233f1  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(void)
0x1800233f6  lea     rcx, [rbp+var_58]; this
0x1800233fa  call    ??1CSdAutomaticLock@@QEAA@XZ; CSdAutomaticLock::~CSdAutomaticLock(void)
0x1800233ff  lea     rcx, [rbp+var_48]; this
0x180023403  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180023408  mov     eax, ebx
0x18002340a  add     rsp, 78h
0x18002340e  pop     r15
0x180023410  pop     r14
0x180023412  pop     r13
0x180023414  pop     r12
0x180023416  pop     rdi
0x180023417  pop     rsi
0x180023418  pop     rbx
0x180023419  pop     rbp
0x18002341a  retn
0x18002341b  lea     rdx, aTemp; "%temp%"
0x180023422  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180023427  mov     ebx, eax
0x180023429  mov     [rbp+var_48], eax
0x18002342c  test    eax, eax
0x18002342e  mov     eax, 130Fh
0x180023433  jmp     loc_180023380
```
