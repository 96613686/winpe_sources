# WinSAT::StorageDevice::PerformIOs(void *,std::vector<WinSAT::StorageDevice::IODescriptor,std::allocator<WinSAT::StorageDevice::IODescriptor>> const &,unsigned __int64,double &,double &)

- ea: `0x140061b44`
- end: `0x140061f5a`
- name: `?PerformIOs@StorageDevice@WinSAT@@QEBA_NPEAXAEBV?$vector@UIODescriptor@StorageDevice@WinSAT@@V?$allocator@UIODescriptor@StorageDevice@WinSAT@@@std@@@std@@_KAEAN3@Z`
- size: `1046`
- prototype: `__int64 __usercall@<rax>(struct WinSAT::StorageDevice *@<rcx>, void *@<rdx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006bb04`
- `0x14006c0c8`
- `0x14006c494`
- `0x14006c890`

## callees

- `0x140004348`
- `0x140017af0`
- `0x14004fce4`
- `0x14004fe00`
- `0x140060520`
- `0x140060614`
- `0x140060738`
- `0x140060a7c`
- `0x140060b38`
- `0x140061b44`
- `0x140062234`
- `0x14006225c`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x140061ced`
- `KERNEL32!FlushFileBuffers` at `0x140061ced`
- `KERNEL32!QueryPerformanceCounter` at `0x140061bea`
- `KERNEL32!QueryPerformanceCounter` at `0x140061e27`
- `KERNEL32!QueryPerformanceCounter` at `0x140061e63`
- `KERNEL32!QueryPerformanceCounter` at `0x140061bea`
- `KERNEL32!QueryPerformanceCounter` at `0x140061e27`
- `KERNEL32!QueryPerformanceCounter` at `0x140061e63`
- `KERNEL32!GetLastError` at `0x140061d00`
- `KERNEL32!GetLastError` at `0x140061f1d`
- `KERNEL32!GetLastError` at `0x140061d00`
- `KERNEL32!GetLastError` at `0x140061f1d`
- `KERNEL32!SleepEx` at `0x140061efa`
- `KERNEL32!SleepEx` at `0x140061efa`
- `KERNEL32!ReadFileEx` at `0x140061cad`
- `KERNEL32!ReadFileEx` at `0x140061cad`
- `KERNEL32!WriteFileEx` at `0x140061cd9`
- `KERNEL32!WriteFileEx` at `0x140061cd9`
- `KERNEL32!CancelIo` at `0x140061ee5`
- `KERNEL32!CancelIo` at `0x140061ee5`
- `KERNEL32!VirtualFree` at `0x140061f17`
- `KERNEL32!VirtualFree` at `0x140061f17`
- `KERNEL32!QueryPerformanceFrequency` at `0x140061b9f`
- `KERNEL32!QueryPerformanceFrequency` at `0x140061b9f`
- `KERNEL32!SetLastError` at `0x140061e18`
- `KERNEL32!SetLastError` at `0x140061e18`

## string_xrefs

- `0x140061dc2`: `Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinSAT::StorageDevice::PerformIOs(
        struct WinSAT::StorageDevice *a1,
        void *a2,
        __int64 *a3,
        __int64 a4,
        double *a5,
        double *a6)
{
  void *v7; // rdi
  double LowPart; // xmm6_8
  __int64 v10; // rcx
  char v11; // r14
  DWORD v12; // r12d
  __int64 v13; // rbx
  unsigned int i; // eax
  struct _OVERLAPPED *v15; // r15
  int v16; // eax
  BOOL File; // eax
  DWORD LastError; // edi
  unsigned __int16 v19; // r9
  __int64 v20; // rdi
  const unsigned __int16 *v21; // rax
  __int64 *v22; // rax
  const unsigned __int16 *v23; // r9
  const unsigned __int16 *v24; // rax
  __int64 *v25; // rax
  unsigned __int64 v26; // rcx
  double v27; // xmm1_8
  LPOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+28h] [rbp-59h]
  unsigned int v30; // [rsp+38h] [rbp-49h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-41h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-39h] BYREF
  LARGE_INTEGER Frequency; // [rsp+50h] [rbp-31h] BYREF
  LARGE_INTEGER v34; // [rsp+58h] [rbp-29h] BYREF
  LARGE_INTEGER v35; // [rsp+60h] [rbp-21h] BYREF
  _ULARGE_INTEGER v36; // [rsp+68h] [rbp-19h] BYREF
  union _LARGE_INTEGER v37[5]; // [rsp+70h] [rbp-11h] BYREF
  BOOL v38; // [rsp+D8h] [rbp+57h]

  v7 = a2;
  PerformanceCount.QuadPart = 0;
  v35.QuadPart = 0;
  v34.QuadPart = 0;
  Frequency.QuadPart = 0;
  v36.HighPart = 0;
  lpBuffer = 0;
  *((_DWORD *)a1 + 22) = 0;
  *a5 = 0.0;
  if ( !QueryPerformanceFrequency(&Frequency) || !Frequency.QuadPart )
    return 0;
  LowPart = (double)(int)Frequency.LowPart;
  WinSAT::TimeGate::TimeGate(v37, Frequency);
  v11 = 1;
  if ( WinSAT::StorageDevice::AllocateBufferForLargestIO(v10, a3, &lpBuffer) )
  {
    v38 = QueryPerformanceCounter(&PerformanceCount);
    if ( v38 )
    {
      v12 = 0;
      v13 = *a3;
LABEL_6:
      if ( v13 == a3[1] )
      {
        if ( QueryPerformanceCounter(&v34) )
          *a6 = (double)(v34.LowPart - PerformanceCount.LowPart) / LowPart;
        if ( WinSAT::StorageDevice::GateIORate(a1, v7, 0) && QueryPerformanceCounter(&v35) )
        {
          v26 = v12 * 0xAAAAAAAAAAAAAAABuLL * ((a3[1] - *a3) >> 3);
          if ( (v26 & 0x8000000000000000uLL) != 0LL )
            v27 = (double)(int)(v26 & 1 | (v26 >> 1)) + (double)(int)(v26 & 1 | (v26 >> 1));
          else
            v27 = (double)(int)v26;
          *a5 = v27 / ((double)(v35.LowPart - PerformanceCount.LowPart) / LowPart) * 0.00000095367431640625;
        }
      }
      else if ( (*((_DWORD *)a1 + 22) < *(_DWORD *)(v13 + 12)
              || WinSAT::TimeGate::GateOnSleepTime((WinSAT::TimeGate *)v37, *(_DWORD *)(v13 + 20)))
             && WinSAT::StorageDevice::GateIORate(a1, v7, *(_DWORD *)(v13 + 12)) )
      {
        for ( i = 0; ; i = v30 + 1 )
        {
          v30 = i;
          if ( i > 0xA )
            break;
          v36.QuadPart = a4 + *(_QWORD *)v13;
          v12 = *(_DWORD *)(v13 + 8);
          if ( !*(_DWORD *)(v13 + 16) || (v15 = 0, *(_DWORD *)(v13 + 16) == 1) )
          {
            v15 = WinSAT::StorageDevice::OverlappedIOManager::RequestOverlapped(
                    (struct WinSAT::StorageDevice *)((char *)a1 + 8),
                    &v36,
                    a1);
            if ( !v15 )
            {
              SetLastError(0xEu);
              break;
            }
          }
          v16 = *(_DWORD *)(v13 + 16);
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              _InterlockedAdd((volatile signed __int32 *)a1 + 22, 1u);
              File = WriteFileEx(*((HANDLE *)a1 + 9), lpBuffer, v12, v15, WinSAT::StorageDevice::IOCompRoutine);
            }
            else
            {
              if ( v16 != 2 )
              {
                File = v38;
                goto LABEL_23;
              }
              File = FlushFileBuffers(*((HANDLE *)a1 + 9));
            }
          }
          else
          {
            _InterlockedAdd((volatile signed __int32 *)a1 + 22, 1u);
            File = ReadFileEx(*((HANDLE *)a1 + 9), lpBuffer, v12, v15, WinSAT::StorageDevice::IOCompRoutine);
          }
          v38 = File;
LABEL_23:
          if ( File || (LastError = GetLastError(), LastError == 997) )
          {
            v13 += 24;
            v7 = a2;
            goto LABEL_6;
          }
          if ( v15 )
            WinSAT::StorageDevice::OverlappedIOManager::ReleaseOverlapped(
              (struct WinSAT::StorageDevice *)((char *)a1 + 8),
              v15);
          if ( *(_DWORD *)(v13 + 16) != 2 )
            _InterlockedDecrement((volatile signed __int32 *)a1 + 22);
          if ( LastError != 1453 && LastError != 1450 && LastError != 1784 && LastError != 1816 && LastError != 8 )
          {
            if ( **((_BYTE **)a1 + 12) )
            {
              if ( *(_DWORD *)(v13 + 16) )
              {
                v23 = L"Write";
                if ( *(_DWORD *)(v13 + 16) != 1 )
                  v23 = L"unexpected";
              }
              else
              {
                v23 = L"Read";
              }
              LODWORD(lpCompletionRoutine) = LastError;
              v24 = mlib::MUISpf_(
                      (mlib *)"base\\winsat\\storage\\storedev.cpp",
                      (const char *)0x502,
                      430,
                      (unsigned __int16)v23,
                      lpCompletionRoutine);
              v25 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                      (__int64 *)(*((_QWORD *)a1 + 3) + 240LL),
                      (__int64)v24);
              std::endl(v25);
            }
            break;
          }
          if ( **((_BYTE **)a1 + 12) )
          {
            v20 = *((_QWORD *)a1 + 3);
            v21 = mlib::MUIStr_((mlib *)"base\\winsat\\storage\\storedev.cpp", (const char *)0x4F6, 429, v19);
            v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v20 + 240), (__int64)v21);
            std::endl(v22);
          }
        }
      }
    }
  }
  if ( *((int *)a1 + 22) > 0 )
  {
    CancelIo(*((HANDLE *)a1 + 9));
    while ( *((int *)a1 + 22) > 0 && SleepEx(0x2710u, 1) )
      ;
  }
  if ( lpBuffer )
    VirtualFree(lpBuffer, 0, 0x8000u);
  if ( GetLastError() )
    v11 = 0;
  WinSAT::TimeGate::~TimeGate((WinSAT::TimeGate *)v37);
  return v11;
}

