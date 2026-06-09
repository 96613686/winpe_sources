# DavCreateUrlCacheEntry

- ea: `0x180019454`
- end: `0x1800196c7`
- name: `DavCreateUrlCacheEntry`
- size: `627`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001507c`
- `0x180016d24`
- `0x18001832c`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b81c`
- `0x18000b93c`
- `0x180019454`
- `0x18002a964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001959c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001959c`
- `KERNEL32!LocalFree` at `0x18001962c`
- `KERNEL32!LocalFree` at `0x18001962c`
- `KERNEL32!LocalAlloc` at `0x18001958e`
- `KERNEL32!LocalAlloc` at `0x18001958e`

## pseudocode

```c
__int64 __fastcall DavCreateUrlCacheEntry(__int64 a1)
{
  _WORD *v1; // rdx
  __int64 v3; // rax
  _WORD *v4; // rax
  const wchar_t *v5; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rcx
  wchar_t *v10; // rbp
  DWORD LastError; // eax
  unsigned int v12; // edi
  _WORD *v13; // rdx
  _WORD *v14; // rax
  __int64 v15; // rcx
  _WORD *v16; // rcx
  unsigned int v18; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_WORD **)(a1 + 568);
  if ( !*v1 )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v7 = 232;
LABEL_21:
    WPP_SF_(v6[2], v7, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
LABEL_22:
    v6 = WPP_GLOBAL_Control;
LABEL_23:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_S(v6[2], 233, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v5);
    goto LABEL_26;
  }
  v3 = -1;
  do
    ++v3;
  while ( v1[v3] );
  v4 = &v1[v3 - 1];
  if ( v4 == v1 )
  {
LABEL_15:
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v7 = 231;
    goto LABEL_21;
  }
  while ( *v4 != 46 )
  {
    if ( *v4 != 47 && *v4 != 92 && --v4 != v1 )
      continue;
    if ( v4 == v1 || *v4 != 46 )
      goto LABEL_15;
    break;
  }
  v5 = v4 + 1;
  if ( !v4[1] )
    goto LABEL_15;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v4 + 1);
    goto LABEL_22;
  }
LABEL_26:
  v8 = 260;
  v18 = 260;
  v10 = (wchar_t *)LocalAlloc(0x40u, 0x208u);
  if ( v10 )
  {
    v12 = TfsCreateEntry(v9, *(const wchar_t **)(a1 + 584), v5, v10, &v18);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          235,
          (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          v12,
          *(_QWORD *)(a1 + 584));
      LocalFree(v10);
      *(_QWORD *)(a1 + 576) = 0;
    }
    else
    {
      *(_QWORD *)(a1 + 576) = v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v10);
      v13 = *(_WORD **)(a1 + 576);
      v14 = (_WORD *)(a1 + 2312);
      v15 = 2147483646;
      do
      {
        if ( !v15 )
          break;
        if ( !*v13 )
          break;
        *v14++ = *v13++;
        --v15;
        --v8;
      }
      while ( v8 );
      v16 = v14 - 1;
      if ( v8 )
        v16 = v14;
      *v16 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
  }
  return v12;
}

```

## disassembly

