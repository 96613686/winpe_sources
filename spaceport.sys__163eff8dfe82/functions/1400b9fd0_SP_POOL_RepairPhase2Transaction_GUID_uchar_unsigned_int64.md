# SP_POOL::RepairPhase2Transaction(_GUID *,uchar *,unsigned __int64 *)

- ea: `0x1400b9fd0`
- end: `0x1400ba6ef`
- name: `?RepairPhase2Transaction@SP_POOL@@QEAAJPEAU_GUID@@PEAEPEA_K@Z`
- size: `1823`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this, struct _GUID *, unsigned __int8 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x14009e19c`

## callees

- `0x14000b3e0`
- `0x14000ba20`
- `0x14000c6b0`
- `0x14000d2b0`
- `0x14000d460`
- `0x14000fb70`
- `0x1400187f0`
- `0x140018810`
- `0x1400189c0`
- `0x140018c30`
- `0x140018f10`
- `0x140054904`
- `0x14005f764`
- `0x140068110`
- `0x140068150`
- `0x1400adb5c`
- `0x1400b9fd0`
- `0x1400ba700`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400ba6b2`
- `ntoskrnl!EtwWriteTransfer` at `0x1400ba6b2`

## pseudocode

```c
__int64 __fastcall SP_POOL::RepairPhase2Transaction(
        SDB_POOL_CONFIG **this,
        struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned __int64 *a4)
{
  SDB_POOL_CONFIG *v4; // rcx
  SDB_RECORD *SpaceById; // rax
  SDB_RECORD *v6; // rdi
  __int64 result; // rax
  int v8; // ebx
  __int64 v9; // rax
  void *v10; // rdx
  void *v11; // rdx
  unsigned int v12; // esi
  unsigned __int64 *v13; // r14
  SDB_SPACE *Object; // r15
  int v15; // r13d
  __int64 *v16; // rcx
  __int64 v17; // rdx
  SDB_RECORD *v18; // rdi
  struct SDB_OBJECT *v19; // rax
  __int64 v20; // rdx
  struct SDB_OBJECT *v21; // r15
  SDB_RECORD *v22; // rax
  SDB_RECORD *v23; // r12
  struct SDB_OBJECT *v24; // rax
  struct SDB_RECORD *v25; // rax
  SP_POOL *v26; // rsi
  __int64 v27; // r9
  int v28; // r14d
  int v29; // eax
  SDB_EXTENT *v30; // rsi
  struct _SP_PROVISIONING_INFO *v31; // rdi
  __int64 v32; // rdx
  SDB_RECORD *Extent; // rdi
  SDB_EXTENT *v34; // rax
  SDB_RECORD *i; // rdi
  struct SDB_OBJECT *v36; // rax
  __int64 v37; // rdx
  struct SDB_OBJECT *v38; // rsi
  __int64 v39; // r8
  unsigned __int64 v40; // rcx
  __int64 v41; // rdi
  SDB_RECORD *RecordByType; // rcx
  __int64 v43; // rcx
  SDB_SPACE *v44; // rdi
  unsigned int v45; // r13d
  unsigned int j; // r12d
  struct SDB_RECORD *k; // r15
  struct SDB_OBJECT *v48; // rax
  SDB_RECORD *Drive; // rax
  __int64 v50; // r8
  __int64 v51; // r9
  int v52; // r14d
  int v53; // eax
  SDB_EXTENT *v54; // rsi
  struct _SP_PROVISIONING_INFO *v55; // rdi
  int v56; // [rsp+30h] [rbp-D0h] BYREF
  SP_POOL *v57; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v58; // [rsp+40h] [rbp-C0h]
  SDB_SPACE *v59; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 *v63; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  char *v65; // [rsp+90h] [rbp-70h]
  int v66; // [rsp+98h] [rbp-68h]
  int v67; // [rsp+9Ch] [rbp-64h]
  __int64 *v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h]
  char *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  unsigned __int64 **v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  int *v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]

  v57 = (SP_POOL *)this;
  v4 = this[6];
  v63 = a4;
  v61 = (__int64)a3;
  v60 = 0;
  SpaceById = SDB_POOL_CONFIG::FindSpaceById(v4, a2);
  v6 = SpaceById;
  if ( !SpaceById )
    return 3224895558LL;
  if ( SDB_RECORD::IsPreTouched(SpaceById) )
  {
    v8 = 0;
LABEL_11:
    v12 = 0;
    v13 = 0;
    v58 = 0;
    v56 = 0;
    Object = SDB_RECORD::GetObject(v6);
    v59 = Object;
    v15 = 0;
    while ( 1 )
    {
      v16 = (__int64 *)*((_QWORD *)Object + 49);
      v17 = *v16;
      LOBYTE(v17) = 5;
      *(_QWORD *)&EventDescriptor.Id = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v16 + 72))(v16, v17, 0);
      v18 = *(SDB_RECORD **)&EventDescriptor.Id;
      if ( *(_QWORD *)&EventDescriptor.Id )
        break;
LABEL_34:
      if ( ++v15 > v12 )
      {
        Extent = SDB_SPACE::GetExtent(Object, 0, &v60);
        if ( Extent )
        {
          while ( 1 )
          {
            v34 = SDB_RECORD::GetObject(Extent);
            if ( !SDB_EXTENT::SupportsSafeReallocation(v34) )
              break;
            Extent = SDB_SPACE::GetExtent(Object, Extent, &v60);
            if ( !Extent )
              goto LABEL_38;
          }
LABEL_73:
          if ( v8 >= 0 )
            *v63 += (unsigned __int64)v13;
LABEL_75:
          v26 = v57;
          goto LABEL_76;
        }
LABEL_38:
        v26 = v57;
        if ( *((_DWORD *)v57 + 18) == 1 )
        {
          v41 = *((_QWORD *)v57 + 6);
          LOBYTE(v32) = 2;
          RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(v41, v32, 0);
          if ( RecordByType )
          {
            while ( *((_DWORD *)SDB_RECORD::GetObject(RecordByType) + 17) != 3 )
            {
              LOBYTE(v32) = 2;
              RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(v41, v32, v43);
              if ( !RecordByType )
                goto LABEL_52;
            }
LABEL_40:
            LOBYTE(v32) = 2;
            for ( i = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)v57 + 6), v32, 0);
                  i;
                  i = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)v26 + 6), v37, i) )
            {
              v36 = SDB_RECORD::GetObject(i);
              v38 = v36;
              if ( *((_DWORD *)v36 + 17) == 5 || SpIsDriveConnected(v36) )
              {
                v26 = v57;
              }
              else
              {
                v40 = *((_QWORD *)v38 + 30);
                v26 = v57;
                if ( v40 <= MEMORY[0xFFFFF78000000008] )
                {
                  LOBYTE(v39) = 2;
                  v8 = SP_POOL::RetireDrive(v57, i, v39);
                  if ( v8 < 0 )
                    goto LABEL_76;
                }
              }
              LOBYTE(v37) = 2;
            }
          }
        }
        else if ( *((_DWORD *)v57 + 18) == 2 )
        {
          goto LABEL_40;
        }
LABEL_52:
        v44 = v59;
        v45 = 0;
        for ( j = 0; j <= v45; ++j )
        {
          for ( k = SDB_SPACE::GetExtent(v44, 0, &v60); k; k = SDB_SPACE::GetExtent(v44, k, &v60) )
          {
            v48 = SDB_RECORD::GetObject(k);
            if ( *((_DWORD *)v48 + 18) == -1 )
            {
              Drive = SDB_EXTENT::GetDrive(v48);
              if ( *((_DWORD *)SDB_RECORD::GetObject(Drive) + 17) == 5 )
              {
                LOBYTE(v51) = 1;
                v52 = 0;
                while ( 1 )
                {
                  LOBYTE(v50) = 6;
                  v53 = SDB_POOL_CONFIG::ReallocateExtent(*((_QWORD *)v26 + 6), k, v50, v51);
                  v8 = v53;
                  if ( v53 >= 0 )
                  {
                    v13 = (unsigned __int64 *)((char *)v58 + 1);
                    v58 = (unsigned __int64 *)((char *)v58 + 1);
                    goto LABEL_70;
                  }
                  if ( v53 == -1073741823 && !j )
                  {
                    v13 = v58;
                    v45 = 1;
                    v8 = 0;
                    goto LABEL_70;
                  }
                  v54 = SDB_RECORD::GetObject(k);
                  if ( *(_DWORD *)SDB_EXTENT::Resiliency(v54) == 3 )
                  {
                    v55 = SDB_EXTENT::Provisioning(v54);
                    if ( *((_DWORD *)SDB_EXTENT::Provisioning(v54) + 5) == *((_DWORD *)v55 + 7) )
                      break;
                  }
                  LOBYTE(v51) = 0;
                  if ( (unsigned int)++v52 >= 2 )
                    break;
                  v26 = v57;
                }
                v13 = v58;
                if ( v8 == -1073740703 )
                {
                  v8 = 0;
                  v26 = v57;
                  *(_BYTE *)v61 = 1;
                }
                else
                {
                  if ( v8 != -1073741823 )
                    goto LABEL_75;
                  v26 = v57;
                  v8 = 0;
                }
LABEL_70:
                v44 = v59;
              }
            }
          }
        }
        goto LABEL_73;
      }
    }
    while ( 1 )
    {
      v19 = SDB_RECORD::GetObject(v18);
      v21 = v19;
      if ( *((_BYTE *)v19 + 56) == 4 )
      {
        v22 = SDB_SPACE::FindExtent(v59, *((_QWORD *)v19 + 4), *((_DWORD *)v19 + 10), *((_DWORD *)v19 + 11));
        v23 = v22;
        if ( v22 )
        {
          v24 = SDB_RECORD::GetObject(v22);
          if ( *((_QWORD *)v21 + 6) == *((_QWORD *)v24 + 1) && *((_DWORD *)v24 + 18) == -1 )
            break;
        }
      }
LABEL_32:
      v12 = v56;
LABEL_33:
      Object = v59;
      LOBYTE(v20) = 5;
      *(_QWORD *)&EventDescriptor.Id = (*(__int64 (__fastcall **)(_QWORD, __int64, SDB_RECORD *))(**((_QWORD **)v59 + 49)
                                                                                                + 72LL))(
                                         *((_QWORD *)v59 + 49),
                                         v20,
                                         v18);
      v18 = *(SDB_RECORD **)&EventDescriptor.Id;
      if ( !*(_QWORD *)&EventDescriptor.Id )
        goto LABEL_34;
    }
    v25 = SDB_EXTENT::GetDrive(v24);
    v26 = v57;
    v8 = SP_POOL::RetireDrive(v57, v25, *((unsigned __int8 *)v21 + 57));
    if ( v8 >= 0 )
    {
      LOBYTE(v27) = 1;
      v28 = 0;
      while ( 1 )
      {
        v29 = SDB_POOL_CONFIG::ReallocateExtent(*((_QWORD *)v26 + 6), v23, *((unsigned __int8 *)v21 + 57), v27);
        v8 = v29;
        if ( v29 >= 0 )
        {
          v18 = *(SDB_RECORD **)&EventDescriptor.Id;
          v13 = (unsigned __int64 *)((char *)v58 + 1);
          v58 = (unsigned __int64 *)((char *)v58 + 1);
          goto LABEL_32;
        }
        if ( v29 == -1073741823 && !v15 )
        {
          v13 = v58;
          v12 = 1;
          v18 = *(SDB_RECORD **)&EventDescriptor.Id;
          v8 = 0;
          v56 = 1;
          goto LABEL_33;
        }
        v30 = SDB_RECORD::GetObject(v23);
        if ( *(_DWORD *)SDB_EXTENT::Resiliency(v30) == 3 )
        {
          v31 = SDB_EXTENT::Provisioning(v30);
          if ( *((_DWORD *)SDB_EXTENT::Provisioning(v30) + 5) == *((_DWORD *)v31 + 7) )
            break;
        }
        LOBYTE(v27) = 0;
        if ( (unsigned int)++v28 >= 2 )
          break;
        v26 = v57;
      }
      v13 = v58;
      if ( v8 == -1073740703 )
      {
        v8 = 0;
        v12 = v56;
        v18 = *(SDB_RECORD **)&EventDescriptor.Id;
        *(_BYTE *)v61 = 1;
        goto LABEL_33;
      }
      if ( v8 == -1073741823 )
      {
        v12 = v56;
        v8 = 0;
        v18 = *(SDB_RECORD **)&EventDescriptor.Id;
        goto LABEL_33;
      }
      goto LABEL_75;
    }
LABEL_76:
    if ( v13
      && (unsigned int)dword_14007F050 > 5
      && (qword_14007F060 & 0x400000000000LL) != 0
      && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
    {
      EventDescriptor.Keyword = 0x400000000000LL;
      v74 = &v56;
      v56 = v8;
      v72 = &v63;
      v63 = v13;
      v70 = (char *)v26 + 108;
      v61 = 0x1000000;
      v68 = &v61;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14007F058;
      v75 = 4;
      v73 = 8;
      v71 = 16;
      v69 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_14007F058;
      v65 = byte_140075A65;
      UserData.Reserved = 2;
      v66 = 98;
      v67 = 1;
      LODWORD(v57) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    return (unsigned int)v8;
  }
  result = SC_SPARSE::SetNextObject((SC_SPARSE *)(*((_QWORD *)v6 + 2) + 192LL), v6);
  v8 = result;
  if ( (int)result < 0 )
    return result;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 4) + 16LL))(*((_QWORD *)v6 + 4));
  *((_QWORD *)v6 + 5) = v9;
  if ( !v9 )
  {
    SC_SPARSE::SetLastObject((SC_SPARSE *)(*((_QWORD *)v6 + 2) + 192LL), v10);
    return 3221225626LL;
  }
  *((_WORD *)v6 + 15) |= 1u;
  if ( (*((_WORD *)v6 + 15) & 4) == 0 )
    goto LABEL_11;
  v8 = (*(__int64 (__fastcall **)(_QWORD, SDB_RECORD *))(**((_QWORD **)v6 + 2) + 48LL))(*((_QWORD *)v6 + 2), v6);
  if ( v8 >= 0 )
    goto LABEL_11;
  SC_SPARSE::SetLastObject((SC_SPARSE *)(*((_QWORD *)v6 + 2) + 192LL), v11);
  (*(void (__fastcall **)(_QWORD, SDB_RECORD *))(**((_QWORD **)v6 + 2) + 56LL))(*((_QWORD *)v6 + 2), v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b9fd0  push    rbp
0x1400b9fd2  push    rdi
0x1400b9fd3  lea     rbp, [rsp-28h]
0x1400b9fd8  sub     rsp, 128h
0x1400b9fdf  mov     rax, cs:__security_cookie
0x1400b9fe6  xor     rax, rsp
0x1400b9fe9  mov     [rbp+30h+var_50], rax
0x1400b9fed  mov     [rsp+130h+var_F8], rcx
0x1400b9ff2  mov     rcx, [rcx+30h]; this
0x1400b9ff6  mov     [rsp+130h+var_C0], r9
0x1400b9ffb  mov     [rsp+130h+var_D8], r8
0x1400ba000  mov     [rsp+130h+var_E0], 0
0x1400ba009  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x1400ba00e  mov     rdi, rax
0x1400ba011  test    rax, rax
0x1400ba014  jnz     short loc_1400BA020
0x1400ba016  mov     eax, 0C0380046h
0x1400ba01b  jmp     loc_1400BA6D8
0x1400ba020  mov     rcx, rdi; this
0x1400ba023  mov     [rsp+130h+var_10], rbx
0x1400ba02b  call    ?IsPreTouched@SDB_RECORD@@QEAAEXZ; SDB_RECORD::IsPreTouched(void)
0x1400ba030  test    al, al
0x1400ba032  jnz     loc_1400BA0D6
0x1400ba038  mov     rcx, [rdi+10h]
0x1400ba03c  mov     rdx, rdi; void *
0x1400ba03f  add     rcx, 0C0h; this
0x1400ba046  call    ?SetNextObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetNextObject(void *)
0x1400ba04b  mov     ebx, eax
0x1400ba04d  test    eax, eax
0x1400ba04f  js      loc_1400BA6D0
0x1400ba055  mov     rcx, [rdi+20h]
0x1400ba059  mov     rax, [rcx]
0x1400ba05c  mov     rax, [rax+10h]
0x1400ba060  call    _guard_dispatch_icall
0x1400ba065  mov     [rdi+28h], rax
0x1400ba069  test    rax, rax
0x1400ba06c  jnz     short loc_1400BA088
0x1400ba06e  mov     rcx, [rdi+10h]
0x1400ba072  add     rcx, 0C0h; this
0x1400ba079  call    ?SetLastObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetLastObject(void *)
0x1400ba07e  mov     eax, 0C000009Ah
0x1400ba083  jmp     loc_1400BA6D0
0x1400ba088  or      word ptr [rdi+1Eh], 1
0x1400ba08d  movzx   eax, word ptr [rdi+1Eh]
0x1400ba091  test    al, 4
0x1400ba093  jz      short loc_1400BA0D8
0x1400ba095  mov     rcx, [rdi+10h]
0x1400ba099  mov     rdx, rdi
0x1400ba09c  mov     rax, [rcx]
0x1400ba09f  mov     rax, [rax+30h]
0x1400ba0a3  call    _guard_dispatch_icall
0x1400ba0a8  mov     ebx, eax
0x1400ba0aa  test    eax, eax
0x1400ba0ac  jns     short loc_1400BA0D8
0x1400ba0ae  mov     rcx, [rdi+10h]
0x1400ba0b2  add     rcx, 0C0h; this
0x1400ba0b9  call    ?SetLastObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetLastObject(void *)
0x1400ba0be  mov     rcx, [rdi+10h]
0x1400ba0c2  mov     rdx, rdi
0x1400ba0c5  mov     rax, [rcx]
0x1400ba0c8  mov     rax, [rax+38h]
0x1400ba0cc  call    _guard_dispatch_icall
0x1400ba0d1  jmp     loc_1400BA6CE
0x1400ba0d6  xor     ebx, ebx
0x1400ba0d8  mov     [rsp+130h+var_18], rsi
0x1400ba0e0  mov     rcx, rdi; this
0x1400ba0e3  mov     [rsp+130h+var_20], r12
0x1400ba0eb  xor     esi, esi
0x1400ba0ed  mov     [rsp+130h+var_28], r13
0x1400ba0f5  mov     [rsp+130h+var_30], r14
0x1400ba0fd  xor     r14d, r14d
0x1400ba100  mov     [rsp+130h+var_F0], r14
0x1400ba105  mov     [rsp+130h+var_38], r15
0x1400ba10d  mov     [rsp+130h+var_100], esi
0x1400ba111  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba116  mov     r15, rax
0x1400ba119  mov     [rsp+130h+var_E8], rax
0x1400ba11e  xor     r13d, r13d
0x1400ba121  mov     rcx, [r15+188h]
0x1400ba128  xor     r8d, r8d
0x1400ba12b  mov     rdx, [rcx]
0x1400ba12e  mov     rax, [rdx+48h]
0x1400ba132  mov     dl, 5
0x1400ba134  call    _guard_dispatch_icall
0x1400ba139  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1400ba13e  mov     rdi, rax
0x1400ba141  test    rax, rax
0x1400ba144  jz      loc_1400BA2DC
0x1400ba14a  nop     word ptr [rax+rax+00h]
0x1400ba150  mov     rcx, rdi; this
0x1400ba153  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba158  mov     r15, rax
0x1400ba15b  cmp     byte ptr [rax+38h], 4
0x1400ba15f  jnz     loc_1400BA2AA
0x1400ba165  mov     r9d, [rax+2Ch]; unsigned int
0x1400ba169  mov     r8d, [rax+28h]; unsigned int
0x1400ba16d  mov     rdx, [rax+20h]; unsigned __int64
0x1400ba171  mov     rcx, [rsp+130h+var_E8]; this
0x1400ba176  call    ?FindExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE::FindExtent(unsigned __int64,ulong,ulong)
0x1400ba17b  mov     r12, rax
0x1400ba17e  test    rax, rax
0x1400ba181  jz      loc_1400BA2AA
0x1400ba187  mov     rcx, rax; this
0x1400ba18a  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba18f  mov     rcx, [rax+8]
0x1400ba193  cmp     [r15+30h], rcx
0x1400ba197  jnz     loc_1400BA2AA
0x1400ba19d  cmp     dword ptr [rax+48h], 0FFFFFFFFh
0x1400ba1a1  jnz     loc_1400BA2AA
0x1400ba1a7  mov     rcx, rax; this
0x1400ba1aa  call    ?GetDrive@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetDrive(void)
0x1400ba1af  mov     rsi, [rsp+130h+var_F8]
0x1400ba1b4  mov     rdx, rax
0x1400ba1b7  movzx   r8d, byte ptr [r15+39h]
0x1400ba1bc  mov     rcx, rsi
0x1400ba1bf  call    ?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z; SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)
0x1400ba1c4  mov     ebx, eax
0x1400ba1c6  test    eax, eax
0x1400ba1c8  js      loc_1400BA579
0x1400ba1ce  mov     r9b, 1
0x1400ba1d1  xor     r14d, r14d
0x1400ba1d4  movzx   r8d, byte ptr [r15+39h]
0x1400ba1d9  mov     rdx, r12
0x1400ba1dc  mov     rcx, [rsi+30h]
0x1400ba1e0  call    ?ReallocateExtent@SDB_POOL_CONFIG@@QEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@E@Z; SDB_POOL_CONFIG::ReallocateExtent(SDB_RECORD *,_SC_COLUMN_REASON,uchar)
0x1400ba1e5  mov     ebx, eax
0x1400ba1e7  test    eax, eax
0x1400ba1e9  jns     loc_1400BA298
0x1400ba1ef  cmp     eax, 0C0000001h
0x1400ba1f4  jnz     short loc_1400BA1FB
0x1400ba1f6  test    r13d, r13d
0x1400ba1f9  jz      short loc_1400BA241
0x1400ba1fb  mov     rcx, r12; this
0x1400ba1fe  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba203  mov     rcx, rax; this
0x1400ba206  mov     rsi, rax
0x1400ba209  call    ?Resiliency@SDB_EXTENT@@QEAAPEAVSP_RESILIENCY_INFO@@XZ; SDB_EXTENT::Resiliency(void)
0x1400ba20e  cmp     dword ptr [rax], 3
0x1400ba211  jnz     short loc_1400BA22E
0x1400ba213  mov     rcx, rsi; this
0x1400ba216  call    ?Provisioning@SDB_EXTENT@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SDB_EXTENT::Provisioning(void)
0x1400ba21b  mov     rcx, rsi; this
0x1400ba21e  mov     rdi, rax
0x1400ba221  call    ?Provisioning@SDB_EXTENT@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SDB_EXTENT::Provisioning(void)
0x1400ba226  mov     ecx, [rdi+1Ch]
0x1400ba229  cmp     [rax+14h], ecx
0x1400ba22c  jz      short loc_1400BA258
0x1400ba22e  xor     r9b, r9b
0x1400ba231  inc     r14d
0x1400ba234  cmp     r14d, 2
0x1400ba238  jnb     short loc_1400BA258
0x1400ba23a  mov     rsi, [rsp+130h+var_F8]
0x1400ba23f  jmp     short loc_1400BA1D4
0x1400ba241  mov     r14, [rsp+130h+var_F0]
0x1400ba246  mov     esi, 1
0x1400ba24b  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba250  xor     ebx, ebx
0x1400ba252  mov     [rsp+130h+var_100], esi
0x1400ba256  jmp     short loc_1400BA2AE
0x1400ba258  mov     r14, [rsp+130h+var_F0]
0x1400ba25d  cmp     ebx, 0C0000461h
0x1400ba263  jnz     short loc_1400BA27A
0x1400ba265  mov     rax, [rsp+130h+var_D8]
0x1400ba26a  xor     ebx, ebx
0x1400ba26c  mov     esi, [rsp+130h+var_100]
0x1400ba270  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba275  mov     byte ptr [rax], 1
0x1400ba278  jmp     short loc_1400BA2AE
0x1400ba27a  mov     [rsp+130h+var_F0], r14
0x1400ba27f  cmp     ebx, 0C0000001h
0x1400ba285  jnz     loc_1400BA574
0x1400ba28b  mov     esi, [rsp+130h+var_100]
0x1400ba28f  xor     ebx, ebx
0x1400ba291  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba296  jmp     short loc_1400BA2AE
0x1400ba298  mov     r14, [rsp+130h+var_F0]
0x1400ba29d  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba2a2  inc     r14
0x1400ba2a5  mov     [rsp+130h+var_F0], r14
0x1400ba2aa  mov     esi, [rsp+130h+var_100]
0x1400ba2ae  mov     r15, [rsp+130h+var_E8]
0x1400ba2b3  mov     r8, rdi
0x1400ba2b6  mov     dl, 5
0x1400ba2b8  mov     rcx, [r15+188h]
0x1400ba2bf  mov     rax, [rcx]
0x1400ba2c2  mov     rax, [rax+48h]
0x1400ba2c6  call    _guard_dispatch_icall
0x1400ba2cb  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1400ba2d0  mov     rdi, rax
0x1400ba2d3  test    rax, rax
0x1400ba2d6  jnz     loc_1400BA150
0x1400ba2dc  inc     r13d
0x1400ba2df  cmp     r13d, esi
0x1400ba2e2  jbe     loc_1400BA121
0x1400ba2e8  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba2ed  xor     edx, edx; struct SDB_RECORD *
0x1400ba2ef  mov     rcx, r15; this
0x1400ba2f2  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba2f7  mov     rdi, rax
0x1400ba2fa  test    rax, rax
0x1400ba2fd  jz      short loc_1400BA330
0x1400ba2ff  nop
0x1400ba300  mov     rcx, rdi; this
0x1400ba303  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba308  mov     rcx, rax; this
0x1400ba30b  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x1400ba310  test    al, al
0x1400ba312  jz      loc_1400BA568
0x1400ba318  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba31d  mov     rdx, rdi; struct SDB_RECORD *
0x1400ba320  mov     rcx, r15; this
0x1400ba323  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba328  mov     rdi, rax
0x1400ba32b  test    rax, rax
0x1400ba32e  jnz     short loc_1400BA300
0x1400ba330  mov     rsi, [rsp+130h+var_F8]
0x1400ba335  mov     ecx, [rsi+48h]
0x1400ba338  sub     ecx, 1
0x1400ba33b  jz      short loc_1400BA3B6
0x1400ba33d  cmp     ecx, 1
0x1400ba340  jnz     loc_1400BA415
0x1400ba346  mov     rcx, [rsi+30h]
0x1400ba34a  xor     r8d, r8d
0x1400ba34d  mov     dl, 2
0x1400ba34f  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba354  mov     rdi, rax
0x1400ba357  test    rax, rax
0x1400ba35a  jz      loc_1400BA415
0x1400ba360  mov     rcx, rdi; this
0x1400ba363  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba368  mov     rsi, rax
0x1400ba36b  cmp     dword ptr [rax+44h], 5
0x1400ba36f  jz      loc_1400BA3F6
0x1400ba375  mov     rcx, rax; struct SDB_DRIVE *
0x1400ba378  call    ?SpIsDriveConnected@@YAEPEAVSDB_DRIVE@@@Z; SpIsDriveConnected(SDB_DRIVE *)
0x1400ba37d  test    al, al
0x1400ba37f  jnz     short loc_1400BA3F6
0x1400ba381  mov     rcx, [rsi+0F0h]
0x1400ba388  mov     rax, ds:0FFFFF78000000008h
0x1400ba392  mov     rsi, [rsp+130h+var_F8]
0x1400ba397  cmp     rcx, rax
0x1400ba39a  ja      short loc_1400BA3FB
0x1400ba39c  mov     r8b, 2
0x1400ba39f  mov     rdx, rdi
0x1400ba3a2  mov     rcx, rsi
0x1400ba3a5  call    ?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z; SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)
0x1400ba3aa  mov     ebx, eax
0x1400ba3ac  test    eax, eax
0x1400ba3ae  js      loc_1400BA579
0x1400ba3b4  jmp     short loc_1400BA3FB
0x1400ba3b6  mov     rdi, [rsi+30h]
0x1400ba3ba  xor     r8d, r8d
0x1400ba3bd  mov     rcx, rdi
0x1400ba3c0  mov     dl, 2
0x1400ba3c2  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba3c7  mov     rcx, rax; this
0x1400ba3ca  test    rax, rax
0x1400ba3cd  jz      short loc_1400BA415
0x1400ba3cf  nop
0x1400ba3d0  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba3d5  cmp     dword ptr [rax+44h], 3
0x1400ba3d9  jz      loc_1400BA346
0x1400ba3df  mov     r8, rcx
0x1400ba3e2  mov     dl, 2
0x1400ba3e4  mov     rcx, rdi
0x1400ba3e7  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba3ec  mov     rcx, rax
0x1400ba3ef  test    rax, rax
0x1400ba3f2  jnz     short loc_1400BA3D0
0x1400ba3f4  jmp     short loc_1400BA415
0x1400ba3f6  mov     rsi, [rsp+130h+var_F8]
0x1400ba3fb  mov     rcx, [rsi+30h]
0x1400ba3ff  mov     r8, rdi
0x1400ba402  mov     dl, 2
0x1400ba404  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba409  mov     rdi, rax
0x1400ba40c  test    rax, rax
0x1400ba40f  jnz     loc_1400BA360
0x1400ba415  mov     rdi, [rsp+130h+var_E8]
0x1400ba41a  xor     r13d, r13d
0x1400ba41d  xor     r12d, r12d
0x1400ba420  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba425  xor     edx, edx; struct SDB_RECORD *
0x1400ba427  mov     rcx, rdi; this
0x1400ba42a  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba42f  mov     r15, rax
0x1400ba432  test    rax, rax
0x1400ba435  jz      loc_1400BA55C
0x1400ba43b  nop     dword ptr [rax+rax+00h]
0x1400ba440  mov     rcx, r15; this
0x1400ba443  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba448  cmp     dword ptr [rax+48h], 0FFFFFFFFh
0x1400ba44c  jnz     loc_1400BA540
0x1400ba452  mov     rcx, rax; this
0x1400ba455  call    ?GetDrive@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetDrive(void)
0x1400ba45a  mov     rcx, rax; this
0x1400ba45d  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba462  cmp     dword ptr [rax+44h], 5
0x1400ba466  jnz     loc_1400BA540
0x1400ba46c  mov     r9b, 1
  ... truncated ...
```
