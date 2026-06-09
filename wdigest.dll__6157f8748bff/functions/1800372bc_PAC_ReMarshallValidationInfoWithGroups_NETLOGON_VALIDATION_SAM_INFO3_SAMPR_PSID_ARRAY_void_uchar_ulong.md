# PAC_ReMarshallValidationInfoWithGroups(_NETLOGON_VALIDATION_SAM_INFO3 *,_SAMPR_PSID_ARRAY *,void *,uchar * *,ulong *)

- ea: `0x1800372bc`
- end: `0x180037482`
- name: `?PAC_ReMarshallValidationInfoWithGroups@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_SAMPR_PSID_ARRAY@@PEAXPEAPEAEPEAK@Z`
- size: `454`
- prototype: `int(struct _NETLOGON_VALIDATION_SAM_INFO3 *, struct _SAMPR_PSID_ARRAY *, void *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180036ddc`

## callees

- `0x180009770`
- `0x180012880`
- `0x180013304`
- `0x180023f80`
- `0x180036c10`
- `0x1800372bc`

## pseudocode

```c
__int64 __fastcall PAC_ReMarshallValidationInfoWithGroups(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        struct _SAMPR_PSID_ARRAY *a2,
        void *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  _OWORD *v5; // r8
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v7; // rax
  __int64 v8; // rcx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  int v18; // edx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v21; // rax
  unsigned int v22; // edx
  size_t v23; // rbx
  _DWORD *v24; // rax
  _DWORD *v25; // rdi
  unsigned int v26; // ebx
  unsigned int v27; // r10d
  unsigned int i; // ecx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 j; // r11
  __int64 v32; // r9
  __int64 v33; // rcx
  _BYTE v35[168]; // [rsp+20h] [rbp-E0h] BYREF
  int v36; // [rsp+C8h] [rbp-38h]
  unsigned int v37; // [rsp+130h] [rbp+30h]
  _DWORD *v38; // [rsp+138h] [rbp+38h]
  __int64 v39; // [rsp+140h] [rbp+40h]
  int v40; // [rsp+148h] [rbp+48h]
  __int64 v41; // [rsp+150h] [rbp+50h]

  v5 = v35;
  v7 = a1;
  v8 = 2;
  do
  {
    v11 = *((_OWORD *)v7 + 1);
    *v5 = *(_OWORD *)v7;
    v12 = *((_OWORD *)v7 + 2);
    v5[1] = v11;
    v13 = *((_OWORD *)v7 + 3);
    v5[2] = v12;
    v14 = *((_OWORD *)v7 + 4);
    v5[3] = v13;
    v15 = *((_OWORD *)v7 + 5);
    v5[4] = v14;
    v16 = *((_OWORD *)v7 + 6);
    v5[5] = v15;
    v17 = *((_OWORD *)v7 + 7);
    v7 = (struct _NETLOGON_VALIDATION_SAM_INFO3 *)((char *)v7 + 128);
    v5[6] = v16;
    v5[7] = v17;
    v5 += 8;
    --v8;
  }
  while ( v8 );
  v18 = *(_DWORD *)a2;
  v19 = *((_OWORD *)v7 + 1);
  *v5 = *(_OWORD *)v7;
  v20 = *((_OWORD *)v7 + 2);
  v21 = *((_QWORD *)v7 + 6);
  v5[1] = v19;
  v5[2] = v20;
  *((_QWORD *)v5 + 6) = v21;
  v36 &= ~0x200u;
  v22 = v37 + v18;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  if ( v22 < v37 )
  {
    return (unsigned int)-1073741675;
  }
  else
  {
    v23 = 16LL * v22;
    v24 = MIDL_user_allocate(v23);
    v25 = v24;
    if ( v24 )
    {
      memset_0(v24, 0, v23);
      if ( *(_DWORD *)a2 )
      {
        v36 |= 0x20u;
        v27 = 0;
        for ( i = 0; i < *((_DWORD *)a1 + 68); ++i )
        {
          v29 = *((_QWORD *)a1 + 35);
          if ( (*(_DWORD *)(v29 + 16LL * i + 8) & 0x20000000) == 0 )
          {
            v30 = 2LL * v27++;
            *(_OWORD *)&v25[2 * v30] = *(_OWORD *)(v29 + 16LL * i);
          }
        }
        for ( j = 0; (unsigned int)j < *(_DWORD *)a2; v25[2 * v32 + 2] = 536870919 )
        {
          v32 = v27++;
          v32 *= 2;
          v33 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * j);
          j = (unsigned int)(j + 1);
          *(_QWORD *)&v25[2 * v32] = v33;
        }
        v38 = v25;
        v37 = v27;
      }
      v26 = PAC_EncodeValidationInformation((struct _NETLOGON_VALIDATION_SAM_INFO3 *)v35, a4, a5);
      DigestFreeMemory(v25);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return v26;
}

```

