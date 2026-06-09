# CSimulatorEnclave::CSimulatorEnclave(EnclaveConfiguration const &,IMemObj *)

- ea: `0x1008392b0`
- end: `0x100839528`
- name: `??0CSimulatorEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z`
- size: `632`
- prototype: `CSimulatorEnclave *__fastcall(CSimulatorEnclave *__hidden this, const struct EnclaveConfiguration *, struct IMemObj *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x100837ae0`

## callees

- `0x10045f130`
- `0x1004c7420`
- `0x10082cad0`
- `0x1008376b0`
- `0x1008378d0`
- `0x1008392b0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10083949f`
- `KERNEL32!GetProcAddress` at `0x10083949f`
- `KERNEL32!LoadLibraryW` at `0x100839448`
- `KERNEL32!LoadLibraryW` at `0x100839448`
- `KERNEL32!GetLastError` at `0x10083946e`
- `KERNEL32!GetLastError` at `0x1008394c9`
- `KERNEL32!GetLastError` at `0x10083946e`
- `KERNEL32!GetLastError` at `0x1008394c9`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1008393c6`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1008393c6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100839510`
- `sqldk!??_V@YAXPEAX@Z` at `0x100839510`
- `sqldk!SystemThread_TlsIndex` at `0x100839301`
- `sqldk!SystemThread_TlsIndex` at `0x100839387`
- `sqldk!SystemThread_TlsIndex` at `0x1008393db`
- `sqldk!SystemThread_TlsOffset` at `0x10083930a`
- `sqldk!SystemThread_TlsOffset` at `0x100839390`
- `sqldk!SystemThread_TlsOffset` at `0x1008393e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100839325`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008393a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008393ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100839325`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008393a9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008393ff`

## string_xrefs

- `0x100839339`: `\aetm-enclave.vsm.pkg\aetm-enclave-Simulator.dll`
- `0x100839456`: `LoadLibrary`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CSimulatorEnclave *__fastcall CSimulatorEnclave::CSimulatorEnclave(
        CSimulatorEnclave *this,
        const struct EnclaveConfiguration *a2,
        struct IMemObj *a3)
{
  WCHAR *EnclavePath; // rsi
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  HMODULE LibraryW; // rax
  HMODULE v12; // rbx
  DWORD v13; // eax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  int v17; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+38h] [rbp-21h]
  int v19; // [rsp+40h] [rbp-19h] BYREF
  int v20; // [rsp+44h] [rbp-15h]
  __int64 v21; // [rsp+48h] [rbp-11h]
  int v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h]
  __int64 v24; // [rsp+60h] [rbp+7h]
  __int64 v25; // [rsp+68h] [rbp+Fh]
  __int64 v26; // [rsp+70h] [rbp+17h]
  bool v27; // [rsp+80h] [rbp+27h]

  CEnclave::CEnclave(this, a2, a3);
  *(_QWORD *)this = &CSimulatorEnclave::`vftable';
  *((_QWORD *)this + 34) = 0;
  if ( *(_DWORD *)a2 != 4 )
  {
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 256LL) )
      SystemThread::MakeMiniSOSThread(0);
    EnclavePath = (WCHAR *)GetEnclavePath((wchar_t *)L"\\aetm-enclave.vsm.pkg\\aetm-enclave-Simulator.dll");
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v17, 1);
    v22 = 536871501;
    v23 = 0;
    v25 = 0;
    v24 = 0;
    v26 = 0;
    v27 = 0;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = *(_QWORD *)(v7 + 600);
    if ( v8 )
      v27 = (unsigned int)SOS_Task::PushWait(v8, &v22) == 0;
    v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v10 = *(_QWORD *)(v9 + 256);
    if ( !v10 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v10 = *(_QWORD *)(v9 + 256);
    }
    v21 = v10;
    v20 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
    if ( v20 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
    {
      v19 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
    }
    else
    {
      v19 = 0;
    }
    LibraryW = LoadLibraryW(EnclavePath);
    v12 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "DoWork");
      *((_QWORD *)this + 34) = ProcAddress;
      if ( ProcAddress )
      {
        *((_QWORD *)this + 1) = v12;
      }
      else
      {
        scierrlog(0x91BBu, L"Simulator", L"DoWorkProcAddress");
        LastError = GetLastError();
        scierrlog(0x91BAu, L"Simulator", LastError);
      }
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v19);
    }
    else
    {
      scierrlog(0x91BBu, L"Simulator", L"LoadLibrary");
      v13 = GetLastError();
      scierrlog(0x91BAu, L"Simulator", v13);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v19);
    }
    *(_DWORD *)(v18 + 616) &= ~v17;
    operator delete[](EnclavePath);
  }
  return this;
}

```

