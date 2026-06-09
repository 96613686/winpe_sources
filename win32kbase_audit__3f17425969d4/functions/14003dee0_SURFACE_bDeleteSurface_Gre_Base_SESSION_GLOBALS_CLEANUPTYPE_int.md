# SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)

- ea: `0x14003dee0`
- end: `0x14003e5ee`
- name: `?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z`
- size: `1806`
- prototype: `__int64 __fastcall(__int64, __int64 *, int, int)`
- caller_count: `8`
- callee_count: `35`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140027d70`
- `0x140039f10`
- `0x14003db48`
- `0x14003ea80`
- `0x14003ebe4`
- `0x14003ec5c`
- `0x140170390`
- `0x1401e6fb8`

## callees

- `0x140011e60`
- `0x140011f04`
- `0x1400123f0`
- `0x1400181a0`
- `0x14001ae6c`
- `0x140022dbc`
- `0x140025024`
- `0x14002d170`
- `0x140031520`
- `0x1400318f0`
- `0x140033af8`
- `0x140033c00`
- `0x1400345b0`
- `0x14003ac68`
- `0x14003af40`
- `0x14003b510`
- `0x14003dee0`
- `0x140070750`
- `0x1400782b0`
- `0x140079f00`
- `0x14007cc90`
- `0x1400903e0`
- `0x1400f68c0`
- `0x14010d82c`
- `0x14010f6d0`
- `0x140111520`
- `0x140119784`
- `0x14012e228`
- `0x1401473cc`
- `0x1401570b8`
- `0x1401701f8`
- `0x1401b7eec`
- `0x1401e2c10`
- `0x1401e2d00`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e246`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e2b6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e246`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003e2b6`
- `ntoskrnl!PsGetProcessId` at `0x14003e4b8`
- `ntoskrnl!PsGetProcessId` at `0x14003e4b8`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14003e2fb`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14003e2fb`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14003e321`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14003e321`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003e264`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003e2d4`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003e264`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003e2d4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e1f0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e215`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e3bb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e3e5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e556`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e57b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e1f0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e215`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e3bb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e3e5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e556`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003e57b`

## pseudocode

