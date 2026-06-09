# UbpmpValidateConsumerActionParameters

- ea: `0x18001e0a0`
- end: `0x18001e8d4`
- name: `UbpmpValidateConsumerActionParameters`
- size: `2100`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ce00`

## callees

- `0x18001e0a0`
- `0x18001e8dc`
- `0x18001e9f4`
- `0x180030be8`
- `0x1800356cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e1c0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001e1c0`
- `RPCRT4!UuidIsNil` at `0x18001e2a8`
- `RPCRT4!UuidIsNil` at `0x18001e2a8`

## pseudocode

```c
__int64 __fastcall UbpmpValidateConsumerActionParameters(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  int v5; // r9d
  _DWORD *v6; // rax
  int *v7; // rax
  __int64 v8; // rcx
  int v9; // r9d
  __int64 v10; // rcx
  unsigned int v12; // r9d
  __int64 v13; // rcx
  __int64 v14; // r11
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // r8d
  _QWORD *v18; // rcx
  int v19; // edx
  UUID *v20; // rcx
  int v21; // r10d
  _QWORD *v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  int v25; // r8d
  _QWORD *v26; // rcx
  int v27; // edx
  RPC_STATUS Status; // [rsp+58h] [rbp+10h] BYREF

  v4 = 87;
  if ( !*(_QWORD *)a2 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 93;
    goto LABEL_43;
  }
  v5 = *(_DWORD *)(a2 + 16);
  if ( v5 != 1 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 94;
    goto LABEL_75;
  }
  v6 = *(_DWORD **)(a2 + 32);
  if ( v6 && (*v6 & 0xFFFC0000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *v6,
        a1);
    return v4;
  }
  v7 = *(int **)(a2 + 24);
  if ( !v7 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 96;
    goto LABEL_43;
  }
  v8 = *((_QWORD *)v7 + 5);
  if ( v8 && (!*(_DWORD *)(v8 + 8) || !*(_QWORD *)v8) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 97;
      goto LABEL_43;
    }
    return v4;
  }
  v9 = *v7;
  if ( *v7 == 1 )
  {
    if ( !*((_QWORD *)v7 + 1) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 98;
        goto LABEL_43;
      }
      return v4;
    }
  }
  else
  {
    switch ( v9 )
    {
      case 2:
        Status = 0;
        v20 = (UUID *)*((_QWORD *)v7 + 1);
        if ( !v20 || UuidIsNil(v20, &Status) == 1 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v4;
          v19 = 99;
          goto LABEL_43;
        }
        break;
      case 3:
        if ( !*((_QWORD *)v7 + 1) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v4;
          v19 = 100;
          goto LABEL_43;
        }
        break;
      case 4:
        v24 = *((_QWORD *)v7 + 1);
        if ( !v24 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 101;
            goto LABEL_43;
          }
          return v4;
        }
        if ( !*(_DWORD *)v24 && !*(_DWORD *)(v24 + 4) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 102;
            goto LABEL_43;
          }
          return v4;
        }
        if ( *(_DWORD *)(v24 + 8) )
        {
          if ( !*(_QWORD *)(v24 + 16) )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 103;
              goto LABEL_43;
            }
            return v4;
          }
        }
        else if ( *(_QWORD *)(v24 + 16) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 104;
            goto LABEL_43;
          }
          return v4;
        }
        break;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            v9,
            a1,
            87);
        return v4;
    }
  }
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 24) + 32LL);
  if ( !v10 )
    return 0;
  v12 = *(_DWORD *)(v10 + 36);
  if ( v12 >= 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        v12,
        a1,
        87);
    return v4;
  }
  if ( (unsigned int)(*(_DWORD *)v10 - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_DWORD *)v10,
        a1,
        87);
    return v4;
  }
  v13 = *(_QWORD *)(v10 + 8);
  if ( !v13 || !IsValidSid(*(PSID *)(v13 + 8)) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 108;
    goto LABEL_43;
  }
  v14 = *(_QWORD *)(a2 + 24);
  v15 = *(_QWORD *)(v14 + 32);
  v16 = *(_QWORD *)(v15 + 16);
  if ( v16 )
  {
    v25 = *(_DWORD *)(v15 + 32);
    if ( v25 != 4 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 109;
      v5 = v25;
      goto LABEL_75;
    }
  }
  v5 = *(_DWORD *)(v15 + 32);
  if ( ((v5 - 2) & 0xFFFFFFFC) != 0 || v5 == 3 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 110;
    goto LABEL_75;
  }
  v17 = *(_DWORD *)(v15 + 76);
  if ( (v17 & 0xFFFFFFF8) != 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 111;
    v5 = v17;
    goto LABEL_75;
  }
  if ( (v17 & 1) != 0 && v5 != 4 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 112;
LABEL_116:
    WPP_SF_ddSd(v26[2], v27, v17, v5, v17, a1, 87);
    return v4;
  }
  if ( (v17 & 2) != 0 && v5 != 5 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 113;
    goto LABEL_116;
  }
  if ( (v17 & 4) != 0 && v5 != 4 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 114;
    goto LABEL_116;
  }
  if ( !v16 && v5 == 4 && !*(_QWORD *)(v15 + 24) && (v17 & 1) == 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 115;
    v5 = 4;
    goto LABEL_75;
  }
  if ( v5 != 2 )
  {
    if ( *(_DWORD *)v15 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v17, 2, v5, a1, 87);
      return v4;
    }
    v21 = *(_DWORD *)(v15 + 36);
    if ( (unsigned int)(v21 - 1) <= 1 && (v5 != 4 || v21 != 1 || v17 != 4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, v17, v21, v5, a1, 87);
      return v4;
    }
  }
  if ( *(_DWORD *)(v15 + 96) && !*(_QWORD *)(v15 + 104) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 118;
      goto LABEL_43;
    }
    return v4;
  }
  if ( *(_QWORD *)(v15 + 80) )
  {
    if ( *(_DWORD *)(v15 + 36) == 1 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 120;
    }
    else
    {
      if ( *(_DWORD *)v14 != 2 )
        return 0;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 121;
    }
LABEL_75:
    WPP_SF_dSd(v22[2], v23, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, v5, a1, 87);
    return v4;
  }
  if ( !*(_QWORD *)(v15 + 104) )
    return 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v4;
  v19 = 119;
