# DavCreateNewEntry

- ea: `0x1800031d0`
- end: `0x180003450`
- name: `DavCreateNewEntry`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000235c`

## callees

- `0x1800031d0`
- `0x18000b4f0`
- `0x18000b6b4`
- `0x18000b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000329d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000329d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033ce`
- `KERNEL32!LocalAlloc` at `0x18000328f`
- `KERNEL32!LocalAlloc` at `0x1800033c0`
- `KERNEL32!LocalAlloc` at `0x18000328f`
- `KERNEL32!LocalAlloc` at `0x1800033c0`

## pseudocode

```c
__int64 __fastcall DavCreateNewEntry(
        __int64 *a1,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        const wchar_t *a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const wchar_t *pszSrc)
{
  __int64 v10; // rax
  __int64 v14; // r10
  unsigned int v15; // r12d
  unsigned int v16; // ebp
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  _DWORD *v23; // rax
  DWORD LastError; // ebx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  wchar_t *v28; // rbx
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // r11
  __int64 v32; // rax
  wchar_t *v33; // rax
  __int64 v34; // rax
  _DWORD *v35; // r11
  __int64 v36; // rcx

  v10 = -1;
  if ( pszSrc )
  {
    v14 = -1;
    do
      ++v14;
    while ( pszSrc[v14] );
    v15 = v14 + 1;
  }
  else
  {
    v15 = 0;
  }
  if ( a4 )
  {
    do
      ++v10;
    while ( a4[v10] );
    v16 = v10 + 1;
  }
  else
  {
    v16 = 0;
  }
  if ( a2 )
  {
    v17 = 2LL * a3;
    if ( a7 )
    {
      v18 = *(unsigned __int16 *)(a7 + 2);
      goto LABEL_15;
    }
  }
  else
  {
    v17 = 0;
  }
  v18 = 0;
LABEL_15:
  v19 = v17 + ((v18 + 1) & 0xFFFFFFFFFFFFFFFEuLL);
  if ( pszSrc )
    v20 = 2LL * v15;
  else
    v20 = 0;
  v21 = v19 + v20;
  if ( a4 )
    v22 = 2LL * v16;
  else
    v22 = 0;
  v23 = LocalAlloc(0x40u, (v21 + v22 + 89) & 0xFFFFFFFFFFFFFFFEuLL);
  *a1 = (__int64)v23;
  if ( !v23 )
  {
    LastError = GetLastError();
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v26 = 265;
LABEL_25:
    WPP_SF_d(v25[2], v26, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    return LastError;
  }
  *(_QWORD *)v23 = 0;
  v28 = (wchar_t *)(((unsigned __int64)v23 + 89) & 0xFFFFFFFFFFFFFFFEuLL);
  v23[9] = 1;
  if ( a2 )
  {
    *((_QWORD *)v23 + 3) = v28;
    v23[8] = a3;
    StringCchCopyW((STRSAFE_LPWSTR)(((unsigned __int64)v23 + 89) & 0xFFFFFFFFFFFFFFFEuLL), a3, a2);
    v28 += v29;
    if ( a7 )
    {
      *(_QWORD *)(*a1 + 48) = v28;
      StringCbCopyW(v28, *(unsigned __int16 *)(a7 + 2), *(STRSAFE_LPCWSTR *)(a7 + 8));
      v28 = (wchar_t *)(((unsigned __int64)v28 + *(unsigned __int16 *)(a7 + 2) + 1) & 0xFFFFFFFFFFFFFFFEuLL);
    }
  }
  else
  {
    *((_QWORD *)v23 + 3) = 0;
    *((_QWORD *)v23 + 6) = 0;
  }
  v30 = *a1;
  if ( pszSrc )
  {
    *(_QWORD *)(v30 + 72) = v28;
    StringCchCopyW(v28, v15, pszSrc);
    v28 += v31;
  }
  else
  {
    *(_QWORD *)(v30 + 72) = 0;
  }
  if ( a4 )
  {
    v32 = *a1;
    *(_QWORD *)(v32 + 56) = v28;
    *(_DWORD *)(v32 + 64) = v16;
    StringCchCopyW(v28, v16, a4);
  }
  if ( a5 )
  {
    v33 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned int)(a6 + 1) + 16);
    if ( !v33 )
    {
      LastError = GetLastError();
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v26 = 266;
      goto LABEL_25;
    }
    StringCchCopyW(v33 + 4, (unsigned int)(a6 + 1), a5);
    v34 = *a1;
    v35[1] = a6;
    *v35 = 1;
    *(_QWORD *)(v34 + 16) = v35;
  }
  v36 = *a1;
  *(_QWORD *)(v36 + 80) = a9;
  *(_QWORD *)(v36 + 40) = a8;
  return 0;
}

