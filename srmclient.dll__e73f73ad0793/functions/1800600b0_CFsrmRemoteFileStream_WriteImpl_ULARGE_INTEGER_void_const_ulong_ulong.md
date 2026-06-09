# CFsrmRemoteFileStream::WriteImpl(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x1800600b0`
- end: `0x1800604b3`
- name: `?WriteImpl@CFsrmRemoteFileStream@@AEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `1027`
- prototype: `int(CFsrmRemoteFileStream *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180060030`
- `0x1800600a0`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18005fe48`
- `0x1800600b0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180060265`
- `KERNEL32!WriteFile` at `0x180060265`
- `KERNEL32!GetLastError` at `0x18006026f`
- `KERNEL32!GetLastError` at `0x18006026f`
- `KERNEL32!GetOverlappedResult` at `0x1800602a8`
- `KERNEL32!GetOverlappedResult` at `0x1800602a8`
- `KERNEL32!GetCurrentThread` at `0x18006019b`
- `KERNEL32!GetCurrentThread` at `0x1800602fb`
- `KERNEL32!GetCurrentThread` at `0x18006019b`
- `KERNEL32!GetCurrentThread` at `0x1800602fb`
- `KERNEL32!WaitForSingleObject` at `0x180060234`
- `KERNEL32!WaitForSingleObject` at `0x180060234`
- `KERNEL32!SetThreadPriority` at `0x1800601a9`
- `KERNEL32!SetThreadPriority` at `0x180060309`
- `KERNEL32!SetThreadPriority` at `0x1800601a9`
- `KERNEL32!SetThreadPriority` at `0x180060309`

## string_xrefs

- `0x1800600fe`: `base\fs\fsrm\service\stream\streamlib.cpp`
- `0x18006010c`: `CFsrmRemoteFileStream::WriteImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsrmRemoteFileStream::WriteImpl(
        CFsrmRemoteFileStream *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
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
  char v22; // al
  int LastFailureAsHRESULT; // eax
  char v24; // al
  int v25; // eax
  char v26; // al
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1D8h] BYREF
  _BYTE *v28; // [rsp+48h] [rbp-1D0h]
  int v29; // [rsp+50h] [rbp-1C8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-1C0h] BYREF
  _com_error *v31; // [rsp+78h] [rbp-1A0h] BYREF
  const exception *v32; // [rsp+80h] [rbp-198h] BYREF
  _QWORD v33[3]; // [rsp+88h] [rbp-190h] BYREF
  int v34; // [rsp+A0h] [rbp-178h]
  int v35; // [rsp+A4h] [rbp-174h]
  int v36; // [rsp+A8h] [rbp-170h]
  _DWORD v37[28]; // [rsp+B0h] [rbp-168h] BYREF
  void **v38; // [rsp+120h] [rbp-F8h] BYREF
  signed int v39; // [rsp+128h] [rbp-F0h]
  unsigned int v40; // [rsp+14Ch] [rbp-CCh]

  LowPart = a2.LowPart;
  HighPart = a2.HighPart;
  v28 = v33;
  v33[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v33[1] = L"CFsrmRemoteFileStream::WriteImpl";
  v33[2] = L"STREAMLC";
  v34 = 1692;
  v35 = 26;
  v36 = 255;
  v37[24] = 0x1000000;
  memset_0(v37, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v38, (const struct CSrmDebugInfo *)v33, 0);
  if ( a5 )
    *a5 = 0;
  v28 = (char *)this + 128;
  if ( *((_BYTE *)this + 128) )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  try
  {
    if ( !a3 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, -2147024809);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6A7u, Hr, 0);
    }
    v39 = 0;
    if ( *((_QWORD *)this + 9) == -1 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, -2147024809);
      v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6A8u, v20, 0);
    }
    v39 = 0;
    if ( *((_DWORD *)this + 28) != 2 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, -2147024891);
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6A9u, v21, 0);
    }
    v39 = 0;
    *(_OWORD *)&Overlapped.Internal = 0;
    Overlapped.hEvent = 0;
    Overlapped.Pointer = (PVOID)__PAIR64__(HighPart, LowPart);
    Overlapped.hEvent = (HANDLE)*((_QWORD *)this + 13);
    NumberOfBytesWritten = 0;
    v39 = 0;
    v11 = (void *)*((_QWORD *)this + 11);
    if ( v11 && WaitForSingleObject(v11, 0) != 258 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, -2147200134);
      v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6B3u, v22, 0);
    }
    v39 = 0;
    if ( !WriteFile(*((HANDLE *)this + 9), a3, a4, &NumberOfBytesWritten, &Overlapped) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        CFsrmRemoteFileStream::WaitForCompletion(v13, *((void **)this + 13), *((void **)this + 11));
        if ( !GetOverlappedResult(*((HANDLE *)this + 9), &Overlapped, &NumberOfBytesWritten, 0) )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15, v14);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, LastFailureAsHRESULT);
          v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6BCu, v24, 0);
        }
        v39 = 0;
      }
      else
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v39 = LastError;
        if ( LastError < 0 )
        {
          v25 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
          CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v38, v25);
          v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v38);
          CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v38, 0x6C0u, v26, 0);
        }
        v39 = LastError;
      }
    }
    if ( a5 )
      *a5 = NumberOfBytesWritten;
  }
  catch ( long v29 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v38,
      v29,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::WriteImpl",
      0x6C9u,
      v40);
  }
  catch ( _com_error *v31 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v38,
      v31,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::WriteImpl",
      0x6C9u,
      v40);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v38,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::WriteImpl",
      0x6C9u,
      v40);
  }
  catch ( const exception *v32 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v38,
      v32,
      L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
      L"STREAMLC",
      L"CFsrmRemoteFileStream::WriteImpl",
      0x6C9u,
      v40);
  }
  if ( *v28 )
  {
    v16 = GetCurrentThread();
    SetThreadPriority(v16, 0x20000);
  }
  v17 = v39;
  v38 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v38);
  return v17;
}

```

## disassembly

```asm
0x1800600b0  mov     r11, rsp
0x1800600b3  push    rbx
0x1800600b4  push    rsi
0x1800600b5  push    rdi
0x1800600b6  push    r12
0x1800600b8  push    r13
0x1800600ba  push    r14
0x1800600bc  push    r15
0x1800600be  sub     rsp, 1E0h
0x1800600c5  mov     rax, cs:__security_cookie
0x1800600cc  xor     rax, rsp
0x1800600cf  mov     [rsp+218h+var_48], rax
0x1800600d7  mov     r13d, r9d
0x1800600da  mov     r15, r8
0x1800600dd  mov     rbx, rdx
0x1800600e0  mov     rsi, rcx
0x1800600e3  mov     r12, rdx
0x1800600e6  shr     r12, 20h
0x1800600ea  mov     r14, [rsp+218h+arg_20]
0x1800600f2  lea     rax, [r11-190h]
0x1800600f9  mov     [rsp+218h+var_1D0], rax
0x1800600fe  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x180060105  mov     [r11-190h], rax
0x18006010c  lea     rax, aCfsrmremotefil_4; "CFsrmRemoteFileStream::WriteImpl"
0x180060113  mov     [r11-188h], rax
0x18006011a  lea     rax, aStreamlc; "STREAMLC"
0x180060121  mov     [r11-180h], rax
0x180060128  mov     [rsp+218h+var_178], 69Ch
0x180060133  mov     [rsp+218h+var_174], 1Ah
0x18006013e  mov     [rsp+218h+var_170], 0FFh
0x180060149  xor     edi, edi
0x18006014b  mov     [rsp+218h+var_108], 1000000h
0x180060156  xor     edx, edx; Val
0x180060158  lea     r8d, [rdi+60h]; Size
0x18006015c  lea     rcx, [r11-168h]; void *
0x180060163  call    memset_0
0x180060168  nop
0x180060169  xor     r8d, r8d
0x18006016c  lea     rdx, [rsp+218h+var_190]
0x180060174  lea     rcx, [rsp+218h+var_F8]
0x18006017c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180060181  nop
0x180060182  test    r14, r14
0x180060185  jz      short loc_18006018A
0x180060187  mov     [r14], edi
0x18006018a  lea     rax, [rsi+80h]
0x180060191  mov     [rsp+218h+var_1D0], rax
0x180060196  cmp     [rax], dil
0x180060199  jz      short loc_1800601B0
0x18006019b  call    cs:__imp_GetCurrentThread
0x1800601a1  mov     rcx, rax; hThread
0x1800601a4  mov     edx, 10000h; nPriority
0x1800601a9  call    cs:__imp_SetThreadPriority
0x1800601af  nop
0x1800601b0  mov     eax, [rsp+218h+var_F0]
0x1800601b7  mov     [rsp+218h+var_F0], eax
0x1800601be  test    r15, r15
0x1800601c1  jz      loc_18006035B
0x1800601c7  mov     [rsp+218h+var_F0], edi
0x1800601ce  mov     [rsp+218h+var_F0], edi
0x1800601d5  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1800601da  jz      loc_180060392
0x1800601e0  mov     [rsp+218h+var_F0], edi
0x1800601e7  mov     [rsp+218h+var_F0], edi
0x1800601ee  cmp     dword ptr [rsi+70h], 2
0x1800601f2  jnz     loc_1800603C9
0x1800601f8  mov     [rsp+218h+var_F0], edi
0x1800601ff  xorps   xmm0, xmm0
0x180060202  movups  xmmword ptr [rsp+218h+Overlapped.Internal], xmm0
0x180060207  movups  xmmword ptr [rsp+218h+Overlapped.10h], xmm0
0x18006020c  mov     dword ptr [rsp+218h+Overlapped.10h], ebx
0x180060210  mov     dword ptr [rsp+218h+Overlapped.10h+4], r12d
0x180060215  mov     rax, [rsi+68h]
0x180060219  mov     [rsp+218h+Overlapped.hEvent], rax
0x18006021e  mov     [rsp+218h+NumberOfBytesWritten], edi
0x180060222  mov     [rsp+218h+var_F0], edi
0x180060229  mov     rcx, [rsi+58h]; hHandle
0x18006022d  test    rcx, rcx
0x180060230  jz      short loc_180060245
0x180060232  xor     edx, edx; dwMilliseconds
0x180060234  call    cs:__imp_WaitForSingleObject
0x18006023a  cmp     eax, 102h
0x18006023f  jnz     loc_180060400
0x180060245  mov     [rsp+218h+var_F0], edi
0x18006024c  lea     rax, [rsp+218h+Overlapped]
0x180060251  mov     [rsp+218h+lpOverlapped], rax; lpOverlapped
0x180060256  lea     r9, [rsp+218h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006025b  mov     r8d, r13d; nNumberOfBytesToWrite
0x18006025e  mov     rdx, r15; lpBuffer
0x180060261  mov     rcx, [rsi+48h]; hFile
0x180060265  call    cs:__imp_WriteFile
0x18006026b  test    eax, eax
0x18006026d  jnz     short loc_1800602E1
0x18006026f  call    cs:__imp_GetLastError
0x180060275  cmp     eax, 3E5h
0x18006027a  jnz     short loc_1800602BF
0x18006027c  mov     r8, [rsi+58h]; void *
0x180060280  mov     rdx, [rsi+68h]; void *
0x180060284  call    ?WaitForCompletion@CFsrmRemoteFileStream@@CAXPEAX00@Z; CFsrmRemoteFileStream::WaitForCompletion(void *,void *,void *)
0x180060289  mov     eax, [rsp+218h+var_F0]
0x180060290  mov     [rsp+218h+var_F0], eax
0x180060297  xor     r9d, r9d; bWait
0x18006029a  lea     r8, [rsp+218h+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x18006029f  lea     rdx, [rsp+218h+Overlapped]; lpOverlapped
0x1800602a4  mov     rcx, [rsi+48h]; hFile
0x1800602a8  call    cs:__imp_GetOverlappedResult
0x1800602ae  test    eax, eax
0x1800602b0  jz      loc_180060437
0x1800602b6  mov     [rsp+218h+var_F0], edi
0x1800602bd  jmp     short loc_1800602E1
0x1800602bf  test    eax, eax
0x1800602c1  jle     short loc_1800602CB
0x1800602c3  movzx   eax, ax
0x1800602c6  or      eax, 80070000h
0x1800602cb  mov     [rsp+218h+var_F0], eax
0x1800602d2  test    eax, eax
0x1800602d4  js      loc_180060470
0x1800602da  mov     [rsp+218h+var_F0], eax
0x1800602e1  test    r14, r14
0x1800602e4  jz      short loc_1800602ED
0x1800602e6  mov     eax, [rsp+218h+NumberOfBytesWritten]
0x1800602ea  mov     [r14], eax
0x1800602ed  jmp     short loc_1800602F1
0x1800602ef  xor     edi, edi
0x1800602f1  mov     rax, [rsp+218h+var_1D0]
0x1800602f6  cmp     [rax], dil
0x1800602f9  jz      short loc_18006030F
0x1800602fb  call    cs:__imp_GetCurrentThread
0x180060301  mov     rcx, rax; hThread
0x180060304  mov     edx, 20000h; nPriority
0x180060309  call    cs:__imp_SetThreadPriority
0x18006030f  mov     ebx, [rsp+218h+var_F0]
0x180060316  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18006031d  mov     [rsp+218h+var_F8], rax
0x180060325  lea     rcx, [rsp+218h+var_F8]; this
0x18006032d  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180060332  mov     eax, ebx
0x180060334  mov     rcx, [rsp+218h+var_48]
0x18006033c  xor     rcx, rsp; StackCookie
0x18006033f  call    __security_check_cookie
0x180060344  add     rsp, 1E0h
0x18006034b  pop     r15
0x18006034d  pop     r14
0x18006034f  pop     r13
0x180060351  pop     r12
0x180060353  pop     rdi
0x180060354  pop     rsi
0x180060355  pop     rbx
0x180060356  retn
0x180060357  jmp     short loc_1800602EF
0x180060359  jmp     short loc_1800602EF
0x18006035b  mov     edx, 80070057h; int
0x180060360  lea     rcx, [rsp+218h+var_F8]; this
0x180060368  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18006036d  lea     rcx, [rsp+218h+var_F8]; this
0x180060375  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006037a  mov     r8d, eax; char
0x18006037d  xor     r9d, r9d; unsigned __int16 *
0x180060380  mov     edx, 6A7h; unsigned int
0x180060385  lea     rcx, [rsp+218h+var_F8]; this
0x18006038d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180060392  mov     edx, 80070057h; int
0x180060397  lea     rcx, [rsp+218h+var_F8]; this
0x18006039f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800603a4  lea     rcx, [rsp+218h+var_F8]; this
0x1800603ac  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800603b1  mov     r8d, eax; char
0x1800603b4  xor     r9d, r9d; unsigned __int16 *
0x1800603b7  mov     edx, 6A8h; unsigned int
0x1800603bc  lea     rcx, [rsp+218h+var_F8]; this
0x1800603c4  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800603c9  mov     edx, 80070005h; int
0x1800603ce  lea     rcx, [rsp+218h+var_F8]; this
0x1800603d6  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800603db  lea     rcx, [rsp+218h+var_F8]; this
0x1800603e3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800603e8  mov     r8d, eax; char
0x1800603eb  xor     r9d, r9d; unsigned __int16 *
0x1800603ee  mov     edx, 6A9h; unsigned int
0x1800603f3  lea     rcx, [rsp+218h+var_F8]; this
0x1800603fb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180060400  mov     edx, 8004537Ah; int
0x180060405  lea     rcx, [rsp+218h+var_F8]; this
0x18006040d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180060412  lea     rcx, [rsp+218h+var_F8]; this
0x18006041a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006041f  mov     r8d, eax; char
0x180060422  xor     r9d, r9d; unsigned __int16 *
0x180060425  mov     edx, 6B3h; unsigned int
0x18006042a  lea     rcx, [rsp+218h+var_F8]; this
0x180060432  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180060437  call    GetLastFailureAsHRESULT
0x18006043c  mov     edx, eax; int
0x18006043e  lea     rcx, [rsp+218h+var_F8]; this
0x180060446  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18006044b  lea     rcx, [rsp+218h+var_F8]; this
0x180060453  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180060458  mov     r8d, eax; char
0x18006045b  xor     r9d, r9d; unsigned __int16 *
0x18006045e  mov     edx, 6BCh; unsigned int
0x180060463  lea     rcx, [rsp+218h+var_F8]; this
0x18006046b  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180060470  lea     rcx, [rsp+218h+var_F8]; this
0x180060478  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18006047d  mov     edx, eax; int
0x18006047f  lea     rcx, [rsp+218h+var_F8]; this
0x180060487  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18006048c  lea     rcx, [rsp+218h+var_F8]; this
0x180060494  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180060499  mov     r8d, eax; char
0x18006049c  xor     r9d, r9d; unsigned __int16 *
0x18006049f  mov     edx, 6C0h; unsigned int
0x1800604a4  lea     rcx, [rsp+218h+var_F8]; this
0x1800604ac  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
