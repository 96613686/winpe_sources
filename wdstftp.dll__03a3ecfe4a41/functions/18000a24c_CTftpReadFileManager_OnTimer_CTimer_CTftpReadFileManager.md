# CTftpReadFileManager::OnTimer(CTimer<CTftpReadFileManager> *)

- ea: `0x18000a24c`
- end: `0x18000a4b2`
- name: `?OnTimer@CTftpReadFileManager@@QEAAXPEAV?$CTimer@VCTftpReadFileManager@@@@@Z`
- size: `614`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000a760`

## callees

- `0x180005850`
- `0x180009614`
- `0x18000a24c`
- `0x18000a68c`
- `0x18000a800`
- `0x18000a960`
- `0x18003c084`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a26c`
- `KERNEL32!EnterCriticalSection` at `0x18000a26c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a486`
- `KERNEL32!LeaveCriticalSection` at `0x18000a486`

## string_xrefs

- `0x18000a382`: `CTftpReadFileManager::OnTimer: [Timeout/Delete] CTftpFileReader instance for file: %s (Cache size = %I64u).`
- `0x18000a458`: `CTftpReadFileManager::OnTimer: [Timeout/Mark to Delete] CTftpFileReader instance for file: %s (Cache size = %I64u).`

## pseudocode

```c
void __fastcall CTftpReadFileManager::OnTimer(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // eax
  __int64 v3; // rdx
  int v4; // eax
  __int64 v5; // rbx
  LPCRITICAL_SECTION v6; // rcx
  unsigned int *v7; // rcx
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int *v11; // rcx
  unsigned int v12; // edx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-58h]
  __int128 v17; // [rsp+30h] [rbp-48h] BYREF
  __int128 v18; // [rsp+40h] [rbp-38h] BYREF
  void *v19; // [rsp+50h] [rbp-28h] BYREF
  int v20; // [rsp+58h] [rbp-20h]
  int v21; // [rsp+5Ch] [rbp-1Ch]

  v19 = 0;
  v20 = 0;
  v21 = 0;
  EnterCriticalSection(lpCriticalSection);
  v2 = 0;
  v3 = *(_QWORD *)&lpCriticalSection[3].LockCount;
  *(_QWORD *)&v18 = 0;
  if ( v3 )
  {
    *((_QWORD *)&v18 + 1) = v3;
  }
  else
  {
    *((_QWORD *)&v18 + 1) = 0;
    CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(&lpCriticalSection[3], &v18);
    v2 = v18;
  }
  v17 = v18;
  if ( !v2 )
  {
    v4 = v17;
    do
    {
      v5 = 0;
      if ( !v4 )
        v5 = *((_QWORD *)&v17 + 1);
      v6 = lpCriticalSection + 3;
      if ( *(_DWORD *)(v5 + 48) )
      {
        CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(v6, &v17);
        goto LABEL_32;
      }
      if ( !*(_DWORD *)(v5 + 52) )
      {
        *(_DWORD *)(v5 + 52) = 1;
        CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(v6, &v17);
        if ( g_ErrLibTraceFunctionEx )
        {
          _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0);
          g_ErrLibTraceFunctionEx(
            0x20000u,
            L"CTftpReadFileManager::OnTimer: [Timeout/Mark to Delete] CTftpFileReader instance for file: %s (Cache size = %I64u).",
            *(_QWORD *)(v5 + 72));
        }
        goto LABEL_32;
      }
      CSmHashTable<CTftpFileReader,CNoLock,113>::EnumRemoveAt(v6, &v17);
      CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v19);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0) )
      {
        v7 = *(unsigned int **)(v5 + 88);
        v8 = v7[31];
        if ( v8 )
        {
          if ( v8 != 1 )
          {
            v9 = 0;
            goto LABEL_18;
          }
          v10 = v7[40];
        }
        else
        {
          v10 = v7[27];
        }
        v9 = v7[26] * v10;
      }
      else
      {
        v9 = 0;
      }
LABEL_18:
      lpCriticalSection[1].OwningThread = (char *)lpCriticalSection[1].OwningThread - v9;
      if ( g_ErrLibTraceFunctionEx )
      {
        _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0);
        g_ErrLibTraceFunctionEx(
          0x20000u,
          L"CTftpReadFileManager::OnTimer: [Timeout/Delete] CTftpFileReader instance for file: %s (Cache size = %I64u).",
          *(_QWORD *)(v5 + 72));
      }
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0) )
      {
        v13 = 0;
        goto LABEL_28;
      }
      v11 = *(unsigned int **)(v5 + 88);
      v12 = v11[31];
      if ( !v12 )
      {
        v14 = v11[27];
        goto LABEL_25;
      }
      if ( v12 == 1 )
      {
        v14 = v11[40];
LABEL_25:
        v13 = v11[26] * v14;
        goto LABEL_28;
      }
      v13 = 0;
LABEL_28:
      LODWORD(v16) = v13 >> 10;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 8, 1, v16);
LABEL_32:
      v4 = v17;
    }
    while ( !(_DWORD)v17 );
  }
  LeaveCriticalSection(lpCriticalSection);
  CTftpReadFileManager::DeleteFileReaders(v15, (__int64 **)&v19);
  if ( v19 )
    operator delete(v19);
}

```