```

## disassembly

```asm
0x140061b44  mov     rax, rsp
0x140061b47  mov     [rax+18h], rbx
0x140061b4b  mov     [rax+20h], r9
0x140061b4f  mov     [rax+10h], rdx
0x140061b53  push    rbp
0x140061b54  push    rsi
0x140061b55  push    rdi
0x140061b56  push    r12
0x140061b58  push    r13
0x140061b5a  push    r14
0x140061b5c  push    r15
0x140061b5e  lea     rbp, [rax-4Fh]
0x140061b62  sub     rsp, 90h
0x140061b69  movaps  xmmword ptr [rax-48h], xmm6
0x140061b6d  mov     r13, r8
0x140061b70  mov     rdi, rdx
0x140061b73  mov     rsi, rcx
0x140061b76  xor     ecx, ecx
0x140061b78  mov     qword ptr [rbp+47h+PerformanceCount], rcx
0x140061b7c  mov     qword ptr [rbp+47h+var_68], rcx
0x140061b80  mov     qword ptr [rbp+47h+var_70], rcx
0x140061b84  mov     qword ptr [rbp+47h+Frequency], rcx
0x140061b88  xor     eax, eax
0x140061b8a  mov     dword ptr [rbp+47h+var_60+4], eax
0x140061b8d  mov     [rbp+47h+lpBuffer], rcx
0x140061b91  mov     [rsi+58h], ecx
0x140061b94  mov     r15, [rbp+47h+arg_20]
0x140061b98  mov     [r15], rcx
0x140061b9b  lea     rcx, [rbp+47h+Frequency]; lpFrequency
0x140061b9f  call    cs:__imp_QueryPerformanceFrequency
0x140061ba5  test    eax, eax
0x140061ba7  jz      loc_140061F38
0x140061bad  mov     rdx, qword ptr [rbp+47h+Frequency]; union _LARGE_INTEGER
0x140061bb1  test    rdx, rdx
0x140061bb4  jz      loc_140061F38
0x140061bba  xorps   xmm6, xmm6
0x140061bbd  cvtsi2sd xmm6, rdx
0x140061bc2  lea     rcx, [rbp+47h+var_58]; this
0x140061bc6  call    ??0TimeGate@WinSAT@@QEAA@T_LARGE_INTEGER@@@Z; WinSAT::TimeGate::TimeGate(_LARGE_INTEGER)
0x140061bcb  nop
0x140061bcc  lea     r8, [rbp+47h+lpBuffer]
0x140061bd0  mov     rdx, r13
0x140061bd3  call    ?AllocateBufferForLargestIO@StorageDevice@WinSAT@@AEBA_NAEBV?$vector@UIODescriptor@StorageDevice@WinSAT@@V?$allocator@UIODescriptor@StorageDevice@WinSAT@@@std@@@std@@AEAPEAX@Z; WinSAT::StorageDevice::AllocateBufferForLargestIO(std::vector<WinSAT::StorageDevice::IODescriptor> const &,void * &)
0x140061bd8  mov     r14d, 1
0x140061bde  test    al, al
0x140061be0  jz      loc_140061EDA
0x140061be6  lea     rcx, [rbp+47h+PerformanceCount]; lpPerformanceCount
0x140061bea  call    cs:__imp_QueryPerformanceCounter
0x140061bf0  mov     [rbp+47h+arg_0], eax
0x140061bf3  test    eax, eax
0x140061bf5  jz      loc_140061EDA
0x140061bfb  xor     r12d, r12d
0x140061bfe  mov     rbx, [r13+0]
0x140061c02  cmp     rbx, [r13+8]
0x140061c06  jz      loc_140061E23
0x140061c0c  mov     eax, [rsi+58h]
0x140061c0f  cmp     eax, [rbx+0Ch]
0x140061c12  jl      short loc_140061C28
0x140061c14  mov     edx, [rbx+14h]; unsigned int
0x140061c17  lea     rcx, [rbp+47h+var_58]; this
0x140061c1b  call    ?GateOnSleepTime@TimeGate@WinSAT@@QEAA_NK@Z; WinSAT::TimeGate::GateOnSleepTime(ulong)
0x140061c20  test    al, al
0x140061c22  jz      loc_140061EDA
0x140061c28  mov     r8d, [rbx+0Ch]; int
0x140061c2c  mov     rdx, rdi; void *
0x140061c2f  mov     rcx, rsi; this
0x140061c32  call    ?GateIORate@StorageDevice@WinSAT@@AEBA_NPEAXJ@Z; WinSAT::StorageDevice::GateIORate(void *,long)
0x140061c37  test    al, al
0x140061c39  jz      loc_140061EDA
0x140061c3f  xor     eax, eax
0x140061c41  mov     [rbp+47h+var_90], eax
0x140061c44  cmp     eax, 0Ah
0x140061c47  ja      loc_140061EDA
0x140061c4d  mov     rax, [rbx]
0x140061c50  add     rax, [rbp+47h+arg_18]
0x140061c54  mov     qword ptr [rbp+47h+var_60], rax
0x140061c58  mov     r12d, [rbx+8]
0x140061c5c  cmp     dword ptr [rbx+10h], 0
0x140061c60  jz      short loc_140061C6B
0x140061c62  xor     r15d, r15d
0x140061c65  cmp     [rbx+10h], r14d
0x140061c69  jnz     short loc_140061C87
0x140061c6b  lea     rcx, [rsi+8]; this
0x140061c6f  mov     r8, rsi; struct WinSAT::StorageDevice *
0x140061c72  lea     rdx, [rbp+47h+var_60]; union _ULARGE_INTEGER *
0x140061c76  call    ?RequestOverlapped@OverlappedIOManager@StorageDevice@WinSAT@@QEAAPEAU_OVERLAPPED@@AEAT_ULARGE_INTEGER@@PEBV23@@Z; WinSAT::StorageDevice::OverlappedIOManager::RequestOverlapped(_ULARGE_INTEGER &,WinSAT::StorageDevice const *)
0x140061c7b  mov     r15, rax
0x140061c7e  test    rax, rax
0x140061c81  jz      loc_140061E13
0x140061c87  mov     eax, [rbx+10h]
0x140061c8a  test    eax, eax
0x140061c8c  jnz     short loc_140061CB5
0x140061c8e  lock add [rsi+58h], r14d
0x140061c93  lea     rax, ?IOCompRoutine@StorageDevice@WinSAT@@CAXKKPEAU_OVERLAPPED@@@Z; WinSAT::StorageDevice::IOCompRoutine(ulong,ulong,_OVERLAPPED *)
0x140061c9a  mov     [rsp+0C0h+lpCompletionRoutine], rax; lpCompletionRoutine
0x140061c9f  mov     r9, r15; lpOverlapped
0x140061ca2  mov     r8d, r12d; nNumberOfBytesToRead
0x140061ca5  mov     rdx, [rbp+47h+lpBuffer]; lpBuffer
0x140061ca9  mov     rcx, [rsi+48h]; hFile
0x140061cad  call    cs:__imp_ReadFileEx
0x140061cb3  jmp     short loc_140061CDF
0x140061cb5  cmp     eax, r14d
0x140061cb8  jnz     short loc_140061CE4
0x140061cba  lock add [rsi+58h], r14d
0x140061cbf  lea     rax, ?IOCompRoutine@StorageDevice@WinSAT@@CAXKKPEAU_OVERLAPPED@@@Z; WinSAT::StorageDevice::IOCompRoutine(ulong,ulong,_OVERLAPPED *)
0x140061cc6  mov     [rsp+0C0h+lpCompletionRoutine], rax; lpCompletionRoutine
0x140061ccb  mov     r9, r15; lpOverlapped
0x140061cce  mov     r8d, r12d; nNumberOfBytesToWrite
0x140061cd1  mov     rdx, [rbp+47h+lpBuffer]; lpBuffer
0x140061cd5  mov     rcx, [rsi+48h]; hFile
0x140061cd9  call    cs:__imp_WriteFileEx
0x140061cdf  mov     [rbp+47h+arg_0], eax
0x140061ce2  jmp     short loc_140061CF8
0x140061ce4  cmp     eax, 2
0x140061ce7  jnz     short loc_140061CF5
0x140061ce9  mov     rcx, [rsi+48h]; hFile
0x140061ced  call    cs:__imp_FlushFileBuffers
0x140061cf3  jmp     short loc_140061CDF
0x140061cf5  mov     eax, [rbp+47h+arg_0]
0x140061cf8  test    eax, eax
0x140061cfa  jnz     loc_140061D99
0x140061d00  call    cs:__imp_GetLastError
0x140061d06  mov     edi, eax
0x140061d08  cmp     eax, 3E5h
0x140061d0d  jz      loc_140061D99
0x140061d13  test    r15, r15
0x140061d16  jz      short loc_140061D24
0x140061d18  lea     rcx, [rsi+8]; this
0x140061d1c  mov     rdx, r15; struct _OVERLAPPED *
0x140061d1f  call    ?ReleaseOverlapped@OverlappedIOManager@StorageDevice@WinSAT@@QEAAXPEAU_OVERLAPPED@@@Z; WinSAT::StorageDevice::OverlappedIOManager::ReleaseOverlapped(_OVERLAPPED *)
0x140061d24  cmp     dword ptr [rbx+10h], 2
0x140061d28  jz      short loc_140061D2E
0x140061d2a  lock dec dword ptr [rsi+58h]
0x140061d2e  cmp     edi, 5ADh
0x140061d34  jz      short loc_140061D53
0x140061d36  cmp     edi, 5AAh
0x140061d3c  jz      short loc_140061D53
0x140061d3e  cmp     edi, 6F8h
0x140061d44  jz      short loc_140061D53
0x140061d46  cmp     edi, 718h
0x140061d4c  jz      short loc_140061D53
0x140061d4e  cmp     edi, 8
0x140061d51  jnz     short loc_140061DA6
0x140061d53  mov     rax, [rsi+60h]
0x140061d57  cmp     byte ptr [rax], 0
0x140061d5a  jz      short loc_140061D8E
0x140061d5c  mov     rdi, [rsi+18h]
0x140061d60  mov     edx, 4F6h; char *
0x140061d65  mov     r8d, 1ADh; int
0x140061d6b  lea     rcx, aBaseWinsatStor_1; "base\\winsat\\storage\\storedev.cpp"
0x140061d72  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140061d77  mov     rdx, rax
0x140061d7a  lea     rcx, [rdi+0F0h]
0x140061d81  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140061d86  mov     rcx, rax
0x140061d89  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140061d8e  mov     eax, [rbp+47h+var_90]
0x140061d91  add     eax, r14d
0x140061d94  jmp     loc_140061C41
0x140061d99  add     rbx, 18h
0x140061d9d  mov     rdi, [rbp+47h+arg_8]
0x140061da1  jmp     loc_140061C02
0x140061da6  mov     rax, [rsi+60h]
0x140061daa  cmp     byte ptr [rax], 0
0x140061dad  jz      loc_140061EDA
0x140061db3  cmp     dword ptr [rbx+10h], 0
0x140061db7  jnz     short loc_140061DC2
0x140061db9  lea     r9, aRead_0; "Read"
0x140061dc0  jmp     short loc_140061DD8
0x140061dc2  lea     r9, aWrite; "Write"
0x140061dc9  lea     rax, aUnexpected_0; "unexpected"
0x140061dd0  cmp     [rbx+10h], r14d
0x140061dd4  cmovnz  r9, rax; unsigned __int16
0x140061dd8  mov     r8d, 1AEh; int
0x140061dde  mov     dword ptr [rsp+0C0h+lpCompletionRoutine], edi
0x140061de2  mov     edx, 502h; char *
0x140061de7  lea     rcx, aBaseWinsatStor_1; "base\\winsat\\storage\\storedev.cpp"
0x140061dee  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140061df3  mov     rcx, [rsi+18h]
0x140061df7  add     rcx, 0F0h
0x140061dfe  mov     rdx, rax
0x140061e01  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140061e06  mov     rcx, rax
0x140061e09  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140061e0e  jmp     loc_140061EDA
0x140061e13  mov     ecx, 0Eh; dwErrCode
0x140061e18  call    cs:__imp_SetLastError
0x140061e1e  jmp     loc_140061EDA
0x140061e23  lea     rcx, [rbp+47h+var_70]; lpPerformanceCount
0x140061e27  call    cs:__imp_QueryPerformanceCounter
0x140061e2d  test    eax, eax
0x140061e2f  jz      short loc_140061E4D
0x140061e31  mov     rax, qword ptr [rbp+47h+var_70]
0x140061e35  sub     rax, qword ptr [rbp+47h+PerformanceCount]
0x140061e39  xorps   xmm0, xmm0
0x140061e3c  cvtsi2sd xmm0, rax
0x140061e41  divsd   xmm0, xmm6
0x140061e45  mov     rax, [rbp+47h+arg_28]
0x140061e49  movsd   qword ptr [rax], xmm0
0x140061e4d  xor     r8d, r8d; int
0x140061e50  mov     rdx, rdi; void *
0x140061e53  mov     rcx, rsi; this
0x140061e56  call    ?GateIORate@StorageDevice@WinSAT@@AEBA_NPEAXJ@Z; WinSAT::StorageDevice::GateIORate(void *,long)
0x140061e5b  test    al, al
0x140061e5d  jz      short loc_140061EDA
0x140061e5f  lea     rcx, [rbp+47h+var_68]; lpPerformanceCount
0x140061e63  call    cs:__imp_QueryPerformanceCounter
0x140061e69  test    eax, eax
0x140061e6b  jz      short loc_140061EDA
0x140061e6d  mov     rcx, [r13+8]
0x140061e71  sub     rcx, [r13+0]
0x140061e75  sar     rcx, 3
0x140061e79  mov     rax, 0AAAAAAAAAAAAAAABh
0x140061e83  imul    rcx, rax
0x140061e87  mov     eax, r12d
0x140061e8a  imul    rcx, rax
0x140061e8e  xorps   xmm1, xmm1
0x140061e91  test    rcx, rcx
0x140061e94  js      short loc_140061E9D
0x140061e96  cvtsi2sd xmm1, rcx
0x140061e9b  jmp     short loc_140061EB2
0x140061e9d  mov     rax, rcx
0x140061ea0  shr     rax, 1
0x140061ea3  and     rcx, r14
0x140061ea6  or      rax, rcx
0x140061ea9  cvtsi2sd xmm1, rax
0x140061eae  addsd   xmm1, xmm1
0x140061eb2  mov     rax, qword ptr [rbp+47h+var_68]
0x140061eb6  sub     rax, qword ptr [rbp+47h+PerformanceCount]
0x140061eba  xorps   xmm0, xmm0
0x140061ebd  cvtsi2sd xmm0, rax
0x140061ec2  divsd   xmm0, xmm6
0x140061ec6  divsd   xmm1, xmm0
0x140061eca  mulsd   xmm1, cs:__real@3eb0000000000000
0x140061ed2  mov     rax, [rbp+47h+arg_20]
0x140061ed6  movsd   qword ptr [rax], xmm1
0x140061eda  mov     eax, [rsi+58h]
0x140061edd  test    eax, eax
0x140061edf  jle     short loc_140061F04
0x140061ee1  mov     rcx, [rsi+48h]; hFile
0x140061ee5  call    cs:__imp_CancelIo
0x140061eeb  mov     eax, [rsi+58h]
0x140061eee  test    eax, eax
0x140061ef0  jle     short loc_140061F04
0x140061ef2  mov     edx, r14d; bAlertable
0x140061ef5  mov     ecx, 2710h; dwMilliseconds
0x140061efa  call    cs:__imp_SleepEx
0x140061f00  test    eax, eax
0x140061f02  jnz     short loc_140061EEB
0x140061f04  cmp     [rbp+47h+lpBuffer], 0
0x140061f09  jz      short loc_140061F1D
0x140061f0b  xor     edx, edx; dwSize
0x140061f0d  mov     r8d, 8000h; dwFreeType
0x140061f13  mov     rcx, [rbp+47h+lpBuffer]; lpAddress
0x140061f17  call    cs:__imp_VirtualFree
0x140061f1d  call    cs:__imp_GetLastError
0x140061f23  test    eax, eax
0x140061f25  jz      short loc_140061F2A
0x140061f27  xor     r14b, r14b
0x140061f2a  lea     rcx, [rbp+47h+var_58]; this
0x140061f2e  call    ??1TimeGate@WinSAT@@QEAA@XZ; WinSAT::TimeGate::~TimeGate(void)
0x140061f33  mov     al, r14b
0x140061f36  jmp     short loc_140061F3A
0x140061f38  xor     al, al
0x140061f3a  lea     r11, [rsp+0C0h+var_30]
0x140061f42  mov     rbx, [r11+50h]
0x140061f46  movaps  xmm6, xmmword ptr [r11-10h]
0x140061f4b  mov     rsp, r11
0x140061f4e  pop     r15
0x140061f50  pop     r14
0x140061f52  pop     r13
0x140061f54  pop     r12
0x140061f56  pop     rdi
0x140061f57  pop     rsi
0x140061f58  pop     rbp
0x140061f59  retn
```