## disassembly

```asm
0x1008392b0  mov     [rsp-8+arg_0], rcx
0x1008392b5  push    rbp
0x1008392b6  push    rbx
0x1008392b7  push    rsi
0x1008392b8  push    rdi
0x1008392b9  push    r14
0x1008392bb  lea     rbp, [rsp-37h]
0x1008392c0  sub     rsp, 90h
0x1008392c7  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1008392cf  mov     rbx, rdx
0x1008392d2  mov     rdi, rcx
0x1008392d5  call    ??0CEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CEnclave::CEnclave(EnclaveConfiguration const &,IMemObj *)
0x1008392da  nop
0x1008392db  lea     rax, ??_7CSimulatorEnclave@@6B@; const CSimulatorEnclave::`vftable'
0x1008392e2  mov     [rdi], rax
0x1008392e5  xor     r14d, r14d
0x1008392e8  mov     [rdi+110h], r14
0x1008392ef  cmp     dword ptr [rbx], 4
0x1008392f2  jz      loc_100839517
0x1008392f8  mov     rdx, gs:58h
0x100839301  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100839308  mov     ecx, [rax]
0x10083930a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100839311  mov     ebx, [rax]
0x100839313  add     rbx, [rdx+rcx*8]
0x100839317  mov     rdx, [rbx+100h]
0x10083931e  test    rdx, rdx
0x100839321  jnz     short loc_100839332
0x100839323  xor     ecx, ecx
0x100839325  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10083932b  mov     rdx, [rbx+100h]
0x100839332  mov     rdx, [rdx+3E8h]
0x100839339  lea     rcx, aAetmEnclaveVsm; "\\aetm-enclave.vsm.pkg\\aetm-enclave-Si"...
0x100839340  call    GetEnclavePath
0x100839345  mov     rsi, rax
0x100839348  mov     [rbp+57h+arg_8], rax
0x10083934c  mov     edx, 1
0x100839351  lea     rcx, [rbp+57h+var_80]
0x100839355  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10083935a  nop
0x10083935b  lea     rax, [rbp+57h+var_70]
0x10083935f  mov     [rbp+57h+arg_18], rax
0x100839363  mov     [rbp+57h+var_60], 2000024Dh
0x10083936a  mov     [rbp+57h+var_58], r14
0x10083936e  mov     [rbp+57h+var_48], r14
0x100839372  mov     [rbp+57h+var_50], r14
0x100839376  mov     [rbp+57h+var_40], r14
0x10083937a  mov     [rbp+57h+var_30], 0
0x10083937e  mov     rdx, gs:58h
0x100839387  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10083938e  mov     ecx, [rax]
0x100839390  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100839397  mov     ebx, [rax]
0x100839399  add     rbx, [rdx+rcx*8]
0x10083939d  mov     rcx, [rbx+100h]
0x1008393a4  test    rcx, rcx
0x1008393a7  jnz     short loc_1008393B6
0x1008393a9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008393af  mov     rcx, [rbx+100h]
0x1008393b6  mov     rcx, [rcx+258h]
0x1008393bd  test    rcx, rcx
0x1008393c0  jz      short loc_1008393D2
0x1008393c2  lea     rdx, [rbp+57h+var_60]
0x1008393c6  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1008393cc  test    eax, eax
0x1008393ce  setz    [rbp+57h+var_30]
0x1008393d2  mov     rdx, gs:58h
0x1008393db  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1008393e2  mov     ecx, [rax]
0x1008393e4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008393eb  mov     ebx, [rax]
0x1008393ed  add     rbx, [rdx+rcx*8]
0x1008393f1  mov     rdx, [rbx+100h]
0x1008393f8  test    rdx, rdx
0x1008393fb  jnz     short loc_10083940C
0x1008393fd  xor     ecx, ecx
0x1008393ff  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100839405  mov     rdx, [rbx+100h]
0x10083940c  mov     [rbp+57h+var_68], rdx
0x100839410  mov     eax, [rdx+320h]
0x100839416  shr     eax, 0Bh
0x100839419  and     eax, 1
0x10083941c  mov     [rbp+57h+var_6C], eax
0x10083941f  jnz     short loc_100839430
0x100839421  test    byte ptr [rdx+320h], 4
0x100839428  jz      short loc_100839430
0x10083942a  mov     [rbp+57h+var_70], r14d
0x10083942e  jmp     short loc_100839445
0x100839430  mov     [rbp+57h+var_70], 1
0x100839437  mov     rcx, [rdx+260h]
0x10083943e  mov     rax, [rcx]
0x100839441  call    qword ptr [rax+8]
0x100839444  nop
0x100839445  mov     rcx, rsi; lpLibFileName
0x100839448  call    cs:__imp_LoadLibraryW
0x10083944e  mov     rbx, rax
0x100839451  test    rax, rax
0x100839454  jnz     short loc_100839495
0x100839456  lea     r8, aLoadlibrary; "LoadLibrary"
0x10083945d  lea     rdx, aSimulator; "Simulator"
0x100839464  mov     ecx, 91BBh; unsigned int
0x100839469  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10083946e  call    cs:__imp_GetLastError
0x100839474  mov     r8d, eax
0x100839477  lea     rdx, aSimulator; "Simulator"
0x10083947e  mov     ecx, 91BAh; unsigned int
0x100839483  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100839488  nop
0x100839489  lea     rcx, [rbp+57h+var_70]; this
0x10083948d  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100839492  nop
0x100839493  jmp     short loc_1008394FE
0x100839495  lea     rdx, aDowork; "DoWork"
0x10083949c  mov     rcx, rbx; hModule
0x10083949f  call    cs:__imp_GetProcAddress
0x1008394a5  mov     [rdi+110h], rax
0x1008394ac  test    rax, rax
0x1008394af  jnz     short loc_1008394F0
0x1008394b1  lea     r8, aDoworkprocaddr; "DoWorkProcAddress"
0x1008394b8  lea     rdx, aSimulator; "Simulator"
0x1008394bf  mov     ecx, 91BBh; unsigned int
0x1008394c4  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1008394c9  call    cs:__imp_GetLastError
0x1008394cf  mov     r8d, eax
0x1008394d2  lea     rdx, aSimulator; "Simulator"
0x1008394d9  mov     ecx, 91BAh; unsigned int
0x1008394de  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1008394e3  nop
0x1008394e4  lea     rcx, [rbp+57h+var_70]; this
0x1008394e8  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1008394ed  nop
0x1008394ee  jmp     short loc_1008394FE
0x1008394f0  mov     [rdi+8], rbx
0x1008394f4  lea     rcx, [rbp+57h+var_70]; this
0x1008394f8  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1008394fd  nop
0x1008394fe  mov     ecx, [rbp+57h+var_80]
0x100839501  mov     rax, [rbp+57h+var_78]
0x100839505  not     ecx
0x100839507  and     [rax+268h], ecx
0x10083950d  mov     rcx, rsi
0x100839510  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100839516  nop
0x100839517  mov     rax, rdi
0x10083951a  add     rsp, 90h
0x100839521  pop     r14
0x100839523  pop     rdi
0x100839524  pop     rsi
0x100839525  pop     rbx
0x100839526  pop     rbp
0x100839527  retn
```
