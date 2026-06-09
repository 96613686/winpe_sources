# VmCommitDevices(void *,ulong,_VM_DEVICE_CHANGE *)

- ea: `0x14000eba0`
- end: `0x14000f152`
- name: `?VmCommitDevices@@YAXPEAXKPEAU_VM_DEVICE_CHANGE@@@Z`
- size: `1458`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *, unsigned int, struct _VM_DEVICE_CHANGE *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400033a0`
- `0x140003c50`
- `0x140003e70`
- `0x140003eb0`
- `0x140003ef0`
- `0x140005050`
- `0x140005090`
- `0x140005540`
- `0x14000eba0`
- `0x14000f158`
- `0x14000f19c`
- `0x14000f378`
- `0x14000f56c`
- `0x14000f6fc`
- `0x140011920`
- `0x1400120f0`
- `0x1400123e8`
- `0x140015c30`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000ec77`
- `ntoskrnl!IoDeleteDevice` at `0x14000eeea`
- `ntoskrnl!IoDeleteDevice` at `0x14000ec77`
- `ntoskrnl!IoDeleteDevice` at `0x14000eeea`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000ef8f`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000f117`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000ef8f`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000f117`
- `ntoskrnl!RtlCompareMemory` at `0x14000efdb`
- `ntoskrnl!RtlCompareMemory` at `0x14000efdb`

## pseudocode

