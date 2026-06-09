# CShellProtectedRegLock::Lock(void)

- ea: `0x180155524`
- end: `0x180155723`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `511`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180155cf4`
- `0x180355b08`

## callees

- `0x1800a2d04`
- `0x18013d330`
- `0x18013f791`
- `0x180155524`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801556f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801556f8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180155566`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180155566`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180155685`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180155685`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801555cd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801555cd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18015561f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18015561f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015565c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801556a5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015565c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801556a5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015558f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801555b7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015558f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801555b7`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801556ef`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801556ef`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Lock(CShellProtectedRegLock *this)
{
  struct _ACL *v2; // rcx
  struct _ACL *v3; // rcx
  int v4; // ebx
  DWORD v5; // r15d
  void *v6; // rcx
  DWORD LengthSid; // r13d
  DWORD nAceListLength; // esi
  __int64 v9; // rbx
  struct _ACL *pDacl; // r14
  _WORD *v11; // rbx
  int v12; // esi
  DWORD v13; // ebx
  struct _ACL *v14; // rcx
  DWORD dwAclRevision; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( !EqualSid(qword_180406F38, **(PSID **)this) )
    {
      v2 = (struct _ACL *)*((_QWORD *)this + 2);
      pAclInformation = 0;
      v18 = 0;
      if ( GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v3 = (struct _ACL *)*((_QWORD *)this + 2);
        v4 = HIDWORD(pAclInformation);
        dwAclRevision = 0;
        v5 = 2;
        if ( GetAclInformation(v3, &dwAclRevision, 4u, AclRevisionInformation) )
          v5 = dwAclRevision;
        LengthSid = GetLengthSid(**(PSID **)this);
        nAceListLength = LengthSid + 8;
        if ( LengthSid + 8 <= 0xFFFF )
        {
          v9 = nAceListLength + v4;
          if ( (unsigned int)v9 <= 0xFFFF )
          {
            pAcl = 0;
            if ( CTLocalAllocPolicy::Alloc(v6, 0x40u, (unsigned int)v9 + nAceListLength, (void **)&pAcl) >= 0 )
            {
              pDacl = pAcl;
              InitializeAcl(pAcl, v9, v5);
              v11 = (_WORD *)((char *)pDacl + v9);
              *(_BYTE *)v11 = 1;
              v11[1] = LengthSid + 8;
              *((_DWORD *)v11 + 1) = 2;
              memcpy_0(v11 + 4, **(const void ***)this, LengthSid);
              if ( AddAce(pDacl, v5, 0xFFFFFFFF, v11, nAceListLength) )
              {
                v12 = 0;
                v13 = 0;
                if ( !(_DWORD)pAclInformation )
                  goto LABEL_16;
                do
                {
                  v14 = (struct _ACL *)*((_QWORD *)this + 2);
                  pAcl = 0;
                  if ( GetAce(v14, v13, (LPVOID *)&pAcl) )
                  {
                    if ( !AddAce(pDacl, v5, 0xFFFFFFFF, pAcl, pAcl->AclSize) )
                      v12 = 1;
                  }
                  ++v13;
                }
                while ( v13 < (unsigned int)pAclInformation );
                if ( !v12 )
LABEL_16:
                  SetSecurityInfo(*((HANDLE *)this + 1), SE_REGISTRY_KEY, 0x20000004u, 0, 0, pDacl, 0);
              }
              LocalFree(pDacl);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180155524  mov     [rsp-28h+arg_8], rbx
0x180155529  mov     [rsp-28h+arg_10], rsi
0x18015552e  push    rbp
0x18015552f  push    rdi
0x180155530  push    r13
0x180155532  push    r14
0x180155534  push    r15
0x180155536  mov     rbp, rsp
0x180155539  sub     rsp, 70h
0x18015553d  mov     rax, cs:__security_cookie
0x180155544  xor     rax, rsp
0x180155547  mov     [rbp+var_10], rax
0x18015554b  cmp     qword ptr [rcx+10h], 0
0x180155550  mov     rdi, rcx
0x180155553  jz      loc_1801556FE
0x180155559  mov     rdx, [rcx]
0x18015555c  lea     rcx, qword_180406F38; pSid1
0x180155563  mov     rdx, [rdx]; pSid2
0x180155566  call    cs:__imp_EqualSid
0x18015556c  test    eax, eax
0x18015556e  jnz     loc_1801556FE
0x180155574  mov     rcx, [rdi+10h]; pAcl
0x180155578  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18015557c  xor     eax, eax
0x18015557e  mov     [rbp+pAclInformation], rax
0x180155582  mov     [rbp+var_18], eax
0x180155585  lea     esi, [rax+2]
0x180155588  mov     r9d, esi; dwAclInformationClass
0x18015558b  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18015558f  call    cs:__imp_GetAclInformation
0x180155595  test    eax, eax
0x180155597  jz      loc_1801556FE
0x18015559d  mov     rcx, [rdi+10h]; pAcl
0x1801555a1  lea     r9d, [rsi-1]; dwAclInformationClass
0x1801555a5  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1801555a8  lea     r8d, [rsi+2]; nAclInformationLength
0x1801555ac  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x1801555b0  mov     [rbp+dwAclRevision], 0
0x1801555b7  call    cs:__imp_GetAclInformation
0x1801555bd  mov     rcx, [rdi]
0x1801555c0  mov     r15d, esi
0x1801555c3  test    eax, eax
0x1801555c5  cmovnz  r15d, [rbp+dwAclRevision]
0x1801555ca  mov     rcx, [rcx]; pSid
0x1801555cd  call    cs:__imp_GetLengthSid
0x1801555d3  mov     r13d, eax
0x1801555d6  mov     eax, 0FFFFh
0x1801555db  lea     esi, [r13+8]
0x1801555df  cmp     esi, eax
0x1801555e1  ja      loc_1801556FE
0x1801555e7  add     ebx, esi
0x1801555e9  cmp     ebx, eax
0x1801555eb  ja      loc_1801556FE
0x1801555f1  lea     r8d, [rbx+rsi]; unsigned __int64
0x1801555f5  mov     [rbp+pAcl], 0
0x1801555fd  lea     r9, [rbp+pAcl]; void **
0x180155601  mov     edx, 40h ; '@'; unsigned int
0x180155606  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18015560b  test    eax, eax
0x18015560d  js      loc_1801556FE
0x180155613  mov     r14, [rbp+pAcl]
0x180155617  mov     r8d, r15d; dwAclRevision
0x18015561a  mov     rcx, r14; pAcl
0x18015561d  mov     edx, ebx; nAclLength
0x18015561f  call    cs:__imp_InitializeAcl
0x180155625  add     rbx, r14
0x180155628  mov     r8d, r13d; Size
0x18015562b  mov     byte ptr [rbx], 1
0x18015562e  lea     rcx, [rbx+8]; void *
0x180155632  mov     [rbx+2], si
0x180155636  mov     dword ptr [rbx+4], 2
0x18015563d  mov     rdx, [rdi]
0x180155640  mov     rdx, [rdx]; Src
0x180155643  call    memcpy_0
0x180155648  or      r13d, 0FFFFFFFFh
0x18015564c  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x180155650  mov     r8d, r13d; dwStartingAceIndex
0x180155653  mov     r9, rbx; pAceList
0x180155656  mov     edx, r15d; dwAceRevision
0x180155659  mov     rcx, r14; pAcl
0x18015565c  call    cs:__imp_AddAce
0x180155662  test    eax, eax
0x180155664  jz      loc_1801556F5
0x18015566a  xor     esi, esi
0x18015566c  xor     ebx, ebx
0x18015566e  cmp     dword ptr [rbp+pAclInformation], ebx
0x180155671  jbe     short loc_1801556C7
0x180155673  mov     rcx, [rdi+10h]; pAcl
0x180155677  lea     r8, [rbp+pAcl]; pAce
0x18015567b  mov     edx, ebx; dwAceIndex
0x18015567d  mov     [rbp+pAcl], 0
0x180155685  call    cs:__imp_GetAce
0x18015568b  test    eax, eax
0x18015568d  jz      short loc_1801556B7
0x18015568f  mov     r9, [rbp+pAcl]; pAceList
0x180155693  mov     r8d, r13d; dwStartingAceIndex
0x180155696  mov     edx, r15d; dwAceRevision
0x180155699  mov     rcx, r14; pAcl
0x18015569c  movzx   eax, word ptr [r9+2]
0x1801556a1  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1801556a5  call    cs:__imp_AddAce
0x1801556ab  test    eax, eax
0x1801556ad  mov     eax, 1
0x1801556b2  cmovz   esi, eax
0x1801556b5  jmp     short loc_1801556BC
0x1801556b7  mov     eax, 1
0x1801556bc  add     ebx, eax
0x1801556be  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1801556c1  jb      short loc_180155673
0x1801556c3  test    esi, esi
0x1801556c5  jnz     short loc_1801556F5
0x1801556c7  mov     rcx, [rdi+8]; handle
0x1801556cb  xor     r9d, r9d; psidOwner
0x1801556ce  mov     [rsp+70h+pSacl], 0; pSacl
0x1801556d7  mov     r8d, 20000004h; SecurityInfo
0x1801556dd  mov     [rsp+70h+pDacl], r14; pDacl
0x1801556e2  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x1801556eb  lea     edx, [r9+4]; ObjectType
0x1801556ef  call    cs:__imp_SetSecurityInfo
0x1801556f5  mov     rcx, r14; hMem
0x1801556f8  call    cs:__imp_LocalFree
0x1801556fe  mov     rcx, [rbp+var_10]
0x180155702  xor     rcx, rsp; StackCookie
0x180155705  call    __security_check_cookie
0x18015570a  lea     r11, [rsp+70h+var_s0]
0x18015570f  mov     rbx, [r11+38h]
0x180155713  mov     rsi, [r11+40h]
0x180155717  mov     rsp, r11
0x18015571a  pop     r15
0x18015571c  pop     r14
0x18015571e  pop     r13
0x180155720  pop     rdi
0x180155721  pop     rbp
0x180155722  retn
```
