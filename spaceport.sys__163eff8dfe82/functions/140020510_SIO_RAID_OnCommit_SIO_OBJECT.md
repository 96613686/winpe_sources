# SIO_RAID::OnCommit(SIO_OBJECT *)

- ea: `0x140020510`
- end: `0x140020ef1`
- name: `?OnCommit@SIO_RAID@@UEAAXPEAVSIO_OBJECT@@@Z`
- size: `2529`
- prototype: `void __fastcall(SIO_RAID *__hidden this, struct SIO_OBJECT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400204a0`
- `0x140024100`

## callees

- `0x140005940`
- `0x14000bb50`
- `0x14000e2e0`
- `0x140020510`
- `0x140023cb0`
- `0x14004af98`
- `0x14004b708`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020726`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400208dc`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400209ed`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020c98`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020d05`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020d36`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020726`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400208dc`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400209ed`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020c98`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020d05`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140020d36`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002066b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020851`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020962`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020c0b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020ce9`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002066b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020851`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020962`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020c0b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140020ce9`

## pseudocode

```c
void __fastcall SIO_RAID::OnCommit(SIO_RAID *this, unsigned __int64 a2)
{
  __int64 v2; // r15
  unsigned __int64 v3; // r8
  unsigned int i; // r12d
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // r14d
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbp
  __int64 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rdi
  KIRQL v16; // al
  __int64 v17; // rcx
  KIRQL v18; // r8
  __int64 v19; // rcx
  _WORD *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // di
  __int64 v24; // r9
  char v25; // di
  KIRQL v26; // al
  __int64 v27; // r9
  __int64 v28; // rcx
  KIRQL v29; // r14
  __int64 v30; // rcx
  __int64 v31; // rdi
  char v32; // al
  KIRQL v33; // al
  __int64 v34; // r9
  __int64 v35; // rcx
  KIRQL v36; // r14
  __int64 v37; // rcx
  __int64 v38; // rdi
  char v39; // al
  _QWORD *v40; // rcx
  __int64 v41; // rax
  unsigned int v42; // r15d
  char v43; // si
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int k; // r12d
  __int64 v47; // rdi
  __int64 v48; // rcx
  __int64 v49; // r14
  SIO_SPACE *v50; // rsi
  struct SIO_SPACE_DRIVE *DriveContext; // rax
  __int64 v52; // r10
  unsigned int v53; // edx
  char *v54; // r9
  unsigned __int64 v55; // r8
  int v56; // ecx
  unsigned __int64 v57; // rdx
  char *v58; // r8
  KIRQL v59; // al
  __int64 v60; // r9
  __int64 v61; // rcx
  KIRQL v62; // bp
  __int64 v63; // rcx
  __int64 v64; // rdi
  char v65; // al
  char v66; // al
  volatile LONG *v67; // rcx
  KIRQL v68; // dl
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rdx
  _WORD *v73; // rdi
  KIRQL v74; // al
  __int64 v75; // rax
  SIO_SPACE *v76; // rcx
  unsigned __int64 v77; // rsi
  _QWORD *v78; // rdx
  __int64 v79; // rdi
  SIO_SPACE_DRIVE *v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdx
  int v84; // eax
  __int16 v85; // ax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  int v92; // [rsp+20h] [rbp-58h]
  char v93; // [rsp+80h] [rbp+8h]
  unsigned int j; // [rsp+88h] [rbp+10h]
  _QWORD *v95; // [rsp+98h] [rbp+20h]

  v2 = 0;
  v93 = 0;
  v3 = a2;
  v95 = *(_QWORD **)(*((_QWORD *)this + 1) + 176LL);
  if ( a2 )
    v2 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, *((_QWORD *)this + 2));
  for ( i = 0; ; ++i )
  {
    v6 = *((_QWORD *)this + 4);
    v7 = v6 ? v6 + 88 : *((_QWORD *)this + 1) + 80LL;
    if ( i >= *(_DWORD *)(v7 + 16) )
      break;
    v8 = 0;
    for ( j = 0; v8 < *((unsigned __int8 *)this + 43); j = ++v8 )
    {
      v9 = *((_QWORD *)this + 4);
      if ( v9 )
        v10 = v9 + 88;
      else
        v10 = *((_QWORD *)this + 1) + 80LL;
      v11 = *((_QWORD *)this + 6) + 32LL * (i + *(_DWORD *)(v10 + 16) * v8);
      if ( (*(_BYTE *)(v11 + 2) & 0xF) == 7 )
        continue;
      if ( v2 )
      {
        if ( !*(_BYTE *)(v2 + 43) )
          goto LABEL_21;
        v3 = *(_QWORD *)(v2 + 32);
        a2 = 0;
        v12 = *(_QWORD *)(v2 + 48);
        while ( 1 )
        {
          v13 = v3 ? v3 + 88 : *(_QWORD *)(v2 + 8) + 80LL;
          if ( *(_DWORD *)(32LL * (i + *(_DWORD *)(v13 + 16) * (_DWORD)a2) + v12 + 16) == *(_DWORD *)(v11 + 16) )
            break;
          a2 = (unsigned int)(a2 + 1);
          if ( (unsigned int)a2 >= *(unsigned __int8 *)(v2 + 43) )
            goto LABEL_21;
        }
        if ( (_DWORD)a2 == -1 )
        {
LABEL_21:
          v14 = 0;
        }
        else
        {
          if ( v3 )
            a2 = (unsigned int)(*(_DWORD *)(v3 + 104) * a2);
          else
            a2 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v2 + 8) + 96LL) * a2);
          v14 = v12 + 32LL * (i + (unsigned int)a2);
        }
        if ( v14 )
        {
          *(_WORD *)v11 |= *(_WORD *)v14 & 0x40;
          if ( (*(_WORD *)v14 & 0x80u) != 0 )
          {
            v15 = *(_QWORD *)(*((_QWORD *)this + 1) + 176LL);
            v16 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
            v17 = *((_QWORD *)this + 4);
            v18 = v16;
            if ( v17 )
              v19 = v17 + 88;
            else
              v19 = *((_QWORD *)this + 1) + 80LL;
            v20 = (_WORD *)(*((_QWORD *)this + 6) + 32LL * (i + *(_DWORD *)(v19 + 16) * v8));
            if ( (*v20 & 0x80u) == 0 )
            {
              _InterlockedIncrement64((volatile signed __int64 *)(v15 + 312));
              v21 = *((_QWORD *)this + 4);
              if ( v21 )
                v22 = v21 + 56;
              else
                v22 = *((_QWORD *)this + 1) + 48LL;
              _InterlockedAdd64((volatile signed __int64 *)(v15 + 352), *(_QWORD *)(v22 + 8));
              *v20 |= 0x80u;
            }
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v18);
          }
        }
      }
      else
      {
        v14 = 0;
      }
      if ( (*(_BYTE *)(v11 + 2) & 0xF) == 1 )
      {
        if ( v14 )
        {
          if ( v2 )
          {
            if ( (*(_BYTE *)(v14 + 2) & 0xF) == 2
              && (*(unsigned __int8 (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)v2 + 176LL))(
                   v2,
                   a2,
                   v3) )
            {
              if ( (*(_DWORD *)(*((_QWORD *)this + 1) + 44LL) & 1) == 0 )
              {
                v33 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
                v35 = *((_QWORD *)this + 4);
                v36 = v33;
                if ( v35 )
                  v37 = v35 + 88;
                else
                  v37 = *((_QWORD *)this + 1) + 80LL;
                v38 = *((_QWORD *)this + 6) + 32LL * (i + *(_DWORD *)(v37 + 16) * j);
                if ( (*(_WORD *)v38 & 2) == 0 && (*(_BYTE *)(v38 + 3) & 0xFu) <= 1 )
                {
                  v39 = *(_BYTE *)(v38 + 2) & 0xF;
                  if ( v39 == 1 || (LOBYTE(v34) = 0, v39 == 2) )
                    LOBYTE(v34) = 1;
                  if ( !(*(unsigned __int8 (__fastcall **)(SIO_RAID *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 168LL))(
                          this,
                          i,
                          j,
                          v34) )
                    *(_BYTE *)(v38 + 3) = 19;
                }
                ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v36);
                v8 = j;
                SIO_RAID::InvalidateStripeState(this, i, j);
                v93 = 1;
              }
            }
            else
            {
              *(_WORD *)v11 |= *(_WORD *)v14 & 1;
            }
          }
          goto LABEL_87;
        }
      }
      else
      {
        switch ( *(_BYTE *)(v11 + 2) & 0xF )
        {
          case 2:
            v25 = (*(__int64 (__fastcall **)(SIO_RAID *, unsigned __int64, unsigned __int64))(*(_QWORD *)this + 184LL))(
                    this,
                    a2,
                    v3);
            if ( v2 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v2 + 184LL))(v2) || v25 )
            {
              v26 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
              v28 = *((_QWORD *)this + 4);
              v29 = v26;
              if ( v28 )
                v30 = v28 + 88;
              else
                v30 = *((_QWORD *)this + 1) + 80LL;
              v31 = *((_QWORD *)this + 6) + 32LL * (i + *(_DWORD *)(v30 + 16) * j);
              if ( (*(_WORD *)v31 & 2) == 0 && (*(_BYTE *)(v31 + 3) & 0xFu) <= 1 )
              {
                v32 = *(_BYTE *)(v31 + 2) & 0xF;
                if ( v32 == 1 || (LOBYTE(v27) = 0, v32 == 2) )
                  LOBYTE(v27) = 1;
                if ( !(*(unsigned __int8 (__fastcall **)(SIO_RAID *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 168LL))(
                        this,
                        i,
                        j,
                        v27) )
                  *(_BYTE *)(v31 + 3) = 19;
              }
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v29);
              v8 = j;
              SIO_RAID::InvalidateStripeState(this, i, j);
              v93 = 1;
            }
LABEL_68:
            if ( v14 )
              goto LABEL_87;
            continue;
          case 3:
            v23 = (*(__int64 (__fastcall **)(SIO_RAID *, unsigned __int64, unsigned __int64))(*(_QWORD *)this + 184LL))(
                    this,
                    a2,
                    v3);
            if ( v2
              && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v2 + 176LL))(v2)
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v2 + 184LL))(v2)
               || (*(_DWORD *)(*((_QWORD *)this + 1) + 44LL) & 1) == 0)
              || v23 )
            {
              SIO_RAID::InvalidateStripeState(this, i, v8);
            }
            break;
          case 4:
            break;
          default:
            goto LABEL_68;
        }
        if ( !SIO_SPACE::GetDrive(*((SIO_SPACE **)this + 1), *(_DWORD *)(v11 + 4)) )
          goto LABEL_68;
        if ( v14 )
        {
          v24 = *(_BYTE *)(v14 + 2) & 0xF;
          if ( (unsigned __int8)(v24 - 5) <= 1u )
          {
            LOBYTE(v92) = *(_BYTE *)(v11 + 2) >> 4;
            SIO_RAID::SetColumnActiveState(this, i, v8, v24, v92);
          }
LABEL_87:
          v3 = v11;
          if ( ((*(_BYTE *)(v11 + 2) ^ *(_BYTE *)(v14 + 2)) & 0xF) == 0 )
          {
            a2 = *(unsigned __int8 *)(v14 + 3);
            *(_BYTE *)(v11 + 3) ^= (a2 ^ *(_BYTE *)(v11 + 3)) & 0xF;
            LOBYTE(a2) = *(_BYTE *)(v14 + 3) ^ (*(_BYTE *)(v14 + 3) ^ a2) & 0xF;
            *(_BYTE *)(v11 + 3) = a2;
          }
        }
      }
    }
  }
  if ( v2 )
  {
    if ( *(char *)(v2 + 40) < 0 )
      SIO_RAID::CheckUnmapped(this);
    if ( *(_QWORD *)(*((_QWORD *)this + 1) + 376LL) && !*((_QWORD *)this + 8) )
    {
      *((_QWORD *)this + 8) = *(_QWORD *)(v2 + 64);
      *(_QWORD *)(v2 + 64) = 0;
    }
  }
  else
  {
    v40 = (_QWORD *)*((_QWORD *)this + 1);
    v41 = v40[47];
    if ( v41 && *(_QWORD *)(v41 + 16) )
      (*(void (__fastcall **)(_QWORD *, unsigned __int64, unsigned __int64))(*v40 + 128LL))(v40, a2, v3);
  }
  v42 = 0;
  v43 = v93;
  while ( 1 )
  {
    v44 = *((_QWORD *)this + 4);
    v45 = v44 ? v44 + 88 : *((_QWORD *)this + 1) + 80LL;
    if ( v42 >= *(_DWORD *)(v45 + 16) )
      break;
    for ( k = 0; k < *((unsigned __int8 *)this + 43); ++k )
    {
      v47 = *((_QWORD *)this + 4);
      if ( v47 )
        v48 = v47 + 88;
      else
        v48 = *((_QWORD *)this + 1) + 80LL;
      v49 = *((_QWORD *)this + 6) + 32LL * (v42 + *(_DWORD *)(v48 + 16) * k);
      if ( (*(_BYTE *)(v49 + 2) & 0xF) != 1 && (*(_BYTE *)(v49 + 2) & 0xF) != 3 )
        goto LABEL_143;
      v50 = (SIO_SPACE *)*((_QWORD *)this + 1);
      DriveContext = SIO_SPACE::GetDriveContext(v50, *(_DWORD *)(v49 + 4));
      if ( !DriveContext )
        goto LABEL_142;
      v52 = *((_QWORD *)DriveContext + 1);
      if ( !v52 )
        goto LABEL_142;
      v53 = *((_DWORD *)DriveContext + 6);
      v54 = (char *)DriveContext + 32;
      v55 = *(_QWORD *)(v49 + 8);
      v56 = 0;
      if ( !v53 )
LABEL_116:
        __fastfail(0x50u);
      while ( v55 >= *(_QWORD *)&v54[16 * v56] )
      {
        if ( ++v56 >= v53 )
          goto LABEL_116;
      }
      v57 = v55 + *(_QWORD *)&v54[16 * v56 + 8];
      v58 = (char *)(v47 + 56);
      if ( !v47 )
        v58 = (char *)v50 + 48;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(*(_QWORD *)v52 + 104LL))(
              *((_QWORD *)DriveContext + 1),
              v57,
              *((_QWORD *)v58 + 1)) )
        goto LABEL_142;
      if ( (*(_BYTE *)(v49 + 2) & 0xF) == 1 )
      {
        v59 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
        v61 = *((_QWORD *)this + 4);
        v62 = v59;
        if ( v61 )
          v63 = v61 + 88;
        else
          v63 = *((_QWORD *)this + 1) + 80LL;
        v64 = *((_QWORD *)this + 6) + 32LL * (v42 + *(_DWORD *)(v63 + 16) * k);
        if ( (*(_WORD *)v64 & 2) != 0 || (*(_BYTE *)(v64 + 3) & 0xFu) > 1 )
        {
          v68 = v59;
          v67 = (volatile LONG *)((char *)this + 24);
          goto LABEL_139;
        }
        v65 = *(_BYTE *)(v64 + 2) & 0xF;
        if ( v65 == 1 || (LOBYTE(v60) = 0, v65 == 2) )
          LOBYTE(v60) = 1;
        v66 = (*(__int64 (__fastcall **)(SIO_RAID *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 168LL))(
                this,
                v42,
                k,
                v60);
        v67 = (volatile LONG *)((char *)this + 24);
        v68 = v62;
        if ( !v66 )
        {
          *(_BYTE *)(v64 + 3) = 51;
LABEL_139:
          ExReleaseSpinLockExclusive(v67, v68);
          v43 = 1;
          v93 = 1;
          goto LABEL_132;
        }
        ExReleaseSpinLockExclusive(v67, v62);
      }
      v43 = v93;
LABEL_132:
      v69 = *((_QWORD *)this + 1);
      if ( (*(_DWORD *)(v69 + 44) & 8) == 0 )
        goto LABEL_143;
      v70 = *((_QWORD *)this + 4);
      v71 = v69 + 80;
      v72 = v70 + 88;
      if ( !v70 )
        v72 = v71;
      v73 = (_WORD *)(*((_QWORD *)this + 6) + 32LL * (v42 + *(_DWORD *)(v72 + 16) * k));
      v74 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
      *v73 &= ~0x40u;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v74);
      v75 = *((_QWORD *)this + 4);
      v76 = (SIO_SPACE *)*((_QWORD *)this + 1);
      if ( v75 )
      {
        v77 = *(_QWORD *)(v75 + 64);
        v78 = (_QWORD *)(v75 + 88);
      }
      else
      {
        v77 = *((_QWORD *)v76 + 7);
        v78 = (_QWORD *)((char *)v76 + 80);
      }
      v79 = *((_QWORD *)this + 6) + 32LL * (v42 + *((_DWORD *)v78 + 4) * k);
      v80 = SIO_SPACE::GetDriveContext(v76, *(_DWORD *)(v79 + 4));
      SIO_SPACE_DRIVE::SetStripeState(v80, *(_QWORD *)(v79 + 8), v77, 0);
LABEL_142:
      v43 = v93;
LABEL_143:
      if ( *(_DWORD *)(v49 + 20) != -1 && (*(_WORD *)v49 & 4) == 0 )
      {
        while ( 1 )
        {
          v81 = *((_QWORD *)this + 4);
          v82 = v81 ? v81 + 88 : *((_QWORD *)this + 1) + 80LL;
          v83 = *((_QWORD *)this + 6) + 32LL * (v42 + *(_DWORD *)(v49 + 20) * *(_DWORD *)(v82 + 16));
          v84 = *(_DWORD *)(v83 + 20);
          if ( v84 == -1 )
            break;
          *(_DWORD *)(v49 + 20) = v84;
          v85 = *(_WORD *)v83 & 0xFFFB;
          *(_DWORD *)(v83 + 20) = -1;
          *(_WORD *)v83 = v85;
          if ( (*(_BYTE *)(v83 + 2) & 0xF) != 8 )
          {
            *(_BYTE *)(v83 + 3) = 120;
            v43 = 1;
          }
          ++v95[38];
          v86 = *((_QWORD *)this + 4);
          if ( v86 )
            v87 = *(_QWORD *)(v86 + 64);
          else
            v87 = *(_QWORD *)(*((_QWORD *)this + 1) + 56LL);
          v95[43] += v87;
        }
        v93 = v43;
        if ( (*(_WORD *)v49 & 0x10) != 0 )
        {
          ++v95[37];
          v88 = *((_QWORD *)this + 4);
          if ( v88 )
            v89 = *(_QWORD *)(v88 + 64);
          else
            v89 = *(_QWORD *)(*((_QWORD *)this + 1) + 56LL);
          v95[42] += v89;
        }
        else
        {
          ++v95[36];
          v90 = *((_QWORD *)this + 4);
          if ( v90 )
            v91 = v90 + 56;
          else
            v91 = *((_QWORD *)this + 1) + 48LL;
          v95[41] += *(_QWORD *)(v91 + 8);
        }
      }
    }
    ++v42;
  }
  if ( v43 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1), 0, 65531);
}

```