```asm
0x180019454  mov     [rsp+arg_8], rbx
0x180019459  mov     [rsp+arg_10], rbp
0x18001945e  push    rsi
0x18001945f  push    rdi
0x180019460  push    r12
0x180019462  push    r14
0x180019464  push    r15
0x180019466  sub     rsp, 30h
0x18001946a  mov     rdx, [rcx+238h]
0x180019471  lea     r12, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180019478  xor     r15d, r15d
0x18001947b  mov     r14, rcx
0x18001947e  cmp     [rdx], r15w
0x180019482  jz      loc_180019528
0x180019488  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001948c  inc     rax
0x18001948f  cmp     [rdx+rax*2], r15w
0x180019494  jnz     short loc_18001948C
0x180019496  dec     rax
0x180019499  lea     rax, [rdx+rax*2]
0x18001949d  cmp     rax, rdx
0x1800194a0  jz      short loc_180019505
0x1800194a2  cmp     word ptr [rax], 2Eh ; '.'
0x1800194a6  jz      short loc_1800194C8
0x1800194a8  cmp     word ptr [rax], 2Fh ; '/'
0x1800194ac  jz      short loc_1800194BD
0x1800194ae  cmp     word ptr [rax], 5Ch ; '\'
0x1800194b2  jz      short loc_1800194BD
0x1800194b4  sub     rax, 2
0x1800194b8  cmp     rax, rdx
0x1800194bb  jnz     short loc_1800194A2
0x1800194bd  cmp     rax, rdx
0x1800194c0  jz      short loc_180019505
0x1800194c2  cmp     word ptr [rax], 2Eh ; '.'
0x1800194c6  jnz     short loc_180019505
0x1800194c8  lea     rdi, [rax+2]
0x1800194cc  cmp     [rdi], r15w
0x1800194d0  jz      short loc_180019505
0x1800194d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194d9  lea     rbx, WPP_GLOBAL_Control
0x1800194e0  cmp     rcx, rbx
0x1800194e3  jz      loc_18001957B
0x1800194e9  test    byte ptr [rcx+1Ch], 2
0x1800194ed  jz      short loc_18001955C
0x1800194ef  mov     rcx, [rcx+10h]
0x1800194f3  mov     edx, 0E6h
0x1800194f8  mov     r9, rdi
0x1800194fb  mov     r8, r12
0x1800194fe  call    WPP_SF_S
0x180019503  jmp     short loc_180019555
0x180019505  mov     rdi, r15
0x180019508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001950f  lea     rbx, WPP_GLOBAL_Control
0x180019516  cmp     rcx, rbx
0x180019519  jz      short loc_18001957B
0x18001951b  test    byte ptr [rcx+1Ch], 2
0x18001951f  jz      short loc_18001955C
0x180019521  mov     edx, 0E7h
0x180019526  jmp     short loc_180019549
0x180019528  mov     rdi, r15
0x18001952b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019532  lea     rbx, WPP_GLOBAL_Control
0x180019539  cmp     rcx, rbx
0x18001953c  jz      short loc_18001957B
0x18001953e  test    byte ptr [rcx+1Ch], 2
0x180019542  jz      short loc_18001955C
0x180019544  mov     edx, 0E8h
0x180019549  mov     rcx, [rcx+10h]
0x18001954d  mov     r8, r12
0x180019550  call    WPP_SF_
0x180019555  mov     rcx, cs:WPP_GLOBAL_Control
0x18001955c  cmp     rcx, rbx
0x18001955f  jz      short loc_18001957B
0x180019561  test    byte ptr [rcx+1Ch], 2
0x180019565  jz      short loc_18001957B
0x180019567  mov     rcx, [rcx+10h]
0x18001956b  mov     edx, 0E9h
0x180019570  mov     r9, rdi
0x180019573  mov     r8, r12
0x180019576  call    WPP_SF_S
0x18001957b  mov     esi, 104h
0x180019580  mov     edx, 208h; uBytes
0x180019585  mov     ecx, 40h ; '@'; uFlags
0x18001958a  mov     [rsp+58h+arg_0], esi
0x18001958e  call    cs:__imp_LocalAlloc
0x180019594  mov     rbp, rax
0x180019597  test    rax, rax
0x18001959a  jnz     short loc_1800195D5
0x18001959c  call    cs:__imp_GetLastError
0x1800195a2  mov     edi, eax
0x1800195a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195ab  cmp     rcx, rbx
0x1800195ae  jz      loc_1800196AE
0x1800195b4  test    byte ptr [rcx+1Ch], 1
0x1800195b8  jz      loc_1800196AE
0x1800195be  mov     rcx, [rcx+10h]
0x1800195c2  lea     edx, [rsi-1Ah]
0x1800195c5  mov     r9d, eax
0x1800195c8  mov     r8, r12
0x1800195cb  call    WPP_SF_d
0x1800195d0  jmp     loc_1800196AE
0x1800195d5  mov     rdx, [r14+248h]
0x1800195dc  lea     rax, [rsp+58h+arg_0]
0x1800195e1  mov     r9, rbp
0x1800195e4  mov     [rsp+58h+var_38], rax
0x1800195e9  mov     r8, rdi
0x1800195ec  call    TfsCreateEntry
0x1800195f1  mov     edi, eax
0x1800195f3  test    eax, eax
0x1800195f5  jz      short loc_18001963B
0x1800195f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195fe  cmp     rcx, rbx
0x180019601  jz      short loc_180019629
0x180019603  test    byte ptr [rcx+1Ch], 1
0x180019607  jz      short loc_180019629
0x180019609  mov     rax, [r14+248h]
0x180019610  mov     edx, 0EBh
0x180019615  mov     rcx, [rcx+10h]
0x180019619  mov     r9d, edi
0x18001961c  mov     r8, r12
0x18001961f  mov     [rsp+58h+var_38], rax
0x180019624  call    WPP_SF_dS
0x180019629  mov     rcx, rbp; hMem
0x18001962c  call    cs:__imp_LocalFree
0x180019632  mov     [r14+240h], r15
0x180019639  jmp     short loc_1800196AE
0x18001963b  mov     [r14+240h], rbp
0x180019642  mov     rcx, cs:WPP_GLOBAL_Control
0x180019649  cmp     rcx, rbx
0x18001964c  jz      short loc_180019668
0x18001964e  test    byte ptr [rcx+1Ch], 2
0x180019652  jz      short loc_180019668
0x180019654  mov     rcx, [rcx+10h]
0x180019658  mov     edx, 0ECh
0x18001965d  mov     r9, rbp
0x180019660  mov     r8, r12
0x180019663  call    WPP_SF_S
0x180019668  mov     rdx, [r14+240h]
0x18001966f  lea     rax, [r14+908h]
0x180019676  mov     ecx, 7FFFFFFEh
0x18001967b  test    rcx, rcx
0x18001967e  jz      short loc_18001969F
0x180019680  movzx   r8d, word ptr [rdx]
0x180019684  test    r8w, r8w
0x180019688  jz      short loc_18001969F
0x18001968a  mov     [rax], r8w
0x18001968e  add     rdx, 2
0x180019692  add     rax, 2
0x180019696  dec     rcx
0x180019699  sub     rsi, 1
0x18001969d  jnz     short loc_18001967B
0x18001969f  test    rsi, rsi
0x1800196a2  lea     rcx, [rax-2]
0x1800196a6  cmovnz  rcx, rax
0x1800196aa  mov     [rcx], r15w
0x1800196ae  mov     rbx, [rsp+58h+arg_8]
0x1800196b3  mov     eax, edi
0x1800196b5  mov     rbp, [rsp+58h+arg_10]
0x1800196ba  add     rsp, 30h
0x1800196be  pop     r15
0x1800196c0  pop     r14
0x1800196c2  pop     r12
0x1800196c4  pop     rdi
0x1800196c5  pop     rsi
0x1800196c6  retn
```
