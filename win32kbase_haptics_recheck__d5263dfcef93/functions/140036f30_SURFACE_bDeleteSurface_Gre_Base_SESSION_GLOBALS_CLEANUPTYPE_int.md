# SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)

- ea: `0x140036f30`
- end: `0x140037643`
- name: `?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z`
- size: `1811`
- prototype: ``
- caller_count: `8`
- callee_count: `35`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400112e0`
- `0x140025bf8`
- `0x140033530`
- `0x140036160`
- `0x14003653c`
- `0x1400369f4`
- `0x14003764c`
- `0x1401e6e78`

## callees

- `0x140006cf8`
- `0x140009ae8`
- `0x140013e18`
- `0x1400178f0`
- `0x14001bca0`
- `0x14001bfa0`
- `0x14001d2c0`
- `0x14001e404`
- `0x14001f570`
- `0x14001fa50`
- `0x140021f80`
- `0x140022024`
- `0x14002ae20`
- `0x1400363f0`
- `0x140036f30`
- `0x140039f30`
- `0x14003a720`
- `0x140042520`
- `0x140093b98`
- `0x1400af5f8`
- `0x1400b5ab0`
- `0x1400f3720`
- `0x14010ae6c`
- `0x14010ce00`
- `0x14010f2b0`
- `0x140116550`
- `0x14014661c`
- `0x140153938`
- `0x140154980`
- `0x14016dcf0`
- `0x1401b72cc`
- `0x1401e267c`
- `0x1401e2870`
- `0x1401e2b00`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14003729b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003730b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003729b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003730b`
- `ntoskrnl!PsGetProcessId` at `0x14003750d`
- `ntoskrnl!PsGetProcessId` at `0x14003750d`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x140037350`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x140037350`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140037376`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140037376`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400372b9`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140037329`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400372b9`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140037329`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037245`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003726a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037410`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003743a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400375ab`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400375d0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037245`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003726a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140037410`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003743a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400375ab`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400375d0`

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
  unsigned int v18; // r15d
  __int64 v19; // r15
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  int (*v23)(void); // rax
  void (__fastcall *v24)(__int64 *); // rax
  struct _GRETHREAD *CurrentThread; // rax
  void *v26; // r14
  int v27; // r12d
  struct _GRETHREAD *v28; // rsi
  PVOID v29; // rcx
  unsigned int v30; // eax
  PVOID v31; // rdx
  int (*v32)(void); // rax
  PVOID v33; // rsi
  void (__fastcall *v34)(PVOID); // rax
  PEPROCESS *v35; // r8
  __int64 *v36; // rax
  __int64 *v37; // rcx
  __int64 **v38; // rdx
  PVOID v39; // rsi
  unsigned int ProcessId; // eax
  __int64 v41; // rbx
  int (*v42)(void); // rax
  void (__fastcall *v43)(__int64); // rax
  int v45; // [rsp+30h] [rbp-D8h]
  PVOID BaseAddress; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v47; // [rsp+50h] [rbp-B8h]
  int v48; // [rsp+54h] [rbp-B4h]
  ULONG_PTR v49; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A8h] BYREF
  ULONG_PTR RegionSize; // [rsp+68h] [rbp-A0h] BYREF
  int v52; // [rsp+70h] [rbp-98h]
  int v53; // [rsp+74h] [rbp-94h]
  int v54; // [rsp+78h] [rbp-90h]
  unsigned int v55; // [rsp+7Ch] [rbp-8Ch]
  void *v56; // [rsp+80h] [rbp-88h] BYREF
  __int64 v57; // [rsp+88h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-78h]
  __int64 v59; // [rsp+98h] [rbp-70h]
  __int64 v60; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v61; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v62; // [rsp+B8h] [rbp-50h]
  __int128 v63; // [rsp+C8h] [rbp-40h]
  __int64 v64; // [rsp+D8h] [rbp-30h]
  _BYTE v65[24]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v66[224]; // [rsp+F8h] [rbp-10h] BYREF

  v6 = 1;
  if ( !SURFACE::bIsDefault((SURFACE *)a1) && a1 )
  {
    if ( *((_WORD *)a1 + 50) )
    {
      v8 = 0;
      v48 = 0;
      v10 = 0;
      v58 = 0;
      v9 = 0;
    }
    else
    {
      v7 = a1[9];
      v8 = (void *)a1[30];
      v9 = (void *)a1[34];
      v58 = a1[29];
      v48 = *((_DWORD *)a1 + 66);
      v10 = (void *)(v7 - (unsigned __int16)*((_DWORD *)a1 + 65));
    }
    v11 = *((_OWORD *)a1 + 20);
    v12 = *a2;
    v13 = *((_OWORD *)a1 + 21);
    v57 = a1[22];
    v64 = a1[23];
    v47 = *((_WORD *)a1 + 51);
    RegionSize = a1[37];
    v52 = *((_DWORD *)a1 + 92);
    v49 = a1[79];
    v56 = (void *)a1[80];
    v53 = *((_DWORD *)a1 + 164);
    v14 = *((_DWORD *)a1 + 165);
    v61 = v11;
    v55 = v14;
    v15 = *((_OWORD *)a1 + 22);
    v54 = *((_DWORD *)a1 + 166);
    v62 = v13;
    v63 = v15;
    IsLockOwnedByCurrentThread = GrepIsLockOwnedByCurrentThread((HSEMAPHORE)(v12 + 624));
    NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(
      (NEEDDYNAMICMODECHANGESHARELOCK *)v65,
      !IsLockOwnedByCurrentThread);
    v17 = a1[6];
    v50 = v17;
    if ( !v17 || (a1[20] & 0x400000) == 0 || (*(_DWORD *)(v17 + 40) & 1) == 0 )
      NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v65);
    v60 = 0;
    DEVLOCKOBJ::DEVLOCKOBJ(v66, 2);
    if ( (a1[20] & 0x400000) != 0 && v17 )
    {
      NEEDGRELOCK::vLock((NEEDGRELOCK *)&v60, (struct PDEVOBJ *)&v50);
      DEVLOCKOBJ::vLock((DEVLOCKOBJ *)v66, (struct PDEVOBJ *)&v50);
    }
    v59 = *a1;
    v18 = 0;
    LODWORD(v50) = GreGetObjectOwner(v59, 5);
    LODWORD(BaseAddress) = 0;
    if ( !a4 )
    {
      v19 = v59;
      if ( !HmgRemoveObject((struct Gre::Base::SESSION_GLOBALS *)a2, *((_DWORD *)a2 + 778), 5, (__int64)&BaseAddress) )
      {
        if ( a3 != 1 || (LOBYTE(v45) = 5, !HmgRemoveObjectImpl(a2, v19, 0, 1, 1, v45, &BaseAddress)) )
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
LABEL_98:
              DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v66);
              NEEDGRELOCK::vUnlock((NEEDGRELOCK *)&v60);
              NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded((NEEDDYNAMICMODECHANGESHARELOCK *)v65);
              return v6;
            }
            v20 = *((_DWORD *)a1 + 40);
            if ( (v20 & 0x800) != 0 )
            {
              if ( !*((_DWORD *)a1 + 92) )
              {
                *((_DWORD *)a1 + 92) = 1;
                _InterlockedAdd((volatile signed __int32 *)a2 + 25, 1u);
              }
            }
            else
            {
              *((_DWORD *)a1 + 40) = v20 | 0x1000000;
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
    BaseAddress = (PVOID)a1[9];
    if ( v52 )
      _InterlockedDecrement((volatile signed __int32 *)a2 + 25);
    if ( (a1[20] & 0x40000) != 0 && a1[76] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v22, v21);
    v23 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2048LL);
    if ( v23 )
    {
      if ( v23() >= 0 )
      {
        v24 = *(void (__fastcall **)(__int64 *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2056LL);
        if ( v24 )
          v24(a1);
      }
    }
    SURFACE::vDeleteDriverRealization((SURFACE *)a1);
    if ( v9 )
    {
      if ( *((_DWORD *)a1 + 64) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
        MmUnsecureVirtualMemory(v9);
      goto LABEL_89;
    }
    if ( v48 )
    {
      if ( BaseAddress )
      {
        v61 = 0u;
        v62 = (unsigned __int64)v10;
        LODWORD(v63) = 3;
        Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v61);
      }
      goto LABEL_89;
    }
    if ( v8 )
    {
      if ( *((_DWORD *)a1 + 64) == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
      {
        MmUnsecureVirtualMemory(v8);
        if ( BaseAddress )
        {
          if ( v58 )
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
    if ( (v47 & 8) == 0 )
    {
      if ( (v47 & 0x800) != 0 )
      {
        SEMOBJ<36>::SEMOBJ<36>(&v56, a2);
        v35 = (PEPROCESS *)a1[39];
        if ( v35 )
        {
          v36 = a1 + 72;
          v37 = (__int64 *)a1[72];
          if ( v37 != a1 + 72 )
          {
            if ( (__int64 *)v37[1] != v36 || (v38 = (__int64 **)a1[73], *v38 != v36) )
              __fastfail(3u);
            *v38 = v37;
            v37[1] = (__int64)v38;
          }
          v39 = BaseAddress;
          if ( BaseAddress && RegionSize )
          {
            ProcessId = (unsigned int)PsGetProcessId(*v35);
            Gre::MapViewOfSectionObj::Unmap(ProcessId, v39);
          }
        }
        W32PIDLOCK::vCleanUp((W32PIDLOCK *)&v61);
        if ( RegionSize )
        {
          v49 = RegionSize;
          Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v49);
        }
        SEMOBJ<36>::vUnlock(&v56);
      }
      else if ( (v47 & 0x10) != 0 )
      {
        vFreeKernelSection(BaseAddress);
      }
      goto LABEL_89;
    }
    if ( (v47 & 0x80u) == 0 )
    {
      EngTryFreeUserMem(BaseAddress);
LABEL_89:
      if ( (*((_DWORD *)a1 + 41) & 0x1000) != 0 )
        GrepCaptureLiveMemoryDump(400, 4, v59, v18, (unsigned int)v50, 0);
      SURFACE_Free(a1);
      v41 = v64;
      if ( v64 )
      {
        v42 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2096LL);
        if ( v42 )
        {
          if ( v42() >= 0 )
          {
            v43 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2104LL);
            if ( v43 )
              v43(v41);
          }
        }
      }
      if ( v57 )
        XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v57);
      goto LABEL_98;
    }
    CurrentThread = GreGetCurrentThread();
    v26 = v56;
    v27 = v53;
    v28 = CurrentThread;
    *(_QWORD *)&v61 = 0;
    v29 = v56;
    *((_QWORD *)&v62 + 1) = 0;
    if ( v53 )
      v29 = BaseAddress;
    *(_QWORD *)&v62 = v29;
    *((_QWORD *)&v61 + 1) = 0;
    LODWORD(v63) = 1;
    Gre::MapViewOfSectionObj::~MapViewOfSectionObj((Gre::MapViewOfSectionObj *)&v61);
    if ( v28 && *((_QWORD *)v28 + 8) )
    {
      v30 = UMPDGetThreadClientPID(v28);
    }
    else
    {
      if ( !v54 )
      {
        v32 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2080LL);
        if ( v32 )
        {
          if ( v32() >= 0 )
          {
            v33 = BaseAddress;
            v34 = *(void (__fastcall **)(PVOID))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2088LL);
            if ( v34 )
              v34(v33);
          }
        }
        goto LABEL_70;
      }
      v30 = v55;
    }
    v31 = BaseAddress;
    if ( v27 )
      v31 = v26;
    Gre::MapViewOfSectionObj::Unmap(v30, v31);
LABEL_70:
    if ( v49 )
      Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v49);
    else
      GrepCaptureLiveMemoryDump(400, 68, 2, 0, 0, 0);
    goto LABEL_89;
  }
  return v6;
}

```

