# OneXSetEapUserData

- ea: `0x1801b2614`
- end: `0x1801b28e9`
- name: `OneXSetEapUserData`
- size: `725`
- prototype: `__int64 __fastcall(void *, __int64, __int128 *, unsigned int, void *Src, _OWORD *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012a8c0`
- `0x1801ad7bc`
- `0x1802097c8`

## callees

- `0x1800e0c6c`
- `0x1800e0ca4`
- `0x180107318`
- `0x1801b219c`
- `0x1801b2348`
- `0x1801b2614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2855`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801b284b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801b284b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801b26ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801b26ec`
- `MobileNetworking!FreeMemory` at `0x1801b28a9`
- `MobileNetworking!FreeMemory` at `0x1801b28c9`
- `MobileNetworking!FreeMemory` at `0x1801b28a9`
- `MobileNetworking!FreeMemory` at `0x1801b28c9`

## pseudocode

```c
__int64 __fastcall OneXSetEapUserData(
        void *a1,
        __int64 a2,
        __int128 *a3,
        unsigned int a4,
        void *Src,
        _OWORD *a6,
        unsigned int *a7)
{
  unsigned int *v7; // r15
  __int64 v8; // rsi
  size_t v9; // r13
  void *v10; // r8
  DWORD v11; // eax
  DWORD AlignedSize; // ebx
  unsigned int LengthSid; // ebp
  int v14; // r14d
  PSID v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // edi
  _OWORD *v18; // rdi
  _DWORD *v19; // r15
  char *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned int v23; // r10d
  bool v24; // zf
  char *v25; // r9
  __int128 *v26; // r8
  __int128 v27; // xmm0
  unsigned int *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rax
  void *v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rcx
  unsigned int *v34; // rdx
  PSID *v36; // [rsp+20h] [rbp-48h] BYREF
  __int64 v37[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v39; // [rsp+78h] [rbp+10h] BYREF
  __int128 *v40; // [rsp+80h] [rbp+18h]

  v40 = a3;
  v39 = a2;
  v7 = a7;
  v8 = 0;
  v9 = a4;
  v10 = a1;
  v37[0] = 0;
  v36 = 0;
  if ( !a7 )
  {
    AlignedSize = 87;
    goto LABEL_38;
  }
  if ( a2 )
  {
    v8 = a2;
LABEL_6:
    LengthSid = 0;
    v14 = 0;
    v15 = 0;
    v16 = 64;
    if ( !Src || !(_DWORD)v9 )
      goto LABEL_17;
    v14 = v9 + 20;
    if ( (unsigned int)v9 < 0xFFFFFFEC && (int)v9 + 27 >= (unsigned int)(v9 + 20) )
    {
      v17 = ((v9 + 27) & 0xFFFFFFF8) + 64;
      if ( v17 >= 0x40 )
      {
        if ( v10 )
        {
          AlignedSize = OneXGetTokenInformation(v10);
          if ( AlignedSize )
            goto LABEL_38;
          v15 = *v36;
          LengthSid = GetLengthSid(*v36);
        }
        else
        {
          LengthSid = *(_DWORD *)(v8 + 20);
          v15 = (PSID)(v8 + *(unsigned int *)(v8 + 24));
        }
        if ( LengthSid + 7 >= LengthSid )
        {
          v16 = v17 + ((LengthSid + 7) & 0xFFFFFFF8);
          if ( v16 >= v17 )
          {
LABEL_17:
            v18 = a6;
            if ( !a6 )
            {
              *v7 = v16;
              AlignedSize = 234;
              goto LABEL_38;
            }
            if ( *v7 < v16 )
            {
              *v7 = v16;
              AlignedSize = 122;
              goto LABEL_38;
            }
            v19 = (_DWORD *)a6 + 3;
            v20 = (char *)a6 + 12;
            *a6 = *(_OWORD *)v8;
            v18[1] = *(_OWORD *)(v8 + 16);
            v18[2] = *(_OWORD *)(v8 + 32);
            v18[3] = *(_OWORD *)(v8 + 48);
            v21 = *((unsigned int *)v18 + 4);
            *((_DWORD *)v18 + 1) = v16;
            AlignedSize = GetAlignedSize(32, v20, v21);
            if ( AlignedSize )
              goto LABEL_38;
            if ( (unsigned int)(*v19 + v14) >= *v19 )
            {
              v24 = Src == 0;
              v25 = (char *)v18 + v22;
              *v19 += v14;
              if ( v24 || !(_DWORD)v9 )
              {
                *(_DWORD *)v25 &= ~1u;
                AlignedSize = GetAlignedSize(v23, v25 + 28, v22);
                if ( AlignedSize )
                  goto LABEL_38;
                *(_DWORD *)(v32 + 24) = 0;
                *(_OWORD *)(v32 + 4) = 0;
              }
              else
              {
                v26 = v40;
                *(_DWORD *)v25 |= 1u;
                v27 = *v26;
                *(_OWORD *)(v25 + 4) = *v26;
                AlignedSize = GetAlignedSize(v23, v25 + 28, v26);
                if ( AlignedSize )
                  goto LABEL_38;
                v30 = *v28;
                v31 = Src;
                *(_DWORD *)(v29 + 24) = v14;
                *(_DWORD *)(v30 + v29 + 16) = v9;
                *(_OWORD *)(v30 + v29) = v27;
                memcpy_0((void *)(v30 + v29 + 20), v31, v9);
              }
              v33 = (unsigned int)*v19;
              *((_DWORD *)v18 + 6) = *((_DWORD *)v18 + 4);
              AlignedSize = IncrementDwordByAlignedSize(v33);
              if ( !AlignedSize )
              {
                if ( LengthSid )
                {
                  if ( CopySid(LengthSid, (char *)v18 + *v34, v15) || (AlignedSize = GetLastError()) == 0 )
                  {
                    *((_DWORD *)v18 + 2) |= 1u;
                    *((_DWORD *)v18 + 5) = LengthSid;
                  }
                }
                else
                {
                  *((_DWORD *)v18 + 2) &= ~1u;
                  *((_DWORD *)v18 + 5) = 0;
                }
              }
LABEL_38:
              if ( v39 )
                goto LABEL_40;
              goto LABEL_39;
            }
            *v19 = -1;
          }
        }
      }
    }
    AlignedSize = 534;
    goto LABEL_38;
  }
  v11 = OneXCreateDefaultUserProfile(v37, 0, a1);
  v8 = v37[0];
  AlignedSize = v11;
  if ( !v11 )
  {
    v10 = a1;
    goto LABEL_6;
  }
LABEL_39:
  v39 = v8;
  FreeMemory(&v39, "OneXFreeUserProfile", 84);
LABEL_40:
  if ( v36 )
    FreeMemory(&v36, "OneXSetEapUserData", 766);
  return AlignedSize;
}

```

## disassembly

```asm
0x1801b2614  mov     rax, rsp
0x1801b2617  mov     [rax+20h], rbx
0x1801b261b  mov     [rax+18h], r8
0x1801b261f  mov     [rax+10h], rdx
0x1801b2623  mov     [rax+8], rcx
0x1801b2627  push    rbp
0x1801b2628  push    rsi
0x1801b2629  push    rdi
0x1801b262a  push    r12
0x1801b262c  push    r13
0x1801b262e  push    r14
0x1801b2630  push    r15
0x1801b2632  sub     rsp, 30h
0x1801b2636  mov     r15, [rsp+68h+arg_30]
0x1801b263e  xor     esi, esi
0x1801b2640  mov     r13d, r9d
0x1801b2643  mov     r8, rcx
0x1801b2646  mov     [rax-40h], rsi
0x1801b264a  mov     [rax-48h], rsi
0x1801b264e  test    r15, r15
0x1801b2651  jz      loc_1801B2885
0x1801b2657  test    rdx, rdx
0x1801b265a  jnz     short loc_1801B267B
0x1801b265c  lea     rcx, [rax-40h]
0x1801b2660  call    OneXCreateDefaultUserProfile
0x1801b2665  mov     rsi, [rsp+68h+var_40]
0x1801b266a  mov     ebx, eax
0x1801b266c  test    eax, eax
0x1801b266e  jnz     loc_1801B2892
0x1801b2674  mov     r8, [rsp+68h+TokenHandle]
0x1801b2679  jmp     short loc_1801B267E
0x1801b267b  mov     rsi, rdx
0x1801b267e  xor     ebp, ebp
0x1801b2680  xor     r14d, r14d
0x1801b2683  xor     r12d, r12d
0x1801b2686  lea     eax, [rbp+40h]
0x1801b2689  cmp     [rsp+68h+Src], rbp
0x1801b2691  jz      loc_1801B2718
0x1801b2697  test    r13d, r13d
0x1801b269a  jz      short loc_1801B2718
0x1801b269c  lea     r14d, [r13+14h]
0x1801b26a0  cmp     r14d, 14h
0x1801b26a4  jb      loc_1801B287E
0x1801b26aa  lea     ecx, [r14+7]
0x1801b26ae  cmp     ecx, r14d
0x1801b26b1  jb      loc_1801B287E
0x1801b26b7  and     ecx, 0FFFFFFF8h
0x1801b26ba  lea     edi, [rcx+40h]
0x1801b26bd  cmp     edi, eax
0x1801b26bf  jb      loc_1801B287E
0x1801b26c5  test    r8, r8
0x1801b26c8  jz      short loc_1801B26F6
0x1801b26ca  lea     rdx, [rsp+68h+var_48]
0x1801b26cf  mov     rcx, r8; TokenHandle
0x1801b26d2  call    OneXGetTokenInformation
0x1801b26d7  mov     ebx, eax
0x1801b26d9  test    eax, eax
0x1801b26db  jnz     loc_1801B288A
0x1801b26e1  mov     rax, [rsp+68h+var_48]
0x1801b26e6  mov     r12, [rax]
0x1801b26e9  mov     rcx, r12; pSid
0x1801b26ec  call    cs:__imp_GetLengthSid
0x1801b26f2  mov     ebp, eax
0x1801b26f4  jmp     short loc_1801B2700
0x1801b26f6  mov     r12d, [rsi+18h]
0x1801b26fa  mov     ebp, [rsi+14h]
0x1801b26fd  add     r12, rsi
0x1801b2700  lea     eax, [rbp+7]
0x1801b2703  cmp     eax, ebp
0x1801b2705  jb      loc_1801B287E
0x1801b270b  and     eax, 0FFFFFFF8h
0x1801b270e  add     eax, edi
0x1801b2710  cmp     eax, edi
0x1801b2712  jb      loc_1801B287E
0x1801b2718  mov     rdi, [rsp+68h+arg_28]
0x1801b2720  test    rdi, rdi
0x1801b2723  jnz     short loc_1801B2732
0x1801b2725  mov     [r15], eax
0x1801b2728  mov     ebx, 0EAh
0x1801b272d  jmp     loc_1801B288A
0x1801b2732  cmp     [r15], eax
0x1801b2735  jnb     short loc_1801B2744
0x1801b2737  mov     [r15], eax
0x1801b273a  mov     ebx, 7Ah ; 'z'
0x1801b273f  jmp     loc_1801B288A
0x1801b2744  movups  xmm0, xmmword ptr [rsi]
0x1801b2747  lea     r15, [rdi+0Ch]
0x1801b274b  mov     r10d, 20h ; ' '
0x1801b2751  mov     rdx, r15
0x1801b2754  mov     ecx, r10d
0x1801b2757  movups  xmmword ptr [rdi], xmm0
0x1801b275a  movups  xmm1, xmmword ptr [rsi+10h]
0x1801b275e  movups  xmmword ptr [rdi+10h], xmm1
0x1801b2762  movups  xmm0, xmmword ptr [rsi+20h]
0x1801b2766  movups  xmmword ptr [rdi+20h], xmm0
0x1801b276a  movups  xmm1, xmmword ptr [rsi+30h]
0x1801b276e  movups  xmmword ptr [rdi+30h], xmm1
0x1801b2772  mov     r8d, [rdi+10h]
0x1801b2776  mov     [rdi+4], eax
0x1801b2779  call    GetAlignedSize
0x1801b277e  mov     ebx, eax
0x1801b2780  test    eax, eax
0x1801b2782  jnz     loc_1801B288A
0x1801b2788  mov     eax, [r15]
0x1801b278b  lea     ecx, [rax+r14]
0x1801b278f  cmp     ecx, eax
0x1801b2791  jb      loc_1801B2877
0x1801b2797  cmp     [rsp+68h+Src], 0
0x1801b27a0  lea     r9, [rdi+r8]
0x1801b27a4  mov     [r15], ecx
0x1801b27a7  jz      short loc_1801B2804
0x1801b27a9  test    r13d, r13d
0x1801b27ac  jz      short loc_1801B2804
0x1801b27ae  mov     r8, [rsp+68h+arg_10]
0x1801b27b6  lea     rdx, [r9+1Ch]
0x1801b27ba  or      dword ptr [r9], 1
0x1801b27be  mov     ecx, r10d
0x1801b27c1  movaps  xmm0, xmmword ptr [r8]
0x1801b27c5  movdqu  xmmword ptr [r9+4], xmm0
0x1801b27cb  call    GetAlignedSize
0x1801b27d0  mov     ebx, eax
0x1801b27d2  test    eax, eax
0x1801b27d4  jnz     loc_1801B288A
0x1801b27da  mov     eax, [rdx]
0x1801b27dc  lea     rcx, [r9+14h]
0x1801b27e0  mov     rdx, [rsp+68h+Src]; Src
0x1801b27e8  mov     r8, r13; Size
0x1801b27eb  mov     [r9+18h], r14d
0x1801b27ef  add     rcx, rax; void *
0x1801b27f2  mov     [rax+r9+10h], r13d
0x1801b27f7  movdqu  xmmword ptr [rax+r9], xmm0
0x1801b27fd  call    memcpy_0
0x1801b2802  jmp     short loc_1801B2826
0x1801b2804  and     dword ptr [r9], 0FFFFFFFEh
0x1801b2808  lea     rdx, [r9+1Ch]
0x1801b280c  mov     ecx, r10d
0x1801b280f  call    GetAlignedSize
0x1801b2814  mov     ebx, eax
0x1801b2816  test    eax, eax
0x1801b2818  jnz     short loc_1801B288A
0x1801b281a  xorps   xmm0, xmm0
0x1801b281d  mov     [r9+18h], eax
0x1801b2821  movups  xmmword ptr [r9+4], xmm0
0x1801b2826  mov     eax, [rdi+10h]
0x1801b2829  lea     rdx, [rdi+18h]
0x1801b282d  mov     ecx, [r15]
0x1801b2830  mov     [rdx], eax
0x1801b2832  call    IncrementDwordByAlignedSize
0x1801b2837  mov     ebx, eax
0x1801b2839  test    eax, eax
0x1801b283b  jnz     short loc_1801B288A
0x1801b283d  test    ebp, ebp
0x1801b283f  jz      short loc_1801B286A
0x1801b2841  mov     edx, [rdx]
0x1801b2843  mov     r8, r12; pSourceSid
0x1801b2846  add     rdx, rdi; pDestinationSid
0x1801b2849  mov     ecx, ebp; nDestinationSidLength
0x1801b284b  call    cs:__imp_CopySid
0x1801b2851  test    eax, eax
0x1801b2853  jnz     short loc_1801B2861
0x1801b2855  call    cs:__imp_GetLastError
0x1801b285b  mov     ebx, eax
0x1801b285d  test    eax, eax
0x1801b285f  jnz     short loc_1801B288A
0x1801b2861  or      dword ptr [rdi+8], 1
0x1801b2865  mov     [rdi+14h], ebp
0x1801b2868  jmp     short loc_1801B288A
0x1801b286a  and     dword ptr [rdi+8], 0FFFFFFFEh
0x1801b286e  mov     dword ptr [rdi+14h], 0
0x1801b2875  jmp     short loc_1801B288A
0x1801b2877  mov     dword ptr [r15], 0FFFFFFFFh
0x1801b287e  mov     ebx, 216h
0x1801b2883  jmp     short loc_1801B288A
0x1801b2885  mov     ebx, 57h ; 'W'
0x1801b288a  cmp     [rsp+68h+arg_8], 0
0x1801b2890  jnz     short loc_1801B28AF
0x1801b2892  mov     r8d, 54h ; 'T'
0x1801b2898  mov     [rsp+68h+arg_8], rsi
0x1801b289d  lea     rdx, aOnexfreeuserpr; "OneXFreeUserProfile"
0x1801b28a4  lea     rcx, [rsp+68h+arg_8]
0x1801b28a9  call    cs:__imp_FreeMemory
0x1801b28af  cmp     [rsp+68h+var_48], 0
0x1801b28b5  jz      short loc_1801B28CF
0x1801b28b7  mov     r8d, 2FEh
0x1801b28bd  lea     rdx, aOnexseteapuser; "OneXSetEapUserData"
0x1801b28c4  lea     rcx, [rsp+68h+var_48]
0x1801b28c9  call    cs:__imp_FreeMemory
0x1801b28cf  mov     eax, ebx
0x1801b28d1  mov     rbx, [rsp+68h+arg_18]
0x1801b28d9  add     rsp, 30h
0x1801b28dd  pop     r15
0x1801b28df  pop     r14
0x1801b28e1  pop     r13
0x1801b28e3  pop     r12
0x1801b28e5  pop     rdi
0x1801b28e6  pop     rsi
0x1801b28e7  pop     rbp
0x1801b28e8  retn
```
