# SDB_SPACE_CONFIG::Create(SDB_POOL_CONFIG *,SDB_SPACE *)

- ea: `0x14000d4f0`
- end: `0x14000d70a`
- name: `?Create@SDB_SPACE_CONFIG@@QEAAJPEAVSDB_POOL_CONFIG@@PEAVSDB_SPACE@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(SDB_SPACE_CONFIG *__hidden this, struct SDB_POOL_CONFIG *, struct SDB_SPACE *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140061a5c`
- `0x140065734`

## callees

- `0x14000bad0`
- `0x14000d4c0`
- `0x14000d4f0`
- `0x14000db70`
- `0x14000eba0`
- `0x14001fe40`
- `0x140025e50`
- `0x140026e00`
- `0x140027130`
- `0x1400594d0`
- `0x140059aec`
- `0x140060210`
- `0x140060a78`
- `0x1400662e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6a3`

## pseudocode

```c
__int64 __fastcall SDB_SPACE_CONFIG::Create(SS_STORE **this, struct SDB_POOL_CONFIG *a2, struct SDB_SPACE *a3)
{
  int v3; // r9d
  __int64 v4; // r15
  unsigned int v6; // ebp
  __int64 v8; // rdx
  __int64 result; // rax
  unsigned int i; // ebx
  struct SDB_RECORD *DriveById; // rax
  SDB_DRIVE *v13; // rcx
  struct SC_DRIVE *Drive; // rdi
  struct SDB_RECORD *v15; // r8
  int v16; // edi
  unsigned int v17; // ecx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // ebx
  _OWORD v21[4]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int8 v22; // [rsp+78h] [rbp+10h] BYREF
  struct SDB_RECORD *v23; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp+20h] BYREF

  v3 = *((_DWORD *)a3 + 21);
  v4 = *((_QWORD *)a3 + 43);
  v6 = *((_DWORD *)a3 + 84);
  v8 = *((unsigned int *)a2 + 12);
  v21[0] = *((_OWORD *)a3 + 2);
  v24 = 0;
  v23 = 0;
  v22 = 0;
  result = ((__int64 (__fastcall *)(SS_STORE **, __int64, _OWORD *, _QWORD))SDB_CONFIG::Create)(
             this,
             v8,
             v21,
             (unsigned int)(v3 << 22));
  if ( (int)result >= 0 )
  {
    for ( i = 0; i < v6; ++i )
    {
      DriveById = SDB_POOL_CONFIG::FindDriveById(a2, (struct _GUID *)(v4 + 16LL * i));
      v23 = DriveById;
      if ( !DriveById )
        return 3221226021LL;
      if ( (*((_BYTE *)DriveById + 30) & 1) != 0 )
        v13 = (SDB_DRIVE *)*((_QWORD *)DriveById + 5);
      else
        v13 = (SDB_DRIVE *)*((_QWORD *)DriveById + 4);
      Drive = SDB_DRIVE::GetDrive(v13);
      if ( Drive )
      {
        result = SDB_POOL_CONFIG::GetSpaceConfigSlotByDrive(a2, *((_DWORD *)a3 + 20), v15, &v24);
        if ( (int)result < 0 )
          return result;
        v16 = SDB_CONFIG::NewPath((SDB_CONFIG *)this, Drive, v24);
        if ( v16 < 0 )
        {
          SS_STORE::AbortPaths(this[1]);
          return (unsigned int)v16;
        }
      }
    }
    SS_STORE::CommitPaths(this[1]);
    v17 = *((_DWORD *)this + 12);
    if ( v17 > 0xA )
    {
      *((_DWORD *)this + 11) = *((_DWORD *)this + 10);
      v18 = *((_DWORD *)this + 4);
      *((_DWORD *)this + 13) = v17;
      *((_DWORD *)this + 5) = v18;
      result = SDB_SPACE_CONFIG::CreateMetadataRecord((SDB_SPACE_CONFIG *)this, &v23);
      if ( (int)result < 0 )
        return result;
      if ( (*((_BYTE *)v23 + 30) & 1) != 0 )
        v19 = *((_QWORD *)v23 + 5);
      else
        v19 = *((_QWORD *)v23 + 4);
      *(_DWORD *)(v19 + 32) = *((_DWORD *)a3 + 84);
      *(_QWORD *)(v19 + 40) = *((_QWORD *)a3 + 43);
      *((_DWORD *)a3 + 84) = 0;
      *((_QWORD *)a3 + 43) = 0;
      v20 = SDB_CONFIG::CommitTransaction((SDB_CONFIG *)this, &v22);
      if ( v20 < 0 )
      {
        SDB_CONFIG::AbortRecords((SDB_CONFIG *)this);
        return (unsigned int)v20;
      }
      SDB_CONFIG::CommitRecords((SDB_CONFIG *)this);
    }
    if ( *((_DWORD *)this + 12) <= 0xAu )
    {
      ExFreePoolWithTag(*((PVOID *)a3 + 43), 0);
      *((_QWORD *)a3 + 43) = 0;
      *((_DWORD *)a3 + 84) = 0;
    }
    SDB_SPACE_CONFIG::UpdateTolerance(this, *((unsigned int *)a3 + 30), v6, (char *)a3 + 32);
    this[35] = (SS_STORE *)*((_QWORD *)a3 + 34);
    return SC_SPARSE::Initialize((SC_SPARSE *)(this + 36), 0x10000000000uLL);
  }
  return result;
}

```

