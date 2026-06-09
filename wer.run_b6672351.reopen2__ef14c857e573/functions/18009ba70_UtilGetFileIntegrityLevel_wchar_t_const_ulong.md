# UtilGetFileIntegrityLevel(wchar_t const *,ulong *)

- ea: `0x18009ba70`
- end: `0x18009bbd0`
- name: `?UtilGetFileIntegrityLevel@@YAJPEB_WPEAK@Z`
- size: `352`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007b4b4`

## callees

- `0x18001e0d0`
- `0x180020680`
- `0x18002d2e0`
- `0x18009ba70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bacd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bacd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009bb7f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009bb7f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18009babd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18009babd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009bb5a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009bb5a`

## pseudocode

```c
__int64 __fastcall UtilGetFileIntegrityLevel(const wchar_t *a1, unsigned int *a2)
{
  int FileSecurityDescriptor; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // ebx
  struct _ACL *v7; // rcx
  int v8; // r14d
  DWORD v9; // edi
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+28h] [rbp-8h] BYREF
  BOOL bSaclPresent; // [rsp+68h] [rbp+38h] BYREF
  BOOL bSaclDefaulted; // [rsp+70h] [rbp+40h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+48h] BYREF

  pSecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  *a2 = 0;
  FileSecurityDescriptor = UtilGetFileSecurityDescriptor(a1);
  if ( FileSecurityDescriptor )
  {
    if ( FileSecurityDescriptor == 1 )
      *a2 = 0x2000;
    goto LABEL_22;
  }
  if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_9;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_9:
    v6 = 0x2000;
    if ( bSaclPresent )
    {
      v7 = pSacl;
      if ( pSacl )
      {
        if ( pSacl->AceCount )
        {
          v8 = 0;
          v9 = 0;
          do
          {
            if ( v8 )
              break;
            pAce = 0;
            if ( GetAce(v7, v9, &pAce) && *(_BYTE *)pAce == 17 && (*((_BYTE *)pAce + 1) & 8) == 0 )
            {
              v8 = 1;
              v6 = *GetSidSubAuthority((char *)pAce + 8, 0);
            }
            v7 = pSacl;
            ++v9;
          }
          while ( v9 < pSacl->AceCount );
        }
      }
    }
    *a2 = v6;
LABEL_22:
    v5 = 0;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v5);
LABEL_23:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&pSecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x18009ba70  mov     [rsp-28h+arg_0], rbx
0x18009ba75  push    rbp
0x18009ba76  push    rsi
0x18009ba77  push    rdi
0x18009ba78  push    r14
0x18009ba7a  push    r15
0x18009ba7c  mov     rbp, rsp
0x18009ba7f  sub     rsp, 30h
0x18009ba83  xor     r15d, r15d
0x18009ba86  lea     r8, [rbp+pSecurityDescriptor]
0x18009ba8a  mov     [rbp+pSecurityDescriptor], r15
0x18009ba8e  mov     rsi, rdx
0x18009ba91  mov     [rbp+pSacl], r15
0x18009ba95  mov     [rbp+bSaclPresent], r15d
0x18009ba99  mov     [rbp+bSaclDefaulted], r15d
0x18009ba9d  mov     [rdx], r15d
0x18009baa0  call    UtilGetFileSecurityDescriptor
0x18009baa5  test    eax, eax
0x18009baa7  jnz     loc_18009BBA5
0x18009baad  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009bab1  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x18009bab5  lea     r8, [rbp+pSacl]; pSacl
0x18009bab9  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18009babd  call    cs:__imp_GetSecurityDescriptorSacl
0x18009bac4  nop     dword ptr [rax+rax+00h]
0x18009bac9  test    eax, eax
0x18009bacb  jnz     short loc_18009BB2A
0x18009bacd  call    cs:__imp_GetLastError
0x18009bad4  nop     dword ptr [rax+rax+00h]
0x18009bad9  mov     ebx, eax
0x18009badb  test    eax, eax
0x18009badd  jle     short loc_18009BAE8
0x18009badf  movzx   ebx, ax
0x18009bae2  or      ebx, 80070000h
0x18009bae8  test    ebx, ebx
0x18009baea  jns     short loc_18009BB2A
0x18009baec  mov     rcx, cs:WPP_GLOBAL_Control
0x18009baf3  lea     rax, WPP_GLOBAL_Control
0x18009bafa  cmp     rcx, rax
0x18009bafd  jz      loc_18009BBB3
0x18009bb03  test    byte ptr [rcx+1Ch], 1
0x18009bb07  jz      loc_18009BBB3
0x18009bb0d  mov     rcx, [rcx+10h]
0x18009bb11  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009bb18  mov     edx, 12h
0x18009bb1d  mov     r9d, ebx
0x18009bb20  call    WPP_SF_d
0x18009bb25  jmp     loc_18009BBB3
0x18009bb2a  mov     ebx, 2000h
0x18009bb2f  cmp     [rbp+bSaclPresent], r15d
0x18009bb33  jz      short loc_18009BBA1
0x18009bb35  mov     rcx, [rbp+pSacl]; pAcl
0x18009bb39  test    rcx, rcx
0x18009bb3c  jz      short loc_18009BBA1
0x18009bb3e  cmp     [rcx+4], r15w
0x18009bb43  jbe     short loc_18009BBA1
0x18009bb45  mov     r14d, r15d
0x18009bb48  mov     edi, r15d
0x18009bb4b  test    r14d, r14d
0x18009bb4e  jnz     short loc_18009BBA1
0x18009bb50  lea     r8, [rbp+pAce]; pAce
0x18009bb54  mov     [rbp+pAce], r15
0x18009bb58  mov     edx, edi; dwAceIndex
0x18009bb5a  call    cs:__imp_GetAce
0x18009bb61  nop     dword ptr [rax+rax+00h]
0x18009bb66  test    eax, eax
0x18009bb68  jz      short loc_18009BB93
0x18009bb6a  mov     rcx, [rbp+pAce]
0x18009bb6e  cmp     byte ptr [rcx], 11h
0x18009bb71  jnz     short loc_18009BB93
0x18009bb73  test    byte ptr [rcx+1], 8
0x18009bb77  jnz     short loc_18009BB93
0x18009bb79  add     rcx, 8; pSid
0x18009bb7d  xor     edx, edx; nSubAuthority
0x18009bb7f  call    cs:__imp_GetSidSubAuthority
0x18009bb86  nop     dword ptr [rax+rax+00h]
0x18009bb8b  mov     r14d, 1
0x18009bb91  mov     ebx, [rax]
0x18009bb93  mov     rcx, [rbp+pSacl]
0x18009bb97  inc     edi
0x18009bb99  movzx   eax, word ptr [rcx+4]
0x18009bb9d  cmp     edi, eax
0x18009bb9f  jb      short loc_18009BB4B
0x18009bba1  mov     [rsi], ebx
0x18009bba3  jmp     short loc_18009BBB0
0x18009bba5  cmp     eax, 1
0x18009bba8  jnz     short loc_18009BBB0
0x18009bbaa  mov     dword ptr [rsi], 2000h
0x18009bbb0  mov     ebx, r15d
0x18009bbb3  lea     rcx, [rbp+pSecurityDescriptor]; void *
0x18009bbb7  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18009bbbc  mov     eax, ebx
0x18009bbbe  mov     rbx, [rsp+30h+arg_0]
0x18009bbc3  add     rsp, 30h
0x18009bbc7  pop     r15
0x18009bbc9  pop     r14
0x18009bbcb  pop     rdi
0x18009bbcc  pop     rsi
0x18009bbcd  pop     rbp
0x18009bbce  retn
```
