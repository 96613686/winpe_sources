# StorReset

- ea: `0x14004ee60`
- end: `0x14004f699`
- name: `StorReset`
- size: `2105`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140054e60`
- `0x140087e84`

## callees

- `0x1400253b4`
- `0x1400290b0`
- `0x140033880`
- `0x140039cb8`
- `0x140042ab8`
- `0x14004a0a8`
- `0x14004ee60`
- `0x14009dd68`
- `0x1400a521c`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004efa5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004f490`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004efa5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14004f490`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f4ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f4ac`
- `ntoskrnl!KeInitializeEvent` at `0x14004f009`
- `ntoskrnl!KeInitializeEvent` at `0x14004f026`
- `ntoskrnl!KeInitializeEvent` at `0x14004f009`
- `ntoskrnl!KeInitializeEvent` at `0x14004f026`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f2c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f35a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f45e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f521`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f2c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f35a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f45e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004f521`
- `ntoskrnl!RtlCompareMemory` at `0x14004f163`
- `ntoskrnl!RtlCompareMemory` at `0x14004f253`
- `ntoskrnl!RtlCompareMemory` at `0x14004f271`
- `ntoskrnl!RtlCompareMemory` at `0x14004f163`
- `ntoskrnl!RtlCompareMemory` at `0x14004f253`
- `ntoskrnl!RtlCompareMemory` at `0x14004f271`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004ef56`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004ef56`
- `HAL!KeQueryPerformanceCounter` at `0x14004ef97`
- `HAL!KeQueryPerformanceCounter` at `0x14004f313`
- `HAL!KeQueryPerformanceCounter` at `0x14004ef97`
- `HAL!KeQueryPerformanceCounter` at `0x14004f313`

## pseudocode

