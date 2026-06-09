# CWmiArbitrator::RegisterTask(_IWmiCoreHandle *)

- ea: `0x180056c60`
- end: `0x180057091`
- name: `?RegisterTask@CWmiArbitrator@@UEAAJPEAU_IWmiCoreHandle@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(CWmiArbitrator *__hidden this, struct _IWmiCoreHandle *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001f50`
- `0x18000b140`
- `0x180052330`
- `0x180056c60`
- `0x18008aca0`
- `0x18008acb8`
- `0x180092ba0`
- `0x1800a43b8`
- `0x1800a443c`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056e37`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056eec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056fbc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056e37`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056eec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180056fbc`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180056d91`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180056d91`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x180056de3`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x180056de3`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180056dc5`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180056dc5`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180056dab`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180056dab`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180056cc3`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180056cc3`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180056d38`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005702b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180056d38`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005702b`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180056cd4`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180056cd4`
- `wbemcomn!GetMemLogObject` at `0x180056d4e`
- `wbemcomn!GetMemLogObject` at `0x180056e4a`
- `wbemcomn!GetMemLogObject` at `0x180056efe`
- `wbemcomn!GetMemLogObject` at `0x180056fd2`
- `wbemcomn!GetMemLogObject` at `0x180056d4e`
- `wbemcomn!GetMemLogObject` at `0x180056e4a`
- `wbemcomn!GetMemLogObject` at `0x180056efe`
- `wbemcomn!GetMemLogObject` at `0x180056fd2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056d5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056e5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056f0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056fe2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056d5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056e5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056f0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056fe2`

## string_xrefs

