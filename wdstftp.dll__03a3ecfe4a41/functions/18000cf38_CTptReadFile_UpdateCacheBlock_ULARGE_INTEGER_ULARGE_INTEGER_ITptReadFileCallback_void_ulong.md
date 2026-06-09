# CTptReadFile::UpdateCacheBlock(_ULARGE_INTEGER,_ULARGE_INTEGER,ITptReadFileCallback *,void *,ulong *)

- ea: `0x18000cf38`
- end: `0x18000d2b5`
- name: `?UpdateCacheBlock@CTptReadFile@@AEAAKT_ULARGE_INTEGER@@0PEAVITptReadFileCallback@@PEAXPEAK@Z`
- size: `893`
- prototype: `__int64 __fastcall(CTptReadFile *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER, struct ITptReadFileCallback *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000d2bc`

## callees

- `0x18000a960`
- `0x18000cad4`
- `0x18000cb68`
- `0x18000ccc4`
- `0x18000cf38`
- `0x18000d570`
- `0x18000e674`
- `0x18003aa68`
- `0x18003ab60`
- `0x18003c514`
- `0x18003ce78`
- `0x1800607e0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000cf5f`
- `KERNEL32!EnterCriticalSection` at `0x18000cf5f`
- `KERNEL32!LeaveCriticalSection` at `0x18000d11c`
- `KERNEL32!LeaveCriticalSection` at `0x18000d11c`
- `KERNEL32!GetLastError` at `0x18000d038`
- `KERNEL32!GetLastError` at `0x18000d23c`
- `KERNEL32!GetLastError` at `0x18000d038`
- `KERNEL32!GetLastError` at `0x18000d23c`
- `KERNEL32!ReadFile` at `0x18000d028`
- `KERNEL32!ReadFile` at `0x18000d028`
- `KERNEL32!SetEvent` at `0x18000d073`
- `KERNEL32!SetEvent` at `0x18000d29c`
- `KERNEL32!SetEvent` at `0x18000d073`
- `KERNEL32!SetEvent` at `0x18000d29c`
- `WDSSRV!WdsPacketAllocate` at `0x18000d20b`
- `WDSSRV!WdsPacketAllocate` at `0x18000d20b`
- `WDSSRV!WdsPacketFree` at `0x18000d105`
- `WDSSRV!WdsPacketFree` at `0x18000d105`

## string_xrefs

- `0x18000cfc6`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000d14e`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000d0cf`: `m_bIOCompleted`
- `0x18000d0e0`: `base\eco\wds\transport\lib\tptreadfile.h`

## pseudocode

