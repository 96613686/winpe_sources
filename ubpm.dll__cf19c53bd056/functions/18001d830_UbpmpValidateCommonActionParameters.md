# UbpmpValidateCommonActionParameters

- ea: `0x18001d830`
- end: `0x18001e090`
- name: `UbpmpValidateCommonActionParameters`
- size: `2144`
- prototype: `__int64 __fastcall(__int64, _QWORD *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ce00`

## callees

- `0x18001d830`
- `0x18001e98c`
- `0x18001e9f4`
- `0x180030be8`
- `0x180035000`
- `0x180035618`
- `0x1800356cc`
- `0x180035804`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001dcdd`
- `msvcrt!_wcsicmp` at `0x18001dd7e`
- `msvcrt!_wcsicmp` at `0x18001dcdd`
- `msvcrt!_wcsicmp` at `0x18001dd7e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001de32`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001de32`

## pseudocode

```c
__int64 __fastcall UbpmpValidateCommonActionParameters(__int64 a1, _QWORD *a2, bool *a3)
{
  __int64 v3; // rax
  void *v6; // r10
  int v7; // edx
  const wchar_t *v8; // r9
  _DWORD *v9; // r15
  const wchar_t *v10; // r8
  __int64 v11; // r12
  char v12; // r13
  bool v13; // zf
  unsigned int v15; // ebx
  __int64 v16; // rbp
  __int64 v17; // rcx
  unsigned __int16 i; // bp
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  int v26; // edx
  _QWORD *v27; // rcx
  int v28; // r9d
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // r11
  __int64 v32; // rcx
  __int64 v33; // r11
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // r11
  __int64 v38; // rax
  __int64 v39; // rcx
  void *v40; // rdx
  const wchar_t *v41; // [rsp+40h] [rbp-58h]
  int v42; // [rsp+A0h] [rbp+8h]
  const wchar_t *v43; // [rsp+A8h] [rbp+10h]
  __int64 v44; // [rsp+B0h] [rbp+18h]
  void *v45; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 40);
  v6 = 0;
  v7 = 0;
  v45 = 0;
  v8 = 0;
  v42 = 0;
  v9 = *(_DWORD **)(v3 + 32);
  v10 = 0;
  v11 = 0;
  v43 = 0;
  v12 = 0;
  v41 = 0;
  v13 = *(_DWORD *)(v3 + 16) == 1;
  v15 = 87;
  *a3 = 0;
  *a2 = 0;
  if ( v13 )
  {
    v16 = *(_QWORD *)(v3 + 24);
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(a1 + 8),
          87);
      return v15;
    }
    if ( v9 )
    {
      if ( (*v9 & 0x40) != 0 && (*v9 & 0x180) == 0x100 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_LSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            134,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *v9,
            *(_QWORD *)(a1 + 8));
        return v15;
      }
      v8 = 0;
    }
    v17 = *(_QWORD *)(v16 + 32);
    if ( v17 )
    {
      v20 = *(unsigned __int8 *)(v17 + 49);
      if ( (unsigned __int8)v20 >= 2u )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v28 = v20;
          v29 = 135;
LABEL_33:
          WPP_SF_dSd(
            v27[2],
            v29,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            v28,
            *(_QWORD *)(a1 + 8),
            v15);
        }
        return v15;
      }
      v21 = *(_QWORD *)(v17 + 40);
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_iSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            v21,
            *(_QWORD *)(a1 + 8),
            87);
        return v15;
      }
      if ( *(_BYTE *)(v17 + 48) )
      {
        v24 = UbpmConsumerSetDefaultPrivilegesMask(*(_QWORD *)(v17 + 8), v17 + 40);
        if ( v24 )
        {
          v15 = v24;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v15;
          v26 = 137;
          goto LABEL_37;
        }
      }
      v22 = *(_QWORD *)(v16 + 32);
      v23 = *(_QWORD *)(v22 + 8);
      v11 = *(_QWORD *)(v22 + 40);
      if ( v23 )
        v6 = *(void **)(v23 + 8);
      else
        v6 = 0;
      v8 = *(const wchar_t **)(v22 + 56);
      v10 = *(const wchar_t **)(v22 + 64);
      v7 = *(_DWORD *)(v22 + 72);
      v12 = *(_BYTE *)(v22 + 49);
      *a3 = *(_DWORD *)v16 != 1;
      v45 = v6;
      v43 = v8;
      v41 = v10;
      v42 = v7;
      *a2 = v22;
    }
  }
  for ( i = 1; ; ++i )
  {
    if ( (unsigned int)i >= *(_DWORD *)(a1 + 32) )
      return 0;
    v30 = *(_QWORD *)(a1 + 40);
    v44 = 40LL * i;
    v31 = v44 + v30;
    v32 = *(_QWORD *)(v44 + v30 + 32);
    if ( !v32 )
      break;
    if ( v9 )
    {
      v33 = *(_QWORD *)(v30 + 32);
      if ( *(_DWORD *)(v32 + 12) != *(_DWORD *)(v33 + 12)
        || *(_DWORD *)(v32 + 32) != *(_DWORD *)(v33 + 32)
        || *(_DWORD *)(v32 + 36) != *(_DWORD *)(v33 + 36)
        || *(_DWORD *)(v32 + 4) != *(_DWORD *)(v33 + 4)
        || *(_DWORD *)(v32 + 8) != *(_DWORD *)(v33 + 8)
        || ((*(_BYTE *)v33 ^ *(_BYTE *)v32) & 0x40) != 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v15;
        v29 = 139;
        goto LABEL_32;
      }
      v31 = v44 + v30;
    }
    else if ( *(_DWORD *)(v32 + 12)
           || *(_DWORD *)(v32 + 32)
           || *(_DWORD *)(v32 + 36)
           || *(_DWORD *)(v32 + 4)
           || *(_DWORD *)(v32 + 8)
           || (*(_BYTE *)v32 & 0x40) != 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v15;
      v29 = 138;
      goto LABEL_32;
    }
LABEL_63:
    if ( *(_DWORD *)(v31 + 16) != 1 )
      continue;
    v35 = *(_QWORD *)(v31 + 24);
    if ( !v35 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          141,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(a1 + 8),
          i,
          v15);
      return v15;
    }
    if ( v32 && (*(_DWORD *)v32 & 0x1C0) == 0x140 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dLSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (_DWORD)v10,
          i,
          *(_DWORD *)v32,
          *(_QWORD *)(a1 + 8),
          v15);
      return v15;
    }
    v36 = *(_QWORD *)(v35 + 32);
    if ( v36 )
    {
      if ( *(_BYTE *)(v36 + 48) )
      {
        v24 = UbpmConsumerSetDefaultPrivilegesMask(*(_QWORD *)(v36 + 8), v36 + 40);
        v15 = v24;
        if ( !v24 )
        {
          v10 = v41;
          v8 = v43;
          v7 = v42;
          v6 = v45;
          goto LABEL_71;
        }
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v15;
        v26 = 143;
LABEL_37:
        WPP_SF_Sd(v25[2], v26, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, *(_QWORD *)(a1 + 8), v24);
        return v15;
      }
LABEL_71:
      v37 = *(_QWORD *)(a1 + 40);
      v38 = *(_QWORD *)(*(_QWORD *)(v44 + v37 + 24) + 32LL);
      if ( v11 != *(_QWORD *)(v38 + 40) || v12 != *(_BYTE *)(v38 + 49) || v7 != *(_DWORD *)(v38 + 72) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v29 = 144;
          goto LABEL_32;
        }
        return v15;
      }
      if ( v8 )
      {
        if ( *(_QWORD *)(v38 + 56) )
        {
          if ( _wcsicmp(v8, *(const wchar_t **)(v38 + 56)) )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v29 = 145;
              goto LABEL_32;
            }
            return v15;
          }
          v10 = v41;
          v8 = v43;
          v7 = v42;
          v6 = v45;
        }
        v37 = *(_QWORD *)(a1 + 40);
        if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + v37 + 24) + 32LL) + 56LL) )
          goto LABEL_79;
LABEL_83:
        v39 = *(_QWORD *)(*(_QWORD *)(v44 + v37 + 24) + 32LL);
        if ( v10 )
        {
          if ( *(_QWORD *)(v39 + 64) )
          {
            if ( _wcsicmp(v10, *(const wchar_t **)(v39 + 64)) )
            {
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v29 = 147;
                goto LABEL_32;
              }
              return v15;
            }
            v10 = v41;
            v8 = v43;
            v7 = v42;
            v6 = v45;
          }
          v37 = *(_QWORD *)(a1 + 40);
          if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + v37 + 24) + 32LL) + 64LL) )
            goto LABEL_88;
          goto LABEL_92;
        }
        if ( !*(_QWORD *)(v39 + 64) )
        {
LABEL_92:
          if ( v11 || v12 )
          {
            if ( !v6
              || (v40 = *(void **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + v37 + 24) + 32LL) + 8LL) + 8LL)) == 0
              || !EqualSid(v6, v40) )
            {
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v29 = 149;
                goto LABEL_32;
              }
              return v15;
            }
            v10 = v41;
            v8 = v43;
            v7 = v42;
            v6 = v45;
          }
          goto LABEL_103;
        }
LABEL_88:
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v15;
        v29 = 148;
      }
      else
      {
        if ( !*(_QWORD *)(v38 + 56) )
          goto LABEL_83;
LABEL_79:
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v15;
        v29 = 146;
      }
LABEL_32:
      v28 = i;
      goto LABEL_33;
    }
    if ( v11 || v12 || v8 || v10 || v7 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v29 = 150;
        goto LABEL_32;
      }
      return v15;
    }
LABEL_103:
    if ( !*a3 )
      *a3 = **(_DWORD **)(v44 + *(_QWORD *)(a1 + 40) + 24) != 1;
  }
  if ( !v9 )
    goto LABEL_63;
  v34 = *(_QWORD *)(v30 + 32);
  if ( !*(_DWORD *)(v34 + 12)
    && !*(_DWORD *)(v34 + 32)
    && !*(_DWORD *)(v34 + 36)
    && !*(_DWORD *)(v34 + 4)
    && !*(_DWORD *)(v34 + 8)
    && (*(_BYTE *)v34 & 0x40) == 0 )
  {
    goto LABEL_63;
  }
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v29 = 140;
    goto LABEL_32;
  }
  return v15;
}

```

