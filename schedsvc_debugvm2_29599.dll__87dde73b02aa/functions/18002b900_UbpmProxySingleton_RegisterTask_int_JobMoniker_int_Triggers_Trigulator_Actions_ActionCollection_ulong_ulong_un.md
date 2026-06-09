# UbpmProxySingleton::RegisterTask(int,JobMoniker &,int,Triggers::Trigulator &,Actions::ActionCollection &,ulong,ulong,unsigned __int64,ushort const *)

- ea: `0x18002b900`
- end: `0x18002be11`
- name: `?RegisterTask@UbpmProxySingleton@@UEAAJHAEAVJobMoniker@@HAEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@KK_KPEBG@Z`
- size: `1297`
- prototype: `int(UbpmProxySingleton *__hidden this, int, struct JobMoniker *, int, struct Triggers::Trigulator *, struct Actions::ActionCollection *, unsigned int, unsigned int, unsigned __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002b900`
- `0x18002be20`
- `0x18002c144`
- `0x18002c1b0`
- `0x18002c89c`
- `0x18002cd8c`
- `0x18002d03c`
- `0x18004fbe0`
- `0x180052584`
- `0x180056794`
- `0x1800590e4`
- `0x180059154`
- `0x1800597e4`
- `0x180070d3c`
- `0x180070f0c`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `UBPM!UbpmCloseTriggerConsumer` at `0x18002be00`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18002be00`
- `UBPM!UbpmTriggerConsumerSetStatePublishingSecurity` at `0x18002bc80`
- `UBPM!UbpmTriggerConsumerSetStatePublishingSecurity` at `0x18002bc80`
- `UBPM!UbpmTriggerConsumerRegister` at `0x18002bbae`
- `UBPM!UbpmTriggerConsumerRegister` at `0x18002bbae`
- `OLEAUT32!__imp_SysStringLen` at `0x18002bb19`
- `OLEAUT32!__imp_SysStringLen` at `0x18002bb19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b995`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bcb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b995`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bcb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bb95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bb95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbc9`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002bd7c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002bd7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bbf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bbf9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002bb51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002bb51`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UbpmProxySingleton::RegisterTask(
        UbpmProxySingleton *this,
        int a2,
        BSTR **a3,
        int a4,
        struct Triggers::Trigulator *a5,
        struct Actions::ActionCollection *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int64 a9,
        unsigned __int16 *a10)
{
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ebx
  int v19; // esi
  _QWORD *v20; // rbx
  __int64 v21; // rcx
  BSTR *v22; // rax
  UINT v23; // eax
  BSTR *v24; // rax
  BSTR v25; // rcx
  int v26; // ebx
  int v27; // edx
  tsched *v28; // rcx
  int v29; // eax
  int v31; // eax
  char LastHrError; // al
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v38; // [rsp+60h] [rbp-A0h]
  char v39[8]; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v40; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR v41[2]; // [rsp+80h] [rbp-80h] BYREF
  char v42[16]; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A4h] [rbp-5Ch]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  int v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  __int128 v49; // [rsp+E4h] [rbp-1Ch]
  __int64 v50; // [rsp+188h] [rbp+88h]
  __int64 v51; // [rsp+190h] [rbp+90h]
  __int128 v52; // [rsp+228h] [rbp+128h]
  __int64 v53; // [rsp+400h] [rbp+300h]
  __int64 v54; // [rsp+408h] [rbp+308h]
  __int64 v55; // [rsp+418h] [rbp+318h]

  UbpmParams::UbpmParams((UbpmParams *)v41, (const struct JobMoniker *)a3, a2);
  v36 = 0;
  v37[0] = a7;
  v37[1] = a8;
  v38 = a9;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  LOBYTE(SystemTimeAsFileTime[0].dwLowDateTime) = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  v14 = *((_QWORD *)a5 + 6);
  v15 = *(_QWORD *)(v14 + 208);
  if ( v15 )
  {
    v16 = 0xFFFFFFFFLL;
    if ( *(_DWORD *)(v15 + 12) != -1 )
    {
      *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *((_OWORD *)a5 + 1);
      v17 = *(_QWORD *)(v14 + 208);
      if ( v17 )
        v16 = *(unsigned int *)(v17 + 12);
      if ( *(_QWORD *)&SystemTimeAsFileTime[1] > (unsigned __int64)~(10000000 * v16) )
        SystemTimeAsFileTime[1] = (struct _FILETIME)-1LL;
      else
        *(_QWORD *)&SystemTimeAsFileTime[1] += 10000000 * v16;
      v39[0] = 0;
      GetSystemTimeAsFileTime(&v40);
      if ( (unsigned __int8)TSTime::operator>=(v39, SystemTimeAsFileTime) )
      {
        JobStore::DeleteExpiredTask(JobStore::m_pCommonStore, (const struct JobMoniker *)a3);
        if ( !a2 )
          (*(void (__fastcall **)(UbpmProxySingleton *, BSTR **))(*(_QWORD *)this + 8LL))(this, a3);
        v18 = 0;
        goto LABEL_35;
      }
      Triggers::Trigulator::ScheduleExpiredTaskDeletion(a5, (const struct JobMoniker *)a3);
    }
  }
  v18 = UbpmParams::Init(v41, (const struct JobMoniker *)a3, a10);
  if ( v18 >= 0 )
  {
    v18 = Actions::ActionCollection::ExportToUbpmFormat(a6, (struct IUbpmRegistrationParams *)v41);
    if ( v18 >= 0 )
    {
      v18 = UbpmParams::SetActionConstraints((UbpmParams *)v41, (const struct JobMoniker *)a3);
      if ( v18 >= 0 )
      {
        v19 = 0;
        v20 = (_QWORD *)*((_QWORD *)a5 + 4);
        while ( 1 )
        {
          v20 = (_QWORD *)*v20;
          if ( v20 == *((_QWORD **)a5 + 4) )
            break;
          v21 = v20[2];
          if ( v21 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21) == 52428 )
            ++v19;
        }
        v18 = Triggers::Trigulator::ExportToUbpmFormat(
                a5,
                (struct JobMoniker *)a3,
                (const struct Triggers::TriggerExportOptions *)v37,
                (struct IUbpmRegistrationParams *)v41);
        if ( v18 >= 0 )
        {
          if ( v53 != v54 )
          {
            v44 = -1431655765 * ((v54 - v53) >> 4);
            v45 = v53;
          }
          if ( v50 != v51 )
          {
            v46 = -858993459 * ((v51 - v50) >> 3);
            v47 = v50;
          }
          v48 = v55;
          v49 = v52;
          v22 = a3[2];
          if ( v22 && (!*v22 ? (v23 = 0) : (v23 = SysStringLen(*v22)), v23) )
          {
            v24 = a3[2];
            if ( v24 )
              v25 = *v24;
            else
              LODWORD(v25) = 0;
            v26 = (_DWORD)v25 + 14;
          }
          else
          {
            v26 = 0;
          }
          if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                  L"D:(A;;GA;;;SY)(A;;GR;;;LS)(A;;GR;;;NS)(A;;GR;;;BA)",
                  1u,
                  &SecurityDescriptor,
                  &SecurityDescriptorSize) )
          {
            LastHrError = tsched::GetLastHrError(v28, v27);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                36,
                (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
                v26,
                LastHrError);
            }
          }
          if ( dword_1800BDD1C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 4LL) )
          {
            Init_thread_header(&dword_1800BDD1C);
            if ( dword_1800BDD1C == -1 )
            {
              InitializeSRWLock(&stru_1800BDD20);
              Init_thread_footer(&dword_1800BDD1C);
            }
          }
          SystemTimeAsFileTime[0] = (struct _FILETIME)&stru_1800BDD20;
          AcquireSRWLockExclusive(&stru_1800BDD20);
          if ( !a4 )
            v43 |= 0x100u;
          v29 = UbpmTriggerConsumerRegister(v42, &v36);
          v18 = v29;
          if ( v29 > 0 )
            v18 = (unsigned __int16)v29 | 0x80070000;
          if ( v18 >= 0 )
          {
            if ( !v19
              || (v18 = Triggers::Trigulator::RegisterAllUbpmEmulatedTriggers(a5, (struct JobMoniker *)a3), v18 >= 0) )
            {
              SystemTimeAsFileTime[0].dwHighDateTime = 0;
              SystemTimeAsFileTime[1] = (struct _FILETIME)SecurityDescriptor;
              SystemTimeAsFileTime[0].dwLowDateTime = SecurityDescriptorSize;
              v31 = UbpmTriggerConsumerSetStatePublishingSecurity(v36, SystemTimeAsFileTime);
              v18 = v31;
              if ( v31 > 0 )
                v18 = (unsigned __int16)v31 | 0x80070000;
            }
          }
          ReleaseSRWLockExclusive(&stru_1800BDD20);
        }
      }
    }
  }