## disassembly

```asm
0x14000d4f0  mov     rax, rsp
0x14000d4f3  push    rbp
0x14000d4f4  push    rsi
0x14000d4f5  push    rdi
0x14000d4f6  push    r12
0x14000d4f8  push    r13
0x14000d4fa  push    r14
0x14000d4fc  push    r15
0x14000d4fe  sub     rsp, 30h
0x14000d502  movups  xmm0, xmmword ptr [r8+20h]
0x14000d507  mov     r9d, [r8+54h]
0x14000d50b  xor     edi, edi
0x14000d50d  mov     r15, [r8+158h]
0x14000d514  mov     r13, r8
0x14000d517  mov     ebp, [r8+150h]
0x14000d51e  mov     rsi, rdx
0x14000d521  mov     edx, [rdx+30h]
0x14000d524  lea     r8, [rax-48h]
0x14000d528  shl     r9d, 16h
0x14000d52c  mov     r14, rcx
0x14000d52f  movaps  xmmword ptr [rax-48h], xmm0
0x14000d533  mov     [rax+20h], rdi
0x14000d537  mov     [rax+18h], rdi
0x14000d53b  mov     [rax+10h], dil
0x14000d53f  call    ?Create@SDB_CONFIG@@QEAAJW4_SC_VERSION@@U_GUID@@K@Z; SDB_CONFIG::Create(_SC_VERSION,_GUID,ulong)
0x14000d544  test    eax, eax
0x14000d546  js      loc_14000D6F9
0x14000d54c  mov     [rsp+68h+arg_0], rbx
0x14000d551  mov     ebx, edi
0x14000d553  cmp     ebx, ebp
0x14000d555  jnb     loc_14000D5EC
0x14000d55b  mov     edx, ebx
0x14000d55d  mov     rcx, rsi; this
0x14000d560  shl     rdx, 4
0x14000d564  add     rdx, r15; struct _GUID *
0x14000d567  call    ?FindDriveById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindDriveById(_GUID *)
0x14000d56c  mov     [rsp+68h+arg_10], rax
0x14000d574  mov     r8, rax
0x14000d577  test    rax, rax
0x14000d57a  jz      short loc_14000D5E2
0x14000d57c  test    byte ptr [rax+1Eh], 1
0x14000d580  jz      short loc_14000D588
0x14000d582  mov     rcx, [rax+28h]
0x14000d586  jmp     short loc_14000D58C
0x14000d588  mov     rcx, [rax+20h]; this
0x14000d58c  call    ?GetDrive@SDB_DRIVE@@QEAAPEAVSC_DRIVE@@XZ; SDB_DRIVE::GetDrive(void)
0x14000d591  mov     rdi, rax
0x14000d594  test    rax, rax
0x14000d597  jz      short loc_14000D5CE
0x14000d599  mov     edx, [r13+50h]; unsigned int
0x14000d59d  lea     r9, [rsp+68h+arg_18]; unsigned __int64 *
0x14000d5a5  mov     rcx, rsi; this
0x14000d5a8  call    ?GetSpaceConfigSlotByDrive@SDB_POOL_CONFIG@@QEAAJKPEAVSDB_RECORD@@PEA_K@Z; SDB_POOL_CONFIG::GetSpaceConfigSlotByDrive(ulong,SDB_RECORD *,unsigned __int64 *)
0x14000d5ad  test    eax, eax
0x14000d5af  js      loc_14000D6F4
0x14000d5b5  mov     r8, [rsp+68h+arg_18]; unsigned __int64
0x14000d5bd  mov     rdx, rdi; struct SC_DRIVE *
0x14000d5c0  mov     rcx, r14; this
0x14000d5c3  call    ?NewPath@SDB_CONFIG@@QEAAJPEAVSC_DRIVE@@_K@Z; SDB_CONFIG::NewPath(SC_DRIVE *,unsigned __int64)
0x14000d5c8  mov     edi, eax
0x14000d5ca  test    eax, eax
0x14000d5cc  js      short loc_14000D5D2
0x14000d5ce  inc     ebx
0x14000d5d0  jmp     short loc_14000D553
0x14000d5d2  mov     rcx, [r14+8]; this
0x14000d5d6  call    ?AbortPaths@SS_STORE@@QEAAXXZ; SS_STORE::AbortPaths(void)
0x14000d5db  mov     eax, edi
0x14000d5dd  jmp     loc_14000D6F4
0x14000d5e2  mov     eax, 0C0000225h
0x14000d5e7  jmp     loc_14000D6F4
0x14000d5ec  mov     rcx, [r14+8]; this
0x14000d5f0  call    ?CommitPaths@SS_STORE@@QEAAXXZ; SS_STORE::CommitPaths(void)
0x14000d5f5  mov     ecx, [r14+30h]
0x14000d5f9  cmp     ecx, 0Ah
0x14000d5fc  jbe     loc_14000D691
0x14000d602  mov     eax, [r14+28h]
0x14000d606  lea     rdx, [rsp+68h+arg_10]; struct SDB_RECORD **
0x14000d60e  mov     [r14+2Ch], eax
0x14000d612  mov     eax, [r14+10h]
0x14000d616  mov     [r14+34h], ecx
0x14000d61a  mov     rcx, r14; this
0x14000d61d  mov     [r14+14h], eax
0x14000d621  call    ?CreateMetadataRecord@SDB_SPACE_CONFIG@@AEAAJPEAPEAVSDB_RECORD@@@Z; SDB_SPACE_CONFIG::CreateMetadataRecord(SDB_RECORD * *)
0x14000d626  test    eax, eax
0x14000d628  js      loc_14000D6F4
0x14000d62e  mov     rcx, [rsp+68h+arg_10]
0x14000d636  test    byte ptr [rcx+1Eh], 1
0x14000d63a  jz      short loc_14000D642
0x14000d63c  mov     rdx, [rcx+28h]
0x14000d640  jmp     short loc_14000D646
0x14000d642  mov     rdx, [rcx+20h]
0x14000d646  mov     eax, [r13+150h]
0x14000d64d  xor     edi, edi
0x14000d64f  mov     [rdx+20h], eax
0x14000d652  mov     rcx, r14; this
0x14000d655  mov     rax, [r13+158h]
0x14000d65c  mov     [rdx+28h], rax
0x14000d660  lea     rdx, [rsp+68h+arg_8]; unsigned __int8 *
0x14000d665  mov     [r13+150h], edi
0x14000d66c  mov     [r13+158h], rdi
0x14000d673  call    ?CommitTransaction@SDB_CONFIG@@QEAAJPEAE@Z; SDB_CONFIG::CommitTransaction(uchar *)
0x14000d678  mov     ebx, eax
0x14000d67a  mov     rcx, r14; this
0x14000d67d  test    eax, eax
0x14000d67f  jns     short loc_14000D68A
0x14000d681  call    ?AbortRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::AbortRecords(void)
0x14000d686  mov     eax, ebx
0x14000d688  jmp     short loc_14000D6F4
0x14000d68a  call    ?CommitRecords@SDB_CONFIG@@QEAAXXZ; SDB_CONFIG::CommitRecords(void)
0x14000d68f  jmp     short loc_14000D693
0x14000d691  xor     edi, edi
0x14000d693  cmp     dword ptr [r14+30h], 0Ah
0x14000d698  ja      short loc_14000D6BD
0x14000d69a  mov     rcx, [r13+158h]; P
0x14000d6a1  xor     edx, edx; Tag
0x14000d6a3  call    cs:__imp_ExFreePoolWithTag
0x14000d6aa  nop     dword ptr [rax+rax+00h]
0x14000d6af  mov     [r13+158h], rdi
0x14000d6b6  mov     [r13+150h], edi
0x14000d6bd  mov     edx, [r13+78h]
0x14000d6c1  lea     r9, [r13+20h]
0x14000d6c5  mov     r8d, ebp
0x14000d6c8  mov     rcx, r14
0x14000d6cb  call    ?UpdateTolerance@SDB_SPACE_CONFIG@@QEAAXW4_SC_FD_TYPE@@KPEAU_GUID@@@Z; SDB_SPACE_CONFIG::UpdateTolerance(_SC_FD_TYPE,ulong,_GUID *)
0x14000d6d0  mov     rax, [r13+110h]
0x14000d6d7  lea     rcx, [r14+120h]; this
0x14000d6de  mov     rdx, 10000000000h; unsigned __int64
0x14000d6e8  mov     [r14+118h], rax
0x14000d6ef  call    ?Initialize@SC_SPARSE@@QEAAJ_K@Z; SC_SPARSE::Initialize(unsigned __int64)
0x14000d6f4  mov     rbx, [rsp+68h+arg_0]
0x14000d6f9  add     rsp, 30h
0x14000d6fd  pop     r15
0x14000d6ff  pop     r14
0x14000d701  pop     r13
0x14000d703  pop     r12
0x14000d705  pop     rdi
0x14000d706  pop     rsi
0x14000d707  pop     rbp
0x14000d708  retn
```
