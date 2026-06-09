# USBVideoPinBuildDescriptors

- ea: `0x140023dfc`
- end: `0x1400247cb`
- name: `USBVideoPinBuildDescriptors`
- size: `2511`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14001bdfc`

## callees

- `0x140001008`
- `0x140001048`
- `0x140001078`
- `0x14000cbf0`
- `0x140015234`
- `0x14001916c`
- `0x14001a938`
- `0x14001b15c`
- `0x14001b2f4`
- `0x140021aa4`
- `0x140021dd8`
- `0x140023dfc`
- `0x140040a30`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400242e6`
- `ntoskrnl!KeInitializeEvent` at `0x1400242e6`
- `ntoskrnl!KeInitializeSemaphore` at `0x14002430f`
- `ntoskrnl!KeInitializeSemaphore` at `0x140024494`
- `ntoskrnl!KeInitializeSemaphore` at `0x140024621`
- `ntoskrnl!KeInitializeSemaphore` at `0x14002430f`
- `ntoskrnl!KeInitializeSemaphore` at `0x140024494`
- `ntoskrnl!KeInitializeSemaphore` at `0x140024621`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023f57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140023ef2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024066`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140023ef2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024066`
- `ntoskrnl!KeInitializeMutex` at `0x1400242ce`
- `ntoskrnl!KeInitializeMutex` at `0x1400242ce`
- `ks!KsAddItemToObjectBag` at `0x140023f3d`
- `ks!KsAddItemToObjectBag` at `0x1400240be`
- `ks!KsAddItemToObjectBag` at `0x140023f3d`
- `ks!KsAddItemToObjectBag` at `0x1400240be`

## pseudocode

