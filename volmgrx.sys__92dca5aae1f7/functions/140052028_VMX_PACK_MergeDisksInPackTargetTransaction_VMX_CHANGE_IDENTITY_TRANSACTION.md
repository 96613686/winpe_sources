# VMX_PACK::MergeDisksInPackTargetTransaction(VMX_CHANGE_IDENTITY_TRANSACTION *)

- ea: `0x140052028`
- end: `0x140052beb`
- name: `?MergeDisksInPackTargetTransaction@VMX_PACK@@QEAAJPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@@Z`
- size: `3011`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this, struct VMX_CHANGE_IDENTITY_TRANSACTION *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x140039028`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001b960`
- `0x14001b9a0`
- `0x14002aed4`
- `0x14003f05c`
- `0x14003f51c`
- `0x14004012c`
- `0x1400401cc`
- `0x140040270`
- `0x1400402dc`
- `0x14004037c`
- `0x14004e2a0`
- `0x1400505c4`
- `0x140050afc`
- `0x1400514e4`
- `0x140051818`
- `0x140051a14`
- `0x140052028`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14005255e`
- `ntoskrnl!ExUuidCreate` at `0x14005255e`

## pseudocode

```c
__int64 __fastcall VMX_PACK::MergeDisksInPackTargetTransaction(
        VMX_CONFIG **this,
        struct VMX_CHANGE_IDENTITY_TRANSACTION *a2)
{
  VMX_PACK *v3; // rcx
  __int64 v4; // rbx
  struct VMX_CONFIG *v5; // r8
  VMX_PACK *v6; // rcx
  VMX_PACK *v7; // r14
  __int16 v8; // ax
  bool v9; // zf
  _WORD *v10; // rax
  __int64 v11; // r13
  struct VMX_RECORD *DiskById; // rax
  VMX_CONFIG *v13; // r11
  VMX_RECORD *v14; // rbx
  __int16 v15; // ax
  __int16 v16; // ax
  NTSTATUS v17; // edi
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r15
  unsigned int v21; // r8d
  VMX_NOTIFICATION_QUEUE *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // r14
  VMX_RECORD *i; // r15
  __int64 *v27; // rax
  __int64 v28; // r13
  VMX_PACK *v29; // rcx
  VMX_PACK *j; // r12
  __int16 v31; // ax
  __int64 *v32; // rax
  __int64 v33; // r15
  VMX_RECORD *v34; // r13
  struct VMX_RECORD *k; // rcx
  VMX_CONFIG *v36; // rcx
  struct VMX_RECORD *VolumeById; // rax
  VMX_CONFIG *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // r8
  unsigned int v41; // r8d
  UUID v42; // xmm0
  __int64 v43; // rax
  __int64 v44; // r8
  _QWORD *v45; // rax
  __int64 v46; // r8
  _QWORD *v47; // r15
  VMX_RECORD *v48; // rcx
  struct VMX_RECORD *v49; // rax
  unsigned int v50; // r9d
  VMX_RECORD *v51; // rdi
  __int64 v52; // rax
  __int64 v53; // r8
  struct VMX_RECORD *m; // rcx
  VMX_RECORD *v55; // rax
  VMX_CONFIG *v56; // rcx
  VMX_CONFIG *v57; // r11
  _QWORD *v58; // rax
  __int64 v59; // r8
  _QWORD *v60; // r15
  VMX_RECORD *v61; // rcx
  struct VMX_RECORD *v62; // rax
  unsigned int v63; // r9d
  VMX_RECORD *v64; // rdi
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // r8
  unsigned int v69; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v70; // [rsp+34h] [rbp-45h] BYREF
  VMX_RECORD *v71; // [rsp+38h] [rbp-41h] BYREF
  VMX_RECORD *v72; // [rsp+40h] [rbp-39h] BYREF
  struct VMX_RECORD *v73; // [rsp+48h] [rbp-31h] BYREF
  VMX_PACK *v74; // [rsp+50h] [rbp-29h]
  struct VMX_RECORD *v75; // [rsp+58h] [rbp-21h]
  VMX_RECORD *v76; // [rsp+60h] [rbp-19h] BYREF
  __int64 v77; // [rsp+68h] [rbp-11h]
  struct VMX_RECORD *v78; // [rsp+70h] [rbp-9h]
  __int64 v79; // [rsp+78h] [rbp-1h]
  UUID Uuid; // [rsp+80h] [rbp+7h] BYREF

