# TGetEventMasksOrSubMasks

- ea: `0x180034a80`
- end: `0x180034f9a`
- name: `TGetEventMasksOrSubMasks`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x18001c7c0`
- `0x18001f494`
- `0x1800344d0`
- `0x180034a80`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180034ac6`
- `KERNEL32!GetCurrentThreadId` at `0x180034f3e`
- `KERNEL32!GetCurrentThreadId` at `0x180034ac6`
- `KERNEL32!GetCurrentThreadId` at `0x180034f3e`
- `KERNEL32!LeaveCriticalSection` at `0x180034be9`
- `KERNEL32!LeaveCriticalSection` at `0x180034f26`
- `KERNEL32!LeaveCriticalSection` at `0x180034f64`
- `KERNEL32!LeaveCriticalSection` at `0x180034be9`
- `KERNEL32!LeaveCriticalSection` at `0x180034f26`
- `KERNEL32!LeaveCriticalSection` at `0x180034f64`
- `KERNEL32!EnterCriticalSection` at `0x180034ab6`
- `KERNEL32!EnterCriticalSection` at `0x180034b69`
- `KERNEL32!EnterCriticalSection` at `0x180034c47`
- `KERNEL32!EnterCriticalSection` at `0x180034ce8`
- `KERNEL32!EnterCriticalSection` at `0x180034d8d`
- `KERNEL32!EnterCriticalSection` at `0x180034e31`
- `KERNEL32!EnterCriticalSection` at `0x180034ab6`
- `KERNEL32!EnterCriticalSection` at `0x180034b69`
- `KERNEL32!EnterCriticalSection` at `0x180034c47`
- `KERNEL32!EnterCriticalSection` at `0x180034ce8`
- `KERNEL32!EnterCriticalSection` at `0x180034d8d`
- `KERNEL32!EnterCriticalSection` at `0x180034e31`

## pseudocode

