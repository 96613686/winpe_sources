# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x1800214a4`
- end: `0x180021718`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `628`
- prototype: `int(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021fa4`

## callees

- `0x1800214a4`
- `0x180022520`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180021540`
- `msvcrt!wcspbrk` at `0x180021540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002161d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002161d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021634`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021652`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021679`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002169c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021652`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180021679`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002169c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216ac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216b6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216c4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216ce`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216e6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216ac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216b6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216c4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216ce`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800216e6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180021684`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180021684`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215c0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215d3`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215c0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215d3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800215a0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180021613`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800215a0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180021613`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::DetermineUserAndDomain(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct STRU *a4,
        struct STRU *a5,
        int *a6)
{
  int v9; // r15d
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  signed int v12; // eax
  unsigned int v13; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v15; // rbx
  __int64 v16; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-69h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-65h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v21[4]; // [rsp+50h] [rbp-59h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+70h] [rbp-39h]
  unsigned int v23; // [rsp+78h] [rbp-31h]
  __int16 v24; // [rsp+7Ch] [rbp-2Dh]
  _QWORD v25[4]; // [rsp+80h] [rbp-29h] BYREF
  PSID Sid; // [rsp+A0h] [rbp-9h]
  DWORD v27; // [rsp+A8h] [rbp-1h]
  __int16 v28; // [rsp+ACh] [rbp+3h]

  Sid = v25;
  v25[0] = 0;
  v28 = 256;
  v21[0] = 0;
  ReferencedDomainName = (LPWSTR)v21;
  v27 = 32;
  v9 = 1;
  v23 = 32;
  v24 = 256;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( a4 && a5 && a6 )
  {
    v10 = wcspbrk(a2, L"/\\");
    v11 = v10;
    if ( v10 )
    {
      v16 = v10 - a2;
      if ( (_DWORD)v16 )
        LastError = STRU::Copy(a5, a2, v16);
      else
        LastError = STRU::Copy(a5, L".");
      if ( LastError < 0 )
        goto LABEL_25;
      v15 = v11 + 1;
    }
    else
    {
      v9 = 0;
      if ( *(_WORD *)this == 92 && !*((_WORD *)this + 1) )
      {
        cbSid = v27;
        cchReferencedDomainName = v23 >> 1;
        if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          if ( GetLastError() != 122
            || !BUFFER::Resize((BUFFER *)v25, cbSid)
            || !BUFFER::Resize((BUFFER *)v21, 2 * cchReferencedDomainName) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_25;
          }
          cbSid = v27;
          cchReferencedDomainName = v23 >> 1;
          if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            v12 = GetLastError();
            v13 = v12;
            if ( v12 > 0 )
              v13 = (unsigned __int16)v12 | 0x80070000;
            goto LABEL_26;
          }
        }
        this = (IIS_LOGON_PROVIDER *)ReferencedDomainName;
      }
      LastError = STRU::Copy(a5, (const unsigned __int16 *)this);
      if ( LastError < 0 )
      {
LABEL_25:
        v13 = LastError;
LABEL_26:
        BUFFER::~BUFFER((BUFFER *)v21);
        BUFFER::~BUFFER((BUFFER *)v25);
        return v13;
      }
      v15 = a2;
    }
    *a6 = v9;
    LastError = STRU::Copy(a4, v15);
    if ( LastError < 0 )
      goto LABEL_25;
    BUFFER::~BUFFER((BUFFER *)v21);
    BUFFER::~BUFFER((BUFFER *)v25);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v21);
    BUFFER::~BUFFER((BUFFER *)v25);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800214a4  mov     [rsp-8+arg_10], rbx
