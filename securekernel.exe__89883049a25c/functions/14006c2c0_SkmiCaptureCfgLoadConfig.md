# SkmiCaptureCfgLoadConfig

- ea: `0x14006c2c0`
- end: `0x14006c7c5`
- name: `SkmiCaptureCfgLoadConfig`
- size: `1285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006c25c`

## callees

- `0x14006c2c0`
- `0x1400f3620`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCaptureCfgLoadConfig(__int64 a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // esi
  unsigned int v9; // r15d
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  unsigned int *v13; // rdx
  unsigned __int64 v14; // r9
  unsigned int v15; // edi
  unsigned int v16; // esi
  unsigned __int64 v17; // rcx
  unsigned int v18; // r8d
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r12
  __int64 v21; // r15
  unsigned int v22; // r11d
  __int64 i; // rcx
  unsigned int v24; // edx
  unsigned __int64 v25; // r9
  unsigned int v26; // r10d
  unsigned __int64 v27; // rcx
  __int64 v28; // r9
  __int64 j; // rcx
  unsigned int v30; // edx
  unsigned int v32; // [rsp+28h] [rbp-210h]
  _BYTE v35[128]; // [rsp+A0h] [rbp-198h] BYREF
  unsigned __int64 v36; // [rsp+120h] [rbp-118h]
  __int64 v37; // [rsp+128h] [rbp-110h]
  __int64 v38; // [rsp+130h] [rbp-108h]
  unsigned __int64 v39; // [rsp+140h] [rbp-F8h]
  __int64 v40; // [rsp+148h] [rbp-F0h]

  v8 = 328;
  memset_0(v35, 0, 0x148u);
  v9 = *(_DWORD *)(a4 + 16);
  v32 = v9;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( *(_WORD *)(a3 + 24) == 523 )
  {
    if ( *(_DWORD *)(a3 + 132) > 0xAu )
    {
      v11 = *(_DWORD *)(a3 + 216);
      v10 = *(_DWORD *)(a3 + 220);
    }
    if ( v10 )
    {
      if ( v11 + 148 < v11 || v11 + 148 > v9 )
      {
        SkmiImageCfgFailure = 2;
        return v12;
      }
      v13 = (unsigned int *)(a1 + v11);
      if ( v10 >= 0x94 )
        goto LABEL_15;
      if ( *(_WORD *)(a3 + 4) != 332 )
      {
        SkmiImageCfgFailure = 5;
        return v12;
      }
      if ( v10 > 4 )
        v10 = *v13;
      if ( v10 >= 0x94 )
      {
LABEL_15:
        if ( v10 < 0x148 )
          v8 = v10;
        if ( v8 + v11 <= v11 || v8 + v11 > v9 )
        {
          SkmiImageCfgFailure = 6;
          return v12;
        }
        memmove(v35, v13, v8);
        if ( (v38 & 0x400) != 0 && v36 )
        {
          v14 = 0;
          v15 = 0;
          if ( (v38 & 0x4000) != 0 && v8 >= 0xB0 )
          {
            v14 = v39;
            v15 = v40;
          }
          if ( v36 < a2 || !(_DWORD)v37 || (v16 = ((unsigned int)v38 >> 28) + 4, (unsigned int)v37 >= 0xFFFFFFFF / v16) )
          {
            v12 = -1073741819;
            SkmiImageCfgFailure = 8;
            return v12;
          }
          v17 = v36 - a2;
          v18 = v16 * v37;
          v19 = v36 - a2 + v16 * (unsigned int)v37;
          if ( v19 <= v36 - a2 || (v20 = v9, v19 > v9) || v18 + 4 < v18 )
          {
            v12 = -1073741819;
            SkmiImageCfgFailure = 9;
            return v12;
          }
          v21 = v17 + a1;
          v22 = 0;
          for ( i = 0; (unsigned int)i < v18; i = v16 + (unsigned int)i )
          {
            v24 = *(_DWORD *)(i + v21);
            if ( v24 >= v32 )
            {
              v12 = -1073741701;
              SkmiImageCfgFailure = 10;
              break;
            }
            if ( (_DWORD)i && v24 < v22 )
            {
              v12 = -1073741701;
              SkmiImageCfgFailure = 11;
              break;
            }
            v22 = *(_DWORD *)(i + v21);
          }
          if ( (v12 & 0x80000000) == 0 )
          {
            if ( !v14 )
              goto LABEL_55;
            if ( v14 < a2 || !v15 || v15 >= 0xFFFFFFFF / v16 )
            {
              v12 = -1073741819;
              SkmiImageCfgFailure = 15;
              return v12;
            }
            v25 = v14 - a2;
            v26 = v15 * v16;
            v27 = v25 + v15 * v16;
            if ( v27 <= v25 || v27 > v20 || v26 + 4 < v26 )
            {
              v12 = -1073741819;
              SkmiImageCfgFailure = 16;
              return v12;
            }
            v28 = a1 + v25;
            for ( j = 0; (unsigned int)j < v26; j = v16 + (unsigned int)j )
            {
              v30 = *(_DWORD *)(j + v28);
              if ( v30 > v32 - 8 )
              {
                v12 = -1073741819;
                SkmiImageCfgFailure = 17;
                break;
              }
              if ( (_DWORD)j && v30 < v22 )
              {
                v12 = -1073741701;
                SkmiImageCfgFailure = 10;
                break;
              }
              v22 = *(_DWORD *)(j + v28);
            }
            if ( (v12 & 0x80000000) == 0 )
            {
LABEL_55:
              *(_DWORD *)(a4 + 24) = v38;
              *(_QWORD *)a4 = v21;
              *(_DWORD *)(a4 + 8) = v18;
              *(_BYTE *)(a4 + 20) = 1;
            }
          }
        }
      }
      else
      {
        SkmiImageCfgFailure = 4;
      }
    }
  }
  else
  {
    SkmiImageCfgFailure = 1;
  }
  return v12;
}