```c
void __fastcall VmCommitDevices(struct VM_ROOT_EXTENSION *a1, unsigned int a2, struct _VM_DEVICE_CHANGE *a3)
{
  unsigned int i; // r14d
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  struct VM_ROOT_EXTENSION *v12; // rax
  __int64 v13; // rdx
  struct VM_ROOT_EXTENSION **v14; // rcx
  struct VM_ROOT_EXTENSION **v15; // rdx
  unsigned int v16; // r14d
  __int64 v17; // rbx
  __int64 v18; // rsi
  char v20; // al
  int v21; // r15d
  __int128 v22; // xmm0
  struct _DEVICE_OBJECT *v23; // rcx
  struct VM_VOLUME_EXTENSION *ExtensionForPendingBasicVolume; // rax
  struct VM_VOLUME_EXTENSION *v25; // r14
  char *v26; // rcx
  __int64 v27; // rdx
  char **v28; // rax
  bool v29; // r15
  unsigned __int64 v30; // rax
  int v31; // eax
  unsigned __int16 v32; // r8
  __int64 v33; // rbx
  unsigned int j; // r14d
  __int64 v35; // rbx
  struct VM_VOLUME_EXTENSION *ExtensionForPendingDynamicVolume; // rax
  __int64 v37; // r8
  int v38; // r9d
  struct VM_VOLUME_EXTENSION *v39; // r15
  struct VM_ROOT_EXTENSION *v40; // rsi
  __int64 v41; // rcx
  struct VM_ROOT_EXTENSION **v42; // rax
  struct VM_ROOT_EXTENSION **v43; // rcx
  char v44; // [rsp+20h] [rbp-E0h]
  char v45; // [rsp+21h] [rbp-DFh]
  int v46; // [rsp+24h] [rbp-DCh]
  __int64 v47; // [rsp+28h] [rbp-D8h]
  _QWORD v48[14]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v49; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 Source1[54]; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int8 Source2[54]; // [rsp+DAh] [rbp-26h] BYREF

  v47 = *((_QWORD *)a1 + 49);
  memset(v48, 0, 0x68u);
  v44 = 0;
  for ( i = 0; i < a2; ++i )
  {
    v7 = 112LL * i;
    v8 = *(_QWORD *)((char *)a3 + v7);
    if ( v8 )
    {
      if ( *((_BYTE *)a3 + v7 + 16) ? *(_QWORD *)((char *)a3 + v7 + 104) == 0 : *(_QWORD *)((char *)a3 + v7 + 24) == 0 )
      {
        *(_QWORD *)(v8 + 48) = MEMORY[0xFFFFF78000000014];
        if ( *(_BYTE *)(v8 + 158) )
        {
          if ( *((_BYTE *)a3 + v7 + 17) )
            VmpNotify((struct VM_VOLUME_EXTENSION *)v8, &GUID_IO_VOLUME_PREPARE_DELETE, 0, 0);
          VmpDeleteLegacyNameLinks((struct VM_VOLUME_EXTENSION *)v8, 0);
          VmpReleaseInterfaces(v8);
          memset((char *)v48 + 1, 0, 0x67u);
          LOBYTE(v48[0]) = *((_BYTE *)a3 + v7 + 16);
          VmpZeroRefCallback(
            (struct VM_VOLUME_EXTENSION *)v8,
            (int (*)(struct VM_VOLUME_EXTENSION *, void *))VmpSetTargetCallback,
            v48);
          v12 = (struct VM_ROOT_EXTENSION *)(v8 + 32);
          v13 = *(_QWORD *)(v8 + 32);
          if ( *(_QWORD *)(v13 + 8) != v8 + 32
            || (v14 = *(struct VM_ROOT_EXTENSION ***)(v8 + 40), *v14 != v12)
            || (*v14 = (struct VM_ROOT_EXTENSION *)v13,
                *(_QWORD *)(v13 + 8) = v14,
                v15 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 29),
                *v15 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 224)) )
          {
LABEL_64:
            __fastfail(3u);
          }
          *(_QWORD *)v12 = (char *)a1 + 224;
          *(_QWORD *)(v8 + 40) = v15;
          *v15 = v12;
          *((_QWORD *)a1 + 29) = v12;
          if ( *((_BYTE *)a3 + v7 + 17) )
            *(_BYTE *)(v8 + 159) = 1;
          v44 = 1;
        }
        else
        {
          v10 = *(_QWORD *)(v8 + 32);
          if ( *(_QWORD *)(v10 + 8) != v8 + 32 )
            goto LABEL_64;
          v11 = *(_QWORD **)(v8 + 40);
          if ( *v11 != v8 + 32 )
            goto LABEL_64;
          *v11 = v10;
          *(_QWORD *)(v10 + 8) = v11;
          VmpCleanupVolumeExtension((struct VM_VOLUME_EXTENSION *)v8);
          IoDeleteDevice(*(PDEVICE_OBJECT *)v8);
        }
      }
    }
  }
  v46 = 0;
  v16 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v17 = 112LL * v16;
      v18 = *(_QWORD *)((char *)a3 + v17);
      if ( !v18 )
        goto LABEL_49;
      if ( *((_BYTE *)a3 + v17 + 16)
         ? *(_QWORD *)((char *)a3 + v17 + 104) == 0
         : *(_QWORD *)((char *)a3 + v17 + 24) == 0 )
      {
        goto LABEL_49;
      }
      v20 = *(_BYTE *)(v18 + 426);
      v51 = 48;
      v45 = v20;
      v21 = VmpQueryUniqueIdInternal((struct VM_VOLUME_EXTENSION *)v18, &v51, Source2);
      VmpDeleteLegacyNameLinks((struct VM_VOLUME_EXTENSION *)v18, 0);
      memset((char *)v48 + 1, 0, 0x67u);
      LOBYTE(v48[0]) = *((_BYTE *)a3 + v17 + 16);
      if ( LOBYTE(v48[0]) )
      {
        *(_DWORD *)(*(_QWORD *)v18 + 152LL) = (*(__int64 (__fastcall **)(_QWORD))(v47 + 136))(*(_QWORD *)((char *)a3 + v17 + 104));
        *(_BYTE *)(*(_QWORD *)v18 + 76LL) = (*(__int64 (__fastcall **)(_QWORD))(v47 + 128))(*(_QWORD *)((char *)a3 + v17 + 104))
                                          + 2;
        v48[12] = *(_QWORD *)((char *)a3 + v17 + 104);
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)v18 + 152LL) = *(_DWORD *)(*(_QWORD *)((char *)a3 + v17 + 24) + 152LL);
        *(_BYTE *)(*(_QWORD *)v18 + 76LL) = *(_BYTE *)(*(_QWORD *)((char *)a3 + v17 + 24) + 76LL) + 1;
        v22 = *(_OWORD *)((char *)a3 + v17 + 72);
        v23 = *(struct _DEVICE_OBJECT **)((char *)a3 + v17 + 32);
        v48[1] = *(_QWORD *)((char *)a3 + v17 + 24);
        v48[3] = *(_QWORD *)((char *)a3 + v17 + 40);
        LODWORD(v48[4]) = *(_DWORD *)((char *)a3 + v17 + 48);
        LODWORD(v48[6]) = *(_DWORD *)((char *)a3 + v17 + 52);
        v48[7] = *(_QWORD *)((char *)a3 + v17 + 56);
        v48[8] = *(_QWORD *)((char *)a3 + v17 + 64);
        LOBYTE(v48[11]) = *((_BYTE *)a3 + v17 + 96);
        v48[2] = v23;
        *(_OWORD *)&v48[9] = v22;
        VmpGetInstancePath(v23, (unsigned __int16 **)&v48[5]);
        ExtensionForPendingBasicVolume = VmpFindExtensionForPendingBasicVolume(
                                           a1,
                                           *(struct _DEVICE_OBJECT **)((char *)a3 + v17 + 24));
        v25 = ExtensionForPendingBasicVolume;
        if ( ExtensionForPendingBasicVolume )
        {
          v26 = (char *)ExtensionForPendingBasicVolume + 32;
          v27 = *((_QWORD *)ExtensionForPendingBasicVolume + 4);
          if ( *(struct VM_VOLUME_EXTENSION **)(v27 + 8) != (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingBasicVolume
                                                                                         + 32) )
            goto LABEL_64;
          v28 = (char **)*((_QWORD *)ExtensionForPendingBasicVolume + 5);
          if ( *v28 != v26 )
            goto LABEL_64;
          *v28 = (char *)v27;
          *(_QWORD *)(v27 + 8) = v28;
          VmpCleanupVolumeExtension(v25);
          IoDeleteDevice(*(PDEVICE_OBJECT *)v25);
        }
        v16 = v46;
      }
      v29 = v21 >= 0;
      VmpZeroRefCallback(
        (struct VM_VOLUME_EXTENSION *)v18,
        (int (*)(struct VM_VOLUME_EXTENSION *, void *))VmpSetTargetCallback,
        v48);
      if ( *((_BYTE *)a3 + v17 + 16) )
      {
        v30 = (*(__int64 (__fastcall **)(_QWORD))(v47 + 152))(*(_QWORD *)(v18 + 432));
        VmpApplyGptAttributes((struct VM_VOLUME_EXTENSION *)v18, v30);
      }
      VmpCreateLegacyNameLinks((struct VM_VOLUME_EXTENSION *)v18, 0);
      VmpSetDevicePowerState((struct VM_VOLUME_EXTENSION *)v18, *(enum _DEVICE_POWER_STATE *)((char *)a3 + v17 + 20));
      if ( *((_BYTE *)a3 + v17 + 16) )
      {
        if ( !v45 )
          VmpRestoreExtensionDriver(a1);
      }
      else if ( v45 )
      {
        VmpPageExtensionDriver(a1);
      }
      if ( *(_BYTE *)(v18 + 158) )
        IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)v18, PowerRelations);
      v49 = 48;
      v31 = VmpQueryUniqueIdInternal((struct VM_VOLUME_EXTENSION *)v18, &v49, Source1);
      if ( !v29 || v31 < 0 )
        break;
      v32 = v49;
      if ( v49 != v51 )
        goto LABEL_47;
      v33 = v51;
      if ( RtlCompareMemory(Source1, Source2, v51) != v33 )
        break;
LABEL_48:
      VmpNotify((struct VM_VOLUME_EXTENSION *)v18, &GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE, 0, 0);
LABEL_49:
      v46 = ++v16;
      if ( v16 >= a2 )
        goto LABEL_50;
    }
    v32 = v49;
LABEL_47:
    VmpNotify((struct VM_VOLUME_EXTENSION *)v18, &GUID_IO_VOLUME_UNIQUE_ID_CHANGE, v32 + 2, &v49);
    goto LABEL_48;
  }
LABEL_50:
  for ( j = 0; j < a2; ++j )
  {
    v35 = 112LL * j;
    if ( !*(_QWORD *)((char *)a3 + v35) )
    {
      if ( *((_BYTE *)a3 + v35 + 16) )
      {
        if ( !*(_QWORD *)((char *)a3 + v35 + 104) )
          continue;
      }
      else if ( !*(_QWORD *)((char *)a3 + v35 + 24) )
      {
        continue;
      }
      ExtensionForPendingDynamicVolume = VmpFindExtensionForPendingDynamicVolume(a1, *(void **)((char *)a3 + v35 + 104));
      v39 = ExtensionForPendingDynamicVolume;
      v40 = (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingDynamicVolume + 32);
      v41 = *((_QWORD *)ExtensionForPendingDynamicVolume + 4);
      if ( *(struct VM_VOLUME_EXTENSION **)(v41 + 8) != (struct VM_VOLUME_EXTENSION *)((char *)ExtensionForPendingDynamicVolume
                                                                                     + 32) )
        goto LABEL_64;
      v42 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)ExtensionForPendingDynamicVolume + 5);
      if ( *v42 != v40 )
        goto LABEL_64;
      *v42 = (struct VM_ROOT_EXTENSION *)v41;
      *(_QWORD *)(v41 + 8) = v42;
      LOBYTE(v37) = *((_DWORD *)v39 + 37) > v38;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(v47 + 232))(0, *(_QWORD *)((char *)a3 + v35 + 104), v37);
      v43 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 27);
      if ( *v43 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 208) )
        goto LABEL_64;
      *((_QWORD *)v40 + 1) = v43;
      *(_QWORD *)v40 = (char *)a1 + 208;
      *v43 = v40;
      *((_QWORD *)a1 + 27) = v40;
      VmpSetDevicePowerState(v39, *(enum _DEVICE_POWER_STATE *)((char *)a3 + v35 + 20));
      v44 = 1;
    }
  }
  if ( v44 )
    IoInvalidateDeviceRelations(*((PDEVICE_OBJECT *)a1 + 6), SingleBusRelations);
}

```

