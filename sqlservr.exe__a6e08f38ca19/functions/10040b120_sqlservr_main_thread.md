# sqlservr_main_thread

- ea: `0x10040b120`
- end: `0x10040b2a6`
- name: `sqlservr_main_thread`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040b120`
- `0x1004115f0`
- `0x100416770`
- `0x1004233a0`

## import_xrefs

- `sqldk!?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A` at `0x10040b1ff`
- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040b15f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040b1eb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040b1eb`
- `sqldk!SystemThread_TlsOffset` at `0x10040b1d0`
- `sqldk!SystemThread_TlsIndex` at `0x10040b1c7`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040b226`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040b226`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040b275`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040b275`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040b1b7`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040b1b7`
- `sqldk!?ProcessBufferArray@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@IQEAPEA_W@Z` at `0x10040b249`
- `sqldk!?ProcessBufferArray@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@IQEAPEA_W@Z` at `0x10040b249`
- `api-ms-win-crt-runtime-l1-1-0!_endthread` at `0x10040b27b`
- `api-ms-win-crt-runtime-l1-1-0!_endthread` at `0x10040b27b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall sqlservr_main_thread(int a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // r8
  void *v7; // rsp
  void *v8; // rsp
  __int64 v9; // rdi
  __int64 v10; // rbx
  char *v11; // r8
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-20h]
  __int64 v14; // [rsp+40h] [rbp+0h] BYREF
  _BYTE v15[6048]; // [rsp+50h] [rbp+10h] BYREF

  v14 = -2;
  v4 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
  v5 = 8 * v4 + 15;
  if ( v5 <= 8 * v4 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
  v7 = alloca(v6);
  v8 = alloca(v6);
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v15, 0, v4, (void **)&v14, 1, 0, 0);
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  *(_DWORD *)(v10 + 616) |= 0x20u;
  v11 = (char *)&SOS_PublicGlobals::sm_osMemoryClerk + 64;
  if ( !SOS_PublicGlobals::sm_osMemoryClerk )
    v11 = 0;
  LOWORD(v13) = 128;
  *(_QWORD *)(v10 + 1000) = MemoryObjectFactory::CreateMemObject(1, 4, v11, 8, v13);
  if ( a1 > 1 )
  {
    _mm_lfence();
    v12 = DkParametersProcessor::ProcessBufferArray(&qword_1004A1720, (unsigned int)(a1 - 1), a2 + 8);
    if ( v12 )
    {
      _mm_lfence();
      InitializeErrorReportingForStartupFailure();
      LogInvalidParameterInCommandLine(v12, &qword_1004A1720);
    }
  }
  sqlservr_main();
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v15);
  _endthread();
}

```

## disassembly

```asm
0x10040b120  push    rbp
0x10040b122  push    rsi
0x10040b123  push    rdi
0x10040b124  push    r14
0x10040b126  push    r15
0x10040b128  mov     eax, 1800h
0x10040b12d  call    _alloca_probe
0x10040b132  sub     rsp, rax
0x10040b135  lea     rbp, [rsp+40h]
0x10040b13a  mov     [rbp+17E0h+var_17E0], 0FFFFFFFFFFFFFFFEh
0x10040b142  mov     [rbp+17E0h+arg_10], rbx
0x10040b149  mov     rax, cs:__security_cookie
0x10040b150  xor     rax, rbp
0x10040b153  mov     [rbp+17E0h+var_30], rax
0x10040b15a  mov     r14, rdx
0x10040b15d  mov     esi, ecx
0x10040b15f  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040b166  mov     rcx, [rax+8]
0x10040b16a  lea     rax, ds:0[rcx*8]
0x10040b172  lea     r8, [rax+0Fh]
0x10040b176  cmp     r8, rax
0x10040b179  ja      short loc_10040B185
0x10040b17b  mov     r8, 0FFFFFFFFFFFFFF0h
0x10040b185  and     r8, 0FFFFFFFFFFFFFFF0h
0x10040b189  mov     rax, r8
0x10040b18c  call    _alloca_probe
0x10040b191  sub     rsp, r8
0x10040b194  lea     r9, [rsp+1820h+var_17E0]
0x10040b199  xor     r15d, r15d
0x10040b19c  mov     [rsp+1820h+var_17F0], r15
0x10040b1a1  mov     [rsp+1820h+var_17F8], r15
0x10040b1a6  mov     [rsp+1820h+var_1800], 1
0x10040b1ae  mov     r8, rcx
0x10040b1b1  xor     edx, edx
0x10040b1b3  lea     rcx, [rbp+17E0h+var_17D0]
0x10040b1b7  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040b1bd  nop
0x10040b1be  mov     rdx, gs:58h
0x10040b1c7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040b1ce  mov     ecx, [rax]
0x10040b1d0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040b1d7  mov     edi, [rax]
0x10040b1d9  add     rdi, [rdx+rcx*8]
0x10040b1dd  mov     rbx, [rdi+100h]
0x10040b1e4  test    rbx, rbx
0x10040b1e7  jnz     short loc_10040B1F8
0x10040b1e9  xor     ecx, ecx
0x10040b1eb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040b1f1  mov     rbx, [rdi+100h]
0x10040b1f8  or      dword ptr [rbx+268h], 20h
0x10040b1ff  mov     rax, cs:__imp_?sm_osMemoryClerk@SOS_PublicGlobals@@2VMemoryClerk@@A; MemoryClerk SOS_PublicGlobals::sm_osMemoryClerk
0x10040b206  mov     edx, 80h
0x10040b20b  lea     r9d, [rdx-78h]
0x10040b20f  lea     r8, [rax+40h]
0x10040b213  test    rax, rax
0x10040b216  cmovz   r8, r15
0x10040b21a  mov     word ptr [rsp+1820h+var_1800], dx
0x10040b21f  lea     edx, [r9-4]
0x10040b223  lea     ecx, [rdx-3]
0x10040b226  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x10040b22c  mov     [rbx+3E8h], rax
0x10040b233  cmp     esi, 1
0x10040b236  jle     short loc_10040B26B
0x10040b238  lfence
0x10040b23b  lea     r8, [r14+8]
0x10040b23f  lea     edx, [rsi-1]
0x10040b242  lea     rcx, qword_1004A1720
0x10040b249  call    cs:__imp_?ProcessBufferArray@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@IQEAPEA_W@Z; DkParametersProcessor::ProcessBufferArray(uint,wchar_t * * const)
0x10040b24f  mov     ebx, eax
0x10040b251  test    eax, eax
0x10040b253  jz      short loc_10040B26B
0x10040b255  lfence
0x10040b258  call    ?InitializeErrorReportingForStartupFailure@@YAXXZ; InitializeErrorReportingForStartupFailure(void)
0x10040b25d  lea     rdx, qword_1004A1720
0x10040b264  mov     ecx, ebx
0x10040b266  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x10040b26b  call    ?sqlservr_main@@YAXXZ; sqlservr_main(void)
0x10040b270  nop
0x10040b271  lea     rcx, [rbp+17E0h+var_17D0]
0x10040b275  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040b27b  call    cs:__imp__endthread
0x10040b281  mov     rcx, [rbp+17E0h+var_30]
0x10040b288  xor     rcx, rbp; StackCookie
0x10040b28b  call    __security_check_cookie
0x10040b290  mov     rbx, [rbp+17E0h+arg_10]
0x10040b297  lea     rsp, [rbp+17C0h]
0x10040b29e  pop     r15
0x10040b2a0  pop     r14
0x10040b2a2  pop     rdi
0x10040b2a3  pop     rsi
0x10040b2a4  pop     rbp
0x10040b2a5  retn
```
