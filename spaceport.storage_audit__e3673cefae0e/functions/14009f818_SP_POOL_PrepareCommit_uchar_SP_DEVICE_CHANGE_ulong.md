# SP_POOL::PrepareCommit(uchar *,_SP_DEVICE_CHANGE * *,ulong *)

- ea: `0x14009f818`
- end: `0x14009fd4e`
- name: `?PrepareCommit@SP_POOL@@AEAAJPEAEPEAPEAU_SP_DEVICE_CHANGE@@PEAK@Z`
- size: `1334`
- prototype: `__int64 __fastcall(SP_POOL *__hidden this, unsigned __int8 *, struct _SP_DEVICE_CHANGE **, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14009e3e4`

## callees

- `0x1400044d0`
- `0x14000ba20`
- `0x14000c630`
- `0x1400187f0`
- `0x14001c760`
- `0x14001e4a0`
- `0x1400216f0`
- `0x1400268c0`
- `0x14002fd40`
- `0x14004068c`
- `0x14005f000`
- `0x140068000`
- `0x14008c3c0`
- `0x14008f898`
- `0x14009cb1c`
- `0x14009cda0`
- `0x14009d884`
- `0x14009eafc`
- `0x14009eb4c`
- `0x14009f818`
- `0x1400a47b8`
- `0x1400b0edc`
- `0x1400b145c`
- `0x1400b6b10`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14009fc7c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14009fc7c`

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
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // ecx
  __int64 v28; // rdx
  struct _SP_DEVICE_CHANGE *v29; // rbp
  SDB_RECORD *v30; // rax
  __int64 v31; // rdx
  SP_POOL *k; // rbx
  SDB_RECORD *v33; // r13
  struct SDB_OBJECT *v34; // rax
  struct SDB_OBJECT *v35; // rsi
  char v36; // r12
  __int64 v37; // r14
  struct SDB_SPACE *v38; // rdx
  SP_POOL *v39; // rcx
  struct _GUID v40; // xmm1
  SP_POOL *v41; // rcx
  __int64 v42; // r15
  __int64 v43; // rcx
  int v44; // eax
  SP_SPACE *v45; // rbx
  SP_SPACE *v46; // rax
  SP_SPACE *v47; // rax
  __int64 v48; // r12
  unsigned int v49; // ebx
  int v50; // esi
  int *UnbiasedInterruptTime; // rax
  unsigned __int64 v53; // [rsp+28h] [rbp-A0h]
  unsigned __int64 v54; // [rsp+30h] [rbp-98h]
  __int64 v55; // [rsp+38h] [rbp-90h]
  unsigned int v56; // [rsp+40h] [rbp-88h]
  char v57; // [rsp+48h] [rbp-80h]
  struct _GUID v58; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID v59; // [rsp+60h] [rbp-68h] BYREF
  struct _GUID v60; // [rsp+70h] [rbp-58h] BYREF
  unsigned __int8 *v62; // [rsp+D8h] [rbp+10h]

  v62 = a2;
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
    if ( (v9 & 0x10) != 0 && *((_DWORD *)SDB_RECORD::GetObject((SDB_RECORD *)v22) + 47) )
    {
      LOWORD(v9) = v9 & 0xFFEF;
      *(_WORD *)(RecordByRecordId + 30) = v9;
      LOBYTE(v9) = 3;
      RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)this + 6), v9);
      v5 = SDB_RECORD::PreTouch((SDB_RECORD *)RecordByRecordId, 0);
      if ( v5 < 0 )
        return (unsigned int)v5;
      *(_WORD *)(RecordByRecordId + 30) |= 0x10u;
    }
  }
  LOBYTE(v23) = 3;
  v25 = SDB_POOL_CONFIG::GetRecordByType(v21, v23, 0);
  if ( v25 )
  {
    do
    {
      v27 = RecordByRecordId + 1;
      LOBYTE(v26) = 3;
      if ( (*(_BYTE *)(v25 + 30) & 0x10) == 0 )
        v27 = RecordByRecordId;
      LODWORD(RecordByRecordId) = v27;
      v25 = SDB_POOL_CONFIG::GetRecordByType(v21, v26, v25);
    }
    while ( v25 );
    if ( (_DWORD)RecordByRecordId )
    {
      v29 = (struct _SP_DEVICE_CHANGE *)SC_ENV::Allocate((unsigned int)(32 * RecordByRecordId), 0x58587053u, 0, 0);
      if ( v29 )
      {
        v56 = 0;
        LOBYTE(v28) = 3;
        v30 = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)this + 6), v28, 0);
        for ( k = this; ; v30 = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(*((_QWORD *)k + 6), v31, v33) )
        {
          v33 = v30;
          if ( !v30 )
          {
            *v62 = 1;
            *a3 = v29;
            *a4 = v56;
            return (unsigned int)v5;
          }
          if ( (*((_BYTE *)v30 + 30) & 0x10) != 0 )
          {
            v34 = SDB_RECORD::GetObject(v30);
            v35 = v34;
            if ( (*((_BYTE *)v34 + 64) & 1) == 0 )
              break;
          }
LABEL_69:
          LOBYTE(v31) = 3;
        }
        v36 = 0;
        v58 = (struct _GUID)*((_OWORD *)v34 + 2);
        *(_QWORD *)&v58.Data1 = SpAcquireReference(&v58);
        v37 = *(_QWORD *)&v58.Data1;
        if ( *(_QWORD *)&v58.Data1 )
        {
LABEL_47:
          SP_DEVICE::AcquireMutex((SP_DEVICE *)v37);
          v42 = 32LL * v56++;
          *(_QWORD *)((char *)v29 + v42) = v37;
          v43 = *(_QWORD *)(v37 + 3224);
          *(_QWORD *)((char *)v29 + v42 + 16) = v43;
          if ( (*((_BYTE *)v33 + 30) & 8) != 0 )
          {
            *((_BYTE *)v29 + v42 + 24) = 1;
          }
          else
          {
            if ( v43 )
            {
              v46 = (SP_SPACE *)SIO_SPACE::operator new(0x4E0u);
              if ( !v46 || (v47 = SP_SPACE::SP_SPACE(v46), (v45 = v47) == 0) )
              {
                v5 = -1073741670;
LABEL_71:
                SP_POOL::AbortDevices(v41, v29, v56);
                SC_ENV_ALLOCATOR::operator delete[](v29);
                return (unsigned int)v5;
              }
              *((_QWORD *)v47 + 144) = v37;
              *((_QWORD *)v47 + 145) = this;
              v44 = SP_SPACE::Initialize(v47, v35, *(struct SIO_SPACE **)((char *)v29 + v42 + 16));
            }
            else
            {
              v44 = SP_DEVICE::Initialize((SP_DEVICE *)v37, k, v35);
              v45 = *(SP_SPACE **)(v37 + 3232);
            }
            v5 = v44;
            if ( v44 >= 0 )
            {
              if ( v36 )
              {
                if ( v45 )
                  (**(void (__fastcall ***)(SP_SPACE *, __int64))v45)(v45, 1);
              }
              else
              {
                *((_DWORD *)v35 + 66) = 1;
                *(_QWORD *)((char *)v29 + v42 + 8) = v45;
              }
            }
            else
            {
              if ( v45 )
                (**(void (__fastcall ***)(SP_SPACE *, __int64))v45)(v45, 1);
              if ( v5 == -1073741670 )
                goto LABEL_71;
              v48 = (__int64)v35 + 32;
              if ( *((int *)v35 + 66) <= 1 && (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
                McTemplateK0jq_EtwWriteTransfer(v41, SpaceDetached, 0, (char *)v35 + 32, v5);
              v49 = 1029;
              v50 = *((_DWORD *)v35 + 66);
              if ( *(_DWORD *)(v37 + 3136) != -1 )
                v49 = 1022;
              UnbiasedInterruptTime = (int *)KeQueryUnbiasedInterruptTime();
              LODWORD(v54) = v5;
              LODWORD(v53) = v50;
              SC_ENV::EventWrite(
                v49,
                (__int64)this + 108,
                v48,
                *(_QWORD *)(v37 + 3280),
                UnbiasedInterruptTime,
                v53,
                v54,
                v55,
                v56,
                v57,
                v58.Data1,
                v58.Data4[0]);
              v5 = 0;
            }
            k = this;
          }
          goto LABEL_69;
        }
        if ( SP_POOL::IsSpaceSystem(k, v35) )
        {
          if ( !SP_POOL::IsSpaceCritical(v39, v38) )
            goto LABEL_41;
        }
        else if ( (*((_BYTE *)v35 + 312) & 1) != 0 )
        {
LABEL_41:
          if ( *((_DWORD *)v35 + 66) <= 1u )
            *((_DWORD *)v35 + 66) = 2;
          if ( !SDB_SPACE::NeedsInit(v35) )
            goto LABEL_69;
          v36 = 1;
        }
        v40 = *(struct _GUID *)((char *)k + 108);
        v59 = (struct _GUID)*((_OWORD *)v35 + 2);
        v60 = v40;
        v5 = SpCreateDevice(&v60, &v59, 0, (PVOID **)&v58);
        if ( v5 < 0 )
          goto LABEL_71;
        v37 = *(_QWORD *)&v58.Data1;
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
0x14009f818  mov     rax, rsp
0x14009f81b  mov     [rax+20h], r9
0x14009f81f  mov     [rax+18h], r8
0x14009f823  mov     [rax+10h], rdx
0x14009f827  mov     [rax+8], rcx
0x14009f82b  push    rbx
0x14009f82c  push    rbp
0x14009f82d  push    rsi
0x14009f82e  push    rdi
0x14009f82f  push    r12
0x14009f831  push    r13
0x14009f833  push    r14
0x14009f835  push    r15
0x14009f837  sub     rsp, 88h
0x14009f83e  mov     rbx, [rcx+30h]
0x14009f842  xor     eax, eax
0x14009f844  mov     edi, eax
0x14009f846  mov     [rdx], al
0x14009f848  mov     [r8], rax
0x14009f84b  mov     r13, rcx
0x14009f84e  mov     [r9], eax
0x14009f851  mov     rax, [rbx+110h]
0x14009f858  test    byte ptr [rax+1Eh], 40h
0x14009f85c  jz      short loc_14009F861
0x14009f85e  mov     byte ptr [rdx], 1
0x14009f861  xor     r8d, r8d
0x14009f864  mov     dl, 3
0x14009f866  mov     rcx, rbx
0x14009f869  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009f86e  mov     rbp, rax
0x14009f871  mov     r14d, 58587053h
0x14009f877  test    rax, rax
0x14009f87a  jz      loc_14009F96F
0x14009f880  mov     rcx, rax; this
0x14009f883  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009f888  mov     rsi, rax
0x14009f88b  mov     al, [rcx+1Eh]
0x14009f88e  test    al, al
0x14009f890  jns     short loc_14009F898
0x14009f892  cmp     byte ptr [rsi+42h], 7
0x14009f896  jz      short loc_14009F89D
0x14009f898  mov     r8, rbp
0x14009f89b  jmp     short loc_14009F864
0x14009f89d  mov     ecx, 4E0h; unsigned __int64
0x14009f8a2  call    ??2SIO_SPACE@@SAPEAX_K@Z; SIO_SPACE::operator new(unsigned __int64)
0x14009f8a7  test    rax, rax
0x14009f8aa  jz      loc_14009FA09
0x14009f8b0  mov     rcx, rax; this
0x14009f8b3  call    ??0SP_SPACE@@QEAA@XZ; SP_SPACE::SP_SPACE(void)
0x14009f8b8  mov     rbx, rax
0x14009f8bb  test    rax, rax
0x14009f8be  jz      loc_14009FA09
0x14009f8c4  xor     r8d, r8d; struct SIO_SPACE *
0x14009f8c7  mov     rdx, rsi; struct SDB_SPACE *
0x14009f8ca  mov     rcx, rax; this
0x14009f8cd  call    ?Initialize@SP_SPACE@@UEAAJPEAVSDB_SPACE@@PEAVSIO_SPACE@@@Z; SP_SPACE::Initialize(SDB_SPACE *,SIO_SPACE *)
0x14009f8d2  mov     edi, eax
0x14009f8d4  test    eax, eax
0x14009f8d6  js      loc_14009F9F1
0x14009f8dc  xor     r9d, r9d; unsigned __int64
0x14009f8df  xor     r8d, r8d; unsigned __int8
0x14009f8e2  mov     edx, r14d; unsigned int
0x14009f8e5  mov     ecx, 148h; unsigned __int64
0x14009f8ea  call    ??2SC_ENV_ALLOCATOR@@SAPEAX_KKE0@Z; SC_ENV_ALLOCATOR::operator new(unsigned __int64,ulong,uchar,unsigned __int64)
0x14009f8ef  test    rax, rax
0x14009f8f2  jz      loc_14009F9EC
0x14009f8f8  mov     rcx, rax; this
0x14009f8fb  call    ??0SIO_LOG@@QEAA@XZ; SIO_LOG::SIO_LOG(void)
0x14009f900  mov     rsi, rax
0x14009f903  test    rax, rax
0x14009f906  jz      loc_14009F9EC
0x14009f90c  mov     rcx, [rbx+70h]
0x14009f910  mov     r9b, 1; unsigned __int8
0x14009f913  mov     [rsp+0C8h+var_98], 0; unsigned __int64
0x14009f91c  mov     r8, rbx; struct SIO_SPACE *
0x14009f91f  mov     [rsp+0C8h+var_A0], rcx; unsigned __int64
0x14009f924  mov     edx, 2; unsigned int
0x14009f929  mov     rcx, rax; this
0x14009f92c  mov     [rsp+0C8h+var_A8], 0; unsigned __int8
0x14009f931  call    ?Initialize@SIO_LOG@@QEAAJKPEAVSIO_SPACE@@EE_K1@Z; SIO_LOG::Initialize(ulong,SIO_SPACE *,uchar,uchar,unsigned __int64,unsigned __int64)
0x14009f936  mov     edi, eax
0x14009f938  test    eax, eax
0x14009f93a  mov     rax, [rsi]
0x14009f93d  mov     edx, 1
0x14009f942  mov     rcx, rsi
0x14009f945  mov     rax, [rax]
0x14009f948  js      loc_14009F9E5
0x14009f94e  call    _guard_dispatch_icall
0x14009f953  mov     rax, [rbx]
0x14009f956  mov     edx, 1
0x14009f95b  mov     rcx, rbx
0x14009f95e  mov     rax, [rax]
0x14009f961  call    _guard_dispatch_icall
0x14009f966  mov     eax, 0FF7Fh
0x14009f96b  and     [rbp+1Eh], ax
0x14009f96f  xor     r8d, r8d
0x14009f972  mov     rsi, [r13+30h]
0x14009f976  mov     dl, 3
0x14009f978  mov     rcx, rsi
0x14009f97b  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009f980  mov     rbx, rax
0x14009f983  test    rbx, rbx
0x14009f986  jz      loc_14009FA13
0x14009f98c  movzx   edx, word ptr [rax+1Eh]
0x14009f990  test    dl, 10h
0x14009f993  jz      short loc_14009F9E0
0x14009f995  mov     rcx, rax; this
0x14009f998  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009f99d  cmp     dword ptr [rax+0BCh], 0
0x14009f9a4  jz      short loc_14009F9E0
0x14009f9a6  mov     ecx, 0FFEFh
0x14009f9ab  and     dx, cx
0x14009f9ae  mov     [rbx+1Eh], dx
0x14009f9b2  mov     dl, 3
0x14009f9b4  mov     r8d, [rax+0BCh]
0x14009f9bb  mov     rcx, [r13+30h]
0x14009f9bf  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x14009f9c4  xor     edx, edx; struct SDB_OBJECT *
0x14009f9c6  mov     rcx, rax; this
0x14009f9c9  mov     rbx, rax
0x14009f9cc  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x14009f9d1  mov     edi, eax
0x14009f9d3  test    eax, eax
0x14009f9d5  js      loc_14009FD37
0x14009f9db  or      word ptr [rbx+1Eh], 10h
0x14009f9e0  mov     r8, rbx
0x14009f9e3  jmp     short loc_14009F972
0x14009f9e5  call    _guard_dispatch_icall
0x14009f9ea  jmp     short loc_14009F9F1
0x14009f9ec  mov     edi, 0C000009Ah
0x14009f9f1  mov     rax, [rbx]
0x14009f9f4  mov     edx, 1
0x14009f9f9  mov     rcx, rbx
0x14009f9fc  mov     rax, [rax]
0x14009f9ff  call    _guard_dispatch_icall
0x14009fa04  jmp     loc_14009FD37
0x14009fa09  mov     edi, 0C000009Ah
0x14009fa0e  jmp     loc_14009FD37
0x14009fa13  xor     r8d, r8d
0x14009fa16  mov     dl, 3
0x14009fa18  mov     rcx, rsi
0x14009fa1b  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa20  test    rax, rax
0x14009fa23  jz      loc_14009FD37
0x14009fa29  test    byte ptr [rax+1Eh], 10h
0x14009fa2d  lea     ecx, [rbx+1]
0x14009fa30  mov     r8, rax
0x14009fa33  mov     dl, 3
0x14009fa35  cmovz   ecx, ebx
0x14009fa38  mov     ebx, ecx
0x14009fa3a  mov     rcx, rsi
0x14009fa3d  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa42  test    rax, rax
0x14009fa45  jnz     short loc_14009FA29
0x14009fa47  test    ebx, ebx
0x14009fa49  jz      loc_14009FD37
0x14009fa4f  shl     ebx, 5
0x14009fa52  xor     r9d, r9d; unsigned int
0x14009fa55  mov     ecx, ebx; unsigned __int64
0x14009fa57  xor     r8d, r8d; unsigned __int8
0x14009fa5a  mov     edx, r14d; unsigned int
0x14009fa5d  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14009fa62  mov     rbp, rax
0x14009fa65  test    rax, rax
0x14009fa68  jz      short loc_14009FA09
0x14009fa6a  mov     rcx, [r13+30h]
0x14009fa6e  xor     eax, eax
0x14009fa70  xor     r8d, r8d
0x14009fa73  mov     [rsp+0C8h+var_88], eax
0x14009fa77  mov     dl, 3
0x14009fa79  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14009fa7e  mov     rbx, [rsp+0C8h+arg_0]
0x14009fa86  mov     r13, rax
0x14009fa89  test    rax, rax
0x14009fa8c  jz      loc_14009FD13
0x14009fa92  test    byte ptr [rax+1Eh], 10h
0x14009fa96  jz      loc_14009FCE4
0x14009fa9c  mov     rcx, rax; this
0x14009fa9f  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x14009faa4  mov     rsi, rax
0x14009faa7  test    byte ptr [rax+40h], 1
0x14009faab  jnz     loc_14009FCE4
0x14009fab1  movups  xmm0, xmmword ptr [rax+20h]
0x14009fab5  lea     rcx, [rsp+0C8h+var_78]; struct _GUID
0x14009faba  xor     r12b, r12b
0x14009fabd  movdqu  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x14009fac3  call    ?SpAcquireReference@@YAPEAVSP_DEVICE@@U_GUID@@@Z; SpAcquireReference(_GUID)
0x14009fac8  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x14009facd  mov     r14, rax
0x14009fad0  test    rax, rax
0x14009fad3  jnz     loc_14009FB5C
0x14009fad9  mov     rdx, rsi; struct SDB_SPACE *
0x14009fadc  mov     rcx, rbx; this
0x14009fadf  call    ?IsSpaceSystem@SP_POOL@@QEAAEPEAVSDB_SPACE@@@Z; SP_POOL::IsSpaceSystem(SDB_SPACE *)
0x14009fae4  test    al, al
0x14009fae6  jz      short loc_14009FAF3
0x14009fae8  call    ?IsSpaceCritical@SP_POOL@@QEAAEPEAVSDB_SPACE@@@Z; SP_POOL::IsSpaceCritical(SDB_SPACE *)
0x14009faed  test    al, al
0x14009faef  jnz     short loc_14009FB22
0x14009faf1  jmp     short loc_14009FAFC
0x14009faf3  test    byte ptr [rsi+138h], 1
0x14009fafa  jz      short loc_14009FB22
0x14009fafc  cmp     dword ptr [rsi+108h], 1
0x14009fb03  ja      short loc_14009FB0F
0x14009fb05  mov     dword ptr [rsi+108h], 2
0x14009fb0f  mov     rcx, rsi; this
0x14009fb12  call    ?NeedsInit@SDB_SPACE@@QEAAEXZ; SDB_SPACE::NeedsInit(void)
0x14009fb17  test    al, al
0x14009fb19  jz      loc_14009FCE4
0x14009fb1f  mov     r12b, 1
0x14009fb22  movups  xmm0, xmmword ptr [rsi+20h]
0x14009fb26  lea     r9, [rsp+0C8h+var_78]; struct SP_DEVICE **
0x14009fb2b  xor     r8d, r8d; unsigned __int8
0x14009fb2e  movups  xmm1, xmmword ptr [rbx+6Ch]
0x14009fb32  lea     rdx, [rsp+0C8h+var_68]; struct _GUID
0x14009fb37  lea     rcx, [rsp+0C8h+var_58]; struct _GUID
0x14009fb3c  movdqu  xmmword ptr [rsp+0C8h+var_68.Data1], xmm0
0x14009fb42  movdqu  xmmword ptr [rsp+0C8h+var_58.Data1], xmm1
0x14009fb48  call    ?SpCreateDevice@@YAJU_GUID@@0EPEAPEAVSP_DEVICE@@@Z; SpCreateDevice(_GUID,_GUID,uchar,SP_DEVICE * *)
0x14009fb4d  mov     edi, eax
0x14009fb4f  test    eax, eax
0x14009fb51  js      loc_14009FCFC
0x14009fb57  mov     r14, qword ptr [rsp+0C8h+var_78.Data1]
0x14009fb5c  mov     rcx, r14; this
0x14009fb5f  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14009fb64  mov     eax, [rsp+0C8h+var_88]
0x14009fb68  mov     r15d, eax
0x14009fb6b  inc     eax
0x14009fb6d  shl     r15, 5
0x14009fb71  mov     [rsp+0C8h+var_88], eax
0x14009fb75  mov     [r15+rbp], r14
0x14009fb79  mov     rcx, [r14+0C98h]
0x14009fb80  mov     [r15+rbp+10h], rcx
0x14009fb85  test    byte ptr [r13+1Eh], 8
0x14009fb8a  jz      short loc_14009FB97
0x14009fb8c  mov     byte ptr [r15+rbp+18h], 1
0x14009fb92  jmp     loc_14009FCE4
0x14009fb97  test    rcx, rcx
0x14009fb9a  jnz     short loc_14009FBB3
0x14009fb9c  mov     r8, rsi; struct SDB_SPACE *
0x14009fb9f  mov     rdx, rbx; struct SP_POOL *
0x14009fba2  mov     rcx, r14; this
0x14009fba5  call    ?Initialize@SP_DEVICE@@QEAAJPEAVSP_POOL@@PEAVSDB_SPACE@@@Z; SP_DEVICE::Initialize(SP_POOL *,SDB_SPACE *)
0x14009fbaa  mov     rbx, [r14+0CA0h]
0x14009fbb1  jmp     short loc_14009FC00
0x14009fbb3  mov     ecx, 4E0h; unsigned __int64
0x14009fbb8  call    ??2SIO_SPACE@@SAPEAX_K@Z; SIO_SPACE::operator new(unsigned __int64)
0x14009fbbd  test    rax, rax
0x14009fbc0  jz      loc_14009FCF7
0x14009fbc6  mov     rcx, rax; this
0x14009fbc9  call    ??0SP_SPACE@@QEAA@XZ; SP_SPACE::SP_SPACE(void)
0x14009fbce  mov     rbx, rax
0x14009fbd1  test    rax, rax
0x14009fbd4  jz      loc_14009FCF7
0x14009fbda  mov     [rax+480h], r14
0x14009fbe1  mov     rdx, rsi; struct SDB_SPACE *
0x14009fbe4  mov     rax, [rsp+0C8h+arg_0]
0x14009fbec  mov     rcx, rbx; this
0x14009fbef  mov     [rbx+488h], rax
0x14009fbf6  mov     r8, [r15+rbp+10h]; struct SIO_SPACE *
0x14009fbfb  call    ?Initialize@SP_SPACE@@UEAAJPEAVSDB_SPACE@@PEAVSIO_SPACE@@@Z; SP_SPACE::Initialize(SDB_SPACE *,SIO_SPACE *)
0x14009fc00  mov     edi, eax
0x14009fc02  test    eax, eax
0x14009fc04  jns     loc_14009FCAE
0x14009fc0a  test    rbx, rbx
0x14009fc0d  jz      short loc_14009FC22
0x14009fc0f  mov     rax, [rbx]
0x14009fc12  mov     edx, 1
0x14009fc17  mov     rcx, rbx
0x14009fc1a  mov     rax, [rax]
0x14009fc1d  call    _guard_dispatch_icall
0x14009fc22  cmp     edi, 0C000009Ah
0x14009fc28  jz      loc_14009FCFC
0x14009fc2e  cmp     dword ptr [rsi+108h], 1
0x14009fc35  lea     r12, [rsi+20h]
0x14009fc39  jg      short loc_14009FC5A
0x14009fc3b  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1
0x14009fc42  jz      short loc_14009FC5A
0x14009fc44  mov     r9, r12
0x14009fc47  mov     dword ptr [rsp+0C8h+var_A8], edi
0x14009fc4b  xor     r8d, r8d
0x14009fc4e  lea     rdx, SpaceDetached
0x14009fc55  call    McTemplateK0jq_EtwWriteTransfer
0x14009fc5a  cmp     dword ptr [r14+0C40h], 0FFFFFFFFh
0x14009fc62  mov     ebx, 405h
0x14009fc67  mov     r15, [rsp+0C8h+arg_0]
0x14009fc6f  mov     esi, [rsi+108h]
0x14009fc75  jz      short loc_14009FC7C
0x14009fc77  mov     ebx, 3FEh
0x14009fc7c  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14009fc83  nop     dword ptr [rax+rax+00h]
0x14009fc88  mov     r9, [r14+0CD0h]
0x14009fc8f  lea     rdx, [r15+6Ch]
0x14009fc93  mov     dword ptr [rsp+0C8h+var_98], edi
0x14009fc97  mov     r8, r12
0x14009fc9a  mov     dword ptr [rsp+0C8h+var_A0], esi
0x14009fc9e  mov     ecx, ebx; unsigned int
0x14009fca0  mov     qword ptr [rsp+0C8h+var_A8], rax
0x14009fca5  call    ?EventWrite@SC_ENV@@SAXKZZ; SC_ENV::EventWrite(ulong,...)
0x14009fcaa  xor     edi, edi
  ... truncated ...
```
