# VmsCdpEnumPorts

- ea: `0x140036270`
- end: `0x140036d8c`
- name: `VmsCdpEnumPorts`
- size: `2844`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007b6a0`

## callees

- `0x140027a64`
- `0x140034924`
- `0x140034b9c`
- `0x140034ecc`
- `0x140035058`
- `0x140035c9c`
- `0x1400361dc`
- `0x140036270`
- `0x1400370b4`
- `0x140037714`
- `0x140038120`
- `0x14003833c`
- `0x140038404`
- `0x140038574`
- `0x14003a450`
- `0x14003fc38`
- `0x140040c40`
- `0x1400566f8`
- `0x1400845f8`
- `0x14008497c`
- `0x1400b4e20`
- `0x14018fa58`
- `0x1401bb300`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bbf20`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140036ac1`
- `ntoskrnl!KeReleaseMutex` at `0x140036ac1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400363c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400363c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036575`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036656`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036575`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036656`
- `NDIS!NdisAcquireRWLockRead` at `0x1400364e4`
- `NDIS!NdisAcquireRWLockRead` at `0x140036598`
- `NDIS!NdisAcquireRWLockRead` at `0x1400364e4`
- `NDIS!NdisAcquireRWLockRead` at `0x140036598`
- `NDIS!NdisReleaseRWLock` at `0x140036a6f`
- `NDIS!NdisReleaseRWLock` at `0x140036a8b`
- `NDIS!NdisReleaseRWLock` at `0x1401bc85b`
- `NDIS!NdisReleaseRWLock` at `0x1401bc88c`
- `NDIS!NdisReleaseRWLock` at `0x140036a6f`
- `NDIS!NdisReleaseRWLock` at `0x140036a8b`
- `NDIS!NdisReleaseRWLock` at `0x1401bc85b`
- `NDIS!NdisReleaseRWLock` at `0x1401bc88c`

## pseudocode

