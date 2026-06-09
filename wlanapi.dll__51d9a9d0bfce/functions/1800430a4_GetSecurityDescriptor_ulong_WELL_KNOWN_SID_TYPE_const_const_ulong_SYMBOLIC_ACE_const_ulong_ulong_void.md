# GetSecurityDescriptor(ulong,WELL_KNOWN_SID_TYPE const * const,ulong,_SYMBOLIC_ACE const *,ulong,ulong,void * *)

- ea: `0x1800430a4`
- end: `0x180043715`
- name: `?GetSecurityDescriptor@@YAKKQEBW4WELL_KNOWN_SID_TYPE@@KPEBU_SYMBOLIC_ACE@@KKPEAPEAX@Z`
- size: `1649`
- prototype: `unsigned int __fastcall(unsigned int, const enum WELL_KNOWN_SID_TYPE *const, unsigned int, const struct _SYMBOLIC_ACE *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180042f38`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x18001a5bc`
- `0x18003af3c`
- `0x18003af80`
- `0x1800430a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004327d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004351f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004327d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004351f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043654`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180043273`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180043273`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004356c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004356c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180043226`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180043226`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043339`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043339`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800435b2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800435b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800434d4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800434d4`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004364a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004364a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800432c0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800432c0`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180043515`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180043515`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004346a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004346a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043189`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043189`

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
  PSECURITY_DESCRIPTOR v8; // r12
  __int64 i; // rdi
  unsigned int WLMemory; // ebx
  DWORD LastError; // eax
  union DOT11_OUI_HEADER *v13; // rcx
  __int64 v14; // rdx
  union DOT11_OUI_HEADER *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // esi
  DWORD v18; // edi
  __int64 j; // rbx
  DWORD v20; // eax
  __int64 k; // rdi
  DWORD v22; // r8d
  PSID v23; // r9
  __int64 m; // rdi
  DWORD cbSid; // [rsp+20h] [rbp-B1h] BYREF
  DWORD dwBufferLength; // [rsp+24h] [rbp-ADh] BYREF
  PACL pAcl; // [rsp+28h] [rbp-A9h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+30h] [rbp-A1h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-99h]
  void **v31; // [rsp+40h] [rbp-91h]
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-89h] BYREF
  __int64 v33; // [rsp+68h] [rbp-69h]
  PSID pSid[4]; // [rsp+70h] [rbp-61h] BYREF
  PSID pOwner; // [rsp+90h] [rbp-41h]

  v7 = 0;
  v30 = a3;
  v31 = a7;
  cbSid = 0;
  v8 = 0;
  pAcl = 0;
  dwBufferLength = 0;
  v33 = 0;
  pSelfRelativeSecurityDescriptor = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset_0(pSid, 0, 0x50u);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
  }
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
  {
    cbSid = 68;
    WLMemory = AllocateWLMemory(68, &pSid[i]);
    if ( WLMemory )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 12;
LABEL_17:
        WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
      }
      goto LABEL_96;
    }
    if ( !CreateWellKnownSid(*(&qword_180073190 + i), 0, pSid[i], &cbSid) )
    {
      LastError = GetLastError();
      WLMemory = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 13;
LABEL_13:
          WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, LastError);
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
        v17 = v30;
        v18 = 8;
        for ( j = 0; (unsigned int)j < v17; j = (unsigned int)(j + 1) )
        {
          if ( *((_DWORD *)a4 + 3 * j + 1) >= 5u )
          {
            WLMemory = 87;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 20;
              goto LABEL_17;
            }
            goto LABEL_96;
          }
        }
        WLMemory = AllocateWLMemory(v18, &pAcl);
        if ( WLMemory )
        {
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
          }
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
                    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
                  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
                WLMemory = AllocateWLMemory(LastError, &pSelfRelativeSecurityDescriptor);
                if ( WLMemory )
                {
                  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids);
                  }
                  v8 = pSelfRelativeSecurityDescriptor;
                }
                else
                {
                  v8 = pSelfRelativeSecurityDescriptor;
                  if ( MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength)
                    || (LastError = GetLastError(), (WLMemory = LastError) == 0) )
                  {
                    *v31 = v8;
                    v8 = 0;
                  }
                  else
                  {
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
                if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v14 = 26;
                  goto LABEL_13;
                }
              }
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v14 = 25;
                goto LABEL_13;
              }
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 16;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 15;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 14;
      goto LABEL_13;
    }
  }
LABEL_96:
  for ( m = 0; m != 10; ++m )
  {
    if ( pSid[m] )
      ((void (*)(void))FreeWLMemory)();
  }
  if ( v8 )
    FreeWLMemory(v8);
  if ( v7 )
    FreeWLMemory(v7);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids, WLMemory);
  }
  return WLMemory;
}

```

