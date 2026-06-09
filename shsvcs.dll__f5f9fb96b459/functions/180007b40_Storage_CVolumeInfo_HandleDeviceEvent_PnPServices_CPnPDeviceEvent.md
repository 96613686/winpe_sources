# Storage::CVolumeInfo::HandleDeviceEvent(PnPServices::CPnPDeviceEvent *)

- ea: `0x180007b40`
- end: `0x180007f89`
- name: `?HandleDeviceEvent@CVolumeInfo@Storage@@UEAAJPEAVCPnPDeviceEvent@PnPServices@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(Storage::CVolumeInfo *__hidden this, struct PnPServices::CPnPDeviceEvent *)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b40`
- `0x180007f90`
- `0x180008230`
- `0x1800083e0`
- `0x180016fa0`
- `0x1800181ac`
- `0x180018ea0`
- `0x1800233bc`
- `0x18002c4a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007dac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e6b`
- `ntdll!RtlPublishWnfStateData` at `0x180007ee0`
- `ntdll!RtlPublishWnfStateData` at `0x180007ee0`

## pseudocode

```c
__int64 __fastcall Storage::CVolumeInfo::HandleDeviceEvent(
        union _ULARGE_INTEGER *this,
        struct PnPServices::CPnPDeviceEvent *a2)
{
  unsigned int updated; // r14d
  __int64 v5; // rax
  __int64 v6; // rax
  int LowPart; // r8d
  union _ULARGE_INTEGER v8; // rax
  union _ULARGE_INTEGER *v9; // r9
  __int64 result; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  struct _RTL_CRITICAL_SECTION *v14; // rbp
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int64 v16; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  union _ULARGE_INTEGER *v18; // rax
  __int64 v19; // r8
  _OWORD *v20; // rcx
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  struct _GUID v36; // [rsp+30h] [rbp-158h] BYREF
  _BYTE v37[328]; // [rsp+40h] [rbp-148h] BYREF
  union _ULARGE_INTEGER v38; // [rsp+198h] [rbp+10h] BYREF

  updated = 0;
  if ( *((_DWORD *)a2 + 4) != 32774 )
    return 0;
  v5 = *(_QWORD *)&GUID_IO_MEDIA_ARRIVAL.Data1 - *(_QWORD *)((char *)a2 + 20);
  if ( !v5 )
    v5 = *(_QWORD *)GUID_IO_MEDIA_ARRIVAL.Data4 - *(_QWORD *)((char *)a2 + 28);
  if ( !v5 )
  {
    this[411].LowPart = 0;
    updated = Storage::CVolume::UpdateMediaInfo((Storage::CVolume *)&this[2], 1);
    goto LABEL_58;
  }
  v6 = *(_QWORD *)&GUID_IO_DEVICE_BECOMING_READY.Data1 - *(_QWORD *)((char *)a2 + 20);
  if ( *(_QWORD *)&GUID_IO_DEVICE_BECOMING_READY.Data1 == *(_QWORD *)((char *)a2 + 20) )
    v6 = *(_QWORD *)GUID_IO_DEVICE_BECOMING_READY.Data4 - *(_QWORD *)((char *)a2 + 28);
  if ( !v6 )
  {
    v38.QuadPart = 0;
    GetLocalTimeAsULARGE_INTEGER(&v38);
    LowPart = this[411].LowPart;
    v8 = v38;
    switch ( LowPart )
    {
      case 1:
        v9 = this + 412;
        if ( v38.QuadPart - this[412].QuadPart < 0x11E1A300 )
        {
          LowPart = 1;
        }
        else
        {
          LowPart = 2;
          this[411].LowPart = 2;
        }
        break;
      case 2:
        if ( v38.QuadPart - this[413].QuadPart >= 0x3938700 )
        {
          v9 = this + 412;
LABEL_18:
          *v9 = v8;
          this[411].LowPart = 1;
        }
LABEL_19:
        this[413] = v8;
        return updated;
      case 0:
        goto LABEL_18;
      default:
        v9 = this + 412;
        break;
    }
    goto LABEL_19;
  }
  v11 = *(_QWORD *)&GUID_IO_MEDIA_REMOVAL.Data1 - *(_QWORD *)((char *)a2 + 20);
  if ( *(_QWORD *)&GUID_IO_MEDIA_REMOVAL.Data1 == *(_QWORD *)((char *)a2 + 20) )
    v11 = *(_QWORD *)GUID_IO_MEDIA_REMOVAL.Data4 - *(_QWORD *)((char *)a2 + 28);
  if ( !v11 )
  {
    this[411].LowPart = 0;
    updated = Storage::CVolume::UpdateMediaInfoOnRemove((Storage::CVolume *)&this[2]);
    goto LABEL_58;
  }
  v12 = *(_QWORD *)&GUID_IO_VOLUME_NAME_CHANGE.Data1 - *(_QWORD *)((char *)a2 + 20);
  if ( *(_QWORD *)&GUID_IO_VOLUME_NAME_CHANGE.Data1 == *(_QWORD *)((char *)a2 + 20) )
    v12 = *(_QWORD *)GUID_IO_VOLUME_NAME_CHANGE.Data4 - *(_QWORD *)((char *)a2 + 28);
  if ( v12 )
  {
    v13 = *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1 - *(_QWORD *)((char *)a2 + 20);
    if ( *(_QWORD *)&GUID_IO_VOLUME_CHANGE.Data1 == *(_QWORD *)((char *)a2 + 20) )
      v13 = *(_QWORD *)GUID_IO_VOLUME_CHANGE.Data4 - *(_QWORD *)((char *)a2 + 28);
    if ( v13 )
    {
      v16 = *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 - *(_QWORD *)((char *)a2 + 20);
      if ( *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 == *(_QWORD *)((char *)a2 + 20) )
        v16 = *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4 - *(_QWORD *)((char *)a2 + 28);
      if ( !v16 )
      {
        v17 = (struct _RTL_CRITICAL_SECTION *)&this[405];
        if ( this == (union _ULARGE_INTEGER *)-3232LL )
          v17 = 0;
        EnterCriticalSection(v17);
        v18 = this + 6;
        v19 = 2;
        v20 = v37;
        do
        {
          v20 += 8;
          v21 = *(_OWORD *)&v18->LowPart;
          v22 = *(_OWORD *)&v18[2].LowPart;
          v18 += 16;
          *(v20 - 8) = v21;
          v23 = *(_OWORD *)&v18[-12].LowPart;
          *(v20 - 7) = v22;
          v24 = *(_OWORD *)&v18[-10].LowPart;
          *(v20 - 6) = v23;
          v25 = *(_OWORD *)&v18[-8].LowPart;
          *(v20 - 5) = v24;
          v26 = *(_OWORD *)&v18[-6].LowPart;
          *(v20 - 4) = v25;
          v27 = *(_OWORD *)&v18[-4].LowPart;
          *(v20 - 3) = v26;
          v28 = *(_OWORD *)&v18[-2].LowPart;
          *(v20 - 2) = v27;
          *(v20 - 1) = v28;
          --v19;
        }
        while ( v19 );
        v29 = *(_OWORD *)&v18[2].LowPart;
        *v20 = *(_OWORD *)&v18->LowPart;
        v30 = *(_OWORD *)&v18[4].LowPart;
        v20[1] = v29;
        v20[2] = v30;
        LeaveCriticalSection(v17);
        v31 = 0;
        if ( (v37[16] & 4) != 0 )
        {
          this[8].LowPart &= ~4u;
          v31 = 1;
        }
        if ( *((_DWORD *)a2 + 12) )
        {
          if ( !v31 )
            return updated;
          goto LABEL_71;
        }
        updated = Storage::CVolume::UpdateMediaInfo((Storage::CVolume *)&this[2], 0);
LABEL_58:
        if ( (updated & 0x80000000) == 0 )
        {
LABEL_71:
          Storage::CVolumeInfo::_DispatchEvent(
            (Storage::CVolumeInfo *)&this[-2],
            (const struct _GUID *)((char *)a2 + 20));
          return updated;
        }
        return updated;
      }
      v32 = *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1 - *(_QWORD *)((char *)a2 + 20);
      if ( *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1 == *(_QWORD *)((char *)a2 + 20) )
        v32 = *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4 - *(_QWORD *)((char *)a2 + 28);
      if ( v32 )
      {
        v33 = *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1 - *(_QWORD *)((char *)a2 + 20);
        if ( *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1 == *(_QWORD *)((char *)a2 + 20) )
          v33 = *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4 - *(_QWORD *)((char *)a2 + 28);
        if ( v33 )
        {
          v34 = *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1 - *(_QWORD *)((char *)a2 + 20);
          if ( *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1 == *(_QWORD *)((char *)a2 + 20) )
            v34 = *(_QWORD *)GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4 - *(_QWORD *)((char *)a2 + 28);
          if ( !v34 )
            goto LABEL_70;
          v35 = *(_QWORD *)&GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1 - *(_QWORD *)((char *)a2 + 20);
          if ( *(_QWORD *)&GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1 == *(_QWORD *)((char *)a2 + 20) )
            v35 = *(_QWORD *)GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4 - *(_QWORD *)((char *)a2 + 28);
          if ( !v35 )
          {
LABEL_70:
            if ( (int)Storage::CVolume::UpdateBitLockerStatus((Storage::CVolume *)&this[2]) < 0 )
              return updated;
          }
          goto LABEL_71;
        }
        this[8].LowPart &= ~4u;
        Storage::CVolumeInfo::_DispatchEvent((Storage::CVolumeInfo *)&this[-2], (const struct _GUID *)((char *)a2 + 20));
        return updated;
      }
      this[8].LowPart |= 4u;
    }
    else
    {
      Storage::CVolumeInfo::_UpdateMountPoints((Storage::CVolumeInfo *)&this[-2]);
      v14 = (struct _RTL_CRITICAL_SECTION *)&this[405];
      v15 = (struct _RTL_CRITICAL_SECTION *)&this[405];
      if ( this == (union _ULARGE_INTEGER *)-3232LL )
        v15 = 0;
      EnterCriticalSection(v15);
      updated = Storage::CVolume::_UpdateMediaInfo((LPCWSTR *)&this[2], 0, 1);
      Storage::CVolume::UpdateBitLockerStatus((Storage::CVolume *)&this[2]);
      if ( this == (union _ULARGE_INTEGER *)-3232LL )
        v14 = 0;
      LeaveCriticalSection(v14);
    }
    RtlPublishWnfStateData(WNF_OSWN_STORAGE_SHELLHWD_EVENT, 0, 0, 0, 0);
    goto LABEL_58;
  }
  result = Storage::CVolume::GetBasicInfo((Storage::CVolume *)&this[2], (struct Storage::VOLUMEBASICINFO *)v37);
  if ( (int)result >= 0 )
  {
    this[8].LowPart &= ~4u;
    result = Storage::CVolume::UpdateMediaInfo((Storage::CVolume *)&this[2], 0);
    if ( (int)result >= 0 )
    {
      v36 = GUID_IO_VOLUME_MOUNT;
      Storage::CVolumeInfo::_DispatchEvent((Storage::CVolumeInfo *)&this[-2], &v36);
      updated = Storage::CVolumeInfo::_UpdateMountPoints((Storage::CVolumeInfo *)&this[-2]);
      goto LABEL_58;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007b40  push    rdi
0x180007b42  push    r14
0x180007b44  push    r15
0x180007b46  sub     rsp, 170h
0x180007b4d  xor     r14d, r14d
0x180007b50  mov     rdi, rdx
0x180007b53  cmp     dword ptr [rdx+10h], 8006h
0x180007b5a  mov     r15, rcx
0x180007b5d  jnz     loc_180007F81
0x180007b63  mov     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data1
0x180007b6a  mov     [rsp+188h+arg_0], rbx
0x180007b72  sub     rax, [rdx+14h]
0x180007b76  jnz     short loc_180007B83
0x180007b78  mov     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data4
0x180007b7f  sub     rax, [rdx+1Ch]
0x180007b83  mov     [rsp+188h+arg_10], rbp
0x180007b8b  mov     [rsp+188h+arg_18], rsi
0x180007b93  test    rax, rax
0x180007b96  jnz     short loc_180007BB5
0x180007b98  mov     [rcx+0CD8h], r14d
0x180007b9f  mov     edx, 1; int
0x180007ba4  add     rcx, 10h; this
0x180007ba8  call    ?UpdateMediaInfo@CVolume@Storage@@QEAAJH@Z; Storage::CVolume::UpdateMediaInfo(int)
0x180007bad  mov     r14d, eax
0x180007bb0  jmp     loc_180007EE6
0x180007bb5  mov     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data1
0x180007bbc  sub     rax, [rdx+14h]
0x180007bc0  jnz     short loc_180007BCD
0x180007bc2  mov     rax, qword ptr cs:GUID_IO_DEVICE_BECOMING_READY.Data4
0x180007bc9  sub     rax, [rdx+1Ch]
0x180007bcd  test    rax, rax
0x180007bd0  jnz     loc_180007C95
0x180007bd6  lea     rcx, [rsp+188h+arg_8]; union _ULARGE_INTEGER *
0x180007bde  mov     qword ptr [rsp+188h+arg_8], r14
0x180007be6  call    ?GetLocalTimeAsULARGE_INTEGER@@YAXPEAT_ULARGE_INTEGER@@@Z; GetLocalTimeAsULARGE_INTEGER(_ULARGE_INTEGER *)
0x180007beb  mov     r8d, [r15+0CD8h]
0x180007bf2  mov     edx, 1
0x180007bf7  mov     rax, qword ptr [rsp+188h+arg_8]
0x180007bff  cmp     r8d, edx
0x180007c02  jnz     short loc_180007C2E
0x180007c04  lea     r9, [r15+0CE0h]
0x180007c0b  mov     rcx, rax
0x180007c0e  sub     rcx, [r9]
0x180007c11  cmp     rcx, 11E1A300h
0x180007c18  jb      short loc_180007C29
0x180007c1a  mov     r8d, 2
0x180007c20  mov     [r15+0CD8h], r8d
0x180007c27  jmp     short loc_180007C57
0x180007c29  mov     r8d, edx
0x180007c2c  jmp     short loc_180007C57
0x180007c2e  cmp     r8d, 2
0x180007c32  jnz     short loc_180007C50
0x180007c34  mov     rcx, rax
0x180007c37  sub     rcx, [r15+0CE8h]
0x180007c3e  cmp     rcx, 3938700h
0x180007c45  jb      short loc_180007C66
0x180007c47  lea     r9, [r15+0CE0h]
0x180007c4e  jmp     short loc_180007C5C
0x180007c50  lea     r9, [r15+0CE0h]
0x180007c57  test    r8d, r8d
0x180007c5a  jnz     short loc_180007C66
0x180007c5c  mov     [r9], rax
0x180007c5f  mov     [r15+0CD8h], edx
0x180007c66  mov     [r15+0CE8h], rax
0x180007c6d  mov     eax, r14d
0x180007c70  mov     rbp, [rsp+188h+arg_10]
0x180007c78  mov     rsi, [rsp+188h+arg_18]
0x180007c80  mov     rbx, [rsp+188h+arg_0]
0x180007c88  add     rsp, 170h
0x180007c8f  pop     r15
0x180007c91  pop     r14
0x180007c93  pop     rdi
0x180007c94  retn
0x180007c95  mov     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data1
0x180007c9c  sub     rax, [rdx+14h]
0x180007ca0  jnz     short loc_180007CAD
0x180007ca2  mov     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data4
0x180007ca9  sub     rax, [rdx+1Ch]
0x180007cad  test    rax, rax
0x180007cb0  jnz     short loc_180007CCA
0x180007cb2  mov     [rcx+0CD8h], r14d
0x180007cb9  add     rcx, 10h; this
0x180007cbd  call    ?UpdateMediaInfoOnRemove@CVolume@Storage@@QEAAJXZ; Storage::CVolume::UpdateMediaInfoOnRemove(void)
0x180007cc2  mov     r14d, eax
0x180007cc5  jmp     loc_180007EE6
0x180007cca  mov     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x180007cd1  sub     rax, [rdx+14h]
0x180007cd5  jnz     short loc_180007CE2
0x180007cd7  mov     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data4
0x180007cde  sub     rax, [rdx+1Ch]
0x180007ce2  test    rax, rax
0x180007ce5  jnz     short loc_180007D40
0x180007ce7  lea     rdx, [rsp+188h+var_148]; struct Storage::VOLUMEBASICINFO *
0x180007cec  add     rcx, 10h; this
0x180007cf0  call    ?GetBasicInfo@CVolume@Storage@@QEAAJPEAUVOLUMEBASICINFO@2@@Z; Storage::CVolume::GetBasicInfo(Storage::VOLUMEBASICINFO *)
0x180007cf5  test    eax, eax
0x180007cf7  js      loc_180007C70
0x180007cfd  and     dword ptr [r15+40h], 0FFFFFFFBh
0x180007d02  lea     rcx, [r15+10h]; this
0x180007d06  xor     edx, edx; int
0x180007d08  call    ?UpdateMediaInfo@CVolume@Storage@@QEAAJH@Z; Storage::CVolume::UpdateMediaInfo(int)
0x180007d0d  test    eax, eax
0x180007d0f  js      loc_180007C70
0x180007d15  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x180007d1c  lea     rdx, [rsp+188h+var_158]; struct _GUID *
0x180007d21  lea     rcx, [r15-10h]; this
0x180007d25  movups  xmmword ptr [rsp+188h+var_158.Data1], xmm0
0x180007d2a  call    ?_DispatchEvent@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@@Z; Storage::CVolumeInfo::_DispatchEvent(_GUID const *)
0x180007d2f  lea     rcx, [r15-10h]; this
0x180007d33  call    ?_UpdateMountPoints@CVolumeInfo@Storage@@AEAAJXZ; Storage::CVolumeInfo::_UpdateMountPoints(void)
0x180007d38  mov     r14d, eax
0x180007d3b  jmp     loc_180007EE6
0x180007d40  mov     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data1
0x180007d47  sub     rax, [rdx+14h]
0x180007d4b  jnz     short loc_180007D58
0x180007d4d  mov     rax, qword ptr cs:GUID_IO_VOLUME_CHANGE.Data4
0x180007d54  sub     rax, [rdx+1Ch]
0x180007d58  test    rax, rax
0x180007d5b  jnz     short loc_180007DB7
0x180007d5d  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180007d61  call    ?_UpdateMountPoints@CVolumeInfo@Storage@@AEAAJXZ; Storage::CVolumeInfo::_UpdateMountPoints(void)
0x180007d66  xor     eax, eax
0x180007d68  lea     rsi, [r15+0CA0h]
0x180007d6f  lea     rbp, [rsi+8]
0x180007d73  test    rsi, rsi
0x180007d76  mov     rcx, rbp
0x180007d79  cmovz   rcx, rax; lpCriticalSection
0x180007d7d  call    cs:__imp_EnterCriticalSection
0x180007d83  xor     edx, edx; struct CSafeHandle *
0x180007d85  lea     rcx, [r15+10h]; this
0x180007d89  mov     r8d, 1; int
0x180007d8f  call    ?_UpdateMediaInfo@CVolume@Storage@@AEAAJPEAVCSafeHandle@@H@Z; Storage::CVolume::_UpdateMediaInfo(CSafeHandle *,int)
0x180007d94  lea     rcx, [r15+10h]; this
0x180007d98  mov     r14d, eax
0x180007d9b  call    ?UpdateBitLockerStatus@CVolume@Storage@@QEAAJXZ; Storage::CVolume::UpdateBitLockerStatus(void)
0x180007da0  xor     eax, eax
0x180007da2  test    rsi, rsi
0x180007da5  cmovz   rbp, rax
0x180007da9  mov     rcx, rbp; lpCriticalSection
0x180007dac  call    cs:__imp_LeaveCriticalSection
0x180007db2  jmp     loc_180007EC8
0x180007db7  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x180007dbe  sub     rax, [rdx+14h]
0x180007dc2  jnz     short loc_180007DCF
0x180007dc4  mov     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x180007dcb  sub     rax, [rdx+1Ch]
0x180007dcf  test    rax, rax
0x180007dd2  jnz     loc_180007EA7
0x180007dd8  add     rcx, 0CA0h
0x180007ddf  lea     rsi, [rcx+8]
0x180007de3  cmovz   rsi, rax
0x180007de7  mov     rcx, rsi; lpCriticalSection
0x180007dea  call    cs:__imp_EnterCriticalSection
0x180007df0  lea     rax, [r15+30h]
0x180007df4  mov     r8d, 2
0x180007dfa  lea     rcx, [rsp+188h+var_148]
0x180007dff  lea     rcx, [rcx+80h]
0x180007e06  movups  xmm0, xmmword ptr [rax]
0x180007e09  movups  xmm1, xmmword ptr [rax+10h]
0x180007e0d  lea     rax, [rax+80h]
0x180007e14  movups  xmmword ptr [rcx-80h], xmm0
0x180007e18  movups  xmm0, xmmword ptr [rax-60h]
0x180007e1c  movups  xmmword ptr [rcx-70h], xmm1
0x180007e20  movups  xmm1, xmmword ptr [rax-50h]
0x180007e24  movups  xmmword ptr [rcx-60h], xmm0
0x180007e28  movups  xmm0, xmmword ptr [rax-40h]
0x180007e2c  movups  xmmword ptr [rcx-50h], xmm1
0x180007e30  movups  xmm1, xmmword ptr [rax-30h]
0x180007e34  movups  xmmword ptr [rcx-40h], xmm0
0x180007e38  movups  xmm0, xmmword ptr [rax-20h]
0x180007e3c  movups  xmmword ptr [rcx-30h], xmm1
0x180007e40  movups  xmm1, xmmword ptr [rax-10h]
0x180007e44  movups  xmmword ptr [rcx-20h], xmm0
0x180007e48  movups  xmmword ptr [rcx-10h], xmm1
0x180007e4c  sub     r8, 1
0x180007e50  jnz     short loc_180007DFF
0x180007e52  movups  xmm0, xmmword ptr [rax]
0x180007e55  movups  xmm1, xmmword ptr [rax+10h]
0x180007e59  movups  xmmword ptr [rcx], xmm0
0x180007e5c  movups  xmm0, xmmword ptr [rax+20h]
0x180007e60  movups  xmmword ptr [rcx+10h], xmm1
0x180007e64  movups  xmmword ptr [rcx+20h], xmm0
0x180007e68  mov     rcx, rsi; lpCriticalSection
0x180007e6b  call    cs:__imp_LeaveCriticalSection
0x180007e71  xor     edx, edx
0x180007e73  test    [rsp+188h+var_138], 4
0x180007e78  jz      short loc_180007E84
0x180007e7a  and     dword ptr [r15+40h], 0FFFFFFFBh
0x180007e7f  mov     edx, 1
0x180007e84  cmp     [rdi+30h], r14d
0x180007e88  jnz     short loc_180007E9A
0x180007e8a  xor     edx, edx; int
0x180007e8c  lea     rcx, [r15+10h]; this
0x180007e90  call    ?UpdateMediaInfo@CVolume@Storage@@QEAAJH@Z; Storage::CVolume::UpdateMediaInfo(int)
0x180007e95  mov     r14d, eax
0x180007e98  jmp     short loc_180007EE6
0x180007e9a  test    edx, edx
0x180007e9c  jnz     loc_180007F6F
0x180007ea2  jmp     loc_180007C6D
0x180007ea7  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x180007eae  sub     rax, [rdx+14h]
0x180007eb2  jnz     short loc_180007EBF
0x180007eb4  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x180007ebb  sub     rax, [rdx+1Ch]
0x180007ebf  test    rax, rax
0x180007ec2  jnz     short loc_180007EF1
0x180007ec4  or      dword ptr [rcx+40h], 4
0x180007ec8  mov     rcx, cs:WNF_OSWN_STORAGE_SHELLHWD_EVENT
0x180007ecf  xor     r9d, r9d
0x180007ed2  xor     r8d, r8d
0x180007ed5  mov     [rsp+188h+var_168], 0
0x180007ede  xor     edx, edx
0x180007ee0  call    cs:__imp_RtlPublishWnfStateData
0x180007ee6  test    r14d, r14d
0x180007ee9  js      loc_180007C6D
0x180007eef  jmp     short loc_180007F6F
0x180007ef1  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
0x180007ef8  sub     rax, [rdx+14h]
0x180007efc  jnz     short loc_180007F09
0x180007efe  mov     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data4
0x180007f05  sub     rax, [rdx+1Ch]
0x180007f09  test    rax, rax
0x180007f0c  jnz     short loc_180007F24
0x180007f0e  and     dword ptr [rcx+40h], 0FFFFFFFBh
0x180007f12  lea     rdx, [rdi+14h]; struct _GUID *
0x180007f16  lea     rcx, [r15-10h]; this
0x180007f1a  call    ?_DispatchEvent@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@@Z; Storage::CVolumeInfo::_DispatchEvent(_GUID const *)
0x180007f1f  jmp     loc_180007C6D
0x180007f24  mov     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x180007f2b  sub     rax, [rdx+14h]
0x180007f2f  jnz     short loc_180007F3C
0x180007f31  mov     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4
0x180007f38  sub     rax, [rdx+1Ch]
0x180007f3c  test    rax, rax
0x180007f3f  jz      short loc_180007F5E
0x180007f41  mov     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data1
0x180007f48  sub     rax, [rdx+14h]
0x180007f4c  jnz     short loc_180007F59
0x180007f4e  mov     rax, qword ptr cs:GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE.Data4
0x180007f55  sub     rax, [rdx+1Ch]
0x180007f59  test    rax, rax
0x180007f5c  jnz     short loc_180007F6F
0x180007f5e  add     rcx, 10h; this
0x180007f62  call    ?UpdateBitLockerStatus@CVolume@Storage@@QEAAJXZ; Storage::CVolume::UpdateBitLockerStatus(void)
0x180007f67  test    eax, eax
0x180007f69  js      loc_180007C6D
0x180007f6f  lea     rcx, [r15-10h]; this
0x180007f73  lea     rdx, [rdi+14h]; struct _GUID *
0x180007f77  call    ?_DispatchEvent@CVolumeInfo@Storage@@AEAAJPEBU_GUID@@@Z; Storage::CVolumeInfo::_DispatchEvent(_GUID const *)
0x180007f7c  jmp     loc_180007C6D
0x180007f81  mov     eax, r14d
0x180007f84  jmp     loc_180007C88
```
