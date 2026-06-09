# CreateDeltaTTFEx

- ea: `0x1800285cc`
- end: `0x180028bdf`
- name: `CreateDeltaTTFEx`
- size: `1555`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022ba4`

## callees

- `0x18000ee80`
- `0x18000f298`
- `0x18000fd44`
- `0x18000ffc4`
- `0x18001009c`
- `0x180010448`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800120bc`
- `0x180012a18`
- `0x1800134a0`
- `0x1800164a0`
- `0x180019dc0`
- `0x18001bc30`
- `0x18001be6c`
- `0x18001d5f8`
- `0x180028114`
- `0x1800281d0`
- `0x180028388`
- `0x1800285cc`
- `0x180028c2c`
- `0x180028dfc`
- `0x180028f78`
- `0x18002912c`
- `0x180029228`

## pseudocode

```c
__int64 __fastcall CreateDeltaTTFEx(
        __int64 a1,
        unsigned int a2,
        LPVOID *a3,
        _DWORD *a4,
        unsigned int *a5,
        int a6,
        unsigned __int16 a7,
        int a8,
        unsigned __int16 a9,
        unsigned __int16 a10,
        __int64 a11,
        __int16 a12)
{
  unsigned int v12; // r12d
  unsigned __int16 NumGlyphs; // ax
  unsigned __int16 v17; // si
  __int64 v18; // rdi
  int v19; // r8d
  unsigned __int16 KeepGlyphList; // bx
  __int64 v21; // r8
  int v22; // r9d
  LPVOID v23; // r13
  void *v24; // rax
  int v25; // r12d
  __int64 v26; // r8
  int v27; // r9d
  __int64 v28; // r8
  unsigned int v29; // ecx
  __int16 v30; // [rsp+20h] [rbp-A1h]
  unsigned int v31; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v32; // [rsp+64h] [rbp-5Dh]
  __int16 v33; // [rsp+68h] [rbp-59h] BYREF
  LPVOID lpMem[2]; // [rsp+70h] [rbp-51h] BYREF
  __int64 (__fastcall *v35)(LPVOID, SIZE_T); // [rsp+80h] [rbp-41h]
  _WORD v36[2]; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int16 v37; // [rsp+8Ch] [rbp-35h] BYREF
  unsigned __int16 v38; // [rsp+90h] [rbp-31h] BYREF
  __int64 v39; // [rsp+98h] [rbp-29h] BYREF
  unsigned int v40; // [rsp+A0h] [rbp-21h]
  int v41; // [rsp+A4h] [rbp-1Dh]
  __int64 v42; // [rsp+A8h] [rbp-19h]
  int v43; // [rsp+B0h] [rbp-11h] BYREF
  unsigned int *v44; // [rsp+B8h] [rbp-9h]

  v32 = a2;
  v38 = -1;
  v12 = a2;
  v44 = a5;
  v36[0] = 0;
  v33 = 0;
  v37 = 0;
  v43 = 0;
  v31 = 0;
  v35 = 0;
  *(_OWORD *)lpMem = 0;
  if ( !a1 )
    return 1100;
  if ( !a2 )
    return 1101;
  if ( !a3 )
    return 1102;
  if ( !a4 )
    return 1103;
  if ( !a5 )
    return 1104;
  v39 = a1;
  v40 = a2;
  v41 = 0;
  v42 = 0;
  *a5 = 0;
  NumGlyphs = GetNumGlyphs(&v39);
  v17 = NumGlyphs;
  if ( !NumGlyphs )
    return 1009;
  v18 = Mem_Alloc(NumGlyphs);
  if ( !v18 )
    return 1005;
  KeepGlyphList = MakeKeepGlyphList((unsigned int)&v39, a10, v19, a9, a11, a12, v18, v17, (__int64)&v33, (__int64)v36);
  if ( !KeepGlyphList )
  {
    v23 = *a3;
    if ( *a3 && *a4 )
    {
      v24 = *a3;
    }
    else
    {
      CalcOutputBufferSize((unsigned int)&v39, v17, v36[0], v22, v12, (__int64)a4);
      v24 = (void *)T2MemReAlloc(0, (unsigned int)*a4);
      *a3 = v24;
      if ( !v24 )
      {
        Mem_Free(v18);
        return 1005;
      }
    }
    lpMem[0] = v24;
    lpMem[1] = (LPVOID)(unsigned int)*a4;
    v35 = T2MemReAlloc;
    KeepGlyphList = CopyOffsetDirectoryTables(&v39, lpMem, v21, &v31);
    if ( KeepGlyphList
      || (KeepGlyphList = CopyTableOver(lpMem, &v39, "head", &v31)) != 0
      || (KeepGlyphList = CopyTableOver(lpMem, &v39, "hhea", &v31)) != 0
      || (KeepGlyphList = CopyTableOver(lpMem, &v39, "maxp", &v31)) != 0 )
    {
LABEL_49:
      Mem_Free(v18);
      if ( !KeepGlyphList )
      {
        v29 = v31;
        if ( v31 <= v12 )
        {
          *a3 = lpMem[0];
          *a4 = lpMem[1];
          *v44 = v29;
          return KeepGlyphList;
        }
        KeepGlyphList = 1007;
      }
      if ( v23 )
      {
        *a3 = lpMem[0];
      }
      else
      {
        T2free(lpMem[0]);
        *a3 = 0;
      }
      return KeepGlyphList;
    }
    v25 = 1;
    CopyTableOver(lpMem, &v39, "OS/2", &v31);
    KeepGlyphList = ModXmtxXhea((unsigned int)&v39, (unsigned int)lpMem, v18, v17, 0, v33, 1, (__int64)&v31);
    if ( KeepGlyphList )
    {
      if ( KeepGlyphList != 1007 )
        goto LABEL_48;
      v25 = 0;
    }
    KeepGlyphList = ModLTSH((unsigned int)&v39, (unsigned int)lpMem, v18, v17, 0, (__int64)&v31);
    if ( !KeepGlyphList )
    {
      KeepGlyphList = ModVDMX(&v39, lpMem, v26, &v31);
      if ( !KeepGlyphList )
      {
        if ( v25 != 1 )
        {
          CopyTableOver(lpMem, &v39, "hdmx", &v31);
LABEL_35:
          KeepGlyphList = ModCmap(
                            (unsigned int)&v39,
                            (unsigned int)lpMem,
                            v18,
                            v17,
                            (__int64)&v38,
                            (__int64)&v37,
                            (__int64)&v31);
          if ( !KeepGlyphList )
          {
            CopyTableOver(lpMem, &v39, "fpgm", &v31);
            CopyTableOver(lpMem, &v39, "prep", &v31);
            CopyTableOver(lpMem, &v39, "cvt ", &v31);
            KeepGlyphList = ModGlyfLocaAndHead(&v39, lpMem, v18, v17);
            if ( !KeepGlyphList )
            {
              KeepGlyphList = ModMaxP(&v39, lpMem, &v31);
              if ( !KeepGlyphList )
              {
                KeepGlyphList = ModOS2(
                                  (unsigned int)&v39,
                                  (unsigned int)lpMem,
                                  v38,
                                  v37,
                                  (unsigned int)&v43,
                                  (__int64)&v31);
                if ( !KeepGlyphList )
                {
                  KeepGlyphList = ModKern((unsigned int)&v39, (unsigned int)lpMem, v18, v17, v30, (__int64)&v31);
                  if ( !KeepGlyphList )
                  {
                    KeepGlyphList = ModName((unsigned int)&v39, (unsigned int)lpMem, a7, v27, (__int64)&v31);
                    if ( !KeepGlyphList )
                    {
                      KeepGlyphList = ModPost(&v39, lpMem, v28, &v31);
                      if ( !KeepGlyphList )
                      {
                        CopyTableOver(lpMem, &v39, "gasp", &v31);
                        CopyTableOver(lpMem, &v39, "PCLT", &v31);
                        CopyTableOver(lpMem, &v39, "vhea", &v31);
                        KeepGlyphList = ModXmtxXhea(
                                          (unsigned int)&v39,
                                          (unsigned int)lpMem,
                                          v18,
                                          v17,
                                          0,
                                          v33,
                                          0,
                                          (__int64)&v31);
                        if ( !KeepGlyphList || KeepGlyphList == 1007 )
                        {
                          KeepGlyphList = ModSbit((unsigned int)&v39, (unsigned int)lpMem, v18, v17, (__int64)&v31);
                          if ( !KeepGlyphList )
                          {
                            KeepGlyphList = CopyForgottenTables(&v39, lpMem, &v31);
                            if ( !KeepGlyphList )
                            {
                              KeepGlyphList = CompressTables(lpMem, &v31);
                              if ( !KeepGlyphList )
                                SetFileChecksum(lpMem, v31);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          goto LABEL_48;
        }
        KeepGlyphList = ModHdmx((unsigned int)&v39, (unsigned int)lpMem, v18, v17, 0, (__int64)&v31);
        if ( !KeepGlyphList )
          goto LABEL_35;
      }
    }
LABEL_48:
    v12 = v32;
    goto LABEL_49;
  }
  Mem_Free(v18);
  return KeepGlyphList;
}

```

