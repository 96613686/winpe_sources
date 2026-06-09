# NtGdiDdDDICreateDCFromMemory

- ea: `0x1401a1820`
- end: `0x1401a1e59`
- name: `NtGdiDdDDICreateDCFromMemory`
- size: `1593`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14003d0e8`
- `0x14005b820`
- `0x1400684f8`
- `0x14009a3b8`
- `0x14009a40c`
- `0x1400a7e98`
- `0x1400acb4c`
- `0x1401a1820`
- `0x1401a1e60`
- `0x1401a1ec0`
- `0x1401a1f38`
- `0x1402a0fc4`
- `0x1402a7178`
- `0x140342fa0`
- `0x1403d30b8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1401a19da`
- `ntoskrnl!ProbeForWrite` at `0x1401a19da`
- `win32kbase!GreCreateDisplayDC` at `0x1401a1cd9`
- `win32kbase!GreCreateDisplayDC` at `0x1401a1cd9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a1a33`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a1a33`
- `win32kbase!HmgShareLock` at `0x1401a1b49`
- `win32kbase!HmgShareLock` at `0x1401a1b49`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401a197e`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401a1bcb`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401a1c7f`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1857`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1857`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a18bb`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1992`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1a14`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1c93`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1d97`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a18bb`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1992`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1a14`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1c93`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a1d97`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x1401a1d18`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x1401a1d18`
- `win32kbase!EngCreateBitmap` at `0x1401a1af5`
- `win32kbase!EngCreateBitmap` at `0x1401a1af5`
- `win32kbase!EngDeleteSurface` at `0x1401a1c42`
- `win32kbase!EngDeleteSurface` at `0x1401a1e2c`
- `win32kbase!EngDeleteSurface` at `0x1401a1c42`
- `win32kbase!EngDeleteSurface` at `0x1401a1e2c`
- `win32kbase!GrepDeleteDC` at `0x1401a1c2c`
- `win32kbase!GrepDeleteDC` at `0x1401a1c2c`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x1401a19f6`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x1401a19f6`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a1960`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a1e42`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a1960`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a1e42`
- `win32kbase!EngCreatePalette` at `0x1401a1aa8`
- `win32kbase!EngCreatePalette` at `0x1401a1aa8`
- `win32kbase!EngDeletePalette` at `0x1401a1c61`
- `win32kbase!EngDeletePalette` at `0x1401a1c61`
- `win32kbase!GreSetBitmapOwner` at `0x1401a1d2e`
- `win32kbase!GreSetBitmapOwner` at `0x1401a1d2e`

## pseudocode

```c
__int64 __fastcall NtGdiDdDDICreateDCFromMemory(char *Src)
{
  unsigned int v2; // r8d
  ULONG *v3; // r12
  int v4; // esi
  FLONG flBlue; // edi
  ULONG v6; // r13d
  FLONG flGreen; // r14d
  Gre::Base *v9; // rcx
  void *v10; // r15
  unsigned int v11; // r15d
  FLONG v12; // r9d
  ULONG v13; // esi
  HPALETTE Palette; // rax
  HPALETTE v15; // rdi
  SIZE_T v16; // r12
  unsigned int v17; // edx
  unsigned __int64 v18; // r8
  struct Gre::Base::SESSION_GLOBALS *v19; // rsi
  __int64 v20; // r8
  __int64 v21; // rax
  char v22; // r14
  void *v23; // rsi
  char *v24; // rsi
  HDC DisplayDC; // rax
  __int64 v26; // r9
  bool v27; // zf
  HSURF hsurf; // [rsp+30h] [rbp-608h] BYREF
  SIZE_T Length; // [rsp+38h] [rbp-600h]
  ULONG cColors[2]; // [rsp+40h] [rbp-5F8h]
  void *v31; // [rsp+48h] [rbp-5F0h]
  HDC v32; // [rsp+50h] [rbp-5E8h] BYREF
  SIZEL sizl; // [rsp+58h] [rbp-5E0h]
  struct Gre::Base::SESSION_GLOBALS *v34[2]; // [rsp+60h] [rbp-5D8h] BYREF
  __int64 v35; // [rsp+70h] [rbp-5C8h] BYREF
  volatile void *Address[4]; // [rsp+78h] [rbp-5C0h] BYREF
  void *Srca[2]; // [rsp+98h] [rbp-5A0h]
  __int64 v38; // [rsp+A8h] [rbp-590h]
  char *v39; // [rsp+B0h] [rbp-588h]
  _BYTE v40[32]; // [rsp+B8h] [rbp-580h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-560h]
  _QWORD v42[8]; // [rsp+E0h] [rbp-558h] BYREF
  _BYTE v43[112]; // [rsp+120h] [rbp-518h] BYREF
  _BYTE v44[96]; // [rsp+190h] [rbp-4A8h] BYREF
  _BYTE v45[1024]; // [rsp+1F0h] [rbp-448h] BYREF

  v39 = Src;
  ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v44);
  v32 = 0;
  hsurf = 0;
  Length = 0;
  memset(Address, 0, sizeof(Address));
  *(_OWORD *)Srca = 0;
  v38 = 0;
  RtlCopyFromUser(Address, Src, 0x38u);
  sizl = *(SIZEL *)((char *)&Address[1] + 4);
  v2 = (unsigned int)Address[2];
  if ( SHIDWORD(Address[1]) <= 0 || SLODWORD(Address[2]) <= 0 )
    goto LABEL_11;
  cColors[0] = 0;
  v3 = 0;
  switch ( LODWORD(Address[1]) )
  {
    case 0x14:
      v6 = 5;
      goto LABEL_26;
    case 0x15:
    case 0x16:
      v6 = 6;
LABEL_26:
      flGreen = 65280;
      flBlue = 255;
      v4 = 16711680;
      break;
    case 0x17:
      v4 = 63488;
      flBlue = 31;
      v6 = 4;
      flGreen = 2016;
      break;
    case 0x18:
    case 0x19:
      v4 = 31744;
      flBlue = 31;
      v6 = 4;
      flGreen = 992;
      break;
    case 0x29:
      if ( Srca[0] )
      {
        RtlCopyFromUser(v45, Srca[0], 0x400u);
        v3 = (ULONG *)v45;
        v2 = (unsigned int)Address[2];
      }
      else
      {
        v3 = (ULONG *)qword_140365140;
      }
      v6 = 3;
      cColors[0] = 256;
      v4 = 0;
      flGreen = 0;
      flBlue = 0;
      break;
    default:
      goto LABEL_11;
  }
  if ( v2 * (unsigned __int64)HIDWORD(Address[2]) > 0xFFFFFFFF )
    goto LABEL_11;
  LODWORD(Length) = v2 * HIDWORD(Address[2]);
  ProbeForWrite(Address[0], Length, 4u);
  v10 = GrepSecureVirtualMemory((void *)Address[0], Length, 4u);
  v31 = v10;
  if ( !v10 )
    goto LABEL_11;
  v34[0] = Gre::Base::Globals(v9);
  SEMOBJSHARED<1>::SEMOBJSHARED<1>(&v35, v34[0]);
  DCOBJA::DCOBJA((DCOBJA *)v42, v34[0], (HDC)Address[3]);
  if ( !v42[0] )
  {
    GrepUnsecureVirtualMemory(v10);
    DCOBJA::~DCOBJA((DCOBJA *)v42);
    GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v35);
