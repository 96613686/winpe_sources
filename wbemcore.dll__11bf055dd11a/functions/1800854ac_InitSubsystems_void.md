# InitSubsystems(void)

- ea: `0x1800854ac`
- end: `0x1800858e6`
- name: `?InitSubsystems@@YAJXZ`
- size: `1082`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180059524`

## callees

- `0x18000b140`
- `0x18002d324`
- `0x18003cfe0`
- `0x18007e534`
- `0x18007e768`
- `0x1800814ac`
- `0x1800854ac`
- `0x1800858ec`
- `0x1800866b8`
- `0x1800a3f5c`
- `0x1800a4ddc`
- `0x1800a4fb8`
- `0x1800a5040`
- `0x1800a5348`

## import_xrefs

- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x18008577a`
- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x18008577a`
- `wbemcomn!GetMemLogObject` at `0x1800854d2`
- `wbemcomn!GetMemLogObject` at `0x180085551`
- `wbemcomn!GetMemLogObject` at `0x18008559d`
- `wbemcomn!GetMemLogObject` at `0x18008561d`
- `wbemcomn!GetMemLogObject` at `0x18008566f`
- `wbemcomn!GetMemLogObject` at `0x1800856ad`
- `wbemcomn!GetMemLogObject` at `0x1800856fd`
- `wbemcomn!GetMemLogObject` at `0x18008573b`
- `wbemcomn!GetMemLogObject` at `0x180085788`
- `wbemcomn!GetMemLogObject` at `0x1800857cc`
- `wbemcomn!GetMemLogObject` at `0x180085821`
- `wbemcomn!GetMemLogObject` at `0x180085863`
- `wbemcomn!GetMemLogObject` at `0x1800854d2`
- `wbemcomn!GetMemLogObject` at `0x180085551`
- `wbemcomn!GetMemLogObject` at `0x18008559d`
- `wbemcomn!GetMemLogObject` at `0x18008561d`
- `wbemcomn!GetMemLogObject` at `0x18008566f`
- `wbemcomn!GetMemLogObject` at `0x1800856ad`
- `wbemcomn!GetMemLogObject` at `0x1800856fd`
- `wbemcomn!GetMemLogObject` at `0x18008573b`
- `wbemcomn!GetMemLogObject` at `0x180085788`
- `wbemcomn!GetMemLogObject` at `0x1800857cc`
- `wbemcomn!GetMemLogObject` at `0x180085821`
- `wbemcomn!GetMemLogObject` at `0x180085863`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800854e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008555d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800855a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085629`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008567b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800856b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085709`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085746`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085794`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800857dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008582c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008586e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800854e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008555d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800855a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085629`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008567b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800856b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085709`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085746`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085794`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800857dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008582c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008586e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InitSubsystems(void)
{
  struct CCoreServices *Instance; // rax
  struct CCoreServices *v1; // r15
  CMemoryLog *v2; // rax
  int inited; // ebp
  CMemoryLog *v4; // rax
  CMemoryLog *v5; // rax
  CClientCnt *v6; // rcx
  __int64 v7; // rdx
  int v8; // r13d
  int DefaultMofs; // ebp
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  __int64 v17; // r9
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  struct CCoreServices *v21; // [rsp+40h] [rbp+8h] BYREF

  CCoreServices::Initialize();
  Instance = CCoreServices::CreateInstance();
  v1 = Instance;
  if ( Instance )
  {
    v21 = Instance;
    dword_1801ADB08 = 0;
    inited = InitRepository();
    if ( inited >= 0 )
    {
      dword_1801ADB08 = 1;
      if ( g_bDefaultMofLoadingNeeded || AutoRecoveryWasInterrupted() || (v8 = 0, IncompleteWMIDetected()) )
      {
        DefaultMofs = ConfigMgr::LoadDefaultMofs();
        if ( DefaultMofs < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              144,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              (unsigned int)DefaultMofs);
          }
        }
        v8 = 1;
      }
      inited = InitProvSS(v1);
      if ( inited >= 0 )
      {
        inited = InitESS(v1, v8);
        if ( inited >= 0 )
        {
          if ( (unsigned int)CStaticCritSec::anyFailure() )
          {
            v15 = GetMemLogObject();
            CMemoryLog::Write(v15, -1);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                149,
                WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
                2147749898LL);
            }
            v16 = GetMemLogObject();
            inited = -2147217398;
            CMemoryLog::Write(v16, -2147217398);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_67;
            }
            v7 = 150;
            v17 = 2147749898LL;
            goto LABEL_66;
          }
          inited = InitRAHooks(v1);
          if ( inited >= 0 )
          {
            inited = InitProviderRegistrationHooks(v1);
            if ( inited >= 0 )
            {
              WmiSqmRepositorySizeOnInitialization();
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_67;
              }
              v7 = 153;
            }
            else
            {
              v19 = GetMemLogObject();
              CMemoryLog::Write(v19, inited);
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_67;
              }
              v7 = 152;
            }
          }
          else
          {
            v18 = GetMemLogObject();
            CMemoryLog::Write(v18, inited);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_67;
            }
            v7 = 151;
          }
        }
        else
        {
          v13 = GetMemLogObject();
          CMemoryLog::Write(v13, -1);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              147,
              WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
              (unsigned int)inited);
          }
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, inited);
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_67;
          }
          v7 = 148;
        }
      }
      else
      {
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)inited);
        }
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, inited);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_67;
        }
        v7 = 146;
      }
    }
    else
    {
      v4 = GetMemLogObject();
      CMemoryLog::Write(v4, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)inited);
      }
      v5 = GetMemLogObject();
      CMemoryLog::Write(v5, inited);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v7 = 143;
    }
    v17 = (unsigned int)inited;
LABEL_66:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, v17);
LABEL_67:
    CReleaseMe::release((CReleaseMe *)&v21);
    return (unsigned int)inited;
  }
  v2 = GetMemLogObject();
  inited = -2147217402;
  CMemoryLog::Write(v2, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749894LL);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800854ac  mov     [rsp+arg_8], rbp
0x1800854b1  mov     [rsp+arg_10], rsi
0x1800854b6  push    r13
0x1800854b8  push    r14
0x1800854ba  push    r15
0x1800854bc  sub     rsp, 20h
0x1800854c0  call    ?Initialize@CCoreServices@@SAJXZ; CCoreServices::Initialize(void)
0x1800854c5  call    ?CreateInstance@CCoreServices@@SAPEAV1@XZ; CCoreServices::CreateInstance(void)
0x1800854ca  mov     r15, rax
0x1800854cd  test    rax, rax
0x1800854d0  jnz     short loc_180085533
0x1800854d2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800854d8  mov     ebp, 80041006h
0x1800854dd  mov     edx, ebp
0x1800854df  mov     rcx, rax
0x1800854e2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800854e8  lea     r14, WPP_GLOBAL_Control
0x1800854ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800854f6  cmp     rcx, r14
0x1800854f9  jz      loc_1800858CF
0x1800854ff  test    byte ptr [rcx+1Ch], 1
0x180085503  jz      loc_1800858CF
0x180085509  cmp     byte ptr [rcx+19h], 2
0x18008550d  jb      loc_1800858CF
0x180085513  mov     edx, 8Bh
0x180085518  mov     r9d, 80041006h
0x18008551e  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180085525  mov     rcx, [rcx+10h]
0x180085529  call    WPP_SF_d
0x18008552e  jmp     loc_1800858CF
0x180085533  mov     [rsp+38h+arg_0], r15
0x180085538  mov     cs:dword_1801ADB08, 0
0x180085542  call    InitRepository
0x180085547  mov     ebp, eax
0x180085549  test    eax, eax
0x18008554b  jns     loc_1800855DC
0x180085551  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085557  or      edx, 0FFFFFFFFh
0x18008555a  mov     rcx, rax
0x18008555d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085563  lea     r14, WPP_GLOBAL_Control
0x18008556a  lea     rsi, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180085571  mov     rcx, cs:WPP_GLOBAL_Control
0x180085578  cmp     rcx, r14
0x18008557b  jz      short loc_18008559D
0x18008557d  test    byte ptr [rcx+1Ch], 1
0x180085581  jz      short loc_18008559D
0x180085583  cmp     byte ptr [rcx+19h], 2
0x180085587  jb      short loc_18008559D
0x180085589  mov     edx, 8Eh
0x18008558e  mov     r9d, ebp
0x180085591  mov     r8, rsi
0x180085594  mov     rcx, [rcx+10h]
0x180085598  call    WPP_SF_d
0x18008559d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800855a3  mov     edx, ebp
0x1800855a5  mov     rcx, rax
0x1800855a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800855ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800855b5  cmp     rcx, r14
0x1800855b8  jz      loc_1800858C5
0x1800855be  test    byte ptr [rcx+1Ch], 1
0x1800855c2  jz      loc_1800858C5
0x1800855c8  cmp     byte ptr [rcx+19h], 2
0x1800855cc  jb      loc_1800858C5
0x1800855d2  mov     edx, 8Fh
0x1800855d7  jmp     loc_1800858B5
0x1800855dc  mov     cs:dword_1801ADB08, 1
0x1800855e6  lea     r14, WPP_GLOBAL_Control
0x1800855ed  lea     rsi, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800855f4  cmp     cs:?g_bDefaultMofLoadingNeeded@@3_NA, 0; bool g_bDefaultMofLoadingNeeded
0x1800855fb  jnz     short loc_180085612
0x1800855fd  call    ?AutoRecoveryWasInterrupted@@YA_NXZ; AutoRecoveryWasInterrupted(void)
0x180085602  test    al, al
0x180085604  jnz     short loc_180085612
0x180085606  xor     r13d, r13d
0x180085609  call    ?IncompleteWMIDetected@@YA_NXZ; IncompleteWMIDetected(void)
0x18008560e  test    al, al
0x180085610  jz      short loc_180085661
0x180085612  call    ?LoadDefaultMofs@ConfigMgr@@SAJXZ; ConfigMgr::LoadDefaultMofs(void)
0x180085617  mov     ebp, eax
0x180085619  test    eax, eax
0x18008561b  jns     short loc_18008565B
0x18008561d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085623  or      edx, 0FFFFFFFFh
0x180085626  mov     rcx, rax
0x180085629  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008562f  mov     rcx, cs:WPP_GLOBAL_Control
0x180085636  cmp     rcx, r14
0x180085639  jz      short loc_18008565B
0x18008563b  test    byte ptr [rcx+1Ch], 1
0x18008563f  jz      short loc_18008565B
0x180085641  cmp     byte ptr [rcx+19h], 2
0x180085645  jb      short loc_18008565B
0x180085647  mov     edx, 90h
0x18008564c  mov     r9d, ebp
0x18008564f  mov     r8, rsi
0x180085652  mov     rcx, [rcx+10h]
0x180085656  call    WPP_SF_d
0x18008565b  mov     r13d, 1
0x180085661  mov     rcx, r15; struct CCoreServices *
0x180085664  call    ?InitProvSS@@YAJPEAVCCoreServices@@@Z; InitProvSS(CCoreServices *)
0x180085669  mov     ebp, eax
0x18008566b  test    eax, eax
0x18008566d  jns     short loc_1800856EC
0x18008566f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085675  or      edx, 0FFFFFFFFh
0x180085678  mov     rcx, rax
0x18008567b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085681  mov     rcx, cs:WPP_GLOBAL_Control
0x180085688  cmp     rcx, r14
0x18008568b  jz      short loc_1800856AD
0x18008568d  test    byte ptr [rcx+1Ch], 1
0x180085691  jz      short loc_1800856AD
0x180085693  cmp     byte ptr [rcx+19h], 2
0x180085697  jb      short loc_1800856AD
0x180085699  mov     edx, 91h
0x18008569e  mov     r9d, ebp
0x1800856a1  mov     r8, rsi
0x1800856a4  mov     rcx, [rcx+10h]
0x1800856a8  call    WPP_SF_d
0x1800856ad  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800856b3  mov     edx, ebp
0x1800856b5  mov     rcx, rax
0x1800856b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800856be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800856c5  cmp     rcx, r14
0x1800856c8  jz      loc_1800858C5
0x1800856ce  test    byte ptr [rcx+1Ch], 1
0x1800856d2  jz      loc_1800858C5
0x1800856d8  cmp     byte ptr [rcx+19h], 2
0x1800856dc  jb      loc_1800858C5
0x1800856e2  mov     edx, 92h
0x1800856e7  jmp     loc_1800858B5
0x1800856ec  mov     edx, r13d; int
0x1800856ef  mov     rcx, r15; struct _IWmiCoreServices *
0x1800856f2  call    ?InitESS@@YAJPEAU_IWmiCoreServices@@H@Z; InitESS(_IWmiCoreServices *,int)
0x1800856f7  mov     ebp, eax
0x1800856f9  test    eax, eax
0x1800856fb  jns     short loc_18008577A
0x1800856fd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085703  or      edx, 0FFFFFFFFh
0x180085706  mov     rcx, rax
0x180085709  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008570f  mov     rcx, cs:WPP_GLOBAL_Control
0x180085716  cmp     rcx, r14
0x180085719  jz      short loc_18008573B
0x18008571b  test    byte ptr [rcx+1Ch], 1
0x18008571f  jz      short loc_18008573B
0x180085721  cmp     byte ptr [rcx+19h], 2
0x180085725  jb      short loc_18008573B
0x180085727  mov     edx, 93h
0x18008572c  mov     r9d, ebp
0x18008572f  mov     r8, rsi
0x180085732  mov     rcx, [rcx+10h]
0x180085736  call    WPP_SF_d
0x18008573b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085741  mov     edx, ebp
0x180085743  mov     rcx, rax
0x180085746  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008574c  mov     rcx, cs:WPP_GLOBAL_Control
0x180085753  cmp     rcx, r14
0x180085756  jz      loc_1800858C5
0x18008575c  test    byte ptr [rcx+1Ch], 1
0x180085760  jz      loc_1800858C5
0x180085766  cmp     byte ptr [rcx+19h], 2
0x18008576a  jb      loc_1800858C5
0x180085770  mov     edx, 94h
0x180085775  jmp     loc_1800858B5
0x18008577a  call    cs:__imp_?anyFailure@CStaticCritSec@@SAHXZ; CStaticCritSec::anyFailure(void)
0x180085780  test    eax, eax
0x180085782  jz      loc_180085813
0x180085788  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008578e  or      edx, 0FFFFFFFFh
0x180085791  mov     rcx, rax
0x180085794  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008579a  mov     r15d, 8004100Ah
0x1800857a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800857a7  cmp     rcx, r14
0x1800857aa  jz      short loc_1800857CC
0x1800857ac  test    byte ptr [rcx+1Ch], 1
0x1800857b0  jz      short loc_1800857CC
0x1800857b2  cmp     byte ptr [rcx+19h], 2
0x1800857b6  jb      short loc_1800857CC
0x1800857b8  mov     edx, 95h
0x1800857bd  mov     r9d, r15d
0x1800857c0  mov     r8, rsi
0x1800857c3  mov     rcx, [rcx+10h]
0x1800857c7  call    WPP_SF_d
0x1800857cc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800857d2  mov     ebp, 8004100Ah
0x1800857d7  mov     edx, ebp
0x1800857d9  mov     rcx, rax
0x1800857dc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800857e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800857e9  cmp     rcx, r14
0x1800857ec  jz      loc_1800858C5
0x1800857f2  test    byte ptr [rcx+1Ch], 1
0x1800857f6  jz      loc_1800858C5
0x1800857fc  cmp     byte ptr [rcx+19h], 2
0x180085800  jb      loc_1800858C5
0x180085806  mov     edx, 96h
0x18008580b  mov     r9d, r15d
0x18008580e  jmp     loc_1800858B8
0x180085813  mov     rcx, r15; struct _IWmiCoreServices *
0x180085816  call    ?InitRAHooks@@YAJPEAU_IWmiCoreServices@@@Z; InitRAHooks(_IWmiCoreServices *)
0x18008581b  mov     ebp, eax
0x18008581d  test    eax, eax
0x18008581f  jns     short loc_180085855
0x180085821  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085827  mov     edx, ebp
0x180085829  mov     rcx, rax
0x18008582c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085832  mov     rcx, cs:WPP_GLOBAL_Control
0x180085839  cmp     rcx, r14
0x18008583c  jz      loc_1800858C5
0x180085842  test    byte ptr [rcx+1Ch], 1
0x180085846  jz      short loc_1800858C5
0x180085848  cmp     byte ptr [rcx+19h], 2
0x18008584c  jb      short loc_1800858C5
0x18008584e  mov     edx, 97h
0x180085853  jmp     short loc_1800858B5
0x180085855  mov     rcx, r15; struct _IWmiCoreServices *
0x180085858  call    ?InitProviderRegistrationHooks@@YAJPEAU_IWmiCoreServices@@@Z; InitProviderRegistrationHooks(_IWmiCoreServices *)
0x18008585d  mov     ebp, eax
0x18008585f  test    eax, eax
0x180085861  jns     short loc_180085893
0x180085863  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085869  mov     edx, ebp
0x18008586b  mov     rcx, rax
0x18008586e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085874  mov     rcx, cs:WPP_GLOBAL_Control
0x18008587b  cmp     rcx, r14
0x18008587e  jz      short loc_1800858C5
0x180085880  test    byte ptr [rcx+1Ch], 1
0x180085884  jz      short loc_1800858C5
0x180085886  cmp     byte ptr [rcx+19h], 2
0x18008588a  jb      short loc_1800858C5
0x18008588c  mov     edx, 98h
0x180085891  jmp     short loc_1800858B5
0x180085893  call    ?WmiSqmRepositorySizeOnInitialization@@YAXXZ; WmiSqmRepositorySizeOnInitialization(void)
0x180085898  mov     rcx, cs:WPP_GLOBAL_Control
0x18008589f  cmp     rcx, r14
0x1800858a2  jz      short loc_1800858C5
0x1800858a4  test    byte ptr [rcx+1Ch], 1
0x1800858a8  jz      short loc_1800858C5
0x1800858aa  cmp     byte ptr [rcx+19h], 2
0x1800858ae  jb      short loc_1800858C5
0x1800858b0  mov     edx, 99h
0x1800858b5  mov     r9d, ebp
0x1800858b8  mov     r8, rsi
0x1800858bb  mov     rcx, [rcx+10h]
0x1800858bf  call    WPP_SF_d
0x1800858c4  nop
0x1800858c5  lea     rcx, [rsp+38h+arg_0]; this
0x1800858ca  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800858cf  mov     eax, ebp
0x1800858d1  mov     rbp, [rsp+38h+arg_8]
0x1800858d6  mov     rsi, [rsp+38h+arg_10]
0x1800858db  add     rsp, 20h
0x1800858df  pop     r15
0x1800858e1  pop     r14
0x1800858e3  pop     r13
0x1800858e5  retn
```