```c
__int64 __fastcall SURFACE::bDeleteSurface(__int64 a1, __int64 *a2, int a3, int a4)
{
  unsigned int v6; // edi
  __int64 v7; // r14
  void *v8; // r13
  void *v9; // r12
  void *v10; // r14
  __int128 v11; // xmm0
  __int64 v12; // rcx
  __int128 v13; // xmm1
  unsigned int v14; // eax
  __int128 v15; // xmm0
  bool IsLockOwnedByCurrentThread; // al
  __int64 v17; // r15
  unsigned int v18; // r15d
  __int64 v19; // r15
  int v20; // eax
  __int64 v21; // rcx
  int (*v22)(void); // rax
  __int64 v23; // rcx
  void (__fastcall *v24)(__int64); // rax
  struct _GRETHREAD *CurrentThread; // rax
  void *v26; // r14
  int v27; // r12d
  struct _GRETHREAD *v28; // rsi
  PVOID v29; // rcx
  __int64 v30; // rcx
  unsigned int v31; // eax
  PVOID v32; // rdx
  int (*v33)(void); // rax
  __int64 v34; // rcx
  PVOID v35; // rsi
  void (__fastcall *v36)(PVOID); // rax
  PEPROCESS *v37; // r8
  __int64 v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rdx
  PVOID v41; // rsi
  unsigned int ProcessId; // eax
  __int64 v43; // rcx
  __int64 v44; // rbx
  int (*v45)(void); // rax
  __int64 v46; // rcx
  void (__fastcall *v47)(__int64); // rax
  int v49; // [rsp+30h] [rbp-D8h]
  PVOID BaseAddress; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v51; // [rsp+50h] [rbp-B8h]
  int v52; // [rsp+54h] [rbp-B4h]
  ULONG_PTR v53; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A8h] BYREF
  ULONG_PTR RegionSize; // [rsp+68h] [rbp-A0h] BYREF
  int v56; // [rsp+70h] [rbp-98h]
  int v57; // [rsp+74h] [rbp-94h]
  int v58; // [rsp+78h] [rbp-90h]
  unsigned int v59; // [rsp+7Ch] [rbp-8Ch]
  void *v60; // [rsp+80h] [rbp-88h] BYREF
  __int64 v61; // [rsp+88h] [rbp-80h] BYREF
  __int64 v62; // [rsp+90h] [rbp-78h]
  __int64 v63; // [rsp+98h] [rbp-70h]
  __int64 v64; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v65; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-50h]
  __int128 v67; // [rsp+C8h] [rbp-40h]
  __int64 v68; // [rsp+D8h] [rbp-30h]
  _BYTE v69[24]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v70[208]; // [rsp+F8h] [rbp-10h] BYREF

  v6 = 1;
  if ( !SURFACE::bIsDefault((SURFACE *)a1) && a1 )
  {
    if ( *(_WORD *)(a1 + 100) )
    {
      v8 = 0;
      v52 = 0;
      v10 = 0;
      v62 = 0;
      v9 = 0;
    }
    else
    {
      v7 = *(_QWORD *)(a1 + 72);
      v8 = *(void **)(a1 + 224);
      v9 = *(void **)(a1 + 256);
      v62 = *(_QWORD *)(a1 + 216);
      v52 = *(_DWORD *)(a1 + 248);
      v10 = (void *)(v7 - (unsigned __int16)*(_DWORD *)(a1 + 244));
    }
    v11 = *(_OWORD *)(a1 + 304);
    v12 = *a2;
    v13 = *(_OWORD *)(a1 + 320);
    v61 = *(_QWORD *)(a1 + 160);
    v68 = *(_QWORD *)(a1 + 168);
    v51 = *(_WORD *)(a1 + 102);
    RegionSize = *(_QWORD *)(a1 + 280);
    v56 = *(_DWORD *)(a1 + 352);
    v53 = *(_QWORD *)(a1 + 616);
    v60 = *(void **)(a1 + 624);
    v57 = *(_DWORD *)(a1 + 640);
    v14 = *(_DWORD *)(a1 + 644);
    v65 = v11;
    v59 = v14;
    v15 = *(_OWORD *)(a1 + 336);
    v58 = *(_DWORD *)(a1 + 648);
    v66 = v13;
    v67 = v15;
    IsLockOwnedByCurrentThread = GrepIsLockOwnedByCurrentThread((HSEMAPHORE)(v12 + 624));
    NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(
      (NEEDDYNAMICMODECHANGESHARELOCK *)v69,
      !IsLockOwnedByCurrentThread);
    v17 = *(_QWORD *)(a1 + 48);
    v54 = v17;
    if ( !v17 || (*(_DWORD *)(a1 + 144) & 0x400000) == 0 || (*(_DWORD *)(v17 + 40) & 1) == 0 )
      NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v69);
    v64 = 0;
    DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v70);
    if ( (*(_DWORD *)(a1 + 144) & 0x400000) != 0 && v17 )
    {
      NEEDGRELOCK::vLock((NEEDGRELOCK *)&v64, (struct PDEVOBJ *)&v54);
      DEVLOCKOBJ::vLock((DEVLOCKOBJ *)v70, (struct PDEVOBJ *)&v54);
    }
    v63 = *(_QWORD *)a1;
    v18 = 0;
    LODWORD(v54) = GreGetObjectOwner(v63, 5);
    LODWORD(BaseAddress) = 0;
    if ( !a4 )
    {
      v19 = v63;
      if ( !HmgRemoveObject((struct Gre::Base::SESSION_GLOBALS *)a2, *((_DWORD *)a2 + 778), 5, (__int64)&BaseAddress) )
      {
        if ( a3 != 1 || (LOBYTE(v49) = 5, !HmgRemoveObjectImpl(a2, v19, 0, 1, 1, v49, &BaseAddress)) )
        {
          if ( (_DWORD)BaseAddress == 1 )
          {
            if ( !_bittest((const signed __int32 *)(a1 + 144), 0xBu) )
            {
              EngSetLastError(0xAAu);
              goto LABEL_22;
            }
          }
          else
          {
            if ( !*(_QWORD *)(a1 + 192)
              && !(unsigned int)SURFACE::bStockSurface((SURFACE *)a1)
              && !_bittest((const signed __int32 *)(a1 + 144), 0xBu) )
            {
              Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline();
LABEL_22:
              v6 = 0;
LABEL_98:
              DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v70);
              NEEDGRELOCK::vUnlock((NEEDGRELOCK *)&v64);
              NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v69);
              return v6;
            }
            v20 = *(_DWORD *)(a1 + 144);
            if ( (v20 & 0x800) != 0 )
            {
              if ( !*(_DWORD *)(a1 + 352) )
              {
                *(_DWORD *)(a1 + 352) = 1;
                _InterlockedAdd((volatile signed __int32 *)a2 + 25, 1u);
              }
            }
            else
            {
              *(_DWORD *)(a1 + 144) = v20 | 0x1000000;
            }
          }
          HmgDecrementShareReferenceCount(a2, a1);
          goto LABEL_98;
        }
      }
      v18 = (unsigned int)BaseAddress;
    }
    if ( (unsigned int)IsSURFMEMMappingEnabled() )
      SURFACE::UnmapUserVAFromKernel((SURFACE *)a1, 1);
    BaseAddress = *(PVOID *)(a1 + 72);
    if ( v56 )
      _InterlockedDecrement((volatile signed __int32 *)a2 + 25);
    if ( (*(_DWORD *)(a1 + 144) & 0x40000) != 0 && *(_QWORD *)(a1 + 592) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v22 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 24) + 2048LL);
    if ( v22 )
    {
      if ( v22() >= 0 )
      {
        v24 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v23) + 24) + 2056LL);
        if ( v24 )
          v24(a1);
      }
    }
    SURFACE::vDeleteDriverRealization((SURFACE *)a1);
    if ( v9 )
    {
      if ( *(_DWORD *)(a1 + 240) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
        MmUnsecureVirtualMemory(v9);
      goto LABEL_89;
    }
    if ( v52 )
    {
      if ( BaseAddress )
      {
        v65 = 0u;
        v66 = (unsigned __int64)v10;
        LODWORD(v67) = 3;
        Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v65);
      }
      goto LABEL_89;
    }
    if ( v8 )
    {
      if ( *(_DWORD *)(a1 + 240) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
      {
        MmUnsecureVirtualMemory(v8);
        if ( BaseAddress )
        {
          if ( v62 )
          {
            ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v10);
          }
          else
          {
            RegionSize = 0;
            ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
          }
        }
      }
      goto LABEL_89;
    }
    if ( (v51 & 8) == 0 )
    {
      if ( (v51 & 0x800) != 0 )
      {
        SEMOBJ<36>::SEMOBJ<36>(&v60, a2);
        v37 = *(PEPROCESS **)(a1 + 296);
        if ( v37 )
        {
          v38 = a1 + 560;
          v39 = *(_QWORD *)(a1 + 560);
          if ( v39 != a1 + 560 )
          {
            if ( *(_QWORD *)(v39 + 8) != v38 || (v40 = *(_QWORD **)(a1 + 568), *v40 != v38) )
              __fastfail(3u);
            *v40 = v39;
            *(_QWORD *)(v39 + 8) = v40;
          }
          v41 = BaseAddress;
          if ( BaseAddress && RegionSize )
          {
            ProcessId = (unsigned int)PsGetProcessId(*v37);
            Gre::MapViewOfSectionObj::Unmap(ProcessId, v41);
          }
        }
        W32PIDLOCK::vCleanUp((W32PIDLOCK *)&v65);
        if ( RegionSize )
        {
          v53 = RegionSize;
          Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v53);
        }
        SEMOBJ<36>::vUnlock(&v60);
      }
      else if ( (v51 & 0x10) != 0 )
      {
        vFreeKernelSection(BaseAddress);
      }
      goto LABEL_89;
    }
    if ( (v51 & 0x80u) == 0 )
    {
      EngTryFreeUserMem(BaseAddress);
LABEL_89:
      if ( (*(_DWORD *)(a1 + 148) & 0x1000) != 0 )
        GrepCaptureLiveMemoryDump(400, 4, v63, v18, (unsigned int)v54, 0);
      SURFACE_Free((void *)a1);
      v44 = v68;
      if ( v68 )
      {
        v45 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 24) + 2096LL);
        if ( v45 )
        {
          if ( v45() >= 0 )
          {
            v47 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v46) + 24) + 2104LL);
            if ( v47 )
              v47(v44);
          }
        }
      }
      if ( v61 )
        XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v61);
      goto LABEL_98;
    }
    CurrentThread = GreGetCurrentThread();
    v26 = v60;
    v27 = v57;
    v28 = CurrentThread;
    *(_QWORD *)&v65 = 0;
    v29 = v60;
    *((_QWORD *)&v66 + 1) = 0;
    if ( v57 )
      v29 = BaseAddress;
    *(_QWORD *)&v66 = v29;
    *((_QWORD *)&v65 + 1) = 0;
    LODWORD(v67) = 1;
    Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v65);
    if ( v28 && *((_QWORD *)v28 + 8) )
    {
      v31 = UMPDGetThreadClientPID(v28);
    }
    else
    {
      if ( !v58 )
      {
        v33 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v30) + 24) + 2080LL);
        if ( v33 )
        {
          if ( v33() >= 0 )
          {
            v35 = BaseAddress;
            v36 = *(void (__fastcall **)(PVOID))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v34) + 24) + 2088LL);
            if ( v36 )
              v36(v35);
          }
        }
        goto LABEL_70;
      }
      v31 = v59;
    }
    v32 = BaseAddress;
    if ( v27 )
      v32 = v26;
    Gre::MapViewOfSectionObj::Unmap(v31, v32);
LABEL_70:
    if ( v53 )
      Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v53);
    else
      GrepCaptureLiveMemoryDump(400, 68, 2, 0, 0, 0);
    goto LABEL_89;
  }
  return v6;
}

```

