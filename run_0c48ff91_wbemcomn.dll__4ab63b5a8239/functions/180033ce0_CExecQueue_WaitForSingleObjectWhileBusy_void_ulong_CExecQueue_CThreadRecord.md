# CExecQueue::WaitForSingleObjectWhileBusy(void *,ulong,CExecQueue::CThreadRecord *)

- ea: `0x180033ce0`
- end: `0x180033f06`
- name: `?WaitForSingleObjectWhileBusy@CExecQueue@@MEAAKPEAXKPEAVCThreadRecord@1@@Z`
- size: `550`
- prototype: `unsigned int(CExecQueue *__hidden this, void *, unsigned int, struct CExecQueue::CThreadRecord *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800041d0`
- `0x1800041e8`
- `0x180014120`
- `0x180028b80`
- `0x180033454`
- `0x180033ce0`
- `0x180033f20`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033e08`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033e08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033d78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033d78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ecc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033e79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033e79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033d85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e26`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExecQueue::WaitForSingleObjectWhileBusy(
        CExecQueue *this,
        void *a2,
        unsigned int a3,
        struct CExecQueue::CThreadRecord *a4)
{
  void *v6; // r14
  CStaticCritSec *v8; // rdi
  __int64 v9; // r15
  DWORD TickCount; // r13d
  __int64 v11; // rax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // r14d
  DWORD v15; // eax
  DWORD v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-20h] BYREF
  char *v21; // [rsp+28h] [rbp-18h]
  HANDLE pHandles[2]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE v23; // [rsp+80h] [rbp+40h] BYREF
  void *v24; // [rsp+88h] [rbp+48h]

  v24 = a2;
  v6 = a2;
  v8 = (CExecQueue *)((char *)this + 16);
  v21 = (char *)this + 16;
  v20 = 0;
  v9 = *((_QWORD *)a4 + 1);
  TickCount = GetTickCount();
  while ( 1 )
  {
    if ( a3 <= GetTickCount() - TickCount )
    {
      v17 = 258;
      goto LABEL_19;
    }
    CStaticCritSec::Enter(v8);
    v20 = 1;
    v11 = (*(__int64 (__fastcall **)(CExecQueue *, struct CExecQueue::CThreadRecord *))(*(_QWORD *)this + 120LL))(
            this,
            a4);
    if ( v11 )
    {
      *((_QWORD *)a4 + 1) = v11;
      goto LABEL_9;
    }
    *((_DWORD *)a4 + 4) = 1;
    pHandles[0] = v6;
    pHandles[1] = *((HANDLE *)a4 + 4);
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
    v12 = GetTickCount();
    v13 = CompensateForBug(a3, v12 - TickCount);
    v14 = WbemWaitForMultipleObjects(2u, pHandles, v13);
    CStaticCritSec::Enter(v8);
    v20 = 1;
    *((_DWORD *)a4 + 4) = 0;
    if ( v14 != 1 )
      break;
    if ( *((_DWORD *)a4 + 5) || !*((_QWORD *)a4 + 1) )
    {
      SetEvent(*((HANDLE *)a4 + 4));
      LeaveCriticalSection((LPCRITICAL_SECTION)v8);
      v20 = 0;
      v23 = v24;
      v15 = GetTickCount();
      v16 = CompensateForBug(a3, v15 - TickCount);
      v17 = WbemWaitForMultipleObjects(1u, &v23, v16);
      goto LABEL_19;
    }
    v6 = v24;
LABEL_9:
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
    v20 = 0;
    (*(void (__fastcall **)(CExecQueue *, struct CExecQueue::CThreadRecord *))(*(_QWORD *)this + 104LL))(this, a4);
    *((_QWORD *)a4 + 1) = v9;
  }
  v18 = *((_QWORD *)a4 + 1);
  if ( v18 != v9 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)a4 + 160LL))(*(_QWORD *)a4, v18, 0);
    *((_QWORD *)a4 + 1) = v9;
    v14 = WaitForSingleObject(*((HANDLE *)a4 + 4), 0);
    if ( v14 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFF);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8b428a072f23334ffa8fa793348b70d5_Traceguids);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  v20 = 0;
  v17 = v14;