0x1800214a9  push    rbp
0x1800214aa  push    rsi
0x1800214ab  push    rdi
0x1800214ac  push    r12
0x1800214ae  push    r13
0x1800214b0  push    r14
0x1800214b2  push    r15
0x1800214b4  lea     rbp, [rsp-17h]
0x1800214b9  sub     rsp, 0C0h
0x1800214c0  mov     rax, cs:__security_cookie
0x1800214c7  xor     rax, rsp
0x1800214ca  mov     [rbp+47h+var_40], rax
0x1800214ce  mov     r14, [rbp+47h+arg_20]
0x1800214d2  lea     rax, [rbp+47h+var_70]
0x1800214d6  mov     r12, [rbp+47h+arg_28]
0x1800214da  mov     rsi, rdx
0x1800214dd  xor     edx, edx
0x1800214df  mov     [rbp+47h+Sid], rax
0x1800214e3  mov     [rbp+47h+var_70], rdx
0x1800214e7  mov     rdi, rcx
0x1800214ea  mov     [rbp+47h+var_44], 100h
0x1800214f0  lea     rax, [rbp+47h+var_A0]
0x1800214f4  mov     [rbp+47h+var_A0], rdx
0x1800214f8  mov     r13, r9
0x1800214fb  mov     [rbp+47h+var_80], rax
0x1800214ff  lea     ecx, [rdx+20h]
0x180021502  mov     [rbp+47h+var_48], ecx
0x180021505  lea     r15d, [rdx+1]
0x180021509  mov     [rbp+47h+var_78], ecx
0x18002150c  mov     [rbp+47h+var_74], 100h
0x180021512  mov     [rbp+47h+cbSid], edx
0x180021515  mov     [rbp+47h+var_B0], edx
0x180021518  mov     [rbp+47h+var_A8], edx
0x18002151b  test    r9, r9
0x18002151e  jz      loc_1800216D8
0x180021524  test    r14, r14
0x180021527  jz      loc_1800216D8
0x18002152d  test    r12, r12
0x180021530  jz      loc_1800216D8
0x180021536  lea     rdx, Control; "/\\"
0x18002153d  mov     rcx, rsi; String
0x180021540  call    cs:__imp_wcspbrk
0x180021546  mov     rbx, rax
0x180021549  test    rax, rax
0x18002154c  jnz     loc_180021661
0x180021552  xor     r15d, r15d
0x180021555  cmp     word ptr [rdi], 5Ch ; '\'
0x180021559  jnz     loc_18002164C
0x18002155f  cmp     [rdi+2], r15w
0x180021564  jnz     loc_18002164C
0x18002156a  mov     eax, [rbp+47h+var_48]
0x18002156d  lea     rcx, [rbp+47h+var_A8]
0x180021571  mov     r8, [rbp+47h+Sid]; Sid
0x180021575  lea     r9, [rbp+47h+cbSid]; cbSid
0x180021579  mov     [rsp+0F0h+peUse], rcx; peUse
0x18002157e  mov     rdx, rsi; lpAccountName
0x180021581  mov     [rbp+47h+cbSid], eax
0x180021584  lea     rcx, [rbp+47h+var_B0]
0x180021588  mov     eax, [rbp+47h+var_78]
0x18002158b  shr     eax, 1
0x18002158d  mov     [rsp+0F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180021592  xor     ecx, ecx; lpSystemName
0x180021594  mov     [rbp+47h+var_B0], eax
0x180021597  mov     rax, [rbp+47h+var_80]
0x18002159b  mov     [rsp+0F0h+ReferencedDomainName], rax; ReferencedDomainName
0x1800215a0  call    cs:__imp_LookupAccountNameW
0x1800215a6  test    eax, eax
0x1800215a8  jnz     loc_180021648
0x1800215ae  call    cs:__imp_GetLastError
0x1800215b4  cmp     eax, 7Ah ; 'z'
0x1800215b7  jnz     short loc_180021634
0x1800215b9  mov     edx, [rbp+47h+cbSid]
0x1800215bc  lea     rcx, [rbp+47h+var_70]
0x1800215c0  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800215c6  test    al, al
0x1800215c8  jz      short loc_180021634
0x1800215ca  mov     edx, [rbp+47h+var_B0]
0x1800215cd  lea     rcx, [rbp+47h+var_A0]
0x1800215d1  add     edx, edx
0x1800215d3  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800215d9  test    al, al
0x1800215db  jz      short loc_180021634
0x1800215dd  mov     eax, [rbp+47h+var_48]
0x1800215e0  lea     rcx, [rbp+47h+var_A8]
0x1800215e4  mov     r8, [rbp+47h+Sid]; Sid
0x1800215e8  lea     r9, [rbp+47h+cbSid]; cbSid
0x1800215ec  mov     [rsp+0F0h+peUse], rcx; peUse
0x1800215f1  mov     rdx, rsi; lpAccountName
0x1800215f4  mov     [rbp+47h+cbSid], eax
0x1800215f7  lea     rcx, [rbp+47h+var_B0]
0x1800215fb  mov     eax, [rbp+47h+var_78]
0x1800215fe  shr     eax, 1
0x180021600  mov     [rsp+0F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180021605  xor     ecx, ecx; lpSystemName
0x180021607  mov     [rbp+47h+var_B0], eax
0x18002160a  mov     rax, [rbp+47h+var_80]
0x18002160e  mov     [rsp+0F0h+ReferencedDomainName], rax; ReferencedDomainName
0x180021613  call    cs:__imp_LookupAccountNameW
0x180021619  test    eax, eax
0x18002161b  jnz     short loc_180021648
0x18002161d  call    cs:__imp_GetLastError
0x180021623  mov     ebx, eax
0x180021625  test    eax, eax
0x180021627  jle     short loc_1800216A8
0x180021629  movzx   ebx, ax
0x18002162c  or      ebx, 80070000h
0x180021632  jmp     short loc_1800216A8
0x180021634  call    cs:__imp_GetLastError
0x18002163a  test    eax, eax
0x18002163c  jle     short loc_1800216A6
0x18002163e  movzx   eax, ax
0x180021641  or      eax, 80070000h
0x180021646  jmp     short loc_1800216A6
0x180021648  mov     rdi, [rbp+47h+var_80]
0x18002164c  mov     rdx, rdi
0x18002164f  mov     rcx, r14
0x180021652  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180021658  test    eax, eax
0x18002165a  js      short loc_1800216A6
0x18002165c  mov     rbx, rsi
0x18002165f  jmp     short loc_180021692
0x180021661  mov     r8, rbx
0x180021664  mov     rcx, r14
0x180021667  sub     r8, rsi
0x18002166a  sar     r8, 1
0x18002166d  test    r8d, r8d
0x180021670  jnz     short loc_180021681
0x180021672  lea     rdx, asc_180027680; "."
0x180021679  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002167f  jmp     short loc_18002168A
0x180021681  mov     rdx, rsi
0x180021684  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002168a  test    eax, eax
0x18002168c  js      short loc_1800216A6
0x18002168e  add     rbx, 2
0x180021692  mov     rdx, rbx
0x180021695  mov     [r12], r15d
0x180021699  mov     rcx, r13
0x18002169c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800216a2  test    eax, eax
0x1800216a4  jns     short loc_1800216C0
0x1800216a6  mov     ebx, eax
0x1800216a8  lea     rcx, [rbp+47h+var_A0]
0x1800216ac  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216b2  lea     rcx, [rbp+47h+var_70]
0x1800216b6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216bc  mov     eax, ebx
0x1800216be  jmp     short loc_1800216F1
0x1800216c0  lea     rcx, [rbp+47h+var_A0]
0x1800216c4  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216ca  lea     rcx, [rbp+47h+var_70]
0x1800216ce  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216d4  xor     eax, eax
0x1800216d6  jmp     short loc_1800216F1
0x1800216d8  lea     rcx, [rbp+47h+var_A0]
0x1800216dc  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216e2  lea     rcx, [rbp+47h+var_70]
0x1800216e6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800216ec  mov     eax, 80070057h
0x1800216f1  mov     rcx, [rbp+47h+var_40]
0x1800216f5  xor     rcx, rsp; StackCookie
0x1800216f8  call    __security_check_cookie
0x1800216fd  mov     rbx, [rsp+0F0h+arg_10]
0x180021705  add     rsp, 0C0h
0x18002170c  pop     r15
0x18002170e  pop     r14
0x180021710  pop     r13
0x180021712  pop     r12
0x180021714  pop     rdi
0x180021715  pop     rsi
0x180021716  pop     rbp
0x180021717  retn
```
