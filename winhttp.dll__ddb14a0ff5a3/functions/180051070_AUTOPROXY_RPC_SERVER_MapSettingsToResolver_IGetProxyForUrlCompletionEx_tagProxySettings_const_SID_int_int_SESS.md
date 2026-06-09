# AUTOPROXY_RPC_SERVER::MapSettingsToResolver(IGetProxyForUrlCompletionEx *,tagProxySettings const *,_SID *,int,int,_SESSION_OPTIONS const *,IProxyResolver * *)

- ea: `0x180051070`
- end: `0x18005191d`
- name: `?MapSettingsToResolver@AUTOPROXY_RPC_SERVER@@AEAAJPEAUIGetProxyForUrlCompletionEx@@PEBUtagProxySettings@@PEAU_SID@@HHPEBU_SESSION_OPTIONS@@PEAPEAUIProxyResolver@@@Z`
- size: `2221`
- prototype: `__int64 __fastcall(AUTOPROXY_RPC_SERVER *__hidden this, struct IGetProxyForUrlCompletionEx *, const struct tagProxySettings *, struct _SID *, int, int, const struct _SESSION_OPTIONS *, struct IProxyResolver **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180050d90`
- `0x1800ac620`

## callees

- `0x180051070`
- `0x180051924`
- `0x1800519e0`
- `0x1800526c0`
- `0x180052794`
- `0x180052904`
- `0x180052b88`
- `0x18009920c`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800cf58c`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dd064`
- `0x1800dd924`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051602`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800516c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051602`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800516c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005137e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005137e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051595`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051595`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800511bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800514cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800511bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800514cc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051697`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051697`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051685`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051685`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005113a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051426`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005113a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051770`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800512a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800512a2`

## pseudocode

```c
__int64 __fastcall AUTOPROXY_RPC_SERVER::MapSettingsToResolver(
        AUTOPROXY_RPC_SERVER *this,
        struct IGetProxyForUrlCompletionEx *a2,
        const struct tagProxySettings *a3,
        struct _SID *a4,
        int a5,
        int a6,
        const struct _SESSION_OPTIONS *a7,
        struct IProxyResolver **a8)
{
  struct _SESSION_OPTIONS *v9; // rcx
  _OWORD *v11; // rbx
  volatile signed __int32 *v12; // rsi
  struct ProxyResolverNodeInUse *v13; // rdi
  _OWORD *v14; // rax
  int v15; // r13d
  struct IGetProxyForUrlCompletionEx *v16; // rcx
  RTL_SRWLOCK *v18; // r14
  RTL_SRWLOCK *v19; // rax
  int v20; // r15d
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rdi
  _QWORD *v24; // r14
  int v25; // eax
  char v26; // al
  struct ProxyResolverNodeInUse *v27; // rax
  SettingsResolverNode *v28; // rcx
  __int64 v29; // rax
  struct IProxyResolver *v30; // r14
  const unsigned __int16 *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  SettingsResolverNode *v34; // r14
  struct ProxyResolverNodeInUse *v35; // r15
  int v36; // eax
  SettingsResolverNode *v37; // r12
  __int64 v38; // r8
  int v39; // eax
  int v40; // eax
  signed int LastError; // eax
  struct _SID *v42; // [rsp+20h] [rbp-E8h]
  SettingsResolverNode *v43; // [rsp+60h] [rbp-A8h] BYREF
  int v44; // [rsp+68h] [rbp-A0h]
  int v45; // [rsp+6Ch] [rbp-9Ch]
  struct ProxyResolverNodeInUse *v46; // [rsp+70h] [rbp-98h] BYREF
  PSID pSourceSid; // [rsp+78h] [rbp-90h]
  SettingsResolverNode *v48; // [rsp+80h] [rbp-88h] BYREF
  struct _SESSION_OPTIONS *v49; // [rsp+88h] [rbp-80h]
  struct tagProxySettings *v50; // [rsp+90h] [rbp-78h]
  AUTOPROXY_RPC_SERVER *v51; // [rsp+98h] [rbp-70h]
  struct IProxyResolver **v52; // [rsp+A0h] [rbp-68h]
  struct IGetProxyForUrlCompletionEx *v53; // [rsp+A8h] [rbp-60h]
  PSRWLOCK SRWLock; // [rsp+B0h] [rbp-58h]
  PSRWLOCK v55; // [rsp+B8h] [rbp-50h] BYREF

