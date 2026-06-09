# LookupAccountNameWrap(ushort const *,ushort const *,void *,ulong *,ushort *,ulong *,_SID_NAME_USE *)

- ea: `0x180015b10`
- end: `0x180015c6e`
- name: `?LookupAccountNameWrap@@YAHPEBG0PEAXPEAKPEAG2PEAW4_SID_NAME_USE@@@Z`
- size: `350`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int *, unsigned __int16 *, unsigned int *, enum _SID_NAME_USE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800150c4`

## callees

- `0x18000edd8`
- `0x180015b10`

## import_xrefs

- `msvcrt!wcschr` at `0x180015b9e`
- `msvcrt!wcschr` at `0x180015b9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c1f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015b70`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015b70`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015b50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015b50`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180015c56`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180015c56`

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
  if ( lpString1 && !lstrcmpiW(lpString1, a2) && CopySid(*a4, a3, qword_18005F3D0) )
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
0x180015b10  push    rbx
0x180015b12  push    rbp
0x180015b13  push    rsi
0x180015b14  push    rdi
0x180015b15  push    r14
0x180015b17  sub     rsp, 30h
0x180015b1b  mov     rbx, cs:lpCriticalSection
0x180015b22  mov     rsi, r9
0x180015b25  mov     rcx, rbx; lpCriticalSection
0x180015b28  mov     rbp, r8
0x180015b2b  mov     rdi, rdx
0x180015b2e  call    cs:__imp_EnterCriticalSection
0x180015b35  nop     dword ptr [rax+rax+00h]
0x180015b3a  mov     rcx, cs:lpString1; lpString1
0x180015b41  xor     r14d, r14d
0x180015b44  test    rcx, rcx
0x180015b47  jz      loc_180015C1C
0x180015b4d  mov     rdx, rdi; lpString2
0x180015b50  call    cs:__imp_lstrcmpiW
0x180015b57  nop     dword ptr [rax+rax+00h]
0x180015b5c  test    eax, eax
0x180015b5e  jnz     loc_180015C1C
0x180015b64  mov     ecx, [rsi]; nDestinationSidLength
0x180015b66  lea     r8, qword_18005F3D0; pSourceSid
0x180015b6d  mov     rdx, rbp; pDestinationSid
0x180015b70  call    cs:__imp_CopySid
0x180015b77  nop     dword ptr [rax+rax+00h]
0x180015b7c  test    eax, eax
0x180015b7e  jz      loc_180015C1C
0x180015b84  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x180015b8b  call    cs:__imp_LeaveCriticalSection
0x180015b92  nop     dword ptr [rax+rax+00h]
0x180015b97  lea     edx, [r14+5Ch]; Ch
0x180015b9b  mov     rcx, rdi; Str
0x180015b9e  call    cs:__imp_wcschr
0x180015ba5  nop     dword ptr [rax+rax+00h]
0x180015baa  mov     rdx, rax
0x180015bad  test    rax, rax
0x180015bb0  jz      short loc_180015C09
0x180015bb2  mov     rcx, [rsp+58h+arg_28]
0x180015bba  sub     rdx, rdi
0x180015bbd  sar     rdx, 1
0x180015bc0  lea     eax, [rdx+1]
0x180015bc3  cmp     eax, [rcx]
0x180015bc5  ja      short loc_180015C09
0x180015bc7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015bcb  inc     r8
0x180015bce  cmp     [rdi+r8*2], r14w
0x180015bd3  jnz     short loc_180015BCB
0x180015bd5  cmp     rax, r8
0x180015bd8  ja      short loc_180015C09
0x180015bda  mov     r9d, edx; unsigned __int64
0x180015bdd  mov     r8, rdi; unsigned __int16 *
0x180015be0  mov     edx, [rcx]; unsigned __int64
0x180015be2  mov     rcx, [rsp+58h+ReferencedDomainName]; unsigned __int16 *
0x180015bea  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180015bef  mov     edi, eax
0x180015bf1  mov     rcx, rbx; lpCriticalSection
0x180015bf4  not     edi
0x180015bf6  shr     edi, 1Fh
0x180015bf9  call    cs:__imp_LeaveCriticalSection
0x180015c00  nop     dword ptr [rax+rax+00h]
0x180015c05  mov     eax, edi
0x180015c07  jmp     short loc_180015C62
0x180015c09  mov     rcx, rbx; lpCriticalSection
0x180015c0c  call    cs:__imp_LeaveCriticalSection
0x180015c13  nop     dword ptr [rax+rax+00h]
0x180015c18  xor     eax, eax
0x180015c1a  jmp     short loc_180015C62
0x180015c1c  mov     rcx, rbx; lpCriticalSection
0x180015c1f  call    cs:__imp_LeaveCriticalSection
0x180015c26  nop     dword ptr [rax+rax+00h]
0x180015c2b  mov     rax, [rsp+58h+arg_30]
0x180015c33  mov     r8, rsi; cbSid
0x180015c36  mov     r9, [rsp+58h+ReferencedDomainName]; ReferencedDomainName
0x180015c3e  mov     rdx, rbp; Sid
0x180015c41  mov     [rsp+58h+peUse], rax; peUse
0x180015c46  mov     rcx, rdi; lpAccountName
0x180015c49  mov     rax, [rsp+58h+arg_28]
0x180015c51  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180015c56  call    cs:__imp_LookupAccountNameLocalW
0x180015c5d  nop     dword ptr [rax+rax+00h]
0x180015c62  add     rsp, 30h
0x180015c66  pop     r14
0x180015c68  pop     rdi
0x180015c69  pop     rsi
0x180015c6a  pop     rbp
0x180015c6b  pop     rbx
0x180015c6c  retn
```
