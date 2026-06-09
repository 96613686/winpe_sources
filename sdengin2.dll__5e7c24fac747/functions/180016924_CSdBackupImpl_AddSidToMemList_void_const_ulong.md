# CSdBackupImpl::_AddSidToMemList(void * const,ulong)

- ea: `0x180016924`
- end: `0x180016bd8`
- name: `?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z`
- size: `692`
- prototype: `__int64 __fastcall(CSdBackupImpl *this, void *const, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e33c`
- `0x1800212c4`

## callees

- `0x180015534`
- `0x180015654`
- `0x180015934`
- `0x180015dac`
- `0x180016924`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a20c`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016abe`
- `KERNEL32!GetLastError` at `0x180016abe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016a12`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016a12`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180016ab6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180016ab6`

## string_xrefs

- `0x180016964`: `CSdBackupImpl::_AddSidToMemList`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdBackupImpl::_AddSidToMemList", 3035, 1);
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
0x180016924  push    rbp
0x180016926  push    rbx
0x180016927  push    rsi
0x180016928  push    rdi
0x180016929  push    r12
0x18001692b  push    r14
0x18001692d  push    r15
0x18001692f  lea     rbp, [rsp-1E0h]
0x180016937  sub     rsp, 2E0h
0x18001693e  mov     rax, cs:__security_cookie
0x180016945  xor     rax, rsp
0x180016948  mov     [rbp+210h+var_40], rax
0x18001694f  mov     r12d, r8d
0x180016952  mov     r14, rdx
0x180016955  mov     rsi, rcx
0x180016958  mov     r9d, 1; unsigned __int16
0x18001695e  mov     r8d, 0BDBh; unsigned __int16
0x180016964  lea     rdx, aCsdbackupimplA_5; "CSdBackupImpl::_AddSidToMemList"
0x18001696b  lea     rcx, [rsp+310h+var_2D0]; this
0x180016970  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016975  xor     eax, eax
0x180016977  mov     [rbp+210h+Name], ax
0x18001697b  xor     edx, edx; Val
0x18001697d  mov     r8d, 208h; Size
0x180016983  lea     rcx, [rbp+210h+var_24E]; void *
0x180016987  call    memset_0
0x18001698c  xor     eax, eax
0x18001698e  mov     [rbp+210h+var_278], ax
0x180016992  xorps   xmm0, xmm0
0x180016995  movups  xmmword ptr [rbp+210h+var_276], xmm0
0x180016999  movups  xmmword ptr [rbp+210h+var_276+0Eh], xmm0
0x18001699d  mov     [rbp+210h+cchName], 105h
0x1800169a4  mov     [rsp+310h+var_294], 10h
0x1800169ac  mov     [rsp+310h+var_298], eax
0x1800169b0  mov     [rbp+210h+var_280], rax
0x1800169b4  xor     edi, edi
0x1800169b6  mov     [rbp+210h+var_288], rdi
0x1800169ba  test    r14, r14
0x1800169bd  jnz     short loc_1800169D7
0x1800169bf  mov     ebx, 80070057h
0x1800169c4  mov     [rsp+310h+var_2D0], ebx
0x1800169c8  mov     eax, 0BE7h
0x1800169cd  mov     [rsp+310h+var_2CA], ax
0x1800169d2  jmp     loc_180016B90
0x1800169d7  mov     [rsp+310h+var_2D0], eax
0x1800169db  mov     eax, 0BE7h
0x1800169e0  mov     [rsp+310h+var_2CC], ax
0x1800169e5  lea     rcx, [rbp+210h+var_288]; struct CSdUserSidEntry **
0x1800169e9  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x1800169ee  mov     ebx, eax
0x1800169f0  mov     [rsp+310h+var_2D0], eax
0x1800169f4  mov     rdi, [rbp+210h+var_288]
0x1800169f8  test    eax, eax
0x1800169fa  mov     eax, 0BE9h
0x1800169ff  js      short loc_1800169CD
0x180016a01  mov     [rsp+310h+var_2CC], ax
0x180016a06  mov     r8, r14; pSourceSid
0x180016a09  mov     rdx, [rdi+68h]; pDestinationSid
0x180016a0d  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180016a12  call    cs:__imp_CopySid
0x180016a18  test    eax, eax
0x180016a1a  jnz     short loc_180016A2E
0x180016a1c  call    GetLastFailureAsHRESULT
0x180016a21  mov     ebx, eax
0x180016a23  mov     [rsp+310h+var_2D0], eax
0x180016a27  mov     eax, 0BEAh
0x180016a2c  jmp     short loc_1800169CD
0x180016a2e  mov     [rsp+310h+var_2D0], 0
0x180016a36  mov     eax, 0BEAh
0x180016a3b  mov     [rsp+310h+var_2CC], ax
0x180016a40  mov     rcx, [rsi+138h]
0x180016a47  add     rcx, 8
0x180016a4b  lea     r8, [rbp+210h+var_280]
0x180016a4f  mov     rdx, rdi
0x180016a52  call    ?Find@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@PEAPEAV2@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::Find(CSdUserSidEntry *,CSdUserSidEntry * *)
0x180016a57  mov     ebx, eax
0x180016a59  mov     [rsp+310h+var_2D0], eax
0x180016a5d  test    eax, eax
0x180016a5f  mov     eax, 0BEDh
0x180016a64  js      loc_1800169CD
0x180016a6a  mov     [rsp+310h+var_2CC], ax
0x180016a6f  test    ebx, ebx
0x180016a71  jnz     short loc_180016A87
0x180016a73  mov     eax, 0BF1h
0x180016a78  mov     [rsp+310h+var_2D0], 0
0x180016a80  xor     ebx, ebx
0x180016a82  jmp     loc_180016B8B
0x180016a87  lea     rcx, [rsi+114h]; lpSystemName
0x180016a8e  lea     rax, [rsp+310h+var_298]
0x180016a93  mov     [rsp+310h+peUse], rax; peUse
0x180016a98  lea     rax, [rsp+310h+var_294]
0x180016a9d  mov     [rsp+310h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180016aa2  lea     rax, [rbp+210h+var_278]
0x180016aa6  mov     [rsp+310h+ReferencedDomainName], rax; ReferencedDomainName
0x180016aab  lea     r9, [rbp+210h+cchName]; cchName
0x180016aaf  lea     r8, [rbp+210h+Name]; Name
0x180016ab3  mov     rdx, r14; Sid
0x180016ab6  call    cs:__imp_LookupAccountSidW
0x180016abc  mov     ebx, eax
0x180016abe  call    cs:__imp_GetLastError
0x180016ac4  test    ebx, ebx
0x180016ac6  jnz     short loc_180016AEB
0x180016ac8  cmp     eax, 534h
0x180016acd  jnz     short loc_180016AD6
0x180016acf  mov     eax, 0BFAh
0x180016ad4  jmp     short loc_180016A78
0x180016ad6  call    GetLastFailureAsHRESULT
0x180016adb  mov     ebx, eax
0x180016add  mov     [rsp+310h+var_2D0], eax
0x180016ae1  mov     eax, 0BFCh
0x180016ae6  jmp     loc_1800169CD
0x180016aeb  mov     [rsp+310h+var_2D0], 0
0x180016af3  mov     eax, 0BFCh
0x180016af8  mov     [rsp+310h+var_2CC], ax
0x180016afd  lea     r9, [rbp+210h+Name]; unsigned __int16 *
0x180016b01  lea     r8, Str; "\\"
0x180016b08  lea     rdx, [rbp+210h+var_278]; unsigned __int16 *
0x180016b0c  lea     rcx, [rdi+8]; this
0x180016b10  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180016b15  mov     ebx, eax
0x180016b17  mov     [rsp+310h+var_2D0], eax
0x180016b1b  test    eax, eax
0x180016b1d  mov     eax, 0BFFh
0x180016b22  js      loc_1800169CD
0x180016b28  mov     [rsp+310h+var_2CC], ax
0x180016b2d  mov     rcx, [rsi+138h]
0x180016b34  add     rcx, 8
0x180016b38  mov     rdx, rdi
0x180016b3b  call    ?InsertHead@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::InsertHead(CSdUserSidEntry *)
0x180016b40  mov     ebx, eax
0x180016b42  mov     [rsp+310h+var_2D0], eax
0x180016b46  test    eax, eax
0x180016b48  mov     eax, 0C00h
0x180016b4d  js      loc_1800169CD
0x180016b53  mov     [rsp+310h+var_2CC], ax
0x180016b58  mov     rcx, [rsi+250h]
0x180016b5f  mov     rax, [rcx]
0x180016b62  mov     r9, [rdi+8]
0x180016b66  mov     r8d, r12d
0x180016b69  mov     rdx, r14
0x180016b6c  mov     rax, [rax+100h]
0x180016b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b78  mov     ebx, eax
0x180016b7a  mov     [rsp+310h+var_2D0], eax
0x180016b7e  test    eax, eax
0x180016b80  mov     eax, 0C03h
0x180016b85  js      loc_1800169CD
0x180016b8b  mov     [rsp+310h+var_2CC], ax
0x180016b90  test    rdi, rdi
0x180016b93  jz      short loc_180016B9D
0x180016b95  mov     rcx, rdi; this
0x180016b98  call    ?Release@CSdUserSidEntry@@QEAAKXZ; CSdUserSidEntry::Release(void)
0x180016b9d  mov     rcx, [rbp+210h+var_280]; this
0x180016ba1  test    rcx, rcx
0x180016ba4  jz      short loc_180016BAB
0x180016ba6  call    ?Release@CSdUserSidEntry@@QEAAKXZ; CSdUserSidEntry::Release(void)
0x180016bab  lea     rcx, [rsp+310h+var_2D0]; this
0x180016bb0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180016bb5  mov     eax, ebx
0x180016bb7  mov     rcx, [rbp+210h+var_40]
0x180016bbe  xor     rcx, rsp; StackCookie
0x180016bc1  call    __security_check_cookie
0x180016bc6  add     rsp, 2E0h
0x180016bcd  pop     r15
0x180016bcf  pop     r14
0x180016bd1  pop     r12
0x180016bd3  pop     rdi
0x180016bd4  pop     rsi
0x180016bd5  pop     rbx
0x180016bd6  pop     rbp
0x180016bd7  retn
```
