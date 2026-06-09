# SampRODCCacheSearch(_SAMP_RODC_ROLES_CACHE *,void *,ulong,uchar)

- ea: `0x18003986c`
- end: `0x180039ad0`
- name: `?SampRODCCacheSearch@@YAJPEAU_SAMP_RODC_ROLES_CACHE@@PEAXKE@Z`
- size: `612`
- prototype: `int(struct _SAMP_RODC_ROLES_CACHE *, void *, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180038aa0`
- `0x180039318`

## callees

- `0x180027e24`
- `0x18003986c`
- `0x1800bb794`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180039973`
- `ntdll!RtlLengthSid` at `0x180039973`
- `ntdll!RtlEqualSid` at `0x1800398e5`
- `ntdll!RtlEqualSid` at `0x1800398e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003992a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039982`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003992a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039982`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039a66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039a66`

## pseudocode

```c
__int64 __fastcall SampRODCCacheSearch(struct _SAMP_RODC_ROLES_CACHE *a1, void *a2, int a3, char a4)
{
  unsigned int v8; // edi
  __int64 i; // rbx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rbp
  HLOCAL v14; // rsi
  ULONG v15; // ebp
  __int64 v16; // rsi
  __int64 v17; // rbx
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rsi
  __int64 v21; // rbp
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // r15d
  HLOCAL v25; // r14
  __int64 v26; // rdx
  unsigned int v27; // eax

  if ( !a1 )
  {
    v8 = a4 != 0 ? -1073741811 : -1073741275;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        54,
        WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids,
        v8,
        a4 != 0 ? -1073741811 : -1073741275);
    return v8;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
  {
    if ( RtlEqualSid(a2, *(PSID *)(*((_QWORD *)a1 + 1) + 24 * i)) )
      break;
  }
  if ( (_DWORD)i == *(_DWORD *)a1 )
  {
    if ( !a4 )
    {
LABEL_10:
      v11 = -1073741275;
      goto LABEL_31;
    }
    v12 = *((_DWORD *)a1 + 1);
    if ( (unsigned int)i >= v12 )
    {
      v13 = v12 + 8;
      v14 = LocalAlloc(0x40u, 24 * v13);
      if ( !v14 )
      {
LABEL_13:
        v11 = -1073741801;
        goto LABEL_31;
      }
      if ( *((_DWORD *)a1 + 1) )
      {
        memmove_0(v14, *((const void **)a1 + 1), 24LL * *((unsigned int *)a1 + 1));
        LocalFree(*((HLOCAL *)a1 + 1));
      }
      *((_DWORD *)a1 + 1) = v13;
      *((_QWORD *)a1 + 1) = v14;
    }
    v15 = RtlLengthSid(a2);
    v16 = (unsigned int)i;
    v17 = 3 * i;
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v17) = LocalAlloc(0x40u, v15);
    v18 = *(void **)(*((_QWORD *)a1 + 1) + 8 * v17);
    if ( !v18 )
      goto LABEL_13;
    memmove_0(v18, a2, v15);
    *(_DWORD *)(*((_QWORD *)a1 + 1) + 8 * v17 + 12) = 0;
    *(_DWORD *)(*((_QWORD *)a1 + 1) + 8 * v17 + 8) = 0;
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v17 + 16) = 0;
    ++*(_DWORD *)a1;
  }
  else
  {
    v16 = (unsigned int)i;
  }
  v19 = *((_QWORD *)a1 + 1);
  v20 = 3 * v16;
  v11 = 0;
  v21 = 0;
  v22 = *(_DWORD *)(v19 + 8 * v20 + 8);
  if ( v22 )
  {
    while ( a3 != *(_DWORD *)(*(_QWORD *)(v19 + 8 * v20 + 16) + 4 * v21) )
    {
      v21 = (unsigned int)(v21 + 1);
      if ( (unsigned int)v21 >= v22 )
        goto LABEL_23;
    }
    goto LABEL_31;
  }
LABEL_23:
  if ( (_DWORD)v21 == v22 )
  {
    if ( !a4 )
      goto LABEL_10;
    v23 = *(_DWORD *)(v19 + 8 * v20 + 12);
    if ( (unsigned int)v21 >= v23 )
    {
      v24 = v23 + 8;
      v25 = LocalAlloc(0x40u, 4LL * (v23 + 8));
      if ( !v25 )
        goto LABEL_13;
      v26 = *((_QWORD *)a1 + 1);
      v27 = *(_DWORD *)(v26 + 8 * v20 + 12);
      if ( v27 )
      {
        memmove_0(v25, *(const void **)(v26 + 8 * v20 + 16), 4LL * v27);
        LocalFree(*(HLOCAL *)(*((_QWORD *)a1 + 1) + 8 * v20 + 16));
      }
      *(_DWORD *)(*((_QWORD *)a1 + 1) + 8 * v20 + 12) = v24;
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v20 + 16) = v25;
    }
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v20 + 16) + 4 * v21) = a3;
    ++*(_DWORD *)(*((_QWORD *)a1 + 1) + 8 * v20 + 8);
  }
