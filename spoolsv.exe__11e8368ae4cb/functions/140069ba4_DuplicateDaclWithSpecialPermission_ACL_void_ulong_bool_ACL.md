# DuplicateDaclWithSpecialPermission(_ACL *,void * *,ulong,bool,_ACL * *)

- ea: `0x140069ba4`
- end: `0x140069db6`
- name: `?DuplicateDaclWithSpecialPermission@@YAKPEAU_ACL@@PEAPEAXK_NPEAPEAU1@@Z`
- size: `530`
- prototype: `unsigned int __usercall@<eax>(PACL pAcl@<rcx>, void **@<rdx>, unsigned int@<r8d>, bool@<r9b>, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006a3dc`

## callees

- `0x14000a398`
- `0x14002abc0`
- `0x14002b810`
- `0x14002bbcc`
- `0x140069ba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069d4e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140069bf9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140069bf9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140069c9b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140069c9b`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140069cd9`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140069cd9`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140069d3d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140069d3d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140069c6d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140069c6d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140069d16`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140069d16`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140069c1c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140069c1c`

## pseudocode

```c
DWORD __fastcall DuplicateDaclWithSpecialPermission(PACL pAcl, void **a2, unsigned int a3, char a4, struct _ACL **a5)
{
  DWORD v8; // edi
  __int64 i; // rbx
  DWORD LengthSid; // eax
  struct _ACL *v11; // rsi
  char v12; // r14
  DWORD j; // edi
  __int64 k; // rbx
  unsigned __int16 *v15; // r9
  __int64 m; // rbx
  DWORD LastError; // ebx
  struct _ACL *v19; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcla; // [rsp+48h] [rbp-28h]
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+58h] [rbp-18h]

  pAcla = pAcl;
  pAclInformation = 0;
  v23 = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    return GetLastError();
  v8 = HIDWORD(pAclInformation);
  for ( i = 0; (unsigned int)i < a3; v8 += LengthSid + 12 )
  {
    LengthSid = GetLengthSid(a2[i]);
    i = (unsigned int)(i + 1);
  }
  v19 = 0;
  v11 = (struct _ACL *)operator new[](v8);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
  if ( v11 )
  {
    v19 = v11;
    memset_0(v11, 0, v8);
    if ( !InitializeAcl(v11, v8, 2u) )
    {
LABEL_24:
      LastError = GetLastError();
      NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
      return LastError;
    }
    v12 = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= (unsigned int)pAclInformation )
      {
        *a5 = v11;
        v19 = 0;
        NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
        return 0;
      }
      pAce = 0;
      if ( !GetAce(pAcla, j, &pAce) )
        goto LABEL_24;
      if ( !v12 )
      {
        if ( a4 )
        {
          v12 = 1;
          for ( k = 0; (unsigned int)k < a3; k = (unsigned int)(k + 1) )
          {
            if ( !AddAccessDeniedAceEx(v11, 2u, 3u, 0xF003Fu, a2[k]) )
              goto LABEL_24;
          }
        }
        else
        {
          v15 = (unsigned __int16 *)pAce;
          if ( *(_BYTE *)pAce == 6 )
            goto LABEL_22;
          v12 = 1;
          for ( m = 0; (unsigned int)m < a3; m = (unsigned int)(m + 1) )
          {
            if ( !AddAccessAllowedAceEx(v11, 2u, 3u, 0x20019u, a2[m]) )
              goto LABEL_24;
          }
        }
      }
      v15 = (unsigned __int16 *)pAce;
LABEL_22:
      if ( !AddAce(v11, 2u, 0xFFFFFFFF, v15, v15[1]) )
        goto LABEL_24;
    }
  }
  v19 = 0;
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
  return 8;
}