LABEL_11:
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v44);
    return 3221225485LL;
  }
  v11 = 0;
  Length = *(_QWORD *)(v42[0] + 48LL);
  v12 = v4;
  v13 = cColors[0];
  Palette = EngCreatePalette((unsigned int)(v6 > 3) + 1, cColors[0], v3, v12, flGreen, flBlue);
  v15 = Palette;
  *(_QWORD *)cColors = Palette;
  if ( !Palette )
    goto LABEL_30;
  if ( v13 == 256 )
  {
    v27 = v3 == 0;
    v16 = Length;
    if ( v27 )
      DxEngSyncPaletteTableWithDevice(Palette, (HDEV)Length);
  }
  else
  {
    v16 = Length;
  }
  hsurf = (HSURF)EngCreateBitmap(sizl, SHIDWORD(Address[2]), v6, 1u, (PVOID)Address[0]);
  DxEngSetPaletteState(v15, v17, v18);
  if ( hsurf )
  {
    v19 = v34[0];
    SEMOBJSHARED<1>::SEMOBJSHARED<1>(v34, v34[0]);
    SURFREF::SURFREF((SURFREF *)v40);
    LOBYTE(v20) = 5;
    v21 = HmgShareLock(v19, hsurf, v20, 16);
    v41 = v21;
    if ( v21 )
    {
      v22 = 1;
      DxEngSelectPaletteToSurface((struct _SURFOBJ *)(v21 + 24), v15);
      v23 = v31;
      *(_QWORD *)(v41 + 256) = v31;
      *(_DWORD *)(v41 + 144) |= 0x100000u;
      *(_DWORD *)(v41 + 144) |= 0x4000u;
      *(_DWORD *)(v41 + 144) |= 0x200u;
    }
    else
    {
      v22 = 0;
      v23 = v31;
    }
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v40);
    GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v34[0]);
    if ( v22 )
    {
      DisplayDC = (HDC)GreCreateDisplayDC(v16, 1);
      v32 = DisplayDC;
      if ( DisplayDC )
      {
        APIDCOBJ::APIDCOBJ((APIDCOBJ *)v43, DisplayDC);
        LOBYTE(v26) = 7;
        GrepSelectBitmap(v34, v43, hsurf, v26);
        GreSetBitmapOwner(hsurf, 2147483650LL);
        APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v43);
      }
    }
  }
  else
  {
LABEL_30:
    v23 = v31;
  }
  if ( !v32 )
  {
    if ( hsurf )
    {
      EngDeleteSurface(hsurf);
      hsurf = 0;
    }
    else
    {
      GrepUnsecureVirtualMemory(v23);
    }
    v11 = -1073741801;
  }
  v24 = v39;
  RtlCopyToUser(v39 + 40, &v32, 8u);
  RtlCopyToUser(v24 + 48, &hsurf, 8u);
  if ( v15 )
    EngDeletePalette(v15);
  DCOBJA::~DCOBJA((DCOBJA *)v42);
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v35);
  ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v44);
  return v11;
}

