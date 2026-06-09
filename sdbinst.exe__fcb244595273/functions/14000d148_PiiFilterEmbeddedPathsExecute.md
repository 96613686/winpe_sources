# PiiFilterEmbeddedPathsExecute

- ea: `0x14000d148`
- end: `0x14000d6fb`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1459`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000c540`

## callees

- `0x14000ac7c`
- `0x14000acf4`
- `0x14000d148`
- `0x14001112c`

## import_xrefs

- `msvcrt!iswspace` at `0x14000d5f1`
- `msvcrt!iswspace` at `0x14000d656`
- `msvcrt!iswspace` at `0x14000d5f1`
- `msvcrt!iswspace` at `0x14000d656`
- `msvcrt!wcschr` at `0x14000d695`
- `msvcrt!wcschr` at `0x14000d695`
- `msvcrt!wcsstr` at `0x14000d3f5`
- `msvcrt!wcsstr` at `0x14000d536`
- `msvcrt!wcsstr` at `0x14000d588`
- `msvcrt!wcsstr` at `0x14000d3f5`
- `msvcrt!wcsstr` at `0x14000d536`
- `msvcrt!wcsstr` at `0x14000d588`
- `ntdll!RtlAllocateHeap` at `0x14000d186`
- `ntdll!RtlAllocateHeap` at `0x14000d1b5`
- `ntdll!RtlAllocateHeap` at `0x14000d186`
- `ntdll!RtlAllocateHeap` at `0x14000d1b5`
- `ntdll!RtlFreeHeap` at `0x14000d6c1`
- `ntdll!RtlFreeHeap` at `0x14000d6de`
- `ntdll!RtlFreeHeap` at `0x14000d6c1`
- `ntdll!RtlFreeHeap` at `0x14000d6de`

## pseudocode

