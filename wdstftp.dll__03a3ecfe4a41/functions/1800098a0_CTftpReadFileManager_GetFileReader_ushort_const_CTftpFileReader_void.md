# CTftpReadFileManager::GetFileReader(ushort const *,CTftpFileReader * *,void * *)

- ea: `0x1800098a0`
- end: `0x180009d18`
- name: `?GetFileReader@CTftpReadFileManager@@QEAAKPEBGPEAPEAVCTftpFileReader@@PEAPEAX@Z`
- size: `1144`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, struct CTftpFileReader **, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x180006590`

## callees

- `0x180005850`
- `0x180008a2c`
- `0x180008a8c`
- `0x180008b1c`
- `0x180008d80`
- `0x180009614`
- `0x1800096b0`
- `0x1800098a0`
- `0x18000a590`
- `0x18000a960`
- `0x18000c49c`
- `0x18003c084`
- `0x18003c63c`
- `0x18003ce78`
- `0x1800607e0`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800098d5`
- `KERNEL32!EnterCriticalSection` at `0x1800098d5`
- `KERNEL32!LeaveCriticalSection` at `0x180009c8f`
- `KERNEL32!LeaveCriticalSection` at `0x180009c8f`
- `KERNEL32!DeleteCriticalSection` at `0x180009cda`
- `KERNEL32!DeleteCriticalSection` at `0x180009cda`

## string_xrefs