## disassembly

```asm
0x140036f30  mov     rax, rsp
0x140036f33  mov     [rax+8], rbx
0x140036f37  mov     [rax+20h], r9d
0x140036f3b  mov     [rax+18h], r8d
0x140036f3f  push    rbp
0x140036f40  push    rsi
0x140036f41  push    rdi
0x140036f42  push    r12
0x140036f44  push    r13
0x140036f46  push    r14
0x140036f48  push    r15
0x140036f4a  lea     rbp, [rax-0D8h]
0x140036f51  sub     rsp, 1A0h
0x140036f58  mov     rsi, rdx
0x140036f5b  mov     rbx, rcx
0x140036f5e  mov     edi, 1
0x140036f63  call    ?bIsDefault@SURFACE@@QEBA_NXZ; SURFACE::bIsDefault(void)
0x140036f68  xor     ecx, ecx
0x140036f6a  test    al, al
0x140036f6c  jnz     loc_140037625
0x140036f72  test    rbx, rbx
0x140036f75  jz      loc_140037625
0x140036f7b  cmp     [rbx+64h], cx
0x140036f7f  jnz     short loc_140036FB6
0x140036f81  mov     rax, [rbx+0E8h]
0x140036f88  mov     r14, [rbx+48h]
0x140036f8c  mov     r13, [rbx+0F0h]
0x140036f93  mov     r12, [rbx+110h]
0x140036f9a  mov     [rbp+0D0h+var_148], rax
0x140036f9e  mov     eax, [rbx+108h]
0x140036fa4  mov     dword ptr [rsp+1D0h+var_188+4], eax
0x140036fa8  mov     eax, [rbx+104h]
0x140036fae  movzx   ecx, ax
0x140036fb1  sub     r14, rcx
0x140036fb4  jmp     short loc_140036FC7
0x140036fb6  mov     r13, rcx
0x140036fb9  mov     dword ptr [rsp+1D0h+var_188+4], ecx
0x140036fbd  mov     r14, rcx
0x140036fc0  mov     [rbp+0D0h+var_148], rcx
0x140036fc4  mov     r12, rcx
0x140036fc7  mov     rax, [rbx+0B0h]
0x140036fce  movups  xmm0, xmmword ptr [rbx+140h]
0x140036fd5  mov     rcx, [rsi]
0x140036fd8  movups  xmm1, xmmword ptr [rbx+150h]
0x140036fdf  mov     [rbp+0D0h+var_150], rax
0x140036fe3  add     rcx, 270h; HSEMAPHORE
0x140036fea  mov     rax, [rbx+0B8h]
0x140036ff1  mov     [rbp+0D0h+var_100], rax
0x140036ff5  movzx   eax, word ptr [rbx+66h]
0x140036ff9  mov     word ptr [rsp+1D0h+var_188], ax
0x140036ffe  mov     rax, [rbx+128h]
0x140037005  mov     [rsp+1D0h+RegionSize], rax
0x14003700a  mov     eax, [rbx+170h]
0x140037010  mov     [rsp+1D0h+var_168], eax
0x140037014  mov     rax, [rbx+278h]
0x14003701b  mov     [rsp+1D0h+var_180], rax
0x140037020  mov     rax, [rbx+280h]
0x140037027  mov     [rsp+1D0h+var_158], rax
0x14003702c  mov     eax, [rbx+290h]
0x140037032  mov     [rsp+1D0h+var_164], eax
0x140037036  mov     eax, [rbx+294h]
0x14003703c  movups  [rbp+0D0h+var_130], xmm0
0x140037040  mov     dword ptr [rsp+1D0h+var_160+4], eax
0x140037044  movups  xmm0, xmmword ptr [rbx+160h]
0x14003704b  mov     eax, [rbx+298h]
0x140037051  mov     dword ptr [rsp+1D0h+var_160], eax
0x140037055  movups  [rbp+0D0h+var_120], xmm1
0x140037059  movups  [rbp+0D0h+var_110], xmm0
0x14003705d  call    ?GrepIsLockOwnedByCurrentThread@@YA_NQEAUHSEMAPHORE__@@@Z; GrepIsLockOwnedByCurrentThread(HSEMAPHORE__ * const)
0x140037062  xor     al, dil
0x140037065  lea     rcx, [rbp+0D0h+var_F8]; this
0x140037069  mov     dl, al; bool
0x14003706b  call    ??0NEEDDYNAMICMODECHANGESHARELOCK@@QEAA@_N@Z; NEEDDYNAMICMODECHANGESHARELOCK::NEEDDYNAMICMODECHANGESHARELOCK(bool)
0x140037070  mov     r15, [rbx+30h]
0x140037074  mov     [rsp+1D0h+var_178], r15
0x140037079  test    r15, r15
0x14003707c  jz      short loc_140037093
0x14003707e  test    dword ptr [rbx+0A0h], 400000h
0x140037088  jz      short loc_140037093
0x14003708a  mov     eax, [r15+28h]
0x14003708e  test    dil, al
0x140037091  jnz     short loc_14003709C
0x140037093  lea     rcx, [rbp+0D0h+var_F8]; this
0x140037097  call    ?vUnlockIfNeeded@NEEDDYNAMICMODECHANGESHARELOCK@@QEAAXXZ; NEEDDYNAMICMODECHANGESHARELOCK::vUnlockIfNeeded(void)
0x14003709c  mov     edx, 2
0x1400370a1  mov     [rbp+0D0h+var_138], 0
0x1400370a9  lea     rcx, [rbp+0D0h+var_E0]
0x1400370ad  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x1400370b2  test    dword ptr [rbx+0A0h], 400000h
0x1400370bc  jz      short loc_1400370DF
0x1400370be  test    r15, r15
0x1400370c1  jz      short loc_1400370DF
0x1400370c3  lea     rdx, [rsp+1D0h+var_178]; struct PDEVOBJ *
0x1400370c8  lea     rcx, [rbp+0D0h+var_138]; this
0x1400370cc  call    ?vLock@NEEDGRELOCK@@QEAAXAEAVPDEVOBJ@@@Z; NEEDGRELOCK::vLock(PDEVOBJ &)
0x1400370d1  lea     rdx, [rsp+1D0h+var_178]; struct PDEVOBJ *
0x1400370d6  lea     rcx, [rbp+0D0h+var_E0]; this
0x1400370da  call    ?vLock@DEVLOCKOBJ@@QEAAXAEAVPDEVOBJ@@@Z; DEVLOCKOBJ::vLock(PDEVOBJ &)
0x1400370df  mov     rax, [rbx]
0x1400370e2  mov     edx, 5
0x1400370e7  mov     rcx, rax
0x1400370ea  mov     [rbp+0D0h+var_140], rax
0x1400370ee  call    GreGetObjectOwner
0x1400370f3  xor     r15d, r15d
0x1400370f6  mov     dword ptr [rsp+1D0h+var_178], eax
0x1400370fa  mov     dword ptr [rsp+1D0h+BaseAddress], r15d
0x1400370ff  cmp     [rbp+0D0h+arg_18], r15d
0x140037106  jnz     loc_140037202
0x14003710c  mov     r15, [rbp+0D0h+var_140]
0x140037110  lea     rax, [rsp+1D0h+BaseAddress]
0x140037115  mov     qword ptr [rsp+1D0h+var_1A8+8], rax; __int64
0x14003711a  mov     r9d, edi
0x14003711d  mov     eax, [rsi+0C28h]
0x140037123  xor     r8d, r8d
0x140037126  mov     byte ptr [rsp+1D0h+var_1A8], 5; char
0x14003712b  mov     rdx, r15
0x14003712e  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x140037131  mov     [rsp+1D0h+var_1B0], eax; int
0x140037135  call    HmgRemoveObject
0x14003713a  test    rax, rax
0x14003713d  jnz     loc_1400371FD
0x140037143  cmp     [rbp+0D0h+arg_10], edi
0x140037149  jnz     short loc_140037178
0x14003714b  lea     rax, [rsp+1D0h+BaseAddress]
0x140037150  mov     r9d, edi
0x140037153  mov     qword ptr [rsp+1D0h+var_1A8+8], rax
0x140037158  xor     r8d, r8d
0x14003715b  mov     byte ptr [rsp+1D0h+var_1A8], 5
0x140037160  mov     rdx, r15
0x140037163  mov     rcx, rsi
0x140037166  mov     [rsp+1D0h+var_1B0], edi
0x14003716a  call    ?HmgRemoveObjectImpl@@YAPEAXAEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@JJW4HandleLockOptions@@EPEAK@Z; HmgRemoveObjectImpl(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,long,long,HandleLockOptions,uchar,ulong *)
0x14003716f  test    rax, rax
0x140037172  jnz     loc_1400371FD
0x140037178  cmp     dword ptr [rsp+1D0h+BaseAddress], edi
0x14003717c  jz      short loc_1400371D7
0x14003717e  cmp     qword ptr [rbx+0D0h], 0
0x140037186  jnz     short loc_1400371AA
0x140037188  mov     rcx, rbx; this
0x14003718b  call    ?bStockSurface@SURFACE@@QEAAHXZ; SURFACE::bStockSurface(void)
0x140037190  test    eax, eax
0x140037192  jnz     short loc_1400371AA
0x140037194  bt      dword ptr [rbx+0A0h], 0Bh
0x14003719c  jb      short loc_1400371AA
0x14003719e  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x1400371a3  xor     edi, edi
0x1400371a5  jmp     loc_14003760A
0x1400371aa  mov     eax, [rbx+0A0h]
0x1400371b0  bt      eax, 0Bh
0x1400371b4  jb      short loc_1400371C2
0x1400371b6  bts     eax, 18h
0x1400371ba  mov     [rbx+0A0h], eax
0x1400371c0  jmp     short loc_1400371E1
0x1400371c2  cmp     dword ptr [rbx+170h], 0
0x1400371c9  jnz     short loc_1400371E1
0x1400371cb  mov     [rbx+170h], edi
0x1400371d1  lock add [rsi+64h], edi
0x1400371d5  jmp     short loc_1400371E1
0x1400371d7  bt      dword ptr [rbx+0A0h], 0Bh
0x1400371df  jnb     short loc_1400371F1
0x1400371e1  mov     rdx, rbx
0x1400371e4  mov     rcx, rsi
0x1400371e7  call    HmgDecrementShareReferenceCount
0x1400371ec  jmp     loc_14003760A
0x1400371f1  mov     ecx, 0AAh; iError
0x1400371f6  call    EngSetLastError
0x1400371fb  jmp     short loc_1400371A3
0x1400371fd  mov     r15d, dword ptr [rsp+1D0h+BaseAddress]
0x140037202  call    IsSURFMEMMappingEnabled
0x140037207  test    eax, eax
0x140037209  jz      short loc_140037216
0x14003720b  mov     dl, dil; bool
0x14003720e  mov     rcx, rbx; this
0x140037211  call    ?UnmapUserVAFromKernel@SURFACE@@QEAAX_N@Z; SURFACE::UnmapUserVAFromKernel(bool)
0x140037216  cmp     [rsp+1D0h+var_168], 0
0x14003721b  mov     rax, [rbx+48h]
0x14003721f  mov     [rsp+1D0h+BaseAddress], rax
0x140037224  jz      short loc_14003722A
0x140037226  lock dec dword ptr [rsi+64h]
0x14003722a  test    dword ptr [rbx+0A0h], 40000h
0x140037234  jz      short loc_140037245
0x140037236  cmp     qword ptr [rbx+260h], 0
0x14003723e  jz      short loc_140037245
0x140037240  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140037245  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003724c  nop     dword ptr [rax+rax+00h]
0x140037251  mov     rcx, [rax+18h]
0x140037255  mov     rax, [rcx+800h]
0x14003725c  test    rax, rax
0x14003725f  jz      short loc_14003728E
0x140037261  call    _guard_dispatch_icall
0x140037266  test    eax, eax
0x140037268  js      short loc_14003728E
0x14003726a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140037271  nop     dword ptr [rax+rax+00h]
0x140037276  mov     rcx, [rax+18h]
0x14003727a  mov     rax, [rcx+808h]
0x140037281  test    rax, rax
0x140037284  jz      short loc_14003728E
0x140037286  mov     rcx, rbx
0x140037289  call    _guard_dispatch_icall
0x14003728e  mov     rcx, rbx; this
0x140037291  call    ?vDeleteDriverRealization@SURFACE@@QEAAXXZ; SURFACE::vDeleteDriverRealization(void)
0x140037296  test    r12, r12
0x140037299  jz      short loc_1400372CA
0x14003729b  call    cs:__imp_PsGetCurrentProcessId
0x1400372a2  nop     dword ptr [rax+rax+00h]
0x1400372a7  and     eax, 0FFFFFFFCh
0x1400372aa  cmp     [rbx+100h], eax
0x1400372b0  jnz     loc_140037567
0x1400372b6  mov     rcx, r12; SecureHandle
0x1400372b9  call    cs:__imp_MmUnsecureVirtualMemory
0x1400372c0  nop     dword ptr [rax+rax+00h]
0x1400372c5  jmp     loc_140037567
0x1400372ca  cmp     dword ptr [rsp+1D0h+var_188+4], 0
0x1400372cf  jz      short loc_140037306
0x1400372d1  xor     r13d, r13d
0x1400372d4  cmp     [rsp+1D0h+BaseAddress], r13
0x1400372d9  jz      loc_14003756A
0x1400372df  xor     eax, eax
0x1400372e1  mov     qword ptr [rbp+0D0h+var_130], r13
0x1400372e5  lea     rcx, [rbp+0D0h+var_130]; this
0x1400372e9  mov     qword ptr [rbp+0D0h+var_130+8], rax
0x1400372ed  mov     qword ptr [rbp+0D0h+var_120], r14
0x1400372f1  mov     qword ptr [rbp+0D0h+var_120+8], r13
0x1400372f5  mov     dword ptr [rbp+0D0h+var_110], 3
0x1400372fc  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x140037301  jmp     loc_14003756A
0x140037306  test    r13, r13
0x140037309  jz      short loc_140037387
0x14003730b  call    cs:__imp_PsGetCurrentProcessId
0x140037312  nop     dword ptr [rax+rax+00h]
0x140037317  and     eax, 0FFFFFFFCh
0x14003731a  cmp     [rbx+100h], eax
0x140037320  jnz     loc_140037567
0x140037326  mov     rcx, r13; SecureHandle
0x140037329  call    cs:__imp_MmUnsecureVirtualMemory
0x140037330  nop     dword ptr [rax+rax+00h]
0x140037335  xor     r13d, r13d
0x140037338  cmp     [rsp+1D0h+BaseAddress], r13
0x14003733d  jz      loc_14003756A
0x140037343  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140037347  cmp     [rbp+0D0h+var_148], r13
0x14003734b  jz      short loc_140037361
0x14003734d  mov     rdx, r14; BaseAddress
0x140037350  call    cs:__imp_ZwUnmapViewOfSection
0x140037357  nop     dword ptr [rax+rax+00h]
0x14003735c  jmp     loc_14003756A
0x140037361  mov     r9d, 8000h; FreeType
0x140037367  mov     [rsp+1D0h+RegionSize], r13
0x14003736c  lea     r8, [rsp+1D0h+RegionSize]; RegionSize
0x140037371  lea     rdx, [rsp+1D0h+BaseAddress]; BaseAddress
0x140037376  call    cs:__imp_ZwFreeVirtualMemory
0x14003737d  nop     dword ptr [rax+rax+00h]
0x140037382  jmp     loc_14003756A
0x140037387  movzx   eax, word ptr [rsp+1D0h+var_188]
0x14003738c  test    al, 8
0x14003738e  jz      loc_1400374AE
0x140037394  test    al, al
0x140037396  jns     loc_14003749F
0x14003739c  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x1400373a1  mov     r14, [rsp+1D0h+var_158]
0x1400373a6  xor     r13d, r13d
0x1400373a9  mov     r12d, [rsp+1D0h+var_164]
0x1400373ae  mov     rsi, rax
0x1400373b1  test    r12d, r12d
0x1400373b4  mov     qword ptr [rbp+0D0h+var_130], r13
0x1400373b8  mov     rcx, r14
0x1400373bb  mov     qword ptr [rbp+0D0h+var_120+8], r13
0x1400373bf  cmovnz  rcx, [rsp+1D0h+BaseAddress]
0x1400373c5  xor     eax, eax
0x1400373c7  mov     qword ptr [rbp+0D0h+var_120], rcx
0x1400373cb  lea     rcx, [rbp+0D0h+var_130]; this
0x1400373cf  mov     qword ptr [rbp+0D0h+var_130+8], rax
0x1400373d3  mov     dword ptr [rbp+0D0h+var_110], edi
0x1400373d6  call    ??1MapViewOfSectionObj@Gre@@QEAA@XZ; Gre::MapViewOfSectionObj::~MapViewOfSectionObj(void)
0x1400373db  test    rsi, rsi
0x1400373de  jz      short loc_1400373F0
0x1400373e0  cmp     [rsi+40h], r13
0x1400373e4  jz      short loc_1400373F0
0x1400373e6  mov     rcx, rsi
0x1400373e9  call    UMPDGetThreadClientPID
0x1400373ee  jmp     short loc_1400373FB
0x1400373f0  cmp     dword ptr [rsp+1D0h+var_160], r13d
0x1400373f5  jz      short loc_140037410
0x1400373f7  mov     eax, dword ptr [rsp+1D0h+var_160+4]
0x1400373fb  mov     rdx, [rsp+1D0h+BaseAddress]
0x140037400  test    r12d, r12d
0x140037403  mov     ecx, eax; unsigned int
0x140037405  cmovnz  rdx, r14; void *
0x140037409  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x14003740e  jmp     short loc_14003745E
0x140037410  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140037417  nop     dword ptr [rax+rax+00h]
0x14003741c  mov     rcx, [rax+18h]
0x140037420  mov     rax, [rcx+820h]
0x140037427  test    rax, rax
0x14003742a  jz      short loc_14003745E
0x14003742c  call    _guard_dispatch_icall
0x140037431  test    eax, eax
  ... truncated ...
```
