# CVSMEnclave::CVSMEnclave(EnclaveConfiguration const &,IMemObj *)

- ea: `0x1008385d0`
- end: `0x100838aef`
- name: `??0CVSMEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z`
- size: `1311`
- prototype: `CVSMEnclave *__fastcall(CVSMEnclave *__hidden this, const struct EnclaveConfiguration *, struct IMemObj *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x100837ae0`

## callees

- `0x100401170`
- `0x10045f130`
- `0x1004c7420`
- `0x10082cad0`
- `0x1008376b0`
- `0x1008378d0`
- `0x1008385d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100838856`
- `KERNEL32!GetProcAddress` at `0x100838902`
- `KERNEL32!GetProcAddress` at `0x100838995`
- `KERNEL32!GetProcAddress` at `0x100838a23`
- `KERNEL32!GetProcAddress` at `0x100838a62`
- `KERNEL32!GetProcAddress` at `0x100838856`
- `KERNEL32!GetProcAddress` at `0x100838902`
- `KERNEL32!GetProcAddress` at `0x100838995`
- `KERNEL32!GetProcAddress` at `0x100838a23`
- `KERNEL32!GetProcAddress` at `0x100838a62`
- `KERNEL32!LoadLibraryW` at `0x1008387e1`
- `KERNEL32!LoadLibraryW` at `0x1008387e1`
- `KERNEL32!GetCurrentProcess` at `0x100838887`
- `KERNEL32!GetCurrentProcess` at `0x1008389c6`
- `KERNEL32!GetCurrentProcess` at `0x100838887`
- `KERNEL32!GetCurrentProcess` at `0x1008389c6`
- `KERNEL32!GetLastError` at `0x1008387ef`
- `KERNEL32!GetLastError` at `0x100838864`
- `KERNEL32!GetLastError` at `0x1008388c7`
- `KERNEL32!GetLastError` at `0x10083890d`
- `KERNEL32!GetLastError` at `0x10083894a`
- `KERNEL32!GetLastError` at `0x1008389a3`
- `KERNEL32!GetLastError` at `0x1008389e8`
- `KERNEL32!GetLastError` at `0x100838a35`
- `KERNEL32!GetLastError` at `0x100838a74`
- `KERNEL32!GetLastError` at `0x1008387ef`
- `KERNEL32!GetLastError` at `0x100838864`
- `KERNEL32!GetLastError` at `0x1008388c7`
- `KERNEL32!GetLastError` at `0x10083890d`
- `KERNEL32!GetLastError` at `0x10083894a`
- `KERNEL32!GetLastError` at `0x1008389a3`
- `KERNEL32!GetLastError` at `0x1008389e8`
- `KERNEL32!GetLastError` at `0x100838a35`
- `KERNEL32!GetLastError` at `0x100838a74`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10083875b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10083875b`
- `sqldk!??_V@YAXPEAX@Z` at `0x100838ac7`
- `sqldk!??_V@YAXPEAX@Z` at `0x100838ac7`
- `sqldk!SystemThread_TlsIndex` at `0x100838693`
- `sqldk!SystemThread_TlsIndex` at `0x10083871a`
- `sqldk!SystemThread_TlsIndex` at `0x100838770`
- `sqldk!SystemThread_TlsOffset` at `0x10083869c`
- `sqldk!SystemThread_TlsOffset` at `0x100838723`
- `sqldk!SystemThread_TlsOffset` at `0x100838779`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008386b7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083873e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838794`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1008386b7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10083873e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838794`

## string_xrefs

- `0x1008388d0`: `CreateVSMEnclave`
- `0x1008386cb`: `\aetm-enclave.vsm.pkg\aetm-enclave.dll`
- `0x1008387da`: `api-ms-win-core-enclave-l1-1-1.dll`
- `0x1008387f8`: `VsmLoadLibrary`
- `0x10083884c`: `CreateEnclave`
- `0x10083886d`: `CreateEnclaveProcAddress`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
CVSMEnclave *__fastcall CVSMEnclave::CVSMEnclave(
        CVSMEnclave *this,
        const struct EnclaveConfiguration *a2,
        struct IMemObj *a3)
{
  void *EnclavePath; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rdx
  HMODULE LibraryW; // rdi
  DWORD LastError; // eax
  FARPROC ProcAddress; // rsi
  DWORD v14; // eax
  HANDLE CurrentProcess; // rax
  HMODULE v16; // rsi
  DWORD v17; // eax
  FARPROC v18; // rax
  DWORD v19; // eax
  DWORD v20; // eax
  int v21; // eax
  FARPROC v22; // r15
  DWORD v23; // eax
  HANDLE v24; // rax
  DWORD v25; // eax
  FARPROC v26; // rax
  DWORD v27; // eax
  FARPROC v28; // rax
  DWORD v29; // eax
  _DWORD v31[4]; // [rsp+40h] [rbp-99h] BYREF
  int v32; // [rsp+50h] [rbp-89h] BYREF
  __int64 v33; // [rsp+58h] [rbp-81h]
  int v34; // [rsp+60h] [rbp-79h] BYREF
  int v35; // [rsp+64h] [rbp-75h]
  __int64 v36; // [rsp+68h] [rbp-71h]
  int v37; // [rsp+70h] [rbp-69h] BYREF
  __int64 v38; // [rsp+78h] [rbp-61h]
  __int64 v39; // [rsp+80h] [rbp-59h]
  __int64 v40; // [rsp+88h] [rbp-51h]
  __int64 v41; // [rsp+90h] [rbp-49h]
  bool v42; // [rsp+A0h] [rbp-39h]
  int *v43; // [rsp+B0h] [rbp-29h]
  __int64 v44; // [rsp+B8h] [rbp-21h]
  CVSMEnclave *v45; // [rsp+C0h] [rbp-19h]
  void *v46; // [rsp+C8h] [rbp-11h]
  int v47; // [rsp+D0h] [rbp-9h] BYREF
  const unsigned __int8 near *v48; // [rsp+D4h] [rbp-5h]
  __int128 v49; // [rsp+DCh] [rbp+3h]
  __int64 v50; // [rsp+ECh] [rbp+13h]

  v44 = -2;
  v45 = this;
  CEnclave::CEnclave(this, a2, a3);
  *(_QWORD *)this = &CVSMEnclave::`vftable';
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  v43 = (int *)((char *)this + 288);
  *((_QWORD *)this + 38) = (char *)this + 296;
  *((_QWORD *)this + 37) = (char *)this + 296;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 1;
  *((_DWORD *)this + 81) = 1;
  *((_QWORD *)this + 41) = 1;
  *((_QWORD *)this + 36) = &EventAutoInternal<SuspendQueueSLock>::`vftable';
  *((_QWORD *)this + 42) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *(_OWORD *)((char *)this + 360) = 0;
  *(_OWORD *)((char *)this + 376) = 0;
  *((_QWORD *)this + 49) = 0;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  EnclavePath = (void *)GetEnclavePath((wchar_t *)L"\\aetm-enclave.vsm.pkg\\aetm-enclave.dll");
  v46 = EnclavePath;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v32, 1);
  v43 = &v34;
  v37 = 536871501;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v42 = (unsigned int)SOS_Task::PushWait(v8, &v37) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v36 = v10;
  v35 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v35 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v34 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v34 = 0;
  }
  LibraryW = LoadLibraryW(L"api-ms-win-core-enclave-l1-1-1.dll");
  if ( !LibraryW )
  {
    LastError = GetLastError();
    scierrlog(0x9275u, L"VBS", L"VsmLoadLibrary", LastError);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
    goto LABEL_15;
  }
  v49 = 0;
  v50 = 0;
  v48 = CVSMEnclave::OwnerID;
  v47 = 0;
  ProcAddress = GetProcAddress(LibraryW, "CreateEnclave");
  if ( !ProcAddress )
  {
    v14 = GetLastError();
    scierrlog(0x9275u, L"VBS", L"CreateEnclaveProcAddress", v14);
LABEL_19:
    v17 = GetLastError();
    scierrlog(0x9275u, L"VBS", L"CreateVSMEnclave", v17);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
    goto LABEL_15;
  }
  CurrentProcess = GetCurrentProcess();
  v16 = (HMODULE)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64, _QWORD, int, int *, int, _QWORD))ProcAddress)(
                   CurrentProcess,
                   0,
                   0x100000000LL,
                   0,
                   16,
                   &v47,
                   36,
                   0);
  if ( !v16 )
    goto LABEL_19;
  v18 = GetProcAddress(LibraryW, "LoadEnclaveImageW");
  if ( v18 )
  {
    if ( ((unsigned __int8 (__fastcall *)(HMODULE, void *))v18)(v16, EnclavePath) )
    {
      v21 = *((_DWORD *)a2 + 1);
      v31[0] = 8;
      v31[1] = v21;
      v22 = GetProcAddress(LibraryW, "InitializeEnclave");
      if ( v22 )
      {
        v24 = GetCurrentProcess();
        if ( ((unsigned __int8 (__fastcall *)(HANDLE, HMODULE, _DWORD *, _QWORD, _QWORD))v22)(v24, v16, v31, v31[0], 0) )
        {
          v26 = GetProcAddress(v16, "DoWork");
          *((_QWORD *)this + 34) = v26;
          if ( v26 )
          {
            v28 = GetProcAddress(LibraryW, "CallEnclave");
            *((_QWORD *)this + 35) = v28;
            if ( !v28 )
            {
              v29 = GetLastError();
              scierrlog(0x9275u, L"VBS", L"CallEnclaveProcAddress", v29);
              AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
              goto LABEL_15;
            }
            *((_QWORD *)this + 1) = v16;
          }
          else
          {
            v27 = GetLastError();
            scierrlog(0x9275u, L"VBS", L"DoWork", v27);
          }
          AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
          *(_DWORD *)(v33 + 616) &= ~v32;
          goto LABEL_34;
        }
      }
      else
      {
        v23 = GetLastError();
        scierrlog(0x9275u, L"VBS", L"InitializeEnclaveProcAddress", v23);
      }
      v25 = GetLastError();
      scierrlog(0x9275u, L"VBS", L"InitializeVSMEnclave", v25);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
    }
    else
    {
      v20 = GetLastError();
      scierrlog(0x9275u, L"VBS", L"LoadEnclaveImage", v20);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
    }
  }
  else
  {
    v19 = GetLastError();
    scierrlog(0x9275u, L"VBS", L"LoadEnclaveImageProcAddress", v19);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
  }
LABEL_15:
  *(_DWORD *)(v33 + 616) &= ~v32;
LABEL_34:
  operator delete[](EnclavePath);
  return this;
}

```

