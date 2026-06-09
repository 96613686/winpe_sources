# SIO_RAID::RepairPhase1(void)

- ea: `0x14004c0e8`
- end: `0x14004c53b`
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
- `0x14004aea8`
- `0x14004b11c`
- `0x14004b648`
- `0x14004c0e8`
- `0x14004cd14`
- `0x14005f664`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c34a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c4b9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c34a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004c4b9`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c2f7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c411`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c2f7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004c411`

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
0x14004c0e8  push    rbx
0x14004c0ea  push    rbp
0x14004c0eb  push    rsi
0x14004c0ec  push    rdi
0x14004c0ed  push    r12
0x14004c0ef  push    r13
0x14004c0f1  push    r14
0x14004c0f3  push    r15
0x14004c0f5  sub     rsp, 48h
0x14004c0f9  mov     rbx, rcx
0x14004c0fc  mov     rax, 0FFFFF78000000008h
0x14004c106  xor     r14d, r14d
0x14004c109  mov     rax, [rax]
0x14004c10c  mov     [rsp+88h+var_50], rax
0x14004c111  mov     rax, [rcx+8]
0x14004c115  mov     rdx, [rax+148h]
0x14004c11c  mov     eax, 200h
0x14004c121  mov     rcx, [rdx+8]
0x14004c125  xor     edx, edx
0x14004c127  div     dword ptr [rcx+1Ch]
0x14004c12a  mov     edx, [rcx+18h]
0x14004c12d  mov     ecx, [rcx+0A8h]
0x14004c133  sub     edx, eax
0x14004c135  shr     edx, 1
0x14004c137  mov     eax, ecx
0x14004c139  sub     eax, edx
0x14004c13b  cmp     edx, ecx
0x14004c13d  mov     rcx, rbx; this
0x14004c140  sbb     edi, edi
0x14004c142  and     edi, eax
0x14004c144  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c149  mov     rcx, rbx; this
0x14004c14c  mov     rsi, rax
0x14004c14f  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c154  cmp     [rax+10h], r14d
0x14004c158  jbe     loc_14004C526
0x14004c15e  movzx   r9d, byte ptr [rbx+2Bh]
0x14004c163  lea     r10d, [rdi-100h]
0x14004c16a  xor     r12d, r12d
0x14004c16d  mov     [rsp+88h+arg_18], r10d
0x14004c175  imul    r9d, [rsi+10h]
0x14004c17a  mov     [rsp+88h+arg_10], r9d
0x14004c182  xor     ecx, ecx
0x14004c184  movzx   eax, byte ptr [rbx+2Bh]
0x14004c188  mov     [rsp+88h+arg_8], ecx
0x14004c18f  cmp     ecx, eax
0x14004c191  jnb     loc_14004C501
0x14004c197  mov     r8d, ecx; unsigned int
0x14004c19a  mov     edx, r12d; unsigned int
0x14004c19d  mov     rcx, rbx; this
0x14004c1a0  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c1a5  mov     r13, rax
0x14004c1a8  lea     rsi, [rax+10h]
0x14004c1ac  mov     [rsp+88h+var_58], rsi
0x14004c1b1  cmp     r10d, r9d
0x14004c1b4  jnb     short loc_14004C1DB
0x14004c1b6  mov     rcx, [rbx+8]
0x14004c1ba  mov     r8d, r12d; unsigned int
0x14004c1bd  mov     r9d, [rsi]; unsigned int
0x14004c1c0  mov     rdx, [rbx+10h]; unsigned __int64
0x14004c1c4  mov     rcx, [rcx+148h]; this
0x14004c1cb  call    ?FindColumnRecord@SDB_SPACE_CONFIG@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE_CONFIG::FindColumnRecord(unsigned __int64,ulong,ulong)
0x14004c1d0  test    rax, rax
0x14004c1d3  jz      loc_14004C4E3
0x14004c1d9  jmp     short loc_14004C1E0
0x14004c1db  mov     [rsp+88h+var_58], rsi
0x14004c1e0  mov     rdi, [rbx+8]
0x14004c1e4  mov     rcx, rdi; this
0x14004c1e7  lea     rdx, [rdi+18h]
0x14004c1eb  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x14004c1f0  mov     r8, [rbx+10h]; unsigned __int64
0x14004c1f4  mov     r9d, r12d; unsigned int
0x14004c1f7  mov     rcx, [rax+90h]; this
0x14004c1fe  mov     eax, [rsi]
0x14004c200  mov     [rsp+88h+var_68], eax; unsigned int
0x14004c204  call    ?FindExtent@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@_KKK@Z; SDB_POOL_CONFIG::FindExtent(_GUID *,unsigned __int64,ulong,ulong)
0x14004c209  mov     rcx, rax
0x14004c20c  test    rax, rax
0x14004c20f  jz      loc_14004C4E3
0x14004c215  test    byte ptr [rax+1Eh], 1
0x14004c219  jz      short loc_14004C221
0x14004c21b  add     rcx, 28h ; '('
0x14004c21f  jmp     short loc_14004C225
0x14004c221  add     rcx, 20h ; ' '
0x14004c225  mov     r15, [rcx]
0x14004c228  mov     dl, 2
0x14004c22a  mov     rcx, [r15+10h]
0x14004c22e  mov     r8d, [r15+3Ch]
0x14004c232  mov     rcx, [rcx+10h]
0x14004c236  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x14004c23b  mov     rcx, rax
0x14004c23e  test    byte ptr [rax+1Eh], 1
0x14004c242  jz      short loc_14004C24A
0x14004c244  add     rcx, 28h ; '('
0x14004c248  jmp     short loc_14004C24E
0x14004c24a  add     rcx, 20h ; ' '
0x14004c24e  mov     rbp, [rcx]
0x14004c251  mov     rcx, rdi; this
0x14004c254  mov     edx, [r13+4]; unsigned int
0x14004c258  call    ?GetDrive@SIO_SPACE@@QEAAPEAVSC_DRIVE@@K@Z; SIO_SPACE::GetDrive(ulong)
0x14004c25d  cmp     dword ptr [rbp+44h], 5
0x14004c261  mov     r9, rax
0x14004c264  jnz     short loc_14004C26B
0x14004c266  mov     sil, 6
0x14004c269  jmp     short loc_14004C29F
0x14004c26b  mov     eax, [rbp+0FCh]
0x14004c271  test    al, 4
0x14004c273  jz      short loc_14004C27F
0x14004c275  mov     edx, 2
0x14004c27a  mov     sil, dl
0x14004c27d  jmp     short loc_14004C2A4
0x14004c27f  test    r9, r9
0x14004c282  jz      short loc_14004C297
0x14004c284  mov     eax, [r9+240h]
0x14004c28b  cmp     eax, 0C0000483h
0x14004c290  jnz     short loc_14004C297
0x14004c292  mov     sil, 4
0x14004c295  jmp     short loc_14004C29F
0x14004c297  mov     sil, [r13+2]
0x14004c29b  shr     sil, 4
0x14004c29f  mov     edx, 2
0x14004c2a4  movzx   edi, byte ptr [r13+2]
0x14004c2a9  mov     ecx, edi
0x14004c2ab  mov     [rsp+88h+arg_0], 1
0x14004c2b3  and     ecx, 0Fh
0x14004c2b6  sub     ecx, 1
0x14004c2b9  jz      short loc_14004C2D6
0x14004c2bb  sub     ecx, 1
0x14004c2be  jz      short loc_14004C2D6
0x14004c2c0  sub     ecx, 1
0x14004c2c3  jz      loc_14004C39C
0x14004c2c9  sub     ecx, edx
0x14004c2cb  jz      short loc_14004C2D6
0x14004c2cd  cmp     ecx, 1
0x14004c2d0  jnz     loc_14004C4E3
0x14004c2d6  mov     rcx, r15; this
0x14004c2d9  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x14004c2de  test    al, al
0x14004c2e0  jnz     loc_14004C4E3
0x14004c2e6  shr     dil, 4
0x14004c2ea  cmp     sil, dil
0x14004c2ed  jz      loc_14004C4E3
0x14004c2f3  lea     rcx, [rbx+18h]; SpinLock
0x14004c2f7  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004c2fe  nop     dword ptr [rax+rax+00h]
0x14004c303  mov     byte ptr [rsp+88h+var_68], sil
0x14004c308  mov     r9b, 4
0x14004c30b  mov     esi, [rsp+88h+arg_8]
0x14004c312  mov     edx, r12d
0x14004c315  mov     r8d, esi
0x14004c318  mov     rcx, rbx
0x14004c31b  mov     bpl, al
0x14004c31e  call    ?SetColumnPendingStateInternal@SIO_RAID@@AEAAJKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnPendingStateInternal(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x14004c323  cmp     eax, 0C0E70013h
0x14004c328  jnz     short loc_14004C340
0x14004c32a  movzx   edx, word ptr [r13+0]
0x14004c32f  or      dx, 2
0x14004c333  mov     [rsp+88h+arg_0], 0
0x14004c33b  mov     [r13+0], dx
0x14004c340  xor     r14d, r14d
0x14004c343  lea     rcx, [rbx+18h]; SpinLock
0x14004c347  mov     dl, bpl; OldIrql
0x14004c34a  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004c351  nop     dword ptr [rax+rax+00h]
0x14004c356  cmp     [rsp+88h+arg_0], 0
0x14004c35e  jnz     loc_14004C4E3
0x14004c364  mov     r9, [rsp+88h+var_58]
0x14004c369  mov     r8d, r12d; unsigned int
0x14004c36c  mov     rcx, [rbx+8]
0x14004c370  mov     rdx, [rbx+10h]; unsigned __int64
0x14004c374  mov     r9d, [r9]; unsigned int
0x14004c377  mov     rcx, [rcx+148h]; this
0x14004c37e  call    ?FindColumnRecord@SDB_SPACE_CONFIG@@QEAAPEAVSDB_RECORD@@_KKK@Z; SDB_SPACE_CONFIG::FindColumnRecord(unsigned __int64,ulong,ulong)
0x14004c383  mov     rcx, rbx; this
0x14004c386  test    rax, rax
0x14004c389  jz      loc_14004C4D1
0x14004c38f  mov     rdx, rax; struct SDB_RECORD *
0x14004c392  call    ?UpdateColumnRecord@SIO_RAID@@AEAAJPEAVSDB_RECORD@@@Z; SIO_RAID::UpdateColumnRecord(SDB_RECORD *)
0x14004c397  jmp     loc_14004C4DC
0x14004c39c  shr     dil, 4
0x14004c3a0  cmp     sil, dil
0x14004c3a3  jnz     short loc_14004C3C2
0x14004c3a5  mov     rcx, r13; this
0x14004c3a8  call    ?CanRegenerate@SIO_COLUMN@@QEAAEXZ; SIO_COLUMN::CanRegenerate(void)
0x14004c3ad  test    al, al
0x14004c3af  jz      short loc_14004C3C2
0x14004c3b1  test    r9, r9
0x14004c3b4  jnz     loc_14004C4E3
0x14004c3ba  mov     sil, 1
0x14004c3bd  mov     dil, 4
0x14004c3c0  jmp     short loc_14004C3CB
0x14004c3c2  mov     dil, 4
0x14004c3c5  cmp     sil, 1
0x14004c3c9  jnz     short loc_14004C3F7
0x14004c3cb  mov     rax, [rsp+88h+var_50]
0x14004c3d0  cmp     [rbp+0F0h], rax
0x14004c3d7  ja      short loc_14004C3EA
0x14004c3d9  mov     rcx, [rbx+8]; this
0x14004c3dd  call    ?GetTopLevel@SIO_SPACE@@QEAAPEAV1@XZ; SIO_SPACE::GetTopLevel(void)
0x14004c3e2  mov     ecx, [rax+2Ch]
0x14004c3e5  test    cl, 8
0x14004c3e8  jz      short loc_14004C3F7
0x14004c3ea  mov     r14d, [rsp+88h+arg_8]
0x14004c3f2  mov     dil, 3
0x14004c3f5  jmp     short loc_14004C40D
0x14004c3f7  mov     r14d, [rsp+88h+arg_8]
0x14004c3ff  mov     edx, r12d; unsigned int
0x14004c402  mov     r8d, r14d; unsigned int
0x14004c405  mov     rcx, rbx; this
0x14004c408  call    ?InvalidateStripeState@SIO_RAID@@IEAAXKK@Z; SIO_RAID::InvalidateStripeState(ulong,ulong)
0x14004c40d  lea     rcx, [rbx+18h]; SpinLock
0x14004c411  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004c418  nop     dword ptr [rax+rax+00h]
0x14004c41d  mov     r15b, al
0x14004c420  movzx   eax, word ptr [r13+0]
0x14004c425  test    al, 4
0x14004c427  jz      short loc_14004C47C
0x14004c429  movzx   r10d, byte ptr [rbx+2Bh]
0x14004c42e  xor     r9d, r9d
0x14004c431  cmp     r9d, r10d
0x14004c434  jnb     short loc_14004C45C
0x14004c436  mov     r8d, r9d; unsigned int
0x14004c439  mov     edx, r12d; unsigned int
0x14004c43c  mov     rcx, rbx; this
0x14004c43f  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c444  cmp     [rax+14h], r14d
0x14004c448  jz      short loc_14004C44F
0x14004c44a  inc     r9d
0x14004c44d  jmp     short loc_14004C431
0x14004c44f  mov     r8d, r9d; unsigned int
0x14004c452  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x14004c457  mov     rcx, rax
0x14004c45a  jmp     short loc_14004C45E
0x14004c45c  xor     ecx, ecx
0x14004c45e  test    rcx, rcx
0x14004c461  jz      short loc_14004C47C
0x14004c463  mov     al, [rcx+2]
0x14004c466  and     al, 0Fh
0x14004c468  cmp     al, 1
0x14004c46a  jnz     short loc_14004C47C
0x14004c46c  test    byte ptr [rcx+3], 0Fh
0x14004c470  mov     eax, 8
0x14004c475  movzx   edi, dil
0x14004c479  cmovz   edi, eax
0x14004c47c  mov     r9b, dil
0x14004c47f  mov     byte ptr [rsp+88h+var_68], sil
0x14004c484  mov     r8d, r14d
0x14004c487  mov     edx, r12d
0x14004c48a  mov     rcx, rbx
0x14004c48d  call    ?SetColumnPendingStateInternal@SIO_RAID@@AEAAJKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnPendingStateInternal(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x14004c492  cmp     eax, 0C0E70013h
0x14004c497  jnz     short loc_14004C4AF
0x14004c499  movzx   eax, word ptr [r13+0]
0x14004c49e  or      ax, 2
0x14004c4a2  mov     [rsp+88h+arg_0], 0
0x14004c4aa  mov     [r13+0], ax
0x14004c4af  xor     r14d, r14d
0x14004c4b2  lea     rcx, [rbx+18h]; SpinLock
0x14004c4b6  mov     dl, r15b; OldIrql
0x14004c4b9  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004c4c0  nop     dword ptr [rax+rax+00h]
0x14004c4c5  mov     esi, [rsp+88h+arg_8]
0x14004c4cc  jmp     loc_14004C356
0x14004c4d1  mov     r8d, esi; unsigned int
0x14004c4d4  mov     edx, r12d; unsigned int
0x14004c4d7  call    ?CreateColumnRecord@SIO_RAID@@AEAAJKK@Z; SIO_RAID::CreateColumnRecord(ulong,ulong)
0x14004c4dc  mov     r14d, eax
0x14004c4df  test    eax, eax
0x14004c4e1  js      short loc_14004C526
0x14004c4e3  mov     ecx, [rsp+88h+arg_8]
0x14004c4ea  mov     r9d, [rsp+88h+arg_10]
0x14004c4f2  inc     ecx
0x14004c4f4  mov     r10d, [rsp+88h+arg_18]
0x14004c4fc  jmp     loc_14004C184
0x14004c501  mov     rcx, rbx; this
0x14004c504  inc     r12d
0x14004c507  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004c50c  mov     r9d, [rsp+88h+arg_10]
0x14004c514  mov     r10d, [rsp+88h+arg_18]
0x14004c51c  cmp     r12d, [rax+10h]
0x14004c520  jb      loc_14004C182
0x14004c526  mov     eax, r14d
0x14004c529  add     rsp, 48h
0x14004c52d  pop     r15
0x14004c52f  pop     r14
0x14004c531  pop     r13
0x14004c533  pop     r12
0x14004c535  pop     rdi
0x14004c536  pop     rsi
0x14004c537  pop     rbp
0x14004c538  pop     rbx
0x14004c539  retn
```