- `0x180056d9f`: `Max Tasks`
- `0x180056dd7`: `Max Tasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWmiArbitrator::RegisterTask(CWmiArbitrator *this, struct _IWmiCoreHandle *a2)
{
  int v4; // r15d
  unsigned int v5; // ebp
  CMemoryLog *MemLogObject; // rax
  unsigned int v8; // ebx
  CClientCnt *v9; // rcx
  CWmiTask *v10; // rcx
  CWmiArbitrator *v11; // rcx
  unsigned int v12; // r14d
  CMemoryLog *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // ebp
  CWmiTask *v17; // rcx
  CWmiArbitrator *v18; // rcx
  CMemoryLog *v19; // rax
  CWmiTask *v20; // rcx
  CWmiArbitrator *v21; // rcx
  unsigned int v22; // r14d
  signed int v23; // ebp
  signed int v24; // r12d
  CMemoryLog *v25; // rax
  _BYTE v26[88]; // [rsp+20h] [rbp-58h] BYREF
  char v27; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    v8 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 15;
      v15 = 2147749896LL;
LABEL_60:
      WPP_SF_d(*((_QWORD *)v9 + 2), v14, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids, v15);
    }
    return v8;
  }
  v4 = *((_DWORD *)a2 + 3);
  if ( !dword_1801ADB98 )
  {
    Registry::Registry((Registry *)v26, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
    if ( Registry::GetDWORD((Registry *)v26, L"Max Tasks", (unsigned int *)&dword_1801A2760) == 1 )
      Registry::SetDWORD((Registry *)v26, L"Max Tasks", dword_1801A2760);
    dword_1801ADB98 = 1;
    Registry::~Registry((Registry *)v26);
  }
  v5 = dword_1801A2760;
  if ( (unsigned int)dword_1801A2760 < 0x1388 )
  {
    v5 = 5000;
    dword_1801A2760 = 5000;
  }
  if ( v5 && (v4 & 0x10000000) != 0 )
  {
    if ( !(unsigned int)CWmiTask::IsESSNamespace(a2)
      && !(unsigned int)CWmiTask::IsProviderNamespace(v10)
      && (_BYTE)v4 != 25
      && !*((_DWORD *)this + 108) )
    {
      v12 = 0;
      if ( (unsigned int)CWmiArbitrator::IsTaskArbitrated(v11, a2) )
      {
        while ( *((_DWORD *)this + 4) > v5 )
        {
          Sleep(0x4Bu);
          v12 += 75;
          if ( v12 > ConfigMgr::GetMaxWaitBeforeDenial() )
          {
            v13 = GetMemLogObject();
            v8 = -2147217339;
            CMemoryLog::Write(v13, -2147217339);
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 16;
              v15 = 2147749957LL;
              goto LABEL_60;
            }
            return v8;
          }
        }
      }
    }
    v16 = 0;
    if ( !*((_DWORD *)this + 108) )
    {
      while ( !CWmiArbitrator::AcceptsNewTasks(this, 0)
           && !(unsigned int)CWmiTask::IsESSNamespace(a2)
           && !(unsigned int)CWmiTask::IsProviderNamespace(v17)
           && !*((_DWORD *)this + 108)
           && (unsigned int)CWmiArbitrator::IsTaskArbitrated(v18, a2) == 1 )
      {
        Sleep(0x4Bu);
        v16 += 75;
        if ( v16 > ConfigMgr::GetMaxWaitBeforeDenial() )
        {
          v19 = GetMemLogObject();
          v8 = -2147217300;
          CMemoryLog::Write(v19, -2147217300);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 17;
            v15 = 2147749996LL;
            goto LABEL_60;
          }
          return v8;
        }
      }
    }
    if ( !(unsigned int)CWmiTask::IsESSNamespace(a2)
      && !(unsigned int)CWmiTask::IsProviderNamespace(v20)
      && (_BYTE)v4 != 25
      && !*((_DWORD *)this + 108) )
    {
      if ( (unsigned int)CWmiArbitrator::IsTaskArbitrated(v21, a2) )
      {
        v22 = *((_DWORD *)this + 5);
        if ( v22 > *((_DWORD *)this + 31) )
        {
          v23 = 0;
          v24 = v22 * ConfigMgr::GetNewTaskResistance();
          do
          {
            if ( v23 >= v24 )
              break;
            Sleep(0x4Bu);
            v23 += 75;
          }
          while ( *((_DWORD *)this + 5) > *((_DWORD *)this + 31) );
        }
      }
    }
  }
  CInCritSec::CInCritSec((CInCritSec *)&v27, (struct _RTL_CRITICAL_SECTION *)((char *)this + 384));
  if ( CFlexArray::Add((CWmiArbitrator *)((char *)this + 128), a2) )
  {
    v25 = GetMemLogObject();
    v8 = -2147217402;
    CMemoryLog::Write(v25, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids, 2147749894LL);
    }
    CInCritSec::~CInCritSec((CInCritSec *)&v27);
    return v8;
  }
  (*(void (__fastcall **)(struct _IWmiCoreHandle *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( ++*((_DWORD *)this + 3) > (unsigned int)dword_1801ADAD0 )
    dword_1801ADAD0 = *((_DWORD *)this + 3);
  if ( (v4 & 0x10000000) != 0 && (_BYTE)v4 != 25 )
  {
    ++*((_DWORD *)this + 4);
    if ( !*((_DWORD *)a2 + 7) )
      CWmiArbitrator::RegisterTaskForEntryThrottling(this, a2);
  }
  *((double *)this + 9) = (double)*((int *)this + 4) / 100.0 + 1.0;
  CInCritSec::~CInCritSec((CInCritSec *)&v27);
  return 0;
}

```

## disassembly

