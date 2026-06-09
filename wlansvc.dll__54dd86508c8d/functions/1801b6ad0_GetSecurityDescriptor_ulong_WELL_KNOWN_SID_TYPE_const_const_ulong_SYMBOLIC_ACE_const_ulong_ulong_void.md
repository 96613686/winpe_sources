# GetSecurityDescriptor(ulong,WELL_KNOWN_SID_TYPE const * const,ulong,_SYMBOLIC_ACE const *,ulong,ulong,void * *)

- ea: `0x1801b6ad0`
- end: `0x1801b7141`
- name: `?GetSecurityDescriptor@@YAKKQEBW4WELL_KNOWN_SID_TYPE@@KPEBU_SYMBOLIC_ACE@@KKPEAPEAX@Z`
- size: `1649`
- prototype: `unsigned int __fastcall(unsigned int, const enum WELL_KNOWN_SID_TYPE *const, unsigned int, const struct _SYMBOLIC_ACE *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1801b6964`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180076260`
- `0x1800dff74`
- `0x180106340`
- `0x180107330`
- `0x1801b6ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b7080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b7080`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801b7076`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801b7076`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801b6f00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1801b6f00`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801b6bb5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801b6bb5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801b6fde`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801b6fde`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801b6e96`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801b6e96`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801b6c52`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801b6c52`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x1801b6f41`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x1801b6f41`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1801b6c9f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1801b6c9f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801b6d65`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801b6d65`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1801b6f98`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1801b6f98`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1801b6cec`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1801b6cec`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(
        __int64 a1,
        const enum WELL_KNOWN_SID_TYPE *const a2,
        unsigned int a3,
        const struct _SYMBOLIC_ACE *a4,
        unsigned int a5,
        unsigned int a6,
        void **a7)
{
  struct _ACL *v7; // r13
  unsigned __int16 *v8; // r12
  __int64 i; // rdi
  unsigned int WLMemory; // ebx
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // esi
  DWORD v18; // edi
  __int64 j; // rbx
  DWORD v20; // eax
  __int64 k; // rdi
  DWORD v22; // r8d
  PSID v23; // r9
  __int64 m; // rdi
  unsigned __int16 *v25; // rcx
  DWORD cbSid; // [rsp+20h] [rbp-B1h] BYREF
  DWORD dwBufferLength; // [rsp+24h] [rbp-ADh] BYREF
  PACL pAcl; // [rsp+28h] [rbp-A9h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+30h] [rbp-A1h]
  unsigned int v31; // [rsp+38h] [rbp-99h]
  void **v32; // [rsp+40h] [rbp-91h]
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-89h] BYREF
  __int64 v34; // [rsp+68h] [rbp-69h]
  PSID pSid[4]; // [rsp+70h] [rbp-61h] BYREF
  PSID pOwner; // [rsp+90h] [rbp-41h]

  v7 = 0;
  v31 = a3;
  v32 = a7;
  cbSid = 0;
  v8 = 0;
  pAcl = 0;
  dwBufferLength = 0;
  v34 = 0;
  pSelfRelativeSecurityDescriptor = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(pSid, 0, 0x50u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
  {
    cbSid = 68;
    WLMemory = AllocateWLMemory(0x44u);
    if ( WLMemory )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 12;
LABEL_17:
        WPP_SF_(v15[2], v16, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
      }
      goto LABEL_96;
    }
    if ( !CreateWellKnownSid(*(&qword_18025BDA0 + i), 0, pSid[i], &cbSid) )
    {
      LastError = GetLastError();
      WLMemory = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 13;
LABEL_13:
          WPP_SF_d(v13[2], v14, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, LastError);
          goto LABEL_96;
        }
        goto LABEL_96;
      }
    }
  }
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
  {
    if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
      || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
    {
      if ( SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0)
        || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
      {
        v17 = v31;
        v18 = 8;
        for ( j = 0; (unsigned int)j < v17; j = (unsigned int)(j + 1) )
        {
          if ( *((_DWORD *)a4 + 3 * j + 1) >= 5u )
          {
            WLMemory = 87;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 17;
              goto LABEL_17;
            }
            goto LABEL_96;
          }
          if ( *((_BYTE *)a4 + 12 * j) > 1u )
          {
            WLMemory = 87;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 18;
              goto LABEL_17;
            }
            goto LABEL_96;
          }
          v20 = GetLengthSid(pSid[*((unsigned int *)a4 + 3 * j + 1)]) + 8;
          if ( v20 < 8 )
          {
            WLMemory = 534;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 19;
              goto LABEL_17;
            }
            goto LABEL_96;
          }
          v18 += v20;
          if ( v18 < v20 )
          {
            WLMemory = 534;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 20;
              goto LABEL_17;
            }
            goto LABEL_96;
          }
        }
        WLMemory = AllocateWLMemory(v18);
        if ( WLMemory )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
          v7 = pAcl;
        }
        else
        {
          v7 = pAcl;
          if ( InitializeAcl(pAcl, v18, 2u) || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
          {
            for ( k = 0; (unsigned int)k < v17; k = (unsigned int)(k + 1) )
            {
              v22 = *((_DWORD *)a4 + 3 * k + 2);
              v23 = pSid[*((unsigned int *)a4 + 3 * k + 1)];
              if ( *((_BYTE *)a4 + 12 * k) )
              {
                if ( !AddAccessDeniedAce(v7, 2u, v22, v23) )
                {
                  LastError = GetLastError();
                  WLMemory = LastError;
                  if ( LastError )
                  {
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v14 = 24;
                      goto LABEL_13;
                    }
                    goto LABEL_96;
                  }
                }
              }
              else if ( !AddAccessAllowedAce(v7, 2u, v22, v23) )
              {
                LastError = GetLastError();
                WLMemory = LastError;
                if ( LastError )
                {
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v14 = 23;
                    goto LABEL_13;
                  }
                  goto LABEL_96;
                }
              }
            }
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v7, 0)
              || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
            {
              LastError = GetSecurityDescriptorLength(pSecurityDescriptor);
              dwBufferLength = LastError;
              if ( LastError >= 0x28 )
              {
                WLMemory = AllocateWLMemory(LastError);
                if ( WLMemory )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
                  v8 = (unsigned __int16 *)pSelfRelativeSecurityDescriptor;
                }
                else
                {
                  v8 = (unsigned __int16 *)pSelfRelativeSecurityDescriptor;
                  if ( MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength)
                    || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
                  {
                    *v32 = v8;
                    v8 = 0;
                  }
                  else
                  {
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v14 = 28;
                      goto LABEL_13;
                    }
                  }
                }
              }
              else
              {
                WLMemory = 5023;
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v14 = 26;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v14 = 25;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v14 = 22;
              goto LABEL_13;
            }
          }
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 16;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 15;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 14;
      goto LABEL_13;
    }
  }
