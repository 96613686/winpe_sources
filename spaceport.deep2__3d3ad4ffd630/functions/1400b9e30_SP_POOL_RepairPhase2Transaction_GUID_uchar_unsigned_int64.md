# SP_POOL::RepairPhase2Transaction(_GUID *,uchar *,unsigned __int64 *)

- ea: `0x1400b9e30`
- end: `0x1400ba54f`
- name: `?RepairPhase2Transaction@SP_POOL@@QEAAJPEAU_GUID@@PEAEPEA_K@Z`
- size: `1823`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this, struct _GUID *, unsigned __int8 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x14009e17c`

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
- `0x140054808`
- `0x14005f664`
- `0x140067fc0`
- `0x140068000`
- `0x1400ad9bc`
- `0x1400b9e30`
- `0x1400ba560`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400ba512`
- `ntoskrnl!EtwWriteTransfer` at `0x1400ba512`

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
      v65 = byte_140075ADD;
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
0x1400b9e30  push    rbp
0x1400b9e32  push    rdi
0x1400b9e33  lea     rbp, [rsp-28h]
0x1400b9e38  sub     rsp, 128h
0x1400b9e3f  mov     rax, cs:__security_cookie
0x1400b9e46  xor     rax, rsp
0x1400b9e49  mov     [rbp+30h+var_50], rax
0x1400b9e4d  mov     [rsp+130h+var_F8], rcx
0x1400b9e52  mov     rcx, [rcx+30h]; this
0x1400b9e56  mov     [rsp+130h+var_C0], r9
0x1400b9e5b  mov     [rsp+130h+var_D8], r8
0x1400b9e60  mov     [rsp+130h+var_E0], 0
0x1400b9e69  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x1400b9e6e  mov     rdi, rax
0x1400b9e71  test    rax, rax
0x1400b9e74  jnz     short loc_1400B9E80
0x1400b9e76  mov     eax, 0C0380046h
0x1400b9e7b  jmp     loc_1400BA538
0x1400b9e80  mov     rcx, rdi; this
0x1400b9e83  mov     [rsp+130h+var_10], rbx
0x1400b9e8b  call    ?IsPreTouched@SDB_RECORD@@QEAAEXZ; SDB_RECORD::IsPreTouched(void)
0x1400b9e90  test    al, al
0x1400b9e92  jnz     loc_1400B9F36
0x1400b9e98  mov     rcx, [rdi+10h]
0x1400b9e9c  mov     rdx, rdi; void *
0x1400b9e9f  add     rcx, 0C0h; this
0x1400b9ea6  call    ?SetNextObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetNextObject(void *)
0x1400b9eab  mov     ebx, eax
0x1400b9ead  test    eax, eax
0x1400b9eaf  js      loc_1400BA530
0x1400b9eb5  mov     rcx, [rdi+20h]
0x1400b9eb9  mov     rax, [rcx]
0x1400b9ebc  mov     rax, [rax+10h]
0x1400b9ec0  call    _guard_dispatch_icall
0x1400b9ec5  mov     [rdi+28h], rax
0x1400b9ec9  test    rax, rax
0x1400b9ecc  jnz     short loc_1400B9EE8
0x1400b9ece  mov     rcx, [rdi+10h]
0x1400b9ed2  add     rcx, 0C0h; this
0x1400b9ed9  call    ?SetLastObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetLastObject(void *)
0x1400b9ede  mov     eax, 0C000009Ah
0x1400b9ee3  jmp     loc_1400BA530
0x1400b9ee8  or      word ptr [rdi+1Eh], 1
0x1400b9eed  movzx   eax, word ptr [rdi+1Eh]
0x1400b9ef1  test    al, 4
0x1400b9ef3  jz      short loc_1400B9F38
0x1400b9ef5  mov     rcx, [rdi+10h]
0x1400b9ef9  mov     rdx, rdi
0x1400b9efc  mov     rax, [rcx]
0x1400b9eff  mov     rax, [rax+30h]
0x1400b9f03  call    _guard_dispatch_icall
0x1400b9f08  mov     ebx, eax
0x1400b9f0a  test    eax, eax
0x1400b9f0c  jns     short loc_1400B9F38
0x1400b9f0e  mov     rcx, [rdi+10h]
0x1400b9f12  add     rcx, 0C0h; this
0x1400b9f19  call    ?SetLastObject@SC_SPARSE@@QEAAJPEAX@Z; SC_SPARSE::SetLastObject(void *)
0x1400b9f1e  mov     rcx, [rdi+10h]
0x1400b9f22  mov     rdx, rdi
0x1400b9f25  mov     rax, [rcx]
0x1400b9f28  mov     rax, [rax+38h]
0x1400b9f2c  call    _guard_dispatch_icall
0x1400b9f31  jmp     loc_1400BA52E
0x1400b9f36  xor     ebx, ebx
0x1400b9f38  mov     [rsp+130h+var_18], rsi
0x1400b9f40  mov     rcx, rdi; this
0x1400b9f43  mov     [rsp+130h+var_20], r12
0x1400b9f4b  xor     esi, esi
0x1400b9f4d  mov     [rsp+130h+var_28], r13
0x1400b9f55  mov     [rsp+130h+var_30], r14
0x1400b9f5d  xor     r14d, r14d
0x1400b9f60  mov     [rsp+130h+var_F0], r14
0x1400b9f65  mov     [rsp+130h+var_38], r15
0x1400b9f6d  mov     [rsp+130h+var_100], esi
0x1400b9f71  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b9f76  mov     r15, rax
0x1400b9f79  mov     [rsp+130h+var_E8], rax
0x1400b9f7e  xor     r13d, r13d
0x1400b9f81  mov     rcx, [r15+188h]
0x1400b9f88  xor     r8d, r8d
0x1400b9f8b  mov     rdx, [rcx]
0x1400b9f8e  mov     rax, [rdx+48h]
0x1400b9f92  mov     dl, 5
0x1400b9f94  call    _guard_dispatch_icall
0x1400b9f99  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1400b9f9e  mov     rdi, rax
0x1400b9fa1  test    rax, rax
0x1400b9fa4  jz      loc_1400BA13C
0x1400b9faa  nop     word ptr [rax+rax+00h]
0x1400b9fb0  mov     rcx, rdi; this
0x1400b9fb3  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b9fb8  mov     r15, rax
0x1400b9fbb  cmp     byte ptr [rax+38h], 4
0x1400b9fbf  jnz     loc_1400BA10A
0x1400b9fc5  mov     r9d, [rax+2Ch]; unsigned int
0x1400b9fc9  mov     r8d, [rax+28h]; unsigned int
0x1400b9fcd  mov     rdx, [rax+20h]; unsigned __int64
0x1400b9fd1  mov     rcx, [rsp+130h+var_E8]; this
0x1400b9fd6  call    ?FindExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE::FindExtent(unsigned __int64,ulong,ulong)
0x1400b9fdb  mov     r12, rax
0x1400b9fde  test    rax, rax
0x1400b9fe1  jz      loc_1400BA10A
0x1400b9fe7  mov     rcx, rax; this
0x1400b9fea  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b9fef  mov     rcx, [rax+8]
0x1400b9ff3  cmp     [r15+30h], rcx
0x1400b9ff7  jnz     loc_1400BA10A
0x1400b9ffd  cmp     dword ptr [rax+48h], 0FFFFFFFFh
0x1400ba001  jnz     loc_1400BA10A
0x1400ba007  mov     rcx, rax; this
0x1400ba00a  call    ?GetDrive@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetDrive(void)
0x1400ba00f  mov     rsi, [rsp+130h+var_F8]
0x1400ba014  mov     rdx, rax
0x1400ba017  movzx   r8d, byte ptr [r15+39h]
0x1400ba01c  mov     rcx, rsi
0x1400ba01f  call    ?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z; SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)
0x1400ba024  mov     ebx, eax
0x1400ba026  test    eax, eax
0x1400ba028  js      loc_1400BA3D9
0x1400ba02e  mov     r9b, 1
0x1400ba031  xor     r14d, r14d
0x1400ba034  movzx   r8d, byte ptr [r15+39h]
0x1400ba039  mov     rdx, r12
0x1400ba03c  mov     rcx, [rsi+30h]
0x1400ba040  call    ?ReallocateExtent@SDB_POOL_CONFIG@@QEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@E@Z; SDB_POOL_CONFIG::ReallocateExtent(SDB_RECORD *,_SC_COLUMN_REASON,uchar)
0x1400ba045  mov     ebx, eax
0x1400ba047  test    eax, eax
0x1400ba049  jns     loc_1400BA0F8
0x1400ba04f  cmp     eax, 0C0000001h
0x1400ba054  jnz     short loc_1400BA05B
0x1400ba056  test    r13d, r13d
0x1400ba059  jz      short loc_1400BA0A1
0x1400ba05b  mov     rcx, r12; this
0x1400ba05e  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba063  mov     rcx, rax; this
0x1400ba066  mov     rsi, rax
0x1400ba069  call    ?Resiliency@SDB_EXTENT@@QEAAPEAVSP_RESILIENCY_INFO@@XZ; SDB_EXTENT::Resiliency(void)
0x1400ba06e  cmp     dword ptr [rax], 3
0x1400ba071  jnz     short loc_1400BA08E
0x1400ba073  mov     rcx, rsi; this
0x1400ba076  call    ?Provisioning@SDB_EXTENT@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SDB_EXTENT::Provisioning(void)
0x1400ba07b  mov     rcx, rsi; this
0x1400ba07e  mov     rdi, rax
0x1400ba081  call    ?Provisioning@SDB_EXTENT@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SDB_EXTENT::Provisioning(void)
0x1400ba086  mov     ecx, [rdi+1Ch]
0x1400ba089  cmp     [rax+14h], ecx
0x1400ba08c  jz      short loc_1400BA0B8
0x1400ba08e  xor     r9b, r9b
0x1400ba091  inc     r14d
0x1400ba094  cmp     r14d, 2
0x1400ba098  jnb     short loc_1400BA0B8
0x1400ba09a  mov     rsi, [rsp+130h+var_F8]
0x1400ba09f  jmp     short loc_1400BA034
0x1400ba0a1  mov     r14, [rsp+130h+var_F0]
0x1400ba0a6  mov     esi, 1
0x1400ba0ab  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba0b0  xor     ebx, ebx
0x1400ba0b2  mov     [rsp+130h+var_100], esi
0x1400ba0b6  jmp     short loc_1400BA10E
0x1400ba0b8  mov     r14, [rsp+130h+var_F0]
0x1400ba0bd  cmp     ebx, 0C0000461h
0x1400ba0c3  jnz     short loc_1400BA0DA
0x1400ba0c5  mov     rax, [rsp+130h+var_D8]
0x1400ba0ca  xor     ebx, ebx
0x1400ba0cc  mov     esi, [rsp+130h+var_100]
0x1400ba0d0  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba0d5  mov     byte ptr [rax], 1
0x1400ba0d8  jmp     short loc_1400BA10E
0x1400ba0da  mov     [rsp+130h+var_F0], r14
0x1400ba0df  cmp     ebx, 0C0000001h
0x1400ba0e5  jnz     loc_1400BA3D4
0x1400ba0eb  mov     esi, [rsp+130h+var_100]
0x1400ba0ef  xor     ebx, ebx
0x1400ba0f1  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba0f6  jmp     short loc_1400BA10E
0x1400ba0f8  mov     r14, [rsp+130h+var_F0]
0x1400ba0fd  mov     rdi, qword ptr [rsp+130h+EventDescriptor.Id]
0x1400ba102  inc     r14
0x1400ba105  mov     [rsp+130h+var_F0], r14
0x1400ba10a  mov     esi, [rsp+130h+var_100]
0x1400ba10e  mov     r15, [rsp+130h+var_E8]
0x1400ba113  mov     r8, rdi
0x1400ba116  mov     dl, 5
0x1400ba118  mov     rcx, [r15+188h]
0x1400ba11f  mov     rax, [rcx]
0x1400ba122  mov     rax, [rax+48h]
0x1400ba126  call    _guard_dispatch_icall
0x1400ba12b  mov     qword ptr [rsp+130h+EventDescriptor.Id], rax
0x1400ba130  mov     rdi, rax
0x1400ba133  test    rax, rax
0x1400ba136  jnz     loc_1400B9FB0
0x1400ba13c  inc     r13d
0x1400ba13f  cmp     r13d, esi
0x1400ba142  jbe     loc_1400B9F81
0x1400ba148  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba14d  xor     edx, edx; struct SDB_RECORD *
0x1400ba14f  mov     rcx, r15; this
0x1400ba152  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba157  mov     rdi, rax
0x1400ba15a  test    rax, rax
0x1400ba15d  jz      short loc_1400BA190
0x1400ba15f  nop
0x1400ba160  mov     rcx, rdi; this
0x1400ba163  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba168  mov     rcx, rax; this
0x1400ba16b  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x1400ba170  test    al, al
0x1400ba172  jz      loc_1400BA3C8
0x1400ba178  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba17d  mov     rdx, rdi; struct SDB_RECORD *
0x1400ba180  mov     rcx, r15; this
0x1400ba183  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba188  mov     rdi, rax
0x1400ba18b  test    rax, rax
0x1400ba18e  jnz     short loc_1400BA160
0x1400ba190  mov     rsi, [rsp+130h+var_F8]
0x1400ba195  mov     ecx, [rsi+48h]
0x1400ba198  sub     ecx, 1
0x1400ba19b  jz      short loc_1400BA216
0x1400ba19d  cmp     ecx, 1
0x1400ba1a0  jnz     loc_1400BA275
0x1400ba1a6  mov     rcx, [rsi+30h]
0x1400ba1aa  xor     r8d, r8d
0x1400ba1ad  mov     dl, 2
0x1400ba1af  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba1b4  mov     rdi, rax
0x1400ba1b7  test    rax, rax
0x1400ba1ba  jz      loc_1400BA275
0x1400ba1c0  mov     rcx, rdi; this
0x1400ba1c3  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba1c8  mov     rsi, rax
0x1400ba1cb  cmp     dword ptr [rax+44h], 5
0x1400ba1cf  jz      loc_1400BA256
0x1400ba1d5  mov     rcx, rax; struct SDB_DRIVE *
0x1400ba1d8  call    ?SpIsDriveConnected@@YAEPEAVSDB_DRIVE@@@Z; SpIsDriveConnected(SDB_DRIVE *)
0x1400ba1dd  test    al, al
0x1400ba1df  jnz     short loc_1400BA256
0x1400ba1e1  mov     rcx, [rsi+0F0h]
0x1400ba1e8  mov     rax, ds:0FFFFF78000000008h
0x1400ba1f2  mov     rsi, [rsp+130h+var_F8]
0x1400ba1f7  cmp     rcx, rax
0x1400ba1fa  ja      short loc_1400BA25B
0x1400ba1fc  mov     r8b, 2
0x1400ba1ff  mov     rdx, rdi
0x1400ba202  mov     rcx, rsi
0x1400ba205  call    ?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z; SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)
0x1400ba20a  mov     ebx, eax
0x1400ba20c  test    eax, eax
0x1400ba20e  js      loc_1400BA3D9
0x1400ba214  jmp     short loc_1400BA25B
0x1400ba216  mov     rdi, [rsi+30h]
0x1400ba21a  xor     r8d, r8d
0x1400ba21d  mov     rcx, rdi
0x1400ba220  mov     dl, 2
0x1400ba222  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba227  mov     rcx, rax; this
0x1400ba22a  test    rax, rax
0x1400ba22d  jz      short loc_1400BA275
0x1400ba22f  nop
0x1400ba230  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba235  cmp     dword ptr [rax+44h], 3
0x1400ba239  jz      loc_1400BA1A6
0x1400ba23f  mov     r8, rcx
0x1400ba242  mov     dl, 2
0x1400ba244  mov     rcx, rdi
0x1400ba247  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba24c  mov     rcx, rax
0x1400ba24f  test    rax, rax
0x1400ba252  jnz     short loc_1400BA230
0x1400ba254  jmp     short loc_1400BA275
0x1400ba256  mov     rsi, [rsp+130h+var_F8]
0x1400ba25b  mov     rcx, [rsi+30h]
0x1400ba25f  mov     r8, rdi
0x1400ba262  mov     dl, 2
0x1400ba264  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x1400ba269  mov     rdi, rax
0x1400ba26c  test    rax, rax
0x1400ba26f  jnz     loc_1400BA1C0
0x1400ba275  mov     rdi, [rsp+130h+var_E8]
0x1400ba27a  xor     r13d, r13d
0x1400ba27d  xor     r12d, r12d
0x1400ba280  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x1400ba285  xor     edx, edx; struct SDB_RECORD *
0x1400ba287  mov     rcx, rdi; this
0x1400ba28a  call    ?GetExtent@SDB_SPACE@@QEAAPEAVSDB_RECORD@@PEAV2@PEA_K@Z; SDB_SPACE::GetExtent(SDB_RECORD *,unsigned __int64 *)
0x1400ba28f  mov     r15, rax
0x1400ba292  test    rax, rax
0x1400ba295  jz      loc_1400BA3BC
0x1400ba29b  nop     dword ptr [rax+rax+00h]
0x1400ba2a0  mov     rcx, r15; this
0x1400ba2a3  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba2a8  cmp     dword ptr [rax+48h], 0FFFFFFFFh
0x1400ba2ac  jnz     loc_1400BA3A0
0x1400ba2b2  mov     rcx, rax; this
0x1400ba2b5  call    ?GetDrive@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetDrive(void)
0x1400ba2ba  mov     rcx, rax; this
0x1400ba2bd  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba2c2  cmp     dword ptr [rax+44h], 5
0x1400ba2c6  jnz     loc_1400BA3A0
0x1400ba2cc  mov     r9b, 1
  ... truncated ...
```
