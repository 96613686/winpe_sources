# WcCopyAsPlaceHolderHandler

- ea: `0x14002befc`
- end: `0x14002c87d`
- name: `WcCopyAsPlaceHolderHandler`
- size: `2433`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x140031e40`

## callees

- `0x1400020c4`
- `0x1400024d4`
- `0x140007dc0`
- `0x1400142d0`
- `0x14002befc`
- `0x14002c884`
- `0x14002c9dc`
- `0x14002cae8`
- `0x14002da54`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002c7e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c7e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c826`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c840`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c85a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c826`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c840`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c85a`
- `ntoskrnl!ExAllocatePool2` at `0x14002c2c4`
- `ntoskrnl!ExAllocatePool2` at `0x14002c31d`
- `ntoskrnl!ExAllocatePool2` at `0x14002c580`
- `ntoskrnl!ExAllocatePool2` at `0x14002c2c4`
- `ntoskrnl!ExAllocatePool2` at `0x14002c31d`
- `ntoskrnl!ExAllocatePool2` at `0x14002c580`
- `FLTMGR!FltClose` at `0x14002c7cd`
- `FLTMGR!FltClose` at `0x14002c7cd`
- `FLTMGR!FltObjectDereference` at `0x14002c7f8`
- `FLTMGR!FltObjectDereference` at `0x14002c80d`
- `FLTMGR!FltObjectDereference` at `0x14002c7f8`
- `FLTMGR!FltObjectDereference` at `0x14002c80d`

## pseudocode

