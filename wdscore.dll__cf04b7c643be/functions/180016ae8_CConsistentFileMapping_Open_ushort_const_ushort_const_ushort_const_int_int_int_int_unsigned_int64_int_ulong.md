# CConsistentFileMapping::Open(ushort const *,ushort const *,ushort const *,int,int,int,int,unsigned __int64,int *,ulong)

- ea: `0x180016ae8`
- end: `0x180017005`
- name: `?Open@CConsistentFileMapping@@IEAAHPEBG00HHHH_KPEAHK@Z`
- size: `1309`
- prototype: `__int64 __fastcall(CConsistentFileMapping *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, int, int, unsigned __int64, int *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180010ab0`

## callees

- `0x180002250`
- `0x180010180`
- `0x180016888`
- `0x180016ae8`
- `0x18001dc70`
- `0x1800274de`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016f6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016fca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016f6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016fca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028eab`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180016b49`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180016b49`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180016d49`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180016d49`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016e21`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016f21`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180028dc4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016e21`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016f21`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180028dc4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016df2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016df2`

## string_xrefs

- `0x180016cc4`: `CConsistentFileMapping::Open`
- `0x180016c99`: `CConsistentFileMapping::Open: CreateFile failed.`

## pseudocode

```c
__int64 __fastcall CConsistentFileMapping::Open(
        CConsistentFileMapping *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned __int64 a9,
        int *a10,
        unsigned int a11)
{
  unsigned __int64 v12; // rbx
  __int64 v13; // r13
  void *v14; // r15
  const void *v15; // r14
  int v16; // edi
  HANDLE MutexW; // r12
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ebx
  int v21; // eax
  int *v22; // rdi
  void *v23; // rax
  void *v24; // rax
  unsigned int v25; // ebx
  DWORD dwDesiredAccess; // [rsp+64h] [rbp-74h]
  DWORD FileSizeHigh[2]; // [rsp+68h] [rbp-70h] BYREF
  int v29; // [rsp+70h] [rbp-68h]
  void *v30; // [rsp+78h] [rbp-60h]
  void *v31; // [rsp+80h] [rbp-58h]
  unsigned int v32; // [rsp+88h] [rbp-50h]
  __int64 v33; // [rsp+90h] [rbp-48h]
  HANDLE v34; // [rsp+98h] [rbp-40h]
  LPCWSTR lpModuleName; // [rsp+D8h] [rbp+0h]

  v12 = a9;
  v13 = -1;
  v33 = -1;
  v14 = 0;
  v31 = 0;
  v15 = 0;
  v30 = 0;
  v16 = 4;
  dwDesiredAccess = 4;
  v29 = 2;
  MutexW = CreateMutexW(0, 1, a3);
  v34 = MutexW;
  if ( !MutexW )
    goto LABEL_31;
  if ( (**(unsigned int (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32) == 183 )
  {
    (*(void (__fastcall **)(struct IKernel32Interface *, HANDLE, __int64))(*(_QWORD *)g_Kernel32 + 416LL))(
      g_Kernel32,
      MutexW,
      0xFFFFFFFFLL);
    if ( a10 )
      *a10 = 0;
    v16 = 4;
  }
  *((_DWORD *)this + 15) = a7;
  v18 = 0x80000000LL;
  v32 = 0x80000000;
  if ( a5 )
    v19 = a6 != 0 ? 1 : 3;
  else
    v19 = 0;
  if ( !a6 )
  {
    v29 = 4;
    v16 = 6;
    dwDesiredAccess = 6;
    v18 = 3221225472LL;
    v32 = -1073741824;
  }
  v13 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, const unsigned __int16 *, __int64, __int64, _QWORD, int, unsigned int, _QWORD))(*(_QWORD *)g_Kernel32 + 192LL))(
          g_Kernel32,
          a2,
          v18,
          v19,
          0,
          4,
          (a7 != 0 ? 0x100 : 0) | 0x10000000u,
          0);
  v33 = v13;
  if ( v13 == -1 )
  {
    if ( g_bEnableDiagnosticMode )
    {
      v20 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
      v21 = (unsigned int)ConstructPartialMsgW(0x6B000000u, "CConsistentFileMapping::Open: CreateFile failed.");
      WdsSetupLogMessageW(
        v21,
        589824,
        (int)L"D",
        0,
        561,
        L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
        (__int64)L"CConsistentFileMapping::Open",
        lpModuleName,
        v20,
        0,
        0);
LABEL_30:
      v16 = dwDesiredAccess;
    }
LABEL_31:
    v25 = 0;
    goto LABEL_32;
  }
  v22 = a10;
  if ( a10 )
  {
    if ( (**(unsigned int (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32) == 183 )
    {
      *v22 = 0;
    }
    else
    {
      *v22 = 1;
      *((_DWORD *)this + 13) = 1;
    }
  }
  FileSizeHigh[1] = 0;
  FileSizeHigh[0] = GetFileSize((HANDLE)v13, &FileSizeHigh[1]);
  if ( FileSizeHigh[0] == -1 )
    goto LABEL_30;
  if ( *(_QWORD *)FileSizeHigh )
  {
    v16 = dwDesiredAccess;
  }
  else
  {
    *(_QWORD *)FileSizeHigh = v12 << 8;
    if ( !is_mul_ok(0x100u, v12) )
      goto LABEL_30;
    v23 = (void *)(*(__int64 (__fastcall **)(struct IKernel32Interface *, __int64, _QWORD, _QWORD, _DWORD, DWORD, _QWORD))(*(_QWORD *)g_Kernel32 + 592LL))(
                    g_Kernel32,
                    v13,
                    0,
                    a11 | v29,
                    0,
                    FileSizeHigh[0],
                    0);
    v14 = v23;
    v31 = v23;
    v16 = dwDesiredAccess;
    if ( !v23 )
      goto LABEL_31;
    v24 = MapViewOfFile(v23, dwDesiredAccess, 0, 0, FileSizeHigh[0]);
    v15 = v24;
    v30 = v24;
    if ( !v24 )
      goto LABEL_31;
    memset_0(v24, 0, FileSizeHigh[0]);
    UnmapViewOfFile(v15);
    v30 = 0;
    (*(void (__fastcall **)(struct IKernel32Interface *, void *))(*(_QWORD *)g_Kernel32 + 200LL))(g_Kernel32, v14);
    v31 = 0;
  }
  a8 = 0;
  if ( !(unsigned int)CBBSharedMemory::Open((CConsistentFileMapping *)((char *)this + 96), a4, 0x100u, &a8) )
  {
    v14 = 0;
    v31 = 0;
    v15 = 0;
    v30 = 0;
    goto LABEL_31;
  }
  *((_QWORD *)this + 1) = *((_QWORD *)this + 13);
  if ( !a8 )
  {
    **((_QWORD **)this + 1) = *(_QWORD *)FileSizeHigh;
    *(_DWORD *)(*((_QWORD *)this + 1) + 20LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) = 0;
  }
  v25 = 1;
  v14 = 0;
  v31 = 0;
  v15 = 0;
  v30 = 0;
LABEL_32:
  if ( v14 )
  {
    if ( v15 )
      UnmapViewOfFile(v15);
    (*(void (__fastcall **)(struct IKernel32Interface *, void *))(*(_QWORD *)g_Kernel32 + 200LL))(g_Kernel32, v14);
  }
  if ( v25 )
  {
    *((_QWORD *)this + 4) = MutexW;
    *((_QWORD *)this + 2) = v13;
    *((_QWORD *)this + 5) = (*(__int64 (__fastcall **)(CConsistentFileMapping *))(*(_QWORD *)this + 72LL))(this);
    if ( !*((_DWORD *)this + 13) )
      ReleaseMutex(MutexW);
    *((_DWORD *)this + 14) = a11;
    *((_DWORD *)this + 16) = v29;
    *((_DWORD *)this + 17) = v16;
    *((_DWORD *)this + 18) = a5;
  }
  else
  {
    CBBSharedMemory::Close((CConsistentFileMapping *)((char *)this + 96));
    if ( v13 != -1 )
      (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 200LL))(g_Kernel32, v13);
    if ( MutexW )
    {
      ReleaseMutex(MutexW);
      (*(void (__fastcall **)(struct IKernel32Interface *, HANDLE))(*(_QWORD *)g_Kernel32 + 200LL))(g_Kernel32, MutexW);
    }
  }
  return v25;
}

```

