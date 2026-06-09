# SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)

- ea: `0x180027a9c`
- end: `0x180027c63`
- name: `?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z`
- size: `455`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, void *const@<r9>, unsigned __int8)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024f08`
- `0x1800252f0`
- `0x180025c68`

## callees

- `0x180027a9c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027c11`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027c11`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180027b0d`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180027b0d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027bb8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027bfc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027bb8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027bfc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180027b48`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180027b48`

## pseudocode

```c
__int64 __fastcall SxAddKnownAce(PACL pAcl, BYTE a2, int a3, void *const a4, BYTE a5)
{
  __int16 v9; // ax
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  PACL v14; // rbx
  unsigned int i; // ecx
  DWORD LengthSid; // eax
  WORD v17; // dx
  bool v18; // cc
  DWORD v19; // eax
  __int64 v20; // rcx
  unsigned int v22; // [rsp+20h] [rbp-40h] BYREF
  __int16 v23; // [rsp+24h] [rbp-3Ch]
  __int16 v24; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "SxAddKnownAce", 0x292u, 1u);
  v9 = 666;
  if ( !pAcl || (v23 = 666, v9 = 667, !a4) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_3;
  }
  v22 = 0;
  v23 = 667;
  if ( IsValidAcl(pAcl) )
  {
    v22 = 0;
    v23 = 669;
    if ( !IsValidSid(a4) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
      v22 = LastFailureAsHRESULT;
      v12 = 670;
      goto LABEL_7;
    }
    v22 = 0;
    v23 = 670;
    v14 = pAcl + 1;
    for ( i = 0; i < pAcl->AceCount; ++i )
      v14 = (PACL)((char *)v14 + v14->AclSize);
    v9 = 680;
    if ( v14 < &pAcl[pAcl->AclSize] )
    {
      v23 = 680;
      LengthSid = GetLengthSid(a4);
      v17 = LengthSid + 8;
      v18 = (char *)&v14[1] + LengthSid <= (char *)pAcl + pAcl->AclSize;
      v9 = 685;
      if ( v18 )
      {
        v22 = 0;
        v23 = 685;
        v14->Sbz1 = a2;
        v14->AclRevision = a5;
        v14->AclSize = v17;
        *(_DWORD *)&v14->AceCount = a3;
        v19 = GetLengthSid(a4);
        if ( !CopySid(v19, &v14[1], a4) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
          v22 = LastFailureAsHRESULT;
          v12 = 695;
          goto LABEL_7;
        }
        LastFailureAsHRESULT = 0;
        v23 = 695;
        ++pAcl->AceCount;
LABEL_18:
        v22 = LastFailureAsHRESULT;
        goto LABEL_19;
      }
    }
    LastFailureAsHRESULT = -2130706378;
LABEL_3:
    v24 = v9;
    goto LABEL_18;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
  v22 = LastFailureAsHRESULT;
  v12 = 669;
LABEL_7:
  v24 = v12;
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180027a9c  push    rbp
0x180027a9e  push    rbx
0x180027a9f  push    rsi
0x180027aa0  push    rdi
0x180027aa1  push    r13
0x180027aa3  push    r14
0x180027aa5  push    r15
0x180027aa7  mov     rbp, rsp
0x180027aaa  sub     rsp, 60h
0x180027aae  mov     rsi, r9
0x180027ab1  mov     r14d, r8d
0x180027ab4  mov     r15b, dl
0x180027ab7  mov     rdi, rcx
0x180027aba  mov     r13d, 1
0x180027ac0  mov     r9d, r13d; unsigned __int16
0x180027ac3  mov     r8d, 292h; unsigned __int16
0x180027ac9  lea     rdx, aSxaddknownace; "SxAddKnownAce"
0x180027ad0  lea     rcx, [rbp+var_40]; this
0x180027ad4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027ad9  mov     eax, 29Ah
0x180027ade  test    rdi, rdi
0x180027ae1  jnz     short loc_180027AF1
0x180027ae3  mov     ebx, 80070057h
0x180027ae8  mov     [rbp+var_3A], ax
0x180027aec  jmp     loc_180027C45
0x180027af1  mov     [rbp+var_3C], ax
0x180027af5  mov     eax, 29Bh
0x180027afa  test    rsi, rsi
0x180027afd  jz      short loc_180027AE3
0x180027aff  mov     [rbp+var_40], 0
0x180027b06  mov     [rbp+var_3C], ax
0x180027b0a  mov     rcx, rdi; pAcl
0x180027b0d  call    cs:__imp_IsValidAcl
0x180027b14  nop     dword ptr [rax+rax+00h]
0x180027b19  test    eax, eax
0x180027b1b  jnz     short loc_180027B35
0x180027b1d  call    GetLastFailureAsHRESULT
0x180027b22  mov     ebx, eax
0x180027b24  mov     [rbp+var_40], eax
0x180027b27  mov     eax, 29Dh
0x180027b2c  mov     [rbp+var_3A], ax
0x180027b30  jmp     loc_180027C48
0x180027b35  mov     [rbp+var_40], 0
0x180027b3c  mov     eax, 29Dh
0x180027b41  mov     [rbp+var_3C], ax
0x180027b45  mov     rcx, rsi; pSid
0x180027b48  call    cs:__imp_IsValidSid
0x180027b4f  nop     dword ptr [rax+rax+00h]
0x180027b54  test    eax, eax
0x180027b56  jnz     short loc_180027B69
0x180027b58  call    GetLastFailureAsHRESULT
0x180027b5d  mov     ebx, eax
0x180027b5f  mov     [rbp+var_40], eax
0x180027b62  mov     eax, 29Eh
0x180027b67  jmp     short loc_180027B2C
0x180027b69  mov     [rbp+var_40], 0
0x180027b70  mov     eax, 29Eh
0x180027b75  mov     [rbp+var_3C], ax
0x180027b79  lea     rbx, [rdi+8]
0x180027b7d  xor     ecx, ecx
0x180027b7f  movzx   edx, word ptr [rdi+4]
0x180027b83  test    edx, edx
0x180027b85  jz      short loc_180027B95
0x180027b87  movzx   eax, word ptr [rbx+2]
0x180027b8b  add     rbx, rax
0x180027b8e  add     ecx, r13d
0x180027b91  cmp     ecx, edx
0x180027b93  jb      short loc_180027B87
0x180027b95  movzx   eax, word ptr [rdi+2]
0x180027b99  lea     rcx, [rdi+rax*8]
0x180027b9d  mov     eax, 2A8h
0x180027ba2  cmp     rbx, rcx
0x180027ba5  jb      short loc_180027BB1
0x180027ba7  mov     ebx, 81000036h
0x180027bac  jmp     loc_180027AE8
0x180027bb1  mov     [rbp+var_3C], ax
0x180027bb5  mov     rcx, rsi; pSid
0x180027bb8  call    cs:__imp_GetLengthSid
0x180027bbf  nop     dword ptr [rax+rax+00h]
0x180027bc4  lea     edx, [rax+8]
0x180027bc7  movzx   ecx, word ptr [rdi+2]
0x180027bcb  add     rcx, rdi
0x180027bce  mov     eax, edx
0x180027bd0  add     rax, rbx
0x180027bd3  cmp     rax, rcx
0x180027bd6  mov     eax, 2ADh
0x180027bdb  ja      short loc_180027BA7
0x180027bdd  mov     [rbp+var_40], 0
0x180027be4  mov     [rbp+var_3C], ax
0x180027be8  mov     [rbx+1], r15b
0x180027bec  mov     al, [rbp+arg_20]
0x180027bef  mov     [rbx], al
0x180027bf1  mov     [rbx+2], dx
0x180027bf5  mov     [rbx+4], r14d
0x180027bf9  mov     rcx, rsi; pSid
0x180027bfc  call    cs:__imp_GetLengthSid
0x180027c03  nop     dword ptr [rax+rax+00h]
0x180027c08  mov     ecx, eax; nDestinationSidLength
0x180027c0a  mov     r8, rsi; pSourceSid
0x180027c0d  lea     rdx, [rbx+8]; pDestinationSid
0x180027c11  call    cs:__imp_CopySid
0x180027c18  nop     dword ptr [rax+rax+00h]
0x180027c1d  test    eax, eax
0x180027c1f  jnz     short loc_180027C35
0x180027c21  call    GetLastFailureAsHRESULT
0x180027c26  mov     ebx, eax
0x180027c28  mov     [rbp+var_40], eax
0x180027c2b  mov     eax, 2B7h
0x180027c30  jmp     loc_180027B2C
0x180027c35  xor     ebx, ebx
0x180027c37  mov     eax, 2B7h
0x180027c3c  mov     [rbp+var_3C], ax
0x180027c40  add     [rdi+4], r13w
0x180027c45  mov     [rbp+var_40], ebx
0x180027c48  lea     rcx, [rbp+var_40]; this
0x180027c4c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180027c51  mov     eax, ebx
0x180027c53  add     rsp, 60h
0x180027c57  pop     r15
0x180027c59  pop     r14
0x180027c5b  pop     r13
0x180027c5d  pop     rdi
0x180027c5e  pop     rsi
0x180027c5f  pop     rbx
0x180027c60  pop     rbp
0x180027c61  retn
```
