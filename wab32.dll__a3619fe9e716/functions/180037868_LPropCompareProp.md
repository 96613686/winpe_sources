# LPropCompareProp

- ea: `0x180037868`
- end: `0x180037cc1`
- name: `LPropCompareProp`
- size: `1113`
- prototype: `LONG __stdcall(LPSPropValue lpSPropValueA, LPSPropValue lpSPropValueB)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020f00`
- `0x180021a70`
- `0x180021b54`
- `0x180022a40`
- `0x1800230f0`
- `0x1800372f0`

## callees

- `0x180037868`
- `0x180091e86`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x180037a91`
- `KERNEL32!CompareStringA` at `0x180037ca9`
- `KERNEL32!CompareStringA` at `0x180037a91`
- `KERNEL32!CompareStringA` at `0x180037ca9`
- `KERNEL32!CompareStringW` at `0x180037a5f`
- `KERNEL32!CompareStringW` at `0x180037c7e`
- `KERNEL32!CompareStringW` at `0x180037a5f`
- `KERNEL32!CompareStringW` at `0x180037c7e`

## pseudocode

```c
LONG __stdcall LPropCompareProp(LPSPropValue lpSPropValueA, LPSPropValue lpSPropValueB)
{
  unsigned int v4; // r12d
  unsigned int v5; // r15d
  LONG v6; // edi
  unsigned int ulPropTag; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  LPBYTE v12; // r8
  LPBYTE v13; // r9
  __int64 v14; // rax
  int v15; // ecx
  unsigned int v16; // ecx
  bool v17; // cf
  LONG result; // eax
  double v19; // xmm0_8
  double v20; // xmm1_8
  bool v21; // cc
  float v22; // xmm0_4
  float v23; // xmm1_4
  bool v24; // zf
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  LPBYTE v29; // r9
  LPBYTE v30; // r10
  unsigned int v31; // eax
  unsigned int v32; // ecx
  int v33; // eax
  unsigned int ulPropTag_low; // eax
  LONG v35; // ebx
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  float flt; // xmm0_4
  float v40; // xmm1_4
  bool v41; // cc
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  LONG l; // eax
  double dbl; // xmm0_8
  double v47; // xmm1_8
  LONG Hi; // eax
  unsigned int ul; // eax
  bool v50; // cf
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // edi
  size_t v56; // r8
  unsigned int v57; // r14d
  LPBYTE lpb; // rdx
  LPBYTE v59; // rcx
  unsigned int dwHighDateTime; // eax
  unsigned int v61; // eax
  int v62; // eax

  if ( (lpSPropValueA->ulPropTag & 0x1000) == 0 )
  {
    ulPropTag_low = LOWORD(lpSPropValueA->ulPropTag);
    if ( ulPropTag_low <= 0x14 )
    {
      if ( ulPropTag_low == 20 )
      {
        v35 = 0;
      }
      else
      {
        v35 = 0;
        if ( ulPropTag_low <= 5 )
        {
          if ( ulPropTag_low != 5 )
          {
            if ( !LOWORD(lpSPropValueA->ulPropTag) )
              return 0;
            v36 = ulPropTag_low - 1;
            if ( !v36 )
              return 0;
            v37 = v36 - 1;
            if ( !v37 )
              return lpSPropValueA->Value.i - lpSPropValueB->Value.i;
            v38 = v37 - 1;
            if ( v38 )
            {
              if ( v38 == 1 )
              {
                flt = lpSPropValueB->Value.flt;
                v40 = lpSPropValueA->Value.flt;
                if ( v40 != flt )
                {
                  v41 = flt <= v40;
                  goto LABEL_58;
                }
                return v35;
              }
              return 0;
            }
LABEL_67:
            l = lpSPropValueA->Value.l;
            if ( l != lpSPropValueB->Value.l )
            {
              v35 = -1;
              if ( l > lpSPropValueB->Value.l )
                return 1;
            }
            return v35;
          }
          goto LABEL_71;
        }
        v42 = ulPropTag_low - 6;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 3;
            if ( v44 )
            {
              if ( v44 == 1 )
              {
                LOBYTE(v35) = lpSPropValueB->Value.i != 0;
                return (lpSPropValueA->Value.i != 0) - v35;
              }
              return 0;
            }
            goto LABEL_67;
          }
LABEL_71:
          dbl = lpSPropValueB->Value.dbl;
          v47 = lpSPropValueA->Value.dbl;
          if ( v47 != dbl )
          {
            v41 = dbl <= v47;
LABEL_58:
            v35 = 1;
            if ( !v41 )
              return -1;
          }
          return v35;
        }
      }
      Hi = lpSPropValueA->Value.cur.Hi;
      if ( Hi != lpSPropValueB->Value.cur.Hi )
      {
        v35 = 1;
        if ( Hi < lpSPropValueB->Value.cur.Hi )
          return -1;
        return v35;
      }
      ul = lpSPropValueA->Value.ul;
      v50 = ul < lpSPropValueB->Value.l;
      if ( ul == lpSPropValueB->Value.l )
        return v35;
      return v50 ? -1 : 1;
    }
    v51 = ulPropTag_low - 30;
    if ( v51 )
    {
      v52 = v51 - 1;
      if ( v52 )
      {
        v53 = v52 - 33;
        if ( v53 )
        {
          v54 = v53 - 8;
          if ( !v54 )
            return memcmp_0(lpSPropValueA->Value.lpszA, lpSPropValueB->Value.lpszA, 0x10u);
          if ( v54 == 186 )
          {
            v55 = lpSPropValueB->Value.ul;
            v56 = v55;
            v57 = lpSPropValueA->Value.ul;
            lpb = lpSPropValueB->Value.bin.lpb;
            v59 = lpSPropValueA->Value.bin.lpb;
            if ( v57 < v55 )
              v56 = v57;
            result = memcmp_0(v59, lpb, v56);
            if ( result )
              return result;
            if ( v57 != v55 )
              return v57 < v55 ? -1 : 1;
          }
          return 0;
        }
        dwHighDateTime = lpSPropValueA->Value.ft.dwHighDateTime;
        v50 = dwHighDateTime < lpSPropValueB->Value.cur.Hi;
        if ( dwHighDateTime == lpSPropValueB->Value.cur.Hi )
        {
          v61 = lpSPropValueA->Value.ul;
          v50 = v61 < lpSPropValueB->Value.l;
          if ( v61 == lpSPropValueB->Value.l )
            return 0;
        }
        return v50 ? -1 : 1;
      }
      v62 = CompareStringW(0x400u, 0x10001u, lpSPropValueA->Value.lpszW, -1, lpSPropValueB->Value.lpszW, -1);
    }
    else
    {
      v62 = CompareStringA(0x400u, 0x30001u, lpSPropValueA->Value.lpszA, -1, lpSPropValueB->Value.lpszA, -1);
    }
    return v62 - 2;
  }
  v4 = lpSPropValueA->Value.ul;
  if ( v4 >= lpSPropValueB->Value.l )
    v4 = lpSPropValueB->Value.ul;
  v5 = 0;
  v6 = 1;
  while ( 1 )
  {
    if ( v5 >= v4 )
      return lpSPropValueA->Value.l - lpSPropValueB->Value.l;
    ulPropTag = (unsigned __int16)lpSPropValueA->ulPropTag;
    if ( ulPropTag > 0x1014 )
    {
      v25 = ulPropTag - 4126;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 33;
          if ( !v27 )
          {
            v12 = lpSPropValueA->Value.bin.lpb;
            v13 = lpSPropValueB->Value.bin.lpb;
            v14 = v5;
            v32 = *(_DWORD *)&v12[8 * v5 + 4];
            if ( v32 != *(_DWORD *)&v13[8 * v5 + 4] )
              return v32 < *(_DWORD *)&v13[8 * v5 + 4] ? -1 : 1;
            goto LABEL_14;
          }
          v28 = v27 - 8;
          if ( !v28 )
            goto LABEL_42;
          if ( v28 != 186 )
            return 0;
          v29 = lpSPropValueA->Value.bin.lpb;
          v30 = lpSPropValueB->Value.bin.lpb;
          v31 = *(_DWORD *)&v29[16 * v5];
          v17 = v31 < *(_DWORD *)&v30[16 * v5];
          if ( v31 == *(_DWORD *)&v30[16 * v5] )
            result = memcmp_0(*(const void **)&v29[16 * v5 + 8], *(const void **)&v30[16 * v5 + 8], v31);
          else
LABEL_15:
            result = v17 ? -1 : 1;
LABEL_28:
          v24 = result == 0;
LABEL_41:
          if ( !v24 )
            return result;
          goto LABEL_42;
        }
        v33 = CompareStringW(
                0x400u,
                0x10003u,
                *(PCNZWCH *)&lpSPropValueA->Value.bin.lpb[8 * v5],
                -1,
                *(PCNZWCH *)&lpSPropValueB->Value.bin.lpb[8 * v5],
                -1);
      }
      else
      {
        v33 = CompareStringA(
                0x400u,
                0x30003u,
                *(PCNZCH *)&lpSPropValueA->Value.bin.lpb[8 * v5],
                -1,
                *(PCNZCH *)&lpSPropValueB->Value.bin.lpb[8 * v5],
                -1);
      }
      v24 = v33 == 2;
      result = v33 - 2;
      goto LABEL_41;
    }
    if ( ulPropTag == 4116 )
      goto LABEL_13;
    v8 = ulPropTag - 4098;
    if ( !v8 )
    {
      if ( *(__int16 *)&lpSPropValueA->Value.bin.lpb[2 * v5] != *(__int16 *)&lpSPropValueB->Value.bin.lpb[2 * v5] )
        return *(__int16 *)&lpSPropValueA->Value.bin.lpb[2 * v5] - *(__int16 *)&lpSPropValueB->Value.bin.lpb[2 * v5];
      goto LABEL_42;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      if ( *(_DWORD *)&lpSPropValueA->Value.bin.lpb[4 * v5] != *(_DWORD *)&lpSPropValueB->Value.bin.lpb[4 * v5] )
        return *(_DWORD *)&lpSPropValueA->Value.bin.lpb[4 * v5] - *(_DWORD *)&lpSPropValueB->Value.bin.lpb[4 * v5];
      goto LABEL_42;
    }
    v10 = v9 - 1;
    if ( !v10 )
      break;
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        return 0;
LABEL_13:
      v12 = lpSPropValueA->Value.bin.lpb;
      v13 = lpSPropValueB->Value.bin.lpb;
      v14 = v5;
      v15 = *(_DWORD *)&v12[8 * v5 + 4];
      if ( v15 != *(_DWORD *)&v13[8 * v5 + 4] )
      {
        result = -1;
        if ( v15 >= *(_DWORD *)&v13[8 * v5 + 4] )
          return 1;
        return result;
      }
