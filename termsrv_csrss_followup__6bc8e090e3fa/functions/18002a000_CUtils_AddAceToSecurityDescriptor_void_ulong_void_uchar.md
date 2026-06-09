# CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)

- ea: `0x18002a000`
- end: `0x18002a4c1`
- name: `?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z`
- size: `1217`
- prototype: `static int(void **, unsigned int, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bf878`

## callees

- `0x180009940`
- `0x1800168c0`
- `0x18002a000`
- `0x180033f60`
- `0x180034df8`
- `0x1800a07d4`
- `0x1800a3400`
- `0x1800cae70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a21d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a489`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a23c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a23c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002a2b2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002a328`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002a2b2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002a328`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a205`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a205`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002a28a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002a28a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002a104`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002a104`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002a0a5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002a391`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002a0a5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002a391`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a13b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a13b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a3d5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a3d5`

## string_xrefs

- `0x18002a0d0`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x18002a3bc`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x18002a400`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x18002a12f`: `GetAclInformation 0x%x`
- `0x18002a267`: `InitializeAcl failed: 0x%x`
- `0x18002a461`: `SD has NULL DACL, Present %d, Defaulted %d`

## pseudocode

```c
__int64 __fastcall CUtils::AddAceToSecurityDescriptor(void **a1, int a2, void *a3)
{
  struct _ACL *v5; // r12
  PSECURITY_DESCRIPTOR v6; // r15
  __int16 *v7; // rbx
  unsigned int v8; // ebx
  signed int LastError; // eax
  const char *v10; // rdx
  signed int v11; // eax
  DWORD LengthSid; // eax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  DWORD v17; // ebx
  struct _ACL *v18; // rax
  signed int v19; // eax
  DWORD i; // ebx
  signed int v21; // eax
  signed int v22; // eax
  unsigned int *v23; // r8
  signed int v24; // eax
  signed int v25; // eax
  unsigned int *v26; // r8
  signed int v27; // eax
  __int16 pAceList; // [rsp+30h] [rbp+0h] BYREF
  unsigned __int16 v30; // [rsp+32h] [rbp+2h]
  int v31; // [rsp+34h] [rbp+4h]
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp+Ch] BYREF
  PACL pDacl; // [rsp+40h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp+18h] BYREF
  DWORD v36; // [rsp+50h] [rbp+20h]
  LPVOID pAce; // [rsp+58h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+60h] [rbp+30h]
  void *v39; // [rsp+68h] [rbp+38h] BYREF
  PSID pSourceSid; // [rsp+70h] [rbp+40h]
  __int16 *p_pAceList; // [rsp+78h] [rbp+48h]
  void **v42; // [rsp+88h] [rbp+58h]
  void *v43; // [rsp+90h] [rbp+60h]
  __int16 *v44; // [rsp+98h] [rbp+68h]
  __int64 pAclInformation; // [rsp+A0h] [rbp+70h] BYREF
  int v46; // [rsp+A8h] [rbp+78h]

  pSourceSid = a3;
  v42 = a1;
  v43 = a3;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  pAclInformation = 0;
  v46 = 0;
  pDacl = 0;
  v5 = 0;
  v39 = 0;
  v6 = 0;
  pSecurityDescriptor = 0;
  v7 = (__int16 *)*a1;
  pSelfRelativeSecurityDescriptor = v7;
  v44 = v7;
  if ( v7[1] < 0 )
  {
    if ( !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v10 = "GetSecurityDescriptorDacl failed: 0x%x";
LABEL_8:
      _DbgPrintMessage(8, v10, v8);
      goto LABEL_54;
    }
    if ( pDacl )
    {
      if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v11 = GetLastError();
        v8 = v11;
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        v10 = "GetAclInformation 0x%x";
        goto LABEL_8;
      }
      LengthSid = GetLengthSid(a3);
      v36 = LengthSid;
      LOWORD(v31) = LengthSid + 8;
      pAceList = LengthSid + 8;
      v13 = (unsigned __int16)(LengthSid + 8) + 15LL;
      if ( v13 <= (unsigned __int16)(LengthSid + 8) )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
      v15 = alloca(v14);
      v16 = alloca(v14);
      p_pAceList = &pAceList;
      if ( !&pAceList
        || (pAceList = 0,
            v30 = LengthSid + 8,
            v31 = a2,
            CopySid((unsigned __int16)LengthSid, &bDaclDefaulted, pSourceSid),
            v17 = HIDWORD(pAclInformation) + v30,
            v18 = (struct _ACL *)LocalAlloc(0, v17),
            (v5 = v18) == 0) )
      {
        v8 = -2147024882;
        goto LABEL_54;
      }
      if ( !InitializeAcl(v18, v17, 2u) )
      {
        v19 = GetLastError();
        v8 = v19;
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
        v10 = "InitializeAcl failed: 0x%x";
        goto LABEL_8;
      }
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        if ( !GetAce(pDacl, i, &pAce) )
        {
          v22 = GetLastError();
          v8 = v22;
          if ( v22 > 0 )
            v8 = (unsigned __int16)v22 | 0x80070000;
          v10 = "GetAce failed: 0x%x";
          goto LABEL_8;
        }
        if ( !AddAce(v5, 2u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
          goto LABEL_28;
      }
      if ( !AddAce(v5, 2u, i, &pAceList, v30) )
      {
LABEL_28:
        v21 = GetLastError();
        v8 = v21;
        if ( v21 > 0 )
          v8 = (unsigned __int16)v21 | 0x80070000;
        v10 = "AddAce failed: 0x%x";
        goto LABEL_8;
      }
      if ( !(unsigned int)CUtils::SelfRelativeToAbsoluteSD(pSelfRelativeSecurityDescriptor, &pSecurityDescriptor, v23) )
      {
        v24 = GetLastError();
        v8 = v24;
        if ( v24 > 0 )
          v8 = (unsigned __int16)v24 | 0x80070000;
        _DbgPrintMessage(8, "SelfRelativeToAbsoluteSD failed: 0x%x", v8);
        v6 = pSecurityDescriptor;
        goto LABEL_54;
      }
      v6 = pSecurityDescriptor;
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        v25 = GetLastError();
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        v10 = "GetSecurityDescriptorDacl failed: 0x%x";
        goto LABEL_8;
      }
      if ( !SetSecurityDescriptorDacl(v6, 1, v5, 0) )
      {
        v27 = GetLastError();
        v8 = v27;
        if ( v27 > 0 )
          v8 = (unsigned __int16)v27 | 0x80070000;
        v10 = "SetSecurityDescriptorDacl failed: 0x%x";
        goto LABEL_8;
      }
      if ( pDacl )
        pDacl = (PACL)LocalFree(pDacl);
      v5 = 0;
      if ( !(unsigned int)CUtils::AbsoluteToSelfRelativeSD(v6, &v39, v26) )
      {
        _DbgPrintMessage(8, "AbsoluteToSelfRelativeSD failed");
        goto LABEL_3;
      }
      CUtils::CleanupSD(*a1);
      *a1 = v39;
    }
    else
    {
      _DbgPrintMessage(8, "SD has NULL DACL, Present %d, Defaulted %d", bDaclPresent, bDaclDefaulted);
    }
    v8 = 0;
    goto LABEL_54;
  }
  _DbgPrintMessage(8, "SD is not Self-Relative");
LABEL_3:
  v8 = -2147023558;
LABEL_54:
  if ( v6 )
    CUtils::CleanupSD(v6);
  if ( v5 )
    LocalFree(v5);
  return v8;
}

```