## disassembly

```asm
0x18000a24c  mov     [rsp-20h+arg_8], rdx
0x18000a251  push    rbp
0x18000a252  push    rbx
0x18000a253  push    rsi
0x18000a254  push    rdi
0x18000a255  mov     rbp, rsp
0x18000a258  sub     rsp, 78h
0x18000a25c  and     [rbp+var_28], 0
0x18000a261  mov     rdi, rcx
0x18000a264  and     [rbp+var_20], 0
0x18000a268  and     [rbp+var_1C], 0
0x18000a26c  call    cs:__imp_EnterCriticalSection
0x18000a273  nop     dword ptr [rax+rax+00h]
0x18000a278  xor     eax, eax
0x18000a27a  lea     rsi, [rdi+78h]
0x18000a27e  mov     rdx, [rsi+8]
0x18000a282  mov     qword ptr [rbp+var_38], rax
0x18000a286  test    rdx, rdx
0x18000a289  jnz     short loc_18000A2A1
0x18000a28b  and     qword ptr [rbp+var_38+8], rax
0x18000a28f  lea     rdx, [rbp+var_38]
0x18000a293  mov     rcx, rsi
0x18000a296  call    ?MoveNext@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000a29b  mov     rax, qword ptr [rbp+var_38]
0x18000a29f  jmp     short loc_18000A2A5
0x18000a2a1  mov     qword ptr [rbp+var_38+8], rdx
0x18000a2a5  movaps  xmm0, [rbp+var_38]
0x18000a2a9  movdqa  [rbp+var_48], xmm0
0x18000a2ae  test    eax, eax
0x18000a2b0  jnz     loc_18000A483
0x18000a2b6  mov     eax, dword ptr [rbp+var_48]
0x18000a2b9  xor     ebx, ebx
0x18000a2bb  test    eax, eax
0x18000a2bd  jnz     short loc_18000A2C3
0x18000a2bf  mov     rbx, qword ptr [rbp+var_48+8]
0x18000a2c3  cmp     dword ptr [rbx+30h], 0
0x18000a2c7  lea     rdx, [rbp+var_48]
0x18000a2cb  mov     rcx, rsi
0x18000a2ce  jnz     loc_18000A473
0x18000a2d4  cmp     dword ptr [rbx+34h], 0
0x18000a2d8  jz      loc_18000A3FC
0x18000a2de  call    ?EnumRemoveAt@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@QEAAPEAVCTftpFileReader@@AEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)
0x18000a2e3  mov     rdx, rbx
0x18000a2e6  lea     rcx, [rbp+var_28]
0x18000a2ea  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x18000a2ef  xor     eax, eax
0x18000a2f1  mov     [rbp+arg_8], rax
0x18000a2f5  lock xadd [rbx+38h], eax
0x18000a2fa  test    eax, eax
0x18000a2fc  jz      short loc_18000A32A
0x18000a2fe  mov     rcx, [rbx+58h]
0x18000a302  mov     edx, [rcx+7Ch]
0x18000a305  test    edx, edx
0x18000a307  jz      short loc_18000A325
0x18000a309  cmp     edx, 1
0x18000a30c  jz      short loc_18000A312
0x18000a30e  xor     eax, eax
0x18000a310  jmp     short loc_18000A31F
0x18000a312  mov     eax, [rcx+0A0h]
0x18000a318  mov     ecx, [rcx+68h]
0x18000a31b  imul    rax, rcx
0x18000a31f  mov     [rbp+arg_8], rax
0x18000a323  jmp     short loc_18000A32E
0x18000a325  mov     eax, [rcx+6Ch]
0x18000a328  jmp     short loc_18000A318
0x18000a32a  mov     rax, [rbp+arg_8]
0x18000a32e  sub     [rdi+38h], rax
0x18000a332  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a33a  jz      short loc_18000A39B
0x18000a33c  xor     eax, eax
0x18000a33e  mov     [rbp+arg_0], rax
0x18000a342  lock xadd [rbx+38h], eax
0x18000a347  test    eax, eax
0x18000a349  jz      short loc_18000A37A
0x18000a34b  mov     rcx, [rbx+58h]
0x18000a34f  mov     edx, [rcx+7Ch]
0x18000a352  test    edx, edx
0x18000a354  jz      short loc_18000A374
0x18000a356  cmp     edx, 1
0x18000a359  jz      short loc_18000A360
0x18000a35b  xor     r9d, r9d
0x18000a35e  jmp     short loc_18000A36E
0x18000a360  mov     r9d, [rcx+0A0h]
0x18000a367  mov     eax, [rcx+68h]
0x18000a36a  imul    r9, rax
0x18000a36e  mov     [rbp+arg_0], r9
0x18000a372  jmp     short loc_18000A37E
0x18000a374  mov     r9d, [rcx+6Ch]
0x18000a378  jmp     short loc_18000A367
0x18000a37a  mov     r9, [rbp+arg_0]
0x18000a37e  mov     r8, [rbx+48h]
0x18000a382  lea     rdx, aCtftpreadfilem_1; "CTftpReadFileManager::OnTimer: [Timeout"...
0x18000a389  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a390  mov     ecx, 20000h
0x18000a395  call    cs:__guard_dispatch_icall_fptr
0x18000a39b  xor     eax, eax
0x18000a39d  mov     [rbp+arg_10], rax
0x18000a3a1  lock xadd [rbx+38h], eax
0x18000a3a6  test    eax, eax
0x18000a3a8  jz      short loc_18000A3D6
0x18000a3aa  mov     rcx, [rbx+58h]
0x18000a3ae  mov     edx, [rcx+7Ch]
0x18000a3b1  test    edx, edx
0x18000a3b3  jz      short loc_18000A3D1
0x18000a3b5  cmp     edx, 1
0x18000a3b8  jz      short loc_18000A3BE
0x18000a3ba  xor     eax, eax
0x18000a3bc  jmp     short loc_18000A3CB
0x18000a3be  mov     eax, [rcx+0A0h]
0x18000a3c4  mov     ecx, [rcx+68h]
0x18000a3c7  imul    rax, rcx
0x18000a3cb  mov     [rbp+arg_10], rax
0x18000a3cf  jmp     short loc_18000A3DA
0x18000a3d1  mov     eax, [rcx+6Ch]
0x18000a3d4  jmp     short loc_18000A3C4
0x18000a3d6  mov     rax, [rbp+arg_10]
0x18000a3da  mov     edx, 1; unsigned int
0x18000a3df  shr     rax, 0Ah
0x18000a3e3  mov     r9d, edx
0x18000a3e6  mov     [rsp+78h+var_58], eax
0x18000a3ea  lea     rcx, qword_1800779F0; this
0x18000a3f1  lea     r8d, [rdx+7]
0x18000a3f5  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000a3fa  jmp     short loc_18000A478
0x18000a3fc  mov     dword ptr [rbx+34h], 1
0x18000a403  call    ?MoveNext@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000a408  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a410  jz      short loc_18000A478
0x18000a412  xor     eax, eax
0x18000a414  mov     [rbp+arg_18], rax
0x18000a418  lock xadd [rbx+38h], eax
0x18000a41d  test    eax, eax
0x18000a41f  jz      short loc_18000A450
0x18000a421  mov     rcx, [rbx+58h]
0x18000a425  mov     edx, [rcx+7Ch]
0x18000a428  test    edx, edx
0x18000a42a  jz      short loc_18000A44A
0x18000a42c  cmp     edx, 1
0x18000a42f  jz      short loc_18000A436
0x18000a431  xor     r9d, r9d
0x18000a434  jmp     short loc_18000A444
0x18000a436  mov     r9d, [rcx+0A0h]
0x18000a43d  mov     eax, [rcx+68h]
0x18000a440  imul    r9, rax
0x18000a444  mov     [rbp+arg_18], r9
0x18000a448  jmp     short loc_18000A454
0x18000a44a  mov     r9d, [rcx+6Ch]
0x18000a44e  jmp     short loc_18000A43D
0x18000a450  mov     r9, [rbp+arg_18]
0x18000a454  mov     r8, [rbx+48h]
0x18000a458  lea     rdx, aCtftpreadfilem_0; "CTftpReadFileManager::OnTimer: [Timeout"...
0x18000a45f  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000a466  mov     ecx, 20000h
0x18000a46b  call    cs:__guard_dispatch_icall_fptr
0x18000a471  jmp     short loc_18000A478
0x18000a473  call    ?MoveNext@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000a478  mov     eax, dword ptr [rbp+var_48]
0x18000a47b  test    eax, eax
0x18000a47d  jz      loc_18000A2B9
0x18000a483  mov     rcx, rdi; lpCriticalSection
0x18000a486  call    cs:__imp_LeaveCriticalSection
0x18000a48d  nop     dword ptr [rax+rax+00h]
0x18000a492  lea     rdx, [rbp+var_28]
0x18000a496  call    ?DeleteFileReaders@CTftpReadFileManager@@AEAAXAEAV?$CDynArray@PEAVCTftpFileReader@@VCDeallocateNone@@@@@Z; CTftpReadFileManager::DeleteFileReaders(CDynArray<CTftpFileReader *,CDeallocateNone> &)
0x18000a49b  mov     rcx, [rbp+var_28]; void *
0x18000a49f  test    rcx, rcx
0x18000a4a2  jz      short loc_18000A4A9
0x18000a4a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a4a9  add     rsp, 78h
0x18000a4ad  pop     rdi
0x18000a4ae  pop     rsi
0x18000a4af  pop     rbx
0x18000a4b0  pop     rbp
0x18000a4b1  retn
```
