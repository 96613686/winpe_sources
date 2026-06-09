# SDB_POOL_CONFIG::SnapshotSpaceTransaction(_GUID *,_GUID *)

- ea: `0x140065884`
- end: `0x140065ada`
- name: `?SnapshotSpaceTransaction@SDB_POOL_CONFIG@@QEAAJPEAU_GUID@@0@Z`
- size: `598`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x140061410`
- `0x140063ad0`

## callees

- `0x14000b3e0`
- `0x14000d4f0`
- `0x14001e760`
- `0x140026790`
- `0x1400268c0`
- `0x140026e00`
- `0x14006016c`
- `0x140060588`
- `0x1400620a0`
- `0x1400631d0`
- `0x140065884`
- `0x140068150`
- `0x14009d6cc`
- `0x1400b3544`
- `0x1400b6cb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140065aaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065aaf`

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
0x140065884  mov     rax, rsp
0x140065887  push    rbx
0x140065888  push    rbp
0x140065889  push    rsi
0x14006588a  push    rdi
0x14006588b  push    r12
0x14006588d  push    r13
0x14006588f  push    r14
0x140065891  push    r15
0x140065893  sub     rsp, 38h
0x140065897  mov     r13, r8
0x14006589a  mov     qword ptr [rax+20h], 0
0x1400658a2  mov     r14, rcx
0x1400658a5  mov     qword ptr [rax-58h], 0
0x1400658ad  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x1400658b2  mov     rbp, rax
0x1400658b5  test    rax, rax
0x1400658b8  jnz     short loc_1400658C4
0x1400658ba  mov     edi, 0C0380046h
0x1400658bf  jmp     loc_140065AC6
0x1400658c4  xor     edx, edx; struct SDB_OBJECT *
0x1400658c6  mov     rcx, rbp; this
0x1400658c9  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x1400658ce  mov     edi, eax
0x1400658d0  test    eax, eax
0x1400658d2  js      loc_140065AC6
0x1400658d8  movzx   eax, word ptr [rbp+1Eh]
0x1400658dc  mov     r12d, 1
0x1400658e2  and     rax, r12
0x1400658e5  mov     rcx, rbp; this
0x1400658e8  mov     rsi, [rbp+rax*8+20h]
0x1400658ed  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x1400658f2  mov     rbx, [rsi+0E8h]
0x1400658f9  lea     r9, [rsp+78h+arg_18]
0x140065901  mov     r8, rsi
0x140065904  mov     qword ptr [rsi+0E8h], 0
0x14006590f  mov     dl, 3
0x140065911  mov     rcx, r14
0x140065914  call    ?CreateRecord@SDB_CONFIG@@QEAAJW4_SDB_RECORD_TYPE@@PEAVSDB_OBJECT@@PEAPEAVSDB_RECORD@@@Z; SDB_CONFIG::CreateRecord(_SDB_RECORD_TYPE,SDB_OBJECT *,SDB_RECORD * *)
0x140065919  mov     [rsi+0E8h], rbx
0x140065920  mov     edi, eax
0x140065922  test    eax, eax
0x140065924  js      loc_140065A92
0x14006592a  mov     rcx, [rsp+78h+arg_18]
0x140065932  test    [rcx+1Eh], r12b
0x140065936  jz      short loc_14006593E
0x140065938  mov     r15, [rcx+28h]
0x14006593c  jmp     short loc_140065942
0x14006593e  mov     r15, [rcx+20h]
0x140065942  xor     r9d, r9d; unsigned int
0x140065945  xor     r8d, r8d; unsigned __int8
0x140065948  mov     edx, 61587053h; unsigned int
0x14006594d  lea     ecx, [r9+50h]; unsigned __int64
0x140065951  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140065956  test    rax, rax
0x140065959  jz      short loc_140065963
0x14006595b  mov     rcx, rax; this
0x14006595e  call    ??0SC_SPARSE@@QEAA@XZ; SC_SPARSE::SC_SPARSE(void)
0x140065963  mov     [r15+0E8h], rax
0x14006596a  test    rax, rax
0x14006596d  jz      loc_140065A8D
0x140065973  mov     rdx, 10000000000h; unsigned __int64
0x14006597d  mov     rcx, rax; this
0x140065980  call    ?Initialize@SC_SPARSE@@QEAAJ_K@Z; SC_SPARSE::Initialize(unsigned __int64)
0x140065985  mov     edi, eax
0x140065987  test    eax, eax
0x140065989  js      loc_140065A92
0x14006598f  lea     r8, [rsp+78h+var_58]; struct SDB_SPACE_CONFIG **
0x140065994  mov     rdx, rsi; struct SDB_SPACE *
0x140065997  mov     rcx, r14; struct SDB_POOL_CONFIG *
0x14006599a  call    ?Load@SDB_SPACE_CONFIG@@SAJPEAVSDB_POOL_CONFIG@@PEAVSDB_SPACE@@PEAPEAV1@@Z; SDB_SPACE_CONFIG::Load(SDB_POOL_CONFIG *,SDB_SPACE *,SDB_SPACE_CONFIG * *)
0x14006599f  mov     edi, eax
0x1400659a1  test    eax, eax
0x1400659a3  js      loc_140065A92
0x1400659a9  mov     rbx, [rsp+78h+var_58]
0x1400659ae  lea     r9, [rsi+158h]; struct _GUID **
0x1400659b5  mov     rcx, rbx; this
0x1400659b8  lea     r8, [rsi+150h]; unsigned int *
0x1400659bf  mov     rdx, r14; struct SDB_POOL_CONFIG *
0x1400659c2  call    ?GetMetadataDrives@SDB_SPACE_CONFIG@@QEAAJPEAVSDB_POOL_CONFIG@@PEAKQEAPEAU_GUID@@@Z; SDB_SPACE_CONFIG::GetMetadataDrives(SDB_POOL_CONFIG *,ulong *,_GUID * * const)
0x1400659c7  mov     edi, eax
0x1400659c9  test    rbx, rbx
0x1400659cc  jz      short loc_1400659DF
0x1400659ce  mov     rax, [rbx]
0x1400659d1  mov     edx, r12d
0x1400659d4  mov     rcx, rbx
0x1400659d7  mov     rax, [rax]
0x1400659da  call    _guard_dispatch_icall
0x1400659df  test    edi, edi
0x1400659e1  js      loc_140065A92
0x1400659e7  lea     rcx, [rsi+20h]; struct _GUID *
0x1400659eb  call    ?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z; SC_ENV::CreateGuid(_GUID *)
0x1400659f0  mov     edi, eax
0x1400659f2  test    eax, eax
0x1400659f4  js      loc_140065A92
0x1400659fa  movzx   eax, word ptr [rsi+40h]
0x1400659fe  mov     ecx, 0FFC1h
0x140065a03  and     ax, cx
0x140065a06  mov     byte ptr [rsi+42h], 8
0x140065a0a  or      ax, r12w
0x140065a0e  mov     rdx, rsi; struct SDB_SPACE *
0x140065a11  mov     rcx, r14; this
0x140065a14  mov     [rsi+40h], ax
0x140065a18  call    ?AllocateConfigSpaceSlots@SDB_POOL_CONFIG@@QEAAJPEAVSDB_SPACE@@@Z; SDB_POOL_CONFIG::AllocateConfigSpaceSlots(SDB_SPACE *)
0x140065a1d  mov     edi, eax
0x140065a1f  test    eax, eax
0x140065a21  js      short loc_140065A92
0x140065a23  xor     r9d, r9d; unsigned int
0x140065a26  xor     r8d, r8d; unsigned __int8
0x140065a29  mov     edx, 6E427053h; unsigned int
0x140065a2e  mov     ecx, 170h; unsigned __int64
0x140065a33  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140065a38  test    rax, rax
0x140065a3b  jz      short loc_140065A8D
0x140065a3d  mov     rcx, rax; this
0x140065a40  call    ??0SDB_SPACE_CONFIG@@QEAA@XZ; SDB_SPACE_CONFIG::SDB_SPACE_CONFIG(void)
0x140065a45  mov     rbx, rax
0x140065a48  test    rax, rax
0x140065a4b  jz      short loc_140065A8D
0x140065a4d  mov     r8, rsi; struct SDB_SPACE *
0x140065a50  mov     rdx, r14; struct SDB_POOL_CONFIG *
0x140065a53  mov     rcx, rax; this
0x140065a56  call    ?Create@SDB_SPACE_CONFIG@@QEAAJPEAVSDB_POOL_CONFIG@@PEAVSDB_SPACE@@@Z; SDB_SPACE_CONFIG::Create(SDB_POOL_CONFIG *,SDB_SPACE *)
0x140065a5b  mov     rcx, [rbx]
0x140065a5e  mov     edi, eax
0x140065a60  mov     edx, r12d
0x140065a63  mov     rax, [rcx]
0x140065a66  mov     rcx, rbx
0x140065a69  call    _guard_dispatch_icall
0x140065a6e  test    edi, edi
0x140065a70  js      short loc_140065A92
0x140065a72  mov     eax, [rbp+18h]
0x140065a75  mov     [r15+0C0h], eax
0x140065a7c  test    r13, r13
0x140065a7f  jz      short loc_140065A92
0x140065a81  movups  xmm0, xmmword ptr [rsi+20h]
0x140065a85  movdqu  xmmword ptr [r13+0], xmm0
0x140065a8b  jmp     short loc_140065A92
0x140065a8d  mov     edi, 0C000009Ah
0x140065a92  test    rsi, rsi
0x140065a95  jz      short loc_140065AC6
0x140065a97  mov     rcx, [rsi+158h]; P
0x140065a9e  test    rcx, rcx
0x140065aa1  jz      short loc_140065AC6
0x140065aa3  xor     edx, edx; Tag
0x140065aa5  mov     dword ptr [rsi+150h], 0
0x140065aaf  call    cs:__imp_ExFreePoolWithTag
0x140065ab6  nop     dword ptr [rax+rax+00h]
0x140065abb  mov     qword ptr [rsi+158h], 0
0x140065ac6  mov     eax, edi
0x140065ac8  add     rsp, 38h
0x140065acc  pop     r15
0x140065ace  pop     r14
0x140065ad0  pop     r13
0x140065ad2  pop     r12
0x140065ad4  pop     rdi
0x140065ad5  pop     rsi
0x140065ad6  pop     rbp
0x140065ad7  pop     rbx
0x140065ad8  retn
```