```c
__int64 __fastcall WcCopyAsPlaceHolderHandler(__int64 a1, __int64 a2)
{
  unsigned int v2; // r8d
  _WORD *v4; // r13
  int InstanceFromVolumeName; // ebx
  int v6; // r9d
  unsigned int v7; // ecx
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  unsigned int v10; // eax
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
  __int64 Pool2; // rax
  char v31; // [rsp+30h] [rbp-D0h]
  char v32; // [rsp+38h] [rbp-C8h]
  bool v33; // [rsp+70h] [rbp-90h] BYREF
  PVOID FltObject; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING pusResult; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v36; // [rsp+90h] [rbp-70h] BYREF
  HANDLE FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Object; // [rsp+A8h] [rbp-58h] BYREF
  PVOID v39; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING InstanceName; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING VolumeName; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v42; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v43; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h]
  bool v45; // [rsp+150h] [rbp+50h] BYREF
  bool v46; // [rsp+158h] [rbp+58h] BYREF
  bool v47; // [rsp+160h] [rbp+60h] BYREF
  char v48; // [rsp+168h] [rbp+68h] BYREF

  v2 = *(_DWORD *)(a1 + 4);
  FileHandle = 0;
  Object = 0;
  v44 = 0;
  *(_QWORD *)&pusResult.Length = 0;
  *(_QWORD *)&v36.Length = 0;
  v4 = 0;
  FltObject = 0;
  v39 = 0;
  v45 = 0;
  v33 = 0;
  v46 = 0;
  v48 = 0;
  v47 = 0;
  pusResult.Buffer = 0;
  v36.Buffer = 0;
  v43 = 0;
  VolumeName = 0;
  v42 = 0;
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
  v10 = *(unsigned __int16 *)(a1 + 124) + (_DWORD)a2;
  if ( v10 < (unsigned int)a2 || v2 < v10 )
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
  InstanceFromVolumeName = WcValidateContainerRootId(a1 + a2);
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
        WPP_GLOBAL_Control->DeviceExtension,
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
  InstanceFromVolumeName = WcValidateContainerRootId(v19);
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
    pusResult.MaximumLength = -1;
LABEL_43:
    InstanceFromVolumeName = -1073741675;
    goto LABEL_93;
  }
  pusResult.MaximumLength = v22;
  pusResult.Length = 0;
  pusResult.Buffer = (PWSTR)ExAllocatePool2(256, v22, 1953317719);
  if ( !pusResult.Buffer )
  {
LABEL_46:
    InstanceFromVolumeName = -1073741670;
    goto LABEL_93;
  }
  v23 = v19[2];
  v24 = *(_WORD *)(a1 + 152) + v23;
  if ( v24 < v23 || (v25 = v24 + 2, v25 < 2u) )
  {
    v36.MaximumLength = -1;
    goto LABEL_43;
  }
  v36.MaximumLength = v25;
  v36.Length = 0;
  v36.Buffer = (PWSTR)ExAllocatePool2(256, v25, 1953317719);
  if ( !v36.Buffer )
    goto LABEL_46;
  InstanceFromVolumeName = WcRelPathToFullPath(&pusResult.Length, *(_WORD *)(a1 + 144));
  if ( InstanceFromVolumeName >= 0 )
  {
    InstanceFromVolumeName = WcRelPathToFullPath(&v36.Length, *(_WORD *)(a1 + 152));
    if ( InstanceFromVolumeName >= 0 )
    {
      VolumeName.Length = v18[1];
      VolumeName.MaximumLength = VolumeName.Length;
      VolumeName.Buffer = v18 + 3;
      v42.Length = v19[1];
      v42.MaximumLength = v42.Length;
      v42.Buffer = v19 + 3;
      InstanceFromVolumeName = WcGetInstanceFromVolumeName(&VolumeName, &InstanceName, (PFLT_INSTANCE *)&FltObject);
      if ( InstanceFromVolumeName >= 0 )
      {
        InstanceFromVolumeName = WcGetInstanceFromVolumeName(&v42, &InstanceName, (PFLT_INSTANCE *)&v39);
        if ( InstanceFromVolumeName >= 0 )
        {
          InstanceFromVolumeName = WcOpenAsReparsePoint(
                                     &pusResult,
                                     0,
                                     0,
                                     (struct _FLT_INSTANCE *)FltObject,
                                     0x80020000,
                                     *(_DWORD *)(a1 + 116),
                                     &FileHandle,
                                     (PFILE_OBJECT *)&Object,
                                     &v33,
                                     &v45,
                                     &v46,
                                     &v48,
                                     &v47);
          if ( InstanceFromVolumeName >= 0 )
          {
            if ( v45 || v46 || v47 )
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
            if ( v48 )
            {
              LODWORD(v43) = -2147483616;
              v26 = &v43;
              WORD2(v43) = 0;
              v27 = 8;
            }
            else
            {
              v28 = (unsigned __int16 *)(a1 + *(unsigned int *)(a1 + 156));
              v27 = v28[12] + 34;
              Pool2 = ExAllocatePool2(256, v27, 1953317719);
              v4 = (_WORD *)Pool2;
              if ( !Pool2 )
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
              memmove((void *)(Pool2 + 8), v28, *(unsigned int *)(a1 + 160));
              *(_DWORD *)v4 = *(_DWORD *)(a1 + 128);
              InstanceFromVolumeName = RtlUShortAdd(0x1Au, v4[16], v4 + 2);
              if ( InstanceFromVolumeName < 0 )
                goto LABEL_93;
              v26 = (__int128 *)v4;
            }
            InstanceFromVolumeName = WcCopyAsPlaceHolder(
                                       (__int64)FileHandle,
                                       (struct _FILE_OBJECT *)Object,
                                       (struct _FLT_INSTANCE *)FltObject,
                                       &v36,
                                       (struct _FLT_INSTANCE *)v39,
                                       0,
                                       0,
                                       (__int64)v26,
                                       v27,
                                       (*(_BYTE *)(a1 + 8) & 1u) << 6);
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
  if ( v39 )
    FltObjectDereference(v39);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x746D4357u);
  if ( pusResult.Buffer )
    ExFreePoolWithTag(pusResult.Buffer, 0x746D4357u);
  if ( v36.Buffer )
    ExFreePoolWithTag(v36.Buffer, 0x746D4357u);
  return (unsigned int)InstanceFromVolumeName;
}

```

## disassembly