LABEL_43:
  WPP_SF_Sd(v18[2], v19, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, a1, 87);
  return 87;
}

```

## disassembly

```asm
0x18001e0a0  mov     [rsp+arg_0], rbx
0x18001e0a5  mov     [rsp+arg_10], rsi
0x18001e0aa  push    rdi
0x18001e0ab  sub     rsp, 40h
0x18001e0af  cmp     qword ptr [rdx], 0
0x18001e0b3  mov     rbx, rdx
0x18001e0b6  mov     rsi, rcx
0x18001e0b9  mov     edi, 57h ; 'W'
0x18001e0be  jz      loc_18001E43B
0x18001e0c4  mov     r9d, [rdx+10h]
0x18001e0c8  cmp     r9d, 1
0x18001e0cc  jnz     loc_18001E4AA
0x18001e0d2  mov     rax, [rdx+20h]
0x18001e0d6  test    rax, rax
0x18001e0d9  jz      short loc_18001E0EB
0x18001e0db  mov     r9d, [rax]
0x18001e0de  test    r9d, 0FFFC0000h
0x18001e0e5  jnz     loc_18001E4FB
0x18001e0eb  mov     rax, [rdx+18h]
0x18001e0ef  test    rax, rax
0x18001e0f2  jz      loc_18001E306
0x18001e0f8  mov     rcx, [rax+28h]
0x18001e0fc  test    rcx, rcx
0x18001e0ff  jnz     loc_18001E53B
0x18001e105  mov     r9d, [rax]
0x18001e108  cmp     r9d, 1
0x18001e10c  jnz     short loc_18001E13A
0x18001e10e  cmp     qword ptr [rax+8], 0
0x18001e113  jz      loc_18001E652
0x18001e119  mov     rax, [rbx+18h]
0x18001e11d  mov     rcx, [rax+20h]
0x18001e121  test    rcx, rcx
0x18001e124  jnz     short loc_18001E191
0x18001e126  xor     edi, edi
0x18001e128  mov     eax, edi
0x18001e12a  mov     rbx, [rsp+48h+arg_0]
0x18001e12f  mov     rsi, [rsp+48h+arg_10]
0x18001e134  add     rsp, 40h
0x18001e138  pop     rdi
0x18001e139  retn
0x18001e13a  mov     ecx, r9d
0x18001e13d  sub     ecx, 2
0x18001e140  jz      loc_18001E292
0x18001e146  sub     ecx, 1
0x18001e149  jz      loc_18001E39A
0x18001e14f  cmp     ecx, 1
0x18001e152  jz      loc_18001E576
0x18001e158  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e15f  lea     rax, WPP_GLOBAL_Control
0x18001e166  cmp     rcx, rax
0x18001e169  jz      short loc_18001E128
0x18001e16b  test    byte ptr [rcx+1Ch], 1
0x18001e16f  jz      short loc_18001E128
0x18001e171  mov     rcx, [rcx+10h]
0x18001e175  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001e17c  mov     edx, 69h ; 'i'
0x18001e181  mov     dword ptr [rsp+48h+var_20], edi
0x18001e185  mov     [rsp+48h+var_28], rsi
0x18001e18a  call    WPP_SF_dSd
0x18001e18f  jmp     short loc_18001E128
0x18001e191  mov     r9d, [rcx+24h]
0x18001e195  cmp     r9d, 3
0x18001e199  jnb     loc_18001E466
0x18001e19f  mov     r9d, [rcx]
0x18001e1a2  lea     eax, [r9-1]
0x18001e1a6  cmp     eax, 1
0x18001e1a9  ja      loc_18001E890
0x18001e1af  mov     rcx, [rcx+8]
0x18001e1b3  test    rcx, rcx
0x18001e1b6  jz      loc_18001E32E
0x18001e1bc  mov     rcx, [rcx+8]; pSid
0x18001e1c0  call    cs:__imp_IsValidSid
0x18001e1c6  test    eax, eax
0x18001e1c8  jz      loc_18001E32E
0x18001e1ce  mov     r11, [rbx+18h]
0x18001e1d2  mov     rcx, [r11+20h]
0x18001e1d6  mov     rdx, [rcx+10h]
0x18001e1da  test    rdx, rdx
0x18001e1dd  jnz     loc_18001E67D
0x18001e1e3  mov     r9d, [rcx+20h]
0x18001e1e7  lea     eax, [r9-2]
0x18001e1eb  test    eax, 0FFFFFFFCh
0x18001e1f0  jnz     loc_18001E865
0x18001e1f6  cmp     r9d, 3
0x18001e1fa  jz      loc_18001E865
0x18001e200  mov     r8d, [rcx+4Ch]
0x18001e204  test    r8d, 0FFFFFFF8h
0x18001e20b  jnz     loc_18001E6B9
0x18001e211  mov     eax, r8d
0x18001e214  and     eax, 1
0x18001e217  jnz     loc_18001E6E7
0x18001e21d  test    r8b, 2
0x18001e221  jnz     loc_18001E731
0x18001e227  test    r8b, 4
0x18001e22b  jnz     loc_18001E763
0x18001e231  test    rdx, rdx
0x18001e234  jnz     short loc_18001E240
0x18001e236  cmp     r9d, 4
0x18001e23a  jz      loc_18001E790
0x18001e240  cmp     r9d, 2
0x18001e244  jnz     loc_18001E356
0x18001e24a  cmp     dword ptr [rcx+60h], 0
0x18001e24e  ja      loc_18001E7C9
0x18001e254  cmp     qword ptr [rcx+50h], 0
0x18001e259  jnz     loc_18001E7FF
0x18001e25f  cmp     qword ptr [rcx+68h], 0
0x18001e264  jz      loc_18001E126
0x18001e26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e271  lea     rax, WPP_GLOBAL_Control
0x18001e278  cmp     rcx, rax
0x18001e27b  jz      loc_18001E128
0x18001e281  test    byte ptr [rcx+1Ch], 1
0x18001e285  jz      loc_18001E128
0x18001e28b  mov     edx, 77h ; 'w'
0x18001e290  jmp     short loc_18001E2DD
0x18001e292  mov     [rsp+48h+Status], 0
0x18001e29a  mov     rcx, [rax+8]; Uuid
0x18001e29e  test    rcx, rcx
0x18001e2a1  jz      short loc_18001E2B7
0x18001e2a3  lea     rdx, [rsp+48h+Status]; Status
0x18001e2a8  call    cs:__imp_UuidIsNil
0x18001e2ae  cmp     eax, 1
0x18001e2b1  jnz     loc_18001E119
0x18001e2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2be  lea     rax, WPP_GLOBAL_Control
0x18001e2c5  cmp     rcx, rax
0x18001e2c8  jz      loc_18001E128
0x18001e2ce  test    byte ptr [rcx+1Ch], 1
0x18001e2d2  jz      loc_18001E128
0x18001e2d8  mov     edx, 63h ; 'c'
0x18001e2dd  mov     rcx, [rcx+10h]
0x18001e2e1  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001e2e8  mov     r9, rsi
0x18001e2eb  mov     dword ptr [rsp+48h+var_28], edi
0x18001e2ef  call    WPP_SF_Sd
0x18001e2f4  mov     rbx, [rsp+48h+arg_0]
0x18001e2f9  mov     eax, edi
0x18001e2fb  mov     rsi, [rsp+48h+arg_10]
0x18001e300  add     rsp, 40h
0x18001e304  pop     rdi
0x18001e305  retn
0x18001e306  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e30d  lea     rax, WPP_GLOBAL_Control
0x18001e314  cmp     rcx, rax
0x18001e317  jz      loc_18001E128
0x18001e31d  test    byte ptr [rcx+1Ch], 1
0x18001e321  jz      loc_18001E128
0x18001e327  mov     edx, 60h ; '`'
0x18001e32c  jmp     short loc_18001E2DD
0x18001e32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e335  lea     rax, WPP_GLOBAL_Control
0x18001e33c  cmp     rcx, rax
0x18001e33f  jz      loc_18001E128
0x18001e345  test    byte ptr [rcx+1Ch], 1
0x18001e349  jz      loc_18001E128
0x18001e34f  mov     edx, 6Ch ; 'l'
0x18001e354  jmp     short loc_18001E2DD
0x18001e356  cmp     dword ptr [rcx], 2
0x18001e359  jnz     short loc_18001E3D0
0x18001e35b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e362  lea     rax, WPP_GLOBAL_Control
0x18001e369  cmp     rcx, rax
0x18001e36c  jz      loc_18001E128
0x18001e372  test    byte ptr [rcx+1Ch], 1
0x18001e376  jz      loc_18001E128
0x18001e37c  mov     [rsp+48h+var_18], edi
0x18001e380  mov     edx, 74h ; 't'
0x18001e385  mov     [rsp+48h+var_20], rsi
0x18001e38a  mov     dword ptr [rsp+48h+var_28], r9d
0x18001e38f  mov     r9d, 2
0x18001e395  jmp     loc_18001E42D
0x18001e39a  cmp     qword ptr [rax+8], 0
0x18001e39f  jnz     loc_18001E119
0x18001e3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3ac  lea     rax, WPP_GLOBAL_Control
0x18001e3b3  cmp     rcx, rax
0x18001e3b6  jz      loc_18001E128
0x18001e3bc  test    byte ptr [rcx+1Ch], 1
0x18001e3c0  jz      loc_18001E128
0x18001e3c6  mov     edx, 64h ; 'd'
0x18001e3cb  jmp     loc_18001E2DD
0x18001e3d0  mov     r10d, [rcx+24h]
0x18001e3d4  lea     eax, [r10-1]
0x18001e3d8  cmp     eax, 1
0x18001e3db  ja      loc_18001E24A
0x18001e3e1  cmp     r9d, 4
0x18001e3e5  jnz     short loc_18001E3F6
0x18001e3e7  cmp     r10d, 1
0x18001e3eb  jnz     short loc_18001E3F6
0x18001e3ed  cmp     r8d, r9d
0x18001e3f0  jz      loc_18001E24A
0x18001e3f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3fd  lea     rax, WPP_GLOBAL_Control
0x18001e404  cmp     rcx, rax
0x18001e407  jz      loc_18001E128
0x18001e40d  test    byte ptr [rcx+1Ch], 1
0x18001e411  jz      loc_18001E128
0x18001e417  mov     [rsp+48h+var_18], edi
0x18001e41b  mov     edx, 75h ; 'u'
0x18001e420  mov     [rsp+48h+var_20], rsi
0x18001e425  mov     dword ptr [rsp+48h+var_28], r9d
0x18001e42a  mov     r9d, r10d
0x18001e42d  mov     rcx, [rcx+10h]
0x18001e431  call    WPP_SF_ddSd
0x18001e436  jmp     loc_18001E128
0x18001e43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e442  lea     rax, WPP_GLOBAL_Control
0x18001e449  cmp     rcx, rax
0x18001e44c  jz      loc_18001E128
0x18001e452  test    byte ptr [rcx+1Ch], 1
0x18001e456  jz      loc_18001E128
0x18001e45c  mov     edx, 5Dh ; ']'
0x18001e461  jmp     loc_18001E2DD
0x18001e466  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e46d  lea     rax, WPP_GLOBAL_Control
0x18001e474  cmp     rcx, rax
0x18001e477  jz      loc_18001E128
0x18001e47d  test    byte ptr [rcx+1Ch], 1
0x18001e481  jz      loc_18001E128
0x18001e487  mov     rcx, [rcx+10h]
0x18001e48b  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001e492  mov     edx, 6Ah ; 'j'
0x18001e497  mov     dword ptr [rsp+48h+var_20], edi
0x18001e49b  mov     [rsp+48h+var_28], rsi
0x18001e4a0  call    WPP_SF_dSd
0x18001e4a5  jmp     loc_18001E128
0x18001e4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4b1  lea     rax, WPP_GLOBAL_Control
0x18001e4b8  cmp     rcx, rax
0x18001e4bb  jz      loc_18001E128
0x18001e4c1  test    byte ptr [rcx+1Ch], 1
0x18001e4c5  jz      loc_18001E128
0x18001e4cb  mov     edx, 5Eh ; '^'
0x18001e4d0  jmp     short loc_18001E4DD
0x18001e4d2  mov     edx, 73h ; 's'
0x18001e4d7  mov     r9d, 4
0x18001e4dd  mov     rcx, [rcx+10h]
0x18001e4e1  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001e4e8  mov     dword ptr [rsp+48h+var_20], edi
0x18001e4ec  mov     [rsp+48h+var_28], rsi
0x18001e4f1  call    WPP_SF_dSd
0x18001e4f6  jmp     loc_18001E128
0x18001e4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e502  lea     rax, WPP_GLOBAL_Control
0x18001e509  cmp     rcx, rax
0x18001e50c  jz      loc_18001E128
0x18001e512  test    byte ptr [rcx+1Ch], 1
0x18001e516  jz      loc_18001E128
0x18001e51c  mov     rcx, [rcx+10h]
0x18001e520  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001e527  mov     edx, 5Fh ; '_'
0x18001e52c  mov     [rsp+48h+var_28], rsi
0x18001e531  call    WPP_SF_LSd
0x18001e536  jmp     loc_18001E128
0x18001e53b  cmp     dword ptr [rcx+8], 0
0x18001e53f  jz      short loc_18001E54B
0x18001e541  cmp     qword ptr [rcx], 0
0x18001e545  jnz     loc_18001E105
0x18001e54b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e552  lea     rax, WPP_GLOBAL_Control
0x18001e559  cmp     rcx, rax
0x18001e55c  jz      loc_18001E128
0x18001e562  test    byte ptr [rcx+1Ch], 1
0x18001e566  jz      loc_18001E128
0x18001e56c  mov     edx, 61h ; 'a'
0x18001e571  jmp     loc_18001E2DD
0x18001e576  mov     rcx, [rax+8]
0x18001e57a  test    rcx, rcx
0x18001e57d  jnz     short loc_18001E5AA
0x18001e57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e586  lea     rax, WPP_GLOBAL_Control
0x18001e58d  cmp     rcx, rax
0x18001e590  jz      loc_18001E128
0x18001e596  test    byte ptr [rcx+1Ch], 1
0x18001e59a  jz      loc_18001E128
0x18001e5a0  mov     edx, 65h ; 'e'
0x18001e5a5  jmp     loc_18001E2DD
0x18001e5aa  cmp     dword ptr [rcx], 0
0x18001e5ad  jnz     short loc_18001E5E0
0x18001e5af  cmp     dword ptr [rcx+4], 0
0x18001e5b3  jnz     short loc_18001E5E0
0x18001e5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5bc  lea     rax, WPP_GLOBAL_Control
0x18001e5c3  cmp     rcx, rax
0x18001e5c6  jz      loc_18001E128
0x18001e5cc  test    byte ptr [rcx+1Ch], 1
0x18001e5d0  jz      loc_18001E128
0x18001e5d6  mov     edx, 66h ; 'f'
0x18001e5db  jmp     loc_18001E2DD
0x18001e5e0  cmp     dword ptr [rcx+8], 0
0x18001e5e4  jz      short loc_18001E61C
0x18001e5e6  cmp     qword ptr [rcx+10h], 0
0x18001e5eb  jnz     loc_18001E119
0x18001e5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5f8  lea     rax, WPP_GLOBAL_Control
0x18001e5ff  cmp     rcx, rax
0x18001e602  jz      loc_18001E128
0x18001e608  test    byte ptr [rcx+1Ch], 1
0x18001e60c  jz      loc_18001E128
0x18001e612  mov     edx, 67h ; 'g'
  ... truncated ...
```