## disassembly

```asm
0x1800285cc  push    rbp
0x1800285ce  push    rbx
0x1800285cf  push    rsi
0x1800285d0  push    rdi
0x1800285d1  push    r12
0x1800285d3  push    r13
0x1800285d5  push    r14
0x1800285d7  push    r15
0x1800285d9  lea     rbp, [rsp-7]
0x1800285de  sub     rsp, 0C8h
0x1800285e5  mov     rbx, [rbp+3Fh+arg_50]
0x1800285ec  xor     r13d, r13d
0x1800285ef  mov     eax, 0FFFFh
0x1800285f4  mov     [rbp+3Fh+var_9C], edx
0x1800285f7  mov     [rbp+3Fh+var_70], ax
0x1800285fb  mov     r12d, edx
0x1800285fe  mov     rdx, [rbp+3Fh+arg_20]
0x180028602  xor     eax, eax
0x180028604  mov     [rbp+3Fh+var_48], rdx
0x180028608  xorps   xmm0, xmm0
0x18002860b  mov     [rbp+3Fh+var_78], r13w
0x180028610  mov     r15, r9
0x180028613  mov     [rbp+3Fh+var_98], r13w
0x180028618  mov     r14, r8
0x18002861b  mov     [rbp+3Fh+var_74], r13w
0x180028620  mov     [rbp+3Fh+var_50], r13d
0x180028624  mov     [rbp+3Fh+var_A0], r13d
0x180028628  mov     [rbp+3Fh+var_80], rax
0x18002862c  movups  xmmword ptr [rbp+3Fh+lpMem], xmm0
0x180028630  test    rcx, rcx
0x180028633  jnz     short loc_18002863F
0x180028635  mov     eax, 44Ch
0x18002863a  jmp     loc_180028BCB
0x18002863f  test    r12d, r12d
0x180028642  jnz     short loc_18002864E
0x180028644  mov     eax, 44Dh
0x180028649  jmp     loc_180028BCB
0x18002864e  test    r14, r14
0x180028651  jnz     short loc_18002865D
0x180028653  mov     eax, 44Eh
0x180028658  jmp     loc_180028BCB
0x18002865d  test    r15, r15
0x180028660  jnz     short loc_18002866C
0x180028662  mov     eax, 44Fh
0x180028667  jmp     loc_180028BCB
0x18002866c  test    rdx, rdx
0x18002866f  jnz     short loc_18002867B
0x180028671  mov     eax, 450h
0x180028676  jmp     loc_180028BCB
0x18002867b  mov     [rbp+3Fh+var_68], rcx
0x18002867f  lea     rcx, [rbp+3Fh+var_68]
0x180028683  mov     [rbp+3Fh+var_60], r12d
0x180028687  mov     [rbp+3Fh+var_5C], r13d
0x18002868b  mov     [rbp+3Fh+var_58], r13
0x18002868f  mov     [rdx], r13d
0x180028692  call    GetNumGlyphs
0x180028697  movzx   esi, ax
0x18002869a  test    si, si
0x18002869d  jnz     short loc_1800286A9
0x18002869f  mov     eax, 3F1h
0x1800286a4  jmp     loc_180028BCB
0x1800286a9  mov     rcx, rsi; Size
0x1800286ac  call    Mem_Alloc
0x1800286b1  mov     rdi, rax
0x1800286b4  test    rax, rax
0x1800286b7  jnz     short loc_1800286C3
0x1800286b9  mov     eax, 3EDh
0x1800286be  jmp     loc_180028BCB
0x1800286c3  movzx   r9d, [rbp+3Fh+arg_40]
0x1800286cb  lea     rax, [rbp+3Fh+var_78]
0x1800286cf  movzx   edx, [rbp+3Fh+arg_48]
0x1800286d6  lea     rcx, [rbp+3Fh+var_68]
0x1800286da  mov     [rsp+100h+var_B8], rax
0x1800286df  lea     rax, [rbp+3Fh+var_98]
0x1800286e3  mov     [rsp+100h+var_C0], rax
0x1800286e8  movzx   eax, [rbp+3Fh+arg_58]
0x1800286ef  mov     word ptr [rsp+100h+var_C8], si
0x1800286f4  mov     [rsp+100h+var_D0], rdi
0x1800286f9  mov     word ptr [rsp+100h+var_D8], ax
0x1800286fe  mov     [rsp+100h+var_E0], rbx
0x180028703  call    MakeKeepGlyphList
0x180028708  movzx   ebx, ax
0x18002870b  test    ax, ax
0x18002870e  jz      short loc_18002871D
0x180028710  mov     rcx, rdi
0x180028713  call    Mem_Free
0x180028718  jmp     loc_180028BC8
0x18002871d  mov     r13, [r14]
0x180028720  xor     ebx, ebx
0x180028722  test    r13, r13
0x180028725  jz      loc_1800288CB
0x18002872b  cmp     [r15], ebx
0x18002872e  jz      loc_1800288CB
0x180028734  mov     rax, r13
0x180028737  mov     [rbp+3Fh+lpMem], rax
0x18002873b  lea     r9, [rbp+3Fh+var_A0]
0x18002873f  mov     eax, [r15]
0x180028742  lea     rdx, [rbp+3Fh+lpMem]
0x180028746  mov     dword ptr [rbp+3Fh+lpMem+8], eax
0x180028749  lea     rcx, [rbp+3Fh+var_68]
0x18002874d  lea     rax, T2MemReAlloc
0x180028754  mov     dword ptr [rbp+3Fh+lpMem+0Ch], ebx
0x180028757  mov     [rbp+3Fh+var_80], rax
0x18002875b  call    CopyOffsetDirectoryTables
0x180028760  movzx   ebx, ax
0x180028763  test    ax, ax
0x180028766  jnz     loc_180028B7D
0x18002876c  lea     r9, [rbp+3Fh+var_A0]
0x180028770  lea     r8, aHead; "head"
0x180028777  lea     rdx, [rbp+3Fh+var_68]
0x18002877b  lea     rcx, [rbp+3Fh+lpMem]
0x18002877f  call    CopyTableOver
0x180028784  movzx   ebx, ax
0x180028787  test    ax, ax
0x18002878a  jnz     loc_180028B7D
0x180028790  lea     r9, [rbp+3Fh+var_A0]
0x180028794  lea     r8, aHhea; "hhea"
0x18002879b  lea     rdx, [rbp+3Fh+var_68]
0x18002879f  lea     rcx, [rbp+3Fh+lpMem]
0x1800287a3  call    CopyTableOver
0x1800287a8  movzx   ebx, ax
0x1800287ab  test    ax, ax
0x1800287ae  jnz     loc_180028B7D
0x1800287b4  lea     r9, [rbp+3Fh+var_A0]
0x1800287b8  lea     r8, aMaxp; "maxp"
0x1800287bf  lea     rdx, [rbp+3Fh+var_68]
0x1800287c3  lea     rcx, [rbp+3Fh+lpMem]
0x1800287c7  call    CopyTableOver
0x1800287cc  movzx   ebx, ax
0x1800287cf  test    ax, ax
0x1800287d2  jnz     loc_180028B7D
0x1800287d8  mov     ebx, 1
0x1800287dd  lea     r9, [rbp+3Fh+var_A0]
0x1800287e1  lea     r8, aOs2; "OS/2"
0x1800287e8  mov     r12d, ebx
0x1800287eb  lea     rdx, [rbp+3Fh+var_68]
0x1800287ef  lea     rcx, [rbp+3Fh+lpMem]
0x1800287f3  call    CopyTableOver
0x1800287f8  xor     ecx, ecx
0x1800287fa  lea     rdx, [rbp+3Fh+lpMem]
0x1800287fe  mov     eax, ecx
0x180028800  movzx   r9d, si
0x180028804  lea     rcx, [rbp+3Fh+var_A0]
0x180028808  mov     r8, rdi
0x18002880b  mov     [rsp+100h+var_C8], rcx
0x180028810  movzx   ecx, [rbp+3Fh+var_98]
0x180028814  mov     dword ptr [rsp+100h+var_D0], ebx
0x180028818  mov     word ptr [rsp+100h+var_D8], cx
0x18002881d  lea     rcx, [rbp+3Fh+var_68]
0x180028821  mov     word ptr [rsp+100h+var_E0], ax
0x180028826  call    ModXmtxXhea
0x18002882b  movzx   ebx, ax
0x18002882e  xor     eax, eax
0x180028830  test    bx, bx
0x180028833  jz      short loc_180028846
0x180028835  mov     ecx, 3EFh
0x18002883a  cmp     bx, cx
0x18002883d  jnz     loc_180028B79
0x180028843  mov     r12d, eax
0x180028846  lea     rcx, [rbp+3Fh+var_A0]
0x18002884a  movzx   r9d, si
0x18002884e  mov     [rsp+100h+var_D8], rcx
0x180028853  lea     rdx, [rbp+3Fh+lpMem]
0x180028857  lea     rcx, [rbp+3Fh+var_68]
0x18002885b  mov     word ptr [rsp+100h+var_E0], ax
0x180028860  mov     r8, rdi
0x180028863  call    ModLTSH
0x180028868  movzx   ebx, ax
0x18002886b  test    ax, ax
0x18002886e  jnz     loc_180028B79
0x180028874  lea     r9, [rbp+3Fh+var_A0]
0x180028878  lea     rdx, [rbp+3Fh+lpMem]
0x18002887c  lea     rcx, [rbp+3Fh+var_68]
0x180028880  call    ModVDMX
0x180028885  movzx   ebx, ax
0x180028888  test    ax, ax
0x18002888b  jnz     loc_180028B79
0x180028891  cmp     r12d, 1
0x180028895  jnz     short loc_180028909
0x180028897  lea     rcx, [rbp+3Fh+var_A0]
0x18002889b  xor     r12d, r12d
0x18002889e  mov     [rsp+100h+var_D8], rcx
0x1800288a3  lea     rdx, [rbp+3Fh+lpMem]
0x1800288a7  lea     rcx, [rbp+3Fh+var_68]
0x1800288ab  mov     word ptr [rsp+100h+var_E0], r12w
0x1800288b1  movzx   r9d, si
0x1800288b5  mov     r8, rdi
0x1800288b8  call    ModHdmx
0x1800288bd  movzx   ebx, ax
0x1800288c0  test    ax, ax
0x1800288c3  jnz     loc_180028B79
0x1800288c9  jmp     short loc_180028924
0x1800288cb  movzx   r8d, [rbp+3Fh+var_78]
0x1800288d0  lea     rcx, [rbp+3Fh+var_68]
0x1800288d4  mov     [rsp+100h+var_D8], r15
0x1800288d9  movzx   edx, si
0x1800288dc  mov     dword ptr [rsp+100h+var_E0], r12d
0x1800288e1  call    CalcOutputBufferSize
0x1800288e6  mov     edx, [r15]; dwBytes
0x1800288e9  xor     ecx, ecx; lpMem
0x1800288eb  call    T2MemReAlloc
0x1800288f0  mov     [r14], rax
0x1800288f3  test    rax, rax
0x1800288f6  jnz     loc_180028737
0x1800288fc  mov     rcx, rdi
0x1800288ff  call    Mem_Free
0x180028904  jmp     loc_1800286B9
0x180028909  lea     r9, [rbp+3Fh+var_A0]
0x18002890d  lea     r8, aHdmx; "hdmx"
0x180028914  lea     rdx, [rbp+3Fh+var_68]
0x180028918  lea     rcx, [rbp+3Fh+lpMem]
0x18002891c  call    CopyTableOver
0x180028921  xor     r12d, r12d
0x180028924  lea     rax, [rbp+3Fh+var_A0]
0x180028928  movzx   r9d, si
0x18002892c  mov     [rsp+100h+var_D0], rax
0x180028931  lea     rdx, [rbp+3Fh+lpMem]
0x180028935  lea     rax, [rbp+3Fh+var_74]
0x180028939  mov     r8, rdi
0x18002893c  mov     [rsp+100h+var_D8], rax
0x180028941  lea     rcx, [rbp+3Fh+var_68]
0x180028945  lea     rax, [rbp+3Fh+var_70]
0x180028949  mov     [rsp+100h+var_E0], rax
0x18002894e  call    ModCmap
0x180028953  movzx   ebx, ax
0x180028956  test    ax, ax
0x180028959  jnz     loc_180028B79
0x18002895f  lea     r9, [rbp+3Fh+var_A0]
0x180028963  lea     r8, aFpgm; "fpgm"
0x18002896a  lea     rdx, [rbp+3Fh+var_68]
0x18002896e  lea     rcx, [rbp+3Fh+lpMem]
0x180028972  call    CopyTableOver
0x180028977  lea     r9, [rbp+3Fh+var_A0]
0x18002897b  lea     r8, aPrep; "prep"
0x180028982  lea     rdx, [rbp+3Fh+var_68]
0x180028986  lea     rcx, [rbp+3Fh+lpMem]
0x18002898a  call    CopyTableOver
0x18002898f  lea     r9, [rbp+3Fh+var_A0]
0x180028993  lea     r8, aCvt; "cvt "
0x18002899a  lea     rdx, [rbp+3Fh+var_68]
0x18002899e  lea     rcx, [rbp+3Fh+lpMem]
0x1800289a2  call    CopyTableOver
0x1800289a7  lea     rax, [rbp+3Fh+var_A0]
0x1800289ab  movzx   r9d, si
0x1800289af  mov     [rsp+100h+var_D8], rax
0x1800289b4  lea     rdx, [rbp+3Fh+lpMem]
0x1800289b8  lea     rax, [rbp+3Fh+var_50]
0x1800289bc  mov     r8, rdi
0x1800289bf  lea     rcx, [rbp+3Fh+var_68]
0x1800289c3  mov     [rsp+100h+var_E0], rax
0x1800289c8  call    ModGlyfLocaAndHead
0x1800289cd  movzx   ebx, ax
0x1800289d0  test    ax, ax
0x1800289d3  jnz     loc_180028B79
0x1800289d9  lea     r8, [rbp+3Fh+var_A0]
0x1800289dd  lea     rdx, [rbp+3Fh+lpMem]
0x1800289e1  lea     rcx, [rbp+3Fh+var_68]
0x1800289e5  call    ModMaxP
0x1800289ea  movzx   ebx, ax
0x1800289ed  test    ax, ax
0x1800289f0  jnz     loc_180028B79
0x1800289f6  movzx   r9d, [rbp+3Fh+var_74]
0x1800289fb  lea     rax, [rbp+3Fh+var_A0]
0x1800289ff  movzx   r8d, [rbp+3Fh+var_70]
0x180028a04  lea     rdx, [rbp+3Fh+lpMem]
0x180028a08  lea     rcx, [rbp+3Fh+var_68]
0x180028a0c  mov     [rsp+100h+var_D8], rax
0x180028a11  call    ModOS2
0x180028a16  movzx   ebx, ax
0x180028a19  test    ax, ax
0x180028a1c  jnz     loc_180028B79
0x180028a22  lea     rax, [rbp+3Fh+var_A0]
0x180028a26  movzx   r9d, si
0x180028a2a  mov     r8, rdi
0x180028a2d  mov     [rsp+100h+var_D8], rax
0x180028a32  lea     rdx, [rbp+3Fh+lpMem]
0x180028a36  lea     rcx, [rbp+3Fh+var_68]
0x180028a3a  call    ModKern
0x180028a3f  movzx   ebx, ax
0x180028a42  test    ax, ax
0x180028a45  jnz     loc_180028B79
0x180028a4b  movzx   r8d, [rbp+3Fh+arg_30]
0x180028a50  lea     rax, [rbp+3Fh+var_A0]
0x180028a54  lea     rdx, [rbp+3Fh+lpMem]
0x180028a58  mov     [rsp+100h+var_E0], rax
0x180028a5d  lea     rcx, [rbp+3Fh+var_68]
0x180028a61  call    ModName
0x180028a66  movzx   ebx, ax
0x180028a69  test    ax, ax
0x180028a6c  jnz     loc_180028B79
0x180028a72  lea     r9, [rbp+3Fh+var_A0]
0x180028a76  lea     rdx, [rbp+3Fh+lpMem]
0x180028a7a  lea     rcx, [rbp+3Fh+var_68]
0x180028a7e  call    ModPost
0x180028a83  movzx   ebx, ax
0x180028a86  test    ax, ax
0x180028a89  jnz     loc_180028B79
0x180028a8f  lea     r9, [rbp+3Fh+var_A0]
0x180028a93  lea     r8, aGasp; "gasp"
0x180028a9a  lea     rdx, [rbp+3Fh+var_68]
  ... truncated ...
```