```

## disassembly

```asm
0x1401a1820  push    rsi
0x1401a1822  push    rdi
0x1401a1823  push    r12
0x1401a1825  push    r13
0x1401a1827  push    r14
0x1401a1829  push    r15
0x1401a182b  sub     rsp, 608h
0x1401a1832  mov     rax, cs:__security_cookie
0x1401a1839  xor     rax, rsp
0x1401a183c  mov     [rsp+638h+var_48], rax
0x1401a1844  mov     rdi, rcx
0x1401a1847  mov     [rsp+638h+var_588], rcx
0x1401a184f  lea     rcx, [rsp+638h+var_4A8]
0x1401a1857  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x1401a185e  nop     dword ptr [rax+rax+00h]
0x1401a1863  mov     [rsp+638h+var_5E8], 0
0x1401a186c  mov     [rsp+638h+hsurf], 0
0x1401a1875  mov     [rsp+638h+Length], 0
0x1401a187e  xorps   xmm0, xmm0
0x1401a1881  xor     eax, eax
0x1401a1883  movups  xmmword ptr [rsp+638h+Address], xmm0
0x1401a1888  movups  xmmword ptr [rsp+638h+lWidth], xmm0
0x1401a1890  movups  xmmword ptr [rsp+638h+Src], xmm0
0x1401a1898  mov     [rsp+638h+var_590], rax
0x1401a18a0  lea     r8d, [rax+38h]; Size
0x1401a18a4  mov     rdx, rdi; Src
0x1401a18a7  lea     rcx, [rsp+638h+Address]; void *
0x1401a18ac  call    RtlCopyFromUser
0x1401a18b1  jmp     short loc_1401A18D1
0x1401a18b3  lea     rcx, [rsp+638h+var_4A8]
0x1401a18bb  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a18c2  nop     dword ptr [rax+rax+00h]
0x1401a18c7  mov     eax, 0C000000Dh
0x1401a18cc  jmp     loc_1401A19A3
0x1401a18d1  mov     eax, dword ptr [rsp+638h+Address+0Ch]
0x1401a18d8  mov     [rsp+638h+sizl.cx], eax
0x1401a18dc  mov     r8d, [rsp+638h+lWidth]
0x1401a18e4  mov     [rsp+638h+sizl.cy], r8d
0x1401a18e9  test    eax, eax
0x1401a18eb  jle     loc_1401A198A
0x1401a18f1  test    r8d, r8d
0x1401a18f4  jle     loc_1401A198A
0x1401a18fa  mov     [rsp+638h+cColors], 0
0x1401a1902  xor     r12d, r12d
0x1401a1905  mov     ecx, dword ptr [rsp+638h+Address+8]
0x1401a190c  sub     ecx, 14h
0x1401a190f  jz      loc_1401A1DF9
0x1401a1915  sub     ecx, 1
0x1401a1918  jz      loc_1401A1CA7
0x1401a191e  sub     ecx, 1
0x1401a1921  jz      loc_1401A1CA7
0x1401a1927  sub     ecx, 1
0x1401a192a  jnz     loc_1401A1D56
0x1401a1930  mov     esi, 0F800h
0x1401a1935  lea     edi, [rcx+1Fh]
0x1401a1938  lea     r13d, [r12+4]
0x1401a193d  mov     r14d, 7E0h
0x1401a1943  mov     ecx, [rsp+638h+lWidth+4]
0x1401a194a  mov     eax, r8d
0x1401a194d  imul    rcx, rax
0x1401a1951  mov     eax, 0FFFFFFFFh
0x1401a1956  cmp     rcx, rax
0x1401a1959  jbe     short loc_1401A19C6
0x1401a195b  jmp     short loc_1401A198A
0x1401a195d  mov     rcx, r15
0x1401a1960  call    cs:__imp_?GrepUnsecureVirtualMemory@@YAXPEAX@Z; GrepUnsecureVirtualMemory(void *)
0x1401a1967  nop     dword ptr [rax+rax+00h]
0x1401a196c  lea     rcx, [rsp+638h+var_558]; this
0x1401a1974  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x1401a1979  mov     rdx, [rsp+638h+var_5C8]
0x1401a197e  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401a1985  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1401a198a  lea     rcx, [rsp+638h+var_4A8]
0x1401a1992  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a1999  nop     dword ptr [rax+rax+00h]
0x1401a199e  mov     eax, 0C000000Dh
0x1401a19a3  mov     rcx, [rsp+638h+var_48]
0x1401a19ab  xor     rcx, rsp; StackCookie
0x1401a19ae  call    __security_check_cookie
0x1401a19b3  add     rsp, 608h
0x1401a19ba  pop     r15
0x1401a19bc  pop     r14
0x1401a19be  pop     r13
0x1401a19c0  pop     r12
0x1401a19c2  pop     rdi
0x1401a19c3  pop     rsi
0x1401a19c4  retn
0x1401a19c6  mov     dword ptr [rsp+638h+Length], ecx
0x1401a19ca  mov     r8d, 4; Alignment
0x1401a19d0  mov     rdx, [rsp+638h+Length]; Length
0x1401a19d5  mov     rcx, [rsp+638h+Address]; Address
0x1401a19da  call    cs:__imp_ProbeForWrite
0x1401a19e1  nop     dword ptr [rax+rax+00h]
0x1401a19e6  mov     r8d, 4
0x1401a19ec  mov     rdx, [rsp+638h+Length]
0x1401a19f1  mov     rcx, [rsp+638h+Address]
0x1401a19f6  call    cs:__imp_?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z; GrepSecureVirtualMemory(void *,unsigned __int64,uint)
0x1401a19fd  nop     dword ptr [rax+rax+00h]
0x1401a1a02  mov     r15, rax
0x1401a1a05  mov     [rsp+638h+var_5F0], rax
0x1401a1a0a  jmp     short loc_1401A1A2A
0x1401a1a0c  lea     rcx, [rsp+638h+var_4A8]
0x1401a1a14  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a1a1b  nop     dword ptr [rax+rax+00h]
0x1401a1a20  mov     eax, 0C000000Dh
0x1401a1a25  jmp     loc_1401A19A3
0x1401a1a2a  test    r15, r15
0x1401a1a2d  jz      loc_1401A198A
0x1401a1a33  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401a1a3a  nop     dword ptr [rax+rax+00h]
0x1401a1a3f  mov     [rsp+638h+var_5D8], rax
0x1401a1a44  mov     rdx, rax
0x1401a1a47  lea     rcx, [rsp+638h+var_5C8]
0x1401a1a4c  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x1401a1a51  mov     r8, qword ptr [rsp+638h+lWidth+8]; HDC
0x1401a1a59  mov     rdx, [rsp+638h+var_5D8]; struct Gre::Base::SESSION_GLOBALS *
0x1401a1a5e  lea     rcx, [rsp+638h+var_558]; this
0x1401a1a66  call    ??0DCOBJA@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHDC__@@@Z; DCOBJA::DCOBJA(Gre::Base::SESSION_GLOBALS &,HDC__ *)
0x1401a1a6b  mov     rax, [rsp+638h+var_558]
0x1401a1a73  test    rax, rax
0x1401a1a76  jz      loc_1401A195D
0x1401a1a7c  xor     r15d, r15d
0x1401a1a7f  mov     rax, [rax+30h]
0x1401a1a83  mov     [rsp+638h+Length], rax
0x1401a1a88  xor     ecx, ecx
0x1401a1a8a  cmp     r13d, 3
0x1401a1a8e  setnbe  cl
0x1401a1a91  inc     ecx; iMode
0x1401a1a93  mov     [rsp+638h+flBlue], edi; flBlue
0x1401a1a97  mov     [rsp+638h+flGreen], r14d; flGreen
0x1401a1a9c  mov     r9d, esi; flRed
0x1401a1a9f  mov     r8, r12; pulColors
0x1401a1aa2  mov     esi, [rsp+638h+cColors]
0x1401a1aa6  mov     edx, esi; cColors
0x1401a1aa8  call    cs:__imp_EngCreatePalette
0x1401a1aaf  nop     dword ptr [rax+rax+00h]
0x1401a1ab4  mov     rdi, rax
0x1401a1ab7  mov     qword ptr [rsp+638h+cColors], rax
0x1401a1abc  test    rax, rax
0x1401a1abf  jz      loc_1401A1D4C
0x1401a1ac5  cmp     esi, 100h
0x1401a1acb  jz      loc_1401A1E04
0x1401a1ad1  mov     r12, [rsp+638h+Length]
0x1401a1ad6  mov     rax, [rsp+638h+Address]
0x1401a1adb  mov     qword ptr [rsp+638h+flGreen], rax; pvBits
0x1401a1ae0  mov     r9d, 1; fl
0x1401a1ae6  mov     r8d, r13d; iFormat
0x1401a1ae9  mov     edx, [rsp+638h+lWidth+4]; lWidth
0x1401a1af0  mov     rcx, qword ptr [rsp+638h+sizl.cx]; sizl
0x1401a1af5  call    cs:__imp_EngCreateBitmap
0x1401a1afc  nop     dword ptr [rax+rax+00h]
0x1401a1b01  mov     [rsp+638h+hsurf], rax
0x1401a1b06  mov     rcx, rdi; HPALETTE
0x1401a1b09  call    ?DxEngSetPaletteState@@YAHPEAUHPALETTE__@@K_K@Z; DxEngSetPaletteState(HPALETTE__ *,ulong,unsigned __int64)
0x1401a1b0e  cmp     [rsp+638h+hsurf], r15
0x1401a1b13  jz      loc_1401A1D4C
0x1401a1b19  mov     rsi, [rsp+638h+var_5D8]
0x1401a1b1e  mov     rdx, rsi
0x1401a1b21  lea     rcx, [rsp+638h+var_5D8]
0x1401a1b26  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x1401a1b2b  lea     rcx, [rsp+638h+var_580]; this
0x1401a1b33  call    ??0SURFREF@@QEAA@XZ; SURFREF::SURFREF(void)
0x1401a1b38  mov     r9d, 10h
0x1401a1b3e  mov     r8b, 5
0x1401a1b41  mov     rdx, [rsp+638h+hsurf]
0x1401a1b46  mov     rcx, rsi
0x1401a1b49  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1401a1b50  nop     dword ptr [rax+rax+00h]
0x1401a1b55  mov     [rsp+638h+var_560], rax
0x1401a1b5d  test    rax, rax
0x1401a1b60  jz      loc_1401A1CC2
0x1401a1b66  mov     r14b, 1
0x1401a1b69  lea     rcx, [rax+18h]; struct _SURFOBJ *
0x1401a1b6d  mov     rdx, rdi; HPALETTE
0x1401a1b70  call    ?DxEngSelectPaletteToSurface@@YAPEAUHPALETTE__@@PEAU_SURFOBJ@@PEAU1@@Z; DxEngSelectPaletteToSurface(_SURFOBJ *,HPALETTE__ *)
0x1401a1b75  mov     rax, [rsp+638h+var_560]
0x1401a1b7d  mov     rsi, [rsp+638h+var_5F0]
0x1401a1b82  mov     [rax+100h], rsi
0x1401a1b89  mov     rax, [rsp+638h+var_560]
0x1401a1b91  bts     dword ptr [rax+90h], 14h
0x1401a1b99  mov     rax, [rsp+638h+var_560]
0x1401a1ba1  bts     dword ptr [rax+90h], 0Eh
0x1401a1ba9  mov     rax, [rsp+638h+var_560]
0x1401a1bb1  bts     dword ptr [rax+90h], 9
0x1401a1bb9  lea     rcx, [rsp+638h+var_580]; this
0x1401a1bc1  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x1401a1bc6  mov     rdx, [rsp+638h+var_5D8]
0x1401a1bcb  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401a1bd2  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1401a1bd7  test    r14b, r14b
0x1401a1bda  jnz     loc_1401A1CCF
0x1401a1be0  cmp     [rsp+638h+var_5E8], r15
0x1401a1be5  jz      loc_1401A1E22
0x1401a1beb  mov     rsi, [rsp+638h+var_588]
0x1401a1bf3  lea     rcx, [rsi+28h]; void *
0x1401a1bf7  mov     r14d, 8
0x1401a1bfd  mov     r8d, r14d; Size
0x1401a1c00  lea     rdx, [rsp+638h+var_5E8]; Src
0x1401a1c05  call    RtlCopyToUser
0x1401a1c0a  lea     rcx, [rsi+30h]; void *
0x1401a1c0e  mov     r8d, r14d; Size
0x1401a1c11  lea     rdx, [rsp+638h+hsurf]; Src
0x1401a1c16  call    RtlCopyToUser
0x1401a1c1b  jmp     short loc_1401A1C59
0x1401a1c1d  mov     rcx, [rsp+638h+var_5E8]
0x1401a1c22  test    rcx, rcx
0x1401a1c25  jz      short loc_1401A1C38
0x1401a1c27  mov     edx, 1400000h
0x1401a1c2c  call    cs:__imp_GrepDeleteDC
0x1401a1c33  nop     dword ptr [rax+rax+00h]
0x1401a1c38  mov     rcx, [rsp+638h+hsurf]; hsurf
0x1401a1c3d  test    rcx, rcx
0x1401a1c40  jz      short loc_1401A1C4E
0x1401a1c42  call    cs:__imp_EngDeleteSurface
0x1401a1c49  nop     dword ptr [rax+rax+00h]
0x1401a1c4e  mov     r15d, 0C000000Dh
0x1401a1c54  mov     rdi, qword ptr [rsp+638h+cColors]
0x1401a1c59  test    rdi, rdi
0x1401a1c5c  jz      short loc_1401A1C6D
0x1401a1c5e  mov     rcx, rdi; hpal
0x1401a1c61  call    cs:__imp_EngDeletePalette
0x1401a1c68  nop     dword ptr [rax+rax+00h]
0x1401a1c6d  lea     rcx, [rsp+638h+var_558]; this
0x1401a1c75  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x1401a1c7a  mov     rdx, [rsp+638h+var_5C8]
0x1401a1c7f  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401a1c86  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1401a1c8b  lea     rcx, [rsp+638h+var_4A8]
0x1401a1c93  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a1c9a  nop     dword ptr [rax+rax+00h]
0x1401a1c9f  mov     eax, r15d
0x1401a1ca2  jmp     loc_1401A19A3
0x1401a1ca7  mov     r13d, 6
0x1401a1cad  mov     r14d, 0FF00h
0x1401a1cb3  mov     edi, 0FFh
0x1401a1cb8  mov     esi, 0FF0000h
0x1401a1cbd  jmp     loc_1401A1943
0x1401a1cc2  xor     r14b, r14b
0x1401a1cc5  mov     rsi, [rsp+638h+var_5F0]
0x1401a1cca  jmp     loc_1401A1BB9
0x1401a1ccf  xor     r8d, r8d
0x1401a1cd2  lea     edx, [r8+1]
0x1401a1cd6  mov     rcx, r12
0x1401a1cd9  call    cs:__imp_GreCreateDisplayDC
0x1401a1ce0  nop     dword ptr [rax+rax+00h]
0x1401a1ce5  mov     [rsp+638h+var_5E8], rax
0x1401a1cea  test    rax, rax
0x1401a1ced  jz      loc_1401A1BE0
0x1401a1cf3  mov     rdx, rax; HDC
0x1401a1cf6  lea     rcx, [rsp+638h+var_518]; this
0x1401a1cfe  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *)
0x1401a1d03  mov     r9b, 7
0x1401a1d06  mov     r8, [rsp+638h+hsurf]
0x1401a1d0b  lea     rdx, [rsp+638h+var_518]
0x1401a1d13  lea     rcx, [rsp+638h+var_5D8]
0x1401a1d18  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x1401a1d1f  nop     dword ptr [rax+rax+00h]
0x1401a1d24  mov     edx, 80000002h
0x1401a1d29  mov     rcx, [rsp+638h+hsurf]
0x1401a1d2e  call    cs:__imp_GreSetBitmapOwner
0x1401a1d35  nop     dword ptr [rax+rax+00h]
0x1401a1d3a  lea     rcx, [rsp+638h+var_518]; this
0x1401a1d42  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1401a1d47  jmp     loc_1401A1BE0
0x1401a1d4c  mov     rsi, [rsp+638h+var_5F0]
0x1401a1d51  jmp     loc_1401A1BE0
0x1401a1d56  sub     ecx, 1
0x1401a1d59  jz      loc_1401A1DE0
0x1401a1d5f  sub     ecx, 1
0x1401a1d62  jz      short loc_1401A1DE0
0x1401a1d64  cmp     ecx, 10h
0x1401a1d67  jnz     loc_1401A198A
0x1401a1d6d  mov     rdx, [rsp+638h+Src]; Src
0x1401a1d75  test    rdx, rdx
0x1401a1d78  jz      short loc_1401A1DBF
0x1401a1d7a  mov     r8d, 400h; Size
0x1401a1d80  lea     rcx, [rsp+638h+var_448]; void *
0x1401a1d88  call    RtlCopyFromUser
0x1401a1d8d  jmp     short loc_1401A1DAD
0x1401a1d8f  lea     rcx, [rsp+638h+var_4A8]
0x1401a1d97  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a1d9e  nop     dword ptr [rax+rax+00h]
0x1401a1da3  mov     eax, 0C000000Dh
0x1401a1da8  jmp     loc_1401A19A3
0x1401a1dad  lea     r12, [rsp+638h+var_448]
0x1401a1db5  mov     r8d, [rsp+638h+lWidth]
0x1401a1dbd  jmp     short loc_1401A1DC6
0x1401a1dbf  lea     r12, qword_140365140
0x1401a1dc6  mov     r13d, 3
0x1401a1dcc  mov     [rsp+638h+cColors], 100h
0x1401a1dd4  xor     esi, esi
0x1401a1dd6  xor     r14d, r14d
0x1401a1dd9  xor     edi, edi
0x1401a1ddb  jmp     loc_1401A1943
0x1401a1de0  mov     esi, 7C00h
0x1401a1de5  mov     edi, 1Fh
0x1401a1dea  lea     r13d, [rdi-1Bh]
0x1401a1dee  mov     r14d, 3E0h
0x1401a1df4  jmp     loc_1401A1943
0x1401a1df9  mov     r13d, 5
  ... truncated ...
```
