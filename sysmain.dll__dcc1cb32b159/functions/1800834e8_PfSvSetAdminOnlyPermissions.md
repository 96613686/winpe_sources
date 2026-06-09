# PfSvSetAdminOnlyPermissions

- ea: `0x1800834e8`
- end: `0x180083687`
- name: `PfSvSetAdminOnlyPermissions`
- size: `415`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180023244`
- `0x180073670`

## callees

- `0x1800834e8`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083560`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008356f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008356f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180083630`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180083630`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800835b8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800835b8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800835dd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800835dd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180083553`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180083553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008365b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008365b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008359a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008359a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008358c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008364d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008358c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008364d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008361f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008361f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180083611`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180083611`

## pseudocode

```c
__int64 __fastcall PfSvSetAdminOnlyPermissions(LPWSTR pObjectName)
{
  struct _ACL *pDacl; // rbx
  DWORD LastError; // eax
  DWORD v4; // edi
  HANDLE ProcessHeap; // rcx
  struct _ACL *v6; // rax
  unsigned int v7; // edi
  HANDLE v8; // rcx
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = GetLengthSid(pSid) + 16;
    if ( *(_QWORD *)&PfSvcGlobals )
      ProcessHeap = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
    else
      ProcessHeap = GetProcessHeap();
    v6 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v4);
    pDacl = v6;
    if ( !v6 )
    {
      v7 = 8;
      goto LABEL_15;
    }
    if ( InitializeAcl(v6, v4, 2u) && AddAccessAllowedAceEx(pDacl, 2u, 3u, 0x10000000u, pSid) )
    {
      if ( pObjectName )
        LastError = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000005, pSid, 0, pDacl, 0);
      else
        LastError = SetSecurityInfo(0, SE_FILE_OBJECT, 5u, pSid, 0, pDacl, 0);
      goto LABEL_14;
    }
  }
  else
  {
    pDacl = 0;
  }
  LastError = GetLastError();
LABEL_14:
  v7 = LastError;
LABEL_15:
  if ( pSid )
    FreeSid(pSid);
  if ( pDacl )
  {
    if ( *(_QWORD *)&PfSvcGlobals )
      v8 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
    else
      v8 = GetProcessHeap();
    HeapFree(v8, 0, pDacl);
  }
  return v7;
}