## disassembly

```asm
0x1800430a4  push    rbp
0x1800430a6  push    rbx
0x1800430a7  push    rsi
0x1800430a8  push    rdi
0x1800430a9  push    r12
0x1800430ab  push    r13
0x1800430ad  push    r14
0x1800430af  push    r15
0x1800430b1  lea     rbp, [rsp-7]
0x1800430b6  sub     rsp, 0D8h
0x1800430bd  mov     rax, cs:__security_cookie
0x1800430c4  xor     rax, rsp
0x1800430c7  mov     [rbp+3Fh+var_50], rax
0x1800430cb  mov     r14, [rbp+3Fh+arg_30]
0x1800430cf  lea     rcx, [rbp+3Fh+pSid]; void *
0x1800430d3  xor     r13d, r13d
0x1800430d6  mov     [rsp+110h+var_D8], r8d
0x1800430db  xorps   xmm0, xmm0
0x1800430de  mov     [rsp+110h+var_D0], r14
0x1800430e3  xor     eax, eax
0x1800430e5  mov     [rsp+110h+cbSid], 0
0x1800430ed  xor     r12d, r12d
0x1800430f0  mov     [rsp+110h+pAcl], r13
0x1800430f5  lea     r8d, [r13+50h]; Size
0x1800430f9  mov     [rsp+110h+dwBufferLength], r13d
0x1800430fe  xor     edx, edx; Val
0x180043100  mov     [rbp+3Fh+var_A8], rax
0x180043104  mov     r15, r9
0x180043107  mov     [rsp+110h+pSelfRelativeSecurityDescriptor], r12
0x18004310c  movups  [rsp+110h+pSecurityDescriptor], xmm0
0x180043111  movups  [rbp+3Fh+var_B8], xmm0
0x180043115  call    memset_0
0x18004311a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043121  lea     r14, WPP_GLOBAL_Control
0x180043128  cmp     rcx, r14
0x18004312b  jz      short loc_180043147
0x18004312d  test    byte ptr [rcx+1Ch], 8
0x180043131  jz      short loc_180043147
0x180043133  mov     rcx, [rcx+10h]
0x180043137  lea     edx, [r13+0Ah]
0x18004313b  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x180043142  call    WPP_SF_
0x180043147  xor     edi, edi
0x180043149  cmp     edi, 5
0x18004314c  jnb     loc_18004321C
0x180043152  lea     r14, [rbp+3Fh+pSid]
0x180043156  mov     [rsp+110h+cbSid], 44h ; 'D'
0x18004315e  lea     r14, [r14+rdi*8]
0x180043162  mov     ecx, 44h ; 'D'
0x180043167  mov     rdx, r14
0x18004316a  call    AllocateWLMemory
0x18004316f  mov     ebx, eax
0x180043171  test    eax, eax
0x180043173  jnz     short loc_1800431E1
0x180043175  mov     r8, [r14]; pSid
0x180043178  lea     rcx, qword_180073190
0x18004317f  mov     ecx, [rcx+rdi*4]; WellKnownSidType
0x180043182  lea     r9, [rsp+110h+cbSid]; cbSid
0x180043187  xor     edx, edx; DomainSid
0x180043189  call    cs:__imp_CreateWellKnownSid
0x18004318f  test    eax, eax
0x180043191  jnz     short loc_18004319F
0x180043193  call    cs:__imp_GetLastError
0x180043199  mov     ebx, eax
0x18004319b  test    eax, eax
0x18004319d  jnz     short loc_1800431A3
0x18004319f  inc     edi
0x1800431a1  jmp     short loc_180043149
0x1800431a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431aa  lea     r14, WPP_GLOBAL_Control
0x1800431b1  cmp     rcx, r14
0x1800431b4  jz      loc_180043695
0x1800431ba  test    byte ptr [rcx+1Ch], 1
0x1800431be  jz      loc_180043695
0x1800431c4  mov     edx, 0Dh
0x1800431c9  mov     rcx, [rcx+10h]
0x1800431cd  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x1800431d4  mov     r9d, eax
0x1800431d7  call    WPP_SF_d
0x1800431dc  jmp     loc_180043695
0x1800431e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431e8  lea     r14, WPP_GLOBAL_Control
0x1800431ef  cmp     rcx, r14
0x1800431f2  jz      loc_180043695
0x1800431f8  test    byte ptr [rcx+1Ch], 1
0x1800431fc  jz      loc_180043695
0x180043202  mov     edx, 0Ch
0x180043207  mov     rcx, [rcx+10h]
0x18004320b  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x180043212  call    WPP_SF_
0x180043217  jmp     loc_180043695
0x18004321c  mov     edx, 1; dwRevision
0x180043221  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x180043226  call    cs:__imp_InitializeSecurityDescriptor
0x18004322c  test    eax, eax
0x18004322e  jnz     short loc_180043267
0x180043230  call    cs:__imp_GetLastError
0x180043236  mov     ebx, eax
0x180043238  test    eax, eax
0x18004323a  jz      short loc_180043267
0x18004323c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043243  lea     r14, WPP_GLOBAL_Control
0x18004324a  cmp     rcx, r14
0x18004324d  jz      loc_180043695
0x180043253  test    byte ptr [rcx+1Ch], 1
0x180043257  jz      loc_180043695
0x18004325d  mov     edx, 0Eh
0x180043262  jmp     loc_1800431C9
0x180043267  mov     rdx, [rbp+3Fh+pOwner]; pOwner
0x18004326b  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x180043270  xor     r8d, r8d; bOwnerDefaulted
0x180043273  call    cs:__imp_SetSecurityDescriptorOwner
0x180043279  test    eax, eax
0x18004327b  jnz     short loc_1800432B4
0x18004327d  call    cs:__imp_GetLastError
0x180043283  mov     ebx, eax
0x180043285  test    eax, eax
0x180043287  jz      short loc_1800432B4
0x180043289  mov     rcx, cs:WPP_GLOBAL_Control
0x180043290  lea     r14, WPP_GLOBAL_Control
0x180043297  cmp     rcx, r14
0x18004329a  jz      loc_180043695
0x1800432a0  test    byte ptr [rcx+1Ch], 1
0x1800432a4  jz      loc_180043695
0x1800432aa  mov     edx, 0Fh
0x1800432af  jmp     loc_1800431C9
0x1800432b4  mov     rdx, [rbp+3Fh+pOwner]; pGroup
0x1800432b8  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x1800432bd  xor     r8d, r8d; bGroupDefaulted
0x1800432c0  call    cs:__imp_SetSecurityDescriptorGroup
0x1800432c6  test    eax, eax
0x1800432c8  jnz     short loc_180043301
0x1800432ca  call    cs:__imp_GetLastError
0x1800432d0  mov     ebx, eax
0x1800432d2  test    eax, eax
0x1800432d4  jz      short loc_180043301
0x1800432d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432dd  lea     r14, WPP_GLOBAL_Control
0x1800432e4  cmp     rcx, r14
0x1800432e7  jz      loc_180043695
0x1800432ed  test    byte ptr [rcx+1Ch], 1
0x1800432f1  jz      loc_180043695
0x1800432f7  mov     edx, 10h
0x1800432fc  jmp     loc_1800431C9
0x180043301  mov     esi, [rsp+110h+var_D8]
0x180043305  mov     edi, 8
0x18004330a  xor     ebx, ebx
0x18004330c  cmp     ebx, esi
0x18004330e  jnb     loc_18004340D
0x180043314  lea     rcx, [rbx+rbx*2]
0x180043318  cmp     dword ptr [r15+rcx*4+4], 5
0x18004331e  jnb     loc_1800433DF
0x180043324  cmp     byte ptr [r15+rcx*4], 1
0x180043329  ja      loc_1800433B1
0x18004332f  mov     ecx, [r15+rcx*4+4]
0x180043334  mov     rcx, [rbp+rcx*8+3Fh+pSid]; pSid
0x180043339  call    cs:__imp_GetLengthSid
0x18004333f  add     eax, 8
0x180043342  cmp     eax, 8
0x180043345  jb      short loc_180043381
0x180043347  add     edi, eax
0x180043349  cmp     edi, eax
0x18004334b  jb      short loc_180043351
0x18004334d  inc     ebx
0x18004334f  jmp     short loc_18004330C
0x180043351  mov     ebx, 216h
0x180043356  mov     rcx, cs:WPP_GLOBAL_Control
0x18004335d  lea     r14, WPP_GLOBAL_Control
0x180043364  cmp     rcx, r14
0x180043367  jz      loc_180043695
0x18004336d  test    byte ptr [rcx+1Ch], 1
0x180043371  jz      loc_180043695
0x180043377  mov     edx, 14h
0x18004337c  jmp     loc_180043207
0x180043381  mov     ebx, 216h
0x180043386  mov     rcx, cs:WPP_GLOBAL_Control
0x18004338d  lea     r14, WPP_GLOBAL_Control
0x180043394  cmp     rcx, r14
0x180043397  jz      loc_180043695
0x18004339d  test    byte ptr [rcx+1Ch], 1
0x1800433a1  jz      loc_180043695
0x1800433a7  mov     edx, 13h
0x1800433ac  jmp     loc_180043207
0x1800433b1  mov     ebx, 57h ; 'W'
0x1800433b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433bd  lea     r14, WPP_GLOBAL_Control
0x1800433c4  cmp     rcx, r14
0x1800433c7  jz      loc_180043695
0x1800433cd  test    byte ptr [rcx+1Ch], 1
0x1800433d1  jz      loc_180043695
0x1800433d7  lea     edx, [rbx-45h]
0x1800433da  jmp     loc_180043207
0x1800433df  mov     ebx, 57h ; 'W'
0x1800433e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433eb  lea     r14, WPP_GLOBAL_Control
0x1800433f2  cmp     rcx, r14
0x1800433f5  jz      loc_180043695
0x1800433fb  test    byte ptr [rcx+1Ch], 1
0x1800433ff  jz      loc_180043695
0x180043405  lea     edx, [rbx-46h]
0x180043408  jmp     loc_180043207
0x18004340d  mov     ecx, edi
0x18004340f  lea     rdx, [rsp+110h+pAcl]
0x180043414  call    AllocateWLMemory
0x180043419  mov     ebx, eax
0x18004341b  test    eax, eax
0x18004341d  jz      short loc_180043457
0x18004341f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043426  lea     r14, WPP_GLOBAL_Control
0x18004342d  cmp     rcx, r14
0x180043430  jz      short loc_18004344D
0x180043432  test    byte ptr [rcx+1Ch], 1
0x180043436  jz      short loc_18004344D
0x180043438  mov     rcx, [rcx+10h]
0x18004343c  lea     r8, WPP_6182d216504e38fbc7ab7351306d8f7c_Traceguids
0x180043443  mov     edx, 15h
0x180043448  call    WPP_SF_
0x18004344d  mov     r13, [rsp+110h+pAcl]
0x180043452  jmp     loc_180043695
0x180043457  mov     r13, [rsp+110h+pAcl]
0x18004345c  mov     r14d, 2
0x180043462  mov     r8d, r14d; dwAclRevision
0x180043465  mov     rcx, r13; pAcl
0x180043468  mov     edx, edi; nAclLength
0x18004346a  call    cs:__imp_InitializeAcl
0x180043470  test    eax, eax
0x180043472  jnz     short loc_1800434AB
0x180043474  call    cs:__imp_GetLastError
0x18004347a  mov     ebx, eax
0x18004347c  test    eax, eax
0x18004347e  jz      short loc_1800434AB
0x180043480  mov     rcx, cs:WPP_GLOBAL_Control
0x180043487  lea     r14, WPP_GLOBAL_Control
0x18004348e  cmp     rcx, r14
0x180043491  jz      loc_180043695
0x180043497  test    byte ptr [rcx+1Ch], 1
0x18004349b  jz      loc_180043695
0x1800434a1  mov     edx, 16h
0x1800434a6  jmp     loc_1800431C9
0x1800434ab  xor     edi, edi
0x1800434ad  cmp     edi, esi
0x1800434af  jnb     loc_18004355D
0x1800434b5  lea     rcx, [rdi+rdi*2]
0x1800434b9  mov     edx, r14d; dwAceRevision
0x1800434bc  mov     r9d, [r15+rcx*4+4]
0x1800434c1  mov     r8d, [r15+rcx*4+8]; AccessMask
0x1800434c6  cmp     [r15+rcx*4], r12b
0x1800434ca  mov     rcx, r13; pAcl
0x1800434cd  mov     r9, [rbp+r9*8+3Fh+pSid]; pSid
0x1800434d2  jnz     short loc_180043515
0x1800434d4  call    cs:__imp_AddAccessAllowedAce
0x1800434da  test    eax, eax
0x1800434dc  jnz     short loc_18004352B
0x1800434de  call    cs:__imp_GetLastError
0x1800434e4  mov     ebx, eax
0x1800434e6  test    eax, eax
0x1800434e8  jz      short loc_18004352B
0x1800434ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434f1  lea     r14, WPP_GLOBAL_Control
0x1800434f8  cmp     rcx, r14
0x1800434fb  jz      loc_180043695
0x180043501  test    byte ptr [rcx+1Ch], 1
0x180043505  jz      loc_180043695
0x18004350b  mov     edx, 17h
0x180043510  jmp     loc_1800431C9
0x180043515  call    cs:__imp_AddAccessDeniedAce
0x18004351b  test    eax, eax
0x18004351d  jnz     short loc_18004352B
0x18004351f  call    cs:__imp_GetLastError
0x180043525  mov     ebx, eax
0x180043527  test    eax, eax
0x180043529  jnz     short loc_180043532
0x18004352b  inc     edi
0x18004352d  jmp     loc_1800434AD
0x180043532  mov     rcx, cs:WPP_GLOBAL_Control
0x180043539  lea     r14, WPP_GLOBAL_Control
0x180043540  cmp     rcx, r14
0x180043543  jz      loc_180043695
0x180043549  test    byte ptr [rcx+1Ch], 1
0x18004354d  jz      loc_180043695
0x180043553  mov     edx, 18h
0x180043558  jmp     loc_1800431C9
0x18004355d  xor     r9d, r9d; bDaclDefaulted
0x180043560  lea     rcx, [rsp+110h+pSecurityDescriptor]; pSecurityDescriptor
0x180043565  mov     r8, r13; pDacl
0x180043568  lea     edx, [r9+1]; bDaclPresent
0x18004356c  call    cs:__imp_SetSecurityDescriptorDacl
0x180043572  test    eax, eax
0x180043574  jnz     short loc_1800435AD
0x180043576  call    cs:__imp_GetLastError
0x18004357c  mov     ebx, eax
0x18004357e  test    eax, eax
0x180043580  jz      short loc_1800435AD
0x180043582  mov     rcx, cs:WPP_GLOBAL_Control
0x180043589  lea     r14, WPP_GLOBAL_Control
0x180043590  cmp     rcx, r14
0x180043593  jz      loc_180043695
0x180043599  test    byte ptr [rcx+1Ch], 1
0x18004359d  jz      loc_180043695
0x1800435a3  mov     edx, 19h
  ... truncated ...
```
