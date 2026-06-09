# CSGXEnclave::CSGXEnclave(EnclaveConfiguration const &,IMemObj *)

- ea: `0x100838f00`
- end: `0x1008391a6`
- name: `??0CSGXEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z`
- size: `678`
- prototype: `CSGXEnclave *__fastcall(CSGXEnclave *__hidden this, const struct EnclaveConfiguration *, struct IMemObj *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x100837ae0`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x10045f130`
- `0x1004c7420`
- `0x10082cad0`
- `0x1008376b0`
- `0x1008378d0`
- `0x100838f00`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1008390c5`
- `KERNEL32!LoadLibraryExW` at `0x1008390c5`
- `KERNEL32!GetLastError` at `0x1008390d0`
- `KERNEL32!GetLastError` at `0x1008390d0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100839033`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100839033`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083917f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10083917f`
- `sqldk!SystemThread_TlsIndex` at `0x100838f4f`
- `sqldk!SystemThread_TlsIndex` at `0x100838ff3`
- `sqldk!SystemThread_TlsIndex` at `0x100839048`
- `sqldk!SystemThread_TlsOffset` at `0x100838f58`
- `sqldk!SystemThread_TlsOffset` at `0x100838ffc`
- `sqldk!SystemThread_TlsOffset` at `0x100839051`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838f73`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100839015`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083906c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838f73`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100839015`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083906c`
- `sgx_urts!sgx_create_enclavew` at `0x10083912c`
- `sgx_urts!sgx_create_enclavew` at `0x10083912c`

## string_xrefs

- `0x1008390be`: `sgx_urts.dll`
- `0x1008390d9`: `SgxLoadLibrary`
- `0x100838f87`: `\aetm-enclave.sgx.pkg\aetm-sgx-enclave.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CSGXEnclave *__fastcall CSGXEnclave::CSGXEnclave(
        CSGXEnclave *this,
        const struct EnclaveConfiguration *a2,
        struct IMemObj *a3)
{
  void *EnclavePath; // rsi
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rdx
  DWORD LastError; // eax
  unsigned int enclavew; // eax
  _DWORD v13[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+54h] [rbp-ACh]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  bool v24; // [rsp+90h] [rbp-70h]
  _QWORD v25[6]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[1024]; // [rsp+D0h] [rbp-30h] BYREF

