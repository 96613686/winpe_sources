# CreateSecurityDescriptorHelper(ACE_DATA *,ulong,void *,void *,void * *)

- ea: `0x1800504d4`
- end: `0x1800508a0`
- name: `?CreateSecurityDescriptorHelper@@YAKPEAUACE_DATA@@KPEAX1PEAPEAX@Z`
- size: `972`
- prototype: `unsigned int __fastcall(struct ACE_DATA *, unsigned int, void *, void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800508a8`

## callees

- `0x1800504d4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180050885`
- `KERNEL32!LocalFree` at `0x180050893`
- `KERNEL32!LocalFree` at `0x18007781f`
- `KERNEL32!LocalFree` at `0x180077836`
- `KERNEL32!LocalFree` at `0x180050885`
- `KERNEL32!LocalFree` at `0x180050893`
- `KERNEL32!LocalFree` at `0x18007781f`
- `KERNEL32!LocalFree` at `0x180077836`
- `KERNEL32!LocalAlloc` at `0x1800505b9`
- `KERNEL32!LocalAlloc` at `0x180050651`
- `KERNEL32!LocalAlloc` at `0x1800505b9`
- `KERNEL32!LocalAlloc` at `0x180050651`
- `KERNEL32!GetLastError` at `0x18005060c`
- `KERNEL32!GetLastError` at `0x1800507a1`
- `KERNEL32!GetLastError` at `0x18005060c`
- `KERNEL32!GetLastError` at `0x1800507a1`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800507d0`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800507d0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180050857`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180050857`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050797`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050797`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005083c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005083c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800507f3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800507f3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180050602`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005063f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180050602`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005063f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180050809`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180050809`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050529`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800506af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050788`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050529`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800506af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180050788`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005081f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18005081f`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptorHelper(struct ACE_DATA *a1, unsigned int a2, void *a3, void *a4, void **a5)
{
  struct ACE_DATA *v5; // rax
  DWORD LastError; // edi
  DWORD v7; // r14d
  DWORD v8; // r12d
  DWORD v9; // r13d
  _WORD *v10; // r15
  unsigned int v11; // esi
  DWORD LengthSid; // ecx
  DWORD v13; // ecx
  unsigned int v15; // eax
  struct _ACL *v16; // rax
  struct _ACL *v17; // rsi
  struct _ACL *v18; // rcx
  struct _ACL *v19; // rbx
  unsigned int i; // r14d
  DWORD nAceListLength; // r13d
  void *v22; // rdi
  int v23; // edx
  char v24; // al
  char v25; // cl
  DWORD v26; // eax
  struct _ACL *pDacl; // [rsp+40h] [rbp-68h]
  struct _ACL *pSacl; // [rsp+50h] [rbp-58h]
  unsigned int v30; // [rsp+B8h] [rbp+10h]
  struct _ACL *pAcl; // [rsp+C0h] [rbp+18h]

  v30 = a2;
  v5 = a1;
  LastError = 0;
  pDacl = 0;
  pSacl = 0;
  v7 = 8;
  v8 = 8;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  while ( v11 < a2 )
  {
    LengthSid = GetLengthSid(**((PSID **)v5 + 2 * v11 + 1));
    if ( !*((_BYTE *)a1 + 16 * v11) || *((_BYTE *)a1 + 16 * v11) == 1 )
    {
      v13 = LengthSid + 12;
      v7 += v13;
    }
    else
    {
      if ( *((_BYTE *)a1 + 16 * v11) != 2 )
        return 87;
      v13 = LengthSid + 12;
      v8 += v13;
    }
    ++v11;
    if ( v9 > v13 )
      v13 = v9;
    v9 = v13;
    v5 = a1;
    a2 = v30;
  }
  v15 = 40;
  if ( v7 != 8 )
    v15 = v7 + 40;
  if ( v8 != 8 )
    v15 += v8;
  v16 = (struct _ACL *)LocalAlloc(0x40u, v15);
  v17 = v16;
  if ( !v16 )
  {
    LastError = 8;
    goto LABEL_45;
  }
  v18 = v16 + 5;
  v19 = v16 + 5;
  if ( v7 != 8 )
  {
    pDacl = v16 + 5;
    v19 = (struct _ACL *)((char *)v18 + v7);
    if ( !InitializeAcl(v18, v7, 2u) )
      goto LABEL_20;
  }
  if ( v8 != 8 )
  {
    pSacl = v19;
    if ( !InitializeAcl(v19, v8, 2u) )
      goto LABEL_20;
  }
  v10 = LocalAlloc(0x40u, v9);
  if ( !v10 )
  {
    LastError = 8;
    goto LABEL_45;
  }
  for ( i = 0; i < v30; ++i )
  {
    pAcl = 0;
    nAceListLength = GetLengthSid(**((PSID **)a1 + 2 * i + 1));
    if ( *((_BYTE *)a1 + 16 * i) )
    {
      if ( *((_BYTE *)a1 + 16 * i) == 1 )
      {
        nAceListLength += 12;
        pAcl = pDacl;
        v22 = (void *)**((_QWORD **)a1 + 2 * i + 1);
        v23 = *((_DWORD *)a1 + 4 * i + 1);
        v24 = *((_BYTE *)a1 + 16 * i + 2);
        v25 = *((_BYTE *)a1 + 16 * i + 1);
        *(_BYTE *)v10 = 1;
      }
      else
      {
        if ( *((_BYTE *)a1 + 16 * i) != 2 )
          goto LABEL_36;
        nAceListLength += 12;
        pAcl = pSacl;
        v22 = (void *)**((_QWORD **)a1 + 2 * i + 1);
        v23 = *((_DWORD *)a1 + 4 * i + 1);
        v24 = *((_BYTE *)a1 + 16 * i + 2);
        v25 = *((_BYTE *)a1 + 16 * i + 1);
        *(_BYTE *)v10 = 2;
      }
    }
    else
    {
      nAceListLength += 12;
      pAcl = pDacl;
      v22 = (void *)**((_QWORD **)a1 + 2 * i + 1);
      v23 = *((_DWORD *)a1 + 4 * i + 1);
      v24 = *((_BYTE *)a1 + 16 * i + 2);
      v25 = *((_BYTE *)a1 + 16 * i + 1);
      *(_BYTE *)v10 = 0;
    }
    v10[1] = nAceListLength;
    *((_BYTE *)v10 + 1) = v24 | v25;
    *((_DWORD *)v10 + 1) = v23;
    v26 = GetLengthSid(v22);
    if ( CopySid(v26, v10 + 4, v22) )
      LastError = 0;
    else
      LastError = GetLastError();
LABEL_36:
    if ( LastError )
      goto LABEL_45;
    if ( !AddAce(pAcl, 2u, 0xFFFFFFFF, v10, nAceListLength) )
      goto LABEL_20;
  }
  if ( !InitializeSecurityDescriptor(v17, 1u)
    || !SetSecurityDescriptorOwner(v17, 0, 0)
    || !SetSecurityDescriptorGroup(v17, 0, 0)
    || !SetSecurityDescriptorDacl(v17, 1, pDacl, 0)
    || !SetSecurityDescriptorSacl(v17, 0, pSacl, 0) )
  {
LABEL_20:
    LastError = GetLastError();
    goto LABEL_45;
  }
  *a5 = v17;
  v17 = 0;
  LastError = 0;
LABEL_45:
  if ( v17 )
    LocalFree(v17);
  if ( v10 )
    LocalFree(v10);
  return LastError;
}

