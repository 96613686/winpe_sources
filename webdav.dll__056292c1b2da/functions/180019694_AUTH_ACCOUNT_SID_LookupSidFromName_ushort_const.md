# AUTH_ACCOUNT_SID::LookupSidFromName(ushort const *)

- ea: `0x180019694`
- end: `0x18001984e`
- name: `?LookupSidFromName@AUTH_ACCOUNT_SID@@QEAAJPEBG@Z`
- size: `442`
- prototype: `int(AUTH_ACCOUNT_SID *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800021c4`

## callees

- `0x180019694`
- `0x180022520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001971b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001971b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197c1`
- `iisutil!PuDbgPrintError` at `0x18001980f`
- `iisutil!PuDbgPrintError` at `0x18001980f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800196ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800196ca`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019825`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019825`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180019759`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180019785`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180019759`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180019785`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001970d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800197b7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001970d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800197b7`

## string_xrefs

- `0x1800197f8`: `AUTH_ACCOUNT_SID::LookupSidFromName`

## pseudocode

```c
__int64 __fastcall AUTH_ACCOUNT_SID::LookupSidFromName(AUTH_ACCOUNT_SID *this, const unsigned __int16 *a2)
{
  void *v4; // r8
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  signed int v8; // eax
  signed int v9; // eax
  DWORD cbSid; // [rsp+40h] [rbp+7h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp+Bh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp+Fh] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp+17h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+70h] [rbp+37h]
  unsigned int v16; // [rsp+78h] [rbp+3Fh]

  cbSid = 0;
  STRU::STRU((STRU *)v14);
  v4 = (void *)*((_QWORD *)this + 4);
  cbSid = *((_DWORD *)this + 10);
  cchReferencedDomainName = v16 >> 1;
  peUse = 0;
  if ( LookupAccountNameW(0, a2, v4, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_18;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v7 = 241;
LABEL_17:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\auth_util.cxx",
        v7,
        "AUTH_ACCOUNT_SID::LookupSidFromName",
        v6,
        "Failed to Lookup account %S (LookupAccountNameW() failed)\n",
        a2);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( !BUFFER::Resize(this, cbSid) || BUFFER::Resize((BUFFER *)v14, 2 * cchReferencedDomainName) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v6 = v8;
    goto LABEL_19;
  }
  if ( LookupAccountNameW(0, a2, *((PSID *)this + 4), &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
LABEL_18:
    *((_QWORD *)this + 6) = *((_QWORD *)this + 4);
    v6 = 0;
    goto LABEL_19;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = 285;
    goto LABEL_17;
  }
LABEL_19:
  STRU::~STRU((STRU *)v14);
  return v6;
}

```

## disassembly

```asm
0x180019694  mov     [rsp-8+arg_10], rbx
0x180019699  mov     [rsp-8+arg_18], rdi
0x18001969e  push    rbp
0x18001969f  lea     rbp, [rsp-57h]
0x1800196a4  sub     rsp, 90h
0x1800196ab  mov     rax, cs:__security_cookie
0x1800196b2  xor     rax, rsp
0x1800196b5  mov     [rbp+57h+var_8], rax
0x1800196b9  mov     rbx, rcx
0x1800196bc  mov     [rbp+57h+cbSid], 0
0x1800196c3  lea     rcx, [rbp+57h+var_40]
0x1800196c7  mov     rdi, rdx
0x1800196ca  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800196d0  mov     eax, [rbx+28h]
0x1800196d3  lea     rcx, [rbp+57h+var_48]
0x1800196d7  mov     r8, [rbx+20h]; Sid
0x1800196db  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800196df  mov     [rsp+90h+peUse], rcx; peUse
0x1800196e4  mov     rdx, rdi; lpAccountName
0x1800196e7  mov     [rbp+57h+cbSid], eax
0x1800196ea  lea     rcx, [rbp+57h+var_4C]
0x1800196ee  mov     eax, [rbp+57h+var_18]
0x1800196f1  shr     eax, 1
0x1800196f3  mov     [rsp+90h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800196f8  xor     ecx, ecx; lpSystemName
0x1800196fa  mov     [rbp+57h+var_4C], eax
0x1800196fd  mov     rax, [rbp+57h+var_20]
0x180019701  mov     [rsp+90h+ReferencedDomainName], rax; ReferencedDomainName
0x180019706  mov     [rbp+57h+var_48], 0
0x18001970d  call    cs:__imp_LookupAccountNameW
0x180019713  test    eax, eax
0x180019715  jnz     loc_180019817
0x18001971b  call    cs:__imp_GetLastError
0x180019721  cmp     eax, 7Ah ; 'z'
0x180019724  jz      short loc_180019753
0x180019726  call    cs:__imp_GetLastError
0x18001972c  mov     ebx, eax
0x18001972e  test    eax, eax
0x180019730  jle     short loc_18001973B
0x180019732  movzx   ebx, ax
0x180019735  or      ebx, 80070000h
0x18001973b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019742  jz      loc_180019821
0x180019748  mov     r8d, 0F1h
0x18001974e  jmp     loc_1800197E5
0x180019753  mov     edx, [rbp+57h+cbSid]
0x180019756  mov     rcx, rbx
0x180019759  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001975f  test    al, al
0x180019761  jnz     short loc_18001977C
0x180019763  call    cs:__imp_GetLastError
0x180019769  test    eax, eax
0x18001976b  jle     short loc_180019775
0x18001976d  movzx   eax, ax
0x180019770  or      eax, 80070000h
0x180019775  mov     ebx, eax
0x180019777  jmp     loc_180019821
0x18001977c  mov     edx, [rbp+57h+var_4C]
0x18001977f  lea     rcx, [rbp+57h+var_40]
0x180019783  add     edx, edx
0x180019785  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001978b  test    al, al
0x18001978d  jnz     short loc_180019763
0x18001978f  mov     rax, [rbp+57h+var_20]
0x180019793  lea     rcx, [rbp+57h+var_48]
0x180019797  mov     r8, [rbx+20h]; Sid
0x18001979b  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001979f  mov     [rsp+90h+peUse], rcx; peUse
0x1800197a4  mov     rdx, rdi; lpAccountName
0x1800197a7  lea     rcx, [rbp+57h+var_4C]
0x1800197ab  mov     [rsp+90h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800197b0  xor     ecx, ecx; lpSystemName
0x1800197b2  mov     [rsp+90h+ReferencedDomainName], rax; ReferencedDomainName
0x1800197b7  call    cs:__imp_LookupAccountNameW
0x1800197bd  test    eax, eax
0x1800197bf  jnz     short loc_180019817
0x1800197c1  call    cs:__imp_GetLastError
0x1800197c7  mov     ebx, eax
0x1800197c9  test    eax, eax
0x1800197cb  jle     short loc_1800197D6
0x1800197cd  movzx   ebx, ax
0x1800197d0  or      ebx, 80070000h
0x1800197d6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800197dd  jz      short loc_180019821
0x1800197df  mov     r8d, 11Dh
0x1800197e5  mov     rcx, cs:g_pDebug
0x1800197ec  lea     rax, aFailedToLookup; "Failed to Lookup account %S (LookupAcco"...
0x1800197f3  mov     [rsp+90h+peUse], rdi
0x1800197f8  lea     r9, aAuthAccountSid; "AUTH_ACCOUNT_SID::LookupSidFromName"
0x1800197ff  mov     [rsp+90h+cchReferencedDomainName], rax
0x180019804  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001980b  mov     dword ptr [rsp+90h+ReferencedDomainName], ebx
0x18001980f  call    cs:__imp_PuDbgPrintError
0x180019815  jmp     short loc_180019821
0x180019817  mov     rax, [rbx+20h]
0x18001981b  mov     [rbx+30h], rax
0x18001981f  xor     ebx, ebx
0x180019821  lea     rcx, [rbp+57h+var_40]
0x180019825  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001982b  mov     eax, ebx
0x18001982d  mov     rcx, [rbp+57h+var_8]
0x180019831  xor     rcx, rsp; StackCookie
0x180019834  call    __security_check_cookie
0x180019839  lea     r11, [rsp+90h+var_s0]
0x180019841  mov     rbx, [r11+20h]
0x180019845  mov     rdi, [r11+28h]
0x180019849  mov     rsp, r11
0x18001984c  pop     rbp
0x18001984d  retn
```
