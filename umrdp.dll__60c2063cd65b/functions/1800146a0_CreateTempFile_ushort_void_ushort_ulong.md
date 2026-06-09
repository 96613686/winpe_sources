# CreateTempFile(ushort *,void *,ushort *,ulong)

- ea: `0x1800146a0`
- end: `0x180014913`
- name: `?CreateTempFile@@YAKPEAGPEAX0K@Z`
- size: `627`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014e4c`
- `0x180017494`

## callees

- `0x180009e50`
- `0x18000a01c`
- `0x1800146a0`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001474f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001489e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001474f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001489e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001477a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001477a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148e4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180014817`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180014817`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800147fe`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800147fe`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800147bb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800147d3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800147bb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800147d3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001479d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001479d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014760`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001476b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014760`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001476b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014742`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014742`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014884`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014884`

## pseudocode

```c
__int64 __fastcall CreateTempFile(unsigned __int16 *a1, void *a2, unsigned __int16 *a3)
{
  int v4; // r14d
  void *UserSid; // r15
  DWORD LastError; // ebx
  void *v8; // rdi
  struct _ACL *v9; // rsi
  DWORD LengthSid; // ebx
  DWORD v11; // ebx
  struct _ACL *v12; // rax
  HLOCAL v13; // rax
  signed __int32 v14; // eax
  HANDLE v15; // rax
  __int64 nSubAuthority2; // [rsp+20h] [rbp-49h]
  PSID hMem; // [rsp+60h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+17h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v4 = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  UserSid = TSNUTL_GetUserSid(a2);
  if ( !UserSid )
  {
    LastError = GetLastError();
    goto LABEL_25;
  }
  v8 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    LengthSid = GetLengthSid(hMem);
    v11 = GetLengthSid(UserSid) + 24 + LengthSid;
    v12 = (struct _ACL *)LocalAlloc(0, v11);
    v9 = v12;
    if ( v12 )
    {
      if ( !InitializeAcl(v12, v11, 2u)
        || !AddAccessAllowedAce(v9, 2u, 0x10000000u, hMem)
        || !AddAccessAllowedAce(v9, 2u, 0x10000000u, UserSid) )
      {
        goto LABEL_5;
      }
      v13 = LocalAlloc(0, 0x28u);
      v8 = v13;
      if ( v13 )
      {
        if ( InitializeSecurityDescriptor(v13, 1u) && SetSecurityDescriptorDacl(v8, 1, v9, 0) )
        {
          SecurityAttributes.nLength = 24;
          SecurityAttributes.lpSecurityDescriptor = v8;
          SecurityAttributes.bInheritHandle = 0;
          while ( 1 )
          {
            v14 = _InterlockedIncrement(&dword_18005DE58);
            if ( v4 )
              break;
            LODWORD(nSubAuthority2) = v14;
            StringCchPrintfW(a3, 0x104u, L"%sprn%04d.tmp", a1, nSubAuthority2);
            v15 = CreateFileW(a3, 0x80000000, 0, &SecurityAttributes, 1u, 0x80u, 0);
            if ( v15 == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              if ( LastError != 80 )
                goto LABEL_21;
            }
            else
            {
              CloseHandle(v15);
              v4 = 1;
            }
          }
          LastError = 0;
          goto LABEL_21;
        }
        goto LABEL_5;
      }
    }
    LastError = 8;
    goto LABEL_21;
  }
  v9 = 0;
LABEL_5:
  LastError = GetLastError();
LABEL_21:
  LocalFree(UserSid);
  if ( v9 )
    LocalFree(v9);
  if ( v8 )
    LocalFree(v8);
LABEL_25:
  if ( hMem )
    LocalFree(hMem);
  return LastError;
}