## disassembly

```asm
0x140020510  push    rbx
0x140020512  push    rbp
0x140020513  push    rsi
0x140020514  push    rdi
0x140020515  push    r12
0x140020517  push    r13
0x140020519  push    r14
0x14002051b  push    r15
0x14002051d  sub     rsp, 38h
0x140020521  xor     al, al
0x140020523  xor     r15d, r15d
0x140020526  mov     [rsp+78h+arg_0], al
0x14002052d  mov     r8, rdx
0x140020530  mov     rax, [rcx+8]
0x140020534  mov     rbx, rcx
0x140020537  mov     r13, [rax+0B0h]
0x14002053e  mov     [rsp+78h+arg_18], r13
0x140020546  test    rdx, rdx
0x140020549  jz      short loc_140020561
0x14002054b  mov     rax, [rdx]
0x14002054e  mov     rdx, [rcx+10h]
0x140020552  mov     rcx, r8
0x140020555  mov     rax, [rax+68h]
0x140020559  call    _guard_dispatch_icall
0x14002055e  mov     r15, rax
0x140020561  xor     r12d, r12d
0x140020564  mov     r13d, 80h
0x14002056a  nop     word ptr [rax+rax+00h]
0x140020570  mov     rax, [rbx+20h]
0x140020574  test    rax, rax
0x140020577  jz      short loc_14002057F
0x140020579  add     rax, 58h ; 'X'
0x14002057d  jmp     short loc_140020587
0x14002057f  mov     rax, [rbx+8]
0x140020583  add     rax, 50h ; 'P'
0x140020587  cmp     r12d, [rax+10h]
0x14002058b  jnb     loc_140020A86
0x140020591  xor     r14d, r14d
0x140020594  mov     [rsp+78h+arg_8], r14d
0x14002059c  cmp     [rbx+2Bh], r14b
0x1400205a0  jbe     loc_140020A7E
0x1400205a6  mov     rcx, [rbx+20h]
0x1400205aa  test    rcx, rcx
0x1400205ad  jz      short loc_1400205B5
0x1400205af  add     rcx, 58h ; 'X'
0x1400205b3  jmp     short loc_1400205BD
0x1400205b5  mov     rcx, [rbx+8]
0x1400205b9  add     rcx, 50h ; 'P'
0x1400205bd  mov     ebp, r14d
0x1400205c0  imul    ebp, [rcx+10h]
0x1400205c4  add     ebp, r12d
0x1400205c7  shl     rbp, 5
0x1400205cb  add     rbp, [rbx+30h]
0x1400205cf  mov     [rsp+78h+arg_10], rbp
0x1400205d7  movzx   eax, byte ptr [rbp+2]
0x1400205db  and     al, 0Fh
0x1400205dd  cmp     al, 7
0x1400205df  jz      loc_140020A66
0x1400205e5  test    r15, r15
0x1400205e8  jz      loc_140020734
0x1400205ee  movzx   r9d, byte ptr [r15+2Bh]
0x1400205f3  test    r9d, r9d
0x1400205f6  jz      short loc_140020634
0x1400205f8  mov     r8, [r15+20h]
0x1400205fc  xor     edx, edx
0x1400205fe  mov     r11d, [rbp+10h]
0x140020602  mov     r10, [r15+30h]
0x140020606  test    r8, r8
0x140020609  jz      short loc_140020611
0x14002060b  lea     rcx, [r8+58h]
0x14002060f  jmp     short loc_140020619
0x140020611  mov     rcx, [r15+8]
0x140020615  add     rcx, 50h ; 'P'
0x140020619  mov     eax, edx
0x14002061b  imul    eax, [rcx+10h]
0x14002061f  add     eax, r12d
0x140020622  shl     rax, 5
0x140020626  cmp     [rax+r10+10h], r11d
0x14002062b  jz      short loc_14002068A
0x14002062d  inc     edx
0x14002062f  cmp     edx, r9d
0x140020632  jb      short loc_140020606
0x140020634  xor     esi, esi
0x140020636  test    rsi, rsi
0x140020639  jz      loc_140020736
0x14002063f  movzx   ecx, word ptr [rsi]
0x140020642  movzx   eax, word ptr [rbp+0]
0x140020646  and     cx, 40h
0x14002064a  or      cx, ax
0x14002064d  mov     [rbp+0], cx
0x140020651  movzx   eax, word ptr [rsi]
0x140020654  test    al, al
0x140020656  jns     loc_140020736
0x14002065c  mov     rax, [rbx+8]
0x140020660  lea     rcx, [rbx+18h]; SpinLock
0x140020664  mov     rdi, [rax+0B0h]
0x14002066b  call    cs:__imp_ExAcquireSpinLockExclusive
0x140020672  nop     dword ptr [rax+rax+00h]
0x140020677  mov     rcx, [rbx+20h]
0x14002067b  movzx   r8d, al
0x14002067f  test    rcx, rcx
0x140020682  jz      short loc_1400206C8
0x140020684  add     rcx, 58h ; 'X'
0x140020688  jmp     short loc_1400206D0
0x14002068a  cmp     edx, 0FFFFFFFFh
0x14002068d  jz      short loc_140020634
0x14002068f  mov     rax, r8
0x140020692  test    r8, r8
0x140020695  jz      short loc_1400206AC
0x140020697  imul    edx, [rax+68h]
0x14002069b  add     rax, 58h ; 'X'
0x14002069f  lea     esi, [r12+rdx]
0x1400206a3  shl     rsi, 5
0x1400206a7  add     rsi, r10
0x1400206aa  jmp     short loc_140020636
0x1400206ac  mov     rax, [r15+8]
0x1400206b0  add     rax, 50h ; 'P'
0x1400206b4  imul    edx, [rax+10h]
0x1400206b8  lea     esi, [r12+rdx]
0x1400206bc  shl     rsi, 5
0x1400206c0  add     rsi, r10
0x1400206c3  jmp     loc_140020636
0x1400206c8  mov     rcx, [rbx+8]
0x1400206cc  add     rcx, 50h ; 'P'
0x1400206d0  mov     edx, r14d
0x1400206d3  imul    edx, [rcx+10h]
0x1400206d7  add     edx, r12d
0x1400206da  shl     rdx, 5
0x1400206de  add     rdx, [rbx+30h]
0x1400206e2  movzx   eax, word ptr [rdx]
0x1400206e5  test    al, al
0x1400206e7  js      short loc_14002071E
0x1400206e9  lock inc qword ptr [rdi+138h]
0x1400206f1  mov     rax, [rbx+20h]
0x1400206f5  test    rax, rax
0x1400206f8  jz      short loc_140020700
0x1400206fa  add     rax, 38h ; '8'
0x1400206fe  jmp     short loc_140020708
0x140020700  mov     rax, [rbx+8]
0x140020704  add     rax, 30h ; '0'
0x140020708  mov     rax, [rax+8]
0x14002070c  lock add [rdi+160h], rax
0x140020714  movzx   eax, word ptr [rdx]
0x140020717  or      ax, r13w
0x14002071b  mov     [rdx], ax
0x14002071e  movzx   edx, r8b; OldIrql
0x140020722  lea     rcx, [rbx+18h]; SpinLock
0x140020726  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002072d  nop     dword ptr [rax+rax+00h]
0x140020732  jmp     short loc_140020736
0x140020734  xor     esi, esi
0x140020736  movzx   ecx, byte ptr [rbp+2]
0x14002073a  and     ecx, 0Fh
0x14002073d  sub     ecx, 1
0x140020740  jz      loc_140020914
0x140020746  sub     ecx, 1
0x140020749  jz      loc_140020814
0x14002074f  sub     ecx, 1
0x140020752  jz      short loc_14002075E
0x140020754  cmp     ecx, 1
0x140020757  jz      short loc_1400207C3
0x140020759  jmp     loc_140020906
0x14002075e  mov     rax, [rbx]
0x140020761  mov     rcx, rbx
0x140020764  mov     rax, [rax+0B8h]
0x14002076b  call    _guard_dispatch_icall
0x140020770  movzx   edi, al
0x140020773  test    r15, r15
0x140020776  jz      short loc_1400207B0
0x140020778  mov     rcx, [r15]
0x14002077b  mov     rax, [rcx+0B0h]
0x140020782  mov     rcx, r15
0x140020785  call    _guard_dispatch_icall
0x14002078a  test    al, al
0x14002078c  jz      short loc_1400207B0
0x14002078e  mov     rcx, [r15]
0x140020791  mov     rax, [rcx+0B8h]
0x140020798  mov     rcx, r15
0x14002079b  call    _guard_dispatch_icall
0x1400207a0  test    al, al
0x1400207a2  jnz     short loc_1400207B5
0x1400207a4  mov     rax, [rbx+8]
0x1400207a8  mov     ecx, [rax+2Ch]
0x1400207ab  test    cl, 1
0x1400207ae  jz      short loc_1400207B5
0x1400207b0  test    dil, dil
0x1400207b3  jz      short loc_1400207C3
0x1400207b5  mov     r8d, r14d; unsigned int
0x1400207b8  mov     edx, r12d; unsigned int
0x1400207bb  mov     rcx, rbx; this
0x1400207be  call    ?InvalidateStripeState@SIO_RAID@@IEAAXKK@Z; SIO_RAID::InvalidateStripeState(ulong,ulong)
0x1400207c3  mov     edx, [rbp+4]; unsigned int
0x1400207c6  mov     rcx, [rbx+8]; this
0x1400207ca  call    ?GetDrive@SIO_SPACE@@QEAAPEAVSC_DRIVE@@K@Z; SIO_SPACE::GetDrive(ulong)
0x1400207cf  test    rax, rax
0x1400207d2  jz      loc_140020906
0x1400207d8  test    rsi, rsi
0x1400207db  jz      loc_140020A66
0x1400207e1  movzx   r9d, byte ptr [rsi+2]
0x1400207e6  and     r9b, 0Fh
0x1400207ea  lea     eax, [r9-5]
0x1400207ee  cmp     al, 1
0x1400207f0  ja      loc_140020A2B
0x1400207f6  movzx   eax, byte ptr [rbp+2]
0x1400207fa  mov     r8d, r14d
0x1400207fd  shr     al, 4
0x140020800  mov     edx, r12d
0x140020803  mov     rcx, rbx
0x140020806  mov     byte ptr [rsp+78h+var_58], al
0x14002080a  call    ?SetColumnActiveState@SIO_RAID@@IEAAXKKW4_SC_COLUMN_STATE@@W4_SC_COLUMN_REASON@@@Z; SIO_RAID::SetColumnActiveState(ulong,ulong,_SC_COLUMN_STATE,_SC_COLUMN_REASON)
0x14002080f  jmp     loc_140020A2B
0x140020814  mov     rax, [rbx]
0x140020817  mov     rcx, rbx
0x14002081a  mov     rax, [rax+0B8h]
0x140020821  call    _guard_dispatch_icall
0x140020826  movzx   edi, al
0x140020829  test    r15, r15
0x14002082c  jz      short loc_140020844
0x14002082e  mov     rcx, [r15]
0x140020831  mov     rax, [rcx+0B8h]
0x140020838  mov     rcx, r15
0x14002083b  call    _guard_dispatch_icall
0x140020840  test    al, al
0x140020842  jnz     short loc_14002084D
0x140020844  test    dil, dil
0x140020847  jz      loc_140020906
0x14002084d  lea     rcx, [rbx+18h]; SpinLock
0x140020851  call    cs:__imp_ExAcquireSpinLockExclusive
0x140020858  nop     dword ptr [rax+rax+00h]
0x14002085d  mov     rcx, [rbx+20h]
0x140020861  movzx   r14d, al
0x140020865  test    rcx, rcx
0x140020868  jz      short loc_140020870
0x14002086a  add     rcx, 58h ; 'X'
0x14002086e  jmp     short loc_140020878
0x140020870  mov     rcx, [rbx+8]
0x140020874  add     rcx, 50h ; 'P'
0x140020878  mov     r8d, [rsp+78h+arg_8]
0x140020880  mov     edi, r8d
0x140020883  imul    edi, [rcx+10h]
0x140020887  add     edi, r12d
0x14002088a  shl     rdi, 5
0x14002088e  add     rdi, [rbx+30h]
0x140020892  movzx   eax, word ptr [rdi]
0x140020895  test    al, 2
0x140020897  jnz     short loc_1400208D4
0x140020899  movzx   eax, byte ptr [rdi+3]
0x14002089d  and     al, 0Fh
0x14002089f  cmp     al, 1
0x1400208a1  ja      short loc_1400208D4
0x1400208a3  movzx   eax, byte ptr [rdi+2]
0x1400208a7  and     al, 0Fh
0x1400208a9  cmp     al, 1
0x1400208ab  jz      short loc_1400208B4
0x1400208ad  xor     r9b, r9b
0x1400208b0  cmp     al, 2
0x1400208b2  jnz     short loc_1400208B7
0x1400208b4  mov     r9b, 1
0x1400208b7  mov     rax, [rbx]
0x1400208ba  mov     edx, r12d
0x1400208bd  mov     rcx, rbx
0x1400208c0  mov     rax, [rax+0A8h]
0x1400208c7  call    _guard_dispatch_icall
0x1400208cc  test    al, al
0x1400208ce  jnz     short loc_1400208D4
0x1400208d0  mov     byte ptr [rdi+3], 13h
0x1400208d4  movzx   edx, r14b; OldIrql
0x1400208d8  lea     rcx, [rbx+18h]; SpinLock
0x1400208dc  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400208e3  nop     dword ptr [rax+rax+00h]
0x1400208e8  mov     r14d, [rsp+78h+arg_8]
0x1400208f0  mov     edx, r12d; unsigned int
0x1400208f3  mov     r8d, r14d; unsigned int
0x1400208f6  mov     rcx, rbx; this
0x1400208f9  call    ?InvalidateStripeState@SIO_RAID@@IEAAXKK@Z; SIO_RAID::InvalidateStripeState(ulong,ulong)
0x1400208fe  mov     [rsp+78h+arg_0], 1
0x140020906  test    rsi, rsi
0x140020909  jz      loc_140020A66
0x14002090f  jmp     loc_140020A2B
0x140020914  test    rsi, rsi
0x140020917  jz      loc_140020A66
0x14002091d  test    r15, r15
0x140020920  jz      loc_140020A2B
0x140020926  movzx   eax, byte ptr [rsi+2]
0x14002092a  and     al, 0Fh
0x14002092c  cmp     al, 2
0x14002092e  jnz     loc_140020A19
0x140020934  mov     rax, [r15]
0x140020937  mov     rcx, r15
0x14002093a  mov     rax, [rax+0B0h]
0x140020941  call    _guard_dispatch_icall
0x140020946  test    al, al
0x140020948  jz      loc_140020A19
0x14002094e  mov     rax, [rbx+8]
0x140020952  mov     ecx, [rax+2Ch]
0x140020955  test    cl, 1
0x140020958  jnz     loc_140020A2B
0x14002095e  lea     rcx, [rbx+18h]; SpinLock
0x140020962  call    cs:__imp_ExAcquireSpinLockExclusive
0x140020969  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
