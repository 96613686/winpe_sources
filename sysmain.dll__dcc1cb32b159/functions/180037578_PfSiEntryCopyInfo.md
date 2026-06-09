# PfSiEntryCopyInfo

- ea: `0x180037578`
- end: `0x18003794e`
- name: `PfSiEntryCopyInfo`
- size: `982`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180036c4c`
- `0x180037004`

## callees

- `0x180028550`
- `0x180037394`
- `0x180037578`
- `0x18003a2ac`
- `0x18003a460`
- `0x180056494`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037787`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037787`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800377c4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800377c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003778d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003778d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800377e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800377e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037752`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037752`

## pseudocode

```c
__int64 __fastcall PfSiEntryCopyInfo(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rsi
  unsigned __int64 v4; // r14
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int8 *v10; // rcx
  _BYTE *v11; // rbp
  unsigned int v12; // r9d
  unsigned __int8 *v13; // rax
  unsigned __int64 v14; // r13
  unsigned __int8 *v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int8 *v17; // r10
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 inserted; // rax
  unsigned int v23; // ecx
  __int64 *v24; // rdx
  int v25; // ecx
  __int64 v26; // rdx
  __int64 v27; // r9
  int v28; // edx
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // r8
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  __int64 v35; // [rsp+38h] [rbp-160h]
  __int64 v36; // [rsp+40h] [rbp-158h]
  _BYTE Mem[256]; // [rsp+50h] [rbp-148h] BYREF

  v3 = a3[1];
  v4 = 0;
  if ( !v3 )
  {
LABEL_40:
    v26 = *(_QWORD *)(a2 + 24);
    *(_DWORD *)(a2 + 20) = *((_DWORD *)a3 + 5);
    *(_DWORD *)(a2 + 40) = *((_DWORD *)a3 + 7);
    if ( v26 )
    {
      PfSiEntryDereference(a1);
      *(_QWORD *)(a2 + 24) = 0;
    }
    v27 = *a3;
    if ( *a3 )
    {
      *(_QWORD *)(a2 + 24) = v27;
      v28 = *(_DWORD *)(v27 + 16);
      if ( (v28 & 0x3FFFFFF8) == 8 )
      {
        v29 = v28 & 3;
        v30 = a1 + 16 * (v29 + 22);
        if ( *(_QWORD *)(v30 + 8) != v30 )
        {
          v31 = (_QWORD *)(v27 + 32);
          v32 = (_QWORD *)(a1 + 16 * (v29 + 22));
          while ( 1 )
          {
            v33 = (_QWORD *)*v32;
            if ( (_QWORD *)*v32 == v31 )
              break;
            v32 = (_QWORD *)*v32;
            if ( v33 == *(_QWORD **)(v30 + 8) )
              goto LABEL_52;
          }
          *v32 = *v31;
          if ( *(_QWORD **)(v30 + 8) == v31 )
            *(_QWORD *)(v30 + 8) = v32;
          --**(_QWORD **)(v30 + 8);
        }
      }
LABEL_52:
      *(_DWORD *)(v27 + 16) ^= (*(_DWORD *)(v27 + 16) ^ (*(_DWORD *)(v27 + 16) + 16)) & 0x3FFFFFF0;
    }
    v23 = 0;
    if ( v4 )
    {
      PfScStringDereferenceEx(*(_QWORD *)&PfSvcGlobals + 96LL, v4, 0);
      PfSiEntryUpdateLog(a2, 19);
      return 0;
    }
    return v23;
  }
  if ( (*(_DWORD *)(a2 + 16) & 3) != 0 )
  {
    if ( (*(_DWORD *)(a2 + 16) & 3) == 1 )
    {
      v9 = PfScStringInsertEx(*(_QWORD *)&PfSvcGlobals + 96LL, *(_QWORD *)(v3 + 16), *(unsigned __int16 *)(v3 + 24));
      if ( !v9 )
        goto LABEL_36;
      if ( (*(_BYTE *)(a2 + 16) & 4) != 0 )
        v4 = *(_QWORD *)(a2 + 64);
      *(_OWORD *)(a2 + 48) = *(_OWORD *)v3;
      *(_OWORD *)(a2 + 64) = *(_OWORD *)(v3 + 16);
      *(_WORD *)(a2 + 74) |= 1u;
      *(_QWORD *)(a2 + 64) = v9;
    }
    else if ( (*(_DWORD *)(a2 + 16) & 3) == 2 )
    {
      v8 = PfScStringInsertEx(*(_QWORD *)&PfSvcGlobals + 96LL, v3 + 26, *(unsigned __int16 *)(v3 + 24));
      if ( !v8 )
        goto LABEL_36;
      if ( (*(_BYTE *)(a2 + 16) & 4) != 0 )
        v4 = *(_QWORD *)(a2 + 72);
      *(_OWORD *)(a2 + 48) = *(_OWORD *)v3;
      *(_OWORD *)(a2 + 64) = *(_OWORD *)(v3 + 16);
      *(_QWORD *)(a2 + 72) = v8;
    }
    goto LABEL_40;
  }
  v10 = (unsigned __int8 *)(v3 + 28);
  v11 = Mem;
  v36 = *(unsigned __int16 *)(v3 + 26);
  v35 = *(_QWORD *)&PfSvcGlobals + 96LL;
  v12 = 16;
  v13 = (unsigned __int8 *)(v3 + 26);
  v14 = v3 + 28 + 2 * v36;
  while ( 2 )
  {
    v15 = v10;
    v16 = (unsigned __int64)v11;
    v17 = v13;
    v18 = 314159;
    while ( 1 )
    {
      if ( v15 != (unsigned __int8 *)v14 && *(_WORD *)v15 != 92 )
        goto LABEL_19;
      if ( v16 >= (unsigned __int64)&v11[16 * v12] )
        break;
      *(_QWORD *)v16 = v18;
      v19 = v15 - v17;
      v17 = v15;
      *(_DWORD *)(v16 + 8) = (v19 >> 1) - 1;
      v16 += 16LL;
      if ( v15 == (unsigned __int8 *)v14 )
      {
        v16 = (__int64)(v16 - (_QWORD)v11) >> 4;
        goto LABEL_26;
      }
LABEL_19:
      v18 = v15[1] + 37 * (*v15 + 37 * v18);
      v15 += 2;
    }
    LODWORD(v16) = ((__int64)(v16 - (_QWORD)v11) >> 4) + 1;
    while ( (unsigned __int64)v15 < v14 )
    {
      v20 = v16 + 1;
      if ( *(_WORD *)v15 != 92 )
        v20 = v16;
      v15 += 2;
      LODWORD(v16) = v20;
    }
LABEL_26:
    if ( (unsigned int)v16 <= v12 )
    {
      RtlAcquireSRWLockExclusive(v35);
      *(_DWORD *)(v35 + 136) = GetCurrentThreadId();
      inserted = PfScStringInsertInternal(v35, (int)v3 + 28, v36, (_DWORD)v11, v16, 0);
      *(_DWORD *)(v35 + 136) = 0;
      v21 = inserted;
      RtlReleaseSRWLockExclusive(v35);
LABEL_32:
      if ( v11 && v11 != Mem )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v11);
      if ( !v21 )
        break;
      v24 = (__int64 *)(a2 + 72);
      if ( (*(_BYTE *)(a2 + 16) & 4) != 0 )
        v4 = *v24 & 0xFFFFFFFFFFFFFFFCuLL;
      *(_OWORD *)(a2 + 48) = *(_OWORD *)v3;
      *(_OWORD *)(a2 + 64) = *(_OWORD *)(v3 + 16);
      *v24 = v21;
      v25 = v21 ^ (*(_DWORD *)(v3 + 24) ^ v21) & 1;
      *(_DWORD *)v24 = v25;
      *(_DWORD *)v24 = v25 ^ ((unsigned __int8)v25 ^ (unsigned __int8)(*(_DWORD *)(v3 + 24) >> 1)) & 2;
      goto LABEL_40;
    }
    if ( (unsigned int)v16 > 0x100 )
    {
      v21 = 0;
      goto LABEL_32;
    }
    v11 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 16LL * (unsigned int)v16);
    if ( v11 )
    {
      v13 = (unsigned __int8 *)(v3 + 26);
      v10 = (unsigned __int8 *)(v3 + 28);
      v12 = v16;
      continue;
    }
    break;
  }
