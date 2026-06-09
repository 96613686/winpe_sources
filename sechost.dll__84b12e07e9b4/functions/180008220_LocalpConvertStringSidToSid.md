# LocalpConvertStringSidToSid

- ea: `0x180008220`
- end: `0x180008732`
- name: `LocalpConvertStringSidToSid`
- size: `1298`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180005d00`
- `0x180006540`
- `0x180006680`
- `0x180007fcc`
- `0x180008010`

## callees

- `0x180008220`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x180008332`
- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x180008332`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180008305`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180008305`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x1800082c2`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x1800084ef`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x1800082c2`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x1800084ef`
- `api-ms-win-core-crt-l1-1-0!iswctype` at `0x1800083fd`
- `api-ms-win-core-crt-l1-1-0!iswctype` at `0x1800083fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800085a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800085a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008644`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008644`

## pseudocode

```c
__int64 __fastcall LocalpConvertStringSidToSid(_WORD *a1, _QWORD *a2, wchar_t **a3)
{
  unsigned int v3; // esi
  wchar_t *v6; // rbx
  int v7; // r15d
  wchar_t *v8; // rbx
  wchar_t *v9; // rax
  int v10; // r8d
  unsigned __int64 v11; // rcx
  wchar_t *v12; // r13
  wchar_t *v13; // rbp
  wchar_t *v14; // rbx
  __int64 v15; // rdx
  char v16; // di
  unsigned __int64 v17; // rcx
  unsigned __int8 v18; // di
  _DWORD *v19; // rbx
  wchar_t *v20; // r13
  __int64 v21; // r14
  int v22; // r8d
  unsigned __int64 v23; // rcx
  unsigned int v25; // edi
  char *v26; // rax
  int v27; // eax
  wchar_t *v28; // rcx
  wchar_t *v29; // rbp
  __int64 v30; // rax
  size_t v31; // rsi
  wchar_t *v32; // rax
  int v33; // [rsp+20h] [rbp-268h]
  __int16 v34; // [rsp+24h] [rbp-264h]
  wchar_t *EndPtr; // [rsp+28h] [rbp-260h] BYREF
  wchar_t *v36; // [rsp+30h] [rbp-258h]
  unsigned int v37; // [rsp+38h] [rbp-250h]
  unsigned int v38; // [rsp+3Ch] [rbp-24Ch]
  char v39; // [rsp+40h] [rbp-248h] BYREF

  v3 = 0;
  EndPtr = 0;
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  if ( ((*a1 - 83) & 0xFFDF) != 0 || a1[1] != 45 )
    return 3221225592LL;
  v6 = a1 + 2;
  v7 = 10;
  if ( a1[2] == 48 && ((a1[3] - 88) & 0xFFDF) == 0 )
    v7 = 16;
  v37 = wcstoul(a1 + 2, &EndPtr, v7);
  if ( v37 > 0xFF )
    return 3221225592LL;
  if ( EndPtr == v6 )
    return 3221225592LL;
  if ( *EndPtr != 45 )
    return 3221225592LL;
  v8 = EndPtr + 1;
  if ( !EndPtr[1] )
    return 3221225592LL;
  v9 = wcschr(EndPtr + 1, 0x2Du);
  if ( !v9 || v9 == v8 )
    return 3221225592LL;
  v10 = *v8 != 48 || ((v8[1] - 88) & 0xFFDF) != 0 ? v7 : 16;
  v11 = _wcstoui64(v8, &EndPtr, v10);
  if ( v11 > 0xFFFFFFFFFFFFLL )
    return 3221225592LL;
  v12 = EndPtr;
  if ( EndPtr == v8 || *EndPtr != 45 || !EndPtr[1] )
    return 3221225592LL;
  HIBYTE(v34) = v11;
  v13 = 0;
  LOBYTE(v34) = BYTE1(v11);
  v14 = EndPtr;
  v38 = 0;
  v15 = 0x800120100000001LL;
  HIBYTE(v33) = BYTE2(v11);
  v36 = 0;
  BYTE2(v33) = BYTE3(v11);
  BYTE1(v33) = BYTE4(v11);
  v16 = 0;
  LOBYTE(v33) = BYTE5(v11);
  while ( 1 )
  {
    if ( !v14 )
      goto LABEL_39;
    if ( v16 == -1 )
    {
      v25 = -1073741675;
      *a3 = v14;
      v28 = 0;
      goto LABEL_68;
    }
    v17 = *v14;
    if ( (_DWORD)v17 != 45 )
      break;
    if ( *(v14 - 1) == 45 )
      goto LABEL_24;
    ++v16;
    if ( v14[1] == 48 )
    {
      v15 = 0x800120100000001LL;
      if ( ((v14[2] - 88) & 0xFFDF) == 0 )
        v14 += 2;
    }
LABEL_28:
    ++v14;
  }
  if ( (unsigned int)v17 <= 0x3B && _bittest64(&v15, v17) )
  {
LABEL_37:
    if ( *(v14 - 1) != 45 )
    {
      ++v16;
      *a3 = v14;
      goto LABEL_39;
    }
    v25 = -1073741704;
    *a3 = v14 - 1;
    v28 = 0;
LABEL_68:
    LocalFree(v28);
    return v25;
  }
LABEL_24:
  if ( v14[1] == 58 && (((_WORD)v17 - 71) & 0xFFF3) == 0 && (_DWORD)v17 != 75 )
    goto LABEL_37;
  if ( !iswctype(v17, 0x80u) )
  {
    v25 = -1073741704;
    *a3 = v14;
    v28 = 0;
    goto LABEL_68;
  }
  if ( *v14 != 68 || v14[1] != 58 )
  {
    v15 = 0x800120100000001LL;
    goto LABEL_28;
  }
  v29 = v12;
  v30 = v14 - v12;
  v31 = 2 * v30;
  if ( v30 < 256 )
  {
    v12 = (wchar_t *)&v39;
    goto LABEL_81;
  }
  v32 = (wchar_t *)LocalAlloc(0x40u, v31 + 2);
  v36 = v32;
  if ( !v32 )
  {
    v25 = -1073741801;
    v28 = 0;
    goto LABEL_68;
  }
  v12 = v32;
LABEL_81:
  memcpy_0(v12, v29, v31);
  v13 = v36;
  v12[v31 / 2] = 0;
  ++v16;
  *a3 = v14;
  v3 = 0;
LABEL_39:
  if ( v16 && (v18 = v16 - 1) != 0 )
  {
    v19 = LocalAlloc(0x40u, 4LL * v18);
    if ( v19 )
    {
      v20 = v12 + 1;
      v21 = 0x800320000000001LL;
      while ( v3 < v18 )
      {
        if ( *v20 != 48 || ((v20[1] - 88) & 0xFFDF) != 0 )
          v22 = v7;
        else
          v22 = 16;
        v19[v3] = wcstoul(v20, &EndPtr, v22);
        if ( EndPtr )
        {
          v23 = *EndPtr;
          if ( (unsigned int)v23 > 0x3B || !_bittest64(&v21, v23) )
          {
            if ( EndPtr[1] != 58
              || (LOWORD(v23) = v23 - 68, (unsigned __int16)v23 > 0xFu)
              || (v27 = 34825, !_bittest(&v27, v23)) )
            {
              v13 = v36;
              goto LABEL_52;
            }
          }
        }
        v20 = EndPtr + 1;
        ++v3;
      }
      v13 = v36;
      v26 = (char *)LocalAlloc(0x40u, 4LL * v18 + 12);
      *a2 = v26;
      if ( v26 )
      {
        *v26 = v37;
        *(_DWORD *)(v26 + 2) = v33;
        *((_WORD *)v26 + 3) = v34;
        v26[1] = v18;
        memcpy_0(v26 + 8, v19, 4LL * v18);
        v25 = v38;
      }
      else
      {
        v25 = -1073741801;
      }
    }
    else
    {
      v25 = -1073741801;
    }
  }
  else
  {
    v19 = 0;
LABEL_52:
    v25 = -1073741704;
  }
  LocalFree(v19);
  if ( v13 )
  {
    v28 = v13;
    goto LABEL_68;
  }
  return v25;
}

```

