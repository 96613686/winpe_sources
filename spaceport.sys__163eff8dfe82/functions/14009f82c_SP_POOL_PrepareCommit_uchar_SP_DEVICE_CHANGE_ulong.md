# SP_POOL::PrepareCommit(uchar *,_SP_DEVICE_CHANGE * *,ulong *)

- ea: `0x14009f82c`
- end: `0x14009fd62`
- name: `?PrepareCommit@SP_POOL@@AEAAJPEAEPEAPEAU_SP_DEVICE_CHANGE@@PEAK@Z`
- size: `1334`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this, unsigned __int8 *, struct _SP_DEVICE_CHANGE **, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14009e404`

## callees

- `0x1400044d0`
- `0x14000ba20`
- `0x14000c630`
- `0x1400187f0`
- `0x14001c760`
- `0x14001e4a0`
- `0x1400216f0`
- `0x1400268c0`
- `0x14002fdb0`
- `0x14004074c`
- `0x14005f100`
- `0x140068150`
- `0x14008c3c0`
- `0x14008f898`
- `0x14009cb38`
- `0x14009cdc0`
- `0x14009d8a4`
- `0x14009eb10`
- `0x14009eb60`
- `0x14009f82c`
- `0x1400a48e8`
- `0x1400b107c`
- `0x1400b15fc`
- `0x1400b6cb0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14009fc90`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14009fc90`

## pseudocode

