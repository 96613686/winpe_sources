# NtGdiDdDDICreateDCFromMemory

- ea: `0x14019fae0`
- end: `0x1401a0119`
- name: `NtGdiDdDDICreateDCFromMemory`
- size: `1593`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14005fab8`
- `0x14005fb0c`
- `0x140062bf4`
- `0x14007eef8`
- `0x140080fd4`
- `0x140092390`
- `0x14009654c`
- `0x14019fae0`
- `0x1401a0120`
- `0x1401a0180`
- `0x1401a01f8`
- `0x14029eaf4`
- `0x1402a4d38`
- `0x140341ff0`
- `0x1403d20b8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14019fc9a`
- `ntoskrnl!ProbeForWrite` at `0x14019fc9a`
- `win32kbase!GreCreateDisplayDC` at `0x14019ff99`
- `win32kbase!GreCreateDisplayDC` at `0x14019ff99`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14019fcf3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14019fcf3`
- `win32kbase!HmgShareLock` at `0x14019fe09`
- `win32kbase!HmgShareLock` at `0x14019fe09`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14019fc3e`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14019fe8b`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14019ff3f`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fb17`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fb17`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fb7b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fc52`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fcd4`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019ff53`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a0057`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fb7b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fc52`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019fcd4`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14019ff53`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401a0057`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14019ffd8`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14019ffd8`
- `win32kbase!EngCreateBitmap` at `0x14019fdb5`
- `win32kbase!EngCreateBitmap` at `0x14019fdb5`
- `win32kbase!EngDeleteSurface` at `0x14019ff02`
- `win32kbase!EngDeleteSurface` at `0x1401a00ec`
- `win32kbase!EngDeleteSurface` at `0x14019ff02`
- `win32kbase!EngDeleteSurface` at `0x1401a00ec`
- `win32kbase!GrepDeleteDC` at `0x14019feec`
- `win32kbase!GrepDeleteDC` at `0x14019feec`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x14019fcb6`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x14019fcb6`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x14019fc20`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a0102`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x14019fc20`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1401a0102`
- `win32kbase!EngCreatePalette` at `0x14019fd68`
- `win32kbase!EngCreatePalette` at `0x14019fd68`
- `win32kbase!EngDeletePalette` at `0x14019ff21`
- `win32kbase!EngDeletePalette` at `0x14019ff21`
- `win32kbase!GreSetBitmapOwner` at `0x14019ffee`
- `win32kbase!GreSetBitmapOwner` at `0x14019ffee`

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
        v3 = (ULONG *)qword_1403641C0;
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
      *(_QWORD *)(v41 + 272) = v31;
      *(_DWORD *)(v41 + 160) |= 0x100000u;
      *(_DWORD *)(v41 + 160) |= 0x4000u;
      *(_DWORD *)(v41 + 160) |= 0x200u;
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
0x14019fae0  push    rsi
0x14019fae2  push    rdi
0x14019fae3  push    r12
0x14019fae5  push    r13
0x14019fae7  push    r14
0x14019fae9  push    r15
0x14019faeb  sub     rsp, 608h
0x14019faf2  mov     rax, cs:__security_cookie
0x14019faf9  xor     rax, rsp
0x14019fafc  mov     [rsp+638h+var_48], rax
0x14019fb04  mov     rdi, rcx
0x14019fb07  mov     [rsp+638h+var_588], rcx
0x14019fb0f  lea     rcx, [rsp+638h+var_4A8]
0x14019fb17  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x14019fb1e  nop     dword ptr [rax+rax+00h]
0x14019fb23  mov     [rsp+638h+var_5E8], 0
0x14019fb2c  mov     [rsp+638h+hsurf], 0
0x14019fb35  mov     [rsp+638h+Length], 0
0x14019fb3e  xorps   xmm0, xmm0
0x14019fb41  xor     eax, eax
0x14019fb43  movups  xmmword ptr [rsp+638h+Address], xmm0
0x14019fb48  movups  xmmword ptr [rsp+638h+lWidth], xmm0
0x14019fb50  movups  xmmword ptr [rsp+638h+Src], xmm0
0x14019fb58  mov     [rsp+638h+var_590], rax
0x14019fb60  lea     r8d, [rax+38h]; Size
0x14019fb64  mov     rdx, rdi; Src
0x14019fb67  lea     rcx, [rsp+638h+Address]; void *
0x14019fb6c  call    RtlCopyFromUser
0x14019fb71  jmp     short loc_14019FB91
0x14019fb73  lea     rcx, [rsp+638h+var_4A8]
0x14019fb7b  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14019fb82  nop     dword ptr [rax+rax+00h]
0x14019fb87  mov     eax, 0C000000Dh
0x14019fb8c  jmp     loc_14019FC63
0x14019fb91  mov     eax, dword ptr [rsp+638h+Address+0Ch]
0x14019fb98  mov     [rsp+638h+sizl.cx], eax
0x14019fb9c  mov     r8d, [rsp+638h+lWidth]
0x14019fba4  mov     [rsp+638h+sizl.cy], r8d
0x14019fba9  test    eax, eax
0x14019fbab  jle     loc_14019FC4A
0x14019fbb1  test    r8d, r8d
0x14019fbb4  jle     loc_14019FC4A
0x14019fbba  mov     [rsp+638h+cColors], 0
0x14019fbc2  xor     r12d, r12d
0x14019fbc5  mov     ecx, dword ptr [rsp+638h+Address+8]
0x14019fbcc  sub     ecx, 14h
0x14019fbcf  jz      loc_1401A00B9
0x14019fbd5  sub     ecx, 1
0x14019fbd8  jz      loc_14019FF67
0x14019fbde  sub     ecx, 1
0x14019fbe1  jz      loc_14019FF67
0x14019fbe7  sub     ecx, 1
0x14019fbea  jnz     loc_1401A0016
0x14019fbf0  mov     esi, 0F800h
0x14019fbf5  lea     edi, [rcx+1Fh]
0x14019fbf8  lea     r13d, [r12+4]
0x14019fbfd  mov     r14d, 7E0h
0x14019fc03  mov     ecx, [rsp+638h+lWidth+4]
0x14019fc0a  mov     eax, r8d
0x14019fc0d  imul    rcx, rax
0x14019fc11  mov     eax, 0FFFFFFFFh
0x14019fc16  cmp     rcx, rax
0x14019fc19  jbe     short loc_14019FC86
0x14019fc1b  jmp     short loc_14019FC4A
0x14019fc1d  mov     rcx, r15
0x14019fc20  call    cs:__imp_?GrepUnsecureVirtualMemory@@YAXPEAX@Z; GrepUnsecureVirtualMemory(void *)
0x14019fc27  nop     dword ptr [rax+rax+00h]
0x14019fc2c  lea     rcx, [rsp+638h+var_558]; this
0x14019fc34  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x14019fc39  mov     rdx, [rsp+638h+var_5C8]
0x14019fc3e  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14019fc45  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14019fc4a  lea     rcx, [rsp+638h+var_4A8]
0x14019fc52  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14019fc59  nop     dword ptr [rax+rax+00h]
0x14019fc5e  mov     eax, 0C000000Dh
0x14019fc63  mov     rcx, [rsp+638h+var_48]
0x14019fc6b  xor     rcx, rsp; StackCookie
0x14019fc6e  call    __security_check_cookie
0x14019fc73  add     rsp, 608h
0x14019fc7a  pop     r15
0x14019fc7c  pop     r14
0x14019fc7e  pop     r13
0x14019fc80  pop     r12
0x14019fc82  pop     rdi
0x14019fc83  pop     rsi
0x14019fc84  retn
0x14019fc86  mov     dword ptr [rsp+638h+Length], ecx
0x14019fc8a  mov     r8d, 4; Alignment
0x14019fc90  mov     rdx, [rsp+638h+Length]; Length
0x14019fc95  mov     rcx, [rsp+638h+Address]; Address
0x14019fc9a  call    cs:__imp_ProbeForWrite
0x14019fca1  nop     dword ptr [rax+rax+00h]
0x14019fca6  mov     r8d, 4
0x14019fcac  mov     rdx, [rsp+638h+Length]
0x14019fcb1  mov     rcx, [rsp+638h+Address]
0x14019fcb6  call    cs:__imp_?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z; GrepSecureVirtualMemory(void *,unsigned __int64,uint)
0x14019fcbd  nop     dword ptr [rax+rax+00h]
0x14019fcc2  mov     r15, rax
0x14019fcc5  mov     [rsp+638h+var_5F0], rax
0x14019fcca  jmp     short loc_14019FCEA
0x14019fccc  lea     rcx, [rsp+638h+var_4A8]
0x14019fcd4  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14019fcdb  nop     dword ptr [rax+rax+00h]
0x14019fce0  mov     eax, 0C000000Dh
0x14019fce5  jmp     loc_14019FC63
0x14019fcea  test    r15, r15
0x14019fced  jz      loc_14019FC4A
0x14019fcf3  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14019fcfa  nop     dword ptr [rax+rax+00h]
0x14019fcff  mov     [rsp+638h+var_5D8], rax
0x14019fd04  mov     rdx, rax
0x14019fd07  lea     rcx, [rsp+638h+var_5C8]
0x14019fd0c  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x14019fd11  mov     r8, qword ptr [rsp+638h+lWidth+8]; HDC
0x14019fd19  mov     rdx, [rsp+638h+var_5D8]; struct Gre::Base::SESSION_GLOBALS *
0x14019fd1e  lea     rcx, [rsp+638h+var_558]; this
0x14019fd26  call    ??0DCOBJA@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHDC__@@@Z; DCOBJA::DCOBJA(Gre::Base::SESSION_GLOBALS &,HDC__ *)
0x14019fd2b  mov     rax, [rsp+638h+var_558]
0x14019fd33  test    rax, rax
0x14019fd36  jz      loc_14019FC1D
0x14019fd3c  xor     r15d, r15d
0x14019fd3f  mov     rax, [rax+30h]
0x14019fd43  mov     [rsp+638h+Length], rax
0x14019fd48  xor     ecx, ecx
0x14019fd4a  cmp     r13d, 3
0x14019fd4e  setnbe  cl
0x14019fd51  inc     ecx; iMode
0x14019fd53  mov     [rsp+638h+flBlue], edi; flBlue
0x14019fd57  mov     [rsp+638h+flGreen], r14d; flGreen
0x14019fd5c  mov     r9d, esi; flRed
0x14019fd5f  mov     r8, r12; pulColors
0x14019fd62  mov     esi, [rsp+638h+cColors]
0x14019fd66  mov     edx, esi; cColors
0x14019fd68  call    cs:__imp_EngCreatePalette
0x14019fd6f  nop     dword ptr [rax+rax+00h]
0x14019fd74  mov     rdi, rax
0x14019fd77  mov     qword ptr [rsp+638h+cColors], rax
0x14019fd7c  test    rax, rax
0x14019fd7f  jz      loc_1401A000C
0x14019fd85  cmp     esi, 100h
0x14019fd8b  jz      loc_1401A00C4
0x14019fd91  mov     r12, [rsp+638h+Length]
0x14019fd96  mov     rax, [rsp+638h+Address]
0x14019fd9b  mov     qword ptr [rsp+638h+flGreen], rax; pvBits
0x14019fda0  mov     r9d, 1; fl
0x14019fda6  mov     r8d, r13d; iFormat
0x14019fda9  mov     edx, [rsp+638h+lWidth+4]; lWidth
0x14019fdb0  mov     rcx, qword ptr [rsp+638h+sizl.cx]; sizl
0x14019fdb5  call    cs:__imp_EngCreateBitmap
0x14019fdbc  nop     dword ptr [rax+rax+00h]
0x14019fdc1  mov     [rsp+638h+hsurf], rax
0x14019fdc6  mov     rcx, rdi; HPALETTE
0x14019fdc9  call    ?DxEngSetPaletteState@@YAHPEAUHPALETTE__@@K_K@Z; DxEngSetPaletteState(HPALETTE__ *,ulong,unsigned __int64)
0x14019fdce  cmp     [rsp+638h+hsurf], r15
0x14019fdd3  jz      loc_1401A000C
0x14019fdd9  mov     rsi, [rsp+638h+var_5D8]
0x14019fdde  mov     rdx, rsi
0x14019fde1  lea     rcx, [rsp+638h+var_5D8]
0x14019fde6  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x14019fdeb  lea     rcx, [rsp+638h+var_580]; this
0x14019fdf3  call    ??0SURFREF@@QEAA@XZ; SURFREF::SURFREF(void)
0x14019fdf8  mov     r9d, 10h
0x14019fdfe  mov     r8b, 5
0x14019fe01  mov     rdx, [rsp+638h+hsurf]
0x14019fe06  mov     rcx, rsi
0x14019fe09  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14019fe10  nop     dword ptr [rax+rax+00h]
0x14019fe15  mov     [rsp+638h+var_560], rax
0x14019fe1d  test    rax, rax
0x14019fe20  jz      loc_14019FF82
0x14019fe26  mov     r14b, 1
0x14019fe29  lea     rcx, [rax+18h]; struct _SURFOBJ *
0x14019fe2d  mov     rdx, rdi; HPALETTE
0x14019fe30  call    ?DxEngSelectPaletteToSurface@@YAPEAUHPALETTE__@@PEAU_SURFOBJ@@PEAU1@@Z; DxEngSelectPaletteToSurface(_SURFOBJ *,HPALETTE__ *)
0x14019fe35  mov     rax, [rsp+638h+var_560]
0x14019fe3d  mov     rsi, [rsp+638h+var_5F0]
0x14019fe42  mov     [rax+110h], rsi
0x14019fe49  mov     rax, [rsp+638h+var_560]
0x14019fe51  bts     dword ptr [rax+0A0h], 14h
0x14019fe59  mov     rax, [rsp+638h+var_560]
0x14019fe61  bts     dword ptr [rax+0A0h], 0Eh
0x14019fe69  mov     rax, [rsp+638h+var_560]
0x14019fe71  bts     dword ptr [rax+0A0h], 9
0x14019fe79  lea     rcx, [rsp+638h+var_580]; this
0x14019fe81  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14019fe86  mov     rdx, [rsp+638h+var_5D8]
0x14019fe8b  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14019fe92  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14019fe97  test    r14b, r14b
0x14019fe9a  jnz     loc_14019FF8F
0x14019fea0  cmp     [rsp+638h+var_5E8], r15
0x14019fea5  jz      loc_1401A00E2
0x14019feab  mov     rsi, [rsp+638h+var_588]
0x14019feb3  lea     rcx, [rsi+28h]; void *
0x14019feb7  mov     r14d, 8
0x14019febd  mov     r8d, r14d; Size
0x14019fec0  lea     rdx, [rsp+638h+var_5E8]; Src
0x14019fec5  call    RtlCopyToUser
0x14019feca  lea     rcx, [rsi+30h]; void *
0x14019fece  mov     r8d, r14d; Size
0x14019fed1  lea     rdx, [rsp+638h+hsurf]; Src
0x14019fed6  call    RtlCopyToUser
0x14019fedb  jmp     short loc_14019FF19
0x14019fedd  mov     rcx, [rsp+638h+var_5E8]
0x14019fee2  test    rcx, rcx
0x14019fee5  jz      short loc_14019FEF8
0x14019fee7  mov     edx, 1400000h
0x14019feec  call    cs:__imp_GrepDeleteDC
0x14019fef3  nop     dword ptr [rax+rax+00h]
0x14019fef8  mov     rcx, [rsp+638h+hsurf]; hsurf
0x14019fefd  test    rcx, rcx
0x14019ff00  jz      short loc_14019FF0E
0x14019ff02  call    cs:__imp_EngDeleteSurface
0x14019ff09  nop     dword ptr [rax+rax+00h]
0x14019ff0e  mov     r15d, 0C000000Dh
0x14019ff14  mov     rdi, qword ptr [rsp+638h+cColors]
0x14019ff19  test    rdi, rdi
0x14019ff1c  jz      short loc_14019FF2D
0x14019ff1e  mov     rcx, rdi; hpal
0x14019ff21  call    cs:__imp_EngDeletePalette
0x14019ff28  nop     dword ptr [rax+rax+00h]
0x14019ff2d  lea     rcx, [rsp+638h+var_558]; this
0x14019ff35  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x14019ff3a  mov     rdx, [rsp+638h+var_5C8]
0x14019ff3f  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14019ff46  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14019ff4b  lea     rcx, [rsp+638h+var_4A8]
0x14019ff53  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14019ff5a  nop     dword ptr [rax+rax+00h]
0x14019ff5f  mov     eax, r15d
0x14019ff62  jmp     loc_14019FC63
0x14019ff67  mov     r13d, 6
0x14019ff6d  mov     r14d, 0FF00h
0x14019ff73  mov     edi, 0FFh
0x14019ff78  mov     esi, 0FF0000h
0x14019ff7d  jmp     loc_14019FC03
0x14019ff82  xor     r14b, r14b
0x14019ff85  mov     rsi, [rsp+638h+var_5F0]
0x14019ff8a  jmp     loc_14019FE79
0x14019ff8f  xor     r8d, r8d
0x14019ff92  lea     edx, [r8+1]
0x14019ff96  mov     rcx, r12
0x14019ff99  call    cs:__imp_GreCreateDisplayDC
0x14019ffa0  nop     dword ptr [rax+rax+00h]
0x14019ffa5  mov     [rsp+638h+var_5E8], rax
0x14019ffaa  test    rax, rax
0x14019ffad  jz      loc_14019FEA0
0x14019ffb3  mov     rdx, rax; HDC
0x14019ffb6  lea     rcx, [rsp+638h+var_518]; this
0x14019ffbe  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *)
0x14019ffc3  mov     r9b, 7
0x14019ffc6  mov     r8, [rsp+638h+hsurf]
0x14019ffcb  lea     rdx, [rsp+638h+var_518]
0x14019ffd3  lea     rcx, [rsp+638h+var_5D8]
0x14019ffd8  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14019ffdf  nop     dword ptr [rax+rax+00h]
0x14019ffe4  mov     edx, 80000002h
0x14019ffe9  mov     rcx, [rsp+638h+hsurf]
0x14019ffee  call    cs:__imp_GreSetBitmapOwner
0x14019fff5  nop     dword ptr [rax+rax+00h]
0x14019fffa  lea     rcx, [rsp+638h+var_518]; this
0x1401a0002  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1401a0007  jmp     loc_14019FEA0
0x1401a000c  mov     rsi, [rsp+638h+var_5F0]
0x1401a0011  jmp     loc_14019FEA0
0x1401a0016  sub     ecx, 1
0x1401a0019  jz      loc_1401A00A0
0x1401a001f  sub     ecx, 1
0x1401a0022  jz      short loc_1401A00A0
0x1401a0024  cmp     ecx, 10h
0x1401a0027  jnz     loc_14019FC4A
0x1401a002d  mov     rdx, [rsp+638h+Src]; Src
0x1401a0035  test    rdx, rdx
0x1401a0038  jz      short loc_1401A007F
0x1401a003a  mov     r8d, 400h; Size
0x1401a0040  lea     rcx, [rsp+638h+var_448]; void *
0x1401a0048  call    RtlCopyFromUser
0x1401a004d  jmp     short loc_1401A006D
0x1401a004f  lea     rcx, [rsp+638h+var_4A8]
0x1401a0057  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401a005e  nop     dword ptr [rax+rax+00h]
0x1401a0063  mov     eax, 0C000000Dh
0x1401a0068  jmp     loc_14019FC63
0x1401a006d  lea     r12, [rsp+638h+var_448]
0x1401a0075  mov     r8d, [rsp+638h+lWidth]
0x1401a007d  jmp     short loc_1401A0086
0x1401a007f  lea     r12, qword_1403641C0
0x1401a0086  mov     r13d, 3
0x1401a008c  mov     [rsp+638h+cColors], 100h
0x1401a0094  xor     esi, esi
0x1401a0096  xor     r14d, r14d
0x1401a0099  xor     edi, edi
0x1401a009b  jmp     loc_14019FC03
0x1401a00a0  mov     esi, 7C00h
0x1401a00a5  mov     edi, 1Fh
0x1401a00aa  lea     r13d, [rdi-1Bh]
0x1401a00ae  mov     r14d, 3E0h
0x1401a00b4  jmp     loc_14019FC03
0x1401a00b9  mov     r13d, 5
  ... truncated ...
```