## disassembly

```asm
0x180008220  mov     r11, rsp
0x180008223  push    rsi
0x180008224  push    r12
0x180008226  push    r14
0x180008228  sub     rsp, 270h
0x18000822f  mov     rax, cs:__security_cookie
0x180008236  xor     rax, rsp
0x180008239  mov     [rsp+288h+var_48], rax
0x180008241  xor     esi, esi
0x180008243  mov     r14, r8
0x180008246  mov     [rsp+288h+EndPtr], rsi
0x18000824b  mov     r12, rdx
0x18000824e  test    rcx, rcx
0x180008251  jz      loc_180008522
0x180008257  test    rdx, rdx
0x18000825a  jz      loc_180008522
0x180008260  test    r8, r8
0x180008263  jz      loc_180008522
0x180008269  movzx   eax, word ptr [rcx]
0x18000826c  mov     [r11-28h], rdi
0x180008270  sub     ax, 53h ; 'S'
0x180008274  mov     [r11+20h], rbx
0x180008278  mov     edi, 0FFDFh
0x18000827d  mov     [r11-20h], rbp
0x180008281  mov     [r11-30h], r13
0x180008285  mov     [r11-38h], r15
0x180008289  test    di, ax
0x18000828c  jnz     loc_180008613
0x180008292  cmp     word ptr [rcx+2], 2Dh ; '-'
0x180008297  jnz     loc_180008613
0x18000829d  cmp     word ptr [rcx+4], 30h ; '0'
0x1800082a2  lea     rbx, [rcx+4]
0x1800082a6  mov     r15d, 0Ah
0x1800082ac  mov     ebp, 10h
0x1800082b1  jz      loc_18000869B
0x1800082b7  mov     r8d, r15d; Radix
0x1800082ba  lea     rdx, [rsp+288h+EndPtr]; EndPtr
0x1800082bf  mov     rcx, rbx; String
0x1800082c2  call    cs:__imp_wcstoul
0x1800082c8  mov     [rsp+288h+var_250], eax
0x1800082cc  cmp     eax, 0FFh
0x1800082d1  ja      loc_180008613
0x1800082d7  mov     rcx, [rsp+288h+EndPtr]
0x1800082dc  cmp     rcx, rbx
0x1800082df  jz      loc_180008613
0x1800082e5  cmp     word ptr [rcx], 2Dh ; '-'
0x1800082e9  jnz     loc_180008613
0x1800082ef  cmp     [rcx+2], si
0x1800082f3  lea     rbx, [rcx+2]
0x1800082f7  jz      loc_180008613
0x1800082fd  mov     edx, 2Dh ; '-'; Ch
0x180008302  mov     rcx, rbx; Str
0x180008305  call    cs:__imp_wcschr
0x18000830b  test    rax, rax
0x18000830e  jz      loc_180008613
0x180008314  cmp     rax, rbx
0x180008317  jz      loc_180008613
0x18000831d  cmp     word ptr [rbx], 30h ; '0'
0x180008321  jz      loc_1800085FA
0x180008327  mov     r8d, r15d; Radix
0x18000832a  lea     rdx, [rsp+288h+EndPtr]; EndPtr
0x18000832f  mov     rcx, rbx; String
0x180008332  call    cs:__imp__wcstoui64
0x180008338  mov     rcx, rax
0x18000833b  mov     rax, 0FFFFFFFFFFFFh
0x180008345  cmp     rcx, rax
0x180008348  ja      loc_180008613
0x18000834e  mov     r13, [rsp+288h+EndPtr]
0x180008353  cmp     r13, rbx
0x180008356  jz      loc_180008613
0x18000835c  cmp     word ptr [r13+0], 2Dh ; '-'
0x180008362  jnz     loc_180008613
0x180008368  cmp     [r13+2], si
0x18000836d  jz      loc_180008613
0x180008373  mov     rax, rcx
0x180008376  mov     byte ptr [rsp+288h+var_264+1], cl
0x18000837a  shr     rax, 8
0x18000837e  mov     rbp, rsi
0x180008381  mov     byte ptr [rsp+288h+var_264], al
0x180008385  mov     rbx, r13
0x180008388  mov     rax, rcx
0x18000838b  mov     [rsp+288h+var_24C], esi
0x18000838f  shr     rax, 10h
0x180008393  mov     rdx, 800120100000001h
0x18000839d  mov     byte ptr [rsp+288h+var_268+3], al
0x1800083a1  mov     r8d, 0FFF3h
0x1800083a7  mov     rax, rcx
0x1800083aa  mov     [rsp+288h+var_258], rsi
0x1800083af  shr     rax, 18h
0x1800083b3  mov     byte ptr [rsp+288h+var_268+2], al
0x1800083b7  mov     rax, rcx
0x1800083ba  shr     rax, 20h
0x1800083be  shr     rcx, 28h
0x1800083c2  mov     byte ptr [rsp+288h+var_268+1], al
0x1800083c6  xor     dil, dil
0x1800083c9  mov     byte ptr [rsp+288h+var_268], cl
0x1800083cd  nop     dword ptr [rax]
0x1800083d0  test    rbx, rbx
0x1800083d3  jz      loc_180008487
0x1800083d9  cmp     dil, 0FFh
0x1800083dd  jz      loc_180008719
0x1800083e3  movzx   ecx, word ptr [rbx]; C
0x1800083e6  cmp     ecx, 2Dh ; '-'
0x1800083e9  jnz     short loc_18000842B
0x1800083eb  cmp     [rbx-2], cx
0x1800083ef  jnz     short loc_180008438
0x1800083f1  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800083f6  jz      short loc_180008464
0x1800083f8  mov     edx, 80h; Type
0x1800083fd  call    cs:__imp_iswctype
0x180008403  test    eax, eax
0x180008405  jz      loc_18000870A
0x18000840b  cmp     word ptr [rbx], 44h ; 'D'
0x18000840f  jz      loc_18000864F
0x180008415  mov     r8d, 0FFF3h
0x18000841b  mov     rdx, 800120100000001h
0x180008425  add     rbx, 2
0x180008429  jmp     short loc_1800083D0
0x18000842b  cmp     ecx, 3Bh ; ';'
0x18000842e  ja      short loc_1800083F1
0x180008430  bt      rdx, rcx
0x180008434  jnb     short loc_1800083F1
0x180008436  jmp     short loc_180008472
0x180008438  inc     dil
0x18000843b  cmp     word ptr [rbx+2], 30h ; '0'
0x180008440  jnz     short loc_180008425
0x180008442  movzx   eax, word ptr [rbx+4]
0x180008446  mov     edx, 0FFDFh
0x18000844b  sub     ax, 58h ; 'X'
0x18000844f  test    dx, ax
0x180008452  mov     rdx, 800120100000001h
0x18000845c  jnz     short loc_180008425
0x18000845e  add     rbx, 4
0x180008462  jmp     short loc_180008425
0x180008464  lea     eax, [rcx-47h]
0x180008467  test    r8w, ax
0x18000846b  jnz     short loc_1800083F8
0x18000846d  cmp     ecx, 4Bh ; 'K'
0x180008470  jz      short loc_1800083F8
0x180008472  cmp     word ptr [rbx-2], 2Dh ; '-'
0x180008477  lea     rax, [rbx-2]
0x18000847b  jz      loc_1800086AF
0x180008481  inc     dil
0x180008484  mov     [r14], rbx
0x180008487  test    dil, dil
0x18000848a  jz      loc_180008529
0x180008490  sub     dil, 1
0x180008494  jz      loc_180008529
0x18000849a  movzx   edx, dil
0x18000849e  mov     ecx, 40h ; '@'; uFlags
0x1800084a3  shl     rdx, 2; uBytes
0x1800084a7  call    cs:__imp_LocalAlloc
0x1800084ad  mov     rbx, rax
0x1800084b0  test    rax, rax
0x1800084b3  jz      loc_180008728
0x1800084b9  add     r13, 2
0x1800084bd  movzx   ebp, dil
0x1800084c1  mov     r14, 800320000000001h
0x1800084cb  nop     dword ptr [rax+rax+00h]
0x1800084d0  cmp     esi, ebp
0x1800084d2  jnb     loc_18000858A
0x1800084d8  cmp     word ptr [r13+0], 30h ; '0'
0x1800084de  jz      loc_180008679
0x1800084e4  mov     r8d, r15d; Radix
0x1800084e7  lea     rdx, [rsp+288h+EndPtr]; EndPtr
0x1800084ec  mov     rcx, r13; String
0x1800084ef  call    cs:__imp_wcstoul
0x1800084f5  mov     ecx, esi
0x1800084f7  mov     [rbx+rcx*4], eax
0x1800084fa  mov     rdx, [rsp+288h+EndPtr]
0x1800084ff  test    rdx, rdx
0x180008502  jz      short loc_18000851A
0x180008504  movzx   ecx, word ptr [rdx]
0x180008507  cmp     ecx, 3Bh ; ';'
0x18000850a  ja      loc_1800085E9
0x180008510  bt      r14, rcx
0x180008514  jnb     loc_1800085E9
0x18000851a  lea     r13, [rdx+2]
0x18000851e  inc     esi
0x180008520  jmp     short loc_1800084D0
0x180008522  mov     eax, 0C000000Dh
0x180008527  jmp     short loc_18000856D
0x180008529  mov     rbx, rsi
0x18000852c  mov     edi, 0C0000078h
0x180008531  mov     rcx, rbx; hMem
0x180008534  call    cs:__imp_LocalFree
0x18000853a  test    rbp, rbp
0x18000853d  jnz     loc_180008641
0x180008543  mov     eax, edi
0x180008545  mov     r13, [rsp+288h+var_30]
0x18000854d  mov     rbx, [rsp+288h+arg_18]
0x180008555  mov     rbp, [rsp+288h+var_20]
0x18000855d  mov     r15, [rsp+288h+var_38]
0x180008565  mov     rdi, [rsp+288h+var_28]
0x18000856d  mov     rcx, [rsp+288h+var_48]
0x180008575  xor     rcx, rsp; StackCookie
0x180008578  call    __security_check_cookie
0x18000857d  add     rsp, 270h
0x180008584  pop     r14
0x180008586  pop     r12
0x180008588  pop     rsi
0x180008589  retn
0x18000858a  mov     rbp, [rsp+288h+var_258]
0x18000858f  mov     ecx, 40h ; '@'; uFlags
0x180008594  movzx   esi, dil
0x180008598  lea     rdx, ds:0Ch[rsi*4]; uBytes
0x1800085a0  call    cs:__imp_LocalAlloc
0x1800085a6  mov     [r12], rax
0x1800085aa  mov     rcx, rax
0x1800085ad  test    rax, rax
0x1800085b0  jz      short loc_18000861D
0x1800085b2  mov     eax, [rsp+288h+var_250]
0x1800085b6  lea     r8, ds:0[rsi*4]; Size
0x1800085be  mov     [rcx], al
0x1800085c0  mov     rdx, rbx; Src
0x1800085c3  mov     eax, [rsp+288h+var_268]
0x1800085c7  mov     [rcx+2], eax
0x1800085ca  movzx   eax, [rsp+288h+var_264]
0x1800085cf  mov     [rcx+6], ax
0x1800085d3  mov     [rcx+1], dil
0x1800085d7  add     rcx, 8; void *
0x1800085db  call    memcpy_0
0x1800085e0  mov     edi, [rsp+288h+var_24C]
0x1800085e4  jmp     loc_180008531
0x1800085e9  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1800085ee  jz      short loc_180008627
0x1800085f0  mov     rbp, [rsp+288h+var_258]
0x1800085f5  jmp     loc_18000852C
0x1800085fa  movzx   eax, word ptr [rbx+2]
0x1800085fe  sub     ax, 58h ; 'X'
0x180008602  test    di, ax
0x180008605  jnz     loc_180008327
0x18000860b  mov     r8d, ebp
0x18000860e  jmp     loc_18000832A
0x180008613  mov     eax, 0C0000078h
0x180008618  jmp     loc_180008545
0x18000861d  mov     edi, 0C0000017h
0x180008622  jmp     loc_180008531
0x180008627  sub     cx, 44h ; 'D'
0x18000862b  cmp     cx, 0Fh
0x18000862f  ja      short loc_1800085F0
0x180008631  mov     eax, 8809h
0x180008636  bt      eax, ecx
0x180008639  jb      loc_18000851A
0x18000863f  jmp     short loc_1800085F0
0x180008641  mov     rcx, rbp; hMem
0x180008644  call    cs:__imp_LocalFree
0x18000864a  jmp     loc_180008543
0x18000864f  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180008654  jnz     loc_180008415
0x18000865a  mov     rax, rbx
0x18000865d  mov     rbp, r13
0x180008660  sub     rax, r13
0x180008663  sar     rax, 1
0x180008666  lea     rsi, [rax+rax]
0x18000866a  cmp     rax, 100h
0x180008670  jge     short loc_1800086BB
0x180008672  lea     r13, [rsp+288h+var_248]
0x180008677  jmp     short loc_1800086E3
0x180008679  movzx   eax, word ptr [r13+2]
0x18000867e  mov     ecx, 0FFDFh
0x180008683  sub     ax, 58h ; 'X'
0x180008687  test    cx, ax
0x18000868a  jnz     loc_1800084E4
0x180008690  mov     r8d, 10h
0x180008696  jmp     loc_1800084E7
0x18000869b  movzx   eax, word ptr [rbx+2]
0x18000869f  sub     ax, 58h ; 'X'
0x1800086a3  test    di, ax
0x1800086a6  cmovz   r15d, ebp
0x1800086aa  jmp     loc_1800082B7
0x1800086af  mov     edi, 0C0000078h
0x1800086b4  mov     [r14], rax
0x1800086b7  xor     ecx, ecx
0x1800086b9  jmp     short loc_180008644
0x1800086bb  lea     rdx, [rsi+2]; uBytes
0x1800086bf  mov     ecx, 40h ; '@'; uFlags
0x1800086c4  call    cs:__imp_LocalAlloc
0x1800086ca  mov     [rsp+288h+var_258], rax
0x1800086cf  test    rax, rax
0x1800086d2  jnz     short loc_1800086E0
0x1800086d4  mov     edi, 0C0000017h
0x1800086d9  xor     ecx, ecx
0x1800086db  jmp     loc_180008644
0x1800086e0  mov     r13, rax
0x1800086e3  mov     r8, rsi; Size
0x1800086e6  mov     rdx, rbp; Src
0x1800086e9  mov     rcx, r13; void *
0x1800086ec  call    memcpy_0
0x1800086f1  mov     rbp, [rsp+288h+var_258]
0x1800086f6  xor     eax, eax
0x1800086f8  mov     [rsi+r13], ax
0x1800086fd  inc     dil
0x180008700  mov     [r14], rbx
0x180008703  xor     esi, esi
0x180008705  jmp     loc_180008487
0x18000870a  mov     edi, 0C0000078h
0x18000870f  mov     [r14], rbx
0x180008712  xor     ecx, ecx
0x180008714  jmp     loc_180008644
  ... truncated ...
```