```

## disassembly

```asm
0x1800031d0  mov     dword ptr [rsp+cchDest], r8d
0x1800031d5  push    rbx
0x1800031d6  push    rbp
0x1800031d7  push    rsi
0x1800031d8  push    rdi
0x1800031d9  push    r12
0x1800031db  push    r13
0x1800031dd  push    r14
0x1800031df  push    r15
0x1800031e1  sub     rsp, 28h
0x1800031e5  mov     r15, [rsp+68h+pszSrc]
0x1800031ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800031f1  xor     ebx, ebx
0x1800031f3  mov     rsi, r9
0x1800031f6  mov     r13, rdx
0x1800031f9  mov     r14, rcx
0x1800031fc  test    r15, r15
0x1800031ff  jz      short loc_180003214
0x180003201  mov     r10, rax
0x180003204  inc     r10
0x180003207  cmp     [r15+r10*2], bx
0x18000320c  jnz     short loc_180003204
0x18000320e  lea     r12d, [r10+1]
0x180003212  jmp     short loc_180003217
0x180003214  mov     r12d, ebx
0x180003217  test    rsi, rsi
0x18000321a  jz      short loc_18000322B
0x18000321c  inc     rax
0x18000321f  cmp     [r9+rax*2], bx
0x180003224  jnz     short loc_18000321C
0x180003226  lea     ebp, [rax+1]
0x180003229  jmp     short loc_18000322D
0x18000322b  mov     ebp, ebx
0x18000322d  mov     rdi, [rsp+68h+arg_30]
0x180003235  test    r13, r13
0x180003238  jz      short loc_18000324B
0x18000323a  mov     ecx, r8d
0x18000323d  add     rcx, rcx
0x180003240  test    rdi, rdi
0x180003243  jz      short loc_18000324E
0x180003245  movzx   eax, word ptr [rdi+2]
0x180003249  jmp     short loc_180003251
0x18000324b  mov     rcx, rbx
0x18000324e  mov     rax, rbx
0x180003251  lea     rdx, [rax+1]
0x180003255  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180003259  add     rdx, rcx
0x18000325c  test    r15, r15
0x18000325f  jz      short loc_180003269
0x180003261  mov     eax, r12d
0x180003264  add     rax, rax
0x180003267  jmp     short loc_18000326C
0x180003269  mov     rax, rbx
0x18000326c  lea     rcx, [rdx+rax]
0x180003270  test    rsi, rsi
0x180003273  jz      short loc_18000327C
0x180003275  mov     eax, ebp
0x180003277  add     rax, rax
0x18000327a  jmp     short loc_18000327F
0x18000327c  mov     rax, rbx
0x18000327f  lea     rdx, [rax+59h]
0x180003283  add     rdx, rcx
0x180003286  mov     ecx, 40h ; '@'; uFlags
0x18000328b  and     rdx, 0FFFFFFFFFFFFFFFEh; uBytes
0x18000328f  call    cs:__imp_LocalAlloc
0x180003295  mov     [r14], rax
0x180003298  test    rax, rax
0x18000329b  jnz     short loc_1800032DD
0x18000329d  call    cs:__imp_GetLastError
0x1800032a3  mov     ebx, eax
0x1800032a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ac  lea     rdx, WPP_GLOBAL_Control
0x1800032b3  cmp     rcx, rdx
0x1800032b6  jz      short loc_1800032D6
0x1800032b8  test    byte ptr [rcx+1Ch], 1
0x1800032bc  jz      short loc_1800032D6
0x1800032be  mov     edx, 109h
0x1800032c3  mov     rcx, [rcx+10h]
0x1800032c7  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800032ce  mov     r9d, ebx
0x1800032d1  call    WPP_SF_d
0x1800032d6  mov     eax, ebx
0x1800032d8  jmp     loc_18000343F
0x1800032dd  mov     [rax], rbx
0x1800032e0  lea     rbx, [rax+59h]
0x1800032e4  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800032e8  mov     dword ptr [rax+24h], 1
0x1800032ef  test    r13, r13
0x1800032f2  jz      short loc_180003343
0x1800032f4  mov     ecx, dword ptr [rsp+68h+cchDest]
0x1800032fb  mov     r8, r13; pszSrc
0x1800032fe  mov     [rax+18h], rbx
0x180003302  mov     r11d, ecx
0x180003305  mov     [rax+20h], ecx
0x180003308  mov     edx, ecx; cchDest
0x18000330a  mov     rcx, rbx; pszDest
0x18000330d  call    StringCchCopyW
0x180003312  lea     rbx, [rbx+r11*2]
0x180003316  test    rdi, rdi
0x180003319  jz      short loc_180003353
0x18000331b  mov     rax, [r14]
0x18000331e  mov     rcx, rbx; pszDest
0x180003321  mov     [rax+30h], rbx
0x180003325  movzx   edx, word ptr [rdi+2]; cbDest
0x180003329  mov     r8, [rdi+8]; pszSrc
0x18000332d  call    StringCbCopyW
0x180003332  movzx   r11d, word ptr [rdi+2]
0x180003337  inc     r11
0x18000333a  add     rbx, r11
0x18000333d  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180003341  jmp     short loc_180003353
0x180003343  mov     qword ptr [rax+18h], 0
0x18000334b  mov     qword ptr [rax+30h], 0
0x180003353  mov     rax, [r14]
0x180003356  test    r15, r15
0x180003359  jz      short loc_180003376
0x18000335b  mov     r8, r15; pszSrc
0x18000335e  mov     edx, r12d; cchDest
0x180003361  mov     rcx, rbx; pszDest
0x180003364  mov     [rax+48h], rbx
0x180003368  mov     r11d, r12d
0x18000336b  call    StringCchCopyW
0x180003370  lea     rbx, [rbx+r11*2]
0x180003374  jmp     short loc_18000337E
0x180003376  mov     qword ptr [rax+48h], 0
0x18000337e  test    rsi, rsi
0x180003381  jz      short loc_18000339A
0x180003383  mov     rax, [r14]
0x180003386  mov     r8, rsi; pszSrc
0x180003389  mov     edx, ebp; cchDest
0x18000338b  mov     rcx, rbx; pszDest
0x18000338e  mov     [rax+38h], rbx
0x180003392  mov     [rax+40h], ebp
0x180003395  call    StringCchCopyW
0x18000339a  mov     rbx, [rsp+68h+arg_20]
0x1800033a2  test    rbx, rbx
0x1800033a5  jz      short loc_180003422
0x1800033a7  mov     edi, [rsp+68h+arg_28]
0x1800033ae  mov     ecx, 40h ; '@'; uFlags
0x1800033b3  lea     eax, [rdi+1]
0x1800033b6  lea     rdx, ds:10h[rax*2]; uBytes
0x1800033be  mov     esi, eax
0x1800033c0  call    cs:__imp_LocalAlloc
0x1800033c6  mov     r11, rax
0x1800033c9  test    rax, rax
0x1800033cc  jnz     short loc_180003401
0x1800033ce  call    cs:__imp_GetLastError
0x1800033d4  mov     ebx, eax
0x1800033d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033dd  lea     rdx, WPP_GLOBAL_Control
0x1800033e4  cmp     rcx, rdx
0x1800033e7  jz      loc_1800032D6
0x1800033ed  test    byte ptr [rcx+1Ch], 1
0x1800033f1  jz      loc_1800032D6
0x1800033f7  mov     edx, 10Ah
0x1800033fc  jmp     loc_1800032C3
0x180003401  lea     rcx, [rax+8]; pszDest
0x180003405  mov     r8, rbx; pszSrc
0x180003408  mov     rdx, rsi; cchDest
0x18000340b  call    StringCchCopyW
0x180003410  mov     rax, [r14]
0x180003413  mov     [r11+4], edi
0x180003417  mov     dword ptr [r11], 1
0x18000341e  mov     [rax+10h], r11
0x180003422  mov     rcx, [r14]
0x180003425  mov     rax, [rsp+68h+arg_40]
0x18000342d  mov     [rcx+50h], rax
0x180003431  mov     rax, [rsp+68h+arg_38]
0x180003439  mov     [rcx+28h], rax
0x18000343d  xor     eax, eax
0x18000343f  add     rsp, 28h
0x180003443  pop     r15
0x180003445  pop     r14
0x180003447  pop     r13
0x180003449  pop     r12
0x18000344b  pop     rdi
0x18000344c  pop     rsi
0x18000344d  pop     rbp
0x18000344e  pop     rbx
0x18000344f  retn
```
