# LookupAccountNameWrap(ushort const *,ushort const *,void *,ulong *,ushort *,ulong *,_SID_NAME_USE *)

- ea: `0x180014dbc`
- end: `0x180014ee3`
- name: `?LookupAccountNameWrap@@YAHPEBG0PEAXPEAKPEAG2PEAW4_SID_NAME_USE@@@Z`
- size: `295`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int *, unsigned __int16 *, unsigned int *, enum _SID_NAME_USE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014450`

## callees

- `0x18000e4d8`
- `0x180014dbc`

## import_xrefs

- `msvcrt!wcschr` at `0x180014e32`
- `msvcrt!wcschr` at `0x180014e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014dda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014dda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ea1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014e10`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014e10`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014df6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014df6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180014ed2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180014ed2`

## pseudocode

```c
BOOL __fastcall LookupAccountNameWrap(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        void *a3,
        unsigned int *a4,
        unsigned __int16 *ReferencedDomainName,
        unsigned int *cchReferencedDomainName,
        enum _SID_NAME_USE *peUse)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  wchar_t *v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r8
  BOOL v15; // edi

  v7 = lpCriticalSection;
  EnterCriticalSection(lpCriticalSection);
  if ( lpString1 && !lstrcmpiW(lpString1, a2) && CopySid(*a4, a3, qword_18005D3D0) )
  {
    LeaveCriticalSection(lpCriticalSection);
    v11 = wcschr(a2, 0x5Cu);
    if ( !v11 )
      goto LABEL_10;
    v12 = v11 - a2;
    v13 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v13 > *cchReferencedDomainName )
      goto LABEL_10;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    if ( v13 <= v14 )
    {
      v15 = (int)StringCchCopyNW(ReferencedDomainName, *cchReferencedDomainName, a2, (unsigned int)v12) >= 0;
      LeaveCriticalSection(v7);
      return v15;
    }
    else
    {
LABEL_10:
      LeaveCriticalSection(v7);
      return 0;
    }
  }
  else
  {
    LeaveCriticalSection(v7);
    return LookupAccountNameLocalW(a2, a3, a4, ReferencedDomainName, cchReferencedDomainName, peUse);
  }
}

```

## disassembly

```asm
0x180014dbc  push    rbx
0x180014dbe  push    rbp
0x180014dbf  push    rsi
0x180014dc0  push    rdi
0x180014dc1  push    r14
0x180014dc3  sub     rsp, 30h
0x180014dc7  mov     rbx, cs:lpCriticalSection
0x180014dce  mov     rsi, r9
0x180014dd1  mov     rcx, rbx; lpCriticalSection
0x180014dd4  mov     rbp, r8
0x180014dd7  mov     rdi, rdx
0x180014dda  call    cs:__imp_EnterCriticalSection
0x180014de0  mov     rcx, cs:lpString1; lpString1
0x180014de7  xor     r14d, r14d
0x180014dea  test    rcx, rcx
0x180014ded  jz      loc_180014E9E
0x180014df3  mov     rdx, rdi; lpString2
0x180014df6  call    cs:__imp_lstrcmpiW
0x180014dfc  test    eax, eax
0x180014dfe  jnz     loc_180014E9E
0x180014e04  mov     ecx, [rsi]; nDestinationSidLength
0x180014e06  lea     r8, qword_18005D3D0; pSourceSid
0x180014e0d  mov     rdx, rbp; pDestinationSid
0x180014e10  call    cs:__imp_CopySid
0x180014e16  test    eax, eax
0x180014e18  jz      loc_180014E9E
0x180014e1e  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x180014e25  call    cs:__imp_LeaveCriticalSection
0x180014e2b  lea     edx, [r14+5Ch]; Ch
0x180014e2f  mov     rcx, rdi; Str
0x180014e32  call    cs:__imp_wcschr
0x180014e38  mov     rdx, rax
0x180014e3b  test    rax, rax
0x180014e3e  jz      short loc_180014E91
0x180014e40  mov     rcx, [rsp+58h+arg_28]
0x180014e48  sub     rdx, rdi
0x180014e4b  sar     rdx, 1
0x180014e4e  lea     eax, [rdx+1]
0x180014e51  cmp     eax, [rcx]
0x180014e53  ja      short loc_180014E91
0x180014e55  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014e59  inc     r8
0x180014e5c  cmp     [rdi+r8*2], r14w
0x180014e61  jnz     short loc_180014E59
0x180014e63  cmp     rax, r8
0x180014e66  ja      short loc_180014E91
0x180014e68  mov     r9d, edx; unsigned __int64
0x180014e6b  mov     r8, rdi; unsigned __int16 *
0x180014e6e  mov     edx, [rcx]; unsigned __int64
0x180014e70  mov     rcx, [rsp+58h+ReferencedDomainName]; unsigned __int16 *
0x180014e78  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180014e7d  mov     edi, eax
0x180014e7f  mov     rcx, rbx; lpCriticalSection
0x180014e82  not     edi
0x180014e84  shr     edi, 1Fh
0x180014e87  call    cs:__imp_LeaveCriticalSection
0x180014e8d  mov     eax, edi
0x180014e8f  jmp     short loc_180014ED8
0x180014e91  mov     rcx, rbx; lpCriticalSection
0x180014e94  call    cs:__imp_LeaveCriticalSection
0x180014e9a  xor     eax, eax
0x180014e9c  jmp     short loc_180014ED8
0x180014e9e  mov     rcx, rbx; lpCriticalSection
0x180014ea1  call    cs:__imp_LeaveCriticalSection
0x180014ea7  mov     rax, [rsp+58h+arg_30]
0x180014eaf  mov     r8, rsi; cbSid
0x180014eb2  mov     r9, [rsp+58h+ReferencedDomainName]; ReferencedDomainName
0x180014eba  mov     rdx, rbp; Sid
0x180014ebd  mov     [rsp+58h+peUse], rax; peUse
0x180014ec2  mov     rcx, rdi; lpAccountName
0x180014ec5  mov     rax, [rsp+58h+arg_28]
0x180014ecd  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180014ed2  call    cs:__imp_LookupAccountNameLocalW
0x180014ed8  add     rsp, 30h
0x180014edc  pop     r14
0x180014ede  pop     rdi
0x180014edf  pop     rsi
0x180014ee0  pop     rbp
0x180014ee1  pop     rbx
0x180014ee2  retn
```