```asm
0x180056c60  push    rbx
0x180056c62  push    rbp
0x180056c63  push    rdi
0x180056c64  push    r12
0x180056c66  push    r14
0x180056c68  push    r15
0x180056c6a  sub     rsp, 48h
0x180056c6e  mov     rdi, rdx
0x180056c71  mov     rbx, rcx
0x180056c74  test    rdx, rdx
0x180056c77  jz      loc_180056D4E
0x180056c7d  mov     r15d, [rdx+0Ch]
0x180056c81  cmp     cs:dword_1801ADB98, 0
0x180056c88  jz      loc_180056D7F
0x180056c8e  mov     ebp, cs:dword_1801A2760
0x180056c94  mov     eax, 1388h
0x180056c99  cmp     ebp, eax
0x180056c9b  jnb     short loc_180056CA5
0x180056c9d  mov     ebp, eax
0x180056c9f  mov     cs:dword_1801A2760, eax
0x180056ca5  test    ebp, ebp
0x180056ca7  jz      short loc_180056CB4
0x180056ca9  bt      r15d, 1Ch
0x180056cae  jb      loc_180056DEB
0x180056cb4  lea     rdx, [rbx+180h]
0x180056cbb  lea     rcx, [rsp+78h+arg_8]
0x180056cc3  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180056cc9  nop
0x180056cca  lea     rcx, [rbx+80h]
0x180056cd1  mov     rdx, rdi
0x180056cd4  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180056cda  test    eax, eax
0x180056cdc  jnz     loc_180056FD2
0x180056ce2  mov     rax, [rdi]
0x180056ce5  mov     rcx, rdi
0x180056ce8  mov     rax, [rax+8]
0x180056cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cf1  inc     dword ptr [rbx+0Ch]
0x180056cf4  mov     eax, [rbx+0Ch]
0x180056cf7  cmp     eax, cs:dword_1801ADAD0
0x180056cfd  jbe     short loc_180056D05
0x180056cff  mov     cs:dword_1801ADAD0, eax
0x180056d05  bt      r15d, 1Ch
0x180056d0a  jb      loc_180057036
0x180056d10  mov     eax, [rbx+10h]
0x180056d13  xorps   xmm0, xmm0
0x180056d16  cvtsi2sd xmm0, rax
0x180056d1b  divsd   xmm0, cs:__real@4059000000000000
0x180056d23  addsd   xmm0, cs:__real@3ff0000000000000
0x180056d2b  movsd   qword ptr [rbx+48h], xmm0
0x180056d30  lea     rcx, [rsp+78h+arg_8]
0x180056d38  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180056d3e  xor     eax, eax
0x180056d40  add     rsp, 48h
0x180056d44  pop     r15
0x180056d46  pop     r14
0x180056d48  pop     r12
0x180056d4a  pop     rdi
0x180056d4b  pop     rbp
0x180056d4c  pop     rbx
0x180056d4d  retn
0x180056d4e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056d54  mov     ebx, 80041008h
0x180056d59  mov     edx, ebx
0x180056d5b  mov     rcx, rax
0x180056d5e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056d64  lea     rax, WPP_GLOBAL_Control
0x180056d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d72  cmp     rcx, rax
0x180056d75  jnz     loc_18005705D
0x180056d7b  mov     eax, ebx
0x180056d7d  jmp     short loc_180056D40
0x180056d7f  mov     r8d, 3
0x180056d85  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\WBEM\\CIMOM"
0x180056d8c  lea     rcx, [rsp+78h+var_58]
0x180056d91  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180056d97  nop
0x180056d98  lea     r8, dword_1801A2760
0x180056d9f  lea     rdx, aMaxTasks; "Max Tasks"
0x180056da6  lea     rcx, [rsp+78h+var_58]
0x180056dab  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x180056db1  cmp     eax, 1
0x180056db4  jz      short loc_180056DD0
0x180056db6  mov     cs:dword_1801ADB98, 1
0x180056dc0  lea     rcx, [rsp+78h+var_58]
0x180056dc5  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180056dcb  jmp     loc_180056C8E
0x180056dd0  mov     r8d, cs:dword_1801A2760
0x180056dd7  lea     rdx, aMaxTasks; "Max Tasks"
0x180056dde  lea     rcx, [rsp+78h+var_58]
0x180056de3  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x180056de9  jmp     short loc_180056DB6
0x180056deb  mov     rcx, rdi; this
0x180056dee  call    ?IsESSNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsESSNamespace(void)
0x180056df3  mov     r12d, 4Bh ; 'K'
0x180056df9  test    eax, eax
0x180056dfb  jnz     loc_180056E9B
0x180056e01  call    ?IsProviderNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsProviderNamespace(void)
0x180056e06  test    eax, eax
0x180056e08  jnz     loc_180056E9B
0x180056e0e  cmp     r15b, 19h
0x180056e12  jz      loc_180056E9B
0x180056e18  cmp     [rbx+1B0h], eax
0x180056e1e  jnz     short loc_180056E9B
0x180056e20  xor     r14d, r14d
0x180056e23  mov     rdx, rdi; struct CWmiTask *
0x180056e26  call    ?IsTaskArbitrated@CWmiArbitrator@@QEAAHPEAVCWmiTask@@@Z; CWmiArbitrator::IsTaskArbitrated(CWmiTask *)
0x180056e2b  test    eax, eax
0x180056e2d  jz      short loc_180056E9B
0x180056e2f  cmp     [rbx+10h], ebp
0x180056e32  jbe     short loc_180056E9B
0x180056e34  mov     ecx, r12d; dwMilliseconds
0x180056e37  call    cs:__imp_Sleep
0x180056e3d  add     r14d, r12d
0x180056e40  call    ?GetMaxWaitBeforeDenial@ConfigMgr@@SAKXZ; ConfigMgr::GetMaxWaitBeforeDenial(void)
0x180056e45  cmp     r14d, eax
0x180056e48  jbe     short loc_180056E2F
0x180056e4a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056e50  mov     ebx, 80041045h
0x180056e55  mov     edx, ebx
0x180056e57  mov     rcx, rax
0x180056e5a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056e60  lea     rax, WPP_GLOBAL_Control
0x180056e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e6e  cmp     rcx, rax
0x180056e71  jz      loc_180056D7B
0x180056e77  test    byte ptr [rcx+1Ch], 1
0x180056e7b  jz      loc_180056D7B
0x180056e81  cmp     byte ptr [rcx+19h], 2
0x180056e85  jb      loc_180056D7B
0x180056e8b  mov     edx, 10h
0x180056e90  mov     r9d, 80041045h
0x180056e96  jmp     loc_18005707C
0x180056e9b  xor     ebp, ebp
0x180056e9d  cmp     [rbx+1B0h], ebp
0x180056ea3  jnz     loc_180056F4F
0x180056ea9  xor     edx, edx; struct CCoreExecReq *
0x180056eab  mov     rcx, rbx; this
0x180056eae  call    ?AcceptsNewTasks@CWmiArbitrator@@QEAAHPEAVCCoreExecReq@@@Z; CWmiArbitrator::AcceptsNewTasks(CCoreExecReq *)
0x180056eb3  test    eax, eax
0x180056eb5  jnz     loc_180056F4F
0x180056ebb  mov     rcx, rdi; this
0x180056ebe  call    ?IsESSNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsESSNamespace(void)
0x180056ec3  test    eax, eax
0x180056ec5  jnz     loc_180056F4F
0x180056ecb  call    ?IsProviderNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsProviderNamespace(void)
0x180056ed0  test    eax, eax
0x180056ed2  jnz     short loc_180056F4F
0x180056ed4  cmp     [rbx+1B0h], eax
0x180056eda  jnz     short loc_180056F4F
0x180056edc  mov     rdx, rdi; struct CWmiTask *
0x180056edf  call    ?IsTaskArbitrated@CWmiArbitrator@@QEAAHPEAVCWmiTask@@@Z; CWmiArbitrator::IsTaskArbitrated(CWmiTask *)
0x180056ee4  cmp     eax, 1
0x180056ee7  jnz     short loc_180056F4F
0x180056ee9  mov     ecx, r12d; dwMilliseconds
0x180056eec  call    cs:__imp_Sleep
0x180056ef2  add     ebp, r12d
0x180056ef5  call    ?GetMaxWaitBeforeDenial@ConfigMgr@@SAKXZ; ConfigMgr::GetMaxWaitBeforeDenial(void)
0x180056efa  cmp     ebp, eax
0x180056efc  jbe     short loc_180056EA9
0x180056efe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056f04  mov     ebx, 8004106Ch
0x180056f09  mov     edx, ebx
0x180056f0b  mov     rcx, rax
0x180056f0e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056f14  lea     rax, WPP_GLOBAL_Control
0x180056f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f22  cmp     rcx, rax
0x180056f25  jz      loc_180056D7B
0x180056f2b  test    byte ptr [rcx+1Ch], 1
0x180056f2f  jz      loc_180056D7B
0x180056f35  cmp     byte ptr [rcx+19h], 2
0x180056f39  jb      loc_180056D7B
0x180056f3f  mov     edx, 11h
0x180056f44  mov     r9d, 8004106Ch
0x180056f4a  jmp     loc_18005707C
0x180056f4f  mov     rcx, rdi; this
0x180056f52  call    ?IsESSNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsESSNamespace(void)
0x180056f57  test    eax, eax
0x180056f59  jnz     loc_180056CB4
0x180056f5f  call    ?IsProviderNamespace@CWmiTask@@QEAAHXZ; CWmiTask::IsProviderNamespace(void)
0x180056f64  test    eax, eax
0x180056f66  jnz     loc_180056CB4
0x180056f6c  cmp     r15b, 19h
0x180056f70  jz      loc_180056CB4
0x180056f76  cmp     [rbx+1B0h], eax
0x180056f7c  jnz     loc_180056CB4
0x180056f82  mov     rdx, rdi; struct CWmiTask *
0x180056f85  call    ?IsTaskArbitrated@CWmiArbitrator@@QEAAHPEAVCWmiTask@@@Z; CWmiArbitrator::IsTaskArbitrated(CWmiTask *)
0x180056f8a  test    eax, eax
0x180056f8c  jz      loc_180056CB4
0x180056f92  mov     r14d, [rbx+14h]
0x180056f96  cmp     r14d, [rbx+7Ch]
0x180056f9a  jbe     loc_180056CB4
0x180056fa0  xor     ebp, ebp
0x180056fa2  call    ?GetNewTaskResistance@ConfigMgr@@SAKXZ; ConfigMgr::GetNewTaskResistance(void)
0x180056fa7  mov     r12d, eax
0x180056faa  imul    r12d, r14d
0x180056fae  cmp     ebp, r12d
0x180056fb1  jge     loc_180056CB4
0x180056fb7  mov     ecx, 4Bh ; 'K'; dwMilliseconds
0x180056fbc  call    cs:__imp_Sleep
0x180056fc2  add     ebp, 4Bh ; 'K'
0x180056fc5  mov     ecx, [rbx+7Ch]
0x180056fc8  cmp     [rbx+14h], ecx
0x180056fcb  ja      short loc_180056FAE
0x180056fcd  jmp     loc_180056CB4
0x180056fd2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056fd8  mov     ebx, 80041006h
0x180056fdd  mov     edx, ebx
0x180056fdf  mov     rcx, rax
0x180056fe2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056fe8  lea     rax, WPP_GLOBAL_Control
0x180056fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ff6  cmp     rcx, rax
0x180056ff9  jz      short loc_180057023
0x180056ffb  test    byte ptr [rcx+1Ch], 1
0x180056fff  jz      short loc_180057023
0x180057001  cmp     byte ptr [rcx+19h], 2
0x180057005  jb      short loc_180057023
0x180057007  mov     edx, 12h
0x18005700c  mov     r9d, 80041006h
0x180057012  lea     r8, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids
0x180057019  mov     rcx, [rcx+10h]
0x18005701d  call    WPP_SF_d
0x180057022  nop
0x180057023  lea     rcx, [rsp+78h+arg_8]
0x18005702b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180057031  jmp     loc_180056D7B
0x180057036  cmp     r15b, 19h
0x18005703a  jz      loc_180056D10
0x180057040  inc     dword ptr [rbx+10h]
0x180057043  cmp     dword ptr [rdi+1Ch], 0
0x180057047  jnz     loc_180056D10
0x18005704d  mov     rdx, rdi; struct CWmiTask *
0x180057050  mov     rcx, rbx; this
0x180057053  call    ?RegisterTaskForEntryThrottling@CWmiArbitrator@@QEAAJPEAVCWmiTask@@@Z; CWmiArbitrator::RegisterTaskForEntryThrottling(CWmiTask *)
0x180057058  jmp     loc_180056D10
0x18005705d  test    byte ptr [rcx+1Ch], 1
0x180057061  jz      loc_180056D7B
0x180057067  cmp     byte ptr [rcx+19h], 2
0x18005706b  jb      loc_180056D7B
0x180057071  mov     edx, 0Fh
0x180057076  mov     r9d, 80041008h
0x18005707c  lea     r8, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids
0x180057083  mov     rcx, [rcx+10h]
0x180057087  call    WPP_SF_d
0x18005708c  jmp     loc_180056D7B
```