```c
__int64 __fastcall CTptReadFile::UpdateCacheBlock(
        CTptReadFile *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3,
        struct ITptReadFileCallback *a4,
        void *a5,
        unsigned int *a6)
{
  struct CTptReadFile::CacheBlock *CacheBlock; // rax
  void *v11; // r8
  struct CTptReadFile::CacheBlock *v12; // r14
  DWORD v13; // ebx
  struct CTptReadFile::CacheBlock *lpOverlapped; // rsi
  const char *v15; // rdx
  const char *v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r8
  void *v19; // rdx
  const char *v20; // rdx
  __int64 v21; // r8
  unsigned int v23; // eax
  const char *v24; // rdx
  struct CTptReadFile::CacheBlock *v25; // rax
  DWORD v26; // eax
  __int64 v27; // rcx
  LPCRITICAL_SECTION v28; // rax
  __int64 v29; // rax
  const char *v30; // rdx
  DWORD LastError; // eax
  const char *v32; // rdx
  DWORD HighPart; // [rsp+6Ch] [rbp+14h]

  HighPart = a2.HighPart;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  CacheBlock = CTptReadFile::FindCacheBlock((LPCRITICAL_SECTION)this, a2);
  v12 = CacheBlock;
  if ( CacheBlock )
  {
    if ( !*((_DWORD *)CacheBlock + 18) )
    {
      v23 = CTptReadFile::CacheBlock::AddCallback(CacheBlock, a4, v11);
      v13 = ElValidateWin32(v23, v24, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x3B2u);
      goto LABEL_26;
    }
    if ( !*((_DWORD *)CacheBlock + 19) )
    {
      v13 = 183;
      *a6 = *((_DWORD *)CacheBlock + 20);
      goto LABEL_26;
    }
    *((_DWORD *)CacheBlock + 13) = 0;
    lpOverlapped = CacheBlock;
    *((_QWORD *)CacheBlock + 9) = 0;
    *((_DWORD *)CacheBlock + 20) = 0;
LABEL_6:
    v13 = CTptReadFile::CacheBlock::AddCallback(lpOverlapped, a4, v11);
    if ( !ElValidateWin32(v13, v15, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x3E3u) )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 42);
      v13 = 0;
      if ( !ElValidateWin32(0, v16, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x3E6u) )
      {
        v18 = *((unsigned int *)lpOverlapped + 12);
        v19 = (void *)*((_QWORD *)lpOverlapped + 7);
        if ( *((_DWORD *)this + 10) )
        {
          if ( !(unsigned int)WIMReadFileEx(*((_QWORD *)this + 9), v19, v18, lpOverlapped) )
          {
            LastError = GetLastError();
            v13 = ElValidateWin32(LastError, v32, "base\\eco\\wds\\wdslib\\wim\\wdswimfile.cpp", 0x245u);
          }
          if ( ElValidateWin32(v13, v30, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x404u) )
          {
            CMRSWLock::ReaderLock((LPCRITICAL_SECTION)((char *)this + 184));
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 42, 0xFFFFFFFF) == 1 )
              SetEvent(*((HANDLE *)this + 22));
            CMRSWLock::ReaderRelease((CTptReadFile *)((char *)this + 184));
            goto LABEL_18;
          }
        }
        else
        {
          if ( !ReadFile(*((HANDLE *)this + 7), v19, v18, (LPDWORD)lpOverlapped + 13, (LPOVERLAPPED)lpOverlapped) )
          {
            v13 = GetLastError();
            if ( v13 != 997 )
            {
              CMRSWLock::ReaderLock((LPCRITICAL_SECTION)((char *)this + 184));
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 42, 0xFFFFFFFF) == 1 )
                SetEvent(*((HANDLE *)this + 22));
              CMRSWLock::ReaderRelease((CTptReadFile *)((char *)this + 184));
              if ( ElValidateWin32(v13, v20, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x3F7u) )
                goto LABEL_18;
            }
          }
          v13 = 0;
        }
        if ( lpOverlapped != v12 )
          CTptReadFile::AddCacheBlock(this, lpOverlapped);
        lpOverlapped = 0;
        v12 = 0;
      }
    }
LABEL_18:
    if ( v12 )
      CTptReadFile::RemoveCacheBlock(this, v12);
    goto LABEL_20;
  }
  v25 = (struct CTptReadFile::CacheBlock *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  lpOverlapped = v25;
  if ( v25 )
  {
    *((_QWORD *)v25 + 12) = 0;
    *((_QWORD *)v25 + 13) = 0;
    memset_0(v25, 0, 0x20u);
    *((_QWORD *)lpOverlapped + 4) = 0;
    *((_QWORD *)lpOverlapped + 5) = 0;
    *((_QWORD *)lpOverlapped + 6) = 0;
    *((_QWORD *)lpOverlapped + 7) = 0;
    *((_QWORD *)lpOverlapped + 8) = 0;
    *((_QWORD *)lpOverlapped + 9) = 0;
    *((_DWORD *)lpOverlapped + 20) = 0;
    *((_QWORD *)lpOverlapped + 11) = 0;
  }
  else
  {
    lpOverlapped = 0;
  }
  if ( !lpOverlapped )
  {
    v13 = 8;
    goto LABEL_26;
  }
  v26 = a3.LowPart - a2.LowPart + 1;
  *((_DWORD *)lpOverlapped + 12) = v26;
  LODWORD(v27) = v26;
  if ( v26 > *((_DWORD *)this + 26) )
  {
    v27 = *((unsigned int *)this + 26);
    *((_DWORD *)lpOverlapped + 12) = v27;
    a3.QuadPart = v27 + a2.QuadPart - 1;
  }
  *((_DWORD *)lpOverlapped + 5) = HighPart;
  v28 = lpCriticalSection;
  *((union _ULARGE_INTEGER *)lpOverlapped + 4) = a2;
  *((union _ULARGE_INTEGER *)lpOverlapped + 5) = a3;
  *((_QWORD *)lpOverlapped + 8) = this;
  *((_DWORD *)lpOverlapped + 4) = a2.LowPart;
  v29 = WdsPacketAllocate(*(_QWORD *)&v28[4].LockCount, 0, (unsigned int)v27);
  *((_QWORD *)lpOverlapped + 7) = v29;
  if ( v29 )
    goto LABEL_6;
  v13 = 8;
LABEL_20:
  if ( lpOverlapped )
  {
    if ( !*((_DWORD *)lpOverlapped + 18) )
      WdsAssert("base\\eco\\wds\\transport\\lib\\tptreadfile.h", 0xD1u, "m_bIOCompleted", v17, 0);
    v21 = *((_QWORD *)lpOverlapped + 7);
    if ( v21 )
      WdsPacketFree(*(_QWORD *)&lpCriticalSection[4].LockCount, 0, v21, v17);
    operator delete(lpOverlapped);
  }
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return v13;
}

```