```c
__int64 __fastcall StorReset(__int64 a1, unsigned int a2, int a3, char a4)
{
  unsigned int v4; // r13d
  __int64 v7; // r14
  void *v8; // r15
  LARGE_INTEGER v9; // rdi
  signed int v10; // esi
  __int64 RaidAdapter; // rax
  unsigned __int16 v12; // dx
  __int64 v13; // rax
  LARGE_INTEGER v14; // rax
  __int64 v15; // rcx
  __int64 Pool; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rbx
  __int64 v21; // r15
  int *v22; // rax
  int v23; // r13d
  __int64 v24; // rcx
  char v25; // r12
  char *v26; // rbx
  __int64 v27; // rdx
  signed int v28; // eax
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v30; // r8
  _DWORD *v31; // rcx
  __int64 v32; // rax
  signed int v33; // eax
  int v34; // ebx
  LARGE_INTEGER v35; // rbx
  _DWORD *v36; // rax
  int v37; // eax
  int v38; // edx
  unsigned int *v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rcx
  __int64 *v43; // r15
  unsigned int LowPart; // r8d
  unsigned __int64 v45; // r11
  unsigned __int64 v46; // rbx
  __int64 *v47; // rdx
  _BYTE v49[4]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v50; // [rsp+64h] [rbp-4Dh]
  char v51; // [rsp+68h] [rbp-49h]
  char v52; // [rsp+69h] [rbp-48h]
  _BYTE *v53; // [rsp+70h] [rbp-41h]
  unsigned int v54; // [rsp+78h] [rbp-39h] BYREF
  int v55; // [rsp+7Ch] [rbp-35h]
  __int64 v56; // [rsp+80h] [rbp-31h] BYREF
  __int128 v57; // [rsp+88h] [rbp-29h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-19h] BYREF
  __int128 v59; // [rsp+A0h] [rbp-11h] BYREF

  v50 = a2;
  v4 = a2;
  v54 = 0;
  PerformanceFrequency.QuadPart = 0;
  v55 = a3;
  v52 = 0;
  v51 = 0;
  v7 = 0;
  v8 = 0;
  v9.QuadPart = 0;
  if ( a2 >= 3 )
  {
    v10 = -1073741822;
    goto LABEL_71;
  }
  if ( (unsigned int)(a3 - 1) > 1
    || (*(_DWORD *)(*(_QWORD *)(a1 - 16) + 248LL) & 1) != 0
    || (RaidAdapter = RaMiniportGetRaidAdapter(), (v7 = RaidAdapter) == 0) )
  {
    v10 = -1073741811;
    goto LABEL_71;
  }
  if ( v4 == 2 && *(_DWORD *)(RaidAdapter + 376) != 5 )
    goto LABEL_9;
  v13 = *(_QWORD *)(RaidAdapter + 5440);
  if ( !v13
    || !*(_QWORD *)(v13 + 8)
    || *(_WORD *)(v13 + 2) < v12
    || *(_WORD *)v13 < 0x50u
    || !*(_QWORD *)(v13 + 56)
    || !*(_QWORD *)(v13 + 64)
    || !*(_QWORD *)(v13 + 72) )
  {
    goto LABEL_9;
  }
  if ( !(unsigned __int8)StorIsIoGatewayPaused(*(_QWORD *)(v7 + 1024)) )
  {
    v10 = -1073741808;
    goto LABEL_71;
  }
  if ( KeGetCurrentIrql() )
  {
    v10 = -1073741496;
    goto LABEL_71;
  }
  if ( _interlockedbittestandset((volatile signed __int32 *)(v7 + 128), 2u) )
  {
    v10 = -1073740682;
    goto LABEL_71;
  }
  v52 = 1;
  if ( UseQPCTime )
    v14 = KeQueryPerformanceCounter(&PerformanceFrequency);
  else
    v14.QuadPart = KeQueryUnbiasedInterruptTime();
  v15 = *(_QWORD *)(v7 + 6208);
  v9 = v14;
  if ( !v15 )
  {
    Pool = RaidAllocatePool(64, 80, 1163026770, *(_QWORD *)(v7 + 8));
    *(_QWORD *)(v7 + 6208) = Pool;
    v15 = Pool;
    if ( !Pool )
      goto LABEL_28;
  }
  if ( v4 == 1 )
  {
    if ( (*(_DWORD *)v15 & 1) == 0 )
    {
      KeInitializeEvent((PRKEVENT)(v15 + 32), SynchronizationEvent, 0);
      KeInitializeEvent((PRKEVENT)(*(_QWORD *)(v7 + 6208) + 56LL), SynchronizationEvent, 0);
      **(_DWORD **)(v7 + 6208) |= 1u;
      v15 = *(_QWORD *)(v7 + 6208);
    }
    if ( a3 == 1 )
    {
      ++*(_DWORD *)(v15 + 24);
    }
    else if ( a3 == 2 )
    {
      ++*(_DWORD *)(v15 + 20);
    }
    *(_DWORD *)(*(_QWORD *)(v7 + 6208) + 16LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v7 + 6208) + 8LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v7 + 6208) + 4LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v7 + 6208) + 12LL) = 0;
    **(_DWORD **)(v7 + 6208) &= ~0x20u;
    **(_DWORD **)(v7 + 6208) &= ~0x80u;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD))(*(_QWORD *)(v7 + 5440) + 56LL))(
          *(_QWORD *)(*(_QWORD *)(v7 + 5440) + 8LL),
          &v54,
          0);
  v10 = v17;
  if ( v17 != -1073741789 )
  {
    if ( v17 >= 0 )
      v10 = -1073741823;
    goto LABEL_71;
  }
  if ( v54 - 1 > 0xFFF )
  {
LABEL_9:
    v10 = -1073741637;
    goto LABEL_71;
  }
  v18 = RaidAllocatePool(64, 24LL * v54, 1163026770, *(_QWORD *)(v7 + 8));
  v53 = (_BYTE *)v18;
  v8 = (void *)v18;
  if ( !v18 )
  {
LABEL_28:
    v10 = -1073741670;
    goto LABEL_71;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64))(*(_QWORD *)(v7 + 5440) + 56LL))(
          *(_QWORD *)(*(_QWORD *)(v7 + 5440) + 8LL),
          &v54,
          v18);
  if ( v10 < 0 )
    goto LABEL_71;
  v19 = 0;
  v20 = 4;
  while ( 1 )
  {
    if ( (unsigned int)v19 >= v54 )
    {
      v10 = -1073741637;
      goto LABEL_70;
    }
    v21 = (unsigned int)v19;
    if ( v4 == 2 )
    {
      if ( RtlCompareMemory(&v53[24 * v19], &GUID_BUS_TYPE_PCI, 0x10u) == 16 && (v53[24 * v19 + 16] & 4) != 0 )
        goto LABEL_52;
      v4 = v50;
      goto LABEL_54;
    }
    if ( v4 == 1 )
      break;
    if ( !v4 && (v53[24 * v19 + 16] & 1) != 0 )
    {
LABEL_52:
      v22 = (int *)(v7 + 6096);
      goto LABEL_56;
    }
LABEL_54:
    v19 = (unsigned int)(v19 + 1);
  }
  if ( (v53[24 * v19 + 16] & 2) == 0 )
    goto LABEL_54;
  v22 = (int *)(v7 + 6100);
LABEL_56:
  v23 = *v22;
  v24 = *(_QWORD *)(v7 + 5440);
  v49[0] = 0;
  *(_QWORD *)&v57 = 0;
  *(_QWORD *)&v59 = 0;
  v56 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int128 *, __int128 *))(v24 + 72))(
          *(_QWORD *)(v24 + 8),
          v49,
          &v57,
          &v59);
  if ( v10 < 0 )
  {
LABEL_69:
    v4 = v50;
LABEL_70:
    v8 = v53;
    goto LABEL_71;
  }
  if ( v49[0] )
  {
    v4 = v50;
    v8 = v53;
    v10 = -1073741436;
    goto LABEL_71;
  }
  v25 = a4 & 1;
  if ( !v50 )
  {
    v20 = 1;
    goto LABEL_80;
  }
  if ( v50 != 2 )
  {
    if ( v50 == 1 )
    {
      v26 = &v53[24 * v21];
      if ( RtlCompareMemory(v26, &GUID_BUS_TYPE_ACPI, 0x10u) != 16
        && RtlCompareMemory(v26, &GUID_BUS_TYPE_PCI, 0x10u) != 16 )
      {
        v10 = -1073741637;
        goto LABEL_69;
      }
      v20 = 2;
      if ( v25 )
        goto LABEL_68;
      LOBYTE(v27) = 1;
      v51 = 1;
      v28 = RaidRequestDIrpForAssociatedUnits(v7, v27);
      v10 = v28;
      if ( v28 == 259 )
      {
        KeWaitForSingleObject((PVOID)(*(_QWORD *)(v7 + 6208) + 32LL), Executive, 0, 0, 0);
        **(_DWORD **)(v7 + 6208) |= 0x20u;
        goto LABEL_68;
      }
      if ( v28 != -1073741823 && v28 != -1073741436 )
      {
        v31 = *(_DWORD **)(v7 + 6208);
        if ( v31[1] && (*v31 & 0x10) != 0 )
        {
          KeWaitForSingleObject(v31 + 8, Executive, 0, 0, 0);
          **(_DWORD **)(v7 + 6208) |= 0x80u;
        }
        goto LABEL_69;
      }
LABEL_68:
      v10 = RaCallMiniportAdapterControlSafe(v7 + 360, 27);
      if ( v10 < 0 )
        goto LABEL_69;
    }
    else
    {
      v20 = 0;
    }
  }
LABEL_80:
  v56 = 0;
  if ( !v25 )
  {
    *(_BYTE *)(v7 + 111) |= 0x20u;
    v56 = 1;
  }
  v32 = 3 * v21;
  v8 = v53;
  v33 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, __int64 *, _QWORD))(*(_QWORD *)(v7 + 5440) + 64LL))(
          *(_QWORD *)(*(_QWORD *)(v7 + 5440) + 8LL),
          &v53[8 * v32],
          v20,
          &v56,
          0);
  v10 = v33;
  if ( v33 )
  {
    if ( v33 == 259 )
    {
      if ( !v25 )
      {
        v34 = 0;
        if ( !(200 * v23) )
        {
LABEL_89:
          v10 = -1073741643;
          goto LABEL_69;
        }
        while ( 1 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int128 *, __int128 *))(*(_QWORD *)(v7 + 5440) + 72LL))(
                  *(_QWORD *)(*(_QWORD *)(v7 + 5440) + 8LL),
                  v49,
                  &v57,
                  &v59);
          if ( v10 < 0 || !v49[0] )
            break;
          StorDelayExecution(0x1388u);
          if ( ++v34 >= (unsigned int)(200 * v23) )
            goto LABEL_89;
        }
        v8 = v53;
        goto LABEL_93;
      }
      v10 = 0;
    }
LABEL_91:
    v4 = v50;
  }
  else
  {
LABEL_93:
    if ( (*(_BYTE *)(v7 + 111) & 0x20) == 0 )
      goto LABEL_91;
    KeWaitForSingleObject((PVOID)(v7 + 6168), Executive, 0, 0, 0);
    v4 = v50;
    v10 = *(_DWORD *)(v7 + 88) != 1 ? 0xC0000184 : 0;
  }
LABEL_71:
  if ( UseQPCTime )
    PerformanceCounter = KeQueryPerformanceCounter(0);
  else
    PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
  v35 = PerformanceCounter;
  if ( v8 )
    ExFreePoolWithTag(v8, 0x45526152u);
  if ( v7 )
  {
    if ( v4 == 1 )
    {
      if ( v51 )
      {
        v36 = *(_DWORD **)(v7 + 6208);
        if ( v36 )
        {
          if ( ((*v36 & 0x20) != 0 || (*v36 & 0x80u) != 0) && v55 == 1 )
          {
            v37 = RaidRequestDIrpForAssociatedUnits(v7, 0);
            v38 = v37;
            if ( v37 == 259 )
            {
              KeWaitForSingleObject((PVOID)(*(_QWORD *)(v7 + 6208) + 56LL), Executive, 0, 0, 0);
              v38 = 0;
            }
            else if ( v10 >= 0 && v37 < 0 )
            {
              v10 = -1073741436;
            }
            v39 = *(unsigned int **)(v7 + 6208);
            v40 = *v39;
            if ( v38 < 0 )
            {
              v41 = v40 | 0x40;
LABEL_117:
              *v39 = v41;
            }
            else
            {
              if ( (v40 & 0x20) != 0 )
              {
                v41 = v40 & 0xFFFFFFDF;
                goto LABEL_117;
              }
              if ( (v40 & 0x80u) != 0 )
              {
                v41 = v40 & 0xFFFFFF7F;
                goto LABEL_117;
              }
            }
          }
        }
      }
    }
    if ( StorEtwLoggingEnabled )
    {
      v42 = *(_QWORD *)(v7 + 16);
      v43 = *(__int64 **)(v7 + 5144);
      v59 = *(_OWORD *)(v7 + 5128);
      v57 = 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RaidDriverGetName)(v42, &v57, (LARGE_INTEGER)v30.QuadPart);
      if ( v9.QuadPart && v35.QuadPart )
      {
        if ( v35.QuadPart <= 0 || v35.QuadPart >= v9.QuadPart )
          v46 = v35.QuadPart - v9.QuadPart;
        else
          v46 = v35.QuadPart - v9.QuadPart - 1;
        if ( UseQPCTime == (_BYTE)v45 )
        {
          LOBYTE(v45) = v46;
        }
        else
        {
          LowPart = PerformanceFrequency.LowPart;
          if ( PerformanceFrequency.QuadPart && v46 )
            v45 = 10000
                * (1000 * (v46 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart)
                / PerformanceFrequency.QuadPart
                + 10000
                * (1000 * (v46 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart
                 + 1000 * (v46 / PerformanceFrequency.QuadPart));
        }
      }
      if ( (byte_140177436 & 8) != 0 )
      {
        v47 = &qword_140155FE0;
        if ( v43 )
          v47 = v43;
        McTemplateK0qjzztqdqx_EtwWriteTransfer(
          *(unsigned __int8 *)(v7 + 104) >> 7,
          (_DWORD)v47,
          LowPart,
          *(_DWORD *)(v7 + 56),
          (__int64)&v59,
          *((__int64 *)&v57 + 1),
          (__int64)v47,
          *(_BYTE *)(v7 + 104) >> 7,
          v4,
          v10,
          *(_DWORD *)(v7 + 5844),
          v45);
      }
    }
    *(_BYTE *)(v7 + 111) &= ~0x20u;
    if ( v52 )
      *(_DWORD *)(v7 + 128) &= ~4u;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14004ee60  push    rbp
0x14004ee62  push    rbx
0x14004ee63  push    rsi
0x14004ee64  push    rdi
0x14004ee65  push    r12
0x14004ee67  push    r13
0x14004ee69  push    r14
0x14004ee6b  push    r15
0x14004ee6d  lea     rbp, [rsp-17h]
0x14004ee72  sub     rsp, 0C8h
0x14004ee79  mov     rax, cs:__security_cookie
0x14004ee80  xor     rax, rsp
0x14004ee83  mov     [rbp+4Fh+var_50], rax
0x14004ee87  xor     esi, esi
0x14004ee89  mov     [rbp+4Fh+var_9C], edx
0x14004ee8c  mov     r13d, edx
0x14004ee8f  mov     [rbp+4Fh+var_88], esi
0x14004ee92  mov     ebx, r8d
0x14004ee95  mov     qword ptr [rbp+4Fh+PerformanceFrequency], rsi
0x14004ee99  mov     r12, r9
0x14004ee9c  mov     [rbp+4Fh+var_84], ebx
0x14004ee9f  lea     edx, [rsi+3]
0x14004eea2  mov     [rbp+4Fh+var_97], sil
0x14004eea6  mov     [rbp+4Fh+var_98], sil
0x14004eeaa  mov     r14d, esi
0x14004eead  mov     r15d, esi
0x14004eeb0  mov     edi, esi
0x14004eeb2  cmp     r13d, edx
0x14004eeb5  jb      short loc_14004EEC1
0x14004eeb7  mov     esi, 0C0000002h
0x14004eebc  jmp     loc_14004F2FE
0x14004eec1  lea     eax, [r8-1]
0x14004eec5  cmp     eax, 1
0x14004eec8  jbe     short loc_14004EED4
0x14004eeca  mov     esi, 0C000000Dh
0x14004eecf  jmp     loc_14004F2FE
0x14004eed4  mov     rcx, [rcx-10h]
0x14004eed8  mov     eax, [rcx+0F8h]
0x14004eede  test    al, 1
0x14004eee0  jnz     short loc_14004EECA
0x14004eee2  call    RaMiniportGetRaidAdapter
0x14004eee7  mov     r14, rax
0x14004eeea  test    rax, rax
0x14004eeed  jz      short loc_14004EECA
0x14004eeef  cmp     r13d, 2
0x14004eef3  jnz     short loc_14004EF08
0x14004eef5  cmp     dword ptr [rax+178h], 5
0x14004eefc  jz      short loc_14004EF08
0x14004eefe  mov     esi, 0C00000BBh
0x14004ef03  jmp     loc_14004F2FE
0x14004ef08  mov     rax, [rax+1540h]
0x14004ef0f  test    rax, rax
0x14004ef12  jz      short loc_14004EEFE
0x14004ef14  cmp     [rax+8], rsi
0x14004ef18  jz      short loc_14004EEFE
0x14004ef1a  cmp     [rax+2], dx
0x14004ef1e  jb      short loc_14004EEFE
0x14004ef20  mov     ecx, 50h ; 'P'
0x14004ef25  cmp     [rax], cx
0x14004ef28  jb      short loc_14004EEFE
0x14004ef2a  cmp     [rax+38h], rsi
0x14004ef2e  jz      short loc_14004EEFE
0x14004ef30  cmp     [rax+40h], rsi
0x14004ef34  jz      short loc_14004EEFE
0x14004ef36  cmp     [rax+48h], rsi
0x14004ef3a  jz      short loc_14004EEFE
0x14004ef3c  mov     rcx, [r14+400h]
0x14004ef43  call    StorIsIoGatewayPaused
0x14004ef48  test    al, al
0x14004ef4a  jnz     short loc_14004EF56
0x14004ef4c  mov     esi, 0C0000010h
0x14004ef51  jmp     loc_14004F2FE
0x14004ef56  call    cs:__imp_KeGetCurrentIrql
0x14004ef5d  nop     dword ptr [rax+rax+00h]
0x14004ef62  test    al, al
0x14004ef64  jz      short loc_14004EF70
0x14004ef66  mov     esi, 0C0000148h
0x14004ef6b  jmp     loc_14004F2FE
0x14004ef70  lock bts dword ptr [r14+80h], 2
0x14004ef7a  jnb     short loc_14004EF86
0x14004ef7c  mov     esi, 0C0000476h
0x14004ef81  jmp     loc_14004F2FE
0x14004ef86  cmp     cs:UseQPCTime, sil
0x14004ef8d  mov     [rbp+4Fh+var_97], 1
0x14004ef91  jz      short loc_14004EFA5
0x14004ef93  lea     rcx, [rbp+4Fh+PerformanceFrequency]; PerformanceFrequency
0x14004ef97  call    cs:__imp_KeQueryPerformanceCounter
0x14004ef9e  nop     dword ptr [rax+rax+00h]
0x14004efa3  jmp     short loc_14004EFB1
0x14004efa5  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14004efac  nop     dword ptr [rax+rax+00h]
0x14004efb1  mov     rcx, [r14+1840h]
0x14004efb8  mov     rdi, rax
0x14004efbb  test    rcx, rcx
0x14004efbe  jnz     short loc_14004EFEE
0x14004efc0  mov     r9, [r14+8]
0x14004efc4  lea     edx, [rcx+50h]
0x14004efc7  lea     ecx, [rdx-10h]
0x14004efca  mov     r8d, 45526152h
0x14004efd0  call    RaidAllocatePool
0x14004efd5  mov     [r14+1840h], rax
0x14004efdc  mov     rcx, rax
0x14004efdf  test    rax, rax
0x14004efe2  jnz     short loc_14004EFEE
0x14004efe4  mov     esi, 0C000009Ah
0x14004efe9  jmp     loc_14004F2FE
0x14004efee  cmp     r13d, 1
0x14004eff2  jnz     loc_14004F092
0x14004eff8  mov     eax, [rcx]
0x14004effa  test    r13b, al
0x14004effd  jnz     short loc_14004F043
0x14004efff  add     rcx, 20h ; ' '; Event
0x14004f003  xor     r8d, r8d; State
0x14004f006  mov     edx, r13d; Type
0x14004f009  call    cs:__imp_KeInitializeEvent
0x14004f010  nop     dword ptr [rax+rax+00h]
0x14004f015  mov     rcx, [r14+1840h]
0x14004f01c  xor     r8d, r8d; State
0x14004f01f  add     rcx, 38h ; '8'; Event
0x14004f023  mov     edx, r13d; Type
0x14004f026  call    cs:__imp_KeInitializeEvent
0x14004f02d  nop     dword ptr [rax+rax+00h]
0x14004f032  mov     rax, [r14+1840h]
0x14004f039  or      [rax], r13d
0x14004f03c  mov     rcx, [r14+1840h]
0x14004f043  cmp     ebx, 1
0x14004f046  jnz     short loc_14004F04D
0x14004f048  inc     dword ptr [rcx+18h]
0x14004f04b  jmp     short loc_14004F055
0x14004f04d  cmp     ebx, 2
0x14004f050  jnz     short loc_14004F055
0x14004f052  inc     dword ptr [rcx+14h]
0x14004f055  mov     rax, [r14+1840h]
0x14004f05c  mov     [rax+10h], esi
0x14004f05f  mov     rax, [r14+1840h]
0x14004f066  mov     [rax+8], esi
0x14004f069  mov     rax, [r14+1840h]
0x14004f070  mov     [rax+4], esi
0x14004f073  mov     rax, [r14+1840h]
0x14004f07a  mov     [rax+0Ch], esi
0x14004f07d  mov     rax, [r14+1840h]
0x14004f084  and     dword ptr [rax], 0FFFFFFDFh
0x14004f087  mov     rax, [r14+1840h]
0x14004f08e  btr     dword ptr [rax], 7
0x14004f092  mov     rcx, [r14+1540h]
0x14004f099  lea     rdx, [rbp+4Fh+var_88]
0x14004f09d  xor     r8d, r8d
0x14004f0a0  mov     rax, [rcx+38h]
0x14004f0a4  mov     rcx, [rcx+8]
0x14004f0a8  call    _guard_dispatch_icall
0x14004f0ad  mov     esi, eax
0x14004f0af  cmp     eax, 0C0000023h
0x14004f0b4  jz      short loc_14004F0CE
0x14004f0b6  mov     r12d, 0C0000184h
0x14004f0bc  test    eax, eax
0x14004f0be  js      loc_14004F304
0x14004f0c4  mov     esi, 0C0000001h
0x14004f0c9  jmp     loc_14004F304
0x14004f0ce  mov     ecx, [rbp+4Fh+var_88]
0x14004f0d1  lea     eax, [rcx-1]
0x14004f0d4  cmp     eax, 0FFFh
0x14004f0d9  ja      loc_14004EEFE
0x14004f0df  mov     r9, [r14+8]
0x14004f0e3  lea     rdx, [rcx+rcx*2]
0x14004f0e7  shl     rdx, 3
0x14004f0eb  mov     ecx, 40h ; '@'
0x14004f0f0  mov     r8d, 45526152h
0x14004f0f6  call    RaidAllocatePool
0x14004f0fb  mov     [rbp+4Fh+var_90], rax
0x14004f0ff  mov     r15, rax
0x14004f102  test    rax, rax
0x14004f105  jz      loc_14004EFE4
0x14004f10b  mov     rcx, [r14+1540h]
0x14004f112  lea     rdx, [rbp+4Fh+var_88]
0x14004f116  mov     r8, r15
0x14004f119  mov     rax, [rcx+38h]
0x14004f11d  mov     rcx, [rcx+8]
0x14004f121  call    _guard_dispatch_icall
0x14004f126  mov     esi, eax
0x14004f128  test    eax, eax
0x14004f12a  js      loc_14004F2FE
0x14004f130  xor     esi, esi
0x14004f132  lea     ebx, [rsi+4]
0x14004f135  cmp     esi, [rbp+4Fh+var_88]
0x14004f138  jnb     loc_14004F486
0x14004f13e  mov     r15d, esi
0x14004f141  lea     rax, [rsi+rsi*2]
0x14004f145  cmp     r13d, 2
0x14004f149  jnz     short loc_14004F181
0x14004f14b  mov     rcx, [rbp+4Fh+var_90]
0x14004f14f  lea     rdx, GUID_BUS_TYPE_PCI; Source2
0x14004f156  mov     r8d, 10h; Length
0x14004f15c  lea     r13, [rcx+rax*8]
0x14004f160  mov     rcx, r13; Source1
0x14004f163  call    cs:__imp_RtlCompareMemory
0x14004f16a  nop     dword ptr [rax+rax+00h]
0x14004f16f  cmp     rax, 10h
0x14004f173  jnz     short loc_14004F17B
0x14004f175  test    [r13+10h], bl
0x14004f179  jnz     short loc_14004F197
0x14004f17b  mov     r13d, [rbp+4Fh+var_9C]
0x14004f17f  jmp     short loc_14004F1AB
0x14004f181  cmp     r13d, 1
0x14004f185  jz      short loc_14004F1A0
0x14004f187  test    r13d, r13d
0x14004f18a  jnz     short loc_14004F1AB
0x14004f18c  mov     rcx, [rbp+4Fh+var_90]
0x14004f190  test    byte ptr [rcx+rax*8+10h], 1
0x14004f195  jz      short loc_14004F1AB
0x14004f197  lea     rax, [r14+17D0h]
0x14004f19e  jmp     short loc_14004F1B6
0x14004f1a0  mov     rcx, [rbp+4Fh+var_90]
0x14004f1a4  test    byte ptr [rcx+rax*8+10h], 2
0x14004f1a9  jnz     short loc_14004F1AF
0x14004f1ab  inc     esi
0x14004f1ad  jmp     short loc_14004F135
0x14004f1af  lea     rax, [r14+17D4h]
0x14004f1b6  mov     r13d, [rax]
0x14004f1b9  lea     r9, [rbp+4Fh+var_60]
0x14004f1bd  mov     rcx, [r14+1540h]
0x14004f1c4  lea     r8, [rbp+4Fh+var_78]
0x14004f1c8  xor     eax, eax
0x14004f1ca  lea     rdx, [rbp+4Fh+var_A0]
0x14004f1ce  mov     [rbp+4Fh+var_A0], al
0x14004f1d1  mov     qword ptr [rbp+4Fh+var_78], rax
0x14004f1d5  mov     qword ptr [rbp+4Fh+var_60], rax
0x14004f1d9  mov     [rbp+4Fh+var_80], rax
0x14004f1dd  mov     rax, [rcx+48h]
0x14004f1e1  mov     rcx, [rcx+8]
0x14004f1e5  call    _guard_dispatch_icall
0x14004f1ea  mov     esi, eax
0x14004f1ec  test    eax, eax
0x14004f1ee  js      loc_14004F2F6
0x14004f1f4  cmp     [rbp+4Fh+var_A0], 0
0x14004f1f8  jz      short loc_14004F210
0x14004f1fa  mov     r13d, [rbp+4Fh+var_9C]
0x14004f1fe  mov     r12d, 0C0000184h
0x14004f204  mov     r15, [rbp+4Fh+var_90]
0x14004f208  mov     esi, r12d
0x14004f20b  jmp     loc_14004F304
0x14004f210  mov     eax, [rbp+4Fh+var_9C]
0x14004f213  and     r12d, 1
0x14004f217  test    eax, eax
0x14004f219  jnz     short loc_14004F223
0x14004f21b  lea     ebx, [rax+1]
0x14004f21e  jmp     loc_14004F37F
0x14004f223  cmp     eax, 2
0x14004f226  jz      loc_14004F37F
0x14004f22c  cmp     eax, 1
0x14004f22f  jnz     loc_14004F37D
0x14004f235  mov     rcx, [rbp+4Fh+var_90]
0x14004f239  lea     rax, [r15+r15*2]
0x14004f23d  mov     esi, 10h
0x14004f242  lea     rdx, GUID_BUS_TYPE_ACPI; Source2
0x14004f249  mov     r8d, esi; Length
0x14004f24c  lea     rbx, [rcx+rax*8]
0x14004f250  mov     rcx, rbx; Source1
0x14004f253  call    cs:__imp_RtlCompareMemory
0x14004f25a  nop     dword ptr [rax+rax+00h]
0x14004f25f  cmp     rax, rsi
0x14004f262  jz      short loc_14004F286
0x14004f264  mov     r8d, esi; Length
0x14004f267  lea     rdx, GUID_BUS_TYPE_PCI; Source2
0x14004f26e  mov     rcx, rbx; Source1
0x14004f271  call    cs:__imp_RtlCompareMemory
0x14004f278  nop     dword ptr [rax+rax+00h]
0x14004f27d  cmp     rax, rsi
0x14004f280  jnz     loc_14004F373
0x14004f286  mov     ebx, 2
0x14004f28b  test    r12b, r12b
0x14004f28e  jnz     short loc_14004F2D9
0x14004f290  mov     dl, 1
0x14004f292  mov     [rbp+4Fh+var_98], 1
0x14004f296  mov     rcx, r14
0x14004f299  call    RaidRequestDIrpForAssociatedUnits
0x14004f29e  mov     esi, eax
0x14004f2a0  cmp     eax, 103h
0x14004f2a5  jnz     short loc_14004F324
0x14004f2a7  mov     rcx, [r14+1840h]
0x14004f2ae  xor     r9d, r9d; Alertable
0x14004f2b1  add     rcx, 20h ; ' '; Object
0x14004f2b5  mov     [rsp+100h+Timeout], 0; Timeout
0x14004f2be  xor     r8d, r8d; WaitMode
0x14004f2c1  xor     edx, edx; WaitReason
0x14004f2c3  call    cs:__imp_KeWaitForSingleObject
0x14004f2ca  nop     dword ptr [rax+rax+00h]
0x14004f2cf  mov     rax, [r14+1840h]
0x14004f2d6  or      dword ptr [rax], 20h
0x14004f2d9  xor     r8d, r8d
0x14004f2dc  lea     rcx, [r14+168h]
0x14004f2e3  lea     edx, [r8+1Bh]
0x14004f2e7  call    RaCallMiniportAdapterControlSafe
0x14004f2ec  mov     esi, eax
0x14004f2ee  test    eax, eax
0x14004f2f0  jns     loc_14004F37F
0x14004f2f6  mov     r13d, [rbp+4Fh+var_9C]
0x14004f2fa  mov     r15, [rbp+4Fh+var_90]
0x14004f2fe  mov     r12d, 0C0000184h
0x14004f304  cmp     cs:UseQPCTime, 0
0x14004f30b  jz      loc_14004F490
  ... truncated ...
```
