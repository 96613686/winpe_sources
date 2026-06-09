# CRecoMaster::PerformTask(CRecoInst *,_ENGINETASK *)

- ea: `0x180132970`
- end: `0x180132e04`
- name: `?PerformTask@CRecoMaster@@UEAAJPEAVCRecoInst@@PEAU_ENGINETASK@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this, struct CRecoInst *, struct _ENGINETASK *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013ec0`
- `0x180026508`
- `0x18003a138`
- `0x180051cd8`
- `0x18005abb0`
- `0x180061774`
- `0x18012ae14`
- `0x18012c110`
- `0x18012e648`
- `0x18012f4bc`
- `0x180131ce4`
- `0x180132970`
- `0x180132e0c`
- `0x18013319c`
- `0x180133804`
- `0x180136e0c`
- `0x180136f74`
- `0x18016f298`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801329f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801329f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132aa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132af5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132c2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132deb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132aa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132af5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132c2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180132deb`

## string_xrefs

- `0x180132a2d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132a84`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132ad6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132b2b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132b87`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132c0d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132c69`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180132dcc`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x1801329ae`: `Do StartAvailabilityAssurance for processId: %d, task: %d`
- `0x180132d93`: `Queuing pending task '%S' (%u)`

## pseudocode

```c
__int64 __fastcall CRecoMaster::PerformTask(CRecoMaster *this, struct CRecoInst *a2, struct _ENGINETASK *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  char v14; // r14
  int v15; // eax
  struct CSRTask *v16; // r10
  enum SPRECOSTATE v17; // r8d
  int v18; // eax
  int ShouldStopStream; // eax
  struct CSRTask **v20; // r11
  const struct CSRTask **v21; // rdi
  __int64 v22; // r11
  const struct CSRTask *v23; // rdx
  __int64 v24; // rdx
  unsigned int v25; // r9d
  const wchar_t *v26; // rax
  int v27; // r9d
  int v28; // eax
  struct CSRTask *v29; // [rsp+20h] [rbp-30h] BYREF
  struct CSRTask **v30; // [rsp+28h] [rbp-28h] BYREF
  __int64 v31; // [rsp+30h] [rbp-20h]
  CRecoMaster *v32; // [rsp+38h] [rbp-18h]
  struct CRecoInst **v33; // [rsp+40h] [rbp-10h]
  char v34; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  char v36; // [rsp+80h] [rbp+30h] BYREF
  struct CRecoInst *v37; // [rsp+88h] [rbp+38h] BYREF
  char v38; // [rsp+98h] [rbp+48h] BYREF

  v37 = a2;
  v32 = this;
  v33 = &v37;
  v34 = 1;
  if ( (unsigned int)CRecoMaster::IsStartAvailabilityAssuranceAllowed(this, a2, a3) )
  {
    DoTraceMessage(8, "Do StartAvailabilityAssurance for processId: %d, task: %d", *((_DWORD *)a2 + 284), *(_DWORD *)a3);
    _InterlockedExchange((volatile __int32 *)this + 388, *((_DWORD *)a2 + 284));
    (*(void (__fastcall **)(CRecoMaster *))(*(_QWORD *)this + 352LL))(this);
  }
  v31 = ((unsigned __int64)this + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  v6 = (struct _RTL_CRITICAL_SECTION *)(v31 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
  v36 = 0;
  v38 = 0;
  v29 = 0;
  v30 = &v29;
  v7 = wil::ResultFromException__lambda_c650ed23cead0c7c654945ffe0851144___(&v30);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)v7,
      (int)v29);
    std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
    LeaveCriticalSection(v6);
    CRecoMaster::EndAvailabilityAssurance(this, v37);
    return v8;
  }
  v10 = CSRTask::Init(v29, v37, a3);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)v10,
      (int)v29);
    std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
    LeaveCriticalSection(v6);
    CRecoMaster::EndAvailabilityAssurance(this, v37);
    return v8;
  }
  v11 = CRecoMaster::PerformTask_ProcessBookmarks(this, &v29, &v38);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)v11,
      (int)v29);
    std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
    LeaveCriticalSection(v6);
    CRecoMaster::EndAvailabilityAssurance(this, v37);
    return v8;
  }
  v12 = CRecoMaster::PerformTask_ArbiterTasks(this, &v29, &v36);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)v12,
      (int)v29);
    std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
    LeaveCriticalSection(v6);
    CRecoMaster::EndAvailabilityAssurance(this, v37);
    return v8;
  }
  v14 = v38;
  LOBYTE(v13) = v38;
  v15 = CRecoMaster::PerformTask_ImmediateTasks(this, &v29, v13, &v36);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
      (const char *)(unsigned int)v15,
      (int)v29);
    std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
    LeaveCriticalSection(v6);
    CRecoMaster::EndAvailabilityAssurance(this, v37);
    return v8;
  }
  v16 = v29;
  if ( *((_DWORD *)v29 + 4) == 32 )
  {
    if ( *((_BYTE *)this + 181) )
    {
      v17 = *((_DWORD *)v29 + 1064);
      if ( v17 == SPRST_INACTIVE || v17 == SPRST_INACTIVE_WITH_PURGE )
      {
        v18 = CRecoMaster::ChangeRecoInstState(this, *((struct CRecoInst **)v29 + 1), v17, 0);
        v8 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25D,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
            (const char *)(unsigned int)v18,
            (int)v29);
          std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
          LeaveCriticalSection(v6);
          CRecoMaster::EndAvailabilityAssurance(this, v37);
          return v8;
        }
        ShouldStopStream = CRecoMaster::ShouldStopStream(
                             this,
                             *((struct CRecoInst **)v29 + 1),
                             (enum SPRECOSTATE)*((_DWORD *)v29 + 1064));
        v8 = ShouldStopStream;
        if ( ShouldStopStream < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25E,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
            (const char *)(unsigned int)ShouldStopStream,
            (int)v29);
          std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
          LeaveCriticalSection(v6);
          CRecoMaster::EndAvailabilityAssurance(this, v37);
          return v8;
        }
        v16 = v29;
      }
    }
  }
  if ( v36 )
  {
    v29 = 0;
    CSpProducerConsumerIOCompletionQueue<CSREvent,1>::InsertTail((char *)this + 560, v16);
  }
  else
  {
    if ( v14 )
    {
      v20 = (struct CSRTask **)((char *)this + 736);
      v29 = 0;
      v21 = (const struct CSRTask **)*((_QWORD *)this + 92);
      if ( v21 )
      {
        if ( (int)CSRTask::Compare(v16, *((const struct CSRTask **)this + 93)) >= 0 )
        {
          *(_QWORD *)v16 = 0;
          **(_QWORD **)(v22 + 8) = v16;
          *(_QWORD *)(v22 + 8) = v16;
          goto LABEL_25;
        }
        v23 = (const struct CSRTask *)v21;
        while ( (int)CSRTask::Compare(v16, v23) >= 0 )
        {
          v23 = *v21;
          v21 = (const struct CSRTask **)*v21;
        }
        *(_QWORD *)v16 = v24;
      }
      else
      {
        *(_QWORD *)v16 = 0;
        *((_QWORD *)this + 93) = v16;
      }
      *v20 = v16;
      goto LABEL_25;
    }
    if ( *((_BYTE *)this + 181)
      && !(unsigned int)CSRTask::IsAsyncTask(*((unsigned int *)v16 + 4))
      && v25 != 18
      && v25 != 29 )
    {
      v26 = (const wchar_t *)SpEngineTaskIdToString(v25);
      DoTraceMessage(8, "Queuing pending task '%S' (%u)", v26, v27);
      v16 = v29;
    }
    v29 = 0;
    v28 = CRecoMaster::QueuePendingTask(this, v16);
    v8 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
        (const char *)(unsigned int)v28,
        (int)v29);
      std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
      LeaveCriticalSection(v6);
      CRecoMaster::EndAvailabilityAssurance(this, v37);
      return v8;
    }
  }
