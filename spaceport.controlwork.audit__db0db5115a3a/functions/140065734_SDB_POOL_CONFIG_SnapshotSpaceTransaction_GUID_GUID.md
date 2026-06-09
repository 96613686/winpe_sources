# SDB_POOL_CONFIG::SnapshotSpaceTransaction(_GUID *,_GUID *)

- ea: `0x140065734`
- end: `0x14006598a`
- name: `?SnapshotSpaceTransaction@SDB_POOL_CONFIG@@QEAAJPEAU_GUID@@0@Z`
- size: `598`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400612c0`
- `0x140063980`

## callees

- `0x14000b3e0`
- `0x14000d4f0`
- `0x14001e760`
- `0x140026790`
- `0x1400268c0`
- `0x140026e00`
- `0x140060018`
- `0x140060438`
- `0x140061f50`
- `0x140063080`
- `0x140065734`
- `0x140068000`
- `0x14009d6ac`
- `0x1400b33a4`
- `0x1400b6b10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006595f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006595f`

## pseudocode

```c
__int64 __fastcall SDB_POOL_CONFIG::SnapshotSpaceTransaction(SDB_POOL_CONFIG *this, struct _GUID *a2, struct _GUID *a3)
{
  SDB_RECORD *SpaceById; // rax
  SDB_RECORD *v6; // rbp
  NTSTATUS MetadataDrives; // edi
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // r15
  SC_SPARSE *v13; // rax
  SDB_SPACE_CONFIG *v14; // rbx
  __int16 v15; // ax
  SDB_SPACE_CONFIG *v16; // rax
  SDB_SPACE_CONFIG *v17; // rax
  SDB_SPACE_CONFIG *v18; // rbx
  void *v19; // rcx
  SDB_SPACE_CONFIG *v21; // [rsp+20h] [rbp-58h] BYREF
  __int64 v22; // [rsp+98h] [rbp+20h] BYREF

  v22 = 0;
  v21 = 0;
  SpaceById = SDB_POOL_CONFIG::FindSpaceById(this, a2);
  v6 = SpaceById;
  if ( !SpaceById )
    return (unsigned int)-1070071738;
  MetadataDrives = SDB_RECORD::PreTouch(SpaceById, 0);
  if ( MetadataDrives < 0 )
    return (unsigned int)MetadataDrives;
  v8 = *((_QWORD *)v6 + (*((_WORD *)v6 + 15) & 1LL) + 4);
  SDB_RECORD::Touch(v6);
  v9 = *(_QWORD *)(v8 + 232);
  *(_QWORD *)(v8 + 232) = 0;
  LOBYTE(v10) = 3;
  v11 = SDB_CONFIG::CreateRecord(this, v10, v8, &v22, v21);
  *(_QWORD *)(v8 + 232) = v9;
  MetadataDrives = v11;
  if ( v11 >= 0 )
  {
    if ( (*(_BYTE *)(v22 + 30) & 1) != 0 )
      v12 = *(_QWORD *)(v22 + 40);
    else
      v12 = *(_QWORD *)(v22 + 32);
    v13 = (SC_SPARSE *)SC_ENV::Allocate(0x50u, 0x61587053u, 0, 0);
    if ( v13 )
      v13 = SC_SPARSE::SC_SPARSE(v13);
    *(_QWORD *)(v12 + 232) = v13;
    if ( !v13 )
      goto LABEL_23;
    MetadataDrives = SC_SPARSE::Initialize(v13, 0x10000000000uLL);
    if ( MetadataDrives < 0 )
      goto LABEL_24;
    MetadataDrives = SDB_SPACE_CONFIG::Load(this, (struct SDB_SPACE *)v8, &v21);
    if ( MetadataDrives < 0 )
      goto LABEL_24;
    v14 = v21;
    MetadataDrives = SDB_SPACE_CONFIG::GetMetadataDrives(
                       v21,
                       this,
                       (unsigned int *)(v8 + 336),
                       (struct _GUID **const)(v8 + 344));
    if ( v14 )
      (**(void (__fastcall ***)(SDB_SPACE_CONFIG *, __int64))v14)(v14, 1);
    if ( MetadataDrives < 0 )
      goto LABEL_24;
    MetadataDrives = SC_ENV::CreateGuid((struct _GUID *)(v8 + 32));
    if ( MetadataDrives < 0 )
      goto LABEL_24;
    v15 = *(_WORD *)(v8 + 64) & 0xFFC1;
    *(_BYTE *)(v8 + 66) = 8;
    *(_WORD *)(v8 + 64) = v15 | 1;
    MetadataDrives = SDB_POOL_CONFIG::AllocateConfigSpaceSlots(this, (struct SDB_SPACE *)v8);
    if ( MetadataDrives < 0 )
      goto LABEL_24;
    v16 = (SDB_SPACE_CONFIG *)SC_ENV::Allocate(0x170u, 0x6E427053u, 0, 0);
    if ( v16 && (v17 = SDB_SPACE_CONFIG::SDB_SPACE_CONFIG(v16), (v18 = v17) != 0) )
    {
      MetadataDrives = SDB_SPACE_CONFIG::Create(v17, this, (struct SDB_SPACE *)v8);
      (**(void (__fastcall ***)(SDB_SPACE_CONFIG *, __int64))v18)(v18, 1);
      if ( MetadataDrives >= 0 )
      {
        *(_DWORD *)(v12 + 192) = *((_DWORD *)v6 + 6);
        if ( a3 )
          *a3 = *(struct _GUID *)(v8 + 32);
      }
    }
    else
    {
LABEL_23:
      MetadataDrives = -1073741670;
    }
  }
LABEL_24:
  if ( v8 )
  {
    v19 = *(void **)(v8 + 344);
    if ( v19 )
    {
      *(_DWORD *)(v8 + 336) = 0;
      ExFreePoolWithTag(v19, 0);
      *(_QWORD *)(v8 + 344) = 0;
    }
  }
  return (unsigned int)MetadataDrives;
}