## disassembly

```asm
0x1008385d0  push    rbp
0x1008385d2  push    rbx
0x1008385d3  push    rsi
0x1008385d4  push    rdi
0x1008385d5  push    r12
0x1008385d7  push    r14
0x1008385d9  push    r15
0x1008385db  lea     rbp, [rsp-27h]
0x1008385e0  sub     rsp, 100h
0x1008385e7  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x1008385ef  mov     rax, cs:__security_cookie
0x1008385f6  xor     rax, rsp
0x1008385f9  mov     [rbp+57h+var_38], rax
0x1008385fd  mov     r15, rdx
0x100838600  mov     r14, rcx
0x100838603  mov     [rbp+57h+var_70], rcx
0x100838607  call    ??0CEnclave@@QEAA@AEBUEnclaveConfiguration@@PEAVIMemObj@@@Z; CEnclave::CEnclave(EnclaveConfiguration const &,IMemObj *)
0x10083860c  nop
0x10083860d  lea     rax, ??_7CVSMEnclave@@6B@; const CVSMEnclave::`vftable'
0x100838614  mov     [r14], rax
0x100838617  xor     r12d, r12d
0x10083861a  mov     [r14+110h], r12
0x100838621  mov     [r14+118h], r12
0x100838628  lea     rcx, [r14+120h]
0x10083862f  mov     [rbp+57h+var_80], rcx
0x100838633  lea     rax, [rcx+8]
0x100838637  mov     [rax+8], rax
0x10083863b  mov     [rax], rax
0x10083863e  mov     [rcx+18h], r12
0x100838642  mov     dword ptr [rcx+20h], 1
0x100838649  mov     dword ptr [rcx+24h], 1
0x100838650  mov     qword ptr [rcx+28h], 1
0x100838658  lea     rax, ??_7?$EventAutoInternal@USuspendQueueSLock@@@@6B@; const EventAutoInternal<SuspendQueueSLock>::`vftable'
0x10083865f  mov     [rcx], rax
0x100838662  mov     [rcx+30h], r12
0x100838666  xorps   xmm0, xmm0
0x100838669  xor     eax, eax
0x10083866b  movups  xmmword ptr [r14+158h], xmm0
0x100838673  movups  xmmword ptr [r14+168h], xmm0
0x10083867b  movups  xmmword ptr [r14+178h], xmm0
0x100838683  mov     [r14+188h], rax
0x10083868a  mov     rdx, gs:58h
0x100838693  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10083869a  mov     ecx, [rax]
0x10083869c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1008386a3  mov     ebx, [rax]
0x1008386a5  add     rbx, [rdx+rcx*8]
0x1008386a9  mov     rdx, [rbx+100h]
0x1008386b0  test    rdx, rdx
0x1008386b3  jnz     short loc_1008386C4
0x1008386b5  xor     ecx, ecx
0x1008386b7  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008386bd  mov     rdx, [rbx+100h]
0x1008386c4  mov     rdx, [rdx+3E8h]
0x1008386cb  lea     rcx, aAetmEnclaveVsm_0; "\\aetm-enclave.vsm.pkg\\aetm-enclave.dl"...
0x1008386d2  call    GetEnclavePath
0x1008386d7  mov     rbx, rax
0x1008386da  mov     [rbp+57h+var_68], rax
0x1008386de  mov     edx, 1
0x1008386e3  lea     rcx, [rsp+130h+var_E0]
0x1008386e8  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1008386ed  nop
0x1008386ee  lea     rax, [rbp+57h+var_D0]
0x1008386f2  mov     [rbp+57h+var_80], rax
0x1008386f6  mov     [rbp+57h+var_C0], 2000024Dh
0x1008386fd  mov     [rbp+57h+var_B8], r12
0x100838701  mov     [rbp+57h+var_A8], r12
0x100838705  mov     [rbp+57h+var_B0], r12
0x100838709  mov     [rbp+57h+var_A0], r12
0x10083870d  mov     [rbp+57h+var_90], 0
0x100838711  mov     rdx, gs:58h
0x10083871a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100838721  mov     ecx, [rax]
0x100838723  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10083872a  mov     edi, [rax]
0x10083872c  add     rdi, [rdx+rcx*8]
0x100838730  mov     rax, [rdi+100h]
0x100838737  test    rax, rax
0x10083873a  jnz     short loc_10083874B
0x10083873c  xor     ecx, ecx
0x10083873e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100838744  mov     rax, [rdi+100h]
0x10083874b  mov     rcx, [rax+258h]
0x100838752  test    rcx, rcx
0x100838755  jz      short loc_100838767
0x100838757  lea     rdx, [rbp+57h+var_C0]
0x10083875b  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100838761  test    eax, eax
0x100838763  setz    [rbp+57h+var_90]
0x100838767  mov     rdx, gs:58h
0x100838770  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100838777  mov     ecx, [rax]
0x100838779  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100838780  mov     edi, [rax]
0x100838782  add     rdi, [rdx+rcx*8]
0x100838786  mov     rdx, [rdi+100h]
0x10083878d  test    rdx, rdx
0x100838790  jnz     short loc_1008387A1
0x100838792  xor     ecx, ecx
0x100838794  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10083879a  mov     rdx, [rdi+100h]
0x1008387a1  mov     [rbp+57h+var_C8], rdx
0x1008387a5  mov     eax, [rdx+320h]
0x1008387ab  shr     eax, 0Bh
0x1008387ae  and     eax, 1
0x1008387b1  mov     [rbp+57h+var_CC], eax
0x1008387b4  jnz     short loc_1008387C5
0x1008387b6  test    byte ptr [rdx+320h], 4
0x1008387bd  jz      short loc_1008387C5
0x1008387bf  mov     [rbp+57h+var_D0], r12d
0x1008387c3  jmp     short loc_1008387DA
0x1008387c5  mov     [rbp+57h+var_D0], 1
0x1008387cc  mov     rcx, [rdx+260h]
0x1008387d3  mov     rax, [rcx]
0x1008387d6  call    qword ptr [rax+8]
0x1008387d9  nop
0x1008387da  lea     rcx, LibFileName; "api-ms-win-core-enclave-l1-1-1.dll"
0x1008387e1  call    cs:__imp_LoadLibraryW
0x1008387e7  mov     rdi, rax
0x1008387ea  test    rax, rax
0x1008387ed  jnz     short loc_100838831
0x1008387ef  call    cs:__imp_GetLastError
0x1008387f5  mov     r9d, eax
0x1008387f8  lea     r8, aVsmloadlibrary; "VsmLoadLibrary"
0x1008387ff  lea     rdx, aVbs; "VBS"
0x100838806  mov     ecx, 9275h; unsigned int
0x10083880b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838810  nop
0x100838811  lea     rcx, [rbp+57h+var_D0]; this
0x100838815  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10083881a  nop
0x10083881b  mov     ecx, [rsp+130h+var_E0]
0x10083881f  not     ecx
0x100838821  mov     rax, [rsp+130h+var_D8]
0x100838826  and     [rax+268h], ecx
0x10083882c  jmp     loc_100838AC4
0x100838831  xorps   xmm0, xmm0
0x100838834  movdqu  [rbp+57h+var_54], xmm0
0x100838839  mov     [rbp+57h+var_44], r12
0x10083883d  mov     rax, cs:?OwnerID@CVSMEnclave@@0QBEB; uchar const near * const CVSMEnclave::OwnerID
0x100838844  mov     [rbp+57h+var_5C], rax
0x100838848  mov     [rbp+57h+var_60], r12d
0x10083884c  lea     rdx, aCreateenclave; "CreateEnclave"
0x100838853  mov     rcx, rdi; hModule
0x100838856  call    cs:__imp_GetProcAddress
0x10083885c  mov     rsi, rax
0x10083885f  test    rax, rax
0x100838862  jnz     short loc_100838887
0x100838864  call    cs:__imp_GetLastError
0x10083886a  mov     r9d, eax
0x10083886d  lea     r8, aCreateenclavep; "CreateEnclaveProcAddress"
0x100838874  lea     rdx, aVbs; "VBS"
0x10083887b  mov     ecx, 9275h; unsigned int
0x100838880  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838885  jmp     short loc_1008388C7
0x100838887  call    cs:__imp_GetCurrentProcess
0x10083888d  mov     rcx, rax
0x100838890  mov     [rsp+130h+var_F8], r12
0x100838895  mov     [rsp+130h+var_100], 24h ; '$'
0x10083889d  lea     rax, [rbp+57h+var_60]
0x1008388a1  mov     [rsp+130h+var_108], rax
0x1008388a6  mov     dword ptr [rsp+130h+var_110], 10h
0x1008388ae  xor     r9d, r9d
0x1008388b1  xor     edx, edx
0x1008388b3  mov     r8, 100000000h
0x1008388bd  call    rsi
0x1008388bf  mov     rsi, rax
0x1008388c2  test    rax, rax
0x1008388c5  jnz     short loc_1008388F8
0x1008388c7  call    cs:__imp_GetLastError
0x1008388cd  mov     r9d, eax
0x1008388d0  lea     r8, aCreatevsmencla; "CreateVSMEnclave"
0x1008388d7  lea     rdx, aVbs; "VBS"
0x1008388de  mov     ecx, 9275h; unsigned int
0x1008388e3  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1008388e8  nop
0x1008388e9  lea     rcx, [rbp+57h+var_D0]; this
0x1008388ed  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1008388f2  nop
0x1008388f3  jmp     loc_10083881B
0x1008388f8  lea     rdx, aLoadenclaveima_0; "LoadEnclaveImageW"
0x1008388ff  mov     rcx, rdi; hModule
0x100838902  call    cs:__imp_GetProcAddress
0x100838908  test    rax, rax
0x10083890b  jnz     short loc_10083893E
0x10083890d  call    cs:__imp_GetLastError
0x100838913  mov     r9d, eax
0x100838916  lea     r8, aLoadenclaveima; "LoadEnclaveImageProcAddress"
0x10083891d  lea     rdx, aVbs; "VBS"
0x100838924  mov     ecx, 9275h; unsigned int
0x100838929  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10083892e  nop
0x10083892f  lea     rcx, [rbp+57h+var_D0]; this
0x100838933  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100838938  nop
0x100838939  jmp     loc_10083881B
0x10083893e  mov     rdx, rbx
0x100838941  mov     rcx, rsi
0x100838944  call    rax
0x100838946  test    al, al
0x100838948  jnz     short loc_10083897B
0x10083894a  call    cs:__imp_GetLastError
0x100838950  mov     r9d, eax
0x100838953  lea     r8, aLoadenclaveima_1; "LoadEnclaveImage"
0x10083895a  lea     rdx, aVbs; "VBS"
0x100838961  mov     ecx, 9275h; unsigned int
0x100838966  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10083896b  nop
0x10083896c  lea     rcx, [rbp+57h+var_D0]; this
0x100838970  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100838975  nop
0x100838976  jmp     loc_10083881B
0x10083897b  mov     eax, [r15+4]
0x10083897f  mov     [rsp+130h+var_F0], 8
0x100838987  mov     [rsp+130h+var_EC], eax
0x10083898b  lea     rdx, aInitializeencl; "InitializeEnclave"
0x100838992  mov     rcx, rdi; hModule
0x100838995  call    cs:__imp_GetProcAddress
0x10083899b  mov     r15, rax
0x10083899e  test    rax, rax
0x1008389a1  jnz     short loc_1008389C6
0x1008389a3  call    cs:__imp_GetLastError
0x1008389a9  mov     r9d, eax
0x1008389ac  lea     r8, aInitializeencl_0; "InitializeEnclaveProcAddress"
0x1008389b3  lea     rdx, aVbs; "VBS"
0x1008389ba  mov     ecx, 9275h; unsigned int
0x1008389bf  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1008389c4  jmp     short loc_1008389E8
0x1008389c6  call    cs:__imp_GetCurrentProcess
0x1008389cc  mov     rcx, rax
0x1008389cf  mov     [rsp+130h+var_110], r12
0x1008389d4  mov     r9d, [rsp+130h+var_F0]
0x1008389d9  lea     r8, [rsp+130h+var_F0]
0x1008389de  mov     rdx, rsi
0x1008389e1  call    r15
0x1008389e4  test    al, al
0x1008389e6  jnz     short loc_100838A19
0x1008389e8  call    cs:__imp_GetLastError
0x1008389ee  mov     r9d, eax
0x1008389f1  lea     r8, aInitializevsme; "InitializeVSMEnclave"
0x1008389f8  lea     rdx, aVbs; "VBS"
0x1008389ff  mov     ecx, 9275h; unsigned int
0x100838a04  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838a09  nop
0x100838a0a  lea     rcx, [rbp+57h+var_D0]; this
0x100838a0e  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100838a13  nop
0x100838a14  jmp     loc_10083881B
0x100838a19  lea     rdx, aDowork; "DoWork"
0x100838a20  mov     rcx, rsi; hModule
0x100838a23  call    cs:__imp_GetProcAddress
0x100838a29  mov     [r14+110h], rax
0x100838a30  test    rax, rax
0x100838a33  jnz     short loc_100838A58
0x100838a35  call    cs:__imp_GetLastError
0x100838a3b  mov     r9d, eax
0x100838a3e  lea     r8, aDowork_0; "DoWork"
0x100838a45  lea     rdx, aVbs; "VBS"
0x100838a4c  mov     ecx, 9275h; unsigned int
0x100838a51  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838a56  jmp     short loc_100838AA9
0x100838a58  lea     rdx, aCallenclave; "CallEnclave"
0x100838a5f  mov     rcx, rdi; hModule
0x100838a62  call    cs:__imp_GetProcAddress
0x100838a68  mov     [r14+118h], rax
0x100838a6f  test    rax, rax
0x100838a72  jnz     short loc_100838AA5
0x100838a74  call    cs:__imp_GetLastError
0x100838a7a  mov     r9d, eax
0x100838a7d  lea     r8, aCallenclavepro; "CallEnclaveProcAddress"
0x100838a84  lea     rdx, aVbs; "VBS"
0x100838a8b  mov     ecx, 9275h; unsigned int
0x100838a90  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838a95  nop
0x100838a96  lea     rcx, [rbp+57h+var_D0]; this
0x100838a9a  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100838a9f  nop
0x100838aa0  jmp     loc_10083881B
0x100838aa5  mov     [r14+8], rsi
0x100838aa9  lea     rcx, [rbp+57h+var_D0]; this
0x100838aad  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x100838ab2  nop
0x100838ab3  mov     edx, [rsp+130h+var_E0]
0x100838ab7  not     edx
0x100838ab9  mov     rcx, [rsp+130h+var_D8]
0x100838abe  and     [rcx+268h], edx
0x100838ac4  mov     rcx, rbx
0x100838ac7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100838acd  nop
0x100838ace  mov     rax, r14
0x100838ad1  mov     rcx, [rbp+57h+var_38]
0x100838ad5  xor     rcx, rsp; StackCookie
0x100838ad8  call    __security_check_cookie
0x100838add  add     rsp, 100h
0x100838ae4  pop     r15
0x100838ae6  pop     r14
0x100838ae8  pop     r12
0x100838aea  pop     rdi
0x100838aeb  pop     rsi
0x100838aec  pop     rbx
  ... truncated ...
```