```

## disassembly

```asm
0x1800834e8  mov     r11, rsp
0x1800834eb  mov     [r11+10h], rbx
0x1800834ef  mov     [r11+18h], rsi
0x1800834f3  push    rbp
0x1800834f4  push    rdi
0x1800834f5  push    r14
0x1800834f7  mov     rbp, rsp
0x1800834fa  sub     rsp, 80h
0x180083501  mov     rax, cs:__security_cookie
0x180083508  xor     rax, rsp
0x18008350b  mov     [rbp+var_10], rax
0x18008350f  xor     r14d, r14d
0x180083512  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180083518  lea     rax, [rbp+pSid]
0x18008351c  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x180083520  mov     [r11-48h], rax
0x180083524  mov     rsi, rcx
0x180083527  mov     [r11-50h], r14d
0x18008352b  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18008352f  mov     [r11-58h], r14d
0x180083533  lea     r8d, [r14+20h]; nSubAuthority0
0x180083537  mov     [r11-60h], r14d
0x18008353b  mov     r9d, 220h; nSubAuthority1
0x180083541  mov     [r11-68h], r14d
0x180083545  mov     dl, 2; nSubAuthorityCount
0x180083547  mov     [r11-70h], r14d
0x18008354b  mov     [r11-78h], r14d
0x18008354f  mov     [rbp+pSid], r14
0x180083553  call    cs:__imp_AllocateAndInitializeSid
0x180083559  test    eax, eax
0x18008355b  jnz     short loc_18008356B
0x18008355d  mov     ebx, r14d
0x180083560  call    cs:__imp_GetLastError
0x180083566  jmp     loc_180083625
0x18008356b  mov     rcx, [rbp+pSid]; pSid
0x18008356f  call    cs:__imp_GetLengthSid
0x180083575  mov     rcx, cs:PfSvcGlobals
0x18008357c  lea     edi, [rax+10h]
0x18008357f  mov     ebx, edi
0x180083581  test    rcx, rcx
0x180083584  jz      short loc_18008358C
0x180083586  mov     rcx, [rcx+58h]
0x18008358a  jmp     short loc_180083595
0x18008358c  call    cs:__imp_GetProcessHeap
0x180083592  mov     rcx, rax; hHeap
0x180083595  mov     r8, rbx; dwBytes
0x180083598  xor     edx, edx; dwFlags
0x18008359a  call    cs:__imp_HeapAlloc
0x1800835a0  mov     rbx, rax
0x1800835a3  test    rax, rax
0x1800835a6  jnz     short loc_1800835AD
0x1800835a8  lea     edi, [rax+8]
0x1800835ab  jmp     short loc_180083627
0x1800835ad  mov     r8d, 2; dwAclRevision
0x1800835b3  mov     edx, edi; nAclLength
0x1800835b5  mov     rcx, rbx; pAcl
0x1800835b8  call    cs:__imp_InitializeAcl
0x1800835be  test    eax, eax
0x1800835c0  jz      short loc_180083560
0x1800835c2  mov     rax, [rbp+pSid]
0x1800835c6  mov     edx, 2; dwAceRevision
0x1800835cb  mov     r9d, 10000000h; AccessMask
0x1800835d1  mov     [rsp+80h+psidGroup], rax; pSid
0x1800835d6  mov     rcx, rbx; pAcl
0x1800835d9  lea     r8d, [rdx+1]; AceFlags
0x1800835dd  call    cs:__imp_AddAccessAllowedAceEx
0x1800835e3  test    eax, eax
0x1800835e5  jz      loc_180083560
0x1800835eb  mov     r9, [rbp+pSid]; psidOwner
0x1800835ef  mov     edx, 1; ObjectType
0x1800835f4  mov     [rsp+80h+pSacl], r14; pSacl
0x1800835f9  mov     [rsp+80h+pDacl], rbx; pDacl
0x1800835fe  mov     [rsp+80h+psidGroup], r14; psidGroup
0x180083603  test    rsi, rsi
0x180083606  jz      short loc_180083619
0x180083608  mov     r8d, 80000005h; SecurityInfo
0x18008360e  mov     rcx, rsi; pObjectName
0x180083611  call    cs:__imp_SetNamedSecurityInfoW
0x180083617  jmp     short loc_180083625
0x180083619  xor     ecx, ecx; handle
0x18008361b  lea     r8d, [rcx+5]; SecurityInfo
0x18008361f  call    cs:__imp_SetSecurityInfo
0x180083625  mov     edi, eax
0x180083627  mov     rcx, [rbp+pSid]; pSid
0x18008362b  test    rcx, rcx
0x18008362e  jz      short loc_180083636
0x180083630  call    cs:__imp_FreeSid
0x180083636  test    rbx, rbx
0x180083639  jz      short loc_180083661
0x18008363b  mov     rcx, cs:PfSvcGlobals
0x180083642  test    rcx, rcx
0x180083645  jz      short loc_18008364D
0x180083647  mov     rcx, [rcx+58h]
0x18008364b  jmp     short loc_180083656
0x18008364d  call    cs:__imp_GetProcessHeap
0x180083653  mov     rcx, rax; hHeap
0x180083656  mov     r8, rbx; lpMem
0x180083659  xor     edx, edx; dwFlags
0x18008365b  call    cs:__imp_HeapFree
0x180083661  mov     eax, edi
0x180083663  mov     rcx, [rbp+var_10]
0x180083667  xor     rcx, rsp; StackCookie
0x18008366a  call    __security_check_cookie
0x18008366f  lea     r11, [rsp+80h+var_s0]
0x180083677  mov     rbx, [r11+28h]
0x18008367b  mov     rsi, [r11+30h]
0x18008367f  mov     rsp, r11
0x180083682  pop     r14
0x180083684  pop     rdi
0x180083685  pop     rbp
0x180083686  retn
```