## disassembly

```asm
0x1800372bc  push    rbp
0x1800372be  push    rbx
0x1800372bf  push    rsi
0x1800372c0  push    rdi
0x1800372c1  push    r12
0x1800372c3  push    r14
0x1800372c5  push    r15
0x1800372c7  lea     rbp, [rsp-70h]
0x1800372cc  sub     rsp, 170h
0x1800372d3  mov     rax, cs:__security_cookie
0x1800372da  xor     rax, rsp
0x1800372dd  mov     [rbp+0A0h+var_40], rax
0x1800372e1  mov     r12, [rbp+0A0h+arg_20]
0x1800372e8  lea     r8, [rsp+1A0h+var_180]
0x1800372ed  mov     r14, rcx
0x1800372f0  mov     rax, rcx
0x1800372f3  mov     ecx, 2
0x1800372f8  mov     rsi, rdx
0x1800372fb  mov     r15, r9
0x1800372fe  lea     edx, [rcx+7Eh]
0x180037301  movups  xmm0, xmmword ptr [rax]
0x180037304  movups  xmm1, xmmword ptr [rax+10h]
0x180037308  movups  xmmword ptr [r8], xmm0
0x18003730c  movups  xmm0, xmmword ptr [rax+20h]
0x180037310  movups  xmmword ptr [r8+10h], xmm1
0x180037315  movups  xmm1, xmmword ptr [rax+30h]
0x180037319  movups  xmmword ptr [r8+20h], xmm0
0x18003731e  movups  xmm0, xmmword ptr [rax+40h]
0x180037322  movups  xmmword ptr [r8+30h], xmm1
0x180037327  movups  xmm1, xmmword ptr [rax+50h]
0x18003732b  movups  xmmword ptr [r8+40h], xmm0
0x180037330  movups  xmm0, xmmword ptr [rax+60h]
0x180037334  movups  xmmword ptr [r8+50h], xmm1
0x180037339  movups  xmm1, xmmword ptr [rax+70h]
0x18003733d  add     rax, rdx
0x180037340  movups  xmmword ptr [r8+60h], xmm0
0x180037345  movups  xmmword ptr [r8+70h], xmm1
0x18003734a  add     r8, rdx
0x18003734d  sub     rcx, 1
0x180037351  jnz     short loc_180037301
0x180037353  movups  xmm0, xmmword ptr [rax]
0x180037356  mov     edx, [rsi]
0x180037358  movups  xmm1, xmmword ptr [rax+10h]
0x18003735c  movups  xmmword ptr [r8], xmm0
0x180037360  movups  xmm0, xmmword ptr [rax+20h]
0x180037364  mov     rax, [rax+30h]
0x180037368  movups  xmmword ptr [r8+10h], xmm1
0x18003736d  movups  xmmword ptr [r8+20h], xmm0
0x180037372  mov     [r8+30h], rax
0x180037376  btr     [rbp+0A0h+var_D8], 9
0x18003737b  add     edx, [rbp+0A0h+var_70]
0x18003737e  mov     [rbp+0A0h+var_60], rcx
0x180037382  mov     [rbp+0A0h+var_50], rcx
0x180037386  mov     [rbp+0A0h+var_58], ecx
0x180037389  cmp     edx, [rbp+0A0h+var_70]
0x18003738c  jb      loc_18003745D
0x180037392  mov     ebx, edx
0x180037394  shl     rbx, 4
0x180037398  mov     rcx, rbx; size
0x18003739b  call    MIDL_user_allocate
0x1800373a0  mov     rdi, rax
0x1800373a3  test    rax, rax
0x1800373a6  jnz     short loc_1800373B2
0x1800373a8  mov     ebx, 0C0000017h
0x1800373ad  jmp     loc_180037462
0x1800373b2  mov     r8, rbx; Size
0x1800373b5  xor     edx, edx; Val
0x1800373b7  mov     rcx, rdi; void *
0x1800373ba  call    memset_0
0x1800373bf  cmp     dword ptr [rsi], 0
0x1800373c2  jz      short loc_180037441
0x1800373c4  or      [rbp+0A0h+var_D8], 20h
0x1800373c8  xor     r10d, r10d
0x1800373cb  xor     ecx, ecx
0x1800373cd  cmp     [r14+110h], ecx
0x1800373d4  jbe     short loc_18003740B
0x1800373d6  mov     r8, [r14+118h]
0x1800373dd  mov     edx, ecx
0x1800373df  add     rdx, rdx
0x1800373e2  test    dword ptr [r8+rdx*8+8], 20000000h
0x1800373eb  jnz     short loc_180037400
0x1800373ed  movups  xmm0, xmmword ptr [r8+rdx*8]
0x1800373f2  mov     eax, r10d
0x1800373f5  add     rax, rax
0x1800373f8  inc     r10d
0x1800373fb  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180037400  inc     ecx
0x180037402  cmp     ecx, [r14+110h]
0x180037409  jb      short loc_1800373D6
0x18003740b  xor     r11d, r11d
0x18003740e  cmp     [rsi], r11d
0x180037411  jbe     short loc_180037439
0x180037413  mov     rax, [rsi+8]
0x180037417  mov     r9d, r10d
0x18003741a  inc     r10d
0x18003741d  add     r9, r9
0x180037420  mov     rcx, [rax+r11*8]
0x180037424  inc     r11d
0x180037427  mov     [rdi+r9*8], rcx
0x18003742b  mov     dword ptr [rdi+r9*8+8], 20000007h
0x180037434  cmp     r11d, [rsi]
0x180037437  jb      short loc_180037413
0x180037439  mov     [rbp+0A0h+var_68], rdi
0x18003743d  mov     [rbp+0A0h+var_70], r10d
0x180037441  mov     r8, r12; unsigned int *
0x180037444  lea     rcx, [rsp+1A0h+var_180]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x180037449  mov     rdx, r15; unsigned __int8 **
0x18003744c  call    ?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z; PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)
0x180037451  mov     rcx, rdi; hMem
0x180037454  mov     ebx, eax
0x180037456  call    DigestFreeMemory
0x18003745b  jmp     short loc_180037462
0x18003745d  mov     ebx, 0C0000095h
0x180037462  mov     eax, ebx
0x180037464  mov     rcx, [rbp+0A0h+var_40]
0x180037468  xor     rcx, rsp; StackCookie
0x18003746b  call    __security_check_cookie
0x180037470  add     rsp, 170h
0x180037477  pop     r15
0x180037479  pop     r14
0x18003747b  pop     r12
0x18003747d  pop     rdi
0x18003747e  pop     rsi
0x18003747f  pop     rbx
0x180037480  pop     rbp
0x180037481  retn
```