LABEL_19:
  CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v20);
  return v17;
}

```

## disassembly

```asm
0x180033ce0  mov     [rsp-38h+arg_10], rbx
0x180033ce5  mov     [rsp-38h+arg_8], rdx
0x180033cea  push    rbp
0x180033ceb  push    rsi
0x180033cec  push    rdi
0x180033ced  push    r12
0x180033cef  push    r13
0x180033cf1  push    r14
0x180033cf3  push    r15
0x180033cf5  mov     rbp, rsp
0x180033cf8  sub     rsp, 40h
0x180033cfc  mov     rbx, r9
0x180033cff  mov     r12d, r8d
0x180033d02  mov     r14, rdx
0x180033d05  mov     rsi, rcx
0x180033d08  lea     rdi, [rcx+10h]
0x180033d0c  mov     [rbp+var_18], rdi
0x180033d10  mov     [rbp+var_20], 0
0x180033d17  mov     r15, [r9+8]
0x180033d1b  call    cs:__imp_GetTickCount
0x180033d21  mov     r13d, eax
0x180033d24  call    cs:__imp_GetTickCount
0x180033d2a  sub     eax, r13d
0x180033d2d  cmp     r12d, eax
0x180033d30  jbe     loc_180033EDE
0x180033d36  mov     rcx, rdi; this
0x180033d39  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180033d3e  mov     [rbp+var_20], 1
0x180033d45  mov     rax, [rsi]
0x180033d48  mov     rdx, rbx
0x180033d4b  mov     rcx, rsi
0x180033d4e  mov     rax, [rax+78h]
0x180033d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d57  test    rax, rax
0x180033d5a  jz      short loc_180033D62
0x180033d5c  mov     [rbx+8], rax
0x180033d60  jmp     short loc_180033DD9
0x180033d62  mov     dword ptr [rbx+10h], 1
0x180033d69  mov     [rbp+pHandles], r14
0x180033d6d  mov     rax, [rbx+20h]
0x180033d71  mov     [rbp+var_8], rax
0x180033d75  mov     rcx, rdi; lpCriticalSection
0x180033d78  call    cs:__imp_LeaveCriticalSection
0x180033d7e  mov     [rbp+var_20], 0
0x180033d85  call    cs:__imp_GetTickCount
0x180033d8b  sub     eax, r13d
0x180033d8e  mov     edx, eax; unsigned int
0x180033d90  mov     ecx, r12d; unsigned int
0x180033d93  call    ?CompensateForBug@@YAKKK@Z; CompensateForBug(ulong,ulong)
0x180033d98  mov     r8d, eax; dwTimeout
0x180033d9b  lea     rdx, [rbp+pHandles]; pHandles
0x180033d9f  mov     ecx, 2; cHandles
0x180033da4  call    ?WbemWaitForMultipleObjects@@YAKKPEAPEAXK@Z; WbemWaitForMultipleObjects(ulong,void * *,ulong)
0x180033da9  mov     r14d, eax
0x180033dac  mov     rcx, rdi; this
0x180033daf  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180033db4  mov     [rbp+var_20], 1
0x180033dbb  xor     eax, eax
0x180033dbd  mov     [rbx+10h], eax
0x180033dc0  cmp     r14d, 1
0x180033dc4  jnz     loc_180033E51
0x180033dca  cmp     [rbx+14h], eax
0x180033dcd  jnz     short loc_180033E04
0x180033dcf  cmp     [rbx+8], rax
0x180033dd3  jz      short loc_180033E04
0x180033dd5  mov     r14, [rbp+arg_8]
0x180033dd9  mov     rcx, rdi; lpCriticalSection
0x180033ddc  call    cs:__imp_LeaveCriticalSection
0x180033de2  mov     [rbp+var_20], 0
0x180033de9  mov     rax, [rsi]
0x180033dec  mov     rdx, rbx
0x180033def  mov     rcx, rsi
0x180033df2  mov     rax, [rax+68h]
0x180033df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dfb  mov     [rbx+8], r15
0x180033dff  jmp     loc_180033D24
0x180033e04  mov     rcx, [rbx+20h]; hEvent
0x180033e08  call    cs:__imp_SetEvent
0x180033e0e  mov     rcx, rdi; lpCriticalSection
0x180033e11  call    cs:__imp_LeaveCriticalSection
0x180033e17  mov     [rbp+var_20], 0
0x180033e1e  mov     rax, [rbp+arg_8]
0x180033e22  mov     [rbp+arg_0], rax
0x180033e26  call    cs:__imp_GetTickCount
0x180033e2c  sub     eax, r13d
0x180033e2f  mov     edx, eax; unsigned int
0x180033e31  mov     ecx, r12d; unsigned int
0x180033e34  call    ?CompensateForBug@@YAKKK@Z; CompensateForBug(ulong,ulong)
0x180033e39  mov     r8d, eax; dwTimeout
0x180033e3c  lea     rdx, [rbp+arg_0]; pHandles
0x180033e40  mov     ecx, 1; cHandles
0x180033e45  call    ?WbemWaitForMultipleObjects@@YAKKPEAPEAXK@Z; WbemWaitForMultipleObjects(ulong,void * *,ulong)
0x180033e4a  mov     ebx, eax
0x180033e4c  jmp     loc_180033EE3
0x180033e51  mov     rdx, [rbx+8]
0x180033e55  cmp     rdx, r15
0x180033e58  jz      short loc_180033EC9
0x180033e5a  mov     rcx, [rbx]
0x180033e5d  mov     rax, [rcx]
0x180033e60  xor     r8d, r8d
0x180033e63  mov     rax, [rax+0A0h]
0x180033e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e6f  mov     [rbx+8], r15
0x180033e73  xor     edx, edx; dwMilliseconds
0x180033e75  mov     rcx, [rbx+20h]; hHandle
0x180033e79  call    cs:__imp_WaitForSingleObject
0x180033e7f  mov     r14d, eax
0x180033e82  test    eax, eax
0x180033e84  jz      short loc_180033EC9
0x180033e86  or      edx, 0FFFFFFFFh; int
0x180033e89  lea     rcx, unk_18006A9C0; this
0x180033e90  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180033e95  lea     rax, WPP_GLOBAL_Control
0x180033e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ea3  cmp     rcx, rax
0x180033ea6  jz      short loc_180033EC9
0x180033ea8  test    byte ptr [rcx+1Ch], 1
0x180033eac  jz      short loc_180033EC9
0x180033eae  cmp     byte ptr [rcx+19h], 2
0x180033eb2  jb      short loc_180033EC9
0x180033eb4  mov     edx, 12h
0x180033eb9  lea     r8, WPP_8b428a072f23334ffa8fa793348b70d5_Traceguids
0x180033ec0  mov     rcx, [rcx+10h]
0x180033ec4  call    WPP_SF_
0x180033ec9  mov     rcx, rdi; lpCriticalSection
0x180033ecc  call    cs:__imp_LeaveCriticalSection
0x180033ed2  mov     [rbp+var_20], 0
0x180033ed9  mov     ebx, r14d
0x180033edc  jmp     short loc_180033EE3
0x180033ede  mov     ebx, 102h
0x180033ee3  lea     rcx, [rbp+var_20]; this
0x180033ee7  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x180033eec  mov     eax, ebx
0x180033eee  mov     rbx, [rsp+40h+arg_10]
0x180033ef6  add     rsp, 40h
0x180033efa  pop     r15
0x180033efc  pop     r14
0x180033efe  pop     r13
0x180033f00  pop     r12
0x180033f02  pop     rdi
0x180033f03  pop     rsi
0x180033f04  pop     rbp
0x180033f05  retn
```