```

## disassembly

```asm
0x140069ba4  mov     [rsp-38h+arg_10], rbx
0x140069ba9  push    rbp
0x140069baa  push    rsi
0x140069bab  push    rdi
0x140069bac  push    r12
0x140069bae  push    r13
0x140069bb0  push    r14
0x140069bb2  push    r15
0x140069bb4  mov     rbp, rsp
0x140069bb7  sub     rsp, 70h
0x140069bbb  mov     rax, cs:__security_cookie
0x140069bc2  xor     rax, rsp
0x140069bc5  mov     [rbp+var_10], rax
0x140069bc9  mov     r13, [rbp+arg_20]
0x140069bcd  mov     rax, rcx
0x140069bd0  mov     [rbp+pAcl], rcx
0x140069bd4  mov     r15d, r8d
0x140069bd7  xor     ecx, ecx
0x140069bd9  mov     [rbp+var_40], r9b
0x140069bdd  mov     r12, rdx
0x140069be0  mov     [rbp+pAclInformation], rcx
0x140069be4  mov     [rbp+var_18], ecx
0x140069be7  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140069beb  lea     r14d, [rcx+2]
0x140069bef  lea     r8d, [rcx+0Ch]; nAclInformationLength
0x140069bf3  mov     r9d, r14d; dwAclInformationClass
0x140069bf6  mov     rcx, rax; pAcl
0x140069bf9  call    cs:__imp_GetAclInformation
0x140069bff  test    eax, eax
0x140069c01  jnz     short loc_140069C0E
0x140069c03  call    cs:__imp_GetLastError
0x140069c09  jmp     loc_140069D92
0x140069c0e  mov     edi, dword ptr [rbp+pAclInformation+4]
0x140069c11  xor     ebx, ebx
0x140069c13  test    r15d, r15d
0x140069c16  jz      short loc_140069C2E
0x140069c18  mov     rcx, [r12+rbx*8]; pSid
0x140069c1c  call    cs:__imp_GetLengthSid
0x140069c22  add     edi, 0Ch
0x140069c25  inc     ebx
0x140069c27  add     edi, eax
0x140069c29  cmp     ebx, r15d
0x140069c2c  jb      short loc_140069C18
0x140069c2e  mov     ecx, edi; unsigned __int64
0x140069c30  mov     ebx, edi
0x140069c32  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140069c37  lea     rcx, [rbp+var_38]
0x140069c3b  mov     [rbp+var_38], 0
0x140069c43  mov     rsi, rax
0x140069c46  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140069c4b  test    rsi, rsi
0x140069c4e  jz      loc_140069D7C
0x140069c54  mov     r8d, ebx; Size
0x140069c57  mov     [rbp+var_38], rsi
0x140069c5b  xor     edx, edx; Val
0x140069c5d  mov     rcx, rsi; void *
0x140069c60  call    memset_0
0x140069c65  mov     r8d, r14d; dwAclRevision
0x140069c68  mov     edx, edi; nAclLength
0x140069c6a  mov     rcx, rsi; pAcl
0x140069c6d  call    cs:__imp_InitializeAcl
0x140069c73  test    eax, eax
0x140069c75  jz      loc_140069D4E
0x140069c7b  xor     r14b, r14b
0x140069c7e  xor     edi, edi
0x140069c80  cmp     edi, dword ptr [rbp+pAclInformation]
0x140069c83  jnb     loc_140069D63
0x140069c89  mov     rcx, [rbp+pAcl]; pAcl
0x140069c8d  lea     r8, [rbp+pAce]; pAce
0x140069c91  mov     edx, edi; dwAceIndex
0x140069c93  mov     [rbp+pAce], 0
0x140069c9b  call    cs:__imp_GetAce
0x140069ca1  test    eax, eax
0x140069ca3  jz      loc_140069D4E
0x140069ca9  test    r14b, r14b
0x140069cac  jnz     short loc_140069D24
0x140069cae  cmp     [rbp+var_40], r14b
0x140069cb2  jz      short loc_140069CE7
0x140069cb4  mov     r14b, 1
0x140069cb7  xor     ebx, ebx
0x140069cb9  cmp     ebx, r15d
0x140069cbc  jnb     short loc_140069D24
0x140069cbe  mov     rcx, [r12+rbx*8]
0x140069cc2  mov     edx, 2; dwAceRevision
0x140069cc7  mov     [rsp+70h+pSid], rcx; pSid
0x140069ccc  mov     r9d, 0F003Fh; AccessMask
0x140069cd2  mov     rcx, rsi; pAcl
0x140069cd5  lea     r8d, [rdx+1]; AceFlags
0x140069cd9  call    cs:__imp_AddAccessDeniedAceEx
0x140069cdf  test    eax, eax
0x140069ce1  jz      short loc_140069D4E
0x140069ce3  inc     ebx
0x140069ce5  jmp     short loc_140069CB9
0x140069ce7  mov     r9, [rbp+pAce]
0x140069ceb  cmp     byte ptr [r9], 6
0x140069cef  jz      short loc_140069D28
0x140069cf1  mov     r14b, 1
0x140069cf4  xor     ebx, ebx
0x140069cf6  cmp     ebx, r15d
0x140069cf9  jnb     short loc_140069D24
0x140069cfb  mov     rcx, [r12+rbx*8]
0x140069cff  mov     edx, 2; dwAceRevision
0x140069d04  mov     [rsp+70h+pSid], rcx; pSid
0x140069d09  mov     r9d, 20019h; AccessMask
0x140069d0f  mov     rcx, rsi; pAcl
0x140069d12  lea     r8d, [rdx+1]; AceFlags
0x140069d16  call    cs:__imp_AddAccessAllowedAceEx
0x140069d1c  test    eax, eax
0x140069d1e  jz      short loc_140069D4E
0x140069d20  inc     ebx
0x140069d22  jmp     short loc_140069CF6
0x140069d24  mov     r9, [rbp+pAce]; pAceList
0x140069d28  movzx   eax, word ptr [r9+2]
0x140069d2d  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140069d31  mov     edx, 2; dwAceRevision
0x140069d36  mov     dword ptr [rsp+70h+pSid], eax; nAceListLength
0x140069d3a  mov     rcx, rsi; pAcl
0x140069d3d  call    cs:__imp_AddAce
0x140069d43  test    eax, eax
0x140069d45  jz      short loc_140069D4E
0x140069d47  inc     edi
0x140069d49  jmp     loc_140069C80
0x140069d4e  call    cs:__imp_GetLastError
0x140069d54  lea     rcx, [rbp+var_38]
0x140069d58  mov     ebx, eax
0x140069d5a  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140069d5f  mov     eax, ebx
0x140069d61  jmp     short loc_140069D92
0x140069d63  lea     rcx, [rbp+var_38]
0x140069d67  mov     [r13+0], rsi
0x140069d6b  mov     [rbp+var_38], 0
0x140069d73  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140069d78  xor     eax, eax
0x140069d7a  jmp     short loc_140069D92
0x140069d7c  lea     rcx, [rbp+var_38]
0x140069d80  mov     [rbp+var_38], 0
0x140069d88  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140069d8d  mov     eax, 8
0x140069d92  mov     rcx, [rbp+var_10]
0x140069d96  xor     rcx, rsp; StackCookie
0x140069d99  call    __security_check_cookie
0x140069d9e  mov     rbx, [rsp+70h+arg_10]
0x140069da6  add     rsp, 70h
0x140069daa  pop     r15
0x140069dac  pop     r14
0x140069dae  pop     r13
0x140069db0  pop     r12
0x140069db2  pop     rdi
0x140069db3  pop     rsi
0x140069db4  pop     rbp
0x140069db5  retn
```