```c
_DWORD *__fastcall TGetEventMasksOrSubMasks(unsigned __int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned __int64 v7; // rbp
  __int64 v8; // rdi
  size_t v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // r14
  unsigned int SubMaskIndex; // eax
  __int64 v20; // r9
  _DWORD *v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 i; // rax
  int v25; // eax
  __int64 v26; // rcx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rsi
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 j; // rax
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 k; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rsi
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 m; // rax
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rsi
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 n; // rax
  unsigned int v47; // eax
  __int64 v48; // r8
  _DWORD *v49; // r9
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 ii; // rax
  int v53; // eax
  size_t v54; // rdx
  _DWORD *result; // rax

  v7 = 0;
  v8 = 0;
  if ( *(_DWORD *)(a2 + 16) )
    v7 = *(unsigned int *)(a2 + 24) + ((unsigned __int64)*(unsigned int *)(a2 + 28) << 32);
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 1028;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v9, "\\server\\event.c");
  v11 = *(_DWORD *)(a2 + 8);
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            if ( v15 != 1 )
            {
              *(_DWORD *)a2 = -2147483576;
              goto LABEL_81;
            }
            v16 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1229734736);
            v17 = v16;
            if ( !v16 || *(_DWORD *)v16 != 1229734736 )
            {
              *(_DWORD *)a2 = -1879048173;
              goto LABEL_81;
            }
            v18 = v16 >> 4;
            EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v16 >> 4)
                                                                 & (unsigned int)gdwPointerToLockTableIndexBits));
            if ( v17 != -100 && a2 != -20 )
            {
              if ( !*(_DWORD *)(a2 + 16) )
              {
                v22 = 1;
                v23 = 0;
                for ( i = 0; i != 31; ++i )
                {
                  v8 = v23 | v22;
                  if ( !*(_DWORD *)(v17 + 100 + 4 * i) )
                    v8 = v23;
                  v22 *= 2;
                  v23 = v8;
                }
                goto LABEL_20;
              }
LABEL_15:
              SubMaskIndex = GetSubMaskIndex(v7);
              *v21 = *(_DWORD *)(v20 + 4LL * SubMaskIndex);
LABEL_20:
              v25 = 0;
LABEL_22:
              *(_DWORD *)a2 = v25;
              LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v18 & gdwPointerToLockTableIndexBits));
              DereferenceObject(v26, *(_DWORD *)(a2 + 12), 1);
              goto LABEL_81;
            }
          }
          else
          {
            v27 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1347436880);
            v28 = v27;
            if ( !v27 || *(_DWORD *)v27 != 1347436880 )
            {
              *(_DWORD *)a2 = -1879048185;
              goto LABEL_81;
            }
            v18 = v27 >> 4;
            EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v27 >> 4)
                                                                 & (unsigned int)gdwPointerToLockTableIndexBits));
            if ( v28 != -76 && a2 != -20 )
            {
              if ( !*(_DWORD *)(a2 + 16) )
              {
                v29 = 1;
                v30 = 0;
                for ( j = 0; j != 31; ++j )
                {
                  v8 = v30 | v29;
                  if ( !*(_DWORD *)(v28 + 76 + 4 * j) )
                    v8 = v30;
                  v29 *= 2;
                  v30 = v8;
                }
                goto LABEL_20;
              }
              goto LABEL_15;
            }
          }
        }
        else
        {
          v32 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1229734723);
          v33 = v32;
          if ( !v32 || *(_DWORD *)v32 != 1229734723 )
          {
            *(_DWORD *)a2 = -2147483624;
            goto LABEL_81;
          }
          v18 = v32 >> 4;
          EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v32 >> 4)
                                                               & (unsigned int)gdwPointerToLockTableIndexBits));
          if ( v33 != -92 && a2 != -20 )
          {
            if ( !*(_DWORD *)(a2 + 16) )
            {
              v34 = 1;
              v35 = 0;
              for ( k = 0; k != 31; ++k )
              {
                v8 = v35 | v34;
                if ( !*(_DWORD *)(v33 + 92 + 4 * k) )
                  v8 = v35;
                v34 *= 2;
                v35 = v8;
              }
              goto LABEL_20;
            }
            goto LABEL_15;
          }
        }
      }
      else
      {
        v37 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1229734732);
        v38 = v37;
        if ( !v37 || *(_DWORD *)v37 != 1229734732 )
        {
          *(_DWORD *)a2 = -2147483605;
          goto LABEL_81;
        }
        v18 = v37 >> 4;
        EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v37 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
        if ( v38 != -168 && a2 != -20 )
        {
          if ( !*(_DWORD *)(a2 + 16) )
          {
            v39 = 1;
            v40 = 0;
            for ( m = 0; m != 31; ++m )
            {
              v8 = v40 | v39;
              if ( !*(_DWORD *)(v38 + 168 + 4 * m) )
                v8 = v40;
              v39 *= 2;
              v40 = v8;
            }
            goto LABEL_20;
          }
          goto LABEL_15;
        }
      }
    }
    else
    {
      v42 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1347436876);
      v43 = v42;
      if ( !v42 || *(_DWORD *)v42 != 1347436876 )
      {
        *(_DWORD *)a2 = -2147483628;
        goto LABEL_81;
      }
      v18 = v42 >> 4;
      EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v42 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
      if ( v43 != -80 && a2 != -20 )
      {
        if ( !*(_DWORD *)(a2 + 16) )
        {
          v44 = 1;
          v45 = 0;
          for ( n = 0; n != 31; ++n )
          {
            v8 = v45 | v44;
            if ( !*(_DWORD *)(v43 + 80 + 4 * n) )
              v8 = v45;
            v44 *= 2;
            v45 = v8;
          }
          goto LABEL_20;
        }
        goto LABEL_15;
      }
    }
    v25 = -2147483595;
    goto LABEL_22;
  }
  if ( WaitForExclusiveClientAccess(a1) )
  {
    if ( a1 == -252 || a2 == -20 )
    {
      v53 = -2147483595;
    }
    else
    {
      if ( *(_DWORD *)(a2 + 16) )
      {
        v47 = GetSubMaskIndex(v7);
        *v49 = *(_DWORD *)(v48 + 4LL * v47);
      }
      else
      {
        v50 = 0;
        v51 = 1;
        for ( ii = 0; ii != 31; ++ii )
        {
          v8 = v50 | v51;
          if ( !*(_DWORD *)(a1 + 252 + 4 * ii) )
            v8 = v50;
          v51 *= 2;
          v50 = v8;
        }
      }
      v53 = 0;
    }
    *(_DWORD *)a2 = v53;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
  }
  else
  {
    *(_DWORD *)a2 = -2147483598;
  }
LABEL_81:
  dword_1800519F8 = 1235;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v54, "\\server\\event.c");
  LeaveCriticalSection(&CriticalSection);
  if ( !*(_DWORD *)a2 && !*(_DWORD *)(a2 + 16) )
    *(_QWORD *)(a2 + 32) = v8;
  result = a5;
  *a5 = 40;
  return result;
}

```

