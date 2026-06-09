# WcCopyAsPlaceHolderHandler

- ea: `0x14002bf4c`
- end: `0x14002c8cd`
- name: `WcCopyAsPlaceHolderHandler`
- size: `2433`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x140031e90`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x140007dc0`
- `0x1400142d0`
- `0x14002bf4c`
- `0x14002c8d4`
- `0x14002ca2c`
- `0x14002cb38`
- `0x14002daa4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002c832`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c832`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c890`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c8aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c890`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c8aa`
- `ntoskrnl!ExAllocatePool2` at `0x14002c314`
- `ntoskrnl!ExAllocatePool2` at `0x14002c36d`
- `ntoskrnl!ExAllocatePool2` at `0x14002c5d0`
- `ntoskrnl!ExAllocatePool2` at `0x14002c314`
- `ntoskrnl!ExAllocatePool2` at `0x14002c36d`
- `ntoskrnl!ExAllocatePool2` at `0x14002c5d0`
- `FLTMGR!FltClose` at `0x14002c81d`
- `FLTMGR!FltClose` at `0x14002c81d`
- `FLTMGR!FltObjectDereference` at `0x14002c848`
- `FLTMGR!FltObjectDereference` at `0x14002c85d`
- `FLTMGR!FltObjectDereference` at `0x14002c848`
- `FLTMGR!FltObjectDereference` at `0x14002c85d`

## pseudocode

