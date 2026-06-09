# RecordCache::GetRecord(ulong,Buffer &,ulong &)

- ea: `0x1800377a8`
- end: `0x1800379fd`
- name: `?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z`
- size: `597`
- prototype: `bool __fastcall(RecordCache *__hidden this, unsigned int, struct Buffer *, unsigned int *)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18003732c`
- `0x180037500`
- `0x1800381e0`
- `0x180038354`

## callees

- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x180012cb0`
- `0x1800169e8`
- `0x180023548`
- `0x1800377a8`
- `0x1800384e8`
- `0x1800385dc`
- `0x18003871c`
- `0x18003881c`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003781a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003781a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003785a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800379d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003785a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800379d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall RecordCache::GetRecord(RecordCache *this, unsigned int a2, struct Buffer *a3, unsigned int *a4)
{
  int v8; // r15d
  char v9; // si
  __int64 v11; // rbx
  unsigned int v12; // edx
  _BYTE v13[32]; // [rsp+20h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]
  int v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+B8h] [rbp+48h]

  v8 = *((_DWORD *)a3 + 5);
  v19 = *((_DWORD *)a3 + 4);
  v9 = 1;
  Buffer::Buffer((Buffer *)v13, 0, 0, 1);
  Buffer::Set((Buffer *)v13, (const unsigned __int8 *)this + 968, 8u);
  Buffer::SetCurrentIndex((Buffer *)v13, 8u);
  AcquireSRWLockExclusive((PSRWLOCK)this + 8);
  *a4 = 0;
  if ( (a2 / 0x64 == *((_DWORD *)this + 36) || RecordCache::SeekToBlock(this, a2))
    && RecordCache::SeekToRecord(this, a2) )
  {
    v11 = *((_QWORD *)this + 2);
    if ( (unsigned __int64)(v11 + 8) > *((_QWORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 259;
      throw (EvtException *)&pExceptionObject;
    }
    RecordCache::ReadBytes((HANDLE *)this, (struct Buffer *)v13);
    if ( *((_QWORD *)this + 2) + (unsigned __int64)*((unsigned int *)this + 243) > *((_QWORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 268;
      throw (EvtException *)&pExceptionObject;
    }
    *a4 = *((_DWORD *)this + 243);
    v12 = *((_DWORD *)this + 243);
    if ( v8 - v19 < v12 )
    {
      v9 = 0;
      RecordCache::Seek(this, v11 - *((_QWORD *)this + 122));
    }
    else
    {
      Buffer::SetCurrentIndex((RecordCache *)((char *)this + 992), v12);
      RecordCache::ReadBytes((HANDLE *)this, (RecordCache *)((char *)this + 992));
      Buffer::Write(a3, *((const void **)this + 125), *((_DWORD *)this + 252));
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    Buffer::~Buffer((Buffer *)v13);
    return v9;
  }
  else
  {
    ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    Buffer::~Buffer((Buffer *)v13);
    return 0;
  }
}

```

## disassembly

