# COMXProc::CHardwareDevicesImpl::Advise(ulong,unsigned __int64,unsigned __int64,ulong *)

- ea: `0x1800291e0`
- end: `0x1800292d0`
- name: `?Advise@CHardwareDevicesImpl@COMXProc@@UEAAJK_K0PEAK@Z`
- size: `240`
- prototype: `__int64 __fastcall(COMXProc::CHardwareDevicesImpl *this, unsigned int, unsigned __int64, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003570`
- `0x1800176e8`
- `0x180019598`
- `0x180028c24`
- `0x180028cf8`
- `0x1800291e0`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002925d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002925d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292af`

## pseudocode

```c
__int64 __fastcall COMXProc::CHardwareDevicesImpl::Advise(
        COMXProc::CHardwareDevicesImpl *this,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned int *a5)
{
  XProcHelpers *v8; // rcx
  int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // [rsp+30h] [rbp-48h] BYREF
  COMXProc::CAdviseClient *v15; // [rsp+38h] [rbp-40h] BYREF

  v9 = XProcHelpers::XProcFunctionCallEnter(1);
  if ( v9 >= 0 )
  {
    if ( a2 && a3 && a4 && a5 )
    {
      v15 = 0;
      v10 = _InterlockedIncrement(&COMXProc::CHardwareDevicesImpl::_lAdviseToken);
      v14 = 0;
      EnterCriticalSection(&CriticalSection);
      v9 = CNamedElemList<COMXProc::CAdviseClient>::GetOrAdd<int,unsigned long>(v11, v10, &v15, &v14);
      if ( v9 >= 0 )
      {
        v9 = COMXProc::CAdviseClient::_Init(v15, a2, a3, a4);
        if ( v9 < 0 )
          CNamedElemList<COMXProc::CAdviseClient>::Remove<unsigned long>(v12, v10);
        else
          *a5 = v10;
        CRefCounted::Release(v15);
      }
      LeaveCriticalSection(&CriticalSection);
    }
    else
    {
      v9 = -2147024809;
    }
    XProcHelpers::XProcFunctionCallExit(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800291e0  push    rbx
0x1800291e2  push    rbp
0x1800291e3  push    rsi
0x1800291e4  push    rdi
0x1800291e5  push    r14
0x1800291e7  push    r15
0x1800291e9  sub     rsp, 48h
0x1800291ed  mov     ecx, 1
0x1800291f2  mov     rbp, r9
0x1800291f5  mov     r14, r8
0x1800291f8  mov     r15d, edx
0x1800291fb  call    ?XProcFunctionCallEnter@XProcHelpers@@YAJW4XPROC_ENTER_BEHAVIOR@@@Z; XProcHelpers::XProcFunctionCallEnter(XPROC_ENTER_BEHAVIOR)
0x180029200  mov     ebx, eax
0x180029202  test    eax, eax
0x180029204  js      loc_1800292C1
0x18002920a  test    r15d, r15d
0x18002920d  jz      loc_1800292B7
0x180029213  test    r14, r14
0x180029216  jz      loc_1800292B7
0x18002921c  test    rbp, rbp
0x18002921f  jz      loc_1800292B7
0x180029225  mov     rsi, [rsp+78h+arg_20]
0x18002922d  test    rsi, rsi
0x180029230  jz      loc_1800292B7
0x180029236  mov     edi, 1
0x18002923b  lock xadd cs:?_lAdviseToken@CHardwareDevicesImpl@COMXProc@@0JA, edi; long COMXProc::CHardwareDevicesImpl::_lAdviseToken
0x180029243  lea     rcx, CriticalSection; lpCriticalSection
0x18002924a  mov     [rsp+78h+var_40], 0
0x180029253  inc     edi
0x180029255  mov     [rsp+78h+var_48], 0
0x18002925d  call    cs:__imp_EnterCriticalSection
0x180029263  lea     r9, [rsp+78h+var_48]
0x180029268  mov     edx, edi
0x18002926a  lea     r8, [rsp+78h+var_40]
0x18002926f  call    ??$GetOrAdd@HK@?$CNamedElemList@VCAdviseClient@COMXProc@@@@QEAAJKPEAPEAVCAdviseClient@COMXProc@@PEAHH@Z; CNamedElemList<COMXProc::CAdviseClient>::GetOrAdd<int,ulong>(ulong,COMXProc::CAdviseClient * *,int *,int)
0x180029274  mov     ebx, eax
0x180029276  test    eax, eax
0x180029278  js      short loc_1800292A8
0x18002927a  mov     rcx, [rsp+78h+var_40]; this
0x18002927f  mov     r9, rbp; unsigned __int64
0x180029282  mov     r8, r14; unsigned __int64
0x180029285  mov     edx, r15d; unsigned int
0x180029288  call    ?_Init@CAdviseClient@COMXProc@@QEAAJK_K0@Z; COMXProc::CAdviseClient::_Init(ulong,unsigned __int64,unsigned __int64)
0x18002928d  mov     ebx, eax
0x18002928f  test    eax, eax
0x180029291  js      short loc_180029297
0x180029293  mov     [rsi], edi
0x180029295  jmp     short loc_18002929E
0x180029297  mov     edx, edi
0x180029299  call    ??$Remove@K@?$CNamedElemList@VCAdviseClient@COMXProc@@@@QEAAJK@Z; CNamedElemList<COMXProc::CAdviseClient>::Remove<ulong>(ulong)
0x18002929e  mov     rcx, [rsp+78h+var_40]; this
0x1800292a3  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800292a8  lea     rcx, CriticalSection; lpCriticalSection
0x1800292af  call    cs:__imp_LeaveCriticalSection
0x1800292b5  jmp     short loc_1800292BC
0x1800292b7  mov     ebx, 80070057h
0x1800292bc  call    ?XProcFunctionCallExit@XProcHelpers@@YAJXZ; XProcHelpers::XProcFunctionCallExit(void)
0x1800292c1  mov     eax, ebx
0x1800292c3  add     rsp, 48h
0x1800292c7  pop     r15
0x1800292c9  pop     r14
0x1800292cb  pop     rdi
0x1800292cc  pop     rsi
0x1800292cd  pop     rbp
0x1800292ce  pop     rbx
0x1800292cf  retn
```
