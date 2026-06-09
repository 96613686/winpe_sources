# CTftpFileReader::AddFileReference(void * *)

- ea: `0x180008d80`
- end: `0x180009002`
- name: `?AddFileReference@CTftpFileReader@@QEAAKPEAPEAX@Z`
- size: `642`
- prototype: `__int64 __fastcall(CTftpFileReader *this, struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800098a0`

## callees

- `0x180005850`
- `0x180008d80`
- `0x180009008`
- `0x18000a960`
- `0x18000beac`
- `0x18000bfcc`
- `0x18000c168`
- `0x18000c5fc`
- `0x18000d66c`
- `0x18000d84c`
- `0x18003c084`
- `0x18003ce78`
- `0x1800607e0`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180008da6`
- `KERNEL32!EnterCriticalSection` at `0x180008da6`
- `KERNEL32!LeaveCriticalSection` at `0x180008fdb`
- `KERNEL32!LeaveCriticalSection` at `0x180008fdb`
- `KERNEL32!DeleteCriticalSection` at `0x180008fc3`
- `KERNEL32!DeleteCriticalSection` at `0x180008fc3`

## string_xrefs

- `0x180008e0a`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180008e34`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180008ea4`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180008f22`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180008ed7`: `CTftpFileReader::AddFileReference: Using shared CTptReadFile instance for file: %s.`
- `0x180008f4b`: `CTftpFileReader::AddFileReference: Created a new CTptReadFile instance for file: %s.`

## pseudocode

```c
__int64 __fastcall CTftpFileReader::AddFileReference(CTftpFileReader *this, struct _RTL_CRITICAL_SECTION **a2)
{
  unsigned int v4; // ebp
  struct _RTL_CRITICAL_SECTION *File; // rbx
  CTptReadFile *v6; // rax
  unsigned int v7; // r8d
  const char *v8; // rdx
  const char *v9; // rdx
  LPCRITICAL_SECTION v10; // rcx
  unsigned __int64 LockSemaphore; // rax
  int OwningThread; // edx
  unsigned __int64 v13; // rax
  unsigned int v14; // eax
  const char *v15; // rdx
  const char *v16; // rdx
  void (*v17)(unsigned int, const unsigned __int16 *, ...); // rax

  v4 = 0;
  File = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) )
    goto LABEL_15;
  v6 = (CTptReadFile *)operator new(0x130u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    File = (struct _RTL_CRITICAL_SECTION *)CTptReadFile::CTptReadFile(v6);
  if ( !File )
  {
    v4 = 8;
    goto LABEL_24;
  }
  v4 = CTptReadFile::Initialize(File, (unsigned int)lpCriticalSection[13].OwningThread, v7);
  if ( !ElValidateWin32(v4, v8, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x11Fu) )
  {
    v4 = CTptReadFile::Open(File, *((const unsigned __int16 **)this + 9));
    if ( !ElValidateWin32(v4, v9, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x122u) )
    {
      if ( !*((_DWORD *)this + 16) )
      {
        v10 = lpCriticalSection;
        LockSemaphore = (unsigned __int64)File[1].LockSemaphore;
        *((_QWORD *)this + 10) = LockSemaphore;
        OwningThread = (int)v10[13].OwningThread;
        *((_DWORD *)this + 16) = 1;
        v13 = LockSemaphore / (unsigned int)(2 * OwningThread);
        if ( v13 > 0xFFFFFFFF )
          LODWORD(v13) = -2;
        *((_DWORD *)this + 15) = v13;
      }
      v14 = *((_DWORD *)this + 15);
      if ( v14 < 2 || *((_DWORD *)this + 12) != v14 )
      {
        v4 = CDynArray<CTptReadFile *,CDeallocateNone>::AddItem((char *)this + 96);
        if ( ElValidateWin32(v4, v16, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x148u) )
          goto LABEL_22;
        v17 = g_ErrLibTraceFunctionEx;
        *a2 = File;
        File = 0;
        if ( v17 )
          v17(
            0x10000u,
            L"CTftpFileReader::AddFileReference: Created a new CTptReadFile instance for file: %s.",
            *((_QWORD *)this + 9));
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 6);
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 7);
        goto LABEL_21;
      }
      v4 = CTftpFileReader::SwitchToSharedCacheMode(this);
      if ( ElValidateWin32(v4, v15, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x132u) )
        goto LABEL_22;
LABEL_15:
      *a2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 11);
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(
          0x10000u,
          L"CTftpFileReader::AddFileReference: Using shared CTptReadFile instance for file: %s.",
          *((_QWORD *)this + 9));