## disassembly

```asm
0x14000eba0  mov     [rsp-8+arg_8], rbx
0x14000eba5  push    rbp
0x14000eba6  push    rsi
0x14000eba7  push    rdi
0x14000eba8  push    r12
0x14000ebaa  push    r13
0x14000ebac  push    r14
0x14000ebae  push    r15
0x14000ebb0  lea     rbp, [rsp-20h]
0x14000ebb5  sub     rsp, 120h
0x14000ebbc  mov     rax, cs:__security_cookie
0x14000ebc3  xor     rax, rsp
0x14000ebc6  mov     [rbp+50h+var_40], rax
0x14000ebca  mov     rax, [rcx+188h]
0x14000ebd1  mov     r12d, edx
0x14000ebd4  xor     edx, edx; Val
0x14000ebd6  mov     [rsp+150h+var_128], rax
0x14000ebdb  mov     rdi, r8
0x14000ebde  mov     r13, rcx
0x14000ebe1  lea     rcx, [rsp+150h+var_120]; void *
0x14000ebe6  lea     r8d, [rdx+68h]; Size
0x14000ebea  call    memset
0x14000ebef  xor     r9d, r9d
0x14000ebf2  mov     [rsp+150h+var_130], r9b
0x14000ebf7  mov     r14d, r9d
0x14000ebfa  test    r12d, r12d
0x14000ebfd  jz      loc_14000ED4E
0x14000ec03  mov     eax, r14d
0x14000ec06  imul    rsi, rax, 70h ; 'p'
0x14000ec0a  mov     rbx, [rsi+rdi]
0x14000ec0e  test    rbx, rbx
0x14000ec11  jz      loc_14000ED42
0x14000ec17  cmp     [rsi+rdi+10h], r9b
0x14000ec1c  jnz     short loc_14000EC25
0x14000ec1e  cmp     [rsi+rdi+18h], r9
0x14000ec23  jmp     short loc_14000EC2A
0x14000ec25  cmp     [rsi+rdi+68h], r9
0x14000ec2a  jnz     loc_14000ED42
0x14000ec30  mov     rax, ds:0FFFFF78000000014h
0x14000ec3a  mov     [rbx+30h], rax
0x14000ec3e  cmp     [rbx+9Eh], r9b
0x14000ec45  jnz     short loc_14000EC8B
0x14000ec47  lea     rax, [rbx+20h]
0x14000ec4b  mov     rcx, [rax]
0x14000ec4e  cmp     [rcx+8], rax
0x14000ec52  jnz     loc_14000F14B
0x14000ec58  mov     rdx, [rbx+28h]
0x14000ec5c  cmp     [rdx], rax
0x14000ec5f  jnz     loc_14000F14B
0x14000ec65  mov     [rdx], rcx
0x14000ec68  mov     [rcx+8], rdx
0x14000ec6c  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ec6f  call    ?VmpCleanupVolumeExtension@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpCleanupVolumeExtension(VM_VOLUME_EXTENSION *)
0x14000ec74  mov     rcx, [rbx]; DeviceObject
0x14000ec77  call    cs:__imp_IoDeleteDevice
0x14000ec7e  nop     dword ptr [rax+rax+00h]
0x14000ec83  xor     r9d, r9d
0x14000ec86  jmp     loc_14000ED42
0x14000ec8b  cmp     [rsi+rdi+11h], r9b
0x14000ec90  jz      short loc_14000ECA7
0x14000ec92  xor     r8d, r8d; unsigned __int16
0x14000ec95  lea     rdx, GUID_IO_VOLUME_PREPARE_DELETE; struct _GUID *
0x14000ec9c  xor     r9d, r9d; void *
0x14000ec9f  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000eca2  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x14000eca7  xor     edx, edx; unsigned __int8
0x14000eca9  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ecac  call    ?VmpDeleteLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpDeleteLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x14000ecb1  mov     rcx, rbx
0x14000ecb4  call    VmpReleaseInterfaces
0x14000ecb9  xor     edx, edx; Val
0x14000ecbb  lea     rcx, [rsp+150h+var_11F]; void *
0x14000ecc0  lea     r8d, [rdx+67h]; Size
0x14000ecc4  call    memset
0x14000ecc9  mov     al, [rsi+rdi+10h]
0x14000eccd  lea     r8, [rsp+150h+var_120]; void *
0x14000ecd2  lea     rdx, ?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x14000ecd9  mov     [rsp+150h+var_120], al
0x14000ecdd  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000ece0  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x14000ece5  lea     rax, [rbx+20h]
0x14000ece9  mov     rdx, [rax]
0x14000ecec  cmp     [rdx+8], rax
0x14000ecf0  jnz     loc_14000F14B
0x14000ecf6  mov     rcx, [rbx+28h]
0x14000ecfa  cmp     [rcx], rax
0x14000ecfd  jnz     loc_14000F14B
0x14000ed03  mov     [rcx], rdx
0x14000ed06  mov     [rdx+8], rcx
0x14000ed0a  lea     rcx, [r13+0E0h]
0x14000ed11  mov     rdx, [rcx+8]
0x14000ed15  cmp     [rdx], rcx
0x14000ed18  jnz     loc_14000F14B
0x14000ed1e  mov     [rax], rcx
0x14000ed21  xor     r9d, r9d
0x14000ed24  mov     [rax+8], rdx
0x14000ed28  mov     [rdx], rax
0x14000ed2b  mov     [rcx+8], rax
0x14000ed2f  cmp     [rsi+rdi+11h], r9b
0x14000ed34  jz      short loc_14000ED3D
0x14000ed36  mov     byte ptr [rbx+9Fh], 1
0x14000ed3d  mov     [rsp+150h+var_130], 1
0x14000ed42  inc     r14d
0x14000ed45  cmp     r14d, r12d
0x14000ed48  jb      loc_14000EC03
0x14000ed4e  mov     [rsp+150h+var_12C], r9d
0x14000ed53  mov     r14d, r9d
0x14000ed56  test    r12d, r12d
0x14000ed59  jz      loc_14000F036
0x14000ed5f  mov     ecx, 30h ; '0'
0x14000ed64  mov     eax, r14d
0x14000ed67  imul    rbx, rax, 70h ; 'p'
0x14000ed6b  mov     rsi, [rbx+rdi]
0x14000ed6f  test    rsi, rsi
0x14000ed72  jz      loc_14000F025
0x14000ed78  cmp     [rbx+rdi+10h], r9b
0x14000ed7d  jnz     short loc_14000ED86
0x14000ed7f  cmp     [rbx+rdi+18h], r9
0x14000ed84  jmp     short loc_14000ED8B
0x14000ed86  cmp     [rbx+rdi+68h], r9
0x14000ed8b  jz      loc_14000F025
0x14000ed91  mov     al, [rsi+1AAh]
0x14000ed97  lea     r8, [rbp+50h+Source2]; unsigned __int8 *
0x14000ed9b  mov     [rbp+50h+var_78], cx
0x14000ed9f  lea     rdx, [rbp+50h+var_78]; unsigned __int16 *
0x14000eda3  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000eda6  mov     [rsp+150h+var_12F], al
0x14000edaa  call    ?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z; VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)
0x14000edaf  xor     edx, edx; unsigned __int8
0x14000edb1  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000edb4  mov     r15d, eax
0x14000edb7  call    ?VmpDeleteLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpDeleteLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x14000edbc  xor     edx, edx; Val
0x14000edbe  lea     rcx, [rsp+150h+var_11F]; void *
0x14000edc3  lea     r8d, [rdx+67h]; Size
0x14000edc7  call    memset
0x14000edcc  mov     al, [rbx+rdi+10h]
0x14000edd0  mov     [rsp+150h+var_120], al
0x14000edd4  test    al, al
0x14000edd6  jz      short loc_14000EE23
0x14000edd8  mov     rax, [rsp+150h+var_128]
0x14000eddd  mov     rcx, [rbx+rdi+68h]
0x14000ede2  mov     rax, [rax+88h]
0x14000ede9  call    _guard_dispatch_icall
0x14000edee  mov     rcx, [rsi]
0x14000edf1  mov     [rcx+98h], eax
0x14000edf7  mov     rax, [rsp+150h+var_128]
0x14000edfc  mov     rcx, [rbx+rdi+68h]
0x14000ee01  mov     rax, [rax+80h]
0x14000ee08  call    _guard_dispatch_icall
0x14000ee0d  mov     rcx, [rsi]
0x14000ee10  add     al, 2
0x14000ee12  mov     [rcx+4Ch], al
0x14000ee15  mov     rax, [rbx+rdi+68h]
0x14000ee1a  mov     [rbp+50h+var_C0], rax
0x14000ee1e  jmp     loc_14000EEFB
0x14000ee23  mov     rax, [rbx+rdi+18h]
0x14000ee28  lea     rdx, [rsp+150h+var_F8]; unsigned __int16 **
0x14000ee2d  mov     ecx, [rax+98h]
0x14000ee33  mov     rax, [rsi]
0x14000ee36  mov     [rax+98h], ecx
0x14000ee3c  mov     rax, [rbx+rdi+18h]
0x14000ee41  mov     cl, [rax+4Ch]
0x14000ee44  mov     rax, [rsi]
0x14000ee47  inc     cl
0x14000ee49  mov     [rax+4Ch], cl
0x14000ee4c  mov     rax, [rbx+rdi+18h]
0x14000ee51  movups  xmm0, xmmword ptr [rbx+rdi+48h]
0x14000ee56  mov     rcx, [rbx+rdi+20h]; Pdo
0x14000ee5b  mov     [rsp+150h+var_118], rax
0x14000ee60  mov     rax, [rbx+rdi+28h]
0x14000ee65  mov     [rsp+150h+var_108], rax
0x14000ee6a  mov     eax, [rbx+rdi+30h]
0x14000ee6e  mov     [rsp+150h+var_100], eax
0x14000ee72  mov     eax, [rbx+rdi+34h]
0x14000ee76  mov     [rsp+150h+var_F0], eax
0x14000ee7a  mov     rax, [rbx+rdi+38h]
0x14000ee7f  mov     [rsp+150h+var_E8], rax
0x14000ee84  mov     rax, [rbx+rdi+40h]
0x14000ee89  mov     [rsp+150h+var_E0], rax
0x14000ee8e  mov     al, [rbx+rdi+60h]
0x14000ee92  mov     [rbp+50h+var_C8], al
0x14000ee95  mov     [rsp+150h+var_110], rcx
0x14000ee9a  movdqu  [rsp+150h+var_D8], xmm0
0x14000eea0  call    ?VmpGetInstancePath@@YAJPEAU_DEVICE_OBJECT@@PEAPEAG@Z; VmpGetInstancePath(_DEVICE_OBJECT *,ushort * *)
0x14000eea5  mov     rdx, [rbx+rdi+18h]; struct _DEVICE_OBJECT *
0x14000eeaa  mov     rcx, r13; struct VM_ROOT_EXTENSION *
0x14000eead  call    ?VmpFindExtensionForPendingBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpFindExtensionForPendingBasicVolume(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)
0x14000eeb2  mov     r14, rax
0x14000eeb5  test    rax, rax
0x14000eeb8  jz      short loc_14000EEF6
0x14000eeba  lea     rcx, [rax+20h]
0x14000eebe  mov     rdx, [rcx]
0x14000eec1  cmp     [rdx+8], rcx
0x14000eec5  jnz     loc_14000F14B
0x14000eecb  mov     rax, [rax+28h]
0x14000eecf  cmp     [rax], rcx
0x14000eed2  jnz     loc_14000F14B
0x14000eed8  mov     [rax], rdx
0x14000eedb  mov     rcx, r14; struct VM_VOLUME_EXTENSION *
0x14000eede  mov     [rdx+8], rax
0x14000eee2  call    ?VmpCleanupVolumeExtension@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpCleanupVolumeExtension(VM_VOLUME_EXTENSION *)
0x14000eee7  mov     rcx, [r14]; DeviceObject
0x14000eeea  call    cs:__imp_IoDeleteDevice
0x14000eef1  nop     dword ptr [rax+rax+00h]
0x14000eef6  mov     r14d, [rsp+150h+var_12C]
0x14000eefb  shr     r15d, 1Fh
0x14000eeff  lea     r8, [rsp+150h+var_120]; void *
0x14000ef04  lea     rdx, ?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x14000ef0b  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000ef0e  xor     r15b, 1
0x14000ef12  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x14000ef17  cmp     byte ptr [rbx+rdi+10h], 0
0x14000ef1c  jz      short loc_14000EF41
0x14000ef1e  mov     rax, [rsp+150h+var_128]
0x14000ef23  mov     rcx, [rsi+1B0h]
0x14000ef2a  mov     rax, [rax+98h]
0x14000ef31  call    _guard_dispatch_icall
0x14000ef36  mov     rdx, rax; unsigned __int64
0x14000ef39  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000ef3c  call    ?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z; VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)
0x14000ef41  xor     edx, edx; unsigned __int8
0x14000ef43  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000ef46  call    ?VmpCreateLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z; VmpCreateLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)
0x14000ef4b  mov     edx, [rbx+rdi+14h]; enum _DEVICE_POWER_STATE
0x14000ef4f  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000ef52  call    ?VmpSetDevicePowerState@@YAXPEAVVM_VOLUME_EXTENSION@@W4_DEVICE_POWER_STATE@@@Z; VmpSetDevicePowerState(VM_VOLUME_EXTENSION *,_DEVICE_POWER_STATE)
0x14000ef57  cmp     byte ptr [rbx+rdi+10h], 0
0x14000ef5c  jz      short loc_14000EF6F
0x14000ef5e  cmp     [rsp+150h+var_12F], 0
0x14000ef63  jnz     short loc_14000EF7E
0x14000ef65  mov     rcx, r13
0x14000ef68  call    VmpRestoreExtensionDriver
0x14000ef6d  jmp     short loc_14000EF7E
0x14000ef6f  cmp     [rsp+150h+var_12F], 0
0x14000ef74  jz      short loc_14000EF7E
0x14000ef76  mov     rcx, r13
0x14000ef79  call    VmpPageExtensionDriver
0x14000ef7e  cmp     byte ptr [rsi+9Eh], 0
0x14000ef85  jz      short loc_14000EF9B
0x14000ef87  mov     rcx, [rsi]; DeviceObject
0x14000ef8a  mov     edx, 2; Type
0x14000ef8f  call    cs:__imp_IoInvalidateDeviceRelations
0x14000ef96  nop     dword ptr [rax+rax+00h]
0x14000ef9b  mov     eax, 30h ; '0'
0x14000efa0  lea     r8, [rbp+50h+Source1]; unsigned __int8 *
0x14000efa4  lea     rdx, [rbp+50h+var_B0]; unsigned __int16 *
0x14000efa8  mov     [rbp+50h+var_B0], ax
0x14000efac  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000efaf  call    ?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z; VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)
0x14000efb4  test    r15b, r15b
0x14000efb7  jz      short loc_14000EFEC
0x14000efb9  shr     eax, 1Fh
0x14000efbc  xor     al, 1
0x14000efbe  jz      short loc_14000EFEC
0x14000efc0  movzx   r8d, [rbp+50h+var_B0]
0x14000efc5  cmp     r8w, [rbp+50h+var_78]
0x14000efca  jnz     short loc_14000EFF1
0x14000efcc  movzx   ebx, [rbp+50h+var_78]
0x14000efd0  lea     rdx, [rbp+50h+Source2]; Source2
0x14000efd4  mov     r8d, ebx; Length
0x14000efd7  lea     rcx, [rbp+50h+Source1]; Source1
0x14000efdb  call    cs:__imp_RtlCompareMemory
0x14000efe2  nop     dword ptr [rax+rax+00h]
0x14000efe7  cmp     rax, rbx
0x14000efea  jz      short loc_14000F009
0x14000efec  movzx   r8d, [rbp+50h+var_B0]
0x14000eff1  add     r8w, 2; unsigned __int16
0x14000eff6  lea     r9, [rbp+50h+var_B0]; void *
0x14000effa  lea     rdx, GUID_IO_VOLUME_UNIQUE_ID_CHANGE; struct _GUID *
0x14000f001  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000f004  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x14000f009  xor     r8d, r8d; unsigned __int16
0x14000f00c  lea     rdx, GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE; struct _GUID *
0x14000f013  xor     r9d, r9d; void *
0x14000f016  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x14000f019  call    ?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z; VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)
0x14000f01e  xor     r9d, r9d
0x14000f021  lea     ecx, [r9+30h]
0x14000f025  inc     r14d
0x14000f028  mov     [rsp+150h+var_12C], r14d
0x14000f02d  cmp     r14d, r12d
0x14000f030  jb      loc_14000ED64
0x14000f036  mov     r14d, r9d
0x14000f039  test    r12d, r12d
0x14000f03c  jz      loc_14000F107
0x14000f042  mov     eax, r14d
0x14000f045  imul    rbx, rax, 70h ; 'p'
0x14000f049  cmp     [rbx+rdi], r9
0x14000f04d  jnz     loc_14000F0FB
0x14000f053  cmp     [rbx+rdi+10h], r9b
0x14000f058  jnz     short loc_14000F066
0x14000f05a  cmp     [rbx+rdi+18h], r9
0x14000f05f  jnz     short loc_14000F071
0x14000f061  jmp     loc_14000F0FB
0x14000f066  cmp     [rbx+rdi+68h], r9
0x14000f06b  jz      loc_14000F0FB
0x14000f071  mov     rdx, [rbx+rdi+68h]; void *
0x14000f076  mov     rcx, r13; struct VM_ROOT_EXTENSION *
0x14000f079  call    ?VmpFindExtensionForPendingDynamicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAX@Z; VmpFindExtensionForPendingDynamicVolume(VM_ROOT_EXTENSION *,void *)
  ... truncated ...
```
