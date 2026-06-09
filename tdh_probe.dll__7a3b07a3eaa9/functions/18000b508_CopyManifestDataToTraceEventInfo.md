# CopyManifestDataToTraceEventInfo

- ea: `0x18000b508`
- end: `0x18000b9be`
- name: `CopyManifestDataToTraceEventInfo`
- size: `1206`
- prototype: `__int64 __fastcall(int, __int64, _OWORD *, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009c7c`

## callees

- `0x18000b508`
- `0x18000b9d0`
- `0x18000c3f0`
- `0x180023b05`

## pseudocode

```c
__int64 __fastcall CopyManifestDataToTraceEventInfo(int a1, __int64 a2, _OWORD *a3, __int64 a4, int a5, _DWORD *a6)
{
  __int64 v9; // rax
  int v10; // edx
  __int128 v11; // xmm0
  __int128 v12; // xmm0
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  _WORD *v19; // rcx
  __int64 v20; // r10
  unsigned __int64 v21; // r8
  __int64 v22; // rax
  _WORD *v23; // r9
  _WORD *v24; // rcx
  unsigned int v25; // edx
  _WORD *v26; // rcx
  const wchar_t *v27; // r8
  unsigned int i; // r10d
  __int64 v29; // rcx
  const wchar_t *v30; // r8
  const wchar_t *v31; // r8
  const wchar_t *v32; // r8
  const wchar_t *v33; // r8
  const void *v34; // rdx
  const wchar_t *v35; // r8
  const wchar_t *v36; // r8
  unsigned int j; // ebp
  __int64 result; // rax
  unsigned __int64 v39; // r8
  _WORD *v40; // r9
  _WORD *v41; // rcx
  const wchar_t *v42; // r8
  __int64 v43; // r11
  __int64 v44; // r14

  *(_OWORD *)a4 = *a3;
  if ( *(_BYTE *)(a2 + 964) )
  {
    v11 = *(_OWORD *)(a2 + 968);
    v10 = 4;
  }
  else
  {
    v9 = *(_QWORD *)(a2 + 1032);
    v10 = 0;
    if ( v9 )
      v11 = *(_OWORD *)(v9 + 8);
    else
      v11 = 0;
  }
  *(_OWORD *)(a4 + 16) = v11;
  v12 = *(_OWORD *)(a2 + 984);
  *(_DWORD *)(a4 + 48) = 0;
  *(_OWORD *)(a4 + 32) = v12;
  v13 = *(_QWORD *)(a2 + 1008);
  if ( v13 )
    v14 = *(_DWORD *)(v13 + 12);
  else
    v14 = 0;
  *(_DWORD *)(a4 + 100) = v14;
  v15 = *(_QWORD *)(a2 + 1008);
  if ( v15 )
    v16 = *(_DWORD *)(v15 + 8);
  else
    v16 = 0;
  *(_DWORD *)(a4 + 104) = v16;
  v17 = *(_QWORD *)(a2 + 1008);
  if ( v17 )
    v10 |= *(_DWORD *)(v17 + 20);
  *(_DWORD *)(a4 + 108) = v10;
  if ( v14 )
  {
    v18 = 24LL * (unsigned int)(v14 - 1) + 136;
    if ( v18 > 0xFFFFFFFF )
      return 534;
  }
  else
  {
    LODWORD(v18) = 136;
  }
  v19 = *(_WORD **)a2;
  v20 = 2147483646;
  if ( *(_QWORD *)a2 )
  {
    v21 = (unsigned __int64)(unsigned int)(a5 - v18) >> 1;
    if ( !v21 )
    {
LABEL_78:
      LOWORD(v25) = 87;
      return (unsigned __int16)v25;
    }
    v22 = 2147483646;
    v23 = (_WORD *)(a4 + (unsigned int)v18);
    do
    {
      if ( !v22 )
        break;
      if ( !*v19 )
        break;
      *v23++ = *v19++;
      --v22;
      --v21;
    }
    while ( v21 );
    v24 = v23 - 1;
    v25 = v21 == 0 ? 0x8007007A : 0;
    if ( v21 )
      v24 = v23;
    *v24 = 0;
    if ( !v21 )
      return (unsigned __int16)v25;
    *(_DWORD *)(a4 + 52) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 592) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 52) = 0;
  }
  v26 = *(_WORD **)(a2 + 8);
  if ( !v26 )
  {
    *(_DWORD *)(a4 + 56) = 0;
    goto LABEL_24;
  }
  v39 = (unsigned __int64)(unsigned int)(a5 - v18) >> 1;
  if ( !v39 )
    goto LABEL_78;
  v40 = (_WORD *)(a4 + (unsigned int)v18);
  do
  {
    if ( !v20 )
      break;
    if ( !*v26 )
      break;
    *v40++ = *v26++;
    --v20;
    --v39;
  }
  while ( v39 );
  v41 = v40 - 1;
  v25 = v39 == 0 ? 0x8007007A : 0;
  if ( v39 )
    v41 = v40;
  *v41 = 0;
  if ( !v39 )
    return (unsigned __int16)v25;
  *(_DWORD *)(a4 + 56) = v18;
  LODWORD(v18) = *(_DWORD *)(a2 + 596) + v18;
LABEL_24:
  v27 = *(const wchar_t **)(a2 + 16);
  if ( v27 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v27);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 60) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 600) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 60) = 0;
  }
  if ( *(_DWORD *)(a2 + 860) )
  {
    *(_DWORD *)(a4 + 64) = v18;
    for ( i = 0; i < *(_DWORD *)(a2 + 860); ++i )
    {
      v42 = *(const wchar_t **)(a2 + 8LL * i + 24);
      if ( v42 )
      {
        LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v42);
        if ( (int)result < 0 )
          return (unsigned __int16)result;
        LODWORD(v18) = *(_DWORD *)(a2 + 4 * v43 + 604) + v18;
      }
    }
    v29 = (unsigned int)v18;
    LODWORD(v18) = v18 + 2;
    *(_WORD *)(v29 + a4) = 0;
  }
  else
  {
    *(_DWORD *)(a4 + 64) = 0;
  }
  v30 = *(const wchar_t **)(a2 + 536);
  if ( v30 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v30);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 68) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 864) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 68) = 0;
  }
  v31 = *(const wchar_t **)(a2 + 544);
  if ( v31 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v31);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 72) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 868) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 72) = 0;
  }
  v32 = *(const wchar_t **)(a2 + 552);
  if ( v32 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v32);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 76) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 872) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 76) = 0;
  }
  v33 = *(const wchar_t **)(a2 + 560);
  if ( v33 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v33);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 80) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 876) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 80) = 0;
  }
  v34 = *(const void **)(a2 + 568);
  if ( v34 )
  {
    memcpy_0((void *)(a4 + (unsigned int)v18), v34, *(unsigned int *)(a2 + 880));
    *(_DWORD *)(a4 + 84) = v18;
    *(_DWORD *)(a4 + 88) = *(_DWORD *)(a2 + 880);
    LODWORD(v18) = (*(_DWORD *)(a2 + 880) + 1 + v18) & 0xFFFFFFFE;
  }
  else
  {
    *(_QWORD *)(a4 + 84) = 0;
  }
  v35 = *(const wchar_t **)(a2 + 576);
  if ( v35 )
  {
    LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v35);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    *(_DWORD *)(a4 + 92) = v18;
    LODWORD(v18) = *(_DWORD *)(a2 + 884) + v18;
  }
  else
  {
    *(_DWORD *)(a4 + 92) = 0;
  }
  v36 = *(const wchar_t **)(a2 + 584);
  if ( !v36 )
  {
    *(_DWORD *)(a4 + 96) = 0;
    goto LABEL_44;
  }
  LODWORD(result) = StringCbCopyW((wchar_t *)(a4 + (unsigned int)v18), (unsigned int)(a5 - v18), v36);
  if ( (int)result < 0 )
    return (unsigned __int16)result;
  *(_DWORD *)(a4 + 96) = v18;
  LODWORD(v18) = *(_DWORD *)(a2 + 888) + v18;
LABEL_44:
  for ( j = 0; j < *(_DWORD *)(a4 + 100); ++j )
  {
    v44 = *(_QWORD *)(a2 + 1064) + 88LL * j;
    result = FillEventPropertyInfoFromManifest(
               a1,
               *(_DWORD *)(a2 + 1064) + 88 * j,
               (unsigned int)a4 + 8 * (j + 2 * (j + 7)),
               a4,
               v18);
    if ( (_DWORD)result )
      return result;
    LODWORD(v18) = *(_DWORD *)(v44 + 64) + *(_DWORD *)(v44 + 72) + v18;
  }
  *a6 = v18;
  return 0;
}

```