```

## disassembly

```asm
0x140065734  mov     rax, rsp
0x140065737  push    rbx
0x140065738  push    rbp
0x140065739  push    rsi
0x14006573a  push    rdi
0x14006573b  push    r12
0x14006573d  push    r13
0x14006573f  push    r14
0x140065741  push    r15
0x140065743  sub     rsp, 38h
0x140065747  mov     r13, r8
0x14006574a  mov     qword ptr [rax+20h], 0
0x140065752  mov     r14, rcx
0x140065755  mov     qword ptr [rax-58h], 0
0x14006575d  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x140065762  mov     rbp, rax
0x140065765  test    rax, rax
0x140065768  jnz     short loc_140065774
0x14006576a  mov     edi, 0C0380046h
0x14006576f  jmp     loc_140065976
0x140065774  xor     edx, edx; struct SDB_OBJECT *
0x140065776  mov     rcx, rbp; this
0x140065779  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x14006577e  mov     edi, eax
0x140065780  test    eax, eax
0x140065782  js      loc_140065976
0x140065788  movzx   eax, word ptr [rbp+1Eh]
0x14006578c  mov     r12d, 1
0x140065792  and     rax, r12
0x140065795  mov     rcx, rbp; this
0x140065798  mov     rsi, [rbp+rax*8+20h]
0x14006579d  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x1400657a2  mov     rbx, [rsi+0E8h]
0x1400657a9  lea     r9, [rsp+78h+arg_18]
0x1400657b1  mov     r8, rsi
0x1400657b4  mov     qword ptr [rsi+0E8h], 0
0x1400657bf  mov     dl, 3
0x1400657c1  mov     rcx, r14
0x1400657c4  call    ?CreateRecord@SDB_CONFIG@@QEAAJW4_SDB_RECORD_TYPE@@PEAVSDB_OBJECT@@PEAPEAVSDB_RECORD@@@Z; SDB_CONFIG::CreateRecord(_SDB_RECORD_TYPE,SDB_OBJECT *,SDB_RECORD * *)
0x1400657c9  mov     [rsi+0E8h], rbx
0x1400657d0  mov     edi, eax
0x1400657d2  test    eax, eax
0x1400657d4  js      loc_140065942
0x1400657da  mov     rcx, [rsp+78h+arg_18]
0x1400657e2  test    [rcx+1Eh], r12b
0x1400657e6  jz      short loc_1400657EE
0x1400657e8  mov     r15, [rcx+28h]
0x1400657ec  jmp     short loc_1400657F2
0x1400657ee  mov     r15, [rcx+20h]
0x1400657f2  xor     r9d, r9d; unsigned int
0x1400657f5  xor     r8d, r8d; unsigned __int8
0x1400657f8  mov     edx, 61587053h; unsigned int
0x1400657fd  lea     ecx, [r9+50h]; unsigned __int64
0x140065801  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140065806  test    rax, rax
0x140065809  jz      short loc_140065813
0x14006580b  mov     rcx, rax; this
0x14006580e  call    ??0SC_SPARSE@@QEAA@XZ; SC_SPARSE::SC_SPARSE(void)
0x140065813  mov     [r15+0E8h], rax
0x14006581a  test    rax, rax
0x14006581d  jz      loc_14006593D
0x140065823  mov     rdx, 10000000000h; unsigned __int64
0x14006582d  mov     rcx, rax; this
0x140065830  call    ?Initialize@SC_SPARSE@@QEAAJ_K@Z; SC_SPARSE::Initialize(unsigned __int64)
0x140065835  mov     edi, eax
0x140065837  test    eax, eax
0x140065839  js      loc_140065942
0x14006583f  lea     r8, [rsp+78h+var_58]; struct SDB_SPACE_CONFIG **
0x140065844  mov     rdx, rsi; struct SDB_SPACE *
0x140065847  mov     rcx, r14; struct SDB_POOL_CONFIG *
0x14006584a  call    ?Load@SDB_SPACE_CONFIG@@SAJPEAVSDB_POOL_CONFIG@@PEAVSDB_SPACE@@PEAPEAV1@@Z; SDB_SPACE_CONFIG::Load(SDB_POOL_CONFIG *,SDB_SPACE *,SDB_SPACE_CONFIG * *)
0x14006584f  mov     edi, eax
0x140065851  test    eax, eax
0x140065853  js      loc_140065942
0x140065859  mov     rbx, [rsp+78h+var_58]
0x14006585e  lea     r9, [rsi+158h]; struct _GUID **
0x140065865  mov     rcx, rbx; this
0x140065868  lea     r8, [rsi+150h]; unsigned int *
0x14006586f  mov     rdx, r14; struct SDB_POOL_CONFIG *
0x140065872  call    ?GetMetadataDrives@SDB_SPACE_CONFIG@@QEAAJPEAVSDB_POOL_CONFIG@@PEAKQEAPEAU_GUID@@@Z; SDB_SPACE_CONFIG::GetMetadataDrives(SDB_POOL_CONFIG *,ulong *,_GUID * * const)
0x140065877  mov     edi, eax
0x140065879  test    rbx, rbx
0x14006587c  jz      short loc_14006588F
0x14006587e  mov     rax, [rbx]
0x140065881  mov     edx, r12d
0x140065884  mov     rcx, rbx
0x140065887  mov     rax, [rax]
0x14006588a  call    _guard_dispatch_icall
0x14006588f  test    edi, edi
0x140065891  js      loc_140065942
0x140065897  lea     rcx, [rsi+20h]; struct _GUID *
0x14006589b  call    ?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z; SC_ENV::CreateGuid(_GUID *)
0x1400658a0  mov     edi, eax
0x1400658a2  test    eax, eax
0x1400658a4  js      loc_140065942
0x1400658aa  movzx   eax, word ptr [rsi+40h]
0x1400658ae  mov     ecx, 0FFC1h
0x1400658b3  and     ax, cx
0x1400658b6  mov     byte ptr [rsi+42h], 8
0x1400658ba  or      ax, r12w
0x1400658be  mov     rdx, rsi; struct SDB_SPACE *
0x1400658c1  mov     rcx, r14; this
0x1400658c4  mov     [rsi+40h], ax
0x1400658c8  call    ?AllocateConfigSpaceSlots@SDB_POOL_CONFIG@@QEAAJPEAVSDB_SPACE@@@Z; SDB_POOL_CONFIG::AllocateConfigSpaceSlots(SDB_SPACE *)
0x1400658cd  mov     edi, eax
0x1400658cf  test    eax, eax
0x1400658d1  js      short loc_140065942
0x1400658d3  xor     r9d, r9d; unsigned int
0x1400658d6  xor     r8d, r8d; unsigned __int8
0x1400658d9  mov     edx, 6E427053h; unsigned int
0x1400658de  mov     ecx, 170h; unsigned __int64
0x1400658e3  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400658e8  test    rax, rax
0x1400658eb  jz      short loc_14006593D
0x1400658ed  mov     rcx, rax; this
0x1400658f0  call    ??0SDB_SPACE_CONFIG@@QEAA@XZ; SDB_SPACE_CONFIG::SDB_SPACE_CONFIG(void)
0x1400658f5  mov     rbx, rax
0x1400658f8  test    rax, rax
0x1400658fb  jz      short loc_14006593D
0x1400658fd  mov     r8, rsi; struct SDB_SPACE *
0x140065900  mov     rdx, r14; struct SDB_POOL_CONFIG *
0x140065903  mov     rcx, rax; this
0x140065906  call    ?Create@SDB_SPACE_CONFIG@@QEAAJPEAVSDB_POOL_CONFIG@@PEAVSDB_SPACE@@@Z; SDB_SPACE_CONFIG::Create(SDB_POOL_CONFIG *,SDB_SPACE *)
0x14006590b  mov     rcx, [rbx]
0x14006590e  mov     edi, eax
0x140065910  mov     edx, r12d
0x140065913  mov     rax, [rcx]
0x140065916  mov     rcx, rbx
0x140065919  call    _guard_dispatch_icall
0x14006591e  test    edi, edi
0x140065920  js      short loc_140065942
0x140065922  mov     eax, [rbp+18h]
0x140065925  mov     [r15+0C0h], eax
0x14006592c  test    r13, r13
0x14006592f  jz      short loc_140065942
0x140065931  movups  xmm0, xmmword ptr [rsi+20h]
0x140065935  movdqu  xmmword ptr [r13+0], xmm0
0x14006593b  jmp     short loc_140065942
0x14006593d  mov     edi, 0C000009Ah
0x140065942  test    rsi, rsi
0x140065945  jz      short loc_140065976
0x140065947  mov     rcx, [rsi+158h]; P
0x14006594e  test    rcx, rcx
0x140065951  jz      short loc_140065976
0x140065953  xor     edx, edx; Tag
0x140065955  mov     dword ptr [rsi+150h], 0
0x14006595f  call    cs:__imp_ExFreePoolWithTag
0x140065966  nop     dword ptr [rax+rax+00h]
0x14006596b  mov     qword ptr [rsi+158h], 0
0x140065976  mov     eax, edi
0x140065978  add     rsp, 38h
0x14006597c  pop     r15
0x14006597e  pop     r14
0x140065980  pop     r13
0x140065982  pop     r12
0x140065984  pop     rdi
0x140065985  pop     rsi
0x140065986  pop     rbp
0x140065987  pop     rbx
0x140065988  retn
```
