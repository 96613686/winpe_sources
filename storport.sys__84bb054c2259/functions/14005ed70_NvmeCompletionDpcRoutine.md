# NvmeCompletionDpcRoutine

- ea: `0x14005ed70`
- end: `0x140060496`
- name: `NvmeCompletionDpcRoutine`
- size: `5926`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14009da30`
- `0x140112880`
- `0x14012f440`
- `0x140136064`

## callees

- `0x14003e8b0`
- `0x1400407e0`
- `0x140044110`
- `0x140044f10`
- `0x14005ed70`
- `0x140065dc0`
- `0x1400da868`
- `0x140116220`
- `0x140131650`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005f128`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb7f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fdbc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005ff6e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005f128`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fb7f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005fdbc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005ff6e`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f25a`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f2aa`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f9e5`
- `ntoskrnl!PoFxIdleComponent` at `0x14005fce9`
- `ntoskrnl!PoFxIdleComponent` at `0x14005fd38`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f25a`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f2aa`
- `ntoskrnl!PoFxIdleComponent` at `0x14005f9e5`
- `ntoskrnl!PoFxIdleComponent` at `0x14005fce9`
- `ntoskrnl!PoFxIdleComponent` at `0x14005fd38`
- `ntoskrnl!EtwWriteEx` at `0x14005f769`
- `ntoskrnl!EtwWriteEx` at `0x1400603fd`
- `ntoskrnl!EtwWriteEx` at `0x14005f769`
- `ntoskrnl!EtwWriteEx` at `0x1400603fd`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14005f233`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14005fcc3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14005f233`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14005fcc3`
- `ntoskrnl!KeLowerIrql` at `0x14005f0ec`
- `ntoskrnl!KeLowerIrql` at `0x14005fb33`
- `ntoskrnl!KeLowerIrql` at `0x14005f0ec`
- `ntoskrnl!KeLowerIrql` at `0x14005fb33`
- `ntoskrnl!KfRaiseIrql` at `0x14005f0ad`
- `ntoskrnl!KfRaiseIrql` at `0x14005faf7`
- `ntoskrnl!KfRaiseIrql` at `0x14005f0ad`
- `ntoskrnl!KfRaiseIrql` at `0x14005faf7`
- `ntoskrnl!IofCompleteRequest` at `0x14005f1cb`
- `ntoskrnl!IofCompleteRequest` at `0x14005fc62`
- `ntoskrnl!IofCompleteRequest` at `0x14005f1cb`
- `ntoskrnl!IofCompleteRequest` at `0x14005fc62`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005f283`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005fd11`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005f283`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005fd11`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ee64`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005f80f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005ee64`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005f80f`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14005fbf5`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14005fbf5`
- `ntoskrnl!IoRecordIoAttribution` at `0x14005fc19`
- `ntoskrnl!IoRecordIoAttribution` at `0x14005fc19`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14005fba0`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14005fba0`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14005f8ad`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14005f8ad`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x14005fab2`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x14005fab2`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005fde9`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005fde9`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14005fa78`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14005fa78`

## string_xrefs

- `0x14005f68c`: `Command status`
- `0x14005f5b6`: `NVMe command failed`
- `0x140060240`: `Invalid command ID in CQ entry`

## pseudocode

```c
void __fastcall NvmeCompletionDpcRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        volatile signed __int32 *SystemArgument1,
        char *SystemArgument2)
{
  char *v4; // r12
  volatile signed __int32 *v5; // r13
  char v6; // al
  unsigned int v7; // edi
  _WORD *v8; // rsi
  ULONG CurrentProcessorNumber; // eax
  __int16 v10; // cx
  __int16 v11; // dx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r10
  signed __int32 v19; // r9d
  __int64 v20; // rax
  char v21; // cl
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // r8
  PIRP v25; // rdx
  _QWORD *v26; // r12
  _LARGE_INTEGER ByteOffset; // r15
  unsigned __int16 v28; // si
  __int64 v29; // r13
  unsigned __int8 v30; // r14
  __int64 v31; // rsi
  KIRQL v32; // al
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // r14
  int v36; // esi
  unsigned __int64 v37; // rax
  PIRP v38; // r8
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 v41; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v42; // rcx
  __int64 v43; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // r8
  PIRP v49; // rsi
  int v50; // edx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r9
  __int64 v54; // rdx
  bool v55; // zf
  __int64 v56; // rcx
  unsigned __int64 v57; // rax
  __int64 v58; // rax
  const wchar_t *v59; // r8
  unsigned int v60; // eax
  __int64 v61; // rcx
  const wchar_t *v62; // rdx
  __int64 v63; // rax
  int v64; // eax
  const int *v65; // rcx
  __int64 v66; // rax
  int v67; // eax
  const int *v68; // rax
  const int *v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  _DWORD *v73; // r14
  unsigned int v74; // edx
  unsigned int v75; // ecx
  __int64 v76; // rdx
  unsigned int v77; // ecx
  __int64 v78; // r8
  unsigned int v79; // edx
  __int64 v80; // rsi
  signed __int32 v81; // ecx
  _QWORD *v82; // rcx
  __int128 v83; // xmm1
  __int64 Namespace; // rax
  __int64 v85; // r10
  __int64 v86; // r14
  __int64 v87; // rdx
  __int64 v88; // rax
  int v89; // r14d
  __int64 v90; // r8
  int GenericIrpExtension; // eax
  __int64 v92; // r9
  __int64 v93; // rbx
  _LARGE_INTEGER v94; // r15
  __int64 v95; // rsi
  unsigned __int8 v96; // r14
  KIRQL v97; // r12
  __int64 v98; // rcx
  unsigned __int64 v99; // rdx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v101; // rbx
  int MajorFunction; // ecx
  __int64 v103; // rax
  ULONG64 UnbiasedInterruptTimePrecise; // rax
  bool v105; // sf
  __int64 v106; // rbx
  __int64 v107; // rdx
  __int64 v108; // rsi
  __int64 v109; // rax
  __int64 v110; // rbx
  __int64 v111; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v112; // rcx
  __int64 v113; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v114; // rcx
  __int64 v115; // rcx
  int v116; // ecx
  __int64 v117; // rcx
  __int64 v118; // rbx
  _IO_STACK_LOCATION *v119; // rax
  unsigned __int64 v120; // rdx
  unsigned int v121; // ecx
  __int64 v122; // rax
  signed __int32 v123; // ebx
  char v124; // cl
  __int64 v125; // rdx
  unsigned __int16 *v126; // r9
  char v127; // al
  __int16 v128; // bx
  unsigned __int64 v129; // r10
  __int64 v130; // r9
  __int64 v131; // rax
  const wchar_t *v132; // rdx
  unsigned int v133; // eax
  __int64 v134; // rcx
  const wchar_t *v135; // r8
  __int64 v136; // r10
  __int64 v137; // rax
  int v138; // eax
  const int *v139; // rcx
  __int64 v140; // rax
  int v141; // eax
  const int *v142; // r11
  const int *v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rax
  signed __int32 v147[8]; // [rsp+0h] [rbp-100h] BYREF
  LPCGUID ActivityId; // [rsp+20h] [rbp-E0h]
  int v149; // [rsp+40h] [rbp-C0h]
  char v150; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v151; // [rsp+46h] [rbp-BAh]
  KIRQL v152; // [rsp+48h] [rbp-B8h]
  int v153; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 v154; // [rsp+50h] [rbp-B0h]
  int v155; // [rsp+54h] [rbp-ACh]
  unsigned int v156; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v157; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v158; // [rsp+68h] [rbp-98h]
  __int64 v159; // [rsp+70h] [rbp-90h]
  __int64 v160; // [rsp+78h] [rbp-88h]
  __int64 v161; // [rsp+80h] [rbp-80h] BYREF
  PVOID Context; // [rsp+88h] [rbp-78h]
  _DWORD *v163; // [rsp+90h] [rbp-70h] BYREF
  PIRP Irp; // [rsp+98h] [rbp-68h] BYREF
  ULONG v165; // [rsp+A0h] [rbp-60h]
  signed __int32 v166; // [rsp+A4h] [rbp-5Ch]
  volatile signed __int32 *v167; // [rsp+A8h] [rbp-58h]
  PIRP v168; // [rsp+B0h] [rbp-50h]
  __int64 v169; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v170; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v171; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v172; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v173; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v174; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v175; // [rsp+E8h] [rbp-18h] BYREF
  PVOID v176; // [rsp+F0h] [rbp-10h]
  GUID v177; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 QpcTimeStamp[2]; // [rsp+108h] [rbp+8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+118h] [rbp+18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+130h] [rbp+30h] BYREF
  __int64 v181; // [rsp+140h] [rbp+40h]
  __int64 v182; // [rsp+148h] [rbp+48h]
  const wchar_t *v183; // [rsp+150h] [rbp+50h]
  int v184; // [rsp+158h] [rbp+58h]
  int v185; // [rsp+15Ch] [rbp+5Ch]
  const int *v186; // [rsp+160h] [rbp+60h]
  int v187; // [rsp+168h] [rbp+68h]
  int v188; // [rsp+16Ch] [rbp+6Ch]
  char *v189; // [rsp+170h] [rbp+70h]
  __int64 v190; // [rsp+178h] [rbp+78h]
  char *v191; // [rsp+180h] [rbp+80h]
  __int64 v192; // [rsp+188h] [rbp+88h]
  const int *v193; // [rsp+190h] [rbp+90h]
  int v194; // [rsp+198h] [rbp+98h]
  int v195; // [rsp+19Ch] [rbp+9Ch]
  char *v196; // [rsp+1A0h] [rbp+A0h]
  int v197; // [rsp+1A8h] [rbp+A8h]
  int v198; // [rsp+1ACh] [rbp+ACh]
  char *v199; // [rsp+1B0h] [rbp+B0h]
  int v200; // [rsp+1B8h] [rbp+B8h]
  int v201; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v202; // [rsp+1C0h] [rbp+C0h]
  __int64 v203; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v204; // [rsp+1D0h] [rbp+D0h]
  __int64 v205; // [rsp+1D8h] [rbp+D8h]
  __int64 *v206; // [rsp+1E0h] [rbp+E0h]
  __int64 v207; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v208; // [rsp+1F0h] [rbp+F0h]
  __int64 v209; // [rsp+1F8h] [rbp+F8h]
  __int64 *v210; // [rsp+200h] [rbp+100h]
  __int64 v211; // [rsp+208h] [rbp+108h]
  const wchar_t *v212; // [rsp+210h] [rbp+110h]
  __int64 v213; // [rsp+218h] [rbp+118h]
  __int64 *v214; // [rsp+220h] [rbp+120h]
  __int64 v215; // [rsp+228h] [rbp+128h]
  const wchar_t *v216; // [rsp+230h] [rbp+130h]
  __int64 v217; // [rsp+238h] [rbp+138h]
  __int64 *v218; // [rsp+240h] [rbp+140h]
  __int64 v219; // [rsp+248h] [rbp+148h]
  const wchar_t *v220; // [rsp+250h] [rbp+150h]
  __int64 v221; // [rsp+258h] [rbp+158h]
  __int64 *v222; // [rsp+260h] [rbp+160h]
  __int64 v223; // [rsp+268h] [rbp+168h]
  const wchar_t *v224; // [rsp+270h] [rbp+170h]
  __int64 v225; // [rsp+278h] [rbp+178h]
  __int64 *v226; // [rsp+280h] [rbp+180h]
  __int64 v227; // [rsp+288h] [rbp+188h]
  const wchar_t *v228; // [rsp+290h] [rbp+190h]
  __int64 v229; // [rsp+298h] [rbp+198h]
  PIRP *p_Irp; // [rsp+2A0h] [rbp+1A0h]
  __int64 v231; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v232; // [rsp+2B0h] [rbp+1B0h]
  __int64 v233; // [rsp+2B8h] [rbp+1B8h]
  __int64 *v234; // [rsp+2C0h] [rbp+1C0h]
  __int64 v235; // [rsp+2C8h] [rbp+1C8h]

  if ( !SystemArgument2 )
    return;
  Context = SystemArgument2;
  v167 = SystemArgument1;
  v4 = SystemArgument2;
  v176 = DeferredContext;
  v5 = SystemArgument1;
  v175 = 0;
  if ( !SystemArgument1 )
    return;
  while ( _InterlockedCompareExchange(SystemArgument1 + 10, 1, 0) )
    ;
  if ( _InterlockedCompareExchange(SystemArgument1 + 11, 1, 0) )
  {
    _InterlockedExchange(SystemArgument1 + 10, 0);
    goto LABEL_189;
  }
  _InterlockedOr(v147, 0);
  _InterlockedExchange(SystemArgument1 + 10, 0);
  _InterlockedOr(v147, 0);
  if ( **((_QWORD **)SystemArgument2 + 164) == 1 )
    goto LABEL_188;
  v6 = SystemArgument2[1728];
  v7 = 0;
  v163 = (_DWORD *)(*(_QWORD *)SystemArgument1 + 16LL * *((unsigned __int16 *)SystemArgument1 + 17));
  v8 = v163;
  v155 = 0;
  v166 = 0;
  v161 = 0;
  v150 = v6;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v10 = *((_WORD *)v5 + 18);
  v11 = v8[7] & 1;
  v165 = CurrentProcessorNumber;
  if ( v11 == v10 )
    goto LABEL_188;
  while ( 1 )
  {
    v12 = (unsigned __int16)v8[5];
    v13 = (unsigned __int16)v8[6];
    v14 = (unsigned __int16)v8[7];
    LOWORD(v153) = v8[4];
    v151 = v12;
    v15 = (_WORD)v12 ? 192 * v12 + *((_QWORD *)v4 + 91) - 192LL : *((_QWORD *)v4 + 89);
    v16 = *(unsigned int *)(v15 + 124);
    v159 = v15;
    v156 = v16 - 1;
    if ( (unsigned int)v13 >= (int)v16 - 1 )
      break;
    v17 = *(_QWORD *)(v15 + 32);
    v18 = v13 << 7;
    v160 = v13;
    v157 = v18;
    *(_BYTE *)(v17 + v18 + 60) &= ~1u;
    if ( (((unsigned int)v14 >> 9) & 7) != 0 )
    {
      if ( (((unsigned int)v14 >> 9) & 7) == 1 )
      {
        switch ( (unsigned __int8)((unsigned int)v14 >> 1) )
        {
          case 0u:
          case 1u:
          case 2u:
          case 3u:
          case 5u:
          case 6u:
          case 7u:
          case 8u:
          case 9u:
          case 0xAu:
          case 0xCu:
          case 0xDu:
          case 0xEu:
          case 0xFu:
          case 0x1Cu:
          case 0x1Fu:
          case 0x20u:
          case 0x21u:
          case 0x22u:
          case 0x80u:
          case 0x81u:
          case 0x83u:
            goto LABEL_19;
          case 0xBu:
          case 0x10u:
          case 0x11u:
            v19 = -2147483210;
            break;
          case 0x12u:
          case 0x13u:
          case 0x16u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
            goto LABEL_21;
          case 0x14u:
            v19 = -1073741800;
            break;
          case 0x1Bu:
            v19 = -1073741637;
            break;
          case 0x1Eu:
          case 0x82u:
            goto LABEL_17;
          default:
            goto LABEL_30;
        }
      }
      else
      {
        if ( (((unsigned int)v14 >> 9) & 7) == 2 && (unsigned __int8)((unsigned int)v14 >> 1) == 134 )
          JUMPOUT(0x14005EF51LL);
LABEL_30:
        v19 = -1073741435;
      }
    }
    else
    {
      switch ( (unsigned __int8)((unsigned int)v14 >> 1) )
      {
        case 0u:
          v19 = 0;
          break;
        case 1u:
        case 2u:
        case 0xBu:
        case 0xDu:
        case 0xEu:
        case 0xFu:
        case 0x10u:
        case 0x11u:
        case 0x12u:
        case 0x13u:
        case 0x16u:
        case 0x18u:
        case 0x1Eu:
        case 0x80u:
        case 0x81u:
        case 0x83u:
LABEL_19:
          v19 = -1073741808;
          break;
        case 5u:
        case 6u:
        case 0x14u:
LABEL_21:
          v19 = -1073741436;
          break;
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
        case 0x1Bu:
          v19 = -1073741248;
          break;
        case 0xCu:
          v19 = -1073740758;
          break;
        case 0x15u:
LABEL_17:
          v19 = -1073741790;
          break;
        case 0x19u:
        case 0x1Au:
          v19 = -1073741643;
          break;
        case 0x82u:
          v19 = -1073741661;
          break;
        default:
          goto LABEL_30;
      }
    }
    v20 = *(_QWORD *)(v15 + 32);
    v149 = v19;
    v21 = *(_BYTE *)(v18 + v20 + 60);
    v22 = *(_QWORD *)(v15 + 32);
    if ( (v21 & 8) != 0 )
    {
      v23 = *(_QWORD *)(v18 + v22 + 40);
      v24 = *(_WORD *)(v18 + v22 + 52);
      v168 = 0;
      v158 = v24;
      v25 = *(PIRP *)(v23 + 24);
      v26 = *(_QWORD **)(v23 + 16);
      Irp = v25;
      ByteOffset = v25->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset;
      v28 = *(_WORD *)(ByteOffset.QuadPart + 32);
      v154 = v28;
      _InterlockedExchange((volatile __int32 *)(v23 + 104), 5);
      *(_DWORD *)(v23 + 112) = v19;
      if ( v19 < 0 )
        _InterlockedCompareExchange((volatile signed __int32 *)(ByteOffset.QuadPart + 112), v19, 0);
      v29 = _InterlockedExchange64((volatile __int64 *)(v23 + 88), 0);
      if ( v29 )
      {
        v169 = *(_QWORD *)(v29 + 24);
        if ( v169 )
        {
          v30 = *(_BYTE *)(v29 + 126) & 1;
          v31 = *(_QWORD *)(v26[2] + 128LL);
          v32 = KfRaiseIrql(2u);
          v33 = *(_QWORD *)(v31 + 1160);
          v152 = v32;
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v33 + 8) + 96LL))(v33, v169, v30 ^ 1u);
          if ( v152 < 2u )
            KeLowerIrql(v152);
          v28 = v154;
        }
        v34 = v26[2];
        *(_QWORD *)(v29 + 24) = 0;
        *(_QWORD *)(v29 + 88) = 0;
        *(_BYTE *)(v29 + 126) = 0;
        ExpInterlockedPushEntrySList(
          *(PSLIST_HEADER *)(*(_QWORD *)(v34 + 896) + 8LL * *(unsigned int *)(v29 + 120)),
          (PSLIST_ENTRY)v29);
        v25 = Irp;
        v24 = v158;
      }
      if ( _InterlockedIncrement((volatile signed __int32 *)(ByteOffset.QuadPart + 116)) >= v28 )
      {
        v35 = v24;
        if ( !_bittest64((const signed __int64 *)(v26[2] + 136LL), 0x20u) && *(_WORD *)(ByteOffset.QuadPart + 120) )
        {
          do
            _mm_pause();
          while ( *(_WORD *)(ByteOffset.QuadPart + 120) );
        }
        v36 = *(_DWORD *)(ByteOffset.QuadPart + 112);
        if ( v36 < 0 )
          v37 = 0;
        else
          v37 = *(unsigned int *)(ByteOffset.QuadPart + 48);
        v25->IoStatus.Information = v37;
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))FreeNVMeChainedIoSplitContext)(
          v26[2],
          v24,
          (_LARGE_INTEGER)ByteOffset.QuadPart,
          v25);
        v38 = Irp;
        if ( (*((_BYTE *)&Irp->Tail.CompletionKey + 31) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(v26[87] + 8 * v35));
        v38->IoStatus.Status = v36;
        IofCompleteRequest(v38, 0);
        v39 = v26[16];
        if ( !*(_BYTE *)v39
          && _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(v39 + 24) + 8 * v35), 0xFFFFFFFF) == 1 )
        {
          v40 = *(_QWORD *)(v26[2] + 128LL);
          v41 = v26[16];
          if ( v41 )
          {
            if ( *(_QWORD *)(v41 + 8) )
            {
              v42 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v41 + 40);
              if ( v42 )
              {
                if ( ExAcquireRundownProtectionCacheAware(v42) )
                {
                  PoFxIdleComponent(**(_QWORD **)(v26[16] + 8LL), 0, 2);
                  v43 = v26[16];
                  if ( v43 )
                  {
                    if ( *(_QWORD *)(v43 + 8) )
                    {
                      v44 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v43 + 40);
                      if ( v44 )
                        ExReleaseRundownProtectionCacheAware(v44);
                    }
                  }
                }
              }
            }
          }
          v45 = *(_QWORD *)(v40 + 168);
          if ( *(_BYTE *)v45 == 1 )
            PoFxIdleComponent(**(_QWORD **)(v45 + 8), 0, 2);
        }
      }
      v5 = v167;
      v4 = (char *)Context;
      v15 = v159;
    }
    else if ( (*(_BYTE *)(v18 + v22 + 60) & 2) != 0 )
    {
      v168 = 0;
    }
    else
    {
      v168 = *(PIRP *)((v13 << 7) + *(_QWORD *)(v15 + 32) + 24);
    }
    v46 = v160;
    v47 = *(_QWORD *)(v15 + 32);
    v48 = *(_QWORD *)((v160 << 7) + v47 + 16);
    if ( v48 )
    {
      *(_QWORD *)((v160 << 7) + v47 + 16) = 0;
      FreeNVMePrpListBufferEntry(v4, *(unsigned __int16 *)((v46 << 7) + *(_QWORD *)(v15 + 32) + 52));
      v46 = v160;
    }
    v49 = v168;
    if ( v168 )
    {
      v50 = v149;
      if ( v149 < 0 )
      {
        v51 = *(_QWORD *)(v15 + 24);
        v52 = v46;
        v53 = *((_QWORD *)v4 + 16);
        v169 = v151;
        v161 = v14;
        Irp = v168;
        v54 = *(_QWORD *)(v15 + 32) + (v52 << 7);
        v177 = 0;
        v174 = *(_QWORD *)(*(_QWORD *)(v51 + 16LL * *(unsigned __int16 *)(v54 + 56)) + 56LL);
        v173 = *(_QWORD *)(*(_QWORD *)(v51 + 16LL * *(unsigned __int16 *)(v54 + 56)) + 48LL);
        v172 = *(_QWORD *)(*(_QWORD *)(v51 + 16LL * *(unsigned __int16 *)(v54 + 56)) + 40LL);
        v171 = *(unsigned int *)(*(_QWORD *)(v51 + 16LL * *(unsigned __int16 *)(v54 + 56)) + 4LL);
        v55 = (v4[136] & 2) == 0;
        v56 = **(unsigned int **)(v51 + 16LL * *(unsigned __int16 *)(v54 + 56));
        *(_QWORD *)&EventDescriptor.Id = EventNVMeControllerError;
        v57 = 0x800000000002000LL;
        v170 = v56;
        if ( !v55 )
          v57 = 0x80000000000A000LL;
        EventDescriptor.Keyword = v57;
        v58 = *(_QWORD *)(v53 + 16);
        v59 = *(const wchar_t **)(v58 + 48);
        if ( v59 )
        {
          v60 = *(unsigned __int16 *)(v58 + 40);
          if ( (_WORD)v60 )
          {
            LODWORD(v61) = v60 >> 1;
            if ( v60 >> 1 )
            {
              while ( 1 )
              {
                v61 = (unsigned int)(v61 - 1);
                v62 = &v59[v61];
                if ( *v62 == 92 )
                  break;
                if ( !(_DWORD)v61 )
                  goto LABEL_79;
              }
              if ( v62 )
                v59 = v62 + 1;
            }
          }
        }
LABEL_79:
        *(_QWORD *)&UserData.Size = 4;
        UserData.Ptr = v53 + 56;
        v182 = 16;
        v181 = v53 + 1048;
        if ( v59 )
        {
          v63 = -1;
          do
            v55 = v59[++v63] == 0;
          while ( !v55 );
          v64 = 2 * v63 + 2;
        }
        else
        {
          v64 = 10;
          v59 = L"NULL";
        }
        v65 = (const int *)*((_QWORD *)v4 + 99);
        v183 = v59;
        v184 = v64;
        v185 = 0;
        if ( v65 )
        {
          v66 = -1;
          do
            ++v66;
          while ( *((_BYTE *)v65 + v66) );
          v67 = v66 + 1;
        }
        else
        {
          v67 = 1;
          v65 = &dword_140157D94;
        }
        v187 = v67;
        v189 = v4 + 4;
        v191 = v4 + 744;
        v68 = (const int *)*((_QWORD *)v4 + 94);
        v186 = v65;
        v69 = &dword_140157D94;
        v188 = 0;
        if ( v68 )
          v69 = v68;
        v190 = 2;
        v70 = -1;
        v192 = 1;
        do
          ++v70;
        while ( *((_BYTE *)v69 + v70) );
        v193 = v69;
        v194 = v70 + 1;
        v196 = v4 + 800;
        v71 = -1;
        v195 = 0;
        do
          ++v71;
        while ( v4[v71 + 800] );
        v198 = 0;
        v197 = v71 + 1;
        v72 = -1;
        v199 = v4 + 841;
        do
          ++v72;
        while ( v4[v72 + 841] );
        v201 = 0;
        v200 = v72 + 1;
        v203 = 40;
        v202 = L"NVMe command failed";
        v205 = 10;
        v204 = L"CDW0";
        v206 = &v170;
        v208 = L"NSID";
        v210 = &v171;
        v212 = L"CDW10|CDW11";
        v214 = &v172;
        v216 = L"CDW12|CDW13";
        v218 = &v173;
        v220 = L"CDW14|CDW15";
        v222 = &v174;
        v224 = L"SQ ID";
        v226 = &v169;
        v228 = L"Irp";
        p_Irp = &Irp;
        v232 = L"Command status";
        v234 = &v161;
        v207 = 8;
        v209 = 10;
        v211 = 8;
        v213 = 24;
        v215 = 8;
        v217 = 24;
        v219 = 8;
        v221 = 24;
        v223 = 8;
        v225 = 12;
        v227 = 8;
        v229 = 8;
        v231 = 8;
        v233 = 30;
        v235 = 8;
        EtwWriteEx(StorPortEventProvider_Context, &EventDescriptor, 0, 1u, &v177, 0, 0x1Au, &UserData);
        v50 = v149;
      }
      v73 = *(_DWORD **)(*(_QWORD *)(v15 + 24) + 16LL * *(unsigned __int16 *)(v157 + *(_QWORD *)(v15 + 32) + 56));
      if ( (v4[1384] & 2) != 0 || v50 < 0 && (v151 || (((unsigned __int8)*v73 - 2) & 0xFFFFFFF7) != 0) )
      {
        v74 = v163[1];
        v75 = *v163;
        v55 = *(_DWORD *)v4 == 1314276178;
        HIWORD(QpcTimeStamp[1]) = 0;
        LOWORD(v177.Data1) = v151;
        HIWORD(v177.Data1) = *((_WORD *)v5 + 16);
        *(_DWORD *)&v177.Data2 = *v73;
        *(_DWORD *)((char *)&QpcTimeStamp[1] + 2) = 0;
        *(_QWORD *)v177.Data4 = v49;
        QpcTimeStamp[0] = __PAIR64__(v74, v75);
        LOWORD(QpcTimeStamp[1]) = v14;
        if ( v55 )
        {
          v76 = *(_QWORD *)(*((_QWORD *)v4 + 174) + 8LL * KeGetCurrentProcessorNumberEx(0));
          v77 = *(_DWORD *)(v76 + 12);
          _InterlockedOr(v147, 0);
          if ( v77 )
          {
            v78 = v76 + 64;
            if ( v76 != -64 )
            {
              v79 = _InterlockedIncrement((volatile signed __int32 *)v76) % v77;
              v80 = v78 + ((unsigned __int64)v79 << 6);
              v81 = v79;
              if ( (*((_DWORD *)v4 + 340) & 1) != 0 )
                v81 = _InterlockedIncrement((volatile signed __int32 *)v4 + 352);
              *(_DWORD *)(v80 + 4) = v81;
              v55 = v151 == 0;
              v82 = (_QWORD *)(v80 + 8);
              *(_WORD *)v80 = 1;
              *(_WORD *)(v80 + 2) = !v55;
              if ( (*((_DWORD *)v4 + 340) & 2) != 0 )
                KeQuerySystemTimePrecise(v82, 4);
              else
                *v82 = MEMORY[0xFFFFF78000000014];
              v83 = *(_OWORD *)QpcTimeStamp;
              *(GUID *)(v80 + 16) = v177;
              *(_OWORD *)(v80 + 32) = v83;
              v49 = v168;
            }
          }
        }
      }
      Namespace = NvmeControllerGetNamespace(v4, *(unsigned int *)(v157 + *(_QWORD *)(v15 + 32) + 88));
      v85 = Namespace;
      v161 = Namespace;
      if ( (*(_DWORD *)(*(_QWORD *)(Namespace + 624) + 4LL) & 1) != 0 )
      {
        StorpTelemetryCollectNvmePerfData(v157 + *(_QWORD *)(v15 + 32), (_DWORD)v73, Namespace, v149, v165);
        v85 = v161;
      }
      if ( (v14 & 0x1FE) != 0 && (*(_DWORD *)(*(_QWORD *)(v85 + 624) + 4LL) & 2) != 0 )
        StorpTelemetryCollectNvmeErrorData(*(_QWORD *)(v15 + 32) + v157, v85, v73, v163);
    }
    *(_WORD *)(v15 + 140) = v153;
    v86 = v157;
    if ( (*(_BYTE *)(v157 + *(_QWORD *)(v15 + 32) + 61) & 1) != 0
      && !_InterlockedCompareExchange(
            (volatile signed __int32 *)(*(_QWORD *)_InterlockedExchange64(
                                                     (volatile __int64 *)(v157 + *(_QWORD *)(v15 + 32) + 80),
                                                     0)
                                      + 4268LL),
            1,
            0) )
    {
      v48 = *((_QWORD *)v4 + 16);
      v87 = *(_QWORD *)(v48 + 168);
      if ( *(_BYTE *)v87 == 1
        && _InterlockedExchangeAdd(
             *(volatile signed __int32 **)(*(_QWORD *)(v87 + 16)
                                         + 8LL * *(unsigned __int16 *)(v86 + *(_QWORD *)(v15 + 32) + 52)),
             0xFFFFFFFF) == 1 )
      {
        PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v48 + 168) + 8LL), 0, 2);
      }
    }
    if ( (*(_BYTE *)(v86 + *(_QWORD *)(v15 + 32) + 60) & 0x20) != 0
      && !_interlockedbittestandset((volatile signed __int32 *)v4 + 270, 6u) )
    {
      NvmeControllerRestartRoutine(0, v4);
    }
    v88 = *(_QWORD *)(v15 + 32);
    if ( *(_QWORD *)(v86 + v88 + 32) )
      (*(void (__fastcall **)(char *, _QWORD, _DWORD *))(v86 + v88 + 32))(v4, *(_QWORD *)(v86 + v88 + 40), v163);
    if ( v49 )
    {
      v89 = v149;
      if ( v149 < 0 )
      {
        v49->IoStatus.Information = 0;
        v153 = 0;
        GenericIrpExtension = IoGetGenericIrpExtension(v49, &v153, 4);
        if ( (int)(GenericIrpExtension + 0x80000000) < 0 || GenericIrpExtension == -1073741275 )
        {
          BYTE1(v153) |= 4u;
          HIWORD(v153) = v14;
          LOBYTE(v92) = 1;
          IoSetGenericIrpExtension(v49, &v153, 4, v92);
        }
        v90 = v157;
      }
      else
      {
        v90 = v157;
        v49->IoStatus.Information = *(unsigned int *)(v157 + *(_QWORD *)(v15 + 32) + 48);
      }
      if ( *(char *)(v90 + *(_QWORD *)(v15 + 32) + 60) < 0 )
      {
        v93 = *((_QWORD *)v4 + 16);
        v94 = v49->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset;
        v95 = *(_QWORD *)(v94.QuadPart + 24);
        v96 = *(_BYTE *)(v94.QuadPart + 126) & 1;
        v97 = KfRaiseIrql(2u);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v93 + 1160) + 8LL) + 96LL))(
          *(_QWORD *)(v93 + 1160),
          v95,
          v96 ^ 1u);
        if ( v97 < 2u )
          KeLowerIrql(v97);
        v4 = (char *)Context;
        v98 = *(_QWORD *)(*(_QWORD *)(v94.QuadPart + 40) + 184LL);
        *(_QWORD *)(v98 + 8) = *(_QWORD *)(v94.QuadPart + 48);
        *(_QWORD *)(v98 + 24) = *(_QWORD *)(v94.QuadPart + 56);
        *(_QWORD *)(v94.QuadPart + 24) = 0;
        *(_QWORD *)(v94.QuadPart + 88) = 0;
        *(_BYTE *)(v94.QuadPart + 126) = 0;
        ExpInterlockedPushEntrySList(
          *(PSLIST_HEADER *)(*((_QWORD *)v4 + 112) + 8LL * *(unsigned int *)(v94.QuadPart + 120)),
          (PSLIST_ENTRY)v94.QuadPart);
        v49 = v168;
        v15 = v159;
        v89 = v149;
      }
      if ( (int)IoGetIoAttributionHandle(v49, &v175) >= 0 )
      {
        v99 = *(_QWORD *)(v157 + *(_QWORD *)(v15 + 32) + 64);
        CurrentStackLocation = v49->Tail.Overlay.CurrentStackLocation;
        v101 = v175;
        v177 = 0;
        v177.Data1 = 1;
        *(_OWORD *)QpcTimeStamp = 0;
        MajorFunction = CurrentStackLocation->MajorFunction;
        v103 = *(_QWORD *)(v15 + 32);
        *(_DWORD *)&v177.Data2 = MajorFunction;
        QpcTimeStamp[0] = v99;
        *(_DWORD *)v177.Data4 = *(_DWORD *)(v157 + v103 + 48);
        UnbiasedInterruptTimePrecise = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp[1]);
        v105 = v49->IoStatus.Status < 0;
        QpcTimeStamp[1] = UnbiasedInterruptTimePrecise;
        if ( v105 )
          *(_DWORD *)&v177.Data2 |= 0x400u;
        IoRecordIoAttribution(v101, &v177);
      }
      v106 = v165;
      v107 = *(unsigned __int16 *)(v157 + *(_QWORD *)(v15 + 32) + 52);
      if ( (_DWORD)v107 == v165 )
      {
        if ( (*((_BYTE *)&v49->Tail.CompletionKey + 31) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v161 + 696) + 8LL * v165));
        v49->IoStatus.Status = v89;
        IofCompleteRequest(v49, 0);
        v108 = v161;
        v109 = *(_QWORD *)(v161 + 128);
        if ( !*(_BYTE *)v109
          && _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(v109 + 24) + 8 * v106), 0xFFFFFFFF) == 1 )
        {
          v110 = *(_QWORD *)(*(_QWORD *)(v108 + 16) + 128LL);
          v111 = *(_QWORD *)(v108 + 128);
          if ( v111 )
          {
            if ( *(_QWORD *)(v111 + 8) )
            {
              v112 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v111 + 40);
              if ( v112 )
              {
                if ( ExAcquireRundownProtectionCacheAware(v112) )
                {
                  PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v108 + 128) + 8LL), 0, 2);
                  v113 = *(_QWORD *)(v108 + 128);
                  if ( v113 )
                  {
                    if ( *(_QWORD *)(v113 + 8) )
                    {
                      v114 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v113 + 40);
                      if ( v114 )
                        ExReleaseRundownProtectionCacheAware(v114);
                    }
                  }
                }
              }
            }
          }
          v115 = *(_QWORD *)(v110 + 168);
          if ( *(_BYTE *)v115 == 1 )
            PoFxIdleComponent(**(_QWORD **)(v115 + 8), 0, 2);
        }
      }
      else
      {
        v117 = v161;
        v118 = *(_QWORD *)(*((_QWORD *)v4 + 139) + 8 * v107);
        v119 = v49->Tail.Overlay.CurrentStackLocation;
        v49->IoStatus.Status = v89;
        v119->Parameters.Read.ByteOffset.QuadPart = v117;
        v120 = ((unsigned __int64)&v49->Tail.Overlay.DriverContext[1] + 7) & 0xFFFFFFFFFFFFFFF0uLL;
        *(_BYTE *)(v120 + 8) = ((_BYTE)v49 + 120) & 0xF;
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v118 + 192), (PSLIST_ENTRY)v120);
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v118 + 256), 1, 0) )
          KeInsertQueueDpc(*(PRKDPC *)(v118 + 24), (PVOID)v118, 0);
      }
    }
    _InterlockedOr(v147, 0);
    while ( _InterlockedCompareExchange(v5 + 10, 1, 0) )
      ;
    v116 = *((unsigned __int16 *)v5 + 17);
    if ( v116 == v156 )
    {
      *((_WORD *)v5 + 18) = *((_WORD *)v5 + 18) != 1;
      *((_WORD *)v5 + 17) = 0;
    }
    else
    {
      *((_WORD *)v5 + 17) = v116 + 1;
    }
    v8 = (_WORD *)(*(_QWORD *)v5 + 16LL * *((unsigned __int16 *)v5 + 17));
    v163 = v8;
    if ( (v8[7] & 1) == *((_WORD *)v5 + 18) )
    {
      v121 = v7 & 0xFFFF0000 | *((unsigned __int16 *)v5 + 17);
      v7 = v121;
      if ( v150 == 1 )
      {
        v122 = *((_QWORD *)v4 + 16);
        v156 = v121;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, unsigned int *))(v122 + 536))(
          *((_QWORD *)v4 + 206) + 64LL,
          *((unsigned int *)v5 + 4),
          4,
          0,
          &v156);
      }
      else
      {
        **((_DWORD **)v5 + 2) = v121;
        _InterlockedOr(v147, 0);
      }
      v123 = _InterlockedCompareExchange(v5 + 11, 0, 1);
      v166 = v123;
    }
    else
    {
      v123 = v166;
    }
    v124 = 0;
    _InterlockedCompareExchange(v5 + 10, 0, 1);
    _InterlockedOr(v147, 0);
    LOWORD(v155) = v155 + 1;
    v125 = v160 << 7;
    v160 <<= 7;
    if ( !*((_DWORD *)v4 + 237) )
    {
      v126 = (unsigned __int16 *)(v125 + *(_QWORD *)(v15 + 32) + 54LL);
      if ( *(_WORD *)(v15 + 136) )
      {
        if ( *((_DWORD *)v4 + 238) )
        {
          v127 = NvmeProcessPendingIoInCompletionDpc((__int64)v4, v15, v48, (__int64)v126);
          goto LABEL_181;
        }
        if ( *((_DWORD *)v4 + 240) )
        {
          LOBYTE(ActivityId) = 0;
LABEL_180:
          v127 = NvmeControllerProcessPendingCommand(
                   (_DWORD)v4,
                   *(unsigned __int16 *)(((unsigned __int64)*v126 << 7) + *(_QWORD *)(v15 + 32) + 52),
                   v15,
                   (_DWORD)v126,
                   (char)ActivityId);
LABEL_181:
          v125 = v160;
          v124 = v127;
        }
      }
      else if ( *((_DWORD *)v4 + 239) )
      {
        LOBYTE(ActivityId) = 1;
        goto LABEL_180;
      }
      if ( v124 )
        goto LABEL_184;
      goto LABEL_183;
    }
    if ( **((_DWORD **)v4 + 164) == 1 && !*(_DWORD *)(*((_QWORD *)v4 + 164) + 4LL) )
      goto LABEL_184;