## disassembly

```asm
0x18000b508  push    rbx
0x18000b50a  push    rbp
0x18000b50b  push    rsi
0x18000b50c  push    rdi
0x18000b50d  push    r12
0x18000b50f  push    r14
0x18000b511  push    r15
0x18000b513  sub     rsp, 30h
0x18000b517  movups  xmm0, xmmword ptr [r8]
0x18000b51b  xor     r12d, r12d
0x18000b51e  mov     rdi, r9
0x18000b521  mov     rsi, rdx
0x18000b524  mov     r15d, ecx
0x18000b527  movdqu  xmmword ptr [r9], xmm0
0x18000b52c  cmp     [rdx+3C4h], r12b
0x18000b533  jnz     loc_18000B8A5
0x18000b539  mov     rax, [rsi+408h]
0x18000b540  mov     edx, r12d
0x18000b543  test    rax, rax
0x18000b546  jnz     loc_18000B761
0x18000b54c  xorps   xmm0, xmm0
0x18000b54f  movdqu  xmmword ptr [r9+10h], xmm0
0x18000b555  movups  xmm0, xmmword ptr [rsi+3D8h]
0x18000b55c  mov     [r9+30h], r12d
0x18000b560  movdqu  xmmword ptr [r9+20h], xmm0
0x18000b566  mov     rax, [rsi+3F0h]
0x18000b56d  test    rax, rax
0x18000b570  jz      loc_18000B76A
0x18000b576  mov     eax, [rax+0Ch]
0x18000b579  mov     [r9+64h], eax
0x18000b57d  mov     rcx, [rsi+3F0h]
0x18000b584  test    rcx, rcx
0x18000b587  jnz     loc_18000B74F
0x18000b58d  mov     ecx, r12d
0x18000b590  mov     [r9+68h], ecx
0x18000b594  mov     rcx, [rsi+3F0h]
0x18000b59b  test    rcx, rcx
0x18000b59e  jnz     loc_18000B8B6
0x18000b5a4  mov     [r9+6Ch], edx
0x18000b5a8  test    eax, eax
0x18000b5aa  jz      loc_18000B757
0x18000b5b0  dec     eax
0x18000b5b2  lea     rax, [rax+rax*2]
0x18000b5b6  lea     rbx, ds:88h[rax*8]
0x18000b5be  mov     eax, 0FFFFFFFFh
0x18000b5c3  cmp     rbx, rax
0x18000b5c6  ja      loc_18000B77B
0x18000b5cc  mov     rcx, [rsi]
0x18000b5cf  mov     r10d, 7FFFFFFEh
0x18000b5d5  mov     ebp, [rsp+68h+arg_20]
0x18000b5dc  mov     r11d, 8007007Ah
0x18000b5e2  test    rcx, rcx
0x18000b5e5  jz      loc_18000B772
0x18000b5eb  mov     r8d, ebp
0x18000b5ee  sub     r8d, ebx
0x18000b5f1  shr     r8, 1
0x18000b5f4  jz      loc_18000B906
0x18000b5fa  mov     r9d, ebx
0x18000b5fd  mov     eax, r10d
0x18000b600  add     r9, rdi
0x18000b603  test    rax, rax
0x18000b606  jz      short loc_18000B625
0x18000b608  movzx   edx, word ptr [rcx]
0x18000b60b  test    dx, dx
0x18000b60e  jz      short loc_18000B625
0x18000b610  mov     [r9], dx
0x18000b614  add     rcx, 2
0x18000b618  add     r9, 2
0x18000b61c  dec     rax
0x18000b61f  sub     r8, 1
0x18000b623  jnz     short loc_18000B603
0x18000b625  mov     rax, r8
0x18000b628  lea     rcx, [r9-2]
0x18000b62c  neg     rax
0x18000b62f  sbb     edx, edx
0x18000b631  not     edx
0x18000b633  and     edx, r11d
0x18000b636  test    r8, r8
0x18000b639  cmovnz  rcx, r9
0x18000b63d  mov     [rcx], r12w
0x18000b641  jz      loc_18000B90B
0x18000b647  mov     [rdi+34h], ebx
0x18000b64a  add     ebx, [rsi+250h]
0x18000b650  mov     rcx, [rsi+8]
0x18000b654  test    rcx, rcx
0x18000b657  jnz     loc_18000B782
0x18000b65d  mov     [rdi+38h], r12d
0x18000b661  mov     r8, [rsi+10h]; wchar_t *
0x18000b665  test    r8, r8
0x18000b668  jnz     loc_18000B8E2
0x18000b66e  mov     [rdi+3Ch], r12d
0x18000b672  cmp     [rsi+35Ch], r12d
0x18000b679  jz      loc_18000B838
0x18000b67f  mov     [rdi+40h], ebx
0x18000b682  mov     r10d, r12d
0x18000b685  cmp     r10d, [rsi+35Ch]
0x18000b68c  jb      loc_18000B7E9
0x18000b692  mov     ecx, ebx
0x18000b694  add     ebx, 2
0x18000b697  mov     [rcx+rdi], r12w
0x18000b69c  mov     r8, [rsi+218h]; wchar_t *
0x18000b6a3  test    r8, r8
0x18000b6a6  jnz     loc_18000B818
0x18000b6ac  mov     [rdi+44h], r12d
0x18000b6b0  mov     r8, [rsi+220h]; wchar_t *
0x18000b6b7  test    r8, r8
0x18000b6ba  jnz     loc_18000B923
0x18000b6c0  mov     [rdi+48h], r12d
0x18000b6c4  mov     r8, [rsi+228h]; wchar_t *
0x18000b6cb  test    r8, r8
0x18000b6ce  jnz     loc_18000B841
0x18000b6d4  mov     [rdi+4Ch], r12d
0x18000b6d8  mov     r8, [rsi+230h]; wchar_t *
0x18000b6df  test    r8, r8
0x18000b6e2  jnz     loc_18000B8BE
0x18000b6e8  mov     [rdi+50h], r12d
0x18000b6ec  mov     rdx, [rsi+238h]; Src
0x18000b6f3  test    rdx, rdx
0x18000b6f6  jnz     loc_18000B947
0x18000b6fc  mov     [rdi+54h], r12
0x18000b700  mov     r8, [rsi+240h]; wchar_t *
0x18000b707  test    r8, r8
0x18000b70a  jnz     loc_18000B976
0x18000b710  mov     [rdi+5Ch], r12d
0x18000b714  mov     r8, [rsi+248h]; wchar_t *
0x18000b71b  test    r8, r8
0x18000b71e  jnz     loc_18000B99A
0x18000b724  mov     [rdi+60h], r12d
0x18000b728  mov     ebp, r12d
0x18000b72b  cmp     ebp, [rdi+64h]
0x18000b72e  jb      loc_18000B861
0x18000b734  mov     rax, [rsp+68h+arg_28]
0x18000b73c  mov     [rax], ebx
0x18000b73e  xor     eax, eax
0x18000b740  add     rsp, 30h
0x18000b744  pop     r15
0x18000b746  pop     r14
0x18000b748  pop     r12
0x18000b74a  pop     rdi
0x18000b74b  pop     rsi
0x18000b74c  pop     rbp
0x18000b74d  pop     rbx
0x18000b74e  retn
0x18000b74f  mov     ecx, [rcx+8]
0x18000b752  jmp     loc_18000B590
0x18000b757  mov     ebx, 88h
0x18000b75c  jmp     loc_18000B5CC
0x18000b761  movups  xmm0, xmmword ptr [rax+8]
0x18000b765  jmp     loc_18000B54F
0x18000b76a  mov     eax, r12d
0x18000b76d  jmp     loc_18000B579
0x18000b772  mov     [r9+34h], r12d
0x18000b776  jmp     loc_18000B650
0x18000b77b  mov     eax, 216h
0x18000b780  jmp     short loc_18000B740
0x18000b782  mov     r8d, ebp
0x18000b785  sub     r8d, ebx
0x18000b788  shr     r8, 1
0x18000b78b  jz      loc_18000B906
0x18000b791  mov     r9d, ebx
0x18000b794  add     r9, rdi
0x18000b797  test    r10, r10
0x18000b79a  jz      short loc_18000B7B9
0x18000b79c  movzx   eax, word ptr [rcx]
0x18000b79f  test    ax, ax
0x18000b7a2  jz      short loc_18000B7B9
0x18000b7a4  mov     [r9], ax
0x18000b7a8  add     rcx, 2
0x18000b7ac  add     r9, 2
0x18000b7b0  dec     r10
0x18000b7b3  sub     r8, 1
0x18000b7b7  jnz     short loc_18000B797
0x18000b7b9  mov     rax, r8
0x18000b7bc  lea     rcx, [r9-2]
0x18000b7c0  neg     rax
0x18000b7c3  sbb     edx, edx
0x18000b7c5  not     edx
0x18000b7c7  and     edx, r11d
0x18000b7ca  test    r8, r8
0x18000b7cd  cmovnz  rcx, r9
0x18000b7d1  mov     [rcx], r12w
0x18000b7d5  jz      loc_18000B90B
0x18000b7db  mov     [rdi+38h], ebx
0x18000b7de  add     ebx, [rsi+254h]
0x18000b7e4  jmp     loc_18000B661
0x18000b7e9  mov     r11d, r10d
0x18000b7ec  mov     r8, [rsi+r11*8+18h]; wchar_t *
0x18000b7f1  test    r8, r8
0x18000b7f4  jz      loc_18000B91B
0x18000b7fa  mov     edx, ebp
0x18000b7fc  mov     ecx, ebx
0x18000b7fe  sub     edx, ebx; unsigned __int64
0x18000b800  add     rcx, rdi; wchar_t *
0x18000b803  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b808  test    eax, eax
0x18000b80a  jns     loc_18000B913
0x18000b810  movzx   eax, ax
0x18000b813  jmp     loc_18000B740
0x18000b818  mov     edx, ebp
0x18000b81a  mov     ecx, ebx
0x18000b81c  sub     edx, ebx; unsigned __int64
0x18000b81e  add     rcx, rdi; wchar_t *
0x18000b821  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b826  test    eax, eax
0x18000b828  js      short loc_18000B810
0x18000b82a  mov     [rdi+44h], ebx
0x18000b82d  add     ebx, [rsi+360h]
0x18000b833  jmp     loc_18000B6B0
0x18000b838  mov     [rdi+40h], r12d
0x18000b83c  jmp     loc_18000B69C
0x18000b841  mov     edx, ebp
0x18000b843  mov     ecx, ebx
0x18000b845  sub     edx, ebx; unsigned __int64
0x18000b847  add     rcx, rdi; wchar_t *
0x18000b84a  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b84f  test    eax, eax
0x18000b851  js      short loc_18000B810
0x18000b853  mov     [rdi+4Ch], ebx
0x18000b856  add     ebx, [rsi+368h]
0x18000b85c  jmp     loc_18000B6D8
0x18000b861  mov     edx, ebp
0x18000b863  mov     r9, rdi
0x18000b866  imul    r14, rdx, 58h ; 'X'
0x18000b86a  mov     ecx, r15d
0x18000b86d  mov     [rsp+68h+var_48], ebx
0x18000b871  add     r14, [rsi+428h]
0x18000b878  lea     rax, [rdx+7]
0x18000b87c  lea     rax, [rdx+rax*2]
0x18000b880  mov     rdx, r14
0x18000b883  lea     r8, [rdi+rax*8]
0x18000b887  call    FillEventPropertyInfoFromManifest
0x18000b88c  test    eax, eax
0x18000b88e  jnz     loc_18000B740
0x18000b894  mov     eax, [r14+48h]
0x18000b898  add     eax, [r14+40h]
0x18000b89c  add     ebx, eax
0x18000b89e  inc     ebp
0x18000b8a0  jmp     loc_18000B72B
0x18000b8a5  movups  xmm0, xmmword ptr [rsi+3C8h]
0x18000b8ac  mov     edx, 4
0x18000b8b1  jmp     loc_18000B54F
0x18000b8b6  or      edx, [rcx+14h]
0x18000b8b9  jmp     loc_18000B5A4
0x18000b8be  mov     edx, ebp
0x18000b8c0  mov     ecx, ebx
0x18000b8c2  sub     edx, ebx; unsigned __int64
0x18000b8c4  add     rcx, rdi; wchar_t *
0x18000b8c7  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b8cc  test    eax, eax
0x18000b8ce  js      loc_18000B810
0x18000b8d4  mov     [rdi+50h], ebx
0x18000b8d7  add     ebx, [rsi+36Ch]
0x18000b8dd  jmp     loc_18000B6EC
0x18000b8e2  mov     edx, ebp
0x18000b8e4  mov     ecx, ebx
0x18000b8e6  sub     edx, ebx; unsigned __int64
0x18000b8e8  add     rcx, rdi; wchar_t *
0x18000b8eb  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b8f0  test    eax, eax
0x18000b8f2  js      loc_18000B810
0x18000b8f8  mov     [rdi+3Ch], ebx
0x18000b8fb  add     ebx, [rsi+258h]
0x18000b901  jmp     loc_18000B672
0x18000b906  mov     edx, 80070057h
0x18000b90b  movzx   eax, dx
0x18000b90e  jmp     loc_18000B740
0x18000b913  add     ebx, [rsi+r11*4+25Ch]
0x18000b91b  inc     r10d
0x18000b91e  jmp     loc_18000B685
0x18000b923  mov     edx, ebp
0x18000b925  mov     ecx, ebx
0x18000b927  sub     edx, ebx; unsigned __int64
0x18000b929  add     rcx, rdi; wchar_t *
0x18000b92c  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b931  test    eax, eax
0x18000b933  js      loc_18000B810
0x18000b939  mov     [rdi+48h], ebx
0x18000b93c  add     ebx, [rsi+364h]
0x18000b942  jmp     loc_18000B6C4
0x18000b947  mov     r8d, [rsi+370h]; Size
0x18000b94e  mov     ecx, ebx
0x18000b950  add     rcx, rdi; void *
0x18000b953  call    memcpy_0
0x18000b958  mov     [rdi+54h], ebx
0x18000b95b  mov     eax, [rsi+370h]
0x18000b961  mov     [rdi+58h], eax
0x18000b964  mov     eax, [rsi+370h]
0x18000b96a  inc     eax
0x18000b96c  add     ebx, eax
0x18000b96e  and     ebx, 0FFFFFFFEh
0x18000b971  jmp     loc_18000B700
0x18000b976  mov     edx, ebp
0x18000b978  mov     ecx, ebx
0x18000b97a  sub     edx, ebx; unsigned __int64
0x18000b97c  add     rcx, rdi; wchar_t *
0x18000b97f  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b984  test    eax, eax
0x18000b986  js      loc_18000B810
0x18000b98c  mov     [rdi+5Ch], ebx
0x18000b98f  add     ebx, [rsi+374h]
  ... truncated ...
```