## disassembly

```asm
0x18001d830  push    rbx
0x18001d832  push    rbp
0x18001d833  push    rsi
0x18001d834  push    rdi
0x18001d835  push    r12
0x18001d837  push    r13
0x18001d839  push    r14
0x18001d83b  push    r15
0x18001d83d  sub     rsp, 58h
0x18001d841  mov     rax, [rcx+28h]
0x18001d845  mov     r14, r8
0x18001d848  mov     rsi, rdx
0x18001d84b  xor     r10d, r10d
0x18001d84e  xor     edx, edx
0x18001d850  mov     [rsp+98h+arg_18], r10
0x18001d858  xor     r9d, r9d
0x18001d85b  mov     [rsp+98h+arg_0], edx
0x18001d862  mov     r15, [rax+20h]
0x18001d866  xor     r8d, r8d
0x18001d869  xor     r12d, r12d
0x18001d86c  mov     [rsp+98h+arg_8], r9
0x18001d874  xor     r13b, r13b
0x18001d877  mov     [rsp+98h+var_58], r8
0x18001d87c  cmp     dword ptr [rax+10h], 1
0x18001d880  mov     rdi, rcx
0x18001d883  mov     ebx, 57h ; 'W'
0x18001d888  mov     [r14], dl
0x18001d88b  mov     [rsi], rdx
0x18001d88e  jnz     short loc_18001D8BB
0x18001d890  mov     rbp, [rax+18h]
0x18001d894  test    rbp, rbp
0x18001d897  jz      loc_18001D996
0x18001d89d  test    r15, r15
0x18001d8a0  jz      short loc_18001D8B2
0x18001d8a2  mov     r9d, [r15]
0x18001d8a5  test    r9b, 40h
0x18001d8a9  jnz     loc_18001DA04
0x18001d8af  mov     r9, rdx
0x18001d8b2  mov     rcx, [rbp+20h]
0x18001d8b6  test    rcx, rcx
0x18001d8b9  jnz     short loc_18001D8E1
0x18001d8bb  mov     ebp, 1
0x18001d8c0  movzx   esi, bp
0x18001d8c3  cmp     esi, [rdi+20h]
0x18001d8c6  jb      loc_18001DAEF
0x18001d8cc  xor     ebx, ebx
0x18001d8ce  mov     eax, ebx
0x18001d8d0  add     rsp, 58h
0x18001d8d4  pop     r15
0x18001d8d6  pop     r14
0x18001d8d8  pop     r13
0x18001d8da  pop     r12
0x18001d8dc  pop     rdi
0x18001d8dd  pop     rsi
0x18001d8de  pop     rbp
0x18001d8df  pop     rbx
0x18001d8e0  retn
0x18001d8e1  movzx   eax, byte ptr [rcx+31h]
0x18001d8e5  cmp     al, 2
0x18001d8e7  jnb     loc_18001D9D9
0x18001d8ed  mov     r9, [rcx+28h]
0x18001d8f1  lea     rdx, [rcx+28h]
0x18001d8f5  test    r9, r9
0x18001d8f8  js      loc_18001DA85
0x18001d8fe  cmp     [rcx+30h], r8b
0x18001d902  jnz     short loc_18001D957
0x18001d904  mov     rcx, [rbp+20h]
0x18001d908  mov     rax, [rcx+8]
0x18001d90c  mov     r12, [rcx+28h]
0x18001d910  test    rax, rax
0x18001d913  jz      short loc_18001D991
0x18001d915  mov     r10, [rax+8]
0x18001d919  cmp     dword ptr [rbp+0], 1
0x18001d91d  mov     r9, [rcx+38h]
0x18001d921  mov     r8, [rcx+40h]
0x18001d925  setnz   al
0x18001d928  mov     edx, [rcx+48h]
0x18001d92b  movzx   r13d, byte ptr [rcx+31h]
0x18001d930  mov     [r14], al
0x18001d933  mov     [rsp+98h+arg_18], r10
0x18001d93b  mov     [rsp+98h+arg_8], r9
0x18001d943  mov     [rsp+98h+var_58], r8
0x18001d948  mov     [rsp+98h+arg_0], edx
0x18001d94f  mov     [rsi], rcx
0x18001d952  jmp     loc_18001D8BB
0x18001d957  mov     rcx, [rcx+8]
0x18001d95b  call    UbpmConsumerSetDefaultPrivilegesMask
0x18001d960  test    eax, eax
0x18001d962  jz      short loc_18001D904
0x18001d964  mov     ebx, eax
0x18001d966  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d96d  lea     rdx, WPP_GLOBAL_Control
0x18001d974  cmp     rcx, rdx
0x18001d977  jz      loc_18001D8CE
0x18001d97d  test    byte ptr [rcx+1Ch], 1
0x18001d981  jz      loc_18001D8CE
0x18001d987  mov     edx, 89h
0x18001d98c  jmp     loc_18001DAD2
0x18001d991  xor     r10d, r10d
0x18001d994  jmp     short loc_18001D919
0x18001d996  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d99d  lea     rdx, WPP_GLOBAL_Control
0x18001d9a4  cmp     rcx, rdx
0x18001d9a7  jz      loc_18001D8CE
0x18001d9ad  test    byte ptr [rcx+1Ch], 1
0x18001d9b1  jz      loc_18001D8CE
0x18001d9b7  mov     r9, [rdi+8]
0x18001d9bb  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001d9c2  mov     rcx, [rcx+10h]
0x18001d9c6  mov     edx, 85h
0x18001d9cb  mov     dword ptr [rsp+98h+var_78], ebx
0x18001d9cf  call    WPP_SF_Sd
0x18001d9d4  jmp     loc_18001D8CE
0x18001d9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9e0  lea     rdx, WPP_GLOBAL_Control
0x18001d9e7  cmp     rcx, rdx
0x18001d9ea  jz      loc_18001D8CE
0x18001d9f0  test    byte ptr [rcx+1Ch], 1
0x18001d9f4  jz      loc_18001D8CE
0x18001d9fa  mov     r9d, eax
0x18001d9fd  mov     edx, 87h
0x18001da02  jmp     short loc_18001DA63
0x18001da04  mov     eax, r9d
0x18001da07  and     eax, 180h
0x18001da0c  cmp     eax, 100h
0x18001da11  jnz     loc_18001D8AF
0x18001da17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da1e  lea     rdx, WPP_GLOBAL_Control
0x18001da25  cmp     rcx, rdx
0x18001da28  jz      loc_18001D8CE
0x18001da2e  test    byte ptr [rcx+1Ch], 1
0x18001da32  jz      loc_18001D8CE
0x18001da38  mov     rax, [rdi+8]
0x18001da3c  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001da43  mov     rcx, [rcx+10h]
0x18001da47  mov     edx, 86h
0x18001da4c  mov     [rsp+98h+var_78], rax
0x18001da51  call    WPP_SF_LSd
0x18001da56  jmp     loc_18001D8CE
0x18001da5b  mov     edx, 8Ah
0x18001da60  mov     r9d, esi
0x18001da63  mov     rax, [rdi+8]
0x18001da67  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001da6e  mov     rcx, [rcx+10h]
0x18001da72  mov     dword ptr [rsp+98h+var_70], ebx
0x18001da76  mov     [rsp+98h+var_78], rax
0x18001da7b  call    WPP_SF_dSd
0x18001da80  jmp     loc_18001D8CE
0x18001da85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da8c  lea     rdx, WPP_GLOBAL_Control
0x18001da93  cmp     rcx, rdx
0x18001da96  jz      loc_18001D8CE
0x18001da9c  test    byte ptr [rcx+1Ch], 1
0x18001daa0  jz      loc_18001D8CE
0x18001daa6  mov     rax, [rdi+8]
0x18001daaa  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001dab1  mov     rcx, [rcx+10h]
0x18001dab5  mov     edx, 88h
0x18001daba  mov     dword ptr [rsp+98h+var_70], ebx
0x18001dabe  mov     [rsp+98h+var_78], rax
0x18001dac3  call    WPP_SF_iSd
0x18001dac8  jmp     loc_18001D8CE
0x18001dacd  mov     edx, 8Fh
0x18001dad2  mov     r9, [rdi+8]
0x18001dad6  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001dadd  mov     rcx, [rcx+10h]
0x18001dae1  mov     dword ptr [rsp+98h+var_78], eax
0x18001dae5  call    WPP_SF_Sd
0x18001daea  jmp     loc_18001D8CE
0x18001daef  movzx   eax, bp
0x18001daf2  lea     rcx, [rax+rax*4]
0x18001daf6  mov     rax, [rdi+28h]
0x18001dafa  lea     rcx, ds:0[rcx*8]
0x18001db02  mov     [rsp+98h+arg_10], rcx
0x18001db0a  lea     r11, [rcx+rax]
0x18001db0e  mov     rcx, [rcx+rax+20h]
0x18001db13  mov     [rsp+98h+var_50], r11
0x18001db18  test    rcx, rcx
0x18001db1b  jz      loc_18001DBCC
0x18001db21  test    r15, r15
0x18001db24  jnz     short loc_18001DB73
0x18001db26  cmp     [rcx+0Ch], r15d
0x18001db2a  jnz     short loc_18001DB4D
0x18001db2c  cmp     [rcx+20h], r15d
0x18001db30  jnz     short loc_18001DB4D
0x18001db32  cmp     [rcx+24h], r15d
0x18001db36  jnz     short loc_18001DB4D
0x18001db38  cmp     [rcx+4], r15d
0x18001db3c  jnz     short loc_18001DB4D
0x18001db3e  cmp     [rcx+8], r15d
0x18001db42  jnz     short loc_18001DB4D
0x18001db44  test    byte ptr [rcx], 40h
0x18001db47  jz      loc_18001DC10
0x18001db4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db54  lea     rdx, WPP_GLOBAL_Control
0x18001db5b  cmp     rcx, rdx
0x18001db5e  jz      loc_18001D8CE
0x18001db64  test    byte ptr [rcx+1Ch], 1
0x18001db68  jz      loc_18001D8CE
0x18001db6e  jmp     loc_18001DA5B
0x18001db73  mov     r11, [rax+20h]
0x18001db77  mov     eax, [r11+0Ch]
0x18001db7b  cmp     [rcx+0Ch], eax
0x18001db7e  jnz     loc_18001DEB2
0x18001db84  mov     eax, [r11+20h]
0x18001db88  cmp     [rcx+20h], eax
0x18001db8b  jnz     loc_18001DEB2
0x18001db91  mov     eax, [r11+24h]
0x18001db95  cmp     [rcx+24h], eax
0x18001db98  jnz     loc_18001DEB2
0x18001db9e  mov     eax, [r11+4]
0x18001dba2  cmp     [rcx+4], eax
0x18001dba5  jnz     loc_18001DEB2
0x18001dbab  mov     eax, [r11+8]
0x18001dbaf  cmp     [rcx+8], eax
0x18001dbb2  jnz     loc_18001DEB2
0x18001dbb8  mov     eax, [rcx]
0x18001dbba  xor     eax, [r11]
0x18001dbbd  test    al, 40h
0x18001dbbf  jnz     loc_18001DEB2
0x18001dbc5  mov     r11, [rsp+98h+var_50]
0x18001dbca  jmp     short loc_18001DC10
0x18001dbcc  test    r15, r15
0x18001dbcf  jz      short loc_18001DC10
0x18001dbd1  mov     rax, [rax+20h]
0x18001dbd5  cmp     dword ptr [rax+0Ch], 0
0x18001dbd9  jnz     loc_18001DEDD
0x18001dbdf  cmp     dword ptr [rax+20h], 0
0x18001dbe3  jnz     loc_18001DEDD
0x18001dbe9  cmp     dword ptr [rax+24h], 0
0x18001dbed  jnz     loc_18001DEDD
0x18001dbf3  cmp     dword ptr [rax+4], 0
0x18001dbf7  jnz     loc_18001DEDD
0x18001dbfd  cmp     dword ptr [rax+8], 0
0x18001dc01  jnz     loc_18001DEDD
0x18001dc07  test    byte ptr [rax], 40h
0x18001dc0a  jnz     loc_18001DEDD
0x18001dc10  cmp     dword ptr [r11+10h], 1
0x18001dc15  jnz     loc_18001DEAA
0x18001dc1b  mov     rax, [r11+18h]
0x18001dc1f  mov     [rsp+98h+var_50], rax
0x18001dc24  test    rax, rax
0x18001dc27  jz      loc_18001E049
0x18001dc2d  test    rcx, rcx
0x18001dc30  jz      short loc_18001DC4D
0x18001dc32  mov     r11d, [rcx]
0x18001dc35  mov     eax, r11d
0x18001dc38  and     eax, 1C0h
0x18001dc3d  cmp     eax, 140h
0x18001dc42  jz      loc_18001DF08
0x18001dc48  mov     rax, [rsp+98h+var_50]
0x18001dc4d  mov     rcx, [rax+20h]
0x18001dc51  test    rcx, rcx
0x18001dc54  jz      loc_18001DE5E
0x18001dc5a  cmp     byte ptr [rcx+30h], 0
0x18001dc5e  jz      short loc_18001DC93
0x18001dc60  lea     rdx, [rcx+28h]
0x18001dc64  mov     rcx, [rcx+8]
0x18001dc68  call    UbpmConsumerSetDefaultPrivilegesMask
0x18001dc6d  mov     ebx, eax
0x18001dc6f  test    eax, eax
0x18001dc71  jnz     loc_18001DF4C
0x18001dc77  mov     r8, [rsp+98h+var_58]
0x18001dc7c  mov     r9, [rsp+98h+arg_8]
0x18001dc84  mov     edx, [rsp+98h+arg_0]
0x18001dc8b  mov     r10, [rsp+98h+arg_18]
0x18001dc93  mov     r11, [rdi+28h]
0x18001dc97  mov     rcx, [rsp+98h+arg_10]
0x18001dc9f  mov     rcx, [rcx+r11+18h]
0x18001dca4  mov     rax, [rcx+20h]
0x18001dca8  cmp     r12, [rax+28h]
0x18001dcac  jnz     loc_18001DFF3
0x18001dcb2  cmp     r13b, [rax+31h]
0x18001dcb6  jnz     loc_18001DFF3
0x18001dcbc  cmp     edx, [rax+48h]
0x18001dcbf  jnz     loc_18001DFF3
0x18001dcc5  test    r9, r9
0x18001dcc8  jz      loc_18001DD4E
0x18001dcce  mov     rcx, [rax+38h]
0x18001dcd2  test    rcx, rcx
0x18001dcd5  jz      short loc_18001DD07
0x18001dcd7  mov     rdx, rcx; String2
0x18001dcda  mov     rcx, r9; String1
0x18001dcdd  call    cs:__imp__wcsicmp
0x18001dce3  test    eax, eax
0x18001dce5  jnz     loc_18001DF72
0x18001dceb  mov     r8, [rsp+98h+var_58]
0x18001dcf0  mov     r9, [rsp+98h+arg_8]
0x18001dcf8  mov     edx, [rsp+98h+arg_0]
0x18001dcff  mov     r10, [rsp+98h+arg_18]
0x18001dd07  mov     r11, [rdi+28h]
0x18001dd0b  mov     rax, [rsp+98h+arg_10]
0x18001dd13  mov     rax, [rax+r11+18h]
0x18001dd18  mov     rcx, [rax+20h]
0x18001dd1c  cmp     qword ptr [rcx+38h], 0
0x18001dd21  jnz     short loc_18001DD55
0x18001dd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd2a  lea     rdx, WPP_GLOBAL_Control
0x18001dd31  cmp     rcx, rdx
0x18001dd34  jz      loc_18001D8CE
  ... truncated ...
```
