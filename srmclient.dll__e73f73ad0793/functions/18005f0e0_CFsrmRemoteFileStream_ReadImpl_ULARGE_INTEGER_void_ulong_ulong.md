# CFsrmRemoteFileStream::ReadImpl(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x18005f0e0`
- end: `0x18005f494`
- name: `?ReadImpl@CFsrmRemoteFileStream@@AEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `948`
- prototype: `int(CFsrmRemoteFileStream *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18005f020`
- `0x18005f0b0`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18005f0e0`
- `0x18005fe48`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18005f27d`
- `KERNEL32!ReadFile` at `0x18005f27d`
- `KERNEL32!GetLastError` at `0x18005f287`
- `KERNEL32!GetLastError` at `0x18005f287`
- `KERNEL32!GetOverlappedResult` at `0x18005f2c0`
- `KERNEL32!GetOverlappedResult` at `0x18005f2c0`
- `KERNEL32!GetCurrentThread` at `0x18005f1cb`
- `KERNEL32!GetCurrentThread` at `0x18005f313`
- `KERNEL32!GetCurrentThread` at `0x18005f1cb`
- `KERNEL32!GetCurrentThread` at `0x18005f313`
- `KERNEL32!WaitForSingleObject` at `0x18005f24c`
- `KERNEL32!WaitForSingleObject` at `0x18005f24c`
- `KERNEL32!SetThreadPriority` at `0x18005f1d9`
- `KERNEL32!SetThreadPriority` at `0x18005f321`
- `KERNEL32!SetThreadPriority` at `0x18005f1d9`
- `KERNEL32!SetThreadPriority` at `0x18005f321`

## string_xrefs

- `0x18005f12e`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18005f13c`: `CFsrmRemoteFileStream::ReadImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsrmRemoteFileStream::ReadImpl(
        CFsrmRemoteFileStream *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        DWORD a4,
        unsigned int *a5)
{
  DWORD LowPart; // ebx
  DWORD HighPart; // r12d
  HANDLE CurrentThread; // rax
  void *v11; // rcx
  signed int LastError; // eax
  void *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  HANDLE v16; // rax
  unsigned int v17; // ebx
  char Hr; // al
  char v20; // al
  char v21; // al
  int LastFailureAsHRESULT; // eax
  char v23; // al
  int v24; // eax
  char v25; // al
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-1D8h] BYREF
  _BYTE *v27; // [rsp+48h] [rbp-1D0h]
  int v28; // [rsp+50h] [rbp-1C8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-1C0h] BYREF
  _com_error *v30; // [rsp+78h] [rbp-1A0h] BYREF
  const exception *v31; // [rsp+80h] [rbp-198h] BYREF
  _QWORD v32[3]; // [rsp+88h] [rbp-190h] BYREF
  int v33; // [rsp+A0h] [rbp-178h]
  int v34; // [rsp+A4h] [rbp-174h]
  int v35; // [rsp+A8h] [rbp-170h]
  _DWORD v36[28]; // [rsp+B0h] [rbp-168h] BYREF
  void **v37; // [rsp+120h] [rbp-F8h] BYREF
  signed int v38; // [rsp+128h] [rbp-F0h]
  unsigned int v39; // [rsp+14Ch] [rbp-CCh]

  LowPart = a2.LowPart;
  HighPart = a2.HighPart;
  v27 = v32;
  v32[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v32[1] = L"CFsrmRemoteFileStream::ReadImpl";
  v32[2] = L"STREAMLC";
  v33 = 1627;
  v34 = 26;
  v35 = 255;
  v36[24] = 0x1000000;
  memset_0(v36, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v37, (const struct CSrmDebugInfo *)v32, 0);
  if ( a5 )
    *a5 = 0;
  v27 = (char *)this + 128;
  if ( *((_BYTE *)this + 128) )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  try
  {
    if ( !a3 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v37, -2147024809);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v37, 0x666u, Hr, 0);
    }
    v38 = 0;
    if ( *((_QWORD *)this + 9) == -1 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v37, -2147024809);
      v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v37, 0x667u, v20, 0);
    }
    v38 = 0;
    *(_OWORD *)&Overlapped.Internal = 0;
    Overlapped.hEvent = 0;
    Overlapped.Pointer = (PVOID)__PAIR64__(HighPart, LowPart);
    Overlapped.hEvent = (HANDLE)*((_QWORD *)this + 13);
    NumberOfBytesRead = 0;
    v38 = 0;
    v11 = (void *)*((_QWORD *)this + 11);
    if ( v11 && WaitForSingleObject(v11, 0) != 258 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v37, -2147200134);
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v37, 0x671u, v21, 0);
    }
    v38 = 0;
    if ( !ReadFile(*((HANDLE *)this + 9), a3, a4, &NumberOfBytesRead, &Overlapped) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        CFsrmRemoteFileStream::WaitForCompletion(v13, *((void **)this + 13), *((void **)this + 11));
        if ( !GetOverlappedResult(*((HANDLE *)this + 9), &Overlapped, &NumberOfBytesRead, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15, v14);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v37, LastFailureAsHRESULT);
          v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v37, 0x67Eu, v23, 0);
        }
        v38 = 0;
      }
      else
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v38 = LastError;
        if ( LastError < 0 )
        {
          v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v37, v24);
          v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v37);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v37, 0x682u, v25, 0);
        }
        v38 = LastError;
      }
    }
    if ( a5 )
      *a5 = NumberOfBytesRead;
  }
  catch ( long v28 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v37,
      v28,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::ReadImpl",
      0x68Bu,
      v39);
  }
  catch ( _com_error *v30 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v37,
      v30,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::ReadImpl",
      0x68Bu,
      v39);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v37,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::ReadImpl",
      0x68Bu,
      v39);
  }
  catch ( const exception *v31 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v37,
      v31,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::ReadImpl",
      0x68Bu,
      v39);
  }
  if ( *v27 )
  {
    v16 = GetCurrentThread();
    SetThreadPriority(v16, 0x20000);
  }
  v17 = v38;
  v37 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v37);
  return v17;
}

```

## disassembly

```asm
0x18005f0e0  mov     r11, rsp
0x18005f0e3  push    rbx
0x18005f0e4  push    rsi
0x18005f0e5  push    rdi
0x18005f0e6  push    r12
0x18005f0e8  push    r13
0x18005f0ea  push    r14
0x18005f0ec  push    r15
0x18005f0ee  sub     rsp, 1E0h
0x18005f0f5  mov     rax, cs:__security_cookie
0x18005f0fc  xor     rax, rsp
0x18005f0ff  mov     [rsp+218h+var_48], rax
0x18005f107  mov     r13d, r9d
0x18005f10a  mov     r15, r8
0x18005f10d  mov     rbx, rdx
0x18005f110  mov     rsi, rcx
0x18005f113  mov     r12, rdx
0x18005f116  shr     r12, 20h
0x18005f11a  mov     r14, [rsp+218h+arg_20]
0x18005f122  lea     rax, [r11-190h]
0x18005f129  mov     [rsp+218h+var_1D0], rax
0x18005f12e  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005f135  mov     [r11-190h], rax
0x18005f13c  lea     rax, aCfsrmremotefil; "CFsrmRemoteFileStream::ReadImpl"
0x18005f143  mov     [r11-188h], rax
0x18005f14a  lea     rax, aStreamlc; "STREAMLC"
0x18005f151  mov     [r11-180h], rax
0x18005f158  mov     [rsp+218h+var_178], 65Bh
0x18005f163  mov     [rsp+218h+var_174], 1Ah
0x18005f16e  mov     [rsp+218h+var_170], 0FFh
0x18005f179  xor     edi, edi
0x18005f17b  mov     [rsp+218h+var_108], 1000000h
0x18005f186  xor     edx, edx; Val
0x18005f188  lea     r8d, [rdi+60h]; Size
0x18005f18c  lea     rcx, [r11-168h]; void *
0x18005f193  call    memset_0
0x18005f198  nop
0x18005f199  xor     r8d, r8d
0x18005f19c  lea     rdx, [rsp+218h+var_190]
0x18005f1a4  lea     rcx, [rsp+218h+var_F8]
0x18005f1ac  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005f1b1  nop
0x18005f1b2  test    r14, r14
0x18005f1b5  jz      short loc_18005F1BA
0x18005f1b7  mov     [r14], edi
0x18005f1ba  lea     rax, [rsi+80h]
0x18005f1c1  mov     [rsp+218h+var_1D0], rax
0x18005f1c6  cmp     [rax], dil
0x18005f1c9  jz      short loc_18005F1E0
0x18005f1cb  call    cs:__imp_GetCurrentThread
0x18005f1d1  mov     rcx, rax; hThread
0x18005f1d4  mov     edx, 10000h; nPriority
0x18005f1d9  call    cs:__imp_SetThreadPriority
0x18005f1df  nop
0x18005f1e0  mov     eax, [rsp+218h+var_F0]
0x18005f1e7  mov     [rsp+218h+var_F0], eax
0x18005f1ee  test    r15, r15
0x18005f1f1  jz      loc_18005F373
0x18005f1f7  mov     [rsp+218h+var_F0], edi
0x18005f1fe  mov     [rsp+218h+var_F0], edi
0x18005f205  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x18005f20a  jz      loc_18005F3AA
0x18005f210  mov     [rsp+218h+var_F0], edi
0x18005f217  xorps   xmm0, xmm0
0x18005f21a  movups  xmmword ptr [rsp+218h+Overlapped.Internal], xmm0
0x18005f21f  movups  xmmword ptr [rsp+218h+Overlapped.10h], xmm0
0x18005f224  mov     dword ptr [rsp+218h+Overlapped.10h], ebx
0x18005f228  mov     dword ptr [rsp+218h+Overlapped.10h+4], r12d
0x18005f22d  mov     rax, [rsi+68h]
0x18005f231  mov     [rsp+218h+Overlapped.hEvent], rax
0x18005f236  mov     [rsp+218h+NumberOfBytesRead], edi
0x18005f23a  mov     [rsp+218h+var_F0], edi
0x18005f241  mov     rcx, [rsi+58h]; hHandle
0x18005f245  test    rcx, rcx
0x18005f248  jz      short loc_18005F25D
0x18005f24a  xor     edx, edx; dwMilliseconds
0x18005f24c  call    cs:__imp_WaitForSingleObject
0x18005f252  cmp     eax, 102h
0x18005f257  jnz     loc_18005F3E1
0x18005f25d  mov     [rsp+218h+var_F0], edi
0x18005f264  lea     rax, [rsp+218h+Overlapped]
0x18005f269  mov     [rsp+218h+lpOverlapped], rax; lpOverlapped
0x18005f26e  lea     r9, [rsp+218h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005f273  mov     r8d, r13d; nNumberOfBytesToRead
0x18005f276  mov     rdx, r15; lpBuffer
0x18005f279  mov     rcx, [rsi+48h]; hFile
0x18005f27d  call    cs:__imp_ReadFile
0x18005f283  test    eax, eax
0x18005f285  jnz     short loc_18005F2F9
0x18005f287  call    cs:__imp_GetLastError
0x18005f28d  cmp     eax, 3E5h
0x18005f292  jnz     short loc_18005F2D7
0x18005f294  mov     r8, [rsi+58h]; void *
0x18005f298  mov     rdx, [rsi+68h]; void *
0x18005f29c  call    ?WaitForCompletion@CFsrmRemoteFileStream@@CAXPEAX00@Z; CFsrmRemoteFileStream::WaitForCompletion(void *,void *,void *)
0x18005f2a1  mov     eax, [rsp+218h+var_F0]
0x18005f2a8  mov     [rsp+218h+var_F0], eax
0x18005f2af  xor     r9d, r9d; bWait
0x18005f2b2  lea     r8, [rsp+218h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x18005f2b7  lea     rdx, [rsp+218h+Overlapped]; lpOverlapped
0x18005f2bc  mov     rcx, [rsi+48h]; hFile
0x18005f2c0  call    cs:__imp_GetOverlappedResult
0x18005f2c6  test    eax, eax
0x18005f2c8  jz      loc_18005F418
0x18005f2ce  mov     [rsp+218h+var_F0], edi
0x18005f2d5  jmp     short loc_18005F2F9
0x18005f2d7  test    eax, eax
0x18005f2d9  jle     short loc_18005F2E3
0x18005f2db  movzx   eax, ax
0x18005f2de  or      eax, 80070000h
0x18005f2e3  mov     [rsp+218h+var_F0], eax
0x18005f2ea  test    eax, eax
0x18005f2ec  js      loc_18005F451
0x18005f2f2  mov     [rsp+218h+var_F0], eax
0x18005f2f9  test    r14, r14
0x18005f2fc  jz      short loc_18005F305
0x18005f2fe  mov     eax, [rsp+218h+NumberOfBytesRead]
0x18005f302  mov     [r14], eax
0x18005f305  jmp     short loc_18005F309
0x18005f307  xor     edi, edi
0x18005f309  mov     rax, [rsp+218h+var_1D0]
0x18005f30e  cmp     [rax], dil
0x18005f311  jz      short loc_18005F327
0x18005f313  call    cs:__imp_GetCurrentThread
0x18005f319  mov     rcx, rax; hThread
0x18005f31c  mov     edx, 20000h; nPriority
0x18005f321  call    cs:__imp_SetThreadPriority
0x18005f327  mov     ebx, [rsp+218h+var_F0]
0x18005f32e  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005f335  mov     [rsp+218h+var_F8], rax
0x18005f33d  lea     rcx, [rsp+218h+var_F8]; this
0x18005f345  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005f34a  mov     eax, ebx
0x18005f34c  mov     rcx, [rsp+218h+var_48]
0x18005f354  xor     rcx, rsp; StackCookie
0x18005f357  call    __security_check_cookie
0x18005f35c  add     rsp, 1E0h
0x18005f363  pop     r15
0x18005f365  pop     r14
0x18005f367  pop     r13
0x18005f369  pop     r12
0x18005f36b  pop     rdi
0x18005f36c  pop     rsi
0x18005f36d  pop     rbx
0x18005f36e  retn
0x18005f36f  jmp     short loc_18005F307
0x18005f371  jmp     short loc_18005F307
0x18005f373  mov     edx, 80070057h; int
0x18005f378  lea     rcx, [rsp+218h+var_F8]; this
0x18005f380  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005f385  lea     rcx, [rsp+218h+var_F8]; this
0x18005f38d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f392  mov     r8d, eax; char
0x18005f395  xor     r9d, r9d; unsigned __int16 *
0x18005f398  mov     edx, 666h; unsigned int
0x18005f39d  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3a5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005f3aa  mov     edx, 80070057h; int
0x18005f3af  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3b7  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005f3bc  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3c4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f3c9  mov     r8d, eax; char
0x18005f3cc  xor     r9d, r9d; unsigned __int16 *
0x18005f3cf  mov     edx, 667h; unsigned int
0x18005f3d4  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3dc  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005f3e1  mov     edx, 8004537Ah; int
0x18005f3e6  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3ee  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005f3f3  lea     rcx, [rsp+218h+var_F8]; this
0x18005f3fb  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f400  mov     r8d, eax; char
0x18005f403  xor     r9d, r9d; unsigned __int16 *
0x18005f406  mov     edx, 671h; unsigned int
0x18005f40b  lea     rcx, [rsp+218h+var_F8]; this
0x18005f413  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005f418  call    GetLastFailureAsHRESULT
0x18005f41d  mov     edx, eax; int
0x18005f41f  lea     rcx, [rsp+218h+var_F8]; this
0x18005f427  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005f42c  lea     rcx, [rsp+218h+var_F8]; this
0x18005f434  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f439  mov     r8d, eax; char
0x18005f43c  xor     r9d, r9d; unsigned __int16 *
0x18005f43f  mov     edx, 67Eh; unsigned int
0x18005f444  lea     rcx, [rsp+218h+var_F8]; this
0x18005f44c  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005f451  lea     rcx, [rsp+218h+var_F8]; this
0x18005f459  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f45e  mov     edx, eax; int
0x18005f460  lea     rcx, [rsp+218h+var_F8]; this
0x18005f468  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005f46d  lea     rcx, [rsp+218h+var_F8]; this
0x18005f475  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005f47a  mov     r8d, eax; char
0x18005f47d  xor     r9d, r9d; unsigned __int16 *
0x18005f480  mov     edx, 682h; unsigned int
0x18005f485  lea     rcx, [rsp+218h+var_F8]; this
0x18005f48d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