```

## disassembly

```asm
0x1800504d4  mov     r11, rsp
0x1800504d7  mov     [r11+18h], r8
0x1800504db  mov     [rsp+arg_8], edx
0x1800504df  mov     [r11+8], rcx
0x1800504e3  push    rbx
0x1800504e4  push    rsi
0x1800504e5  push    rdi
0x1800504e6  push    r12
0x1800504e8  push    r13
0x1800504ea  push    r14
0x1800504ec  push    r15
0x1800504ee  sub     rsp, 70h
0x1800504f2  mov     rax, rcx
0x1800504f5  xor     edi, edi
0x1800504f7  mov     [r11-60h], rdi
0x1800504fb  mov     [r11-68h], rdi
0x1800504ff  mov     [r11-58h], rdi
0x180050503  lea     ebx, [rdi+8]
0x180050506  mov     r14d, ebx
0x180050509  mov     r12d, ebx
0x18005050c  xor     r13d, r13d
0x18005050f  xor     r15d, r15d
0x180050512  mov     [r11-50h], r15
0x180050516  xor     esi, esi
0x180050518  cmp     esi, edx
0x18005051a  jnb     short loc_18005058D
0x18005051c  mov     ebx, esi
0x18005051e  add     rbx, rbx
0x180050521  mov     rcx, [rax+rbx*8+8]
0x180050526  mov     rcx, [rcx]; pSid
0x180050529  call    cs:__imp_GetLengthSid
0x18005052f  mov     ecx, eax
0x180050531  mov     rax, [rsp+0A8h+arg_0]
0x180050539  movzx   edx, byte ptr [rax+rbx*8]
0x18005053d  test    edx, edx
0x18005053f  jz      short loc_180050555
0x180050541  sub     edx, 1
0x180050544  jz      short loc_180050555
0x180050546  cmp     edx, 1
0x180050549  jnz     short loc_180050578
0x18005054b  lea     eax, [rcx+0Ch]
0x18005054e  mov     ecx, eax
0x180050550  add     r12d, eax
0x180050553  jmp     short loc_18005055B
0x180050555  add     ecx, 0Ch
0x180050558  add     r14d, ecx
0x18005055b  inc     esi
0x18005055d  cmp     r13d, ecx
0x180050560  cmova   ecx, r13d
0x180050564  mov     r13d, ecx
0x180050567  mov     rax, [rsp+0A8h+arg_0]
0x18005056f  mov     edx, [rsp+0A8h+arg_8]
0x180050576  jmp     short loc_180050518
0x180050578  mov     eax, 57h ; 'W'
0x18005057d  add     rsp, 70h
0x180050581  pop     r15
0x180050583  pop     r14
0x180050585  pop     r13
0x180050587  pop     r12
0x180050589  pop     rdi
0x18005058a  pop     rsi
0x18005058b  pop     rbx
0x18005058c  retn
0x18005058d  mov     eax, 28h ; '('
0x180050592  mov     [rsp+0A8h+var_74], eax
0x180050596  lea     ebx, [rax-20h]
0x180050599  cmp     r14d, ebx
0x18005059c  jz      short loc_1800505A6
0x18005059e  lea     eax, [r14+28h]
0x1800505a2  mov     [rsp+0A8h+var_74], eax
0x1800505a6  cmp     r12d, ebx
0x1800505a9  jz      short loc_1800505B2
0x1800505ab  add     eax, r12d
0x1800505ae  mov     [rsp+0A8h+var_74], eax
0x1800505b2  mov     edx, eax; uBytes
0x1800505b4  mov     ecx, 40h ; '@'; uFlags
0x1800505b9  call    cs:__imp_LocalAlloc
0x1800505bf  mov     rsi, rax
0x1800505c2  mov     [rsp+0A8h+var_60], rax
0x1800505c7  test    rax, rax
0x1800505ca  jnz     short loc_1800505D7
0x1800505cc  mov     edi, ebx
0x1800505ce  mov     [rsp+0A8h+var_78], ebx
0x1800505d2  jmp     loc_18005087D
0x1800505d7  lea     rcx, [rax+28h]; pAcl
0x1800505db  mov     rbx, rcx
0x1800505de  mov     [rsp+0A8h+var_48], rcx
0x1800505e3  cmp     r14d, 8
0x1800505e7  jz      short loc_18005061D
0x1800505e9  mov     [rsp+0A8h+pDacl], rcx
0x1800505ee  mov     ebx, r14d
0x1800505f1  add     rbx, rcx
0x1800505f4  mov     [rsp+0A8h+var_48], rbx
0x1800505f9  mov     r8d, 2; dwAclRevision
0x1800505ff  mov     edx, r14d; nAclLength
0x180050602  call    cs:__imp_InitializeAcl
0x180050608  test    eax, eax
0x18005060a  jnz     short loc_18005061D
0x18005060c  call    cs:__imp_GetLastError
0x180050612  mov     edi, eax
0x180050614  mov     [rsp+0A8h+var_78], eax
0x180050618  jmp     loc_18005087D
0x18005061d  cmp     r12d, 8
0x180050621  jz      short loc_180050649
0x180050623  mov     rcx, rbx; pAcl
0x180050626  mov     [rsp+0A8h+pSacl], rbx
0x18005062b  mov     eax, r12d
0x18005062e  add     rbx, rax
0x180050631  mov     [rsp+0A8h+var_48], rbx
0x180050636  mov     r8d, 2; dwAclRevision
0x18005063c  mov     edx, r12d; nAclLength
0x18005063f  call    cs:__imp_InitializeAcl
0x180050645  test    eax, eax
0x180050647  jz      short loc_18005060C
0x180050649  mov     edx, r13d; uBytes
0x18005064c  mov     ecx, 40h ; '@'; uFlags
0x180050651  call    cs:__imp_LocalAlloc
0x180050657  mov     r15, rax
0x18005065a  mov     [rsp+0A8h+var_50], rax
0x18005065f  test    rax, rax
0x180050662  jnz     short loc_18005066C
0x180050664  lea     edi, [rax+8]
0x180050667  jmp     loc_180050879
0x18005066c  xor     r14d, r14d
0x18005066f  mov     [rsp+0A8h+var_70], r14d
0x180050674  mov     r12, [rsp+0A8h+arg_0]
0x18005067c  cmp     r14d, [rsp+0A8h+arg_8]
0x180050684  jnb     loc_1800507EB
0x18005068a  mov     [rsp+0A8h+arg_18], 0
0x180050695  mov     [rsp+0A8h+pAcl], 0
0x1800506a1  mov     ebx, r14d
0x1800506a4  add     rbx, rbx
0x1800506a7  mov     rcx, [r12+rbx*8+8]
0x1800506ac  mov     rcx, [rcx]; pSid
0x1800506af  call    cs:__imp_GetLengthSid
0x1800506b5  mov     r13d, eax
0x1800506b8  mov     [rsp+0A8h+arg_18], eax
0x1800506bf  movzx   edx, byte ptr [r12+rbx*8]
0x1800506c4  test    edx, edx
0x1800506c6  jz      short loc_180050742
0x1800506c8  sub     edx, 1
0x1800506cb  jz      short loc_18005070C
0x1800506cd  cmp     edx, 1
0x1800506d0  jnz     loc_1800507B1
0x1800506d6  add     r13d, 0Ch
0x1800506da  mov     [rsp+0A8h+arg_18], r13d
0x1800506e2  mov     rax, [rsp+0A8h+pSacl]
0x1800506e7  mov     [rsp+0A8h+pAcl], rax
0x1800506ef  mov     rax, [r12+rbx*8+8]
0x1800506f4  mov     rdi, [rax]
0x1800506f7  mov     edx, [r12+rbx*8+4]
0x1800506fc  mov     al, [r12+rbx*8+2]
0x180050701  mov     cl, [r12+rbx*8+1]
0x180050706  mov     byte ptr [r15], 2
0x18005070a  jmp     short loc_180050776
0x18005070c  add     r13d, 0Ch
0x180050710  mov     [rsp+0A8h+arg_18], r13d
0x180050718  mov     rax, [rsp+0A8h+pDacl]
0x18005071d  mov     [rsp+0A8h+pAcl], rax
0x180050725  mov     rax, [r12+rbx*8+8]
0x18005072a  mov     rdi, [rax]
0x18005072d  mov     edx, [r12+rbx*8+4]
0x180050732  mov     al, [r12+rbx*8+2]
0x180050737  mov     cl, [r12+rbx*8+1]
0x18005073c  mov     byte ptr [r15], 1
0x180050740  jmp     short loc_180050776
0x180050742  add     r13d, 0Ch
0x180050746  mov     [rsp+0A8h+arg_18], r13d
0x18005074e  mov     rax, [rsp+0A8h+pDacl]
0x180050753  mov     [rsp+0A8h+pAcl], rax
0x18005075b  mov     rax, [r12+rbx*8+8]
0x180050760  mov     rdi, [rax]
0x180050763  mov     edx, [r12+rbx*8+4]
0x180050768  mov     al, [r12+rbx*8+2]
0x18005076d  mov     cl, [r12+rbx*8+1]
0x180050772  mov     byte ptr [r15], 0
0x180050776  mov     [r15+2], r13w
0x18005077b  or      cl, al
0x18005077d  mov     [r15+1], cl
0x180050781  mov     [r15+4], edx
0x180050785  mov     rcx, rdi; pSid
0x180050788  call    cs:__imp_GetLengthSid
0x18005078e  mov     ecx, eax; nDestinationSidLength
0x180050790  mov     r8, rdi; pSourceSid
0x180050793  lea     rdx, [r15+8]; pDestinationSid
0x180050797  call    cs:__imp_CopySid
0x18005079d  test    eax, eax
0x18005079f  jnz     short loc_1800507AB
0x1800507a1  call    cs:__imp_GetLastError
0x1800507a7  mov     edi, eax
0x1800507a9  jmp     short loc_1800507AD
0x1800507ab  xor     edi, edi
0x1800507ad  mov     [rsp+0A8h+var_78], edi
0x1800507b1  test    edi, edi
0x1800507b3  jnz     loc_18005087D
0x1800507b9  mov     [rsp+0A8h+nAceListLength], r13d; nAceListLength
0x1800507be  mov     r9, r15; pAceList
0x1800507c1  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800507c5  lea     edx, [rdi+2]; dwAceRevision
0x1800507c8  mov     rcx, [rsp+0A8h+pAcl]; pAcl
0x1800507d0  call    cs:__imp_AddAce
0x1800507d6  test    eax, eax
0x1800507d8  jz      loc_18005060C
0x1800507de  inc     r14d
0x1800507e1  mov     [rsp+0A8h+var_70], r14d
0x1800507e6  jmp     loc_18005067C
0x1800507eb  mov     edx, 1; dwRevision
0x1800507f0  mov     rcx, rsi; pSecurityDescriptor
0x1800507f3  call    cs:__imp_InitializeSecurityDescriptor
0x1800507f9  test    eax, eax
0x1800507fb  jz      loc_18005060C
0x180050801  xor     r8d, r8d; bOwnerDefaulted
0x180050804  xor     edx, edx; pOwner
0x180050806  mov     rcx, rsi; pSecurityDescriptor
0x180050809  call    cs:__imp_SetSecurityDescriptorOwner
0x18005080f  test    eax, eax
0x180050811  jz      loc_18005060C
0x180050817  xor     r8d, r8d; bGroupDefaulted
0x18005081a  xor     edx, edx; pGroup
0x18005081c  mov     rcx, rsi; pSecurityDescriptor
0x18005081f  call    cs:__imp_SetSecurityDescriptorGroup
0x180050825  test    eax, eax
0x180050827  jz      loc_18005060C
0x18005082d  xor     r9d, r9d; bDaclDefaulted
0x180050830  mov     r8, [rsp+0A8h+pDacl]; pDacl
0x180050835  lea     edx, [r9+1]; bDaclPresent
0x180050839  mov     rcx, rsi; pSecurityDescriptor
0x18005083c  call    cs:__imp_SetSecurityDescriptorDacl
0x180050842  test    eax, eax
0x180050844  jz      loc_18005060C
0x18005084a  xor     r9d, r9d; bSaclDefaulted
0x18005084d  mov     r8, [rsp+0A8h+pSacl]; pSacl
0x180050852  xor     edx, edx; bSaclPresent
0x180050854  mov     rcx, rsi; pSecurityDescriptor
0x180050857  call    cs:__imp_SetSecurityDescriptorSacl
0x18005085d  test    eax, eax
0x18005085f  jz      loc_18005060C
0x180050865  mov     rax, [rsp+0A8h+arg_20]
0x18005086d  mov     [rax], rsi
0x180050870  xor     esi, esi
0x180050872  mov     [rsp+0A8h+var_60], rsi
0x180050877  xor     edi, edi
0x180050879  mov     [rsp+0A8h+var_78], edi
0x18005087d  test    rsi, rsi
0x180050880  jz      short loc_18005088B
0x180050882  mov     rcx, rsi; hMem
0x180050885  call    cs:__imp_LocalFree
0x18005088b  test    r15, r15
0x18005088e  jz      short loc_180050899
0x180050890  mov     rcx, r15; hMem
0x180050893  call    cs:__imp_LocalFree
0x180050899  mov     eax, edi
0x18005089b  jmp     loc_18005057D
0x18007780d  push    rbp
0x18007780f  sub     rsp, 30h
0x180077813  mov     rbp, rdx
0x180077816  mov     rcx, [rbp+48h]; hMem
0x18007781a  test    rcx, rcx
0x18007781d  jz      short loc_18007782D
0x18007781f  call    cs:__imp_LocalFree
0x180077825  mov     qword ptr [rbp+48h], 0
0x18007782d  mov     rcx, [rbp+58h]; hMem
0x180077831  test    rcx, rcx
0x180077834  jz      short loc_180077844
0x180077836  call    cs:__imp_LocalFree
0x18007783c  mov     qword ptr [rbp+58h], 0
0x180077844  add     rsp, 30h
0x180077848  pop     rbp
0x180077849  retn
```