LABEL_31:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 55, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, v11, v11);
  return v11;
}

```

## disassembly

```asm
0x18003986c  push    rbx
0x18003986e  push    rbp
0x18003986f  push    rsi
0x180039870  push    rdi
0x180039871  push    r12
0x180039873  push    r14
0x180039875  push    r15
0x180039877  sub     rsp, 30h
0x18003987b  mov     r14b, r9b
0x18003987e  mov     r12d, r8d
0x180039881  mov     r15, rdx
0x180039884  mov     rdi, rcx
0x180039887  test    rcx, rcx
0x18003988a  jnz     short loc_1800398D0
0x18003988c  neg     r14b
0x18003988f  sbb     edi, edi
0x180039891  and     edi, 0FFFFFDE8h
0x180039897  add     edi, 0C0000225h
0x18003989d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398a4  test    dword ptr [rcx+44h], 20000h
0x1800398ab  jz      short loc_1800398C9
0x1800398ad  mov     rcx, [rcx+38h]
0x1800398b1  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x1800398b8  mov     edx, 36h ; '6'
0x1800398bd  mov     [rsp+68h+var_48], edi
0x1800398c1  mov     r9d, edi
0x1800398c4  call    WPP_SF_Dd
0x1800398c9  mov     eax, edi
0x1800398cb  jmp     loc_180039AC1
0x1800398d0  xor     ebx, ebx
0x1800398d2  cmp     [rcx], ebx
0x1800398d4  jbe     short loc_1800398F5
0x1800398d6  mov     rdx, [rdi+8]
0x1800398da  lea     rcx, [rbx+rbx*2]
0x1800398de  mov     rdx, [rdx+rcx*8]; Sid2
0x1800398e2  mov     rcx, r15; Sid1
0x1800398e5  call    cs:__imp_RtlEqualSid
0x1800398eb  test    al, al
0x1800398ed  jnz     short loc_1800398F5
0x1800398ef  inc     ebx
0x1800398f1  cmp     ebx, [rdi]
0x1800398f3  jb      short loc_1800398D6
0x1800398f5  cmp     ebx, [rdi]
0x1800398f7  jnz     loc_1800399D7
0x1800398fd  test    r14b, r14b
0x180039900  jnz     short loc_18003990C
0x180039902  mov     ebx, 0C0000225h
0x180039907  jmp     loc_180039A93
0x18003990c  mov     eax, [rdi+4]
0x18003990f  cmp     ebx, eax
0x180039911  jb      short loc_180039970
0x180039913  lea     ebp, [rax+8]
0x180039916  mov     ecx, 40h ; '@'; uFlags
0x18003991b  lea     rdx, ds:0[rbp*2]
0x180039923  add     rdx, rbp
0x180039926  shl     rdx, 3; uBytes
0x18003992a  call    cs:__imp_LocalAlloc
0x180039930  mov     rsi, rax
0x180039933  test    rax, rax
0x180039936  jnz     short loc_180039942
0x180039938  mov     ebx, 0C0000017h
0x18003993d  jmp     loc_180039A93
0x180039942  cmp     dword ptr [rdi+4], 0
0x180039946  jbe     short loc_180039969
0x180039948  mov     eax, [rdi+4]
0x18003994b  mov     rcx, rsi; void *
0x18003994e  mov     rdx, [rdi+8]; Src
0x180039952  lea     r8, [rax+rax*2]
0x180039956  shl     r8, 3; Size
0x18003995a  call    memmove_0
0x18003995f  mov     rcx, [rdi+8]; hMem
0x180039963  call    cs:__imp_LocalFree
0x180039969  mov     [rdi+4], ebp
0x18003996c  mov     [rdi+8], rsi
0x180039970  mov     rcx, r15; Sid
0x180039973  call    cs:__imp_RtlLengthSid
0x180039979  mov     edx, eax; uBytes
0x18003997b  mov     ecx, 40h ; '@'; uFlags
0x180039980  mov     ebp, eax
0x180039982  call    cs:__imp_LocalAlloc
0x180039988  mov     rcx, [rdi+8]
0x18003998c  mov     esi, ebx
0x18003998e  lea     rbx, [rbx+rbx*2]
0x180039992  mov     [rcx+rbx*8], rax
0x180039996  mov     rax, [rdi+8]
0x18003999a  mov     rcx, [rax+rbx*8]; void *
0x18003999e  test    rcx, rcx
0x1800399a1  jz      short loc_180039938
0x1800399a3  mov     r8d, ebp; Size
0x1800399a6  mov     rdx, r15; Src
0x1800399a9  call    memmove_0
0x1800399ae  mov     rax, [rdi+8]
0x1800399b2  mov     dword ptr [rax+rbx*8+0Ch], 0
0x1800399ba  mov     rax, [rdi+8]
0x1800399be  mov     dword ptr [rax+rbx*8+8], 0
0x1800399c6  mov     rax, [rdi+8]
0x1800399ca  mov     qword ptr [rax+rbx*8+10h], 0
0x1800399d3  inc     dword ptr [rdi]
0x1800399d5  jmp     short loc_1800399D9
0x1800399d7  mov     esi, ebx
0x1800399d9  mov     rdx, [rdi+8]
0x1800399dd  lea     rsi, [rsi+rsi*2]
0x1800399e1  xor     ebx, ebx
0x1800399e3  xor     ebp, ebp
0x1800399e5  mov     ecx, [rdx+rsi*8+8]
0x1800399e9  test    ecx, ecx
0x1800399eb  jz      short loc_180039A02
0x1800399ed  mov     r8, [rdx+rsi*8+10h]
0x1800399f2  cmp     r12d, [r8+rbp*4]
0x1800399f6  jz      loc_180039A93
0x1800399fc  inc     ebp
0x1800399fe  cmp     ebp, ecx
0x180039a00  jb      short loc_1800399F2
0x180039a02  cmp     ebp, ecx
0x180039a04  jnz     loc_180039A93
0x180039a0a  test    r14b, r14b
0x180039a0d  jz      loc_180039902
0x180039a13  mov     eax, [rdx+rsi*8+0Ch]
0x180039a17  cmp     ebp, eax
0x180039a19  jb      short loc_180039A7E
0x180039a1b  lea     r15d, [rax+8]
0x180039a1f  mov     ecx, 40h ; '@'; uFlags
0x180039a24  mov     edx, r15d
0x180039a27  shl     rdx, 2; uBytes
0x180039a2b  call    cs:__imp_LocalAlloc
0x180039a31  mov     r14, rax
0x180039a34  test    rax, rax
0x180039a37  jz      loc_180039938
0x180039a3d  mov     rdx, [rdi+8]
0x180039a41  mov     eax, [rdx+rsi*8+0Ch]
0x180039a45  test    eax, eax
0x180039a47  jz      short loc_180039A6C
0x180039a49  mov     rdx, [rdx+rsi*8+10h]; Src
0x180039a4e  mov     r8d, eax
0x180039a51  shl     r8, 2; Size
0x180039a55  mov     rcx, r14; void *
0x180039a58  call    memmove_0
0x180039a5d  mov     rcx, [rdi+8]
0x180039a61  mov     rcx, [rcx+rsi*8+10h]; hMem
0x180039a66  call    cs:__imp_LocalFree
0x180039a6c  mov     rax, [rdi+8]
0x180039a70  mov     [rax+rsi*8+0Ch], r15d
0x180039a75  mov     rax, [rdi+8]
0x180039a79  mov     [rax+rsi*8+10h], r14
0x180039a7e  mov     rax, [rdi+8]
0x180039a82  mov     rax, [rax+rsi*8+10h]
0x180039a87  mov     [rax+rbp*4], r12d
0x180039a8b  mov     rax, [rdi+8]
0x180039a8f  inc     dword ptr [rax+rsi*8+8]
0x180039a93  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a9a  test    dword ptr [rcx+44h], 20000h
0x180039aa1  jz      short loc_180039ABF
0x180039aa3  mov     rcx, [rcx+38h]
0x180039aa7  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180039aae  mov     edx, 37h ; '7'
0x180039ab3  mov     [rsp+68h+var_48], ebx
0x180039ab7  mov     r9d, ebx
0x180039aba  call    WPP_SF_Dd
0x180039abf  mov     eax, ebx
0x180039ac1  add     rsp, 30h
0x180039ac5  pop     r15
0x180039ac7  pop     r14
0x180039ac9  pop     r12
0x180039acb  pop     rdi
0x180039acc  pop     rsi
0x180039acd  pop     rbp
0x180039ace  pop     rbx
0x180039acf  retn
```