```

## disassembly

```asm
0x14006c2c0  mov     [rsp+arg_8], rdx
0x14006c2c5  push    rbx
0x14006c2c6  push    rsi
0x14006c2c7  push    rdi
0x14006c2c8  push    r12
0x14006c2ca  push    r13
0x14006c2cc  push    r14
0x14006c2ce  push    r15
0x14006c2d0  sub     rsp, 200h
0x14006c2d7  mov     rax, cs:__security_cookie
0x14006c2de  xor     rax, rsp
0x14006c2e1  mov     [rsp+238h+var_48], rax
0x14006c2e9  mov     r13, r9
0x14006c2ec  mov     rdi, r8
0x14006c2ef  mov     r12, rdx
0x14006c2f2  mov     r14, rcx
0x14006c2f5  mov     [rsp+238h+var_1D0], rcx
0x14006c2fa  mov     [rsp+238h+var_1A0], r9
0x14006c302  mov     [rsp+238h+var_1B0], rcx
0x14006c30a  mov     [rsp+238h+var_1C8], r9
0x14006c30f  mov     [rsp+238h+var_1F8], 0
0x14006c317  mov     [rsp+238h+var_20C], 0
0x14006c31f  mov     esi, 148h
0x14006c324  mov     r8d, esi; Size
0x14006c327  xor     edx, edx; Val
0x14006c329  lea     rcx, [rsp+238h+var_198]; void *
0x14006c331  call    memset_0
0x14006c336  mov     [rsp+238h+var_218], 0
0x14006c33e  mov     r15d, [r13+10h]
0x14006c342  mov     [rsp+238h+var_210], r15d
0x14006c347  mov     [rsp+238h+var_1FC], r15d
0x14006c34c  xor     eax, eax
0x14006c34e  mov     [rsp+238h+var_218], eax
0x14006c352  xor     ecx, ecx
0x14006c354  mov     [rsp+238h+var_204], ecx
0x14006c358  xor     ebx, ebx
0x14006c35a  mov     edx, 20Bh
0x14006c35f  cmp     [rdi+18h], dx
0x14006c363  jz      short loc_14006C374
0x14006c365  mov     cs:SkmiImageCfgFailure, 1
0x14006c36f  jmp     loc_14006C79F
0x14006c374  mov     [rsp+238h+var_1F8], 8
0x14006c37c  cmp     dword ptr [rdi+84h], 0Ah
0x14006c383  jbe     short loc_14006C399
0x14006c385  mov     ecx, [rdi+0D8h]
0x14006c38b  mov     [rsp+238h+var_204], ecx
0x14006c38f  mov     eax, [rdi+0DCh]
0x14006c395  mov     [rsp+238h+var_218], eax
0x14006c399  movzx   r8d, word ptr [rdi+4]
0x14006c39e  mov     [rsp+238h+var_1E0], r8w
0x14006c3a4  test    eax, eax
0x14006c3a6  jz      loc_14006C79F
0x14006c3ac  lea     edx, [rcx+94h]
0x14006c3b2  cmp     edx, ecx
0x14006c3b4  jbe     loc_14006C787
0x14006c3ba  cmp     edx, r15d
0x14006c3bd  ja      loc_14006C787
0x14006c3c3  mov     edx, ecx
0x14006c3c5  add     rdx, r14; Src
0x14006c3c8  mov     [rsp+238h+var_1E8], rdx
0x14006c3cd  cmp     eax, 94h
0x14006c3d2  jnb     short loc_14006C44E
0x14006c3d4  mov     r9d, 14Ch
0x14006c3da  cmp     r8w, r9w
0x14006c3de  jnz     short loc_14006C43F
0x14006c3e0  cmp     eax, 4
0x14006c3e3  jbe     short loc_14006C3EB
0x14006c3e5  mov     eax, [rdx]
0x14006c3e7  mov     [rsp+238h+var_218], eax
0x14006c3eb  jmp     short loc_14006C425
0x14006c3ed  mov     ebx, eax
0x14006c3ef  mov     esi, 148h
0x14006c3f4  mov     eax, [rsp+238h+var_218]
0x14006c3f8  mov     ecx, [rsp+238h+var_204]
0x14006c3fc  mov     rdx, [rsp+238h+var_1E8]
0x14006c401  mov     r15d, [rsp+238h+var_1FC]
0x14006c406  mov     [rsp+238h+var_210], r15d
0x14006c40b  mov     r8, [rsp+238h+var_1B0]
0x14006c413  mov     [rsp+238h+var_1D0], r8
0x14006c418  mov     r13, [rsp+238h+var_1C8]
0x14006c41d  mov     r12, [rsp+238h+arg_8]
0x14006c425  test    ebx, ebx
0x14006c427  js      short loc_14006C430
0x14006c429  cmp     eax, 94h
0x14006c42e  jnb     short loc_14006C44E
0x14006c430  mov     cs:SkmiImageCfgFailure, 4
0x14006c43a  jmp     loc_14006C79F
0x14006c43f  mov     cs:SkmiImageCfgFailure, 5
0x14006c449  jmp     loc_14006C79F
0x14006c44e  cmp     eax, esi
0x14006c450  jnb     short loc_14006C454
0x14006c452  mov     esi, eax
0x14006c454  mov     [rsp+238h+var_218], esi
0x14006c458  lea     eax, [rsi+rcx]
0x14006c45b  cmp     eax, ecx
0x14006c45d  jbe     loc_14006C77B
0x14006c463  cmp     eax, r15d
0x14006c466  ja      loc_14006C77B
0x14006c46c  mov     r8d, esi; Size
0x14006c46f  lea     rcx, [rsp+238h+var_198]; void *
0x14006c477  call    memmove
0x14006c47c  nop
0x14006c47d  mov     r14, [rsp+238h+var_108]
0x14006c485  mov     [rsp+238h+var_1F0], r14d
0x14006c48a  bt      r14d, 0Ah
0x14006c48f  jnb     loc_14006C79F
0x14006c495  mov     rcx, [rsp+238h+var_118]
0x14006c49d  test    rcx, rcx
0x14006c4a0  jz      loc_14006C79F
0x14006c4a6  xor     r9d, r9d
0x14006c4a9  mov     [rsp+238h+var_1B8], r9
0x14006c4b1  xor     edi, edi
0x14006c4b3  mov     [rsp+238h+var_200], edi
0x14006c4b7  bt      r14d, 0Eh
0x14006c4bc  jnb     short loc_14006C4E2
0x14006c4be  cmp     esi, 0B0h
0x14006c4c4  jb      short loc_14006C4E2
0x14006c4c6  mov     r9, [rsp+238h+var_F8]
0x14006c4ce  mov     [rsp+238h+var_1B8], r9
0x14006c4d6  mov     rdi, [rsp+238h+var_F0]
0x14006c4de  mov     [rsp+238h+var_200], edi
0x14006c4e2  cmp     rcx, r12
0x14006c4e5  jb      loc_14006C75C
0x14006c4eb  mov     r8, [rsp+238h+var_110]
0x14006c4f3  test    r8d, r8d
0x14006c4f6  jz      loc_14006C75C
0x14006c4fc  mov     esi, r14d
0x14006c4ff  shr     esi, 1Ch
0x14006c502  add     esi, 4
0x14006c505  mov     [rsp+238h+var_1DC], esi
0x14006c509  xor     edx, edx
0x14006c50b  or      eax, 0FFFFFFFFh
0x14006c50e  div     esi
0x14006c510  mov     r10d, eax
0x14006c513  mov     [rsp+238h+var_1D8], eax
0x14006c517  cmp     r8d, eax
0x14006c51a  jnb     loc_14006C75C
0x14006c520  sub     rcx, r12
0x14006c523  imul    r8d, esi
0x14006c527  mov     [rsp+238h+var_1F4], r8d
0x14006c52c  mov     edx, r8d
0x14006c52f  add     rdx, rcx
0x14006c532  cmp     rdx, rcx
0x14006c535  jbe     loc_14006C74B
0x14006c53b  mov     r12d, r15d
0x14006c53e  mov     [rsp+238h+var_1A8], r12
0x14006c546  cmp     rdx, r12
0x14006c549  ja      loc_14006C74B
0x14006c54f  lea     eax, [r8+4]
0x14006c553  cmp     eax, r8d
0x14006c556  jb      loc_14006C74B
0x14006c55c  mov     r15, [rsp+238h+var_1D0]
0x14006c561  add     r15, rcx
0x14006c564  mov     [rsp+238h+var_1E8], r15
0x14006c569  xor     r11d, r11d
0x14006c56c  mov     [rsp+238h+var_20C], r11d
0x14006c571  xor     ecx, ecx
0x14006c573  mov     [rsp+238h+var_208], ecx
0x14006c577  cmp     ecx, r8d
0x14006c57a  jnb     short loc_14006C5C4
0x14006c57c  mov     edx, [rcx+r15]
0x14006c580  cmp     edx, [rsp+238h+var_210]
0x14006c584  jb      short loc_14006C59B
0x14006c586  mov     ebx, 0C000007Bh
0x14006c58b  mov     [rsp+238h+var_214], ebx
0x14006c58f  mov     cs:SkmiImageCfgFailure, 0Ah
0x14006c599  jmp     short loc_14006C5C4
0x14006c59b  test    ecx, ecx
0x14006c59d  jz      short loc_14006C5B9
0x14006c59f  cmp     edx, r11d
0x14006c5a2  jnb     short loc_14006C5B9
0x14006c5a4  mov     ebx, 0C000007Bh
0x14006c5a9  mov     [rsp+238h+var_214], ebx
0x14006c5ad  mov     cs:SkmiImageCfgFailure, 0Bh
0x14006c5b7  jmp     short loc_14006C5C4
0x14006c5b9  mov     r11d, edx
0x14006c5bc  mov     [rsp+238h+var_20C], edx
0x14006c5c0  add     ecx, esi
0x14006c5c2  jmp     short loc_14006C573
0x14006c5c4  mov     rdx, [rsp+238h+var_1D0]
0x14006c5c9  jmp     short loc_14006C621
0x14006c5cb  mov     ebx, eax
0x14006c5cd  mov     [rsp+238h+var_214], eax
0x14006c5d1  mov     cs:SkmiImageCfgFailure, 0Ch
0x14006c5db  mov     r8d, [rsp+238h+var_1F4]
0x14006c5e0  mov     edi, [rsp+238h+var_200]
0x14006c5e4  mov     r9, [rsp+238h+var_1B8]
0x14006c5ec  mov     r11d, [rsp+238h+var_20C]
0x14006c5f1  mov     esi, [rsp+238h+var_1DC]
0x14006c5f5  mov     eax, [rsp+238h+var_1FC]
0x14006c5f9  mov     [rsp+238h+var_210], eax
0x14006c5fd  mov     r15, [rsp+238h+var_1E8]
0x14006c602  mov     rdx, [rsp+238h+var_1B0]
0x14006c60a  mov     r14d, [rsp+238h+var_1F0]
0x14006c60f  mov     r13, [rsp+238h+var_1C8]
0x14006c614  mov     r10d, [rsp+238h+var_1D8]
0x14006c619  mov     r12, [rsp+238h+var_1A8]
0x14006c621  test    ebx, ebx
0x14006c623  js      loc_14006C79F
0x14006c629  test    r9, r9
0x14006c62c  jz      loc_14006C70F
0x14006c632  mov     rax, [rsp+238h+arg_8]
0x14006c63a  cmp     r9, rax
0x14006c63d  jb      loc_14006C73A
0x14006c643  test    edi, edi
0x14006c645  jz      loc_14006C73A
0x14006c64b  cmp     edi, r10d
0x14006c64e  jnb     loc_14006C73A
0x14006c654  sub     r9, rax
0x14006c657  mov     r10d, esi
0x14006c65a  imul    r10d, edi
0x14006c65e  mov     ecx, r10d
0x14006c661  add     rcx, r9
0x14006c664  cmp     rcx, r9
0x14006c667  jbe     loc_14006C729
0x14006c66d  cmp     rcx, r12
0x14006c670  ja      loc_14006C729
0x14006c676  lea     eax, [r10+4]
0x14006c67a  cmp     eax, r10d
0x14006c67d  jb      loc_14006C729
0x14006c683  add     r9, rdx
0x14006c686  xor     ecx, ecx
0x14006c688  mov     edi, [rsp+238h+var_210]
0x14006c68c  mov     [rsp+238h+var_208], ecx
0x14006c690  cmp     ecx, r10d
0x14006c693  jnb     short loc_14006C6E1
0x14006c695  mov     edx, [rcx+r9]
0x14006c699  mov     eax, edi
0x14006c69b  sub     eax, [rsp+238h+var_1F8]
0x14006c69f  cmp     edx, eax
0x14006c6a1  jbe     short loc_14006C6B8
0x14006c6a3  mov     ebx, 0C0000005h
0x14006c6a8  mov     [rsp+238h+var_214], ebx
0x14006c6ac  mov     cs:SkmiImageCfgFailure, 11h
0x14006c6b6  jmp     short loc_14006C6E1
0x14006c6b8  test    ecx, ecx
0x14006c6ba  jz      short loc_14006C6D6
0x14006c6bc  cmp     edx, r11d
0x14006c6bf  jnb     short loc_14006C6D6
0x14006c6c1  mov     ebx, 0C000007Bh
0x14006c6c6  mov     [rsp+238h+var_214], ebx
0x14006c6ca  mov     cs:SkmiImageCfgFailure, 0Ah
0x14006c6d4  jmp     short loc_14006C6E1
0x14006c6d6  mov     r11d, edx
0x14006c6d9  mov     [rsp+238h+var_20C], edx
0x14006c6dd  add     ecx, esi
0x14006c6df  jmp     short loc_14006C68C
0x14006c6e1  jmp     short loc_14006C707
0x14006c6e3  mov     ebx, eax
0x14006c6e5  mov     [rsp+238h+var_214], eax
0x14006c6e9  mov     cs:SkmiImageCfgFailure, 12h
0x14006c6f3  mov     r8d, [rsp+238h+var_1F4]
0x14006c6f8  mov     r15, [rsp+238h+var_1E8]
0x14006c6fd  mov     r14d, [rsp+238h+var_1F0]
0x14006c702  mov     r13, [rsp+238h+var_1C8]
0x14006c707  test    ebx, ebx
0x14006c709  js      loc_14006C79F
0x14006c70f  mov     [r13+18h], r14d
0x14006c713  mov     rax, [rsp+238h+var_1A0]
0x14006c71b  mov     [rax], r15
0x14006c71e  mov     [r13+8], r8d
0x14006c722  mov     byte ptr [r13+14h], 1
0x14006c727  jmp     short loc_14006C79F
0x14006c729  mov     ebx, 0C0000005h
0x14006c72e  mov     cs:SkmiImageCfgFailure, 10h
0x14006c738  jmp     short loc_14006C79F
0x14006c73a  mov     ebx, 0C0000005h
0x14006c73f  mov     cs:SkmiImageCfgFailure, 0Fh
0x14006c749  jmp     short loc_14006C79F
0x14006c74b  mov     ebx, 0C0000005h
0x14006c750  mov     cs:SkmiImageCfgFailure, 9
0x14006c75a  jmp     short loc_14006C79F
0x14006c75c  mov     ebx, 0C0000005h
0x14006c761  mov     cs:SkmiImageCfgFailure, 8
0x14006c76b  jmp     short loc_14006C79F
0x14006c76d  mov     ebx, eax
0x14006c76f  mov     cs:SkmiImageCfgFailure, 7
0x14006c779  jmp     short loc_14006C79F
0x14006c77b  mov     cs:SkmiImageCfgFailure, 6
0x14006c785  jmp     short loc_14006C79F
0x14006c787  mov     cs:SkmiImageCfgFailure, 2
0x14006c791  jmp     short loc_14006C79F
0x14006c793  mov     ebx, eax
0x14006c795  mov     cs:SkmiImageCfgFailure, 3
0x14006c79f  mov     eax, ebx
0x14006c7a1  mov     rcx, [rsp+238h+var_48]
0x14006c7a9  xor     rcx, rsp; StackCookie
0x14006c7ac  call    __security_check_cookie
0x14006c7b1  add     rsp, 200h
0x14006c7b8  pop     r15
0x14006c7ba  pop     r14
0x14006c7bc  pop     r13
0x14006c7be  pop     r12
0x14006c7c0  pop     rdi
0x14006c7c1  pop     rsi
0x14006c7c2  pop     rbx
0x14006c7c3  retn
```
