# UbpmpValidateCommonActionParameters

- ea: `0x180019d70`
- end: `0x18001a5e3`
- name: `UbpmpValidateCommonActionParameters`
- size: `2163`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800192f0`

## callees

- `0x180019d70`
- `0x18001aef0`
- `0x18001af64`
- `0x180032e70`
- `0x180037508`
- `0x180037b50`
- `0x180037c0c`
- `0x180037d54`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a21e`
- `msvcrt!_wcsicmp` at `0x18001a2c5`
- `msvcrt!_wcsicmp` at `0x18001a21e`
- `msvcrt!_wcsicmp` at `0x18001a2c5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a37f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a37f`

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
        v24 = UbpmConsumerSetDefaultPrivilegesMask(*(_QWORD *)(v17 + 8), (_QWORD *)(v17 + 40));
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
        v24 = UbpmConsumerSetDefaultPrivilegesMask(*(_QWORD *)(v36 + 8), (_QWORD *)(v36 + 40));
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
0x180019d70  push    rbx
0x180019d72  push    rbp
0x180019d73  push    rsi
0x180019d74  push    rdi
0x180019d75  push    r12
0x180019d77  push    r13
0x180019d79  push    r14
0x180019d7b  push    r15
0x180019d7d  sub     rsp, 58h
0x180019d81  mov     rax, [rcx+28h]
0x180019d85  mov     r14, r8
0x180019d88  mov     rsi, rdx
0x180019d8b  xor     r10d, r10d
0x180019d8e  xor     edx, edx
0x180019d90  mov     [rsp+98h+arg_18], r10
0x180019d98  xor     r9d, r9d
0x180019d9b  mov     [rsp+98h+arg_0], edx
0x180019da2  mov     r15, [rax+20h]
0x180019da6  xor     r8d, r8d
0x180019da9  xor     r12d, r12d
0x180019dac  mov     [rsp+98h+arg_8], r9
0x180019db4  xor     r13b, r13b
0x180019db7  mov     [rsp+98h+var_58], r8
0x180019dbc  cmp     dword ptr [rax+10h], 1
0x180019dc0  mov     rdi, rcx
0x180019dc3  mov     ebx, 57h ; 'W'
0x180019dc8  mov     [r14], dl
0x180019dcb  mov     [rsi], rdx
0x180019dce  jnz     short loc_180019DFB
0x180019dd0  mov     rbp, [rax+18h]
0x180019dd4  test    rbp, rbp
0x180019dd7  jz      loc_180019ED7
0x180019ddd  test    r15, r15
0x180019de0  jz      short loc_180019DF2
0x180019de2  mov     r9d, [r15]
0x180019de5  test    r9b, 40h
0x180019de9  jnz     loc_180019F45
0x180019def  mov     r9, rdx
0x180019df2  mov     rcx, [rbp+20h]
0x180019df6  test    rcx, rcx
0x180019df9  jnz     short loc_180019E22
0x180019dfb  mov     ebp, 1
0x180019e00  movzx   esi, bp
0x180019e03  cmp     esi, [rdi+20h]
0x180019e06  jb      loc_18001A030
0x180019e0c  xor     ebx, ebx
0x180019e0e  mov     eax, ebx
0x180019e10  add     rsp, 58h
0x180019e14  pop     r15
0x180019e16  pop     r14
0x180019e18  pop     r13
0x180019e1a  pop     r12
0x180019e1c  pop     rdi
0x180019e1d  pop     rsi
0x180019e1e  pop     rbp
0x180019e1f  pop     rbx
0x180019e20  retn
0x180019e22  movzx   eax, byte ptr [rcx+31h]
0x180019e26  cmp     al, 2
0x180019e28  jnb     loc_180019F1A
0x180019e2e  mov     r9, [rcx+28h]
0x180019e32  lea     rdx, [rcx+28h]
0x180019e36  test    r9, r9
0x180019e39  js      loc_180019FC6
0x180019e3f  cmp     [rcx+30h], r8b
0x180019e43  jnz     short loc_180019E98
0x180019e45  mov     rcx, [rbp+20h]
0x180019e49  mov     rax, [rcx+8]
0x180019e4d  mov     r12, [rcx+28h]
0x180019e51  test    rax, rax
0x180019e54  jz      short loc_180019ED2
0x180019e56  mov     r10, [rax+8]
0x180019e5a  cmp     dword ptr [rbp+0], 1
0x180019e5e  mov     r9, [rcx+38h]
0x180019e62  mov     r8, [rcx+40h]
0x180019e66  setnz   al
0x180019e69  mov     edx, [rcx+48h]
0x180019e6c  movzx   r13d, byte ptr [rcx+31h]
0x180019e71  mov     [r14], al
0x180019e74  mov     [rsp+98h+arg_18], r10
0x180019e7c  mov     [rsp+98h+arg_8], r9
0x180019e84  mov     [rsp+98h+var_58], r8
0x180019e89  mov     [rsp+98h+arg_0], edx
0x180019e90  mov     [rsi], rcx
0x180019e93  jmp     loc_180019DFB
0x180019e98  mov     rcx, [rcx+8]
0x180019e9c  call    UbpmConsumerSetDefaultPrivilegesMask
0x180019ea1  test    eax, eax
0x180019ea3  jz      short loc_180019E45
0x180019ea5  mov     ebx, eax
0x180019ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180019eae  lea     rdx, WPP_GLOBAL_Control
0x180019eb5  cmp     rcx, rdx
0x180019eb8  jz      loc_180019E0E
0x180019ebe  test    byte ptr [rcx+1Ch], 1
0x180019ec2  jz      loc_180019E0E
0x180019ec8  mov     edx, 89h
0x180019ecd  jmp     loc_18001A013
0x180019ed2  xor     r10d, r10d
0x180019ed5  jmp     short loc_180019E5A
0x180019ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ede  lea     rdx, WPP_GLOBAL_Control
0x180019ee5  cmp     rcx, rdx
0x180019ee8  jz      loc_180019E0E
0x180019eee  test    byte ptr [rcx+1Ch], 1
0x180019ef2  jz      loc_180019E0E
0x180019ef8  mov     r9, [rdi+8]
0x180019efc  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180019f03  mov     rcx, [rcx+10h]
0x180019f07  mov     edx, 85h
0x180019f0c  mov     dword ptr [rsp+98h+var_78], ebx
0x180019f10  call    WPP_SF_Sd
0x180019f15  jmp     loc_180019E0E
0x180019f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f21  lea     rdx, WPP_GLOBAL_Control
0x180019f28  cmp     rcx, rdx
0x180019f2b  jz      loc_180019E0E
0x180019f31  test    byte ptr [rcx+1Ch], 1
0x180019f35  jz      loc_180019E0E
0x180019f3b  mov     r9d, eax
0x180019f3e  mov     edx, 87h
0x180019f43  jmp     short loc_180019FA4
0x180019f45  mov     eax, r9d
0x180019f48  and     eax, 180h
0x180019f4d  cmp     eax, 100h
0x180019f52  jnz     loc_180019DEF
0x180019f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f5f  lea     rdx, WPP_GLOBAL_Control
0x180019f66  cmp     rcx, rdx
0x180019f69  jz      loc_180019E0E
0x180019f6f  test    byte ptr [rcx+1Ch], 1
0x180019f73  jz      loc_180019E0E
0x180019f79  mov     rax, [rdi+8]
0x180019f7d  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180019f84  mov     rcx, [rcx+10h]
0x180019f88  mov     edx, 86h
0x180019f8d  mov     [rsp+98h+var_78], rax
0x180019f92  call    WPP_SF_LSd
0x180019f97  jmp     loc_180019E0E
0x180019f9c  mov     edx, 8Ah
0x180019fa1  mov     r9d, esi
0x180019fa4  mov     rax, [rdi+8]
0x180019fa8  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180019faf  mov     rcx, [rcx+10h]
0x180019fb3  mov     dword ptr [rsp+98h+var_70], ebx
0x180019fb7  mov     [rsp+98h+var_78], rax
0x180019fbc  call    WPP_SF_dSd
0x180019fc1  jmp     loc_180019E0E
0x180019fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fcd  lea     rdx, WPP_GLOBAL_Control
0x180019fd4  cmp     rcx, rdx
0x180019fd7  jz      loc_180019E0E
0x180019fdd  test    byte ptr [rcx+1Ch], 1
0x180019fe1  jz      loc_180019E0E
0x180019fe7  mov     rax, [rdi+8]
0x180019feb  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180019ff2  mov     rcx, [rcx+10h]
0x180019ff6  mov     edx, 88h
0x180019ffb  mov     dword ptr [rsp+98h+var_70], ebx
0x180019fff  mov     [rsp+98h+var_78], rax
0x18001a004  call    WPP_SF_iSd
0x18001a009  jmp     loc_180019E0E
0x18001a00e  mov     edx, 8Fh
0x18001a013  mov     r9, [rdi+8]
0x18001a017  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001a01e  mov     rcx, [rcx+10h]
0x18001a022  mov     dword ptr [rsp+98h+var_78], eax
0x18001a026  call    WPP_SF_Sd
0x18001a02b  jmp     loc_180019E0E
0x18001a030  movzx   eax, bp
0x18001a033  lea     rcx, [rax+rax*4]
0x18001a037  mov     rax, [rdi+28h]
0x18001a03b  lea     rcx, ds:0[rcx*8]
0x18001a043  mov     [rsp+98h+arg_10], rcx
0x18001a04b  lea     r11, [rcx+rax]
0x18001a04f  mov     rcx, [rcx+rax+20h]
0x18001a054  mov     [rsp+98h+var_50], r11
0x18001a059  test    rcx, rcx
0x18001a05c  jz      loc_18001A10D
0x18001a062  test    r15, r15
0x18001a065  jnz     short loc_18001A0B4
0x18001a067  cmp     [rcx+0Ch], r15d
0x18001a06b  jnz     short loc_18001A08E
0x18001a06d  cmp     [rcx+20h], r15d
0x18001a071  jnz     short loc_18001A08E
0x18001a073  cmp     [rcx+24h], r15d
0x18001a077  jnz     short loc_18001A08E
0x18001a079  cmp     [rcx+4], r15d
0x18001a07d  jnz     short loc_18001A08E
0x18001a07f  cmp     [rcx+8], r15d
0x18001a083  jnz     short loc_18001A08E
0x18001a085  test    byte ptr [rcx], 40h
0x18001a088  jz      loc_18001A151
0x18001a08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a095  lea     rdx, WPP_GLOBAL_Control
0x18001a09c  cmp     rcx, rdx
0x18001a09f  jz      loc_180019E0E
0x18001a0a5  test    byte ptr [rcx+1Ch], 1
0x18001a0a9  jz      loc_180019E0E
0x18001a0af  jmp     loc_180019F9C
0x18001a0b4  mov     r11, [rax+20h]
0x18001a0b8  mov     eax, [r11+0Ch]
0x18001a0bc  cmp     [rcx+0Ch], eax
0x18001a0bf  jnz     loc_18001A405
0x18001a0c5  mov     eax, [r11+20h]
0x18001a0c9  cmp     [rcx+20h], eax
0x18001a0cc  jnz     loc_18001A405
0x18001a0d2  mov     eax, [r11+24h]
0x18001a0d6  cmp     [rcx+24h], eax
0x18001a0d9  jnz     loc_18001A405
0x18001a0df  mov     eax, [r11+4]
0x18001a0e3  cmp     [rcx+4], eax
0x18001a0e6  jnz     loc_18001A405
0x18001a0ec  mov     eax, [r11+8]
0x18001a0f0  cmp     [rcx+8], eax
0x18001a0f3  jnz     loc_18001A405
0x18001a0f9  mov     eax, [rcx]
0x18001a0fb  xor     eax, [r11]
0x18001a0fe  test    al, 40h
0x18001a100  jnz     loc_18001A405
0x18001a106  mov     r11, [rsp+98h+var_50]
0x18001a10b  jmp     short loc_18001A151
0x18001a10d  test    r15, r15
0x18001a110  jz      short loc_18001A151
0x18001a112  mov     rax, [rax+20h]
0x18001a116  cmp     dword ptr [rax+0Ch], 0
0x18001a11a  jnz     loc_18001A430
0x18001a120  cmp     dword ptr [rax+20h], 0
0x18001a124  jnz     loc_18001A430
0x18001a12a  cmp     dword ptr [rax+24h], 0
0x18001a12e  jnz     loc_18001A430
0x18001a134  cmp     dword ptr [rax+4], 0
0x18001a138  jnz     loc_18001A430
0x18001a13e  cmp     dword ptr [rax+8], 0
0x18001a142  jnz     loc_18001A430
0x18001a148  test    byte ptr [rax], 40h
0x18001a14b  jnz     loc_18001A430
0x18001a151  cmp     dword ptr [r11+10h], 1
0x18001a156  jnz     loc_18001A3FD
0x18001a15c  mov     rax, [r11+18h]
0x18001a160  mov     [rsp+98h+var_50], rax
0x18001a165  test    rax, rax
0x18001a168  jz      loc_18001A59C
0x18001a16e  test    rcx, rcx
0x18001a171  jz      short loc_18001A18E
0x18001a173  mov     r11d, [rcx]
0x18001a176  mov     eax, r11d
0x18001a179  and     eax, 1C0h
0x18001a17e  cmp     eax, 140h
0x18001a183  jz      loc_18001A45B
0x18001a189  mov     rax, [rsp+98h+var_50]
0x18001a18e  mov     rcx, [rax+20h]
0x18001a192  test    rcx, rcx
0x18001a195  jz      loc_18001A3B1
0x18001a19b  cmp     byte ptr [rcx+30h], 0
0x18001a19f  jz      short loc_18001A1D4
0x18001a1a1  lea     rdx, [rcx+28h]
0x18001a1a5  mov     rcx, [rcx+8]
0x18001a1a9  call    UbpmConsumerSetDefaultPrivilegesMask
0x18001a1ae  mov     ebx, eax
0x18001a1b0  test    eax, eax
0x18001a1b2  jnz     loc_18001A49F
0x18001a1b8  mov     r8, [rsp+98h+var_58]
0x18001a1bd  mov     r9, [rsp+98h+arg_8]
0x18001a1c5  mov     edx, [rsp+98h+arg_0]
0x18001a1cc  mov     r10, [rsp+98h+arg_18]
0x18001a1d4  mov     r11, [rdi+28h]
0x18001a1d8  mov     rcx, [rsp+98h+arg_10]
0x18001a1e0  mov     rcx, [rcx+r11+18h]
0x18001a1e5  mov     rax, [rcx+20h]
0x18001a1e9  cmp     r12, [rax+28h]
0x18001a1ed  jnz     loc_18001A546
0x18001a1f3  cmp     r13b, [rax+31h]
0x18001a1f7  jnz     loc_18001A546
0x18001a1fd  cmp     edx, [rax+48h]
0x18001a200  jnz     loc_18001A546
0x18001a206  test    r9, r9
0x18001a209  jz      loc_18001A295
0x18001a20f  mov     rcx, [rax+38h]
0x18001a213  test    rcx, rcx
0x18001a216  jz      short loc_18001A24E
0x18001a218  mov     rdx, rcx; String2
0x18001a21b  mov     rcx, r9; String1
0x18001a21e  call    cs:__imp__wcsicmp
0x18001a225  nop     dword ptr [rax+rax+00h]
0x18001a22a  test    eax, eax
0x18001a22c  jnz     loc_18001A4C5
0x18001a232  mov     r8, [rsp+98h+var_58]
0x18001a237  mov     r9, [rsp+98h+arg_8]
0x18001a23f  mov     edx, [rsp+98h+arg_0]
0x18001a246  mov     r10, [rsp+98h+arg_18]
0x18001a24e  mov     r11, [rdi+28h]
0x18001a252  mov     rax, [rsp+98h+arg_10]
0x18001a25a  mov     rax, [rax+r11+18h]
0x18001a25f  mov     rcx, [rax+20h]
0x18001a263  cmp     qword ptr [rcx+38h], 0
0x18001a268  jnz     short loc_18001A29C
0x18001a26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a271  lea     rdx, WPP_GLOBAL_Control
0x18001a278  cmp     rcx, rdx
  ... truncated ...
```