```c
__int64 __fastcall VmsCdpEnumPorts(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // esi
  int v5; // eax
  int v6; // edx
  int Record; // eax
  int v8; // edx
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rsi
  int v12; // r14d
  __int64 v13; // rbx
  size_t v14; // r15
  bool v15; // si
  int v16; // edx
  int PortCountUnsafe; // eax
  int v18; // eax
  int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rbx
  int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  __int16 v25; // r10
  int v26; // r8d
  int v27; // ecx
  unsigned __int64 v28; // r14
  int v29; // eax
  int v30; // edx
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // [rsp+0h] [rbp-2C8h] BYREF
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-2A8h]
  __int64 v37; // [rsp+28h] [rbp-2A0h]
  __int64 v38; // [rsp+60h] [rbp-268h]
  int v39; // [rsp+68h] [rbp-260h]
  char v40; // [rsp+70h] [rbp-258h]
  __int64 v41; // [rsp+78h] [rbp-250h]
  __int64 v42; // [rsp+80h] [rbp-248h]
  __int64 v43; // [rsp+88h] [rbp-240h]
  unsigned int inited; // [rsp+100h] [rbp-1C8h] BYREF
  char v45; // [rsp+104h] [rbp-1C4h]
  int v46; // [rsp+108h] [rbp-1C0h]
  bool v47; // [rsp+10Ch] [rbp-1BCh]
  struct _LOCK_STATE_EX v48; // [rsp+110h] [rbp-1B8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+114h] [rbp-1B4h] BYREF
  __int64 v50; // [rsp+118h] [rbp-1B0h] BYREF
  __int64 v51; // [rsp+120h] [rbp-1A8h] BYREF
  unsigned int v52; // [rsp+128h] [rbp-1A0h] BYREF
  __int64 v53; // [rsp+130h] [rbp-198h] BYREF
  __int64 v54; // [rsp+138h] [rbp-190h] BYREF
  __int64 v55; // [rsp+140h] [rbp-188h]
  __int64 *v56; // [rsp+148h] [rbp-180h]
  __int64 v57; // [rsp+150h] [rbp-178h] BYREF
  void *Buf1; // [rsp+158h] [rbp-170h]
  int v59; // [rsp+160h] [rbp-168h] BYREF
  __int64 v60; // [rsp+168h] [rbp-160h]
  __int64 v61; // [rsp+170h] [rbp-158h]
  wchar_t *v62; // [rsp+178h] [rbp-150h]
  __int128 v63; // [rsp+180h] [rbp-148h] BYREF
  _BYTE v64[256]; // [rsp+190h] [rbp-138h] BYREF

  v56 = &v35;
  v54 = a1;
  v62 = (wchar_t *)a3;
  v53 = 0;
  v50 = 0;
  v63 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v48.OldIrql = 0;
  v48.Flags = 0;
  inited = 0;
  v59 = 0;
  v52 = 0;
  memset(v64, 0, 0xFEu);
  v57 = 16646144;
  Buf1 = v64;
  VmsWppTraceApi(
    (unsigned int)&v54,
    (unsigned int)"VmsCdpEnumPorts",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlport.c",
    933,
    4,
    0,
    0,
    1,
    1);
  v61 = *(_QWORD *)(a3 + 184);
  v4 = *(_DWORD *)(v61 + 24);
  v51 = 0;
  v50 = 0;
  v53 = 0;
  v45 = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v5 = LibIoctlInitializeOperation(a3, &v51);
  inited = v5;
  if ( v5 < 0 )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v6, 20, 31, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, v5);
    v46 = 1;
  }
  else
  {
    Record = LibIoctlGetRecordEx(v51, v6, 19, (unsigned int)&v59, (__int64)&v52, 0, (__int64)&v50);
    inited = Record;
    if ( Record < 0 )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v8, 20, 32, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, Record);
      v46 = 5;
    }
    else if ( v52 < 0x100 )
    {
      inited = -1073741811;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v8, 20, 33, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, v52);
      v46 = 10;
    }
    else
    {
      inited = VmsUtilInitUnicodeStringSafe(&v63, v50, 256);
      if ( inited )
      {
        inited = -1073741811;
        v46 = 20;
      }
      else
      {
        inited = VmsUtilUpcaseUnicodeString(&v57, &v63);
        if ( inited )
        {
          v46 = 25;
        }
        else
        {
          LODWORD(v55) = v4 | 0x2000;
          v11 = 0;
          v60 = 0;
          v46 = 0;
          v45 = 1;
          if ( (v54 & 1) != 0 )
            WPP_RECORDER_SF_sddsS(
              v50,
              v9,
              v10,
              34,
              (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids,
              (__int64)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlport.c",
              241,
              ((unsigned int)v54 >> 2) & 0x7F,
              (__int64)"VmsCdpEnumPorts",
              v50);
          NdisAcquireRWLockRead(VmsOmObjectListLock, &LockState, 0);
          v12 = -1073741772;
          v13 = VmsOmSwitchList;
          v14 = (unsigned __int16)v57;
          while ( (__int64 *)v13 != &VmsOmSwitchList )
          {
            v15 = 0;
            v47 = 0;
            if ( (_WORD)v14 == *(_WORD *)(v13 + 72) )
            {
              v15 = memcmp(Buf1, *(const void **)(v13 + 80), v14) == 0;
              v47 = v15;
            }
            if ( v15 )
            {
              v12 = 0;
              v11 = v13;
              v60 = v13;
              break;
            }
            v13 = *(_QWORD *)v13;
            v11 = 0;
          }
          inited = v12;
          if ( v12 )
          {
            inited = -1073741766;
            v46 = 30;
            local_unwind_0(v56, &loc_140036A97);
          }
          else
          {
            if ( KeGetCurrentIrql() != 2 )
              goto LABEL_19;
            while ( 1 )
            {
              NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v11 + 56), &v48, 1u);
              PortCountUnsafe = VmsOmSwitchGetPortCountUnsafe(v11);
              if ( (_DWORD)v55 == 2236448 )
              {
                v21 = PortCountUnsafe;
                v28 = *(unsigned int *)(v61 + 8);
                if ( v28 < 9528LL * PortCountUnsafe )
                {
                  inited = -1073741789;
                  v46 = 40;
                  local_unwind_0(v56, &loc_140036A97);
                }
                VmsOmAssertIoctlMutexIsHeld();
                v29 = LibIoctlSetOutputFixedSizeIfLegacy(v51, 18, v28 < 9544 * v21 ? 9528 : 9544);
                inited = v29;
                if ( v29 < 0 )
                  break;
              }
              v18 = LibIoctlAddArrayRecordEx(v51, 18, 4, 9547);
              inited = v18;
              if ( v18 >= 0 )
              {
                v20 = v11 + 1416;
                v61 = v11 + 1416;
                v21 = *(_QWORD *)(v11 + 1416);
                goto LABEL_22;
              }
              LOBYTE(v19) = 2;
              WPP_RECORDER_SF_d(VmsIfrLog, v19, 20, 36, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, v18);
              v46 = 60;
              local_unwind_0(v56, &loc_140036A97);
LABEL_19:
              WPP_RECORDER_SF_s(
                VmsIfrLog,
                v16,
                19,
                24,
                (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
                (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
              if ( KeGetCurrentIrql() != 2 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM();
            }
            LOBYTE(v30) = 2;
            WPP_RECORDER_SF_d(VmsIfrLog, v30, 20, 35, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, v29);
            v46 = 50;
            v22 = local_unwind_0(v56, &loc_140036A97);
LABEL_36:
            if ( v22 == -1073741789 )
            {
              while ( 1 )
              {
                v21 = *(_QWORD *)v21;
                v20 = v61;
LABEL_22:
                v55 = v21;
                if ( v21 == v20 )
                  break;
                if ( (unsigned __int16)*(_DWORD *)(v21 + 10536) != 6 )
                {
                  v22 = LibIoctlAddArrayRecordElement(v51, 0, &v53);
                  inited = v22;
                  if ( v22 >= 0 )
                  {
                    VmsCdpCopyPortInfo(v21, v53);
                    v24 = v54;
                    if ( (v54 & 1) != 0 )
                    {
                      WPP_RECORDER_SF_sddsSSSSdcSSSSDDDDccDDDcDD(
                        *(_DWORD *)(v53 + 1536),
                        *(unsigned __int16 *)(v53 + 4398),
                        v53 + 4102,
                        38,
                        (__int64)Timeout,
                        v37,
                        106,
                        ((unsigned int)v54 >> 2) & 0x7F,
                        (__int64)"VmsCdpEnumPorts",
                        v53,
                        v53 + 256,
                        v53 + 768,
                        v53 + 1024,
                        *(_DWORD *)(v53 + 1536),
                        *(_BYTE *)(v53 + 1540),
                        v53 + 1542,
                        v53 + 1798,
                        v53 + 3846,
                        v53 + 4102,
                        *(_DWORD *)(v53 + 4360),
                        *(_DWORD *)(v53 + 4368),
                        *(_DWORD *)(v53 + 4372),
                        *(_DWORD *)(v53 + 4376),
                        *(_BYTE *)(v53 + 4380),
                        *(_BYTE *)(v53 + 4381),
                        *(_DWORD *)(v53 + 4384),
                        *(_DWORD *)(v53 + 4388),
                        *(_DWORD *)(v53 + 4392),
                        *(_BYTE *)(v53 + 4396),
                        *(_WORD *)(v53 + 4398),
                        *(_WORD *)(v53 + 4400));
                      v24 = v54;
                      v21 = v55;
                    }
                    if ( (v24 & 1) != 0 )
                    {
                      v25 = *(_WORD *)(v53 + 9526);
                      v26 = (unsigned __int16)*(_DWORD *)(v53 + 9524);
                      LODWORD(v43) = *(_DWORD *)(v53 + 9540);
                      LODWORD(v42) = *(_DWORD *)(v53 + 9536);
                      LODWORD(v41) = *(_DWORD *)(v53 + 9532);
                      v27 = v41;
                      v40 = *(_BYTE *)(v53 + 9531);
                      LOBYTE(v39) = *(_BYTE *)(v53 + 9530);
                      LOBYTE(v38) = *(_BYTE *)(v53 + 9529);
                      LOBYTE(v27) = *(_BYTE *)(v53 + 9528);
                      WPP_RECORDER_SF_sddsDDccccDDd(
                        v27,
                        v53,
                        v26,
                        39,
                        (_DWORD)Timeout,
                        v37,
                        107,
                        (v24 >> 2) & 0x7F,
                        (__int64)"VmsCdpEnumPorts",
                        v26,
                        v25,
                        v27,
                        v38,
                        v39,
                        v40,
                        v41,
                        v42,
                        v43);
                    }
                  }
                  else if ( v22 != -2147483643 )
                  {
                    goto LABEL_36;
                  }
                }
              }
            }
            else
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_d(VmsIfrLog, v23, 20, 37, (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids, v22);
              v46 = 60;
              local_unwind_0(v56, &loc_140036A97);
            }
          }
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v60 + 56), &v48);
          NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
        }
      }
    }
  }
  if ( inited )
  {
    if ( inited == -2147483643 || inited == -1073741789 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_Sd(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          4,
          40,
          (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids,
          v50,
          inited);
    }
    else
    {
      v32 = v46;
      WPP_RECORDER_SF_SDd(
        inited,
        v9,
        v10,
        41,
        (__int64)WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids,
        v50,
        v46,
        inited);
      VmsEtwTracePortOperationFailure(
        (unsigned __int64)&v57 & -(__int64)(v45 != 0),
        v33,
        v34,
        &inited,
        v32,
        0,
        0,
        0,
        (unsigned __int64)&v57 & -(__int64)(v45 != 0),
        0);
    }
  }
  LibIoctlFinalizeAndDeinitializeOperationEx(v51, 0);
  KeReleaseMutex(&VmsOmIoctlMutex, 0);
  ExecMonitorOperationContextInfoUpdate(
    v62,
    1,
    5,
    (const UNICODE_STRING *)((unsigned __int64)&v57 & -(__int64)(v45 != 0)),
    0,
    0,
    0,
    0);
  VmsWppTraceApi(
    (unsigned int)&v54,
    (unsigned int)"VmsCdpEnumPorts",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\ctl\\vmsctlport.c",
    1193,
    4,
    inited,
    1,
    0,
    0);
  return inited;
}

```

