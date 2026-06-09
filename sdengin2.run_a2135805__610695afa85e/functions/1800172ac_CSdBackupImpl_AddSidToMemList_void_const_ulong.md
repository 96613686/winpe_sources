# CSdBackupImpl::_AddSidToMemList(void * const,ulong)

- ea: `0x1800172ac`
- end: `0x180017573`
- name: `?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z`
- size: `711`
- prototype: `int(CSdBackupImpl *__hidden this, void *const, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ee44`
- `0x180021eb8`

## callees

- `0x180015e70`
- `0x180015f90`
- `0x18001627c`
- `0x180016710`
- `0x1800172ac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e8c4`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180017452`
- `KERNEL32!GetLastError` at `0x180017452`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001739a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001739a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017444`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017444`

## string_xrefs

- `0x1800172ec`: `CSdBackupImpl::_AddSidToMemList`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_AddSidToMemList(CSdBackupImpl *this, void *const a2, unsigned int a3)
{
  struct CSdUserSidEntry *v6; // rdi
  int LastFailureAsHRESULT; // ebx
  __int16 v8; // ax
  __int64 v9; // rcx
  BOOL v10; // ebx
  DWORD LastError; // eax
  __int64 v12; // rcx
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v15; // [rsp+44h] [rbp-BCh]
  __int16 v16; // [rsp+46h] [rbp-BAh]
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchReferencedDomainName; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  struct CSdUserSidEntry *v20; // [rsp+88h] [rbp-78h] BYREF
  CSdUserSidEntry *v21; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ReferencedDomainName[20]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Name; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[526]; // [rsp+C2h] [rbp-3Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdBackupImpl::_AddSidToMemList", 0xBDBu, 1u);
  Name = 0;
  memset_0(v24, 0, 0x208u);
  memset(ReferencedDomainName, 0, 32);
  cchName = 261;
  cchReferencedDomainName = 16;
  peUse = 0;
  v21 = 0;
  v6 = 0;
  v20 = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = -2147024809;
    v8 = 3047;
LABEL_3:
    v16 = v8;
    goto LABEL_19;
  }
  v14 = 0;
  v15 = 3047;
  LastFailureAsHRESULT = CSdUserSidEntry::CreateInstance(&v20);
  v14 = LastFailureAsHRESULT;
  v6 = v20;
  v8 = 3049;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v15 = 3049;
  if ( !CopySid(0x44u, *((PSID *)v20 + 13), a2) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v14 = LastFailureAsHRESULT;
    v8 = 3050;
    goto LABEL_3;
  }
  v14 = 0;
  v15 = 3050;
  LastFailureAsHRESULT = CSxList<CSdUserSidList,CSdUserSidEntry>::Find(*((_QWORD *)this + 39) + 8LL, v6, &v21);
  v14 = LastFailureAsHRESULT;
  v8 = 3053;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v15 = 3053;
  if ( !LastFailureAsHRESULT )
  {
    v8 = 3057;
LABEL_10:
    v14 = 0;
    LastFailureAsHRESULT = 0;
    goto LABEL_18;
  }
  v10 = LookupAccountSidW(
          (LPCWSTR)this + 138,
          a2,
          &Name,
          &cchName,
          ReferencedDomainName,
          &cchReferencedDomainName,
          &peUse);
  LastError = GetLastError();
  if ( !v10 )
  {
    if ( LastError != 1332 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
      v14 = LastFailureAsHRESULT;
      v8 = 3068;
      goto LABEL_3;
    }
    v8 = 3066;
    goto LABEL_10;
  }
  v14 = 0;
  v15 = 3068;
  LastFailureAsHRESULT = CBsString::Set((struct CSdUserSidEntry *)((char *)v6 + 8), ReferencedDomainName, L"\\", &Name);
  v14 = LastFailureAsHRESULT;
  v8 = 3071;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v15 = 3071;
  LastFailureAsHRESULT = CSxList<CSdUserSidList,CSdUserSidEntry>::InsertHead(*((_QWORD *)this + 39) + 8LL, v6);
  v14 = LastFailureAsHRESULT;
  v8 = 3072;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v15 = 3072;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, void *const, _QWORD, _QWORD))(**((_QWORD **)this + 74)
                                                                                        + 256LL))(
                           *((_QWORD *)this + 74),
                           a2,
                           a3,
                           *((_QWORD *)v6 + 1));
  v14 = LastFailureAsHRESULT;
  v8 = 3075;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
LABEL_18:
  v15 = v8;
LABEL_19:
  if ( v6 )
    CSdUserSidEntry::Release(v6);
  if ( v21 )
    CSdUserSidEntry::Release(v21);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800172ac  push    rbp
0x1800172ae  push    rbx
0x1800172af  push    rsi
0x1800172b0  push    rdi
0x1800172b1  push    r12
0x1800172b3  push    r14
0x1800172b5  push    r15
0x1800172b7  lea     rbp, [rsp-1E0h]
0x1800172bf  sub     rsp, 2E0h
0x1800172c6  mov     rax, cs:__security_cookie
0x1800172cd  xor     rax, rsp
0x1800172d0  mov     [rbp+210h+var_40], rax
0x1800172d7  mov     r12d, r8d
0x1800172da  mov     r14, rdx
0x1800172dd  mov     rsi, rcx
0x1800172e0  mov     r9d, 1; unsigned __int16
0x1800172e6  mov     r8d, 0BDBh; unsigned __int16
0x1800172ec  lea     rdx, aCsdbackupimplA_5; "CSdBackupImpl::_AddSidToMemList"
0x1800172f3  lea     rcx, [rsp+310h+var_2D0]; this
0x1800172f8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800172fd  xor     eax, eax
0x1800172ff  mov     [rbp+210h+Name], ax
0x180017303  xor     edx, edx; Val
0x180017305  mov     r8d, 208h; Size
0x18001730b  lea     rcx, [rbp+210h+var_24E]; void *
0x18001730f  call    memset_0
0x180017314  xor     eax, eax
0x180017316  mov     [rbp+210h+var_278], ax
0x18001731a  xorps   xmm0, xmm0
0x18001731d  movups  xmmword ptr [rbp+210h+var_276], xmm0
0x180017321  movups  xmmword ptr [rbp+210h+var_276+0Eh], xmm0
0x180017325  mov     [rbp+210h+cchName], 105h
0x18001732c  mov     [rsp+310h+var_294], 10h
0x180017334  mov     [rsp+310h+var_298], eax
0x180017338  mov     [rbp+210h+var_280], rax
0x18001733c  xor     edi, edi
0x18001733e  mov     [rbp+210h+var_288], rdi
0x180017342  test    r14, r14
0x180017345  jnz     short loc_18001735F
0x180017347  mov     ebx, 80070057h
0x18001734c  mov     [rsp+310h+var_2D0], ebx
0x180017350  mov     eax, 0BE7h
0x180017355  mov     [rsp+310h+var_2CA], ax
0x18001735a  jmp     loc_18001752A
0x18001735f  mov     [rsp+310h+var_2D0], eax
0x180017363  mov     eax, 0BE7h
0x180017368  mov     [rsp+310h+var_2CC], ax
0x18001736d  lea     rcx, [rbp+210h+var_288]; struct CSdUserSidEntry **
0x180017371  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x180017376  mov     ebx, eax
0x180017378  mov     [rsp+310h+var_2D0], eax
0x18001737c  mov     rdi, [rbp+210h+var_288]
0x180017380  test    eax, eax
0x180017382  mov     eax, 0BE9h
0x180017387  js      short loc_180017355
0x180017389  mov     [rsp+310h+var_2CC], ax
0x18001738e  mov     r8, r14; pSourceSid
0x180017391  mov     rdx, [rdi+68h]; pDestinationSid
0x180017395  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18001739a  call    cs:__imp_CopySid
0x1800173a1  nop     dword ptr [rax+rax+00h]
0x1800173a6  test    eax, eax
0x1800173a8  jnz     short loc_1800173BC
0x1800173aa  call    GetLastFailureAsHRESULT
0x1800173af  mov     ebx, eax
0x1800173b1  mov     [rsp+310h+var_2D0], eax
0x1800173b5  mov     eax, 0BEAh
0x1800173ba  jmp     short loc_180017355
0x1800173bc  mov     [rsp+310h+var_2D0], 0
0x1800173c4  mov     eax, 0BEAh
0x1800173c9  mov     [rsp+310h+var_2CC], ax
0x1800173ce  mov     rcx, [rsi+138h]
0x1800173d5  add     rcx, 8
0x1800173d9  lea     r8, [rbp+210h+var_280]
0x1800173dd  mov     rdx, rdi
0x1800173e0  call    ?Find@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@PEAPEAV2@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::Find(CSdUserSidEntry *,CSdUserSidEntry * *)
0x1800173e5  mov     ebx, eax
0x1800173e7  mov     [rsp+310h+var_2D0], eax
0x1800173eb  test    eax, eax
0x1800173ed  mov     eax, 0BEDh
0x1800173f2  js      loc_180017355
0x1800173f8  mov     [rsp+310h+var_2CC], ax
0x1800173fd  test    ebx, ebx
0x1800173ff  jnz     short loc_180017415
0x180017401  mov     eax, 0BF1h
0x180017406  mov     [rsp+310h+var_2D0], 0
0x18001740e  xor     ebx, ebx
0x180017410  jmp     loc_180017525
0x180017415  lea     rcx, [rsi+114h]; lpSystemName
0x18001741c  lea     rax, [rsp+310h+var_298]
0x180017421  mov     [rsp+310h+peUse], rax; peUse
0x180017426  lea     rax, [rsp+310h+var_294]
0x18001742b  mov     [rsp+310h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180017430  lea     rax, [rbp+210h+var_278]
0x180017434  mov     [rsp+310h+ReferencedDomainName], rax; ReferencedDomainName
0x180017439  lea     r9, [rbp+210h+cchName]; cchName
0x18001743d  lea     r8, [rbp+210h+Name]; Name
0x180017441  mov     rdx, r14; Sid
0x180017444  call    cs:__imp_LookupAccountSidW
0x18001744b  nop     dword ptr [rax+rax+00h]
0x180017450  mov     ebx, eax
0x180017452  call    cs:__imp_GetLastError
0x180017459  nop     dword ptr [rax+rax+00h]
0x18001745e  test    ebx, ebx
0x180017460  jnz     short loc_180017485
0x180017462  cmp     eax, 534h
0x180017467  jnz     short loc_180017470
0x180017469  mov     eax, 0BFAh
0x18001746e  jmp     short loc_180017406
0x180017470  call    GetLastFailureAsHRESULT
0x180017475  mov     ebx, eax
0x180017477  mov     [rsp+310h+var_2D0], eax
0x18001747b  mov     eax, 0BFCh
0x180017480  jmp     loc_180017355
0x180017485  mov     [rsp+310h+var_2D0], 0
0x18001748d  mov     eax, 0BFCh
0x180017492  mov     [rsp+310h+var_2CC], ax
0x180017497  lea     r9, [rbp+210h+Name]; unsigned __int16 *
0x18001749b  lea     r8, Str; "\\"
0x1800174a2  lea     rdx, [rbp+210h+var_278]; unsigned __int16 *
0x1800174a6  lea     rcx, [rdi+8]; this
0x1800174aa  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x1800174af  mov     ebx, eax
0x1800174b1  mov     [rsp+310h+var_2D0], eax
0x1800174b5  test    eax, eax
0x1800174b7  mov     eax, 0BFFh
0x1800174bc  js      loc_180017355
0x1800174c2  mov     [rsp+310h+var_2CC], ax
0x1800174c7  mov     rcx, [rsi+138h]
0x1800174ce  add     rcx, 8
0x1800174d2  mov     rdx, rdi
0x1800174d5  call    ?InsertHead@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::InsertHead(CSdUserSidEntry *)
0x1800174da  mov     ebx, eax
0x1800174dc  mov     [rsp+310h+var_2D0], eax
0x1800174e0  test    eax, eax
0x1800174e2  mov     eax, 0C00h
0x1800174e7  js      loc_180017355
0x1800174ed  mov     [rsp+310h+var_2CC], ax
0x1800174f2  mov     rcx, [rsi+250h]
0x1800174f9  mov     rax, [rcx]
0x1800174fc  mov     r9, [rdi+8]
0x180017500  mov     r8d, r12d
0x180017503  mov     rdx, r14
0x180017506  mov     rax, [rax+100h]
0x18001750d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017512  mov     ebx, eax
0x180017514  mov     [rsp+310h+var_2D0], eax
0x180017518  test    eax, eax
0x18001751a  mov     eax, 0C03h
0x18001751f  js      loc_180017355
0x180017525  mov     [rsp+310h+var_2CC], ax
0x18001752a  test    rdi, rdi
0x18001752d  jz      short loc_180017537
0x18001752f  mov     rcx, rdi; this
0x180017532  call    ?Release@CSdUserSidEntry@@QEAAKXZ; CSdUserSidEntry::Release(void)
0x180017537  mov     rcx, [rbp+210h+var_280]; this
0x18001753b  test    rcx, rcx
0x18001753e  jz      short loc_180017545
0x180017540  call    ?Release@CSdUserSidEntry@@QEAAKXZ; CSdUserSidEntry::Release(void)
0x180017545  lea     rcx, [rsp+310h+var_2D0]; this
0x18001754a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001754f  mov     eax, ebx
0x180017551  mov     rcx, [rbp+210h+var_40]
0x180017558  xor     rcx, rsp; StackCookie
0x18001755b  call    __security_check_cookie
0x180017560  add     rsp, 2E0h
0x180017567  pop     r15
0x180017569  pop     r14
0x18001756b  pop     r12
0x18001756d  pop     rdi
0x18001756e  pop     rsi
0x18001756f  pop     rbx
0x180017570  pop     rbp
0x180017571  retn
```
