# CTicketManager::Redeem(unsigned __int64,unsigned __int64,uchar *,unsigned __int64 *,std::vector<uchar,wil::secure_allocator<uchar>> *,_WINBIO_RPC_NGC_AUTHORIZATION * *)

- ea: `0x180003694`
- end: `0x1800038e4`
- name: `?Redeem@CTicketManager@@SAJ_K0PEAEPEA_KPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAPEAU_WINBIO_RPC_NGC_AUTHORIZATION@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(__int64, __int64, void *, _QWORD *, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800030f0`
- `0x180061780`
- `0x1800bc4a0`

## callees

- `0x180003694`
- `0x18000394c`
- `0x1800039f4`
- `0x180004728`
- `0x180023d88`
- `0x180055878`
- `0x1800559c8`
- `0x180056e84`
- `0x180068f60`
- `0x180069cc8`
- `0x180092d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800038a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800038a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000371e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000371e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000375e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000375e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800037ce`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800037ce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800037b6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800037b6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003771`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003771`

## string_xrefs

- `0x180003795`: `onecore\ds\security\biometrics\service\server\ticketmanager.cpp`
- `0x180003888`: `onecore\ds\security\biometrics\service\server\ticketmanager.cpp`

## pseudocode

```c
__int64 __fastcall CTicketManager::Redeem(__int64 a1, __int64 a2, void *a3, _QWORD *a4, __int64 a5, _QWORD *a6)
{
  RTL_SRWLOCK *v9; // r15
  __int64 *v10; // rdi
  __int64 *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // r12
  DWORD LengthSid; // eax
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // rax
  struct CTicketManager *v18; // rax
  __int64 v19; // rcx
  const char *v21; // [rsp+28h] [rbp-270h]
  _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-268h] BYREF
  RTL_SRWLOCK *v23; // [rsp+38h] [rbp-260h]
  _BYTE v24[528]; // [rsp+40h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 || !a4 )
    return 2147500035LL;
  memset_0(a3, 0, 0x44u);
  *a4 = 0;
  if ( a6 )
    *a6 = 0;
  v9 = (RTL_SRWLOCK *)((char *)CTicketManager::Instance() + 8);
  AcquireSRWLockExclusive(v9);
  v23 = v9;
  v10 = (__int64 *)*((_QWORD *)CTicketManager::Instance() + 2);
  v11 = (__int64 *)*((_QWORD *)CTicketManager::Instance() + 2);
  while ( 1 )
  {
    v11 = (__int64 *)*v11;
    if ( v11 == v10 )
      break;
    if ( *(_QWORD *)v11[2] == a1 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)(v11[2] + 80)) > 0 )
      {
        v12 = wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x181,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ticketmanager.cpp",
                (const char *)0x80098044LL,
                (int)"Ticket expired",
                v21);
LABEL_19:
        v18 = CTicketManager::Instance();
        *(_QWORD *)v11[1] = *v11;
        v19 = v11[1];
        *(_QWORD *)(*v11 + 8) = v19;
        --*((_QWORD *)v18 + 3);
        std::_List_node<std::shared_ptr<CProtectionTicket>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<CProtectionTicket>,void *>>>(
          v19,
          v11);
        goto LABEL_21;
      }
      v13 = v11[2];
      LengthSid = GetLengthSid((PSID)(v13 + 12));
      v15 = LengthSid;
      if ( LengthSid > 0x44uLL )
      {
        v12 = -2147024809;
        goto LABEL_19;
      }
      CopySid(LengthSid, a3, (PSID)(v13 + 12));
      *a4 = v15;
      v16 = v11[2];
      if ( a5 )
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a5, v16 + 88);
      if ( a6 )
      {
        v17 = *(_QWORD *)(v16 + 112);
        *(_QWORD *)(v16 + 112) = 0;
        *a6 = v17;
        v12 = 0;
        if ( !v17 )
          goto LABEL_19;
        CEtwEvent::CEtwEvent((CEtwEvent *)v24);
        CEtwEvent::CaptureSidInfo((CEtwEvent *)v24, a3);
        CEtwEvent::Write(v24, 1606, 1);
        CEtwEvent::~CEtwEvent((CEtwEvent *)v24);
      }
      v12 = 0;
      goto LABEL_19;
    }
  }
  v12 = wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ticketmanager.cpp",
          (const char *)0x80098044LL,
          (int)"Ticket not found",
          v21);
LABEL_21:
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  return v12;
}

```