## disassembly

```asm
0x14003dee0  mov     rax, rsp
0x14003dee3  mov     [rax+8], rbx
0x14003dee7  mov     [rax+20h], r9d
0x14003deeb  mov     [rax+18h], r8d
0x14003deef  push    rbp
0x14003def0  push    rsi
0x14003def1  push    rdi
0x14003def2  push    r12
0x14003def4  push    r13
0x14003def6  push    r14
0x14003def8  push    r15
0x14003defa  lea     rbp, [rax-0C8h]
0x14003df01  sub     rsp, 190h
0x14003df08  mov     rsi, rdx
0x14003df0b  mov     rbx, rcx
0x14003df0e  mov     edi, 1
0x14003df13  call    ?bIsDefault@SURFACE@@QEBA_NXZ; SURFACE::bIsDefault(void)
0x14003df18  xor     ecx, ecx
0x14003df1a  test    al, al
0x14003df1c  jnz     loc_14003E5D0
0x14003df22  test    rbx, rbx
0x14003df25  jz      loc_14003E5D0
0x14003df2b  cmp     [rbx+64h], cx
0x14003df2f  jnz     short loc_14003DF66
0x14003df31  mov     rax, [rbx+0D8h]
0x14003df38  mov     r14, [rbx+48h]
0x14003df3c  mov     r13, [rbx+0E0h]
0x14003df43  mov     r12, [rbx+100h]
0x14003df4a  mov     [rbp+0C0h+var_138], rax
0x14003df4e  mov     eax, [rbx+0F8h]
0x14003df54  mov     dword ptr [rsp+1C0h+var_178+4], eax
0x14003df58  mov     eax, [rbx+0F4h]
0x14003df5e  movzx   ecx, ax
0x14003df61  sub     r14, rcx
0x14003df64  jmp     short loc_14003DF77
0x14003df66  mov     r13, rcx
0x14003df69  mov     dword ptr [rsp+1C0h+var_178+4], ecx
0x14003df6d  mov     r14, rcx
0x14003df70  mov     [rbp+0C0h+var_138], rcx
0x14003df74  mov     r12, rcx
0x14003df77  mov     rax, [rbx+0A0h]
0x14003df7e  movups  xmm0, xmmword ptr [rbx+130h]
0x14003df85  mov     rcx, [rsi]
0x14003df88  movups  xmm1, xmmword ptr [rbx+140h]
0x14003df8f  mov     [rbp+0C0h+var_140], rax
0x14003df93  add     rcx, 270h; HSEMAPHORE
0x14003df9a  mov     rax, [rbx+0A8h]
0x14003dfa1  mov     [rbp+0C0h+var_F0], rax
0x14003dfa5  movzx   eax, word ptr [rbx+66h]
0x14003dfa9  mov     word ptr [rsp+1C0h+var_178], ax
0x14003dfae  mov     rax, [rbx+118h]
0x14003dfb5  mov     [rsp+1C0h+RegionSize], rax
0x14003dfba  mov     eax, [rbx+160h]
0x14003dfc0  mov     [rsp+1C0h+var_158], eax
0x14003dfc4  mov     rax, [rbx+268h]
0x14003dfcb  mov     [rsp+1C0h+var_170], rax
0x14003dfd0  mov     rax, [rbx+270h]
0x14003dfd7  mov     [rsp+1C0h+var_148], rax
0x14003dfdc  mov     eax, [rbx+280h]
0x14003dfe2  mov     [rsp+1C0h+var_154], eax
0x14003dfe6  mov     eax, [rbx+284h]
0x14003dfec  movups  [rbp+0C0h+var_120], xmm0
0x14003dff0  mov     dword ptr [rsp+1C0h+var_150+4], eax
0x14003dff4  movups  xmm0, xmmword ptr [rbx+150h]
0x14003dffb  mov     eax, [rbx+288h]
0x14003e001  mov     dword ptr [rsp+1C0h+var_150], eax
0x14003e005  movups  [rbp+0C0h+var_110], xmm1
0x14003e009  movups  [rbp+0C0h+var_100], xmm0
0x14003e00d  call    ?GrepIsLockOwnedByCurrentThread@@YA_NQEAUHSEMAPHORE__@@@Z; GrepIsLockOwnedByCurrentThread(HSEMAPHORE__ * const)
0x14003e012  xor     al, dil
0x14003e015  lea     rcx, [rbp+0C0h+var_E8]; this
0x14003e019  mov     dl, al; bool
0x14003e01b  call    ??0NEEDDYNAMICMODECHANGESHARELOCK@@QEAA@_N@Z; NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(bool)
0x14003e020  mov     r15, [rbx+30h]
0x14003e024  mov     [rsp+1C0h+var_168], r15
0x14003e029  test    r15, r15
0x14003e02c  jz      short loc_14003E043
0x14003e02e  test    dword ptr [rbx+90h], 400000h
0x14003e038  jz      short loc_14003E043
0x14003e03a  mov     eax, [r15+28h]
0x14003e03e  test    dil, al
0x14003e041  jnz     short loc_14003E04C
0x14003e043  lea     rcx, [rbp+0C0h+var_E8]; this
0x14003e047  call    ?vUnlockIfNeeded@NEEDDYNAMICMODECHANGESHARELOCK@@QEAAXXZ; NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded(void)
0x14003e04c  lea     rcx, [rbp+0C0h+var_D0]; this
0x14003e050  mov     [rbp+0C0h+var_128], 0
0x14003e058  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x14003e05d  test    dword ptr [rbx+90h], 400000h
0x14003e067  jz      short loc_14003E08A
0x14003e069  test    r15, r15
0x14003e06c  jz      short loc_14003E08A
0x14003e06e  lea     rdx, [rsp+1C0h+var_168]; struct PDEVOBJ *
0x14003e073  lea     rcx, [rbp+0C0h+var_128]; this
0x14003e077  call    ?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z; NEEDGRELOCK::vLock(PDEVOBJ &)
0x14003e07c  lea     rdx, [rsp+1C0h+var_168]; struct PDEVOBJ *
0x14003e081  lea     rcx, [rbp+0C0h+var_D0]; this
0x14003e085  call    ?vLock@DEVLOCKOBJ@@QEAAXAEAVPDEVOBJ@@@Z; DEVLOCKOBJ::vLock(PDEVOBJ &)
0x14003e08a  mov     rax, [rbx]
0x14003e08d  mov     edx, 5
0x14003e092  mov     rcx, rax
0x14003e095  mov     [rbp+0C0h+var_130], rax
0x14003e099  call    GreGetObjectOwner
0x14003e09e  xor     r15d, r15d
0x14003e0a1  mov     dword ptr [rsp+1C0h+var_168], eax
0x14003e0a5  mov     dword ptr [rsp+1C0h+BaseAddress], r15d
0x14003e0aa  cmp     [rbp+0C0h+arg_18], r15d
0x14003e0b1  jnz     loc_14003E1AD
0x14003e0b7  mov     r15, [rbp+0C0h+var_130]
0x14003e0bb  lea     rax, [rsp+1C0h+BaseAddress]
0x14003e0c0  mov     qword ptr [rsp+1C0h+var_198+8], rax; __int64
0x14003e0c5  mov     r9d, edi
0x14003e0c8  mov     eax, [rsi+0C28h]
0x14003e0ce  xor     r8d, r8d
0x14003e0d1  mov     byte ptr [rsp+1C0h+var_198], 5; char
0x14003e0d6  mov     rdx, r15
0x14003e0d9  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x14003e0dc  mov     [rsp+1C0h+var_1A0], eax; int
0x14003e0e0  call    HmgRemoveObject
0x14003e0e5  test    rax, rax
0x14003e0e8  jnz     loc_14003E1A8
0x14003e0ee  cmp     [rbp+0C0h+arg_10], edi
0x14003e0f4  jnz     short loc_14003E123
0x14003e0f6  lea     rax, [rsp+1C0h+BaseAddress]
0x14003e0fb  mov     r9d, edi
0x14003e0fe  mov     qword ptr [rsp+1C0h+var_198+8], rax
0x14003e103  xor     r8d, r8d
0x14003e106  mov     byte ptr [rsp+1C0h+var_198], 5
0x14003e10b  mov     rdx, r15
0x14003e10e  mov     rcx, rsi
0x14003e111  mov     [rsp+1C0h+var_1A0], edi
0x14003e115  call    ?HmgRemoveObjectImpl@@YAPEAXAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@JJW4HandleLockOptions@@EPEAK@Z; HmgRemoveObjectImpl(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,long,long,HandleLockOptions,uchar,ulong *)
0x14003e11a  test    rax, rax
0x14003e11d  jnz     loc_14003E1A8
0x14003e123  cmp     dword ptr [rsp+1C0h+BaseAddress], edi
0x14003e127  jz      short loc_14003E182
0x14003e129  cmp     qword ptr [rbx+0C0h], 0
0x14003e131  jnz     short loc_14003E155
0x14003e133  mov     rcx, rbx; this
0x14003e136  call    ?bStockSurface@SURFACE@@QEAAHXZ; SURFACE::bStockSurface(void)
0x14003e13b  test    eax, eax
0x14003e13d  jnz     short loc_14003E155
0x14003e13f  bt      dword ptr [rbx+90h], 0Bh
0x14003e147  jb      short loc_14003E155
0x14003e149  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x14003e14e  xor     edi, edi
0x14003e150  jmp     loc_14003E5B5
0x14003e155  mov     eax, [rbx+90h]
0x14003e15b  bt      eax, 0Bh
0x14003e15f  jb      short loc_14003E16D
0x14003e161  bts     eax, 18h
0x14003e165  mov     [rbx+90h], eax
0x14003e16b  jmp     short loc_14003E18C
0x14003e16d  cmp     dword ptr [rbx+160h], 0
0x14003e174  jnz     short loc_14003E18C
0x14003e176  mov     [rbx+160h], edi
0x14003e17c  lock add [rsi+64h], edi
0x14003e180  jmp     short loc_14003E18C
0x14003e182  bt      dword ptr [rbx+90h], 0Bh
0x14003e18a  jnb     short loc_14003E19C
0x14003e18c  mov     rdx, rbx
0x14003e18f  mov     rcx, rsi
0x14003e192  call    HmgDecrementShareReferenceCount
0x14003e197  jmp     loc_14003E5B5
0x14003e19c  mov     ecx, 0AAh; iError
0x14003e1a1  call    EngSetLastError
0x14003e1a6  jmp     short loc_14003E14E
0x14003e1a8  mov     r15d, dword ptr [rsp+1C0h+BaseAddress]
0x14003e1ad  call    IsSURFMEMMappingEnabled
0x14003e1b2  test    eax, eax
0x14003e1b4  jz      short loc_14003E1C1
0x14003e1b6  mov     dl, dil; bool
0x14003e1b9  mov     rcx, rbx; this
0x14003e1bc  call    ?UnmapUserVAFromKernel@SURFACE@@QEAAX_N@Z; SURFACE::UnmapUserVAFromKernel(bool)
0x14003e1c1  cmp     [rsp+1C0h+var_158], 0
0x14003e1c6  mov     rax, [rbx+48h]
0x14003e1ca  mov     [rsp+1C0h+BaseAddress], rax
0x14003e1cf  jz      short loc_14003E1D5
0x14003e1d1  lock dec dword ptr [rsi+64h]
0x14003e1d5  test    dword ptr [rbx+90h], 40000h
0x14003e1df  jz      short loc_14003E1F0
0x14003e1e1  cmp     qword ptr [rbx+250h], 0
0x14003e1e9  jz      short loc_14003E1F0
0x14003e1eb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003e1f0  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003e1f7  nop     dword ptr [rax+rax+00h]
0x14003e1fc  mov     rcx, [rax+18h]
0x14003e200  mov     rax, [rcx+800h]
0x14003e207  test    rax, rax
0x14003e20a  jz      short loc_14003E239
0x14003e20c  call    _guard_dispatch_icall
0x14003e211  test    eax, eax
0x14003e213  js      short loc_14003E239
0x14003e215  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003e21c  nop     dword ptr [rax+rax+00h]
0x14003e221  mov     rcx, [rax+18h]
0x14003e225  mov     rax, [rcx+808h]
0x14003e22c  test    rax, rax
0x14003e22f  jz      short loc_14003E239
0x14003e231  mov     rcx, rbx
0x14003e234  call    _guard_dispatch_icall
0x14003e239  mov     rcx, rbx; this
0x14003e23c  call    ?vDeleteDriverRealization@SURFACE@@QEAAXXZ; SURFACE::vDeleteDriverRealization(void)
0x14003e241  test    r12, r12
0x14003e244  jz      short loc_14003E275
0x14003e246  call    cs:__imp_PsGetCurrentProcessId
0x14003e24d  nop     dword ptr [rax+rax+00h]
0x14003e252  and     eax, 0FFFFFFFCh
0x14003e255  cmp     [rbx+0F0h], eax
0x14003e25b  jnz     loc_14003E512
0x14003e261  mov     rcx, r12; SecureHandle
0x14003e264  call    cs:__imp_MmUnsecureVirtualMemory
0x14003e26b  nop     dword ptr [rax+rax+00h]
0x14003e270  jmp     loc_14003E512
0x14003e275  cmp     dword ptr [rsp+1C0h+var_178+4], 0
0x14003e27a  jz      short loc_14003E2B1
0x14003e27c  xor     r13d, r13d
0x14003e27f  cmp     [rsp+1C0h+BaseAddress], r13
0x14003e284  jz      loc_14003E515
0x14003e28a  xor     eax, eax
0x14003e28c  mov     qword ptr [rbp+0C0h+var_120], r13
0x14003e290  lea     rcx, [rbp+0C0h+var_120]; this
0x14003e294  mov     qword ptr [rbp+0C0h+var_120+8], rax
0x14003e298  mov     qword ptr [rbp+0C0h+var_110], r14
0x14003e29c  mov     qword ptr [rbp+0C0h+var_110+8], r13
0x14003e2a0  mov     dword ptr [rbp+0C0h+var_100], 3
0x14003e2a7  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14003e2ac  jmp     loc_14003E515
0x14003e2b1  test    r13, r13
0x14003e2b4  jz      short loc_14003E332
0x14003e2b6  call    cs:__imp_PsGetCurrentProcessId
0x14003e2bd  nop     dword ptr [rax+rax+00h]
0x14003e2c2  and     eax, 0FFFFFFFCh
0x14003e2c5  cmp     [rbx+0F0h], eax
0x14003e2cb  jnz     loc_14003E512
0x14003e2d1  mov     rcx, r13; SecureHandle
0x14003e2d4  call    cs:__imp_MmUnsecureVirtualMemory
0x14003e2db  nop     dword ptr [rax+rax+00h]
0x14003e2e0  xor     r13d, r13d
0x14003e2e3  cmp     [rsp+1C0h+BaseAddress], r13
0x14003e2e8  jz      loc_14003E515
0x14003e2ee  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003e2f2  cmp     [rbp+0C0h+var_138], r13
0x14003e2f6  jz      short loc_14003E30C
0x14003e2f8  mov     rdx, r14; BaseAddress
0x14003e2fb  call    cs:__imp_ZwUnmapViewOfSection
0x14003e302  nop     dword ptr [rax+rax+00h]
0x14003e307  jmp     loc_14003E515
0x14003e30c  mov     r9d, 8000h; FreeType
0x14003e312  mov     [rsp+1C0h+RegionSize], r13
0x14003e317  lea     r8, [rsp+1C0h+RegionSize]; RegionSize
0x14003e31c  lea     rdx, [rsp+1C0h+BaseAddress]; BaseAddress
0x14003e321  call    cs:__imp_ZwFreeVirtualMemory
0x14003e328  nop     dword ptr [rax+rax+00h]
0x14003e32d  jmp     loc_14003E515
0x14003e332  movzx   eax, word ptr [rsp+1C0h+var_178]
0x14003e337  test    al, 8
0x14003e339  jz      loc_14003E459
0x14003e33f  test    al, al
0x14003e341  jns     loc_14003E44A
0x14003e347  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14003e34c  mov     r14, [rsp+1C0h+var_148]
0x14003e351  xor     r13d, r13d
0x14003e354  mov     r12d, [rsp+1C0h+var_154]
0x14003e359  mov     rsi, rax
0x14003e35c  test    r12d, r12d
0x14003e35f  mov     qword ptr [rbp+0C0h+var_120], r13
0x14003e363  mov     rcx, r14
0x14003e366  mov     qword ptr [rbp+0C0h+var_110+8], r13
0x14003e36a  cmovnz  rcx, [rsp+1C0h+BaseAddress]
0x14003e370  xor     eax, eax
0x14003e372  mov     qword ptr [rbp+0C0h+var_110], rcx
0x14003e376  lea     rcx, [rbp+0C0h+var_120]; this
0x14003e37a  mov     qword ptr [rbp+0C0h+var_120+8], rax
0x14003e37e  mov     dword ptr [rbp+0C0h+var_100], edi
0x14003e381  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14003e386  test    rsi, rsi
0x14003e389  jz      short loc_14003E39B
0x14003e38b  cmp     [rsi+40h], r13
0x14003e38f  jz      short loc_14003E39B
0x14003e391  mov     rcx, rsi
0x14003e394  call    UMPDGetThreadClientPID
0x14003e399  jmp     short loc_14003E3A6
0x14003e39b  cmp     dword ptr [rsp+1C0h+var_150], r13d
0x14003e3a0  jz      short loc_14003E3BB
0x14003e3a2  mov     eax, dword ptr [rsp+1C0h+var_150+4]
0x14003e3a6  mov     rdx, [rsp+1C0h+BaseAddress]
0x14003e3ab  test    r12d, r12d
0x14003e3ae  mov     ecx, eax; unsigned int
0x14003e3b0  cmovnz  rdx, r14; void *
0x14003e3b4  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x14003e3b9  jmp     short loc_14003E409
0x14003e3bb  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003e3c2  nop     dword ptr [rax+rax+00h]
0x14003e3c7  mov     rcx, [rax+18h]
0x14003e3cb  mov     rax, [rcx+820h]
0x14003e3d2  test    rax, rax
0x14003e3d5  jz      short loc_14003E409
0x14003e3d7  call    _guard_dispatch_icall
0x14003e3dc  test    eax, eax
0x14003e3de  js      short loc_14003E409
  ... truncated ...
```