```c
__int64 __fastcall PiiFilterEmbeddedPathsExecute(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned __int16 *a4)
{
  signed int v7; // edi
  wchar_t *Heap; // rbp
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rcx
  _QWORD *v15; // r8
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  wchar_t **v18; // rax
  wchar_t *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  wchar_t **v24; // rax
  __int64 *v25; // rax
  __int64 v26; // r13
  unsigned __int16 *v27; // rdi
  __int64 v28; // rcx
  wchar_t *v29; // rax
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  __int64 v32; // r8
  wchar_t *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  __int64 v37; // rbx
  wchar_t *v38; // rax
  __int64 v39; // rcx
  unsigned __int16 *v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rdx
  wchar_t *v43; // rax
  wchar_t *v44; // rcx
  unsigned __int16 *v45; // rax
  wchar_t *v46; // rdx
  wchar_t *v47; // rcx
  wchar_t *i; // rax
  const wchar_t *v49; // rcx
  wchar_t v50; // dx
  unsigned __int16 *v51; // rdi
  const wchar_t *j; // rcx
  wint_t *v53; // rdi
  wint_t *v54; // rbx
  int v55; // esi
  unsigned __int16 v56; // ax
  BOOL v57; // eax
  char *v58; // rdi
  unsigned __int64 v59; // rcx
  wchar_t *v60; // rax
  __int64 v62; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp+18h]

  v62 = a2;
  SubStr = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
  if ( !SubStr )
    return (unsigned int)-1073741801;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
  if ( Heap )
  {
    v9 = 2147483646;
    v10 = 1024;
    v11 = 2147483646;
    v12 = 1024;
    v13 = a1;
    do
    {
      if ( !v11 )
        break;
      if ( !*a4 )
        break;
      *v13++ = *a4++;
      --v11;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v7 = v12 == 0 ? 0x80000005 : 0;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( !v12 )
      goto LABEL_112;
    v15 = (_QWORD *)a3[8];
    v16 = a3[2];
    if ( !(_QWORD *)((char *)v15 + v16) )
    {
LABEL_67:
      v45 = a1;
      v46 = Heap;
      do
      {
        if ( !v9 )
          break;
        if ( !*v45 )
          break;
        *v46++ = *v45++;
        --v9;
        --v10;
      }
      while ( v10 );
      v47 = v46 - 1;
      v7 = v10 == 0 ? 0x80000005 : 0;
      if ( v10 )
        v47 = v46;
      *v47 = 0;
      if ( v10 )
      {
        AslStringUpper(Heap, v46, v15, 0);
        for ( i = wcsstr(Heap, L"\\USERS\\"); i; i = wcsstr(v49, L"\\USERS\\") )
        {
          v49 = i + 7;
          v50 = i[7];
          if ( v50 )
          {
            v51 = &a1[v49 - Heap];
            do
            {
              if ( v50 == 92 )
                break;
              if ( v51 >= a1 + 1024 )
                break;
              ++v49;
              *v51++ = 120;
              v50 = *v49;
            }
            while ( *v49 );
          }
        }
        for ( j = a1; ; j = v54 )
        {
          v60 = wcschr(j, 0x40u);
          if ( !v60 || !*v60 )
            break;
          v53 = v60 - 1;
          LODWORD(v62) = 0;
          v54 = v60 + 1;
          v55 = 0;
          v56 = v60[1];
          if ( v56 )
          {
            do
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(v56, 0, (int *)&v62) )
                break;
              if ( *v54 == 46 )
                v55 = 1;
              v56 = *++v54;
            }
            while ( *v54 );
          }
          v57 = iswspace(*v54) || !*v54 || *v54 == 62;
          if ( v55 && v57 )
          {
            --v54;
            LODWORD(v62) = 0;
            while ( v53 >= a1 )
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(*v53, 1, (int *)&v62) )
              {
                if ( *v53 != 60 && !iswspace(*v53) )
                  goto LABEL_109;
                break;
              }
              --v53;
            }
            if ( !(_DWORD)v62 )
            {
              v58 = (char *)(v53 + 1);
              v59 = (unsigned __int64)((char *)v54 - v58 + 2) >> 1;
              if ( v58 > (char *)v54 )
                v59 = 0;
              if ( v59 )
              {
                while ( v59 )
                {
                  *(_WORD *)v58 = 35;
                  v58 += 2;
                  --v59;
                }
              }
            }
          }
LABEL_109:
          ;
        }
        v7 = 0;
      }
      goto LABEL_112;
    }
    v17 = 0;
    LODWORD(v62) = 0;
    while ( v17 < v16 )
    {
      v15 = a3 + 5;
      if ( !is_mul_ok(a3[1], v17) || (v18 = (wchar_t **)(*v15 + a3[1] * v17), (unsigned __int64)v18 < *v15) )
        v18 = 0;
      v19 = *v18;
      if ( !is_mul_ok(a3[1], v17) || (v20 = (__int64 *)(*v15 + a3[1] * v17), (unsigned __int64)v20 < *v15) )
        v20 = 0;
      v21 = *v20;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
LABEL_36:
      v26 = v21 + 2 * v22;
      v27 = a1;
      v28 = 2147483646;
      v29 = Heap;
      v30 = 1024;
      do
      {
        if ( !v28 )
          break;
        v15 = (_QWORD *)*v27;
        if ( !(_WORD)v15 )
          break;
        *v29 = (unsigned __int16)v15;
        ++v27;
        ++v29;
        --v28;
        --v30;
      }
      while ( v30 );
      v31 = v29 - 1;
      if ( v30 )
        v31 = v29;
      *v31 = 0;
      v7 = v30 == 0 ? 0x80000005 : 0;
      if ( !v30 )
        goto LABEL_112;
      AslStringUpper(Heap, v30, v15, 0);
      v33 = SubStr;
      v34 = 2147483646;
      v35 = 1024;
      do
      {
        if ( !v34 )
          break;
        if ( !*v19 )
          break;
        *v33++ = *v19++;
        --v34;
        --v35;
      }
      while ( v35 );
      v36 = v33 - 1;
      if ( v35 )
        v36 = v33;
      *v36 = 0;
      v7 = v35 == 0 ? 0x80000005 : 0;
      if ( !v35 )
        goto LABEL_112;
      v37 = -1;
      do
        ++v37;
      while ( SubStr[v37] );
      if ( v37 && (AslStringUpper(SubStr, v35, v32, 0), (v38 = wcsstr(Heap, SubStr)) != 0) )
      {
        v39 = v38 - Heap;
        a1[v39] = 0;
        v40 = &a1[v37 + v39];
        if ( v40 >= a1 + 1024 )
          goto LABEL_112;
        v41 = 2147483646;
        v42 = 1024;
        v43 = Heap;
        do
        {
          if ( !v41 )
            break;
          if ( !*v40 )
            break;
          *v43++ = *v40++;
          --v41;
          --v42;
        }
        while ( v42 );
        v44 = v43 - 1;
        if ( v42 )
          v44 = v43;
        *v44 = 0;
        v7 = v42 == 0 ? 0x80000005 : 0;
        if ( !v42 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, 1024, (unsigned __int16 *)(v26 + 2));
        if ( v7 < 0 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, 1024, Heap);
        if ( v7 < 0 )
          goto LABEL_112;
        v17 = (unsigned int)v62;
      }
      else
      {
        v17 = (unsigned int)(v62 + 1);
        LODWORD(v62) = v62 + 1;
      }
      v15 = (_QWORD *)a3[8];
      v16 = a3[2];
      if ( (unsigned int)v17 >= (unsigned __int64)v15 + v16 )
        goto LABEL_67;
    }
    v23 = v17 - v16;
    if ( v23 >= (unsigned __int64)v15 )
    {
      v19 = (wchar_t *)MEMORY[0];
    }
    else
    {
      if ( is_mul_ok(a3[7], v23) && (v24 = (wchar_t **)(a3[11] + a3[7] * v23), (unsigned __int64)v24 >= a3[11]) )
        v19 = *v24;
      else
        v19 = (wchar_t *)MEMORY[0];
      if ( is_mul_ok(a3[7], v23) )
      {
        v25 = (__int64 *)(a3[11] + a3[7] * v23);
        if ( (unsigned __int64)v25 >= a3[11] )
          goto LABEL_34;
      }
    }
    v25 = 0;
LABEL_34:
    v21 = *v25;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
    goto LABEL_36;
  }
  v7 = -1073741801;
LABEL_112:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SubStr);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000d148  mov     [rsp+arg_0], rbx
0x14000d14d  mov     [rsp+arg_8], rdx
0x14000d152  push    rbp
0x14000d153  push    rsi
0x14000d154  push    rdi
0x14000d155  push    r12
0x14000d157  push    r13
0x14000d159  push    r14
0x14000d15b  push    r15
0x14000d15d  sub     rsp, 30h
0x14000d161  mov     r15, rcx
0x14000d164  mov     r14, r8
0x14000d167  mov     rcx, gs:60h
0x14000d170  mov     ebx, 800h
0x14000d175  mov     esi, 8
0x14000d17a  mov     r8d, ebx; Size
0x14000d17d  mov     edx, esi; Flags
0x14000d17f  mov     rdi, r9
0x14000d182  mov     rcx, [rcx+30h]; HeapHandle
0x14000d186  call    cs:__imp_RtlAllocateHeap
0x14000d18c  mov     [rsp+68h+SubStr], rax
0x14000d194  test    rax, rax
0x14000d197  jnz     short loc_14000D1A3
0x14000d199  mov     edi, 0C0000017h
0x14000d19e  jmp     loc_14000D6E4
0x14000d1a3  mov     rcx, gs:60h
0x14000d1ac  mov     r8, rbx; Size
0x14000d1af  mov     edx, esi; Flags
0x14000d1b1  mov     rcx, [rcx+30h]; HeapHandle
0x14000d1b5  call    cs:__imp_RtlAllocateHeap
0x14000d1bb  xor     r9d, r9d
0x14000d1be  mov     rbp, rax
0x14000d1c1  test    rax, rax
0x14000d1c4  jnz     short loc_14000D1D0
0x14000d1c6  mov     edi, 0C0000017h
0x14000d1cb  jmp     loc_14000D6AA
0x14000d1d0  mov     r12d, 7FFFFFFEh
0x14000d1d6  mov     esi, 400h
0x14000d1db  mov     eax, r12d
0x14000d1de  mov     edx, esi
0x14000d1e0  mov     r8, r15
0x14000d1e3  mov     r10d, 1
0x14000d1e9  test    rax, rax
0x14000d1ec  jz      short loc_14000D20A
0x14000d1ee  movzx   ecx, word ptr [rdi]
0x14000d1f1  test    cx, cx
0x14000d1f4  jz      short loc_14000D20A
0x14000d1f6  mov     [r8], cx
0x14000d1fa  add     rdi, 2
0x14000d1fe  add     r8, 2
0x14000d202  sub     rax, r10
0x14000d205  sub     rdx, r10
0x14000d208  jnz     short loc_14000D1E9
0x14000d20a  mov     rax, rdx
0x14000d20d  lea     rcx, [r8-2]
0x14000d211  neg     rax
0x14000d214  sbb     edi, edi
0x14000d216  not     edi
0x14000d218  and     edi, 80000005h
0x14000d21e  test    rdx, rdx
0x14000d221  cmovnz  rcx, r8
0x14000d225  mov     [rcx], r9w
0x14000d229  jz      loc_14000D6AA
0x14000d22f  mov     r8, [r14+40h]
0x14000d233  mov     rdx, [r14+10h]
0x14000d237  lea     rax, [rdx+r8]
0x14000d23b  test    rax, rax
0x14000d23e  jz      loc_14000D4D9
0x14000d244  mov     edi, r9d
0x14000d247  mov     dword ptr [rsp+68h+arg_8], edi
0x14000d24b  cmp     rdi, rdx
0x14000d24e  jnb     short loc_14000D298
0x14000d250  mov     rax, rdi
0x14000d253  lea     r8, [r14+28h]
0x14000d257  mul     qword ptr [r14+8]
0x14000d25b  test    rdx, rdx
0x14000d25e  jnz     short loc_14000D268
0x14000d260  add     rax, [r8]
0x14000d263  cmp     rax, [r8]
0x14000d266  jnb     short loc_14000D26B
0x14000d268  mov     rax, r9
0x14000d26b  mov     rbx, [rax]
0x14000d26e  mov     rax, rdi
0x14000d271  mul     qword ptr [r14+8]
0x14000d275  test    rdx, rdx
0x14000d278  jnz     short loc_14000D282
0x14000d27a  add     rax, [r8]
0x14000d27d  cmp     rax, [r8]
0x14000d280  jnb     short loc_14000D285
0x14000d282  mov     rax, r9
0x14000d285  mov     rcx, [rax]
0x14000d288  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d28c  inc     rax
0x14000d28f  cmp     [rcx+rax*2], r9w
0x14000d294  jnz     short loc_14000D28C
0x14000d296  jmp     short loc_14000D2F7
0x14000d298  sub     rdi, rdx
0x14000d29b  cmp     rdi, r8
0x14000d29e  jnb     short loc_14000D2DB
0x14000d2a0  mov     rax, rdi
0x14000d2a3  mul     qword ptr [r14+38h]
0x14000d2a7  test    rdx, rdx
0x14000d2aa  jnz     short loc_14000D2BB
0x14000d2ac  add     rax, [r14+58h]
0x14000d2b0  cmp     rax, [r14+58h]
0x14000d2b4  jb      short loc_14000D2BB
0x14000d2b6  mov     rbx, [rax]
0x14000d2b9  jmp     short loc_14000D2C3
0x14000d2bb  mov     rbx, ds:0
0x14000d2c3  mov     rax, rdi
0x14000d2c6  mul     qword ptr [r14+38h]
0x14000d2ca  test    rdx, rdx
0x14000d2cd  jnz     short loc_14000D2E3
0x14000d2cf  add     rax, [r14+58h]
0x14000d2d3  cmp     rax, [r14+58h]
0x14000d2d7  jnb     short loc_14000D2E6
0x14000d2d9  jmp     short loc_14000D2E3
0x14000d2db  mov     rbx, ds:0
0x14000d2e3  mov     rax, r9
0x14000d2e6  mov     rcx, [rax]
0x14000d2e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d2ed  inc     rax
0x14000d2f0  cmp     [rcx+rax*2], r9w
0x14000d2f5  jnz     short loc_14000D2ED
0x14000d2f7  lea     r13, [rcx+rax*2]
0x14000d2fb  mov     rdi, r15
0x14000d2fe  mov     rcx, r12
0x14000d301  mov     rax, rbp
0x14000d304  mov     rdx, rsi
0x14000d307  test    rcx, rcx
0x14000d30a  jz      short loc_14000D32A
0x14000d30c  movzx   r8d, word ptr [rdi]
0x14000d310  test    r8w, r8w
0x14000d314  jz      short loc_14000D32A
0x14000d316  mov     [rax], r8w
0x14000d31a  add     rdi, 2
0x14000d31e  add     rax, 2
0x14000d322  sub     rcx, r10
0x14000d325  sub     rdx, r10
0x14000d328  jnz     short loc_14000D307
0x14000d32a  test    rdx, rdx
0x14000d32d  lea     rcx, [rax-2]
0x14000d331  cmovnz  rcx, rax
0x14000d335  mov     rax, rdx
0x14000d338  neg     rax
0x14000d33b  sbb     edi, edi
0x14000d33d  not     edi
0x14000d33f  mov     [rcx], r9w
0x14000d343  and     edi, 80000005h
0x14000d349  test    rdx, rdx
0x14000d34c  jz      loc_14000D6AA
0x14000d352  mov     rcx, rbp
0x14000d355  call    AslStringUpper
0x14000d35a  mov     rax, [rsp+68h+SubStr]
0x14000d362  xor     r9d, r9d
0x14000d365  mov     rcx, r12
0x14000d368  mov     rdx, rsi
0x14000d36b  lea     r10d, [r9+1]
0x14000d36f  test    rcx, rcx
0x14000d372  jz      short loc_14000D38F
0x14000d374  movzx   edi, word ptr [rbx]
0x14000d377  test    di, di
0x14000d37a  jz      short loc_14000D38F
0x14000d37c  mov     [rax], di
0x14000d37f  add     rbx, 2
0x14000d383  add     rax, 2
0x14000d387  sub     rcx, r10
0x14000d38a  sub     rdx, r10
0x14000d38d  jnz     short loc_14000D36F
0x14000d38f  test    rdx, rdx
0x14000d392  lea     rcx, [rax-2]
0x14000d396  cmovnz  rcx, rax
0x14000d39a  mov     rax, rdx
0x14000d39d  neg     rax
0x14000d3a0  sbb     edi, edi
0x14000d3a2  not     edi
0x14000d3a4  mov     [rcx], r9w
0x14000d3a8  and     edi, 80000005h
0x14000d3ae  test    rdx, rdx
0x14000d3b1  jz      loc_14000D6AA
0x14000d3b7  mov     rax, [rsp+68h+SubStr]
0x14000d3bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000d3c3  inc     rbx
0x14000d3c6  cmp     [rax+rbx*2], r9w
0x14000d3cb  jnz     short loc_14000D3C3
0x14000d3cd  test    rbx, rbx
0x14000d3d0  jnz     short loc_14000D3E2
0x14000d3d2  mov     edi, dword ptr [rsp+68h+arg_8]
0x14000d3d6  add     edi, r10d
0x14000d3d9  mov     dword ptr [rsp+68h+arg_8], edi
0x14000d3dd  jmp     loc_14000D4C2
0x14000d3e2  mov     rcx, rax
0x14000d3e5  call    AslStringUpper
0x14000d3ea  mov     rdx, [rsp+68h+SubStr]; SubStr
0x14000d3f2  mov     rcx, rbp; Str
0x14000d3f5  call    cs:__imp_wcsstr
0x14000d3fb  xor     r9d, r9d
0x14000d3fe  mov     rcx, rax
0x14000d401  test    rax, rax
0x14000d404  jnz     short loc_14000D40C
0x14000d406  lea     r10d, [rax+1]
0x14000d40a  jmp     short loc_14000D3D2
0x14000d40c  sub     rcx, rbp
0x14000d40f  sar     rcx, 1
0x14000d412  lea     rax, [rbx+rcx]
0x14000d416  mov     [r15+rcx*2], r9w
0x14000d41b  lea     r8, [r15+rax*2]
0x14000d41f  lea     rax, [r15+800h]
0x14000d426  cmp     r8, rax
0x14000d429  jnb     loc_14000D6AA
0x14000d42f  mov     rcx, r12
0x14000d432  mov     rdx, rsi
0x14000d435  mov     rax, rbp
0x14000d438  test    rcx, rcx
0x14000d43b  jz      short loc_14000D45E
0x14000d43d  movzx   edi, word ptr [r8]
0x14000d441  test    di, di
0x14000d444  jz      short loc_14000D45E
0x14000d446  mov     [rax], di
0x14000d449  add     r8, 2
0x14000d44d  mov     edi, 1
0x14000d452  add     rax, 2
0x14000d456  sub     rcx, rdi
0x14000d459  sub     rdx, rdi
0x14000d45c  jnz     short loc_14000D438
0x14000d45e  test    rdx, rdx
0x14000d461  lea     rcx, [rax-2]
0x14000d465  cmovnz  rcx, rax
0x14000d469  mov     rax, rdx
0x14000d46c  neg     rax
0x14000d46f  sbb     edi, edi
0x14000d471  not     edi
0x14000d473  mov     [rcx], r9w
0x14000d477  and     edi, 80000005h
0x14000d47d  test    rdx, rdx
0x14000d480  jz      loc_14000D6AA
0x14000d486  lea     r8, [r13+2]; unsigned __int16 *
0x14000d48a  mov     rdx, rsi; unsigned __int64
0x14000d48d  mov     rcx, r15; unsigned __int16 *
0x14000d490  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d495  mov     edi, eax
0x14000d497  test    eax, eax
0x14000d499  js      loc_14000D6AA
0x14000d49f  mov     r8, rbp; unsigned __int16 *
0x14000d4a2  mov     rdx, rsi; unsigned __int64
0x14000d4a5  mov     rcx, r15; unsigned __int16 *
0x14000d4a8  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d4ad  xor     r9d, r9d
0x14000d4b0  mov     edi, eax
0x14000d4b2  test    eax, eax
0x14000d4b4  js      loc_14000D6AA
0x14000d4ba  mov     edi, dword ptr [rsp+68h+arg_8]
0x14000d4be  lea     r10d, [r9+1]
0x14000d4c2  mov     r8, [r14+40h]
0x14000d4c6  mov     rdx, [r14+10h]
0x14000d4ca  mov     eax, edi
0x14000d4cc  lea     rcx, [rdx+r8]
0x14000d4d0  cmp     rax, rcx
0x14000d4d3  jb      loc_14000D24B
0x14000d4d9  mov     rax, r15
0x14000d4dc  mov     rdx, rbp
0x14000d4df  test    r12, r12
0x14000d4e2  jz      short loc_14000D4FF
0x14000d4e4  movzx   ecx, word ptr [rax]
0x14000d4e7  test    cx, cx
0x14000d4ea  jz      short loc_14000D4FF
0x14000d4ec  mov     [rdx], cx
0x14000d4ef  add     rax, 2
0x14000d4f3  add     rdx, 2
0x14000d4f7  sub     r12, r10
0x14000d4fa  sub     rsi, r10
0x14000d4fd  jnz     short loc_14000D4DF
0x14000d4ff  mov     rax, rsi
0x14000d502  lea     rcx, [rdx-2]
0x14000d506  neg     rax
0x14000d509  sbb     edi, edi
0x14000d50b  not     edi
0x14000d50d  and     edi, 80000005h
0x14000d513  test    rsi, rsi
0x14000d516  cmovnz  rcx, rdx
0x14000d51a  mov     [rcx], r9w
0x14000d51e  jz      loc_14000D6AA
0x14000d524  mov     rcx, rbp
0x14000d527  call    AslStringUpper
0x14000d52c  lea     rdx, aUsers; "\\USERS\\"
0x14000d533  mov     rcx, rbp; Str
0x14000d536  call    cs:__imp_wcsstr
0x14000d53c  xor     r13d, r13d
0x14000d53f  jmp     short loc_14000D58E
0x14000d541  lea     rcx, [rax+0Eh]
0x14000d545  movzx   edx, word ptr [rcx]
0x14000d548  test    dx, dx
0x14000d54b  jz      short loc_14000D581
0x14000d54d  mov     rax, rcx
0x14000d550  sub     rax, rbp
0x14000d553  sar     rax, 1
0x14000d556  lea     rdi, [r15+rax*2]
0x14000d55a  cmp     dx, 5Ch ; '\'
0x14000d55e  jz      short loc_14000D581
0x14000d560  lea     rax, [r15+800h]
  ... truncated ...
```