- `0x180009acc`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`
- `0x180009b1a`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`
- `0x180009b99`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`
- `0x180009bc3`: `base\eco\wds\transport\server\tftp\tftpreadfilemanager.cpp`
- `0x180009b47`: `CTftpReadFileManager::GetFileReader: CTftpFileReader not found for file: %s; creating a new instance.`
- `0x180009971`: `CTftpReadFileManager::GetFileReader: Using existing CTftpFileReader instance for file: %s.`
- `0x180009a67`: `CTftpReadFileManager::GetFileReader: Existing CTftpFileReader instance for file: %s is modified since opening; deleting it.`
- `0x180009af4`: `CTftpReadFileManager::GetFileReader: Created a new CTftpFileReader instance for file: %s.`

## pseudocode

```c
__int64 __fastcall CTftpReadFileManager::GetFileReader(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        struct CTftpFileReader **a3,
        void **a4)
{
  CTftpFileReader *v5; // rbx
  unsigned int StringHash; // r10d
  CTftpFileReader *v9; // rdx
  CTftpFileReader *v10; // rdi
  char *v11; // rax
  char *v12; // r9
  int v13; // r8d
  int v14; // ecx
  unsigned int *v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // r14d
  CTftpFileReader *v20; // rax
  const char *v21; // rdx
  const char *v22; // rdx
  CTftpFileReader *v23; // rax
  const char *v24; // rdx
  const char *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rcx
  void *v29; // rcx
  void *v31[3]; // [rsp+38h] [rbp-18h] BYREF

  v5 = 0;
  v31[0] = 0;
  v31[1] = 0;
  EnterCriticalSection(lpCriticalSection);
  StringHash = WdsGetStringHash(a2);
  v9 = (CTftpFileReader *)*((_QWORD *)&lpCriticalSection[3].LockCount + 3 * (StringHash % 0x71));
  if ( !v9 )
    goto LABEL_33;
  do
  {
    v10 = v9;
    v9 = (CTftpFileReader *)*((_QWORD *)v9 + 15);
    if ( *((_DWORD *)v10 + 34) == StringHash )
    {
      v11 = (char *)*((_QWORD *)v10 + 9);
      v12 = (char *)((char *)a2 - v11);
      do
      {
        v13 = *(unsigned __int16 *)&v12[(_QWORD)v11];
        v14 = *(unsigned __int16 *)v11 - v13;
        if ( v14 )
          break;
        v11 += 2;
      }
      while ( v13 );
      if ( !v14 )
        break;
    }
    v10 = 0;
  }
  while ( v9 );
  if ( !v10 )
  {
LABEL_33:
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"CTftpReadFileManager::GetFileReader: CTftpFileReader not found for file: %s; creating a new instance.",
        a2);
    v23 = (CTftpFileReader *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 )
      v5 = CTftpFileReader::CTftpFileReader(v23);
    if ( !v5 )
    {
      v19 = 8;
      goto LABEL_47;
    }
    v19 = CTftpFileReader::Initialize(v5, a2);
    if ( !ElValidateWin32(v19, v24, "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp", 0x15Bu) )
    {
      v19 = CTftpFileReader::AddFileReference(v5, a4);
      if ( !ElValidateWin32(v19, v25, "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp", 0x161u) )
      {
        CTftpReadFileManager::PurgeDeadFileReaders(lpCriticalSection, v31);
        v10 = v5;
LABEL_42:
        *a3 = v10;
        if ( v5 )
        {
          v26 = WdsGetStringHash(*((const unsigned __int16 **)v5 + 9));
          *((_DWORD *)v5 + 34) = v26;
          v27 = v26 % 0x71;
          if ( *((_QWORD *)&lpCriticalSection[3].LockCount + 3 * v27) )
          {
            *((_QWORD *)v5 + 15) = 0;
            *((_QWORD *)v5 + 16) = *((_QWORD *)&lpCriticalSection[3].OwningThread + 3 * v27);
            *(_QWORD *)(*((_QWORD *)&lpCriticalSection[3].OwningThread + 3 * v27) + 120LL) = v5;
            *((_QWORD *)&lpCriticalSection[3].OwningThread + 3 * v27) = v5;
          }
          else
          {
            *((_QWORD *)&lpCriticalSection[3].OwningThread + 3 * v27) = v5;
            *((_QWORD *)&lpCriticalSection[3].LockCount + 3 * v27) = v5;
            *((_QWORD *)v5 + 15) = 0;
            *((_QWORD *)v5 + 16) = 0;
          }
          ++*((_DWORD *)&lpCriticalSection[3].LockSemaphore + 6 * v27 + 1);
          ++LODWORD(lpCriticalSection[71].DebugInfo);
          v5 = 0;
        }
        goto LABEL_47;
      }
    }
    goto LABEL_47;
  }
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(
      0x10000u,
      L"CTftpReadFileManager::GetFileReader: Using existing CTftpFileReader instance for file: %s.",
      a2);
  if ( *((_DWORD *)v10 + 12) )
  {
LABEL_31:
    v19 = CTftpFileReader::AddFileReference(v10, a4);
    if ( ElValidateWin32(v19, v22, "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp", 0x19Fu) )
      goto LABEL_47;
    goto LABEL_42;
  }
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)v10 + 14, 0) )
  {
    v17 = 0;
    goto LABEL_20;
  }
  v15 = (unsigned int *)*((_QWORD *)v10 + 11);
  v16 = v15[31];
  if ( !v16 )
  {
    v18 = v15[27];
    goto LABEL_17;
  }
  if ( v16 == 1 )
  {
    v18 = v15[40];
LABEL_17:
    v17 = v15[26] * v18;
    goto LABEL_20;
  }
  v17 = 0;
LABEL_20:
  lpCriticalSection[1].OwningThread = (char *)lpCriticalSection[1].OwningThread - v17;
  _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 14, 0);
  v19 = 8;
  CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 8);
  *((_DWORD *)v10 + 13) = 0;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)v10 + 14, 0)
    || !(unsigned int)CTptReadFile::ModifiedSinceOpen(*((LPCRITICAL_SECTION *)v10 + 11)) )
  {
    goto LABEL_31;
  }
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(
      0x10000u,
      L"CTftpReadFileManager::GetFileReader: Existing CTftpFileReader instance for file: %s is modified since opening; deleting it.",
      a2);
  CSmHashTable<CTftpFileReader,CNoLock,113>::RemoveItem(&lpCriticalSection[3], v10);
  CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(v31);
  v20 = (CTftpFileReader *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v20 )
    v5 = CTftpFileReader::CTftpFileReader(v20);
  if ( v5 )
  {
    v19 = CTftpFileReader::Initialize(v5, a2);
    if ( !ElValidateWin32(v19, v21, "base\\eco\\wds\\transport\\server\\tftp\\tftpreadfilemanager.cpp", 0x191u) )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(
          0x10000u,
          L"CTftpReadFileManager::GetFileReader: Created a new CTftpFileReader instance for file: %s.",
          a2);
      v10 = v5;
      goto LABEL_31;
    }
  }