  v51 = this;
  v9 = a7;
  v49 = a7;
  pSourceSid = a4;
  v11 = 0;
  v50 = a3;
  v12 = 0;
  v53 = a2;
  v13 = 0;
  v52 = a8;
  HIDWORD(v43) = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_qqqDD(a5, (_DWORD)a2, (_DWORD)a3, (_DWORD)this, (__int64)a2, (__int64)a4);
    v9 = v49;
  }
  v45 = 0;
  SRWLock = (PSRWLOCK)((char *)this + 32);
  if ( !a8 )
  {
    v15 = -2147024809;
    HIDWORD(v43) = 1575;
    goto LABEL_11;
  }
  *a8 = 0;
  if ( !a3 )
  {
    v15 = -2147024809;
    HIDWORD(v43) = 1578;
    goto LABEL_11;
  }
  v44 = *((_DWORD *)v9 + 5);
  HIDWORD(v55) = 0;
  v14 = HeapAlloc(g_hWxProcessHeap, 0, 0x88u);
  v11 = v14;
  if ( !v14 )
  {
    v11 = 0;
    HIDWORD(v55) = 546;
    v15 = -2147024882;
LABEL_7:
    HIDWORD(v43) = 1586;
    goto LABEL_11;
  }
  v55 = 0;
  *v14 = 0;
  v14[1] = 0;
  v18 = 0;
  v14[2] = 0;
  v14[3] = 0;
  v14[4] = 0;
  v14[5] = 0;
  v14[6] = 0;
  v14[7] = 0;
  *((_QWORD *)v14 + 16) = 0;
  *(_DWORD *)v14 = 1;
  *((_QWORD *)v14 + 13) = v14 + 2;
  *((_DWORD *)v14 + 32) = 0;
  v14[2] = 0;
  v14[3] = 0;
  v14[4] = 0;
  v14[5] = 0;
  *((_DWORD *)v14 + 24) = 0;
  HIDWORD(v43) = 0;
  HIDWORD(v46) = 0;
  v19 = (RTL_SRWLOCK *)CoTaskMemAlloc(0x70u);
  v15 = -2147024882;
  if ( !v19 )
  {
    HIDWORD(v46) = 76;
    v20 = -2147024882;
    HIDWORD(v43) = 501;
    goto LABEL_31;
  }
  v55 = v19;
  *(_OWORD *)&v19->Ptr = 0;
  v18 = v19;
  *(_OWORD *)&v19[2].Ptr = 0;
  *(_OWORD *)&v19[4].Ptr = 0;
  *(_OWORD *)&v19[6].Ptr = 0;
  *(_OWORD *)&v19[8].Ptr = 0;
  *(_OWORD *)&v19[10].Ptr = 0;
  *(_OWORD *)&v19[12].Ptr = 0;
  v20 = CopyProxySettings<WxCoTaskAllocator>((__int128 *)a3, v19);
  if ( v20 < 0 )
  {
    HIDWORD(v43) = 504;
    goto LABEL_31;
  }
  if ( pSourceSid )
  {
    if ( CopySid(0x44u, *((PSID *)v11 + 13), pSourceSid) )
    {
      *((_DWORD *)v11 + 28) = GetLengthSid(*((PSID *)v11 + 13));
      v20 = 0;
      goto LABEL_27;
    }
    LastError = GetLastError();
    v20 = LastError;
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(v43) = 510;
    if ( v20 >= 0 )
      v20 = -2147418113;
LABEL_31:
    if ( v18 )
      ProxySettingsAllocator::Free((void ***)&v55);
    goto LABEL_33;
  }
LABEL_27:
  v21 = *((_QWORD *)v11 + 3);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  *((_QWORD *)v11 + 3) = 0;
  *((_DWORD *)v11 + 30) = a5;
  *((_DWORD *)v11 + 29) = a6;
  *((_DWORD *)v11 + 31) = v44;
  *((_QWORD *)v11 + 2) = v18;
