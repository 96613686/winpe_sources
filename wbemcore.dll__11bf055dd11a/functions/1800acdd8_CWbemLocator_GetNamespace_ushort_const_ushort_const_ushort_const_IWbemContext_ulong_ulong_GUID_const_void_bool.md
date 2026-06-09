# CWbemLocator::GetNamespace(ushort const *,ushort const *,ushort const *,IWbemContext *,ulong,ulong,_GUID const &,void * *,bool,long)

- ea: `0x1800acdd8`
- end: `0x1800ad41f`
- name: `?GetNamespace@CWbemLocator@@QEAAJPEBG00PEAUIWbemContext@@KKAEBU_GUID@@PEAPEAX_NJ@Z`
- size: `1607`
- prototype: `int(CWbemLocator *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IWbemContext *, unsigned int, unsigned int, const struct _GUID *, void **, bool, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800abf00`
- `0x1800ac040`
- `0x1800ac170`

## callees

- `0x18000aadc`
- `0x18000b140`
- `0x18002d324`
- `0x18002f020`
- `0x18002f504`
- `0x18002fe54`
- `0x18003cfe0`
- `0x180056750`
- `0x18005ac04`
- `0x1800acdd8`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x1800ad2b7`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x1800ad2b7`
- `wbemcomn!GetMemLogObject` at `0x1800aceec`
- `wbemcomn!GetMemLogObject` at `0x1800acf43`
- `wbemcomn!GetMemLogObject` at `0x1800acf91`
- `wbemcomn!GetMemLogObject` at `0x1800ad016`
- `wbemcomn!GetMemLogObject` at `0x1800ad095`
- `wbemcomn!GetMemLogObject` at `0x1800ad180`
- `wbemcomn!GetMemLogObject` at `0x1800ad1cc`
- `wbemcomn!GetMemLogObject` at `0x1800ad26a`
- `wbemcomn!GetMemLogObject` at `0x1800ad2cb`
- `wbemcomn!GetMemLogObject` at `0x1800ad338`
- `wbemcomn!GetMemLogObject` at `0x1800ad37d`
- `wbemcomn!GetMemLogObject` at `0x1800ad3b6`
- `wbemcomn!GetMemLogObject` at `0x1800aceec`
- `wbemcomn!GetMemLogObject` at `0x1800acf43`
- `wbemcomn!GetMemLogObject` at `0x1800acf91`
- `wbemcomn!GetMemLogObject` at `0x1800ad016`
- `wbemcomn!GetMemLogObject` at `0x1800ad095`
- `wbemcomn!GetMemLogObject` at `0x1800ad180`
- `wbemcomn!GetMemLogObject` at `0x1800ad1cc`
- `wbemcomn!GetMemLogObject` at `0x1800ad26a`
- `wbemcomn!GetMemLogObject` at `0x1800ad2cb`
- `wbemcomn!GetMemLogObject` at `0x1800ad338`
- `wbemcomn!GetMemLogObject` at `0x1800ad37d`
- `wbemcomn!GetMemLogObject` at `0x1800ad3b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acefc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acf53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acfa1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad021`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad0a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad18b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad1d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad275`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad2d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad346`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad38b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad3c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acefc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acf53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800acfa1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad021`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad0a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad18b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad1d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad275`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad2d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad346`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad38b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800ad3c4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800acffa`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800acffa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemLocator::GetNamespace(
        CWbemLocator *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IWbemContext *a5,
        unsigned int a6,
        unsigned int a7,
        struct _GUID *a8,
        void **a9,
        bool a10,
        unsigned int a11)
{
  void **v14; // r12
  const unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // rcx
  int v17; // eax
  CMemoryLog *v18; // rax
  unsigned int v19; // edi
  CClientCnt *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  CMemoryLog *v24; // rax
  struct CCoreServices *Instance; // rax
  CCoreServices *v26; // r14
  CMemoryLog *v27; // rax
  HRESULT v28; // eax
  int SystemDefaultLocale; // ebx
  CMemoryLog *v30; // rax
  CClientCnt *v31; // rcx
  __int64 v32; // rdx
  void *v33; // rcx
  int v34; // esi
  CMemoryLog *v35; // rax
  int Services3; // edi
  const struct _GUID *v37; // r14
  CMemoryLog *v38; // rax
  CClientCnt *v39; // rcx
  __int64 v40; // rdx
  CMemoryLog *v41; // rax
  CWbemNamespace *v42; // rdi
  __int64 v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  CClientCnt *v47; // rcx
  __int64 v48; // rdx
  CMemoryLog *v49; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v51; // [rsp+70h] [rbp-19h] BYREF
  void *v52; // [rsp+78h] [rbp-11h] BYREF
  struct CCoreServices *v53; // [rsp+80h] [rbp-9h] BYREF
  void *ppInterface; // [rsp+D0h] [rbp+47h] BYREF
  const struct _GUID *v55; // [rsp+D8h] [rbp+4Fh] BYREF

  ppInterface = this;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)a4);
  }
  WbemIsImpersonating();
  if ( !a2 || (v14 = a9) == 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v48 = 19;
    goto LABEL_101;
  }
  *a9 = 0;
  if ( *a2 != 92 && *a2 != 47 || a2[1] != 92 && a2[1] != 47 )
  {
    v15 = a2;
LABEL_21:
    v17 = PreParsePath(v15, (unsigned int)(g_PathLimit - 19));
    if ( v17 == 1 )
    {
      v18 = GetMemLogObject();
      v19 = -2147217394;
      CMemoryLog::Write(v18, -2147217394);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v19;
      }
      v21 = 22;
      v22 = 2147749902LL;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, v22);
      return v19;
    }
    if ( v17 == 2 )
    {
      v24 = GetMemLogObject();
      v19 = -2147217300;
      CMemoryLog::Write(v24, -2147217300);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v19;
      }
      v21 = 23;
      v22 = 2147749996LL;
      goto LABEL_26;
    }
    Instance = CCoreServices::CreateInstance();
    v26 = Instance;
    if ( !Instance )
    {
      v27 = GetMemLogObject();
      v19 = -2147217402;
      CMemoryLog::Write(v27, -2147217402);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v19;
      }
      v21 = 24;
      v22 = 2147749894LL;
      goto LABEL_26;
    }
    v53 = Instance;
    ppInterface = 0;
    v28 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
    v52 = ppInterface;
    SystemDefaultLocale = 0;
    if ( v28 != -2147417833 )
      SystemDefaultLocale = v28;
    if ( SystemDefaultLocale < 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, SystemDefaultLocale);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_88;
      }
      v32 = 25;
      goto LABEL_55;
    }
    v33 = ppInterface;
    if ( ppInterface )
    {
      v34 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface);
      v33 = ppInterface;
    }
    else
    {
      v34 = 0;
    }
    if ( v33 )
    {
      if ( v34 )
      {
        SystemDefaultLocale = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v33 + 40LL))(v33);
        if ( SystemDefaultLocale < 0 )
        {
          v35 = GetMemLogObject();
          CMemoryLog::Write(v35, SystemDefaultLocale);
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_88;
          }
          v32 = 26;