  v73 = 0;
  v3 = (VMX_PACK *)*((_QWORD *)a2 + 7);
  Uuid = 0;
  v70 = 0;
  v76 = 0;
  v4 = *((_QWORD *)v3 + 2);
  v72 = 0;
  v69 = 0;
  VMX_PACK::MarkClosure(v3, a2);
  v6 = (VMX_PACK *)(v4 + 16);
  v7 = *(VMX_PACK **)(v4 + 16);
  v74 = (VMX_PACK *)(v4 + 16);
  while ( v7 != v6 )
  {
    if ( *((_WORD *)v7 + 16) == 4 )
    {
      v8 = *((_WORD *)v7 + 32);
      if ( (v8 & 0x400) != 0 )
      {
        v9 = (v8 & 1) == 0;
        v10 = (_WORD *)((char *)v7 + 48);
        if ( v9 )
          v10 = (_WORD *)((char *)v7 + 40);
        v11 = *(_QWORD *)v10;
        DiskById = VMX_CONFIG::FindDiskById(this[2], (struct _GUID *)(*(_QWORD *)v10 + 72LL));
        v71 = DiskById;
        v14 = DiskById;
        if ( DiskById )
        {
          v15 = *((_WORD *)DiskById + 32);
          if ( *(_QWORD *)(v11 + 128) )
            v16 = v15 | 0x400;
          else
            v16 = v15 | 0x200;
          *((_WORD *)v14 + 32) = v16;
        }
        else
        {
          v17 = VMX_CONFIG::CreateRecord(v13, &v71);
          if ( v17 < 0 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return (unsigned int)v17;
            }
            v23 = 190;
LABEL_30:
            v24 = (unsigned int)v17;
LABEL_31:
            WPP_SF_d(*((_QWORD *)v22 + 3), v23, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v24);
            return (unsigned int)v17;
          }
          v18 = VMX_ALLOCATED_OBJECT::operator new(136, 256, 1767009622);
          v20 = v18;
          if ( !v18 )
          {
            v24 = 3221225626LL;
            v17 = -1073741670;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return (unsigned int)v17;
            }
            v23 = 191;
            goto LABEL_31;
          }
          v14 = v71;
          *(_QWORD *)v18 = &VMX_DISK_INFO::`vftable';
          LOBYTE(v19) = 1;
          *((_WORD *)v14 + 16) = 4;
          *((_QWORD *)v14 + 6) = v18;
          *((_WORD *)v14 + 32) |= 1u;
          v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, v11, v19);
          if ( v17 < 0 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return (unsigned int)v17;
            }
            v23 = 192;
            goto LABEL_30;
          }
          *(_QWORD *)(v20 + 48) = v14;
          *(_BYTE *)(v20 + 64) = 1;
          VMX_CONFIG::NextDiskName(this[2], (NTSTRSAFE_PSTR)(v20 + 16), v21);
          *(_DWORD *)(v20 + 96) |= 0x20u;
          *(_QWORD *)(v20 + 128) = 0;
          VMX_RECORD::Touch(v14, this[6]);
          ++*((_DWORD *)this[6] + 5);
        }
        v6 = v74;
        *((_QWORD *)v14 + 7) = v7;
      }
    }
    v7 = *(VMX_PACK **)v7;
  }
  v25 = 0;
  for ( i = (VMX_RECORD *)*((_QWORD *)this[2] + 2); ; i = *(VMX_RECORD **)i )
  {
    if ( i == (VMX_CONFIG *)((char *)this[2] + 16) )
    {
      v29 = v74;
      for ( j = *(VMX_PACK **)v74; ; j = *(VMX_PACK **)j )
      {
        if ( j == v29 )
        {
          *((_BYTE *)this[6] + 50) = 1;
          return 0;
        }
        if ( *((_WORD *)j + 16) == 1 )
        {
          v31 = *((_WORD *)j + 32);
          if ( (v31 & 0x400) != 0 )
            break;
        }
LABEL_107:
        ;
      }
      v9 = (v31 & 1) == 0;
      v32 = (__int64 *)((char *)j + 48);
      if ( v9 )
        v32 = (__int64 *)((char *)j + 40);
      v33 = *v32;
      v34 = 0;
      v79 = v33;
      for ( k = *(struct VMX_RECORD **)(v33 + 264); ; k = (struct VMX_RECORD *)*((_QWORD *)v73 + 18) )
      {
        v75 = k;
        if ( !k )
        {
          if ( !v34
            || (v25 = *((_QWORD *)v34 + 6), *(_DWORD *)(v33 + 160) <= 1u)
            || *(_DWORD *)(v25 + 160) != 1
            || (v17 = VMX_PACK::CleanMirrorStuff((VMX_PACK *)this, v34), v17 >= 0) )
          {
            v29 = v74;
            goto LABEL_107;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v23 = 207;
            goto LABEL_30;
          }
          return (unsigned int)v17;
        }
        v73 = (struct VMX_RECORD *)*((_QWORD *)k + (*((_WORD *)k + 32) & 1LL) + 5);
        VMX_PACK::MergeAnalyzeSourcePlex((VMX_PACK *)this, k, &v69, &v70, &v72);
        if ( !v69 || v72 && v69 < v70 )
          break;
LABEL_101:
        ;
      }
      if ( !v34 )
      {
        v36 = this[2];
        Uuid = *(UUID *)(v33 + 232);
        VolumeById = VMX_CONFIG::FindVolumeById(v36, &Uuid);
        if ( VolumeById )
        {
          if ( (*((_BYTE *)VolumeById + 64) & 8) == 0 )
          {
            v17 = ExUuidCreate(&Uuid);
            if ( v17 < 0 )
            {
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v23 = 197;
                goto LABEL_30;
              }
              return (unsigned int)v17;
            }
          }
        }
        v38 = this[2];
        v71 = 0;
        v17 = VMX_CONFIG::CreateRecord(v38, &v71);
        if ( v17 < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v23 = 198;
            goto LABEL_30;
          }
          return (unsigned int)v17;
        }
        v39 = VMX_ALLOCATED_OBJECT::operator new(272, 256, 1767009622);
        v25 = v39;
        if ( !v39 )
        {
          v24 = 3221225626LL;
          v17 = -1073741670;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v23 = 199;
            goto LABEL_31;
          }
          return (unsigned int)v17;
        }
        v34 = v71;
        *(_QWORD *)v39 = &VMX_VOLUME_INFO::`vftable';
        LOBYTE(v40) = 1;
        *((_WORD *)v34 + 16) = 1;
        *((_QWORD *)v34 + 6) = v39;
        *((_QWORD *)v34 + 7) = j;
        *((_WORD *)v34 + 32) |= 1u;
        v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v39 + 8LL))(v39, v33, v40);
        if ( v17 < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v23 = 200;
            goto LABEL_30;
          }
          return (unsigned int)v17;
        }
        *(_QWORD *)(v25 + 48) = v34;
        *(_BYTE *)(v25 + 64) = 1;
        VMX_CONFIG::NextVolumeName(this[2], (NTSTRSAFE_PSTR)(v25 + 16), v41);
        v42 = Uuid;
        *(_DWORD *)(v25 + 160) = 0;
        *(UUID *)(v25 + 232) = v42;
        VMX_CONFIG::NextVolumeMinor(this[2], (unsigned int *)(v25 + 152));
        if ( *(_QWORD *)(v33 + 168) )
          v43 = *(_QWORD *)(*((_QWORD *)this[2] + 1) + 56LL);
        else
          v43 = 0;
        *(_QWORD *)(v25 + 168) = v43;
        *(_QWORD *)(v25 + 192) = 0;
        *(_QWORD *)(v25 + 208) = 0;
        *(_DWORD *)(v25 + 216) = 0;
        *(_QWORD *)(v25 + 248) = 0;
        *(_QWORD *)(v25 + 256) = 0;
        VMX_RECORD::Touch(v34, this[6]);
        LOBYTE(v44) = 1;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, (__int64)this[6] + 8, v44);
      }
      ++*(_DWORD *)(v25 + 160);
      v17 = VMX_CONFIG::CreateRecord(this[2], &v72);
      if ( v17 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v23 = 201;
          goto LABEL_30;
        }
      }
      else
      {
        v45 = (_QWORD *)VMX_ALLOCATED_OBJECT::operator new(176, 256, 1767009622);
        v47 = v45;
        if ( v45 )
        {
          v48 = v72;
          *v45 = &VMX_PLEX_INFO::`vftable';
          v49 = v75;
          LOBYTE(v46) = 1;
          *((_WORD *)v48 + 16) = 2;
          *((_QWORD *)v48 + 6) = v47;
          *((_QWORD *)v48 + 7) = v49;
          *((_WORD *)v48 + 32) |= 1u;
          v17 = (*(__int64 (__fastcall **)(_QWORD *, struct VMX_RECORD *, __int64))(*v47 + 8LL))(v47, v73, v46);
          if ( v17 < 0 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v23 = 203;
              goto LABEL_30;
            }
          }
          else
          {
            v51 = v72;
            v47[6] = v72;
            *((_BYTE *)v47 + 64) = 1;
            VMX_CONFIG::NextSubdiskName(this[2], (char *)(v25 + 16), (char *)v47 + 16, v50);
            if ( *((_QWORD *)v73 + 12) )
              v52 = *(_QWORD *)(*((_QWORD *)this[2] + 1) + 56LL);
            else
              v52 = 0;
            v47[12] = v52;
            v47[13] = *((_QWORD *)v34 + 3);
            v47[14] = 0;
            VMX_RECORD::Touch(v51, this[6]);
            LOBYTE(v53) = 1;
            (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v47 + 40LL))(v47, (__int64)this[6] + 8, v53);
            for ( m = (struct VMX_RECORD *)*((_QWORD *)v73 + 19); ; m = (struct VMX_RECORD *)*((_QWORD *)v71 + 22) )
            {
              v75 = m;
              if ( !m )
              {
                v33 = v79;
                goto LABEL_101;
              }
              v55 = (VMX_RECORD *)*((_QWORD *)m + (*((_WORD *)m + 32) & 1LL) + 5);
              v56 = this[2];
              v71 = v55;
              v78 = VMX_CONFIG::FindDiskById(
                      v56,
                      (struct _GUID *)(*(_QWORD *)(*((_QWORD *)v55 + 19)
                                                 + 8 * (*(_WORD *)(*((_QWORD *)v55 + 19) + 64LL) & 1LL)
                                                 + 40)
                                     + 72LL));
              v77 = *((_QWORD *)v78 + (*((_WORD *)v78 + 32) & 1LL) + 5);
              v17 = VMX_CONFIG::CreateRecord(v57, &v76);
              if ( v17 < 0 )
                break;
              v58 = (_QWORD *)VMX_ALLOCATED_OBJECT::operator new(184, 256, 1767009622);
              v60 = v58;
              if ( !v58 )
              {
                v24 = 3221225626LL;
                v17 = -1073741670;
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                {
                  v23 = 205;
                  goto LABEL_31;
                }
                return (unsigned int)v17;
              }
              v61 = v76;
              *v58 = &VMX_SUBDISK_INFO::`vftable';
              v62 = v75;
              LOBYTE(v59) = 1;
              *((_WORD *)v61 + 16) = 3;
              *((_QWORD *)v61 + 6) = v60;
              *((_QWORD *)v61 + 7) = v62;
              *((_WORD *)v61 + 32) |= 1u;
              v17 = (*(__int64 (__fastcall **)(_QWORD *, VMX_RECORD *, __int64))(*v60 + 8LL))(v60, v71, v59);
              if ( v17 < 0 )
              {
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                {
                  v23 = 206;
                  goto LABEL_30;
                }
                return (unsigned int)v17;
              }
              v64 = v76;
              v65 = v77;
              v60[6] = v76;
              *((_BYTE *)v60 + 64) = 1;
              VMX_CONFIG::NextSubdiskName(this[2], (char *)(v65 + 16), (char *)v60 + 16, v63);
              v60[13] = *((_QWORD *)v72 + 3);
              v60[14] = *((_QWORD *)v78 + 3);
              if ( *((_QWORD *)v71 + 15) )
                v66 = *(_QWORD *)(*((_QWORD *)this[2] + 1) + 56LL);
              else
                v66 = 0;
              v60[15] = v66;
              *((_DWORD *)v60 + 33) = 0;
              v60[18] = 0;
              VMX_RECORD::Touch(v64, this[6]);
              LOBYTE(v67) = 1;
              (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v60 + 40LL))(v60, (__int64)this[6] + 8, v67);
            }
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v23 = 204;
              goto LABEL_30;
            }
          }
        }
        else
        {
          v24 = 3221225626LL;
          v17 = -1073741670;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v23 = 202;
            goto LABEL_31;
          }
        }
      }
      return (unsigned int)v17;
    }
    v72 = i;
    if ( *((_WORD *)i + 16) != 2 )
      continue;
    v27 = (__int64 *)((char *)i + 48);
    if ( (*((_BYTE *)i + 64) & 1) == 0 )
      v27 = (__int64 *)((char *)i + 40);
    v28 = *(_QWORD *)(*v27 + 136);
    v25 = *(_QWORD *)(v28 + 8 * (*(_WORD *)(v28 + 64) & 1LL) + 40);
    VMX_PACK::MergeAnalyzeTargetPlex(v6, i, v5, &v69, &v70, &v73);
    if ( !v70 || v73 && v69 >= v70 )
      continue;
    if ( *(_DWORD *)(v25 + 160) == 1 )
    {
      v17 = VMX_PACK::DeleteVolumeTransaction((VMX_PACK *)this, (struct VMX_RECORD *)v28);
      if ( v17 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v23 = 193;
          goto LABEL_30;
        }
        return (unsigned int)v17;
      }
      continue;
    }
    v17 = VMX_RECORD::PreTouch((VMX_RECORD *)v28);
    if ( v17 < 0 )
      break;
    v17 = VMX_PACK::DeletePlex((VMX_PACK *)this, i, 0);
    if ( v17 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v23 = 195;
        goto LABEL_30;
      }
      return (unsigned int)v17;
    }
    VMX_RECORD::Touch((VMX_RECORD *)v28, this[6]);
    v25 = *(_QWORD *)(v28 + 48);
    if ( *(_DWORD *)(v25 + 160) == 1 )
    {
      v17 = VMX_PACK::CleanMirrorStuff((VMX_PACK *)this, (struct VMX_RECORD *)v28);
      if ( v17 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v23 = 196;
          goto LABEL_30;
        }
        return (unsigned int)v17;
      }
    }
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v23 = 194;
    goto LABEL_30;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140052028  mov     [rsp-8+arg_10], rbx