LABEL_36:
  v23 = 8;
  ++*(_DWORD *)(a1 + 4LL * (*(_DWORD *)(a2 + 16) & 3) + 448);
  return v23;
}

```

## disassembly

```asm
0x180037578  mov     [rsp+arg_18], rbx
0x18003757d  push    rbp
0x18003757e  push    rsi
0x18003757f  push    rdi
0x180037580  push    r12
0x180037582  push    r13
0x180037584  push    r14
0x180037586  push    r15
0x180037588  sub     rsp, 160h
0x18003758f  mov     rax, cs:__security_cookie
0x180037596  xor     rax, rsp
0x180037599  mov     [rsp+198h+var_48], rax
0x1800375a1  mov     rsi, [r8+8]
0x1800375a5  xor     r14d, r14d
0x1800375a8  mov     r12, r8
0x1800375ab  mov     rbx, rdx
0x1800375ae  mov     r15, rcx
0x1800375b1  test    rsi, rsi
0x1800375b4  jz      loc_18003784D
0x1800375ba  mov     eax, [rdx+10h]
0x1800375bd  lea     r11d, [r14+1]
0x1800375c1  and     eax, 3
0x1800375c4  jz      loc_180037671
0x1800375ca  sub     eax, r11d
0x1800375cd  jz      short loc_18003761F
0x1800375cf  cmp     eax, r11d
0x1800375d2  jnz     loc_18003784D
0x1800375d8  mov     rcx, cs:PfSvcGlobals
0x1800375df  lea     rdx, [rsi+1Ah]
0x1800375e3  movzx   r8d, word ptr [rsi+18h]
0x1800375e8  add     rcx, 60h ; '`'
0x1800375ec  xor     r9d, r9d
0x1800375ef  call    PfScStringInsertEx
0x1800375f4  test    rax, rax
0x1800375f7  jz      loc_1800377F4
0x1800375fd  test    byte ptr [rbx+10h], 4
0x180037601  jz      short loc_180037607
0x180037603  mov     r14, [rbx+48h]
0x180037607  movups  xmm0, xmmword ptr [rsi]
0x18003760a  movups  xmmword ptr [rbx+30h], xmm0
0x18003760e  movups  xmm1, xmmword ptr [rsi+10h]
0x180037612  movups  xmmword ptr [rbx+40h], xmm1
0x180037616  mov     [rbx+48h], rax
0x18003761a  jmp     loc_18003784D
0x18003761f  mov     rcx, cs:PfSvcGlobals
0x180037626  xor     r9d, r9d
0x180037629  movzx   r8d, word ptr [rsi+18h]
0x18003762e  add     rcx, 60h ; '`'
0x180037632  mov     rdx, [rsi+10h]
0x180037636  call    PfScStringInsertEx
0x18003763b  test    rax, rax
0x18003763e  jz      loc_1800377F4
0x180037644  test    byte ptr [rbx+10h], 4
0x180037648  jz      short loc_18003764E
0x18003764a  mov     r14, [rbx+40h]
0x18003764e  movups  xmm0, xmmword ptr [rsi]
0x180037651  mov     r8d, 1
0x180037657  movups  xmmword ptr [rbx+30h], xmm0
0x18003765b  movups  xmm1, xmmword ptr [rsi+10h]
0x18003765f  movups  xmmword ptr [rbx+40h], xmm1
0x180037663  or      [rbx+4Ah], r8w
0x180037668  mov     [rbx+40h], rax
0x18003766c  jmp     loc_18003784D
0x180037671  movzx   edx, word ptr [rsi+1Ah]
0x180037675  lea     rcx, [rsi+1Ch]
0x180037679  mov     rax, cs:PfSvcGlobals
0x180037680  lea     rbp, [rsp+198h+Mem]
0x180037685  add     rax, 60h ; '`'
0x180037689  mov     [rsp+198h+var_158], rdx
0x18003768e  mov     [rsp+198h+var_160], rax
0x180037693  mov     r9d, 10h
0x180037699  lea     rax, [rcx-2]
0x18003769d  mov     [rsp+198h+var_168], rax
0x1800376a2  lea     r13, [rcx+rdx*2]
0x1800376a6  mov     r8d, r9d
0x1800376a9  mov     rdx, rcx
0x1800376ac  shl     r8, 4
0x1800376b0  mov     rdi, rbp
0x1800376b3  add     r8, rbp
0x1800376b6  mov     r10, rax
0x1800376b9  mov     ecx, 4CB2Fh
0x1800376be  cmp     rdx, r13
0x1800376c1  jz      short loc_1800376C9
0x1800376c3  cmp     word ptr [rdx], 5Ch ; '\'
0x1800376c7  jnz     short loc_1800376EC
0x1800376c9  cmp     rdi, r8
0x1800376cc  jnb     short loc_180037710
0x1800376ce  mov     rax, rdx
0x1800376d1  mov     [rdi], rcx
0x1800376d4  sub     rax, r10
0x1800376d7  mov     r10, rdx
0x1800376da  sar     rax, 1
0x1800376dd  sub     eax, r11d
0x1800376e0  mov     [rdi+8], eax
0x1800376e3  add     rdi, 10h
0x1800376e7  cmp     rdx, r13
0x1800376ea  jz      short loc_180037707
0x1800376ec  movzx   eax, byte ptr [rdx]
0x1800376ef  imul    rcx, 25h ; '%'
0x1800376f3  add     rcx, rax
0x1800376f6  movzx   eax, byte ptr [rdx+1]
0x1800376fa  imul    rcx, 25h ; '%'
0x1800376fe  add     rcx, rax
0x180037701  add     rdx, 2
0x180037705  jmp     short loc_1800376BE
0x180037707  sub     rdi, rbp
0x18003770a  sar     rdi, 4
0x18003770e  jmp     short loc_180037731
0x180037710  sub     rdi, rbp
0x180037713  sar     rdi, 4
0x180037717  add     edi, r11d
0x18003771a  jmp     short loc_18003772C
0x18003771c  cmp     word ptr [rdx], 5Ch ; '\'
0x180037720  lea     eax, [rdi+1]
0x180037723  cmovnz  eax, edi
0x180037726  add     rdx, 2
0x18003772a  mov     edi, eax
0x18003772c  cmp     rdx, r13
0x18003772f  jb      short loc_18003771C
0x180037731  cmp     edi, r9d
0x180037734  jbe     short loc_18003777F
0x180037736  cmp     edi, 100h
0x18003773c  ja      short loc_18003777B
0x18003773e  mov     rcx, cs:PfSvcGlobals
0x180037745  xor     edx, edx; dwFlags
0x180037747  mov     r8d, edi
0x18003774a  shl     r8, 4; dwBytes
0x18003774e  mov     rcx, [rcx+58h]; hHeap
0x180037752  call    cs:__imp_HeapAlloc
0x180037758  mov     rbp, rax
0x18003775b  test    rax, rax
0x18003775e  jz      loc_1800377F4
0x180037764  mov     rax, [rsp+198h+var_168]
0x180037769  lea     rcx, [rsi+1Ch]
0x18003776d  mov     r9d, edi
0x180037770  mov     r11d, 1
0x180037776  jmp     loc_1800376A6
0x18003777b  xor     edi, edi
0x18003777d  jmp     short loc_1800377CA
0x18003777f  mov     r13, [rsp+198h+var_160]
0x180037784  mov     rcx, r13
0x180037787  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003778d  call    cs:__imp_GetCurrentThreadId
0x180037793  mov     r8d, dword ptr [rsp+198h+var_158]
0x180037798  lea     rdx, [rsi+1Ch]
0x18003779c  mov     r9, rbp
0x18003779f  mov     [rsp+198h+var_170], r14
0x1800377a4  mov     rcx, r13
0x1800377a7  mov     [r13+88h], eax
0x1800377ae  mov     [rsp+198h+var_178], edi
0x1800377b2  call    PfScStringInsertInternal
0x1800377b7  mov     rcx, r13
0x1800377ba  mov     [r13+88h], r14d
0x1800377c1  mov     rdi, rax
0x1800377c4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800377ca  test    rbp, rbp
0x1800377cd  jz      short loc_1800377EF
0x1800377cf  lea     rax, [rsp+198h+Mem]
0x1800377d4  cmp     rbp, rax
0x1800377d7  jz      short loc_1800377EF
0x1800377d9  mov     rcx, cs:PfSvcGlobals
0x1800377e0  mov     r8, rbp; lpMem
0x1800377e3  xor     edx, edx; dwFlags
0x1800377e5  mov     rcx, [rcx+58h]; hHeap
0x1800377e9  call    cs:__imp_HeapFree
0x1800377ef  test    rdi, rdi
0x1800377f2  jnz     short loc_180037810
0x1800377f4  mov     eax, [rbx+10h]
0x1800377f7  mov     ecx, 8
0x1800377fc  and     eax, 3
0x1800377ff  lea     r8d, [rcx-7]
0x180037803  add     [r15+rax*4+1C0h], r8d
0x18003780b  jmp     loc_180037921
0x180037810  test    byte ptr [rbx+10h], 4
0x180037814  lea     rdx, [rbx+48h]
0x180037818  jz      short loc_180037821
0x18003781a  mov     r14, [rdx]
0x18003781d  and     r14, 0FFFFFFFFFFFFFFFCh
0x180037821  movups  xmm0, xmmword ptr [rsi]
0x180037824  mov     ecx, edi
0x180037826  movups  xmmword ptr [rbx+30h], xmm0
0x18003782a  movups  xmm1, xmmword ptr [rsi+10h]
0x18003782e  movups  xmmword ptr [rbx+40h], xmm1
0x180037832  mov     [rdx], rdi
0x180037835  xor     ecx, [rsi+18h]
0x180037838  and     ecx, 1
0x18003783b  xor     ecx, edi
0x18003783d  mov     [rdx], ecx
0x18003783f  mov     eax, [rsi+18h]
0x180037842  shr     eax, 1
0x180037844  xor     eax, ecx
0x180037846  and     eax, 2
0x180037849  xor     eax, ecx
0x18003784b  mov     [rdx], eax
0x18003784d  mov     eax, [r12+14h]
0x180037852  mov     rdx, [rbx+18h]
0x180037856  mov     [rbx+14h], eax
0x180037859  mov     eax, [r12+1Ch]
0x18003785e  mov     [rbx+28h], eax
0x180037861  test    rdx, rdx
0x180037864  jz      short loc_180037876
0x180037866  mov     rcx, r15
0x180037869  call    PfSiEntryDereference
0x18003786e  mov     qword ptr [rbx+18h], 0
0x180037876  mov     r9, [r12]
0x18003787a  test    r9, r9
0x18003787d  jz      short loc_1800378F5
0x18003787f  mov     [rbx+18h], r9
0x180037883  mov     ecx, 8
0x180037888  mov     edx, [r9+10h]
0x18003788c  mov     eax, edx
0x18003788e  and     eax, 3FFFFFF8h
0x180037893  cmp     eax, ecx
0x180037895  jnz     short loc_1800378DC
0x180037897  and     edx, 3
0x18003789a  lea     rcx, [rdx+16h]
0x18003789e  shl     rcx, 4
0x1800378a2  add     rcx, r15
0x1800378a5  cmp     [rcx+8], rcx
0x1800378a9  jz      short loc_1800378DC
0x1800378ab  lea     r8, [r9+20h]
0x1800378af  mov     rdx, rcx
0x1800378b2  mov     rax, [rdx]
0x1800378b5  cmp     rax, r8
0x1800378b8  jz      short loc_1800378C5
0x1800378ba  mov     rdx, rax
0x1800378bd  cmp     rax, [rcx+8]
0x1800378c1  jnz     short loc_1800378B2
0x1800378c3  jmp     short loc_1800378DC
0x1800378c5  mov     rax, [r8]
0x1800378c8  mov     [rdx], rax
0x1800378cb  cmp     [rcx+8], r8
0x1800378cf  jnz     short loc_1800378D5
0x1800378d1  mov     [rcx+8], rdx
0x1800378d5  mov     rax, [rcx+8]
0x1800378d9  dec     qword ptr [rax]
0x1800378dc  mov     eax, [r9+10h]
0x1800378e0  lea     r8d, [rax+10h]
0x1800378e4  xor     r8d, eax
0x1800378e7  and     r8d, 3FFFFFF0h
0x1800378ee  xor     r8d, eax
0x1800378f1  mov     [r9+10h], r8d
0x1800378f5  xor     ecx, ecx
0x1800378f7  test    r14, r14
0x1800378fa  jz      short loc_180037921
0x1800378fc  mov     rcx, cs:PfSvcGlobals
0x180037903  xor     r8d, r8d
0x180037906  add     rcx, 60h ; '`'
0x18003790a  mov     rdx, r14
0x18003790d  call    PfScStringDereferenceEx
0x180037912  mov     edx, 13h
0x180037917  mov     rcx, rbx
0x18003791a  call    PfSiEntryUpdateLog
0x18003791f  xor     ecx, ecx
0x180037921  mov     eax, ecx
0x180037923  mov     rcx, [rsp+198h+var_48]
0x18003792b  xor     rcx, rsp; StackCookie
0x18003792e  call    __security_check_cookie
0x180037933  mov     rbx, [rsp+198h+arg_18]
0x18003793b  add     rsp, 160h
0x180037942  pop     r15
0x180037944  pop     r14
0x180037946  pop     r13
0x180037948  pop     r12
0x18003794a  pop     rdi
0x18003794b  pop     rsi
0x18003794c  pop     rbp
0x18003794d  retn
```
