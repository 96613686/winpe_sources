# CTftpReadFileManager::PurgeModifiedFileReaders(void)

- ea: `0x18000a014`
- end: `0x18000a244`
- name: `?PurgeModifiedFileReaders@CTftpReadFileManager@@QEAAXXZ`
- size: `560`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180002ad0`

## callees

- `0x180005850`
- `0x180009614`
- `0x18000a014`
- `0x18000a68c`
- `0x18000a800`
- `0x18000a960`
- `0x18000c49c`
- `0x18003c084`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a033`
- `KERNEL32!EnterCriticalSection` at `0x18000a033`
- `KERNEL32!LeaveCriticalSection` at `0x18000a211`
- `KERNEL32!LeaveCriticalSection` at `0x18000a211`

## string_xrefs

- `0x18000a04b`: `CTftpReadFileManager::PurgeModifiedFileReaders: Trying to purge unreferenced files that are modified since opening.`
- `0x18000a17d`: `CTftpReadFileManager::PurgeModifiedFileReaders: Deleting an unreferenced file that is modified since opening: %s (CacheSize = %I64u bytes).`

## pseudocode

```c
void __fastcall CTftpReadFileManager::PurgeModifiedFileReaders(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rbx
  unsigned int *v6; // rcx
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int *v10; // rcx
  unsigned int v11; // edx
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-50h]
  __int128 v16; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h] BYREF
  void *v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+5Ch] [rbp-14h]

  v18 = 0;
  v19 = 0;
  v20 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(
      0x20000u,
      L"CTftpReadFileManager::PurgeModifiedFileReaders: Trying to purge unreferenced files that are modified since opening.");
  v2 = 0;
  v3 = *(_QWORD *)&lpCriticalSection[3].LockCount;
  *(_QWORD *)&v16 = 0;
  if ( v3 )
  {
    *((_QWORD *)&v16 + 1) = v3;
  }
  else
  {
    *((_QWORD *)&v16 + 1) = 0;
    CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(&lpCriticalSection[3], &v16);
    v2 = v16;
  }
  v17 = v16;
  if ( !v2 )
  {
    v4 = v17;
    do
    {
      v5 = 0;
      if ( !v4 )
        v5 = *((_QWORD *)&v17 + 1);
      if ( *(_DWORD *)(v5 + 48)
        || !_InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0)
        || !(unsigned int)CTptReadFile::ModifiedSinceOpen(*(LPCRITICAL_SECTION *)(v5 + 88)) )
      {
        CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(&lpCriticalSection[3], &v17);
        goto LABEL_33;
      }
      CSmHashTable<CTftpFileReader,CNoLock,113>::EnumRemoveAt(&lpCriticalSection[3], &v17);
      CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v18);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0) )
      {
        v6 = *(unsigned int **)(v5 + 88);
        v7 = v6[31];
        if ( v7 )
        {
          if ( v7 != 1 )
          {
            v8 = 0;
            goto LABEL_21;
          }
          v9 = v6[40];
        }
        else
        {
          v9 = v6[27];
        }
        v8 = v6[26] * v9;
      }
      else
      {
        v8 = 0;
      }
LABEL_21:
      lpCriticalSection[1].OwningThread = (char *)lpCriticalSection[1].OwningThread - v8;
      if ( g_ErrLibTraceFunctionEx )
      {
        _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0);
        g_ErrLibTraceFunctionEx(
          0x20000u,
          L"CTftpReadFileManager::PurgeModifiedFileReaders: Deleting an unreferenced file that is modified since opening: "
           "%s (CacheSize = %I64u bytes).",
          *(_QWORD *)(v5 + 72));
      }
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0) )
      {
        v12 = 0;
        goto LABEL_31;
      }
      v10 = *(unsigned int **)(v5 + 88);
      v11 = v10[31];
      if ( !v11 )
      {
        v13 = v10[27];
        goto LABEL_28;
      }
      if ( v11 == 1 )
      {
        v13 = v10[40];
LABEL_28:
        v12 = v10[26] * v13;
        goto LABEL_31;
      }
      v12 = 0;
LABEL_31:
      LODWORD(v15) = v12 >> 10;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 8, 1, v15);
LABEL_33:
      v4 = v17;
    }
    while ( !(_DWORD)v17 );
  }
  LeaveCriticalSection(lpCriticalSection);
  CTftpReadFileManager::DeleteFileReaders(v14, (__int64 **)&v18);
  if ( v18 )
    operator delete(v18);
}

```

