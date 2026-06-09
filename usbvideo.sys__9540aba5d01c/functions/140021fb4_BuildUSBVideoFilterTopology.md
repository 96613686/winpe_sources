# BuildUSBVideoFilterTopology

- ea: `0x140021fb4`
- end: `0x14002288d`
- name: `BuildUSBVideoFilterTopology`
- size: `2265`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001bdfc`

## callees

- `0x140001008`
- `0x140001048`
- `0x140001078`
- `0x14000cb20`
- `0x14000d790`
- `0x14000e964`
- `0x1400125c0`
- `0x140012d6c`
- `0x140019d98`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001e3e8`
- `0x140021fb4`
- `0x1400228a0`
- `0x1400229b0`
- `0x140022ac0`
- `0x140022cd0`
- `0x140022e40`
- `0x140022f90`
- `0x140040a30`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002237d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002237d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022326`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022326`
- `ks!KsAddItemToObjectBag` at `0x140022362`
- `ks!KsAddItemToObjectBag` at `0x140022362`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400225d6`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140022700`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400225d6`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140022700`

## pseudocode

```c
__int64 __fastcall BuildUSBVideoFilterTopology(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  unsigned __int16 v7; // ax
  __int64 result; // rax
  int v9; // edx
  int v10; // ebx
  int v11; // r13d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // r14
  __int64 v16; // r12
  SIZE_T v17; // r15
  GUID *PoolWithTag; // rax
  GUID *v19; // rsi
  NTSTATUS v20; // r15d
  GUID *v21; // rcx
  int *v22; // r15
  unsigned int v23; // r10d
  int *v24; // r12
  unsigned int v25; // edx
  GUID *v26; // r15
  __int64 v27; // rax
  __int64 v28; // rcx
  _DWORD *v29; // r12
  unsigned int v30; // ecx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r9
  int v38; // r10d
  int v39; // r8d
  unsigned int v40; // r8d
  unsigned int v41; // edx
  PUSB_INTERFACE_DESCRIPTOR v42; // rax
  GUID *v43; // r13
  unsigned __int8 *VideoSpecificDescriptor; // rax
  unsigned __int8 *v45; // rsi
  int v46; // edx
  int i; // r8d
  __int64 v48; // rax
  unsigned __int8 *v49; // rbx
  unsigned __int8 *p_bLength; // r12
  unsigned int v51; // r9d
  int v52; // eax
  int v53; // edx
  int v54; // r8d
  unsigned int v55; // r8d
  unsigned int j; // ebx
  int v57; // [rsp+40h] [rbp-C0h] BYREF
  int v58; // [rsp+44h] [rbp-BCh] BYREF
  int v59; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v60; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v61; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+54h] [rbp-ACh] BYREF
  GUID *v63; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v66; // [rsp+78h] [rbp-88h] BYREF
  int *v67; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h]
  __int64 v69[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  _BYTE v74[16]; // [rsp+D0h] [rbp-30h] BYREF
  int *v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  int *v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  GUID *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]

  v1 = *(_QWORD *)(a1 + 16);
  v61 = 0;
  LODWORD(v64) = 0;
  v62 = 0;
  v59 = 0;
  v60 = 0;
  v66 = 0;
  v68 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1);
  if ( dword_14004C1E8 && (unsigned __int8)tlgKeywordOn(&dword_14004C1E8, 0x400000000000LL) )
  {
    v3 = *(_QWORD *)(v1 + 1368);
    v70 = &v65;
    v65 = 50333696;
    v72 = v1 + 1348;
    v71 = 8;
    v73 = 16;
    tlgCreate1Sz_wchar_t(v74, v3);
    v6 = *(_QWORD *)(v1 + 32);
    LOWORD(v58) = *(_WORD *)(v6 + 2);
    v75 = &v58;
    v76 = 2;
    v7 = *(_WORD *)(v6 + 2);
    if ( v7 >= 0xC00u )
      v7 = 3072;
    LOWORD(v57) = v7;
    v80 = v7;
    v77 = &v57;
    v79 = (GUID *)v6;
    v78 = 2;
    v81 = 0;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_14004C1E8, (int)&dword_140048CA4, v4, v5, 8u, (__int64)v69);
  }
  result = CountTopologyComponents(*(PVOID *)(v1 + 32), (__int64)&v62);
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  v10 = 1;
  v57 = 0;
  LODWORD(v65) = 1;
  if ( (v62 & 8) == 0 )
  {
    v58 = 0;
    v11 = 0;
    goto LABEL_36;
  }
  v58 = 1;
  LODWORD(v67) = 0;
  LODWORD(v63) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1);
  if ( (int)GetDeviceRegValueDword(*(_QWORD *)(a1 + 32), 1, L"SkipCameraEnumeration", &v67) >= 0 && (_DWORD)v67 )
  {
    v10 = 0;
    LODWORD(v65) = 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_22;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1);
LABEL_22:
  if ( (int)GetDeviceRegValueDword(*(_QWORD *)(a1 + 32), 1, L"SensorCameraMode", &v63) >= 0 && (_DWORD)v63 )
  {
    v9 = 1;
    v57 = 1;
    if ( (unsigned int)v63 <= 1 )
    {
      v11 = 0;
      v58 = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v13 = 25;
        goto LABEL_28;
      }
    }
    else
    {
      v11 = 1;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v13 = 24;
LABEL_28:
        WPP_SF_q(v12->AttachedDevice, v13, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1);
        v9 = 1;
      }
    }
  }
  else
  {
    v9 = 0;
    v11 = v10;
  }
  if ( !v10 )
  {
    v14 = v61;
    goto LABEL_37;
  }
LABEL_36:
  v14 = v61 + 1;
LABEL_37:
  if ( v11 )
    ++v14;
  if ( v9 )
    ++v14;
  if ( v14 > 0x3E8 )
    return 3221225485LL;
  v15 = (unsigned int)v64;
  if ( (unsigned int)v64 > 0x3E8 || HIDWORD(v62) > 0x2710 )
    return 3221225485LL;
  v16 = HIDWORD(v62);
  v17 = 16 * (v14 + HIDWORD(v62) + 32LL * (unsigned int)v64);
  PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, v17, 0x56425355u);
  v19 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v17);
      goto LABEL_47;
    }
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
LABEL_47:
  v20 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(v68 + 8), v19, FreeMem);
  if ( v20 < 0 )
  {
    ExFreePoolWithTag(v19, 0x56425355u);
    return (unsigned int)v20;
  }
  v21 = &v19[v14];
  LODWORD(v64) = v62 & 4;
  v63 = v21;
  *(_DWORD *)(v1 + 116) = 480;
  *(_QWORD *)(v1 + 104) = v19;
  v22 = (int *)&v21[30 * v15];
  *(_QWORD *)(v1 + 120) = v21;
  v67 = v22;
  *(_QWORD *)(v1 + 136) = v22;
  memset(v21, 0, 480 * v15);
  v23 = 0;
  v24 = &v22[4 * v16];
  v25 = 0;
  if ( (_DWORD)v15 )
  {
    v26 = v63;
    do
    {
      v27 = v25++;
      v28 = 30 * v27;
      *(_QWORD *)v26[v28].Data4 = v24;
      v29 = v24 + 4;
      *(_QWORD *)&v26[v28 + 1].Data1 = v29;
      v24 = v29 + 4;
    }
    while ( v25 < (unsigned int)v15 );
    v22 = v67;
  }
  v30 = 0;
  if ( v57 )
  {
    v30 = 1;
    *v19 = KSCATEGORY_SENSOR_CAMERA;
  }
  if ( (_DWORD)v65 )
  {
    v31 = v30++;
    v19[v31] = KSCATEGORY_VIDEO;
  }
  if ( (_DWORD)v64 )
  {
    v32 = v30;
    v33 = v30 + 1;
    v19[v32] = KSCATEGORY_RENDER;
    v34 = v33;
    v30 = v33 + 1;
    v19[v34] = (GUID)KSCATEGORY_RENDER_EXTERNAL;
  }
  if ( v58 )
  {
    v35 = v30++;
    v19[v35] = KSCATEGORY_CAPTURE;
  }
  if ( v11 )
    v19[v30] = KSCATEGORY_VIDEO_CAMERA;
  *(_DWORD *)(v1 + 96) = v14;
  if ( dword_14004C1E8 && (unsigned __int8)tlgKeywordOn(&dword_14004C1E8, 0x400000000000LL) )
  {
    v36 = *(_QWORD *)(v1 + 1368);
    v70 = &v65;
    v65 = 50333696;
    v72 = v1 + 1348;
    v71 = 8;
    v73 = 16;
    tlgCreate1Sz_wchar_t(v74, v36);
    v64 = v14;
    v76 = v37;
    v75 = (int *)&v64;
    v77 = &v57;
    v80 = 16 * (unsigned __int16)v14;
    LOWORD(v57) = v14;
    v78 = 2;
    v79 = v19;
    v81 = v38;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_14004C1E8, (int)&byte_140048D33, v39, v37, v37, (__int64)v69);
    v23 = 0;
  }
  v40 = *(_DWORD *)(v1 + 80);
  v41 = v23;
  if ( v40 )
  {
    do
    {
      if ( *(_DWORD *)(136LL * v41 + *(_QWORD *)(v1 + 88) + 68) == 4 )
        break;
      ++v41;
    }
    while ( v41 < v40 );
  }
  v66 = v41;
  v42 = USBD_ParseConfigurationDescriptorEx(
          *(PUSB_CONFIGURATION_DESCRIPTOR *)(v1 + 32),
          *(PVOID *)(v1 + 32),
          -1,
          -1,
          14,
          1,
          -1);
  v43 = v63;
LABEL_82:
  p_bLength = &v42->bLength;
  if ( v42 )
  {
    VideoSpecificDescriptor = (unsigned __int8 *)GetVideoSpecificDescriptor(*(PVOID *)(v1 + 32));
    v45 = VideoSpecificDescriptor;
    if ( !VideoSpecificDescriptor )
      return 3221225488LL;
    v46 = *(unsigned __int16 *)(VideoSpecificDescriptor + 5);
    for ( i = (_DWORD)VideoSpecificDescriptor + *VideoSpecificDescriptor; ; i = (_DWORD)v49 + *v49 )
    {
      v49 = (unsigned __int8 *)USBParseDescriptorWrapper((_DWORD)v45, v46, i, 36, 4);
      if ( !v49 )
      {
        v42 = USBD_ParseConfigurationDescriptorEx(
                *(PUSB_CONFIGURATION_DESCRIPTOR *)(v1 + 32),
                &p_bLength[*p_bLength],
                -1,
                -1,
                14,
                1,
                -1);
        goto LABEL_82;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1, v49[3]);
      v48 = v49[2];
      if ( (unsigned __int8)v48 >= 8u )
        break;
      result = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, GUID *, int *, int *, unsigned int *, unsigned int *))funcs_14002269C[v48])(
                 v68,
                 v49,
                 v43,
                 v22,
                 &v59,
                 &v60,
                 &v66);
      if ( (int)result < 0 )
        return result;
      v46 = *(unsigned __int16 *)(v45 + 5);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids, v1, v49[2]);
    return 3221225485LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qdddd(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids,
      v1,
      HIDWORD(v62),
      v60,
      v15,
      v59);
  v51 = 0;
  *(_DWORD *)(v1 + 112) = v59;
  for ( *(_DWORD *)(v1 + 128) = v60; v51 < v60; ++v51 )
  {
    v52 = *v22;
    if ( *v22 != -1 )
    {
      if ( v52 >= 0 )
      {
        v59 = v15;
        if ( (_DWORD)v15 )
        {
          v53 = v15;
          v54 = v15;
          while ( 1 )
          {
            v55 = v54 - 1;
            if ( *v22 == *(unsigned __int8 *)(*(_QWORD *)&v43[30 * v55 + 2].Data1 + 3LL) )
              break;
            v59 = --v53;
            v54 = v53;
            if ( !v53 )
              goto LABEL_103;
          }
          *v22 = v55;
          if ( v22[2] == -1 )
            *(_DWORD *)(*(_QWORD *)(v1 + 200) + 4LL * (unsigned int)v22[3]) = v55;
        }
      }
      else
      {
        *v22 = v52 & 0x7FFFFFFF;
      }
    }
LABEL_103:
    v22 += 4;
  }
  for ( j = 0; j < (unsigned int)v15; ++j )
    BuildNodeAutomationTable(&v43[30 * j], v68);
  return 0;
}

```