## disassembly

```asm
0x18002a000  mov     [rsp-8+arg_8], edx
0x18002a004  push    rbp
0x18002a005  push    rsi
0x18002a006  push    rdi
0x18002a007  push    r12
0x18002a009  push    r13
0x18002a00b  push    r14
0x18002a00d  push    r15
0x18002a00f  sub     rsp, 0C0h
0x18002a016  lea     rbp, [rsp+30h]
0x18002a01b  mov     [rbp+0C0h+arg_18], rbx
0x18002a022  mov     rax, cs:__security_cookie
0x18002a029  xor     rax, rbp
0x18002a02c  mov     [rbp+0C0h+var_40], rax
0x18002a033  mov     rsi, r8
0x18002a036  mov     [rbp+0C0h+pSourceSid], r8
0x18002a03a  mov     r13, rcx
0x18002a03d  mov     [rbp+0C0h+var_68], rcx
0x18002a041  mov     [rbp+0C0h+var_60], r8
0x18002a045  xor     edi, edi
0x18002a047  mov     [rbp+0C0h+bDaclPresent], edi
0x18002a04a  mov     [rbp+0C0h+bDaclDefaulted], edi
0x18002a04d  mov     [rbp+0C0h+pAce], rdi
0x18002a051  xor     eax, eax
0x18002a053  mov     [rbp+0C0h+pAclInformation], rax
0x18002a057  mov     [rbp+0C0h+var_48], eax
0x18002a05a  mov     [rbp+0C0h+pDacl], rdi
0x18002a05e  mov     r12d, edi
0x18002a061  mov     [rbp+0C0h+var_88], rdi
0x18002a065  mov     r15d, edi
0x18002a068  mov     [rbp+0C0h+pSecurityDescriptor], rdi
0x18002a06c  mov     rbx, [rcx]
0x18002a06f  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rbx
0x18002a073  mov     [rbp+0C0h+var_58], rbx
0x18002a077  cmp     [rbx+2], di
0x18002a07b  jl      short loc_18002A096
0x18002a07d  lea     rdx, aSdIsNotSelfRel; "SD is not Self-Relative"
0x18002a084  lea     ecx, [rdi+8]; int
0x18002a087  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a08c  mov     ebx, 8007053Ah
0x18002a091  jmp     loc_18002A474
0x18002a096  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x18002a09a  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x18002a09e  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x18002a0a2  mov     rcx, rbx; pSecurityDescriptor
0x18002a0a5  call    cs:__imp_GetSecurityDescriptorDacl
0x18002a0ac  nop     dword ptr [rax+rax+00h]
0x18002a0b1  test    eax, eax
0x18002a0b3  jnz     short loc_18002A0E9
0x18002a0b5  call    cs:__imp_GetLastError
0x18002a0bc  nop     dword ptr [rax+rax+00h]
0x18002a0c1  mov     ebx, eax
0x18002a0c3  test    eax, eax
0x18002a0c5  jle     short loc_18002A0D0
0x18002a0c7  movzx   ebx, ax
0x18002a0ca  or      ebx, 80070000h
0x18002a0d0  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorDacl failed: 0x%x"
0x18002a0d7  mov     ecx, 8; int
0x18002a0dc  mov     r8d, ebx
0x18002a0df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a0e4  jmp     loc_18002A474
0x18002a0e9  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x18002a0ed  test    rcx, rcx
0x18002a0f0  jz      loc_18002A459
0x18002a0f6  mov     r9d, 2; dwAclInformationClass
0x18002a0fc  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18002a100  lea     rdx, [rbp+0C0h+pAclInformation]; pAclInformation
0x18002a104  call    cs:__imp_GetAclInformation
0x18002a10b  nop     dword ptr [rax+rax+00h]
0x18002a110  test    eax, eax
0x18002a112  jnz     short loc_18002A138
0x18002a114  call    cs:__imp_GetLastError
0x18002a11b  nop     dword ptr [rax+rax+00h]
0x18002a120  mov     ebx, eax
0x18002a122  test    eax, eax
0x18002a124  jle     short loc_18002A12F
0x18002a126  movzx   ebx, ax
0x18002a129  or      ebx, 80070000h
0x18002a12f  lea     rdx, aGetaclinformat; "GetAclInformation 0x%x"
0x18002a136  jmp     short loc_18002A0D7
0x18002a138  mov     rcx, rsi; pSid
0x18002a13b  call    cs:__imp_GetLengthSid
0x18002a142  nop     dword ptr [rax+rax+00h]
0x18002a147  mov     r8d, eax
0x18002a14a  mov     [rbp+0C0h+var_A0], eax
0x18002a14d  mov     esi, 8
0x18002a152  lea     edx, [rsi+rax]
0x18002a155  mov     word ptr [rbp+0C0h+var_BC], dx
0x18002a159  mov     [rbp+0C0h+pAceList], dx
0x18002a15d  movzx   eax, dx
0x18002a160  lea     rcx, [rax+0Fh]
0x18002a164  cmp     rcx, rax
0x18002a167  ja      short loc_18002A173
0x18002a169  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002a173  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002a177  mov     rax, rcx
0x18002a17a  call    _alloca_probe
0x18002a17f  sub     rsp, rcx
0x18002a182  lea     r14, [rsp+0F0h+pAceList]
0x18002a187  mov     [rbp+0C0h+var_78], r14
0x18002a18b  mov     r9, [rbp+0C0h+pSourceSid]
0x18002a18f  jmp     short loc_18002A1D6
0x18002a191  call    _o__resetstkoflw_0
0x18002a196  xor     r14d, r14d
0x18002a199  mov     [rbp+0C0h+var_78], r14
0x18002a19d  movzx   r8d, [rbp+0C0h+pAceList]
0x18002a1a2  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18002a1a9  lea     ecx, [r14+8]; int
0x18002a1ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a1b2  xor     edi, edi
0x18002a1b4  lea     esi, [rdi+8]
0x18002a1b7  mov     r12d, edi
0x18002a1ba  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x18002a1be  mov     r13, [rbp+0C0h+var_68]
0x18002a1c2  mov     r9, [rbp+0C0h+var_60]
0x18002a1c6  mov     rax, [rbp+0C0h+var_58]
0x18002a1ca  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x18002a1ce  movzx   edx, word ptr [rbp+0C0h+var_BC]
0x18002a1d2  mov     r8d, [rbp+0C0h+var_A0]
0x18002a1d6  test    r14, r14
0x18002a1d9  jnz     short loc_18002A1E5
0x18002a1db  mov     ebx, 8007000Eh
0x18002a1e0  jmp     loc_18002A474
0x18002a1e5  mov     word ptr [r14], 0
0x18002a1eb  mov     [r14+2], dx
0x18002a1f0  mov     eax, [rbp+0C0h+arg_8]
0x18002a1f6  mov     [r14+4], eax
0x18002a1fa  lea     rdx, [r14+8]; pDestinationSid
0x18002a1fe  movzx   ecx, r8w; nDestinationSidLength
0x18002a202  mov     r8, r9; pSourceSid
0x18002a205  call    cs:__imp_CopySid
0x18002a20c  nop     dword ptr [rax+rax+00h]
0x18002a211  movzx   ebx, word ptr [r14+2]
0x18002a216  add     ebx, dword ptr [rbp+0C0h+pAclInformation+4]
0x18002a219  mov     edx, ebx; uBytes
0x18002a21b  xor     ecx, ecx; uFlags
0x18002a21d  call    cs:__imp_LocalAlloc
0x18002a224  nop     dword ptr [rax+rax+00h]
0x18002a229  mov     r12, rax
0x18002a22c  test    rax, rax
0x18002a22f  jz      short loc_18002A1DB
0x18002a231  mov     r8d, 2; dwAclRevision
0x18002a237  mov     edx, ebx; nAclLength
0x18002a239  mov     rcx, rax; pAcl
0x18002a23c  call    cs:__imp_InitializeAcl
0x18002a243  nop     dword ptr [rax+rax+00h]
0x18002a248  test    eax, eax
0x18002a24a  jnz     short loc_18002A275
0x18002a24c  call    cs:__imp_GetLastError
0x18002a253  nop     dword ptr [rax+rax+00h]
0x18002a258  mov     ebx, eax
0x18002a25a  test    eax, eax
0x18002a25c  jle     short loc_18002A267
0x18002a25e  movzx   ebx, ax
0x18002a261  or      ebx, 80070000h
0x18002a267  lea     rdx, aInitializeaclF; "InitializeAcl failed: 0x%x"
0x18002a26e  mov     ecx, esi
0x18002a270  jmp     loc_18002A0DC
0x18002a275  mov     ebx, edi
0x18002a277  cmp     ebx, dword ptr [rbp+0C0h+pAclInformation]
0x18002a27a  jnb     loc_18002A311
0x18002a280  lea     r8, [rbp+0C0h+pAce]; pAce
0x18002a284  mov     edx, ebx; dwAceIndex
0x18002a286  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x18002a28a  call    cs:__imp_GetAce
0x18002a291  nop     dword ptr [rax+rax+00h]
0x18002a296  test    eax, eax
0x18002a298  jz      short loc_18002A2EA
0x18002a29a  mov     r9, [rbp+0C0h+pAce]; pAceList
0x18002a29e  movzx   eax, word ptr [r9+2]
0x18002a2a3  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x18002a2a7  mov     r8d, ebx; dwStartingAceIndex
0x18002a2aa  mov     edx, 2; dwAceRevision
0x18002a2af  mov     rcx, r12; pAcl
0x18002a2b2  call    cs:__imp_AddAce
0x18002a2b9  nop     dword ptr [rax+rax+00h]
0x18002a2be  test    eax, eax
0x18002a2c0  jz      short loc_18002A2C6
0x18002a2c2  inc     ebx
0x18002a2c4  jmp     short loc_18002A277
0x18002a2c6  call    cs:__imp_GetLastError
0x18002a2cd  nop     dword ptr [rax+rax+00h]
0x18002a2d2  mov     ebx, eax
0x18002a2d4  test    eax, eax
0x18002a2d6  jle     short loc_18002A2E1
0x18002a2d8  movzx   ebx, ax
0x18002a2db  or      ebx, 80070000h
0x18002a2e1  lea     rdx, aAddaceFailed0x; "AddAce failed: 0x%x"
0x18002a2e8  jmp     short loc_18002A26E
0x18002a2ea  call    cs:__imp_GetLastError
0x18002a2f1  nop     dword ptr [rax+rax+00h]
0x18002a2f6  mov     ebx, eax
0x18002a2f8  test    eax, eax
0x18002a2fa  jle     short loc_18002A305
0x18002a2fc  movzx   ebx, ax
0x18002a2ff  or      ebx, 80070000h
0x18002a305  lea     rdx, aGetaceFailed0x_0; "GetAce failed: 0x%x"
0x18002a30c  jmp     loc_18002A26E
0x18002a311  movzx   eax, word ptr [r14+2]
0x18002a316  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x18002a31a  mov     r9, r14; pAceList
0x18002a31d  mov     r8d, ebx; dwStartingAceIndex
0x18002a320  mov     edx, 2; dwAceRevision
0x18002a325  mov     rcx, r12; pAcl
0x18002a328  call    cs:__imp_AddAce
0x18002a32f  nop     dword ptr [rax+rax+00h]
0x18002a334  test    eax, eax
0x18002a336  jz      short loc_18002A2C6
0x18002a338  lea     rdx, [rbp+0C0h+pSecurityDescriptor]; void **
0x18002a33c  mov     rcx, [rbp+0C0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18002a340  call    ?SelfRelativeToAbsoluteSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::SelfRelativeToAbsoluteSD(void *,void * *,ulong *)
0x18002a345  test    eax, eax
0x18002a347  jnz     short loc_18002A37E
0x18002a349  call    cs:__imp_GetLastError
0x18002a350  nop     dword ptr [rax+rax+00h]
0x18002a355  mov     ebx, eax
0x18002a357  test    eax, eax
0x18002a359  jle     short loc_18002A364
0x18002a35b  movzx   ebx, ax
0x18002a35e  or      ebx, 80070000h
0x18002a364  mov     r8d, ebx
0x18002a367  lea     rdx, aSelfrelativeto; "SelfRelativeToAbsoluteSD failed: 0x%x"
0x18002a36e  mov     ecx, esi; int
0x18002a370  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a375  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x18002a379  jmp     loc_18002A474
0x18002a37e  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x18002a382  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x18002a386  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x18002a38a  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x18002a38e  mov     rcx, r15; pSecurityDescriptor
0x18002a391  call    cs:__imp_GetSecurityDescriptorDacl
0x18002a398  nop     dword ptr [rax+rax+00h]
0x18002a39d  test    eax, eax
0x18002a39f  jnz     short loc_18002A3C8
0x18002a3a1  call    cs:__imp_GetLastError
0x18002a3a8  nop     dword ptr [rax+rax+00h]
0x18002a3ad  mov     ebx, eax
0x18002a3af  test    eax, eax
0x18002a3b1  jle     short loc_18002A3BC
0x18002a3b3  movzx   ebx, ax
0x18002a3b6  or      ebx, 80070000h
0x18002a3bc  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorDacl failed: 0x%x"
0x18002a3c3  jmp     loc_18002A26E
0x18002a3c8  xor     r9d, r9d; bDaclDefaulted
0x18002a3cb  mov     r8, r12; pDacl
0x18002a3ce  lea     edx, [r9+1]; bDaclPresent
0x18002a3d2  mov     rcx, r15; pSecurityDescriptor
0x18002a3d5  call    cs:__imp_SetSecurityDescriptorDacl
0x18002a3dc  nop     dword ptr [rax+rax+00h]
0x18002a3e1  test    eax, eax
0x18002a3e3  jnz     short loc_18002A40C
0x18002a3e5  call    cs:__imp_GetLastError
0x18002a3ec  nop     dword ptr [rax+rax+00h]
0x18002a3f1  mov     ebx, eax
0x18002a3f3  test    eax, eax
0x18002a3f5  jle     short loc_18002A400
0x18002a3f7  movzx   ebx, ax
0x18002a3fa  or      ebx, 80070000h
0x18002a400  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl failed: 0x%x"
0x18002a407  jmp     loc_18002A26E
0x18002a40c  mov     rcx, [rbp+0C0h+pDacl]; hMem
0x18002a410  test    rcx, rcx
0x18002a413  jz      short loc_18002A425
0x18002a415  call    cs:__imp_LocalFree
0x18002a41c  nop     dword ptr [rax+rax+00h]
0x18002a421  mov     [rbp+0C0h+pDacl], rax
0x18002a425  mov     r12, rdi
0x18002a428  lea     rdx, [rbp+0C0h+var_88]; void **
0x18002a42c  mov     rcx, r15; pAbsoluteSecurityDescriptor
0x18002a42f  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x18002a434  test    eax, eax
0x18002a436  jnz     short loc_18002A446
0x18002a438  lea     rdx, aAbsolutetoself_0; "AbsoluteToSelfRelativeSD failed"
0x18002a43f  mov     ecx, esi
0x18002a441  jmp     loc_18002A087
0x18002a446  mov     rcx, [r13+0]; hMem
0x18002a44a  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x18002a44f  mov     rax, [rbp+0C0h+var_88]
0x18002a453  mov     [r13+0], rax
0x18002a457  jmp     short loc_18002A472
0x18002a459  mov     r9d, [rbp+0C0h+bDaclDefaulted]
0x18002a45d  mov     r8d, [rbp+0C0h+bDaclPresent]
0x18002a461  lea     rdx, aSdHasNullDaclP; "SD has NULL DACL, Present %d, Defaulted"...
0x18002a468  mov     ecx, 8; int
0x18002a46d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a472  mov     ebx, edi
0x18002a474  test    r15, r15
0x18002a477  jz      short loc_18002A481
0x18002a479  mov     rcx, r15; hMem
0x18002a47c  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x18002a481  test    r12, r12
0x18002a484  jz      short loc_18002A495
0x18002a486  mov     rcx, r12; hMem
0x18002a489  call    cs:__imp_LocalFree
0x18002a490  nop     dword ptr [rax+rax+00h]
0x18002a495  mov     eax, ebx
0x18002a497  mov     rcx, [rbp+0C0h+var_40]
0x18002a49e  xor     rcx, rbp; StackCookie
0x18002a4a1  call    __security_check_cookie
  ... truncated ...
```