LABEL_14:
      v16 = *(_DWORD *)&v13[8 * v14];
      v17 = *(_DWORD *)&v12[8 * v14] < v16;
      if ( *(_DWORD *)&v12[8 * v14] != v16 )
        goto LABEL_15;
      result = 0;
      goto LABEL_28;
    }
    v19 = *(double *)&lpSPropValueA->Value.bin.lpb[8 * v5];
    v20 = *(double *)&lpSPropValueB->Value.bin.lpb[8 * v5];
    if ( v19 != v20 )
    {
      v21 = v20 <= v19;
      goto LABEL_20;
    }
LABEL_42:
    ++v5;
  }
  v22 = *(float *)&lpSPropValueA->Value.bin.lpb[4 * v5];
  v23 = *(float *)&lpSPropValueB->Value.bin.lpb[4 * v5];
  if ( v22 == v23 )
    goto LABEL_42;
  v21 = v23 <= v22;
LABEL_20:
  if ( !v21 )
    return -1;
  return v6;
}

```

## disassembly

```asm
0x180037868  push    rbx
0x18003786a  push    rbp
0x18003786b  push    rsi
0x18003786c  push    rdi
0x18003786d  push    r12
0x18003786f  push    r14
0x180037871  push    r15
0x180037873  sub     rsp, 30h
0x180037877  test    dword ptr [rcx], 1000h
0x18003787d  mov     rbp, rdx
0x180037880  mov     rsi, rcx
0x180037883  jz      loc_180037ABE
0x180037889  mov     r12d, [rcx+8]
0x18003788d  cmp     r12d, [rdx+8]
0x180037891  cmovnb  r12d, [rdx+8]
0x180037896  xor     ebx, ebx
0x180037898  mov     r15d, ebx
0x18003789b  or      r14d, 0FFFFFFFFh
0x18003789f  lea     edi, [rbx+1]
0x1800378a2  cmp     r15d, r12d
0x1800378a5  jnb     loc_180037AB3
0x1800378ab  mov     eax, [rsi]
0x1800378ad  movzx   eax, ax
0x1800378b0  cmp     eax, 1014h
0x1800378b5  ja      loc_1800379B6
0x1800378bb  jz      short loc_1800378E0
0x1800378bd  sub     eax, 1002h
0x1800378c2  jz      loc_18003798B
0x1800378c8  sub     eax, edi
0x1800378ca  jz      loc_18003796A
0x1800378d0  sub     eax, edi
0x1800378d2  jz      short loc_18003793C
0x1800378d4  sub     eax, edi
0x1800378d6  jz      short loc_180037915
0x1800378d8  cmp     eax, edi
0x1800378da  jnz     loc_180037C20
0x1800378e0  mov     r8, [rsi+10h]
0x1800378e4  mov     r9, [rbp+10h]
0x1800378e8  mov     eax, r15d
0x1800378eb  mov     ecx, [r8+rax*8+4]
0x1800378f0  cmp     ecx, [r9+rax*8+4]
0x1800378f5  jnz     loc_180037AA8
0x1800378fb  mov     ecx, [r9+rax*8]
0x1800378ff  cmp     [r8+rax*8], ecx
0x180037903  jz      loc_1800379AD
0x180037909  sbb     eax, eax
0x18003790b  and     eax, 0FFFFFFFEh
0x18003790e  add     eax, edi
0x180037910  jmp     loc_1800379AF
0x180037915  mov     rax, [rsi+10h]
0x180037919  mov     ecx, r15d
0x18003791c  movsd   xmm0, qword ptr [rax+rcx*8]
0x180037921  mov     rax, [rbp+10h]
0x180037925  movsd   xmm1, qword ptr [rax+rcx*8]
0x18003792a  ucomisd xmm0, xmm1
0x18003792e  jp      short loc_180037936
0x180037930  jz      loc_180037AA0
0x180037936  comisd  xmm1, xmm0
0x18003793a  jmp     short loc_18003795F
0x18003793c  mov     rax, [rsi+10h]
0x180037940  mov     ecx, r15d
0x180037943  movss   xmm0, dword ptr [rax+rcx*4]
0x180037948  mov     rax, [rbp+10h]
0x18003794c  movss   xmm1, dword ptr [rax+rcx*4]
0x180037951  ucomiss xmm0, xmm1
0x180037954  jp      short loc_18003795C
0x180037956  jz      loc_180037AA0
0x18003795c  comiss  xmm1, xmm0
0x18003795f  cmova   edi, r14d
0x180037963  mov     eax, edi
0x180037965  jmp     loc_180037CB2
0x18003796a  mov     rcx, [rsi+10h]
0x18003796e  mov     rax, [rbp+10h]
0x180037972  mov     edx, r15d
0x180037975  mov     r8d, [rcx+rdx*4]
0x180037979  sub     r8d, [rax+rdx*4]
0x18003797d  jz      loc_180037AA0
0x180037983  mov     eax, r8d
0x180037986  jmp     loc_180037CB2
0x18003798b  mov     rax, [rsi+10h]
0x18003798f  mov     ecx, r15d
0x180037992  movsx   edx, word ptr [rax+rcx*2]
0x180037996  mov     rax, [rbp+10h]
0x18003799a  movsx   ecx, word ptr [rax+rcx*2]
0x18003799e  sub     edx, ecx
0x1800379a0  jz      loc_180037AA0
0x1800379a6  mov     eax, edx
0x1800379a8  jmp     loc_180037CB2
0x1800379ad  mov     eax, ebx
0x1800379af  test    eax, eax
0x1800379b1  jmp     loc_180037A9A
0x1800379b6  sub     eax, 101Eh
0x1800379bb  jz      loc_180037A67
0x1800379c1  sub     eax, edi
0x1800379c3  jz      short loc_180037A35
0x1800379c5  sub     eax, 21h ; '!'
0x1800379c8  jz      short loc_180037A0E
0x1800379ca  sub     eax, 8
0x1800379cd  jz      loc_180037AA0
0x1800379d3  cmp     eax, 0BAh
0x1800379d8  jnz     loc_180037C20
0x1800379de  mov     r9, [rsi+10h]
0x1800379e2  mov     r10, [rbp+10h]
0x1800379e6  mov     ecx, r15d
0x1800379e9  add     rcx, rcx
0x1800379ec  mov     eax, [r9+rcx*8]
0x1800379f0  cmp     eax, [r10+rcx*8]
0x1800379f4  jnz     loc_180037909
0x1800379fa  mov     rdx, [r10+rcx*8+8]; Buf2
0x1800379ff  mov     r8d, eax; Size
0x180037a02  mov     rcx, [r9+rcx*8+8]; Buf1
0x180037a07  call    memcmp_0
0x180037a0c  jmp     short loc_1800379AF
0x180037a0e  mov     r8, [rsi+10h]
0x180037a12  mov     r9, [rbp+10h]
0x180037a16  mov     eax, r15d
0x180037a19  mov     ecx, [r8+rax*8+4]
0x180037a1e  cmp     ecx, [r9+rax*8+4]
0x180037a23  jz      loc_1800378FB
0x180037a29  sbb     eax, eax
0x180037a2b  and     eax, 0FFFFFFFEh
0x180037a2e  add     eax, edi
0x180037a30  jmp     loc_180037CB2
0x180037a35  mov     rax, [rbp+10h]
0x180037a39  mov     r9d, r14d; cchCount1
0x180037a3c  mov     r8, [rsi+10h]
0x180037a40  mov     edx, 10003h; dwCmpFlags
0x180037a45  mov     ecx, r15d
0x180037a48  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180037a4d  mov     rax, [rax+rcx*8]
0x180037a51  mov     r8, [r8+rcx*8]; lpString1
0x180037a55  mov     ecx, 400h; Locale
0x180037a5a  mov     [rsp+68h+lpString2], rax; lpString2
0x180037a5f  call    cs:__imp_CompareStringW
0x180037a65  jmp     short loc_180037A97
0x180037a67  mov     rax, [rbp+10h]
0x180037a6b  mov     r9d, r14d; cchCount1
0x180037a6e  mov     r8, [rsi+10h]
0x180037a72  mov     edx, 30003h; dwCmpFlags
0x180037a77  mov     ecx, r15d
0x180037a7a  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180037a7f  mov     rax, [rax+rcx*8]
0x180037a83  mov     r8, [r8+rcx*8]; lpString1
0x180037a87  mov     ecx, 400h; Locale
0x180037a8c  mov     [rsp+68h+lpString2], rax; lpString2
0x180037a91  call    cs:__imp_CompareStringA
0x180037a97  add     eax, 0FFFFFFFEh
0x180037a9a  jnz     loc_180037CB2
0x180037aa0  add     r15d, edi
0x180037aa3  jmp     loc_1800378A2
0x180037aa8  mov     eax, r14d
0x180037aab  cmovge  eax, edi
0x180037aae  jmp     loc_180037CB2
0x180037ab3  mov     eax, [rsi+8]
0x180037ab6  sub     eax, [rbp+8]
0x180037ab9  jmp     loc_180037CB2
0x180037abe  movzx   eax, word ptr [rcx]
0x180037ac1  cmp     eax, 14h
0x180037ac4  ja      loc_180037BC6
0x180037aca  jz      loc_180037B99
0x180037ad0  xor     ebx, ebx
0x180037ad2  cmp     eax, 5
0x180037ad5  ja      short loc_180037B33
0x180037ad7  jz      loc_180037B7D
0x180037add  test    eax, eax
0x180037adf  jz      loc_180037C20
0x180037ae5  sub     eax, 1
0x180037ae8  jz      loc_180037C20
0x180037aee  sub     eax, 1
0x180037af1  jz      short loc_180037B24
0x180037af3  sub     eax, 1
0x180037af6  jz      short loc_180037B62
0x180037af8  cmp     eax, 1
0x180037afb  jnz     loc_180037C20
0x180037b01  movss   xmm0, dword ptr [rdx+8]
0x180037b06  movss   xmm1, dword ptr [rcx+8]
0x180037b0b  ucomiss xmm1, xmm0
0x180037b0e  jp      short loc_180037B12
0x180037b10  jz      short loc_180037B76
0x180037b12  or      r14d, 0FFFFFFFFh
0x180037b16  comiss  xmm0, xmm1
0x180037b19  mov     ebx, 1
0x180037b1e  cmova   ebx, r14d
0x180037b22  jmp     short loc_180037B76
0x180037b24  movsx   eax, word ptr [rcx+8]
0x180037b28  movsx   ecx, word ptr [rdx+8]
0x180037b2c  sub     eax, ecx
0x180037b2e  jmp     loc_180037CB2
0x180037b33  sub     eax, 6
0x180037b36  jz      short loc_180037B9B
0x180037b38  sub     eax, 1
0x180037b3b  jz      short loc_180037B7D
0x180037b3d  sub     eax, 3
0x180037b40  jz      short loc_180037B62
0x180037b42  cmp     eax, 1
0x180037b45  jnz     loc_180037C20
0x180037b4b  cmp     [rcx+8], bx
0x180037b4f  mov     eax, ebx
0x180037b51  setnz   al
0x180037b54  cmp     [rdx+8], bx
0x180037b58  setnz   bl
0x180037b5b  sub     eax, ebx
0x180037b5d  jmp     loc_180037CB2
0x180037b62  mov     eax, [rcx+8]
0x180037b65  cmp     eax, [rdx+8]
0x180037b68  jz      short loc_180037B76
0x180037b6a  or      ebx, 0FFFFFFFFh
0x180037b6d  cmp     eax, [rdx+8]
0x180037b70  lea     edi, [rbx+2]
0x180037b73  cmovg   ebx, edi
0x180037b76  mov     eax, ebx
0x180037b78  jmp     loc_180037CB2
0x180037b7d  movsd   xmm0, qword ptr [rdx+8]
0x180037b82  movsd   xmm1, qword ptr [rcx+8]
0x180037b87  ucomisd xmm1, xmm0
0x180037b8b  jp      short loc_180037B8F
0x180037b8d  jz      short loc_180037B76
0x180037b8f  or      r14d, 0FFFFFFFFh
0x180037b93  comisd  xmm0, xmm1
0x180037b97  jmp     short loc_180037B19
0x180037b99  xor     ebx, ebx
0x180037b9b  mov     eax, [rcx+0Ch]
0x180037b9e  cmp     eax, [rdx+0Ch]
0x180037ba1  jnz     short loc_180037BB4
0x180037ba3  mov     eax, [rcx+8]
0x180037ba6  cmp     eax, [rdx+8]
0x180037ba9  jz      short loc_180037B76
0x180037bab  sbb     ebx, ebx
0x180037bad  and     ebx, 0FFFFFFFEh
0x180037bb0  inc     ebx
0x180037bb2  jmp     short loc_180037B76
0x180037bb4  or      r14d, 0FFFFFFFFh
0x180037bb8  mov     ebx, 1
0x180037bbd  cmp     eax, [rdx+0Ch]
0x180037bc0  cmovl   ebx, r14d
0x180037bc4  jmp     short loc_180037B76
0x180037bc6  sub     eax, 1Eh
0x180037bc9  jz      loc_180037C86
0x180037bcf  sub     eax, 1
0x180037bd2  jz      loc_180037C5B
0x180037bd8  sub     eax, 21h ; '!'
0x180037bdb  jz      short loc_180037C3C
0x180037bdd  sub     eax, 8
0x180037be0  jz      short loc_180037C27
0x180037be2  cmp     eax, 0BAh
0x180037be7  jnz     short loc_180037C20
0x180037be9  mov     edi, [rdx+8]
0x180037bec  mov     r8d, edi
0x180037bef  mov     r14d, [rcx+8]
0x180037bf3  cmp     r14d, edi
0x180037bf6  mov     rdx, [rdx+10h]; Buf2
0x180037bfa  mov     rcx, [rcx+10h]; Buf1
0x180037bfe  cmovb   r8d, r14d; Size
0x180037c02  call    memcmp_0
0x180037c07  test    eax, eax
0x180037c09  jnz     loc_180037CB2
0x180037c0f  cmp     r14d, edi
0x180037c12  jz      short loc_180037C20
0x180037c14  sbb     eax, eax
0x180037c16  and     eax, 0FFFFFFFEh
0x180037c19  inc     eax
0x180037c1b  jmp     loc_180037CB2
0x180037c20  xor     eax, eax
0x180037c22  jmp     loc_180037CB2
0x180037c27  mov     rdx, [rdx+8]; Buf2
0x180037c2b  mov     r8d, 10h; Size
0x180037c31  mov     rcx, [rcx+8]; Buf1
0x180037c35  call    memcmp_0
0x180037c3a  jmp     short loc_180037CB2
0x180037c3c  mov     eax, [rcx+0Ch]
0x180037c3f  cmp     eax, [rdx+0Ch]
0x180037c42  jnz     loc_180037BAB
0x180037c48  mov     eax, [rcx+8]
0x180037c4b  cmp     eax, [rdx+8]
0x180037c4e  jnz     loc_180037BAB
0x180037c54  xor     ebx, ebx
0x180037c56  jmp     loc_180037B76
0x180037c5b  mov     rax, [rdx+8]
0x180037c5f  or      r14d, 0FFFFFFFFh
0x180037c63  mov     r8, [rcx+8]; lpString1
0x180037c67  mov     r9d, r14d; cchCount1
0x180037c6a  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180037c6f  mov     edx, 10001h; dwCmpFlags
0x180037c74  mov     ecx, 400h; Locale
0x180037c79  mov     [rsp+68h+lpString2], rax; lpString2
0x180037c7e  call    cs:__imp_CompareStringW
0x180037c84  jmp     short loc_180037CAF
0x180037c86  mov     rax, [rdx+8]
0x180037c8a  or      r14d, 0FFFFFFFFh
0x180037c8e  mov     r8, [rcx+8]; lpString1
0x180037c92  mov     r9d, r14d; cchCount1
0x180037c95  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180037c9a  mov     edx, 30001h; dwCmpFlags
0x180037c9f  mov     ecx, 400h; Locale
0x180037ca4  mov     [rsp+68h+lpString2], rax; lpString2
0x180037ca9  call    cs:__imp_CompareStringA
0x180037caf  sub     eax, 2
0x180037cb2  add     rsp, 30h
0x180037cb6  pop     r15
0x180037cb8  pop     r14
  ... truncated ...
```
