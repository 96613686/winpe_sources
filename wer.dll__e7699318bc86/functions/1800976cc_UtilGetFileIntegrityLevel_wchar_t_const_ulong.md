# UtilGetFileIntegrityLevel(wchar_t const *,ulong *)

- ea: `0x1800976cc`
- end: `0x180097810`
- name: `?UtilGetFileIntegrityLevel@@YAJPEB_WPEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180077f10`

## callees

- `0x18001c650`
- `0x18001fe24`
- `0x18002b8b4`
- `0x1800976cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097723`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800977c6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800977c6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180097719`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180097719`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800977a7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800977a7`

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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v5);
LABEL_23:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&pSecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x1800976cc  mov     [rsp-28h+arg_0], rbx
0x1800976d1  push    rbp
0x1800976d2  push    rsi
0x1800976d3  push    rdi
0x1800976d4  push    r14
0x1800976d6  push    r15
0x1800976d8  mov     rbp, rsp
0x1800976db  sub     rsp, 30h
0x1800976df  xor     r15d, r15d
0x1800976e2  lea     r8, [rbp+pSecurityDescriptor]
0x1800976e6  mov     [rbp+pSecurityDescriptor], r15
0x1800976ea  mov     rsi, rdx
0x1800976ed  mov     [rbp+pSacl], r15
0x1800976f1  mov     [rbp+bSaclPresent], r15d
0x1800976f5  mov     [rbp+bSaclDefaulted], r15d
0x1800976f9  mov     [rdx], r15d
0x1800976fc  call    UtilGetFileSecurityDescriptor
0x180097701  test    eax, eax
0x180097703  jnz     loc_1800977E6
0x180097709  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009770d  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180097711  lea     r8, [rbp+pSacl]; pSacl
0x180097715  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180097719  call    cs:__imp_GetSecurityDescriptorSacl
0x18009771f  test    eax, eax
0x180097721  jnz     short loc_180097777
0x180097723  call    cs:__imp_GetLastError
0x180097729  mov     ebx, eax
0x18009772b  test    eax, eax
0x18009772d  jle     short loc_180097738
0x18009772f  movzx   ebx, ax
0x180097732  or      ebx, 80070000h
0x180097738  test    ebx, ebx
0x18009773a  jns     short loc_180097777
0x18009773c  mov     rcx, cs:WPP_GLOBAL_Control
0x180097743  lea     rax, WPP_GLOBAL_Control
0x18009774a  cmp     rcx, rax
0x18009774d  jz      loc_1800977F4
0x180097753  test    byte ptr [rcx+1Ch], 1
0x180097757  jz      loc_1800977F4
0x18009775d  mov     rcx, [rcx+10h]
0x180097761  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097768  mov     edx, 12h
0x18009776d  mov     r9d, ebx
0x180097770  call    WPP_SF_d
0x180097775  jmp     short loc_1800977F4
0x180097777  mov     ebx, 2000h
0x18009777c  cmp     [rbp+bSaclPresent], r15d
0x180097780  jz      short loc_1800977E2
0x180097782  mov     rcx, [rbp+pSacl]; pAcl
0x180097786  test    rcx, rcx
0x180097789  jz      short loc_1800977E2
0x18009778b  cmp     [rcx+4], r15w
0x180097790  jbe     short loc_1800977E2
0x180097792  mov     r14d, r15d
0x180097795  mov     edi, r15d
0x180097798  test    r14d, r14d
0x18009779b  jnz     short loc_1800977E2
0x18009779d  lea     r8, [rbp+pAce]; pAce
0x1800977a1  mov     [rbp+pAce], r15
0x1800977a5  mov     edx, edi; dwAceIndex
0x1800977a7  call    cs:__imp_GetAce
0x1800977ad  test    eax, eax
0x1800977af  jz      short loc_1800977D4
0x1800977b1  mov     rcx, [rbp+pAce]
0x1800977b5  cmp     byte ptr [rcx], 11h
0x1800977b8  jnz     short loc_1800977D4
0x1800977ba  test    byte ptr [rcx+1], 8
0x1800977be  jnz     short loc_1800977D4
0x1800977c0  add     rcx, 8; pSid
0x1800977c4  xor     edx, edx; nSubAuthority
0x1800977c6  call    cs:__imp_GetSidSubAuthority
0x1800977cc  mov     r14d, 1
0x1800977d2  mov     ebx, [rax]
0x1800977d4  mov     rcx, [rbp+pSacl]
0x1800977d8  inc     edi
0x1800977da  movzx   eax, word ptr [rcx+4]
0x1800977de  cmp     edi, eax
0x1800977e0  jb      short loc_180097798
0x1800977e2  mov     [rsi], ebx
0x1800977e4  jmp     short loc_1800977F1
0x1800977e6  cmp     eax, 1
0x1800977e9  jnz     short loc_1800977F1
0x1800977eb  mov     dword ptr [rsi], 2000h
0x1800977f1  mov     ebx, r15d
0x1800977f4  lea     rcx, [rbp+pSecurityDescriptor]; void *
0x1800977f8  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800977fd  mov     eax, ebx
0x1800977ff  mov     rbx, [rsp+30h+arg_0]
0x180097804  add     rsp, 30h
0x180097808  pop     r15
0x18009780a  pop     r14
0x18009780c  pop     rdi
0x18009780d  pop     rsi
0x18009780e  pop     rbp
0x18009780f  retn
```
