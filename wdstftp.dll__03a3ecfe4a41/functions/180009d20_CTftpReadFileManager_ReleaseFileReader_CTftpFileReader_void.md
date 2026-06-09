# CTftpReadFileManager::ReleaseFileReader(CTftpFileReader *,void *)

- ea: `0x180009d20`
- end: `0x18000a00e`
- name: `?ReleaseFileReader@CTftpReadFileManager@@QEAAXPEAVCTftpFileReader@@PEAX@Z`
- size: `750`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CTftpFileReader *this, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000615c`

## callees

- `0x1800057f8`
- `0x180008b1c`
- `0x180009d20`
- `0x18000a590`
- `0x18000a960`
- `0x18000c168`
- `0x18000c49c`
- `0x18000d66c`
- `0x18000d84c`
- `0x18003c084`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009d40`
- `KERNEL32!EnterCriticalSection` at `0x180009d81`
- `KERNEL32!EnterCriticalSection` at `0x180009d40`
- `KERNEL32!EnterCriticalSection` at `0x180009d81`
- `KERNEL32!LeaveCriticalSection` at `0x180009e0c`
- `KERNEL32!LeaveCriticalSection` at `0x180009e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180009fa0`
- `KERNEL32!LeaveCriticalSection` at `0x180009e0c`
- `KERNEL32!LeaveCriticalSection` at `0x180009e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180009fa0`
- `KERNEL32!DeleteCriticalSection` at `0x180009e3d`
- `KERNEL32!DeleteCriticalSection` at `0x180009fe2`
- `KERNEL32!DeleteCriticalSection` at `0x180009e3d`
- `KERNEL32!DeleteCriticalSection` at `0x180009fe2`

## string_xrefs

- `0x180009d5c`: `CTftpReadFileManager::ReleaseFileReader: Releasing a reference to CTftpFileReader instance for file: %s.`
- `0x180009ee8`: `CTftpReadFileManager::ReleaseFileReader: File %s is modified since opening; deleting the unreferenced CTftpFileReader instance`

## pseudocode