  v25[1] = -2;
  v25[2] = this;
  CEnclave::CEnclave(this, a2, a3);
  *(_QWORD *)this = &CSGXEnclave::`vftable';
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  EnclavePath = (void *)GetEnclavePath((wchar_t *)L"\\aetm-enclave.sgx.pkg\\aetm-sgx-enclave.dll");
  v25[3] = EnclavePath;
  memset_0(v26, 0, sizeof(v26));
  v13[0] = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v14, 1);
  v25[4] = &v16;
  v19 = 536871501;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  v7 = *(_QWORD *)(v6 + 600);
  if ( v7 )
    v24 = (unsigned int)SOS_Task::PushWait(v7, &v19) == 0;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v18 = v9;
  v17 = (*(_DWORD *)(v9 + 800) >> 11) & 1;
  if ( v17 || (*(_BYTE *)(v9 + 800) & 4) == 0 )
  {
    v16 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 608) + 8LL))(*(_QWORD *)(v9 + 608));
  }
  else
  {
    v16 = 0;
  }
  if ( LoadLibraryExW(L"sgx_urts.dll", 0, 0x802u) )
  {
    enclavew = sgx_create_enclavew(EnclavePath, 0, v26, v13, v25, 0);
    if ( enclavew )
      scierrlog(0x91BAu, L"SGX", enclavew);
    else
      *((_QWORD *)this + 2) = v25[0];
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v16);
    *(_DWORD *)(v15 + 616) &= ~v14;
  }
  else
  {
    LastError = GetLastError();
    scierrlog(0x9275u, L"SGX", L"SgxLoadLibrary", LastError);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v16);
    *(_DWORD *)(v15 + 616) &= ~v14;
  }
  operator delete[](EnclavePath);
  return this;
}

```

## disassembly

```asm
0x100838f00  push    rbp
0x100838f02  push    rbx
0x100838f03  push    rsi
0x100838f04  push    rdi
0x100838f05  push    r14
0x100838f07  lea     rbp, [rsp-3E0h]
0x100838f0f  sub     rsp, 4E0h
0x100838f16  mov     [rbp+400h+var_458], 0FFFFFFFFFFFFFFFEh
0x100838f1e  mov     rax, cs:__security_cookie
0x100838f25  xor     rax, rsp
0x100838f28  mov     [rbp+400h+var_30], rax
0x100838f2f  mov     rdi, rcx
0x100838f32  mov     [rbp+400h+var_450], rcx
0x100838f36  call    ??0CEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CEnclave::CEnclave(EnclaveConfiguration const &,IMemObj *)
0x100838f3b  nop
0x100838f3c  lea     rax, ??_7CSGXEnclave@@6B@; const CSGXEnclave::`vftable'
0x100838f43  mov     [rdi], rax
0x100838f46  mov     rdx, gs:58h
0x100838f4f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100838f56  mov     ecx, [rax]
0x100838f58  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100838f5f  mov     ebx, [rax]
0x100838f61  add     rbx, [rdx+rcx*8]
0x100838f65  mov     rdx, [rbx+100h]
0x100838f6c  test    rdx, rdx
0x100838f6f  jnz     short loc_100838F80
0x100838f71  xor     ecx, ecx
0x100838f73  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100838f79  mov     rdx, [rbx+100h]
0x100838f80  mov     rdx, [rdx+3E8h]
0x100838f87  lea     rcx, aAetmEnclaveSgx; "\\aetm-enclave.sgx.pkg\\aetm-sgx-enclav"...
0x100838f8e  call    GetEnclavePath
0x100838f93  mov     rsi, rax
0x100838f96  mov     [rbp+400h+var_448], rax
0x100838f9a  xor     edx, edx; Val
0x100838f9c  mov     r8d, 400h; Size
0x100838fa2  lea     rcx, [rbp+400h+var_430]; void *
0x100838fa6  call    memset_0
0x100838fab  xor     r14d, r14d
0x100838fae  mov     [rsp+500h+var_4D0], r14d
0x100838fb3  lea     edx, [r14+1]
0x100838fb7  lea     rcx, [rsp+500h+var_4C0]
0x100838fbc  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100838fc1  nop
0x100838fc2  lea     rax, [rsp+500h+var_4B0]
0x100838fc7  mov     [rbp+400h+var_440], rax
0x100838fcb  mov     [rsp+500h+var_4A0], 2000024Dh
0x100838fd3  mov     [rsp+500h+var_498], r14
0x100838fd8  mov     [rsp+500h+var_488], r14
0x100838fdd  mov     [rsp+500h+var_490], r14
0x100838fe2  mov     [rbp+400h+var_480], r14
0x100838fe6  mov     [rbp+400h+var_470], r14b
0x100838fea  mov     rdx, gs:58h
0x100838ff3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100838ffa  mov     ecx, [rax]
0x100838ffc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100839003  mov     ebx, [rax]
0x100839005  add     rbx, [rdx+rcx*8]
0x100839009  mov     rcx, [rbx+100h]
0x100839010  test    rcx, rcx
0x100839013  jnz     short loc_100839022
0x100839015  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10083901b  mov     rcx, [rbx+100h]
0x100839022  mov     rcx, [rcx+258h]
0x100839029  test    rcx, rcx
0x10083902c  jz      short loc_10083903F
0x10083902e  lea     rdx, [rsp+500h+var_4A0]
0x100839033  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100839039  test    eax, eax
0x10083903b  setz    [rbp+400h+var_470]
0x10083903f  mov     rdx, gs:58h
0x100839048  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10083904f  mov     ecx, [rax]
0x100839051  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100839058  mov     ebx, [rax]
0x10083905a  add     rbx, [rdx+rcx*8]
0x10083905e  mov     rdx, [rbx+100h]
0x100839065  test    rdx, rdx
0x100839068  jnz     short loc_100839079
0x10083906a  xor     ecx, ecx
0x10083906c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100839072  mov     rdx, [rbx+100h]
0x100839079  mov     [rsp+500h+var_4A8], rdx
0x10083907e  mov     eax, [rdx+320h]
0x100839084  shr     eax, 0Bh
0x100839087  and     eax, 1
0x10083908a  mov     [rsp+500h+var_4AC], eax
0x10083908e  jnz     short loc_1008390A0
0x100839090  test    byte ptr [rdx+320h], 4
0x100839097  jz      short loc_1008390A0
0x100839099  mov     [rsp+500h+var_4B0], r14d
0x10083909e  jmp     short loc_1008390B6
0x1008390a0  mov     [rsp+500h+var_4B0], 1
0x1008390a8  mov     rcx, [rdx+260h]
0x1008390af  mov     rax, [rcx]
0x1008390b2  call    qword ptr [rax+8]
0x1008390b5  nop
0x1008390b6  xor     edx, edx; hFile
0x1008390b8  mov     r8d, 802h; dwFlags
0x1008390be  lea     rcx, aSgxUrtsDll_0; "sgx_urts.dll"
0x1008390c5  call    cs:__imp_LoadLibraryExW
0x1008390cb  test    rax, rax
0x1008390ce  jnz     short loc_100839110
0x1008390d0  call    cs:__imp_GetLastError
0x1008390d6  mov     r9d, eax
0x1008390d9  lea     r8, aSgxloadlibrary; "SgxLoadLibrary"
0x1008390e0  lea     rdx, aSgx; "SGX"
0x1008390e7  mov     ecx, 9275h; unsigned int
0x1008390ec  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1008390f1  nop
0x1008390f2  lea     rcx, [rsp+500h+var_4B0]; this
0x1008390f7  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1008390fc  nop
0x1008390fd  mov     edx, [rsp+500h+var_4C0]
0x100839101  not     edx
0x100839103  mov     rcx, [rsp+500h+var_4B8]
0x100839108  and     [rcx+268h], edx
0x10083910e  jmp     short loc_10083917C
0x100839110  mov     [rsp+500h+var_4D8], r14
0x100839115  lea     rax, [rbp+400h+var_460]
0x100839119  mov     [rsp+500h+var_4E0], rax
0x10083911e  lea     r9, [rsp+500h+var_4D0]
0x100839123  lea     r8, [rbp+400h+var_430]
0x100839127  xor     edx, edx
0x100839129  mov     rcx, rsi
0x10083912c  call    cs:__imp_sgx_create_enclavew
0x100839132  test    eax, eax
0x100839134  jz      short loc_100839158
0x100839136  mov     r8d, eax
0x100839139  lea     rdx, aSgx; "SGX"
0x100839140  mov     ecx, 91BAh; unsigned int
0x100839145  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10083914a  nop
0x10083914b  lea     rcx, [rsp+500h+var_4B0]; this
0x100839150  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100839155  nop
0x100839156  jmp     short loc_10083916B
0x100839158  mov     rax, [rbp+400h+var_460]
0x10083915c  mov     [rdi+10h], rax
0x100839160  lea     rcx, [rsp+500h+var_4B0]; this
0x100839165  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10083916a  nop
0x10083916b  mov     ecx, [rsp+500h+var_4C0]
0x10083916f  mov     rax, [rsp+500h+var_4B8]
0x100839174  not     ecx
0x100839176  and     [rax+268h], ecx
0x10083917c  mov     rcx, rsi
0x10083917f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100839185  nop
0x100839186  mov     rax, rdi
0x100839189  mov     rcx, [rbp+400h+var_30]
0x100839190  xor     rcx, rsp; StackCookie
0x100839193  call    __security_check_cookie
0x100839198  add     rsp, 4E0h
0x10083919f  pop     r14
0x1008391a1  pop     rdi
0x1008391a2  pop     rsi
0x1008391a3  pop     rbx
0x1008391a4  pop     rbp
0x1008391a5  retn
```