```asm
0x14002befc  push    rbp
0x14002befe  push    rbx
0x14002beff  push    rsi
0x14002bf00  push    rdi
0x14002bf01  push    r12
0x14002bf03  push    r13
0x14002bf05  push    r14
0x14002bf07  push    r15
0x14002bf09  lea     rbp, [rsp-8]
0x14002bf0e  sub     rsp, 108h
0x14002bf15  mov     r8d, [rcx+4]
0x14002bf19  xor     r15d, r15d
0x14002bf1c  xorps   xmm0, xmm0
0x14002bf1f  mov     [rbp+40h+FileHandle], r15
0x14002bf23  xor     eax, eax
0x14002bf25  mov     [rbp+40h+Object], r15
0x14002bf29  mov     [rbp+40h+var_48], rax
0x14002bf2d  xorps   xmm1, xmm1
0x14002bf30  mov     qword ptr [rbp+40h+pusResult], r15
0x14002bf34  mov     rdi, rcx
0x14002bf37  mov     qword ptr [rbp+40h+var_B0], r15
0x14002bf3b  mov     r13d, r15d
0x14002bf3e  mov     [rsp+140h+FltObject], r15
0x14002bf43  mov     [rbp+40h+var_90], r15
0x14002bf47  mov     [rbp+40h+arg_0], r15b
0x14002bf4b  mov     [rsp+140h+var_D0], r15b
0x14002bf50  mov     [rbp+40h+arg_8], r15b
0x14002bf54  mov     [rbp+40h+arg_18], r15b
0x14002bf58  mov     [rbp+40h+arg_10], r15b
0x14002bf5c  mov     [rbp+40h+P], r15
0x14002bf60  mov     [rbp+40h+var_A8], r15
0x14002bf64  movups  [rbp+40h+var_58], xmm0
0x14002bf68  movups  xmmword ptr [rbp+40h+VolumeName.Length], xmm0
0x14002bf6c  movups  xmmword ptr [rbp+40h+var_68.Length], xmm1
0x14002bf70  movups  xmmword ptr [rbp+40h+InstanceName.Length], xmm0
0x14002bf74  cmp     r8d, edx
0x14002bf77  jbe     short loc_14002BFA9
0x14002bf79  mov     ecx, 0C000000Dh
0x14002bf7e  mov     ebx, ecx
0x14002bf80  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bf87  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bf8e  jz      loc_14002C866
0x14002bf94  mov     dword ptr [rsp+140h+var_108], ecx
0x14002bf98  lea     r9d, [r15+24h]
0x14002bf9c  mov     dword ptr [rsp+140h+var_110], 25Eh
0x14002bfa4  jmp     loc_14002C794
0x14002bfa9  cmp     dword ptr [rcx], 0A8h
0x14002bfaf  jz      short loc_14002BFE3
0x14002bfb1  mov     ecx, 0C000000Dh
0x14002bfb6  mov     ebx, ecx
0x14002bfb8  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bfbf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bfc6  jz      loc_14002C866
0x14002bfcc  mov     dword ptr [rsp+140h+var_108], ecx
0x14002bfd0  mov     r9d, 25h ; '%'
0x14002bfd6  mov     dword ptr [rsp+140h+var_110], 265h
0x14002bfde  jmp     loc_14002C794
0x14002bfe3  mov     eax, 0A4h
0x14002bfe8  cmp     r8d, eax
0x14002bfeb  jnb     short loc_14002C01F
0x14002bfed  mov     ecx, 0C000000Dh
0x14002bff2  mov     ebx, ecx
0x14002bff4  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bffb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c002  jz      loc_14002C866
0x14002c008  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c00c  mov     r9d, 26h ; '&'
0x14002c012  mov     dword ptr [rsp+140h+var_110], 26Bh
0x14002c01a  jmp     loc_14002C794
0x14002c01f  mov     edx, [rcx+78h]
0x14002c022  cmp     edx, eax
0x14002c024  jnb     short loc_14002C058
0x14002c026  mov     ecx, 0C000000Dh
0x14002c02b  mov     ebx, ecx
0x14002c02d  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c034  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c03b  jz      loc_14002C866
0x14002c041  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c045  mov     r9d, 27h ; '''
0x14002c04b  mov     dword ptr [rsp+140h+var_110], 271h
0x14002c053  jmp     loc_14002C794
0x14002c058  mov     ecx, [rcx+84h]
0x14002c05e  cmp     ecx, eax
0x14002c060  jnb     short loc_14002C094
0x14002c062  mov     ecx, 0C000000Dh
0x14002c067  mov     ebx, ecx
0x14002c069  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c070  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c077  jz      loc_14002C866
0x14002c07d  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c081  mov     r9d, 28h ; '('
0x14002c087  mov     dword ptr [rsp+140h+var_110], 277h
0x14002c08f  jmp     loc_14002C794
0x14002c094  mov     r9d, [rdi+8Ch]
0x14002c09b  cmp     r9d, eax
0x14002c09e  jnb     short loc_14002C0D2
0x14002c0a0  mov     ecx, 0C000000Dh
0x14002c0a5  mov     ebx, ecx
0x14002c0a7  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c0ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c0b5  jz      loc_14002C866
0x14002c0bb  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c0bf  mov     r9d, 29h ; ')'
0x14002c0c5  mov     dword ptr [rsp+140h+var_110], 27Dh
0x14002c0cd  jmp     loc_14002C794
0x14002c0d2  mov     r10d, [rdi+94h]
0x14002c0d9  cmp     r10d, eax
0x14002c0dc  jnb     short loc_14002C110
0x14002c0de  mov     ecx, 0C000000Dh
0x14002c0e3  mov     ebx, ecx
0x14002c0e5  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c0ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c0f3  jz      loc_14002C866
0x14002c0f9  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c0fd  mov     r9d, 2Ah ; '*'
0x14002c103  mov     dword ptr [rsp+140h+var_110], 283h
0x14002c10b  jmp     loc_14002C794
0x14002c110  movzx   ebx, word ptr [rdi+7Ch]
0x14002c114  lea     eax, [rbx+rdx]
0x14002c117  cmp     eax, edx
0x14002c119  jb      loc_14002C767
0x14002c11f  cmp     r8d, eax
0x14002c122  jb      loc_14002C767
0x14002c128  movzx   r11d, word ptr [rdi+88h]
0x14002c130  add     r11d, ecx
0x14002c133  cmp     r11d, ecx
0x14002c136  jb      loc_14002C738
0x14002c13c  cmp     r8d, r11d
0x14002c13f  jb      loc_14002C738
0x14002c145  movzx   ecx, word ptr [rdi+90h]
0x14002c14c  add     ecx, r9d
0x14002c14f  cmp     ecx, r9d
0x14002c152  jb      loc_14002C709
0x14002c158  cmp     r8d, ecx
0x14002c15b  jb      loc_14002C709
0x14002c161  movzx   ecx, word ptr [rdi+98h]
0x14002c168  add     ecx, r10d
0x14002c16b  cmp     ecx, r10d
0x14002c16e  jb      loc_14002C6D7
0x14002c174  cmp     r8d, ecx
0x14002c177  jb      loc_14002C6D7
0x14002c17d  mov     ecx, [rdi+9Ch]
0x14002c183  mov     r9d, [rdi+0A0h]
0x14002c18a  add     r9d, ecx
0x14002c18d  cmp     r9d, ecx
0x14002c190  jb      loc_14002C6A5
0x14002c196  cmp     r8d, r9d
0x14002c199  jb      loc_14002C6A5
0x14002c19f  movzx   eax, word ptr [rdi+70h]
0x14002c1a3  cmp     ax, 64h ; 'd'
0x14002c1a7  jbe     short loc_14002C1DF
0x14002c1a9  mov     ecx, 0C000000Dh
0x14002c1ae  mov     ebx, ecx
0x14002c1b0  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c1b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c1be  jz      loc_14002C866
0x14002c1c4  mov     r9d, 30h ; '0'
0x14002c1ca  mov     dword ptr [rsp+140h+var_108], ecx
0x14002c1ce  mov     dword ptr [rsp+140h+var_110], 2ACh
0x14002c1d6  lea     r8d, [r9-25h]
0x14002c1da  jmp     loc_14002C79A
0x14002c1df  lea     r14, [rdi+rdx]
0x14002c1e3  mov     [rbp+40h+InstanceName.Length], ax
0x14002c1e7  mov     [rbp+40h+InstanceName.MaximumLength], ax
0x14002c1eb  mov     rcx, r14
0x14002c1ee  lea     rax, [rdi+0Ch]
0x14002c1f2  mov     edx, ebx
0x14002c1f4  mov     [rbp+40h+InstanceName.Buffer], rax
0x14002c1f8  call    WcValidateContainerRootId
0x14002c1fd  mov     ebx, eax
0x14002c1ff  test    eax, eax
0x14002c201  jns     short loc_14002C22E
0x14002c203  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c20a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c211  jz      loc_14002C7C4
0x14002c217  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c21b  mov     r9d, 31h ; '1'
0x14002c221  mov     dword ptr [rsp+140h+var_110], 2B9h
0x14002c229  jmp     loc_14002C794
0x14002c22e  mov     esi, [rdi+84h]
0x14002c234  movzx   edx, word ptr [rdi+88h]
0x14002c23b  add     rsi, rdi
0x14002c23e  mov     rcx, rsi
0x14002c241  call    WcValidateContainerRootId
0x14002c246  mov     ebx, eax
0x14002c248  test    eax, eax
0x14002c24a  jns     short loc_14002C277
0x14002c24c  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c253  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c25a  jz      loc_14002C7C4
0x14002c260  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c264  mov     r9d, 32h ; '2'
0x14002c26a  mov     dword ptr [rsp+140h+var_110], 2C2h
0x14002c272  jmp     loc_14002C794
0x14002c277  movzx   eax, word ptr [r14+4]
0x14002c27c  movzx   ecx, ax
0x14002c27f  add     cx, [rdi+90h]
0x14002c286  cmp     cx, ax
0x14002c289  jnb     short loc_14002C29E
0x14002c28b  mov     eax, 0FFFFh
0x14002c290  mov     [rbp+40h+pusResult+2], ax
0x14002c294  mov     ebx, 0C0000095h
0x14002c299  jmp     loc_14002C7C4
0x14002c29e  add     cx, 2
0x14002c2a2  cmp     cx, 2
0x14002c2a6  jb      short loc_14002C28B
0x14002c2a8  mov     [rbp+40h+pusResult+2], cx
0x14002c2ac  mov     r12d, 746D4357h
0x14002c2b2  movzx   edx, cx
0x14002c2b5  mov     ebx, 100h
0x14002c2ba  mov     r8d, r12d
0x14002c2bd  mov     [rbp+40h+pusResult], r15w
0x14002c2c2  mov     ecx, ebx
0x14002c2c4  call    cs:__imp_ExAllocatePool2
0x14002c2cb  nop     dword ptr [rax+rax+00h]
0x14002c2d0  mov     [rbp+40h+P], rax
0x14002c2d4  test    rax, rax
0x14002c2d7  jnz     short loc_14002C2E3
0x14002c2d9  mov     ebx, 0C000009Ah
0x14002c2de  jmp     loc_14002C7C4
0x14002c2e3  movzx   eax, word ptr [rsi+4]
0x14002c2e7  movzx   ecx, ax
0x14002c2ea  add     cx, [rdi+98h]
0x14002c2f1  cmp     cx, ax
0x14002c2f4  jnb     short loc_14002C301
0x14002c2f6  mov     eax, 0FFFFh
0x14002c2fb  mov     [rbp+40h+var_B0+2], ax
0x14002c2ff  jmp     short loc_14002C294
0x14002c301  add     cx, 2
0x14002c305  cmp     cx, 2
0x14002c309  jb      short loc_14002C2F6
0x14002c30b  mov     [rbp+40h+var_B0+2], cx
0x14002c30f  mov     r8d, r12d
0x14002c312  movzx   edx, cx
0x14002c315  mov     rcx, rbx
0x14002c318  mov     [rbp+40h+var_B0], r15w
0x14002c31d  call    cs:__imp_ExAllocatePool2
0x14002c324  nop     dword ptr [rax+rax+00h]
0x14002c329  mov     [rbp+40h+var_A8], rax
0x14002c32d  test    rax, rax
0x14002c330  jz      short loc_14002C2D9
0x14002c332  mov     r9d, [rdi+8Ch]
0x14002c339  lea     r12, [r14+6]
0x14002c33d  movzx   eax, word ptr [rdi+90h]
0x14002c344  lea     rcx, [rbp+40h+pusResult]; pusResult
0x14002c348  movzx   edx, word ptr [r14+4]
0x14002c34d  add     r9, rdi
0x14002c350  mov     r8, r12
0x14002c353  mov     [rsp+140h+var_120], ax; __int16
0x14002c358  call    WcRelPathToFullPath
0x14002c35d  mov     ebx, eax
0x14002c35f  test    eax, eax
0x14002c361  jns     short loc_14002C38E
0x14002c363  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c36a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c371  jz      loc_14002C7C4
0x14002c377  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c37b  mov     r9d, 33h ; '3'
0x14002c381  mov     dword ptr [rsp+140h+var_110], 2F9h
0x14002c389  jmp     loc_14002C794
0x14002c38e  mov     r9d, [rdi+94h]
0x14002c395  lea     r15, [rsi+6]
0x14002c399  movzx   eax, word ptr [rdi+98h]
0x14002c3a0  lea     rcx, [rbp+40h+var_B0]; pusResult
0x14002c3a4  movzx   edx, word ptr [rsi+4]
0x14002c3a8  add     r9, rdi
0x14002c3ab  mov     r8, r15
0x14002c3ae  mov     [rsp+140h+var_120], ax; __int16
0x14002c3b3  call    WcRelPathToFullPath
0x14002c3b8  mov     ebx, eax
0x14002c3ba  test    eax, eax
0x14002c3bc  jns     short loc_14002C3E9
0x14002c3be  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c3c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c3cc  jz      loc_14002C7C4
0x14002c3d2  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c3d6  mov     r9d, 34h ; '4'
0x14002c3dc  mov     dword ptr [rsp+140h+var_110], 304h
0x14002c3e4  jmp     loc_14002C794
0x14002c3e9  movzx   eax, word ptr [r14+2]
0x14002c3ee  lea     r8, [rsp+140h+FltObject]; RetInstance
0x14002c3f3  mov     [rbp+40h+VolumeName.Length], ax
0x14002c3f7  lea     rdx, [rbp+40h+InstanceName]; InstanceName
0x14002c3fb  mov     [rbp+40h+VolumeName.MaximumLength], ax
0x14002c3ff  lea     rcx, [rbp+40h+VolumeName]; VolumeName
0x14002c403  mov     [rbp+40h+VolumeName.Buffer], r12
0x14002c407  movzx   eax, word ptr [rsi+2]
0x14002c40b  mov     [rbp+40h+var_68.Length], ax
0x14002c40f  mov     [rbp+40h+var_68.MaximumLength], ax
0x14002c413  mov     [rbp+40h+var_68.Buffer], r15
0x14002c417  call    WcGetInstanceFromVolumeName
0x14002c41c  xor     r15d, r15d
0x14002c41f  mov     ebx, eax
0x14002c421  test    eax, eax
0x14002c423  jns     short loc_14002C44E
0x14002c425  lea     rax, WPP_RECORDER_INITIALIZED
0x14002c42c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002c433  jz      loc_14002C7C4
0x14002c439  mov     dword ptr [rsp+140h+var_108], ebx
0x14002c43d  lea     r9d, [r15+35h]
  ... truncated ...
```
