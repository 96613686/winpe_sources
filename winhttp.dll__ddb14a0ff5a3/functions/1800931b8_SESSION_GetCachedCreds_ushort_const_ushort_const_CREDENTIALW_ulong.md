# SESSION::GetCachedCreds(ushort const *,ushort const *,_CREDENTIALW * * *,ulong *)

- ea: `0x1800931b8`
- end: `0x1800932ac`
- name: `?GetCachedCreds@SESSION@@QEAAHPEBG0PEAPEAPEAU_CREDENTIALW@@PEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(SESSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _CREDENTIALW ***, DWORD *Count)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800baeb4`

## callees

- `0x1800931b8`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180093274`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180093274`
- `api-ms-win-security-credentials-l1-1-0!CredReadDomainCredentialsW` at `0x180093230`
- `api-ms-win-security-credentials-l1-1-0!CredReadDomainCredentialsW` at `0x180093230`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093252`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093252`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180093266`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180093266`

## pseudocode

```c
_BOOL8 __fastcall SESSION::GetCachedCreds(SESSION *this, WCHAR *a2, WCHAR *a3, struct _CREDENTIALW ***a4, DWORD *Count)
{
  _CREDENTIAL_TARGET_INFORMATIONW TargetInfo; // [rsp+20h] [rbp-41h] BYREF
  int v9; // [rsp+70h] [rbp+Fh] BYREF
  struct _FILETIME FileTime; // [rsp+78h] [rbp+17h] BYREF

  TargetInfo.DnsDomainName = a2;
  TargetInfo.PackageName = (LPWSTR)L"Passport1.4";
  TargetInfo.TargetName = a3;
  *a4 = 0;
  *Count = 0;
  TargetInfo.CredTypeCount = 1;
  v9 = 4;
  memset(&TargetInfo.NetbiosServerName, 0, 24);
  TargetInfo.DnsTreeName = 0;
  TargetInfo.Flags = 0;
  TargetInfo.CredTypes = (LPDWORD)&v9;
  if ( !CredReadDomainCredentialsW(&TargetInfo, 1u, Count, a4) )
  {
LABEL_5:
    *a4 = 0;
    *Count = 0;
    return *a4 != 0;
  }
  if ( *((_DWORD *)this + 1232) )
  {
    FileTime = 0;
    SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 4932), &FileTime);
    if ( CompareFileTime(&(**a4)->LastWritten, &FileTime) != -1 )
    {
      *((_DWORD *)this + 1232) = 0;
      return *a4 != 0;
    }
    CredFree(*a4);
    goto LABEL_5;
  }
  return *a4 != 0;
}

```

## disassembly

```asm
0x1800931b8  push    rbp
0x1800931ba  push    rbx
0x1800931bb  push    rsi
0x1800931bc  push    rdi
0x1800931bd  push    r14
0x1800931bf  lea     rbp, [rsp-2Fh]
0x1800931c4  sub     rsp, 90h
0x1800931cb  mov     rax, cs:__security_cookie
0x1800931d2  xor     rax, rsp
0x1800931d5  mov     [rbp+4Fh+var_30], rax
0x1800931d9  mov     rsi, [rbp+4Fh+Count]
0x1800931dd  lea     rax, aPassport14_0; "Passport1.4"
0x1800931e4  xor     r14d, r14d
0x1800931e7  mov     [rbp+4Fh+TargetInfo.DnsDomainName], rdx
0x1800931eb  mov     [rbp+4Fh+TargetInfo.PackageName], rax
0x1800931ef  mov     rdi, rcx
0x1800931f2  xorps   xmm0, xmm0
0x1800931f5  mov     [rbp+4Fh+TargetInfo.TargetName], r8
0x1800931f9  lea     rax, [rbp+4Fh+var_40]
0x1800931fd  mov     [r9], r14
0x180093200  lea     edx, [r14+1]; Flags
0x180093204  mov     [rsi], r14d
0x180093207  mov     r8, rsi; Count
0x18009320a  mov     [rbp+4Fh+TargetInfo.CredTypeCount], edx
0x18009320d  lea     rcx, [rbp+4Fh+TargetInfo]; TargetInfo
0x180093211  mov     [rbp+4Fh+var_40], 4
0x180093218  mov     rbx, r9
0x18009321b  mov     [rbp+4Fh+TargetInfo.NetbiosServerName], r14
0x18009321f  movdqa  xmmword ptr [rbp+4Fh+TargetInfo.DnsServerName], xmm0
0x180093224  mov     [rbp+4Fh+TargetInfo.DnsTreeName], r14
0x180093228  mov     [rbp+4Fh+TargetInfo.Flags], r14d
0x18009322c  mov     [rbp+4Fh+TargetInfo.CredTypes], rax
0x180093230  call    cs:__imp_CredReadDomainCredentialsW
0x180093236  test    eax, eax
0x180093238  jz      short loc_18009327A
0x18009323a  cmp     [rdi+1340h], r14d
0x180093241  jz      short loc_180093289
0x180093243  lea     rcx, [rdi+1344h]; lpSystemTime
0x18009324a  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], r14
0x18009324e  lea     rdx, [rbp+4Fh+FileTime]; lpFileTime
0x180093252  call    cs:__imp_SystemTimeToFileTime
0x180093258  mov     rax, [rbx]
0x18009325b  lea     rdx, [rbp+4Fh+FileTime]; lpFileTime2
0x18009325f  mov     rcx, [rax]
0x180093262  add     rcx, 18h; lpFileTime1
0x180093266  call    cs:__imp_CompareFileTime
0x18009326c  cmp     eax, 0FFFFFFFFh
0x18009326f  jnz     short loc_180093282
0x180093271  mov     rcx, [rbx]; Buffer
0x180093274  call    cs:__imp_CredFree
0x18009327a  mov     [rbx], r14
0x18009327d  mov     [rsi], r14d
0x180093280  jmp     short loc_180093289
0x180093282  mov     [rdi+1340h], r14d
0x180093289  cmp     [rbx], r14
0x18009328c  mov     eax, r14d
0x18009328f  setnz   al
0x180093292  mov     rcx, [rbp+4Fh+var_30]
0x180093296  xor     rcx, rsp; StackCookie
0x180093299  call    __security_check_cookie
0x18009329e  add     rsp, 90h
0x1800932a5  pop     r14
0x1800932a7  pop     rdi
0x1800932a8  pop     rsi
0x1800932a9  pop     rbx
0x1800932aa  pop     rbp
0x1800932ab  retn
```