```c
void __fastcall CTftpReadFileManager::ReleaseFileReader(
        LPCRITICAL_SECTION lpCriticalSection,
        struct CTftpFileReader *this,
        unsigned int *a3)
{
  int v6; // r15d
  int v7; // r13d
  unsigned __int64 v8; // rbx
  __int64 v9; // rdx
  unsigned int v10; // ecx
  __int64 v11; // rbx
  unsigned int *v12; // rcx
  unsigned int v13; // edx
  __int64 v14; // rax
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-10h]

  EnterCriticalSection(lpCriticalSection);
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(
      0x10000u,
      L"CTftpReadFileManager::ReleaseFileReader: Releasing a reference to CTftpFileReader instance for file: %s.",
      *((_QWORD *)this + 9));
  v6 = 0;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) && a3 == *((unsigned int **)this + 11) )
  {
    v8 = 0;
    goto LABEL_17;
  }
  v9 = 0;
  v6 = 1;
  if ( !*((_DWORD *)this + 27) )
  {
LABEL_21:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    goto LABEL_22;
  }
  while ( a3 != *(unsigned int **)(*((_QWORD *)this + 12) + 8 * v9) )
  {
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= *((_DWORD *)this + 27) )
      goto LABEL_21;
  }
  v10 = a3[31];
  if ( !v10 )
  {
    v11 = a3[27];
    goto LABEL_15;
  }
  if ( v10 == 1 )
  {
    v11 = a3[40];
LABEL_15:
    v8 = a3[26] * v11;
    goto LABEL_16;
  }
  v8 = 0;
LABEL_16:
  CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem((char *)this + 96);
LABEL_17:
  v7 = --*((_DWORD *)this + 12);
  if ( !v6 )
    goto LABEL_21;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a3 )
  {
    CTptReadFile::Shutdown((LPCRITICAL_SECTION)a3);
    CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(a3 + 42);
    CWIMFile::Shutdown((CWIMFile *)(a3 + 18));
    DeleteCriticalSection((LPCRITICAL_SECTION)a3);
    operator delete(a3);
  }
  CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 6, 1, 1);
  LODWORD(v17) = v8 >> 10;
  CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 7, 1, v17);
LABEL_22:
  if ( v7 )
  {
LABEL_36:
    this = 0;
    goto LABEL_37;
  }
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0)
    || !(unsigned int)CTptReadFile::ModifiedSinceOpen(*((LPCRITICAL_SECTION *)this + 11)) )
  {
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) )
    {
      v14 = 0;
      goto LABEL_35;
    }
    v12 = (unsigned int *)*((_QWORD *)this + 11);
    v13 = v12[31];
    if ( v13 )
    {
      if ( v13 != 1 )
      {
        v14 = 0;
LABEL_35:
        lpCriticalSection[1].OwningThread = (char *)lpCriticalSection[1].OwningThread + v14;
        _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0);
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 8);
        goto LABEL_36;
      }
      v15 = v12[40];
    }
    else
    {
      v15 = v12[27];
    }
    v14 = v12[26] * v15;
    goto LABEL_35;
  }
  CSmHashTable<CTftpFileReader,CNoLock,113>::RemoveItem(&lpCriticalSection[3], this);
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(
      0x10000u,
      L"CTftpReadFileManager::ReleaseFileReader: File %s is modified since opening; deleting the unreferenced CTftpFileReader instance",
      *((_QWORD *)this + 9));
LABEL_37:
  LeaveCriticalSection(lpCriticalSection);
  if ( this )
  {
    *(_QWORD *)this = &CTftpFileReader::`vftable';
    CTftpFileReader::Shutdown(this);
    v16 = (void *)*((_QWORD *)this + 12);
    if ( v16 )
    {
      operator delete(v16);
      *((_QWORD *)this + 12) = 0;
      *((_DWORD *)this + 27) = 0;
      *((_DWORD *)this + 26) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180009d20  mov     [rsp-38h+arg_18], rbx
0x180009d25  push    rbp
0x180009d26  push    rsi
0x180009d27  push    rdi
0x180009d28  push    r12
0x180009d2a  push    r13
0x180009d2c  push    r14
0x180009d2e  push    r15
0x180009d30  mov     rbp, rsp
0x180009d33  sub     rsp, 30h
0x180009d37  mov     rsi, r8
0x180009d3a  mov     rdi, rdx
0x180009d3d  mov     r14, rcx
0x180009d40  call    cs:__imp_EnterCriticalSection
0x180009d47  nop     dword ptr [rax+rax+00h]
0x180009d4c  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009d53  test    rax, rax
0x180009d56  jz      short loc_180009D6E
0x180009d58  mov     r8, [rdi+48h]
0x180009d5c  lea     rdx, aCtftpreadfilem_6; "CTftpReadFileManager::ReleaseFileReader"...
0x180009d63  mov     ecx, 10000h
0x180009d68  call    cs:__guard_dispatch_icall_fptr
0x180009d6e  xor     eax, eax
0x180009d70  lea     r12, [rdi+8]
0x180009d74  mov     rcx, r12; lpCriticalSection
0x180009d77  mov     [rbp+arg_0], rax
0x180009d7b  xor     r15d, r15d
0x180009d7e  xor     r13d, r13d
0x180009d81  call    cs:__imp_EnterCriticalSection
0x180009d88  nop     dword ptr [rax+rax+00h]
0x180009d8d  xor     eax, eax
0x180009d8f  lock xadd [rdi+38h], eax
0x180009d94  test    eax, eax
0x180009d96  jz      short loc_180009DA4
0x180009d98  cmp     rsi, [rdi+58h]
0x180009d9c  jnz     short loc_180009DA4
0x180009d9e  mov     rbx, [rbp+arg_0]
0x180009da2  jmp     short loc_180009DF9
0x180009da4  xor     edx, edx
0x180009da6  lea     r15d, [rdx+1]
0x180009daa  cmp     [rdi+6Ch], edx
0x180009dad  jbe     loc_180009E98
0x180009db3  mov     rcx, [rdi+60h]
0x180009db7  cmp     rsi, [rcx+rdx*8]
0x180009dbb  jz      short loc_180009DCA
0x180009dbd  add     edx, r15d
0x180009dc0  cmp     edx, [rdi+6Ch]
0x180009dc3  jb      short loc_180009DB7
0x180009dc5  jmp     loc_180009E98
0x180009dca  mov     ecx, [rsi+7Ch]
0x180009dcd  test    ecx, ecx
0x180009dcf  jz      short loc_180009DE2
0x180009dd1  cmp     ecx, r15d
0x180009dd4  jz      short loc_180009DDA
0x180009dd6  xor     ebx, ebx
0x180009dd8  jmp     short loc_180009DEC
0x180009dda  mov     ebx, [rsi+0A0h]
0x180009de0  jmp     short loc_180009DE5
0x180009de2  mov     ebx, [rsi+6Ch]
0x180009de5  mov     eax, [rsi+68h]
0x180009de8  imul    rbx, rax
0x180009dec  lea     rcx, [rdi+60h]
0x180009df0  mov     [rbp+arg_0], rbx
0x180009df4  call    ?RemoveItem@?$CDynArray@PEAVCEndpointSessionMapEntry@@VCDeallocateNone@@@@QEAAKK@Z; CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(ulong)
0x180009df9  dec     dword ptr [rdi+30h]
0x180009dfc  mov     r13d, [rdi+30h]
0x180009e00  test    r15d, r15d
0x180009e03  jz      loc_180009E92
0x180009e09  mov     rcx, r12; lpCriticalSection
0x180009e0c  call    cs:__imp_LeaveCriticalSection
0x180009e13  nop     dword ptr [rax+rax+00h]
0x180009e18  test    rsi, rsi
0x180009e1b  jz      short loc_180009E51
0x180009e1d  mov     rcx, rsi; lpCriticalSection
0x180009e20  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x180009e25  lea     rcx, [rsi+0A8h]
0x180009e2c  call    ??1?$CChildCount@VCTptReadFile@@@@QEAA@XZ; CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(void)
0x180009e31  lea     rcx, [rsi+48h]; this
0x180009e35  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x180009e3a  mov     rcx, rsi; lpCriticalSection
0x180009e3d  call    cs:__imp_DeleteCriticalSection
0x180009e44  nop     dword ptr [rax+rax+00h]
0x180009e49  mov     rcx, rsi; void *
0x180009e4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e51  mov     r15d, 1
0x180009e57  lea     rcx, qword_1800779F0; this
0x180009e5e  mov     r9d, r15d
0x180009e61  mov     [rsp+30h+var_10], r15d
0x180009e66  mov     edx, r15d; unsigned int
0x180009e69  lea     r8d, [r15+5]
0x180009e6d  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180009e72  shr     rbx, 0Ah
0x180009e76  lea     r8d, [r15+6]
0x180009e7a  mov     r9d, r15d
0x180009e7d  mov     [rsp+30h+var_10], ebx
0x180009e81  mov     edx, r15d; unsigned int
0x180009e84  lea     rcx, qword_1800779F0; this
0x180009e8b  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180009e90  jmp     short loc_180009EA7
0x180009e92  mov     r15d, 1
0x180009e98  mov     rcx, r12; lpCriticalSection
0x180009e9b  call    cs:__imp_LeaveCriticalSection
0x180009ea2  nop     dword ptr [rax+rax+00h]
0x180009ea7  test    r13d, r13d
0x180009eaa  jnz     loc_180009F9B
0x180009eb0  xor     eax, eax
0x180009eb2  lock xadd [rdi+38h], eax
0x180009eb7  test    eax, eax
0x180009eb9  jz      short loc_180009EFF
0x180009ebb  mov     rcx, [rdi+58h]; lpCriticalSection
0x180009ebf  call    ?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ; CTptReadFile::ModifiedSinceOpen(void)
0x180009ec4  test    eax, eax
0x180009ec6  jz      short loc_180009EFF
0x180009ec8  lea     rcx, [r14+78h]
0x180009ecc  mov     rdx, rdi
0x180009ecf  call    ?RemoveItem@?$CSmHashTable@VCTftpFileReader@@VCNoLock@@$0HB@@@QEAAPEAVCTftpFileReader@@PEAV2@@Z; CSmHashTable<CTftpFileReader,CNoLock,113>::RemoveItem(CTftpFileReader *)
0x180009ed4  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009edb  test    rax, rax
0x180009ede  jz      loc_180009F9D
0x180009ee4  mov     r8, [rdi+48h]
0x180009ee8  lea     rdx, aCtftpreadfilem_9; "CTftpReadFileManager::ReleaseFileReader"...
0x180009eef  mov     ecx, 10000h
0x180009ef4  call    cs:__guard_dispatch_icall_fptr
0x180009efa  jmp     loc_180009F9D
0x180009eff  xor     eax, eax
0x180009f01  mov     [rbp+arg_8], rax
0x180009f05  lock xadd [rdi+38h], eax
0x180009f0a  test    eax, eax
0x180009f0c  jz      short loc_180009F3A
0x180009f0e  mov     rcx, [rdi+58h]
0x180009f12  mov     edx, [rcx+7Ch]
0x180009f15  test    edx, edx
0x180009f17  jz      short loc_180009F35
0x180009f19  cmp     edx, 1
0x180009f1c  jz      short loc_180009F22
0x180009f1e  xor     eax, eax
0x180009f20  jmp     short loc_180009F2F
0x180009f22  mov     eax, [rcx+0A0h]
0x180009f28  mov     ecx, [rcx+68h]
0x180009f2b  imul    rax, rcx
0x180009f2f  mov     [rbp+arg_8], rax
0x180009f33  jmp     short loc_180009F3E
0x180009f35  mov     eax, [rcx+6Ch]
0x180009f38  jmp     short loc_180009F28
0x180009f3a  mov     rax, [rbp+arg_8]
0x180009f3e  add     [r14+38h], rax
0x180009f42  xor     eax, eax
0x180009f44  mov     [rbp+arg_10], rax
0x180009f48  lock xadd [rdi+38h], eax
0x180009f4d  test    eax, eax
0x180009f4f  jz      short loc_180009F79
0x180009f51  mov     rcx, [rdi+58h]
0x180009f55  mov     edx, [rcx+7Ch]
0x180009f58  test    edx, edx
0x180009f5a  jz      short loc_180009F74
0x180009f5c  cmp     edx, 1
0x180009f5f  jz      short loc_180009F65
0x180009f61  xor     eax, eax
0x180009f63  jmp     short loc_180009F7D
0x180009f65  mov     eax, [rcx+0A0h]
0x180009f6b  mov     ecx, [rcx+68h]
0x180009f6e  imul    rax, rcx
0x180009f72  jmp     short loc_180009F7D
0x180009f74  mov     eax, [rcx+6Ch]
0x180009f77  jmp     short loc_180009F6B
0x180009f79  mov     rax, [rbp+arg_10]
0x180009f7d  xor     r9d, r9d
0x180009f80  shr     rax, 0Ah
0x180009f84  mov     edx, r15d; unsigned int
0x180009f87  mov     [rsp+30h+var_10], eax
0x180009f8b  lea     rcx, qword_1800779F0; this
0x180009f92  lea     r8d, [r9+8]
0x180009f96  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180009f9b  xor     edi, edi
0x180009f9d  mov     rcx, r14; lpCriticalSection
0x180009fa0  call    cs:__imp_LeaveCriticalSection
0x180009fa7  nop     dword ptr [rax+rax+00h]
0x180009fac  test    rdi, rdi
0x180009faf  jz      short loc_180009FF6
0x180009fb1  lea     rax, ??_7CTftpFileReader@@6B@; const CTftpFileReader::`vftable'
0x180009fb8  mov     rcx, rdi; this
0x180009fbb  mov     [rdi], rax
0x180009fbe  call    ?Shutdown@CTftpFileReader@@QEAAKXZ; CTftpFileReader::Shutdown(void)
0x180009fc3  mov     rcx, [rdi+60h]; void *
0x180009fc7  test    rcx, rcx
0x180009fca  jz      short loc_180009FDE
0x180009fcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009fd1  and     qword ptr [rdi+60h], 0
0x180009fd6  and     dword ptr [rdi+6Ch], 0
0x180009fda  and     dword ptr [rdi+68h], 0
0x180009fde  lea     rcx, [rdi+8]; lpCriticalSection
0x180009fe2  call    cs:__imp_DeleteCriticalSection
0x180009fe9  nop     dword ptr [rax+rax+00h]
0x180009fee  mov     rcx, rdi; void *
0x180009ff1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ff6  mov     rbx, [rsp+30h+arg_18]
0x180009ffe  add     rsp, 30h
0x18000a002  pop     r15
0x18000a004  pop     r14
0x18000a006  pop     r13
0x18000a008  pop     r12
0x18000a00a  pop     rdi
0x18000a00b  pop     rsi
0x18000a00c  pop     rbp
0x18000a00d  retn
```
