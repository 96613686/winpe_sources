# PowerHelperGetRequesterId

- ea: `0x180018418`
- end: `0x1800185fa`
- name: `PowerHelperGetRequesterId`
- size: `482`
- prototype: `unsigned __int16 *__fastcall(__int64, size_t, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000bea8`

## callees

- `0x18001826c`
- `0x180018310`
- `0x18001839c`
- `0x180018418`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018513`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018513`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800184a4`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800184a4`

## string_xrefs

- `0x180018542`: `[SERVICE] `

## pseudocode

```c
unsigned __int16 *__fastcall PowerHelperGetRequesterId(__int64 a1, size_t a2, _DWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rax
  const wchar_t *v10; // r12
  __int64 v11; // rdx
  size_t v12; // rdi
  unsigned __int16 *v13; // r15
  const unsigned __int16 *v14; // r8
  size_t v15; // rdx
  size_t cchToCopy; // [rsp+20h] [rbp-30h]
  __int128 v18; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-10h]
  STRSAFE_LPWSTR pszDest; // [rsp+90h] [rbp+40h] BYREF
  size_t v21; // [rsp+98h] [rbp+48h] BYREF

  v21 = a2;
  *a3 = 0;
  hMem = 0;
  v5 = *(_QWORD *)(a1 + 16);
  pszDest = 0;
  v18 = 0;
  v6 = v5 + a1;
  if ( *(_DWORD *)(a1 + 8) )
  {
    v8 = 0;
    v7 = (const unsigned __int16 *)(v6 & -(__int64)(v5 != 0));
    if ( *(_DWORD *)(a1 + 8) == 2 )
    {
      *(_QWORD *)&v18 = *(_QWORD *)(a1 + 24);
      if ( !(unsigned int)I_QueryTagInformation(0, 1, &v18) )
        v8 = (__int64)hMem;
    }
  }
  else
  {
    v7 = (const unsigned __int16 *)(v6 & -(__int64)(v5 != 0));
    v8 = (*(_QWORD *)(a1 + 24) + a1) & -(__int64)(*(_QWORD *)(a1 + 24) != 0);
  }
  if ( !v7 )
  {
    v10 = L"Legacy Kernel Requester";
    v12 = *(_DWORD *)(a1 + 8) != 0 ? 68LL : 66LL;
LABEL_13:
    v21 = v12;
    goto LABEL_14;
  }
  v9 = -1;
  v10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( v7[v11] );
  v12 = (*(_DWORD *)(a1 + 8) != 0 ? 22LL : 20LL) + 2 * v11;
  v21 = v12;
  if ( v8 )
  {
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    v12 += 2 * v9 + 6;
    goto LABEL_13;
  }
LABEL_14:
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, v12);
  if ( v13 )
  {
    *a3 = 1;
    if ( *(_DWORD *)(a1 + 8) )
    {
      v14 = L"[SERVICE] ";
      if ( *(_DWORD *)(a1 + 8) != 2 )
        v14 = L"[PROCESS] ";
    }
    else
    {
      v14 = L"[DRIVER] ";
    }
    StringCbCopyExW(v13, v12, v14, &pszDest, &v21);
    if ( v7 )
    {
      StringCbCopyExW(pszDest, v21, v7, &pszDest, &v21);
      if ( v8 )
        StringCbPrintfW(pszDest, v21, L" (%s)", v8);
    }
    else
    {
      v15 = v21 >> 1;
      if ( v21 >> 1 )
      {
        if ( v15 > 0x7FFFFFFF )
          *pszDest = 0;
        else
          StringCopyWorkerW_0(pszDest, v15, 0, v10, cchToCopy);
      }
    }
  }
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x180018418  mov     [rsp-38h+arg_10], rbx
0x18001841d  mov     [rsp-38h+arg_8], rdx
0x180018422  push    rbp
0x180018423  push    rsi
0x180018424  push    rdi
0x180018425  push    r12
0x180018427  push    r13
0x180018429  push    r14
0x18001842b  push    r15
0x18001842d  mov     rbp, rsp
0x180018430  sub     rsp, 50h
0x180018434  xor     r15d, r15d
0x180018437  xor     eax, eax
0x180018439  mov     [r8], r15d
0x18001843c  xorps   xmm0, xmm0
0x18001843f  mov     r13, r8
0x180018442  mov     [rbp+hMem], rax
0x180018446  mov     r14, rcx
0x180018449  mov     rax, [rcx+10h]
0x18001844d  mov     [rbp+pszDest], r15
0x180018451  movups  [rbp+var_20], xmm0
0x180018455  lea     rdx, [rax+rcx]
0x180018459  cmp     [rcx+8], r15d
0x18001845d  jnz     short loc_18001847B
0x18001845f  mov     rcx, [rcx+18h]
0x180018463  neg     rax
0x180018466  sbb     rbx, rbx
0x180018469  and     rbx, rdx
0x18001846c  lea     rax, [rcx+r14]
0x180018470  neg     rcx
0x180018473  sbb     rsi, rsi
0x180018476  and     rsi, rax
0x180018479  jmp     short loc_1800184B2
0x18001847b  neg     rax
0x18001847e  mov     rsi, r15
0x180018481  sbb     rbx, rbx
0x180018484  and     rbx, rdx
0x180018487  cmp     dword ptr [rcx+8], 2
0x18001848b  jnz     short loc_1800184B2
0x18001848d  mov     eax, [rcx+18h]
0x180018490  lea     r8, [rbp+var_20]
0x180018494  mov     dword ptr [rbp+var_20], eax
0x180018497  mov     edx, 1
0x18001849c  mov     eax, [rcx+1Ch]
0x18001849f  xor     ecx, ecx
0x1800184a1  mov     dword ptr [rbp+var_20+4], eax
0x1800184a4  call    cs:__imp_I_QueryTagInformation
0x1800184aa  test    eax, eax
0x1800184ac  jnz     short loc_1800184B2
0x1800184ae  mov     rsi, [rbp+hMem]
0x1800184b2  mov     eax, [r14+8]
0x1800184b6  neg     eax
0x1800184b8  sbb     rcx, rcx
0x1800184bb  and     ecx, 2
0x1800184be  add     rcx, 14h
0x1800184c2  test    rbx, rbx
0x1800184c5  jz      short loc_1800184FC
0x1800184c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800184cb  mov     r12, r15
0x1800184ce  mov     rdx, rax
0x1800184d1  inc     rdx
0x1800184d4  cmp     [rbx+rdx*2], r15w
0x1800184d9  jnz     short loc_1800184D1
0x1800184db  lea     rdi, [rcx+rdx*2]
0x1800184df  mov     [rbp+arg_8], rdi
0x1800184e3  test    rsi, rsi
0x1800184e6  jz      short loc_18001850B
0x1800184e8  inc     rax
0x1800184eb  cmp     [rsi+rax*2], r15w
0x1800184f0  jnz     short loc_1800184E8
0x1800184f2  lea     rdi, [rdi+rax*2]
0x1800184f6  add     rdi, 6
0x1800184fa  jmp     short loc_180018507
0x1800184fc  lea     r12, aLegacyKernelRe; "Legacy Kernel Requester"
0x180018503  lea     rdi, [rcx+2Eh]
0x180018507  mov     [rbp+arg_8], rdi
0x18001850b  mov     rdx, rdi; uBytes
0x18001850e  mov     ecx, 40h ; '@'; uFlags
0x180018513  call    cs:__imp_LocalAlloc
0x180018519  mov     r15, rax
0x18001851c  test    rax, rax
0x18001851f  jz      loc_1800185D0
0x180018525  mov     dword ptr [r13+0], 1
0x18001852d  cmp     dword ptr [r14+8], 0
0x180018532  jnz     short loc_18001853D
0x180018534  lea     r8, aDriver_0; "[DRIVER] "
0x18001853b  jmp     short loc_180018554
0x18001853d  cmp     dword ptr [r14+8], 2
0x180018542  lea     r8, aService; "[SERVICE] "
0x180018549  lea     rax, aProcess_0; "[PROCESS] "
0x180018550  cmovnz  r8, rax; unsigned __int16 *
0x180018554  lea     rax, [rbp+arg_8]
0x180018558  mov     rdx, rdi; unsigned __int64
0x18001855b  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x18001855f  mov     [rsp+50h+cchToCopy], rax; unsigned __int64 *
0x180018564  mov     rcx, r15; unsigned __int16 *
0x180018567  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001856c  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180018570  test    rbx, rbx
0x180018573  jz      short loc_1800185AC
0x180018575  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x180018579  lea     rax, [rbp+arg_8]
0x18001857d  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x180018581  mov     [rsp+50h+cchToCopy], rax; unsigned __int64 *
0x180018586  mov     r8, rbx; unsigned __int16 *
0x180018589  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001858e  test    rsi, rsi
0x180018591  jz      short loc_1800185D0
0x180018593  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180018597  lea     r8, aS_0; " (%s)"
0x18001859e  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x1800185a2  mov     r9, rsi
0x1800185a5  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800185aa  jmp     short loc_1800185D0
0x1800185ac  shr     rdx, 1; cchDest
0x1800185af  jz      short loc_1800185D0
0x1800185b1  mov     rcx, [rbp+pszDest]; pszDest
0x1800185b5  cmp     rdx, 7FFFFFFFh
0x1800185bc  ja      short loc_1800185CB
0x1800185be  mov     r9, r12; pszSrc
0x1800185c1  xor     r8d, r8d; pcchNewDestLength
0x1800185c4  call    StringCopyWorkerW_0
0x1800185c9  jmp     short loc_1800185D0
0x1800185cb  xor     eax, eax
0x1800185cd  mov     [rcx], ax
0x1800185d0  mov     rcx, [rbp+hMem]; hMem
0x1800185d4  test    rcx, rcx
0x1800185d7  jz      short loc_1800185DF
0x1800185d9  call    cs:__imp_LocalFree
0x1800185df  mov     rbx, [rsp+50h+arg_10]
0x1800185e7  mov     rax, r15
0x1800185ea  add     rsp, 50h
0x1800185ee  pop     r15
0x1800185f0  pop     r14
0x1800185f2  pop     r13
0x1800185f4  pop     r12
0x1800185f6  pop     rdi
0x1800185f7  pop     rsi
0x1800185f8  pop     rbp
0x1800185f9  retn
```