LABEL_183:
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v15 + 64), (PSLIST_ENTRY)(*(_QWORD *)(v15 + 32) + v125));
LABEL_184:
    if ( v123 || (v8[7] & 1) == *((_WORD *)v5 + 18) )
    {
      v128 = v155;
      goto LABEL_187;
    }
  }
  v129 = 0x800000000002000LL;
  v163 = (_DWORD *)*((_QWORD *)v4 + 121);
  Irp = (PIRP)*(unsigned __int16 *)(v15 + 142);
  v169 = *(unsigned __int16 *)(v15 + 140);
  v171 = *((unsigned int *)v8 + 3);
  v172 = *((unsigned int *)v8 + 2);
  v55 = (v4[136] & 2) == 0;
  v130 = *((_QWORD *)v4 + 16);
  v173 = *((unsigned __int16 *)v5 + 17);
  v174 = *((unsigned __int16 *)v5 + 16);
  *(_QWORD *)&EventDescriptor.Id = EventNVMeControllerError;
  if ( !v55 )
    v129 = 0x80000000000A000LL;
  v170 = v16;
  EventDescriptor.Keyword = v129;
  v177 = 0;
  v131 = *(_QWORD *)(v130 + 16);
  v132 = *(const wchar_t **)(v131 + 48);
  if ( v132 )
  {
    v133 = *(unsigned __int16 *)(v131 + 40);
    if ( (_WORD)v133 )
    {
      LODWORD(v134) = v133 >> 1;
      if ( v133 >> 1 )
      {
        while ( 1 )
        {
          v134 = (unsigned int)(v134 - 1);
          v135 = &v132[v134];
          if ( *v135 == 92 )
            break;
          if ( !(_DWORD)v134 )
            goto LABEL_203;
        }
        if ( v135 )
          v132 = v135 + 1;
      }
    }
  }