LABEL_25:
  std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(&v29);
  LeaveCriticalSection(v6);
  CRecoMaster::EndAvailabilityAssurance(this, v37);
  return 0;
}

```

## disassembly

```asm
0x180132970  mov     [rsp-28h+arg_8], rdx
0x180132975  push    rbp
0x180132976  push    rbx
0x180132977  push    rsi
0x180132978  push    rdi
0x180132979  push    r14
0x18013297b  mov     rbp, rsp
0x18013297e  sub     rsp, 50h
0x180132982  mov     r14, r8
0x180132985  mov     rdi, rdx
0x180132988  mov     rbx, rcx
0x18013298b  mov     [rbp+var_18], rcx
0x18013298f  lea     rax, [rbp+arg_8]
0x180132993  mov     [rbp+var_10], rax
0x180132997  mov     [rbp+var_8], 1
0x18013299b  call    ?IsStartAvailabilityAssuranceAllowed@CRecoMaster@@AEAAHPEAVCRecoInst@@PEAU_ENGINETASK@@@Z; CRecoMaster::IsStartAvailabilityAssuranceAllowed(CRecoInst *,_ENGINETASK *)
0x1801329a0  test    eax, eax
0x1801329a2  jz      short loc_1801329DD
0x1801329a4  mov     r9d, [r14]
0x1801329a7  mov     r8d, [rdi+470h]
0x1801329ae  lea     rdx, aDoStartavailab; "Do StartAvailabilityAssurance for proce"...
0x1801329b5  mov     ecx, 8; int
0x1801329ba  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801329bf  mov     eax, [rdi+470h]
0x1801329c5  xchg    eax, [rbx+610h]
0x1801329cb  mov     rcx, [rbx]
0x1801329ce  mov     rax, [rcx+160h]
0x1801329d5  mov     rcx, rbx
0x1801329d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801329dd  mov     rax, rbx
0x1801329e0  lea     rcx, [rbx+30h]
0x1801329e4  neg     rax
0x1801329e7  sbb     rdx, rdx
0x1801329ea  and     rdx, rcx
0x1801329ed  mov     [rbp+var_20], rdx
0x1801329f1  lea     rsi, [rdx+8]
0x1801329f5  mov     rcx, rsi; lpCriticalSection
0x1801329f8  call    cs:__imp_EnterCriticalSection
0x1801329fe  nop
0x1801329ff  mov     [rbp+arg_0], 0
0x180132a03  mov     [rbp+arg_18], 0
0x180132a07  mov     [rbp+var_30], 0
0x180132a0f  lea     rax, [rbp+var_30]
0x180132a13  mov     [rbp+var_28], rax
0x180132a17  lea     rcx, [rbp+var_28]
0x180132a1b  call    wil__ResultFromException__lambda_c650ed23cead0c7c654945ffe0851144___
0x180132a20  mov     edi, eax
0x180132a22  test    eax, eax
0x180132a24  jns     short loc_180132A67
0x180132a26  mov     rcx, [rbp+28h]; this
0x180132a2a  mov     r9d, eax; char *
0x180132a2d  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132a34  mov     edx, 24Bh; void *
0x180132a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132a3e  nop
0x180132a3f  lea     rcx, [rbp+var_30]
0x180132a43  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132a48  nop
0x180132a49  mov     rcx, rsi; lpCriticalSection
0x180132a4c  call    cs:__imp_LeaveCriticalSection
0x180132a52  nop
0x180132a53  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132a57  mov     rcx, rbx; this
0x180132a5a  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132a5f  nop
0x180132a60  mov     eax, edi
0x180132a62  jmp     loc_180132CE6
0x180132a67  mov     r8, r14; struct _ENGINETASK *
0x180132a6a  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132a6e  mov     rcx, [rbp+var_30]; this
0x180132a72  call    ?Init@CSRTask@@QEAAJPEAVCRecoInst@@PEBU_ENGINETASK@@@Z; CSRTask::Init(CRecoInst *,_ENGINETASK const *)
0x180132a77  mov     edi, eax
0x180132a79  test    eax, eax
0x180132a7b  jns     short loc_180132AB9
0x180132a7d  mov     rcx, [rbp+28h]; this
0x180132a81  mov     r9d, eax; char *
0x180132a84  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132a8b  mov     edx, 24Ch; void *
0x180132a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132a95  nop
0x180132a96  lea     rcx, [rbp+var_30]
0x180132a9a  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132a9f  nop
0x180132aa0  mov     rcx, rsi; lpCriticalSection
0x180132aa3  call    cs:__imp_LeaveCriticalSection
0x180132aa9  nop
0x180132aaa  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132aae  mov     rcx, rbx; this
0x180132ab1  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132ab6  nop
0x180132ab7  jmp     short loc_180132A60
0x180132ab9  lea     r8, [rbp+arg_18]
0x180132abd  lea     rdx, [rbp+var_30]
0x180132ac1  mov     rcx, rbx
0x180132ac4  call    ?PerformTask_ProcessBookmarks@CRecoMaster@@AEAAJAEAV?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@PEA_N@Z; CRecoMaster::PerformTask_ProcessBookmarks(std::unique_ptr<CSRTask> &,bool *)
0x180132ac9  mov     edi, eax
0x180132acb  test    eax, eax
0x180132acd  jns     short loc_180132B0E
0x180132acf  mov     rcx, [rbp+28h]; this
0x180132ad3  mov     r9d, eax; char *
0x180132ad6  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132add  mov     edx, 24Eh; void *
0x180132ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132ae7  nop
0x180132ae8  lea     rcx, [rbp+var_30]
0x180132aec  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132af1  nop
0x180132af2  mov     rcx, rsi; lpCriticalSection
0x180132af5  call    cs:__imp_LeaveCriticalSection
0x180132afb  nop
0x180132afc  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132b00  mov     rcx, rbx; this
0x180132b03  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132b08  nop
0x180132b09  jmp     loc_180132A60
0x180132b0e  lea     r8, [rbp+arg_0]
0x180132b12  lea     rdx, [rbp+var_30]
0x180132b16  mov     rcx, rbx
0x180132b19  call    ?PerformTask_ArbiterTasks@CRecoMaster@@AEAAJAEAV?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@PEA_N@Z; CRecoMaster::PerformTask_ArbiterTasks(std::unique_ptr<CSRTask> &,bool *)
0x180132b1e  mov     edi, eax
0x180132b20  test    eax, eax
0x180132b22  jns     short loc_180132B63
0x180132b24  mov     rcx, [rbp+28h]; this
0x180132b28  mov     r9d, eax; char *
0x180132b2b  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132b32  mov     edx, 24Fh; void *
0x180132b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132b3c  nop
0x180132b3d  lea     rcx, [rbp+var_30]
0x180132b41  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132b46  nop
0x180132b47  mov     rcx, rsi; lpCriticalSection
0x180132b4a  call    cs:__imp_LeaveCriticalSection
0x180132b50  nop
0x180132b51  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132b55  mov     rcx, rbx; this
0x180132b58  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132b5d  nop
0x180132b5e  jmp     loc_180132A60
0x180132b63  lea     r9, [rbp+arg_0]
0x180132b67  mov     r14b, [rbp+arg_18]
0x180132b6b  mov     r8b, r14b
0x180132b6e  lea     rdx, [rbp+var_30]
0x180132b72  mov     rcx, rbx
0x180132b75  call    ?PerformTask_ImmediateTasks@CRecoMaster@@AEAAJAEAV?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@_NPEA_N@Z; CRecoMaster::PerformTask_ImmediateTasks(std::unique_ptr<CSRTask> &,bool,bool *)
0x180132b7a  mov     edi, eax
0x180132b7c  test    eax, eax
0x180132b7e  jns     short loc_180132BBF
0x180132b80  mov     rcx, [rbp+28h]; this
0x180132b84  mov     r9d, eax; char *
0x180132b87  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132b8e  mov     edx, 250h; void *
0x180132b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132b98  nop
0x180132b99  lea     rcx, [rbp+var_30]
0x180132b9d  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132ba2  nop
0x180132ba3  mov     rcx, rsi; lpCriticalSection
0x180132ba6  call    cs:__imp_LeaveCriticalSection
0x180132bac  nop
0x180132bad  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132bb1  mov     rcx, rbx; this
0x180132bb4  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132bb9  nop
0x180132bba  jmp     loc_180132A60
0x180132bbf  mov     r10, [rbp+var_30]
0x180132bc3  cmp     dword ptr [r10+10h], 20h ; ' '
0x180132bc8  jnz     loc_180132CA5
0x180132bce  cmp     byte ptr [rbx+0B5h], 0
0x180132bd5  jz      loc_180132CA5
0x180132bdb  mov     r8d, [r10+10A0h]; enum SPRECOSTATE
0x180132be2  test    r8d, r8d
0x180132be5  jz      short loc_180132BF1
0x180132be7  cmp     r8d, 3
0x180132beb  jnz     loc_180132CA5
0x180132bf1  xor     r9d, r9d; int
0x180132bf4  mov     rdx, [r10+8]; struct CRecoInst *
0x180132bf8  mov     rcx, rbx; this
0x180132bfb  call    ?ChangeRecoInstState@CRecoMaster@@QEAAJPEAVCRecoInst@@W4SPRECOSTATE@@J@Z; CRecoMaster::ChangeRecoInstState(CRecoInst *,SPRECOSTATE,long)
0x180132c00  mov     edi, eax
0x180132c02  test    eax, eax
0x180132c04  jns     short loc_180132C45
0x180132c06  mov     rcx, [rbp+28h]; this
0x180132c0a  mov     r9d, eax; char *
0x180132c0d  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132c14  mov     edx, 25Dh; void *
0x180132c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132c1e  nop
0x180132c1f  lea     rcx, [rbp+var_30]
0x180132c23  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132c28  nop
0x180132c29  mov     rcx, rsi; lpCriticalSection
0x180132c2c  call    cs:__imp_LeaveCriticalSection
0x180132c32  nop
0x180132c33  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132c37  mov     rcx, rbx; this
0x180132c3a  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132c3f  nop
0x180132c40  jmp     loc_180132A60
0x180132c45  mov     rdx, [rbp+var_30]
0x180132c49  mov     r8d, [rdx+10A0h]; enum SPRECOSTATE
0x180132c50  mov     rdx, [rdx+8]; struct CRecoInst *
0x180132c54  mov     rcx, rbx; this
0x180132c57  call    ?ShouldStopStream@CRecoMaster@@QEAAJPEAVCRecoInst@@W4SPRECOSTATE@@@Z; CRecoMaster::ShouldStopStream(CRecoInst *,SPRECOSTATE)
0x180132c5c  mov     edi, eax
0x180132c5e  test    eax, eax
0x180132c60  jns     short loc_180132CA1
0x180132c62  mov     rcx, [rbp+28h]; this
0x180132c66  mov     r9d, eax; char *
0x180132c69  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180132c70  mov     edx, 25Eh; void *
0x180132c75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132c7a  nop
0x180132c7b  lea     rcx, [rbp+var_30]
0x180132c7f  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132c84  nop
0x180132c85  mov     rcx, rsi; lpCriticalSection
0x180132c88  call    cs:__imp_LeaveCriticalSection
0x180132c8e  nop
0x180132c8f  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132c93  mov     rcx, rbx; this
0x180132c96  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132c9b  nop
0x180132c9c  jmp     loc_180132A60
0x180132ca1  mov     r10, [rbp+var_30]
0x180132ca5  cmp     [rbp+arg_0], 0
0x180132ca9  jz      short loc_180132CF1
0x180132cab  mov     [rbp+var_30], 0
0x180132cb3  lea     rcx, [rbx+230h]
0x180132cba  mov     rdx, r10
0x180132cbd  call    ?InsertTail@?$CSpProducerConsumerIOCompletionQueue@VCSREvent@@$00@@QEAAXPEAVCSREvent@@@Z; CSpProducerConsumerIOCompletionQueue<CSREvent,1>::InsertTail(CSREvent *)
0x180132cc2  nop
0x180132cc3  lea     rcx, [rbp+var_30]
0x180132cc7  call    ??1?$unique_ptr@VCSRTask@@U?$default_delete@VCSRTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSRTask>::~unique_ptr<CSRTask>(void)
0x180132ccc  nop
0x180132ccd  mov     rcx, rsi; lpCriticalSection
0x180132cd0  call    cs:__imp_LeaveCriticalSection
0x180132cd6  nop
0x180132cd7  mov     rdx, [rbp+arg_8]; struct CRecoInst *
0x180132cdb  mov     rcx, rbx; this
0x180132cde  call    ?EndAvailabilityAssurance@CRecoMaster@@AEAAXPEAVCRecoInst@@@Z; CRecoMaster::EndAvailabilityAssurance(CRecoInst *)
0x180132ce3  nop
0x180132ce4  xor     eax, eax
0x180132ce6  add     rsp, 50h
0x180132cea  pop     r14
0x180132cec  pop     rdi
0x180132ced  pop     rsi
0x180132cee  pop     rbx
0x180132cef  pop     rbp
0x180132cf0  retn
0x180132cf1  test    r14b, r14b
0x180132cf4  jz      short loc_180132D63
0x180132cf6  lea     r11, [rbx+2E0h]
0x180132cfd  mov     [rbp+var_30], 0
0x180132d05  mov     rdi, [r11]
0x180132d08  test    rdi, rdi
0x180132d0b  jz      short loc_180132D50
0x180132d0d  mov     rdx, [r11+8]; struct CSRTask *
0x180132d11  mov     rcx, r10; struct CSRTask *
0x180132d14  call    ?Compare@CSRTask@@SAJPEBV1@0@Z; CSRTask::Compare(CSRTask const *,CSRTask const *)
0x180132d19  test    eax, eax
0x180132d1b  js      short loc_180132D31
0x180132d1d  mov     qword ptr [r10], 0
0x180132d24  mov     rax, [r11+8]
0x180132d28  mov     [rax], r10
0x180132d2b  mov     [r11+8], r10
0x180132d2f  jmp     short loc_180132CC3
0x180132d31  mov     rdx, rdi; struct CSRTask *
0x180132d34  mov     rcx, r10; struct CSRTask *
0x180132d37  call    ?Compare@CSRTask@@SAJPEBV1@0@Z; CSRTask::Compare(CSRTask const *,CSRTask const *)
0x180132d3c  test    eax, eax
0x180132d3e  js      short loc_180132D4B
0x180132d40  mov     r11, rdi
0x180132d43  mov     rdx, [rdi]
0x180132d46  mov     rdi, rdx
0x180132d49  jmp     short loc_180132D34
0x180132d4b  mov     [r10], rdx
0x180132d4e  jmp     short loc_180132D5B
0x180132d50  mov     qword ptr [r10], 0
0x180132d57  mov     [r11+8], r10
0x180132d5b  mov     [r11], r10
0x180132d5e  jmp     loc_180132CC3
0x180132d63  cmp     byte ptr [rbx+0B5h], 0
0x180132d6a  jz      short loc_180132DA8
0x180132d6c  mov     r9d, [r10+10h]
0x180132d70  mov     ecx, r9d
0x180132d73  call    ?IsAsyncTask@CSRTask@@SAHW4__MIDL___MIDL_itf_sapiint2Donecore_0000_0024_0001@@@Z; CSRTask::IsAsyncTask(__MIDL___MIDL_itf_sapiint2Donecore_0000_0024_0001)
0x180132d78  test    eax, eax
0x180132d7a  jnz     short loc_180132DA8
0x180132d7c  cmp     r9d, 12h
0x180132d80  jz      short loc_180132DA8
0x180132d82  cmp     r9d, 1Dh
0x180132d86  jz      short loc_180132DA8
0x180132d88  mov     ecx, r9d
0x180132d8b  call    SpEngineTaskIdToString
0x180132d90  mov     r8, rax
0x180132d93  lea     rdx, aQueuingPending; "Queuing pending task '%S' (%u)"
0x180132d9a  mov     ecx, 8; int
0x180132d9f  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180132da4  mov     r10, [rbp+var_30]
  ... truncated ...
```