## disassembly

```asm
0x18000a014  mov     [rsp-18h+arg_18], rbx
0x18000a019  push    rbp
0x18000a01a  push    rsi
0x18000a01b  push    rdi
0x18000a01c  mov     rbp, rsp
0x18000a01f  sub     rsp, 70h
0x18000a023  and     [rbp+var_20], 0
0x18000a028  mov     rdi, rcx
0x18000a02b  and     [rbp+var_18], 0
0x18000a02f  and     [rbp+var_14], 0
0x18000a033  call    cs:__imp_EnterCriticalSection
0x18000a03a  nop     dword ptr [rax+rax+00h]
0x18000a03f  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a046  test    rax, rax
0x18000a049  jz      short loc_18000A05D
0x18000a04b  lea     rdx, aCtftpreadfilem_4; "CTftpReadFileManager::PurgeModifiedFile"...
0x18000a052  mov     ecx, 20000h
0x18000a057  call    cs:__guard_dispatch_icall_fptr
0x18000a05d  xor     eax, eax
0x18000a05f  lea     rsi, [rdi+78h]
0x18000a063  mov     rcx, [rsi+8]
0x18000a067  mov     qword ptr [rbp+var_40], rax
0x18000a06b  test    rcx, rcx
0x18000a06e  jnz     short loc_18000A086
0x18000a070  and     qword ptr [rbp+var_40+8], rax
0x18000a074  lea     rdx, [rbp+var_40]
0x18000a078  mov     rcx, rsi
0x18000a07b  call    ?MoveNext@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000a080  mov     rax, qword ptr [rbp+var_40]
0x18000a084  jmp     short loc_18000A08A
0x18000a086  mov     qword ptr [rbp+var_40+8], rcx
0x18000a08a  movaps  xmm0, [rbp+var_40]
0x18000a08e  movdqa  [rbp+var_30], xmm0
0x18000a093  test    eax, eax
0x18000a095  jnz     loc_18000A20E
0x18000a09b  mov     eax, dword ptr [rbp+var_30]
0x18000a09e  xor     ebx, ebx
0x18000a0a0  test    eax, eax
0x18000a0a2  jnz     short loc_18000A0A8
0x18000a0a4  mov     rbx, qword ptr [rbp+var_30+8]
0x18000a0a8  cmp     dword ptr [rbx+30h], 0
0x18000a0ac  jnz     loc_18000A1F7
0x18000a0b2  xor     eax, eax
0x18000a0b4  lock xadd [rbx+38h], eax
0x18000a0b9  test    eax, eax
0x18000a0bb  jz      loc_18000A1F7
0x18000a0c1  mov     rcx, [rbx+58h]; lpCriticalSection
0x18000a0c5  call    ?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ; CTptReadFile::ModifiedSinceOpen(void)
0x18000a0ca  test    eax, eax
0x18000a0cc  jz      loc_18000A1F7
0x18000a0d2  lea     rdx, [rbp+var_30]
0x18000a0d6  mov     rcx, rsi
0x18000a0d9  call    ?EnumRemoveAt@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@QEAAPEAVCTftpFileReader@@AEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)
0x18000a0de  mov     rdx, rbx
0x18000a0e1  lea     rcx, [rbp+var_20]
0x18000a0e5  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x18000a0ea  xor     eax, eax
0x18000a0ec  mov     [rbp+arg_0], rax
0x18000a0f0  lock xadd [rbx+38h], eax
0x18000a0f5  test    eax, eax
0x18000a0f7  jz      short loc_18000A125
0x18000a0f9  mov     rcx, [rbx+58h]
0x18000a0fd  mov     edx, [rcx+7Ch]
0x18000a100  test    edx, edx
0x18000a102  jz      short loc_18000A120
0x18000a104  cmp     edx, 1
0x18000a107  jz      short loc_18000A10D
0x18000a109  xor     eax, eax
0x18000a10b  jmp     short loc_18000A11A
0x18000a10d  mov     eax, [rcx+0A0h]
0x18000a113  mov     ecx, [rcx+68h]
0x18000a116  imul    rax, rcx
0x18000a11a  mov     [rbp+arg_0], rax
0x18000a11e  jmp     short loc_18000A129
0x18000a120  mov     eax, [rcx+6Ch]
0x18000a123  jmp     short loc_18000A113
0x18000a125  mov     rax, [rbp+arg_0]
0x18000a129  sub     [rdi+38h], rax
0x18000a12d  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a135  jz      short loc_18000A196
0x18000a137  xor     eax, eax
0x18000a139  mov     [rbp+arg_8], rax
0x18000a13d  lock xadd [rbx+38h], eax
0x18000a142  test    eax, eax
0x18000a144  jz      short loc_18000A175
0x18000a146  mov     rcx, [rbx+58h]
0x18000a14a  mov     edx, [rcx+7Ch]
0x18000a14d  test    edx, edx
0x18000a14f  jz      short loc_18000A16F
0x18000a151  cmp     edx, 1
0x18000a154  jz      short loc_18000A15B
0x18000a156  xor     r9d, r9d
0x18000a159  jmp     short loc_18000A169
0x18000a15b  mov     r9d, [rcx+0A0h]
0x18000a162  mov     eax, [rcx+68h]
0x18000a165  imul    r9, rax
0x18000a169  mov     [rbp+arg_8], r9
0x18000a16d  jmp     short loc_18000A179
0x18000a16f  mov     r9d, [rcx+6Ch]
0x18000a173  jmp     short loc_18000A162
0x18000a175  mov     r9, [rbp+arg_8]
0x18000a179  mov     r8, [rbx+48h]
0x18000a17d  lea     rdx, aCtftpreadfilem_3; "CTftpReadFileManager::PurgeModifiedFile"...
0x18000a184  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a18b  mov     ecx, 20000h
0x18000a190  call    cs:__guard_dispatch_icall_fptr
0x18000a196  xor     eax, eax
0x18000a198  mov     [rbp+arg_10], rax
0x18000a19c  lock xadd [rbx+38h], eax
0x18000a1a1  test    eax, eax
0x18000a1a3  jz      short loc_18000A1D1
0x18000a1a5  mov     rcx, [rbx+58h]
0x18000a1a9  mov     edx, [rcx+7Ch]
0x18000a1ac  test    edx, edx
0x18000a1ae  jz      short loc_18000A1CC
0x18000a1b0  cmp     edx, 1
0x18000a1b3  jz      short loc_18000A1B9
0x18000a1b5  xor     eax, eax
0x18000a1b7  jmp     short loc_18000A1C6
0x18000a1b9  mov     eax, [rcx+0A0h]
0x18000a1bf  mov     ecx, [rcx+68h]
0x18000a1c2  imul    rax, rcx
0x18000a1c6  mov     [rbp+arg_10], rax
0x18000a1ca  jmp     short loc_18000A1D5
0x18000a1cc  mov     eax, [rcx+6Ch]
0x18000a1cf  jmp     short loc_18000A1BF
0x18000a1d1  mov     rax, [rbp+arg_10]
0x18000a1d5  mov     edx, 1; unsigned int
0x18000a1da  shr     rax, 0Ah
0x18000a1de  mov     r9d, edx
0x18000a1e1  mov     [rsp+70h+var_50], eax
0x18000a1e5  lea     rcx, qword_1800779F0; this
0x18000a1ec  lea     r8d, [rdx+7]
0x18000a1f0  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000a1f5  jmp     short loc_18000A203
0x18000a1f7  lea     rdx, [rbp+var_30]
0x18000a1fb  mov     rcx, rsi
0x18000a1fe  call    ?MoveNext@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000a203  mov     eax, dword ptr [rbp+var_30]
0x18000a206  test    eax, eax
0x18000a208  jz      loc_18000A09E
0x18000a20e  mov     rcx, rdi; lpCriticalSection
0x18000a211  call    cs:__imp_LeaveCriticalSection
0x18000a218  nop     dword ptr [rax+rax+00h]
0x18000a21d  lea     rdx, [rbp+var_20]
0x18000a221  call    ?DeleteFileReaders@CTftpReadFileManager@@AEAAXAEAV?$CDynArray@PEAVCTftpFileReader@@VCDeallocateNone@@@@@Z; CTftpReadFileManager::DeleteFileReaders(CDynArray<CTftpFileReader *,CDeallocateNone> &)
0x18000a226  mov     rcx, [rbp+var_20]; void *
0x18000a22a  test    rcx, rcx
0x18000a22d  jz      short loc_18000A234
0x18000a22f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a234  mov     rbx, [rsp+70h+arg_18]
0x18000a23c  add     rsp, 70h
0x18000a240  pop     rdi
0x18000a241  pop     rsi
0x18000a242  pop     rbp
0x18000a243  retn
```
