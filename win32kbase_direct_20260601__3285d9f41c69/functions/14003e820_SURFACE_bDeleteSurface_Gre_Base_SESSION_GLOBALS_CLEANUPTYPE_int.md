# SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)

- ea: `0x14003e820`
- end: `0x14003ef33`
- name: `?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z`
- size: `1811`
- prototype: ``
- caller_count: `8`
- callee_count: `35`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a450`
- `0x14002ebe8`
- `0x14003dac0`
- `0x14003de9c`
- `0x14003e354`
- `0x14003ef3c`
- `0x14016e630`
- `0x1401e6758`

## callees

- `0x14000f718`
- `0x140012c58`
- `0x14001cf88`
- `0x140020910`
- `0x140024cc0`
- `0x140024fc0`
- `0x1400262e0`
- `0x140027424`
- `0x140028590`
- `0x140028a70`
- `0x14002afa0`
- `0x14002b044`
- `0x1400340a0`
- `0x14003dd50`
- `0x14003e820`
- `0x140041870`
- `0x140042060`
- `0x14004b430`
- `0x1400640e8`
- `0x1400a5510`
- `0x1400f0fb8`
- `0x1400f1640`
- `0x14010c0d4`
- `0x14010e070`
- `0x140110520`
- `0x140116914`
- `0x140145acc`
- `0x140154258`
- `0x1401552a0`
- `0x14016e490`
- `0x1401b6d6c`
- `0x1401e1fec`
- `0x1401e21d0`
- `0x1401e2410`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14003eb8b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003ebfb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003eb8b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003ebfb`
- `ntoskrnl!PsGetProcessId` at `0x14003edfd`
- `ntoskrnl!PsGetProcessId` at `0x14003edfd`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14003ec40`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14003ec40`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14003ec66`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14003ec66`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003eba9`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003ec19`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003eba9`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14003ec19`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eb35`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eb5a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ed00`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ed2a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ee9b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eec0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eb35`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eb5a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ed00`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ed2a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003ee9b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003eec0`

## pseudocode

```c
__int64 __fastcall SURFACE::bDeleteSurface(__int64 *a1, __int64 *a2, int a3, int a4)
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
  __int64 v18; // r15
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int (*v22)(void); // rax
  void (__fastcall *v23)(__int64 *); // rax
  struct _GRETHREAD *CurrentThread; // rax
  void *v25; // r14
  int v26; // r12d
  struct _GRETHREAD *v27; // rsi
  PVOID v28; // rcx
  unsigned int v29; // eax
  PVOID v30; // rdx
  int (*v31)(void); // rax
  PVOID v32; // rsi
  void (__fastcall *v33)(PVOID); // rax
  PEPROCESS *v34; // r8
  __int64 *v35; // rax
  __int64 *v36; // rcx
  __int64 **v37; // rdx
  PVOID v38; // rsi
  unsigned int ProcessId; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdx
  __int64 v44; // rcx
  int (__fastcall *v45)(__int64, __int64); // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  void (__fastcall *v48)(__int64); // rax
  int v50; // [rsp+30h] [rbp-D8h]
  PVOID BaseAddress; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v52; // [rsp+50h] [rbp-B8h]
  int v53; // [rsp+54h] [rbp-B4h]
  ULONG_PTR v54; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A8h] BYREF
  ULONG_PTR RegionSize; // [rsp+68h] [rbp-A0h] BYREF
  int v57; // [rsp+70h] [rbp-98h]
  int v58; // [rsp+74h] [rbp-94h]
  int v59; // [rsp+78h] [rbp-90h]
  unsigned int v60; // [rsp+7Ch] [rbp-8Ch]
  void *v61; // [rsp+80h] [rbp-88h] BYREF
  __int64 v62; // [rsp+88h] [rbp-80h] BYREF
  __int64 v63; // [rsp+90h] [rbp-78h]
  __int64 v64; // [rsp+98h] [rbp-70h]
  __int64 v65; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v66; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v67; // [rsp+B8h] [rbp-50h]
  __int128 v68; // [rsp+C8h] [rbp-40h]
  __int64 v69; // [rsp+D8h] [rbp-30h]
  _BYTE v70[24]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v71[224]; // [rsp+F8h] [rbp-10h] BYREF

  v6 = 1;
  if ( !SURFACE::bIsDefault((SURFACE *)a1) && a1 )
  {
    if ( *((_WORD *)a1 + 50) )
    {
      v8 = 0;
      v53 = 0;
      v10 = 0;
      v63 = 0;
      v9 = 0;
    }
    else
    {
      v7 = a1[9];
      v8 = (void *)a1[30];
      v9 = (void *)a1[34];
      v63 = a1[29];
      v53 = *((_DWORD *)a1 + 66);
      v10 = (void *)(v7 - (unsigned __int16)*((_DWORD *)a1 + 65));
    }
    v11 = *((_OWORD *)a1 + 20);
    v12 = *a2;
    v13 = *((_OWORD *)a1 + 21);
    v62 = a1[22];
    v69 = a1[23];
    v52 = *((_WORD *)a1 + 51);
    RegionSize = a1[37];
    v57 = *((_DWORD *)a1 + 92);
    v54 = a1[79];
    v61 = (void *)a1[80];
    v58 = *((_DWORD *)a1 + 164);
    v14 = *((_DWORD *)a1 + 165);
    v66 = v11;
    v60 = v14;
    v15 = *((_OWORD *)a1 + 22);
    v59 = *((_DWORD *)a1 + 166);
    v67 = v13;
    v68 = v15;
    IsLockOwnedByCurrentThread = GrepIsLockOwnedByCurrentThread((HSEMAPHORE)(v12 + 624));
    NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(
      (NEEDDYNAMICMODECHANGESHARELOCK *)v70,
      !IsLockOwnedByCurrentThread);
    v17 = a1[6];
    v55 = v17;
    if ( !v17 || (a1[20] & 0x400000) == 0 || (*(_DWORD *)(v17 + 40) & 1) == 0 )
      NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v70);
    v65 = 0;
    DEVLOCKOBJ::DEVLOCKOBJ(v71, 2);
    if ( (a1[20] & 0x400000) != 0 && v17 )
    {
      NEEDGRELOCK::vLock((NEEDGRELOCK *)&v65, (struct PDEVOBJ *)&v55);
      DEVLOCKOBJ::vLock((DEVLOCKOBJ *)v71, (struct PDEVOBJ *)&v55);
    }
    v64 = *a1;
    LODWORD(v55) = GreGetObjectOwner(v64, 5);
    LODWORD(BaseAddress) = 0;
    if ( !a4 )
    {
      v18 = v64;
      if ( !HmgRemoveObject((struct Gre::Base::SESSION_GLOBALS *)a2, *((_DWORD *)a2 + 778), 5, (__int64)&BaseAddress) )
      {
        if ( a3 != 1 || (LOBYTE(v50) = 5, !HmgRemoveObjectImpl(a2, v18, 0, 1, 1, v50, &BaseAddress)) )
        {
          if ( (_DWORD)BaseAddress == 1 )
          {
            if ( !_bittest((const signed __int32 *)a1 + 40, 0xBu) )
            {
              EngSetLastError(0xAAu);
              goto LABEL_22;
            }
          }
          else
          {
            if ( !a1[26]
              && !(unsigned int)SURFACE::bStockSurface((SURFACE *)a1)
              && !_bittest((const signed __int32 *)a1 + 40, 0xBu) )
            {
              Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline();
LABEL_22:
              v6 = 0;
LABEL_97:
              DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v71);
              NEEDGRELOCK::vUnlock((NEEDGRELOCK *)&v65);
              NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v70);
              return v6;
            }
            v19 = *((_DWORD *)a1 + 40);
            if ( (v19 & 0x800) != 0 )
            {
              if ( !*((_DWORD *)a1 + 92) )
              {
                *((_DWORD *)a1 + 92) = 1;
                _InterlockedAdd((volatile signed __int32 *)a2 + 25, 1u);
              }
            }
            else
            {
              *((_DWORD *)a1 + 40) = v19 | 0x1000000;
            }
          }
          HmgDecrementShareReferenceCount(a2, a1);
          goto LABEL_97;
        }
      }
    }
    if ( (unsigned int)IsSURFMEMMappingEnabled() )
      SURFACE::UnmapUserVAFromKernel((SURFACE *)a1, 1);
    BaseAddress = (PVOID)a1[9];
    if ( v57 )
      _InterlockedDecrement((volatile signed __int32 *)a2 + 25);
    if ( (a1[20] & 0x40000) != 0 && a1[76] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20);
    v22 = *(int (**)(void))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24) + 2048LL);
    if ( v22 )
    {
      if ( v22() >= 0 )
      {
        v23 = *(void (__fastcall **)(__int64 *))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24)
                                               + 2056LL);
        if ( v23 )
          v23(a1);
      }
    }
    SURFACE::vDeleteDriverRealization((SURFACE *)a1);
    if ( v9 )
    {
      if ( *((_DWORD *)a1 + 64) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
        MmUnsecureVirtualMemory(v9);
      goto LABEL_88;
    }
    if ( v53 )
    {
      if ( BaseAddress )
      {
        v66 = 0u;
        v67 = (unsigned __int64)v10;
        LODWORD(v68) = 3;
        Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v66);
      }
      goto LABEL_88;
    }
    if ( v8 )
    {
      if ( *((_DWORD *)a1 + 64) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
      {
        MmUnsecureVirtualMemory(v8);
        if ( BaseAddress )
        {
          if ( v63 )
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
      goto LABEL_88;
    }
    if ( (v52 & 8) == 0 )
    {
      if ( (v52 & 0x800) != 0 )
      {
        SEMOBJ<36>::SEMOBJ<36>(&v61, a2);
        v34 = (PEPROCESS *)a1[39];
        if ( v34 )
        {
          v35 = a1 + 72;
          v36 = (__int64 *)a1[72];
          if ( v36 != a1 + 72 )
          {
            if ( (__int64 *)v36[1] != v35 || (v37 = (__int64 **)a1[73], *v37 != v35) )
              __fastfail(3u);
            *v37 = v36;
            v36[1] = (__int64)v37;
          }
          v38 = BaseAddress;
          if ( BaseAddress && RegionSize )
          {
            ProcessId = (unsigned int)PsGetProcessId(*v34);
            Gre::MapViewOfSectionObj::Unmap(ProcessId, v38);
          }
        }
        W32PIDLOCK::vCleanUp((W32PIDLOCK *)&v66);
        if ( RegionSize )
        {
          v54 = RegionSize;
          Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v54);
        }
        SEMOBJ<36>::vUnlock(&v61);
      }
      else if ( (v52 & 0x10) != 0 )
      {
        vFreeKernelSection(BaseAddress);
      }
      goto LABEL_88;
    }
    if ( (v52 & 0x80u) == 0 )
    {
      EngTryFreeUserMem(BaseAddress);
LABEL_88:
      if ( (*((_DWORD *)a1 + 41) & 0x1000) != 0 )
        GrepCaptureLiveMemoryDump(400, 4, v64);
      SURFACE_Free(a1);
      v42 = v69;
      if ( v69 )
      {
        v44 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v41, v40) + 24);
        v45 = *(int (__fastcall **)(__int64, __int64))(v44 + 2096);
        if ( v45 )
        {
          if ( v45(v44, v43) >= 0 )
          {
            v48 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v47, v46) + 24) + 2104LL);
            if ( v48 )
              v48(v42);
          }
        }
      }
      if ( v62 )
        XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v62);
      goto LABEL_97;
    }
    CurrentThread = GreGetCurrentThread();
    v25 = v61;
    v26 = v58;
    v27 = CurrentThread;
    *(_QWORD *)&v66 = 0;
    v28 = v61;
    *((_QWORD *)&v67 + 1) = 0;
    if ( v58 )
      v28 = BaseAddress;
    *(_QWORD *)&v67 = v28;
    *((_QWORD *)&v66 + 1) = 0;
    LODWORD(v68) = 1;
    Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v66);
    if ( v27 && *((_QWORD *)v27 + 8) )
    {
      v29 = UMPDGetThreadClientPID(v27);
    }
    else
    {
      if ( !v59 )
      {
        v31 = *(int (**)(void))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24) + 2080LL);
        if ( v31 )
        {
          if ( v31() >= 0 )
          {
            v32 = BaseAddress;
            v33 = *(void (__fastcall **)(PVOID))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24)
                                               + 2088LL);
            if ( v33 )
              v33(v32);
          }
        }
        goto LABEL_69;
      }
      v29 = v60;
    }
    v30 = BaseAddress;
    if ( v26 )
      v30 = v25;
    Gre::MapViewOfSectionObj::Unmap(v29, v30);
