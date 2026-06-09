# UbpmProxySingleton::RunTask(JobMoniker &,Triggers::Trigulator &,Actions::ActionCollection &,ulong,User const &,ulong,std::map<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>> const &,_GUID *)

- ea: `0x18004c2b0`
- end: `0x18004c6da`
- name: `?RunTask@UbpmProxySingleton@@UEAAJAEAVJobMoniker@@AEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@KAEBVUser@@KAEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@PEAU_GUID@@@Z`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006a74`
- `0x18000cc40`
- `0x180011e40`
- `0x18002db74`
- `0x18003bd70`
- `0x1800433ac`
- `0x180045120`
- `0x18004c2b0`
- `0x180051830`
- `0x1800545f4`
- `0x180059140`
- `0x18007bde0`
- `0x18007c2f0`
- `0x18007c444`
- `0x1800829fa`

## import_xrefs

- `UBPM!UbpmCloseTriggerConsumer` at `0x18004c6b7`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18004c6b7`
- `UBPM!UbpmTriggerConsumerControl` at `0x18004c548`
- `UBPM!UbpmTriggerConsumerControl` at `0x18004c548`
- `UBPM!UbpmApiBufferFree` at `0x18004c592`
- `UBPM!UbpmApiBufferFree` at `0x18004c592`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004c331`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004c331`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c421`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004c421`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UbpmProxySingleton::RunTask(
        __int64 a1,
        JobMoniker *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        User *a6,
        int a7,
        __int64 a8,
        _OWORD *a9)
{
  PSID v11; // rsi
  __int64 *v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  int ActionArgs; // ebx
  char v16; // di
  const unsigned __int16 ***DomainAccount; // rax
  _OWORD ***v18; // r8
  int v19; // eax
  const unsigned __int16 **v20; // rax
  const unsigned __int16 *v21; // rsi
  const unsigned __int16 *Path; // rax
  EventManager *v23; // rcx
  __int64 v24; // rcx
  void *v25; // rdi
  __int64 v26; // rcx
  void *v27; // rdi
  void *v29; // [rsp+28h] [rbp-D8h]
  const struct _GUID *v30; // [rsp+30h] [rbp-D0h]
  PSID pSid; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD **v32; // [rsp+48h] [rbp-B8h] BYREF
  void *v33; // [rsp+50h] [rbp-B0h] BYREF
  void *v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  void *v36[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  void *v38[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+A4h] [rbp-5Ch]
  int v42; // [rsp+A8h] [rbp-58h]
  DWORD LengthSid; // [rsp+B0h] [rbp-50h]
  PSID v44; // [rsp+B8h] [rbp-48h]
  __int64 v45; // [rsp+C0h] [rbp-40h]
  char v46; // [rsp+C8h] [rbp-38h]
  void *v47; // [rsp+D0h] [rbp-30h]
  char v48; // [rsp+D8h] [rbp-28h]
  void *v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[80]; // [rsp+F0h] [rbp-10h] BYREF

  v35 = 0;
  memset_0(&v40, 0, 0x48u);
  v32 = 0;
  v11 = 0;
  pSid = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v34 = 0;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v33 = 0;
  v12 = (__int64 *)*((_QWORD *)a2 + 2);
  if ( v12 )
    v13 = *v12;
  else
    v13 = 0;
  v14 = UbpmOpenTriggerConsumer(a2, v13, &v35);
  ActionArgs = v14;
  if ( v14 > 0 )
    ActionArgs = (unsigned __int16)v14 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ActionArgs >> 31) & 0xFFFFFFFE) + 4 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
      *((_QWORD *)a2 + 3),
      ActionArgs);
  }
  v16 = 1;
  if ( ActionArgs < 0 )
    goto LABEL_27;
  v40 = 1;
  v42 = -1;
  v44 = 0;
  LengthSid = 0;
  v45 = 0;
  v41 = (a5 & 2) != 0;
  if ( (a5 & 4) != 0 )
  {
    v41 = ((a5 & 2) != 0) | 2;
    v42 = a7;
    if ( (*(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL) & 0x1000000) != 0 )
      v41 = ((a5 & 2) != 0) | 0x12;
  }
  if ( *(_QWORD *)a6 )
  {
    ActionArgs = User::LookupSid(a6, &pSid);
    v11 = pSid;
    if ( ActionArgs < 0 )
      goto LABEL_26;
    v41 |= 4u;
    v44 = pSid;
    LengthSid = GetLengthSid(pSid);
    if ( User::IsService(a6) )
    {
      v41 |= 8u;
    }
    else if ( (*(_DWORD *)(*((_QWORD *)a2 + 4) + 16LL) & 0x1000000) != 0 )
    {
      v41 |= 0x10u;
    }
  }
  if ( !*(_QWORD *)(a8 + 8) )
    goto LABEL_33;
  ActionArgs = UbpmProxySingleton::ExtractActionArgs(a4, v38, v36);
  if ( ActionArgs < 0 )
    goto LABEL_26;
  ActionArgs = UbpmProxySingleton::ExpandVariablesInStrings(v38, a8);
  if ( ActionArgs < 0 )
    goto LABEL_26;
  ActionArgs = UbpmProxySingleton::CreateShallowStringArray(v38, &v34);
  if ( ActionArgs < 0 )
    goto LABEL_26;
  if ( (unsigned __int64)(((char *)v38[1] - (char *)v38[0]) >> 3) <= 0xFF )
  {
    v46 = ((char *)v38[1] - (char *)v38[0]) >> 3;
    v47 = v34;
    ActionArgs = UbpmProxySingleton::ExpandVariablesInStrings(v36, a8);
    if ( ActionArgs < 0 )
      goto LABEL_26;
    ActionArgs = UbpmProxySingleton::CreateShallowStringArray(v36, &v33);
    if ( ActionArgs < 0 )
      goto LABEL_26;
    if ( (unsigned __int64)(((char *)v36[1] - (char *)v36[0]) >> 3) <= 0xFF )
    {
      v48 = ((char *)v36[1] - (char *)v36[0]) >> 3;
      v49 = v33;
LABEL_33:
      v18 = &v32;
      if ( !a9 )
        v18 = 0;
      v19 = UbpmTriggerConsumerControl(v35, &v40, v18);
      ActionArgs = v19;
      if ( v19 > 0 )
        ActionArgs = (unsigned __int16)v19 | 0x80070000;
      if ( ActionArgs >= 0 )
      {
        if ( !a9 )
          goto LABEL_50;
        if ( v32 )
        {
          *a9 = **v32;
          UbpmApiBufferFree();
          v32 = 0;
          goto LABEL_50;
        }
        ActionArgs = -2147418113;
      }
      goto LABEL_26;
    }
  }
  ActionArgs = -2147024882;