LABEL_21:
      ++*((_DWORD *)this + 12);
    }
  }
LABEL_22:
  if ( File )
  {
    CTptReadFile::Shutdown(File);
    CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(&File[4].LockCount);
    CWIMFile::Shutdown((CWIMFile *)&File[1].SpinCount);
    DeleteCriticalSection(File);
    operator delete(File);
  }
LABEL_24:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v4;
}

```

## disassembly

```asm
0x180008d80  mov     [rsp+arg_0], rbx
0x180008d85  mov     [rsp+arg_8], rbp
0x180008d8a  mov     [rsp+arg_10], rsi
0x180008d8f  push    rdi
0x180008d90  push    r14
0x180008d92  push    r15
0x180008d94  sub     rsp, 30h
0x180008d98  mov     rdi, rcx
0x180008d9b  mov     r14, rdx
0x180008d9e  add     rcx, 8; lpCriticalSection
0x180008da2  xor     ebp, ebp
0x180008da4  xor     ebx, ebx
0x180008da6  call    cs:__imp_EnterCriticalSection
0x180008dad  nop     dword ptr [rax+rax+00h]
0x180008db2  xor     eax, eax
0x180008db4  lock xadd [rdi+38h], eax
0x180008db9  test    eax, eax
0x180008dbb  jnz     loc_180008EBC
0x180008dc1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008dc8  mov     ecx, 130h; unsigned __int64
0x180008dcd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008dd2  test    rax, rax
0x180008dd5  jz      short loc_180008DE2
0x180008dd7  mov     rcx, rax; this
0x180008dda  call    ??0CTptReadFile@@QEAA@XZ; CTptReadFile::CTptReadFile(void)
0x180008ddf  mov     rbx, rax
0x180008de2  test    rbx, rbx
0x180008de5  jnz     short loc_180008DEF
0x180008de7  lea     ebp, [rbx+8]
0x180008dea  jmp     loc_180008FD7
0x180008def  mov     rax, cs:lpCriticalSection
0x180008df6  mov     rcx, rbx; lpCriticalSection
0x180008df9  mov     edx, [rax+218h]; unsigned int
0x180008dff  call    ?Initialize@CTptReadFile@@QEAAKKK@Z; CTptReadFile::Initialize(ulong,ulong)
0x180008e04  mov     r9d, 11Fh; unsigned int
0x180008e0a  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180008e11  mov     ecx, eax; unsigned int
0x180008e13  mov     ebp, eax
0x180008e15  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008e1a  test    eax, eax
0x180008e1c  jnz     loc_180008F9E
0x180008e22  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180008e26  mov     rcx, rbx; lpCriticalSection
0x180008e29  call    ?Open@CTptReadFile@@QEAAKPEBG@Z; CTptReadFile::Open(ushort const *)
0x180008e2e  mov     r9d, 122h; unsigned int
0x180008e34  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180008e3b  mov     ecx, eax; unsigned int
0x180008e3d  mov     ebp, eax
0x180008e3f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008e44  test    eax, eax
0x180008e46  jnz     loc_180008F9E
0x180008e4c  cmp     [rdi+40h], eax
0x180008e4f  jnz     short loc_180008E89
0x180008e51  mov     rcx, cs:lpCriticalSection
0x180008e58  mov     rax, [rbx+40h]
0x180008e5c  mov     [rdi+50h], rax
0x180008e60  mov     edx, [rcx+218h]
0x180008e66  mov     dword ptr [rdi+40h], 1
0x180008e6d  lea     ecx, [rdx+rdx]
0x180008e70  xor     edx, edx
0x180008e72  div     rcx
0x180008e75  mov     ecx, 0FFFFFFFFh
0x180008e7a  mov     edx, 0FFFFFFFEh
0x180008e7f  cmp     rax, rcx
0x180008e82  cmova   rax, rdx
0x180008e86  mov     [rdi+3Ch], eax
0x180008e89  mov     eax, [rdi+3Ch]
0x180008e8c  cmp     eax, 2
0x180008e8f  jb      short loc_180008EEE
0x180008e91  cmp     [rdi+30h], eax
0x180008e94  jnz     short loc_180008EEE
0x180008e96  mov     rcx, rdi; this
0x180008e99  call    ?SwitchToSharedCacheMode@CTftpFileReader@@AEAAKXZ; CTftpFileReader::SwitchToSharedCacheMode(void)
0x180008e9e  mov     r9d, 132h; unsigned int
0x180008ea4  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180008eab  mov     ecx, eax; unsigned int
0x180008ead  mov     ebp, eax
0x180008eaf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008eb4  test    eax, eax
0x180008eb6  jnz     loc_180008F9E
0x180008ebc  mov     rax, [rdi+58h]
0x180008ec0  mov     [r14], rax
0x180008ec3  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180008eca  test    rax, rax
0x180008ecd  jz      loc_180008F9B
0x180008ed3  mov     r8, [rdi+48h]
0x180008ed7  lea     rdx, aCtftpfilereade_0; "CTftpFileReader::AddFileReference: Usin"...
0x180008ede  mov     ecx, 10000h
0x180008ee3  call    cs:__guard_dispatch_icall_fptr
0x180008ee9  jmp     loc_180008F9B
0x180008eee  mov     ecx, [rbx+7Ch]
0x180008ef1  test    ecx, ecx
0x180008ef3  jz      short loc_180008F06
0x180008ef5  cmp     ecx, 1
0x180008ef8  jz      short loc_180008EFE
0x180008efa  xor     esi, esi
0x180008efc  jmp     short loc_180008F10
0x180008efe  mov     esi, [rbx+0A0h]
0x180008f04  jmp     short loc_180008F09
0x180008f06  mov     esi, [rbx+6Ch]
0x180008f09  mov     eax, [rbx+68h]
0x180008f0c  imul    rsi, rax
0x180008f10  lea     rcx, [rdi+60h]
0x180008f14  mov     rdx, rbx
0x180008f17  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x180008f1c  mov     r9d, 148h; unsigned int
0x180008f22  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180008f29  mov     ecx, eax; unsigned int
0x180008f2b  mov     ebp, eax
0x180008f2d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008f32  test    eax, eax
0x180008f34  jnz     short loc_180008F9E
0x180008f36  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180008f3d  mov     [r14], rbx
0x180008f40  xor     ebx, ebx
0x180008f42  test    rax, rax
0x180008f45  jz      short loc_180008F5D
0x180008f47  mov     r8, [rdi+48h]
0x180008f4b  lea     rdx, aCtftpfilereade; "CTftpFileReader::AddFileReference: Crea"...
0x180008f52  mov     ecx, 10000h
0x180008f57  call    cs:__guard_dispatch_icall_fptr
0x180008f5d  xor     r9d, r9d
0x180008f60  mov     [rsp+48h+var_28], 1
0x180008f68  lea     rcx, qword_1800779F0; this
0x180008f6f  lea     edx, [r9+1]; unsigned int
0x180008f73  lea     r8d, [r9+6]
0x180008f77  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008f7c  xor     r9d, r9d
0x180008f7f  shr     rsi, 0Ah
0x180008f83  lea     rcx, qword_1800779F0; this
0x180008f8a  mov     [rsp+48h+var_28], esi
0x180008f8e  lea     edx, [r9+1]; unsigned int
0x180008f92  lea     r8d, [r9+7]
0x180008f96  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008f9b  inc     dword ptr [rdi+30h]
0x180008f9e  test    rbx, rbx
0x180008fa1  jz      short loc_180008FD7
0x180008fa3  mov     rcx, rbx; lpCriticalSection
0x180008fa6  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x180008fab  lea     rcx, [rbx+0A8h]
0x180008fb2  call    ??1?$CChildCount@VCTptReadFile@@@@QEAA@XZ; CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(void)
0x180008fb7  lea     rcx, [rbx+48h]; this
0x180008fbb  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x180008fc0  mov     rcx, rbx; lpCriticalSection
0x180008fc3  call    cs:__imp_DeleteCriticalSection
0x180008fca  nop     dword ptr [rax+rax+00h]
0x180008fcf  mov     rcx, rbx; void *
0x180008fd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008fd7  lea     rcx, [rdi+8]; lpCriticalSection
0x180008fdb  call    cs:__imp_LeaveCriticalSection
0x180008fe2  nop     dword ptr [rax+rax+00h]
0x180008fe7  mov     rbx, [rsp+48h+arg_0]
0x180008fec  mov     eax, ebp
0x180008fee  mov     rbp, [rsp+48h+arg_8]
0x180008ff3  mov     rsi, [rsp+48h+arg_10]
0x180008ff8  add     rsp, 30h
0x180008ffc  pop     r15
0x180008ffe  pop     r14
0x180009000  pop     rdi
0x180009001  retn
```