## disassembly

```asm
0x140021fb4  push    rbp
0x140021fb6  push    rbx
0x140021fb7  push    rsi
0x140021fb8  push    rdi
0x140021fb9  push    r12
0x140021fbb  push    r13
0x140021fbd  push    r14
0x140021fbf  push    r15
0x140021fc1  lea     rbp, [rsp-28h]
0x140021fc6  sub     rsp, 128h
0x140021fcd  mov     rax, cs:__security_cookie
0x140021fd4  xor     rax, rsp
0x140021fd7  mov     [rbp+60h+var_50], rax
0x140021fdb  mov     rdi, [rcx+10h]
0x140021fdf  xor     r14d, r14d
0x140021fe2  mov     [rsp+160h+var_110], r14d
0x140021fe7  mov     rsi, rcx
0x140021fea  mov     dword ptr [rsp+160h+var_F8], r14d
0x140021fef  mov     dword ptr [rsp+160h+var_10C+4], r14d
0x140021ff4  mov     dword ptr [rsp+160h+var_10C], r14d
0x140021ff9  mov     [rsp+160h+var_118], r14d
0x140021ffe  mov     [rsp+160h+var_114], r14d
0x140022003  mov     [rsp+160h+var_E8], r14d
0x140022008  mov     [rbp+60h+var_D8], rcx
0x14002200c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022013  lea     r13, WPP_GLOBAL_Control
0x14002201a  cmp     rcx, r13
0x14002201d  jz      short loc_14002203C
0x14002201f  cmp     byte ptr [rcx+29h], 5
0x140022023  jb      short loc_14002203C
0x140022025  mov     rcx, [rcx+18h]
0x140022029  lea     edx, [r14+14h]
0x14002202d  mov     r9, rdi
0x140022030  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x140022037  call    WPP_SF_q
0x14002203c  mov     eax, cs:dword_14004C1E8
0x140022042  mov     r12d, 8
0x140022048  test    eax, eax
0x14002204a  jz      loc_14002211A
0x140022050  mov     rdx, 400000000000h
0x14002205a  lea     rcx, dword_14004C1E8
0x140022061  call    _tlgKeywordOn
0x140022066  test    al, al
0x140022068  jz      loc_14002211A
0x14002206e  mov     rdx, [rdi+558h]
0x140022075  lea     rax, [rsp+160h+var_F0]
0x14002207a  mov     [rbp+60h+var_B0], rax
0x14002207e  lea     rcx, [rbp+60h+var_90]
0x140022082  lea     rax, [rdi+544h]
0x140022089  mov     [rsp+160h+var_F0], 3000800h
0x140022092  mov     [rbp+60h+var_A0], rax
0x140022096  mov     [rbp+60h+var_A8], r12
0x14002209a  mov     [rbp+60h+var_98], 10h
0x1400220a2  call    _tlgCreate1Sz_wchar_t
0x1400220a7  mov     rcx, [rdi+20h]
0x1400220ab  mov     edx, 0C00h
0x1400220b0  movzx   eax, word ptr [rcx+2]
0x1400220b4  mov     word ptr [rsp+160h+var_11C], ax
0x1400220b9  lea     rax, [rsp+160h+var_11C]
0x1400220be  mov     [rbp+60h+var_80], rax
0x1400220c2  mov     [rbp+60h+var_78], 2
0x1400220ca  movzx   eax, word ptr [rcx+2]
0x1400220ce  cmp     ax, dx
0x1400220d1  jb      short loc_1400220D5
0x1400220d3  mov     eax, edx
0x1400220d5  mov     word ptr [rsp+160h+var_120], ax
0x1400220da  lea     rdx, [rsp+160h+var_120]
0x1400220df  movzx   eax, ax
0x1400220e2  mov     [rbp+60h+var_58], eax
0x1400220e5  lea     rax, [rbp+60h+var_D0]
0x1400220e9  mov     [rbp+60h+var_70], rdx
0x1400220ed  lea     rdx, dword_140048CA4; int
0x1400220f4  mov     [rbp+60h+var_60], rcx
0x1400220f8  lea     rcx, dword_14004C1E8; int
0x1400220ff  mov     qword ptr [rsp+160h+InterfaceSubClass], rax; __int64
0x140022104  mov     [rsp+160h+InterfaceClass], r12d; ULONG
0x140022109  mov     [rbp+60h+var_68], 2
0x140022111  mov     [rbp+60h+var_54], r14d
0x140022115  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002211a  mov     rcx, [rdi+20h]; DescriptorBuffer
0x14002211e  lea     rax, [rsp+160h+var_10C]
0x140022123  lea     r9, [rsp+160h+var_10C+4]
0x140022128  mov     qword ptr [rsp+160h+InterfaceClass], rax; __int64
0x14002212d  lea     r8, [rsp+160h+var_F8]
0x140022132  lea     rdx, [rsp+160h+var_110]
0x140022137  call    CountTopologyComponents
0x14002213c  test    eax, eax
0x14002213e  js      loc_1400227D8
0x140022144  mov     r15d, 1
0x14002214a  mov     edx, r14d
0x14002214d  mov     ebx, r15d
0x140022150  mov     [rsp+160h+var_120], edx
0x140022154  mov     dword ptr [rsp+160h+var_F0], ebx
0x140022158  test    byte ptr [rsp+160h+var_10C], r12b
0x14002215d  jz      loc_1400222BA
0x140022163  mov     [rsp+160h+var_11C], r15d
0x140022168  mov     dword ptr [rbp+60h+var_E0], r14d
0x14002216c  mov     dword ptr [rsp+160h+var_100], r14d
0x140022171  mov     rcx, cs:WPP_GLOBAL_Control
0x140022178  cmp     rcx, r13
0x14002217b  jz      short loc_14002219A
0x14002217d  cmp     byte ptr [rcx+29h], 4
0x140022181  jb      short loc_14002219A
0x140022183  mov     rcx, [rcx+18h]
0x140022187  lea     edx, [r15+14h]
0x14002218b  mov     r9, rdi
0x14002218e  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x140022195  call    WPP_SF_q
0x14002219a  mov     rcx, [rsi+20h]
0x14002219e  lea     r9, [rbp+60h+var_E0]
0x1400221a2  lea     r8, aSkipcameraenum; "SkipCameraEnumeration"
0x1400221a9  mov     edx, r15d
0x1400221ac  call    GetDeviceRegValueDword
0x1400221b1  mov     r12b, 3
0x1400221b4  test    eax, eax
0x1400221b6  js      short loc_1400221EF
0x1400221b8  cmp     dword ptr [rbp+60h+var_E0], r14d
0x1400221bc  jbe     short loc_1400221EF
0x1400221be  mov     ebx, r14d
0x1400221c1  mov     dword ptr [rsp+160h+var_F0], ebx
0x1400221c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221cc  cmp     rcx, r13
0x1400221cf  jz      short loc_140022219
0x1400221d1  cmp     [rcx+29h], r12b
0x1400221d5  jb      short loc_1400221EF
0x1400221d7  mov     rcx, [rcx+18h]
0x1400221db  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x1400221e2  mov     edx, 16h
0x1400221e7  mov     r9, rdi
0x1400221ea  call    WPP_SF_q
0x1400221ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221f6  cmp     rcx, r13
0x1400221f9  jz      short loc_140022219
0x1400221fb  cmp     byte ptr [rcx+29h], 4
0x1400221ff  jb      short loc_140022219
0x140022201  mov     rcx, [rcx+18h]
0x140022205  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x14002220c  mov     edx, 17h
0x140022211  mov     r9, rdi
0x140022214  call    WPP_SF_q
0x140022219  mov     rcx, [rsi+20h]
0x14002221d  lea     r9, [rsp+160h+var_100]
0x140022222  lea     r8, aSensorcameramo; "SensorCameraMode"
0x140022229  mov     edx, r15d
0x14002222c  call    GetDeviceRegValueDword
0x140022231  test    eax, eax
0x140022233  js      short loc_1400222AA
0x140022235  mov     eax, dword ptr [rsp+160h+var_100]
0x140022239  test    eax, eax
0x14002223b  jz      short loc_1400222AA
0x14002223d  mov     edx, r15d
0x140022240  mov     [rsp+160h+var_120], edx
0x140022244  cmp     eax, r15d
0x140022247  jbe     short loc_140022282
0x140022249  mov     r13d, r15d
0x14002224c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022253  lea     rax, WPP_GLOBAL_Control
0x14002225a  cmp     rcx, rax
0x14002225d  jz      short loc_1400222B0
0x14002225f  cmp     [rcx+29h], r12b
0x140022263  jb      short loc_1400222B0
0x140022265  mov     edx, 18h
0x14002226a  mov     rcx, [rcx+18h]
0x14002226e  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x140022275  mov     r9, rdi
0x140022278  call    WPP_SF_q
0x14002227d  mov     edx, r15d
0x140022280  jmp     short loc_1400222B0
0x140022282  mov     r13d, r14d
0x140022285  mov     [rsp+160h+var_11C], r14d
0x14002228a  mov     rcx, cs:WPP_GLOBAL_Control
0x140022291  lea     rax, WPP_GLOBAL_Control
0x140022298  cmp     rcx, rax
0x14002229b  jz      short loc_1400222B0
0x14002229d  cmp     [rcx+29h], r12b
0x1400222a1  jb      short loc_1400222B0
0x1400222a3  mov     edx, 19h
0x1400222a8  jmp     short loc_14002226A
0x1400222aa  mov     edx, r14d
0x1400222ad  mov     r13d, ebx
0x1400222b0  test    ebx, ebx
0x1400222b2  jnz     short loc_1400222C2
0x1400222b4  mov     ebx, [rsp+160h+var_110]
0x1400222b8  jmp     short loc_1400222C9
0x1400222ba  mov     [rsp+160h+var_11C], r14d
0x1400222bf  mov     r13d, r14d
0x1400222c2  mov     ebx, [rsp+160h+var_110]
0x1400222c6  add     ebx, r15d
0x1400222c9  test    r13d, r13d
0x1400222cc  jz      short loc_1400222D1
0x1400222ce  add     ebx, r15d
0x1400222d1  test    edx, edx
0x1400222d3  jz      short loc_1400222D8
0x1400222d5  add     ebx, r15d
0x1400222d8  mov     eax, 3E8h
0x1400222dd  cmp     ebx, eax
0x1400222df  ja      loc_1400227D3
0x1400222e5  mov     r14d, dword ptr [rsp+160h+var_F8]
0x1400222ea  cmp     r14d, eax
0x1400222ed  ja      loc_1400227D3
0x1400222f3  mov     eax, dword ptr [rsp+160h+var_10C+4]
0x1400222f7  cmp     eax, 2710h
0x1400222fc  ja      loc_1400227D3
0x140022302  mov     ecx, ebx
0x140022304  mov     r15d, r14d
0x140022307  shl     r15, 5
0x14002230b  mov     r8d, 56425355h; Tag
0x140022311  add     r15, rax
0x140022314  mov     r12d, eax
0x140022317  add     r15, rcx
0x14002231a  mov     ecx, 600h; PoolType
0x14002231f  shl     r15, 4
0x140022323  mov     rdx, r15; NumberOfBytes
0x140022326  call    cs:__imp_ExAllocatePoolWithTag
0x14002232d  nop     dword ptr [rax+rax+00h]
0x140022332  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140022339  mov     rsi, rax
0x14002233c  jnz     short loc_140022391
0x14002233e  test    rax, rax
0x140022341  jz      short loc_140022396
0x140022343  mov     r8, r15; Size
0x140022346  xor     edx, edx; Val
0x140022348  mov     rcx, rax; void *
0x14002234b  call    memset
0x140022350  mov     rax, [rbp+60h+var_D8]
0x140022354  lea     r8, FreeMem; Free
0x14002235b  mov     rdx, rsi; Item
0x14002235e  mov     rcx, [rax+8]; ObjectBag
0x140022362  call    cs:__imp_KsAddItemToObjectBag
0x140022369  nop     dword ptr [rax+rax+00h]
0x14002236e  mov     r15d, eax
0x140022371  test    eax, eax
0x140022373  jns     short loc_1400223A0
0x140022375  mov     edx, 56425355h; Tag
0x14002237a  mov     rcx, rsi; P
0x14002237d  call    cs:__imp_ExFreePoolWithTag
0x140022384  nop     dword ptr [rax+rax+00h]
0x140022389  mov     eax, r15d
0x14002238c  jmp     loc_1400227D8
0x140022391  test    rsi, rsi
0x140022394  jnz     short loc_140022350
0x140022396  mov     eax, 0C000009Ah
0x14002239b  jmp     loc_1400227D8
0x1400223a0  mov     eax, dword ptr [rsp+160h+var_10C]
0x1400223a4  xor     edx, edx; Val
0x1400223a6  imul    r8, r14, 1E0h; Size
0x1400223ad  and     eax, 4
0x1400223b0  mov     ecx, ebx
0x1400223b2  shl     rcx, 4
0x1400223b6  add     rcx, rsi; void *
0x1400223b9  mov     dword ptr [rsp+160h+var_F8], eax
0x1400223bd  mov     [rsp+160h+var_100], rcx
0x1400223c2  mov     dword ptr [rdi+74h], 1E0h
0x1400223c9  mov     [rdi+68h], rsi
0x1400223cd  lea     r15, [r8+rcx]
0x1400223d1  mov     [rdi+78h], rcx
0x1400223d5  mov     [rbp+60h+var_E0], r15
0x1400223d9  mov     [rdi+88h], r15
0x1400223e0  call    memset
0x1400223e5  shl     r12, 4
0x1400223e9  xor     r10d, r10d
0x1400223ec  add     r12, r15
0x1400223ef  mov     edx, r10d
0x1400223f2  test    r14d, r14d
0x1400223f5  jz      short loc_140022422
0x1400223f7  mov     r15, [rsp+160h+var_100]
0x1400223fc  mov     eax, edx
0x1400223fe  inc     edx
0x140022400  imul    rcx, rax, 1E0h
0x140022407  mov     [rcx+r15+8], r12
0x14002240c  add     r12, 10h
0x140022410  mov     [rcx+r15+10h], r12
0x140022415  add     r12, 10h
0x140022419  cmp     edx, r14d
0x14002241c  jb      short loc_1400223FC
0x14002241e  mov     r15, [rbp+60h+var_E0]
0x140022422  mov     ecx, r10d
0x140022425  mov     r12d, 1
0x14002242b  cmp     [rsp+160h+var_120], r10d
0x140022430  jz      short loc_140022440
0x140022432  movups  xmm0, xmmword ptr cs:KSCATEGORY_SENSOR_CAMERA.Data1
0x140022439  mov     ecx, r12d
0x14002243c  movdqu  xmmword ptr [rsi], xmm0
0x140022440  cmp     dword ptr [rsp+160h+var_F0], r10d
0x140022445  jz      short loc_14002245B
0x140022447  movups  xmm0, xmmword ptr cs:KSCATEGORY_VIDEO.Data1
0x14002244e  mov     eax, ecx
0x140022450  add     rax, rax
0x140022453  add     ecx, r12d
0x140022456  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x14002245b  cmp     dword ptr [rsp+160h+var_F8], r10d
0x140022460  jz      short loc_14002248A
0x140022462  movups  xmm0, xmmword ptr cs:KSCATEGORY_RENDER.Data1
0x140022469  mov     eax, ecx
0x14002246b  add     ecx, r12d
0x14002246e  add     rax, rax
0x140022471  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x140022476  mov     eax, ecx
0x140022478  movups  xmm0, cs:KSCATEGORY_RENDER_EXTERNAL
0x14002247f  add     rax, rax
  ... truncated ...
```