```asm
0x1800377a8  mov     [rsp-38h+arg_10], rbx
0x1800377ad  push    rbp
0x1800377ae  push    rsi
0x1800377af  push    rdi
0x1800377b0  push    r12
0x1800377b2  push    r13
0x1800377b4  push    r14
0x1800377b6  push    r15
0x1800377b8  mov     rbp, rsp
0x1800377bb  sub     rsp, 70h
0x1800377bf  mov     r12, r9
0x1800377c2  mov     r13, r8
0x1800377c5  mov     ebx, edx
0x1800377c7  mov     rdi, rcx
0x1800377ca  mov     r15d, [r8+14h]
0x1800377ce  mov     eax, [r8+10h]
0x1800377d2  mov     [rbp+arg_8], eax
0x1800377d5  mov     sil, 1
0x1800377d8  mov     r9b, sil; bool
0x1800377db  xor     r8d, r8d; unsigned int
0x1800377de  xor     edx, edx; unsigned __int8 *
0x1800377e0  lea     rcx, [rbp+var_50]; this
0x1800377e4  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x1800377e9  nop
0x1800377ea  lea     rdx, [rdi+3C8h]; unsigned __int8 *
0x1800377f1  mov     r14d, 8
0x1800377f7  mov     r8d, r14d; unsigned int
0x1800377fa  lea     rcx, [rbp+var_50]; this
0x1800377fe  call    ?Set@Buffer@@QEAAXPEBEK@Z; Buffer::Set(uchar const *,ulong)
0x180037803  mov     edx, r14d; unsigned int
0x180037806  lea     rcx, [rbp+var_50]; this
0x18003780a  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18003780f  lea     r14, [rdi+40h]
0x180037813  mov     [rbp+arg_0], r14
0x180037817  mov     rcx, r14; SRWLock
0x18003781a  call    cs:__imp_AcquireSRWLockExclusive
0x180037820  nop
0x180037821  mov     dword ptr [r12], 0
0x180037829  mov     eax, 51EB851Fh
0x18003782e  mul     ebx
0x180037830  shr     edx, 5
0x180037833  cmp     edx, [rdi+90h]
0x180037839  jz      short loc_180037849
0x18003783b  mov     edx, ebx; unsigned int
0x18003783d  mov     rcx, rdi; this
0x180037840  call    ?SeekToBlock@RecordCache@@AEAA_NK@Z; RecordCache::SeekToBlock(ulong)
0x180037845  test    al, al
0x180037847  jz      short loc_180037857
0x180037849  mov     edx, ebx; unsigned int
0x18003784b  mov     rcx, rdi; this
0x18003784e  call    ?SeekToRecord@RecordCache@@AEAA_NK@Z; RecordCache::SeekToRecord(ulong)
0x180037853  test    al, al
0x180037855  jnz     short loc_180037871
0x180037857  mov     rcx, r14; SRWLock
0x18003785a  call    cs:__imp_ReleaseSRWLockExclusive
0x180037860  nop
0x180037861  lea     rcx, [rbp+var_50]; this
0x180037865  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003786a  xor     al, al
0x18003786c  jmp     loc_1800379E5
0x180037871  mov     rbx, [rdi+10h]
0x180037875  lea     rax, [rbx+8]
0x180037879  cmp     rax, [rdi+8]
0x18003787d  jbe     short loc_1800378EA
0x18003787f  lea     rax, WPP_GLOBAL_Control
0x180037886  mov     ebx, 0Dh
0x18003788b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037892  cmp     rcx, rax
0x180037895  jz      short loc_1800378B8
0x180037897  test    [rcx+1Ch], sil
0x18003789b  jz      short loc_1800378B8
0x18003789d  cmp     byte ptr [rcx+19h], 2
0x1800378a1  jb      short loc_1800378B8
0x1800378a3  mov     edx, ebx
0x1800378a5  mov     r9d, ebx
0x1800378a8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800378af  mov     rcx, [rcx+10h]
0x1800378b3  call    WPP_SF_D
0x1800378b8  xorps   xmm0, xmm0
0x1800378bb  movdqu  [rbp+pExceptionObject], xmm0
0x1800378c0  mov     [rbp+var_20], 0
0x1800378c8  mov     [rbp+var_18], ebx
0x1800378cb  mov     [rbp+var_14], 0FFFFFFFFh
0x1800378d2  mov     [rbp+var_10], 103h
0x1800378d9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800378e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800378e4  call    _CxxThrowException_0
0x1800378ea  lea     rdx, [rbp+var_50]; struct Buffer *
0x1800378ee  mov     rcx, rdi; this
0x1800378f1  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x1800378f6  mov     ecx, [rdi+3CCh]
0x1800378fc  mov     eax, ecx
0x1800378fe  add     rax, [rdi+10h]
0x180037902  cmp     rax, [rdi+8]
0x180037906  jbe     short loc_180037974
0x180037908  lea     rax, WPP_GLOBAL_Control
0x18003790f  mov     ebx, 0Dh
0x180037914  mov     rcx, cs:WPP_GLOBAL_Control
0x18003791b  cmp     rcx, rax
0x18003791e  jz      short loc_180037942
0x180037920  test    [rcx+1Ch], sil
0x180037924  jz      short loc_180037942
0x180037926  cmp     byte ptr [rcx+19h], 2
0x18003792a  jb      short loc_180037942
0x18003792c  lea     edx, [rbx+1]
0x18003792f  mov     r9d, ebx
0x180037932  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037939  mov     rcx, [rcx+10h]
0x18003793d  call    WPP_SF_D
0x180037942  xorps   xmm0, xmm0
0x180037945  movdqu  [rbp+pExceptionObject], xmm0
0x18003794a  mov     [rbp+var_20], 0
0x180037952  mov     [rbp+var_18], ebx
0x180037955  mov     [rbp+var_14], 0FFFFFFFFh
0x18003795c  mov     [rbp+var_10], 10Ch
0x180037963  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003796a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003796e  call    _CxxThrowException_0
0x180037974  mov     [r12], ecx
0x180037978  mov     edx, [rdi+3CCh]; unsigned int
0x18003797e  sub     r15d, [rbp+arg_8]
0x180037982  cmp     r15d, edx
0x180037985  jb      short loc_1800379B9
0x180037987  lea     rbx, [rdi+3E0h]
0x18003798e  mov     rcx, rbx; this
0x180037991  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x180037996  mov     rdx, rbx; struct Buffer *
0x180037999  mov     rcx, rdi; this
0x18003799c  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x1800379a1  mov     r8d, [rdi+3F0h]; unsigned int
0x1800379a8  mov     rdx, [rdi+3E8h]; void *
0x1800379af  mov     rcx, r13; this
0x1800379b2  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x1800379b7  jmp     short loc_1800379CF
0x1800379b9  xor     sil, sil
0x1800379bc  sub     rbx, [rdi+3D0h]
0x1800379c3  mov     rdx, rbx; unsigned __int64
0x1800379c6  mov     rcx, rdi; this
0x1800379c9  call    ?Seek@RecordCache@@IEAAX_K@Z; RecordCache::Seek(unsigned __int64)
0x1800379ce  nop
0x1800379cf  mov     rcx, r14; SRWLock
0x1800379d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800379d8  nop
0x1800379d9  lea     rcx, [rbp+var_50]; this
0x1800379dd  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800379e2  mov     al, sil
0x1800379e5  mov     rbx, [rsp+70h+arg_10]
0x1800379ed  add     rsp, 70h
0x1800379f1  pop     r15
0x1800379f3  pop     r14
0x1800379f5  pop     r13
0x1800379f7  pop     r12
0x1800379f9  pop     rdi
0x1800379fa  pop     rsi
0x1800379fb  pop     rbp
0x1800379fc  retn
```