```c
__int64 __fastcall WcCopyAsPlaceHolderHandler(__int64 a1, __int64 a2)
{
  unsigned int v2; // r8d
  _WORD *v4; // r13
  NTSTATUS InstanceFromVolumeName; // ebx
  int v6; // r9d
  unsigned int v7; // ecx
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  unsigned int v10; // ebx
  unsigned int v11; // r11d
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // r9d
  USHORT v16; // ax
  int v17; // r8d
  USHORT *v18; // r14
  USHORT *v19; // rsi
  USHORT v20; // ax
  USHORT v21; // cx
  USHORT v22; // cx
  USHORT v23; // ax
  USHORT v24; // cx
  USHORT v25; // cx
  __int128 *v26; // rcx
  unsigned int v27; // esi
  unsigned __int16 *v28; // r14
  __int64 v29; // rax
  char v31; // [rsp+30h] [rbp-D0h]
  char v32; // [rsp+38h] [rbp-C8h]
  char v33[8]; // [rsp+70h] [rbp-90h] BYREF
  PVOID FltObject; // [rsp+78h] [rbp-88h] BYREF
  USHORT pusResult[4]; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h]
  USHORT v37[4]; // [rsp+90h] [rbp-70h] BYREF
  PVOID Pool2; // [rsp+98h] [rbp-68h]
  HANDLE FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Object; // [rsp+A8h] [rbp-58h] BYREF
  PVOID v41; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING InstanceName; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING VolumeName; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v44; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v45; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-8h]
  char v47; // [rsp+150h] [rbp+50h] BYREF
  char v48; // [rsp+158h] [rbp+58h] BYREF
  char v49; // [rsp+160h] [rbp+60h] BYREF
  char v50; // [rsp+168h] [rbp+68h] BYREF

  v2 = *(_DWORD *)(a1 + 4);
  FileHandle = 0;
  Object = 0;
  v46 = 0;
  *(_QWORD *)pusResult = 0;
  *(_QWORD *)v37 = 0;
  v4 = 0;
  FltObject = 0;
  v41 = 0;
  v47 = 0;
  v33[0] = 0;
  v48 = 0;
  v50 = 0;
  v49 = 0;
  P = 0;
  Pool2 = 0;
  v45 = 0;
  VolumeName = 0;
  v44 = 0;
  InstanceName = 0;
  if ( v2 > (unsigned int)a2 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 36;
    v31 = 94;
    goto LABEL_91;
  }
  if ( *(_DWORD *)a1 != 168 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 37;
    v31 = 101;
    goto LABEL_91;
  }
  if ( v2 < 0xA4 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 38;
    v31 = 107;
    goto LABEL_91;
  }
  a2 = *(unsigned int *)(a1 + 120);
  if ( (unsigned int)a2 < 0xA4 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 39;
    v31 = 113;
    goto LABEL_91;
  }
  v7 = *(_DWORD *)(a1 + 132);
  if ( v7 < 0xA4 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 40;
    v31 = 119;
    goto LABEL_91;
  }
  v8 = *(_DWORD *)(a1 + 140);
  if ( v8 < 0xA4 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 41;
    v31 = 125;
    goto LABEL_91;
  }
  v9 = *(_DWORD *)(a1 + 148);
  if ( v9 < 0xA4 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 42;
    v31 = -125;
    goto LABEL_91;
  }
  v10 = *(unsigned __int16 *)(a1 + 124);
  if ( v10 + (unsigned int)a2 < (unsigned int)a2 || v2 < v10 + (unsigned int)a2 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 43;
    v31 = -118;
    goto LABEL_91;
  }
  v11 = v7 + *(unsigned __int16 *)(a1 + 136);
  if ( v11 < v7 || v2 < v11 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 44;
    v31 = -111;
    goto LABEL_91;
  }
  v12 = v8 + *(unsigned __int16 *)(a1 + 144);
  if ( v12 < v8 || v2 < v12 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 45;
    v31 = -104;
    goto LABEL_91;
  }
  v13 = v9 + *(unsigned __int16 *)(a1 + 152);
  if ( v13 < v9 || v2 < v13 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 46;
    v31 = -97;
    goto LABEL_91;
  }
  v14 = *(_DWORD *)(a1 + 156);
  v15 = v14 + *(_DWORD *)(a1 + 160);
  if ( v15 < v14 || v2 < v15 )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v32 = 13;
    v6 = 47;
    v31 = -90;
    goto LABEL_91;
  }
  v16 = *(_WORD *)(a1 + 112);
  if ( v16 > 0x64u )
  {
    InstanceFromVolumeName = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)InstanceFromVolumeName;
    v6 = 48;
    v32 = 13;
    v31 = -84;
    v17 = 11;
    goto LABEL_92;
  }
  v18 = (USHORT *)(a1 + a2);
  InstanceName.Length = *(_WORD *)(a1 + 112);
  InstanceName.MaximumLength = v16;
  InstanceName.Buffer = (PWSTR)(a1 + 12);
  InstanceFromVolumeName = WcValidateContainerRootId(a1 + a2, v10);
  if ( InstanceFromVolumeName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = InstanceFromVolumeName;
      v6 = 49;
      v31 = -71;
LABEL_91:
      v17 = 14;
LABEL_92:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        a2,
        v17,
        v6,
        (__int64)WPP_d2c22b7febde3e254f89b8862cb374bf_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\message.c",
        v31,
        v32);
      goto LABEL_93;
    }
    goto LABEL_93;
  }
  v19 = (USHORT *)(a1 + *(unsigned int *)(a1 + 132));
  InstanceFromVolumeName = WcValidateContainerRootId(v19, *(unsigned __int16 *)(a1 + 136));
  if ( InstanceFromVolumeName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = InstanceFromVolumeName;
      v6 = 50;
      v31 = -62;
      goto LABEL_91;
    }
    goto LABEL_93;
  }
  v20 = v18[2];
  v21 = *(_WORD *)(a1 + 144) + v20;
  if ( v21 < v20 || (v22 = v21 + 2, v22 < 2u) )
  {
    pusResult[1] = -1;
LABEL_43:
    InstanceFromVolumeName = -1073741675;
    goto LABEL_93;
  }
  pusResult[1] = v22;
  pusResult[0] = 0;
  P = (PVOID)ExAllocatePool2(256, v22, 1953317719);
  if ( !P )
  {
LABEL_46:
    InstanceFromVolumeName = -1073741670;
    goto LABEL_93;
  }
  v23 = v19[2];
  v24 = *(_WORD *)(a1 + 152) + v23;
  if ( v24 < v23 || (v25 = v24 + 2, v25 < 2u) )
  {
    v37[1] = -1;
    goto LABEL_43;
  }
  v37[1] = v25;
  v37[0] = 0;
  Pool2 = (PVOID)ExAllocatePool2(256, v25, 1953317719);
  if ( !Pool2 )
    goto LABEL_46;
  InstanceFromVolumeName = WcRelPathToFullPath(pusResult, *(_WORD *)(a1 + 144));
  if ( InstanceFromVolumeName >= 0 )
  {
    InstanceFromVolumeName = WcRelPathToFullPath(v37, *(_WORD *)(a1 + 152));
    if ( InstanceFromVolumeName >= 0 )
    {
      VolumeName.Length = v18[1];
      VolumeName.MaximumLength = VolumeName.Length;
      VolumeName.Buffer = v18 + 3;
      v44.Length = v19[1];
      v44.MaximumLength = v44.Length;
      v44.Buffer = v19 + 3;
      InstanceFromVolumeName = WcGetInstanceFromVolumeName(&VolumeName, &InstanceName, (PFLT_INSTANCE *)&FltObject);
      if ( InstanceFromVolumeName >= 0 )
      {
        InstanceFromVolumeName = WcGetInstanceFromVolumeName(&v44, &InstanceName, (PFLT_INSTANCE *)&v41);
        if ( InstanceFromVolumeName >= 0 )
        {
          InstanceFromVolumeName = WcOpenAsReparsePoint(
                                     pusResult,
                                     0,
                                     0,
                                     FltObject,
                                     -2147352576,
                                     *(_DWORD *)(a1 + 116),
                                     &FileHandle,
                                     &Object,
                                     v33,
                                     &v47,
                                     &v48,
                                     &v50,
                                     &v49);
          if ( InstanceFromVolumeName >= 0 )
          {
            if ( v47 || v48 || v49 )
            {
              InstanceFromVolumeName = -1073741811;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v32 = 13;
                v6 = 56;
                v31 = 55;
                goto LABEL_91;
              }
              goto LABEL_93;
            }
            if ( v50 )
            {
              LODWORD(v45) = -2147483616;
              v26 = &v45;
              WORD2(v45) = 0;
              v27 = 8;
            }
            else
            {
              v28 = (unsigned __int16 *)(a1 + *(unsigned int *)(a1 + 156));
              v27 = v28[12] + 34;
              v29 = ExAllocatePool2(256, v27, 1953317719);
              v4 = (_WORD *)v29;
              if ( !v29 )
              {
                InstanceFromVolumeName = -1073741670;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v32 = -102;
                  v6 = 57;
                  v31 = 86;
                  goto LABEL_91;
                }
                goto LABEL_93;
              }
              memmove((void *)(v29 + 8), v28, *(unsigned int *)(a1 + 160));
              *(_DWORD *)v4 = *(_DWORD *)(a1 + 128);
              InstanceFromVolumeName = RtlUShortAdd(0x1Au, v4[16], v4 + 2);
              if ( InstanceFromVolumeName < 0 )
                goto LABEL_93;
              v26 = (__int128 *)v4;
            }
            InstanceFromVolumeName = WcCopyAsPlaceHolder(
                                       FileHandle,
                                       Object,
                                       FltObject,
                                       v37,
                                       v41,
                                       0,
                                       0,
                                       v26,
                                       v27,
                                       (*(_DWORD *)(a1 + 8) & 1u) << 6);
            if ( InstanceFromVolumeName >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_93;
            v32 = InstanceFromVolumeName;
            v6 = 58;
            v31 = 125;
            goto LABEL_91;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v32 = InstanceFromVolumeName;
            v6 = 55;
            v31 = 49;
            goto LABEL_91;
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v32 = InstanceFromVolumeName;
          v6 = 54;
          v31 = 30;
          goto LABEL_91;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v32 = InstanceFromVolumeName;
        v6 = 53;
        v31 = 21;
        goto LABEL_91;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = InstanceFromVolumeName;
      v6 = 52;
      v31 = 4;
      goto LABEL_91;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v32 = InstanceFromVolumeName;
    v6 = 51;
    v31 = -7;
    goto LABEL_91;
  }
LABEL_93:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v41 )
    FltObjectDereference(v41);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x746D4357u);
  if ( P )
    ExFreePoolWithTag(P, 0x746D4357u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x746D4357u);
  return (unsigned int)InstanceFromVolumeName;
}

```