## disassembly

```asm
0x18000cf38  mov     [rsp+arg_10], rbx
0x18000cf3d  mov     [rsp+arg_18], rbp
0x18000cf42  mov     [rsp+arg_8], rdx
0x18000cf47  push    rsi
0x18000cf48  push    rdi
0x18000cf49  push    r12
0x18000cf4b  push    r14
0x18000cf4d  push    r15
0x18000cf4f  sub     rsp, 30h
0x18000cf53  mov     r15, r9
0x18000cf56  mov     rdi, r8
0x18000cf59  mov     rbx, rdx
0x18000cf5c  mov     rbp, rcx
0x18000cf5f  call    cs:__imp_EnterCriticalSection
0x18000cf66  nop     dword ptr [rax+rax+00h]
0x18000cf6b  mov     rdx, rbx; union _ULARGE_INTEGER
0x18000cf6e  mov     rcx, rbp; lpCriticalSection
0x18000cf71  call    ?FindCacheBlock@CTptReadFile@@AEAAPEAUCacheBlock@1@T_ULARGE_INTEGER@@@Z; CTptReadFile::FindCacheBlock(_ULARGE_INTEGER)
0x18000cf76  xor     r12d, r12d
0x18000cf79  mov     r14, rax
0x18000cf7c  test    rax, rax
0x18000cf7f  jz      loc_18000D164
0x18000cf85  cmp     [rax+48h], r12d
0x18000cf89  jz      loc_18000D141
0x18000cf8f  cmp     [rax+4Ch], r12d
0x18000cf93  jnz     short loc_18000CFAC
0x18000cf95  mov     ecx, [rax+50h]
0x18000cf98  mov     ebx, 0B7h
0x18000cf9d  mov     rax, [rsp+58h+arg_28]
0x18000cfa5  mov     [rax], ecx
0x18000cfa7  jmp     loc_18000D119
0x18000cfac  mov     [rax+34h], r12d
0x18000cfb0  mov     rsi, r14
0x18000cfb3  mov     [rax+48h], r12
0x18000cfb7  mov     [rax+50h], r12d
0x18000cfbb  mov     rdx, r15; struct ITptReadFileCallback *
0x18000cfbe  mov     rcx, rsi; this
0x18000cfc1  call    ?AddCallback@CacheBlock@CTptReadFile@@QEAAKPEAVITptReadFileCallback@@PEAX@Z; CTptReadFile::CacheBlock::AddCallback(ITptReadFileCallback *,void *)
0x18000cfc6  lea     rdi, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000cfcd  mov     r9d, 3E3h; unsigned int
0x18000cfd3  mov     r8, rdi; char *
0x18000cfd6  mov     ecx, eax; unsigned int
0x18000cfd8  mov     ebx, eax
0x18000cfda  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cfdf  test    eax, eax
0x18000cfe1  jnz     loc_18000D0B4
0x18000cfe7  lock inc dword ptr [rbp+0A8h]
0x18000cfee  mov     r9d, 3E6h; unsigned int
0x18000cff4  mov     r8, rdi; char *
0x18000cff7  xor     ecx, ecx; unsigned int
0x18000cff9  mov     ebx, r12d
0x18000cffc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d001  test    eax, eax
0x18000d003  jnz     loc_18000D0B4
0x18000d009  mov     r8d, [rsi+30h]; nNumberOfBytesToRead
0x18000d00d  mov     rdx, [rsi+38h]; lpBuffer
0x18000d011  cmp     [rbp+28h], r12d
0x18000d015  jnz     loc_18000D22C
0x18000d01b  mov     rcx, [rbp+38h]; hFile
0x18000d01f  lea     r9, [rsi+34h]; lpNumberOfBytesRead
0x18000d023  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x18000d028  call    cs:__imp_ReadFile
0x18000d02f  nop     dword ptr [rax+rax+00h]
0x18000d034  test    eax, eax
0x18000d036  jnz     short loc_18000D09B
0x18000d038  call    cs:__imp_GetLastError
0x18000d03f  nop     dword ptr [rax+rax+00h]
0x18000d044  mov     ebx, eax
0x18000d046  cmp     eax, 3E5h
0x18000d04b  jz      short loc_18000D09B
0x18000d04d  lea     r15, [rbp+0B8h]
0x18000d054  mov     rcx, r15; lpCriticalSection
0x18000d057  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000d05c  or      eax, 0FFFFFFFFh
0x18000d05f  lock xadd [rbp+0A8h], eax
0x18000d067  cmp     eax, 1
0x18000d06a  jnz     short loc_18000D07F
0x18000d06c  mov     rcx, [rbp+0B0h]; hEvent
0x18000d073  call    cs:__imp_SetEvent
0x18000d07a  nop     dword ptr [rax+rax+00h]
0x18000d07f  mov     rcx, r15; this
0x18000d082  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000d087  mov     r9d, 3F7h; unsigned int
0x18000d08d  mov     r8, rdi; char *
0x18000d090  mov     ecx, ebx; unsigned int
0x18000d092  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d097  test    eax, eax
0x18000d099  jnz     short loc_18000D0B4
0x18000d09b  mov     ebx, r12d
0x18000d09e  cmp     rsi, r14
0x18000d0a1  jz      short loc_18000D0AE
0x18000d0a3  mov     rdx, rsi; struct CTptReadFile::CacheBlock *
0x18000d0a6  mov     rcx, rbp; this
0x18000d0a9  call    ?AddCacheBlock@CTptReadFile@@AEAAXPEAUCacheBlock@1@@Z; CTptReadFile::AddCacheBlock(CTptReadFile::CacheBlock *)
0x18000d0ae  mov     rsi, r12
0x18000d0b1  mov     r14, r12
0x18000d0b4  test    r14, r14
0x18000d0b7  jz      short loc_18000D0C4
0x18000d0b9  mov     rdx, r14; struct CTptReadFile::CacheBlock *
0x18000d0bc  mov     rcx, rbp; this
0x18000d0bf  call    ?RemoveCacheBlock@CTptReadFile@@AEAAXPEAUCacheBlock@1@@Z; CTptReadFile::RemoveCacheBlock(CTptReadFile::CacheBlock *)
0x18000d0c4  test    rsi, rsi
0x18000d0c7  jz      short loc_18000D119
0x18000d0c9  cmp     [rsi+48h], r12d
0x18000d0cd  jnz     short loc_18000D0EC
0x18000d0cf  lea     r8, aMBiocompleted; "m_bIOCompleted"
0x18000d0d6  mov     dword ptr [rsp+58h+lpOverlapped], r12d; int
0x18000d0db  mov     edx, 0D1h; unsigned int
0x18000d0e0  lea     rcx, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000d0e7  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000d0ec  mov     r8, [rsi+38h]
0x18000d0f0  test    r8, r8
0x18000d0f3  jz      short loc_18000D111
0x18000d0f5  mov     rcx, cs:lpCriticalSection
0x18000d0fc  xor     edx, edx
0x18000d0fe  mov     rcx, [rcx+0A8h]
0x18000d105  call    cs:__imp_WdsPacketFree
0x18000d10c  nop     dword ptr [rax+rax+00h]
0x18000d111  mov     rcx, rsi; void *
0x18000d114  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d119  mov     rcx, rbp; lpCriticalSection
0x18000d11c  call    cs:__imp_LeaveCriticalSection
0x18000d123  nop     dword ptr [rax+rax+00h]
0x18000d128  mov     rbp, [rsp+58h+arg_18]
0x18000d12d  mov     eax, ebx
0x18000d12f  mov     rbx, [rsp+58h+arg_10]
0x18000d134  add     rsp, 30h
0x18000d138  pop     r15
0x18000d13a  pop     r14
0x18000d13c  pop     r12
0x18000d13e  pop     rdi
0x18000d13f  pop     rsi
0x18000d140  retn
0x18000d141  mov     rdx, r15; struct ITptReadFileCallback *
0x18000d144  mov     rcx, r14; this
0x18000d147  call    ?AddCallback@CacheBlock@CTptReadFile@@QEAAKPEAVITptReadFileCallback@@PEAX@Z; CTptReadFile::CacheBlock::AddCallback(ITptReadFileCallback *,void *)
0x18000d14c  mov     ecx, eax; unsigned int
0x18000d14e  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000d155  mov     r9d, 3B2h; unsigned int
0x18000d15b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d160  mov     ebx, eax
0x18000d162  jmp     short loc_18000D119
0x18000d164  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d16b  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000d170  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d175  mov     rsi, rax
0x18000d178  test    rax, rax
0x18000d17b  jz      short loc_18000D1B5
0x18000d17d  xor     edx, edx; Val
0x18000d17f  mov     [rax+60h], r12
0x18000d183  mov     rcx, rax; void *
0x18000d186  mov     [rax+68h], r12
0x18000d18a  lea     r8d, [rdx+20h]; Size
0x18000d18e  call    memset_0
0x18000d193  mov     [rsi+20h], r12
0x18000d197  mov     [rsi+28h], r12
0x18000d19b  mov     [rsi+30h], r12
0x18000d19f  mov     [rsi+38h], r12
0x18000d1a3  mov     [rsi+40h], r12
0x18000d1a7  mov     [rsi+48h], r12
0x18000d1ab  mov     [rsi+50h], r12d
0x18000d1af  mov     [rsi+58h], r12
0x18000d1b3  jmp     short loc_18000D1B8
0x18000d1b5  mov     rsi, r12
0x18000d1b8  test    rsi, rsi
0x18000d1bb  jnz     short loc_18000D1C5
0x18000d1bd  lea     ebx, [rsi+8]
0x18000d1c0  jmp     loc_18000D119
0x18000d1c5  mov     eax, edi
0x18000d1c7  sub     eax, ebx
0x18000d1c9  inc     eax
0x18000d1cb  mov     [rsi+30h], eax
0x18000d1ce  mov     ecx, eax
0x18000d1d0  cmp     eax, [rbp+68h]
0x18000d1d3  jbe     short loc_18000D1E2
0x18000d1d5  mov     ecx, [rbp+68h]
0x18000d1d8  lea     rdi, [rbx-1]
0x18000d1dc  mov     [rsi+30h], ecx
0x18000d1df  add     rdi, rcx
0x18000d1e2  mov     eax, dword ptr [rsp+58h+arg_8+4]
0x18000d1e6  mov     r8d, ecx
0x18000d1e9  mov     [rsi+14h], eax
0x18000d1ec  xor     edx, edx
0x18000d1ee  mov     rax, cs:lpCriticalSection
0x18000d1f5  mov     [rsi+20h], rbx
0x18000d1f9  mov     [rsi+28h], rdi
0x18000d1fd  mov     [rsi+40h], rbp
0x18000d201  mov     [rsi+10h], ebx
0x18000d204  mov     rcx, [rax+0A8h]
0x18000d20b  call    cs:__imp_WdsPacketAllocate
0x18000d212  nop     dword ptr [rax+rax+00h]
0x18000d217  mov     [rsi+38h], rax
0x18000d21b  test    rax, rax
0x18000d21e  jnz     loc_18000CFBB
0x18000d224  lea     ebx, [rax+8]
0x18000d227  jmp     loc_18000D0C4
0x18000d22c  mov     rcx, [rbp+48h]
0x18000d230  mov     r9, rsi
0x18000d233  call    WIMReadFileEx
0x18000d238  test    eax, eax
0x18000d23a  jnz     short loc_18000D25E
0x18000d23c  call    cs:__imp_GetLastError
0x18000d243  nop     dword ptr [rax+rax+00h]
0x18000d248  mov     r9d, 245h; unsigned int
0x18000d24e  lea     r8, aBaseEcoWdsWdsl_0; "base\\eco\\wds\\wdslib\\wim\\wdswimfile"...
0x18000d255  mov     ecx, eax; unsigned int
0x18000d257  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d25c  mov     ebx, eax
0x18000d25e  mov     r9d, 404h; unsigned int
0x18000d264  mov     r8, rdi; char *
0x18000d267  mov     ecx, ebx; unsigned int
0x18000d269  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d26e  test    eax, eax
0x18000d270  jz      loc_18000D09E
0x18000d276  lea     rdi, [rbp+0B8h]
0x18000d27d  mov     rcx, rdi; lpCriticalSection
0x18000d280  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000d285  or      eax, 0FFFFFFFFh
0x18000d288  lock xadd [rbp+0A8h], eax
0x18000d290  cmp     eax, 1
0x18000d293  jnz     short loc_18000D2A8
0x18000d295  mov     rcx, [rbp+0B0h]; hEvent
0x18000d29c  call    cs:__imp_SetEvent
0x18000d2a3  nop     dword ptr [rax+rax+00h]
0x18000d2a8  mov     rcx, rdi; this
0x18000d2ab  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000d2b0  jmp     loc_18000D0B4
```
