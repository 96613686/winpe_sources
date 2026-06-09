# UbpmProxySingleton::RegisterTask(int,JobMoniker &,int,Triggers::Trigulator &,Actions::ActionCollection &,ulong,ulong,unsigned __int64,ushort const *)

- ea: `0x180002a20`
- end: `0x180002f74`
- name: `?RegisterTask@UbpmProxySingleton@@UEAAJHAEAVJobMoniker@@HAEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@KK_KPEBG@Z`
- size: `1364`
- prototype: `int(UbpmProxySingleton *__hidden this, int, struct JobMoniker *, int, struct Triggers::Trigulator *, struct Actions::ActionCollection *, unsigned int, unsigned int, unsigned __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002a20`
- `0x180002f80`
- `0x1800032a8`
- `0x180003310`
- `0x1800039d8`
- `0x180003ec8`
- `0x180004154`
- `0x1800524d4`
- `0x180054c80`
- `0x180059140`
- `0x18005bab4`
- `0x18005bb24`
- `0x18005c1e0`
- `0x180074680`
- `0x18007485c`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `UBPM!UbpmCloseTriggerConsumer` at `0x180002f5d`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180002f5d`
- `UBPM!UbpmTriggerConsumerSetStatePublishingSecurity` at `0x180002dcb`
- `UBPM!UbpmTriggerConsumerSetStatePublishingSecurity` at `0x180002dcb`
- `UBPM!UbpmTriggerConsumerRegister` at `0x180002ce6`
- `UBPM!UbpmTriggerConsumerRegister` at `0x180002ce6`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c3f`
- `OLEAUT32!__imp_SysStringLen` at `0x180002c3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002cc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002cc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d07`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180002ed3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180002ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002c7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002c7d`

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
  char *v41[2]; // [rsp+80h] [rbp-80h] BYREF
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
  v18 = UbpmParams::Init(v41, (const struct JobMoniker *)a3, (char *)a10);
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
          if ( dword_1800C1D04 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 4LL) )
          {
            Init_thread_header(&dword_1800C1D04);
            if ( dword_1800C1D04 == -1 )
            {
              InitializeSRWLock(&stru_1800C1D08);
              Init_thread_footer(&dword_1800C1D04);
            }
          }
          SystemTimeAsFileTime[0] = (struct _FILETIME)&stru_1800C1D08;
          AcquireSRWLockExclusive(&stru_1800C1D08);
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
          ReleaseSRWLockExclusive(&stru_1800C1D08);
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
0x180002a20  mov     [rsp-8+arg_8], rbx
0x180002a25  push    rbp
0x180002a26  push    rsi
0x180002a27  push    rdi
0x180002a28  push    r12
0x180002a2a  push    r13
0x180002a2c  push    r14
0x180002a2e  push    r15
0x180002a30  lea     rbp, [rsp-330h]
0x180002a38  sub     rsp, 430h
0x180002a3f  mov     rax, cs:__security_cookie
0x180002a46  xor     rax, rsp
0x180002a49  mov     [rbp+360h+var_40], rax
0x180002a50  mov     r12d, r9d
0x180002a53  mov     r15, r8
0x180002a56  mov     ebx, edx
0x180002a58  mov     r14, rcx
0x180002a5b  mov     rdi, [rbp+360h+arg_20]
0x180002a62  mov     rsi, [rbp+360h+arg_28]
0x180002a69  mov     r8d, edx; int
0x180002a6c  mov     rdx, r15; struct JobMoniker *
0x180002a6f  lea     rcx, [rbp+360h+var_3E0]; this
0x180002a73  call    ??0UbpmParams@@QEAA@AEBVJobMoniker@@H@Z; UbpmParams::UbpmParams(JobMoniker const &,int)
0x180002a78  nop
0x180002a79  xor     r13d, r13d
0x180002a7c  mov     [rsp+460h+var_410], r13
0x180002a81  mov     eax, [rbp+360h+arg_30]
0x180002a87  mov     [rsp+460h+var_408], eax
0x180002a8b  mov     eax, [rbp+360h+arg_38]
0x180002a91  mov     [rsp+460h+var_404], eax
0x180002a95  mov     rax, [rbp+360h+arg_40]
0x180002a9c  mov     [rsp+460h+var_400], rax
0x180002aa1  mov     [rsp+460h+SecurityDescriptor], r13
0x180002aa6  mov     [rsp+460h+SecurityDescriptorSize], r13d
0x180002aab  mov     byte ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], r13b
0x180002ab0  lea     rcx, [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180002ab5  call    cs:__imp_GetSystemTimeAsFileTime
0x180002abc  nop     dword ptr [rax+rax+00h]
0x180002ac1  mov     rdx, [rdi+30h]
0x180002ac5  mov     rcx, [rdx+0D0h]
0x180002acc  test    rcx, rcx
0x180002acf  jz      short loc_180002B1B
0x180002ad1  mov     eax, 0FFFFFFFFh
0x180002ad6  cmp     [rcx+0Ch], eax
0x180002ad9  jz      short loc_180002B1B
0x180002adb  movups  xmm0, xmmword ptr [rdi+10h]
0x180002adf  movups  xmmword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x180002ae4  mov     rcx, [rdx+0D0h]
0x180002aeb  test    rcx, rcx
0x180002aee  jz      short loc_180002AF3
0x180002af0  mov     eax, [rcx+0Ch]
0x180002af3  imul    rdx, rax, 989680h
0x180002afa  mov     rcx, rdx
0x180002afd  not     rcx
0x180002b00  mov     rax, qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8]
0x180002b05  cmp     rax, rcx
0x180002b08  ja      loc_180002DEF
0x180002b0e  add     rax, rdx
0x180002b11  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x180002b16  jmp     loc_180002DF8
0x180002b1b  mov     r8, [rbp+360h+arg_48]; unsigned __int16 *
0x180002b22  mov     rdx, r15; struct JobMoniker *
0x180002b25  lea     rcx, [rbp+360h+var_3E0]; this
0x180002b29  call    ?Init@UbpmParams@@QEAAJAEBVJobMoniker@@PEBG@Z; UbpmParams::Init(JobMoniker const &,ushort const *)
0x180002b2e  mov     ebx, eax
0x180002b30  test    eax, eax
0x180002b32  js      loc_180002D13
0x180002b38  lea     rdx, [rbp+360h+var_3E0]; struct IUbpmRegistrationParams *
0x180002b3c  mov     rcx, rsi; this
0x180002b3f  call    ?ExportToUbpmFormat@ActionCollection@Actions@@QEAAJAEAUIUbpmRegistrationParams@@@Z; Actions::ActionCollection::ExportToUbpmFormat(IUbpmRegistrationParams &)
0x180002b44  mov     ebx, eax
0x180002b46  test    eax, eax
0x180002b48  js      loc_180002D13
0x180002b4e  mov     rdx, r15; struct JobMoniker *
0x180002b51  lea     rcx, [rbp+360h+var_3E0]; this
0x180002b55  call    ?SetActionConstraints@UbpmParams@@UEAAJAEBVJobMoniker@@@Z; UbpmParams::SetActionConstraints(JobMoniker const &)
0x180002b5a  mov     ebx, eax
0x180002b5c  test    eax, eax
0x180002b5e  js      loc_180002D13
0x180002b64  mov     esi, r13d
0x180002b67  mov     rbx, [rdi+20h]
0x180002b6b  mov     rbx, [rbx]
0x180002b6e  cmp     rbx, [rdi+20h]
0x180002b72  jz      short loc_180002B94
0x180002b74  mov     rcx, [rbx+10h]
0x180002b78  test    rcx, rcx
0x180002b7b  jz      short loc_180002B6B
0x180002b7d  mov     rax, [rcx]
0x180002b80  mov     rax, [rax+48h]
0x180002b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b89  cmp     eax, 0CCCCh
0x180002b8e  jnz     short loc_180002B6B
0x180002b90  inc     esi
0x180002b92  jmp     short loc_180002B6B
0x180002b94  lea     r9, [rbp+360h+var_3E0]; struct IUbpmRegistrationParams *
0x180002b98  lea     r8, [rsp+460h+var_408]; struct Triggers::TriggerExportOptions *
0x180002b9d  mov     rdx, r15; struct JobMoniker *
0x180002ba0  mov     rcx, rdi; this
0x180002ba3  call    ?ExportToUbpmFormat@Trigulator@Triggers@@QEAAJAEAVJobMoniker@@AEBUTriggerExportOptions@2@AEAUIUbpmRegistrationParams@@@Z; Triggers::Trigulator::ExportToUbpmFormat(JobMoniker &,Triggers::TriggerExportOptions const &,IUbpmRegistrationParams &)
0x180002ba8  mov     ebx, eax
0x180002baa  test    eax, eax
0x180002bac  js      loc_180002D13
0x180002bb2  mov     rcx, [rbp+360h+var_60]
0x180002bb9  mov     rax, [rbp+360h+var_58]
0x180002bc0  cmp     rcx, rax
0x180002bc3  jz      short loc_180002BE1
0x180002bc5  sub     rax, rcx
0x180002bc8  sar     rax, 4
0x180002bcc  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180002bd6  imul    rax, rdx
0x180002bda  mov     [rbp+360h+var_3BC], eax
0x180002bdd  mov     [rbp+360h+var_3B8], rcx
0x180002be1  mov     rcx, [rbp+360h+var_2D8]
0x180002be8  mov     rax, [rbp+360h+var_2D0]
0x180002bef  cmp     rcx, rax
0x180002bf2  jz      short loc_180002C10
0x180002bf4  sub     rax, rcx
0x180002bf7  sar     rax, 3
0x180002bfb  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x180002c05  imul    rax, rdx
0x180002c09  mov     [rbp+360h+var_3B0], eax
0x180002c0c  mov     [rbp+360h+var_3A8], rcx
0x180002c10  mov     rax, [rbp+360h+var_48]
0x180002c17  mov     [rbp+360h+var_3A0], rax
0x180002c1b  movups  xmm0, [rbp+360h+var_238]
0x180002c22  movups  [rbp+360h+var_37C], xmm0
0x180002c26  mov     rax, [r15+10h]
0x180002c2a  test    rax, rax
0x180002c2d  jz      loc_180002D92
0x180002c33  mov     rcx, [rax]; pbstr
0x180002c36  test    rcx, rcx
0x180002c39  jz      loc_180002E5B
0x180002c3f  call    cs:__imp_SysStringLen
0x180002c46  nop     dword ptr [rax+rax+00h]
0x180002c4b  test    eax, eax
0x180002c4d  jz      loc_180002D92
0x180002c53  mov     rax, [r15+10h]
0x180002c57  test    rax, rax
0x180002c5a  jz      loc_180002D9A
0x180002c60  mov     rcx, [rax]
0x180002c63  lea     rbx, [rcx+0Eh]
0x180002c67  lea     r9, [rsp+460h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180002c6c  lea     r8, [rsp+460h+SecurityDescriptor]; SecurityDescriptor
0x180002c71  mov     edx, 1; StringSDRevision
0x180002c76  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GR;;;LS)(A;;GR;;;NS)("...
0x180002c7d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002c84  nop     dword ptr [rax+rax+00h]
0x180002c89  test    eax, eax
0x180002c8b  jz      loc_180002E63
0x180002c91  mov     ecx, cs:_tls_index
0x180002c97  mov     rax, gs:58h
0x180002ca0  mov     edx, 4
0x180002ca5  mov     rax, [rax+rcx*8]
0x180002ca9  lea     r14, stru_1800C1D08
0x180002cb0  mov     eax, [rdx+rax]
0x180002cb3  cmp     cs:dword_1800C1D04, eax
0x180002cb9  jg      loc_180002EB7
0x180002cbf  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180002cc4  mov     rcx, r14; SRWLock
0x180002cc7  call    cs:__imp_AcquireSRWLockExclusive
0x180002cce  nop     dword ptr [rax+rax+00h]
0x180002cd3  nop
0x180002cd4  test    r12d, r12d
0x180002cd7  jz      loc_180002EF0
0x180002cdd  lea     rdx, [rsp+460h+var_410]
0x180002ce2  lea     rcx, [rbp+360h+var_3D0]
0x180002ce6  call    cs:__imp_UbpmTriggerConsumerRegister
0x180002ced  nop     dword ptr [rax+rax+00h]
0x180002cf2  mov     ebx, eax
0x180002cf4  test    eax, eax
0x180002cf6  jg      loc_180002EFC
0x180002cfc  test    ebx, ebx
0x180002cfe  jns     loc_180002DA2
0x180002d04  mov     rcx, r14; SRWLock
0x180002d07  call    cs:__imp_ReleaseSRWLockExclusive
0x180002d0e  nop     dword ptr [rax+rax+00h]
0x180002d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1a  lea     rax, WPP_GLOBAL_Control
0x180002d21  cmp     rcx, rax
0x180002d24  jz      short loc_180002D33
0x180002d26  test    dword ptr [rcx+1Ch], 100h
0x180002d2d  jnz     loc_180002F24
0x180002d33  mov     rcx, [rsp+460h+SecurityDescriptor]; hMem
0x180002d38  test    rcx, rcx
0x180002d3b  jz      short loc_180002D4E
0x180002d3d  call    cs:__imp_LocalFree
0x180002d44  nop     dword ptr [rax+rax+00h]
0x180002d49  mov     [rsp+460h+SecurityDescriptor], r13
0x180002d4e  mov     rcx, [rsp+460h+var_410]
0x180002d53  test    rcx, rcx
0x180002d56  jnz     loc_180002F5D
0x180002d5c  lea     rcx, [rbp+360h+var_3E0]; this
0x180002d60  call    ??1UbpmParams@@QEAA@XZ; UbpmParams::~UbpmParams(void)
0x180002d65  mov     eax, ebx
0x180002d67  mov     rcx, [rbp+360h+var_40]
0x180002d6e  xor     rcx, rsp; StackCookie
0x180002d71  call    __security_check_cookie
0x180002d76  mov     rbx, [rsp+460h+arg_8]
0x180002d7e  add     rsp, 430h
0x180002d85  pop     r15
0x180002d87  pop     r14
0x180002d89  pop     r13
0x180002d8b  pop     r12
0x180002d8d  pop     rdi
0x180002d8e  pop     rsi
0x180002d8f  pop     rbp
0x180002d90  retn
0x180002d92  mov     rbx, r13
0x180002d95  jmp     loc_180002C67
0x180002d9a  mov     rcx, r13
0x180002d9d  jmp     loc_180002C63
0x180002da2  test    esi, esi
0x180002da4  jnz     loc_180002F0A
0x180002daa  mov     [rsp+460h+SystemTimeAsFileTime.dwHighDateTime], r13d
0x180002daf  mov     rax, [rsp+460h+SecurityDescriptor]
0x180002db4  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x180002db9  mov     eax, [rsp+460h+SecurityDescriptorSize]
0x180002dbd  mov     [rsp+460h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180002dc1  lea     rdx, [rsp+460h+SystemTimeAsFileTime]
0x180002dc6  mov     rcx, [rsp+460h+var_410]
0x180002dcb  call    cs:__imp_UbpmTriggerConsumerSetStatePublishingSecurity
0x180002dd2  nop     dword ptr [rax+rax+00h]
0x180002dd7  mov     ebx, eax
0x180002dd9  test    eax, eax
0x180002ddb  jle     loc_180002D04
0x180002de1  movzx   ebx, ax
0x180002de4  or      ebx, 80070000h
0x180002dea  jmp     loc_180002D04
0x180002def  mov     qword ptr [rsp+460h+SystemTimeAsFileTime.dwLowDateTime+8], 0FFFFFFFFFFFFFFFFh
0x180002df8  mov     [rsp+460h+var_3F8], 0
0x180002dfd  lea     rcx, [rsp+460h+var_3F0]; lpSystemTimeAsFileTime
0x180002e02  call    cs:__imp_GetSystemTimeAsFileTime
0x180002e09  nop     dword ptr [rax+rax+00h]
0x180002e0e  lea     rdx, [rsp+460h+SystemTimeAsFileTime]
0x180002e13  lea     rcx, [rsp+460h+var_3F8]
0x180002e18  call    ??PTSTime@@QEBA_NAEBV0@@Z; TSTime::operator>=(TSTime const &)
0x180002e1d  mov     rdx, r15; struct JobMoniker *
0x180002e20  test    al, al
0x180002e22  jz      short loc_180002E4E
0x180002e24  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
0x180002e2b  call    ?DeleteExpiredTask@JobStore@@QEAAJAEBVJobMoniker@@@Z; JobStore::DeleteExpiredTask(JobMoniker const &)
0x180002e30  test    ebx, ebx
0x180002e32  jnz     short loc_180002E46
0x180002e34  mov     rax, [r14]
0x180002e37  mov     rdx, r15
0x180002e3a  mov     rcx, r14
0x180002e3d  mov     rax, [rax+8]
0x180002e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e46  mov     ebx, r13d
0x180002e49  jmp     loc_180002D13
0x180002e4e  mov     rcx, rdi; this
0x180002e51  call    ?ScheduleExpiredTaskDeletion@Trigulator@Triggers@@QEBAJAEBVJobMoniker@@@Z; Triggers::Trigulator::ScheduleExpiredTaskDeletion(JobMoniker const &)
0x180002e56  jmp     loc_180002B1B
0x180002e5b  mov     eax, r13d
0x180002e5e  jmp     loc_180002C4B
0x180002e63  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x180002e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e6f  lea     rdx, WPP_GLOBAL_Control
0x180002e76  cmp     rcx, rdx
0x180002e79  jz      loc_180002C91
0x180002e7f  test    dword ptr [rcx+1Ch], 40000h
0x180002e86  jz      loc_180002C91
0x180002e8c  cmp     byte ptr [rcx+19h], 2
0x180002e90  jb      loc_180002C91
0x180002e96  mov     edx, 24h ; '$'
0x180002e9b  mov     [rsp+460h+var_440], eax
0x180002e9f  mov     r9, rbx
0x180002ea2  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180002ea9  mov     rcx, [rcx+10h]
0x180002ead  call    WPP_SF_Sd
0x180002eb2  jmp     loc_180002C91
0x180002eb7  lea     rcx, dword_1800C1D04
0x180002ebe  call    _Init_thread_header
0x180002ec3  cmp     cs:dword_1800C1D04, 0FFFFFFFFh
0x180002eca  jnz     loc_180002CBF
0x180002ed0  mov     rcx, r14; SRWLock
0x180002ed3  call    cs:__imp_InitializeSRWLock
0x180002eda  nop     dword ptr [rax+rax+00h]
0x180002edf  lea     rcx, dword_1800C1D04
0x180002ee6  call    _Init_thread_footer
0x180002eeb  jmp     loc_180002CBF
0x180002ef0  or      [rbp+360h+var_3C0], 100h
0x180002ef7  jmp     loc_180002CDD
0x180002efc  movzx   ebx, ax
0x180002eff  or      ebx, 80070000h
0x180002f05  jmp     loc_180002CFC
0x180002f0a  mov     rdx, r15; struct JobMoniker *
0x180002f0d  mov     rcx, rdi; this
0x180002f10  call    ?RegisterAllUbpmEmulatedTriggers@Trigulator@Triggers@@QEAAJAEAVJobMoniker@@@Z; Triggers::Trigulator::RegisterAllUbpmEmulatedTriggers(JobMoniker &)
0x180002f15  mov     ebx, eax
0x180002f17  test    eax, eax
0x180002f19  js      loc_180002D04
0x180002f1f  jmp     loc_180002DAA
0x180002f24  mov     edx, ebx
0x180002f26  sar     edx, 1Fh
0x180002f29  and     edx, 0FFFFFFFEh
0x180002f2c  add     edx, 4
0x180002f2f  movzx   eax, byte ptr [rcx+19h]
0x180002f33  cmp     eax, edx
0x180002f35  jl      loc_180002D33
  ... truncated ...
```