LABEL_55:
          WPP_SF_d(
            *((_QWORD *)v31 + 2),
            v32,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            (unsigned int)SystemDefaultLocale);
LABEL_88:
          CReleaseMe::release((CReleaseMe *)&v52);
          CReleaseMe::release((CReleaseMe *)&v53);
          return (unsigned int)SystemDefaultLocale;
        }
      }
    }
    a8 = 0;
    Services3 = CCoreServices::GetServices3(
                  v26,
                  a2,
                  a3,
                  a5,
                  a11,
                  0,
                  0,
                  (a10 << 20) + 0x20000,
                  0,
                  0,
                  0xFFFFFFFF,
                  0,
                  &IID_IWbemServices,
                  (void **)&a8);
    v37 = a8;
    v55 = a8;
    if ( v34
      && ppInterface
      && (SystemDefaultLocale = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface),
          SystemDefaultLocale < 0) )
    {
      v38 = GetMemLogObject();
      CMemoryLog::Write(v38, SystemDefaultLocale);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_87;
      }
      v40 = 27;
    }
    else
    {
      if ( Services3 < 0 )
      {
        v41 = GetMemLogObject();
        CMemoryLog::Write(v41, Services3);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            (unsigned int)Services3);
        }
        CReleaseMe::release((CReleaseMe *)&v55);
        SystemDefaultLocale = Services3;
        goto LABEL_88;
      }
      v42 = (CWbemNamespace *)a8;
      *(_DWORD *)a8[7].Data4 = 1;
      if ( !a4 )
        goto LABEL_74;
      v43 = -1;
      do
        ++v43;
      while ( a4[v43] );
      if ( v43 )
      {
        SystemDefaultLocale = CWbemNamespace::_SetLocale(v42, a4);
      }
      else
      {
LABEL_74:
        v51 = 0;
        SystemDefaultLocale = GetSystemDefaultLocale(&v51);
        if ( SystemDefaultLocale < 0 )
        {
          v44 = GetMemLogObject();
          CMemoryLog::Write(v44, SystemDefaultLocale);
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_87;
          }
          v40 = 29;
          goto LABEL_86;
        }
        SystemDefaultLocale = CWbemNamespace::_SetLocale(v42, v51);
        CMUILocale::_Free(v51);
      }
      v55 = 0;
      *v14 = (void *)v37;
      if ( SystemDefaultLocale < 0 )
      {
        v45 = GetMemLogObject();
        CMemoryLog::Write(v45, SystemDefaultLocale);
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_87;
      }
      v40 = 30;
    }
