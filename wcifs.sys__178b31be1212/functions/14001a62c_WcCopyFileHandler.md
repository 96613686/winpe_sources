# WcCopyFileHandler

- ea: `0x14001a62c`
- end: `0x14001b082`
- name: `WcCopyFileHandler`
- size: `2646`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140031e90`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x1400142d0`
- `0x14001a62c`
- `0x14001d8dc`
- `0x140029d84`
- `0x14002c8d4`
- `0x14002ca2c`
- `0x14002cb38`
- `0x14002daa4`
- `0x14002f9e4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001afe2`
- `ntoskrnl!ObfDereferenceObject` at `0x14001afe2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b027`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b05f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b027`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b05f`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa07`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa73`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa07`
- `ntoskrnl!ExAllocatePool2` at `0x14001aa73`
- `FLTMGR!FltClose` at `0x14001afcd`
- `FLTMGR!FltClose` at `0x14001afcd`
- `FLTMGR!FltObjectDereference` at `0x14001aff8`
- `FLTMGR!FltObjectDereference` at `0x14001b00d`
- `FLTMGR!FltObjectDereference` at `0x14001aff8`
- `FLTMGR!FltObjectDereference` at `0x14001b00d`

## pseudocode

```c
__int64 __fastcall WcCopyFileHandler(__int64 a1, __int64 a2)
{
  unsigned int v3; // ecx
  __int128 *v4; // rsi
  char v5; // r15
  NTSTATUS InstanceFromVolumeName; // ebx
  int v7; // r9d
  int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  unsigned int v11; // r10d
  unsigned int v12; // ebx
  unsigned int v13; // r11d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  USHORT v16; // ax
  USHORT *v17; // r15
  int v18; // edx
  int v19; // r9d
  USHORT *v20; // r14
  char v21; // al
  int v22; // r10d
  int v23; // edx
  int v24; // edx
  char v26; // [rsp+30h] [rbp-D0h]
  char v27; // [rsp+30h] [rbp-D0h]
  char v28; // [rsp+38h] [rbp-C8h]
  char v29; // [rsp+38h] [rbp-C8h]
  int v30; // [rsp+38h] [rbp-C8h]
  char v31; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[7]; // [rsp+71h] [rbp-8Fh] BYREF
  PVOID FltObject; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  PVOID Object; // [rsp+88h] [rbp-78h] BYREF
  USHORT v36[4]; // [rsp+90h] [rbp-70h] BYREF
  PVOID Pool2; // [rsp+98h] [rbp-68h]
  USHORT pusResult[4]; // [rsp+A0h] [rbp-60h] BYREF
  PVOID P; // [rsp+A8h] [rbp-58h]
  __int128 *v40; // [rsp+B0h] [rbp-50h]
  HANDLE FileHandle; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v42; // [rsp+C0h] [rbp-40h] BYREF
  UNICODE_STRING InstanceName; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING VolumeName; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING v45; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v47; // [rsp+108h] [rbp+8h]
  char v48; // [rsp+160h] [rbp+60h] BYREF
  char v49; // [rsp+168h] [rbp+68h]
  char v50; // [rsp+170h] [rbp+70h] BYREF
  char v51; // [rsp+178h] [rbp+78h] BYREF

  FileHandle = 0;
  Object = 0;
  v3 = *(_DWORD *)(a1 + 4);
  *(_QWORD *)pusResult = 0;
  v4 = 0;
  *(_QWORD *)v36 = 0;
  v5 = 0;
  FltObject = 0;
  v42 = 0;
  v51 = 0;
  v50 = 0;
  v31 = 0;
  v48 = 0;
  v32[0] = 0;
  v40 = 0;
  v47 = 0;
  v49 = 0;
  LODWORD(v34) = 0;
  P = 0;
  Pool2 = 0;
  VolumeName = 0;
  v45 = 0;
  InstanceName = 0;
  v46 = 0;
  if ( v3 > (unsigned int)a2 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 12;
    v26 = -46;
    goto LABEL_97;
  }
  if ( *(_DWORD *)a1 != 148 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 13;
    v26 = -39;
    goto LABEL_97;
  }
  if ( v3 < 0x92 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v7 = 14;
    v28 = 13;
    v8 = 14;
    v26 = -33;
    goto LABEL_98;
  }
  a2 = *(unsigned int *)(a1 + 116);
  if ( (unsigned int)a2 < 0x92 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 15;
    v26 = -27;
    goto LABEL_97;
  }
  v9 = *(_DWORD *)(a1 + 124);
  if ( v9 < 0x92 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 16;
    v26 = -21;
    goto LABEL_97;
  }
  v10 = *(_DWORD *)(a1 + 132);
  if ( v10 < 0x92 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 17;
    v26 = -15;
    goto LABEL_97;
  }
  v11 = *(_DWORD *)(a1 + 140);
  if ( v11 < 0x92 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 18;
    v26 = -9;
    goto LABEL_97;
  }
  v12 = *(unsigned __int16 *)(a1 + 120);
  if ( v12 + (unsigned int)a2 < (unsigned int)a2 || v3 < v12 + (unsigned int)a2 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 19;
    v26 = -2;
LABEL_97:
    v8 = 14;
    goto LABEL_98;
  }
  v13 = v9 + *(unsigned __int16 *)(a1 + 128);
  if ( v13 < v9 || v3 < v13 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 20;
    v26 = 5;
    goto LABEL_97;
  }
  v14 = v10 + *(unsigned __int16 *)(a1 + 136);
  if ( v14 < v10 || v3 < v14 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 21;
    v26 = 12;
    goto LABEL_97;
  }
  v15 = v11 + *(unsigned __int16 *)(a1 + 144);
  if ( v15 < v11 || v3 < v15 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v28 = 13;
    v7 = 22;
    v26 = 19;
    goto LABEL_97;
  }
  v16 = *(_WORD *)(a1 + 108);
  if ( v16 > 0x64u )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v7 = 23;
    v28 = 13;
    v26 = 25;
    v8 = 11;
    goto LABEL_98;
  }
  v17 = (USHORT *)(a1 + a2);
  InstanceName.Length = *(_WORD *)(a1 + 108);
  InstanceName.MaximumLength = v16;
  InstanceName.Buffer = (PWSTR)(a1 + 8);
  InstanceFromVolumeName = WcValidateContainerRootId(a1 + a2, v12);
  if ( InstanceFromVolumeName >= 0 )
  {
    v20 = (USHORT *)(a1 + *(unsigned int *)(a1 + 124));
    InstanceFromVolumeName = WcValidateContainerRootId(v20, *(unsigned __int16 *)(a1 + 128));
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 25;
      v27 = 47;
      goto LABEL_36;
    }
    InstanceFromVolumeName = RtlUShortAdd(v17[2], *(_WORD *)(a1 + 136), &pusResult[1]);
    if ( InstanceFromVolumeName < 0 )
      goto LABEL_37;
    InstanceFromVolumeName = RtlUShortAdd(2u, pusResult[1], &pusResult[1]);
    if ( InstanceFromVolumeName < 0 )
      goto LABEL_37;
    pusResult[0] = 0;
    P = (PVOID)ExAllocatePool2(256, pusResult[1], 1953317719);
    if ( !P )
    {
      InstanceFromVolumeName = -1073741670;
      goto LABEL_37;
    }
    InstanceFromVolumeName = RtlUShortAdd(v20[2], *(_WORD *)(a1 + 144), &v36[1]);
    if ( InstanceFromVolumeName < 0 )
      goto LABEL_37;
    InstanceFromVolumeName = RtlUShortAdd(2u, v36[1], &v36[1]);
    if ( InstanceFromVolumeName < 0 )
      goto LABEL_37;
    v36[0] = 0;
    Pool2 = (PVOID)ExAllocatePool2(256, v36[1], 1953317719);
    if ( !Pool2 )
    {
      InstanceFromVolumeName = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = -102;
      v19 = 26;
      v27 = 92;
      goto LABEL_36;
    }
    InstanceFromVolumeName = WcRelPathToFullPath(pusResult, *(_WORD *)(a1 + 136));
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 27;
      v27 = 103;
      goto LABEL_36;
    }
    InstanceFromVolumeName = WcRelPathToFullPath(v36, *(_WORD *)(a1 + 144));
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 28;
      v27 = 114;
      goto LABEL_36;
    }
    VolumeName.Length = v17[1];
    VolumeName.MaximumLength = VolumeName.Length;
    VolumeName.Buffer = v17 + 3;
    v45.Length = v20[1];
    v45.MaximumLength = v45.Length;
    v45.Buffer = v20 + 3;
    InstanceFromVolumeName = WcGetInstanceFromVolumeName(&VolumeName, &InstanceName, (PFLT_INSTANCE *)&FltObject);
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 29;
      v27 = -125;
      goto LABEL_36;
    }
    InstanceFromVolumeName = WcGetInstanceFromVolumeName(&v45, &InstanceName, (PFLT_INSTANCE *)&v42);
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 30;
      v27 = -116;
      goto LABEL_36;
    }
    InstanceFromVolumeName = WcOpenAsReparsePoint(
                               pusResult,
                               0,
                               0,
                               FltObject,
                               -2147352576,
                               *(_DWORD *)(a1 + 112),
                               &FileHandle,
                               &Object,
                               &v50,
                               &v51,
                               &v31,
                               &v48,
                               v32);
    if ( InstanceFromVolumeName < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 31;
      v27 = -97;
      goto LABEL_36;
    }
    if ( v50 )
    {
      if ( !v48 )
      {
        InstanceFromVolumeName = WcGetReparseData((PFLT_INSTANCE)FltObject, (PFILE_OBJECT)Object, (__int64)&v34);
        if ( InstanceFromVolumeName >= 0 )
        {
          v4 = v40;
          if ( (int)WcValidateWcReparseInfo(v40, (unsigned int)v34) >= 0 )
          {
            *((_DWORD *)v4 + 3) &= 0xFFFFFFF1;
            v5 = 0;
            goto LABEL_85;
          }
          InstanceFromVolumeName = -1073741566;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_88:
            v5 = v49;
            goto LABEL_99;
          }
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            v24,
            15,
            33,
            (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
            204,
            2);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v23) = 2;
            WPP_RECORDER_SF_sDd(
              wil_details_featureDescriptors_a->DeviceExtension,
              v23,
              15,
              32,
              (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
              188,
              InstanceFromVolumeName);
          }
          v4 = v40;
        }
        v5 = 0;
        goto LABEL_99;
      }
    }
    else if ( !v48 )
    {
      if ( v51 || v31 || (v21 = 1, v32[0]) )
        v21 = 0;
      LOBYTE(v30) = v21;
      InstanceFromVolumeName = WcCopyFile(FileHandle, Object, FltObject, v36, v42, 0, 0, v30, 0);
      if ( InstanceFromVolumeName >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v29 = InstanceFromVolumeName;
      v19 = 35;
      v27 = -8;
      goto LABEL_36;
    }
    v5 = 1;
    LODWORD(v46) = -2147483616;
    v49 = 1;
    v4 = &v46;
    WORD2(v46) = 0;
    v22 = 8;
LABEL_85:
    InstanceFromVolumeName = WcCopyAsPlaceHolder(FileHandle, Object, FltObject, v36, v42, 0, 0, v4, v22, 0);
    if ( InstanceFromVolumeName < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 34;
      v28 = InstanceFromVolumeName;
      v26 = -30;
      v8 = 15;
LABEL_98:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        a2,
        v8,
        v7,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        v26,
        v28);
      goto LABEL_99;
    }
    goto LABEL_88;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = InstanceFromVolumeName;
    v19 = 24;
    v27 = 38;