```c
__int64 __fastcall SP_POOL::PrepareCommit(
        SP_POOL *this,
        unsigned __int8 *a2,
        struct _SP_DEVICE_CHANGE **a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  int v5; // edi
  SDB_RECORD *i; // r8
  SDB_RECORD *RecordByType; // rax
  __int64 v9; // rdx
  SDB_RECORD *v10; // rbp
  struct SDB_OBJECT *Object; // rsi
  __int64 v12; // rcx
  SP_SPACE *v13; // rax
  SP_SPACE *v14; // rax
  unsigned __int64 *v15; // rbx
  SIO_LOG *v16; // rax
  SIO_LOG *v17; // rax
  SIO_LOG *v18; // rsi
  void (__fastcall *v19)(SIO_LOG *, __int64); // rax
  __int64 j; // r8
  __int64 v21; // rsi
  unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  __int64 RecordByRecordId; // rbx
  struct SDB_OBJECT *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // rdx
  struct _SP_DEVICE_CHANGE *v30; // rbp
  SDB_RECORD *v31; // rax
  __int64 v32; // rdx
  SP_POOL *k; // rbx
  SDB_RECORD *v34; // r13
  struct SDB_OBJECT *v35; // rax
  struct SDB_OBJECT *v36; // rsi
  char v37; // r12
  __int64 v38; // r14
  struct SDB_SPACE *v39; // rdx
  SP_POOL *v40; // rcx
  struct _GUID v41; // xmm1
  SP_POOL *v42; // rcx
  __int64 v43; // r15
  __int64 v44; // rcx
  int v45; // eax
  SP_SPACE *v46; // rbx
  SP_SPACE *v47; // rax
  SP_SPACE *v48; // rax
  __int64 v49; // r12
  unsigned int v50; // ebx
  int v51; // esi
  int *UnbiasedInterruptTime; // rax
  unsigned __int64 v54; // [rsp+28h] [rbp-A0h]
  unsigned __int64 v55; // [rsp+30h] [rbp-98h]
  __int64 v56; // [rsp+38h] [rbp-90h]
  unsigned int v57; // [rsp+40h] [rbp-88h]
  char v58; // [rsp+48h] [rbp-80h]
  struct _GUID v59; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID v60; // [rsp+60h] [rbp-68h] BYREF
  struct _GUID v61; // [rsp+70h] [rbp-58h] BYREF
  unsigned __int8 *v63; // [rsp+D8h] [rbp+10h]

  v63 = a2;
  v4 = *((_QWORD *)this + 6);
  v5 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)(v4 + 272) + 30LL) & 0x40) != 0 )
    *a2 = 1;
  for ( i = 0; ; i = v10 )
  {
    LOBYTE(a2) = 3;
    RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(v4, a2, i);
    v10 = RecordByType;
    if ( !RecordByType )
      goto LABEL_15;
    Object = SDB_RECORD::GetObject(RecordByType);
    if ( *(char *)(v12 + 30) < 0 && *((_BYTE *)Object + 66) == 7 )
      break;
  }
  v13 = (SP_SPACE *)SIO_SPACE::operator new(0x4E0u);
  if ( !v13 )
    return (unsigned int)-1073741670;
  v14 = SP_SPACE::SP_SPACE(v13);
  if ( (v15 = (unsigned __int64 *)v14) == 0 )
    return (unsigned int)-1073741670;
  v5 = SP_SPACE::Initialize(v14, Object, 0);
  if ( v5 < 0 )
    goto LABEL_24;
  v16 = (SIO_LOG *)SC_ENV_ALLOCATOR::operator new(0x148u, 0x58587053u, 0, 0);
  if ( !v16 || (v17 = SIO_LOG::SIO_LOG(v16), (v18 = v17) == 0) )
  {
    v5 = -1073741670;
    goto LABEL_24;
  }
  v5 = SIO_LOG::Initialize(v17, 2u, (struct SIO_SPACE *)v15, 1u, 0, v15[14], 0);
  v19 = **(void (__fastcall ***)(SIO_LOG *, __int64))v18;
  if ( v5 < 0 )
  {
    v19(v18, 1);
LABEL_24:
    (*(void (__fastcall **)(unsigned __int64 *, __int64))*v15)(v15, 1);
    return (unsigned int)v5;
  }
  v19(v18, 1);
  (*(void (__fastcall **)(unsigned __int64 *, __int64))*v15)(v15, 1);
  *((_WORD *)v10 + 15) &= ~0x80u;
LABEL_15:
  for ( j = 0; ; j = RecordByRecordId )
  {
    v21 = *((_QWORD *)this + 6);
    LOBYTE(v9) = 3;
    v22 = (unsigned __int16 *)SDB_POOL_CONFIG::GetRecordByType(v21, v9, j);
    RecordByRecordId = (__int64)v22;
    if ( !v22 )
      break;
    v9 = v22[15];
    if ( (v9 & 0x10) != 0 )
    {
      v25 = SDB_RECORD::GetObject((SDB_RECORD *)v22);
      if ( *((_DWORD *)v25 + 47) )
      {
        LOWORD(v9) = v9 & 0xFFEF;
        *(_WORD *)(RecordByRecordId + 30) = v9;
        LOBYTE(v9) = 3;
        RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)this + 6), v9, *((_DWORD *)v25 + 47));
        v5 = SDB_RECORD::PreTouch((SDB_RECORD *)RecordByRecordId, 0);
        if ( v5 < 0 )
          return (unsigned int)v5;
        *(_WORD *)(RecordByRecordId + 30) |= 0x10u;
      }
    }
  }
  LOBYTE(v23) = 3;
  v26 = SDB_POOL_CONFIG::GetRecordByType(v21, v23, 0);
  if ( v26 )
  {
    do
    {
      v28 = RecordByRecordId + 1;
      LOBYTE(v27) = 3;
      if ( (*(_BYTE *)(v26 + 30) & 0x10) == 0 )
        v28 = RecordByRecordId;
      LODWORD(RecordByRecordId) = v28;
      v26 = SDB_POOL_CONFIG::GetRecordByType(v21, v27, v26);
    }
    while ( v26 );
    if ( (_DWORD)RecordByRecordId )
    {
      v30 = (struct _SP_DEVICE_CHANGE *)SC_ENV::Allocate((unsigned int)(32 * RecordByRecordId), 0x58587053u, 0, 0);
      if ( v30 )
      {
        v57 = 0;
        LOBYTE(v29) = 3;
        v31 = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)this + 6), v29, 0);
        for ( k = this; ; v31 = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)k + 6), v32, v34) )
        {
          v34 = v31;
          if ( !v31 )
          {
            *v63 = 1;
            *a3 = v30;
            *a4 = v57;
            return (unsigned int)v5;
          }
          if ( (*((_BYTE *)v31 + 30) & 0x10) != 0 )
          {
            v35 = SDB_RECORD::GetObject(v31);
            v36 = v35;
            if ( (*((_BYTE *)v35 + 64) & 1) == 0 )
              break;
          }
LABEL_69:
          LOBYTE(v32) = 3;
        }
        v37 = 0;
        v59 = (struct _GUID)*((_OWORD *)v35 + 2);
        *(_QWORD *)&v59.Data1 = SpAcquireReference(&v59);
        v38 = *(_QWORD *)&v59.Data1;
        if ( *(_QWORD *)&v59.Data1 )
        {
LABEL_47:
          SP_DEVICE::AcquireMutex((SP_DEVICE *)v38);
          v43 = 32LL * v57++;
          *(_QWORD *)((char *)v30 + v43) = v38;
          v44 = *(_QWORD *)(v38 + 3224);
          *(_QWORD *)((char *)v30 + v43 + 16) = v44;
          if ( (*((_BYTE *)v34 + 30) & 8) != 0 )
          {
            *((_BYTE *)v30 + v43 + 24) = 1;
          }
          else
          {
            if ( v44 )
            {
              v47 = (SP_SPACE *)SIO_SPACE::operator new(0x4E0u);
              if ( !v47 || (v48 = SP_SPACE::SP_SPACE(v47), (v46 = v48) == 0) )
              {
                v5 = -1073741670;
LABEL_71:
                SP_POOL::AbortDevices(v42, v30, v57);
                SC_ENV_ALLOCATOR::operator delete[](v30);
                return (unsigned int)v5;
              }
              *((_QWORD *)v48 + 144) = v38;
              *((_QWORD *)v48 + 145) = this;
              v45 = SP_SPACE::Initialize(v48, v36, *(struct SIO_SPACE **)((char *)v30 + v43 + 16));
            }
            else
            {
              v45 = SP_DEVICE::Initialize((SP_DEVICE *)v38, k, v36);
              v46 = *(SP_SPACE **)(v38 + 3232);
            }
            v5 = v45;
            if ( v45 >= 0 )
            {
              if ( v37 )
              {
                if ( v46 )
                  (**(void (__fastcall ***)(SP_SPACE *, __int64))v46)(v46, 1);
              }
              else
              {
                *((_DWORD *)v36 + 66) = 1;
                *(_QWORD *)((char *)v30 + v43 + 8) = v46;
              }
            }
            else
            {
              if ( v46 )
                (**(void (__fastcall ***)(SP_SPACE *, __int64))v46)(v46, 1);
              if ( v5 == -1073741670 )
                goto LABEL_71;
              v49 = (__int64)v36 + 32;
              if ( *((int *)v36 + 66) <= 1 && (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
                McTemplateK0jq_EtwWriteTransfer(v42, SpaceDetached, 0, (char *)v36 + 32, v5);
              v50 = 1029;
              v51 = *((_DWORD *)v36 + 66);
              if ( *(_DWORD *)(v38 + 3136) != -1 )
                v50 = 1022;
              UnbiasedInterruptTime = (int *)KeQueryUnbiasedInterruptTime();
              LODWORD(v55) = v5;
              LODWORD(v54) = v51;
              SC_ENV::EventWrite(
                v50,
                (__int64)this + 108,
                v49,
                *(_QWORD *)(v38 + 3280),
                UnbiasedInterruptTime,
                v54,
                v55,
                v56,
                v57,
                v58,
                v59.Data1,
                v59.Data4[0]);
              v5 = 0;
            }
            k = this;
          }
          goto LABEL_69;
        }
        if ( SP_POOL::IsSpaceSystem(k, v36) )
        {
          if ( !SP_POOL::IsSpaceCritical(v40, v39) )
            goto LABEL_41;
        }
        else if ( (*((_BYTE *)v36 + 312) & 1) != 0 )
        {
LABEL_41:
          if ( *((_DWORD *)v36 + 66) <= 1u )
            *((_DWORD *)v36 + 66) = 2;
          if ( !SDB_SPACE::NeedsInit(v36) )
            goto LABEL_69;
          v37 = 1;
        }
        v41 = *(struct _GUID *)((char *)k + 108);
        v60 = (struct _GUID)*((_OWORD *)v36 + 2);
        v61 = v41;
        v5 = SpCreateDevice(&v61, &v60, 0, (PVOID **)&v59);
        if ( v5 < 0 )
          goto LABEL_71;
        v38 = *(_QWORD *)&v59.Data1;
        goto LABEL_47;
      }
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14009f82c  mov     rax, rsp
0x14009f82f  mov     [rax+20h], r9
0x14009f833  mov     [rax+18h], r8
0x14009f837  mov     [rax+10h], rdx
0x14009f83b  mov     [rax+8], rcx
0x14009f83f  push    rbx
0x14009f840  push    rbp
0x14009f841  push    rsi
0x14009f842  push    rdi
0x14009f843  push    r12
0x14009f845  push    r13
0x14009f847  push    r14
0x14009f849  push    r15
0x14009f84b  sub     rsp, 88h
0x14009f852  mov     rbx, [rcx+30h]
0x14009f856  xor     eax, eax
0x14009f858  mov     edi, eax
0x14009f85a  mov     [rdx], al
0x14009f85c  mov     [r8], rax
0x14009f85f  mov     r13, rcx
0x14009f862  mov     [r9], eax
0x14009f865  mov     rax, [rbx+110h]
0x14009f86c  test    byte ptr [rax+1Eh], 40h
0x14009f870  jz      short loc_14009F875
0x14009f872  mov     byte ptr [rdx], 1
0x14009f875  xor     r8d, r8d
0x14009f878  mov     dl, 3
0x14009f87a  mov     rcx, rbx
0x14009f87d  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009f882  mov     rbp, rax
0x14009f885  mov     r14d, 58587053h
0x14009f88b  test    rax, rax
0x14009f88e  jz      loc_14009F983
0x14009f894  mov     rcx, rax; this
0x14009f897  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009f89c  mov     rsi, rax
0x14009f89f  mov     al, [rcx+1Eh]
0x14009f8a2  test    al, al
0x14009f8a4  jns     short loc_14009F8AC
0x14009f8a6  cmp     byte ptr [rsi+42h], 7
0x14009f8aa  jz      short loc_14009F8B1
0x14009f8ac  mov     r8, rbp
0x14009f8af  jmp     short loc_14009F878
0x14009f8b1  mov     ecx, 4E0h; unsigned __int64
0x14009f8b6  call    ??2SIO_SPACE@@SAPEAX_K@Z; SIO_SPACE::operator new(unsigned __int64)
0x14009f8bb  test    rax, rax
0x14009f8be  jz      loc_14009FA1D
0x14009f8c4  mov     rcx, rax; this
0x14009f8c7  call    ??0SP_SPACE@@QEAA@XZ; SP_SPACE::SP_SPACE(void)
0x14009f8cc  mov     rbx, rax
0x14009f8cf  test    rax, rax
0x14009f8d2  jz      loc_14009FA1D
0x14009f8d8  xor     r8d, r8d; struct SIO_SPACE *
0x14009f8db  mov     rdx, rsi; struct SDB_SPACE *
0x14009f8de  mov     rcx, rax; this
0x14009f8e1  call    ?Initialize@SP_SPACE@@UEAAJPEAVSDB_SPACE@@PEAVSIO_SPACE@@@Z; SP_SPACE::Initialize(SDB_SPACE *,SIO_SPACE *)
0x14009f8e6  mov     edi, eax
0x14009f8e8  test    eax, eax
0x14009f8ea  js      loc_14009FA05
0x14009f8f0  xor     r9d, r9d; unsigned __int64
0x14009f8f3  xor     r8d, r8d; unsigned __int8
0x14009f8f6  mov     edx, r14d; unsigned int
0x14009f8f9  mov     ecx, 148h; unsigned __int64
0x14009f8fe  call    ??2SC_ENV_ALLOCATOR@@SAPEAX_KKE0@Z; SC_ENV_ALLOCATOR::operator new(unsigned __int64,ulong,uchar,unsigned __int64)
0x14009f903  test    rax, rax
0x14009f906  jz      loc_14009FA00
0x14009f90c  mov     rcx, rax; this
0x14009f90f  call    ??0SIO_LOG@@QEAA@XZ; SIO_LOG::SIO_LOG(void)
0x14009f914  mov     rsi, rax
0x14009f917  test    rax, rax
0x14009f91a  jz      loc_14009FA00
0x14009f920  mov     rcx, [rbx+70h]
0x14009f924  mov     r9b, 1; unsigned __int8
0x14009f927  mov     [rsp+0C8h+var_98], 0; unsigned __int64
0x14009f930  mov     r8, rbx; struct SIO_SPACE *
0x14009f933  mov     [rsp+0C8h+var_A0], rcx; unsigned __int64
0x14009f938  mov     edx, 2; unsigned int
0x14009f93d  mov     rcx, rax; this
0x14009f940  mov     [rsp+0C8h+var_A8], 0; unsigned __int8
0x14009f945  call    ?Initialize@SIO_LOG@@QEAAJKPEAVSIO_SPACE@@EE_K1@Z; SIO_LOG::Initialize(ulong,SIO_SPACE *,uchar,uchar,unsigned __int64,unsigned __int64)
0x14009f94a  mov     edi, eax
0x14009f94c  test    eax, eax
0x14009f94e  mov     rax, [rsi]
0x14009f951  mov     edx, 1
0x14009f956  mov     rcx, rsi
0x14009f959  mov     rax, [rax]
0x14009f95c  js      loc_14009F9F9
0x14009f962  call    _guard_dispatch_icall
0x14009f967  mov     rax, [rbx]
0x14009f96a  mov     edx, 1
0x14009f96f  mov     rcx, rbx
0x14009f972  mov     rax, [rax]
0x14009f975  call    _guard_dispatch_icall
0x14009f97a  mov     eax, 0FF7Fh
0x14009f97f  and     [rbp+1Eh], ax
0x14009f983  xor     r8d, r8d
0x14009f986  mov     rsi, [r13+30h]
0x14009f98a  mov     dl, 3
0x14009f98c  mov     rcx, rsi
0x14009f98f  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009f994  mov     rbx, rax
0x14009f997  test    rbx, rbx
0x14009f99a  jz      loc_14009FA27
0x14009f9a0  movzx   edx, word ptr [rax+1Eh]
0x14009f9a4  test    dl, 10h
0x14009f9a7  jz      short loc_14009F9F4
0x14009f9a9  mov     rcx, rax; this
0x14009f9ac  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009f9b1  cmp     dword ptr [rax+0BCh], 0
0x14009f9b8  jz      short loc_14009F9F4
0x14009f9ba  mov     ecx, 0FFEFh
0x14009f9bf  and     dx, cx
0x14009f9c2  mov     [rbx+1Eh], dx
0x14009f9c6  mov     dl, 3
0x14009f9c8  mov     r8d, [rax+0BCh]
0x14009f9cf  mov     rcx, [r13+30h]
0x14009f9d3  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x14009f9d8  xor     edx, edx; struct SDB_OBJECT *
0x14009f9da  mov     rcx, rax; this
0x14009f9dd  mov     rbx, rax
0x14009f9e0  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x14009f9e5  mov     edi, eax
0x14009f9e7  test    eax, eax
0x14009f9e9  js      loc_14009FD4B
0x14009f9ef  or      word ptr [rbx+1Eh], 10h
0x14009f9f4  mov     r8, rbx
0x14009f9f7  jmp     short loc_14009F986
0x14009f9f9  call    _guard_dispatch_icall
0x14009f9fe  jmp     short loc_14009FA05
0x14009fa00  mov     edi, 0C000009Ah
0x14009fa05  mov     rax, [rbx]
0x14009fa08  mov     edx, 1
0x14009fa0d  mov     rcx, rbx
0x14009fa10  mov     rax, [rax]
0x14009fa13  call    _guard_dispatch_icall
0x14009fa18  jmp     loc_14009FD4B
0x14009fa1d  mov     edi, 0C000009Ah
0x14009fa22  jmp     loc_14009FD4B
0x14009fa27  xor     r8d, r8d
0x14009fa2a  mov     dl, 3
0x14009fa2c  mov     rcx, rsi
0x14009fa2f  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa34  test    rax, rax
0x14009fa37  jz      loc_14009FD4B
0x14009fa3d  test    byte ptr [rax+1Eh], 10h
0x14009fa41  lea     ecx, [rbx+1]
0x14009fa44  mov     r8, rax
0x14009fa47  mov     dl, 3
0x14009fa49  cmovz   ecx, ebx
0x14009fa4c  mov     ebx, ecx
0x14009fa4e  mov     rcx, rsi
0x14009fa51  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa56  test    rax, rax
0x14009fa59  jnz     short loc_14009FA3D
0x14009fa5b  test    ebx, ebx
0x14009fa5d  jz      loc_14009FD4B
0x14009fa63  shl     ebx, 5
0x14009fa66  xor     r9d, r9d; unsigned int
0x14009fa69  mov     ecx, ebx; unsigned __int64
0x14009fa6b  xor     r8d, r8d; unsigned __int8
0x14009fa6e  mov     edx, r14d; unsigned int
0x14009fa71  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14009fa76  mov     rbp, rax
0x14009fa79  test    rax, rax
0x14009fa7c  jz      short loc_14009FA1D
0x14009fa7e  mov     rcx, [r13+30h]
0x14009fa82  xor     eax, eax
0x14009fa84  xor     r8d, r8d
0x14009fa87  mov     [rsp+0C8h+var_88], eax
0x14009fa8b  mov     dl, 3
0x14009fa8d  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa92  mov     rbx, [rsp+0C8h+arg_0]
0x14009fa9a  mov     r13, rax
0x14009fa9d  test    rax, rax
0x14009faa0  jz      loc_14009FD27
0x14009faa6  test    byte ptr [rax+1Eh], 10h
0x14009faaa  jz      loc_14009FCF8
0x14009fab0  mov     rcx, rax; this
0x14009fab3  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009fab8  mov     rsi, rax
0x14009fabb  test    byte ptr [rax+40h], 1
0x14009fabf  jnz     loc_14009FCF8
0x14009fac5  movups  xmm0, xmmword ptr [rax+20h]
0x14009fac9  lea     rcx, [rsp+0C8h+var_78]; struct _GUID
0x14009face  xor     r12b, r12b
0x14009fad1  movdqu  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x14009fad7  call    ?SpAcquireReference@@YAPEAVSP_DEVICE@@U_GUID@@@Z; SpAcquireReference(_GUID)
0x14009fadc  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x14009fae1  mov     r14, rax
0x14009fae4  test    rax, rax
0x14009fae7  jnz     loc_14009FB70
0x14009faed  mov     rdx, rsi; struct SDB_SPACE *
0x14009faf0  mov     rcx, rbx; this
0x14009faf3  call    ?IsSpaceSystem@SP_POOL@@QEAAEPEAVSDB_SPACE@@@Z; SP_POOL::IsSpaceSystem(SDB_SPACE *)
0x14009faf8  test    al, al
0x14009fafa  jz      short loc_14009FB07
0x14009fafc  call    ?IsSpaceCritical@SP_POOL@@QEAAEPEAVSDB_SPACE@@@Z; SP_POOL::IsSpaceCritical(SDB_SPACE *)
0x14009fb01  test    al, al
0x14009fb03  jnz     short loc_14009FB36
0x14009fb05  jmp     short loc_14009FB10
0x14009fb07  test    byte ptr [rsi+138h], 1
0x14009fb0e  jz      short loc_14009FB36
0x14009fb10  cmp     dword ptr [rsi+108h], 1
0x14009fb17  ja      short loc_14009FB23
0x14009fb19  mov     dword ptr [rsi+108h], 2
0x14009fb23  mov     rcx, rsi; this
0x14009fb26  call    ?NeedsInit@SDB_SPACE@@QEAAEXZ; SDB_SPACE::NeedsInit(void)
0x14009fb2b  test    al, al
0x14009fb2d  jz      loc_14009FCF8
0x14009fb33  mov     r12b, 1
0x14009fb36  movups  xmm0, xmmword ptr [rsi+20h]
0x14009fb3a  lea     r9, [rsp+0C8h+var_78]; struct SP_DEVICE **
0x14009fb3f  xor     r8d, r8d; unsigned __int8
0x14009fb42  movups  xmm1, xmmword ptr [rbx+6Ch]
0x14009fb46  lea     rdx, [rsp+0C8h+var_68]; struct _GUID
0x14009fb4b  lea     rcx, [rsp+0C8h+var_58]; struct _GUID
0x14009fb50  movdqu  xmmword ptr [rsp+0C8h+var_68.Data1], xmm0
0x14009fb56  movdqu  xmmword ptr [rsp+0C8h+var_58.Data1], xmm1
0x14009fb5c  call    ?SpCreateDevice@@YAJU_GUID@@0EPEAPEAVSP_DEVICE@@@Z; SpCreateDevice(_GUID,_GUID,uchar,SP_DEVICE * *)
0x14009fb61  mov     edi, eax
0x14009fb63  test    eax, eax
0x14009fb65  js      loc_14009FD10
0x14009fb6b  mov     r14, qword ptr [rsp+0C8h+var_78.Data1]
0x14009fb70  mov     rcx, r14; this
0x14009fb73  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14009fb78  mov     eax, [rsp+0C8h+var_88]
0x14009fb7c  mov     r15d, eax
0x14009fb7f  inc     eax
0x14009fb81  shl     r15, 5
0x14009fb85  mov     [rsp+0C8h+var_88], eax
0x14009fb89  mov     [r15+rbp], r14
0x14009fb8d  mov     rcx, [r14+0C98h]
0x14009fb94  mov     [r15+rbp+10h], rcx
0x14009fb99  test    byte ptr [r13+1Eh], 8
0x14009fb9e  jz      short loc_14009FBAB
0x14009fba0  mov     byte ptr [r15+rbp+18h], 1
0x14009fba6  jmp     loc_14009FCF8
0x14009fbab  test    rcx, rcx
0x14009fbae  jnz     short loc_14009FBC7
0x14009fbb0  mov     r8, rsi; struct SDB_SPACE *
0x14009fbb3  mov     rdx, rbx; struct SP_POOL *
0x14009fbb6  mov     rcx, r14; this
0x14009fbb9  call    ?Initialize@SP_DEVICE@@QEAAJPEAVSP_POOL@@PEAVSDB_SPACE@@@Z; SP_DEVICE::Initialize(SP_POOL *,SDB_SPACE *)
0x14009fbbe  mov     rbx, [r14+0CA0h]
0x14009fbc5  jmp     short loc_14009FC14
0x14009fbc7  mov     ecx, 4E0h; unsigned __int64
0x14009fbcc  call    ??2SIO_SPACE@@SAPEAX_K@Z; SIO_SPACE::operator new(unsigned __int64)
0x14009fbd1  test    rax, rax
0x14009fbd4  jz      loc_14009FD0B
0x14009fbda  mov     rcx, rax; this
0x14009fbdd  call    ??0SP_SPACE@@QEAA@XZ; SP_SPACE::SP_SPACE(void)
0x14009fbe2  mov     rbx, rax
0x14009fbe5  test    rax, rax
0x14009fbe8  jz      loc_14009FD0B
0x14009fbee  mov     [rax+480h], r14
0x14009fbf5  mov     rdx, rsi; struct SDB_SPACE *
0x14009fbf8  mov     rax, [rsp+0C8h+arg_0]
0x14009fc00  mov     rcx, rbx; this
0x14009fc03  mov     [rbx+488h], rax
0x14009fc0a  mov     r8, [r15+rbp+10h]; struct SIO_SPACE *
0x14009fc0f  call    ?Initialize@SP_SPACE@@UEAAJPEAVSDB_SPACE@@PEAVSIO_SPACE@@@Z; SP_SPACE::Initialize(SDB_SPACE *,SIO_SPACE *)
0x14009fc14  mov     edi, eax
0x14009fc16  test    eax, eax
0x14009fc18  jns     loc_14009FCC2
0x14009fc1e  test    rbx, rbx
0x14009fc21  jz      short loc_14009FC36
0x14009fc23  mov     rax, [rbx]
0x14009fc26  mov     edx, 1
0x14009fc2b  mov     rcx, rbx
0x14009fc2e  mov     rax, [rax]
0x14009fc31  call    _guard_dispatch_icall
0x14009fc36  cmp     edi, 0C000009Ah
0x14009fc3c  jz      loc_14009FD10
0x14009fc42  cmp     dword ptr [rsi+108h], 1
0x14009fc49  lea     r12, [rsi+20h]
0x14009fc4d  jg      short loc_14009FC6E
0x14009fc4f  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009fc56  jz      short loc_14009FC6E
0x14009fc58  mov     r9, r12
0x14009fc5b  mov     dword ptr [rsp+0C8h+var_A8], edi
0x14009fc5f  xor     r8d, r8d
0x14009fc62  lea     rdx, SpaceDetached
0x14009fc69  call    McTemplateK0jq_EtwWriteTransfer
0x14009fc6e  cmp     dword ptr [r14+0C40h], 0FFFFFFFFh
0x14009fc76  mov     ebx, 405h
0x14009fc7b  mov     r15, [rsp+0C8h+arg_0]
0x14009fc83  mov     esi, [rsi+108h]
0x14009fc89  jz      short loc_14009FC90
0x14009fc8b  mov     ebx, 3FEh
0x14009fc90  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14009fc97  nop     dword ptr [rax+rax+00h]
0x14009fc9c  mov     r9, [r14+0CD0h]
0x14009fca3  lea     rdx, [r15+6Ch]
0x14009fca7  mov     dword ptr [rsp+0C8h+var_98], edi
0x14009fcab  mov     r8, r12
0x14009fcae  mov     dword ptr [rsp+0C8h+var_A0], esi
0x14009fcb2  mov     ecx, ebx; unsigned int
0x14009fcb4  mov     qword ptr [rsp+0C8h+var_A8], rax
0x14009fcb9  call    ?EventWrite@SC_ENV@@SAXKZZ; SC_ENV::EventWrite(ulong,...)
0x14009fcbe  xor     edi, edi
  ... truncated ...
```