LABEL_86:
    WPP_SF_d(
      *((_QWORD *)v39 + 2),
      v40,
      WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
      (unsigned int)SystemDefaultLocale);
LABEL_87:
    CReleaseMe::release((CReleaseMe *)&v55);
    goto LABEL_88;
  }
  v16 = a2 + 2;
  if ( a2 != (const unsigned __int16 *)-4LL )
  {
    while ( *v16 )
    {
      if ( *v16 == 92 || *v16 == 47 )
      {
        if ( !v16 )
          break;
        if ( v16 == a2 + 3 && a2[2] == 46 )
        {
          v15 = v16 + 1;
          goto LABEL_21;
        }
        v46 = GetMemLogObject();
        CMemoryLog::Write(v46, -2147217400);
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = 21;
          goto LABEL_101;
        }
        return 2147749896LL;
      }
      ++v16;
    }
  }
  v49 = GetMemLogObject();
  CMemoryLog::Write(v49, -2147217400);
  v47 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v48 = 20;
LABEL_101:
    WPP_SF_d(*((_QWORD *)v47 + 2), v48, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x1800acdd8  mov     [rsp-8+arg_10], rbx
0x1800acddd  mov     [rsp-8+ppInterface], rcx
0x1800acde2  push    rbp
0x1800acde3  push    rsi
0x1800acde4  push    rdi
0x1800acde5  push    r12
0x1800acde7  push    r13
0x1800acde9  push    r14
0x1800acdeb  push    r15
0x1800acded  lea     rbp, [rsp-7]
0x1800acdf2  sub     rsp, 90h
0x1800acdf9  mov     r15, r9
0x1800acdfc  mov     r13, r8
0x1800acdff  mov     rdi, rdx
0x1800ace02  lea     rax, WPP_GLOBAL_Control
0x1800ace09  lea     r14, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800ace10  mov     ebx, 1
0x1800ace15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace1c  cmp     rcx, rax
0x1800ace1f  jz      short loc_1800ACE48
0x1800ace21  test    [rcx+1Ch], bl
0x1800ace24  jz      short loc_1800ACE48
0x1800ace26  cmp     byte ptr [rcx+19h], 5
0x1800ace2a  jb      short loc_1800ACE48
0x1800ace2c  lea     edx, [rbx+11h]
0x1800ace2f  mov     qword ptr [rsp+0C0h+var_98], r9
0x1800ace34  mov     qword ptr [rsp+0C0h+var_A0], r8
0x1800ace39  mov     r9, rdi
0x1800ace3c  mov     r8, r14
0x1800ace3f  mov     rcx, [rcx+10h]
0x1800ace43  call    WPP_SF_SSS
0x1800ace48  call    ?WbemIsImpersonating@@YA_NXZ; WbemIsImpersonating(void)
0x1800ace4d  xor     esi, esi
0x1800ace4f  test    rdi, rdi
0x1800ace52  jz      loc_1800AD3B6
0x1800ace58  mov     r12, [rbp+37h+arg_40]
0x1800ace5f  test    r12, r12
0x1800ace62  jz      loc_1800AD3B6
0x1800ace68  mov     [r12], rsi
0x1800ace6c  cmp     word ptr [rdi], 5Ch ; '\'
0x1800ace70  jz      short loc_1800ACE78
0x1800ace72  cmp     word ptr [rdi], 2Fh ; '/'
0x1800ace76  jnz     short loc_1800ACE86
0x1800ace78  cmp     word ptr [rdi+2], 5Ch ; '\'
0x1800ace7d  jz      short loc_1800ACE8B
0x1800ace7f  cmp     word ptr [rdi+2], 2Fh ; '/'
0x1800ace84  jz      short loc_1800ACE8B
0x1800ace86  mov     rcx, rdi
0x1800ace89  jmp     short loc_1800ACEDA
0x1800ace8b  lea     rdx, [rdi+4]
0x1800ace8f  mov     rcx, rdx
0x1800ace92  test    rdx, rdx
0x1800ace95  jz      loc_1800AD37D
0x1800ace9b  cmp     [rcx], si
0x1800ace9e  jz      loc_1800AD37D
0x1800acea4  cmp     word ptr [rcx], 5Ch ; '\'
0x1800acea8  jz      short loc_1800ACEB6
0x1800aceaa  cmp     word ptr [rcx], 2Fh ; '/'
0x1800aceae  jz      short loc_1800ACEB6
0x1800aceb0  add     rcx, 2
0x1800aceb4  jmp     short loc_1800ACE9B
0x1800aceb6  test    rcx, rcx
0x1800aceb9  jz      loc_1800AD37D
0x1800acebf  lea     rax, [rdi+6]
0x1800acec3  cmp     rcx, rax
0x1800acec6  jnz     loc_1800AD338
0x1800acecc  cmp     word ptr [rdx], 2Eh ; '.'
0x1800aced0  jnz     loc_1800AD338
0x1800aced6  add     rcx, 2
0x1800aceda  mov     edx, cs:?g_PathLimit@@3KA; ulong g_PathLimit
0x1800acee0  add     edx, 0FFFFFFEDh
0x1800acee3  call    ?PreParsePath@@YA?AW4AcceptingState@@PEAGK@Z; PreParsePath(ushort *,ulong)
0x1800acee8  cmp     eax, ebx
0x1800aceea  jnz     short loc_1800ACF3E
0x1800aceec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800acef2  mov     edi, 8004100Eh
0x1800acef7  mov     edx, edi
0x1800acef9  mov     rcx, rax
0x1800acefc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800acf02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf09  lea     rax, WPP_GLOBAL_Control
0x1800acf10  cmp     rcx, rax
0x1800acf13  jz      short loc_1800ACF37
0x1800acf15  test    [rcx+1Ch], bl
0x1800acf18  jz      short loc_1800ACF37
0x1800acf1a  cmp     byte ptr [rcx+19h], 2
0x1800acf1e  jb      short loc_1800ACF37
0x1800acf20  mov     edx, 16h
0x1800acf25  mov     r9d, 8004100Eh
0x1800acf2b  mov     r8, r14
0x1800acf2e  mov     rcx, [rcx+10h]
0x1800acf32  call    WPP_SF_d
0x1800acf37  mov     eax, edi
0x1800acf39  jmp     loc_1800AD404
0x1800acf3e  cmp     eax, 2
0x1800acf41  jnz     short loc_1800ACF84
0x1800acf43  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800acf49  mov     edi, 8004106Ch
0x1800acf4e  mov     edx, edi
0x1800acf50  mov     rcx, rax
0x1800acf53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800acf59  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf60  lea     rax, WPP_GLOBAL_Control
0x1800acf67  cmp     rcx, rax
0x1800acf6a  jz      short loc_1800ACF37
0x1800acf6c  test    [rcx+1Ch], bl
0x1800acf6f  jz      short loc_1800ACF37
0x1800acf71  cmp     byte ptr [rcx+19h], 2
0x1800acf75  jb      short loc_1800ACF37
0x1800acf77  mov     edx, 17h
0x1800acf7c  mov     r9d, 8004106Ch
0x1800acf82  jmp     short loc_1800ACF2B
0x1800acf84  call    ?CreateInstance@CCoreServices@@SAPEAV1@XZ; CCoreServices::CreateInstance(void)
0x1800acf89  mov     r14, rax
0x1800acf8c  test    rax, rax
0x1800acf8f  jnz     short loc_1800ACFE7
0x1800acf91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800acf97  mov     edi, 80041006h
0x1800acf9c  mov     edx, edi
0x1800acf9e  mov     rcx, rax
0x1800acfa1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800acfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acfae  lea     rax, WPP_GLOBAL_Control
0x1800acfb5  cmp     rcx, rax
0x1800acfb8  jz      loc_1800ACF37
0x1800acfbe  test    [rcx+1Ch], bl
0x1800acfc1  jz      loc_1800ACF37
0x1800acfc7  cmp     byte ptr [rcx+19h], 2
0x1800acfcb  jb      loc_1800ACF37
0x1800acfd1  lea     edx, [r14+18h]
0x1800acfd5  mov     r9d, 80041006h
0x1800acfdb  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800acfe2  jmp     loc_1800ACF2E
0x1800acfe7  mov     [rbp+37h+var_40], r14
0x1800acfeb  mov     [rbp+37h+ppInterface], rsi
0x1800acfef  lea     rdx, [rbp+37h+ppInterface]; ppInterface
0x1800acff3  lea     rcx, IID_IServerSecurity; riid
0x1800acffa  call    cs:__imp_CoGetCallContext
0x1800ad000  mov     rcx, [rbp+37h+ppInterface]
0x1800ad004  mov     [rbp+37h+var_48], rcx
0x1800ad008  mov     ebx, esi
0x1800ad00a  cmp     eax, 80010117h
0x1800ad00f  cmovnz  ebx, eax
0x1800ad012  test    ebx, ebx
0x1800ad014  jns     short loc_1800AD059
0x1800ad016  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ad01c  mov     edx, ebx
0x1800ad01e  mov     rcx, rax
0x1800ad021  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ad027  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad02e  lea     rax, WPP_GLOBAL_Control
0x1800ad035  cmp     rcx, rax
0x1800ad038  jz      loc_1800AD31E
0x1800ad03e  test    byte ptr [rcx+1Ch], 1
0x1800ad042  jz      loc_1800AD31E
0x1800ad048  cmp     byte ptr [rcx+19h], 2
0x1800ad04c  jb      loc_1800AD31E
0x1800ad052  mov     edx, 19h
0x1800ad057  jmp     short loc_1800AD0D6
0x1800ad059  mov     rcx, [rbp+37h+ppInterface]
0x1800ad05d  xor     ebx, ebx
0x1800ad05f  test    rcx, rcx
0x1800ad062  jz      short loc_1800AD078
0x1800ad064  mov     rax, [rcx]
0x1800ad067  mov     rax, [rax+30h]
0x1800ad06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad070  mov     esi, eax
0x1800ad072  mov     rcx, [rbp+37h+ppInterface]
0x1800ad076  jmp     short loc_1800AD07A
0x1800ad078  mov     esi, ebx
0x1800ad07a  test    rcx, rcx
0x1800ad07d  jz      short loc_1800AD0F0
0x1800ad07f  test    esi, esi
0x1800ad081  jz      short loc_1800AD0F0
0x1800ad083  mov     rax, [rcx]
0x1800ad086  mov     rax, [rax+28h]
0x1800ad08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad08f  mov     ebx, eax
0x1800ad091  test    eax, eax
0x1800ad093  jns     short loc_1800AD0EE
0x1800ad095  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ad09b  mov     edx, ebx
0x1800ad09d  mov     rcx, rax
0x1800ad0a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ad0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad0ad  lea     rax, WPP_GLOBAL_Control
0x1800ad0b4  cmp     rcx, rax
0x1800ad0b7  jz      loc_1800AD31E
0x1800ad0bd  test    byte ptr [rcx+1Ch], 1
0x1800ad0c1  jz      loc_1800AD31E
0x1800ad0c7  cmp     byte ptr [rcx+19h], 2
0x1800ad0cb  jb      loc_1800AD31E
0x1800ad0d1  mov     edx, 1Ah
0x1800ad0d6  mov     r9d, ebx
0x1800ad0d9  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800ad0e0  mov     rcx, [rcx+10h]
0x1800ad0e4  call    WPP_SF_d
0x1800ad0e9  jmp     loc_1800AD31E
0x1800ad0ee  xor     ebx, ebx
0x1800ad0f0  mov     [rbp+37h+arg_38], rbx
0x1800ad0f4  movzx   eax, [rbp+37h+arg_48]
0x1800ad0fb  shl     eax, 14h
0x1800ad0fe  add     eax, 20000h
0x1800ad103  lea     rcx, [rbp+37h+arg_38]
0x1800ad107  mov     [rsp+0C0h+var_58], rcx; void **
0x1800ad10c  lea     rcx, IID_IWbemServices
0x1800ad113  mov     [rsp+0C0h+var_60], rcx; struct _GUID *
0x1800ad118  mov     [rsp+0C0h+var_68], rbx; unsigned __int64
0x1800ad11d  mov     [rsp+0C0h+var_70], 0FFFFFFFFh; unsigned int
0x1800ad125  mov     [rsp+0C0h+var_78], rbx; unsigned __int16 *
0x1800ad12a  mov     [rsp+0C0h+var_80], rbx; unsigned __int16 *
0x1800ad12f  mov     [rsp+0C0h+var_88], eax; unsigned int
0x1800ad133  mov     [rsp+0C0h+var_90], ebx; unsigned int
0x1800ad137  mov     [rsp+0C0h+var_98], ebx; unsigned int
0x1800ad13b  mov     eax, [rbp+37h+arg_50]
0x1800ad141  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800ad145  mov     r9, [rbp+37h+arg_20]; struct IWbemContext *
0x1800ad149  mov     r8, r13; unsigned __int16 *
0x1800ad14c  mov     rdx, rdi; unsigned __int16 *
0x1800ad14f  mov     rcx, r14; this
0x1800ad152  call    ?GetServices3@CCoreServices@@UEAAJPEBG0PEAUIWbemContext@@KKKK00K_KAEBU_GUID@@PEAPEAX@Z; CCoreServices::GetServices3(ushort const *,ushort const *,IWbemContext *,ulong,ulong,ulong,ulong,ushort const *,ushort const *,ulong,unsigned __int64,_GUID const &,void * *)
0x1800ad157  mov     edi, eax
0x1800ad159  mov     r14, [rbp+37h+arg_38]
0x1800ad15d  mov     [rbp+37h+arg_8], r14
0x1800ad161  test    esi, esi
0x1800ad163  jz      short loc_1800AD1C8
0x1800ad165  mov     rcx, [rbp+37h+ppInterface]
0x1800ad169  test    rcx, rcx
0x1800ad16c  jz      short loc_1800AD1C8
0x1800ad16e  mov     rdx, [rcx]
0x1800ad171  mov     rax, [rdx+20h]
0x1800ad175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad17a  mov     ebx, eax
0x1800ad17c  test    eax, eax
0x1800ad17e  jns     short loc_1800AD1C6
0x1800ad180  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ad186  mov     edx, ebx
0x1800ad188  mov     rcx, rax
0x1800ad18b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ad191  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad198  lea     rax, WPP_GLOBAL_Control
0x1800ad19f  cmp     rcx, rax
0x1800ad1a2  jz      loc_1800AD314
0x1800ad1a8  test    byte ptr [rcx+1Ch], 1
0x1800ad1ac  jz      loc_1800AD314
0x1800ad1b2  cmp     byte ptr [rcx+19h], 2
0x1800ad1b6  jb      loc_1800AD314
0x1800ad1bc  mov     edx, 1Bh
0x1800ad1c1  jmp     loc_1800AD300
0x1800ad1c6  xor     ebx, ebx
0x1800ad1c8  test    edi, edi
0x1800ad1ca  jns     short loc_1800AD225
0x1800ad1cc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ad1d2  mov     edx, edi
0x1800ad1d4  mov     rcx, rax
0x1800ad1d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ad1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad1e4  lea     rax, WPP_GLOBAL_Control
0x1800ad1eb  cmp     rcx, rax
0x1800ad1ee  jz      short loc_1800AD215
0x1800ad1f0  test    byte ptr [rcx+1Ch], 1
0x1800ad1f4  jz      short loc_1800AD215
0x1800ad1f6  cmp     byte ptr [rcx+19h], 2
0x1800ad1fa  jb      short loc_1800AD215
0x1800ad1fc  mov     edx, 1Ch
0x1800ad201  mov     r9d, edi
0x1800ad204  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800ad20b  mov     rcx, [rcx+10h]
0x1800ad20f  call    WPP_SF_d
0x1800ad214  nop
0x1800ad215  lea     rcx, [rbp+37h+arg_8]; this
0x1800ad219  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800ad21e  mov     ebx, edi
0x1800ad220  jmp     loc_1800AD31E
0x1800ad225  mov     rdi, [rbp+37h+arg_38]
0x1800ad229  mov     dword ptr [rdi+78h], 1
0x1800ad230  test    r15, r15
0x1800ad233  jz      short loc_1800AD257
0x1800ad235  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ad239  inc     rax
0x1800ad23c  cmp     [r15+rax*2], bx
0x1800ad241  jnz     short loc_1800AD239
0x1800ad243  test    rax, rax
0x1800ad246  jz      short loc_1800AD257
0x1800ad248  mov     rdx, r15; unsigned __int16 *
0x1800ad24b  mov     rcx, rdi; this
0x1800ad24e  call    ?_SetLocale@CWbemNamespace@@QEAAJPEBG@Z; CWbemNamespace::_SetLocale(ushort const *)
0x1800ad253  mov     ebx, eax
0x1800ad255  jmp     short loc_1800AD2BD
0x1800ad257  mov     [rbp+37h+var_50], rbx
0x1800ad25b  lea     rcx, [rbp+37h+var_50]; unsigned __int16 **
0x1800ad25f  call    ?GetSystemDefaultLocale@@YAJPEAPEAG@Z; GetSystemDefaultLocale(ushort * *)
0x1800ad264  mov     ebx, eax
0x1800ad266  test    eax, eax
0x1800ad268  jns     short loc_1800AD2A5
0x1800ad26a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800ad270  mov     edx, ebx
0x1800ad272  mov     rcx, rax
0x1800ad275  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800ad27b  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