LABEL_33:
  if ( v20 < 0 )
  {
    HIDWORD(v55) = 553;
    SettingsResolverNode::Release((SettingsResolverNode *)v11);
    v11 = 0;
    v15 = v20;
    goto LABEL_7;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 17, WPP_162471f81aa1348c530653e1923df6cd_Traceguids);
  AcquireSRWLockShared((PSRWLOCK)this + 4);
  v45 = 1;
  if ( !*((_DWORD *)this + 21) )
  {
    v15 = -2146685199;
    HIDWORD(v43) = 1595;
    goto LABEL_11;
  }
  v22 = (__int64 *)*((_QWORD *)this + 3);
  v55 = (PSRWLOCK)v11;
  v23 = *v22;
  if ( !*(_DWORD *)(*v22 + 44) )
  {
LABEL_60:
    v12 = 0;
    goto LABEL_61;
  }
  v24 = *(_QWORD **)(v23 + 16);
  while ( 1 )
  {
    v25 = (*(__int64 (__fastcall **)(__int64, PSRWLOCK *, _QWORD *))(v23 + 72))(v23, &v55, v24 + 4);
    if ( v25 )
      break;
    v24 = (_QWORD *)v24[1];
LABEL_82:
    if ( !v24 )
      goto LABEL_60;
  }
  if ( v25 == 1 )
  {
    v24 = (_QWORD *)v24[2];
    goto LABEL_82;
  }
  if ( v24 == (_QWORD *)-32LL )
    goto LABEL_60;
  v12 = (volatile signed __int32 *)v24[4];
  _InterlockedIncrement(v12);
  if ( v12 )
  {
    v26 = xmmword_180107A60;
    if ( (xmmword_180107A60 & 4) != 0 )
    {
      WPP_SF_(1026, 68, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
      v26 = xmmword_180107A60;
    }
    HIDWORD(pSourceSid) = 0;
    if ( (v26 & 0x20) != 0 )
      WPP_SF_q(1029, 12, WPP_162471f81aa1348c530653e1923df6cd_Traceguids);
    v27 = (struct ProxyResolverNodeInUse *)HeapAlloc(g_hWxProcessHeap, 0, 0x18u);
    v13 = v27;
    if ( v27 )
    {
      *((_DWORD *)v27 + 3) = 0;
      *(_QWORD *)v27 = &ProxyResolverNodeInUse::`vftable';
      *((_DWORD *)v27 + 2) = 1;
      *((_QWORD *)v27 + 2) = 0;
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_q(1029, 10, WPP_162471f81aa1348c530653e1923df6cd_Traceguids);
      v15 = 0;
      _InterlockedIncrement(v12);
      v28 = (SettingsResolverNode *)*((_QWORD *)v13 + 2);
      if ( v28 )
        SettingsResolverNode::Release(v28);
      *((_QWORD *)v13 + 2) = v12;
      if ( (xmmword_180107A60 & 0x20) != 0 )
      {
        LODWORD(v42) = *((_DWORD *)v12 + 32);
        WPP_SF_qD(1029, 15, WPP_162471f81aa1348c530653e1923df6cd_Traceguids, v12);
      }
      _InterlockedIncrement(v12 + 32);
    }
    else
    {
      HIDWORD(pSourceSid) = 254;
      v13 = 0;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 13, WPP_162471f81aa1348c530653e1923df6cd_Traceguids, (unsigned int)v15, v42);
    if ( v15 >= 0 )
      goto LABEL_58;
    HIDWORD(v43) = 1607;
    goto LABEL_11;
  }
LABEL_61:
  ReleaseSRWLockShared((PSRWLOCK)this + 4);
  v34 = 0;
  v35 = 0;
  v45 = 0;
  v46 = 0;
  v43 = 0;
  v48 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qDD(1029, 65, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, this);
  v55 = (PSRWLOCK)((char *)this + 32);
  v13 = 0;
  v44 = 0;
  v36 = CreateResolverNodeForSettings(
          v31,
          v50,
          v32,
          v33,
          (struct _SID *)pSourceSid,
          a5,
          a6,
          v49,
          *((struct CWxGlobalCountersRefCounted **)this + 37),
          *((_QWORD *)this + 13),
          &v43);
  v37 = v43;
  v15 = v36;
  v38 = (unsigned int)v36;
  if ( v36 < 0 )
  {
    HIDWORD(v43) = 1514;
    v39 = 0;
  }
  else
  {
    AcquireSRWLockExclusive(v55);
    v39 = 1;
    v44 = 1;
    if ( *((_DWORD *)v51 + 21) )
    {
      v40 = CWxRefMap<SettingsResolverMap,SettingsResolverNode>::Insert(*((_QWORD *)v51 + 3), v37, &v48);
      v34 = v48;
      v15 = v40;
      v38 = (unsigned int)v40;
      if ( v40 < 0 )
      {
        v39 = v44;
        HIDWORD(v43) = 1532;
      }
      else
      {
        v15 = ProxyResolverNodeInUse::CreateInstance(v48, &v46);
        v38 = (unsigned int)v15;
        if ( v15 >= 0 )
        {
          ReleaseSRWLockExclusive(v55);
          v13 = v46;
          v39 = 0;
          v44 = 0;
          goto LABEL_68;
        }
        v35 = v46;
        v39 = v44;
        HIDWORD(v43) = 1535;
      }
    }
    else
    {
      v15 = -2146685199;
      HIDWORD(v43) = 1523;
LABEL_68:
      v38 = (unsigned int)v15;
    }
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_d(1029, 66, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v38, v42);
    v39 = v44;
  }
  if ( v39 )
    ReleaseSRWLockExclusive(v55);
  if ( v35 )
    (*(void (__fastcall **)(struct ProxyResolverNodeInUse *, struct IGetProxyForUrlCompletionEx *, __int64))(*(_QWORD *)v35 + 16LL))(
      v35,
      a2,
      v38);
  if ( v34 )
    SettingsResolverNode::Release(v34);
  if ( v37 )
    SettingsResolverNode::Release(v37);
  if ( v15 >= 0 )
  {
LABEL_58:
    v29 = *((_QWORD *)v13 + 2);
    v30 = *(struct IProxyResolver **)(v29 + 24);
    if ( v30 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 8LL))(*(_QWORD *)(v29 + 24));
    v16 = v53;
    *v52 = v30;
    if ( v16 )
      (*(void (__fastcall **)(struct IGetProxyForUrlCompletionEx *, struct ProxyResolverNodeInUse *))(*(_QWORD *)v16 + 32LL))(
        v16,
        v13);
  }
  else
  {
    HIDWORD(v43) = 1619;
  }
LABEL_11:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 69, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v15, v42);
  if ( v45 )
    ReleaseSRWLockShared(SRWLock);
  if ( v13 )
    (*(void (__fastcall **)(struct ProxyResolverNodeInUse *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 && _InterlockedExchangeAdd(v12, 0xFFFFFFFF) == 1 )
    SettingsResolverNode::`scalar deleting destructor'((SettingsResolverNode *)v12, (unsigned int)a2);
  if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
    SettingsResolverNode::`scalar deleting destructor'((SettingsResolverNode *)v11, (unsigned int)a2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180051070  push    rbx
0x180051072  push    rsi
0x180051073  push    rdi
0x180051074  push    r12
0x180051076  push    r13
0x180051078  push    r14
0x18005107a  push    r15
0x18005107c  sub     rsp, 0D0h
0x180051083  mov     rax, cs:__security_cookie
0x18005108a  xor     rax, rsp
0x18005108d  mov     [rsp+108h+var_48], rax
0x180051095  mov     r14, [rsp+108h+arg_38]
0x18005109d  xor     r13d, r13d
0x1800510a0  mov     r12, rcx
0x1800510a3  mov     [rsp+108h+var_70], rcx
0x1800510ab  mov     rcx, [rsp+108h+arg_30]
0x1800510b3  mov     rax, r9
0x1800510b6  mov     [rsp+108h+var_80], rcx
0x1800510be  mov     r15, r8
0x1800510c1  mov     [rsp+108h+pSourceSid], rax
0x1800510c6  mov     ebx, r13d
0x1800510c9  mov     [rsp+108h+var_78], r8
0x1800510d1  mov     esi, r13d
0x1800510d4  mov     [rsp+108h+var_60], rdx
0x1800510dc  mov     edi, r13d
0x1800510df  mov     [rsp+108h+var_68], r14
0x1800510e7  mov     dword ptr [rsp+108h+var_A8+4], r13d
0x1800510ec  test    byte ptr cs:xmmword_180107A60, 20h
0x1800510f3  jnz     loc_1800516FF
0x1800510f9  mov     [rsp+108h+var_9C], r13d
0x1800510fe  lea     rax, [r12+20h]
0x180051103  mov     [rsp+108h+SRWLock], rax
0x18005110b  test    r14, r14
0x18005110e  jz      short loc_18005116A
0x180051110  mov     [r14], r13
0x180051113  test    r15, r15
0x180051116  jz      loc_1800517A1
0x18005111c  mov     eax, [rcx+14h]
0x18005111f  xor     edx, edx; dwFlags
0x180051121  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180051128  mov     r8d, 88h; dwBytes
0x18005112e  mov     [rsp+108h+var_A0], eax
0x180051132  mov     dword ptr [rsp+108h+var_50+4], r13d
0x18005113a  call    cs:__imp_HeapAlloc
0x180051140  mov     rbx, rax
0x180051143  test    rax, rax
0x180051146  jnz     loc_180051234
0x18005114c  mov     rbx, r13
0x18005114f  mov     dword ptr [rsp+108h+var_50+4], 222h
0x18005115a  mov     r13d, 8007000Eh
0x180051160  mov     dword ptr [rsp+108h+var_A8+4], 632h
0x180051168  jmp     short loc_1800511A1
0x18005116a  mov     r13d, 80070057h
0x180051170  mov     dword ptr [rsp+108h+var_A8+4], 627h
0x180051178  jmp     short loc_1800511A1
0x18005117a  mov     rax, [rsp+108h+var_68]
0x180051182  mov     rcx, [rsp+108h+var_60]
0x18005118a  mov     [rax], r14
0x18005118d  test    rcx, rcx
0x180051190  jz      short loc_1800511A1
0x180051192  mov     rax, [rcx]
0x180051195  mov     rdx, rdi
0x180051198  mov     rax, [rax+20h]
0x18005119c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511a1  test    byte ptr cs:xmmword_180107A60, 20h
0x1800511a8  jnz     loc_1800518FF
0x1800511ae  cmp     [rsp+108h+var_9C], 0
0x1800511b3  jz      short loc_1800511C3
0x1800511b5  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x1800511bd  call    cs:__imp_ReleaseSRWLockShared
0x1800511c3  test    rdi, rdi
0x1800511c6  jz      short loc_1800511D7
0x1800511c8  mov     rax, [rdi]
0x1800511cb  mov     rcx, rdi
0x1800511ce  mov     rax, [rax+10h]
0x1800511d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511d7  mov     edi, 0FFFFFFFFh
0x1800511dc  test    rsi, rsi
0x1800511df  jz      short loc_1800511EC
0x1800511e1  mov     eax, edi
0x1800511e3  lock xadd [rsi], eax
0x1800511e7  cmp     eax, 1
0x1800511ea  jz      short loc_180051220
0x1800511ec  test    rbx, rbx
0x1800511ef  jz      short loc_1800511FA
0x1800511f1  lock xadd [rbx], edi
0x1800511f5  cmp     edi, 1
0x1800511f8  jz      short loc_18005122A
0x1800511fa  mov     eax, r13d
0x1800511fd  mov     rcx, [rsp+108h+var_48]
0x180051205  xor     rcx, rsp; StackCookie
0x180051208  call    __security_check_cookie
0x18005120d  add     rsp, 0D0h
0x180051214  pop     r15
0x180051216  pop     r14
0x180051218  pop     r13
0x18005121a  pop     r12
0x18005121c  pop     rdi
0x18005121d  pop     rsi
0x18005121e  pop     rbx
0x18005121f  retn
0x180051220  mov     rcx, rsi; this
0x180051223  call    ??_GSettingsResolverNode@@AEAAPEAXI@Z; SettingsResolverNode::`scalar deleting destructor'(uint)
0x180051228  jmp     short loc_1800511EC
0x18005122a  mov     rcx, rbx; this
0x18005122d  call    ??_GSettingsResolverNode@@AEAAPEAXI@Z; SettingsResolverNode::`scalar deleting destructor'(uint)
0x180051232  jmp     short loc_1800511FA
0x180051234  xorps   xmm0, xmm0
0x180051237  mov     [rsp+0B8h], r13
0x18005123f  movups  xmmword ptr [rbx], xmm0
0x180051242  xor     eax, eax
0x180051244  xor     ecx, ecx
0x180051246  movups  xmmword ptr [rbx+10h], xmm0
0x18005124a  mov     r14, r13
0x18005124d  movups  xmmword ptr [rbx+20h], xmm0
0x180051251  movups  xmmword ptr [rbx+30h], xmm0
0x180051255  movups  xmmword ptr [rbx+40h], xmm0
0x180051259  movups  xmmword ptr [rbx+50h], xmm0
0x18005125d  movups  xmmword ptr [rbx+60h], xmm0
0x180051261  movups  xmmword ptr [rbx+70h], xmm0
0x180051265  mov     [rbx+80h], rax
0x18005126c  lea     rax, [rbx+20h]
0x180051270  mov     dword ptr [rbx], 1
0x180051276  mov     [rbx+68h], rax
0x18005127a  mov     [rbx+80h], r13d
0x180051281  movups  xmmword ptr [rax], xmm0
0x180051284  movups  xmmword ptr [rax+10h], xmm0
0x180051288  movups  xmmword ptr [rax+20h], xmm0
0x18005128c  movups  xmmword ptr [rax+30h], xmm0
0x180051290  mov     [rax+40h], ecx
0x180051293  mov     ecx, 70h ; 'p'; cb
0x180051298  mov     dword ptr [rsp+108h+var_A8+4], r13d
0x18005129d  mov     dword ptr [rsp+108h+var_98+4], r13d
0x1800512a2  call    cs:__imp_CoTaskMemAlloc
0x1800512a8  mov     r13d, 8007000Eh
0x1800512ae  test    rax, rax
0x1800512b1  jz      loc_18005133E
0x1800512b7  xorps   xmm0, xmm0
0x1800512ba  mov     [rsp+0B8h], rax
0x1800512c2  movups  xmmword ptr [rax], xmm0
0x1800512c5  mov     r14, rax
0x1800512c8  movups  xmmword ptr [rax+10h], xmm0
0x1800512cc  movups  xmmword ptr [rax+20h], xmm0
0x1800512d0  movups  xmmword ptr [rax+30h], xmm0
0x1800512d4  movups  xmmword ptr [rax+40h], xmm0
0x1800512d8  movups  xmmword ptr [rax+50h], xmm0
0x1800512dc  movups  xmmword ptr [rax+60h], xmm0
0x1800512e0  mov     rdx, rax
0x1800512e3  mov     rcx, r15
0x1800512e6  call    ??$CopyProxySettings@VWxCoTaskAllocator@@@@YAJPEBUtagProxySettings@@PEAU0@@Z; CopyProxySettings<WxCoTaskAllocator>(tagProxySettings const *,tagProxySettings *)
0x1800512eb  mov     r15d, eax
0x1800512ee  test    eax, eax
0x1800512f0  js      loc_1800517B4
0x1800512f6  mov     rax, [rsp+108h+pSourceSid]
0x1800512fb  test    rax, rax
0x1800512fe  jnz     loc_180051679
0x180051304  mov     rcx, [rbx+18h]
0x180051308  test    rcx, rcx
0x18005130b  jz      short loc_180051319
0x18005130d  mov     rax, [rcx]
0x180051310  mov     rax, [rax+10h]
0x180051314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051319  mov     eax, [rsp+108h+arg_20]
0x180051320  mov     [rbx+18h], rsi
0x180051324  mov     [rbx+78h], eax
0x180051327  mov     eax, [rsp+108h+arg_28]
0x18005132e  mov     [rbx+74h], eax
0x180051331  mov     eax, [rsp+108h+var_A0]
0x180051335  mov     [rbx+7Ch], eax
0x180051338  mov     [rbx+10h], r14
0x18005133c  jmp     short loc_180051363
0x18005133e  mov     dword ptr [rsp+108h+var_98+4], 4Ch ; 'L'
0x180051346  mov     r15d, r13d
0x180051349  mov     dword ptr [rsp+108h+var_A8+4], 1F5h
0x180051351  test    r14, r14
0x180051354  jz      short loc_180051363
0x180051356  lea     rcx, [rsp+108h+var_50]; void **
0x18005135e  call    ?Free@ProxySettingsAllocator@@SAXPEAPEAX@Z; ProxySettingsAllocator::Free(void * *)
0x180051363  test    r15d, r15d
0x180051366  js      loc_1800517C1
0x18005136c  test    byte ptr cs:xmmword_180107A60, 20h
0x180051373  jnz     loc_180051734
0x180051379  lea     rcx, [r12+20h]; SRWLock
0x18005137e  call    cs:__imp_AcquireSRWLockShared
0x180051384  mov     [rsp+108h+var_9C], 1
0x18005138c  cmp     [r12+54h], esi
0x180051391  jz      loc_1800517DE
0x180051397  mov     rax, [r12+18h]
0x18005139c  mov     [rsp+108h+var_50], rbx
0x1800513a4  mov     rdi, [rax]
0x1800513a7  cmp     [rdi+2Ch], esi
0x1800513aa  jz      loc_1800514C5
0x1800513b0  mov     r14, [rdi+10h]
0x1800513b4  mov     rax, [rdi+48h]
0x1800513b8  lea     rsi, [r14+20h]
0x1800513bc  mov     r8, rsi
0x1800513bf  lea     rdx, [rsp+108h+var_50]
0x1800513c7  mov     rcx, rdi
0x1800513ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513cf  test    eax, eax
0x1800513d1  jz      loc_180051667
0x1800513d7  cmp     eax, 1
0x1800513da  jz      loc_1800516B2
0x1800513e0  test    rsi, rsi
0x1800513e3  jz      loc_1800514C5
0x1800513e9  mov     rsi, [rsi]
0x1800513ec  lock inc dword ptr [rsi]
0x1800513ef  test    rsi, rsi
0x1800513f2  jz      loc_1800514C7
0x1800513f8  movzx   eax, byte ptr cs:xmmword_180107A60
0x1800513ff  test    al, 4
0x180051401  jnz     loc_1800517F1
0x180051407  xor     r14d, r14d
0x18005140a  mov     dword ptr [rsp+108h+pSourceSid+4], r14d
0x18005140f  test    al, 20h
0x180051411  jnz     loc_180051813
0x180051417  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18005141e  xor     edx, edx; dwFlags
0x180051420  mov     r8d, 18h; dwBytes
0x180051426  call    cs:__imp_HeapAlloc
0x18005142c  mov     rdi, rax
0x18005142f  test    rax, rax
0x180051432  jz      loc_1800516EF
0x180051438  mov     [rax+0Ch], r14d
0x18005143c  lea     rax, ??_7ProxyResolverNodeInUse@@6B@; const ProxyResolverNodeInUse::`vftable'
0x180051443  mov     [rdi], rax
0x180051446  mov     dword ptr [rdi+8], 1
0x18005144d  mov     [rdi+10h], r14
0x180051451  test    byte ptr cs:xmmword_180107A60, 20h
0x180051458  jnz     loc_180051831
0x18005145e  mov     r13d, r14d
0x180051461  lock inc dword ptr [rsi]
0x180051464  mov     rcx, [rdi+10h]; this
0x180051468  test    rcx, rcx
0x18005146b  jz      short loc_180051472
0x18005146d  call    ?Release@SettingsResolverNode@@QEAAKXZ; SettingsResolverNode::Release(void)
0x180051472  mov     [rdi+10h], rsi
0x180051476  test    byte ptr cs:xmmword_180107A60, 20h
0x18005147d  jnz     loc_18005184F
0x180051483  lock inc dword ptr [rsi+80h]
0x18005148a  test    byte ptr cs:xmmword_180107A60, 20h
0x180051491  jnz     loc_180051752
0x180051497  test    r13d, r13d
0x18005149a  js      loc_180051877
0x1800514a0  mov     rax, [rdi+10h]
0x1800514a4  mov     r14, [rax+18h]
0x1800514a8  test    r14, r14
0x1800514ab  jz      loc_18005117A
0x1800514b1  mov     rax, [r14]
0x1800514b4  mov     rcx, r14
0x1800514b7  mov     rax, [rax+8]
0x1800514bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514c0  jmp     loc_18005117A
0x1800514c5  xor     esi, esi
0x1800514c7  lea     rcx, [r12+20h]; SRWLock
0x1800514cc  call    cs:__imp_ReleaseSRWLockShared
0x1800514d2  xor     r14d, r14d
0x1800514d5  mov     dword ptr [rsp+108h+var_A8+4], 0
0x1800514dd  xor     r15d, r15d
0x1800514e0  mov     [rsp+108h+var_9C], 0
0x1800514e8  mov     [rsp+70h], r15
0x1800514ed  mov     qword ptr [rsp+60h], 0
0x1800514f6  mov     [rsp+108h+var_88], r14
0x1800514fe  test    byte ptr cs:xmmword_180107A60, 20h
0x180051505  jnz     loc_180051884
0x18005150b  mov     rdx, [rsp+108h+var_78]; struct tagProxySettings *
0x180051513  lea     rax, [r12+20h]
0x180051518  mov     [rsp+108h+var_50], rax
0x180051520  xor     edi, edi
0x180051522  lea     rax, [rsp+108h+var_A8]
0x180051527  mov     [rsp+108h+var_A0], r14d
0x18005152c  mov     [rsp+108h+var_B8], rax; struct SettingsResolverNode **
0x180051531  mov     rax, [r12+68h]
0x180051536  mov     [rsp+108h+var_C0], rax; unsigned __int64
0x18005153b  mov     rax, [r12+128h]
0x180051543  mov     [rsp+108h+var_C8], rax; struct CWxGlobalCountersRefCounted *
0x180051548  mov     rax, [rsp+108h+var_80]
0x180051550  mov     [rsp+108h+var_D0], rax; struct _SESSION_OPTIONS *
0x180051555  mov     eax, [rsp+108h+arg_28]
0x18005155c  mov     [rsp+108h+var_D8], eax; int
0x180051560  mov     eax, [rsp+108h+arg_20]
0x180051567  mov     [rsp+108h+var_E0], eax; int
0x18005156b  mov     rax, [rsp+108h+pSourceSid]
0x180051570  mov     [rsp+108h+var_E8], rax; struct _SID *
0x180051575  call    ?CreateResolverNodeForSettings@@YAJPEBGPEBUtagProxySettings@@HHPEAU_SID@@HHPEBU_SESSION_OPTIONS@@PEAVCWxGlobalCountersRefCounted@@_KPEAPEAVSettingsResolverNode@@@Z; CreateResolverNodeForSettings(ushort const *,tagProxySettings const *,int,int,_SID *,int,int,_SESSION_OPTIONS const *,CWxGlobalCountersRefCounted *,unsigned __int64,SettingsResolverNode * *)
0x18005157a  mov     r12, [rsp+108h+var_A8]
0x18005157f  mov     r13d, eax
0x180051582  mov     r8d, eax
0x180051585  test    eax, eax
0x180051587  js      loc_1800518B8
0x18005158d  mov     rcx, [rsp+108h+var_50]; SRWLock
0x180051595  call    cs:__imp_AcquireSRWLockExclusive
0x18005159b  mov     rcx, [rsp+108h+var_70]
0x1800515a3  mov     eax, 1
0x1800515a8  mov     [rsp+108h+var_A0], eax
0x1800515ac  cmp     [rcx+54h], edi
0x1800515af  jz      loc_1800516DC
0x1800515b5  mov     rcx, [rcx+18h]
0x1800515b9  lea     r8, [rsp+108h+var_88]
0x1800515c1  mov     rdx, r12
  ... truncated ...
```