LABEL_47:
  LeaveCriticalSection(lpCriticalSection);
  CTftpReadFileManager::DeleteFileReaders(v28, v31);
  if ( v5 )
  {
    *(_QWORD *)v5 = &CTftpFileReader::`vftable';
    CTftpFileReader::Shutdown(v5);
    v29 = (void *)*((_QWORD *)v5 + 12);
    if ( v29 )
    {
      operator delete(v29);
      *((_QWORD *)v5 + 12) = 0;
      *((_DWORD *)v5 + 27) = 0;
      *((_DWORD *)v5 + 26) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
    operator delete(v5);
  }
  if ( v31[0] )
    operator delete(v31[0]);
  return v19;
}

```

## disassembly

```asm
0x1800098a0  mov     [rsp-28h+arg_8], rbx
0x1800098a5  mov     [rsp-28h+arg_18], rsi
0x1800098aa  mov     [rsp-28h+arg_10], r8
0x1800098af  push    rbp
0x1800098b0  push    rdi
0x1800098b1  push    r12
0x1800098b3  push    r13
0x1800098b5  push    r14
0x1800098b7  mov     rbp, rsp
0x1800098ba  sub     rsp, 50h
0x1800098be  xor     r14d, r14d
0x1800098c1  mov     r13, r9
0x1800098c4  mov     ebx, r14d
0x1800098c7  mov     [rbp+var_18], r14
0x1800098cb  mov     [rbp+var_10], r14
0x1800098cf  mov     r12, rdx
0x1800098d2  mov     rsi, rcx
0x1800098d5  call    cs:__imp_EnterCriticalSection
0x1800098dc  nop     dword ptr [rax+rax+00h]
0x1800098e1  mov     rcx, r12; unsigned __int16 *
0x1800098e4  call    ?WdsGetStringHash@@YAKPEBG@Z; WdsGetStringHash(ushort const *)
0x1800098e9  mov     r10d, eax
0x1800098ec  mov     eax, 21FB7813h
0x1800098f1  mul     r10d
0x1800098f4  mov     ecx, r10d
0x1800098f7  mov     eax, r10d
0x1800098fa  sub     eax, edx
0x1800098fc  shr     eax, 1
0x1800098fe  add     eax, edx
0x180009900  shr     eax, 6
0x180009903  imul    eax, 71h ; 'q'
0x180009906  sub     ecx, eax
0x180009908  lea     rcx, [rcx+rcx*2]
0x18000990c  mov     rdx, [rsi+rcx*8+80h]
0x180009914  test    rdx, rdx
0x180009917  jz      loc_180009B38
0x18000991d  mov     rdi, rdx
0x180009920  mov     rdx, [rdx+78h]
0x180009924  cmp     [rdi+88h], r10d
0x18000992b  jnz     short loc_180009951
0x18000992d  mov     rax, [rdi+48h]
0x180009931  mov     r9, r12
0x180009934  sub     r9, rax
0x180009937  movzx   ecx, word ptr [rax]
0x18000993a  movzx   r8d, word ptr [rax+r9]
0x18000993f  sub     ecx, r8d
0x180009942  jnz     short loc_18000994D
0x180009944  add     rax, 2
0x180009948  test    r8d, r8d
0x18000994b  jnz     short loc_180009937
0x18000994d  test    ecx, ecx
0x18000994f  jz      short loc_180009959
0x180009951  mov     rdi, r14
0x180009954  test    rdx, rdx
0x180009957  jnz     short loc_18000991D
0x180009959  test    rdi, rdi
0x18000995c  jz      loc_180009B38
0x180009962  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009969  test    rax, rax
0x18000996c  jz      short loc_180009983
0x18000996e  mov     r8, r12
0x180009971  lea     rdx, aCtftpreadfilem_7; "CTftpReadFileManager::GetFileReader: Us"...
0x180009978  mov     ecx, 10000h
0x18000997d  call    cs:__guard_dispatch_icall_fptr
0x180009983  cmp     [rdi+30h], r14d
0x180009987  jnz     loc_180009B09
0x18000998d  xor     eax, eax
0x18000998f  mov     [rbp+arg_0], rax
0x180009993  lock xadd [rdi+38h], eax
0x180009998  test    eax, eax
0x18000999a  jz      short loc_1800099C9
0x18000999c  mov     rcx, [rdi+58h]
0x1800099a0  mov     edx, [rcx+7Ch]
0x1800099a3  test    edx, edx
0x1800099a5  jz      short loc_1800099C4
0x1800099a7  cmp     edx, 1
0x1800099aa  jz      short loc_1800099B1
0x1800099ac  mov     rax, r14
0x1800099af  jmp     short loc_1800099BE
0x1800099b1  mov     eax, [rcx+0A0h]
0x1800099b7  mov     ecx, [rcx+68h]
0x1800099ba  imul    rax, rcx
0x1800099be  mov     [rbp+arg_0], rax
0x1800099c2  jmp     short loc_1800099CD
0x1800099c4  mov     eax, [rcx+6Ch]
0x1800099c7  jmp     short loc_1800099B7
0x1800099c9  mov     rax, [rbp+arg_0]
0x1800099cd  sub     [rsi+38h], rax
0x1800099d1  xor     eax, eax
0x1800099d3  mov     [rbp+var_20], rax
0x1800099d7  lock xadd [rdi+38h], eax
0x1800099dc  test    eax, eax
0x1800099de  jz      short loc_180009A0D
0x1800099e0  mov     rcx, [rdi+58h]
0x1800099e4  mov     edx, [rcx+7Ch]
0x1800099e7  test    edx, edx
0x1800099e9  jz      short loc_180009A08
0x1800099eb  cmp     edx, 1
0x1800099ee  jz      short loc_1800099F5
0x1800099f0  mov     rax, r14
0x1800099f3  jmp     short loc_180009A02
0x1800099f5  mov     eax, [rcx+0A0h]
0x1800099fb  mov     ecx, [rcx+68h]
0x1800099fe  imul    rax, rcx
0x180009a02  mov     [rbp+var_20], rax
0x180009a06  jmp     short loc_180009A11
0x180009a08  mov     eax, [rcx+6Ch]
0x180009a0b  jmp     short loc_1800099FB
0x180009a0d  mov     rax, [rbp+var_20]
0x180009a11  mov     r9d, 1
0x180009a17  shr     rax, 0Ah
0x180009a1b  mov     edx, r9d; unsigned int
0x180009a1e  mov     [rsp+50h+var_30], eax
0x180009a22  lea     rcx, qword_1800779F0; this
0x180009a29  lea     r14d, [r9+7]
0x180009a2d  mov     r8d, r14d
0x180009a30  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180009a35  and     [rdi+34h], ebx
0x180009a38  xor     eax, eax
0x180009a3a  lock xadd [rdi+38h], eax
0x180009a3f  test    eax, eax
0x180009a41  jz      loc_180009B09
0x180009a47  mov     rcx, [rdi+58h]; lpCriticalSection
0x180009a4b  call    ?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ; CTptReadFile::ModifiedSinceOpen(void)
0x180009a50  test    eax, eax
0x180009a52  jz      loc_180009B09
0x180009a58  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009a5f  test    rax, rax
0x180009a62  jz      short loc_180009A79
0x180009a64  mov     r8, r12
0x180009a67  lea     rdx, aCtftpreadfilem_2; "CTftpReadFileManager::GetFileReader: Ex"...
0x180009a6e  mov     ecx, 10000h
0x180009a73  call    cs:__guard_dispatch_icall_fptr
0x180009a79  lea     rcx, [rsi+78h]
0x180009a7d  mov     rdx, rdi
0x180009a80  call    ?RemoveItem@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@QEAAPEAVCTftpFileReader@@PEAV2@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::RemoveItem(CTftpFileReader *)
0x180009a85  mov     rdx, rdi
0x180009a88  lea     rcx, [rbp+var_18]
0x180009a8c  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x180009a91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009a98  mov     ecx, 90h; unsigned __int64
0x180009a9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009aa2  test    rax, rax
0x180009aa5  jz      short loc_180009AB2
0x180009aa7  mov     rcx, rax; this
0x180009aaa  call    ??0CTftpFileReader@@QEAA@XZ; CTftpFileReader::CTftpFileReader(void)
0x180009aaf  mov     rbx, rax
0x180009ab2  test    rbx, rbx
0x180009ab5  jz      loc_180009C8C
0x180009abb  mov     rdx, r12; unsigned __int16 *
0x180009abe  mov     rcx, rbx; this
0x180009ac1  call    ?Initialize@CTftpFileReader@@QEAAKPEBG@Z; CTftpFileReader::Initialize(ushort const *)
0x180009ac6  mov     r9d, 191h; unsigned int
0x180009acc  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009ad3  mov     ecx, eax; unsigned int
0x180009ad5  mov     r14d, eax
0x180009ad8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009add  test    eax, eax
0x180009adf  jnz     loc_180009C8C
0x180009ae5  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009aec  test    rax, rax
0x180009aef  jz      short loc_180009B06
0x180009af1  mov     r8, r12
0x180009af4  lea     rdx, aCtftpreadfilem; "CTftpReadFileManager::GetFileReader: Cr"...
0x180009afb  mov     ecx, 10000h
0x180009b00  call    cs:__guard_dispatch_icall_fptr
0x180009b06  mov     rdi, rbx
0x180009b09  mov     rdx, r13; void **
0x180009b0c  mov     rcx, rdi; this
0x180009b0f  call    ?AddFileReference@CTftpFileReader@@QEAAKPEAPEAX@Z; CTftpFileReader::AddFileReference(void * *)
0x180009b14  mov     r9d, 19Fh; unsigned int
0x180009b1a  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009b21  mov     ecx, eax; unsigned int
0x180009b23  mov     r14d, eax
0x180009b26  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009b2b  test    eax, eax
0x180009b2d  jnz     loc_180009C8C
0x180009b33  jmp     loc_180009BEB
0x180009b38  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009b3f  test    rax, rax
0x180009b42  jz      short loc_180009B59
0x180009b44  mov     r8, r12
0x180009b47  lea     rdx, aCtftpreadfilem_8; "CTftpReadFileManager::GetFileReader: CT"...
0x180009b4e  mov     ecx, 10000h
0x180009b53  call    cs:__guard_dispatch_icall_fptr
0x180009b59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b60  mov     ecx, 90h; unsigned __int64
0x180009b65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b6a  test    rax, rax
0x180009b6d  jz      short loc_180009B7A
0x180009b6f  mov     rcx, rax; this
0x180009b72  call    ??0CTftpFileReader@@QEAA@XZ; CTftpFileReader::CTftpFileReader(void)
0x180009b77  mov     rbx, rax
0x180009b7a  test    rbx, rbx
0x180009b7d  jnz     short loc_180009B88
0x180009b7f  lea     r14d, [rbx+8]
0x180009b83  jmp     loc_180009C8C
0x180009b88  mov     rdx, r12; unsigned __int16 *
0x180009b8b  mov     rcx, rbx; this
0x180009b8e  call    ?Initialize@CTftpFileReader@@QEAAKPEBG@Z; CTftpFileReader::Initialize(ushort const *)
0x180009b93  mov     r9d, 15Bh; unsigned int
0x180009b99  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009ba0  mov     ecx, eax; unsigned int
0x180009ba2  mov     r14d, eax
0x180009ba5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009baa  test    eax, eax
0x180009bac  jnz     loc_180009C8C
0x180009bb2  mov     rdx, r13; void **
0x180009bb5  mov     rcx, rbx; this
0x180009bb8  call    ?AddFileReference@CTftpFileReader@@QEAAKPEAPEAX@Z; CTftpFileReader::AddFileReference(void * *)
0x180009bbd  mov     r9d, 161h; unsigned int
0x180009bc3  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009bca  mov     ecx, eax; unsigned int
0x180009bcc  mov     r14d, eax
0x180009bcf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009bd4  test    eax, eax
0x180009bd6  jnz     loc_180009C8C
0x180009bdc  lea     rdx, [rbp+var_18]
0x180009be0  mov     rcx, rsi
0x180009be3  call    ?PurgeDeadFileReaders@CTftpReadFileManager@@AEAAXAEAV?$CDynArray@PEAVCTftpFileReader@@VCDeallocateNone@@@@@Z; CTftpReadFileManager::PurgeDeadFileReaders(CDynArray<CTftpFileReader *,CDeallocateNone> &)
0x180009be8  mov     rdi, rbx
0x180009beb  mov     rcx, [rbp+arg_10]
0x180009bef  mov     [rcx], rdi
0x180009bf2  test    rbx, rbx
0x180009bf5  jz      loc_180009C8C
0x180009bfb  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180009bff  call    ?WdsGetStringHash@@YAKPEBG@Z; WdsGetStringHash(ushort const *)
0x180009c04  mov     r8d, eax
0x180009c07  mov     [rbx+88h], eax
0x180009c0d  mov     ecx, r8d
0x180009c10  mov     eax, 21FB7813h
0x180009c15  mul     r8d
0x180009c18  sub     ecx, edx
0x180009c1a  shr     ecx, 1
0x180009c1c  add     ecx, edx
0x180009c1e  shr     ecx, 6
0x180009c21  imul    ecx, 71h ; 'q'
0x180009c24  sub     r8d, ecx
0x180009c27  lea     rcx, [r8+r8*2]
0x180009c2b  cmp     qword ptr [rsi+rcx*8+80h], 0
0x180009c34  jnz     short loc_180009C55
0x180009c36  mov     [rsi+rcx*8+88h], rbx
0x180009c3e  mov     [rsi+rcx*8+80h], rbx
0x180009c46  and     qword ptr [rbx+78h], 0
0x180009c4b  and     qword ptr [rbx+80h], 0
0x180009c53  jmp     short loc_180009C7D
0x180009c55  and     qword ptr [rbx+78h], 0
0x180009c5a  mov     rax, [rsi+rcx*8+88h]
0x180009c62  mov     [rbx+80h], rax
0x180009c69  mov     rax, [rsi+rcx*8+88h]
0x180009c71  mov     [rax+78h], rbx
0x180009c75  mov     [rsi+rcx*8+88h], rbx
0x180009c7d  inc     dword ptr [rsi+rcx*8+94h]
0x180009c84  inc     dword ptr [rsi+0B18h]
0x180009c8a  xor     ebx, ebx
0x180009c8c  mov     rcx, rsi; lpCriticalSection
0x180009c8f  call    cs:__imp_LeaveCriticalSection
0x180009c96  nop     dword ptr [rax+rax+00h]
0x180009c9b  lea     rdx, [rbp+var_18]
0x180009c9f  call    ?DeleteFileReaders@CTftpReadFileManager@@AEAAXAEAV?$CDynArray@PEAVCTftpFileReader@@VCDeallocateNone@@@@@Z; CTftpReadFileManager::DeleteFileReaders(CDynArray<CTftpFileReader *,CDeallocateNone> &)
0x180009ca4  test    rbx, rbx
0x180009ca7  jz      short loc_180009CEE
0x180009ca9  lea     rax, ??_7CTftpFileReader@@6B@; const CTftpFileReader::`vftable'
0x180009cb0  mov     rcx, rbx; this
0x180009cb3  mov     [rbx], rax
0x180009cb6  call    ?Shutdown@CTftpFileReader@@QEAAKXZ; CTftpFileReader::Shutdown(void)
0x180009cbb  mov     rcx, [rbx+60h]; void *
0x180009cbf  test    rcx, rcx
0x180009cc2  jz      short loc_180009CD6
0x180009cc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cc9  and     qword ptr [rbx+60h], 0
0x180009cce  and     dword ptr [rbx+6Ch], 0
0x180009cd2  and     dword ptr [rbx+68h], 0
0x180009cd6  lea     rcx, [rbx+8]; lpCriticalSection
0x180009cda  call    cs:__imp_DeleteCriticalSection
0x180009ce1  nop     dword ptr [rax+rax+00h]
0x180009ce6  mov     rcx, rbx; void *
0x180009ce9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cee  mov     rcx, [rbp+var_18]; void *
0x180009cf2  test    rcx, rcx
0x180009cf5  jz      short loc_180009CFC
0x180009cf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cfc  lea     r11, [rsp+50h+var_s0]
0x180009d01  mov     eax, r14d
0x180009d04  mov     rbx, [r11+38h]
0x180009d08  mov     rsi, [r11+48h]
0x180009d0c  mov     rsp, r11
0x180009d0f  pop     r14
0x180009d11  pop     r13
0x180009d13  pop     r12
0x180009d15  pop     rdi
0x180009d16  pop     rbp
0x180009d17  retn
```
