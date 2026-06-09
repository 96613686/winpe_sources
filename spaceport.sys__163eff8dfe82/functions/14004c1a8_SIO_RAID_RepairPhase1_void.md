# SIO_RAID::RepairPhase1(void)

- ea: `0x14004c1a8`
- end: `0x14004c5fb`
- name: `?RepairPhase1@SIO_RAID@@AEAAJXZ`
- size: `1107`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x1400135a0`

## callees

- `0x14000aca0`
- `0x14000b080`
- `0x14000b290`
- `0x14000b310`
- `0x14000bb50`
- `0x14000c630`
- `0x140026620`
- `0x1400266c0`
- `0x14004af68`
- `0x14004b1dc`
- `0x14004b708`
- `0x14004c1a8`
- `0x14004cdd4`
- `0x14005f764`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c40a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c579`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c40a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c579`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c3b7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c4d1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c3b7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c4d1`

## pseudocode

```c
__int64 __fastcall SIO_RAID::RepairPhase1(SIO_RAID *this)
{
  unsigned int v2; // r14d
  unsigned int i; // r12d
  unsigned int j; // ecx
  struct SIO_COLUMN *v5; // rax
  struct SIO_COLUMN *v6; // r13
  unsigned int *v7; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  SIO_SPACE *v10; // rdi
  struct SIO_SPACE *TopLevel; // rax
  struct _GUID *v12; // rdx
  struct SDB_RECORD *Extent; // rax
  __int64 v14; // rdx
  SDB_EXTENT **v15; // rcx
  SDB_EXTENT *v16; // r15
  __int64 RecordByRecordId; // rax
  __int64 *v18; // rcx
  __int64 v19; // rbp
  struct SC_DRIVE *Drive; // r9
  char v21; // si
  unsigned __int8 v22; // di
  KIRQL v23; // al
  __int64 v24; // r9
  unsigned int v25; // esi
  KIRQL v26; // bp
  struct SDB_RECORD *ColumnRecord; // rax
  int v28; // eax
  __int64 v29; // r9
  char v30; // di
  unsigned int v31; // r14d
  __int64 k; // r9
  KIRQL v33; // r15
  unsigned int v34; // r10d
  unsigned int v35; // edx
  SIO_RAID *v36; // rcx
  unsigned int v37; // r9d
  struct SIO_COLUMN *v38; // rcx
  unsigned int v40; // [rsp+20h] [rbp-68h]
  unsigned int *v41; // [rsp+30h] [rbp-58h]
  unsigned __int64 v42; // [rsp+38h] [rbp-50h]
  char v43; // [rsp+90h] [rbp+8h]
  unsigned int v44; // [rsp+98h] [rbp+10h]

  v2 = 0;
  v42 = MEMORY[0xFFFFF78000000008];
  SIO_RAID::Resiliency(this);
  if ( *((_DWORD *)SIO_RAID::Resiliency(this) + 4) )
  {
    for ( i = 0; i < *((_DWORD *)SIO_RAID::Resiliency(this) + 4); ++i )
    {
      for ( j = 0; ; j = v44 + 1 )
      {
        v44 = j;
        if ( j >= *((unsigned __int8 *)this + 43) )
          break;
        v5 = SIO_RAID::Get(this, i, j);
        v6 = v5;
        v7 = (unsigned int *)((char *)v5 + 16);
        v41 = (unsigned int *)((char *)v5 + 16);
        if ( v9 >= v8 )
        {
          v41 = (unsigned int *)((char *)v5 + 16);
        }
        else if ( !SDB_SPACE_CONFIG::FindColumnRecord(
                     *(SDB_SPACE_CONFIG **)(*((_QWORD *)this + 1) + 328LL),
                     *((_QWORD *)this + 2),
                     i,
                     *v7) )
        {
          continue;
        }
        v10 = (SIO_SPACE *)*((_QWORD *)this + 1);
        TopLevel = SIO_SPACE::GetTopLevel(v10);
        Extent = SDB_POOL_CONFIG::FindExtent(*((SDB_POOL_CONFIG **)TopLevel + 18), v12, *((_QWORD *)this + 2), i, *v7);
        if ( Extent )
        {
          if ( (*((_BYTE *)Extent + 30) & 1) != 0 )
            v15 = (SDB_EXTENT **)((char *)Extent + 40);
          else
            v15 = (SDB_EXTENT **)((char *)Extent + 32);
          v16 = *v15;
          LOBYTE(v14) = 2;
          RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(
                               *(_QWORD *)(*((_QWORD *)*v15 + 2) + 16LL),
                               v14,
                               *((_DWORD *)*v15 + 15));
          if ( (*(_BYTE *)(RecordByRecordId + 30) & 1) != 0 )
            v18 = (__int64 *)(RecordByRecordId + 40);
          else
            v18 = (__int64 *)(RecordByRecordId + 32);
          v19 = *v18;
          Drive = SIO_SPACE::GetDrive(v10, *((_DWORD *)v6 + 1));
          if ( *(_DWORD *)(v19 + 68) == 5 )
          {
            v21 = 6;
          }
          else if ( (*(_DWORD *)(v19 + 252) & 4) != 0 )
          {
            v21 = 2;
          }
          else if ( Drive && *((_DWORD *)Drive + 144) == -1073740669 )
          {
            v21 = 4;
          }
          else
          {
            v21 = *((_BYTE *)v6 + 2) >> 4;
          }
          v22 = *((_BYTE *)v6 + 2);
          v43 = 1;
          if ( (v22 & 0xF) == 1 || (*((_BYTE *)v6 + 2) & 0xF) == 2 )
            goto LABEL_28;
          if ( (*((_BYTE *)v6 + 2) & 0xF) != 3 )
          {
            if ( (*((_BYTE *)v6 + 2) & 0xFu) - 5 > 1 )
              continue;
LABEL_28:
            if ( SDB_EXTENT::SupportsSafeReallocation(v16) || v21 == v22 >> 4 )
              continue;
            v23 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
            LOBYTE(v40) = v21;
            LOBYTE(v24) = 4;
            v25 = v44;
            v26 = v23;
            if ( (unsigned int)SIO_RAID::SetColumnPendingStateInternal(this, i, v44, v24, v40) == -1058602989 )
            {
              v43 = 0;
              *(_WORD *)v6 |= 2u;
            }
            v2 = 0;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v26);
LABEL_33:
            if ( !v43 )
            {
              ColumnRecord = SDB_SPACE_CONFIG::FindColumnRecord(
                               *(SDB_SPACE_CONFIG **)(*((_QWORD *)this + 1) + 328LL),
                               *((_QWORD *)this + 2),
                               i,
                               *v41);
              v28 = ColumnRecord
                  ? SIO_RAID::UpdateColumnRecord(this, ColumnRecord)
                  : SIO_RAID::CreateColumnRecord(this, i, v25);
              v2 = v28;
              if ( v28 < 0 )
                return v2;
            }
            continue;
          }
          if ( v21 == v22 >> 4 && SIO_COLUMN::CanRegenerate(v6) )
          {
            if ( v29 )
              continue;
            v21 = 1;
            v30 = 4;
LABEL_41:
            if ( *(_QWORD *)(v19 + 240) > v42
              || (*((_DWORD *)SIO_SPACE::GetTopLevel(*((SIO_SPACE **)this + 1)) + 11) & 8) != 0 )
            {
              v31 = v44;
              v30 = 3;
LABEL_45:
              v33 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
              if ( (*(_WORD *)v6 & 4) != 0 )
              {
                v34 = *((unsigned __int8 *)this + 43);
                for ( k = 0; (unsigned int)k < v34; k = v37 + 1 )
                {
                  if ( *((_DWORD *)SIO_RAID::Get(this, i, k) + 5) == v31 )
                  {
                    v38 = SIO_RAID::Get(v36, v35, v37);
                    goto LABEL_52;
                  }
                }
                v38 = 0;
LABEL_52:
                if ( v38 && (*((_BYTE *)v38 + 2) & 0xF) == 1 && (*((_BYTE *)v38 + 3) & 0xF) == 0 )
                  v30 = 8;
              }
              LOBYTE(k) = v30;
              LOBYTE(v40) = v21;
              if ( (unsigned int)SIO_RAID::SetColumnPendingStateInternal(this, i, v31, k, v40) == -1058602989 )
              {
                v43 = 0;
                *(_WORD *)v6 |= 2u;
              }
              v2 = 0;
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v33);
              v25 = v44;
              goto LABEL_33;
            }
          }
          else
          {
            v30 = 4;
            if ( v21 == 1 )
              goto LABEL_41;
          }
          v31 = v44;
          SIO_RAID::InvalidateStripeState(this, i, v44);
          goto LABEL_45;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14004c1a8  push    rbx
0x14004c1aa  push    rbp
0x14004c1ab  push    rsi
0x14004c1ac  push    rdi
0x14004c1ad  push    r12
0x14004c1af  push    r13
0x14004c1b1  push    r14
0x14004c1b3  push    r15
0x14004c1b5  sub     rsp, 48h
0x14004c1b9  mov     rbx, rcx
0x14004c1bc  mov     rax, 0FFFFF78000000008h
0x14004c1c6  xor     r14d, r14d
0x14004c1c9  mov     rax, [rax]
0x14004c1cc  mov     [rsp+88h+var_50], rax
0x14004c1d1  mov     rax, [rcx+8]
0x14004c1d5  mov     rdx, [rax+148h]
0x14004c1dc  mov     eax, 200h
0x14004c1e1  mov     rcx, [rdx+8]
0x14004c1e5  xor     edx, edx
0x14004c1e7  div     dword ptr [rcx+1Ch]
0x14004c1ea  mov     edx, [rcx+18h]
0x14004c1ed  mov     ecx, [rcx+0A8h]
0x14004c1f3  sub     edx, eax
0x14004c1f5  shr     edx, 1
0x14004c1f7  mov     eax, ecx
0x14004c1f9  sub     eax, edx
0x14004c1fb  cmp     edx, ecx
0x14004c1fd  mov     rcx, rbx; this
0x14004c200  sbb     edi, edi
0x14004c202  and     edi, eax
0x14004c204  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c209  mov     rcx, rbx; this
0x14004c20c  mov     rsi, rax
0x14004c20f  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c214  cmp     [rax+10h], r14d
0x14004c218  jbe     loc_14004C5E6
0x14004c21e  movzx   r9d, byte ptr [rbx+2Bh]
0x14004c223  lea     r10d, [rdi-100h]
0x14004c22a  xor     r12d, r12d
0x14004c22d  mov     [rsp+88h+arg_18], r10d
0x14004c235  imul    r9d, [rsi+10h]
0x14004c23a  mov     [rsp+88h+arg_10], r9d
0x14004c242  xor     ecx, ecx
0x14004c244  movzx   eax, byte ptr [rbx+2Bh]
0x14004c248  mov     [rsp+88h+arg_8], ecx
0x14004c24f  cmp     ecx, eax
0x14004c251  jnb     loc_14004C5C1
0x14004c257  mov     r8d, ecx; unsigned int
0x14004c25a  mov     edx, r12d; unsigned int
0x14004c25d  mov     rcx, rbx; this
0x14004c260  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c265  mov     r13, rax
0x14004c268  lea     rsi, [rax+10h]
0x14004c26c  mov     [rsp+88h+var_58], rsi
0x14004c271  cmp     r10d, r9d
0x14004c274  jnb     short loc_14004C29B
0x14004c276  mov     rcx, [rbx+8]
0x14004c27a  mov     r8d, r12d; unsigned int
0x14004c27d  mov     r9d, [rsi]; unsigned int
0x14004c280  mov     rdx, [rbx+10h]; unsigned __int64
0x14004c284  mov     rcx, [rcx+148h]; this
0x14004c28b  call    ?FindColumnRecord@SDB_SPACE_CONFIG@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE_CONFIG::FindColumnRecord(unsigned __int64,ulong,ulong)
0x14004c290  test    rax, rax
0x14004c293  jz      loc_14004C5A3
0x14004c299  jmp     short loc_14004C2A0
0x14004c29b  mov     [rsp+88h+var_58], rsi
0x14004c2a0  mov     rdi, [rbx+8]
0x14004c2a4  mov     rcx, rdi; this
0x14004c2a7  lea     rdx, [rdi+18h]
0x14004c2ab  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x14004c2b0  mov     r8, [rbx+10h]; unsigned __int64
0x14004c2b4  mov     r9d, r12d; unsigned int
0x14004c2b7  mov     rcx, [rax+90h]; this
0x14004c2be  mov     eax, [rsi]
0x14004c2c0  mov     [rsp+88h+var_68], eax; unsigned int
0x14004c2c4  call    ?FindExtent@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@_KKK@Z; SDB_POOL_CONFIG::FindExtent(_GUID *,unsigned __int64,ulong,ulong)
0x14004c2c9  mov     rcx, rax
0x14004c2cc  test    rax, rax
0x14004c2cf  jz      loc_14004C5A3
0x14004c2d5  test    byte ptr [rax+1Eh], 1
0x14004c2d9  jz      short loc_14004C2E1
0x14004c2db  add     rcx, 28h ; '('
0x14004c2df  jmp     short loc_14004C2E5
0x14004c2e1  add     rcx, 20h ; ' '
0x14004c2e5  mov     r15, [rcx]
0x14004c2e8  mov     dl, 2
0x14004c2ea  mov     rcx, [r15+10h]
0x14004c2ee  mov     r8d, [r15+3Ch]
0x14004c2f2  mov     rcx, [rcx+10h]
0x14004c2f6  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x14004c2fb  mov     rcx, rax
0x14004c2fe  test    byte ptr [rax+1Eh], 1
0x14004c302  jz      short loc_14004C30A
0x14004c304  add     rcx, 28h ; '('
0x14004c308  jmp     short loc_14004C30E
0x14004c30a  add     rcx, 20h ; ' '
0x14004c30e  mov     rbp, [rcx]
0x14004c311  mov     rcx, rdi; this
0x14004c314  mov     edx, [r13+4]; unsigned int
0x14004c318  call    ?GetDrive@SIO_SPACE@@QEAAPEAVSC_DRIVE@@K@Z; SIO_SPACE::GetDrive(ulong)
0x14004c31d  cmp     dword ptr [rbp+44h], 5
0x14004c321  mov     r9, rax
0x14004c324  jnz     short loc_14004C32B
0x14004c326  mov     sil, 6
0x14004c329  jmp     short loc_14004C35F
0x14004c32b  mov     eax, [rbp+0FCh]
0x14004c331  test    al, 4
0x14004c333  jz      short loc_14004C33F
0x14004c335  mov     edx, 2
0x14004c33a  mov     sil, dl
0x14004c33d  jmp     short loc_14004C364
0x14004c33f  test    r9, r9
0x14004c342  jz      short loc_14004C357
0x14004c344  mov     eax, [r9+240h]
0x14004c34b  cmp     eax, 0C0000483h
0x14004c350  jnz     short loc_14004C357
0x14004c352  mov     sil, 4
0x14004c355  jmp     short loc_14004C35F
0x14004c357  mov     sil, [r13+2]
0x14004c35b  shr     sil, 4
0x14004c35f  mov     edx, 2
0x14004c364  movzx   edi, byte ptr [r13+2]
0x14004c369  mov     ecx, edi
0x14004c36b  mov     [rsp+88h+arg_0], 1
0x14004c373  and     ecx, 0Fh
0x14004c376  sub     ecx, 1
0x14004c379  jz      short loc_14004C396
0x14004c37b  sub     ecx, 1
0x14004c37e  jz      short loc_14004C396
0x14004c380  sub     ecx, 1
0x14004c383  jz      loc_14004C45C
0x14004c389  sub     ecx, edx
0x14004c38b  jz      short loc_14004C396
0x14004c38d  cmp     ecx, 1
0x14004c390  jnz     loc_14004C5A3
0x14004c396  mov     rcx, r15; this
0x14004c399  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x14004c39e  test    al, al
0x14004c3a0  jnz     loc_14004C5A3
0x14004c3a6  shr     dil, 4
0x14004c3aa  cmp     sil, dil
0x14004c3ad  jz      loc_14004C5A3
0x14004c3b3  lea     rcx, [rbx+18h]; SpinLock
0x14004c3b7  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004c3be  nop     dword ptr [rax+rax+00h]
0x14004c3c3  mov     byte ptr [rsp+88h+var_68], sil
0x14004c3c8  mov     r9b, 4
0x14004c3cb  mov     esi, [rsp+88h+arg_8]
0x14004c3d2  mov     edx, r12d
0x14004c3d5  mov     r8d, esi
0x14004c3d8  mov     rcx, rbx
0x14004c3db  mov     bpl, al
0x14004c3de  call    ?SetColumnPendingStateInternal@SIO_RAID@@AEAAJKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnPendingStateInternal(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x14004c3e3  cmp     eax, 0C0E70013h
0x14004c3e8  jnz     short loc_14004C400
0x14004c3ea  movzx   edx, word ptr [r13+0]
0x14004c3ef  or      dx, 2
0x14004c3f3  mov     [rsp+88h+arg_0], 0
0x14004c3fb  mov     [r13+0], dx
0x14004c400  xor     r14d, r14d
0x14004c403  lea     rcx, [rbx+18h]; SpinLock
0x14004c407  mov     dl, bpl; OldIrql
0x14004c40a  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004c411  nop     dword ptr [rax+rax+00h]
0x14004c416  cmp     [rsp+88h+arg_0], 0
0x14004c41e  jnz     loc_14004C5A3
0x14004c424  mov     r9, [rsp+88h+var_58]
0x14004c429  mov     r8d, r12d; unsigned int
0x14004c42c  mov     rcx, [rbx+8]
0x14004c430  mov     rdx, [rbx+10h]; unsigned __int64
0x14004c434  mov     r9d, [r9]; unsigned int
0x14004c437  mov     rcx, [rcx+148h]; this
0x14004c43e  call    ?FindColumnRecord@SDB_SPACE_CONFIG@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE_CONFIG::FindColumnRecord(unsigned __int64,ulong,ulong)
0x14004c443  mov     rcx, rbx; this
0x14004c446  test    rax, rax
0x14004c449  jz      loc_14004C591
0x14004c44f  mov     rdx, rax; struct SDB_RECORD *
0x14004c452  call    ?UpdateColumnRecord@SIO_RAID@@AEAAJPEAVSDB_RECORD@@@Z; SIO_RAID::UpdateColumnRecord(SDB_RECORD *)
0x14004c457  jmp     loc_14004C59C
0x14004c45c  shr     dil, 4
0x14004c460  cmp     sil, dil
0x14004c463  jnz     short loc_14004C482
0x14004c465  mov     rcx, r13; this
0x14004c468  call    ?CanRegenerate@SIO_COLUMN@@QEAAEXZ; SIO_COLUMN::CanRegenerate(void)
0x14004c46d  test    al, al
0x14004c46f  jz      short loc_14004C482
0x14004c471  test    r9, r9
0x14004c474  jnz     loc_14004C5A3
0x14004c47a  mov     sil, 1
0x14004c47d  mov     dil, 4
0x14004c480  jmp     short loc_14004C48B
0x14004c482  mov     dil, 4
0x14004c485  cmp     sil, 1
0x14004c489  jnz     short loc_14004C4B7
0x14004c48b  mov     rax, [rsp+88h+var_50]
0x14004c490  cmp     [rbp+0F0h], rax
0x14004c497  ja      short loc_14004C4AA
0x14004c499  mov     rcx, [rbx+8]; this
0x14004c49d  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x14004c4a2  mov     ecx, [rax+2Ch]
0x14004c4a5  test    cl, 8
0x14004c4a8  jz      short loc_14004C4B7
0x14004c4aa  mov     r14d, [rsp+88h+arg_8]
0x14004c4b2  mov     dil, 3
0x14004c4b5  jmp     short loc_14004C4CD
0x14004c4b7  mov     r14d, [rsp+88h+arg_8]
0x14004c4bf  mov     edx, r12d; unsigned int
0x14004c4c2  mov     r8d, r14d; unsigned int
0x14004c4c5  mov     rcx, rbx; this
0x14004c4c8  call    ?InvalidateStripeState@SIO_RAID@@IEAAXKK@Z; SIO_RAID::InvalidateStripeState(ulong,ulong)
0x14004c4cd  lea     rcx, [rbx+18h]; SpinLock
0x14004c4d1  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004c4d8  nop     dword ptr [rax+rax+00h]
0x14004c4dd  mov     r15b, al
0x14004c4e0  movzx   eax, word ptr [r13+0]
0x14004c4e5  test    al, 4
0x14004c4e7  jz      short loc_14004C53C
0x14004c4e9  movzx   r10d, byte ptr [rbx+2Bh]
0x14004c4ee  xor     r9d, r9d
0x14004c4f1  cmp     r9d, r10d
0x14004c4f4  jnb     short loc_14004C51C
0x14004c4f6  mov     r8d, r9d; unsigned int
0x14004c4f9  mov     edx, r12d; unsigned int
0x14004c4fc  mov     rcx, rbx; this
0x14004c4ff  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c504  cmp     [rax+14h], r14d
0x14004c508  jz      short loc_14004C50F
0x14004c50a  inc     r9d
0x14004c50d  jmp     short loc_14004C4F1
0x14004c50f  mov     r8d, r9d; unsigned int
0x14004c512  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c517  mov     rcx, rax
0x14004c51a  jmp     short loc_14004C51E
0x14004c51c  xor     ecx, ecx
0x14004c51e  test    rcx, rcx
0x14004c521  jz      short loc_14004C53C
0x14004c523  mov     al, [rcx+2]
0x14004c526  and     al, 0Fh
0x14004c528  cmp     al, 1
0x14004c52a  jnz     short loc_14004C53C
0x14004c52c  test    byte ptr [rcx+3], 0Fh
0x14004c530  mov     eax, 8
0x14004c535  movzx   edi, dil
0x14004c539  cmovz   edi, eax
0x14004c53c  mov     r9b, dil
0x14004c53f  mov     byte ptr [rsp+88h+var_68], sil
0x14004c544  mov     r8d, r14d
0x14004c547  mov     edx, r12d
0x14004c54a  mov     rcx, rbx
0x14004c54d  call    ?SetColumnPendingStateInternal@SIO_RAID@@AEAAJKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnPendingStateInternal(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x14004c552  cmp     eax, 0C0E70013h
0x14004c557  jnz     short loc_14004C56F
0x14004c559  movzx   eax, word ptr [r13+0]
0x14004c55e  or      ax, 2
0x14004c562  mov     [rsp+88h+arg_0], 0
0x14004c56a  mov     [r13+0], ax
0x14004c56f  xor     r14d, r14d
0x14004c572  lea     rcx, [rbx+18h]; SpinLock
0x14004c576  mov     dl, r15b; OldIrql
0x14004c579  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004c580  nop     dword ptr [rax+rax+00h]
0x14004c585  mov     esi, [rsp+88h+arg_8]
0x14004c58c  jmp     loc_14004C416
0x14004c591  mov     r8d, esi; unsigned int
0x14004c594  mov     edx, r12d; unsigned int
0x14004c597  call    ?CreateColumnRecord@SIO_RAID@@AEAAJKK@Z; SIO_RAID::CreateColumnRecord(ulong,ulong)
0x14004c59c  mov     r14d, eax
0x14004c59f  test    eax, eax
0x14004c5a1  js      short loc_14004C5E6
0x14004c5a3  mov     ecx, [rsp+88h+arg_8]
0x14004c5aa  mov     r9d, [rsp+88h+arg_10]
0x14004c5b2  inc     ecx
0x14004c5b4  mov     r10d, [rsp+88h+arg_18]
0x14004c5bc  jmp     loc_14004C244
0x14004c5c1  mov     rcx, rbx; this
0x14004c5c4  inc     r12d
0x14004c5c7  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c5cc  mov     r9d, [rsp+88h+arg_10]
0x14004c5d4  mov     r10d, [rsp+88h+arg_18]
0x14004c5dc  cmp     r12d, [rax+10h]
0x14004c5e0  jb      loc_14004C242
0x14004c5e6  mov     eax, r14d
0x14004c5e9  add     rsp, 48h
0x14004c5ed  pop     r15
0x14004c5ef  pop     r14
0x14004c5f1  pop     r13
0x14004c5f3  pop     r12
0x14004c5f5  pop     rdi
0x14004c5f6  pop     rsi
0x14004c5f7  pop     rbp
0x14004c5f8  pop     rbx
0x14004c5f9  retn
```