LABEL_96:
  for ( m = 0; m != 10; ++m )
  {
    v25 = (unsigned __int16 *)pSid[m];
    if ( v25 )
      SoftAPUtilFreeProfileString(v25);
  }
  if ( v8 )
    SoftAPUtilFreeProfileString(v8);
  if ( v7 )
    SoftAPUtilFreeProfileString((unsigned __int16 *)v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, WLMemory);
  return WLMemory;
}

```

## disassembly

```asm
0x1801b6ad0  push    rbp
0x1801b6ad2  push    rbx
0x1801b6ad3  push    rsi
0x1801b6ad4  push    rdi
0x1801b6ad5  push    r12
0x1801b6ad7  push    r13
0x1801b6ad9  push    r14
0x1801b6adb  push    r15
0x1801b6add  lea     rbp, [rsp-7]
0x1801b6ae2  sub     rsp, 0D8h
0x1801b6ae9  mov     rax, cs:__security_cookie
0x1801b6af0  xor     rax, rsp
0x1801b6af3  mov     [rbp+3Fh+var_50], rax
0x1801b6af7  mov     r14, [rbp+3Fh+arg_30]
0x1801b6afb  lea     rcx, [rbp+3Fh+pSid]; void *
0x1801b6aff  xor     r13d, r13d
0x1801b6b02  mov     [rsp+110h+var_D8], r8d
0x1801b6b07  xorps   xmm0, xmm0
0x1801b6b0a  mov     [rsp+110h+var_D0], r14
0x1801b6b0f  xor     eax, eax
0x1801b6b11  mov     [rsp+110h+cbSid], 0
0x1801b6b19  xor     r12d, r12d
0x1801b6b1c  mov     [rsp+110h+pAcl], r13
0x1801b6b21  lea     r8d, [r13+50h]; Size
0x1801b6b25  mov     [rsp+110h+dwBufferLength], r13d
0x1801b6b2a  xor     edx, edx; Val
0x1801b6b2c  mov     [rbp+3Fh+var_A8], rax
0x1801b6b30  mov     r15, r9
0x1801b6b33  mov     [rsp+110h+pSelfRelativeSecurityDescriptor], r12
0x1801b6b38  movups  [rsp+110h+pSecurityDescriptor], xmm0
0x1801b6b3d  movups  [rbp+3Fh+var_B8], xmm0
0x1801b6b41  call    memset_0
0x1801b6b46  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6b4d  lea     r14, WPP_GLOBAL_Control
0x1801b6b54  cmp     rcx, r14
0x1801b6b57  jz      short loc_1801B6B73
0x1801b6b59  test    byte ptr [rcx+1Ch], 8
0x1801b6b5d  jz      short loc_1801B6B73
0x1801b6b5f  mov     rcx, [rcx+10h]
0x1801b6b63  lea     edx, [r13+0Ah]
0x1801b6b67  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x1801b6b6e  call    WPP_SF_
0x1801b6b73  xor     edi, edi
0x1801b6b75  cmp     edi, 5
0x1801b6b78  jnb     loc_1801B6C48
0x1801b6b7e  lea     r14, [rbp+3Fh+pSid]
0x1801b6b82  mov     [rsp+110h+cbSid], 44h ; 'D'
0x1801b6b8a  lea     r14, [r14+rdi*8]
0x1801b6b8e  mov     ecx, 44h ; 'D'; dwBytes
0x1801b6b93  mov     rdx, r14
0x1801b6b96  call    AllocateWLMemory
0x1801b6b9b  mov     ebx, eax
0x1801b6b9d  test    eax, eax
0x1801b6b9f  jnz     short loc_1801B6C0D
0x1801b6ba1  mov     r8, [r14]; pSid
0x1801b6ba4  lea     rcx, qword_18025BDA0
0x1801b6bab  mov     ecx, [rcx+rdi*4]; WellKnownSidType
0x1801b6bae  lea     r9, [rsp+110h+cbSid]; cbSid
0x1801b6bb3  xor     edx, edx; DomainSid
0x1801b6bb5  call    cs:__imp_CreateWellKnownSid
0x1801b6bbb  test    eax, eax
0x1801b6bbd  jnz     short loc_1801B6BCB
0x1801b6bbf  call    cs:__imp_GetLastError
0x1801b6bc5  mov     ebx, eax
0x1801b6bc7  test    eax, eax
0x1801b6bc9  jnz     short loc_1801B6BCF
0x1801b6bcb  inc     edi
0x1801b6bcd  jmp     short loc_1801B6B75
0x1801b6bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6bd6  lea     r14, WPP_GLOBAL_Control
0x1801b6bdd  cmp     rcx, r14
0x1801b6be0  jz      loc_1801B70C1
0x1801b6be6  test    byte ptr [rcx+1Ch], 1
0x1801b6bea  jz      loc_1801B70C1
0x1801b6bf0  mov     edx, 0Dh
0x1801b6bf5  mov     rcx, [rcx+10h]
0x1801b6bf9  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x1801b6c00  mov     r9d, eax
0x1801b6c03  call    WPP_SF_d
0x1801b6c08  jmp     loc_1801B70C1
0x1801b6c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6c14  lea     r14, WPP_GLOBAL_Control
0x1801b6c1b  cmp     rcx, r14
0x1801b6c1e  jz      loc_1801B70C1
0x1801b6c24  test    byte ptr [rcx+1Ch], 1
0x1801b6c28  jz      loc_1801B70C1
0x1801b6c2e  mov     edx, 0Ch
0x1801b6c33  mov     rcx, [rcx+10h]
0x1801b6c37  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x1801b6c3e  call    WPP_SF_
0x1801b6c43  jmp     loc_1801B70C1
0x1801b6c48  mov     edx, 1; dwRevision
0x1801b6c4d  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x1801b6c52  call    cs:__imp_InitializeSecurityDescriptor
0x1801b6c58  test    eax, eax
0x1801b6c5a  jnz     short loc_1801B6C93
0x1801b6c5c  call    cs:__imp_GetLastError
0x1801b6c62  mov     ebx, eax
0x1801b6c64  test    eax, eax
0x1801b6c66  jz      short loc_1801B6C93
0x1801b6c68  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6c6f  lea     r14, WPP_GLOBAL_Control
0x1801b6c76  cmp     rcx, r14
0x1801b6c79  jz      loc_1801B70C1
0x1801b6c7f  test    byte ptr [rcx+1Ch], 1
0x1801b6c83  jz      loc_1801B70C1
0x1801b6c89  mov     edx, 0Eh
0x1801b6c8e  jmp     loc_1801B6BF5
0x1801b6c93  mov     rdx, [rbp+3Fh+pOwner]; pOwner
0x1801b6c97  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x1801b6c9c  xor     r8d, r8d; bOwnerDefaulted
0x1801b6c9f  call    cs:__imp_SetSecurityDescriptorOwner
0x1801b6ca5  test    eax, eax
0x1801b6ca7  jnz     short loc_1801B6CE0
0x1801b6ca9  call    cs:__imp_GetLastError
0x1801b6caf  mov     ebx, eax
0x1801b6cb1  test    eax, eax
0x1801b6cb3  jz      short loc_1801B6CE0
0x1801b6cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6cbc  lea     r14, WPP_GLOBAL_Control
0x1801b6cc3  cmp     rcx, r14
0x1801b6cc6  jz      loc_1801B70C1
0x1801b6ccc  test    byte ptr [rcx+1Ch], 1
0x1801b6cd0  jz      loc_1801B70C1
0x1801b6cd6  mov     edx, 0Fh
0x1801b6cdb  jmp     loc_1801B6BF5
0x1801b6ce0  mov     rdx, [rbp+3Fh+pOwner]; pGroup
0x1801b6ce4  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x1801b6ce9  xor     r8d, r8d; bGroupDefaulted
0x1801b6cec  call    cs:__imp_SetSecurityDescriptorGroup
0x1801b6cf2  test    eax, eax
0x1801b6cf4  jnz     short loc_1801B6D2D
0x1801b6cf6  call    cs:__imp_GetLastError
0x1801b6cfc  mov     ebx, eax
0x1801b6cfe  test    eax, eax
0x1801b6d00  jz      short loc_1801B6D2D
0x1801b6d02  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6d09  lea     r14, WPP_GLOBAL_Control
0x1801b6d10  cmp     rcx, r14
0x1801b6d13  jz      loc_1801B70C1
0x1801b6d19  test    byte ptr [rcx+1Ch], 1
0x1801b6d1d  jz      loc_1801B70C1
0x1801b6d23  mov     edx, 10h
0x1801b6d28  jmp     loc_1801B6BF5
0x1801b6d2d  mov     esi, [rsp+110h+var_D8]
0x1801b6d31  mov     edi, 8
0x1801b6d36  xor     ebx, ebx
0x1801b6d38  cmp     ebx, esi
0x1801b6d3a  jnb     loc_1801B6E39
0x1801b6d40  lea     rcx, [rbx+rbx*2]
0x1801b6d44  cmp     dword ptr [r15+rcx*4+4], 5
0x1801b6d4a  jnb     loc_1801B6E0B
0x1801b6d50  cmp     byte ptr [r15+rcx*4], 1
0x1801b6d55  ja      loc_1801B6DDD
0x1801b6d5b  mov     ecx, [r15+rcx*4+4]
0x1801b6d60  mov     rcx, [rbp+rcx*8+3Fh+pSid]; pSid
0x1801b6d65  call    cs:__imp_GetLengthSid
0x1801b6d6b  add     eax, 8
0x1801b6d6e  cmp     eax, 8
0x1801b6d71  jb      short loc_1801B6DAD
0x1801b6d73  add     edi, eax
0x1801b6d75  cmp     edi, eax
0x1801b6d77  jb      short loc_1801B6D7D
0x1801b6d79  inc     ebx
0x1801b6d7b  jmp     short loc_1801B6D38
0x1801b6d7d  mov     ebx, 216h
0x1801b6d82  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6d89  lea     r14, WPP_GLOBAL_Control
0x1801b6d90  cmp     rcx, r14
0x1801b6d93  jz      loc_1801B70C1
0x1801b6d99  test    byte ptr [rcx+1Ch], 1
0x1801b6d9d  jz      loc_1801B70C1
0x1801b6da3  mov     edx, 14h
0x1801b6da8  jmp     loc_1801B6C33
0x1801b6dad  mov     ebx, 216h
0x1801b6db2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6db9  lea     r14, WPP_GLOBAL_Control
0x1801b6dc0  cmp     rcx, r14
0x1801b6dc3  jz      loc_1801B70C1
0x1801b6dc9  test    byte ptr [rcx+1Ch], 1
0x1801b6dcd  jz      loc_1801B70C1
0x1801b6dd3  mov     edx, 13h
0x1801b6dd8  jmp     loc_1801B6C33
0x1801b6ddd  mov     ebx, 57h ; 'W'
0x1801b6de2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6de9  lea     r14, WPP_GLOBAL_Control
0x1801b6df0  cmp     rcx, r14
0x1801b6df3  jz      loc_1801B70C1
0x1801b6df9  test    byte ptr [rcx+1Ch], 1
0x1801b6dfd  jz      loc_1801B70C1
0x1801b6e03  lea     edx, [rbx-45h]
0x1801b6e06  jmp     loc_1801B6C33
0x1801b6e0b  mov     ebx, 57h ; 'W'
0x1801b6e10  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6e17  lea     r14, WPP_GLOBAL_Control
0x1801b6e1e  cmp     rcx, r14
0x1801b6e21  jz      loc_1801B70C1
0x1801b6e27  test    byte ptr [rcx+1Ch], 1
0x1801b6e2b  jz      loc_1801B70C1
0x1801b6e31  lea     edx, [rbx-46h]
0x1801b6e34  jmp     loc_1801B6C33
0x1801b6e39  mov     ecx, edi; dwBytes
0x1801b6e3b  lea     rdx, [rsp+110h+pAcl]
0x1801b6e40  call    AllocateWLMemory
0x1801b6e45  mov     ebx, eax
0x1801b6e47  test    eax, eax
0x1801b6e49  jz      short loc_1801B6E83
0x1801b6e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6e52  lea     r14, WPP_GLOBAL_Control
0x1801b6e59  cmp     rcx, r14
0x1801b6e5c  jz      short loc_1801B6E79
0x1801b6e5e  test    byte ptr [rcx+1Ch], 1
0x1801b6e62  jz      short loc_1801B6E79
0x1801b6e64  mov     rcx, [rcx+10h]
0x1801b6e68  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x1801b6e6f  mov     edx, 15h
0x1801b6e74  call    WPP_SF_
0x1801b6e79  mov     r13, [rsp+110h+pAcl]
0x1801b6e7e  jmp     loc_1801B70C1
0x1801b6e83  mov     r13, [rsp+110h+pAcl]
0x1801b6e88  mov     r14d, 2
0x1801b6e8e  mov     r8d, r14d; dwAclRevision
0x1801b6e91  mov     rcx, r13; pAcl
0x1801b6e94  mov     edx, edi; nAclLength
0x1801b6e96  call    cs:__imp_InitializeAcl
0x1801b6e9c  test    eax, eax
0x1801b6e9e  jnz     short loc_1801B6ED7
0x1801b6ea0  call    cs:__imp_GetLastError
0x1801b6ea6  mov     ebx, eax
0x1801b6ea8  test    eax, eax
0x1801b6eaa  jz      short loc_1801B6ED7
0x1801b6eac  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6eb3  lea     r14, WPP_GLOBAL_Control
0x1801b6eba  cmp     rcx, r14
0x1801b6ebd  jz      loc_1801B70C1
0x1801b6ec3  test    byte ptr [rcx+1Ch], 1
0x1801b6ec7  jz      loc_1801B70C1
0x1801b6ecd  mov     edx, 16h
0x1801b6ed2  jmp     loc_1801B6BF5
0x1801b6ed7  xor     edi, edi
0x1801b6ed9  cmp     edi, esi
0x1801b6edb  jnb     loc_1801B6F89
0x1801b6ee1  lea     rcx, [rdi+rdi*2]
0x1801b6ee5  mov     edx, r14d; dwAceRevision
0x1801b6ee8  mov     r9d, [r15+rcx*4+4]
0x1801b6eed  mov     r8d, [r15+rcx*4+8]; AccessMask
0x1801b6ef2  cmp     [r15+rcx*4], r12b
0x1801b6ef6  mov     rcx, r13; pAcl
0x1801b6ef9  mov     r9, [rbp+r9*8+3Fh+pSid]; pSid
0x1801b6efe  jnz     short loc_1801B6F41
0x1801b6f00  call    cs:__imp_AddAccessAllowedAce
0x1801b6f06  test    eax, eax
0x1801b6f08  jnz     short loc_1801B6F57
0x1801b6f0a  call    cs:__imp_GetLastError
0x1801b6f10  mov     ebx, eax
0x1801b6f12  test    eax, eax
0x1801b6f14  jz      short loc_1801B6F57
0x1801b6f16  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6f1d  lea     r14, WPP_GLOBAL_Control
0x1801b6f24  cmp     rcx, r14
0x1801b6f27  jz      loc_1801B70C1
0x1801b6f2d  test    byte ptr [rcx+1Ch], 1
0x1801b6f31  jz      loc_1801B70C1
0x1801b6f37  mov     edx, 17h
0x1801b6f3c  jmp     loc_1801B6BF5
0x1801b6f41  call    cs:__imp_AddAccessDeniedAce
0x1801b6f47  test    eax, eax
0x1801b6f49  jnz     short loc_1801B6F57
0x1801b6f4b  call    cs:__imp_GetLastError
0x1801b6f51  mov     ebx, eax
0x1801b6f53  test    eax, eax
0x1801b6f55  jnz     short loc_1801B6F5E
0x1801b6f57  inc     edi
0x1801b6f59  jmp     loc_1801B6ED9
0x1801b6f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6f65  lea     r14, WPP_GLOBAL_Control
0x1801b6f6c  cmp     rcx, r14
0x1801b6f6f  jz      loc_1801B70C1
0x1801b6f75  test    byte ptr [rcx+1Ch], 1
0x1801b6f79  jz      loc_1801B70C1
0x1801b6f7f  mov     edx, 18h
0x1801b6f84  jmp     loc_1801B6BF5
0x1801b6f89  xor     r9d, r9d; bDaclDefaulted
0x1801b6f8c  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x1801b6f91  mov     r8, r13; pDacl
0x1801b6f94  lea     edx, [r9+1]; bDaclPresent
0x1801b6f98  call    cs:__imp_SetSecurityDescriptorDacl
0x1801b6f9e  test    eax, eax
0x1801b6fa0  jnz     short loc_1801B6FD9
0x1801b6fa2  call    cs:__imp_GetLastError
0x1801b6fa8  mov     ebx, eax
0x1801b6faa  test    eax, eax
0x1801b6fac  jz      short loc_1801B6FD9
0x1801b6fae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6fb5  lea     r14, WPP_GLOBAL_Control
0x1801b6fbc  cmp     rcx, r14
0x1801b6fbf  jz      loc_1801B70C1
0x1801b6fc5  test    byte ptr [rcx+1Ch], 1
0x1801b6fc9  jz      loc_1801B70C1
0x1801b6fcf  mov     edx, 19h
  ... truncated ...
```
