# SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)

- ea: `0x180026a90`
- end: `0x180026c38`
- name: `?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, void *const@<r9>, unsigned __int8)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800240ac`
- `0x180024478`
- `0x180024d68`

## callees

- `0x180026a90`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180026bed`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180026bed`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180026b01`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180026b01`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180026ba0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180026bde`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180026ba0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180026bde`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026b36`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180026b36`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "SxAddKnownAce", 658, 1);
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
0x180026a90  push    rbp
0x180026a92  push    rbx
0x180026a93  push    rsi
0x180026a94  push    rdi
0x180026a95  push    r13
0x180026a97  push    r14
0x180026a99  push    r15
0x180026a9b  mov     rbp, rsp
0x180026a9e  sub     rsp, 60h
0x180026aa2  mov     rsi, r9
0x180026aa5  mov     r14d, r8d
0x180026aa8  mov     r15b, dl
0x180026aab  mov     rdi, rcx
0x180026aae  mov     r13d, 1
0x180026ab4  mov     r9d, r13d; unsigned __int16
0x180026ab7  mov     r8d, 292h; unsigned __int16
0x180026abd  lea     rdx, aSxaddknownace; "SxAddKnownAce"
0x180026ac4  lea     rcx, [rbp+var_40]; this
0x180026ac8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180026acd  mov     eax, 29Ah
0x180026ad2  test    rdi, rdi
0x180026ad5  jnz     short loc_180026AE5
0x180026ad7  mov     ebx, 80070057h
0x180026adc  mov     [rbp+var_3A], ax
0x180026ae0  jmp     loc_180026C1B
0x180026ae5  mov     [rbp+var_3C], ax
0x180026ae9  mov     eax, 29Bh
0x180026aee  test    rsi, rsi
0x180026af1  jz      short loc_180026AD7
0x180026af3  mov     [rbp+var_40], 0
0x180026afa  mov     [rbp+var_3C], ax
0x180026afe  mov     rcx, rdi; pAcl
0x180026b01  call    cs:__imp_IsValidAcl
0x180026b07  test    eax, eax
0x180026b09  jnz     short loc_180026B23
0x180026b0b  call    GetLastFailureAsHRESULT
0x180026b10  mov     ebx, eax
0x180026b12  mov     [rbp+var_40], eax
0x180026b15  mov     eax, 29Dh
0x180026b1a  mov     [rbp+var_3A], ax
0x180026b1e  jmp     loc_180026C1E
0x180026b23  mov     [rbp+var_40], 0
0x180026b2a  mov     eax, 29Dh
0x180026b2f  mov     [rbp+var_3C], ax
0x180026b33  mov     rcx, rsi; pSid
0x180026b36  call    cs:__imp_IsValidSid
0x180026b3c  test    eax, eax
0x180026b3e  jnz     short loc_180026B51
0x180026b40  call    GetLastFailureAsHRESULT
0x180026b45  mov     ebx, eax
0x180026b47  mov     [rbp+var_40], eax
0x180026b4a  mov     eax, 29Eh
0x180026b4f  jmp     short loc_180026B1A
0x180026b51  mov     [rbp+var_40], 0
0x180026b58  mov     eax, 29Eh
0x180026b5d  mov     [rbp+var_3C], ax
0x180026b61  lea     rbx, [rdi+8]
0x180026b65  xor     ecx, ecx
0x180026b67  movzx   edx, word ptr [rdi+4]
0x180026b6b  test    edx, edx
0x180026b6d  jz      short loc_180026B7D
0x180026b6f  movzx   eax, word ptr [rbx+2]
0x180026b73  add     rbx, rax
0x180026b76  add     ecx, r13d
0x180026b79  cmp     ecx, edx
0x180026b7b  jb      short loc_180026B6F
0x180026b7d  movzx   eax, word ptr [rdi+2]
0x180026b81  lea     rcx, [rdi+rax*8]
0x180026b85  mov     eax, 2A8h
0x180026b8a  cmp     rbx, rcx
0x180026b8d  jb      short loc_180026B99
0x180026b8f  mov     ebx, 81000036h
0x180026b94  jmp     loc_180026ADC
0x180026b99  mov     [rbp+var_3C], ax
0x180026b9d  mov     rcx, rsi; pSid
0x180026ba0  call    cs:__imp_GetLengthSid
0x180026ba6  lea     edx, [rax+8]
0x180026ba9  movzx   ecx, word ptr [rdi+2]
0x180026bad  add     rcx, rdi
0x180026bb0  mov     eax, edx
0x180026bb2  add     rax, rbx
0x180026bb5  cmp     rax, rcx
0x180026bb8  mov     eax, 2ADh
0x180026bbd  ja      short loc_180026B8F
0x180026bbf  mov     [rbp+var_40], 0
0x180026bc6  mov     [rbp+var_3C], ax
0x180026bca  mov     [rbx+1], r15b
0x180026bce  mov     al, [rbp+arg_20]
0x180026bd1  mov     [rbx], al
0x180026bd3  mov     [rbx+2], dx
0x180026bd7  mov     [rbx+4], r14d
0x180026bdb  mov     rcx, rsi; pSid
0x180026bde  call    cs:__imp_GetLengthSid
0x180026be4  mov     ecx, eax; nDestinationSidLength
0x180026be6  mov     r8, rsi; pSourceSid
0x180026be9  lea     rdx, [rbx+8]; pDestinationSid
0x180026bed  call    cs:__imp_CopySid
0x180026bf3  test    eax, eax
0x180026bf5  jnz     short loc_180026C0B
0x180026bf7  call    GetLastFailureAsHRESULT
0x180026bfc  mov     ebx, eax
0x180026bfe  mov     [rbp+var_40], eax
0x180026c01  mov     eax, 2B7h
0x180026c06  jmp     loc_180026B1A
0x180026c0b  xor     ebx, ebx
0x180026c0d  mov     eax, 2B7h
0x180026c12  mov     [rbp+var_3C], ax
0x180026c16  add     [rdi+4], r13w
0x180026c1b  mov     [rbp+var_40], ebx
0x180026c1e  lea     rcx, [rbp+var_40]; this
0x180026c22  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180026c27  mov     eax, ebx
0x180026c29  add     rsp, 60h
0x180026c2d  pop     r15
0x180026c2f  pop     r14
0x180026c31  pop     r13
0x180026c33  pop     rdi
0x180026c34  pop     rsi
0x180026c35  pop     rbx
0x180026c36  pop     rbp
0x180026c37  retn
```