LABEL_35:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v18 >> 31) & 0xFFFFFFFE) + 4) )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
      (unsigned int)a3[3],
      v18);
  }
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v36 )
  {
    UbpmCloseTriggerConsumer();
    v36 = 0;
  }
  UbpmParams::~UbpmParams((UbpmParams *)v41);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18002b900  mov     [rsp-8+arg_8], rbx
0x18002b905  push    rbp
0x18002b906  push    rsi
0x18002b907  push    rdi
0x18002b908  push    r12
0x18002b90a  push    r13
0x18002b90c  push    r14
0x18002b90e  push    r15
0x18002b910  lea     rbp, [rsp-330h]
0x18002b918  sub     rsp, 430h
0x18002b91f  mov     rax, cs:__security_cookie
0x18002b926  xor     rax, rsp
0x18002b929  mov     [rbp+360h+var_40], rax
0x18002b930  mov     r12d, r9d
0x18002b933  mov     r15, r8
0x18002b936  mov     ebx, edx
0x18002b938  mov     r14, rcx
0x18002b93b  mov     rdi, [rbp+360h+arg_20]
0x18002b942  mov     rsi, [rbp+360h+arg_28]
0x18002b949  mov     r8d, edx; int
0x18002b94c  mov     rdx, r15; struct JobMoniker *
0x18002b94f  lea     rcx, [rbp+360h+var_3E0]; this
0x18002b953  call    ??0UbpmParams@@QEAA@AEBVJobMoniker@@H@Z; UbpmParams::UbpmParams(JobMoniker const &,int)
0x18002b958  nop
0x18002b959  xor     r13d, r13d
0x18002b95c  mov     [rsp+460h+var_410], r13
0x18002b961  mov     eax, [rbp+360h+arg_30]
0x18002b967  mov     [rsp+460h+var_408], eax
0x18002b96b  mov     eax, [rbp+360h+arg_38]
0x18002b971  mov     [rsp+460h+var_404], eax
0x18002b975  mov     rax, [rbp+360h+arg_40]
0x18002b97c  mov     [rsp+460h+var_400], rax
0x18002b981  mov     [rsp+460h+SecurityDescriptor], r13
0x18002b986  mov     [rsp+460h+SecurityDescriptorSize], r13d
0x18002b98b  mov     byte ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], r13b
0x18002b990  lea     rcx, [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18002b995  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b99b  mov     rdx, [rdi+30h]
0x18002b99f  mov     rcx, [rdx+0D0h]
0x18002b9a6  test    rcx, rcx
0x18002b9a9  jz      short loc_18002B9F5
0x18002b9ab  mov     eax, 0FFFFFFFFh
0x18002b9b0  cmp     [rcx+0Ch], eax
0x18002b9b3  jz      short loc_18002B9F5
0x18002b9b5  movups  xmm0, xmmword ptr [rdi+10h]
0x18002b9b9  movups  xmmword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18002b9be  mov     rcx, [rdx+0D0h]
0x18002b9c5  test    rcx, rcx
0x18002b9c8  jz      short loc_18002B9CD
0x18002b9ca  mov     eax, [rcx+0Ch]
0x18002b9cd  imul    rdx, rax, 989680h
0x18002b9d4  mov     rcx, rdx
0x18002b9d7  not     rcx
0x18002b9da  mov     rax, qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8]
0x18002b9df  cmp     rax, rcx
0x18002b9e2  ja      loc_18002BC9E
0x18002b9e8  add     rax, rdx
0x18002b9eb  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x18002b9f0  jmp     loc_18002BCA7
0x18002b9f5  mov     r8, [rbp+360h+arg_48]; unsigned __int16 *
0x18002b9fc  mov     rdx, r15; struct JobMoniker *
0x18002b9ff  lea     rcx, [rbp+360h+var_3E0]; this
0x18002ba03  call    ?Init@UbpmParams@@QEAAJAEBVJobMoniker@@PEBG@Z; UbpmParams::Init(JobMoniker const &,ushort const *)
0x18002ba08  mov     ebx, eax
0x18002ba0a  test    eax, eax
0x18002ba0c  js      loc_18002BBCF
0x18002ba12  lea     rdx, [rbp+360h+var_3E0]; struct IUbpmRegistrationParams *
0x18002ba16  mov     rcx, rsi; this
0x18002ba19  call    ?ExportToUbpmFormat@ActionCollection@Actions@@QEAAJAEAUIUbpmRegistrationParams@@@Z; Actions::ActionCollection::ExportToUbpmFormat(IUbpmRegistrationParams &)
0x18002ba1e  mov     ebx, eax
0x18002ba20  test    eax, eax
0x18002ba22  js      loc_18002BBCF
0x18002ba28  mov     rdx, r15; struct JobMoniker *
0x18002ba2b  lea     rcx, [rbp+360h+var_3E0]; this
0x18002ba2f  call    ?SetActionConstraints@UbpmParams@@UEAAJAEBVJobMoniker@@@Z; UbpmParams::SetActionConstraints(JobMoniker const &)
0x18002ba34  mov     ebx, eax
0x18002ba36  test    eax, eax
0x18002ba38  js      loc_18002BBCF
0x18002ba3e  mov     esi, r13d
0x18002ba41  mov     rbx, [rdi+20h]
0x18002ba45  mov     rbx, [rbx]
0x18002ba48  cmp     rbx, [rdi+20h]
0x18002ba4c  jz      short loc_18002BA6E
0x18002ba4e  mov     rcx, [rbx+10h]
0x18002ba52  test    rcx, rcx
0x18002ba55  jz      short loc_18002BA45
0x18002ba57  mov     rax, [rcx]
0x18002ba5a  mov     rax, [rax+48h]
0x18002ba5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba63  cmp     eax, 0CCCCh
0x18002ba68  jnz     short loc_18002BA45
0x18002ba6a  inc     esi
0x18002ba6c  jmp     short loc_18002BA45
0x18002ba6e  lea     r9, [rbp+360h+var_3E0]; struct IUbpmRegistrationParams *
0x18002ba72  lea     r8, [rsp+460h+var_408]; struct Triggers::TriggerExportOptions *
0x18002ba77  mov     rdx, r15; struct JobMoniker *
0x18002ba7a  mov     rcx, rdi; this
0x18002ba7d  call    ?ExportToUbpmFormat@Trigulator@Triggers@@QEAAJAEAVJobMoniker@@AEBUTriggerExportOptions@2@AEAUIUbpmRegistrationParams@@@Z; Triggers::Trigulator::ExportToUbpmFormat(JobMoniker &,Triggers::TriggerExportOptions const &,IUbpmRegistrationParams &)
0x18002ba82  mov     ebx, eax
0x18002ba84  test    eax, eax
0x18002ba86  js      loc_18002BBCF
0x18002ba8c  mov     rcx, [rbp+360h+var_60]
0x18002ba93  mov     rax, [rbp+360h+var_58]
0x18002ba9a  cmp     rcx, rax
0x18002ba9d  jz      short loc_18002BABB
0x18002ba9f  sub     rax, rcx
0x18002baa2  sar     rax, 4
0x18002baa6  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18002bab0  imul    rax, rdx
0x18002bab4  mov     [rbp+360h+var_3BC], eax
0x18002bab7  mov     [rbp+360h+var_3B8], rcx
0x18002babb  mov     rcx, [rbp+360h+var_2D8]
0x18002bac2  mov     rax, [rbp+360h+var_2D0]
0x18002bac9  cmp     rcx, rax
0x18002bacc  jz      short loc_18002BAEA
0x18002bace  sub     rax, rcx
0x18002bad1  sar     rax, 3
0x18002bad5  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18002badf  imul    rax, rdx
0x18002bae3  mov     [rbp+360h+var_3B0], eax
0x18002bae6  mov     [rbp+360h+var_3A8], rcx
0x18002baea  mov     rax, [rbp+360h+var_48]
0x18002baf1  mov     [rbp+360h+var_3A0], rax
0x18002baf5  movups  xmm0, [rbp+360h+var_238]
0x18002bafc  movups  [rbp+360h+var_37C], xmm0
0x18002bb00  mov     rax, [r15+10h]
0x18002bb04  test    rax, rax
0x18002bb07  jz      loc_18002BC47
0x18002bb0d  mov     rcx, [rax]; pbstr
0x18002bb10  test    rcx, rcx
0x18002bb13  jz      loc_18002BD04
0x18002bb19  call    cs:__imp_SysStringLen
0x18002bb1f  test    eax, eax
0x18002bb21  jz      loc_18002BC47
0x18002bb27  mov     rax, [r15+10h]
0x18002bb2b  test    rax, rax
0x18002bb2e  jz      loc_18002BC4F
0x18002bb34  mov     rcx, [rax]
0x18002bb37  lea     rbx, [rcx+0Eh]
0x18002bb3b  lea     r9, [rsp+460h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002bb40  lea     r8, [rsp+460h+SecurityDescriptor]; SecurityDescriptor
0x18002bb45  mov     edx, 1; StringSDRevision
0x18002bb4a  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GR;;;LS)(A;;GR;;;NS)("...
0x18002bb51  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002bb57  test    eax, eax
0x18002bb59  jz      loc_18002BD0C
0x18002bb5f  mov     ecx, cs:_tls_index
0x18002bb65  mov     rax, gs:58h
0x18002bb6e  mov     edx, 4
0x18002bb73  mov     rax, [rax+rcx*8]
0x18002bb77  lea     r14, stru_1800BDD20
0x18002bb7e  mov     eax, [rdx+rax]
0x18002bb81  cmp     cs:dword_1800BDD1C, eax
0x18002bb87  jg      loc_18002BD60
0x18002bb8d  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18002bb92  mov     rcx, r14; SRWLock
0x18002bb95  call    cs:__imp_AcquireSRWLockExclusive
0x18002bb9b  nop
0x18002bb9c  test    r12d, r12d
0x18002bb9f  jz      loc_18002BD93
0x18002bba5  lea     rdx, [rsp+460h+var_410]
0x18002bbaa  lea     rcx, [rbp+360h+var_3D0]
0x18002bbae  call    cs:__imp_UbpmTriggerConsumerRegister
0x18002bbb4  mov     ebx, eax
0x18002bbb6  test    eax, eax
0x18002bbb8  jg      loc_18002BD9F
0x18002bbbe  test    ebx, ebx
0x18002bbc0  jns     loc_18002BC57
0x18002bbc6  mov     rcx, r14; SRWLock
0x18002bbc9  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbd6  lea     rax, WPP_GLOBAL_Control
0x18002bbdd  cmp     rcx, rax
0x18002bbe0  jz      short loc_18002BBEF
0x18002bbe2  test    dword ptr [rcx+1Ch], 100h
0x18002bbe9  jnz     loc_18002BDC7
0x18002bbef  mov     rcx, [rsp+460h+SecurityDescriptor]; hMem
0x18002bbf4  test    rcx, rcx
0x18002bbf7  jz      short loc_18002BC04
0x18002bbf9  call    cs:__imp_LocalFree
0x18002bbff  mov     [rsp+460h+SecurityDescriptor], r13
0x18002bc04  mov     rcx, [rsp+460h+var_410]
0x18002bc09  test    rcx, rcx
0x18002bc0c  jnz     loc_18002BE00
0x18002bc12  lea     rcx, [rbp+360h+var_3E0]; this
0x18002bc16  call    ??1UbpmParams@@QEAA@XZ; UbpmParams::~UbpmParams(void)
0x18002bc1b  mov     eax, ebx
0x18002bc1d  mov     rcx, [rbp+360h+var_40]
0x18002bc24  xor     rcx, rsp; StackCookie
0x18002bc27  call    __security_check_cookie
0x18002bc2c  mov     rbx, [rsp+460h+arg_8]
0x18002bc34  add     rsp, 430h
0x18002bc3b  pop     r15
0x18002bc3d  pop     r14
0x18002bc3f  pop     r13
0x18002bc41  pop     r12
0x18002bc43  pop     rdi
0x18002bc44  pop     rsi
0x18002bc45  pop     rbp
0x18002bc46  retn
0x18002bc47  mov     rbx, r13
0x18002bc4a  jmp     loc_18002BB3B
0x18002bc4f  mov     rcx, r13
0x18002bc52  jmp     loc_18002BB37
0x18002bc57  test    esi, esi
0x18002bc59  jnz     loc_18002BDAD
0x18002bc5f  mov     [rsp+460h+SystemTimeAsFileTime.dwHighDateTime], r13d
0x18002bc64  mov     rax, [rsp+460h+SecurityDescriptor]
0x18002bc69  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x18002bc6e  mov     eax, [rsp+460h+SecurityDescriptorSize]
0x18002bc72  mov     [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18002bc76  lea     rdx, [rsp+460h+SystemTimeAsFileTime]
0x18002bc7b  mov     rcx, [rsp+460h+var_410]
0x18002bc80  call    cs:__imp_UbpmTriggerConsumerSetStatePublishingSecurity
0x18002bc86  mov     ebx, eax
0x18002bc88  test    eax, eax
0x18002bc8a  jle     loc_18002BBC6
0x18002bc90  movzx   ebx, ax
0x18002bc93  or      ebx, 80070000h
0x18002bc99  jmp     loc_18002BBC6
0x18002bc9e  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], 0FFFFFFFFFFFFFFFFh
0x18002bca7  mov     [rsp+460h+var_3F8], 0
0x18002bcac  lea     rcx, [rsp+460h+var_3F0]; lpSystemTimeAsFileTime
0x18002bcb1  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bcb7  lea     rdx, [rsp+460h+SystemTimeAsFileTime]
0x18002bcbc  lea     rcx, [rsp+460h+var_3F8]
0x18002bcc1  call    ??PTSTime@@QEBA_NAEBV0@@Z; TSTime::operator>=(TSTime const &)
0x18002bcc6  mov     rdx, r15; struct JobMoniker *
0x18002bcc9  test    al, al
0x18002bccb  jz      short loc_18002BCF7
0x18002bccd  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x18002bcd4  call    ?DeleteExpiredTask@JobStore@@QEAAJAEBVJobMoniker@@@Z; JobStore::DeleteExpiredTask(JobMoniker const &)
0x18002bcd9  test    ebx, ebx
0x18002bcdb  jnz     short loc_18002BCEF
0x18002bcdd  mov     rax, [r14]
0x18002bce0  mov     rdx, r15
0x18002bce3  mov     rcx, r14
0x18002bce6  mov     rax, [rax+8]
0x18002bcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcef  mov     ebx, r13d
0x18002bcf2  jmp     loc_18002BBCF
0x18002bcf7  mov     rcx, rdi; this
0x18002bcfa  call    ?ScheduleExpiredTaskDeletion@Trigulator@Triggers@@QEBAJAEBVJobMoniker@@@Z; Triggers::Trigulator::ScheduleExpiredTaskDeletion(JobMoniker const &)
0x18002bcff  jmp     loc_18002B9F5
0x18002bd04  mov     eax, r13d
0x18002bd07  jmp     loc_18002BB1F
0x18002bd0c  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18002bd11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd18  lea     rdx, WPP_GLOBAL_Control
0x18002bd1f  cmp     rcx, rdx
0x18002bd22  jz      loc_18002BB5F
0x18002bd28  test    dword ptr [rcx+1Ch], 40000h
0x18002bd2f  jz      loc_18002BB5F
0x18002bd35  cmp     byte ptr [rcx+19h], 2
0x18002bd39  jb      loc_18002BB5F
0x18002bd3f  mov     edx, 24h ; '$'
0x18002bd44  mov     [rsp+460h+var_440], eax
0x18002bd48  mov     r9, rbx
0x18002bd4b  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18002bd52  mov     rcx, [rcx+10h]
0x18002bd56  call    WPP_SF_Sd
0x18002bd5b  jmp     loc_18002BB5F
0x18002bd60  lea     rcx, dword_1800BDD1C
0x18002bd67  call    _Init_thread_header
0x18002bd6c  cmp     cs:dword_1800BDD1C, 0FFFFFFFFh
0x18002bd73  jnz     loc_18002BB8D
0x18002bd79  mov     rcx, r14; SRWLock
0x18002bd7c  call    cs:__imp_InitializeSRWLock
0x18002bd82  lea     rcx, dword_1800BDD1C
0x18002bd89  call    _Init_thread_footer
0x18002bd8e  jmp     loc_18002BB8D
0x18002bd93  or      [rbp+360h+var_3C0], 100h
0x18002bd9a  jmp     loc_18002BBA5
0x18002bd9f  movzx   ebx, ax
0x18002bda2  or      ebx, 80070000h
0x18002bda8  jmp     loc_18002BBBE
0x18002bdad  mov     rdx, r15; struct JobMoniker *
0x18002bdb0  mov     rcx, rdi; this
0x18002bdb3  call    ?RegisterAllUbpmEmulatedTriggers@Trigulator@Triggers@@QEAAJAEAVJobMoniker@@@Z; Triggers::Trigulator::RegisterAllUbpmEmulatedTriggers(JobMoniker &)
0x18002bdb8  mov     ebx, eax
0x18002bdba  test    eax, eax
0x18002bdbc  js      loc_18002BBC6
0x18002bdc2  jmp     loc_18002BC5F
0x18002bdc7  mov     edx, ebx
0x18002bdc9  sar     edx, 1Fh
0x18002bdcc  and     edx, 0FFFFFFFEh
0x18002bdcf  add     edx, 4
0x18002bdd2  movzx   eax, byte ptr [rcx+19h]
0x18002bdd6  cmp     eax, edx
0x18002bdd8  jl      loc_18002BBEF
0x18002bdde  mov     edx, 0Bh
0x18002bde3  mov     [rsp+460h+var_440], ebx
0x18002bde7  mov     r9, [r15+18h]
0x18002bdeb  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x18002bdf2  mov     rcx, [rcx+10h]
0x18002bdf6  call    WPP_SF_Sd
0x18002bdfb  jmp     loc_18002BBEF
0x18002be00  call    cs:__imp_UbpmCloseTriggerConsumer
0x18002be06  mov     [rsp+460h+var_410], r13
0x18002be0b  jmp     loc_18002BC12
  ... truncated ...
```
