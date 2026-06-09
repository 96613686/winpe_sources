# ValidateSidRights(void *,void *,int *)

- ea: `0x18002e78c`
- end: `0x18002eab5`
- name: `?ValidateSidRights@@YAKPEAX0PEAH@Z`
- size: `809`
- prototype: `unsigned int(void *, void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002eac0`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18002e78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8f0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002e8e6`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002e8e6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e97f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e97f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e83d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e83d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002e96a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002e96a`

## pseudocode

```c
__int64 __fastcall ValidateSidRights(void *a1, void *a2, int *a3)
{
  union DOT11_OUI_HEADER *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  DWORD LastError; // eax
  PACL v8; // r9
  int v9; // r15d
  DWORD i; // r12d
  DWORD v11; // eax
  LPVOID v12; // rsi
  LPVOID v13; // r14
  int v14; // edi
  char *v15; // r13
  LPVOID pAce; // [rsp+20h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-10h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+50h] BYREF
  int *v21; // [rsp+90h] [rbp+58h]
  WINBOOL bDaclPresent; // [rsp+98h] [rbp+60h] BYREF

  v21 = a3;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  pAce = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v5 = 1338;
    if ( v4 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v5;
    if ( !*((_BYTE *)v4 + 105) || (*((_BYTE *)v4 + 108) & 2) == 0 )
      goto LABEL_62;
    v6 = 15;
LABEL_60:
    WPP_SF_(*((_QWORD *)v4 + 12), v6, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
LABEL_61:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_62;
  }
  v5 = 0;
  if ( GetSecurityDescriptorDacl(a2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, LastError);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v5 )
      goto LABEL_62;
  }
  if ( bDaclDefaulted || !bDaclPresent || (v8 = pDacl) == 0 )
  {
    v5 = 1336;
    if ( v4 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v5;
    if ( !*((_BYTE *)v4 + 105) || (*((_BYTE *)v4 + 108) & 2) == 0 )
      goto LABEL_62;
    v6 = 17;
    goto LABEL_60;
  }
  v9 = 458787;
  for ( i = 0; ; ++i )
  {
    if ( !v9 || i >= v8->AceCount )
      goto LABEL_47;
    pAce = 0;
    if ( GetAce(v8, i, &pAce) )
    {
      v4 = WPP_GLOBAL_Control;
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, v11);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v5 )
        goto LABEL_62;
    }
    if ( !*(_BYTE *)pAce )
    {
      v12 = 0;
      v13 = pAce;
      goto LABEL_36;
    }
    if ( *(_BYTE *)pAce != 1 )
      break;
    v13 = 0;
    v12 = pAce;
LABEL_36:
    v14 = *((_DWORD *)pAce + 1);
    v15 = (char *)pAce + 8;
    if ( !IsValidSid((char *)pAce + 8) )
    {
      v5 = 1337;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
        return v5;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        v6 = 20;
        goto LABEL_60;
      }
      goto LABEL_62;
    }
    if ( EqualSid(v15, a1) )
    {
      if ( v12 && (v14 & v9) != 0 )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids);
        }
LABEL_47:
        *v21 = v9 != 0;
        goto LABEL_61;
      }
      if ( v13 )
        v9 &= ~v14;
    }
    v8 = pDacl;
  }
  v5 = 1336;
  if ( v4 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v5;
  if ( *((_BYTE *)v4 + 105) && (*((_BYTE *)v4 + 108) & 2) != 0 )
  {
    v6 = 19;
    goto LABEL_60;
  }
LABEL_62:
  if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v4 + 105) >= 4u
    && (*((_BYTE *)v4 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 12), 22, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002e78c  mov     [rsp-40h+arg_10], r8
0x18002e791  mov     [rsp-40h+pSid2], rcx
0x18002e796  push    rbp
0x18002e797  push    rbx
0x18002e798  push    rsi
0x18002e799  push    rdi
0x18002e79a  push    r12
0x18002e79c  push    r13
0x18002e79e  push    r14
0x18002e7a0  push    r15
0x18002e7a2  mov     rbp, rsp
0x18002e7a5  sub     rsp, 38h
0x18002e7a9  xor     r13d, r13d
0x18002e7ac  mov     rdi, rdx
0x18002e7af  mov     [rbp+bDaclPresent], r13d
0x18002e7b3  mov     [rbp+bDaclDefaulted], r13d
0x18002e7b7  mov     [rbp+pDacl], r13
0x18002e7bb  mov     [rbp+pAce], r13
0x18002e7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7c6  lea     r14, WPP_GLOBAL_Control
0x18002e7cd  mov     sil, 2
0x18002e7d0  cmp     rcx, r14
0x18002e7d3  jz      short loc_18002E7FC
0x18002e7d5  cmp     byte ptr [rcx+69h], 4
0x18002e7d9  jb      short loc_18002E7FC
0x18002e7db  test    [rcx+6Ch], sil
0x18002e7df  jz      short loc_18002E7FC
0x18002e7e1  mov     rcx, [rcx+60h]
0x18002e7e5  lea     edx, [r13+0Eh]
0x18002e7e9  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002e7f0  call    WPP_SF_
0x18002e7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7fc  test    rdi, rdi
0x18002e7ff  jnz     short loc_18002E82B
0x18002e801  mov     ebx, 53Ah
0x18002e806  cmp     rcx, r14
0x18002e809  jz      loc_18002EAA2
0x18002e80f  cmp     byte ptr [rcx+69h], 1
0x18002e813  jb      loc_18002EA79
0x18002e819  test    [rcx+6Ch], sil
0x18002e81d  jz      loc_18002EA79
0x18002e823  lea     edx, [rdi+0Fh]
0x18002e826  jmp     loc_18002EA62
0x18002e82b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18002e82f  mov     rcx, rdi; pSecurityDescriptor
0x18002e832  lea     r8, [rbp+pDacl]; pDacl
0x18002e836  mov     ebx, r13d
0x18002e839  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18002e83d  call    cs:__imp_GetSecurityDescriptorDacl
0x18002e843  test    eax, eax
0x18002e845  jnz     short loc_18002E890
0x18002e847  call    cs:__imp_GetLastError
0x18002e84d  mov     ebx, eax
0x18002e84f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e856  cmp     rcx, r14
0x18002e859  jz      short loc_18002E886
0x18002e85b  cmp     byte ptr [rcx+69h], 1
0x18002e85f  jb      short loc_18002E886
0x18002e861  test    [rcx+6Ch], sil
0x18002e865  jz      short loc_18002E886
0x18002e867  mov     rcx, [rcx+60h]
0x18002e86b  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002e872  mov     edx, 10h
0x18002e877  mov     r9d, eax
0x18002e87a  call    WPP_SF_d
0x18002e87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e886  test    ebx, ebx
0x18002e888  jnz     loc_18002EA79
0x18002e88e  jmp     short loc_18002E897
0x18002e890  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e897  cmp     [rbp+bDaclDefaulted], r13d
0x18002e89b  jnz     loc_18002EA47
0x18002e8a1  cmp     [rbp+bDaclPresent], r13d
0x18002e8a5  jz      loc_18002EA47
0x18002e8ab  mov     r9, [rbp+pDacl]
0x18002e8af  test    r9, r9
0x18002e8b2  jz      loc_18002EA47
0x18002e8b8  mov     r15d, 70023h
0x18002e8be  mov     r12d, r13d
0x18002e8c1  test    r15d, r15d
0x18002e8c4  jz      loc_18002E9EA
0x18002e8ca  movzx   eax, word ptr [r9+4]
0x18002e8cf  cmp     r12d, eax
0x18002e8d2  jnb     loc_18002E9EA
0x18002e8d8  lea     r8, [rbp+pAce]; pAce
0x18002e8dc  mov     [rbp+pAce], r13
0x18002e8e0  mov     edx, r12d; dwAceIndex
0x18002e8e3  mov     rcx, r9; pAcl
0x18002e8e6  call    cs:__imp_GetAce
0x18002e8ec  test    eax, eax
0x18002e8ee  jnz     short loc_18002E939
0x18002e8f0  call    cs:__imp_GetLastError
0x18002e8f6  mov     ebx, eax
0x18002e8f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8ff  cmp     rcx, r14
0x18002e902  jz      short loc_18002E92F
0x18002e904  cmp     byte ptr [rcx+69h], 1
0x18002e908  jb      short loc_18002E92F
0x18002e90a  test    [rcx+6Ch], sil
0x18002e90e  jz      short loc_18002E92F
0x18002e910  mov     rcx, [rcx+60h]
0x18002e914  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002e91b  mov     edx, 12h
0x18002e920  mov     r9d, eax
0x18002e923  call    WPP_SF_d
0x18002e928  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e92f  test    ebx, ebx
0x18002e931  jnz     loc_18002EA79
0x18002e937  jmp     short loc_18002E940
0x18002e939  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e940  mov     rax, [rbp+pAce]
0x18002e944  cmp     [rax], r13b
0x18002e947  jnz     short loc_18002E951
0x18002e949  mov     rsi, r13
0x18002e94c  mov     r14, rax
0x18002e94f  jmp     short loc_18002E960
0x18002e951  cmp     byte ptr [rax], 1
0x18002e954  jnz     loc_18002EA2A
0x18002e95a  mov     r14, r13
0x18002e95d  mov     rsi, rax
0x18002e960  mov     edi, [rax+4]
0x18002e963  lea     r13, [rax+8]
0x18002e967  mov     rcx, r13; pSid
0x18002e96a  call    cs:__imp_IsValidSid
0x18002e970  test    eax, eax
0x18002e972  jz      loc_18002E9FB
0x18002e978  mov     rdx, [rbp+pSid2]; pSid2
0x18002e97c  mov     rcx, r13; pSid1
0x18002e97f  call    cs:__imp_EqualSid
0x18002e985  xor     r13d, r13d
0x18002e988  test    eax, eax
0x18002e98a  jz      short loc_18002E9A0
0x18002e98c  test    rsi, rsi
0x18002e98f  jz      short loc_18002E996
0x18002e991  test    r15d, edi
0x18002e994  jnz     short loc_18002E9B6
0x18002e996  test    r14, r14
0x18002e999  jz      short loc_18002E9A0
0x18002e99b  not     edi
0x18002e99d  and     r15d, edi
0x18002e9a0  mov     r9, [rbp+pDacl]
0x18002e9a4  lea     r14, WPP_GLOBAL_Control
0x18002e9ab  inc     r12d
0x18002e9ae  mov     sil, 2
0x18002e9b1  jmp     loc_18002E8C1
0x18002e9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9bd  lea     r14, WPP_GLOBAL_Control
0x18002e9c4  cmp     rcx, r14
0x18002e9c7  jz      short loc_18002E9EA
0x18002e9c9  cmp     byte ptr [rcx+69h], 3
0x18002e9cd  jb      short loc_18002E9EA
0x18002e9cf  test    byte ptr [rcx+6Ch], 2
0x18002e9d3  jz      short loc_18002E9EA
0x18002e9d5  mov     rcx, [rcx+60h]
0x18002e9d9  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002e9e0  mov     edx, 15h
0x18002e9e5  call    WPP_SF_
0x18002e9ea  mov     rcx, [rbp+arg_10]
0x18002e9ee  mov     eax, r13d
0x18002e9f1  test    r15d, r15d
0x18002e9f4  setnz   al
0x18002e9f7  mov     [rcx], eax
0x18002e9f9  jmp     short loc_18002EA72
0x18002e9fb  mov     ebx, 539h
0x18002ea00  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea07  lea     r14, WPP_GLOBAL_Control
0x18002ea0e  cmp     rcx, r14
0x18002ea11  jz      loc_18002EAA2
0x18002ea17  cmp     byte ptr [rcx+69h], 1
0x18002ea1b  jb      short loc_18002EA79
0x18002ea1d  test    byte ptr [rcx+6Ch], 2
0x18002ea21  jz      short loc_18002EA79
0x18002ea23  mov     edx, 14h
0x18002ea28  jmp     short loc_18002EA62
0x18002ea2a  mov     ebx, 538h
0x18002ea2f  cmp     rcx, r14
0x18002ea32  jz      short loc_18002EAA2
0x18002ea34  cmp     byte ptr [rcx+69h], 1
0x18002ea38  jb      short loc_18002EA79
0x18002ea3a  test    [rcx+6Ch], sil
0x18002ea3e  jz      short loc_18002EA79
0x18002ea40  mov     edx, 13h
0x18002ea45  jmp     short loc_18002EA62
0x18002ea47  mov     ebx, 538h
0x18002ea4c  cmp     rcx, r14
0x18002ea4f  jz      short loc_18002EAA2
0x18002ea51  cmp     byte ptr [rcx+69h], 1
0x18002ea55  jb      short loc_18002EA79
0x18002ea57  test    [rcx+6Ch], sil
0x18002ea5b  jz      short loc_18002EA79
0x18002ea5d  mov     edx, 11h
0x18002ea62  mov     rcx, [rcx+60h]
0x18002ea66  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ea6d  call    WPP_SF_
0x18002ea72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea79  cmp     rcx, r14
0x18002ea7c  jz      short loc_18002EAA2
0x18002ea7e  cmp     byte ptr [rcx+69h], 4
0x18002ea82  jb      short loc_18002EAA2
0x18002ea84  test    byte ptr [rcx+6Ch], 2
0x18002ea88  jz      short loc_18002EAA2
0x18002ea8a  mov     rcx, [rcx+60h]
0x18002ea8e  lea     r8, WPP_76562b70e03c33e8f14159b6928c51ff_Traceguids
0x18002ea95  mov     edx, 16h
0x18002ea9a  mov     r9d, ebx
0x18002ea9d  call    WPP_SF_d
0x18002eaa2  mov     eax, ebx
0x18002eaa4  add     rsp, 38h
0x18002eaa8  pop     r15
0x18002eaaa  pop     r14
0x18002eaac  pop     r13
0x18002eaae  pop     r12
0x18002eab0  pop     rdi
0x18002eab1  pop     rsi
0x18002eab2  pop     rbx
0x18002eab3  pop     rbp
0x18002eab4  retn
```