LABEL_26:
  v16 = 1;
LABEL_27:
  if ( v11 )
  {
    DomainAccount = (const unsigned __int16 ***)User::GetDomainAccount(a6, v50);
  }
  else
  {
    DomainAccount = (const unsigned __int16 ***)_bstr_t::_bstr_t((_bstr_t *)&pSid, L"(default user)");
    v16 = 2;
  }
  v20 = *DomainAccount;
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  Path = JobMoniker::GetPath(a2);
  EventManager::EvtReport(v23, &JOB_START_FAILED, Path, v21, ActionArgs, v29, v30);
  if ( (v16 & 2) != 0 )
  {
    v16 &= ~2u;
    _bstr_t::~_bstr_t((_bstr_t *)&pSid);
  }
  if ( (v16 & 1) != 0 )
    _bstr_t::~_bstr_t((_bstr_t *)v50);
LABEL_50:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ActionArgs >> 31) & 0xFFFFFFFE) + 4 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
      *((_QWORD *)a2 + 3),
      ActionArgs);
  }
  operator delete(v33);
  v25 = v36[0];
  if ( v36[0] )
  {
    std::vector<_bstr_t>::_Destroy(v24, v36[0], v36[1]);
    operator delete(v25);
  }
  operator delete(v34);
  v27 = v38[0];
  if ( v38[0] )
  {
    std::vector<_bstr_t>::_Destroy(v26, v38[0], v38[1]);
    operator delete(v27);
  }
  if ( v35 )
    UbpmCloseTriggerConsumer();
  return (unsigned int)ActionArgs;
}