## disassembly

```asm
0x180034a80  push    rbx
0x180034a82  push    rbp
0x180034a83  push    rsi
0x180034a84  push    rdi
0x180034a85  push    r14
0x180034a87  push    r15
0x180034a89  sub     rsp, 28h
0x180034a8d  xor     r15d, r15d
0x180034a90  mov     rbx, rdx
0x180034a93  mov     r14, rcx
0x180034a96  mov     ebp, r15d
0x180034a99  mov     edi, r15d
0x180034a9c  cmp     [rdx+10h], r15d
0x180034aa0  jz      short loc_180034AAF
0x180034aa2  mov     ebp, [rdx+1Ch]
0x180034aa5  mov     eax, [rdx+18h]
0x180034aa8  shl     rbp, 20h
0x180034aac  add     rbp, rax
0x180034aaf  lea     rcx, CriticalSection; lpCriticalSection
0x180034ab6  call    cs:__imp_EnterCriticalSection
0x180034abc  mov     cs:dword_1800519E0, 404h
0x180034ac6  call    cs:__imp_GetCurrentThreadId
0x180034acc  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x180034ad3  mov     cs:dword_1800519E4, eax
0x180034ad9  lea     rcx, pszDest; pszDest
0x180034ae0  call    StringCbCopyA
0x180034ae5  mov     eax, [rbx+8]
0x180034ae8  test    eax, eax
0x180034aea  jz      loc_180034E95
0x180034af0  sub     eax, 1
0x180034af3  jz      loc_180034DF4
0x180034af9  sub     eax, 1
0x180034afc  jz      loc_180034D4C
0x180034b02  sub     eax, 1
0x180034b05  jz      loc_180034CAB
0x180034b0b  sub     eax, 1
0x180034b0e  jz      loc_180034C0A
0x180034b14  cmp     eax, 1
0x180034b17  jz      short loc_180034B24
0x180034b19  mov     dword ptr [rbx], 80000048h
0x180034b1f  jmp     loc_180034F34
0x180034b24  mov     edx, [rbx+0Ch]
0x180034b27  mov     r14d, 494C4350h
0x180034b2d  mov     r8d, r14d
0x180034b30  call    ReferenceObject
0x180034b35  mov     rsi, rax
0x180034b38  test    rax, rax
0x180034b3b  jz      loc_180034BFF
0x180034b41  cmp     [rax], r14d
0x180034b44  jnz     loc_180034BFF
0x180034b4a  mov     ecx, cs:gdwPointerToLockTableIndexBits
0x180034b50  mov     r14, rax
0x180034b53  mov     rax, cs:gLockTable
0x180034b5a  shr     r14, 4
0x180034b5e  and     rcx, r14
0x180034b61  lea     rdx, [rcx+rcx*4]
0x180034b65  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180034b69  call    cs:__imp_EnterCriticalSection
0x180034b6f  lea     r9, [rsi+64h]
0x180034b73  mov     esi, 1
0x180034b78  test    r9, r9
0x180034b7b  jz      short loc_180034BCA
0x180034b7d  lea     r8, [rbx+14h]
0x180034b81  test    r8, r8
0x180034b84  jz      short loc_180034BCA
0x180034b86  cmp     [rbx+10h], r15d
0x180034b8a  jz      short loc_180034B9F
0x180034b8c  mov     rcx, rbp
0x180034b8f  call    GetSubMaskIndex
0x180034b94  mov     edx, eax
0x180034b96  mov     eax, [r9+rdx*4]
0x180034b9a  mov     [r8], eax
0x180034b9d  jmp     short loc_180034BC5
0x180034b9f  mov     rcx, rsi
0x180034ba2  mov     rdx, r15
0x180034ba5  mov     rax, r15
0x180034ba8  mov     rdi, rcx
0x180034bab  or      rdi, rdx
0x180034bae  cmp     [r9+rax*4], r15d
0x180034bb2  cmovz   rdi, rdx
0x180034bb6  add     rcx, rcx
0x180034bb9  add     rax, rsi
0x180034bbc  mov     rdx, rdi
0x180034bbf  cmp     rax, 1Fh
0x180034bc3  jnz     short loc_180034BA8
0x180034bc5  mov     eax, r15d
0x180034bc8  jmp     short loc_180034BCF
0x180034bca  mov     eax, 80000035h
0x180034bcf  mov     [rbx], eax
0x180034bd1  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180034bd7  and     rax, r14
0x180034bda  lea     rcx, [rax+rax*4]
0x180034bde  mov     rax, cs:gLockTable
0x180034be5  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180034be9  call    cs:__imp_LeaveCriticalSection
0x180034bef  mov     edx, [rbx+0Ch]
0x180034bf2  mov     r8d, esi
0x180034bf5  call    DereferenceObject
0x180034bfa  jmp     loc_180034F34
0x180034bff  mov     dword ptr [rbx], 90000013h
0x180034c05  jmp     loc_180034F34
0x180034c0a  mov     edx, [rbx+0Ch]
0x180034c0d  mov     r14d, 50504150h
0x180034c13  mov     r8d, r14d
0x180034c16  call    ReferenceObject
0x180034c1b  mov     rsi, rax
0x180034c1e  test    rax, rax
0x180034c21  jz      short loc_180034CA0
0x180034c23  cmp     [rax], r14d
0x180034c26  jnz     short loc_180034CA0
0x180034c28  mov     ecx, cs:gdwPointerToLockTableIndexBits
0x180034c2e  mov     r14, rax
0x180034c31  mov     rax, cs:gLockTable
0x180034c38  shr     r14, 4
0x180034c3c  and     rcx, r14
0x180034c3f  lea     rcx, [rcx+rcx*4]
0x180034c43  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180034c47  call    cs:__imp_EnterCriticalSection
0x180034c4d  lea     r9, [rsi+4Ch]
0x180034c51  mov     esi, 1
0x180034c56  test    r9, r9
0x180034c59  jz      loc_180034BCA
0x180034c5f  lea     r8, [rbx+14h]
0x180034c63  test    r8, r8
0x180034c66  jz      loc_180034BCA
0x180034c6c  cmp     [rbx+10h], r15d
0x180034c70  jnz     loc_180034B8C
0x180034c76  mov     ecx, esi
0x180034c78  mov     rdx, r15
0x180034c7b  mov     rax, r15
0x180034c7e  mov     rdi, rcx
0x180034c81  or      rdi, rdx
0x180034c84  cmp     [r9+rax*4], r15d
0x180034c88  cmovz   rdi, rdx
0x180034c8c  add     rcx, rcx
0x180034c8f  add     rax, rsi
0x180034c92  mov     rdx, rdi
0x180034c95  cmp     rax, 1Fh
0x180034c99  jnz     short loc_180034C7E
0x180034c9b  jmp     loc_180034BC5
0x180034ca0  mov     dword ptr [rbx], 90000007h
0x180034ca6  jmp     loc_180034F34
0x180034cab  mov     edx, [rbx+0Ch]
0x180034cae  mov     r14d, 494C4343h
0x180034cb4  mov     r8d, r14d
0x180034cb7  call    ReferenceObject
0x180034cbc  mov     rsi, rax
0x180034cbf  test    rax, rax
0x180034cc2  jz      short loc_180034D41
0x180034cc4  cmp     [rax], r14d
0x180034cc7  jnz     short loc_180034D41
0x180034cc9  mov     ecx, cs:gdwPointerToLockTableIndexBits
0x180034ccf  mov     r14, rax
0x180034cd2  mov     rax, cs:gLockTable
0x180034cd9  shr     r14, 4
0x180034cdd  and     rcx, r14
0x180034ce0  lea     rcx, [rcx+rcx*4]
0x180034ce4  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180034ce8  call    cs:__imp_EnterCriticalSection
0x180034cee  lea     r9, [rsi+5Ch]
0x180034cf2  mov     esi, 1
0x180034cf7  test    r9, r9
0x180034cfa  jz      loc_180034BCA
0x180034d00  lea     r8, [rbx+14h]
0x180034d04  test    r8, r8
0x180034d07  jz      loc_180034BCA
0x180034d0d  cmp     [rbx+10h], r15d
0x180034d11  jnz     loc_180034B8C
0x180034d17  mov     ecx, esi
0x180034d19  mov     rdx, r15
0x180034d1c  mov     rax, r15
0x180034d1f  mov     rdi, rcx
0x180034d22  or      rdi, rdx
0x180034d25  cmp     [r9+rax*4], r15d
0x180034d29  cmovz   rdi, rdx
0x180034d2d  add     rcx, rcx
0x180034d30  add     rax, rsi
0x180034d33  mov     rdx, rdi
0x180034d36  cmp     rax, 1Fh
0x180034d3a  jnz     short loc_180034D1F
0x180034d3c  jmp     loc_180034BC5
0x180034d41  mov     dword ptr [rbx], 80000018h
0x180034d47  jmp     loc_180034F34
0x180034d4c  mov     edx, [rbx+0Ch]
0x180034d4f  mov     r14d, 494C434Ch
0x180034d55  mov     r8d, r14d
0x180034d58  call    ReferenceObject
0x180034d5d  mov     rsi, rax
0x180034d60  test    rax, rax
0x180034d63  jz      loc_180034DE9
0x180034d69  cmp     [rax], r14d
0x180034d6c  jnz     short loc_180034DE9
0x180034d6e  mov     ecx, cs:gdwPointerToLockTableIndexBits
0x180034d74  mov     r14, rax
0x180034d77  mov     rax, cs:gLockTable
0x180034d7e  shr     r14, 4
0x180034d82  and     rcx, r14
0x180034d85  lea     rcx, [rcx+rcx*4]
0x180034d89  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180034d8d  call    cs:__imp_EnterCriticalSection
0x180034d93  lea     r9, [rsi+0A8h]
0x180034d9a  mov     esi, 1
0x180034d9f  test    r9, r9
0x180034da2  jz      loc_180034BCA
0x180034da8  lea     r8, [rbx+14h]
0x180034dac  test    r8, r8
0x180034daf  jz      loc_180034BCA
0x180034db5  cmp     [rbx+10h], r15d
0x180034db9  jnz     loc_180034B8C
0x180034dbf  mov     ecx, esi
0x180034dc1  mov     rdx, r15
0x180034dc4  mov     rax, r15
0x180034dc7  mov     rdi, rcx
0x180034dca  or      rdi, rdx
0x180034dcd  cmp     [r9+rax*4], r15d
0x180034dd1  cmovz   rdi, rdx
0x180034dd5  add     rcx, rcx
0x180034dd8  add     rax, rsi
0x180034ddb  mov     rdx, rdi
0x180034dde  cmp     rax, 1Fh
0x180034de2  jnz     short loc_180034DC7
0x180034de4  jmp     loc_180034BC5
0x180034de9  mov     dword ptr [rbx], 8000002Bh
0x180034def  jmp     loc_180034F34
0x180034df4  mov     edx, [rbx+0Ch]
0x180034df7  mov     r14d, 5050414Ch
0x180034dfd  mov     r8d, r14d
0x180034e00  call    ReferenceObject
0x180034e05  mov     rsi, rax
0x180034e08  test    rax, rax
0x180034e0b  jz      short loc_180034E8A
0x180034e0d  cmp     [rax], r14d
0x180034e10  jnz     short loc_180034E8A
0x180034e12  mov     ecx, cs:gdwPointerToLockTableIndexBits
0x180034e18  mov     r14, rax
0x180034e1b  mov     rax, cs:gLockTable
0x180034e22  shr     r14, 4
0x180034e26  and     rcx, r14
0x180034e29  lea     rcx, [rcx+rcx*4]
0x180034e2d  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180034e31  call    cs:__imp_EnterCriticalSection
0x180034e37  lea     r9, [rsi+50h]
0x180034e3b  mov     esi, 1
0x180034e40  test    r9, r9
0x180034e43  jz      loc_180034BCA
0x180034e49  lea     r8, [rbx+14h]
0x180034e4d  test    r8, r8
0x180034e50  jz      loc_180034BCA
0x180034e56  cmp     [rbx+10h], r15d
0x180034e5a  jnz     loc_180034B8C
0x180034e60  mov     ecx, esi
0x180034e62  mov     rdx, r15
0x180034e65  mov     rax, r15
0x180034e68  mov     rdi, rcx
0x180034e6b  or      rdi, rdx
0x180034e6e  cmp     [r9+rax*4], r15d
0x180034e72  cmovz   rdi, rdx
0x180034e76  add     rcx, rcx
0x180034e79  add     rax, rsi
0x180034e7c  mov     rdx, rdi
0x180034e7f  cmp     rax, 1Fh
0x180034e83  jnz     short loc_180034E68
0x180034e85  jmp     loc_180034BC5
0x180034e8a  mov     dword ptr [rbx], 80000014h
0x180034e90  jmp     loc_180034F34
0x180034e95  mov     rcx, r14
0x180034e98  call    WaitForExclusiveClientAccess
0x180034e9d  test    rax, rax
0x180034ea0  jz      loc_180034F2E
0x180034ea6  lea     r8, [r14+0FCh]
0x180034ead  test    r8, r8
0x180034eb0  jz      short loc_180034F03
0x180034eb2  lea     r9, [rbx+14h]
0x180034eb6  test    r9, r9
0x180034eb9  jz      short loc_180034F03
0x180034ebb  cmp     [rbx+10h], r15d
0x180034ebf  jz      short loc_180034ED4
0x180034ec1  mov     rcx, rbp
0x180034ec4  call    GetSubMaskIndex
0x180034ec9  mov     edx, eax
0x180034ecb  mov     eax, [r8+rdx*4]
0x180034ecf  mov     [r9], eax
0x180034ed2  jmp     short loc_180034EFE
0x180034ed4  mov     esi, 1
0x180034ed9  mov     rdx, r15
0x180034edc  mov     ecx, esi
0x180034ede  mov     rax, r15
0x180034ee1  mov     rdi, rcx
0x180034ee4  or      rdi, rdx
0x180034ee7  cmp     [r8+rax*4], r15d
0x180034eeb  cmovz   rdi, rdx
0x180034eef  add     rcx, rcx
0x180034ef2  add     rax, rsi
0x180034ef5  mov     rdx, rdi
0x180034ef8  cmp     rax, 1Fh
0x180034efc  jnz     short loc_180034EE1
0x180034efe  mov     eax, r15d
0x180034f01  jmp     short loc_180034F08
0x180034f03  mov     eax, 80000035h
0x180034f08  mov     [rbx], eax
  ... truncated ...
```