0x14005202d  push    rbp
0x14005202e  push    rsi
0x14005202f  push    rdi
0x140052030  push    r12
0x140052032  push    r13
0x140052034  push    r14
0x140052036  push    r15
0x140052038  lea     rbp, [rsp-27h]
0x14005203d  sub     rsp, 0A0h
0x140052044  mov     rax, cs:__security_cookie
0x14005204b  xor     rax, rsp
0x14005204e  mov     [rbp+57h+var_40], rax
0x140052052  mov     rsi, rcx
0x140052055  mov     [rbp+57h+var_88], 0
0x14005205d  mov     rcx, [rdx+38h]; this
0x140052061  xorps   xmm0, xmm0
0x140052064  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140052068  mov     [rbp+57h+var_9C], 0
0x14005206f  mov     [rbp+57h+var_70], 0
0x140052077  mov     rbx, [rcx+10h]
0x14005207b  mov     [rbp+57h+var_90], 0
0x140052083  mov     [rbp+57h+var_A0], 0
0x14005208a  call    ?MarkClosure@VMX_PACK@@QEAAXPEAVVMX_CHANGE_IDENTITY_TRANSACTION@@@Z; VMX_PACK::MarkClosure(VMX_CHANGE_IDENTITY_TRANSACTION *)
0x14005208f  lea     rcx, [rbx+10h]; this
0x140052093  mov     edi, 1
0x140052098  mov     r14, [rcx]
0x14005209b  mov     edx, 400h
0x1400520a0  mov     [rbp+57h+var_80], rcx
0x1400520a4  lea     r12d, [rdi+3]
0x1400520a8  cmp     r14, rcx
0x1400520ab  jz      loc_1400522A1
0x1400520b1  cmp     [r14+20h], r12w
0x1400520b6  jnz     loc_1400521D5
0x1400520bc  movzx   eax, word ptr [r14+40h]
0x1400520c1  test    dx, ax
0x1400520c4  jz      loc_1400521D5
0x1400520ca  test    dil, al
0x1400520cd  lea     rax, [r14+30h]
0x1400520d1  jnz     short loc_1400520D7
0x1400520d3  lea     rax, [r14+28h]
0x1400520d7  mov     r13, [rax]
0x1400520da  mov     r11, [rsi+10h]
0x1400520de  mov     rcx, r11; this
0x1400520e1  lea     rdx, [r13+48h]; struct _GUID *
0x1400520e5  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x1400520ea  mov     [rbp+57h+var_98], rax
0x1400520ee  mov     rbx, rax
0x1400520f1  test    rax, rax
0x1400520f4  jz      short loc_14005211B
0x1400520f6  cmp     qword ptr [r13+80h], 0
0x1400520fe  mov     edx, 400h
0x140052103  movzx   eax, word ptr [rax+40h]
0x140052107  jz      short loc_14005210E
0x140052109  or      ax, dx
0x14005210c  jmp     short loc_140052112
0x14005210e  or      ax, 200h
0x140052112  mov     [rbx+40h], ax
0x140052116  jmp     loc_1400521CD
0x14005211b  lea     rdx, [rbp+57h+var_98]; struct VMX_RECORD **
0x14005211f  mov     rcx, r11; this
0x140052122  call    ?CreateRecord@VMX_CONFIG@@QEAAJPEAPEAVVMX_RECORD@@@Z; VMX_CONFIG::CreateRecord(VMX_RECORD * *)
0x140052127  mov     edi, eax
0x140052129  test    eax, eax
0x14005212b  js      loc_140052254
0x140052131  mov     edx, 100h; unsigned __int64
0x140052136  mov     r8d, 69526D56h; unsigned int
0x14005213c  lea     ecx, [rdx-78h]; unsigned __int64
0x14005213f  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140052144  mov     r15, rax
0x140052147  test    rax, rax
0x14005214a  jz      loc_140052214
0x140052150  mov     rbx, [rbp+57h+var_98]
0x140052154  lea     rax, ??_7VMX_DISK_INFO@@6B@; const VMX_DISK_INFO::`vftable'
0x14005215b  mov     [r15], rax
0x14005215e  mov     edx, 1
0x140052163  mov     r8b, dl
0x140052166  mov     [rbx+20h], r12w
0x14005216b  mov     [rbx+30h], r15
0x14005216f  or      [rbx+40h], dx
0x140052173  mov     rdx, r13
0x140052176  mov     rcx, [r15]
0x140052179  mov     rax, [rcx+8]
0x14005217d  mov     rcx, r15
0x140052180  call    _guard_dispatch_icall
0x140052185  mov     edi, eax
0x140052187  test    eax, eax
0x140052189  js      short loc_1400521DD
0x14005218b  mov     [r15+30h], rbx
0x14005218f  lea     rdx, [r15+10h]; pszDest
0x140052193  mov     edi, 1
0x140052198  mov     [r15+40h], dil
0x14005219c  mov     rcx, [rsi+10h]; this
0x1400521a0  call    ?NextDiskName@VMX_CONFIG@@QEAAXPEADK@Z; VMX_CONFIG::NextDiskName(char *,ulong)
0x1400521a5  or      dword ptr [r15+60h], 20h
0x1400521aa  mov     rcx, rbx; this
0x1400521ad  mov     qword ptr [r15+80h], 0
0x1400521b8  mov     rdx, [rsi+30h]; struct VMX_TRANSACTION *
0x1400521bc  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x1400521c1  mov     rcx, [rsi+30h]
0x1400521c5  mov     edx, 400h
0x1400521ca  add     [rcx+14h], edi
0x1400521cd  mov     rcx, [rbp+57h+var_80]
0x1400521d1  mov     [rbx+38h], r14
0x1400521d5  mov     r14, [r14]
0x1400521d8  jmp     loc_1400520A8
0x1400521dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400521e4  lea     rax, WPP_GLOBAL_Control
0x1400521eb  cmp     rcx, rax
0x1400521ee  jz      loc_140052BC1
0x1400521f4  mov     eax, [rcx+2Ch]
0x1400521f7  mov     ebx, 2
0x1400521fc  test    bl, al
0x1400521fe  jz      loc_140052BC1
0x140052204  cmp     [rcx+29h], bl
0x140052207  jb      loc_140052BC1
0x14005220d  mov     edx, 0C0h
0x140052212  jmp     short loc_140052289
0x140052214  mov     r9d, 0C000009Ah
0x14005221a  mov     edi, r9d
0x14005221d  mov     rcx, cs:WPP_GLOBAL_Control
0x140052224  lea     rax, WPP_GLOBAL_Control
0x14005222b  cmp     rcx, rax
0x14005222e  jz      loc_140052BC1
0x140052234  mov     eax, [rcx+2Ch]
0x140052237  mov     ebx, 2
0x14005223c  test    bl, al
0x14005223e  jz      loc_140052BC1
0x140052244  cmp     [rcx+29h], bl
0x140052247  jb      loc_140052BC1
0x14005224d  mov     edx, 0BFh
0x140052252  jmp     short loc_14005228C
0x140052254  mov     rcx, cs:WPP_GLOBAL_Control
0x14005225b  lea     rax, WPP_GLOBAL_Control
0x140052262  cmp     rcx, rax
0x140052265  jz      loc_140052BC1
0x14005226b  mov     eax, [rcx+2Ch]
0x14005226e  mov     ebx, 2
0x140052273  test    bl, al
0x140052275  jz      loc_140052BC1
0x14005227b  cmp     [rcx+29h], bl
0x14005227e  jb      loc_140052BC1
0x140052284  mov     edx, 0BEh
0x140052289  mov     r9d, edi
0x14005228c  mov     rcx, [rcx+18h]
0x140052290  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140052297  call    WPP_SF_d
0x14005229c  jmp     loc_140052BC1
0x1400522a1  mov     rax, [rsi+10h]
0x1400522a5  xor     r14d, r14d
0x1400522a8  mov     r15, [rax+10h]
0x1400522ac  lea     ebx, [r14+2]
0x1400522b0  mov     rax, [rsi+10h]
0x1400522b4  add     rax, 10h
0x1400522b8  cmp     r15, rax
0x1400522bb  jz      loc_140052482
0x1400522c1  mov     [rbp+57h+var_90], r15
0x1400522c5  cmp     [r15+20h], bx
0x1400522ca  jnz     loc_1400523DB
0x1400522d0  lea     rax, [r15+30h]
0x1400522d4  test    [r15+40h], dil
0x1400522d8  jnz     short loc_1400522DE
0x1400522da  lea     rax, [r15+28h]
0x1400522de  mov     rax, [rax]
0x1400522e1  lea     r9, [rbp+57h+var_A0]; unsigned int *
0x1400522e5  mov     rdx, r15; struct VMX_RECORD *
0x1400522e8  mov     r13, [rax+88h]
0x1400522ef  movzx   eax, word ptr [r13+40h]
0x1400522f4  and     rax, rdi
0x1400522f7  mov     r14, [r13+rax*8+28h]
0x1400522fc  lea     rax, [rbp+57h+var_88]
0x140052300  mov     [rsp+0D0h+var_A8], rax; struct VMX_RECORD **
0x140052305  lea     rax, [rbp+57h+var_9C]
0x140052309  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x14005230e  call    ?MergeAnalyzeTargetPlex@VMX_PACK@@AEAAXPEAVVMX_RECORD@@PEAVVMX_CONFIG@@PEAK2PEAPEAV2@@Z; VMX_PACK::MergeAnalyzeTargetPlex(VMX_RECORD *,VMX_CONFIG *,ulong *,ulong *,VMX_RECORD * *)
0x140052313  mov     eax, [rbp+57h+var_9C]
0x140052316  test    eax, eax
0x140052318  jz      loc_1400523DB
0x14005231e  cmp     [rbp+57h+var_88], 0
0x140052323  jz      short loc_14005232E
0x140052325  cmp     [rbp+57h+var_A0], eax
0x140052328  jnb     loc_1400523DB
0x14005232e  cmp     [r14+0A0h], edi
0x140052335  jnz     short loc_140052381
0x140052337  mov     rdx, r13; struct VMX_RECORD *
0x14005233a  mov     rcx, rsi; this
0x14005233d  call    ?DeleteVolumeTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::DeleteVolumeTransaction(VMX_RECORD *)
0x140052342  mov     edi, eax
0x140052344  test    eax, eax
0x140052346  jns     loc_1400523D6
0x14005234c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052353  lea     rax, WPP_GLOBAL_Control
0x14005235a  cmp     rcx, rax
0x14005235d  jz      loc_140052BC1
0x140052363  mov     eax, [rcx+2Ch]
0x140052366  test    bl, al
0x140052368  jz      loc_140052BC1
0x14005236e  cmp     [rcx+29h], bl
0x140052371  jb      loc_140052BC1
0x140052377  mov     edx, 0C1h
0x14005237c  jmp     loc_140052289
0x140052381  mov     rcx, r13; this
0x140052384  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140052389  mov     edi, eax
0x14005238b  test    eax, eax
0x14005238d  js      loc_14005244D
0x140052393  xor     r8d, r8d; unsigned __int8
0x140052396  mov     rdx, r15; struct VMX_RECORD *
0x140052399  mov     rcx, rsi; this
0x14005239c  call    ?DeletePlex@VMX_PACK@@AEAAJPEAVVMX_RECORD@@E@Z; VMX_PACK::DeletePlex(VMX_RECORD *,uchar)
0x1400523a1  mov     edi, eax
0x1400523a3  test    eax, eax
0x1400523a5  js      short loc_140052418
0x1400523a7  mov     rdx, [rsi+30h]; struct VMX_TRANSACTION *
0x1400523ab  mov     rcx, r13; this
0x1400523ae  call    ?Touch@VMX_RECORD@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RECORD::Touch(VMX_TRANSACTION *)
0x1400523b3  mov     r14, [r13+30h]
0x1400523b7  mov     edi, 1
0x1400523bc  cmp     [r14+0A0h], edi
0x1400523c3  jnz     short loc_1400523DB
0x1400523c5  mov     rdx, r13; struct VMX_RECORD *
0x1400523c8  mov     rcx, rsi; this
0x1400523cb  call    ?CleanMirrorStuff@VMX_PACK@@AEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::CleanMirrorStuff(VMX_RECORD *)
0x1400523d0  mov     edi, eax
0x1400523d2  test    eax, eax
0x1400523d4  js      short loc_1400523E3
0x1400523d6  mov     edi, 1
0x1400523db  mov     r15, [r15]
0x1400523de  jmp     loc_1400522B0
0x1400523e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400523ea  lea     rax, WPP_GLOBAL_Control
0x1400523f1  cmp     rcx, rax
0x1400523f4  jz      loc_140052BC1
0x1400523fa  mov     eax, [rcx+2Ch]
0x1400523fd  test    bl, al
0x1400523ff  jz      loc_140052BC1
0x140052405  cmp     [rcx+29h], bl
0x140052408  jb      loc_140052BC1
0x14005240e  mov     edx, 0C4h
0x140052413  jmp     loc_140052289
0x140052418  mov     rcx, cs:WPP_GLOBAL_Control
0x14005241f  lea     rax, WPP_GLOBAL_Control
0x140052426  cmp     rcx, rax
0x140052429  jz      loc_140052BC1
0x14005242f  mov     eax, [rcx+2Ch]
0x140052432  test    bl, al
0x140052434  jz      loc_140052BC1
0x14005243a  cmp     [rcx+29h], bl
0x14005243d  jb      loc_140052BC1
0x140052443  mov     edx, 0C3h
0x140052448  jmp     loc_140052289
0x14005244d  mov     rcx, cs:WPP_GLOBAL_Control
0x140052454  lea     rax, WPP_GLOBAL_Control
0x14005245b  cmp     rcx, rax
0x14005245e  jz      loc_140052BC1
0x140052464  mov     eax, [rcx+2Ch]
0x140052467  test    bl, al
0x140052469  jz      loc_140052BC1
0x14005246f  cmp     [rcx+29h], bl
0x140052472  jb      loc_140052BC1
0x140052478  mov     edx, 0C2h
0x14005247d  jmp     loc_140052289
0x140052482  mov     rcx, [rbp+57h+var_80]
0x140052486  mov     edx, 400h
0x14005248b  mov     r12, [rcx]
0x14005248e  cmp     r12, rcx
0x140052491  jz      loc_140052BB7
0x140052497  cmp     [r12+20h], di
0x14005249d  jnz     loc_140052970
0x1400524a3  movzx   eax, word ptr [r12+40h]
0x1400524a9  test    dx, ax
0x1400524ac  jz      loc_140052970
0x1400524b2  test    dil, al
0x1400524b5  lea     rax, [r12+30h]
0x1400524ba  jnz     short loc_1400524C1
0x1400524bc  lea     rax, [r12+28h]
0x1400524c1  mov     r15, [rax]
0x1400524c4  xor     r13d, r13d
0x1400524c7  mov     [rbp+57h+var_58], r15
0x1400524cb  mov     rcx, [r15+108h]
0x1400524d2  mov     rax, rcx
0x1400524d5  mov     [rbp+57h+var_78], rcx
0x1400524d9  mov     rdx, rcx
0x1400524dc  test    rax, rax
0x1400524df  jz      loc_140052932
0x1400524e5  movzx   eax, word ptr [rcx+40h]
0x1400524e9  lea     rdx, [rbp+57h+var_90]
0x1400524ed  and     rax, rdi
0x1400524f0  mov     [rsp+0D0h+var_B0], rdx; struct VMX_RECORD **
0x1400524f5  mov     rdx, rcx; struct VMX_RECORD *
0x1400524f8  lea     r9, [rbp+57h+var_9C]; unsigned int *
0x1400524fc  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x140052500  mov     rax, [rcx+rax*8+28h]
0x140052505  mov     rcx, rsi; this
0x140052508  mov     [rbp+57h+var_88], rax
0x14005250c  call    ?MergeAnalyzeSourcePlex@VMX_PACK@@AEAAXPEAVVMX_RECORD@@PEAK1PEAPEAV2@@Z; VMX_PACK::MergeAnalyzeSourcePlex(VMX_RECORD *,ulong *,ulong *,VMX_RECORD * *)
0x140052511  mov     eax, [rbp+57h+var_A0]
0x140052514  test    eax, eax
0x140052516  jz      short loc_14005252C
0x140052518  cmp     [rbp+57h+var_90], 0
  ... truncated ...
```
