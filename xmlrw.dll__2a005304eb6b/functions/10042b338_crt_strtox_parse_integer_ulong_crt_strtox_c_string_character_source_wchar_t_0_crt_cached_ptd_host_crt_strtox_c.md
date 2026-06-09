# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x10042b338`
- end: `0x10042baad`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1909`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10042c5c0`

## callees

- `0x10042b338`
- `0x10042e504`
- `0x10042e5d8`
- `0x10042e738`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(
        __crt_cached_ptd_host *a1,
        __int16 **a2,
        unsigned int a3,
        unsigned __int8 a4)
{
  __int16 *v4; // r12
  unsigned int v5; // r15d
  __int16 *v7; // rcx
  unsigned __int16 v8; // bx
  unsigned int v9; // r14d
  int v10; // esi
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  __int16 *v15; // rcx
  __int16 v16; // dx
  __int16 *v17; // r8
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r9d
  unsigned int v21; // ecx
  int v22; // eax
  int v23; // ecx
  __int16 *v24; // r8
  unsigned int v25; // edx
  BOOL v26; // ecx
  bool v27; // cf
  bool v28; // zf
  __int16 *v29; // rax
  int v31; // eax
  int v32; // ecx
  __int16 *v33; // rdx
  __int16 *v34; // rdx
  __int16 *v35; // [rsp+98h] [rbp-40h]

  v4 = *a2;
  v35 = *a2;
  v5 = a3;
  if ( !*a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a1);
LABEL_6:
    v7 = a2[1];
    if ( v7 )
      *(_QWORD *)v7 = *a2;
    return 0;
  }
  v8 = *v4;
  v9 = 0;
  *a2 = v4 + 1;
  v10 = a4 | 2;
  if ( v8 != 45 )
    v10 = a4;
  if ( ((v8 - 43) & 0xFFFD) == 0 )
  {
    v8 = v4[1];
    *a2 = v4 + 2;
  }
  v11 = 48;
  if ( (a3 & 0xFFFFFFEF) != 0 )
    goto LABEL_73;
  if ( v8 >= 0x30u )
  {
    if ( v8 < 0x3Au )
    {
LABEL_15:
      v12 = v8 - v11;
      goto LABEL_55;
    }
    if ( v8 >= 0xFF10u )
    {
      if ( v8 < 0xFF1Au )
      {
        v12 = v8 - 65296;
LABEL_55:
        if ( v12 != -1 )
          goto LABEL_61;
      }
    }
    else if ( v8 >= 0x660u )
    {
      if ( v8 < 0x66Au )
      {
        v12 = v8 - 1632;
        goto LABEL_55;
      }
      if ( v8 >= 0x6F0u )
      {
        if ( v8 < 0x6FAu )
        {
          v12 = v8 - 1776;
          goto LABEL_55;
        }
        if ( v8 >= 0x966u )
        {
          if ( v8 < 0x970u )
          {
            v12 = v8 - 2406;
            goto LABEL_55;
          }
          if ( v8 >= 0x9E6u )
          {
            if ( v8 < 0x9F0u )
            {
              v12 = v8 - 2534;
              goto LABEL_55;
            }
            v11 = 2662;
            if ( v8 >= 0xA66u )
            {
              if ( v8 < 0xA70u )
                goto LABEL_15;
              v11 = 2790;
              if ( v8 >= 0xAE6u )
              {
                if ( v8 < 0xAF0u )
                  goto LABEL_15;
                v11 = 2918;
                if ( v8 >= 0xB66u )
                {
                  if ( v8 < 0xB70u )
                    goto LABEL_15;
                  v11 = 3174;
                  if ( v8 >= 0xC66u )
                  {
                    if ( v8 < 0xC70u )
                      goto LABEL_15;
                    v11 = 3302;
                    if ( v8 >= 0xCE6u )
                    {
                      if ( v8 < 0xCF0u )
                        goto LABEL_15;
                      v11 = 3430;
                      if ( v8 >= 0xD66u )
                      {
                        if ( v8 < 0xD70u )
                          goto LABEL_15;
                        v11 = 3664;
                        if ( v8 >= 0xE50u )
                        {
                          if ( v8 < 0xE5Au )
                            goto LABEL_15;
                          v11 = 3792;
                          if ( v8 >= 0xED0u )
                          {
                            if ( v8 < 0xEDAu )
                              goto LABEL_15;
                            v11 = 3872;
                            if ( v8 >= 0xF20u )
                            {
                              if ( v8 < 0xF2Au )
                                goto LABEL_15;
                              v11 = 4160;
                              if ( v8 >= 0x1040u )
                              {
                                if ( v8 < 0x104Au )
                                  goto LABEL_15;
                                v11 = 6112;
                                if ( v8 >= 0x17E0u )
                                {
                                  if ( v8 < 0x17EAu )
                                    goto LABEL_15;
                                  v11 = 6160;
                                  if ( (unsigned __int16)(v8 - 6160) <= 9u )
                                    goto LABEL_15;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v13 = v8;
  v14 = v8 - 97;
  if ( (unsigned int)v8 - 65 > 0x19 && v14 > 0x19 )
    goto LABEL_69;
  if ( v14 <= 0x19 )
    v13 = v8 - 32;
  v12 = v13 - 55;
LABEL_61:
  if ( v12 )
  {
LABEL_69:
    v19 = 10;
    goto LABEL_70;
  }
  v15 = *a2;
  v16 = **a2;
  v17 = *a2 + 1;
  *a2 = v17;
  if ( ((v16 - 88) & 0xFFDF) == 0 )
  {
    v8 = *v17;
    *a2 = v17 + 1;
    v19 = 16;
LABEL_70:
    if ( v5 )
      v19 = v5;
    v5 = v19;
    goto LABEL_73;
  }
  *a2 = v15;
  v18 = 8;
  if ( v5 )
    v18 = v5;
  v5 = v18;
  if ( v16 && *v15 != v16 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_73:
  v20 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( v8 >= 0x30u )
    {
      if ( v8 < 0x3Au )
      {
        v21 = v8 - 48;
        goto LABEL_114;
      }
      if ( v8 >= 0xFF10u )
      {
        if ( v8 < 0xFF1Au )
        {
          v21 = v8 - 65296;
LABEL_114:
          if ( v21 != -1 )
            goto LABEL_123;
        }
      }
      else if ( v8 >= 0x660u )
      {
        if ( v8 < 0x66Au )
        {
          v21 = v8 - 1632;
          goto LABEL_114;
        }
        v22 = 1776;
        if ( v8 >= 0x6F0u )
        {
          if ( v8 < 0x6FAu )
            goto LABEL_83;
          v22 = 2406;
          if ( v8 >= 0x966u )
          {
            if ( v8 < 0x970u )
              goto LABEL_83;
            v22 = 2534;
            if ( v8 >= 0x9E6u )
            {
              if ( v8 < 0x9F0u )
                goto LABEL_83;
              v22 = 2662;
              if ( v8 >= 0xA66u )
              {
                if ( v8 < 0xA70u )
                  goto LABEL_83;
                v22 = 2790;
                if ( v8 >= 0xAE6u )
                {
                  if ( v8 < 0xAF0u )
                    goto LABEL_83;
                  v22 = 2918;
                  if ( v8 >= 0xB66u )
                  {
                    if ( v8 < 0xB70u )
                      goto LABEL_83;
                    v22 = 3174;
                    if ( v8 >= 0xC66u )
                    {
                      if ( v8 < 0xC70u )
                        goto LABEL_83;
                      v22 = 3302;
                      if ( v8 >= 0xCE6u )
                      {
                        if ( v8 < 0xCF0u )
                          goto LABEL_83;
                        v22 = 3430;
                        if ( v8 >= 0xD66u )
                        {
                          if ( v8 < 0xD70u )
                            goto LABEL_83;
                          v22 = 3664;
                          if ( v8 >= 0xE50u )
                          {
                            if ( v8 < 0xE5Au )
                              goto LABEL_83;
                            v22 = 3792;
                            if ( v8 >= 0xED0u )
                            {
                              if ( v8 < 0xEDAu )
                                goto LABEL_83;
                              v22 = 3872;
                              if ( v8 >= 0xF20u )
                              {
                                if ( v8 < 0xF2Au )
                                  goto LABEL_83;
                                v22 = 4160;
                                if ( v8 >= 0x1040u )
                                {
                                  if ( v8 < 0x104Au )
                                    goto LABEL_83;
                                  v22 = 6112;
                                  if ( v8 >= 0x17E0u )
                                  {
                                    if ( v8 < 0x17EAu )
                                    {
LABEL_83:
                                      v21 = v8 - v22;
                                      goto LABEL_114;
                                    }
                                    if ( (unsigned __int16)(v8 - 6160) <= 9u )
                                    {
                                      v21 = v8 - 6160;
                                      goto LABEL_114;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( ((v23 = v8, v8 < 0x41u) || v8 > 0x5Au) && (v8 < 0x61u || v8 > 0x7Au) )
    {
      v21 = -1;
    }
    else
    {
      if ( (unsigned __int16)(v8 - 97) <= 0x19u )
        v23 = v8 - 32;
      v21 = v23 - 55;
    }
LABEL_123:
    v24 = *a2;
    if ( v21 >= v5 )
      break;
    v8 = *v24;
    v25 = v5 * v9 + v21;
    v26 = v25 < v5 * v9;
    v27 = v9 < v20;
    v28 = v9 == v20;
    v9 = v25;
    *a2 = v24 + 1;
    v10 |= (4 * (!v27 && !v28 || v26)) | 8;
  }
  *a2 = v24 - 1;
  if ( v8 && *(v24 - 1) != v8 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v10 & 8) != 0 )
  {
    if ( (v10 & 4) != 0 )
    {
      v31 = 1;
      v32 = v10;
LABEL_140:
      *((_BYTE *)a1 + 48) = 1;
      *((_DWORD *)a1 + 11) = 34;
      if ( (v32 & v31) != 0 )
      {
        v33 = a2[1];
        if ( (v10 & 2) != 0 )
        {
          if ( v33 )
            *(_QWORD *)v33 = *a2;
          return 0x80000000LL;
        }
        else
        {
          if ( v33 )
            *(_QWORD *)v33 = *a2;
          return 0x7FFFFFFF;
        }
      }
      v9 = -1;
LABEL_151:
      v34 = a2[1];
      if ( v34 )
        *(_QWORD *)v34 = *a2;
      return v9;
    }
    if ( (v10 & 1) != 0 )
    {
      if ( (v10 & 2) == 0 )
      {
        if ( v9 <= 0x7FFFFFFF )
          goto LABEL_151;
        goto LABEL_139;
      }
      if ( v9 > 0x80000000 )
      {
LABEL_139:
        v32 = 1;
        v31 = v10;
        goto LABEL_140;
      }
    }
    else if ( (v10 & 2) == 0 )
    {
      goto LABEL_151;
    }
    v9 = -v9;
    goto LABEL_151;
  }
  v29 = a2[1];
  *a2 = v35;
  if ( v29 )
    *(_QWORD *)v29 = v35;
  return 0;
}

```

## disassembly

```asm
0x10042b338  mov     [rsp+arg_10], rbx
0x10042b33d  mov     [rsp+arg_0], rcx
0x10042b342  push    rbp
0x10042b343  push    rsi
0x10042b344  push    rdi
0x10042b345  push    r12
0x10042b347  push    r13
0x10042b349  push    r14
0x10042b34b  push    r15
0x10042b34d  sub     rsp, 0A0h
0x10042b354  mov     r12, [rdx]
0x10042b357  xor     r10d, r10d
0x10042b35a  mov     [rsp+0D8h+var_40], r12
0x10042b362  mov     r15d, r8d
0x10042b365  mov     rdi, rdx
0x10042b368  test    r12, r12
0x10042b36b  jnz     short loc_10042B37F
0x10042b36d  call    _errno
0x10042b372  mov     dword ptr [rax], 16h
0x10042b378  call    _invalid_parameter_noinfo
0x10042b37d  jmp     short loc_10042B3B1
0x10042b37f  test    r15d, r15d
0x10042b382  jz      short loc_10042B3C9
0x10042b384  lea     eax, [r8-2]
0x10042b388  cmp     eax, 22h ; '"'
0x10042b38b  jbe     short loc_10042B3C9
0x10042b38d  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x10042b392  xor     r9d, r9d; LineNo
0x10042b395  mov     byte ptr [rcx+30h], 1
0x10042b399  xor     r8d, r8d; FileName
0x10042b39c  mov     dword ptr [rcx+2Ch], 16h
0x10042b3a3  xor     edx, edx; FunctionName
0x10042b3a5  xor     ecx, ecx; Expression
0x10042b3a7  mov     [rsp+0D8h+var_B8], r10; uintptr_t
0x10042b3ac  call    _invalid_parameter_internal
0x10042b3b1  mov     rcx, [rdi+8]
0x10042b3b5  test    rcx, rcx
0x10042b3b8  jz      loc_10042B9F9
0x10042b3be  mov     rax, [rdi]
0x10042b3c1  mov     [rcx], rax
0x10042b3c4  jmp     loc_10042B9F9
0x10042b3c9  movzx   ebx, word ptr [r12]
0x10042b3ce  lea     rcx, [r12+2]
0x10042b3d3  movzx   eax, r9b
0x10042b3d7  mov     r14d, r10d
0x10042b3da  mov     esi, eax
0x10042b3dc  mov     [rdx], rcx
0x10042b3df  or      esi, 2
0x10042b3e2  mov     edx, 0FFFDh
0x10042b3e7  cmp     bx, 2Dh ; '-'
0x10042b3eb  cmovnz  esi, eax
0x10042b3ee  lea     eax, [rbx-2Bh]
0x10042b3f1  test    dx, ax
0x10042b3f4  jnz     short loc_10042B400
0x10042b3f6  movzx   ebx, word ptr [rcx]
0x10042b3f9  lea     rax, [rcx+2]
0x10042b3fd  mov     [rdi], rax
0x10042b400  mov     [rsp+0D8h+arg_8], 9F0h
0x10042b40b  mov     eax, 9E6h
0x10042b410  mov     [rsp+0D8h+var_A8], 0A66h
0x10042b418  mov     ecx, 30h ; '0'
0x10042b41d  mov     [rsp+0D8h+var_A4], 0A70h
0x10042b425  mov     edx, 0FF10h
0x10042b42a  mov     [rsp+0D8h+var_A0], 0AE6h
0x10042b432  mov     r8d, 660h
0x10042b438  mov     [rsp+0D8h+var_9C], 0AF0h
0x10042b440  lea     r11d, [rax-80h]
0x10042b444  mov     [rsp+0D8h+var_98], 0B66h
0x10042b44c  mov     r9d, 6F0h
0x10042b452  mov     [rsp+0D8h+var_94], 0B70h
0x10042b45a  mov     [rsp+0D8h+var_90], 0C66h
0x10042b462  mov     [rsp+0D8h+var_8C], 0C70h
0x10042b46a  mov     [rsp+0D8h+var_88], 0CE6h
0x10042b472  mov     [rsp+0D8h+var_84], 0CF0h
0x10042b47a  mov     [rsp+0D8h+var_80], 0D66h
0x10042b482  mov     [rsp+0D8h+var_7C], 0D70h
0x10042b48a  mov     [rsp+0D8h+var_78], 0E50h
0x10042b492  mov     [rsp+0D8h+var_74], 0E5Ah
0x10042b49a  mov     [rsp+0D8h+var_70], 0ED0h
0x10042b4a2  mov     [rsp+0D8h+var_6C], 0EDAh
0x10042b4aa  mov     [rsp+0D8h+var_68], 0F20h
0x10042b4b2  mov     [rsp+0D8h+var_64], 0F2Ah
0x10042b4ba  mov     [rsp+0D8h+var_60], 1040h
0x10042b4c2  mov     [rsp+0D8h+var_5C], 104Ah
0x10042b4ca  mov     [rsp+0D8h+var_58], 17E0h
0x10042b4d5  mov     [rsp+0D8h+var_54], 17EAh
0x10042b4e0  mov     [rsp+0D8h+var_50], 1810h
0x10042b4eb  mov     [rsp+0D8h+var_4C], 0FF1Ah
0x10042b4f6  mov     [rsp+0D8h+var_48], 19h
0x10042b501  test    r15d, 0FFFFFFEFh
0x10042b508  jnz     loc_10042B76B
0x10042b50e  cmp     bx, cx
0x10042b511  jb      loc_10042B6D7
0x10042b517  cmp     bx, 3Ah ; ':'
0x10042b51b  jnb     short loc_10042B527
0x10042b51d  movzx   eax, bx
0x10042b520  sub     eax, ecx
0x10042b522  jmp     loc_10042B6D2
0x10042b527  cmp     bx, dx
0x10042b52a  jnb     loc_10042B6C3
0x10042b530  cmp     bx, r8w
0x10042b534  jb      loc_10042B6D7
0x10042b53a  mov     ecx, 66Ah
0x10042b53f  cmp     bx, cx
0x10042b542  jnb     short loc_10042B54F
0x10042b544  movzx   eax, bx
0x10042b547  sub     eax, r8d
0x10042b54a  jmp     loc_10042B6D2
0x10042b54f  cmp     bx, r9w
0x10042b553  jb      loc_10042B6D7
0x10042b559  mov     ecx, 6FAh
0x10042b55e  cmp     bx, cx
0x10042b561  jnb     short loc_10042B56E
0x10042b563  movzx   eax, bx
0x10042b566  sub     eax, r9d
0x10042b569  jmp     loc_10042B6D2
0x10042b56e  cmp     bx, r11w
0x10042b572  jb      loc_10042B6D7
0x10042b578  mov     ecx, 970h
0x10042b57d  cmp     bx, cx
0x10042b580  jnb     short loc_10042B58D
0x10042b582  movzx   eax, bx
0x10042b585  sub     eax, r11d
0x10042b588  jmp     loc_10042B6D2
0x10042b58d  cmp     bx, ax
0x10042b590  jb      loc_10042B6D7
0x10042b596  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x10042b59e  jnb     short loc_10042B5AD
0x10042b5a0  movzx   eax, bx
0x10042b5a3  sub     eax, 9E6h
0x10042b5a8  jmp     loc_10042B6D2
0x10042b5ad  mov     ecx, [rsp+0D8h+var_A8]
0x10042b5b1  cmp     bx, cx
0x10042b5b4  jb      loc_10042B6D7
0x10042b5ba  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x10042b5bf  jb      loc_10042B51D
0x10042b5c5  mov     ecx, [rsp+0D8h+var_A0]
0x10042b5c9  cmp     bx, cx
0x10042b5cc  jb      loc_10042B6D7
0x10042b5d2  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x10042b5d7  jb      loc_10042B51D
0x10042b5dd  mov     ecx, [rsp+0D8h+var_98]
0x10042b5e1  cmp     bx, cx
0x10042b5e4  jb      loc_10042B6D7
0x10042b5ea  cmp     bx, word ptr [rsp+0D8h+var_94]
0x10042b5ef  jb      loc_10042B51D
0x10042b5f5  mov     ecx, [rsp+0D8h+var_90]
0x10042b5f9  cmp     bx, cx
0x10042b5fc  jb      loc_10042B6D7
0x10042b602  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x10042b607  jb      loc_10042B51D
0x10042b60d  mov     ecx, [rsp+0D8h+var_88]
0x10042b611  cmp     bx, cx
0x10042b614  jb      loc_10042B6D7
0x10042b61a  cmp     bx, word ptr [rsp+0D8h+var_84]
0x10042b61f  jb      loc_10042B51D
0x10042b625  mov     ecx, [rsp+0D8h+var_80]
0x10042b629  cmp     bx, cx
0x10042b62c  jb      loc_10042B6D7
0x10042b632  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x10042b637  jb      loc_10042B51D
0x10042b63d  mov     ecx, [rsp+0D8h+var_78]
0x10042b641  cmp     bx, cx
0x10042b644  jb      loc_10042B6D7
0x10042b64a  cmp     bx, word ptr [rsp+0D8h+var_74]
0x10042b64f  jb      loc_10042B51D
0x10042b655  mov     ecx, [rsp+0D8h+var_70]
0x10042b659  cmp     bx, cx
0x10042b65c  jb      short loc_10042B6D7
0x10042b65e  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x10042b663  jb      loc_10042B51D
0x10042b669  mov     ecx, [rsp+0D8h+var_68]
0x10042b66d  cmp     bx, cx
0x10042b670  jb      short loc_10042B6D7
0x10042b672  cmp     bx, word ptr [rsp+0D8h+var_64]
0x10042b677  jb      loc_10042B51D
0x10042b67d  mov     ecx, [rsp+0D8h+var_60]
0x10042b681  cmp     bx, cx
0x10042b684  jb      short loc_10042B6D7
0x10042b686  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x10042b68b  jb      loc_10042B51D
0x10042b691  mov     ecx, [rsp+0D8h+var_58]
0x10042b698  cmp     bx, cx
0x10042b69b  jb      short loc_10042B6D7
0x10042b69d  cmp     bx, word ptr [rsp+0D8h+var_54]
0x10042b6a5  jb      loc_10042B51D
0x10042b6ab  mov     ecx, [rsp+0D8h+var_50]
0x10042b6b2  movzx   eax, bx
0x10042b6b5  sub     ax, cx
0x10042b6b8  cmp     ax, 9
0x10042b6bc  ja      short loc_10042B6D7
0x10042b6be  jmp     loc_10042B51D
0x10042b6c3  cmp     bx, word ptr [rsp+0D8h+var_4C]
0x10042b6cb  jnb     short loc_10042B6D7
0x10042b6cd  movzx   eax, bx
0x10042b6d0  sub     eax, edx
0x10042b6d2  cmp     eax, 0FFFFFFFFh
0x10042b6d5  jnz     short loc_10042B6F9
0x10042b6d7  mov     edx, [rsp+0D8h+var_48]
0x10042b6de  movzx   ecx, bx
0x10042b6e1  lea     eax, [rcx-41h]
0x10042b6e4  cmp     eax, edx
0x10042b6e6  lea     eax, [rcx-61h]
0x10042b6e9  jbe     short loc_10042B6EF
0x10042b6eb  cmp     eax, edx
0x10042b6ed  ja      short loc_10042B75C
0x10042b6ef  cmp     eax, edx
0x10042b6f1  ja      short loc_10042B6F6
0x10042b6f3  add     ecx, 0FFFFFFE0h
0x10042b6f6  lea     eax, [rcx-37h]
0x10042b6f9  test    eax, eax
0x10042b6fb  jnz     short loc_10042B75C
0x10042b6fd  mov     rcx, [rdi]
0x10042b700  mov     r9d, 0FFDFh
0x10042b706  movzx   edx, word ptr [rcx]
0x10042b709  lea     r8, [rcx+2]
0x10042b70d  mov     [rdi], r8
0x10042b710  lea     eax, [rdx-58h]
0x10042b713  test    r9w, ax
0x10042b717  jz      short loc_10042B74A
0x10042b719  test    r15d, r15d
0x10042b71c  mov     [rdi], rcx
0x10042b71f  mov     eax, 8
0x10042b724  cmovnz  eax, r15d
0x10042b728  mov     r15d, eax
0x10042b72b  test    dx, dx
0x10042b72e  jz      short loc_10042B76B
0x10042b730  cmp     [rcx], dx
0x10042b733  jz      short loc_10042B76B
0x10042b735  call    _errno
0x10042b73a  mov     dword ptr [rax], 16h
0x10042b740  call    _invalid_parameter_noinfo
0x10042b745  xor     r10d, r10d
0x10042b748  jmp     short loc_10042B76B
0x10042b74a  movzx   ebx, word ptr [r8]
0x10042b74e  lea     rax, [r8+2]
0x10042b752  mov     [rdi], rax
0x10042b755  mov     eax, 10h
0x10042b75a  jmp     short loc_10042B761
0x10042b75c  mov     eax, 0Ah
0x10042b761  test    r15d, r15d
0x10042b764  cmovnz  eax, r15d
0x10042b768  mov     r15d, eax
0x10042b76b  xor     edx, edx
0x10042b76d  or      eax, 0FFFFFFFFh
0x10042b770  div     r15d
0x10042b773  mov     r11d, 61h ; 'a'
0x10042b779  mov     ebp, 660h
0x10042b77e  mov     r9d, eax
0x10042b781  mov     r12d, 0FF10h
0x10042b787  lea     r13d, [r11-31h]
0x10042b78b  cmp     bx, r13w
0x10042b78f  jb      loc_10042B93A
0x10042b795  cmp     bx, 3Ah ; ':'
0x10042b799  jnb     short loc_10042B7A6
0x10042b79b  movzx   ecx, bx
0x10042b79e  sub     ecx, r13d
0x10042b7a1  jmp     loc_10042B935
0x10042b7a6  cmp     bx, r12w
0x10042b7aa  jnb     loc_10042B925
0x10042b7b0  cmp     bx, bp
0x10042b7b3  jb      loc_10042B93A
0x10042b7b9  mov     eax, 66Ah
0x10042b7be  cmp     bx, ax
0x10042b7c1  jnb     short loc_10042B7CD
0x10042b7c3  movzx   ecx, bx
0x10042b7c6  sub     ecx, ebp
0x10042b7c8  jmp     loc_10042B935
0x10042b7cd  mov     eax, 6F0h
0x10042b7d2  cmp     bx, ax
0x10042b7d5  jb      loc_10042B93A
0x10042b7db  lea     ecx, [rax+0Ah]
0x10042b7de  cmp     bx, cx
0x10042b7e1  jnb     short loc_10042B7ED
0x10042b7e3  movzx   ecx, bx
0x10042b7e6  sub     ecx, eax
0x10042b7e8  jmp     loc_10042B935
0x10042b7ed  mov     eax, 966h
0x10042b7f2  cmp     bx, ax
0x10042b7f5  jb      loc_10042B93A
0x10042b7fb  lea     ecx, [rax+0Ah]
0x10042b7fe  cmp     bx, cx
0x10042b801  jb      short loc_10042B7E3
0x10042b803  lea     eax, [rcx+76h]
0x10042b806  cmp     bx, ax
0x10042b809  jb      loc_10042B93A
0x10042b80f  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x10042b817  jb      short loc_10042B7E3
0x10042b819  mov     eax, [rsp+0D8h+var_A8]
0x10042b81d  cmp     bx, ax
0x10042b820  jb      loc_10042B93A
0x10042b826  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x10042b82b  jb      short loc_10042B7E3
0x10042b82d  mov     eax, [rsp+0D8h+var_A0]
0x10042b831  cmp     bx, ax
0x10042b834  jb      loc_10042B93A
0x10042b83a  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x10042b83f  jb      short loc_10042B7E3
0x10042b841  mov     eax, [rsp+0D8h+var_98]
0x10042b845  cmp     bx, ax
  ... truncated ...
```
