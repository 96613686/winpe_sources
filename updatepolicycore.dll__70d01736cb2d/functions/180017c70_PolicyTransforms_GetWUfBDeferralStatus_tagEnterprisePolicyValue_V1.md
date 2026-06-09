# PolicyTransforms::GetWUfBDeferralStatus(tagEnterprisePolicyValue_V1 *)

- ea: `0x180017c70`
- end: `0x180017e6c`
- name: `?GetWUfBDeferralStatus@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180010ae0`
- `0x180017c70`
- `0x18001a320`
- `0x18003002c`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::GetWUfBDeferralStatus(struct tagEnterprisePolicyValue_V1 *a1)
{
  __int64 v1; // rax
  int v3; // ecx
  _DWORD *v4; // rbx
  _DWORD *v5; // rsi
  unsigned int v6; // r15d
  __int64 v7; // r12
  int v8; // eax
  _DWORD *v9; // r14
  __int64 v10; // r12
  int PolicyWithFallback; // eax
  unsigned int v12; // r13d
  __m128i *i; // r12
  int v14; // eax
  int v15; // eax
  _DWORD v17[4]; // [rsp+20h] [rbp-38h]
  __m128i si128; // [rsp+30h] [rbp-28h] BYREF
  int v19; // [rsp+40h] [rbp-18h]
  void *v20; // [rsp+A0h] [rbp+48h] BYREF
  void *v21; // [rsp+A8h] [rbp+50h] BYREF
  void *Block; // [rsp+B0h] [rbp+58h] BYREF
  int v23; // [rsp+B8h] [rbp+60h]
  int v24; // [rsp+BCh] [rbp+64h]

  v1 = 0;
  v23 = 6;
  v24 = 8;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v3 = 40;
  v19 = 50;
  do
    v17[v1++] = v3++;
  while ( v1 < 4 );
  v4 = 0;
  Block = 0;
  v5 = 0;
  v21 = 0;
  v20 = 0;
  if ( a1 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = UpdatePolicyReader::ReadPolicy(v17[v7], &Block);
      v9 = Block;
      v6 = v8;
      if ( v8 < 0 )
        break;
      if ( *((_DWORD *)Block + 1) == 1 )
      {
        if ( *((_WORD *)Block + 8) != 3 )
          break;
        if ( *((_DWORD *)Block + 6) != 1 )
        {
          *((_DWORD *)a1 + 6) = 1;
          *((_WORD *)a1 + 8) = 3;
          *((_DWORD *)a1 + 1) = 1;
          v15 = v9[2];
LABEL_25:
          *((_DWORD *)a1 + 2) = v15;
          break;
        }
      }
      operator delete(Block);
      v9 = 0;
      v7 = (unsigned int)(v7 + 1);
      Block = 0;
      if ( (unsigned int)v7 >= 4 )
      {
        v10 = 0;
        while ( 1 )
        {
          PolicyWithFallback = EnterprisePolicyReader::ReadPolicyWithFallback(*(&v23 + v10), (__int64 *)&v21);
          v4 = v21;
          v6 = PolicyWithFallback;
          if ( PolicyWithFallback < 0 )
            goto LABEL_28;
          if ( *((_DWORD *)v21 + 1) == 1 )
          {
            if ( *((_WORD *)v21 + 8) != 3 )
              goto LABEL_28;
            if ( *((_DWORD *)v21 + 6) )
            {
              *((_DWORD *)a1 + 6) = 1;
              *((_WORD *)a1 + 8) = 3;
              *((_DWORD *)a1 + 1) = 1;
              *((_DWORD *)a1 + 2) = v4[2];
              goto LABEL_28;
            }
          }
          operator delete(v21);
          v4 = 0;
          v10 = (unsigned int)(v10 + 1);
          v21 = 0;
          if ( (unsigned int)v10 >= 2 )
          {
            v12 = 0;
            for ( i = &si128; ; i = (__m128i *)((char *)i + 4) )
            {
              v14 = EnterprisePolicyReader::ReadPolicyWithFallback(i->m128i_i32[0], (__int64 *)&v20);
              v5 = v20;
              v6 = v14;
              if ( v14 < 0 )
                break;
              if ( *((_DWORD *)v20 + 1) == 1 )
              {
                *((_DWORD *)a1 + 6) = 1;
                *((_WORD *)a1 + 8) = 3;
                *((_DWORD *)a1 + 1) = 1;
                v15 = v5[2];
                goto LABEL_25;
              }
              operator delete(v20);
              ++v12;
              v20 = 0;
              if ( v12 >= 5 )
                return v6;
            }
            goto LABEL_30;
          }
        }
      }
    }
    if ( !v9 )
      goto LABEL_30;
    operator delete(v9);
LABEL_28:
    if ( v4 )
      operator delete(v4);
LABEL_30:
    if ( v5 )
      operator delete(v5);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x180017c70  push    rbp
0x180017c72  push    rbx
0x180017c73  push    rsi
0x180017c74  push    rdi
0x180017c75  push    r12
0x180017c77  push    r13
0x180017c79  push    r14
0x180017c7b  push    r15
0x180017c7d  mov     rbp, rsp
0x180017c80  sub     rsp, 58h
0x180017c84  movdqa  xmm0, cs:__xmm@0000000d0000000e0000000700000009
0x180017c8c  xor     eax, eax
0x180017c8e  mov     rdi, rcx
0x180017c91  mov     [rbp+arg_18], 6
0x180017c98  mov     [rbp+arg_1C], 8
0x180017c9f  movdqu  [rbp+var_28], xmm0
0x180017ca4  lea     ecx, [rax+28h]
0x180017ca7  mov     [rbp+var_18], 32h ; '2'
0x180017cae  lea     r13d, [rax+1]
0x180017cb2  mov     [rbp+rax*4+var_38], ecx
0x180017cb6  add     ecx, r13d
0x180017cb9  add     rax, r13
0x180017cbc  cmp     rax, 4
0x180017cc0  jl      short loc_180017CB2
0x180017cc2  xor     ebx, ebx
0x180017cc4  mov     [rbp+Block], 0
0x180017ccc  xor     esi, esi
0x180017cce  mov     [rbp+arg_8], rbx
0x180017cd2  mov     [rbp+arg_0], rsi
0x180017cd6  test    rdi, rdi
0x180017cd9  jnz     short loc_180017CE6
0x180017cdb  mov     r15d, 80004003h
0x180017ce1  jmp     loc_180017E58
0x180017ce6  xor     r12d, r12d
0x180017ce9  mov     ecx, [rbp+r12*4+var_38]
0x180017cee  lea     rdx, [rbp+Block]
0x180017cf2  call    ?ReadPolicy@UpdatePolicyReader@@SAJW4tagUpdatePolicy@@PEAPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 * *)
0x180017cf7  mov     r14, [rbp+Block]
0x180017cfb  mov     r15d, eax
0x180017cfe  test    eax, eax
0x180017d00  js      loc_180017E22
0x180017d06  cmp     [r14+4], r13d
0x180017d0a  jnz     short loc_180017D26
0x180017d0c  mov     eax, 3
0x180017d11  cmp     [r14+10h], ax
0x180017d16  jnz     loc_180017E22
0x180017d1c  cmp     [r14+18h], r13d
0x180017d20  jnz     loc_180017DE2
0x180017d26  mov     edx, 28h ; '('
0x180017d2b  mov     rcx, r14; Block
0x180017d2e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017d33  xor     r14d, r14d
0x180017d36  add     r12d, r13d
0x180017d39  mov     [rbp+Block], r14
0x180017d3d  cmp     r12d, 4
0x180017d41  jb      short loc_180017CE9
0x180017d43  xor     r12d, r12d
0x180017d46  mov     ecx, [rbp+r12*4+arg_18]
0x180017d4b  lea     rdx, [rbp+arg_8]
0x180017d4f  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x180017d54  mov     rbx, [rbp+arg_8]
0x180017d58  mov     r15d, eax
0x180017d5b  test    eax, eax
0x180017d5d  js      loc_180017E34
0x180017d63  cmp     [rbx+4], r13d
0x180017d67  jnz     short loc_180017D7D
0x180017d69  mov     eax, 3
0x180017d6e  cmp     [rbx+10h], ax
0x180017d72  jnz     loc_180017E34
0x180017d78  cmp     [rbx+18h], esi
0x180017d7b  jnz     short loc_180017DF4
0x180017d7d  mov     edx, 30h ; '0'
0x180017d82  mov     rcx, rbx; Block
0x180017d85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017d8a  xor     ebx, ebx
0x180017d8c  add     r12d, r13d
0x180017d8f  mov     [rbp+arg_8], rbx
0x180017d93  cmp     r12d, 2
0x180017d97  jb      short loc_180017D46
0x180017d99  xor     r13d, r13d
0x180017d9c  lea     r12, [rbp+var_28]
0x180017da0  mov     ecx, [r12]
0x180017da4  lea     rdx, [rbp+arg_0]
0x180017da8  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x180017dad  mov     rsi, [rbp+arg_0]
0x180017db1  mov     r15d, eax
0x180017db4  test    eax, eax
0x180017db6  js      loc_180017E46
0x180017dbc  cmp     dword ptr [rsi+4], 1
0x180017dc0  jz      short loc_180017E08
0x180017dc2  mov     edx, 30h ; '0'
0x180017dc7  mov     rcx, rsi; Block
0x180017dca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017dcf  inc     r13d
0x180017dd2  mov     [rbp+arg_0], rbx
0x180017dd6  add     r12, 4
0x180017dda  cmp     r13d, 5
0x180017dde  jb      short loc_180017DA0
0x180017de0  jmp     short loc_180017E58
0x180017de2  mov     [rdi+18h], r13d
0x180017de6  mov     [rdi+10h], ax
0x180017dea  mov     [rdi+4], r13d
0x180017dee  mov     eax, [r14+8]
0x180017df2  jmp     short loc_180017E1F
0x180017df4  mov     [rdi+18h], r13d
0x180017df8  mov     [rdi+10h], ax
0x180017dfc  mov     [rdi+4], r13d
0x180017e00  mov     eax, [rbx+8]
0x180017e03  mov     [rdi+8], eax
0x180017e06  jmp     short loc_180017E34
0x180017e08  mov     dword ptr [rdi+18h], 1
0x180017e0f  mov     word ptr [rdi+10h], 3
0x180017e15  mov     dword ptr [rdi+4], 1
0x180017e1c  mov     eax, [rsi+8]
0x180017e1f  mov     [rdi+8], eax
0x180017e22  test    r14, r14
0x180017e25  jz      short loc_180017E46
0x180017e27  mov     edx, 28h ; '('
0x180017e2c  mov     rcx, r14; Block
0x180017e2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017e34  test    rbx, rbx
0x180017e37  jz      short loc_180017E46
0x180017e39  mov     edx, 30h ; '0'
0x180017e3e  mov     rcx, rbx; Block
0x180017e41  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017e46  test    rsi, rsi
0x180017e49  jz      short loc_180017E58
0x180017e4b  mov     edx, 30h ; '0'
0x180017e50  mov     rcx, rsi; Block
0x180017e53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017e58  mov     eax, r15d
0x180017e5b  add     rsp, 58h
0x180017e5f  pop     r15
0x180017e61  pop     r14
0x180017e63  pop     r13
0x180017e65  pop     r12
0x180017e67  pop     rdi
0x180017e68  pop     rsi
0x180017e69  pop     rbx
0x180017e6a  pop     rbp
0x180017e6b  retn
```