LABEL_203:
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = v130 + 56;
  v182 = 16;
  v181 = v130 + 1048;
  v136 = -1;
  if ( v132 )
  {
    v137 = -1;
    do
      v55 = v132[++v137] == 0;
    while ( !v55 );
    v138 = 2 * v137 + 2;
  }
  else
  {
    v132 = L"NULL";
    v138 = 10;
  }
  v139 = (const int *)*((_QWORD *)v4 + 99);
  v183 = v132;
  v184 = v138;
  v185 = 0;
  if ( v139 )
  {
    v140 = -1;
    do
      ++v140;
    while ( *((_BYTE *)v139 + v140) );
    v141 = v140 + 1;
    v142 = &dword_140157D94;
  }
  else
  {
    v142 = &dword_140157D94;
    v141 = 1;
    v139 = &dword_140157D94;
  }
  v187 = v141;
  v189 = v4 + 4;
  v191 = v4 + 744;
  v143 = (const int *)*((_QWORD *)v4 + 94);
  v186 = v139;
  v188 = 0;
  if ( v143 )
    v142 = v143;
  v190 = 2;
  v144 = -1;
  v192 = 1;
  do
    ++v144;
  while ( *((_BYTE *)v142 + v144) );
  v193 = v142;
  v194 = v144 + 1;
  v145 = -1;
  v195 = 0;
  v196 = v4 + 800;
  do
    ++v145;
  while ( v4[v145 + 800] );
  v198 = 0;
  v197 = v145 + 1;
  v199 = v4 + 841;
  do
    v55 = v4[v136++ + 842] == 0;
  while ( !v55 );
  v200 = v136 + 1;
  v201 = 0;
  v202 = L"Invalid command ID in CQ entry";
  v203 = 62;
  v204 = L"CQ ID";
  v205 = 12;
  v206 = &v174;
  v208 = L"CQ Head";
  v210 = &v173;
  v212 = L"CQ entry DW2";
  v214 = &v172;
  v216 = L"CQ entry DW3";
  v218 = &v171;
  v220 = L"Queue Depth";
  v222 = &v170;
  v224 = L"SQ Head";
  v226 = &v169;
  v228 = L"SQ Tail";
  p_Irp = &Irp;
  v232 = L"Controller state";
  v234 = (__int64 *)&v163;
  v207 = 8;
  v209 = 16;
  v211 = 8;
  v213 = 26;
  v215 = 8;
  v217 = 26;
  v219 = 8;
  v221 = 24;
  v223 = 8;
  v225 = 16;
  v227 = 8;
  v229 = 16;
  v231 = 8;
  v233 = 34;
  v235 = 8;
  EtwWriteEx(StorPortEventProvider_Context, &EventDescriptor, 0, 1u, &v177, 0, 0x1Au, &UserData);
  v128 = v155;
  if ( !(_WORD)v155 )
    goto LABEL_188;
  while ( _InterlockedCompareExchange(v5 + 10, 1, 0) )
    ;
  if ( v150 == 1 )
  {
    v146 = *((_QWORD *)v4 + 16);
    v156 = v7 & 0xFFFF0000 | *((unsigned __int16 *)v5 + 17);
    (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, unsigned int *))(v146 + 536))(
      *((_QWORD *)v4 + 206) + 64LL,
      *((unsigned int *)v5 + 4),
      4,
      0,
      &v156);
  }
  else
  {
    **((_DWORD **)v5 + 2) = v7 & 0xFFFF0000 | *((unsigned __int16 *)v5 + 17);
    _InterlockedOr(v147, 0);
  }
  _InterlockedCompareExchange(v5 + 11, 0, 1);
  _InterlockedCompareExchange(v5 + 10, 0, 1);
