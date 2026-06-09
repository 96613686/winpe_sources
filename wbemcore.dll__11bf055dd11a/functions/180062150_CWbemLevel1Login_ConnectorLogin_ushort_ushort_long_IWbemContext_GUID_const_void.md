# CWbemLevel1Login::ConnectorLogin(ushort *,ushort *,long,IWbemContext *,_GUID const &,void * *)

- ea: `0x180062150`
- end: `0x18006295c`
- name: `?ConnectorLogin@CWbemLevel1Login@@QEAAJPEAG0JPEAUIWbemContext@@AEBU_GUID@@PEAPEAX@Z`
- size: `2060`
- prototype: `__int64 __usercall@<rax>(CWbemLevel1Login *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, struct IWbemContext *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x180062110`

## callees

- `0x18000a8b8`
- `0x18000b140`
- `0x18000b46c`
- `0x18002bf10`
- `0x18002dda4`
- `0x180056750`
- `0x180058788`
- `0x180062150`
- `0x1800b0d88`
- `0x1800ce4c6`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062841`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062852`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062841`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062852`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006286c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006286c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062658`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062756`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062658`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062756`
- `wbemcomn!?ValidateMemSize@CWin32DefaultArena@@SAHH@Z` at `0x1800623bc`
- `wbemcomn!?ValidateMemSize@CWin32DefaultArena@@SAHH@Z` at `0x1800623bc`
- `wbemcomn!GetMemLogObject` at `0x180062186`
- `wbemcomn!GetMemLogObject` at `0x180062239`
- `wbemcomn!GetMemLogObject` at `0x1800622a6`
- `wbemcomn!GetMemLogObject` at `0x18006230d`
- `wbemcomn!GetMemLogObject` at `0x180062363`
- `wbemcomn!GetMemLogObject` at `0x1800623ca`
- `wbemcomn!GetMemLogObject` at `0x18006240d`
- `wbemcomn!GetMemLogObject` at `0x1800624f0`
- `wbemcomn!GetMemLogObject` at `0x18006260d`
- `wbemcomn!GetMemLogObject` at `0x18006265e`
- `wbemcomn!GetMemLogObject` at `0x18006275c`
- `wbemcomn!GetMemLogObject` at `0x1800628d3`
- `wbemcomn!GetMemLogObject` at `0x180062186`
- `wbemcomn!GetMemLogObject` at `0x180062239`
- `wbemcomn!GetMemLogObject` at `0x1800622a6`
- `wbemcomn!GetMemLogObject` at `0x18006230d`
- `wbemcomn!GetMemLogObject` at `0x180062363`
- `wbemcomn!GetMemLogObject` at `0x1800623ca`
- `wbemcomn!GetMemLogObject` at `0x18006240d`
- `wbemcomn!GetMemLogObject` at `0x1800624f0`
- `wbemcomn!GetMemLogObject` at `0x18006260d`
- `wbemcomn!GetMemLogObject` at `0x18006265e`
- `wbemcomn!GetMemLogObject` at `0x18006275c`
- `wbemcomn!GetMemLogObject` at `0x1800628d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062191`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062247`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800622b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006231b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062371`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800623da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006241b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800624fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006261d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006266c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006276a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800628e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062191`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062247`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800622b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006231b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180062371`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800623da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006241b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800624fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006261d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006266c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006276a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800628e1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18006246f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18006246f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemLevel1Login::ConnectorLogin(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        const struct _GUID *a6,
        void **a7)
{
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  void **v14; // r12
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  int v17; // eax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  HRESULT v22; // esi
  void *v23; // rbx
  unsigned int v24; // edi
  CMemoryLog *v25; // rax
  int v26; // esi
  int v27; // r8d
  int v28; // esi
  int v29; // r9d
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  __int64 v32; // rcx
  const char *v33; // rcx
  CMemoryLog *v34; // rax
  const unsigned __int16 *v35; // rcx
  unsigned int v36; // edi
  CMemoryLog *v37; // rax
  int v38; // [rsp+50h] [rbp-58h] BYREF
  int v39; // [rsp+54h] [rbp-54h] BYREF
  int v40; // [rsp+58h] [rbp-50h] BYREF
  const char *v41; // [rsp+60h] [rbp-48h]
  void *v42; // [rsp+68h] [rbp-40h]
  void *ppInterface; // [rsp+70h] [rbp-38h] BYREF
  const unsigned __int16 *v44; // [rsp+78h] [rbp-30h] BYREF

  v11 = InitAndWaitForClient();
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
        (unsigned int)v11);
    }
    return (unsigned int)v11;
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4);
  }
  v14 = a7;
  if ( a7 && a2 )
  {
    if ( (a4 & 0xFFFFFEBF) != 0 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749896LL);
      }
      return 2147749896LL;
    }
    if ( memcmp_0(&IID_IWbemServices, &IID_IWbemServices, 0x10u) )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2147217400);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749896LL);
      }
      return 2147749896LL;
    }
    v17 = PreParsePath(a2, (unsigned int)(g_PathLimit - 19));
    if ( v17 == 1 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, -2147217394);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749902LL);
      }
      return 2147749902LL;
    }
    if ( v17 == 2 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217300);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749996LL);
      }
      return 2147749996LL;
    }
    *v14 = 0;
    if ( !CWin32DefaultArena::ValidateMemSize(0) )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids);
      }
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749894LL);
      }
      return 2147749894LL;
    }
    ppInterface = 0;
    v22 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
    v23 = ppInterface;
    v42 = ppInterface;
    if ( v22 == -2147417833 )
    {
      v24 = CWbemLevel1Login::LoginUser((CWbemLevel1Login *)this, a2, a3, a4, a5, 1, &IID_IWbemServices, v14, 1);
      if ( v23 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
      v42 = 0;
      return v24;
    }
    if ( v22 < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v22);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
          (unsigned int)v22);
      }
      if ( v23 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
      v42 = 0;
      return (unsigned int)v22;
    }
    v26 = 0;
    v40 = 0;
    v39 = 0;
    LODWORD(a6) = 0;
    v38 = 0;
    v44 = 0;
    if ( (*(int (__fastcall **)(void *, int *, int *, _QWORD, const struct _GUID **, _QWORD, const unsigned __int16 **, int *))(*(_QWORD *)ppInterface + 24LL))(
           ppInterface,
           &v40,
           &v39,
           0,
           &a6,
           0,
           &v44,
           &v38) >= 0 )
    {
      v29 = (int)v44;
      if ( v44 )
      {
        v32 = -1;
        do
          ++v32;
        while ( v44[v32] );
        if ( v32 )
          v26 = 1;
      }
    }
    else
    {
      v28 = (*(__int64 (__fastcall **)(void *, int *, int *, _QWORD, const struct _GUID **, _QWORD, _QWORD, int *))(*(_QWORD *)ppInterface + 24LL))(
              ppInterface,
              &v40,
              &v39,
              0,
              &a6,
              0,
              0,
              &v38);
      v29 = 0;
      v44 = 0;
      if ( v28 < 0 )
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            (unsigned int)v28);
        }
        Sleep(0x1388u);
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, -2147217405);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            2147749891LL);
        }
        if ( v23 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
        v42 = 0;
        return 2147749891LL;
      }
      v26 = 0;
    }
    v33 = 0;
    v41 = 0;
    switch ( (int)a6 )
    {
      case 1:
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids);
        }
        Sleep(0x1388u);
        v34 = GetMemLogObject();
        CMemoryLog::Write(v34, -2147217405);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            2147749891LL);
        }
        if ( v23 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
        v42 = 0;
        return 2147749891LL;
      case 2:
        v33 = "Connect";
        goto LABEL_95;
      case 3:
        v33 = "Call";
        goto LABEL_95;
      case 4:
        v33 = "Packet";
        goto LABEL_95;
      case 5:
        v33 = "Integrity";
        goto LABEL_95;
      case 6:
        v33 = "Privacy";
LABEL_95:
        v41 = v33;
        break;
      default:
        break;
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Ssddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v27,
        v29,
        (__int64)v33,
        v40,
        v39,
        v38);
    }
    AcquireSRWLockExclusive(this + 10);
    if ( v26 )
      v35 = v44;
    else
      v35 = L"<unknown>";
    this[3].Ptr = Macro_CloneLPWSTR(v35);
    ReleaseSRWLockExclusive(this + 10);
    v36 = CWbemLevel1Login::LoginUser((CWbemLevel1Login *)this, a2, a3, a4, a5, 0, &IID_IWbemServices, v14, 0);
    if ( v23 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
    v42 = 0;
    return v36;
  }
  else
  {
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
}

```