## disassembly

```asm
0x180016ae8  mov     rax, rsp
0x180016aeb  mov     [rax+20h], r9
0x180016aef  mov     [rax+10h], rdx
0x180016af3  mov     [rax+8], rcx
0x180016af7  push    rbx
0x180016af8  push    rsi
0x180016af9  push    rdi
0x180016afa  push    r12
0x180016afc  push    r13
0x180016afe  push    r14
0x180016b00  push    r15
0x180016b02  sub     rsp, 0A0h
0x180016b09  mov     rsi, rcx
0x180016b0c  mov     rbx, [rsp+0D8h+arg_40]
0x180016b14  mov     qword ptr [rax-40h], 0
0x180016b1c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180016b20  mov     [rax-48h], r13
0x180016b24  xor     r15d, r15d
0x180016b27  mov     [rax-58h], r15
0x180016b2b  xor     r14d, r14d
0x180016b2e  mov     [rax-60h], r14
0x180016b32  mov     [rax-78h], r14d
0x180016b36  lea     edi, [r13+5]
0x180016b3a  mov     [rax-74h], edi
0x180016b3d  mov     dword ptr [rax-68h], 2
0x180016b44  lea     edx, [rdi-3]; bInitialOwner
0x180016b47  xor     ecx, ecx; lpMutexAttributes
0x180016b49  call    cs:__imp_CreateMutexW
0x180016b50  nop     dword ptr [rax+rax+00h]
0x180016b55  mov     r12, rax
0x180016b58  mov     [rsp+0D8h+var_40], rax
0x180016b60  test    rax, rax
0x180016b63  jz      loc_180016F10
0x180016b69  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016b70  mov     rax, [rcx]
0x180016b73  mov     rax, [rax]
0x180016b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b7b  cmp     eax, 0B7h
0x180016b80  jnz     short loc_180016BB3
0x180016b82  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016b89  mov     rax, [rcx]
0x180016b8c  or      r8d, 0FFFFFFFFh
0x180016b90  mov     rdx, r12
0x180016b93  mov     rax, [rax+1A0h]
0x180016b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b9f  mov     rdi, [rsp+0D8h+arg_48]
0x180016ba7  test    rdi, rdi
0x180016baa  jz      short loc_180016BAF
0x180016bac  mov     [rdi], r14d
0x180016baf  mov     edi, [rsp+0D8h+dwDesiredAccess]
0x180016bb3  mov     edx, [rsp+0D8h+arg_30]
0x180016bba  mov     [rsi+3Ch], edx
0x180016bbd  mov     r8d, 80000000h
0x180016bc3  mov     [rsp+0D8h+var_50], r8d
0x180016bcb  mov     ecx, [rsp+0D8h+arg_28]
0x180016bd2  cmp     [rsp+0D8h+arg_20], 0
0x180016bda  jz      short loc_180016BED
0x180016bdc  mov     eax, ecx
0x180016bde  neg     eax
0x180016be0  sbb     r9d, r9d
0x180016be3  and     r9d, 0FFFFFFFEh
0x180016be7  add     r9d, 3
0x180016beb  jmp     short loc_180016BF0
0x180016bed  xor     r9d, r9d
0x180016bf0  test    ecx, ecx
0x180016bf2  jnz     short loc_180016C11
0x180016bf4  mov     [rsp+0D8h+var_68], 4
0x180016bfc  lea     edi, [rcx+6]
0x180016bff  mov     [rsp+0D8h+dwDesiredAccess], edi
0x180016c03  mov     r8d, 0C0000000h
0x180016c09  mov     [rsp+0D8h+var_50], r8d
0x180016c11  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016c18  mov     rax, [rcx]
0x180016c1b  neg     edx
0x180016c1d  sbb     edx, edx
0x180016c1f  and     edx, 100h
0x180016c25  bts     edx, 1Ch
0x180016c29  mov     [rsp+0D8h+lpModuleName], 0
0x180016c32  mov     dword ptr [rsp+0D8h+var_A8], edx
0x180016c36  mov     dword ptr [rsp+0D8h+var_B0], 4
0x180016c3e  mov     [rsp+0D8h+dwNumberOfBytesToMap], 0
0x180016c47  mov     rdx, [rsp+0D8h+arg_8]
0x180016c4f  mov     rax, [rax+0C0h]
0x180016c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c5b  mov     r13, rax
0x180016c5e  mov     [rsp+0D8h+var_48], rax
0x180016c66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016c6a  jnz     loc_180016D00
0x180016c70  cmp     cs:?g_bEnableDiagnosticMode@@3HA, 0; int g_bEnableDiagnosticMode
0x180016c77  jz      loc_180016F10
0x180016c7d  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016c84  mov     rdx, [rcx]
0x180016c87  mov     rax, [rdx]
0x180016c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c8f  mov     ebx, eax
0x180016c91  mov     rdi, [rsp+0D8h]
0x180016c99  lea     rdx, aCconsistentfil_0; "CConsistentFileMapping::Open: CreateFil"...
0x180016ca0  mov     ecx, 6B000000h; unsigned int
0x180016ca5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016caa  mov     [rsp+0D8h+var_88], 0; int
0x180016cb2  mov     [rsp+0D8h+var_90], 0; __int64
0x180016cbb  mov     [rsp+0D8h+var_98], ebx; int
0x180016cbf  mov     [rsp+0D8h+lpModuleName], rdi; lpModuleName
0x180016cc4  lea     rcx, aCconsistentfil; "CConsistentFileMapping::Open"
0x180016ccb  mov     [rsp+0D8h+var_A8], rcx; __int64
0x180016cd0  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x180016cd7  mov     [rsp+0D8h+var_B0], rcx; unsigned __int16 *
0x180016cdc  mov     dword ptr [rsp+0D8h+dwNumberOfBytesToMap], 231h; int
0x180016ce4  xor     r9d, r9d; int
0x180016ce7  lea     r8, aD_1; "D"
0x180016cee  mov     edx, 90000h; int
0x180016cf3  mov     rcx, rax; int
0x180016cf6  call    WdsSetupLogMessageW
0x180016cfb  jmp     loc_180016F0C
0x180016d00  mov     rdi, [rsp+0D8h+arg_48]
0x180016d08  test    rdi, rdi
0x180016d0b  jz      short loc_180016D38
0x180016d0d  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016d14  mov     rax, [rcx]
0x180016d17  mov     rax, [rax]
0x180016d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d1f  cmp     eax, 0B7h
0x180016d24  jnz     short loc_180016D2E
0x180016d26  mov     dword ptr [rdi], 0
0x180016d2c  jmp     short loc_180016D38
0x180016d2e  mov     ecx, 1
0x180016d33  mov     [rdi], ecx
0x180016d35  mov     [rsi+34h], ecx
0x180016d38  mov     qword ptr [rsp+0D8h+FileSizeHigh], 0
0x180016d41  lea     rdx, [rsp+0D8h+FileSizeHigh+4]; lpFileSizeHigh
0x180016d46  mov     rcx, r13; hFile
0x180016d49  call    cs:__imp_GetFileSize
0x180016d50  nop     dword ptr [rax+rax+00h]
0x180016d55  mov     [rsp+0D8h+FileSizeHigh], eax
0x180016d59  cmp     eax, 0FFFFFFFFh
0x180016d5c  jz      loc_180016F0C
0x180016d62  cmp     qword ptr [rsp+0D8h+FileSizeHigh], 0
0x180016d68  jnz     loc_180016E5D
0x180016d6e  mov     qword ptr [rsp+0D8h+FileSizeHigh], rbx
0x180016d73  shl     rbx, 8
0x180016d77  mov     qword ptr [rsp+0D8h+FileSizeHigh], rbx
0x180016d7c  shr     rbx, 20h
0x180016d80  test    ebx, ebx
0x180016d82  jnz     loc_180016F0C
0x180016d88  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016d8f  mov     rax, [rcx]
0x180016d92  mov     r9d, [rsp+0D8h+var_68]
0x180016d97  or      r9d, [rsp+0D8h+arg_50]
0x180016d9f  mov     [rsp+0D8h+var_A8], 0
0x180016da8  mov     edx, [rsp+0D8h+FileSizeHigh]
0x180016dac  mov     dword ptr [rsp+0D8h+var_B0], edx
0x180016db0  mov     dword ptr [rsp+0D8h+dwNumberOfBytesToMap], ebx
0x180016db4  xor     r8d, r8d
0x180016db7  mov     rdx, r13
0x180016dba  mov     rax, [rax+250h]
0x180016dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc6  mov     r15, rax
0x180016dc9  mov     [rsp+0D8h+var_58], rax
0x180016dd1  mov     edi, [rsp+0D8h+dwDesiredAccess]
0x180016dd5  test    rax, rax
0x180016dd8  jz      loc_180016F10
0x180016dde  mov     ecx, [rsp+0D8h+FileSizeHigh]
0x180016de2  mov     [rsp+0D8h+dwNumberOfBytesToMap], rcx; dwNumberOfBytesToMap
0x180016de7  xor     r9d, r9d; dwFileOffsetLow
0x180016dea  xor     r8d, r8d; dwFileOffsetHigh
0x180016ded  mov     edx, edi; dwDesiredAccess
0x180016def  mov     rcx, rax; hFileMappingObject
0x180016df2  call    cs:__imp_MapViewOfFile
0x180016df9  nop     dword ptr [rax+rax+00h]
0x180016dfe  mov     r14, rax
0x180016e01  mov     [rsp+0D8h+var_60], rax
0x180016e06  test    rax, rax
0x180016e09  jz      loc_180016F10
0x180016e0f  mov     r8d, [rsp+0D8h+FileSizeHigh]; Size
0x180016e14  xor     edx, edx; Val
0x180016e16  mov     rcx, rax; void *
0x180016e19  call    memset_0
0x180016e1e  mov     rcx, r14; lpBaseAddress
0x180016e21  call    cs:__imp_UnmapViewOfFile
0x180016e28  nop     dword ptr [rax+rax+00h]
0x180016e2d  mov     [rsp+0D8h+var_60], 0
0x180016e36  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016e3d  mov     rax, [rcx]
0x180016e40  mov     rdx, r15
0x180016e43  mov     rax, [rax+0C8h]
0x180016e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e4f  mov     [rsp+0D8h+var_58], 0
0x180016e5b  jmp     short loc_180016E61
0x180016e5d  mov     edi, [rsp+0D8h+dwDesiredAccess]
0x180016e61  mov     [rsp+0D8h+arg_38], 0
0x180016e6c  lea     rcx, [rsi+60h]; this
0x180016e70  lea     r9, [rsp+0D8h+arg_38]; int *
0x180016e78  mov     r8d, 100h; unsigned __int64
0x180016e7e  mov     rdx, [rsp+0D8h+arg_18]; unsigned __int16 *
0x180016e86  call    ?Open@CBBSharedMemory@@QEAAHPEBG_KPEAH@Z; CBBSharedMemory::Open(ushort const *,unsigned __int64,int *)
0x180016e8b  test    eax, eax
0x180016e8d  jz      short loc_180016EF7
0x180016e8f  mov     rax, [rsi+68h]
0x180016e93  mov     [rsi+8], rax
0x180016e97  cmp     [rsp+0D8h+arg_38], 0
0x180016e9f  jnz     short loc_180016ED9
0x180016ea1  mov     rcx, [rsi+8]
0x180016ea5  mov     rax, qword ptr [rsp+0D8h+FileSizeHigh]
0x180016eaa  mov     [rcx], rax
0x180016ead  mov     rax, [rsi+8]
0x180016eb1  mov     dword ptr [rax+14h], 0
0x180016eb8  mov     rax, [rsi+8]
0x180016ebc  mov     dword ptr [rax+8], 0
0x180016ec3  mov     rax, [rsi+8]
0x180016ec7  mov     dword ptr [rax+10h], 0
0x180016ece  mov     rax, [rsi+8]
0x180016ed2  mov     dword ptr [rax+0Ch], 0
0x180016ed9  mov     ebx, 1
0x180016ede  mov     [rsp+0D8h+var_78], ebx
0x180016ee2  xor     r15d, r15d
0x180016ee5  mov     [rsp+0D8h+var_58], r15
0x180016eed  xor     r14d, r14d
0x180016ef0  mov     [rsp+0D8h+var_60], r14
0x180016ef5  jmp     short loc_180016F14
0x180016ef7  xor     r15d, r15d
0x180016efa  mov     [rsp+0D8h+var_58], r15
0x180016f02  xor     r14d, r14d
0x180016f05  mov     [rsp+0D8h+var_60], r14
0x180016f0a  jmp     short loc_180016F10
0x180016f0c  mov     edi, [rsp+0D8h+dwDesiredAccess]
0x180016f10  mov     ebx, [rsp+0D8h+var_78]
0x180016f14  test    r15, r15
0x180016f17  jz      short loc_180016F46
0x180016f19  test    r14, r14
0x180016f1c  jz      short loc_180016F2D
0x180016f1e  mov     rcx, r14; lpBaseAddress
0x180016f21  call    cs:__imp_UnmapViewOfFile
0x180016f28  nop     dword ptr [rax+rax+00h]
0x180016f2d  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016f34  mov     rax, [rcx]
0x180016f37  mov     rdx, r15
0x180016f3a  mov     rax, [rax+0C8h]
0x180016f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f46  test    ebx, ebx
0x180016f48  jz      short loc_180016F9A
0x180016f4a  mov     [rsi+20h], r12
0x180016f4e  mov     [rsi+10h], r13
0x180016f52  mov     rax, [rsi]
0x180016f55  mov     rcx, rsi
0x180016f58  mov     rax, [rax+48h]
0x180016f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f61  mov     [rsi+28h], rax
0x180016f65  cmp     dword ptr [rsi+34h], 0
0x180016f69  jnz     short loc_180016F7A
0x180016f6b  mov     rcx, r12; hMutex
0x180016f6e  call    cs:__imp_ReleaseMutex
0x180016f75  nop     dword ptr [rax+rax+00h]
0x180016f7a  mov     eax, [rsp+0D8h+arg_50]
0x180016f81  mov     [rsi+38h], eax
0x180016f84  mov     eax, [rsp+0D8h+var_68]
0x180016f88  mov     [rsi+40h], eax
0x180016f8b  mov     [rsi+44h], edi
0x180016f8e  mov     eax, [rsp+0D8h+arg_20]
0x180016f95  mov     [rsi+48h], eax
0x180016f98  jmp     short loc_180016FEF
0x180016f9a  lea     rcx, [rsi+60h]; this
0x180016f9e  call    ?Close@CBBSharedMemory@@QEAAXXZ; CBBSharedMemory::Close(void)
0x180016fa3  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180016fa7  jz      short loc_180016FC2
0x180016fa9  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016fb0  mov     rax, [rcx]
0x180016fb3  mov     rdx, r13
0x180016fb6  mov     rax, [rax+0C8h]
0x180016fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc2  test    r12, r12
0x180016fc5  jz      short loc_180016FEF
0x180016fc7  mov     rcx, r12; hMutex
0x180016fca  call    cs:__imp_ReleaseMutex
0x180016fd1  nop     dword ptr [rax+rax+00h]
0x180016fd6  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180016fdd  mov     rdx, [rcx]
0x180016fe0  mov     rax, [rdx+0C8h]
0x180016fe7  mov     rdx, r12
0x180016fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fef  mov     eax, ebx
0x180016ff1  add     rsp, 0A0h
0x180016ff8  pop     r15
0x180016ffa  pop     r14
0x180016ffc  pop     r13
0x180016ffe  pop     r12
0x180017000  pop     rdi
0x180017001  pop     rsi
0x180017002  pop     rbx
0x180017003  retn
0x180028da4  push    rbx
0x180028da6  push    rbp
0x180028da7  push    rdi
0x180028da8  sub     rsp, 60h
0x180028dac  mov     rbp, rdx
0x180028daf  mov     rbx, [rbp+80h]
0x180028db6  test    rbx, rbx
0x180028db9  jz      short loc_180028DFC
0x180028dbb  mov     rcx, [rbp+78h]; lpBaseAddress
0x180028dbf  test    rcx, rcx
0x180028dc2  jz      short loc_180028DD8
  ... truncated ...
```