```

## disassembly

```asm
0x18004c2b0  push    rbp
0x18004c2b2  push    rbx
0x18004c2b3  push    rsi
0x18004c2b4  push    rdi
0x18004c2b5  push    r12
0x18004c2b7  push    r13
0x18004c2b9  push    r14
0x18004c2bb  push    r15
0x18004c2bd  lea     rbp, [rsp-8]
0x18004c2c2  sub     rsp, 108h
0x18004c2c9  mov     r12, r9
0x18004c2cc  mov     r14, rdx
0x18004c2cf  xor     r13d, r13d
0x18004c2d2  mov     [rbp+40h+arg_8], r13d
0x18004c2d6  mov     [rsp+140h+var_E0], r13
0x18004c2db  xor     edx, edx; Val
0x18004c2dd  lea     r8d, [r13+48h]; Size
0x18004c2e1  lea     rcx, [rbp+40h+var_A0]; void *
0x18004c2e5  call    memset_0
0x18004c2ea  mov     [rsp+140h+var_F8], r13
0x18004c2ef  mov     esi, r13d
0x18004c2f2  mov     [rsp+140h+pSid], r13
0x18004c2f7  xorps   xmm0, xmm0
0x18004c2fa  movdqu  xmmword ptr [rbp+40h+var_C0], xmm0
0x18004c2ff  mov     [rbp+40h+var_B0], r13
0x18004c303  mov     [rsp+140h+var_E8], r13
0x18004c308  movdqu  xmmword ptr [rsp+140h+var_D8], xmm0
0x18004c30e  mov     [rsp+140h+var_C8], r13
0x18004c313  mov     [rsp+140h+var_F0], r13
0x18004c318  mov     rdx, [r14+10h]
0x18004c31c  test    rdx, rdx
0x18004c31f  jz      short loc_18004C326
0x18004c321  mov     rdx, [rdx]
0x18004c324  jmp     short loc_18004C329
0x18004c326  mov     rdx, r13
0x18004c329  lea     r8, [rsp+140h+var_E0]
0x18004c32e  mov     rcx, r14
0x18004c331  call    cs:__imp_UbpmOpenTriggerConsumer
0x18004c338  nop     dword ptr [rax+rax+00h]
0x18004c33d  mov     ebx, eax
0x18004c33f  test    eax, eax
0x18004c341  jle     short loc_18004C34C
0x18004c343  movzx   ebx, ax
0x18004c346  or      ebx, 80070000h
0x18004c34c  lea     rax, WPP_GLOBAL_Control
0x18004c353  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c35a  cmp     rcx, rax
0x18004c35d  jz      short loc_18004C398
0x18004c35f  test    dword ptr [rcx+1Ch], 100h
0x18004c366  jz      short loc_18004C398
0x18004c368  mov     edx, ebx
0x18004c36a  sar     edx, 1Fh
0x18004c36d  and     edx, 0FFFFFFFEh
0x18004c370  add     edx, 4
0x18004c373  movzx   eax, byte ptr [rcx+19h]
0x18004c377  cmp     eax, edx
0x18004c379  jb      short loc_18004C398
0x18004c37b  mov     edx, 0Ah
0x18004c380  mov     [rsp+140h+var_120], ebx
0x18004c384  mov     r9, [r14+18h]
0x18004c388  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x18004c38f  mov     rcx, [rcx+10h]
0x18004c393  call    WPP_SF_Sd
0x18004c398  mov     edi, 1
0x18004c39d  mov     r15, [rbp+40h+arg_28]
0x18004c3a1  test    ebx, ebx
0x18004c3a3  js      loc_18004C4BE
0x18004c3a9  mov     [rbp+40h+var_A0], edi
0x18004c3ac  mov     ecx, r13d
0x18004c3af  mov     [rbp+40h+var_98], 0FFFFFFFFh
0x18004c3b6  mov     [rbp+40h+var_88], r13
0x18004c3ba  mov     [rbp+40h+var_90], r13d
0x18004c3be  mov     [rbp+40h+var_80], r13
0x18004c3c2  test    [rbp+40h+arg_20], 2
0x18004c3c6  cmovnz  ecx, edi
0x18004c3c9  mov     [rbp+40h+var_9C], ecx
0x18004c3cc  mov     edi, 1000000h
0x18004c3d1  test    [rbp+40h+arg_20], 4
0x18004c3d5  jz      short loc_18004C3F5
0x18004c3d7  or      ecx, 2
0x18004c3da  mov     [rbp+40h+var_9C], ecx
0x18004c3dd  mov     eax, [rbp+40h+arg_30]
0x18004c3e3  mov     [rbp+40h+var_98], eax
0x18004c3e6  mov     rax, [r14+20h]
0x18004c3ea  test    [rax+10h], edi
0x18004c3ed  jz      short loc_18004C3F5
0x18004c3ef  or      ecx, 10h
0x18004c3f2  mov     [rbp+40h+var_9C], ecx
0x18004c3f5  cmp     [r15], r13
0x18004c3f8  jz      short loc_18004C44F
0x18004c3fa  lea     rdx, [rsp+140h+pSid]; void **
0x18004c3ff  mov     rcx, r15; this
0x18004c402  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18004c407  mov     ebx, eax
0x18004c409  mov     rsi, [rsp+140h+pSid]
0x18004c40e  test    eax, eax
0x18004c410  js      loc_18004C4B9
0x18004c416  or      [rbp+40h+var_9C], 4
0x18004c41a  mov     [rbp+40h+var_88], rsi
0x18004c41e  mov     rcx, rsi; pSid
0x18004c421  call    cs:__imp_GetLengthSid
0x18004c428  nop     dword ptr [rax+rax+00h]
0x18004c42d  mov     [rbp+40h+var_90], eax
0x18004c430  mov     rcx, r15; this
0x18004c433  call    ?IsService@User@@QEBA_NXZ; User::IsService(void)
0x18004c438  test    al, al
0x18004c43a  jz      short loc_18004C442
0x18004c43c  or      [rbp+40h+var_9C], 8
0x18004c440  jmp     short loc_18004C44F
0x18004c442  mov     rax, [r14+20h]
0x18004c446  test    [rax+10h], edi
0x18004c449  jz      short loc_18004C44F
0x18004c44b  or      [rbp+40h+var_9C], 10h
0x18004c44f  mov     rdi, [rbp+40h+arg_38]
0x18004c456  cmp     [rdi+8], r13
0x18004c45a  jbe     loc_18004C52C
0x18004c460  lea     r8, [rsp+140h+var_D8]
0x18004c465  lea     rdx, [rbp+40h+var_C0]
0x18004c469  mov     rcx, r12
0x18004c46c  call    ?ExtractActionArgs@UbpmProxySingleton@@CAJAEAVActionCollection@Actions@@AEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@1@Z; UbpmProxySingleton::ExtractActionArgs(Actions::ActionCollection &,std::vector<_bstr_t> &,std::vector<_bstr_t> &)
0x18004c471  mov     ebx, eax
0x18004c473  test    eax, eax
0x18004c475  js      short loc_18004C4B9
0x18004c477  mov     rdx, rdi
0x18004c47a  lea     rcx, [rbp+40h+var_C0]
0x18004c47e  call    ?ExpandVariablesInStrings@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@3@H@Z; UbpmProxySingleton::ExpandVariablesInStrings(std::vector<_bstr_t> &,std::map<_bstr_t,_bstr_t> const &,int)
0x18004c483  mov     ebx, eax
0x18004c485  test    eax, eax
0x18004c487  js      short loc_18004C4B9
0x18004c489  lea     rdx, [rsp+140h+var_E8]
0x18004c48e  lea     rcx, [rbp+40h+var_C0]
0x18004c492  call    ?CreateShallowStringArray@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAV?$AutoVectorPtr@PEAG@wmi@@@Z; UbpmProxySingleton::CreateShallowStringArray(std::vector<_bstr_t> &,wmi::AutoVectorPtr<ushort *> &)
0x18004c497  mov     ebx, eax
0x18004c499  test    eax, eax
0x18004c49b  js      short loc_18004C4B9
0x18004c49d  mov     rax, [rbp+40h+var_C0+8]
0x18004c4a1  sub     rax, [rbp+40h+var_C0]
0x18004c4a5  sar     rax, 3
0x18004c4a9  mov     r12d, 0FFh
0x18004c4af  cmp     rax, r12
0x18004c4b2  jbe     short loc_18004C4D9
0x18004c4b4  mov     ebx, 8007000Eh
0x18004c4b9  mov     edi, 1
0x18004c4be  test    rsi, rsi
0x18004c4c1  jz      loc_18004C5A5
0x18004c4c7  lea     rdx, [rbp+40h+var_50]
0x18004c4cb  mov     rcx, r15
0x18004c4ce  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x18004c4d3  nop
0x18004c4d4  jmp     loc_18004C5BB
0x18004c4d9  mov     [rbp+40h+var_78], al
0x18004c4dc  mov     rax, [rsp+140h+var_E8]
0x18004c4e1  mov     [rbp+40h+var_70], rax
0x18004c4e5  mov     rdx, rdi
0x18004c4e8  lea     rcx, [rsp+140h+var_D8]
0x18004c4ed  call    ?ExpandVariablesInStrings@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@3@H@Z; UbpmProxySingleton::ExpandVariablesInStrings(std::vector<_bstr_t> &,std::map<_bstr_t,_bstr_t> const &,int)
0x18004c4f2  mov     ebx, eax
0x18004c4f4  test    eax, eax
0x18004c4f6  js      short loc_18004C4B9
0x18004c4f8  lea     rdx, [rsp+140h+var_F0]
0x18004c4fd  lea     rcx, [rsp+140h+var_D8]
0x18004c502  call    ?CreateShallowStringArray@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAV?$AutoVectorPtr@PEAG@wmi@@@Z; UbpmProxySingleton::CreateShallowStringArray(std::vector<_bstr_t> &,wmi::AutoVectorPtr<ushort *> &)
0x18004c507  mov     ebx, eax
0x18004c509  test    eax, eax
0x18004c50b  js      short loc_18004C4B9
0x18004c50d  mov     rax, [rsp+140h+var_D8+8]
0x18004c512  sub     rax, [rsp+140h+var_D8]
0x18004c517  sar     rax, 3
0x18004c51b  cmp     rax, r12
0x18004c51e  ja      short loc_18004C4B4
0x18004c520  mov     [rbp+40h+var_68], al
0x18004c523  mov     rax, [rsp+140h+var_F0]
0x18004c528  mov     [rbp+40h+var_60], rax
0x18004c52c  lea     r8, [rsp+140h+var_F8]
0x18004c531  mov     rdi, [rbp+40h+arg_40]
0x18004c538  test    rdi, rdi
0x18004c53b  cmovz   r8, r13
0x18004c53f  lea     rdx, [rbp+40h+var_A0]
0x18004c543  mov     rcx, [rsp+140h+var_E0]
0x18004c548  call    cs:__imp_UbpmTriggerConsumerControl
0x18004c54f  nop     dword ptr [rax+rax+00h]
0x18004c554  mov     ebx, eax
0x18004c556  test    eax, eax
0x18004c558  jle     short loc_18004C563
0x18004c55a  movzx   ebx, ax
0x18004c55d  or      ebx, 80070000h
0x18004c563  test    ebx, ebx
0x18004c565  js      loc_18004C4B9
0x18004c56b  test    rdi, rdi
0x18004c56e  jz      loc_18004C60C
0x18004c574  mov     rcx, [rsp+140h+var_F8]
0x18004c579  test    rcx, rcx
0x18004c57c  jnz     short loc_18004C588
0x18004c57e  mov     ebx, 8000FFFFh
0x18004c583  jmp     loc_18004C4B9
0x18004c588  mov     rax, [rcx]
0x18004c58b  movups  xmm0, xmmword ptr [rax]
0x18004c58e  movdqu  xmmword ptr [rdi], xmm0
0x18004c592  call    cs:__imp_UbpmApiBufferFree
0x18004c599  nop     dword ptr [rax+rax+00h]
0x18004c59e  mov     [rsp+140h+var_F8], r13
0x18004c5a3  jmp     short loc_18004C60C
0x18004c5a5  lea     rdx, aDefaultUser; "(default user)"
0x18004c5ac  lea     rcx, [rsp+140h+pSid]; this
0x18004c5b1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c5b6  mov     edi, 2
0x18004c5bb  mov     rax, [rax]
0x18004c5be  test    rax, rax
0x18004c5c1  jz      short loc_18004C5C8
0x18004c5c3  mov     rsi, [rax]
0x18004c5c6  jmp     short loc_18004C5CB
0x18004c5c8  mov     rsi, r13
0x18004c5cb  mov     rcx, r14; this
0x18004c5ce  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004c5d3  mov     [rsp+140h+var_120], ebx; unsigned int
0x18004c5d7  mov     r9, rsi; unsigned __int16 *
0x18004c5da  mov     r8, rax; unsigned __int16 *
0x18004c5dd  lea     rdx, JOB_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004c5e4  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)
0x18004c5e9  test    dil, 2
0x18004c5ed  jz      short loc_18004C5FD
0x18004c5ef  and     edi, 0FFFFFFFDh
0x18004c5f2  lea     rcx, [rsp+140h+pSid]; this
0x18004c5f7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18004c5fc  nop
0x18004c5fd  test    dil, 1
0x18004c601  jz      short loc_18004C60C
0x18004c603  lea     rcx, [rbp+40h+var_50]; this
0x18004c607  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18004c60c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c613  lea     rax, WPP_GLOBAL_Control
0x18004c61a  cmp     rcx, rax
0x18004c61d  jz      short loc_18004C659
0x18004c61f  test    dword ptr [rcx+1Ch], 100h
0x18004c626  jz      short loc_18004C659
0x18004c628  mov     edx, ebx
0x18004c62a  sar     edx, 1Fh
0x18004c62d  and     edx, 0FFFFFFFEh
0x18004c630  add     edx, 4
0x18004c633  movzx   eax, byte ptr [rcx+19h]
0x18004c637  cmp     eax, edx
0x18004c639  jb      short loc_18004C659
0x18004c63b  mov     edx, 0Eh
0x18004c640  mov     [rsp+140h+var_120], ebx
0x18004c644  mov     r9, [r14+18h]
0x18004c648  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x18004c64f  mov     rcx, [rcx+10h]
0x18004c653  call    WPP_SF_Sd
0x18004c658  nop
0x18004c659  mov     rcx, [rsp+140h+var_F0]; void *
0x18004c65e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c663  nop
0x18004c664  mov     rdi, [rsp+140h+var_D8]
0x18004c669  test    rdi, rdi
0x18004c66c  jz      short loc_18004C684
0x18004c66e  mov     r8, [rsp+140h+var_D8+8]
0x18004c673  mov     rdx, rdi
0x18004c676  call    ?_Destroy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@IEAAXPEAV_bstr_t@@0@Z; std::vector<_bstr_t>::_Destroy(_bstr_t *,_bstr_t *)
0x18004c67b  mov     rcx, rdi; void *
0x18004c67e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c683  nop
0x18004c684  mov     rcx, [rsp+140h+var_E8]; void *
0x18004c689  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c68e  nop
0x18004c68f  mov     rdi, [rbp+40h+var_C0]
0x18004c693  test    rdi, rdi
0x18004c696  jz      short loc_18004C6AD
0x18004c698  mov     r8, [rbp+40h+var_C0+8]
0x18004c69c  mov     rdx, rdi
0x18004c69f  call    ?_Destroy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@IEAAXPEAV_bstr_t@@0@Z; std::vector<_bstr_t>::_Destroy(_bstr_t *,_bstr_t *)
0x18004c6a4  mov     rcx, rdi; void *
0x18004c6a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c6ac  nop
0x18004c6ad  mov     rcx, [rsp+140h+var_E0]
0x18004c6b2  test    rcx, rcx
0x18004c6b5  jz      short loc_18004C6C3
0x18004c6b7  call    cs:__imp_UbpmCloseTriggerConsumer
0x18004c6be  nop     dword ptr [rax+rax+00h]
0x18004c6c3  mov     eax, ebx
0x18004c6c5  add     rsp, 108h
0x18004c6cc  pop     r15
0x18004c6ce  pop     r14
0x18004c6d0  pop     r13
0x18004c6d2  pop     r12
0x18004c6d4  pop     rdi
0x18004c6d5  pop     rsi
0x18004c6d6  pop     rbx
0x18004c6d7  pop     rbp
0x18004c6d8  retn
```
