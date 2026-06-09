# SDB_POOL_CONFIG::RebalancePhase1Transaction(unsigned __int64 *)

- ea: `0x140063d50`
- end: `0x140064318`
- name: `?RebalancePhase1Transaction@SDB_POOL_CONFIG@@QEAAJPEA_K@Z`
- size: `1480`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x140061410`

## callees

- `0x14000ba20`
- `0x14000c630`
- `0x14000c840`
- `0x14000cbd0`
- `0x14000d2b0`
- `0x14000e530`
- `0x140012ce0`
- `0x140018360`
- `0x1400268c0`
- `0x14005c96c`
- `0x14005f764`
- `0x140062670`
- `0x140062d40`
- `0x140063d50`
- `0x1400b3210`
- `0x1400b3544`
- `0x1400b6cb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400642d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400642d3`

## pseudocode

```c
__int64 __fastcall SDB_POOL_CONFIG::RebalancePhase1Transaction(SDB_POOL_CONFIG *this, unsigned __int64 *a2)
{
  unsigned int v2; // r12d
  SDB_RECORD *v4; // rcx
  _QWORD *v5; // r13
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rdi
  SDB_RECORD *v9; // rcx
  unsigned int v10; // r15d
  SDB_RECORD *i; // r8
  SDB_RECORD *RecordByType; // rax
  SDB_RECORD *v13; // rbx
  __int64 v14; // rbx
  unsigned __int64 v15; // rdi
  __int64 v16; // r15
  _QWORD *LastObject; // rax
  __int64 v18; // rdx
  __int64 v19; // r15
  unsigned __int64 v20; // rdi
  int v21; // esi
  __int64 v22; // rbx
  __int64 RecordByRecordId; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // r15
  struct SC_ARRAY *Array; // rax
  struct SC_ARRAY *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // rax
  struct SDB_RECORD *Space; // rax
  __int64 v34; // r15
  __int16 v35; // ax
  _QWORD *j; // r8
  __int64 v37; // rcx
  int v38; // eax
  struct _SP_PROVISIONING_INFO *v39; // rax
  struct SDB_RECORD *v40; // rax
  __int64 v41; // rax
  unsigned __int64 v42; // r8
  unsigned __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rax
  SDB_RECORD *v46; // rcx
  void *k; // r8
  void *v48; // rax
  void *v49; // rbx
  __int64 v51; // [rsp+30h] [rbp-89h]
  char *v52; // [rsp+38h] [rbp-81h]
  unsigned __int64 v53; // [rsp+40h] [rbp-79h]
  unsigned __int64 v54; // [rsp+48h] [rbp-71h]
  SDB_DRIVE *v55; // [rsp+58h] [rbp-61h]
  unsigned __int64 v56; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v57[3]; // [rsp+70h] [rbp-49h] BYREF
  __int16 v58; // [rsp+88h] [rbp-31h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-19h]
  unsigned int v60; // [rsp+ACh] [rbp-Dh]
  int v61; // [rsp+B8h] [rbp-1h]
  __int16 v62; // [rsp+BCh] [rbp+3h]
  int v63; // [rsp+120h] [rbp+67h]
  unsigned __int64 *v64; // [rsp+128h] [rbp+6Fh]
  int v65; // [rsp+130h] [rbp+77h]
  int v66; // [rsp+138h] [rbp+7Fh]

  v64 = a2;
  v2 = 0;
  v61 = -1;
  *a2 = 0;
  v57[0] = &SDB_EXTENT::`vftable';
  v4 = (SDB_RECORD *)*((_QWORD *)this + 34);
  v5 = 0;
  v57[1] = 0;
  v6 = 0;
  v57[2] = 0;
  v58 = 0;
  v7 = *((_WORD *)v4 + 15) & 1;
  v62 = 0;
  v63 = 0;
  v8 = *((_QWORD *)v4 + v7 + 4);
  v51 = v8;
  if ( (*(_BYTE *)(v8 + 64) & 0x10) == 0 )
  {
    v63 = SDB_RECORD::PreTouch(v4, 0);
    v6 = v63;
    if ( v63 < 0 )
      goto LABEL_61;
    v9 = (SDB_RECORD *)*((_QWORD *)this + 34);
    v8 = *((_QWORD *)v9 + (*((_WORD *)v9 + 15) & 1) + 4);
    v51 = v8;
    SDB_RECORD::Touch(v9);
    *(_WORD *)(v8 + 64) |= 0x10u;
    if ( !*(_QWORD *)(v8 + 296) )
      *(_QWORD *)(v8 + 296) = MEMORY[0xFFFFF78000000014];
  }
  v10 = 0;
  for ( i = 0; ; i = v13 )
  {
    LOBYTE(a2) = 2;
    RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(this, a2, i);
    v13 = RecordByType;
    if ( !RecordByType )
      break;
    v63 = SDB_RECORD::PreTouch(RecordByType, 0);
    v6 = v63;
    if ( v63 < 0 )
      goto LABEL_61;
    ++v10;
  }
  v5 = SC_ENV::Allocate(8LL * v10, 0x58587053u, 0, 0);
  if ( v5 )
  {
    v66 = 0;
    LOBYTE(a2) = 2;
    v53 = 0;
    v65 = 0;
    v14 = SDB_POOL_CONFIG::GetRecordByType(this, a2, 0);
    if ( v14 )
    {
      v15 = 0;
      do
      {
        v16 = *(_QWORD *)(v14 + 8LL * (*(_WORD *)(v14 + 30) & 1) + 32);
        LastObject = SC_SPARSE::FindLastObject(*(SC_SPARSE **)(v16 + 192), &v56);
        v5[v2] = LastObject;
        if ( LastObject )
        {
          ++v2;
          v18 = LastObject[(*((_WORD *)LastObject + 15) & 1) + 4];
          if ( *(_QWORD *)(v16 + 280) - *(_QWORD *)(v18 + 48) - *(_QWORD *)(v18 + 32) > v15 )
            v15 = *(_QWORD *)(v16 + 280) - *(_QWORD *)(v18 + 48) - *(_QWORD *)(v18 + 32);
        }
        LOBYTE(v18) = 2;
        v14 = SDB_POOL_CONFIG::GetRecordByType(this, v18, v14);
      }
      while ( v14 );
      v53 = v15;
      v8 = v51;
    }
    *(_QWORD *)(v8 + 272) = 0;
    *(_QWORD *)(v8 + 288) = 0;
LABEL_19:
    while ( v2 )
    {
      v19 = 0;
      v20 = -1;
      v21 = v65;
      do
      {
        LOBYTE(a2) = 2;
        v22 = *(_QWORD *)(v5[v19] + 8LL * (*(_WORD *)(v5[v19] + 30LL) & 1) + 32);
        RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(
                             *(_QWORD *)(*(_QWORD *)(v22 + 16) + 16LL),
                             (__int64)a2,
                             *(_DWORD *)(v22 + 60));
        v24 = *(_QWORD *)(RecordByRecordId + 8LL * (*(_WORD *)(RecordByRecordId + 30) & 1) + 32);
        a2 = (unsigned __int64 *)(*(_QWORD *)(v24 + 280) - *(_QWORD *)(v22 + 48));
        if ( (unsigned __int64)a2 >= v20 )
        {
          if ( a2 == (unsigned __int64 *)v20 && !SDB_POOL_CONFIG::GetRandom(this, ++v66) )
            v21 = v19;
        }
        else
        {
          v20 = *(_QWORD *)(v24 + 280) - *(_QWORD *)(v22 + 48);
          v66 = 1;
          v21 = v19;
        }
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < v2 );
      v65 = v21;
      v6 = v63;
      v54 = v20;
      v8 = v51;
      LOBYTE(a2) = 2;
      v52 = (char *)&v5[v65];
      v25 = *(_QWORD *)(*(_QWORD *)v52 + 8LL * (*(_WORD *)(*(_QWORD *)v52 + 30LL) & 1) + 32);
      v26 = SDB_POOL_CONFIG::FindRecordByRecordId(
              *(_QWORD *)(*(_QWORD *)(v25 + 16) + 16LL),
              (__int64)a2,
              *(_DWORD *)(v25 + 60));
      v27 = *(_QWORD *)(v26 + 8LL * (*(_WORD *)(v26 + 30) & 1) + 32);
      v55 = (SDB_DRIVE *)v27;
      v28 = *(_QWORD *)(v25 + 48) >> *(_DWORD *)(v27 + 220);
      if ( (__int64)(v28 - 1) < 0
        || (v56 = *(_QWORD *)(v27 + 192), Array = SC_SPARSE::GetArray((SC_SPARSE *)v56, v28), (v30 = Array) == 0)
        || Array == (struct SC_ARRAY *)(v56 + 8) )
      {
LABEL_37:
        --v2;
        *(_QWORD *)v52 = 0;
        *(_QWORD *)v52 = v5[v2];
        v5[v2] = 0;
      }
      else
      {
        v31 = v28 - *((_QWORD *)Array + 2);
        do
        {
          --v31;
          while ( v31 < 0 )
          {
            v30 = (struct SC_ARRAY *)*((_QWORD *)v30 + 1);
            if ( v30 == (struct SC_ARRAY *)(v56 + 8) )
              goto LABEL_37;
            v31 = (unsigned int)(*(_DWORD *)(v56 + 52) - 1);
          }
          v32 = *((_QWORD *)v30 + v31 + 3);
        }
        while ( !v32 );
        *(_QWORD *)v52 = v32;
      }
      Space = SDB_EXTENT::GetSpace((SDB_EXTENT *)v25);
      v34 = *((_QWORD *)Space + (*((_WORD *)Space + 15) & 1) + 4);
      if ( ((*(_BYTE *)(v34 + 66) - 1) & 0xF7) != 0 && SDB_EXTENT::SupportsSafeReallocation((SDB_EXTENT *)v25) )
      {
        if ( (*(_BYTE *)(v25 + 76) & 2) != 0 )
        {
          *(_QWORD *)(v51 + 272) += *(_QWORD *)(v25 + 32);
          *(_QWORD *)(v51 + 288) += *(_QWORD *)(v25 + 32);
          SDB_DRIVE::ChangeSlabBitmap(v55, *(_QWORD *)(v25 + 48), *(_QWORD *)(v25 + 32), 0);
        }
        if ( *(_DWORD *)(v25 + 72) == -1 )
        {
          v35 = *(_WORD *)(v25 + 78);
          if ( (v35 & 1) != 0 )
            *(_WORD *)(v25 + 78) = v35 & 0xFFFE;
          if ( ((*(_BYTE *)(v25 + 76) & 8) != 0 || v54 <= v53) && (*(_BYTE *)(v51 + 64) & 8) != 0 )
          {
            for ( j = SC_SPARSE::GetObject(*(SC_SPARSE **)(v34 + 232), *(_QWORD *)(v25 + 40) / *(_QWORD *)(v34 + 272));
                  j;
                  j = *(_QWORD **)(v37 + 80) )
            {
              v37 = j[(*((_WORD *)j + 15) & 1) + 4];
              if ( (*(_BYTE *)(v37 + 78) & 1) != 0 )
                goto LABEL_19;
            }
            v38 = SDB_POOL_CONFIG::PickDrive(this, (struct SDB_EXTENT *)v25, 1u, 1u, (struct SDB_EXTENT *)v57);
            v63 = v38;
            v6 = v38;
            if ( v38 == -1073740703 || v38 == -1073741823 )
            {
              v6 = 0;
              v63 = 0;
            }
            else
            {
              if ( v38 < 0 )
                goto LABEL_61;
              v39 = SDB_EXTENT::Provisioning((SDB_EXTENT *)v25);
              if ( SDB_POOL_CONFIG::IsBetterAllocation(
                     this,
                     (struct SDB_EXTENT *)v57,
                     (struct SDB_EXTENT *)v25,
                     *((_QWORD *)v39 + 1)) )
              {
                v40 = SDB_EXTENT::GetSpace((SDB_EXTENT *)v25);
                v41 = *((_QWORD *)v40 + (*((_WORD *)v40 + 15) & 1LL) + 4);
                *(_WORD *)(v41 + 352) |= 4u;
                v42 = *(_QWORD *)(v25 + 32);
                v43 = *(_QWORD *)(v25 + 48);
                *(_WORD *)(v25 + 78) |= 1u;
                SDB_DRIVE::ChangeSlabBitmap(v55, v43, v42, 0);
                LOBYTE(v44) = 2;
                v45 = SDB_POOL_CONFIG::FindRecordByRecordId((__int64)this, v44, v60);
                SDB_DRIVE::ChangeSlabBitmap(
                  *(SDB_DRIVE **)(v45 + 8 * (*(_WORD *)(v45 + 30) & 1LL) + 32),
                  v59,
                  *(_QWORD *)(v25 + 32),
                  1u);
                *(_QWORD *)(v51 + 272) += *(_QWORD *)(v25 + 32);
              }
            }
          }
        }
      }
    }
    if ( !*(_QWORD *)(v8 + 272) )
    {
      v6 = SDB_RECORD::PreTouch(*((SDB_RECORD **)this + 34), 0);
      if ( v6 >= 0 )
      {
        v46 = (SDB_RECORD *)*((_QWORD *)this + 34);
        v8 = *((_QWORD *)v46 + (*((_WORD *)v46 + 15) & 1LL) + 4);
        SDB_RECORD::Touch(v46);
        *(_QWORD *)(v8 + 280) = 0;
        *(_WORD *)(v8 + 64) &= 0xFFE7u;
        *(_QWORD *)(v8 + 296) = 0;
      }
    }
  }
  else
  {
    v6 = -1073741670;
  }
LABEL_61:
  *v64 = *(_QWORD *)(v8 + 272);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  for ( k = 0; ; k = v49 )
  {
    LOBYTE(a2) = 2;
    v48 = (void *)SDB_POOL_CONFIG::GetRecordByType(this, a2, k);
    v49 = v48;
    if ( !v48 )
      break;
    SDB_RECORD::Abort(v48);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140063d50  mov     [rsp-8+arg_8], rdx
0x140063d55  push    rbp
0x140063d56  push    rbx
0x140063d57  push    rsi
0x140063d58  push    rdi
0x140063d59  push    r12
0x140063d5b  push    r13
0x140063d5d  push    r14
0x140063d5f  push    r15
0x140063d61  lea     rbp, [rsp-1Fh]
0x140063d66  sub     rsp, 0D8h
0x140063d6d  xor     r12d, r12d
0x140063d70  mov     [rbp+57h+var_58], 0FFFFFFFFh
0x140063d77  mov     [rdx], r12
0x140063d7a  lea     rax, ??_7SDB_EXTENT@@6B@; const SDB_EXTENT::`vftable'
0x140063d81  mov     [rbp+57h+var_A0], rax
0x140063d85  mov     r14, rcx
0x140063d88  mov     rcx, [rcx+110h]; this
0x140063d8f  mov     r13d, r12d
0x140063d92  mov     [rbp+57h+var_98], r12
0x140063d96  mov     esi, r12d
0x140063d99  mov     [rbp+57h+var_90], r12
0x140063d9d  mov     [rbp+57h+var_88], r12w
0x140063da2  movzx   eax, word ptr [rcx+1Eh]
0x140063da6  and     eax, 1
0x140063da9  mov     [rbp+57h+var_54], r12w
0x140063dae  mov     [rbp+57h+arg_0], r12d
0x140063db2  mov     rdi, [rcx+rax*8+20h]
0x140063db7  mov     [rsp+110h+var_E0], rdi
0x140063dbc  test    byte ptr [rdi+40h], 10h
0x140063dc0  jnz     short loc_140063E15
0x140063dc2  xor     edx, edx; struct SDB_OBJECT *
0x140063dc4  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140063dc9  mov     [rbp+57h+arg_0], eax
0x140063dcc  mov     esi, eax
0x140063dce  test    eax, eax
0x140063dd0  js      loc_1400642BB
0x140063dd6  mov     rcx, [r14+110h]; this
0x140063ddd  movzx   eax, word ptr [rcx+1Eh]
0x140063de1  and     eax, 1
0x140063de4  mov     rdi, [rcx+rax*8+20h]
0x140063de9  mov     [rsp+110h+var_E0], rdi
0x140063dee  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x140063df3  or      word ptr [rdi+40h], 10h
0x140063df8  cmp     [rdi+128h], r12
0x140063dff  jnz     short loc_140063E15
0x140063e01  mov     rax, 0FFFFF78000000014h
0x140063e0b  mov     rax, [rax]
0x140063e0e  mov     [rdi+128h], rax
0x140063e15  mov     r15d, r12d
0x140063e18  xor     r8d, r8d
0x140063e1b  mov     dl, 2
0x140063e1d  mov     rcx, r14
0x140063e20  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063e25  mov     rbx, rax
0x140063e28  test    rax, rax
0x140063e2b  jz      short loc_140063E4C
0x140063e2d  xor     edx, edx; struct SDB_OBJECT *
0x140063e2f  mov     rcx, rax; this
0x140063e32  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140063e37  mov     [rbp+57h+arg_0], eax
0x140063e3a  mov     esi, eax
0x140063e3c  test    eax, eax
0x140063e3e  js      loc_1400642BB
0x140063e44  inc     r15d
0x140063e47  mov     r8, rbx
0x140063e4a  jmp     short loc_140063E1B
0x140063e4c  mov     ecx, r15d
0x140063e4f  xor     r9d, r9d; unsigned int
0x140063e52  shl     rcx, 3; unsigned __int64
0x140063e56  xor     r8d, r8d; unsigned __int8
0x140063e59  mov     edx, 58587053h; unsigned int
0x140063e5e  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140063e63  mov     r13, rax
0x140063e66  test    rax, rax
0x140063e69  jnz     short loc_140063E75
0x140063e6b  mov     esi, 0C000009Ah
0x140063e70  jmp     loc_1400642BB
0x140063e75  xor     r8d, r8d
0x140063e78  mov     [rbp+57h+arg_18], r12d
0x140063e7c  mov     dl, 2
0x140063e7e  mov     [rbp+57h+var_D0], r12
0x140063e82  mov     rcx, r14
0x140063e85  mov     [rbp+57h+arg_10], r12d
0x140063e89  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063e8e  mov     rbx, rax
0x140063e91  test    rax, rax
0x140063e94  jz      short loc_140063F05
0x140063e96  mov     rdi, r12
0x140063e99  movzx   ecx, word ptr [rbx+1Eh]
0x140063e9d  lea     rdx, [rbp+57h+var_B0]; unsigned __int64 *
0x140063ea1  and     ecx, 1
0x140063ea4  mov     r15, [rbx+rcx*8+20h]
0x140063ea9  mov     rcx, [r15+0C0h]; this
0x140063eb0  call    ?FindLastObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindLastObject(unsigned __int64 *)
0x140063eb5  mov     ecx, r12d
0x140063eb8  mov     [r13+rcx*8+0], rax
0x140063ebd  test    rax, rax
0x140063ec0  jz      short loc_140063EE7
0x140063ec2  movzx   ecx, word ptr [rax+1Eh]
0x140063ec6  inc     r12d
0x140063ec9  and     ecx, 1
0x140063ecc  mov     rdx, [rax+rcx*8+20h]
0x140063ed1  mov     rcx, [r15+118h]
0x140063ed8  sub     rcx, [rdx+30h]
0x140063edc  sub     rcx, [rdx+20h]
0x140063ee0  cmp     rcx, rdi
0x140063ee3  cmova   rdi, rcx
0x140063ee7  mov     r8, rbx
0x140063eea  mov     dl, 2
0x140063eec  mov     rcx, r14
0x140063eef  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063ef4  mov     rbx, rax
0x140063ef7  test    rax, rax
0x140063efa  jnz     short loc_140063E99
0x140063efc  mov     [rbp+57h+var_D0], rdi
0x140063f00  mov     rdi, [rsp+110h+var_E0]
0x140063f05  mov     qword ptr [rdi+110h], 0
0x140063f10  mov     qword ptr [rdi+120h], 0
0x140063f1b  mov     r15d, 1
0x140063f21  test    r12d, r12d
0x140063f24  jz      loc_14006426C
0x140063f2a  xor     r15d, r15d
0x140063f2d  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x140063f35  test    r12d, r12d
0x140063f38  jz      loc_140063FC5
0x140063f3e  mov     rdi, [rbp+57h+var_C8]
0x140063f42  mov     esi, [rbp+57h+arg_10]
0x140063f45  mov     rcx, [r13+r15*8+0]
0x140063f4a  mov     dl, 2
0x140063f4c  movzx   eax, word ptr [rcx+1Eh]
0x140063f50  and     eax, 1
0x140063f53  mov     rbx, [rcx+rax*8+20h]
0x140063f58  mov     rcx, [rbx+10h]
0x140063f5c  mov     r8d, [rbx+3Ch]
0x140063f60  mov     rcx, [rcx+10h]
0x140063f64  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x140063f69  movzx   ecx, word ptr [rax+1Eh]
0x140063f6d  and     ecx, 1
0x140063f70  mov     rax, [rax+rcx*8+20h]
0x140063f75  mov     rdx, [rax+118h]
0x140063f7c  sub     rdx, [rbx+30h]
0x140063f80  cmp     rdx, rdi
0x140063f83  jnb     short loc_140063F94
0x140063f85  mov     rdi, rdx
0x140063f88  mov     [rbp+57h+arg_18], 1
0x140063f8f  mov     esi, r15d
0x140063f92  jmp     short loc_140063FAE
0x140063f94  jnz     short loc_140063FAE
0x140063f96  mov     ebx, [rbp+57h+arg_18]
0x140063f99  mov     rcx, r14; this
0x140063f9c  inc     ebx
0x140063f9e  mov     edx, ebx; unsigned int
0x140063fa0  mov     [rbp+57h+arg_18], ebx
0x140063fa3  call    ?GetRandom@SDB_POOL_CONFIG@@IEAAKK@Z; SDB_POOL_CONFIG::GetRandom(ulong)
0x140063fa8  test    eax, eax
0x140063faa  cmovz   esi, r15d
0x140063fae  inc     r15d
0x140063fb1  cmp     r15d, r12d
0x140063fb4  jb      short loc_140063F45
0x140063fb6  mov     [rbp+57h+arg_10], esi
0x140063fb9  mov     esi, [rbp+57h+arg_0]
0x140063fbc  mov     [rbp+57h+var_C8], rdi
0x140063fc0  mov     rdi, [rsp+110h+var_E0]
0x140063fc5  mov     eax, [rbp+57h+arg_10]
0x140063fc8  mov     dl, 2
0x140063fca  lea     rax, ds:0[rax*8]
0x140063fd2  add     rax, r13
0x140063fd5  mov     [rsp+110h+var_D8], rax
0x140063fda  mov     rcx, [rax]
0x140063fdd  movzx   eax, word ptr [rcx+1Eh]
0x140063fe1  and     eax, 1
0x140063fe4  mov     rbx, [rcx+rax*8+20h]
0x140063fe9  mov     rcx, [rbx+10h]
0x140063fed  mov     r8d, [rbx+3Ch]
0x140063ff1  mov     rcx, [rcx+10h]
0x140063ff5  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x140063ffa  mov     r15, [rbx+30h]
0x140063ffe  movzx   ecx, word ptr [rax+1Eh]
0x140064002  and     ecx, 1
0x140064005  mov     rdx, [rax+rcx*8+20h]
0x14006400a  mov     [rbp+57h+var_B8], rdx
0x14006400e  mov     ecx, [rdx+0DCh]
0x140064014  shr     r15, cl
0x140064017  xor     ecx, ecx
0x140064019  mov     [rbp+57h+var_C0], rcx
0x14006401d  lea     rax, [r15-1]
0x140064021  test    rax, rax
0x140064024  js      short loc_14006408B
0x140064026  mov     rax, [rdx+0C0h]
0x14006402d  mov     rdx, r15; unsigned __int64
0x140064030  mov     rcx, rax; this
0x140064033  mov     [rbp+57h+var_B0], rax
0x140064037  call    ?GetArray@SC_SPARSE@@AEAAPEAVSC_ARRAY@@_K@Z; SC_SPARSE::GetArray(unsigned __int64)
0x14006403c  mov     rcx, rax
0x14006403f  test    rax, rax
0x140064042  jz      short loc_140064087
0x140064044  mov     rdx, [rbp+57h+var_B0]
0x140064048  lea     r8, [rdx+8]
0x14006404c  cmp     rax, r8
0x14006404f  jz      short loc_140064087
0x140064051  sub     r15, [rax+10h]
0x140064055  dec     r15
0x140064058  test    r15, r15
0x14006405b  js      short loc_140064071
0x14006405d  mov     rax, [rcx+r15*8+18h]
0x140064062  test    rax, rax
0x140064065  jz      short loc_140064055
0x140064067  mov     rdx, [rsp+110h+var_D8]
0x14006406c  mov     [rdx], rax
0x14006406f  jmp     short loc_1400640AA
0x140064071  mov     rcx, [rcx+8]
0x140064075  cmp     rcx, r8
0x140064078  jz      short loc_140064083
0x14006407a  mov     r15d, [rdx+34h]
0x14006407e  dec     r15d
0x140064081  jmp     short loc_140064058
0x140064083  xor     ecx, ecx
0x140064085  jmp     short loc_14006408B
0x140064087  mov     rcx, [rbp+57h+var_C0]
0x14006408b  mov     rdx, [rsp+110h+var_D8]
0x140064090  dec     r12d
0x140064093  mov     rax, rdx
0x140064096  mov     [rdx], rcx
0x140064099  mov     rax, [r13+r12*8+0]
0x14006409e  mov     [rdx], rax
0x1400640a1  mov     qword ptr [r13+r12*8+0], 0
0x1400640aa  mov     rcx, rbx; this
0x1400640ad  call    ?GetSpace@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetSpace(void)
0x1400640b2  movzx   ecx, word ptr [rax+1Eh]
0x1400640b6  and     ecx, 1
0x1400640b9  mov     r15, [rax+rcx*8+20h]
0x1400640be  mov     al, [r15+42h]
0x1400640c2  dec     al
0x1400640c4  test    al, 0F7h
0x1400640c6  jz      loc_140063F1B
0x1400640cc  mov     rcx, rbx; this
0x1400640cf  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x1400640d4  test    al, al
0x1400640d6  jz      loc_140063F1B
0x1400640dc  test    byte ptr [rbx+4Ch], 2
0x1400640e0  jz      short loc_14006410C
0x1400640e2  mov     rax, [rbx+20h]
0x1400640e6  xor     r9d, r9d; unsigned __int8
0x1400640e9  add     [rdi+110h], rax
0x1400640f0  mov     rax, [rbx+20h]
0x1400640f4  add     [rdi+120h], rax
0x1400640fb  mov     r8, [rbx+20h]; unsigned __int64
0x1400640ff  mov     rdx, [rbx+30h]; unsigned __int64
0x140064103  mov     rcx, [rbp+57h+var_B8]; this
0x140064107  call    ?ChangeSlabBitmap@SDB_DRIVE@@QEAAX_K0E@Z; SDB_DRIVE::ChangeSlabBitmap(unsigned __int64,unsigned __int64,uchar)
0x14006410c  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x140064110  jnz     loc_140063F1B
0x140064116  movzx   eax, word ptr [rbx+4Eh]
0x14006411a  test    al, 1
0x14006411c  jz      short loc_14006412A
0x14006411e  mov     ecx, 0FFFEh
0x140064123  and     ax, cx
0x140064126  mov     [rbx+4Eh], ax
0x14006412a  test    byte ptr [rbx+4Ch], 8
0x14006412e  jnz     short loc_14006413E
0x140064130  mov     rax, [rbp+57h+var_D0]
0x140064134  cmp     [rbp+57h+var_C8], rax
0x140064138  ja      loc_140063F1B
0x14006413e  test    byte ptr [rdi+40h], 8
0x140064142  jz      loc_140063F1B
0x140064148  mov     rax, [rbx+28h]
0x14006414c  xor     edx, edx
0x14006414e  div     qword ptr [r15+110h]
0x140064155  mov     rcx, [r15+0E8h]; this
0x14006415c  mov     rdx, rax; unsigned __int64
0x14006415f  call    ?GetObject@SC_SPARSE@@QEAAPEAX_K@Z; SC_SPARSE::GetObject(unsigned __int64)
0x140064164  mov     r8, rax
0x140064167  mov     r15d, 1
0x14006416d  test    r8, r8
0x140064170  jz      short loc_140064193
0x140064172  movzx   ecx, word ptr [r8+1Eh]
0x140064177  and     cx, r15w
0x14006417b  movzx   eax, cx
0x14006417e  mov     rcx, [r8+rax*8+20h]
0x140064183  test    [rcx+4Eh], r15b
0x140064187  jnz     loc_140063F21
0x14006418d  mov     r8, [rcx+50h]
0x140064191  jmp     short loc_14006416D
0x140064193  lea     rax, [rbp+57h+var_A0]
0x140064197  mov     r9b, r15b; unsigned __int8
0x14006419a  mov     r8b, r15b; unsigned __int8
0x14006419d  mov     [rsp+110h+var_F0], rax; struct SDB_EXTENT *
0x1400641a2  mov     rdx, rbx; struct SDB_EXTENT *
0x1400641a5  mov     rcx, r14; this
0x1400641a8  call    ?PickDrive@SDB_POOL_CONFIG@@QEAAJPEAVSDB_EXTENT@@EE0@Z; SDB_POOL_CONFIG::PickDrive(SDB_EXTENT *,uchar,uchar,SDB_EXTENT *)
0x1400641ad  mov     [rbp+57h+arg_0], eax
0x1400641b0  mov     esi, eax
0x1400641b2  cmp     eax, 0C0000461h
0x1400641b7  jz      loc_140064262
0x1400641bd  cmp     eax, 0C0000001h
0x1400641c2  jz      loc_140064262
0x1400641c8  test    eax, eax
0x1400641ca  js      loc_1400642BB
0x1400641d0  mov     rcx, rbx; this
  ... truncated ...
```