## disassembly

```asm
0x180062150  mov     [rsp+arg_0], rbx
0x180062155  mov     [rsp+arg_8], rsi
0x18006215a  mov     [rsp+arg_10], r8
0x18006215f  push    rdi
0x180062160  push    r12
0x180062162  push    r13
0x180062164  push    r14
0x180062166  push    r15
0x180062168  sub     rsp, 80h
0x18006216f  mov     r13d, r9d
0x180062172  mov     rsi, r8
0x180062175  mov     r14, rdx
0x180062178  mov     r15, rcx
0x18006217b  call    ?InitAndWaitForClient@@YAJXZ; InitAndWaitForClient(void)
0x180062180  mov     ebx, eax
0x180062182  test    eax, eax
0x180062184  jns     short loc_1800621D5
0x180062186  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006218c  mov     edx, ebx
0x18006218e  mov     rcx, rax
0x180062191  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062197  lea     rdi, WPP_GLOBAL_Control
0x18006219e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621a5  cmp     rcx, rdi
0x1800621a8  jz      short loc_1800621CE
0x1800621aa  test    byte ptr [rcx+1Ch], 1
0x1800621ae  jz      short loc_1800621CE
0x1800621b0  cmp     byte ptr [rcx+19h], 2
0x1800621b4  jb      short loc_1800621CE
0x1800621b6  mov     edx, 32h ; '2'
0x1800621bb  mov     r9d, ebx
0x1800621be  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800621c5  mov     rcx, [rcx+10h]
0x1800621c9  call    WPP_SF_d
0x1800621ce  mov     eax, ebx
0x1800621d0  jmp     loc_180062926
0x1800621d5  lea     rdi, WPP_GLOBAL_Control
0x1800621dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621e3  cmp     rcx, rdi
0x1800621e6  jz      short loc_180062216
0x1800621e8  test    byte ptr [rcx+1Ch], 1
0x1800621ec  jz      short loc_180062216
0x1800621ee  cmp     byte ptr [rcx+19h], 5
0x1800621f2  jb      short loc_180062216
0x1800621f4  mov     edx, 33h ; '3'
0x1800621f9  mov     dword ptr [rsp+0A8h+var_80], r13d
0x1800621fe  mov     [rsp+0A8h+var_88], rsi
0x180062203  mov     r9, r14
0x180062206  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x18006220d  mov     rcx, [rcx+10h]
0x180062211  call    WPP_SF_SSD
0x180062216  mov     r12, [rsp+0A8h+arg_30]
0x18006221e  test    r12, r12
0x180062221  jz      loc_1800628D3
0x180062227  test    r14, r14
0x18006222a  jz      loc_1800628D3
0x180062230  test    r13d, 0FFFFFEBFh
0x180062237  jz      short loc_18006228A
0x180062239  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006223f  mov     edx, 80041008h
0x180062244  mov     rcx, rax
0x180062247  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006224d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062254  cmp     rcx, rdi
0x180062257  jz      short loc_180062280
0x180062259  test    byte ptr [rcx+1Ch], 1
0x18006225d  jz      short loc_180062280
0x18006225f  cmp     byte ptr [rcx+19h], 2
0x180062263  jb      short loc_180062280
0x180062265  mov     edx, 35h ; '5'
0x18006226a  mov     r9d, 80041008h
0x180062270  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x180062277  mov     rcx, [rcx+10h]
0x18006227b  call    WPP_SF_d
0x180062280  mov     eax, 80041008h
0x180062285  jmp     loc_180062926
0x18006228a  mov     r8d, 10h; Size
0x180062290  lea     rax, IID_IWbemServices
0x180062297  mov     rdx, rax; Buf2
0x18006229a  mov     rcx, rax; Buf1
0x18006229d  call    memcmp_0
0x1800622a2  test    eax, eax
0x1800622a4  jz      short loc_1800622F7
0x1800622a6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800622ac  mov     edx, 80041008h
0x1800622b1  mov     rcx, rax
0x1800622b4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800622ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800622c1  cmp     rcx, rdi
0x1800622c4  jz      short loc_1800622ED
0x1800622c6  test    byte ptr [rcx+1Ch], 1
0x1800622ca  jz      short loc_1800622ED
0x1800622cc  cmp     byte ptr [rcx+19h], 2
0x1800622d0  jb      short loc_1800622ED
0x1800622d2  mov     edx, 36h ; '6'
0x1800622d7  mov     r9d, 80041008h
0x1800622dd  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800622e4  mov     rcx, [rcx+10h]
0x1800622e8  call    WPP_SF_d
0x1800622ed  mov     eax, 80041008h
0x1800622f2  jmp     loc_180062926
0x1800622f7  mov     edx, cs:?g_PathLimit@@3KA; ulong g_PathLimit
0x1800622fd  add     edx, 0FFFFFFEDh
0x180062300  mov     rcx, r14
0x180062303  call    ?PreParsePath@@YA?AW4AcceptingState@@PEAGK@Z; PreParsePath(ushort *,ulong)
0x180062308  cmp     eax, 1
0x18006230b  jnz     short loc_18006235E
0x18006230d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180062313  mov     edx, 8004100Eh
0x180062318  mov     rcx, rax
0x18006231b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062321  mov     rcx, cs:WPP_GLOBAL_Control
0x180062328  cmp     rcx, rdi
0x18006232b  jz      short loc_180062354
0x18006232d  test    byte ptr [rcx+1Ch], 1
0x180062331  jz      short loc_180062354
0x180062333  cmp     byte ptr [rcx+19h], 2
0x180062337  jb      short loc_180062354
0x180062339  mov     edx, 37h ; '7'
0x18006233e  mov     r9d, 8004100Eh
0x180062344  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x18006234b  mov     rcx, [rcx+10h]
0x18006234f  call    WPP_SF_d
0x180062354  mov     eax, 8004100Eh
0x180062359  jmp     loc_180062926
0x18006235e  cmp     eax, 2
0x180062361  jnz     short loc_1800623B4
0x180062363  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180062369  mov     edx, 8004106Ch
0x18006236e  mov     rcx, rax
0x180062371  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062377  mov     rcx, cs:WPP_GLOBAL_Control
0x18006237e  cmp     rcx, rdi
0x180062381  jz      short loc_1800623AA
0x180062383  test    byte ptr [rcx+1Ch], 1
0x180062387  jz      short loc_1800623AA
0x180062389  cmp     byte ptr [rcx+19h], 2
0x18006238d  jb      short loc_1800623AA
0x18006238f  mov     edx, 38h ; '8'
0x180062394  mov     r9d, 8004106Ch
0x18006239a  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x1800623a1  mov     rcx, [rcx+10h]
0x1800623a5  call    WPP_SF_d
0x1800623aa  mov     eax, 8004106Ch
0x1800623af  jmp     loc_180062926
0x1800623b4  xor     ebx, ebx
0x1800623b6  mov     [r12], rbx
0x1800623ba  xor     ecx, ecx
0x1800623bc  call    cs:__imp_?ValidateMemSize@CWin32DefaultArena@@SAHH@Z; CWin32DefaultArena::ValidateMemSize(int)
0x1800623c2  test    eax, eax
0x1800623c4  jnz     loc_18006245E
0x1800623ca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800623d0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800623d7  mov     rcx, rax
0x1800623da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800623e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623e7  cmp     rcx, rdi
0x1800623ea  jz      short loc_18006240D
0x1800623ec  test    byte ptr [rcx+1Ch], 1
0x1800623f0  jz      short loc_18006240D
0x1800623f2  cmp     byte ptr [rcx+19h], 2
0x1800623f6  jb      short loc_18006240D
0x1800623f8  mov     edx, 39h ; '9'
0x1800623fd  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x180062404  mov     rcx, [rcx+10h]
0x180062408  call    WPP_SF_
0x18006240d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180062413  mov     edx, 80041006h
0x180062418  mov     rcx, rax
0x18006241b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062421  mov     rcx, cs:WPP_GLOBAL_Control
0x180062428  cmp     rcx, rdi
0x18006242b  jz      short loc_180062454
0x18006242d  test    byte ptr [rcx+1Ch], 1
0x180062431  jz      short loc_180062454
0x180062433  cmp     byte ptr [rcx+19h], 2
0x180062437  jb      short loc_180062454
0x180062439  mov     edx, 3Ah ; ':'
0x18006243e  mov     r9d, 80041006h
0x180062444  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x18006244b  mov     rcx, [rcx+10h]
0x18006244f  call    WPP_SF_d
0x180062454  mov     eax, 80041006h
0x180062459  jmp     loc_180062926
0x18006245e  mov     [rsp+0A8h+ppInterface], rbx
0x180062463  lea     rdx, [rsp+0A8h+ppInterface]; ppInterface
0x180062468  lea     rcx, IID_IServerSecurity; riid
0x18006246f  call    cs:__imp_CoGetCallContext
0x180062475  mov     esi, eax
0x180062477  mov     rbx, [rsp+0A8h+ppInterface]
0x18006247c  mov     [rsp+0A8h+var_40], rbx
0x180062481  cmp     eax, 80010117h
0x180062486  jnz     short loc_1800624EC
0x180062488  mov     [rsp+0A8h+var_68], 1; bool
0x18006248d  mov     [rsp+0A8h+var_70], r12; void **
0x180062492  lea     rax, IID_IWbemServices
0x180062499  mov     [rsp+0A8h+var_78], rax; struct _GUID *
0x18006249e  mov     [rsp+0A8h+var_80], 1; bool
0x1800624a3  mov     rax, [rsp+0A8h+arg_20]
0x1800624ab  mov     [rsp+0A8h+var_88], rax; struct IWbemContext *
0x1800624b0  mov     r9d, r13d; int
0x1800624b3  mov     r8, [rsp+0A8h+arg_10]; unsigned __int16 *
0x1800624bb  mov     rdx, r14; unsigned __int16 *
0x1800624be  mov     rcx, r15; this
0x1800624c1  call    ?LoginUser@CWbemLevel1Login@@AEAAJPEAG0JPEAUIWbemContext@@_NAEBU_GUID@@PEAPEAX2@Z; CWbemLevel1Login::LoginUser(ushort *,ushort *,long,IWbemContext *,bool,_GUID const &,void * *,bool)
0x1800624c6  mov     edi, eax
0x1800624c8  test    rbx, rbx
0x1800624cb  jz      short loc_1800624DC
0x1800624cd  mov     rdx, [rbx]
0x1800624d0  mov     rcx, rbx
0x1800624d3  mov     rax, [rdx+10h]
0x1800624d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624dc  mov     [rsp+0A8h+var_40], 0
0x1800624e5  mov     eax, edi
0x1800624e7  jmp     loc_180062926
0x1800624ec  test    esi, esi
0x1800624ee  jns     short loc_180062556
0x1800624f0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800624f6  mov     edx, esi
0x1800624f8  mov     rcx, rax
0x1800624fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062501  mov     rcx, cs:WPP_GLOBAL_Control
0x180062508  cmp     rcx, rdi
0x18006250b  jz      short loc_180062532
0x18006250d  test    byte ptr [rcx+1Ch], 1
0x180062511  jz      short loc_180062532
0x180062513  cmp     byte ptr [rcx+19h], 2
0x180062517  jb      short loc_180062532
0x180062519  mov     edx, 3Bh ; ';'
0x18006251e  mov     r9d, esi
0x180062521  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x180062528  mov     rcx, [rcx+10h]
0x18006252c  call    WPP_SF_d
0x180062531  nop
0x180062532  test    rbx, rbx
0x180062535  jz      short loc_180062546
0x180062537  mov     rax, [rbx]
0x18006253a  mov     rcx, rbx
0x18006253d  mov     rax, [rax+10h]
0x180062541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062546  mov     [rsp+0A8h+var_40], 0
0x18006254f  mov     eax, esi
0x180062551  jmp     loc_180062926
0x180062556  xor     esi, esi
0x180062558  mov     [rsp+0A8h+var_50], esi
0x18006255c  mov     [rsp+0A8h+var_54], esi
0x180062560  mov     dword ptr [rsp+0A8h+arg_28], esi
0x180062567  mov     [rsp+0A8h+var_58], esi
0x18006256b  mov     [rsp+0A8h+var_30], rsi
0x180062570  mov     rcx, [rsp+0A8h+ppInterface]
0x180062575  mov     rax, [rcx]
0x180062578  lea     rdx, [rsp+0A8h+var_58]
0x18006257d  mov     [rsp+0A8h+var_70], rdx
0x180062582  lea     rdx, [rsp+0A8h+var_30]
0x180062587  mov     [rsp+0A8h+var_78], rdx
0x18006258c  mov     qword ptr [rsp+0A8h+var_80], rsi
0x180062591  lea     rdx, [rsp+0A8h+arg_28]
0x180062599  mov     [rsp+0A8h+var_88], rdx
0x18006259e  xor     r9d, r9d
0x1800625a1  lea     r8, [rsp+0A8h+var_54]
0x1800625a6  lea     rdx, [rsp+0A8h+var_50]
0x1800625ab  mov     rax, [rax+18h]
0x1800625af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625b4  test    eax, eax
0x1800625b6  jns     loc_1800626CD
0x1800625bc  mov     rcx, [rsp+0A8h+ppInterface]
0x1800625c1  mov     rax, [rcx]
0x1800625c4  lea     rdx, [rsp+0A8h+var_58]
0x1800625c9  mov     [rsp+0A8h+var_70], rdx
0x1800625ce  mov     [rsp+0A8h+var_78], rsi
0x1800625d3  mov     qword ptr [rsp+0A8h+var_80], rsi
0x1800625d8  lea     rdx, [rsp+0A8h+arg_28]
0x1800625e0  mov     [rsp+0A8h+var_88], rdx
0x1800625e5  xor     r9d, r9d
0x1800625e8  lea     r8, [rsp+0A8h+var_54]
0x1800625ed  lea     rdx, [rsp+0A8h+var_50]
0x1800625f2  mov     rax, [rax+18h]
0x1800625f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625fb  mov     esi, eax
0x1800625fd  xor     r9d, r9d
0x180062600  mov     [rsp+0A8h+var_30], r9
0x180062605  test    eax, eax
0x180062607  jns     loc_1800626F6
0x18006260d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180062613  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18006261a  mov     rcx, rax
0x18006261d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180062623  mov     rcx, cs:WPP_GLOBAL_Control
0x18006262a  cmp     rcx, rdi
0x18006262d  jz      short loc_180062653
0x18006262f  test    byte ptr [rcx+1Ch], 1
0x180062633  jz      short loc_180062653
0x180062635  cmp     byte ptr [rcx+19h], 2
0x180062639  jb      short loc_180062653
0x18006263b  mov     edx, 3Ch ; '<'
0x180062640  mov     r9d, esi
0x180062643  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x18006264a  mov     rcx, [rcx+10h]
0x18006264e  call    WPP_SF_d
0x180062653  mov     ecx, 1388h; dwMilliseconds
  ... truncated ...
```