LABEL_69:
    if ( v54 )
      Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v54);
    else
      GrepCaptureLiveMemoryDump(400, 68, 2);
    goto LABEL_88;
  }
  return v6;
}

```

## disassembly

```asm
0x14003e820  mov     rax, rsp
0x14003e823  mov     [rax+8], rbx
0x14003e827  mov     [rax+20h], r9d
0x14003e82b  mov     [rax+18h], r8d
0x14003e82f  push    rbp
0x14003e830  push    rsi
0x14003e831  push    rdi
0x14003e832  push    r12
0x14003e834  push    r13
0x14003e836  push    r14
0x14003e838  push    r15
0x14003e83a  lea     rbp, [rax-0D8h]
0x14003e841  sub     rsp, 1A0h
0x14003e848  mov     rsi, rdx
0x14003e84b  mov     rbx, rcx
0x14003e84e  mov     edi, 1
0x14003e853  call    ?bIsDefault@SURFACE@@QEBA_NXZ; SURFACE::bIsDefault(void)
0x14003e858  xor     ecx, ecx
0x14003e85a  test    al, al
0x14003e85c  jnz     loc_14003EF15
0x14003e862  test    rbx, rbx
0x14003e865  jz      loc_14003EF15
0x14003e86b  cmp     [rbx+64h], cx
0x14003e86f  jnz     short loc_14003E8A6
0x14003e871  mov     rax, [rbx+0E8h]
0x14003e878  mov     r14, [rbx+48h]
0x14003e87c  mov     r13, [rbx+0F0h]
0x14003e883  mov     r12, [rbx+110h]
0x14003e88a  mov     [rbp+0D0h+var_148], rax
0x14003e88e  mov     eax, [rbx+108h]
0x14003e894  mov     dword ptr [rsp+1D0h+var_188+4], eax
0x14003e898  mov     eax, [rbx+104h]
0x14003e89e  movzx   ecx, ax
0x14003e8a1  sub     r14, rcx
0x14003e8a4  jmp     short loc_14003E8B7
0x14003e8a6  mov     r13, rcx
0x14003e8a9  mov     dword ptr [rsp+1D0h+var_188+4], ecx
0x14003e8ad  mov     r14, rcx
0x14003e8b0  mov     [rbp+0D0h+var_148], rcx
0x14003e8b4  mov     r12, rcx
0x14003e8b7  mov     rax, [rbx+0B0h]
0x14003e8be  movups  xmm0, xmmword ptr [rbx+140h]
0x14003e8c5  mov     rcx, [rsi]
0x14003e8c8  movups  xmm1, xmmword ptr [rbx+150h]
0x14003e8cf  mov     [rbp+0D0h+var_150], rax
0x14003e8d3  add     rcx, 270h; HSEMAPHORE
0x14003e8da  mov     rax, [rbx+0B8h]
0x14003e8e1  mov     [rbp+0D0h+var_100], rax
0x14003e8e5  movzx   eax, word ptr [rbx+66h]
0x14003e8e9  mov     word ptr [rsp+1D0h+var_188], ax
0x14003e8ee  mov     rax, [rbx+128h]
0x14003e8f5  mov     [rsp+1D0h+RegionSize], rax
0x14003e8fa  mov     eax, [rbx+170h]
0x14003e900  mov     [rsp+1D0h+var_168], eax
0x14003e904  mov     rax, [rbx+278h]
0x14003e90b  mov     [rsp+1D0h+var_180], rax
0x14003e910  mov     rax, [rbx+280h]
0x14003e917  mov     [rsp+1D0h+var_158], rax
0x14003e91c  mov     eax, [rbx+290h]
0x14003e922  mov     [rsp+1D0h+var_164], eax
0x14003e926  mov     eax, [rbx+294h]
0x14003e92c  movups  [rbp+0D0h+var_130], xmm0
0x14003e930  mov     dword ptr [rsp+1D0h+var_160+4], eax
0x14003e934  movups  xmm0, xmmword ptr [rbx+160h]
0x14003e93b  mov     eax, [rbx+298h]
0x14003e941  mov     dword ptr [rsp+1D0h+var_160], eax
0x14003e945  movups  [rbp+0D0h+var_120], xmm1
0x14003e949  movups  [rbp+0D0h+var_110], xmm0
0x14003e94d  call    ?GrepIsLockOwnedByCurrentThread@@YA_NQEAUHSEMAPHORE__@@@Z; GrepIsLockOwnedByCurrentThread(HSEMAPHORE__ * const)
0x14003e952  xor     al, dil
0x14003e955  lea     rcx, [rbp+0D0h+var_F8]; this
0x14003e959  mov     dl, al; bool
0x14003e95b  call    ??0NEEDDYNAMICMODECHANGESHARELOCK@@QEAA@_N@Z; NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(bool)
0x14003e960  mov     r15, [rbx+30h]
0x14003e964  mov     [rsp+1D0h+var_178], r15
0x14003e969  test    r15, r15
0x14003e96c  jz      short loc_14003E983
0x14003e96e  test    dword ptr [rbx+0A0h], 400000h
0x14003e978  jz      short loc_14003E983
0x14003e97a  mov     eax, [r15+28h]
0x14003e97e  test    dil, al
0x14003e981  jnz     short loc_14003E98C
0x14003e983  lea     rcx, [rbp+0D0h+var_F8]; this
0x14003e987  call    ?vUnlockIfNeeded@NEEDDYNAMICMODECHANGESHARELOCK@@QEAAXXZ; NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded(void)
0x14003e98c  mov     edx, 2
0x14003e991  mov     [rbp+0D0h+var_138], 0
0x14003e999  lea     rcx, [rbp+0D0h+var_E0]
0x14003e99d  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x14003e9a2  test    dword ptr [rbx+0A0h], 400000h
0x14003e9ac  jz      short loc_14003E9CF
0x14003e9ae  test    r15, r15
0x14003e9b1  jz      short loc_14003E9CF
0x14003e9b3  lea     rdx, [rsp+1D0h+var_178]; struct PDEVOBJ *
0x14003e9b8  lea     rcx, [rbp+0D0h+var_138]; this
0x14003e9bc  call    ?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z; NEEDGRELOCK::vLock(PDEVOBJ &)
0x14003e9c1  lea     rdx, [rsp+1D0h+var_178]; struct PDEVOBJ *
0x14003e9c6  lea     rcx, [rbp+0D0h+var_E0]; this
0x14003e9ca  call    ?vLock@DEVLOCKOBJ@@QEAAXAEAVPDEVOBJ@@@Z; DEVLOCKOBJ::vLock(PDEVOBJ &)
0x14003e9cf  mov     rax, [rbx]
0x14003e9d2  mov     edx, 5
0x14003e9d7  mov     rcx, rax
0x14003e9da  mov     [rbp+0D0h+var_140], rax
0x14003e9de  call    GreGetObjectOwner
0x14003e9e3  xor     r15d, r15d
0x14003e9e6  mov     dword ptr [rsp+1D0h+var_178], eax
0x14003e9ea  mov     dword ptr [rsp+1D0h+BaseAddress], r15d
0x14003e9ef  cmp     [rbp+0D0h+arg_18], r15d
0x14003e9f6  jnz     loc_14003EAF2
0x14003e9fc  mov     r15, [rbp+0D0h+var_140]
0x14003ea00  lea     rax, [rsp+1D0h+BaseAddress]
0x14003ea05  mov     qword ptr [rsp+1D0h+var_1A8+8], rax; __int64
0x14003ea0a  mov     r9d, edi
0x14003ea0d  mov     eax, [rsi+0C28h]
0x14003ea13  xor     r8d, r8d
0x14003ea16  mov     byte ptr [rsp+1D0h+var_1A8], 5; char
0x14003ea1b  mov     rdx, r15
0x14003ea1e  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x14003ea21  mov     [rsp+1D0h+var_1B0], eax; int
0x14003ea25  call    HmgRemoveObject
0x14003ea2a  test    rax, rax
0x14003ea2d  jnz     loc_14003EAED
0x14003ea33  cmp     [rbp+0D0h+arg_10], edi
0x14003ea39  jnz     short loc_14003EA68
0x14003ea3b  lea     rax, [rsp+1D0h+BaseAddress]
0x14003ea40  mov     r9d, edi
0x14003ea43  mov     qword ptr [rsp+1D0h+var_1A8+8], rax
0x14003ea48  xor     r8d, r8d
0x14003ea4b  mov     byte ptr [rsp+1D0h+var_1A8], 5
0x14003ea50  mov     rdx, r15
0x14003ea53  mov     rcx, rsi
0x14003ea56  mov     [rsp+1D0h+var_1B0], edi
0x14003ea5a  call    ?HmgRemoveObjectImpl@@YAPEAXAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@JJW4HandleLockOptions@@EPEAK@Z; HmgRemoveObjectImpl(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,long,long,HandleLockOptions,uchar,ulong *)
0x14003ea5f  test    rax, rax
0x14003ea62  jnz     loc_14003EAED
0x14003ea68  cmp     dword ptr [rsp+1D0h+BaseAddress], edi
0x14003ea6c  jz      short loc_14003EAC7
0x14003ea6e  cmp     qword ptr [rbx+0D0h], 0
0x14003ea76  jnz     short loc_14003EA9A
0x14003ea78  mov     rcx, rbx; this
0x14003ea7b  call    ?bStockSurface@SURFACE@@QEAAHXZ; SURFACE::bStockSurface(void)
0x14003ea80  test    eax, eax
0x14003ea82  jnz     short loc_14003EA9A
0x14003ea84  bt      dword ptr [rbx+0A0h], 0Bh
0x14003ea8c  jb      short loc_14003EA9A
0x14003ea8e  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x14003ea93  xor     edi, edi
0x14003ea95  jmp     loc_14003EEFA
0x14003ea9a  mov     eax, [rbx+0A0h]
0x14003eaa0  bt      eax, 0Bh
0x14003eaa4  jb      short loc_14003EAB2
0x14003eaa6  bts     eax, 18h
0x14003eaaa  mov     [rbx+0A0h], eax
0x14003eab0  jmp     short loc_14003EAD1
0x14003eab2  cmp     dword ptr [rbx+170h], 0
0x14003eab9  jnz     short loc_14003EAD1
0x14003eabb  mov     [rbx+170h], edi
0x14003eac1  lock add [rsi+64h], edi
0x14003eac5  jmp     short loc_14003EAD1
0x14003eac7  bt      dword ptr [rbx+0A0h], 0Bh
0x14003eacf  jnb     short loc_14003EAE1
0x14003ead1  mov     rdx, rbx
0x14003ead4  mov     rcx, rsi
0x14003ead7  call    HmgDecrementShareReferenceCount
0x14003eadc  jmp     loc_14003EEFA
0x14003eae1  mov     ecx, 0AAh; iError
0x14003eae6  call    EngSetLastError
0x14003eaeb  jmp     short loc_14003EA93
0x14003eaed  mov     r15d, dword ptr [rsp+1D0h+BaseAddress]
0x14003eaf2  call    IsSURFMEMMappingEnabled
0x14003eaf7  test    eax, eax
0x14003eaf9  jz      short loc_14003EB06
0x14003eafb  mov     dl, dil; bool
0x14003eafe  mov     rcx, rbx; this
0x14003eb01  call    ?UnmapUserVAFromKernel@SURFACE@@QEAAX_N@Z; SURFACE::UnmapUserVAFromKernel(bool)
0x14003eb06  cmp     [rsp+1D0h+var_168], 0
0x14003eb0b  mov     rax, [rbx+48h]
0x14003eb0f  mov     [rsp+1D0h+BaseAddress], rax
0x14003eb14  jz      short loc_14003EB1A
0x14003eb16  lock dec dword ptr [rsi+64h]
0x14003eb1a  test    dword ptr [rbx+0A0h], 40000h
0x14003eb24  jz      short loc_14003EB35
0x14003eb26  cmp     qword ptr [rbx+260h], 0
0x14003eb2e  jz      short loc_14003EB35
0x14003eb30  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003eb35  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003eb3c  nop     dword ptr [rax+rax+00h]
0x14003eb41  mov     rcx, [rax+18h]
0x14003eb45  mov     rax, [rcx+800h]
0x14003eb4c  test    rax, rax
0x14003eb4f  jz      short loc_14003EB7E
0x14003eb51  call    _guard_dispatch_icall
0x14003eb56  test    eax, eax
0x14003eb58  js      short loc_14003EB7E
0x14003eb5a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003eb61  nop     dword ptr [rax+rax+00h]
0x14003eb66  mov     rcx, [rax+18h]
0x14003eb6a  mov     rax, [rcx+808h]
0x14003eb71  test    rax, rax
0x14003eb74  jz      short loc_14003EB7E
0x14003eb76  mov     rcx, rbx
0x14003eb79  call    _guard_dispatch_icall
0x14003eb7e  mov     rcx, rbx; this
0x14003eb81  call    ?vDeleteDriverRealization@SURFACE@@QEAAXXZ; SURFACE::vDeleteDriverRealization(void)
0x14003eb86  test    r12, r12
0x14003eb89  jz      short loc_14003EBBA
0x14003eb8b  call    cs:__imp_PsGetCurrentProcessId
0x14003eb92  nop     dword ptr [rax+rax+00h]
0x14003eb97  and     eax, 0FFFFFFFCh
0x14003eb9a  cmp     [rbx+100h], eax
0x14003eba0  jnz     loc_14003EE57
0x14003eba6  mov     rcx, r12; SecureHandle
0x14003eba9  call    cs:__imp_MmUnsecureVirtualMemory
0x14003ebb0  nop     dword ptr [rax+rax+00h]
0x14003ebb5  jmp     loc_14003EE57
0x14003ebba  cmp     dword ptr [rsp+1D0h+var_188+4], 0
0x14003ebbf  jz      short loc_14003EBF6
0x14003ebc1  xor     r13d, r13d
0x14003ebc4  cmp     [rsp+1D0h+BaseAddress], r13
0x14003ebc9  jz      loc_14003EE5A
0x14003ebcf  xor     eax, eax
0x14003ebd1  mov     qword ptr [rbp+0D0h+var_130], r13
0x14003ebd5  lea     rcx, [rbp+0D0h+var_130]; this
0x14003ebd9  mov     qword ptr [rbp+0D0h+var_130+8], rax
0x14003ebdd  mov     qword ptr [rbp+0D0h+var_120], r14
0x14003ebe1  mov     qword ptr [rbp+0D0h+var_120+8], r13
0x14003ebe5  mov     dword ptr [rbp+0D0h+var_110], 3
0x14003ebec  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14003ebf1  jmp     loc_14003EE5A
0x14003ebf6  test    r13, r13
0x14003ebf9  jz      short loc_14003EC77
0x14003ebfb  call    cs:__imp_PsGetCurrentProcessId
0x14003ec02  nop     dword ptr [rax+rax+00h]
0x14003ec07  and     eax, 0FFFFFFFCh
0x14003ec0a  cmp     [rbx+100h], eax
0x14003ec10  jnz     loc_14003EE57
0x14003ec16  mov     rcx, r13; SecureHandle
0x14003ec19  call    cs:__imp_MmUnsecureVirtualMemory
0x14003ec20  nop     dword ptr [rax+rax+00h]
0x14003ec25  xor     r13d, r13d
0x14003ec28  cmp     [rsp+1D0h+BaseAddress], r13
0x14003ec2d  jz      loc_14003EE5A
0x14003ec33  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003ec37  cmp     [rbp+0D0h+var_148], r13
0x14003ec3b  jz      short loc_14003EC51
0x14003ec3d  mov     rdx, r14; BaseAddress
0x14003ec40  call    cs:__imp_ZwUnmapViewOfSection
0x14003ec47  nop     dword ptr [rax+rax+00h]
0x14003ec4c  jmp     loc_14003EE5A
0x14003ec51  mov     r9d, 8000h; FreeType
0x14003ec57  mov     [rsp+1D0h+RegionSize], r13
0x14003ec5c  lea     r8, [rsp+1D0h+RegionSize]; RegionSize
0x14003ec61  lea     rdx, [rsp+1D0h+BaseAddress]; BaseAddress
0x14003ec66  call    cs:__imp_ZwFreeVirtualMemory
0x14003ec6d  nop     dword ptr [rax+rax+00h]
0x14003ec72  jmp     loc_14003EE5A
0x14003ec77  movzx   eax, word ptr [rsp+1D0h+var_188]
0x14003ec7c  test    al, 8
0x14003ec7e  jz      loc_14003ED9E
0x14003ec84  test    al, al
0x14003ec86  jns     loc_14003ED8F
0x14003ec8c  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14003ec91  mov     r14, [rsp+1D0h+var_158]
0x14003ec96  xor     r13d, r13d
0x14003ec99  mov     r12d, [rsp+1D0h+var_164]
0x14003ec9e  mov     rsi, rax
0x14003eca1  test    r12d, r12d
0x14003eca4  mov     qword ptr [rbp+0D0h+var_130], r13
0x14003eca8  mov     rcx, r14
0x14003ecab  mov     qword ptr [rbp+0D0h+var_120+8], r13
0x14003ecaf  cmovnz  rcx, [rsp+1D0h+BaseAddress]
0x14003ecb5  xor     eax, eax
0x14003ecb7  mov     qword ptr [rbp+0D0h+var_120], rcx
0x14003ecbb  lea     rcx, [rbp+0D0h+var_130]; this
0x14003ecbf  mov     qword ptr [rbp+0D0h+var_130+8], rax
0x14003ecc3  mov     dword ptr [rbp+0D0h+var_110], edi
0x14003ecc6  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x14003eccb  test    rsi, rsi
0x14003ecce  jz      short loc_14003ECE0
0x14003ecd0  cmp     [rsi+40h], r13
0x14003ecd4  jz      short loc_14003ECE0
0x14003ecd6  mov     rcx, rsi
0x14003ecd9  call    UMPDGetThreadClientPID
0x14003ecde  jmp     short loc_14003ECEB
0x14003ece0  cmp     dword ptr [rsp+1D0h+var_160], r13d
0x14003ece5  jz      short loc_14003ED00
0x14003ece7  mov     eax, dword ptr [rsp+1D0h+var_160+4]
0x14003eceb  mov     rdx, [rsp+1D0h+BaseAddress]
0x14003ecf0  test    r12d, r12d
0x14003ecf3  mov     ecx, eax; unsigned int
0x14003ecf5  cmovnz  rdx, r14; void *
0x14003ecf9  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x14003ecfe  jmp     short loc_14003ED4E
0x14003ed00  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003ed07  nop     dword ptr [rax+rax+00h]
0x14003ed0c  mov     rcx, [rax+18h]
0x14003ed10  mov     rax, [rcx+820h]
0x14003ed17  test    rax, rax
0x14003ed1a  jz      short loc_14003ED4E
0x14003ed1c  call    _guard_dispatch_icall
0x14003ed21  test    eax, eax
  ... truncated ...
```