```

## disassembly

```asm
0x1800146a0  mov     [rsp-8+arg_18], rbx
0x1800146a5  push    rbp
0x1800146a6  push    rsi
0x1800146a7  push    rdi
0x1800146a8  push    r12
0x1800146aa  push    r13
0x1800146ac  push    r14
0x1800146ae  push    r15
0x1800146b0  lea     rbp, [rsp-27h]
0x1800146b5  sub     rsp, 90h
0x1800146bc  mov     rax, cs:__security_cookie
0x1800146c3  xor     rax, rsp
0x1800146c6  mov     [rbp+57h+var_38], rax
0x1800146ca  mov     r13, rcx
0x1800146cd  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800146d3  xor     r14d, r14d
0x1800146d6  xorps   xmm0, xmm0
0x1800146d9  xor     eax, eax
0x1800146db  mov     [rbp+57h+hMem], r14
0x1800146df  mov     rcx, rdx; TokenHandle
0x1800146e2  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x1800146e6  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x1800146ea  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800146ee  mov     r12, r8
0x1800146f1  call    ?TSNUTL_GetUserSid@@YAPEAXPEAX@Z; TSNUTL_GetUserSid(void *)
0x1800146f6  mov     r15, rax
0x1800146f9  test    rax, rax
0x1800146fc  jnz     short loc_18001470B
0x1800146fe  call    cs:__imp_GetLastError
0x180014704  mov     ebx, eax
0x180014706  jmp     loc_1800148DB
0x18001470b  lea     rax, [rbp+57h+hMem]
0x18001470f  xor     r9d, r9d; nSubAuthority1
0x180014712  mov     [rsp+0C0h+pSid], rax; pSid
0x180014717  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001471b  mov     [rsp+0C0h+nSubAuthority7], r14d; nSubAuthority7
0x180014720  mov     dl, 1; nSubAuthorityCount
0x180014722  mov     [rsp+0C0h+nSubAuthority6], r14d; nSubAuthority6
0x180014727  mov     rdi, r14
0x18001472a  mov     [rsp+0C0h+nSubAuthority5], r14d; nSubAuthority5
0x18001472f  lea     r8d, [r9+12h]; nSubAuthority0
0x180014733  mov     [rsp+0C0h+nSubAuthority4], r14d; nSubAuthority4
0x180014738  mov     [rsp+0C0h+nSubAuthority3], r14d; nSubAuthority3
0x18001473d  mov     dword ptr [rsp+0C0h+nSubAuthority2], r14d; nSubAuthority2
0x180014742  call    cs:__imp_AllocateAndInitializeSid
0x180014748  test    eax, eax
0x18001474a  jnz     short loc_18001475C
0x18001474c  mov     rsi, r14
0x18001474f  call    cs:__imp_GetLastError
0x180014755  mov     ebx, eax
0x180014757  jmp     loc_1800148B6
0x18001475c  mov     rcx, [rbp+57h+hMem]; pSid
0x180014760  call    cs:__imp_GetLengthSid
0x180014766  mov     rcx, r15; pSid
0x180014769  mov     ebx, eax
0x18001476b  call    cs:__imp_GetLengthSid
0x180014771  add     eax, 18h
0x180014774  xor     ecx, ecx; uFlags
0x180014776  add     ebx, eax
0x180014778  mov     edx, ebx; uBytes
0x18001477a  call    cs:__imp_LocalAlloc
0x180014780  mov     rsi, rax
0x180014783  test    rax, rax
0x180014786  jnz     short loc_180014792
0x180014788  mov     ebx, 8
0x18001478d  jmp     loc_1800148B6
0x180014792  mov     r8d, 2; dwAclRevision
0x180014798  mov     edx, ebx; nAclLength
0x18001479a  mov     rcx, rsi; pAcl
0x18001479d  call    cs:__imp_InitializeAcl
0x1800147a3  test    eax, eax
0x1800147a5  jz      short loc_18001474F
0x1800147a7  mov     r9, [rbp+57h+hMem]; pSid
0x1800147ab  mov     ebx, 2
0x1800147b0  mov     edx, ebx; dwAceRevision
0x1800147b2  mov     r8d, 10000000h; AccessMask
0x1800147b8  mov     rcx, rsi; pAcl
0x1800147bb  call    cs:__imp_AddAccessAllowedAce
0x1800147c1  test    eax, eax
0x1800147c3  jz      short loc_18001474F
0x1800147c5  mov     r9, r15; pSid
0x1800147c8  mov     r8d, 10000000h; AccessMask
0x1800147ce  mov     edx, ebx; dwAceRevision
0x1800147d0  mov     rcx, rsi; pAcl
0x1800147d3  call    cs:__imp_AddAccessAllowedAce
0x1800147d9  test    eax, eax
0x1800147db  jz      loc_18001474F
0x1800147e1  lea     edx, [rbx+26h]; uBytes
0x1800147e4  xor     ecx, ecx; uFlags
0x1800147e6  call    cs:__imp_LocalAlloc
0x1800147ec  mov     rdi, rax
0x1800147ef  test    rax, rax
0x1800147f2  jz      short loc_180014788
0x1800147f4  mov     ebx, 1
0x1800147f9  mov     rcx, rax; pSecurityDescriptor
0x1800147fc  mov     edx, ebx; dwRevision
0x1800147fe  call    cs:__imp_InitializeSecurityDescriptor
0x180014804  test    eax, eax
0x180014806  jz      loc_18001474F
0x18001480c  xor     r9d, r9d; bDaclDefaulted
0x18001480f  mov     r8, rsi; pDacl
0x180014812  mov     edx, ebx; bDaclPresent
0x180014814  mov     rcx, rdi; pSecurityDescriptor
0x180014817  call    cs:__imp_SetSecurityDescriptorDacl
0x18001481d  test    eax, eax
0x18001481f  jz      loc_18001474F
0x180014825  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18001482c  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rdi
0x180014830  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r14d
0x180014834  mov     eax, ebx
0x180014836  lock xadd cs:dword_18005DE58, eax
0x18001483e  add     eax, ebx
0x180014840  test    r14d, r14d
0x180014843  jnz     short loc_1800148B0
0x180014845  mov     r9, r13
0x180014848  mov     dword ptr [rsp+0C0h+nSubAuthority2], eax
0x18001484c  lea     r8, aSprn04dTmp; "%sprn%04d.tmp"
0x180014853  mov     edx, 104h; unsigned __int64
0x180014858  mov     rcx, r12; unsigned __int16 *
0x18001485b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014860  mov     qword ptr [rsp+0C0h+nSubAuthority4], 0; hTemplateFile
0x180014869  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18001486d  mov     [rsp+0C0h+nSubAuthority3], 80h; dwFlagsAndAttributes
0x180014875  xor     r8d, r8d; dwShareMode
0x180014878  mov     edx, 80000000h; dwDesiredAccess
0x18001487d  mov     dword ptr [rsp+0C0h+nSubAuthority2], ebx; dwCreationDisposition
0x180014881  mov     rcx, r12; lpFileName
0x180014884  call    cs:__imp_CreateFileW
0x18001488a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001488e  jz      short loc_18001489E
0x180014890  mov     rcx, rax; hObject
0x180014893  call    cs:__imp_CloseHandle
0x180014899  mov     r14d, ebx
0x18001489c  jmp     short loc_180014834
0x18001489e  call    cs:__imp_GetLastError
0x1800148a4  mov     ebx, eax
0x1800148a6  cmp     eax, 50h ; 'P'
0x1800148a9  jnz     short loc_1800148B6
0x1800148ab  lea     ebx, [rax-4Fh]
0x1800148ae  jmp     short loc_180014834
0x1800148b0  xor     r14d, r14d
0x1800148b3  mov     ebx, r14d
0x1800148b6  mov     rcx, r15; hMem
0x1800148b9  call    cs:__imp_LocalFree
0x1800148bf  test    rsi, rsi
0x1800148c2  jz      short loc_1800148CD
0x1800148c4  mov     rcx, rsi; hMem
0x1800148c7  call    cs:__imp_LocalFree
0x1800148cd  test    rdi, rdi
0x1800148d0  jz      short loc_1800148DB
0x1800148d2  mov     rcx, rdi; hMem
0x1800148d5  call    cs:__imp_LocalFree
0x1800148db  mov     rcx, [rbp+57h+hMem]; hMem
0x1800148df  test    rcx, rcx
0x1800148e2  jz      short loc_1800148EA
0x1800148e4  call    cs:__imp_LocalFree
0x1800148ea  mov     eax, ebx
0x1800148ec  mov     rcx, [rbp+57h+var_38]
0x1800148f0  xor     rcx, rsp; StackCookie
0x1800148f3  call    __security_check_cookie
0x1800148f8  mov     rbx, [rsp+0C0h+arg_18]
0x180014900  add     rsp, 90h
0x180014907  pop     r15
0x180014909  pop     r14
0x18001490b  pop     r13
0x18001490d  pop     r12
0x18001490f  pop     rdi
0x180014910  pop     rsi
0x180014911  pop     rbp
0x180014912  retn
```
