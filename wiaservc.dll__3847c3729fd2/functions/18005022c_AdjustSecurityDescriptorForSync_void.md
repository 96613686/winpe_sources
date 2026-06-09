# AdjustSecurityDescriptorForSync(void *)

- ea: `0x18005022c`
- end: `0x1800504cd`
- name: `?AdjustSecurityDescriptorForSync@@YAHPEAX@Z`
- size: `673`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050c60`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18005022c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800504b2`
- `KERNEL32!LocalFree` at `0x1800504c0`
- `KERNEL32!LocalFree` at `0x1800777e2`
- `KERNEL32!LocalFree` at `0x1800777f2`
- `KERNEL32!LocalFree` at `0x1800504b2`
- `KERNEL32!LocalFree` at `0x1800504c0`
- `KERNEL32!LocalFree` at `0x1800777e2`
- `KERNEL32!LocalFree` at `0x1800777f2`
- `KERNEL32!LocalAlloc` at `0x180050290`
- `KERNEL32!LocalAlloc` at `0x1800503c5`
- `KERNEL32!LocalAlloc` at `0x180050290`
- `KERNEL32!LocalAlloc` at `0x1800503c5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180050442`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180050442`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180050334`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180050334`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18005049e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18005049e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180050489`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180050489`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005034a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005034a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005041a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005041a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800503e7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800503e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800503af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800503af`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005046d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18005046d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005038a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005038a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005036a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005036a`

## string_xrefs

- `0x1800502a3`: `AdjustSecurityDescriptorForSync, Out of memory!`
- `0x1800502c9`: `AdjustSecurityDescriptorForSync, Out of memory!`
- `0x1800502b5`: `AdjustSecurityDescriptorForSync`
- `0x1800502de`: `AdjustSecurityDescriptorForSync`

## pseudocode

```c
__int64 __fastcall AdjustSecurityDescriptorForSync(HANDLE Handle)
{
  HLOCAL v2; // r14
  char *v3; // rbx
  void *v4; // rdx
  void **v5; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  struct _ACL *v9; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  DWORD LengthSid; // eax
  DWORD v13; // esi
  struct _ACL *v14; // rax
  DWORD v15; // eax
  DWORD v16; // ebx
  WINBOOL bDaclPresent; // [rsp+30h] [rbp-88h] BYREF
  DWORD nLengthNeeded; // [rsp+34h] [rbp-84h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-80h] BYREF
  DWORD v20; // [rsp+3Ch] [rbp-7Ch]
  PACL pDacl; // [rsp+40h] [rbp-78h] BYREF
  struct _ACL *v22; // [rsp+48h] [rbp-70h]
  LPVOID pAce[2]; // [rsp+50h] [rbp-68h] BYREF
  __int64 pAclInformation; // [rsp+60h] [rbp-58h] BYREF
  int v25; // [rsp+68h] [rbp-50h]
  _BYTE pSecurityDescriptor[40]; // [rsp+70h] [rbp-48h] BYREF

  nLengthNeeded = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAclInformation = 0;
  v25 = 0;
  pAce[0] = 0;
  v2 = LocalAlloc(0x40u, 0x10028u);
  pAce[1] = v2;
  if ( v2 )
  {
    v9 = 0;
    v22 = 0;
    v10 = 0;
    if ( GetKernelObjectSecurity(Handle, 4u, v2, 0x10028u, &nLengthNeeded) )
    {
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
        goto LABEL_21;
      if ( !GetSecurityDescriptorDacl(v2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        goto LABEL_21;
      if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_21;
      v11 = HIDWORD(pAclInformation) + 8;
      if ( HIDWORD(pAclInformation) >= 0xFFFFFFF8 )
        goto LABEL_21;
      LengthSid = GetLengthSid(psidLocal);
      v13 = v11 + LengthSid;
      if ( v11 + LengthSid < v11 )
        goto LABEL_21;
      v14 = (struct _ACL *)LocalAlloc(0x40u, v13);
      v9 = v14;
      v22 = v14;
      if ( !v14 || !InitializeAcl(v14, v13, 2u) )
        goto LABEL_21;
      if ( bDaclPresent )
      {
        v15 = pAclInformation;
        if ( (_DWORD)pAclInformation )
        {
          v16 = 0;
          v20 = 0;
          while ( v16 < v15 )
          {
            if ( !GetAce(pDacl, v16, pAce) || !AddAce(v9, 2u, 0xFFFFFFFF, pAce[0], *((unsigned __int16 *)pAce[0] + 1)) )
              goto LABEL_21;
            v20 = ++v16;
            v15 = pAclInformation;
          }
        }
      }
      if ( AddAccessAllowedAce(v9, 2u, 0x120000u, psidLocal) && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0) )
        v10 = SetKernelObjectSecurity(Handle, 4u, pSecurityDescriptor);
      else
LABEL_21:
        v10 = 0;
    }
    LocalFree(v2);
    if ( v9 )
      LocalFree(v9);
    return v10;
  }
  else
  {
    v3 = (char *)WiaTrace_TraceLog("AdjustSecurityDescriptorForSync, Out of memory!");
    WriteDbgTraceErrorWI("AdjustSecurityDescriptorForSync", v3);
    WiaTrcLib::Free((WiaTrcLib *)v3, v4);
    v5 = (void **)WiaTrace_Trace("AdjustSecurityDescriptorForSync, Out of memory!");
    WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"AdjustSecurityDescriptorForSync", 1, v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18005022c  mov     r11, rsp
0x18005022f  mov     [r11+10h], rbx
0x180050233  mov     [r11+18h], rsi
0x180050237  push    rdi
0x180050238  push    r14
0x18005023a  push    r15
0x18005023c  sub     rsp, 0A0h
0x180050243  mov     rax, cs:__security_cookie
0x18005024a  xor     rax, rsp
0x18005024d  mov     [rsp+0B8h+var_20], rax
0x180050255  mov     r15, rcx
0x180050258  mov     [rsp+0B8h+nLengthNeeded], 0
0x180050260  mov     qword ptr [r11-78h], 0
0x180050268  mov     [rsp+0B8h+bDaclPresent], 0
0x180050270  mov     [rsp+0B8h+bDaclDefaulted], 0
0x180050278  xor     eax, eax
0x18005027a  mov     [r11-58h], rax
0x18005027e  mov     [rsp+0B8h+var_50], eax
0x180050282  mov     [r11-68h], rax
0x180050286  mov     esi, 10028h
0x18005028b  mov     edx, esi; uBytes
0x18005028d  lea     ecx, [rax+40h]; uFlags
0x180050290  call    cs:__imp_LocalAlloc
0x180050296  mov     r14, rax
0x180050299  mov     [rsp+0B8h+var_60], rax
0x18005029e  test    rax, rax
0x1800502a1  jnz     short loc_180050315
0x1800502a3  lea     rcx, aAdjustsecurity_0; "AdjustSecurityDescriptorForSync, Out of"...
0x1800502aa  call    WiaTrace_TraceLog
0x1800502af  mov     rbx, rax
0x1800502b2  mov     rdx, rax; char *
0x1800502b5  lea     rcx, aAdjustsecurity; "AdjustSecurityDescriptorForSync"
0x1800502bc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800502c1  mov     rcx, rbx; this
0x1800502c4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800502c9  lea     rcx, aAdjustsecurity_0; "AdjustSecurityDescriptorForSync, Out of"...
0x1800502d0  call    WiaTrace_Trace
0x1800502d5  mov     [rsp+0B8h+lpnLengthNeeded], rax; lpMem
0x1800502da  lea     r9d, [r14+1]; int
0x1800502de  lea     r8, aAdjustsecurity; "AdjustSecurityDescriptorForSync"
0x1800502e5  call    WiaTrace_ProcessTrace_Ex
0x1800502ea  xor     eax, eax
0x1800502ec  mov     rcx, [rsp+0B8h+var_20]
0x1800502f4  xor     rcx, rsp; StackCookie
0x1800502f7  call    __security_check_cookie
0x1800502fc  lea     r11, [rsp+0B8h+var_18]
0x180050304  mov     rbx, [r11+28h]
0x180050308  mov     rsi, [r11+30h]
0x18005030c  mov     rsp, r11
0x18005030f  pop     r15
0x180050311  pop     r14
0x180050313  pop     rdi
0x180050314  retn
0x180050315  xor     edi, edi
0x180050317  mov     [rsp+0B8h+var_70], rdi
0x18005031c  xor     ebx, ebx
0x18005031e  lea     rax, [rsp+0B8h+nLengthNeeded]
0x180050323  mov     [rsp+0B8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180050328  mov     r9d, esi; nLength
0x18005032b  mov     r8, r14; pSecurityDescriptor
0x18005032e  lea     edx, [rdi+4]; RequestedInformation
0x180050331  mov     rcx, r15; Handle
0x180050334  call    cs:__imp_GetKernelObjectSecurity
0x18005033a  test    eax, eax
0x18005033c  jz      loc_1800504AF
0x180050342  lea     edx, [rdi+1]; dwRevision
0x180050345  lea     rcx, [rsp+0B8h+pSecurityDescriptor]; pSecurityDescriptor
0x18005034a  call    cs:__imp_InitializeSecurityDescriptor
0x180050350  test    eax, eax
0x180050352  jz      loc_1800504AD
0x180050358  lea     r9, [rsp+0B8h+bDaclDefaulted]; lpbDaclDefaulted
0x18005035d  lea     r8, [rsp+0B8h+pDacl]; pDacl
0x180050362  lea     rdx, [rsp+0B8h+bDaclPresent]; lpbDaclPresent
0x180050367  mov     rcx, r14; pSecurityDescriptor
0x18005036a  call    cs:__imp_GetSecurityDescriptorDacl
0x180050370  test    eax, eax
0x180050372  jz      loc_1800504AD
0x180050378  lea     r9d, [rdi+2]; dwAclInformationClass
0x18005037c  lea     r8d, [rdi+0Ch]; nAclInformationLength
0x180050380  lea     rdx, [rsp+0B8h+pAclInformation]; pAclInformation
0x180050385  mov     rcx, [rsp+0B8h+pDacl]; pAcl
0x18005038a  call    cs:__imp_GetAclInformation
0x180050390  test    eax, eax
0x180050392  jz      loc_1800504AD
0x180050398  mov     eax, [rsp+0B8h+var_54]
0x18005039c  lea     ebx, [rax+8]
0x18005039f  cmp     ebx, 8
0x1800503a2  jb      loc_1800504AD
0x1800503a8  mov     rcx, cs:?psidLocal@@3PEAXEA; pSid
0x1800503af  call    cs:__imp_GetLengthSid
0x1800503b5  lea     esi, [rbx+rax]
0x1800503b8  cmp     esi, ebx
0x1800503ba  jb      loc_1800504AD
0x1800503c0  mov     edx, esi; uBytes
0x1800503c2  lea     ecx, [rdi+40h]; uFlags
0x1800503c5  call    cs:__imp_LocalAlloc
0x1800503cb  mov     rdi, rax
0x1800503ce  mov     [rsp+0B8h+var_70], rax
0x1800503d3  test    rax, rax
0x1800503d6  jz      loc_1800504AD
0x1800503dc  mov     r8d, 2; dwAclRevision
0x1800503e2  mov     edx, esi; nAclLength
0x1800503e4  mov     rcx, rax; pAcl
0x1800503e7  call    cs:__imp_InitializeAcl
0x1800503ed  test    eax, eax
0x1800503ef  jz      loc_1800504AD
0x1800503f5  cmp     [rsp+0B8h+bDaclPresent], 0
0x1800503fa  jz      short loc_180050458
0x1800503fc  mov     eax, [rsp+0B8h+pAclInformation]
0x180050400  test    eax, eax
0x180050402  jz      short loc_180050458
0x180050404  xor     ebx, ebx
0x180050406  mov     [rsp+0B8h+var_7C], ebx
0x18005040a  cmp     ebx, eax
0x18005040c  jnb     short loc_180050458
0x18005040e  lea     r8, [rsp+0B8h+pAce]; pAce
0x180050413  mov     edx, ebx; dwAceIndex
0x180050415  mov     rcx, [rsp+0B8h+pDacl]; pAcl
0x18005041a  call    cs:__imp_GetAce
0x180050420  test    eax, eax
0x180050422  jz      loc_1800504AD
0x180050428  mov     r9, [rsp+0B8h+pAce]; pAceList
0x18005042d  movzx   eax, word ptr [r9+2]
0x180050432  mov     dword ptr [rsp+0B8h+lpnLengthNeeded], eax; nAceListLength
0x180050436  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18005043a  mov     edx, 2; dwAceRevision
0x18005043f  mov     rcx, rdi; pAcl
0x180050442  call    cs:__imp_AddAce
0x180050448  test    eax, eax
0x18005044a  jz      short loc_1800504AD
0x18005044c  inc     ebx
0x18005044e  mov     [rsp+0B8h+var_7C], ebx
0x180050452  mov     eax, [rsp+0B8h+pAclInformation]
0x180050456  jmp     short loc_18005040A
0x180050458  mov     r9, cs:?psidLocal@@3PEAXEA; pSid
0x18005045f  mov     edx, 2; dwAceRevision
0x180050464  mov     r8d, 120000h; AccessMask
0x18005046a  mov     rcx, rdi; pAcl
0x18005046d  call    cs:__imp_AddAccessAllowedAce
0x180050473  test    eax, eax
0x180050475  jz      short loc_1800504AD
0x180050477  xor     r9d, r9d; bDaclDefaulted
0x18005047a  mov     r8, rdi; pDacl
0x18005047d  lea     edx, [r9+1]; bDaclPresent
0x180050481  lea     rbx, [rsp+0B8h+pSecurityDescriptor]
0x180050486  mov     rcx, rbx; pSecurityDescriptor
0x180050489  call    cs:__imp_SetSecurityDescriptorDacl
0x18005048f  test    eax, eax
0x180050491  jz      short loc_1800504AD
0x180050493  mov     r8, rbx; SecurityDescriptor
0x180050496  mov     edx, 4; SecurityInformation
0x18005049b  mov     rcx, r15; Handle
0x18005049e  call    cs:__imp_SetKernelObjectSecurity
0x1800504a4  xor     ebx, ebx
0x1800504a6  test    eax, eax
0x1800504a8  setnz   bl
0x1800504ab  jmp     short loc_1800504AF
0x1800504ad  xor     ebx, ebx
0x1800504af  mov     rcx, r14; hMem
0x1800504b2  call    cs:__imp_LocalFree
0x1800504b8  test    rdi, rdi
0x1800504bb  jz      short loc_1800504C6
0x1800504bd  mov     rcx, rdi; hMem
0x1800504c0  call    cs:__imp_LocalFree
0x1800504c6  mov     eax, ebx
0x1800504c8  jmp     loc_1800502EC
0x1800777d0  push    rbp
0x1800777d2  sub     rsp, 30h
0x1800777d6  mov     rbp, rdx
0x1800777d9  mov     rcx, [rbp+58h]; hMem
0x1800777dd  test    rcx, rcx
0x1800777e0  jz      short loc_1800777E9
0x1800777e2  call    cs:__imp_LocalFree
0x1800777e8  nop
0x1800777e9  mov     rcx, [rbp+48h]; hMem
0x1800777ed  test    rcx, rcx
0x1800777f0  jz      short loc_180077800
0x1800777f2  call    cs:__imp_LocalFree
0x1800777f8  mov     qword ptr [rbp+48h], 0
0x180077800  add     rsp, 30h
0x180077804  pop     rbp
0x180077805  retn
```
