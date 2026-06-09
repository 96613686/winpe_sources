# CSdRestoreImpl::ConfigureRestore(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180024070`
- end: `0x18002420b`
- name: `?ConfigureRestore@CSdRestoreImpl@@UEAAJPEBG0K0@Z`
- size: `411`
- prototype: `__int64 __fastcall(CSdRestoreImpl *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003520`
- `0x180022780`
- `0x180022c0c`
- `0x180022c34`
- `0x180024070`
- `0x18002935c`
- `0x18002af08`
- `0x180031ddc`
- `0x180072e08`
- `0x180072f14`
- `0x18009e24c`
- `0x1800bbfe0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024196`
- `KERNEL32!LeaveCriticalSection` at `0x180024196`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024119`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024119`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800240fc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800240fc`

## string_xrefs

- `0x18002409e`: `CSdRestoreImpl::ConfigureRestore`
- `0x180024134`: `%windir%\Temp`
- `0x1800241ee`: `%temp%`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::ConfigureRestore(
        CSdRestoreImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
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
0x180024070  push    rbp
0x180024072  push    rbx
0x180024073  push    rsi
0x180024074  push    rdi
0x180024075  push    r12
0x180024077  push    r13
0x180024079  push    r14
0x18002407b  push    r15
0x18002407d  mov     rbp, rsp
0x180024080  sub     rsp, 78h
0x180024084  mov     r15d, r9d
0x180024087  mov     r12, r8
0x18002408a  mov     r13, rdx
0x18002408d  mov     rdi, rcx
0x180024090  mov     ebx, 1
0x180024095  mov     r9d, ebx; unsigned __int16
0x180024098  mov     r8d, 12F9h; unsigned __int16
0x18002409e  lea     rdx, aCsdrestoreimpl_53; "CSdRestoreImpl::ConfigureRestore"
0x1800240a5  lea     rcx, [rbp+var_48]; this
0x1800240a9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800240ae  lea     r14, [rdi+40h]
0x1800240b2  mov     [rbp+var_58], r14
0x1800240b6  mov     rcx, r14; this
0x1800240b9  call    ?Lock@CSdCriticalSection@@QEAAXXZ; CSdCriticalSection::Lock(void)
0x1800240be  mov     [rbp+var_50], ebx
0x1800240c1  lea     rcx, [rbp+arg_0]; void *
0x1800240c5  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x1800240ca  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x1800240d1  lea     rcx, [rbp+arg_0]
0x1800240d5  call    ??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)
0x1800240da  mov     ebx, eax
0x1800240dc  mov     [rbp+var_48], eax
0x1800240df  test    eax, eax
0x1800240e1  mov     eax, 1307h
0x1800240e6  jns     short loc_1800240F1
0x1800240e8  mov     [rbp+var_42], ax
0x1800240ec  jmp     loc_1800241AC
0x1800240f1  mov     [rbp+var_44], ax
0x1800240f5  mov     rbx, [rbp+arg_0]
0x1800240f9  mov     rcx, [rbx]; pSid
0x1800240fc  call    cs:__imp_GetSidSubAuthorityCount
0x180024103  nop     dword ptr [rax+rax+00h]
0x180024108  lea     rsi, [rdi+88h]
0x18002410f  mov     dl, [rax]
0x180024111  dec     dl
0x180024113  movzx   edx, dl; nSubAuthority
0x180024116  mov     rcx, [rbx]; pSid
0x180024119  call    cs:__imp_GetSidSubAuthority
0x180024120  nop     dword ptr [rax+rax+00h]
0x180024125  mov     rcx, rsi; this
0x180024128  cmp     dword ptr [rax], 2000h
0x18002412e  jbe     loc_1800241EE
0x180024134  lea     rdx, aWindirTemp; "%windir%\\Temp"
0x18002413b  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180024140  mov     ebx, eax
0x180024142  mov     [rbp+var_48], eax
0x180024145  test    eax, eax
0x180024147  mov     eax, 130Bh
0x18002414c  js      short loc_1800240E8
0x18002414e  mov     [rbp+var_44], ax
0x180024152  mov     rcx, rdi; this
0x180024155  call    ?_InitializeRestoreLog@CSdRestoreImpl@@AEAAJXZ; CSdRestoreImpl::_InitializeRestoreLog(void)
0x18002415a  mov     ebx, eax
0x18002415c  mov     [rbp+var_48], eax
0x18002415f  test    eax, eax
0x180024161  mov     eax, 1312h
0x180024166  js      short loc_1800240E8
0x180024168  mov     [rbp+var_44], ax
0x18002416c  mov     r9d, r15d; unsigned int
0x18002416f  mov     r8, r12; unsigned __int16 *
0x180024172  mov     rdx, r13; unsigned __int16 *
0x180024175  mov     rcx, rdi; this
0x180024178  call    ?_ConfigureRestoreHelper@CSdRestoreImpl@@AEAAJPEBG0K@Z; CSdRestoreImpl::_ConfigureRestoreHelper(ushort const *,ushort const *,ulong)
0x18002417d  mov     ebx, eax
0x18002417f  mov     [rbp+var_48], eax
0x180024182  test    eax, eax
0x180024184  mov     eax, 1313h
0x180024189  js      loc_1800240E8
0x18002418f  mov     [rbp+var_44], ax
0x180024193  mov     rcx, r14; lpCriticalSection
0x180024196  call    cs:__imp_LeaveCriticalSection
0x18002419d  nop     dword ptr [rax+rax+00h]
0x1800241a2  mov     [rbp+var_50], 0
0x1800241a9  mov     ebx, [rbp+var_48]
0x1800241ac  test    ebx, ebx
0x1800241ae  jns     short loc_1800241BF
0x1800241b0  lea     rdx, [rbp+var_48]; struct CSxFunctionTracer *
0x1800241b4  mov     rcx, rdi; this
0x1800241b7  call    ?_SetInternalLastError@CSdRestoreImpl@@AEAAJPEAVCSxFunctionTracer@@@Z; CSdRestoreImpl::_SetInternalLastError(CSxFunctionTracer *)
0x1800241bc  mov     ebx, [rbp+var_48]
0x1800241bf  lea     rcx, [rbp+arg_0]
0x1800241c3  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter>(void)
0x1800241c8  lea     rcx, [rbp+var_58]; this
0x1800241cc  call    ??1CSdAutomaticLock@@QEAA@XZ; CSdAutomaticLock::~CSdAutomaticLock(void)
0x1800241d1  lea     rcx, [rbp+var_48]; this
0x1800241d5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800241da  mov     eax, ebx
0x1800241dc  add     rsp, 78h
0x1800241e0  pop     r15
0x1800241e2  pop     r14
0x1800241e4  pop     r13
0x1800241e6  pop     r12
0x1800241e8  pop     rdi
0x1800241e9  pop     rsi
0x1800241ea  pop     rbx
0x1800241eb  pop     rbp
0x1800241ec  retn
0x1800241ee  lea     rdx, aTemp; "%temp%"
0x1800241f5  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x1800241fa  mov     ebx, eax
0x1800241fc  mov     [rbp+var_48], eax
0x1800241ff  test    eax, eax
0x180024201  mov     eax, 130Fh
0x180024206  jmp     loc_18002414C
```