```c
__int64 __fastcall USBVideoPinBuildDescriptors(__int64 a1, char **a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v4; // rdi
  unsigned int v6; // eax
  __int64 v7; // r12
  unsigned int v8; // r13d
  __int64 v9; // r14
  unsigned int v10; // eax
  unsigned int v11; // r13d
  unsigned int v12; // r13d
  PVOID PoolWithTag; // rax
  void *v14; // rsi
  void **v15; // rbx
  NTSTATUS v16; // esi
  void *v17; // rcx
  __int64 result; // rax
  int v19; // esi
  int v20; // r15d
  unsigned int v21; // edx
  unsigned int v22; // eax
  void *v23; // rcx
  __int64 v24; // rcx
  unsigned int i; // ebx
  SIZE_T v26; // r15
  char *v27; // rax
  char *v28; // rbx
  __int64 v29; // rsi
  unsigned int v30; // r12d
  char *v31; // r15
  char *v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // r13
  unsigned int v35; // edx
  __int64 v36; // rax
  __int64 v37; // rcx
  bool v38; // zf
  __int64 (__fastcall **v39)(PKSPIN); // rax
  int v40; // eax
  const GUID *v41; // rax
  int v42; // eax
  unsigned __int64 v43; // rax
  unsigned int v44; // r8d
  char **v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rsi
  bool v48; // cf
  __int64 VideoStreamingInputHeader; // rax
  __int64 v50; // r8
  int v51; // eax
  unsigned __int64 v52; // rax
  int v53; // r14d
  unsigned int j; // r13d
  __int64 v55; // rsi
  unsigned __int8 *TerminalUnitForBridgePin; // rax
  _DWORD *v57; // r14
  unsigned __int8 *v58; // rax
  int v59; // eax
  unsigned __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r9
  __int64 v63; // r8
  char v64; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v65; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v66; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v67; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int64 v68; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v69; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v70; // [rsp+4Ch] [rbp-B4h] BYREF
  char **v71; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v72; // [rsp+58h] [rbp-A8h]
  __int64 v73; // [rsp+60h] [rbp-A0h]
  unsigned int v74; // [rsp+68h] [rbp-98h]
  __int64 v75; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v76; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v77; // [rsp+A0h] [rbp-60h]
  __int64 v78; // [rsp+A8h] [rbp-58h]
  __int64 v79; // [rsp+B0h] [rbp-50h]
  __int64 v80; // [rsp+B8h] [rbp-48h]
  char v81[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 *v82; // [rsp+D0h] [rbp-30h]
  __int64 v83; // [rsp+D8h] [rbp-28h]
  unsigned int *v84; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h]
  unsigned int *v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]
  char *v88; // [rsp+100h] [rbp+0h]
  __int64 v89; // [rsp+108h] [rbp+8h]

  v4 = *(_QWORD *)(a1 + 16);
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v72 = (unsigned __int64)a4;
  v68 = (unsigned __int64)a3;
  v71 = a2;
  v73 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
  v6 = CountTerminalUnits(*(PUSB_CONFIGURATION_DESCRIPTOR *)(v4 + 32), &v65, &v66, &v67);
  v7 = v65;
  v8 = v6;
  v9 = v6;
  v10 = v66;
  v11 = v8 - v66;
  *(_DWORD *)(v4 + 712) = v67;
  v12 = v11 - v7;
  v74 = v10;
  v69 = v7;
  v70 = v12;
  *(_DWORD *)(v4 + 688) = v9;
  *(_DWORD *)(v4 + 700) = v7;
  *(_DWORD *)(v4 + 696) = v10;
  *(_DWORD *)(v4 + 692) = v12;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 4LL * (unsigned int)v9, 0x56425355u);
  v14 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 4LL * (unsigned int)v9);
  v15 = (void **)(v4 + 200);
  *(_QWORD *)(v4 + 200) = v14;
  if ( !v14 )
    return 3221225626LL;
  v16 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v14, FreeMem);
  if ( v16 < 0 )
  {
    v17 = *v15;
LABEL_10:
    ExFreePoolWithTag(v17, 0x56425355u);
    return (unsigned int)v16;
  }
  v19 = 0;
  v20 = 0;
  if ( (_DWORD)v9 )
  {
    v21 = 0;
    if ( (unsigned int)v9 < 4 || *v15 <= v15 && (char *)*v15 + 4 * (unsigned int)(v9 - 1) >= (char *)v15 )
      goto LABEL_73;
    v22 = v9 & 0xFFFFFFFC;
    do
      v21 += 4;
    while ( v21 < v22 );
    v23 = *v15;
    v66 = v21;
    memset(v23, -1, 16 * ((unsigned __int64)v22 >> 2));
    v21 = v66;
    if ( v66 < (unsigned int)v9 )
    {
LABEL_73:
      do
      {
        v24 = v21++;
        *((_DWORD *)*v15 + v24) = -1;
      }
      while ( v21 < (unsigned int)v9 );
    }
  }
  for ( i = 0; i < v12; v20 += v65 )
  {
    v66 = 0;
    v65 = 0;
    result = CountFormatsForVideoStreamingInterface(v4, i, (unsigned int)&v66, (unsigned int)&v65, 0);
    if ( (int)result < 0 )
      return result;
    v19 += v66;
    ++i;
  }
  v65 = v20 + v19;
  *(_DWORD *)v72 = 136;
  *(_DWORD *)v68 = v9;
  v26 = (unsigned int)(16 * (v7 + v20 + v19 + 27 * v9));
  v27 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v26, 0x56425355u);
  v28 = v27;
  if ( ExPoolZeroingNativelySupported || !v27 )
  {
    *v71 = v27;
    if ( v27 )
      goto LABEL_26;
    return 3221225626LL;
  }
  memset(v27, 0, (unsigned int)v26);
  *v71 = v28;
LABEL_26:
  v16 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(v73 + 8), v28, FreeMem);
  v17 = v28;
  if ( v16 < 0 )
    goto LABEL_10;
  LOBYTE(v66) = 0;
  LODWORD(v73) = v7 + v12;
  memset(v28, 0, v26);
  v29 = 16 * v7;
  v30 = 0;
  v31 = &v28[136 * v9];
  v32 = &v31[136 * v9];
  *(_QWORD *)(v4 + 744) = v31;
  *(_QWORD *)(v4 + 728) = v32;
  *(_QWORD *)(v4 + 752) = &v32[16 * v9];
  v33 = (__int64)&v32[48 * v9 + v29];
  v75 = (__int64)&v32[48 * v9];
  v71 = (char **)(v33 + 8LL * v65);
  if ( v12 )
  {
    while ( 1 )
    {
      v34 = 136LL * v30;
      v72 = v30;
      v67 = 0;
      LODWORD(v68) = 0;
      v65 = 0;
      result = CountFormatsForVideoStreamingInterface(
                 v4,
                 v30,
                 (unsigned int)&v67,
                 (unsigned int)&v65,
                 (__int64)&v31[v34 + 128]);
      if ( (int)result < 0 )
        break;
      result = GetPinDataRangesFromInterface(v30, v4, v33, (_DWORD)v71, (__int64)&v68);
      if ( (int)result < 0 )
        break;
      v35 = v67;
      *(_DWORD *)&v28[v34 + 16] = 0;
      *(_QWORD *)&v28[v34 + 24] = 0;
      *(_DWORD *)&v28[v34 + 32] = 0;
      *(_QWORD *)&v28[v34 + 40] = 0;
      *(_DWORD *)&v28[v34 + 48] = v35;
      *(_QWORD *)&v28[v34 + 56] = v33 & -(__int64)(v35 != 0);
      v36 = *(_QWORD *)(v4 + 728);
      v37 = 2 * v72;
      v67 = v35;
      *(_DWORD *)(v36 + 8 * v37) = v35;
      *(_QWORD *)(*(_QWORD *)(v4 + 728) + 8 * v37 + 8) = v71;
      result = GetDataFlowDirectionForInterface(*(_QWORD *)(v4 + 32), v30, &v28[v34 + 64]);
      if ( (int)result < 0 )
        break;
      v38 = *(_DWORD *)&v28[v34 + 64] == 1;
      v68 = v67;
      v39 = &off_1400433E0;
      if ( !v38 )
        v39 = &off_140043430;
      *(_QWORD *)&v28[136 * v30] = v39;
      v40 = 1;
      if ( !v38 )
        v40 = 3;
      *(_DWORD *)&v28[v34 + 68] = v40;
      v41 = 0;
      if ( !v38 )
        v41 = &PINNAME_VIDEO_CAPTURE;
      *(_QWORD *)&v28[v34 + 72] = v41;
      v42 = 2097184;
      if ( !v38 )
        v42 = 65552;
      *(_DWORD *)&v28[v34 + 104] = v42;
      *(_DWORD *)&v31[v34 + 120] = v38;
      *(_QWORD *)&v28[v34 + 108] = 1;
      *(_DWORD *)&v31[136 * v30] = -1;
      *(_DWORD *)&v31[v34 + 4] = 0;
      *(_DWORD *)&v31[v34 + 8] = v30;
      *(_QWORD *)&v31[v34 + 12] = 0;
      *(_QWORD *)&v31[v34 + 24] = 0;
      *(_QWORD *)&v31[v34 + 32] = 0;
      KeInitializeMutex((PRKMUTEX)&v31[v34 + 64], 0);
      KeInitializeEvent((PRKEVENT)&v31[v34 + 40], NotificationEvent, 0);
      KeInitializeSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v4 + 752) + 32 * v72), 1, 1);
      *(_QWORD *)&v28[v34 + 128] = &USBVideoPinDataIntersect;
      *(_QWORD *)&v28[v34 + 120] = AllocatorFraming;
      if ( (int)SelectZeroBandwidthInterface(v4, v30) < 0 )
        return 3221225858LL;
      v43 = v68;
      v44 = v65;
      v33 += 8 * v68;
      v68 = v33;
      v45 = &v71[v43];
      v71 = v45;
      if ( v65 )
      {
        v46 = (unsigned int)v73;
        v47 = 136LL * (unsigned int)v73;
        v48 = v67 != 0;
        v67 = -v67;
        v72 = (unsigned int)v73;
        *(_QWORD *)&v28[v47] = &off_140043390;
        v46 *= 2;
        *(_QWORD *)&v28[v47 + 56] = v68 & -(__int64)v48;
        *(_DWORD *)&v28[v47 + 16] = 0;
        *(_QWORD *)&v28[v47 + 24] = 0;
        *(_DWORD *)&v28[v47 + 32] = 0;
        *(_QWORD *)&v28[v47 + 40] = 0;
        *(_DWORD *)&v28[v47 + 48] = v44;
        *(_DWORD *)(*(_QWORD *)(v4 + 728) + 8 * v46) = v44;
        *(_QWORD *)(*(_QWORD *)(v4 + 728) + 8 * v46 + 8) = v45;
        *(_QWORD *)&v28[v47 + 72] = &PINNAME_VIDEO_STILL;
        *(_DWORD *)&v28[v47 + 64] = 2;
        *(_QWORD *)&v28[v47 + 108] = 1;
        *(_DWORD *)&v28[v47 + 68] = 3;
        *(_DWORD *)&v28[v47 + 104] = 65552;
        *(_DWORD *)&v31[v47] = -1;
        *(_DWORD *)&v31[v47 + 4] = 0;
        *(_DWORD *)&v31[v47 + 8] = v30;
        *(_DWORD *)&v31[v47 + 12] = 1;
        *(_QWORD *)&v31[v47 + 24] = 0;
        VideoStreamingInputHeader = GetVideoStreamingInputHeader(v30, *(_QWORD *)(v4 + 32));
        v50 = VideoStreamingInputHeader;
        if ( !VideoStreamingInputHeader )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
          return 3221225473LL;
        }
        v38 = *(_BYTE *)(VideoStreamingInputHeader + 9) == 2;
        v68 += 8LL * v65;
        v71 += v65;
        v51 = (unsigned __int8)v66;
        if ( v38 )
          v51 = 1;
        v38 = *(_BYTE *)(v50 + 10) == 0;
        v66 = v51;
        v52 = v72;
        *(_DWORD *)&v31[v47 + 16] = !v38;
        KeInitializeSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v4 + 752) + 32 * v52), 1, 1);
        LODWORD(v73) = v73 + 1;
        *(_QWORD *)&v28[v47 + 128] = &USBVideoPinDataIntersect;
        *(_QWORD *)&v28[v47 + 120] = AllocatorFraming;
        *(_DWORD *)&v31[v47 + 120] = 2;
        *(_QWORD *)&v31[v47 + 128] = *(_QWORD *)&v31[v34 + 128];
        v33 = v68;
      }
      v12 = v70;
      if ( ++v30 >= v70 )
        goto LABEL_46;
    }
  }
  else
  {
LABEL_46:
    if ( (_DWORD)v73 != (_DWORD)v9
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
    }
    v53 = 0;
    if ( v69 )
    {
      for ( j = 0; j < v69; ++j )
      {
        v55 = 136LL * v30;
        v72 = v30;
        *(_QWORD *)&v28[v55] = 0;
        *(_QWORD *)&v28[v55 + 8] = 0;
        *(_DWORD *)&v28[v55 + 16] = 0;
        *(_QWORD *)&v28[v55 + 24] = 0;
        *(_DWORD *)&v28[v55 + 32] = 0;
        *(_QWORD *)&v28[v55 + 40] = 0;
        *(_DWORD *)&v28[v55 + 48] = 0;
        *(_QWORD *)&v28[v55 + 56] = 0;
        *(_DWORD *)&v28[v55 + 68] = 4;
        TerminalUnitForBridgePin = GetTerminalUnitForBridgePin(*(PUSB_CONFIGURATION_DESCRIPTOR *)(v4 + 32), j);
        if ( TerminalUnitForBridgePin )
          v53 = (TerminalUnitForBridgePin[2] != 2) + 1;
        *(_DWORD *)&v28[v55 + 64] = v53;
        v57 = (_DWORD *)(v75 + 16LL * j);
        *(_QWORD *)&v28[v55 + 72] = v57;
        v58 = GetTerminalUnitForBridgePin(*(PUSB_CONFIGURATION_DESCRIPTOR *)(v4 + 32), j);
        if ( v58 )
        {
          v59 = *((unsigned __int16 *)v58 + 2);
          v57[1] = 1228616464;
          v57[2] = -507018838;
          v57[3] = 1903154482;
          *v57 = v59 + 1052538712;
        }
        v60 = v72;
        v53 = 0;
        *(_QWORD *)&v28[v55 + 108] = 0;
        *(_DWORD *)&v31[v55 + 8] = -1;
        *(_QWORD *)&v31[v55 + 12] = 0;
        *(_QWORD *)&v31[v55 + 24] = 0;
        *(_QWORD *)&v31[136 * v30] = 0;
        KeInitializeSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v4 + 752) + 32 * v60), 1, 1);
        ++v30;
      }
      v12 = v70;
    }
    if ( dword_14004C1E8 && (unsigned __int8)tlgKeywordOn(&dword_14004C1E8, 0x400000000000LL) )
    {
      v61 = *(_QWORD *)(v4 + 1368);
      v77 = &v75;
      v75 = 50333696;
      v79 = v4 + 1348;
      v78 = 8;
      v80 = 16;
      tlgCreate1Sz_wchar_t(v81, v61);
      LODWORD(v68) = v12;
      v82 = &v68;
      v83 = 4;
      v84 = &v70;
      v69 = v74;
      v86 = &v69;
      v64 = v66;
      v88 = &v64;
      v70 = v62;
      v85 = 4;
      v87 = 4;
      v89 = 1;
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_14004C1E8,
        (unsigned __int8 *)&dword_140048D9C,
        v63,
        v62,
        9u,
        &v76);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140023dfc  push    rbp
0x140023dfe  push    rbx
0x140023dff  push    rsi
0x140023e00  push    rdi
0x140023e01  push    r12
0x140023e03  push    r13
0x140023e05  push    r14
0x140023e07  push    r15
0x140023e09  lea     rbp, [rsp-28h]
0x140023e0e  sub     rsp, 128h
0x140023e15  mov     rax, cs:__security_cookie
0x140023e1c  xor     rax, rsp
0x140023e1f  mov     [rbp+60h+var_50], rax
0x140023e23  mov     rdi, [rcx+10h]
0x140023e27  xor     eax, eax
0x140023e29  mov     [rsp+160h+var_12C], eax
0x140023e2d  mov     r15, rcx
0x140023e30  mov     [rsp+160h+var_128], eax
0x140023e34  mov     [rsp+160h+var_124], eax
0x140023e38  mov     [rsp+160h+var_108], r9
0x140023e3d  mov     [rsp+160h+var_120], r8
0x140023e42  mov     [rsp+160h+var_110], rdx
0x140023e47  mov     [rsp+160h+var_100], rcx
0x140023e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e53  lea     rax, WPP_GLOBAL_Control
0x140023e5a  cmp     rcx, rax
0x140023e5d  jz      short loc_140023E7D
0x140023e5f  cmp     byte ptr [rcx+29h], 4
0x140023e63  jb      short loc_140023E7D
0x140023e65  mov     rcx, [rcx+18h]
0x140023e69  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x140023e70  mov     edx, 5Bh ; '['
0x140023e75  mov     r9, rdi
0x140023e78  call    WPP_SF_q
0x140023e7d  mov     rcx, [rdi+20h]; ConfigurationDescriptor
0x140023e81  lea     r9, [rsp+160h+var_124]
0x140023e86  lea     r8, [rsp+160h+var_128]
0x140023e8b  lea     rdx, [rsp+160h+var_12C]
0x140023e90  call    CountTerminalUnits
0x140023e95  mov     r12d, [rsp+160h+var_12C]
0x140023e9a  mov     r13d, eax
0x140023e9d  mov     ecx, [rsp+160h+var_124]
0x140023ea1  mov     r8d, 56425355h; Tag
0x140023ea7  mov     r14d, eax
0x140023eaa  mov     eax, [rsp+160h+var_128]
0x140023eae  mov     ebx, r14d
0x140023eb1  sub     r13d, eax
0x140023eb4  mov     [rdi+2C8h], ecx
0x140023eba  sub     r13d, r12d
0x140023ebd  shl     rbx, 2
0x140023ec1  mov     rdx, rbx; NumberOfBytes
0x140023ec4  mov     [rsp+160h+var_F8], eax
0x140023ec8  mov     ecx, 600h; PoolType
0x140023ecd  mov     [rsp+160h+var_118], r12d
0x140023ed2  mov     [rsp+160h+var_114], r13d
0x140023ed7  mov     [rdi+2B0h], r14d
0x140023ede  mov     [rdi+2BCh], r12d
0x140023ee5  mov     [rdi+2B8h], eax
0x140023eeb  mov     [rdi+2B4h], r13d
0x140023ef2  call    cs:__imp_ExAllocatePoolWithTag
0x140023ef9  nop     dword ptr [rax+rax+00h]
0x140023efe  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140023f05  mov     rsi, rax
0x140023f08  jnz     short loc_140023F1C
0x140023f0a  test    rax, rax
0x140023f0d  jz      short loc_140023F1C
0x140023f0f  mov     r8, rbx; Size
0x140023f12  xor     edx, edx; Val
0x140023f14  mov     rcx, rax; void *
0x140023f17  call    memset
0x140023f1c  lea     rbx, [rdi+0C8h]
0x140023f23  mov     [rbx], rsi
0x140023f26  test    rsi, rsi
0x140023f29  jz      loc_1400247A5
0x140023f2f  mov     rcx, [r15+8]; ObjectBag
0x140023f33  lea     r8, FreeMem; Free
0x140023f3a  mov     rdx, rsi; Item
0x140023f3d  call    cs:__imp_KsAddItemToObjectBag
0x140023f44  nop     dword ptr [rax+rax+00h]
0x140023f49  mov     esi, eax
0x140023f4b  test    eax, eax
0x140023f4d  jns     short loc_140023F6A
0x140023f4f  mov     rcx, [rbx]; P
0x140023f52  mov     edx, 56425355h; Tag
0x140023f57  call    cs:__imp_ExFreePoolWithTag
0x140023f5e  nop     dword ptr [rax+rax+00h]
0x140023f63  mov     eax, esi
0x140023f65  jmp     loc_1400247AA
0x140023f6a  xor     esi, esi
0x140023f6c  xor     r15d, r15d
0x140023f6f  lea     r8d, [rsi+1]
0x140023f73  test    r14d, r14d
0x140023f76  jz      short loc_140023FE3
0x140023f78  xor     edx, edx
0x140023f7a  cmp     r14d, 4
0x140023f7e  jb      short loc_140023FCF
0x140023f80  mov     r9, [rbx]
0x140023f83  cmp     r9, rbx
0x140023f86  ja      short loc_140023F95
0x140023f88  lea     eax, [r14-1]
0x140023f8c  lea     rax, [r9+rax*4]
0x140023f90  cmp     rax, rbx
0x140023f93  jnb     short loc_140023FCF
0x140023f95  mov     eax, r14d
0x140023f98  and     eax, 0FFFFFFFCh
0x140023f9b  add     edx, 4
0x140023f9e  cmp     edx, eax
0x140023fa0  jb      short loc_140023F9B
0x140023fa2  mov     r8d, eax
0x140023fa5  mov     rcx, r9; void *
0x140023fa8  shr     r8, 2
0x140023fac  shl     r8, 4
0x140023fb0  mov     [rsp+160h+var_128], edx
0x140023fb4  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x140023fb8  or      edx, 0FFFFFFFFh; Val
0x140023fbb  call    memset
0x140023fc0  mov     edx, [rsp+160h+var_128]
0x140023fc4  cmp     edx, r14d
0x140023fc7  jnb     short loc_140023FE3
0x140023fc9  mov     r8d, 1
0x140023fcf  mov     rax, [rbx]
0x140023fd2  mov     ecx, edx
0x140023fd4  add     edx, r8d
0x140023fd7  mov     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x140023fde  cmp     edx, r14d
0x140023fe1  jb      short loc_140023FCF
0x140023fe3  xor     ebx, ebx
0x140023fe5  test    r13d, r13d
0x140023fe8  jz      short loc_14002402F
0x140023fea  lea     r9, [rsp+160h+var_12C]
0x140023fef  mov     [rsp+160h+var_128], 0
0x140023ff7  lea     r8, [rsp+160h+var_128]
0x140023ffc  mov     [rsp+160h+var_12C], 0
0x140024004  mov     edx, ebx
0x140024006  mov     qword ptr [rsp+160h+var_140], 0
0x14002400f  mov     rcx, rdi
0x140024012  call    CountFormatsForVideoStreamingInterface
0x140024017  test    eax, eax
0x140024019  js      loc_1400247AA
0x14002401f  add     esi, [rsp+160h+var_128]
0x140024023  inc     ebx
0x140024025  add     r15d, [rsp+160h+var_12C]
0x14002402a  cmp     ebx, r13d
0x14002402d  jb      short loc_140023FEA
0x14002402f  mov     rax, [rsp+160h+var_108]
0x140024034  lea     ecx, [r15+rsi]
0x140024038  mov     [rsp+160h+var_12C], ecx
0x14002403c  mov     r8d, 56425355h; Tag
0x140024042  mov     dword ptr [rax], 88h
0x140024048  mov     rax, [rsp+160h+var_120]
0x14002404d  mov     [rax], r14d
0x140024050  imul    eax, r14d, 1Bh
0x140024054  add     eax, ecx
0x140024056  mov     ecx, 600h; PoolType
0x14002405b  add     eax, r12d
0x14002405e  shl     eax, 4
0x140024061  mov     edx, eax; NumberOfBytes
0x140024063  mov     r15d, eax
0x140024066  call    cs:__imp_ExAllocatePoolWithTag
0x14002406d  nop     dword ptr [rax+rax+00h]
0x140024072  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140024079  mov     rbx, rax
0x14002407c  jnz     short loc_14002409A
0x14002407e  test    rax, rax
0x140024081  jz      short loc_14002409A
0x140024083  mov     r8d, r15d; Size
0x140024086  xor     edx, edx; Val
0x140024088  mov     rcx, rax; void *
0x14002408b  call    memset
0x140024090  mov     rax, [rsp+160h+var_110]
0x140024095  mov     [rax], rbx
0x140024098  jmp     short loc_1400240AB
0x14002409a  mov     rax, [rsp+160h+var_110]
0x14002409f  mov     [rax], rbx
0x1400240a2  test    rbx, rbx
0x1400240a5  jz      loc_1400247A5
0x1400240ab  mov     rcx, [rsp+160h+var_100]
0x1400240b0  lea     r8, FreeMem; Free
0x1400240b7  mov     rdx, rbx; Item
0x1400240ba  mov     rcx, [rcx+8]; ObjectBag
0x1400240be  call    cs:__imp_KsAddItemToObjectBag
0x1400240c5  nop     dword ptr [rax+rax+00h]
0x1400240ca  mov     esi, eax
0x1400240cc  mov     rcx, rbx; void *
0x1400240cf  test    eax, eax
0x1400240d1  js      loc_140023F52
0x1400240d7  lea     eax, [r12+r13]
0x1400240db  mov     byte ptr [rsp+160h+var_128], 0
0x1400240e0  mov     r8, r15; Size
0x1400240e3  mov     dword ptr [rsp+160h+var_100], eax
0x1400240e7  xor     edx, edx; Val
0x1400240e9  call    memset
0x1400240ee  imul    rax, r14, 88h
0x1400240f5  xor     r9d, r9d
0x1400240f8  mov     rsi, r12
0x1400240fb  shl     rsi, 4
0x1400240ff  mov     r12d, r9d
0x140024102  lea     r15, [rax+rbx]
0x140024106  lea     rcx, [rax+r15]
0x14002410a  mov     [rdi+2E8h], r15
0x140024111  mov     rax, r14
0x140024114  mov     [rdi+2D8h], rcx
0x14002411b  shl     rax, 4
0x14002411f  lea     edx, [r9+3]
0x140024123  add     rax, rcx
0x140024126  mov     [rdi+2F0h], rax
0x14002412d  lea     rax, [r14+r14*2]
0x140024131  shl     rax, 4
0x140024135  add     rax, rcx
0x140024138  add     rsi, rax
0x14002413b  mov     [rsp+160h+var_F0], rax
0x140024140  mov     eax, [rsp+160h+var_12C]
0x140024144  lea     rax, [rsi+rax*8]
0x140024148  mov     [rsp+160h+var_110], rax
0x14002414d  test    r13d, r13d
0x140024150  jz      loc_1400244F6
0x140024156  mov     eax, r12d
0x140024159  lea     r8, [rsp+160h+var_124]
0x14002415e  imul    r13, rax, 88h
0x140024165  mov     [rsp+160h+var_108], rax
0x14002416a  mov     edx, r12d
0x14002416d  mov     [rsp+160h+var_124], r9d
0x140024172  lea     rax, [r15+80h]
0x140024179  add     rax, r13
0x14002417c  mov     dword ptr [rsp+160h+var_120], r9d
0x140024181  mov     [rsp+160h+var_12C], r9d
0x140024186  mov     rcx, rdi
0x140024189  lea     r9, [rsp+160h+var_12C]
0x14002418e  mov     qword ptr [rsp+160h+var_140], rax
0x140024193  call    CountFormatsForVideoStreamingInterface
0x140024198  test    eax, eax
0x14002419a  js      loc_1400247AA
0x1400241a0  mov     r9, [rsp+160h+var_110]
0x1400241a5  lea     rax, [rsp+160h+var_120]
0x1400241aa  mov     r8, rsi
0x1400241ad  mov     qword ptr [rsp+160h+var_140], rax
0x1400241b2  mov     rdx, rdi
0x1400241b5  mov     ecx, r12d
0x1400241b8  call    GetPinDataRangesFromInterface
0x1400241bd  xor     ecx, ecx
0x1400241bf  test    eax, eax
0x1400241c1  js      loc_1400247AA
0x1400241c7  mov     edx, [rsp+160h+var_124]
0x1400241cb  lea     r8, [rbx+40h]
0x1400241cf  mov     [rbx+r13+10h], ecx
0x1400241d4  mov     eax, edx
0x1400241d6  mov     [rbx+r13+18h], rcx
0x1400241db  neg     eax
0x1400241dd  mov     [rbx+r13+20h], ecx
0x1400241e2  mov     [rbx+r13+28h], rcx
0x1400241e7  sbb     rcx, rcx
0x1400241ea  mov     [rbx+r13+30h], edx
0x1400241ef  and     rcx, rsi
0x1400241f2  mov     [rbx+r13+38h], rcx
0x1400241f7  add     r8, r13
0x1400241fa  mov     rax, [rdi+2D8h]
0x140024201  mov     rcx, [rsp+160h+var_108]
0x140024206  add     rcx, rcx
0x140024209  mov     [rsp+160h+var_124], edx
0x14002420d  mov     [rax+rcx*8], edx
0x140024210  mov     rdx, [rsp+160h+var_110]
0x140024215  mov     rax, [rdi+2D8h]
0x14002421c  mov     [rax+rcx*8+8], rdx
0x140024221  mov     edx, r12d
0x140024224  mov     rcx, [rdi+20h]
0x140024228  call    GetDataFlowDirectionForInterface
0x14002422d  xor     r8d, r8d
0x140024230  test    eax, eax
0x140024232  js      loc_1400247AA
0x140024238  mov     eax, [rsp+160h+var_124]
0x14002423c  lea     r9d, [r8+1]
0x140024240  cmp     [rbx+r13+40h], r9d
0x140024245  lea     rdx, off_140043430
0x14002424c  mov     [rsp+160h+var_120], rax
0x140024251  lea     rcx, [r15+40h]
0x140024255  lea     rax, off_1400433E0
0x14002425c  cmovnz  rax, rdx
0x140024260  lea     edx, [r8+3]
0x140024264  mov     [rbx+r13], rax
0x140024268  mov     eax, r9d
0x14002426b  cmovnz  eax, edx
0x14002426e  lea     rdx, PINNAME_VIDEO_CAPTURE
0x140024275  mov     [rbx+r13+44h], eax
0x14002427a  mov     eax, r8d
0x14002427d  cmovnz  rax, rdx
0x140024281  mov     edx, 10010h
0x140024286  mov     [rbx+r13+48h], rax
0x14002428b  mov     eax, 200020h
0x140024290  cmovnz  eax, edx
0x140024293  mov     [rbx+r13+68h], eax
0x140024298  mov     eax, r8d
0x14002429b  setz    al
0x14002429e  add     rcx, r13; Mutex
0x1400242a1  mov     [r15+r13+78h], eax
0x1400242a6  xor     edx, edx; Level
0x1400242a8  mov     [rbx+r13+6Ch], r9
0x1400242ad  mov     dword ptr [r15+r13], 0FFFFFFFFh
0x1400242b5  mov     [r15+r13+4], r8d
0x1400242ba  mov     [r15+r13+8], r12d
0x1400242bf  mov     [r15+r13+0Ch], r8
  ... truncated ...
```