## disassembly

```asm
0x140036270  mov     r11, rsp
0x140036273  mov     [r11+10h], rbx
0x140036277  mov     [r11+20h], rsi
0x14003627b  push    rdi
0x14003627c  push    r12
0x14003627e  push    r13
0x140036280  push    r14
0x140036282  push    r15
0x140036284  sub     rsp, 2A0h
0x14003628b  mov     rax, cs:__security_cookie
0x140036292  xor     rax, rsp
0x140036295  mov     [rsp+2C8h+var_38], rax
0x14003629d  mov     [rsp+2C8h+var_180], rsp
0x1400362a5  mov     rbx, r8
0x1400362a8  mov     [r11-190h], rcx
0x1400362af  mov     [rsp+2C8h+var_150], rbx
0x1400362b7  xor     r12d, r12d
0x1400362ba  mov     [r11-198h], r12
0x1400362c1  mov     [r11-1B0h], r12
0x1400362c8  xorps   xmm0, xmm0
0x1400362cb  movups  [rsp+2C8h+var_148], xmm0
0x1400362d3  xor     eax, eax
0x1400362d5  mov     word ptr [rsp+2C8h+LockState.OldIrql], ax
0x1400362dd  mov     [rsp+2C8h+LockState.Flags], al
0x1400362e4  mov     word ptr [rsp+2C8h+var_1B8.OldIrql], ax
0x1400362ec  mov     [rsp+2C8h+var_1B8.Flags], al
0x1400362f3  mov     [r11-1C8h], r12d
0x1400362fa  mov     [r11-168h], r12d
0x140036301  mov     [r11-1A0h], r12d
0x140036308  xor     edx, edx; Val
0x14003630a  mov     r8d, 0FEh; Size
0x140036310  lea     rcx, [r11-138h]; void *
0x140036317  call    memset
0x14003631c  mov     [rsp+2C8h+var_178], 0FE0000h
0x140036328  lea     rax, [rsp+2C8h+var_138]
0x140036330  mov     [rsp+2C8h+Buf1], rax
0x140036338  lea     edi, [r12+1]
0x14003633d  mov     byte ptr [rsp+2C8h+var_288], dil
0x140036342  mov     byte ptr [rsp+2C8h+var_290], dil
0x140036347  mov     byte ptr [rsp+2C8h+var_298], r12b
0x14003634c  mov     dword ptr [rsp+2C8h+var_2A0], r12d
0x140036351  mov     byte ptr [rsp+2C8h+Timeout], 4
0x140036356  mov     r9d, 3A5h
0x14003635c  lea     r14, aOnecoreVmDvNet_3; "onecore\\vm\\dv\\net\\nvsp\\driver\\ctl"...
0x140036363  mov     r8, r14
0x140036366  lea     r15, aVmscdpenumport_0; "VmsCdpEnumPorts"
0x14003636d  mov     rdx, r15
0x140036370  lea     rcx, [rsp+2C8h+var_190]
0x140036378  call    VmsWppTraceApi
0x14003637d  mov     rax, [rbx+0B8h]
0x140036384  mov     [rsp+2C8h+var_158], rax
0x14003638c  mov     esi, [rax+18h]
0x14003638f  mov     [rsp+2C8h+var_1A8], r12
0x140036397  mov     [rsp+2C8h+var_1B0], r12
0x14003639f  mov     [rsp+2C8h+var_198], r12
0x1400363a7  mov     [rsp+2C8h+var_1C4], r12b
0x1400363af  mov     [rsp+2C8h+Timeout], r12; Timeout
0x1400363b4  xor     r9d, r9d; Alertable
0x1400363b7  xor     r8d, r8d; WaitMode
0x1400363ba  xor     edx, edx; WaitReason
0x1400363bc  lea     rcx, VmsOmIoctlMutex; Object
0x1400363c3  call    cs:__imp_KeWaitForSingleObject
0x1400363ca  nop     dword ptr [rax+rax+00h]
0x1400363cf  lea     rdx, [rsp+2C8h+var_1A8]
0x1400363d7  mov     rcx, rbx
0x1400363da  call    LibIoctlInitializeOperation
0x1400363df  mov     [rsp+2C8h+var_1C8], eax
0x1400363e6  test    eax, eax
0x1400363e8  js      loc_140036C2D
0x1400363ee  lea     rax, [rsp+2C8h+var_1B0]
0x1400363f6  mov     [rsp+2C8h+var_298], rax
0x1400363fb  mov     [rsp+2C8h+var_2A0], r12
0x140036400  lea     rax, [rsp+2C8h+var_1A0]
0x140036408  mov     [rsp+2C8h+Timeout], rax
0x14003640d  lea     r9, [rsp+2C8h+var_168]
0x140036415  lea     r8d, [r12+13h]
0x14003641a  mov     rcx, [rsp+2C8h+var_1A8]
0x140036422  call    LibIoctlGetRecordEx
0x140036427  mov     [rsp+2C8h+var_1C8], eax
0x14003642e  test    eax, eax
0x140036430  js      loc_140036C61
0x140036436  mov     eax, [rsp+2C8h+var_1A0]
0x14003643d  mov     r8d, 100h
0x140036443  cmp     eax, r8d
0x140036446  jb      loc_140036C99
0x14003644c  mov     rdx, [rsp+2C8h+var_1B0]
0x140036454  lea     rcx, [rsp+2C8h+var_148]
0x14003645c  call    VmsUtilInitUnicodeStringSafe
0x140036461  mov     [rsp+2C8h+var_1C8], eax
0x140036468  test    eax, eax
0x14003646a  jnz     loc_140036CDC
0x140036470  lea     rdx, [rsp+2C8h+var_148]
0x140036478  lea     rcx, [rsp+2C8h+var_178]
0x140036480  call    VmsUtilUpcaseUnicodeString
0x140036485  mov     [rsp+2C8h+var_1C8], eax
0x14003648c  test    eax, eax
0x14003648e  jnz     loc_140036BD8
0x140036494  bts     esi, 0Dh
0x140036498  mov     dword ptr [rsp+2C8h+var_188], esi
0x14003649f  mov     esi, r12d
0x1400364a2  mov     [rsp+2C8h+var_160], r12
0x1400364aa  mov     [rsp+2C8h+var_1C0], r12d
0x1400364b2  mov     [rsp+2C8h+var_1C4], dil
0x1400364ba  mov     rax, [rsp+2C8h+var_190]
0x1400364c2  test    dil, al
0x1400364c5  jnz     loc_140036BE8
0x1400364cb  lea     r13, WPP_4612b5fb516632bcd2da8faa15e2eb5d_Traceguids
0x1400364d2  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400364d9  xor     r8d, r8d; Flags
0x1400364dc  lea     rdx, [rsp+2C8h+LockState]; LockState
0x1400364e4  call    cs:__imp_NdisAcquireRWLockRead
0x1400364eb  nop     dword ptr [rax+rax+00h]
0x1400364f0  mov     r14d, 0C0000034h
0x1400364f6  lea     rax, VmsOmSwitchList
0x1400364fd  mov     rbx, cs:VmsOmSwitchList
0x140036504  movzx   r15d, word ptr [rsp+2C8h+var_178]
0x14003650d  cmp     rbx, rax
0x140036510  jz      short loc_140036564
0x140036512  movzx   esi, r12b
0x140036516  mov     [rsp+2C8h+var_1BC], sil
0x14003651e  cmp     r15w, [rbx+48h]
0x140036523  jnz     short loc_14003654D
0x140036525  mov     r8, r15; Size
0x140036528  mov     rdx, [rbx+50h]; Buf2
0x14003652c  mov     rcx, [rsp+2C8h+Buf1]; Buf1
0x140036534  call    memcmp
0x140036539  test    eax, eax
0x14003653b  cmovz   esi, edi
0x14003653e  mov     [rsp+2C8h+var_1BC], sil
0x140036546  lea     rax, VmsOmSwitchList
0x14003654d  cmp     sil, dil
0x140036550  jnz     loc_140036A26
0x140036556  mov     r14d, r12d
0x140036559  mov     rsi, rbx
0x14003655c  mov     [rsp+2C8h+var_160], rbx
0x140036564  mov     [rsp+2C8h+var_1C8], r14d
0x14003656c  test    r14d, r14d
0x14003656f  jnz     loc_140036A31
0x140036575  call    cs:__imp_KeGetCurrentIrql
0x14003657c  nop     dword ptr [rax+rax+00h]
0x140036581  cmp     al, 2
0x140036583  jnz     loc_140036628
0x140036589  mov     r8b, dil; Flags
0x14003658c  lea     rdx, [rsp+2C8h+var_1B8]; LockState
0x140036594  mov     rcx, [rsi+38h]; Lock
0x140036598  call    cs:__imp_NdisAcquireRWLockRead
0x14003659f  nop     dword ptr [rax+rax+00h]
0x1400365a4  mov     rcx, rsi
0x1400365a7  call    VmsOmSwitchGetPortCountUnsafe
0x1400365ac  cmp     dword ptr [rsp+2C8h+var_188], 222020h
0x1400365b7  jz      loc_140036916
0x1400365bd  mov     edx, 12h
0x1400365c2  mov     r9d, 254Bh
0x1400365c8  lea     r8d, [rdx-0Eh]
0x1400365cc  mov     rcx, [rsp+2C8h+var_1A8]
0x1400365d4  call    LibIoctlAddArrayRecordEx
0x1400365d9  mov     [rsp+2C8h+var_1C8], eax
0x1400365e0  test    eax, eax
0x1400365e2  jns     loc_140036674
0x1400365e8  mov     r9d, 24h ; '$'
0x1400365ee  mov     dword ptr [rsp+2C8h+var_2A0], eax
0x1400365f2  mov     [rsp+2C8h+Timeout], r13
0x1400365f7  lea     r8d, [r9-10h]
0x1400365fb  mov     dl, 2
0x1400365fd  mov     rcx, cs:VmsIfrLog
0x140036604  call    WPP_RECORDER_SF_d
0x140036609  mov     [rsp+2C8h+var_1C0], 3Ch ; '<'
0x140036614  lea     rdx, loc_140036A97
0x14003661b  mov     rcx, [rsp+2C8h+var_180]
0x140036623  call    _local_unwind_0
0x140036628  mov     r9d, 18h
0x14003662e  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x140036635  mov     [rsp+2C8h+var_2A0], rax
0x14003663a  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140036641  mov     [rsp+2C8h+Timeout], rax
0x140036646  lea     r8d, [r9-5]
0x14003664a  mov     rcx, cs:VmsIfrLog
0x140036651  call    WPP_RECORDER_SF_s
0x140036656  call    cs:__imp_KeGetCurrentIrql
0x14003665d  nop     dword ptr [rax+rax+00h]
0x140036662  cmp     al, 2
0x140036664  jz      loc_140036589
0x14003666a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14003666f  jmp     loc_140036589
0x140036674  lea     rax, [rsi+588h]
0x14003667b  mov     [rsp+2C8h+var_158], rax
0x140036683  mov     rbx, [rax]
0x140036686  mov     [rsp+2C8h+var_188], rbx
0x14003668e  cmp     rbx, rax
0x140036691  jz      loc_140036A24
0x140036697  mov     eax, [rbx+2928h]
0x14003669d  cmp     ax, 6
0x1400366a1  jz      loc_1400367A4
0x1400366a7  lea     r8, [rsp+2C8h+var_198]
0x1400366af  xor     edx, edx
0x1400366b1  mov     rcx, [rsp+2C8h+var_1A8]
0x1400366b9  call    LibIoctlAddArrayRecordElement
0x1400366be  mov     [rsp+2C8h+var_1C8], eax
0x1400366c5  test    eax, eax
0x1400366c7  jns     short loc_1400366E1
0x1400366c9  cmp     eax, 80000005h
0x1400366ce  jnz     loc_1400369D9
0x1400366d4  mov     rbx, [rbx]
0x1400366d7  mov     rax, [rsp+2C8h+var_158]
0x1400366df  jmp     short loc_140036686
0x1400366e1  mov     rdx, [rsp+2C8h+var_198]
0x1400366e9  mov     rcx, rbx
0x1400366ec  call    VmsCdpCopyPortInfo
0x1400366f1  mov     rax, [rsp+2C8h+var_190]
0x1400366f9  test    dil, al
0x1400366fc  jnz     loc_1400367A9
0x140036702  lea     rsi, aVmscdpenumport_0; "VmsCdpEnumPorts"
0x140036709  test    dil, al
0x14003670c  jz      loc_1400367A4
0x140036712  mov     rdx, [rsp+2C8h+var_198]
0x14003671a  movzx   r10d, word ptr [rdx+2536h]
0x140036722  mov     ecx, [rdx+2534h]
0x140036728  movzx   r8d, cx
0x14003672c  shr     eax, 2
0x14003672f  and     eax, 7Fh
0x140036732  mov     r9d, 27h ; '''
0x140036738  mov     ecx, [rdx+2544h]
0x14003673e  mov     dword ptr [rsp+2C8h+var_240], ecx
0x140036745  mov     ecx, [rdx+2540h]
0x14003674b  mov     dword ptr [rsp+2C8h+var_248], ecx
0x140036752  mov     ecx, [rdx+253Ch]
0x140036758  mov     dword ptr [rsp+2C8h+var_250], ecx
0x14003675c  mov     cl, [rdx+253Bh]
0x140036762  mov     [rsp+2C8h+var_258], cl
0x140036766  mov     cl, [rdx+253Ah]
0x14003676c  mov     byte ptr [rsp+2C8h+var_260], cl
0x140036770  mov     cl, [rdx+2539h]
0x140036776  mov     byte ptr [rsp+2C8h+var_268], cl
0x14003677a  mov     cl, [rdx+2538h]
0x140036780  mov     byte ptr [rsp+2C8h+var_270], cl
0x140036784  mov     dword ptr [rsp+2C8h+var_278], r10d
0x140036789  mov     dword ptr [rsp+2C8h+var_280], r8d
0x14003678e  mov     [rsp+2C8h+var_288], rsi
0x140036793  mov     dword ptr [rsp+2C8h+var_290], eax
0x140036797  mov     dword ptr [rsp+2C8h+var_298], 46Bh
0x14003679f  call    WPP_RECORDER_SF_sddsDDccccDDd
0x1400367a4  jmp     loc_1400366D4
0x1400367a9  mov     r15, [rsp+2C8h+var_198]
0x1400367b1  movzx   ecx, word ptr [r15+1130h]
0x1400367b9  movzx   edx, word ptr [r15+112Eh]
0x1400367c1  lea     r8, [r15+1006h]
0x1400367c8  lea     r10, [r15+0F06h]
0x1400367cf  lea     r11, [r15+706h]
0x1400367d6  lea     rbx, [r15+606h]
0x1400367dd  lea     rdi, [r15+400h]
0x1400367e4  lea     rsi, [r15+300h]
0x1400367eb  lea     r14, [r15+100h]
0x1400367f2  shr     eax, 2
0x1400367f5  and     eax, 7Fh
0x1400367f8  mov     r9d, 26h ; '&'
0x1400367fe  mov     [rsp+2C8h+var_1D8], ecx
0x140036805  mov     [rsp+2C8h+var_1E0], edx
0x14003680c  mov     cl, [r15+112Ch]
0x140036813  mov     [rsp+2C8h+var_1E8], cl
0x14003681a  mov     ecx, [r15+1128h]
0x140036821  mov     [rsp+2C8h+var_1F0], ecx
0x140036828  mov     ecx, [r15+1124h]
0x14003682f  mov     [rsp+2C8h+var_1F8], ecx
0x140036836  mov     ecx, [r15+1120h]
0x14003683d  mov     [rsp+2C8h+var_200], ecx
0x140036844  mov     cl, [r15+111Dh]
0x14003684b  mov     [rsp+2C8h+var_208], cl
0x140036852  mov     cl, [r15+111Ch]
0x140036859  mov     [rsp+2C8h+var_210], cl
0x140036860  mov     ecx, [r15+1118h]
0x140036867  mov     [rsp+2C8h+var_218], ecx
0x14003686e  mov     ecx, [r15+1114h]
0x140036875  mov     [rsp+2C8h+var_220], ecx
0x14003687c  mov     ecx, [r15+1110h]
0x140036883  mov     [rsp+2C8h+var_228], ecx
0x14003688a  mov     ecx, [r15+1108h]
0x140036891  mov     [rsp+2C8h+var_230], ecx
0x140036898  mov     [rsp+2C8h+var_238], r8
0x1400368a0  mov     [rsp+2C8h+var_240], r10
0x1400368a8  mov     [rsp+2C8h+var_248], r11
0x1400368b0  mov     [rsp+2C8h+var_250], rbx
0x1400368b5  mov     cl, [r15+604h]
0x1400368bc  mov     [rsp+2C8h+var_258], cl
0x1400368c0  mov     ecx, [r15+600h]
0x1400368c7  mov     [rsp+2C8h+var_260], ecx
0x1400368cb  mov     [rsp+2C8h+var_268], rdi
0x1400368d0  mov     [rsp+2C8h+var_270], rsi
0x1400368d5  mov     [rsp+2C8h+var_278], r14
0x1400368da  mov     [rsp+2C8h+var_280], r15
0x1400368df  lea     rsi, aVmscdpenumport_0; "VmsCdpEnumPorts"
0x1400368e6  mov     [rsp+2C8h+var_288], rsi
0x1400368eb  mov     dword ptr [rsp+2C8h+var_290], eax
0x1400368ef  mov     dword ptr [rsp+2C8h+var_298], 46Ah
0x1400368f7  call    WPP_RECORDER_SF_sddsSSSSdcSSSSDDDDccDDDcDD
0x1400368fc  mov     rax, [rsp+2C8h+var_190]
0x140036904  mov     edi, 1
0x140036909  mov     rbx, [rsp+2C8h+var_188]
0x140036911  jmp     loc_140036709
0x140036916  movsxd  rbx, eax
0x140036919  mov     rax, [rsp+2C8h+var_158]
  ... truncated ...
```