## disassembly

```asm
0x14002bf4c  push    rbp
0x14002bf4e  push    rbx
0x14002bf4f  push    rsi
0x14002bf50  push    rdi
0x14002bf51  push    r12
0x14002bf53  push    r13
0x14002bf55  push    r14
0x14002bf57  push    r15
0x14002bf59  lea     rbp, [rsp-8]
0x14002bf5e  sub     rsp, 108h
0x14002bf65  mov     r8d, [rcx+4]
0x14002bf69  xor     r15d, r15d
0x14002bf6c  xorps   xmm0, xmm0
0x14002bf6f  mov     [rbp+40h+FileHandle], r15
0x14002bf73  xor     eax, eax
0x14002bf75  mov     [rbp+40h+Object], r15
0x14002bf79  mov     [rbp+40h+var_48], rax
0x14002bf7d  xorps   xmm1, xmm1
0x14002bf80  mov     qword ptr [rbp+40h+pusResult], r15
0x14002bf84  mov     rdi, rcx
0x14002bf87  mov     qword ptr [rbp+40h+var_B0], r15
0x14002bf8b  mov     r13d, r15d
0x14002bf8e  mov     [rsp+140h+FltObject], r15
0x14002bf93  mov     [rbp+40h+var_90], r15
0x14002bf97  mov     [rbp+40h+arg_0], r15b
0x14002bf9b  mov     [rsp+140h+var_D0], r15b
0x14002bfa0  mov     [rbp+40h+arg_8], r15b
0x14002bfa4  mov     [rbp+40h+arg_18], r15b
0x14002bfa8  mov     [rbp+40h+arg_10], r15b
0x14002bfac  mov     [rbp+40h+P], r15
0x14002bfb0  mov     [rbp+40h+var_A8], r15
0x14002bfb4  movups  [rbp+40h+var_58], xmm0
0x14002bfb8  movups  xmmword ptr [rbp+40h+VolumeName.Length], xmm0
0x14002bfbc  movups  xmmword ptr [rbp+40h+var_68.Length], xmm1
0x14002bfc0  movups  xmmword ptr [rbp+40h+InstanceName.Length], xmm0
0x14002bfc4  cmp     r8d, edx
0x14002bfc7  jbe     short loc_14002BFF9
0x14002bfc9  mov     ecx, 0C000000Dh
0x14002bfce  mov     ebx, ecx
0x14002bfd0  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bfd7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bfde  jz      loc_14002C8B6
0x14002bfe4  mov     dword ptr [rsp+140h+var_108], ecx
0x14002bfe8  lea     r9d, [r15+24h]
0x14002bfec  mov     dword ptr [rsp+140h+var_110], 25Eh
0x14002bff4  jmp     loc_14002C7E4
0x14002bff9  cmp     dword ptr [rcx], 0A8h
0x14002bfff  jz      short loc_14002C033
0x14002c001  mov     ecx, 0C000000Dh
0x14002c006  mov     ebx, ecx
0x14002c008  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c00f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c016  jz      loc_14002C8B6
0x14002c01c  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c020  mov     r9d, 25h ; '%'
0x14002c026  mov     dword ptr [rsp+140h+var_110], 265h
0x14002c02e  jmp     loc_14002C7E4
0x14002c033  mov     eax, 0A4h
0x14002c038  cmp     r8d, eax
0x14002c03b  jnb     short loc_14002C06F
0x14002c03d  mov     ecx, 0C000000Dh
0x14002c042  mov     ebx, ecx
0x14002c044  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c04b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c052  jz      loc_14002C8B6
0x14002c058  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c05c  mov     r9d, 26h ; '&'
0x14002c062  mov     dword ptr [rsp+140h+var_110], 26Bh
0x14002c06a  jmp     loc_14002C7E4
0x14002c06f  mov     edx, [rcx+78h]
0x14002c072  cmp     edx, eax
0x14002c074  jnb     short loc_14002C0A8
0x14002c076  mov     ecx, 0C000000Dh
0x14002c07b  mov     ebx, ecx
0x14002c07d  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c084  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c08b  jz      loc_14002C8B6
0x14002c091  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c095  mov     r9d, 27h ; '''
0x14002c09b  mov     dword ptr [rsp+140h+var_110], 271h
0x14002c0a3  jmp     loc_14002C7E4
0x14002c0a8  mov     ecx, [rcx+84h]
0x14002c0ae  cmp     ecx, eax
0x14002c0b0  jnb     short loc_14002C0E4
0x14002c0b2  mov     ecx, 0C000000Dh
0x14002c0b7  mov     ebx, ecx
0x14002c0b9  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c0c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c0c7  jz      loc_14002C8B6
0x14002c0cd  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c0d1  mov     r9d, 28h ; '('
0x14002c0d7  mov     dword ptr [rsp+140h+var_110], 277h
0x14002c0df  jmp     loc_14002C7E4
0x14002c0e4  mov     r9d, [rdi+8Ch]
0x14002c0eb  cmp     r9d, eax
0x14002c0ee  jnb     short loc_14002C122
0x14002c0f0  mov     ecx, 0C000000Dh
0x14002c0f5  mov     ebx, ecx
0x14002c0f7  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c0fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c105  jz      loc_14002C8B6
0x14002c10b  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c10f  mov     r9d, 29h ; ')'
0x14002c115  mov     dword ptr [rsp+140h+var_110], 27Dh
0x14002c11d  jmp     loc_14002C7E4
0x14002c122  mov     r10d, [rdi+94h]
0x14002c129  cmp     r10d, eax
0x14002c12c  jnb     short loc_14002C160
0x14002c12e  mov     ecx, 0C000000Dh
0x14002c133  mov     ebx, ecx
0x14002c135  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c13c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c143  jz      loc_14002C8B6
0x14002c149  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c14d  mov     r9d, 2Ah ; '*'
0x14002c153  mov     dword ptr [rsp+140h+var_110], 283h
0x14002c15b  jmp     loc_14002C7E4
0x14002c160  movzx   ebx, word ptr [rdi+7Ch]
0x14002c164  lea     eax, [rbx+rdx]
0x14002c167  cmp     eax, edx
0x14002c169  jb      loc_14002C7B7
0x14002c16f  cmp     r8d, eax
0x14002c172  jb      loc_14002C7B7
0x14002c178  movzx   r11d, word ptr [rdi+88h]
0x14002c180  add     r11d, ecx
0x14002c183  cmp     r11d, ecx
0x14002c186  jb      loc_14002C788
0x14002c18c  cmp     r8d, r11d
0x14002c18f  jb      loc_14002C788
0x14002c195  movzx   ecx, word ptr [rdi+90h]
0x14002c19c  add     ecx, r9d
0x14002c19f  cmp     ecx, r9d
0x14002c1a2  jb      loc_14002C759
0x14002c1a8  cmp     r8d, ecx
0x14002c1ab  jb      loc_14002C759
0x14002c1b1  movzx   ecx, word ptr [rdi+98h]
0x14002c1b8  add     ecx, r10d
0x14002c1bb  cmp     ecx, r10d
0x14002c1be  jb      loc_14002C727
0x14002c1c4  cmp     r8d, ecx
0x14002c1c7  jb      loc_14002C727
0x14002c1cd  mov     ecx, [rdi+9Ch]
0x14002c1d3  mov     r9d, [rdi+0A0h]
0x14002c1da  add     r9d, ecx
0x14002c1dd  cmp     r9d, ecx
0x14002c1e0  jb      loc_14002C6F5
0x14002c1e6  cmp     r8d, r9d
0x14002c1e9  jb      loc_14002C6F5
0x14002c1ef  movzx   eax, word ptr [rdi+70h]
0x14002c1f3  cmp     ax, 64h ; 'd'
0x14002c1f7  jbe     short loc_14002C22F
0x14002c1f9  mov     ecx, 0C000000Dh
0x14002c1fe  mov     ebx, ecx
0x14002c200  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c207  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c20e  jz      loc_14002C8B6
0x14002c214  mov     r9d, 30h ; '0'
0x14002c21a  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c21e  mov     dword ptr [rsp+140h+var_110], 2ACh
0x14002c226  lea     r8d, [r9-25h]
0x14002c22a  jmp     loc_14002C7EA
0x14002c22f  lea     r14, [rdi+rdx]
0x14002c233  mov     [rbp+40h+InstanceName.Length], ax
0x14002c237  mov     [rbp+40h+InstanceName.MaximumLength], ax
0x14002c23b  mov     rcx, r14
0x14002c23e  lea     rax, [rdi+0Ch]
0x14002c242  mov     edx, ebx
0x14002c244  mov     [rbp+40h+InstanceName.Buffer], rax
0x14002c248  call    WcValidateContainerRootId
0x14002c24d  mov     ebx, eax
0x14002c24f  test    eax, eax
0x14002c251  jns     short loc_14002C27E
0x14002c253  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c25a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c261  jz      loc_14002C814
0x14002c267  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c26b  mov     r9d, 31h ; '1'
0x14002c271  mov     dword ptr [rsp+140h+var_110], 2B9h
0x14002c279  jmp     loc_14002C7E4
0x14002c27e  mov     esi, [rdi+84h]
0x14002c284  movzx   edx, word ptr [rdi+88h]
0x14002c28b  add     rsi, rdi
0x14002c28e  mov     rcx, rsi
0x14002c291  call    WcValidateContainerRootId
0x14002c296  mov     ebx, eax
0x14002c298  test    eax, eax
0x14002c29a  jns     short loc_14002C2C7
0x14002c29c  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c2a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c2aa  jz      loc_14002C814
0x14002c2b0  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c2b4  mov     r9d, 32h ; '2'
0x14002c2ba  mov     dword ptr [rsp+140h+var_110], 2C2h
0x14002c2c2  jmp     loc_14002C7E4
0x14002c2c7  movzx   eax, word ptr [r14+4]
0x14002c2cc  movzx   ecx, ax
0x14002c2cf  add     cx, [rdi+90h]
0x14002c2d6  cmp     cx, ax
0x14002c2d9  jnb     short loc_14002C2EE
0x14002c2db  mov     eax, 0FFFFh
0x14002c2e0  mov     [rbp+40h+pusResult+2], ax
0x14002c2e4  mov     ebx, 0C0000095h
0x14002c2e9  jmp     loc_14002C814
0x14002c2ee  add     cx, 2
0x14002c2f2  cmp     cx, 2
0x14002c2f6  jb      short loc_14002C2DB
0x14002c2f8  mov     [rbp+40h+pusResult+2], cx
0x14002c2fc  mov     r12d, 746D4357h
0x14002c302  movzx   edx, cx
0x14002c305  mov     ebx, 100h
0x14002c30a  mov     r8d, r12d
0x14002c30d  mov     [rbp+40h+pusResult], r15w
0x14002c312  mov     ecx, ebx
0x14002c314  call    cs:__imp_ExAllocatePool2
0x14002c31b  nop     dword ptr [rax+rax+00h]
0x14002c320  mov     [rbp+40h+P], rax
0x14002c324  test    rax, rax
0x14002c327  jnz     short loc_14002C333
0x14002c329  mov     ebx, 0C000009Ah
0x14002c32e  jmp     loc_14002C814
0x14002c333  movzx   eax, word ptr [rsi+4]
0x14002c337  movzx   ecx, ax
0x14002c33a  add     cx, [rdi+98h]
0x14002c341  cmp     cx, ax
0x14002c344  jnb     short loc_14002C351
0x14002c346  mov     eax, 0FFFFh
0x14002c34b  mov     [rbp+40h+var_B0+2], ax
0x14002c34f  jmp     short loc_14002C2E4
0x14002c351  add     cx, 2
0x14002c355  cmp     cx, 2
0x14002c359  jb      short loc_14002C346
0x14002c35b  mov     [rbp+40h+var_B0+2], cx
0x14002c35f  mov     r8d, r12d
0x14002c362  movzx   edx, cx
0x14002c365  mov     rcx, rbx
0x14002c368  mov     [rbp+40h+var_B0], r15w
0x14002c36d  call    cs:__imp_ExAllocatePool2
0x14002c374  nop     dword ptr [rax+rax+00h]
0x14002c379  mov     [rbp+40h+var_A8], rax
0x14002c37d  test    rax, rax
0x14002c380  jz      short loc_14002C329
0x14002c382  mov     r9d, [rdi+8Ch]
0x14002c389  lea     r12, [r14+6]
0x14002c38d  movzx   eax, word ptr [rdi+90h]
0x14002c394  lea     rcx, [rbp+40h+pusResult]; pusResult
0x14002c398  movzx   edx, word ptr [r14+4]
0x14002c39d  add     r9, rdi
0x14002c3a0  mov     r8, r12
0x14002c3a3  mov     [rsp+140h+var_120], ax; __int16
0x14002c3a8  call    WcRelPathToFullPath
0x14002c3ad  mov     ebx, eax
0x14002c3af  test    eax, eax
0x14002c3b1  jns     short loc_14002C3DE
0x14002c3b3  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c3ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c3c1  jz      loc_14002C814
0x14002c3c7  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c3cb  mov     r9d, 33h ; '3'
0x14002c3d1  mov     dword ptr [rsp+140h+var_110], 2F9h
0x14002c3d9  jmp     loc_14002C7E4
0x14002c3de  mov     r9d, [rdi+94h]
0x14002c3e5  lea     r15, [rsi+6]
0x14002c3e9  movzx   eax, word ptr [rdi+98h]
0x14002c3f0  lea     rcx, [rbp+40h+var_B0]; pusResult
0x14002c3f4  movzx   edx, word ptr [rsi+4]
0x14002c3f8  add     r9, rdi
0x14002c3fb  mov     r8, r15
0x14002c3fe  mov     [rsp+140h+var_120], ax; __int16
0x14002c403  call    WcRelPathToFullPath
0x14002c408  mov     ebx, eax
0x14002c40a  test    eax, eax
0x14002c40c  jns     short loc_14002C439
0x14002c40e  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c415  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c41c  jz      loc_14002C814
0x14002c422  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c426  mov     r9d, 34h ; '4'
0x14002c42c  mov     dword ptr [rsp+140h+var_110], 304h
0x14002c434  jmp     loc_14002C7E4
0x14002c439  movzx   eax, word ptr [r14+2]
0x14002c43e  lea     r8, [rsp+140h+FltObject]; RetInstance
0x14002c443  mov     [rbp+40h+VolumeName.Length], ax
0x14002c447  lea     rdx, [rbp+40h+InstanceName]; InstanceName
0x14002c44b  mov     [rbp+40h+VolumeName.MaximumLength], ax
0x14002c44f  lea     rcx, [rbp+40h+VolumeName]; VolumeName
0x14002c453  mov     [rbp+40h+VolumeName.Buffer], r12
0x14002c457  movzx   eax, word ptr [rsi+2]
0x14002c45b  mov     [rbp+40h+var_68.Length], ax
0x14002c45f  mov     [rbp+40h+var_68.MaximumLength], ax
0x14002c463  mov     [rbp+40h+var_68.Buffer], r15
0x14002c467  call    WcGetInstanceFromVolumeName
0x14002c46c  xor     r15d, r15d
0x14002c46f  mov     ebx, eax
0x14002c471  test    eax, eax
0x14002c473  jns     short loc_14002C49E
0x14002c475  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c47c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c483  jz      loc_14002C814
0x14002c489  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c48d  lea     r9d, [r15+35h]
  ... truncated ...
```