LABEL_187:
  if ( v128 )
    goto LABEL_189;
LABEL_188:
  _InterlockedCompareExchange(v5 + 11, 0, 1);
LABEL_189:
  if ( ((unsigned __int8)v176 & 1) == 0 && *((_DWORD *)v4 + 226) != 3 )
  {
    *(_DWORD *)(*((_QWORD *)v4 + 115) + 16LL) = 1 << *((_BYTE *)v5 + 24);
    _InterlockedOr(v147, 0);
  }
}

```

## disassembly

```asm
0x14005ed70  test    r9, r9
0x14005ed73  jz      locret_14006001A
0x14005ed79  push    rbp
0x14005ed7a  push    r12
0x14005ed7c  push    r13
0x14005ed7e  push    r15
0x14005ed80  lea     rbp, [rsp-248h]
0x14005ed88  sub     rsp, 348h
0x14005ed8f  mov     rax, cs:__security_cookie
0x14005ed96  xor     rax, rsp
0x14005ed99  mov     [rbp+260h+var_40], rax
0x14005eda0  xor     r15d, r15d
0x14005eda3  mov     [rbp+260h+Context], r9
0x14005eda7  mov     [rbp+260h+var_2B8], r8
0x14005edab  mov     r12, r9
0x14005edae  mov     [rbp+260h+var_270], rdx
0x14005edb2  mov     r13, r8
0x14005edb5  mov     [rbp+260h+var_278], r15
0x14005edb9  test    r8, r8
0x14005edbc  jz      loc_14005FFFD
0x14005edc2  mov     [rsp+360h+var_30], r14
0x14005edca  mov     r14d, 1
0x14005edd0  xor     eax, eax
0x14005edd2  lock cmpxchg [r8+28h], r14d
0x14005edd8  jnz     short loc_14005EDD0
0x14005edda  xor     eax, eax
0x14005eddc  lock cmpxchg [r8+2Ch], r14d
0x14005ede2  mov     eax, r15d
0x14005ede5  jz      short loc_14005EDF0
0x14005ede7  xchg    eax, [r8+28h]
0x14005edeb  jmp     loc_14005FFCB
0x14005edf0  mov     [rsp+360h+arg_0], rbx
0x14005edf8  mov     [rsp+360h+var_20], rsi
0x14005ee00  mov     [rsp+360h+var_28], rdi
0x14005ee08  lock or [rsp+360h+var_360], r15d
0x14005ee0d  xchg    eax, [r8+28h]
0x14005ee11  lock or [rsp+360h+var_360], r15d
0x14005ee16  mov     rax, [r9+520h]
0x14005ee1d  mov     ecx, [rax]
0x14005ee1f  cmp     ecx, r14d
0x14005ee22  jnz     short loc_14005EE36
0x14005ee24  mov     rax, [r9+520h]
0x14005ee2b  mov     ecx, [rax+4]
0x14005ee2e  test    ecx, ecx
0x14005ee30  jz      loc_14005FFA7
0x14005ee36  movzx   esi, word ptr [r8+22h]
0x14005ee3b  xor     ecx, ecx; ProcNumber
0x14005ee3d  movzx   eax, byte ptr [r9+6C0h]
0x14005ee45  mov     edi, r15d
0x14005ee48  shl     rsi, 4
0x14005ee4c  add     rsi, [r8]
0x14005ee4f  mov     [rbp+260h+var_2D0], rsi
0x14005ee53  mov     [rsp+360h+var_30C], r15d
0x14005ee58  mov     [rbp+260h+var_2BC], r15d
0x14005ee5c  mov     [rbp+260h+var_2E0], r15
0x14005ee60  mov     [rsp+360h+var_31C], al
0x14005ee64  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005ee6b  nop     dword ptr [rax+rax+00h]
0x14005ee70  movzx   edx, word ptr [rsi+0Eh]
0x14005ee74  movzx   ecx, word ptr [r13+24h]
0x14005ee79  and     dx, r14w
0x14005ee7d  mov     [rbp+260h+var_2C0], eax
0x14005ee80  cmp     dx, cx
0x14005ee83  jz      loc_14005FFA7
0x14005ee89  lea     r9, cs:140000000h
0x14005ee90  movzx   eax, word ptr [rsi+0Ah]
0x14005ee94  movzx   ecx, word ptr [rsi+8]
0x14005ee98  movzx   edx, word ptr [rsi+0Ch]
0x14005ee9c  movzx   ebx, word ptr [rsi+0Eh]
0x14005eea0  mov     word ptr [rsp+360h+var_314], cx
0x14005eea5  mov     [rsp+360h+var_31A], ax
0x14005eeaa  test    ax, ax
0x14005eead  jnz     short loc_14005EEB9
0x14005eeaf  mov     r15, [r12+2C8h]
0x14005eeb7  jmp     short loc_14005EED3
0x14005eeb9  mov     r15, [r12+2D8h]
0x14005eec1  lea     rcx, [rax+rax*2]
0x14005eec5  shl     rcx, 6
0x14005eec9  add     r15, 0FFFFFFFFFFFFFF40h
0x14005eed0  add     r15, rcx
0x14005eed3  mov     ecx, [r15+7Ch]
0x14005eed7  mov     [rsp+360h+var_2F0], r15
0x14005eedc  lea     r8d, [rcx-1]
0x14005eee0  mov     [rsp+360h+var_308], r8d
0x14005eee5  cmp     edx, r8d
0x14005eee8  jnb     loc_14006001C
0x14005eeee  mov     rcx, [r15+20h]
0x14005eef2  mov     r10, rdx
0x14005eef5  shl     r10, 7
0x14005eef9  mov     r11, rdx
0x14005eefc  mov     [rsp+360h+var_2E8], rdx
0x14005ef01  mov     edx, ebx
0x14005ef03  mov     [rsp+360h+var_300], r10
0x14005ef08  movzx   eax, byte ptr [rcx+r10+3Ch]
0x14005ef0e  and     al, 0FEh
0x14005ef10  mov     [rcx+r10+3Ch], al
0x14005ef15  mov     ecx, ebx
0x14005ef17  shr     ecx, 9
0x14005ef1a  and     ecx, 7
0x14005ef1d  jz      loc_14005EFB5
0x14005ef23  sub     ecx, 1
0x14005ef26  jz      short loc_14005EF60
0x14005ef28  sub     ecx, 1
0x14005ef2b  jnz     def_14005EF4F; jumptable 000000014005EF4F default case, cases 128-133
0x14005ef31  shr     edx, 1
0x14005ef33  movzx   eax, dl
0x14005ef36  add     eax, 0FFFFFF80h; switch 7 cases
0x14005ef39  cmp     eax, 6
0x14005ef3c  ja      def_14005EF4F; jumptable 000000014005EF4F default case, cases 128-133
0x14005ef42  cdqe
0x14005ef44  mov     ecx, ds:(jpt_14005EF4F - 140000000h)[r9+rax*4]
0x14005ef4c  add     rcx, r9
0x14005ef4f  jmp     rcx; switch jump
0x14005ef55  mov     r9d, 0C0000022h; jumptable 000000014005EF4F case 134
0x14005ef5b  jmp     loc_14005F006
0x14005ef60  shr     edx, 1
0x14005ef62  movzx   eax, dl
0x14005ef65  cmp     eax, 83h; switch 132 cases
0x14005ef6a  ja      def_14005EF4F; jumptable 000000014005EF4F default case, cases 128-133
0x14005ef70  movzx   eax, ds:(byte_140163C31 - 140000000h)[r9+rax]
0x14005ef79  mov     ecx, ds:(jpt_14005EF84 - 140000000h)[r9+rax*4]
0x14005ef81  add     rcx, r9
0x14005ef84  jmp     rcx; switch jump
0x14005ef8a  mov     r9d, 0C0000010h; jumptable 000000014005EF84 cases 0-3,5-10,12-15,28,31-34,128,129,131
0x14005ef90  jmp     loc_14005F006
0x14005ef95  mov     r9d, 800001B6h; jumptable 000000014005EF84 cases 11,16,17
0x14005ef9b  jmp     short loc_14005F006
0x14005ef9d  mov     r9d, 0C0000184h; jumptable 000000014005EF84 cases 18,19,22,24-26
0x14005efa3  jmp     short loc_14005F006
0x14005efa5  mov     r9d, 0C0000018h; jumptable 000000014005EF84 case 20
0x14005efab  jmp     short loc_14005F006
0x14005efad  mov     r9d, 0C00000BBh; jumptable 000000014005EF84 case 27
0x14005efb3  jmp     short loc_14005F006
0x14005efb5  shr     edx, 1
0x14005efb7  movzx   eax, dl
0x14005efba  cmp     eax, 83h; switch 132 cases
0x14005efbf  ja      short def_14005EF4F; jumptable 000000014005EF4F default case, cases 128-133
0x14005efc1  movzx   eax, ds:(byte_140163CDD - 140000000h)[r9+rax]
0x14005efca  mov     ecx, ds:(jpt_14005EFD5 - 140000000h)[r9+rax*4]
0x14005efd2  add     rcx, r9
0x14005efd5  jmp     rcx; switch jump
0x14005efdb  xor     r9d, r9d; jumptable 000000014005EFD5 case 0
0x14005efde  jmp     short loc_14005F006
0x14005efe0  mov     r9d, 0C0000240h; jumptable 000000014005EFD5 cases 7-10,27
0x14005efe6  jmp     short loc_14005F006
0x14005efe8  mov     r9d, 0C000042Ah; jumptable 000000014005EFD5 case 12
0x14005efee  jmp     short loc_14005F006
0x14005eff0  mov     r9d, 0C00000B5h; jumptable 000000014005EFD5 cases 25,26
0x14005eff6  jmp     short loc_14005F006
0x14005eff8  mov     r9d, 0C00000A3h; jumptable 000000014005EFD5 case 130
0x14005effe  jmp     short loc_14005F006
0x14005f000  mov     r9d, 0C0000185h; jumptable 000000014005EF4F default case, cases 128-133
0x14005f006  mov     rax, [r15+20h]
0x14005f00a  mov     [rsp+360h+var_320], r9d
0x14005f00f  movzx   ecx, byte ptr [r10+rax+3Ch]
0x14005f015  mov     rax, [r15+20h]
0x14005f019  test    cl, 8
0x14005f01c  jz      loc_14005F414
0x14005f022  mov     rcx, [r10+rax+28h]
0x14005f027  movzx   r8d, word ptr [r10+rax+34h]
0x14005f02d  mov     [rbp+260h+var_2B0], 0
0x14005f035  mov     [rsp+360h+var_2F8], r8w
0x14005f03b  mov     rdx, [rcx+18h]
0x14005f03f  mov     r12, [rcx+10h]
0x14005f043  mov     [rbp+260h+Irp], rdx
0x14005f047  mov     rax, [rdx+0B8h]
0x14005f04e  mov     r15, [rax+18h]
0x14005f052  mov     eax, 5
0x14005f057  movzx   esi, word ptr [r15+20h]
0x14005f05c  mov     [rsp+360h+var_310], si
0x14005f061  xchg    eax, [rcx+68h]
0x14005f064  mov     [rcx+70h], r9d
0x14005f068  test    r9d, r9d
0x14005f06b  jns     short loc_14005F075
0x14005f06d  xor     eax, eax
0x14005f06f  lock cmpxchg [r15+70h], r9d
0x14005f075  xor     r13d, r13d
0x14005f078  xchg    r13, [rcx+58h]
0x14005f07c  test    r13, r13
0x14005f07f  jz      loc_14005F13E
0x14005f085  mov     rax, [r13+18h]
0x14005f089  mov     [rbp+260h+var_2A8], rax
0x14005f08d  test    rax, rax
0x14005f090  jz      loc_14005F103
0x14005f096  mov     rax, [r12+10h]
0x14005f09b  mov     cl, 2; NewIrql
0x14005f09d  movzx   r14d, byte ptr [r13+7Eh]
0x14005f0a2  and     r14b, 1
0x14005f0a6  mov     rsi, [rax+80h]
0x14005f0ad  call    cs:__imp_KfRaiseIrql
0x14005f0b4  nop     dword ptr [rax+rax+00h]
0x14005f0b9  mov     r9, [rsi+488h]
0x14005f0c0  xor     r14b, 1
0x14005f0c4  mov     rdx, [rbp+260h+var_2A8]
0x14005f0c8  movzx   r8d, r14b
0x14005f0cc  mov     [rsp+360h+var_318], al
0x14005f0d0  mov     rcx, [r9+8]
0x14005f0d4  mov     rax, [rcx+60h]
0x14005f0d8  mov     rcx, r9
0x14005f0db  call    _guard_dispatch_icall
0x14005f0e0  movzx   eax, [rsp+360h+var_318]
0x14005f0e5  cmp     al, 2
0x14005f0e7  jnb     short loc_14005F0F8
0x14005f0e9  movzx   ecx, al; NewIrql
0x14005f0ec  call    cs:__imp_KeLowerIrql
0x14005f0f3  nop     dword ptr [rax+rax+00h]
0x14005f0f8  movzx   esi, [rsp+360h+var_310]
0x14005f0fd  mov     r14d, 1
0x14005f103  mov     rcx, [r12+10h]
0x14005f108  xor     eax, eax
0x14005f10a  mov     [r13+18h], rax
0x14005f10e  mov     rdx, r13; ListEntry
0x14005f111  mov     [r13+58h], rax
0x14005f115  mov     [r13+7Eh], al
0x14005f119  mov     rcx, [rcx+380h]
0x14005f120  mov     eax, [r13+78h]
0x14005f124  mov     rcx, [rcx+rax*8]; ListHead
0x14005f128  call    cs:__imp_ExpInterlockedPushEntrySList
0x14005f12f  nop     dword ptr [rax+rax+00h]
0x14005f134  mov     rdx, [rbp+260h+Irp]
0x14005f138  movzx   r8d, [rsp+360h+var_2F8]
0x14005f13e  mov     ecx, r14d
0x14005f141  lock xadd [r15+74h], ecx
0x14005f147  inc     ecx
0x14005f149  movzx   eax, si
0x14005f14c  cmp     ecx, eax
0x14005f14e  jl      loc_14005F2BC
0x14005f154  mov     rax, [r12+10h]
0x14005f159  movzx   r14d, r8w
0x14005f15d  bt      qword ptr [rax+88h], 20h ; ' '
0x14005f166  jb      short loc_14005F17E
0x14005f168  movzx   eax, word ptr [r15+78h]
0x14005f16d  test    ax, ax
0x14005f170  jz      short loc_14005F17E
0x14005f172  pause
0x14005f174  movzx   eax, word ptr [r15+78h]
0x14005f179  test    ax, ax
0x14005f17c  jnz     short loc_14005F172
0x14005f17e  mov     esi, [r15+70h]
0x14005f182  test    esi, esi
0x14005f184  js      short loc_14005F18C
0x14005f186  mov     eax, [r15+30h]
0x14005f18a  jmp     short loc_14005F18E
0x14005f18c  xor     eax, eax
0x14005f18e  mov     [rdx+38h], rax
0x14005f192  mov     r9, rdx
0x14005f195  mov     rcx, [r12+10h]
0x14005f19a  mov     edx, r14d
0x14005f19d  mov     r8, r15
0x14005f1a0  call    FreeNVMeChainedIoSplitContext
0x14005f1a5  mov     r8, [rbp+260h+Irp]
0x14005f1a9  test    byte ptr [r8+97h], 1
0x14005f1b1  jz      short loc_14005F1C2
0x14005f1b3  mov     rax, [r12+2B8h]
0x14005f1bb  mov     rcx, [rax+r14*8]
0x14005f1bf  lock dec dword ptr [rcx]
0x14005f1c2  xor     edx, edx; PriorityBoost
0x14005f1c4  mov     [r8+30h], esi
0x14005f1c8  mov     rcx, r8; Irp
0x14005f1cb  call    cs:__imp_IofCompleteRequest
0x14005f1d2  nop     dword ptr [rax+rax+00h]
0x14005f1d7  mov     rax, [r12+80h]
0x14005f1df  cmp     byte ptr [rax], 0
0x14005f1e2  jnz     loc_14005F2B6
0x14005f1e8  mov     rax, [rax+18h]
0x14005f1ec  mov     rdx, [rax+r14*8]
0x14005f1f0  mov     eax, 0FFFFFFFFh
0x14005f1f5  lock xadd [rdx], eax
0x14005f1f9  cmp     eax, 1
0x14005f1fc  jnz     loc_14005F2B6
0x14005f202  mov     rax, [r12+10h]
0x14005f207  mov     rsi, [rax+80h]
0x14005f20e  mov     rax, [r12+80h]
0x14005f216  test    rax, rax
0x14005f219  jz      loc_14005F28F
0x14005f21f  cmp     qword ptr [rax+8], 0
0x14005f224  jz      loc_14005F28F
0x14005f22a  mov     rcx, [rax+28h]; RunRefCacheAware
0x14005f22e  test    rcx, rcx
0x14005f231  jz      short loc_14005F28F
0x14005f233  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14005f23a  nop     dword ptr [rax+rax+00h]
0x14005f23f  test    al, al
0x14005f241  jz      short loc_14005F28F
0x14005f243  mov     rax, [r12+80h]
0x14005f24b  xor     edx, edx
0x14005f24d  mov     r8d, 2
0x14005f253  mov     rcx, [rax+8]
0x14005f257  mov     rcx, [rcx]
0x14005f25a  call    cs:__imp_PoFxIdleComponent
0x14005f261  nop     dword ptr [rax+rax+00h]
0x14005f266  mov     rax, [r12+80h]
0x14005f26e  test    rax, rax
0x14005f271  jz      short loc_14005F28F
0x14005f273  cmp     qword ptr [rax+8], 0
0x14005f278  jz      short loc_14005F28F
0x14005f27a  mov     rcx, [rax+28h]; RunRefCacheAware
0x14005f27e  test    rcx, rcx
0x14005f281  jz      short loc_14005F28F
0x14005f283  call    cs:__imp_ExReleaseRundownProtectionCacheAware
  ... truncated ...
```
