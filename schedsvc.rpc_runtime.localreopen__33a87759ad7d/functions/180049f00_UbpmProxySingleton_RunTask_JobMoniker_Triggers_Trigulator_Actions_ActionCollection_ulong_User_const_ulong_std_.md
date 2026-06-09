# UbpmProxySingleton::RunTask(JobMoniker &,Triggers::Trigulator &,Actions::ActionCollection &,ulong,User const &,ulong,std::map<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>> const &,_GUID *)

- ea: `0x180049f00`
- end: `0x18004a30b`
- name: `?RunTask@UbpmProxySingleton@@UEAAJAEAVJobMoniker@@AEAVTrigulator@Triggers@@AEAVActionCollection@Actions@@KAEBVUser@@KAEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@PEAU_GUID@@@Z`
- size: `1035`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000dc30`
- `0x18001239c`
- `0x180016e3c`
- `0x18001a260`
- `0x18002132c`
- `0x1800290f0`
- `0x180042fa4`
- `0x180049f00`
- `0x18004f008`
- `0x180051f84`
- `0x180056794`
- `0x180077ce0`
- `0x1800781d4`
- `0x18007831c`
- `0x18007e68a`

## import_xrefs

- `UBPM!UbpmCloseTriggerConsumer` at `0x18004a2ef`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18004a2ef`
- `UBPM!UbpmTriggerConsumerControl` at `0x18004a18c`
- `UBPM!UbpmTriggerConsumerControl` at `0x18004a18c`
- `UBPM!UbpmApiBufferFree` at `0x18004a1d0`
- `UBPM!UbpmApiBufferFree` at `0x18004a1d0`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180049f81`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180049f81`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a06b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a06b`

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
0x180049f00  push    rbp
0x180049f02  push    rbx
0x180049f03  push    rsi
0x180049f04  push    rdi
0x180049f05  push    r12
0x180049f07  push    r13
0x180049f09  push    r14
0x180049f0b  push    r15
0x180049f0d  lea     rbp, [rsp-8]
0x180049f12  sub     rsp, 108h
0x180049f19  mov     r12, r9
0x180049f1c  mov     r14, rdx
0x180049f1f  xor     r13d, r13d
0x180049f22  mov     [rbp+40h+arg_8], r13d
0x180049f26  mov     [rsp+140h+var_E0], r13
0x180049f2b  xor     edx, edx; Val
0x180049f2d  lea     r8d, [r13+48h]; Size
0x180049f31  lea     rcx, [rbp+40h+var_A0]; void *
0x180049f35  call    memset_0
0x180049f3a  mov     [rsp+140h+var_F8], r13
0x180049f3f  mov     esi, r13d
0x180049f42  mov     [rsp+140h+pSid], r13
0x180049f47  xorps   xmm0, xmm0
0x180049f4a  movdqu  xmmword ptr [rbp+40h+var_C0], xmm0
0x180049f4f  mov     [rbp+40h+var_B0], r13
0x180049f53  mov     [rsp+140h+var_E8], r13
0x180049f58  movdqu  xmmword ptr [rsp+140h+var_D8], xmm0
0x180049f5e  mov     [rsp+140h+var_C8], r13
0x180049f63  mov     [rsp+140h+var_F0], r13
0x180049f68  mov     rdx, [r14+10h]
0x180049f6c  test    rdx, rdx
0x180049f6f  jz      short loc_180049F76
0x180049f71  mov     rdx, [rdx]
0x180049f74  jmp     short loc_180049F79
0x180049f76  mov     rdx, r13
0x180049f79  lea     r8, [rsp+140h+var_E0]
0x180049f7e  mov     rcx, r14
0x180049f81  call    cs:__imp_UbpmOpenTriggerConsumer
0x180049f87  mov     ebx, eax
0x180049f89  test    eax, eax
0x180049f8b  jle     short loc_180049F96
0x180049f8d  movzx   ebx, ax
0x180049f90  or      ebx, 80070000h
0x180049f96  lea     rax, WPP_GLOBAL_Control
0x180049f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fa4  cmp     rcx, rax
0x180049fa7  jz      short loc_180049FE2
0x180049fa9  test    dword ptr [rcx+1Ch], 100h
0x180049fb0  jz      short loc_180049FE2
0x180049fb2  mov     edx, ebx
0x180049fb4  sar     edx, 1Fh
0x180049fb7  and     edx, 0FFFFFFFEh
0x180049fba  add     edx, 4
0x180049fbd  movzx   eax, byte ptr [rcx+19h]
0x180049fc1  cmp     eax, edx
0x180049fc3  jb      short loc_180049FE2
0x180049fc5  mov     edx, 0Ah
0x180049fca  mov     [rsp+140h+var_120], ebx
0x180049fce  mov     r9, [r14+18h]
0x180049fd2  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x180049fd9  mov     rcx, [rcx+10h]
0x180049fdd  call    WPP_SF_Sd
0x180049fe2  mov     edi, 1
0x180049fe7  mov     r15, [rbp+40h+arg_28]
0x180049feb  test    ebx, ebx
0x180049fed  js      loc_18004A102
0x180049ff3  mov     [rbp+40h+var_A0], edi
0x180049ff6  mov     ecx, r13d
0x180049ff9  mov     [rbp+40h+var_98], 0FFFFFFFFh
0x18004a000  mov     [rbp+40h+var_88], r13
0x18004a004  mov     [rbp+40h+var_90], r13d
0x18004a008  mov     [rbp+40h+var_80], r13
0x18004a00c  test    [rbp+40h+arg_20], 2
0x18004a010  cmovnz  ecx, edi
0x18004a013  mov     [rbp+40h+var_9C], ecx
0x18004a016  mov     edi, 1000000h
0x18004a01b  test    [rbp+40h+arg_20], 4
0x18004a01f  jz      short loc_18004A03F
0x18004a021  or      ecx, 2
0x18004a024  mov     [rbp+40h+var_9C], ecx
0x18004a027  mov     eax, [rbp+40h+arg_30]
0x18004a02d  mov     [rbp+40h+var_98], eax
0x18004a030  mov     rax, [r14+20h]
0x18004a034  test    [rax+10h], edi
0x18004a037  jz      short loc_18004A03F
0x18004a039  or      ecx, 10h
0x18004a03c  mov     [rbp+40h+var_9C], ecx
0x18004a03f  cmp     [r15], r13
0x18004a042  jz      short loc_18004A093
0x18004a044  lea     rdx, [rsp+140h+pSid]; void **
0x18004a049  mov     rcx, r15; this
0x18004a04c  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18004a051  mov     ebx, eax
0x18004a053  mov     rsi, [rsp+140h+pSid]
0x18004a058  test    eax, eax
0x18004a05a  js      loc_18004A0FD
0x18004a060  or      [rbp+40h+var_9C], 4
0x18004a064  mov     [rbp+40h+var_88], rsi
0x18004a068  mov     rcx, rsi; pSid
0x18004a06b  call    cs:__imp_GetLengthSid
0x18004a071  mov     [rbp+40h+var_90], eax
0x18004a074  mov     rcx, r15; this
0x18004a077  call    ?IsService@User@@QEBA_NXZ; User::IsService(void)
0x18004a07c  test    al, al
0x18004a07e  jz      short loc_18004A086
0x18004a080  or      [rbp+40h+var_9C], 8
0x18004a084  jmp     short loc_18004A093
0x18004a086  mov     rax, [r14+20h]
0x18004a08a  test    [rax+10h], edi
0x18004a08d  jz      short loc_18004A093
0x18004a08f  or      [rbp+40h+var_9C], 10h
0x18004a093  mov     rdi, [rbp+40h+arg_38]
0x18004a09a  cmp     [rdi+8], r13
0x18004a09e  jbe     loc_18004A170
0x18004a0a4  lea     r8, [rsp+140h+var_D8]
0x18004a0a9  lea     rdx, [rbp+40h+var_C0]
0x18004a0ad  mov     rcx, r12
0x18004a0b0  call    ?ExtractActionArgs@UbpmProxySingleton@@CAJAEAVActionCollection@Actions@@AEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@1@Z; UbpmProxySingleton::ExtractActionArgs(Actions::ActionCollection &,std::vector<_bstr_t> &,std::vector<_bstr_t> &)
0x18004a0b5  mov     ebx, eax
0x18004a0b7  test    eax, eax
0x18004a0b9  js      short loc_18004A0FD
0x18004a0bb  mov     rdx, rdi
0x18004a0be  lea     rcx, [rbp+40h+var_C0]
0x18004a0c2  call    ?ExpandVariablesInStrings@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@3@H@Z; UbpmProxySingleton::ExpandVariablesInStrings(std::vector<_bstr_t> &,std::map<_bstr_t,_bstr_t> const &,int)
0x18004a0c7  mov     ebx, eax
0x18004a0c9  test    eax, eax
0x18004a0cb  js      short loc_18004A0FD
0x18004a0cd  lea     rdx, [rsp+140h+var_E8]
0x18004a0d2  lea     rcx, [rbp+40h+var_C0]
0x18004a0d6  call    ?CreateShallowStringArray@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAV?$AutoVectorPtr@PEAG@wmi@@@Z; UbpmProxySingleton::CreateShallowStringArray(std::vector<_bstr_t> &,wmi::AutoVectorPtr<ushort *> &)
0x18004a0db  mov     ebx, eax
0x18004a0dd  test    eax, eax
0x18004a0df  js      short loc_18004A0FD
0x18004a0e1  mov     rax, [rbp+40h+var_C0+8]
0x18004a0e5  sub     rax, [rbp+40h+var_C0]
0x18004a0e9  sar     rax, 3
0x18004a0ed  mov     r12d, 0FFh
0x18004a0f3  cmp     rax, r12
0x18004a0f6  jbe     short loc_18004A11D
0x18004a0f8  mov     ebx, 8007000Eh
0x18004a0fd  mov     edi, 1
0x18004a102  test    rsi, rsi
0x18004a105  jz      loc_18004A1DD
0x18004a10b  lea     rdx, [rbp+40h+var_50]
0x18004a10f  mov     rcx, r15
0x18004a112  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x18004a117  nop
0x18004a118  jmp     loc_18004A1F3
0x18004a11d  mov     [rbp+40h+var_78], al
0x18004a120  mov     rax, [rsp+140h+var_E8]
0x18004a125  mov     [rbp+40h+var_70], rax
0x18004a129  mov     rdx, rdi
0x18004a12c  lea     rcx, [rsp+140h+var_D8]
0x18004a131  call    ?ExpandVariablesInStrings@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@3@H@Z; UbpmProxySingleton::ExpandVariablesInStrings(std::vector<_bstr_t> &,std::map<_bstr_t,_bstr_t> const &,int)
0x18004a136  mov     ebx, eax
0x18004a138  test    eax, eax
0x18004a13a  js      short loc_18004A0FD
0x18004a13c  lea     rdx, [rsp+140h+var_F0]
0x18004a141  lea     rcx, [rsp+140h+var_D8]
0x18004a146  call    ?CreateShallowStringArray@UbpmProxySingleton@@CAJAEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAV?$AutoVectorPtr@PEAG@wmi@@@Z; UbpmProxySingleton::CreateShallowStringArray(std::vector<_bstr_t> &,wmi::AutoVectorPtr<ushort *> &)
0x18004a14b  mov     ebx, eax
0x18004a14d  test    eax, eax
0x18004a14f  js      short loc_18004A0FD
0x18004a151  mov     rax, [rsp+140h+var_D8+8]
0x18004a156  sub     rax, [rsp+140h+var_D8]
0x18004a15b  sar     rax, 3
0x18004a15f  cmp     rax, r12
0x18004a162  ja      short loc_18004A0F8
0x18004a164  mov     [rbp+40h+var_68], al
0x18004a167  mov     rax, [rsp+140h+var_F0]
0x18004a16c  mov     [rbp+40h+var_60], rax
0x18004a170  lea     r8, [rsp+140h+var_F8]
0x18004a175  mov     rdi, [rbp+40h+arg_40]
0x18004a17c  test    rdi, rdi
0x18004a17f  cmovz   r8, r13
0x18004a183  lea     rdx, [rbp+40h+var_A0]
0x18004a187  mov     rcx, [rsp+140h+var_E0]
0x18004a18c  call    cs:__imp_UbpmTriggerConsumerControl
0x18004a192  mov     ebx, eax
0x18004a194  test    eax, eax
0x18004a196  jle     short loc_18004A1A1
0x18004a198  movzx   ebx, ax
0x18004a19b  or      ebx, 80070000h
0x18004a1a1  test    ebx, ebx
0x18004a1a3  js      loc_18004A0FD
0x18004a1a9  test    rdi, rdi
0x18004a1ac  jz      loc_18004A244
0x18004a1b2  mov     rcx, [rsp+140h+var_F8]
0x18004a1b7  test    rcx, rcx
0x18004a1ba  jnz     short loc_18004A1C6
0x18004a1bc  mov     ebx, 8000FFFFh
0x18004a1c1  jmp     loc_18004A0FD
0x18004a1c6  mov     rax, [rcx]
0x18004a1c9  movups  xmm0, xmmword ptr [rax]
0x18004a1cc  movdqu  xmmword ptr [rdi], xmm0
0x18004a1d0  call    cs:__imp_UbpmApiBufferFree
0x18004a1d6  mov     [rsp+140h+var_F8], r13
0x18004a1db  jmp     short loc_18004A244
0x18004a1dd  lea     rdx, aDefaultUser; "(default user)"
0x18004a1e4  lea     rcx, [rsp+140h+pSid]; this
0x18004a1e9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a1ee  mov     edi, 2
0x18004a1f3  mov     rax, [rax]
0x18004a1f6  test    rax, rax
0x18004a1f9  jz      short loc_18004A200
0x18004a1fb  mov     rsi, [rax]
0x18004a1fe  jmp     short loc_18004A203
0x18004a200  mov     rsi, r13
0x18004a203  mov     rcx, r14; this
0x18004a206  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18004a20b  mov     [rsp+140h+var_120], ebx; unsigned int
0x18004a20f  mov     r9, rsi; unsigned __int16 *
0x18004a212  mov     r8, rax; unsigned __int16 *
0x18004a215  lea     rdx, JOB_START_FAILED; struct _EVENT_DESCRIPTOR *
0x18004a21c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)
0x18004a221  test    dil, 2
0x18004a225  jz      short loc_18004A235
0x18004a227  and     edi, 0FFFFFFFDh
0x18004a22a  lea     rcx, [rsp+140h+pSid]; this
0x18004a22f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18004a234  nop
0x18004a235  test    dil, 1
0x18004a239  jz      short loc_18004A244
0x18004a23b  lea     rcx, [rbp+40h+var_50]; this
0x18004a23f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18004a244  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a24b  lea     rax, WPP_GLOBAL_Control
0x18004a252  cmp     rcx, rax
0x18004a255  jz      short loc_18004A291
0x18004a257  test    dword ptr [rcx+1Ch], 100h
0x18004a25e  jz      short loc_18004A291
0x18004a260  mov     edx, ebx
0x18004a262  sar     edx, 1Fh
0x18004a265  and     edx, 0FFFFFFFEh
0x18004a268  add     edx, 4
0x18004a26b  movzx   eax, byte ptr [rcx+19h]
0x18004a26f  cmp     eax, edx
0x18004a271  jb      short loc_18004A291
0x18004a273  mov     edx, 0Eh
0x18004a278  mov     [rsp+140h+var_120], ebx
0x18004a27c  mov     r9, [r14+18h]
0x18004a280  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x18004a287  mov     rcx, [rcx+10h]
0x18004a28b  call    WPP_SF_Sd
0x18004a290  nop
0x18004a291  mov     rcx, [rsp+140h+var_F0]; void *
0x18004a296  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a29b  nop
0x18004a29c  mov     rdi, [rsp+140h+var_D8]
0x18004a2a1  test    rdi, rdi
0x18004a2a4  jz      short loc_18004A2BC
0x18004a2a6  mov     r8, [rsp+140h+var_D8+8]
0x18004a2ab  mov     rdx, rdi
0x18004a2ae  call    ?_Destroy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@IEAAXPEAV_bstr_t@@0@Z; std::vector<_bstr_t>::_Destroy(_bstr_t *,_bstr_t *)
0x18004a2b3  mov     rcx, rdi; void *
0x18004a2b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a2bb  nop
0x18004a2bc  mov     rcx, [rsp+140h+var_E8]; void *
0x18004a2c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a2c6  nop
0x18004a2c7  mov     rdi, [rbp+40h+var_C0]
0x18004a2cb  test    rdi, rdi
0x18004a2ce  jz      short loc_18004A2E5
0x18004a2d0  mov     r8, [rbp+40h+var_C0+8]
0x18004a2d4  mov     rdx, rdi
0x18004a2d7  call    ?_Destroy@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@IEAAXPEAV_bstr_t@@0@Z; std::vector<_bstr_t>::_Destroy(_bstr_t *,_bstr_t *)
0x18004a2dc  mov     rcx, rdi; void *
0x18004a2df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a2e4  nop
0x18004a2e5  mov     rcx, [rsp+140h+var_E0]
0x18004a2ea  test    rcx, rcx
0x18004a2ed  jz      short loc_18004A2F5
0x18004a2ef  call    cs:__imp_UbpmCloseTriggerConsumer
0x18004a2f5  mov     eax, ebx
0x18004a2f7  add     rsp, 108h
0x18004a2fe  pop     r15
0x18004a300  pop     r14
0x18004a302  pop     r13
0x18004a304  pop     r12
0x18004a306  pop     rdi
0x18004a307  pop     rsi
0x18004a308  pop     rbx
0x18004a309  pop     rbp
0x18004a30a  retn
```
