# UbpmProxySingleton::LookupTaskByIndex(_GUID const &,JobStore::TaskIndex,JobMoniker &,int,tsched::InternalTaskState *,_bstr_t *,ulong *)

- ea: `0x180022668`
- end: `0x180022b3b`
- name: `?LookupTaskByIndex@UbpmProxySingleton@@AEAAJAEBU_GUID@@W4TaskIndex@JobStore@@AEAVJobMoniker@@HPEAW4InternalTaskState@tsched@@PEAV_bstr_t@@PEAK@Z`
- size: `1235`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180078380`
- `0x180078450`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18000e4c0`
- `0x18001a430`
- `0x180022600`
- `0x180022668`
- `0x180023b60`
- `0x18002ab90`
- `0x18002af2c`
- `0x1800339c0`
- `0x180039e20`
- `0x18003a3c0`
- `0x180040b70`
- `0x180056794`
- `0x180078b4c`
- `0x180078be4`
- `0x18007e67e`
- `0x18007e6d0`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x1800228a7`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x1800228a7`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180022a5d`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180022a5d`
- `UBPM!UbpmApiBufferFree` at `0x180022a45`
- `UBPM!UbpmApiBufferFree` at `0x180022a45`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18002282c`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18002282c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002277e`
- `OLEAUT32!__imp_SysStringLen` at `0x18002277e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UbpmProxySingleton::LookupTaskByIndex(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        _DWORD *a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned int v8; // r14d
  void *v9; // rsi
  HKEY *v10; // r15
  int v11; // edi
  __int64 v12; // r8
  wmi::RefBase *v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rdi
  OLECHAR **v19; // rax
  OLECHAR *v20; // rcx
  OLECHAR *v21; // rcx
  const unsigned __int16 *v22; // rdx
  int BucketFromRegistry; // eax
  OLECHAR *v24; // rdx
  int v25; // eax
  int v26; // edx
  int v27; // r8d
  signed int v28; // edi
  _QWORD *v29; // r10
  int v30; // eax
  __int64 v31; // rsi
  unsigned int i; // r14d
  __int64 v33; // r15
  __int64 v34; // r12
  __int64 v35; // rdx
  __int64 v37; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v38; // [rsp+38h] [rbp-81h]
  void *Buf1; // [rsp+40h] [rbp-79h]
  __int64 v40; // [rsp+48h] [rbp-71h] BYREF
  __int64 v41; // [rsp+50h] [rbp-69h] BYREF
  wmi::RefBase *v42; // [rsp+58h] [rbp-61h] BYREF
  __int64 v43; // [rsp+60h] [rbp-59h]
  _DWORD *v44; // [rsp+68h] [rbp-51h]
  JobStore *v45; // [rsp+70h] [rbp-49h]
  __int64 v46; // [rsp+78h] [rbp-41h]
  __int64 *v47; // [rsp+80h] [rbp-39h]
  GUID iid; // [rsp+88h] [rbp-31h] BYREF
  OLECHAR **v49; // [rsp+98h] [rbp-21h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-19h]
  __int64 v51; // [rsp+A8h] [rbp-11h] BYREF

  v46 = a4;
  v8 = a3;
  v38 = a3;
  v9 = a2;
  Buf1 = a2;
  v43 = a7;
  v44 = a8;
  v10 = (HKEY *)JobStore::m_pCommonStore;
  v45 = JobStore::m_pCommonStore;
  v42 = 0;
  v11 = JobStore::EnumStoredTasks((__int64)JobStore::m_pCommonStore, a3, &v42);
  v13 = v42;
  if ( v11 < 0 )
    goto LABEL_75;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v11 = 1;
        v14 = *((_DWORD *)v13 + 5) + 1;
        if ( v14 < *((_DWORD *)v13 + 4) )
        {
          *((_DWORD *)v13 + 5) = v14;
          v11 = 0;
        }
        if ( v11 == 1 )
          goto LABEL_74;
        JobMoniker::JobMoniker(&iid, 0, 0);
        v15 = 5LL * *((unsigned int *)v13 + 5);
        v16 = *((_QWORD *)v13 + 3);
        v17 = *(_QWORD *)(v16 + 40LL * *((unsigned int *)v13 + 5) + 16);
        if ( v17 )
          _InterlockedIncrement((volatile signed __int32 *)(v17 + 16));
        _bstr_t::~_bstr_t((_bstr_t *)&v49);
        v49 = *(OLECHAR ***)(v16 + 8 * v15 + 16);
        v50 = *(_QWORD *)(v16 + 8 * v15 + 24);
        iid = *(GUID *)(v16 + 8 * v15);
        v18 = *(_QWORD *)(v16 + 8 * v15 + 32);
        if ( v18 )
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
        wmi::AutoRef<JobBucket>::Release(&v51);
        v51 = v18;
        v19 = v49;
        if ( !v49 )
          goto LABEL_17;
        v20 = *v49;
        if ( *v49 )
        {
          LODWORD(v20) = SysStringLen(v20);
          v19 = v49;
        }
        if ( (_DWORD)v20 )
        {
          v21 = v19 ? *v19 : 0LL;
          v22 = v21 + 7;
        }
        else
        {
LABEL_17:
          v22 = 0;
        }
        BucketFromRegistry = JobStore::LoadBucketFromRegistry(v10, v22, 2u, (__int64)&iid, 0, 0);
        v11 = BucketFromRegistry;
        if ( BucketFromRegistry != -2147023728 && (unsigned int)(BucketFromRegistry + 2147024894) > 1 )
          break;
        wmi::AutoRef<JobBucket>::Release(&v51);
        _bstr_t::~_bstr_t((_bstr_t *)&v49);
      }
      if ( BucketFromRegistry < 0 )
        goto LABEL_73;
      if ( (*(_DWORD *)(v51 + 16) & 0x2000000) != 0 )
        break;
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
    }
    v41 = 0;
    v37 = 0;
    v47 = &v37;
    if ( v49 )
      v24 = *v49;
    else
      v24 = 0;
    v25 = UbpmOpenTriggerConsumer(&iid, v24, &v41);
    v28 = v25;
    if ( v25 > 0 )
      v28 = (unsigned __int16)v25 | 0x80070000;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v28 >> 31) & 0xFFFFFFFE) + 4 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
        v50,
        v28);
      v29 = WPP_GLOBAL_Control;
    }
    if ( v28 < 0 )
    {
      v31 = v37;
    }
    else
    {
      v30 = UbpmTriggerConsumerQueryStatus(v41, &v37);
      v11 = v30;
      if ( v30 > 0 )
        v11 = (unsigned __int16)v30 | 0x80070000;
      v31 = v37;
      if ( v11 >= 0 && v37 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *(_DWORD *)(v31 + 28) )
            goto LABEL_56;
          v33 = 56LL * i;
          v34 = *(_QWORD *)(v31 + 32);
          if ( !memcmp_0(Buf1, (const void *)(v33 + v34 + 16), 0x10u) )
            break;
        }
        if ( a5 )
        {
          v40 = 0;
          v11 = User::FromSid((struct User *)&v40, *(void **)(v33 + v34 + 48), SidTypeUnknown);
          if ( v11 < 0 )
          {
            wmi::AutoRef<User::UserEntry>::Release(&v40);
            v31 = v37;
LABEL_54:
            if ( v11 == -2147023728 )
              goto LABEL_56;
            v29 = WPP_GLOBAL_Control;
            goto LABEL_59;
          }
          wmi::AutoRef<User::UserEntry>::operator=(v51 + 64, v40);
          wmi::AutoRef<User::UserEntry>::Release(&v40);
          v31 = v37;
        }
        if ( a6 )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v31 + 32) + v33 + 32) == 1 )
            *a6 = 2;
          else
            *a6 = *(unsigned __int8 *)(*(_QWORD *)(v31 + 32) + v33 + 32) == 3;
        }
        if ( v43 )
        {
          _bstr_t::operator=(v43, *(_QWORD *)(*(_QWORD *)(v31 + 32) + v33 + 8));
          v31 = v37;
        }
        if ( v44 )
          *v44 = *(_DWORD *)(*(_QWORD *)(v31 + 32) + v33 + 36);
        goto LABEL_54;
      }
LABEL_56:
      v29 = WPP_GLOBAL_Control;
    }
    v11 = 1;
LABEL_59:
    if ( v29 != &WPP_GLOBAL_Control
      && (*((_DWORD *)v29 + 7) & 0x100) != 0
      && *((unsigned __int8 *)v29 + 25) >= ((v11 >> 31) & 0xFFFFFFFE) + 4 )
    {
      WPP_SF__guid_SD(v29[2], v26, v27, (_DWORD)Buf1, v50, v11);
      v31 = v37;
    }
    if ( v31 )
    {
      UbpmApiBufferFree(v31);
      v37 = 0;
    }
    if ( v41 )
      UbpmCloseTriggerConsumer();
    if ( v11 < 0 )
      goto LABEL_73;
    if ( !v11 )
      break;
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
    v10 = (HKEY *)v45;
  }
  JobMoniker::operator=(v46, &iid);
LABEL_73:
  JobMoniker::~JobMoniker((JobMoniker *)&iid);
LABEL_74:
  v8 = v38;
  v9 = Buf1;
LABEL_75:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v35 = ((v11 >> 31) & 0xFFFFFFFE) + 4;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v35 )
      WPP_SF__guid_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v12, v9, v8, v11);
  }
  if ( v13 )
    wmi::RefBase::Release(v13);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180022668  mov     [rsp-8+arg_0], rbx
0x18002266d  push    rbp
0x18002266e  push    rsi
0x18002266f  push    rdi
0x180022670  push    r12
0x180022672  push    r13
0x180022674  push    r14
0x180022676  push    r15
0x180022678  lea     rbp, [rsp-7]
0x18002267d  sub     rsp, 0C0h
0x180022684  mov     rax, cs:__security_cookie
0x18002268b  xor     rax, rsp
0x18002268e  mov     [rbp+37h+var_40], rax
0x180022692  mov     [rbp+37h+var_78], r9
0x180022696  mov     r14d, r8d
0x180022699  mov     [rsp+0F0h+var_B8], r8d
0x18002269e  mov     rsi, rdx
0x1800226a1  mov     [rbp+37h+Buf1], rdx
0x1800226a5  mov     r13, [rbp+37h+arg_28]
0x1800226a9  mov     rax, [rbp+37h+arg_30]
0x1800226ad  mov     [rbp+37h+var_90], rax
0x1800226b1  mov     r12, [rbp+37h+arg_38]
0x1800226b5  mov     [rbp+37h+var_88], r12
0x1800226b9  mov     r15, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x1800226c0  mov     [rbp+37h+var_80], r15
0x1800226c4  mov     [rbp+37h+var_98], 0
0x1800226cc  lea     r8, [rbp+37h+var_98]
0x1800226d0  mov     edx, r14d
0x1800226d3  mov     rcx, r15
0x1800226d6  call    ?EnumStoredTasks@JobStore@@QEBAJW4TaskIndex@1@AEAV?$AutoRef@VIndexEnumerator@@@wmi@@@Z; JobStore::EnumStoredTasks(JobStore::TaskIndex,wmi::AutoRef<IndexEnumerator> &)
0x1800226db  mov     edi, eax
0x1800226dd  mov     rbx, [rbp+37h+var_98]
0x1800226e1  test    eax, eax
0x1800226e3  js      loc_180022AC0
0x1800226e9  mov     edi, 1
0x1800226ee  mov     eax, [rbx+14h]
0x1800226f1  inc     eax
0x1800226f3  cmp     eax, [rbx+10h]
0x1800226f6  jnb     short loc_1800226FD
0x1800226f8  mov     [rbx+14h], eax
0x1800226fb  xor     edi, edi
0x1800226fd  cmp     edi, 1
0x180022700  jz      loc_180022AB7
0x180022706  xor     r8d, r8d; unsigned __int16 *
0x180022709  xor     edx, edx; psz
0x18002270b  lea     rcx, [rbp+37h+iid]; lpiid
0x18002270f  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180022714  nop
0x180022715  mov     eax, [rbx+14h]
0x180022718  lea     rdi, [rax+rax*4]
0x18002271c  mov     rsi, [rbx+18h]
0x180022720  mov     rax, [rsi+rdi*8+10h]
0x180022725  test    rax, rax
0x180022728  jz      short loc_18002272E
0x18002272a  lock inc dword ptr [rax+10h]
0x18002272e  lea     rcx, [rbp+37h+var_58]; this
0x180022732  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180022737  mov     rax, [rsi+rdi*8+10h]
0x18002273c  mov     [rbp+37h+var_58], rax
0x180022740  mov     rax, [rsi+rdi*8+18h]
0x180022745  mov     [rbp+37h+var_50], rax
0x180022749  movups  xmm0, xmmword ptr [rsi+rdi*8]
0x18002274d  movdqu  xmmword ptr [rbp+37h+iid.Data1], xmm0
0x180022752  mov     rdi, [rsi+rdi*8+20h]
0x180022757  test    rdi, rdi
0x18002275a  jz      short loc_180022760
0x18002275c  lock inc dword ptr [rdi+8]
0x180022760  lea     rcx, [rbp+37h+var_48]
0x180022764  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180022769  mov     [rbp+37h+var_48], rdi
0x18002276d  mov     rax, [rbp+37h+var_58]
0x180022771  test    rax, rax
0x180022774  jz      short loc_1800227A0
0x180022776  mov     rcx, [rax]; pbstr
0x180022779  test    rcx, rcx
0x18002277c  jz      short loc_18002278A
0x18002277e  call    cs:__imp_SysStringLen
0x180022784  mov     ecx, eax
0x180022786  mov     rax, [rbp+37h+var_58]
0x18002278a  test    ecx, ecx
0x18002278c  jz      short loc_1800227A0
0x18002278e  test    rax, rax
0x180022791  jz      short loc_180022798
0x180022793  mov     rcx, [rax]
0x180022796  jmp     short loc_18002279A
0x180022798  xor     ecx, ecx
0x18002279a  lea     rdx, [rcx+0Eh]
0x18002279e  jmp     short loc_1800227A2
0x1800227a0  xor     edx, edx
0x1800227a2  mov     [rsp+0F0h+var_C8], 0
0x1800227ab  mov     [rsp+0F0h+var_D0], 0
0x1800227b4  lea     r9, [rbp+37h+iid]
0x1800227b8  mov     r8d, 2
0x1800227be  mov     rcx, r15
0x1800227c1  call    ?LoadBucketFromRegistry@JobStore@@QEAAJPEBGW4StreamingFilters@Triggers@@AEAVJobMoniker@@PEAVTrigulator@3@PEAVActionCollection@Actions@@@Z; JobStore::LoadBucketFromRegistry(ushort const *,Triggers::StreamingFilters,JobMoniker &,Triggers::Trigulator *,Actions::ActionCollection *)
0x1800227c6  mov     edi, eax
0x1800227c8  cmp     eax, 80070490h
0x1800227cd  jz      loc_180022A89
0x1800227d3  add     eax, 7FF8FFFEh
0x1800227d8  cmp     eax, 1
0x1800227db  jbe     loc_180022A89
0x1800227e1  test    edi, edi
0x1800227e3  js      loc_180022AAE
0x1800227e9  mov     rax, [rbp+37h+var_48]
0x1800227ed  test    dword ptr [rax+10h], 2000000h
0x1800227f4  jz      loc_180022A7B
0x1800227fa  mov     [rbp+37h+var_A0], 0
0x180022802  mov     [rsp+0F0h+var_C0], 0
0x18002280b  lea     rax, [rsp+0F0h+var_C0]
0x180022810  mov     [rbp+37h+var_70], rax
0x180022814  mov     rax, [rbp+37h+var_58]
0x180022818  test    rax, rax
0x18002281b  jz      short loc_180022822
0x18002281d  mov     rdx, [rax]
0x180022820  jmp     short loc_180022824
0x180022822  xor     edx, edx
0x180022824  lea     r8, [rbp+37h+var_A0]
0x180022828  lea     rcx, [rbp+37h+iid]
0x18002282c  call    cs:__imp_UbpmOpenTriggerConsumer
0x180022832  mov     edi, eax
0x180022834  test    eax, eax
0x180022836  jle     short loc_180022841
0x180022838  movzx   edi, ax
0x18002283b  or      edi, 80070000h
0x180022841  mov     r10, cs:WPP_GLOBAL_Control
0x180022848  lea     rax, WPP_GLOBAL_Control
0x18002284f  cmp     r10, rax
0x180022852  jz      short loc_180022896
0x180022854  test    dword ptr [r10+1Ch], 100h
0x18002285c  jz      short loc_180022896
0x18002285e  mov     ecx, edi
0x180022860  sar     ecx, 1Fh
0x180022863  and     ecx, 0FFFFFFFEh
0x180022866  add     ecx, 4
0x180022869  movzx   eax, byte ptr [r10+19h]
0x18002286e  cmp     eax, ecx
0x180022870  jb      short loc_180022896
0x180022872  mov     edx, 0Ah
0x180022877  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18002287b  mov     r9, [rbp+37h+var_50]
0x18002287f  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x180022886  mov     rcx, [r10+10h]
0x18002288a  call    WPP_SF_Sd
0x18002288f  mov     r10, cs:WPP_GLOBAL_Control
0x180022896  test    edi, edi
0x180022898  js      loc_1800229EA
0x18002289e  lea     rdx, [rsp+0F0h+var_C0]
0x1800228a3  mov     rcx, [rbp+37h+var_A0]
0x1800228a7  call    cs:__imp_UbpmTriggerConsumerQueryStatus
0x1800228ad  mov     edi, eax
0x1800228af  test    eax, eax
0x1800228b1  jle     short loc_1800228BC
0x1800228b3  movzx   edi, ax
0x1800228b6  or      edi, 80070000h
0x1800228bc  mov     rsi, [rsp+0F0h+var_C0]
0x1800228c1  test    edi, edi
0x1800228c3  js      loc_1800229E1
0x1800228c9  test    rsi, rsi
0x1800228cc  jz      loc_1800229E1
0x1800228d2  xor     r14d, r14d
0x1800228d5  cmp     r14d, [rsi+1Ch]
0x1800228d9  jnb     loc_1800229E1
0x1800228df  mov     eax, r14d
0x1800228e2  imul    r15, rax, 38h ; '8'
0x1800228e6  mov     r12, [rsi+20h]
0x1800228ea  lea     rdx, [r12+10h]
0x1800228ef  add     rdx, r15; Buf2
0x1800228f2  mov     r8d, 10h; Size
0x1800228f8  mov     rcx, [rbp+37h+Buf1]; Buf1
0x1800228fc  call    memcmp_0
0x180022901  test    eax, eax
0x180022903  jz      short loc_18002290A
0x180022905  inc     r14d
0x180022908  jmp     short loc_1800228D5
0x18002290a  cmp     [rbp+37h+arg_20], 0
0x18002290e  jz      short loc_180022965
0x180022910  mov     [rbp+37h+var_A8], 0
0x180022918  mov     r8d, 8; enum _SID_NAME_USE
0x18002291e  mov     rdx, [r15+r12+30h]; void *
0x180022923  lea     rcx, [rbp+37h+var_A8]; this
0x180022927  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x18002292c  mov     edi, eax
0x18002292e  test    eax, eax
0x180022930  jns     short loc_180022945
0x180022932  lea     rcx, [rbp+37h+var_A8]
0x180022936  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002293b  mov     rsi, [rsp+0F0h+var_C0]
0x180022940  jmp     loc_1800229D0
0x180022945  mov     rcx, [rbp+37h+var_48]
0x180022949  add     rcx, 40h ; '@'
0x18002294d  mov     rdx, [rbp+37h+var_A8]
0x180022951  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180022956  nop
0x180022957  lea     rcx, [rbp+37h+var_A8]
0x18002295b  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180022960  mov     rsi, [rsp+0F0h+var_C0]
0x180022965  test    r13, r13
0x180022968  jz      short loc_18002299B
0x18002296a  mov     rax, [rsi+20h]
0x18002296e  movzx   ecx, byte ptr [rax+r15+20h]
0x180022974  sub     ecx, 1
0x180022977  jz      short loc_180022993
0x180022979  sub     ecx, 1
0x18002297c  jz      short loc_180022989
0x18002297e  cmp     ecx, 1
0x180022981  jnz     short loc_180022989
0x180022983  mov     [r13+0], ecx
0x180022987  jmp     short loc_18002299B
0x180022989  mov     dword ptr [r13+0], 0
0x180022991  jmp     short loc_18002299B
0x180022993  mov     dword ptr [r13+0], 2
0x18002299b  mov     rax, [rbp+37h+var_90]
0x18002299f  test    rax, rax
0x1800229a2  jz      short loc_1800229BA
0x1800229a4  mov     rdx, [rsi+20h]
0x1800229a8  mov     rdx, [rdx+r15+8]
0x1800229ad  mov     rcx, rax
0x1800229b0  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x1800229b5  mov     rsi, [rsp+0F0h+var_C0]
0x1800229ba  mov     r12, [rbp+37h+var_88]
0x1800229be  test    r12, r12
0x1800229c1  jz      short loc_1800229D0
0x1800229c3  mov     rax, [rsi+20h]
0x1800229c7  mov     ecx, [rax+r15+24h]
0x1800229cc  mov     [r12], ecx
0x1800229d0  cmp     edi, 80070490h
0x1800229d6  jz      short loc_1800229E1
0x1800229d8  mov     r10, cs:WPP_GLOBAL_Control
0x1800229df  jmp     short loc_1800229F4
0x1800229e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800229e8  jmp     short loc_1800229EF
0x1800229ea  mov     rsi, [rsp+0F0h+var_C0]
0x1800229ef  mov     edi, 1
0x1800229f4  lea     rax, WPP_GLOBAL_Control
0x1800229fb  cmp     r10, rax
0x1800229fe  jz      short loc_180022A3D
0x180022a00  test    dword ptr [r10+1Ch], 100h
0x180022a08  jz      short loc_180022A3D
0x180022a0a  mov     ecx, edi
0x180022a0c  sar     ecx, 1Fh
0x180022a0f  and     ecx, 0FFFFFFFEh
0x180022a12  add     ecx, 4
0x180022a15  movzx   eax, byte ptr [r10+19h]
0x180022a1a  cmp     eax, ecx
0x180022a1c  jb      short loc_180022A3D
0x180022a1e  mov     dword ptr [rsp+0F0h+var_C8], edi
0x180022a22  mov     rax, [rbp+37h+var_50]
0x180022a26  mov     [rsp+0F0h+var_D0], rax
0x180022a2b  mov     r9, [rbp+37h+Buf1]
0x180022a2f  mov     rcx, [r10+10h]
0x180022a33  call    WPP_SF__guid_SD
0x180022a38  mov     rsi, [rsp+0F0h+var_C0]
0x180022a3d  test    rsi, rsi
0x180022a40  jz      short loc_180022A54
0x180022a42  mov     rcx, rsi
0x180022a45  call    cs:__imp_UbpmApiBufferFree
0x180022a4b  mov     [rsp+0F0h+var_C0], 0
0x180022a54  mov     rcx, [rbp+37h+var_A0]
0x180022a58  test    rcx, rcx
0x180022a5b  jz      short loc_180022A63
0x180022a5d  call    cs:__imp_UbpmCloseTriggerConsumer
0x180022a63  test    edi, edi
0x180022a65  js      short loc_180022AAE
0x180022a67  jz      short loc_180022AA0
0x180022a69  lea     rcx, [rbp+37h+iid]; this
0x180022a6d  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022a72  mov     r15, [rbp+37h+var_80]
0x180022a76  jmp     loc_1800226E9
0x180022a7b  lea     rcx, [rbp+37h+iid]; this
0x180022a7f  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022a84  jmp     loc_1800226E9
0x180022a89  lea     rcx, [rbp+37h+var_48]
0x180022a8d  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180022a92  lea     rcx, [rbp+37h+var_58]; this
0x180022a96  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180022a9b  jmp     loc_1800226E9
0x180022aa0  lea     rdx, [rbp+37h+iid]
0x180022aa4  mov     rcx, [rbp+37h+var_78]
0x180022aa8  call    ??4JobMoniker@@QEAAAEAV0@AEBV0@@Z; JobMoniker::operator=(JobMoniker const &)
0x180022aad  nop
0x180022aae  lea     rcx, [rbp+37h+iid]; this
0x180022ab2  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022ab7  mov     r14d, [rsp+0F0h+var_B8]
0x180022abc  mov     rsi, [rbp+37h+Buf1]
0x180022ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac7  lea     rax, WPP_GLOBAL_Control
0x180022ace  cmp     rcx, rax
0x180022ad1  jz      short loc_180022B05
0x180022ad3  test    dword ptr [rcx+1Ch], 100h
0x180022ada  jz      short loc_180022B05
0x180022adc  mov     edx, edi
0x180022ade  sar     edx, 1Fh
0x180022ae1  and     edx, 0FFFFFFFEh
0x180022ae4  add     edx, 4
0x180022ae7  movzx   eax, byte ptr [rcx+19h]
0x180022aeb  cmp     eax, edx
0x180022aed  jb      short loc_180022B05
0x180022aef  mov     dword ptr [rsp+0F0h+var_C8], edi
0x180022af3  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x180022af8  mov     r9, rsi
  ... truncated ...
```