## disassembly

```asm
0x180003694  mov     [rsp+arg_0], rbx
0x180003699  push    rbp
0x18000369a  push    rsi
0x18000369b  push    rdi
0x18000369c  push    r12
0x18000369e  push    r13
0x1800036a0  push    r14
0x1800036a2  push    r15
0x1800036a4  sub     rsp, 260h
0x1800036ab  mov     rax, cs:__security_cookie
0x1800036b2  xor     rax, rsp
0x1800036b5  mov     [rsp+298h+var_48], rax
0x1800036bd  mov     r14, r9
0x1800036c0  mov     rbp, r8
0x1800036c3  mov     r12, rcx
0x1800036c6  mov     r13, [rsp+298h+arg_20]
0x1800036ce  mov     rsi, [rsp+298h+arg_28]
0x1800036d6  test    rcx, rcx
0x1800036d9  jz      loc_1800038B4
0x1800036df  test    r8, r8
0x1800036e2  jz      loc_1800038AD
0x1800036e8  test    r9, r9
0x1800036eb  jz      loc_1800038AD
0x1800036f1  xor     edx, edx; Val
0x1800036f3  lea     r8d, [rdx+44h]; Size
0x1800036f7  mov     rcx, rbp; void *
0x1800036fa  call    memset_0
0x1800036ff  mov     qword ptr [r14], 0
0x180003706  test    rsi, rsi
0x180003709  jz      short loc_180003712
0x18000370b  mov     qword ptr [rsi], 0
0x180003712  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x180003717  lea     r15, [rax+8]
0x18000371b  mov     rcx, r15; SRWLock
0x18000371e  call    cs:__imp_AcquireSRWLockExclusive
0x180003724  mov     [rsp+298h+var_260], r15
0x180003729  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18000372e  mov     rdi, [rax+10h]
0x180003732  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x180003737  mov     rbx, [rax+10h]
0x18000373b  mov     rbx, [rbx]
0x18000373e  cmp     rbx, rdi
0x180003741  jz      loc_18000386E
0x180003747  mov     rax, [rbx+10h]
0x18000374b  cmp     [rax], r12
0x18000374e  jnz     short loc_18000373B
0x180003750  mov     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003759  lea     rcx, [rsp+298h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000375e  call    cs:__imp_GetSystemTimeAsFileTime
0x180003764  mov     rdx, [rbx+10h]
0x180003768  add     rdx, 50h ; 'P'; lpFileTime2
0x18000376c  lea     rcx, [rsp+298h+SystemTimeAsFileTime]; lpFileTime1
0x180003771  call    cs:__imp_CompareFileTime
0x180003777  test    eax, eax
0x180003779  jle     short loc_1800037AD
0x18000377b  mov     rcx, [rsp+298h]; this
0x180003783  lea     rax, aTicketExpired; "Ticket expired"
0x18000378a  mov     qword ptr [rsp+298h+var_278], rax; int
0x18000378f  mov     r9d, 80098044h; char *
0x180003795  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x18000379c  mov     edx, 181h; void *
0x1800037a1  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800037a6  mov     edi, eax
0x1800037a8  jmp     loc_180003846
0x1800037ad  mov     r12, [rbx+10h]
0x1800037b1  lea     rcx, [r12+0Ch]; pSid
0x1800037b6  call    cs:__imp_GetLengthSid
0x1800037bc  mov     edi, eax
0x1800037be  cmp     rdi, 44h ; 'D'
0x1800037c2  ja      short loc_180003841
0x1800037c4  lea     r8, [r12+0Ch]; pSourceSid
0x1800037c9  mov     rdx, rbp; pDestinationSid
0x1800037cc  mov     ecx, edi; nDestinationSidLength
0x1800037ce  call    cs:__imp_CopySid
0x1800037d4  mov     [r14], rdi
0x1800037d7  mov     rdi, [rbx+10h]
0x1800037db  test    r13, r13
0x1800037de  jz      short loc_1800037EC
0x1800037e0  lea     rdx, [rdi+58h]
0x1800037e4  mov     rcx, r13
0x1800037e7  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x1800037ec  test    rsi, rsi
0x1800037ef  jz      short loc_18000383D
0x1800037f1  mov     rax, [rdi+70h]
0x1800037f5  mov     qword ptr [rdi+70h], 0
0x1800037fd  mov     [rsi], rax
0x180003800  xor     edi, edi
0x180003802  test    rax, rax
0x180003805  jz      short loc_180003846
0x180003807  lea     rcx, [rsp+298h+var_258]; this
0x18000380c  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x180003811  nop
0x180003812  mov     rdx, rbp; void *
0x180003815  lea     rcx, [rsp+298h+var_258]; this
0x18000381a  call    ?CaptureSidInfo@CEtwEvent@@QEAAXPEAX@Z; CEtwEvent::CaptureSidInfo(void *)
0x18000381f  mov     edx, 646h
0x180003824  lea     r8d, [rdi+1]
0x180003828  lea     rcx, [rsp+298h+var_258]
0x18000382d  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x180003832  nop
0x180003833  lea     rcx, [rsp+298h+var_258]; this
0x180003838  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18000383d  xor     edi, edi
0x18000383f  jmp     short loc_180003846
0x180003841  mov     edi, 80070057h
0x180003846  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18000384b  mov     rdx, [rbx+8]
0x18000384f  mov     rcx, [rbx]
0x180003852  mov     [rdx], rcx
0x180003855  mov     rdx, [rbx]
0x180003858  mov     rcx, [rbx+8]
0x18000385c  mov     [rdx+8], rcx
0x180003860  dec     qword ptr [rax+18h]
0x180003864  mov     rdx, rbx
0x180003867  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@VCProtectionTicket@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VCProtectionTicket@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VCProtectionTicket@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<CProtectionTicket>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<CProtectionTicket>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<CProtectionTicket>,void *>> &,std::_List_node<std::shared_ptr<CProtectionTicket>,void *> *)
0x18000386c  jmp     short loc_18000389B
0x18000386e  mov     rcx, [rsp+298h]; this
0x180003876  lea     rax, aTicketNotFound; "Ticket not found"
0x18000387d  mov     qword ptr [rsp+298h+var_278], rax; int
0x180003882  mov     r9d, 80098044h; char *
0x180003888  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x18000388f  mov     edx, 177h; void *
0x180003894  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180003899  mov     edi, eax
0x18000389b  test    r15, r15
0x18000389e  jz      short loc_1800038A9
0x1800038a0  mov     rcx, r15; SRWLock
0x1800038a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800038a9  mov     eax, edi
0x1800038ab  jmp     short loc_1800038B9
0x1800038ad  mov     eax, 80004003h
0x1800038b2  jmp     short loc_1800038B9
0x1800038b4  mov     eax, 80070057h
0x1800038b9  mov     rcx, [rsp+298h+var_48]
0x1800038c1  xor     rcx, rsp; StackCookie
0x1800038c4  call    __security_check_cookie
0x1800038c9  mov     rbx, [rsp+298h+arg_0]
0x1800038d1  add     rsp, 260h
0x1800038d8  pop     r15
0x1800038da  pop     r14
0x1800038dc  pop     r13
0x1800038de  pop     r12
0x1800038e0  pop     rdi
0x1800038e1  pop     rsi
0x1800038e2  pop     rbp
0x1800038e3  retn
```