LABEL_36:
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v18,
      14,
      v19,
      (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
      v27,
      v29);
  }
LABEL_37:
  v5 = 0;
LABEL_99:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v42 )
    FltObjectDereference(v42);
  if ( P )
    ExFreePoolWithTag(P, 0x746D4357u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x746D4357u);
  if ( v4 && !v5 )
    ExFreePoolWithTag(v4, 0x69724357u);
  return (unsigned int)InstanceFromVolumeName;
}

```

## disassembly

```asm
0x14001a62c  push    rbp
0x14001a62e  push    rbx
0x14001a62f  push    rsi
0x14001a630  push    rdi
0x14001a631  push    r12
0x14001a633  push    r13
0x14001a635  push    r14
0x14001a637  push    r15
0x14001a639  lea     rbp, [rsp-18h]
0x14001a63e  sub     rsp, 118h
0x14001a645  xor     r12d, r12d
0x14001a648  xorps   xmm0, xmm0
0x14001a64b  xor     eax, eax
0x14001a64d  mov     [rbp+50h+FileHandle], r12
0x14001a651  mov     rdi, rcx
0x14001a654  mov     [rbp+50h+Object], r12
0x14001a658  mov     ecx, [rcx+4]
0x14001a65b  xorps   xmm1, xmm1
0x14001a65e  mov     qword ptr [rbp+50h+pusResult], r12
0x14001a662  mov     esi, r12d
0x14001a665  mov     qword ptr [rbp+50h+var_C0], r12
0x14001a669  mov     r15b, r12b
0x14001a66c  mov     [rsp+150h+FltObject], r12
0x14001a671  mov     [rbp+50h+var_90], r12
0x14001a675  mov     [rbp+50h+arg_18], r12b
0x14001a679  mov     [rbp+50h+arg_10], r12b
0x14001a67d  mov     [rsp+150h+var_E0], r12b
0x14001a682  mov     [rbp+50h+arg_0], r12b
0x14001a686  mov     [rsp+150h+var_DF], r12b
0x14001a68b  mov     [rbp+50h+var_A0], r12
0x14001a68f  mov     [rbp+50h+var_48], rax
0x14001a693  mov     [rbp+50h+arg_8], r12b
0x14001a697  mov     dword ptr [rbp+50h+var_D0], r12d
0x14001a69b  mov     [rbp+50h+P], r12
0x14001a69f  mov     [rbp+50h+var_B8], r12
0x14001a6a3  movups  xmmword ptr [rbp+50h+VolumeName.Length], xmm0
0x14001a6a7  movups  xmmword ptr [rbp+50h+var_68.Length], xmm1
0x14001a6ab  movups  xmmword ptr [rbp+50h+InstanceName.Length], xmm0
0x14001a6af  movups  [rbp+50h+var_58], xmm0
0x14001a6b3  cmp     ecx, edx
0x14001a6b5  jbe     short loc_14001A6E8
0x14001a6b7  mov     ecx, 0C000000Dh
0x14001a6bc  mov     ebx, ecx
0x14001a6be  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a6c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a6cc  jz      loc_14001B06B
0x14001a6d2  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a6d6  lea     r9d, [r12+0Ch]
0x14001a6db  mov     dword ptr [rsp+150h+var_120], 0D2h
0x14001a6e3  jmp     loc_14001AF94
0x14001a6e8  cmp     dword ptr [rdi], 94h
0x14001a6ee  jz      short loc_14001A722
0x14001a6f0  mov     ecx, 0C000000Dh
0x14001a6f5  mov     ebx, ecx
0x14001a6f7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a6fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a705  jz      loc_14001B06B
0x14001a70b  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a70f  mov     r9d, 0Dh
0x14001a715  mov     dword ptr [rsp+150h+var_120], 0D9h
0x14001a71d  jmp     loc_14001AF94
0x14001a722  mov     eax, 92h
0x14001a727  cmp     ecx, eax
0x14001a729  jnb     short loc_14001A760
0x14001a72b  mov     ecx, 0C000000Dh
0x14001a730  mov     ebx, ecx
0x14001a732  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a739  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a740  jz      loc_14001B06B
0x14001a746  mov     r9d, 0Eh
0x14001a74c  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a750  mov     r8d, r9d
0x14001a753  mov     dword ptr [rsp+150h+var_120], 0DFh
0x14001a75b  jmp     loc_14001AF9A
0x14001a760  mov     edx, [rdi+74h]
0x14001a763  cmp     edx, eax
0x14001a765  jnb     short loc_14001A799
0x14001a767  mov     ecx, 0C000000Dh
0x14001a76c  mov     ebx, ecx
0x14001a76e  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a775  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a77c  jz      loc_14001B06B
0x14001a782  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a786  mov     r9d, 0Fh
0x14001a78c  mov     dword ptr [rsp+150h+var_120], 0E5h
0x14001a794  jmp     loc_14001AF94
0x14001a799  mov     r8d, [rdi+7Ch]
0x14001a79d  cmp     r8d, eax
0x14001a7a0  jnb     short loc_14001A7D4
0x14001a7a2  mov     ecx, 0C000000Dh
0x14001a7a7  mov     ebx, ecx
0x14001a7a9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a7b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a7b7  jz      loc_14001B06B
0x14001a7bd  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a7c1  mov     r9d, 10h
0x14001a7c7  mov     dword ptr [rsp+150h+var_120], 0EBh
0x14001a7cf  jmp     loc_14001AF94
0x14001a7d4  mov     r9d, [rdi+84h]
0x14001a7db  cmp     r9d, eax
0x14001a7de  jnb     short loc_14001A812
0x14001a7e0  mov     ecx, 0C000000Dh
0x14001a7e5  mov     ebx, ecx
0x14001a7e7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a7ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a7f5  jz      loc_14001B06B
0x14001a7fb  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a7ff  mov     r9d, 11h
0x14001a805  mov     dword ptr [rsp+150h+var_120], 0F1h
0x14001a80d  jmp     loc_14001AF94
0x14001a812  mov     r10d, [rdi+8Ch]
0x14001a819  cmp     r10d, eax
0x14001a81c  jnb     short loc_14001A850
0x14001a81e  mov     ecx, 0C000000Dh
0x14001a823  mov     ebx, ecx
0x14001a825  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a82c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a833  jz      loc_14001B06B
0x14001a839  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a83d  mov     r9d, 12h
0x14001a843  mov     dword ptr [rsp+150h+var_120], 0F7h
0x14001a84b  jmp     loc_14001AF94
0x14001a850  movzx   ebx, word ptr [rdi+78h]
0x14001a854  lea     eax, [rbx+rdx]
0x14001a857  cmp     eax, edx
0x14001a859  jb      loc_14001AF67
0x14001a85f  cmp     ecx, eax
0x14001a861  jb      loc_14001AF67
0x14001a867  movzx   r11d, word ptr [rdi+80h]
0x14001a86f  add     r11d, r8d
0x14001a872  cmp     r11d, r8d
0x14001a875  jb      loc_14001AF38
0x14001a87b  cmp     ecx, r11d
0x14001a87e  jb      loc_14001AF38
0x14001a884  movzx   r8d, word ptr [rdi+88h]
0x14001a88c  add     r8d, r9d
0x14001a88f  cmp     r8d, r9d
0x14001a892  jb      loc_14001AF09
0x14001a898  cmp     ecx, r8d
0x14001a89b  jb      loc_14001AF09
0x14001a8a1  movzx   r8d, word ptr [rdi+90h]
0x14001a8a9  add     r8d, r10d
0x14001a8ac  cmp     r8d, r10d
0x14001a8af  jb      loc_14001AED7
0x14001a8b5  cmp     ecx, r8d
0x14001a8b8  jb      loc_14001AED7
0x14001a8be  movzx   eax, word ptr [rdi+6Ch]
0x14001a8c2  cmp     ax, 64h ; 'd'
0x14001a8c6  jbe     short loc_14001A8FE
0x14001a8c8  mov     ecx, 0C000000Dh
0x14001a8cd  mov     ebx, ecx
0x14001a8cf  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a8d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a8dd  jz      loc_14001B06B
0x14001a8e3  mov     r9d, 17h
0x14001a8e9  mov     dword ptr [rsp+150h+var_118], ecx
0x14001a8ed  mov     dword ptr [rsp+150h+var_120], 119h
0x14001a8f5  lea     r8d, [r9-0Ch]
0x14001a8f9  jmp     loc_14001AF9A
0x14001a8fe  lea     r15, [rdi+rdx]
0x14001a902  mov     [rbp+50h+InstanceName.Length], ax
0x14001a906  mov     [rbp+50h+InstanceName.MaximumLength], ax
0x14001a90a  mov     rcx, r15
0x14001a90d  lea     rax, [rdi+8]
0x14001a911  mov     edx, ebx
0x14001a913  mov     [rbp+50h+InstanceName.Buffer], rax
0x14001a917  call    WcValidateContainerRootId
0x14001a91c  mov     ebx, eax
0x14001a91e  test    eax, eax
0x14001a920  jns     short loc_14001A97C
0x14001a922  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a929  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a930  jz      short loc_14001A974
0x14001a932  mov     dword ptr [rsp+150h+var_118], ebx
0x14001a936  mov     r9d, 18h
0x14001a93c  mov     dword ptr [rsp+150h+var_120], 126h
0x14001a944  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001a94b  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\wcifs\\message."...
0x14001a952  mov     [rsp+150h+var_128], rax
0x14001a957  mov     r8d, 0Eh
0x14001a95d  lea     rax, WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids
0x14001a964  mov     dl, 2
0x14001a966  mov     qword ptr [rsp+150h+var_130], rax
0x14001a96b  mov     rcx, [rcx+40h]
0x14001a96f  call    WPP_RECORDER_SF_sDd
0x14001a974  mov     r15b, sil
0x14001a977  jmp     loc_14001AFC4
0x14001a97c  mov     r14d, [rdi+7Ch]
0x14001a980  movzx   edx, word ptr [rdi+80h]
0x14001a987  add     r14, rdi
0x14001a98a  mov     rcx, r14
0x14001a98d  call    WcValidateContainerRootId
0x14001a992  mov     ebx, eax
0x14001a994  test    eax, eax
0x14001a996  jns     short loc_14001A9BC
0x14001a998  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a99f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a9a6  jz      short loc_14001A974
0x14001a9a8  mov     dword ptr [rsp+150h+var_118], ebx
0x14001a9ac  mov     r9d, 19h
0x14001a9b2  mov     dword ptr [rsp+150h+var_120], 12Fh
0x14001a9ba  jmp     short loc_14001A944
0x14001a9bc  movzx   edx, word ptr [rdi+88h]; usAddend
0x14001a9c3  lea     r8, [rbp+50h+pusResult+2]; pusResult
0x14001a9c7  movzx   ecx, word ptr [r15+4]; usAugend
0x14001a9cc  call    RtlUShortAdd
0x14001a9d1  mov     ebx, eax
0x14001a9d3  test    eax, eax
0x14001a9d5  js      short loc_14001A974
0x14001a9d7  movzx   edx, [rbp+50h+pusResult+2]; usAddend
0x14001a9db  lea     r8, [rbp+50h+pusResult+2]; pusResult
0x14001a9df  mov     ecx, 2; usAugend
0x14001a9e4  call    RtlUShortAdd
0x14001a9e9  mov     ebx, eax
0x14001a9eb  test    eax, eax
0x14001a9ed  js      short loc_14001A974
0x14001a9ef  movzx   edx, [rbp+50h+pusResult+2]
0x14001a9f3  mov     r13d, 100h
0x14001a9f9  mov     ecx, r13d
0x14001a9fc  mov     [rbp+50h+pusResult], r12w
0x14001aa01  mov     r8d, 746D4357h
0x14001aa07  call    cs:__imp_ExAllocatePool2
0x14001aa0e  nop     dword ptr [rax+rax+00h]
0x14001aa13  mov     [rbp+50h+P], rax
0x14001aa17  test    rax, rax
0x14001aa1a  jnz     short loc_14001AA26
0x14001aa1c  mov     ebx, 0C000009Ah
0x14001aa21  jmp     loc_14001A974
0x14001aa26  movzx   edx, word ptr [rdi+90h]; usAddend
0x14001aa2d  lea     r8, [rbp+50h+var_C0+2]; pusResult
0x14001aa31  movzx   ecx, word ptr [r14+4]; usAugend
0x14001aa36  call    RtlUShortAdd
0x14001aa3b  mov     ebx, eax
0x14001aa3d  test    eax, eax
0x14001aa3f  js      loc_14001A974
0x14001aa45  movzx   edx, [rbp+50h+var_C0+2]; usAddend
0x14001aa49  lea     r8, [rbp+50h+var_C0+2]; pusResult
0x14001aa4d  mov     ecx, 2; usAugend
0x14001aa52  call    RtlUShortAdd
0x14001aa57  mov     ebx, eax
0x14001aa59  test    eax, eax
0x14001aa5b  js      loc_14001A974
0x14001aa61  movzx   edx, [rbp+50h+var_C0+2]
0x14001aa65  mov     r8d, 746D4357h
0x14001aa6b  mov     rcx, r13
0x14001aa6e  mov     [rbp+50h+var_C0], r12w
0x14001aa73  call    cs:__imp_ExAllocatePool2
0x14001aa7a  nop     dword ptr [rax+rax+00h]
0x14001aa7f  mov     [rbp+50h+var_B8], rax
0x14001aa83  test    rax, rax
0x14001aa86  jnz     short loc_14001AAB8
0x14001aa88  mov     ebx, 0C000009Ah
0x14001aa8d  lea     rax, WPP_RECORDER_INITIALIZED
0x14001aa94  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001aa9b  jz      loc_14001A974
0x14001aaa1  mov     dword ptr [rsp+150h+var_118], ebx
0x14001aaa5  mov     r9d, 1Ah
0x14001aaab  mov     dword ptr [rsp+150h+var_120], 15Ch
0x14001aab3  jmp     loc_14001A944
0x14001aab8  mov     r9d, [rdi+84h]
0x14001aabf  lea     r13, [r15+6]
0x14001aac3  movzx   eax, word ptr [rdi+88h]
0x14001aaca  lea     rcx, [rbp+50h+pusResult]; pusResult
0x14001aace  movzx   edx, word ptr [r15+4]
0x14001aad3  add     r9, rdi
0x14001aad6  mov     r8, r13
0x14001aad9  mov     [rsp+150h+var_130], ax; __int16
0x14001aade  call    WcRelPathToFullPath
0x14001aae3  mov     ebx, eax
0x14001aae5  test    eax, eax
0x14001aae7  jns     short loc_14001AB14
0x14001aae9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001aaf0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001aaf7  jz      loc_14001A974
0x14001aafd  mov     dword ptr [rsp+150h+var_118], ebx
0x14001ab01  mov     r9d, 1Bh
0x14001ab07  mov     dword ptr [rsp+150h+var_120], 167h
0x14001ab0f  jmp     loc_14001A944
0x14001ab14  mov     r9d, [rdi+8Ch]
0x14001ab1b  lea     r12, [r14+6]
0x14001ab1f  movzx   eax, word ptr [rdi+90h]
0x14001ab26  lea     rcx, [rbp+50h+var_C0]; pusResult
0x14001ab2a  movzx   edx, word ptr [r14+4]
0x14001ab2f  add     r9, rdi
0x14001ab32  mov     r8, r12
0x14001ab35  mov     [rsp+150h+var_130], ax; __int16
0x14001ab3a  call    WcRelPathToFullPath
0x14001ab3f  mov     ebx, eax
0x14001ab41  test    eax, eax
0x14001ab43  jns     short loc_14001AB70
0x14001ab45  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ab4c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ab53  jz      loc_14001A974
0x14001ab59  mov     dword ptr [rsp+150h+var_118], ebx
0x14001ab5d  mov     r9d, 1Ch
0x14001ab63  mov     dword ptr [rsp+150h+var_120], 172h
0x14001ab6b  jmp     loc_14001A944
0x14001ab70  movzx   eax, word ptr [r15+2]
0x14001ab75  lea     r8, [rsp+150h+FltObject]; RetInstance
0x14001ab7a  mov     [rbp+50h+VolumeName.Length], ax
  ... truncated ...
```
