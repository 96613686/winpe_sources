# CRepository::OpenEseNs(IWmiDbSession *,ushort const *,IWmiDbHandle * *)

- ea: `0x18002cca4`
- end: `0x18002d31d`
- name: `?OpenEseNs@CRepository@@SAJPEAUIWmiDbSession@@PEBGPEAPEAUIWmiDbHandle@@@Z`
- size: `1657`
- prototype: `__int64 __fastcall(struct IWmiDbSession *, const unsigned __int16 *, struct IWmiDbHandle **)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c010`
- `0x18006fa48`
- `0x18008ce28`
- `0x1800a4ddc`
- `0x1800a7250`

## callees

- `0x18000aed8`
- `0x18000b140`
- `0x18002c9f0`
- `0x18002ca8c`
- `0x18002cca4`
- `0x18003cfe0`
- `0x180060ab0`
- `0x180088038`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002cd30`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002cd30`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002cfe6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d0bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002cfe6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002d0bb`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18002cf12`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18002cf12`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18002cecc`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18002cecc`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x18002cedf`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x18002cedf`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002cfa3`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d040`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d091`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d2f5`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002cfa3`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d040`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d091`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002d2f5`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002ceed`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002ceff`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002ceed`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002ceff`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002ce63`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002ce63`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18002ce91`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18002ce91`
- `wbemcomn!GetMemLogObject` at `0x18002cd63`
- `wbemcomn!GetMemLogObject` at `0x18002d00b`
- `wbemcomn!GetMemLogObject` at `0x18002d063`
- `wbemcomn!GetMemLogObject` at `0x18002d112`
- `wbemcomn!GetMemLogObject` at `0x18002d17e`
- `wbemcomn!GetMemLogObject` at `0x18002d218`
- `wbemcomn!GetMemLogObject` at `0x18002d275`
- `wbemcomn!GetMemLogObject` at `0x18002cd63`
- `wbemcomn!GetMemLogObject` at `0x18002d00b`
- `wbemcomn!GetMemLogObject` at `0x18002d063`
- `wbemcomn!GetMemLogObject` at `0x18002d112`
- `wbemcomn!GetMemLogObject` at `0x18002d17e`
- `wbemcomn!GetMemLogObject` at `0x18002d218`
- `wbemcomn!GetMemLogObject` at `0x18002d275`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd6e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d01c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d06f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d122`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d18e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d228`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d285`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd6e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d01c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d06f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d122`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d18e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d228`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d285`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRepository::OpenEseNs(
        struct IWmiDbSession *a1,
        const unsigned __int16 *a2,
        struct IWmiDbHandle **a3)
{
  const unsigned __int16 *v4; // rbx
  struct IWmiDbSession *v5; // r12
  __int64 v6; // rsi
  unsigned __int64 v7; // rsi
  wchar_t *v8; // rax
  wchar_t **v9; // r8
  wchar_t *v10; // r14
  unsigned int v11; // ebx
  CMemoryLog *v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // rdx
  unsigned __int16 v15; // cx
  wchar_t *v16; // rcx
  wchar_t *v17; // rbx
  struct IWmiDbHandle *v18; // r15
  struct IWbemPath *NewPath; // rax
  struct IWbemPath *v20; // rsi
  HRESULT (__stdcall *SetText)(IWbemPath *, ULONG, LPCWSTR); // rbx
  __int64 v22; // rax
  int v23; // r13d
  wchar_t **v24; // r8
  CMemoryLog *v26; // rax
  unsigned int v27; // ebx
  CMemoryLog *v28; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CClientCnt *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  struct IWmiDbHandle *v40; // [rsp+40h] [rbp-78h] BYREF
  char v41[8]; // [rsp+48h] [rbp-70h] BYREF
  void *v42[2]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v43[48]; // [rsp+60h] [rbp-58h] BYREF
  struct IWbemPath *v45; // [rsp+D8h] [rbp+20h] BYREF

  v4 = a2;
  v5 = a1;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
  }
  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    v27 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v27;
    }
    v31 = 36;
    v32 = 2147749896LL;
    goto LABEL_55;
  }
  if ( !v5 )
    v5 = CRepository::m_pEseSession;
  *a3 = 0;
  if ( !v4 )
  {
    if ( CRepository::m_pEseRoot )
    {
      *a3 = (struct IWmiDbHandle *)GetAddRef<IWmiDbHandle>();
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 0);
      }
      return 0;
    }
    v33 = GetMemLogObject();
    v27 = -2147217398;
    CMemoryLog::Write(v33, -2147217398);
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v27;
    }
    v31 = 37;
    v32 = 2147749898LL;
LABEL_55:
    WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v32);
    return v27;
  }
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = v6 + 1;
  v8 = (wchar_t *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v7, 2u));
  v10 = v8;
  v42[0] = v8;
  v42[1] = 0;
  if ( !v8 )
  {
    v26 = GetMemLogObject();
    v27 = -2147217402;
    CMemoryLog::Write(v26, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
    }
    return v27;
  }
  if ( !v7 )
  {
    v11 = -2147024809;
LABEL_11:
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v11);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v11);
    }
    goto LABEL_26;
  }
  if ( v7 > 0x7FFFFFFF )
  {
    v11 = -2147024809;
    *v8 = 0;
    goto LABEL_11;
  }
  v13 = 2147483646;
  v14 = v10;
  do
  {
    if ( !v13 )
      break;
    v15 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v14++ = v15;
    --v13;
    --v7;
  }
  while ( v7 );
  v11 = v7 == 0 ? 0x8007007A : 0;
  v16 = v14 - 1;
  if ( v7 )
    v16 = v14;
  *v16 = 0;
  if ( !v7 )
    goto LABEL_11;
LABEL_26:
  v17 = wcstok_mvcrt_legacy_two_parameter_form(v10, L"\\", v9);
  CInCritSec::CInCritSec((CInCritSec *)v41, (struct _RTL_CRITICAL_SECTION *)g_globCS);
  v18 = CRepository::m_pEseRoot;
  if ( CRepository::m_pEseRoot )
  {
    (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)CRepository::m_pEseRoot + 8LL))(CRepository::m_pEseRoot);
    v18 = CRepository::m_pEseRoot;
  }
  CInCritSec::~CInCritSec((CInCritSec *)v41);
  v40 = 0;
  if ( !v18 )
  {
    v34 = GetMemLogObject();
    v27 = -2147217398;
    CMemoryLog::Write(v34, -2147217398);
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control )
      goto LABEL_80;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_80;
    v36 = 41;
    v37 = 2147749898LL;
LABEL_76:
    WPP_SF_d(*((_QWORD *)v35 + 2), v36, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, v37);
    goto LABEL_80;
  }
  while ( 1 )
  {
    if ( !v17 )
      goto LABEL_35;
    NewPath = ConfigMgr::GetNewPath();
    v20 = NewPath;
    if ( !NewPath )
    {
      (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v18 + 16LL))(v18);
      v38 = GetMemLogObject();
      v27 = -2147217402;
      CMemoryLog::Write(v38, -2147217402);
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control )
        goto LABEL_80;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_80;
      v36 = 42;
      v37 = 2147749894LL;
      goto LABEL_76;
    }
    v45 = NewPath;
    WString2::WString2((WString2 *)v43);
    try
    {
      WString2::operator=(v43, L"__namespace='");
      WString2::operator+=(v43, v17);
      WString2::operator+=(v43, L"'");
    }
    catch ( CX_MemoryException )
    {
      v39 = GetMemLogObject();
      CMemoryLog::Write(v39, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
      }
      WString2::~WString2((WString2 *)v43);
      CReleaseMe::release((CReleaseMe *)&v45);
      v27 = -2147217402;
LABEL_80:
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v42);
      return v27;
    }
    SetText = v20->lpVtbl->SetText;
    v22 = WString2::operator unsigned short *(v43);
    ((void (__fastcall *)(struct IWbemPath *, __int64, __int64))SetText)(v20, 12, v22);
    v23 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, struct IWmiDbHandle *, struct IWbemPath *, _QWORD, int, struct IWmiDbHandle **))(*(_QWORD *)v5 + 24LL))(
            v5,
            v18,
            v20,
            0,
            1,
            &v40);
    v17 = wcstok_mvcrt_legacy_two_parameter_form(0, L"\\", v24);
    (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v23 < 0 )
      break;
    if ( !v17 )
    {
      *a3 = v40;
      WString2::~WString2((WString2 *)v43);
      ((void (__fastcall *)(struct IWbemPath *))v20->lpVtbl->Release)(v20);
      v45 = 0;
LABEL_35:
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 0);
      }
      if ( v10 )
        CWin32DefaultArena::WbemMemFree(v10);
      return 0;
    }
    v18 = v40;
    WString2::~WString2((WString2 *)v43);
    ((void (__fastcall *)(struct IWbemPath *))v20->lpVtbl->Release)(v20);
    v45 = 0;
  }
  v28 = GetMemLogObject();
  CMemoryLog::Write(v28, v23);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (unsigned int)v23);
  }
  WString2::~WString2((WString2 *)v43);
  ((void (__fastcall *)(struct IWbemPath *))v20->lpVtbl->Release)(v20);
  v45 = 0;
  if ( v10 )
    CWin32DefaultArena::WbemMemFree(v10);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18002cca4  mov     [rsp+arg_0], rbx
0x18002cca9  mov     [rsp+arg_8], rsi
0x18002ccae  mov     [rsp+arg_10], r8
0x18002ccb3  push    rdi
0x18002ccb4  push    r12
0x18002ccb6  push    r13
0x18002ccb8  push    r14
0x18002ccba  push    r15
0x18002ccbc  sub     rsp, 90h
0x18002ccc3  mov     rsi, r8
0x18002ccc6  mov     rbx, rdx
0x18002ccc9  mov     r12, rcx
0x18002cccc  lea     r15, WPP_GLOBAL_Control
0x18002ccd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccda  cmp     rcx, r15
0x18002ccdd  jnz     loc_18002CDB1
0x18002cce3  lea     rdi, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18002ccea  xor     r13d, r13d
0x18002cced  test    rsi, rsi
0x18002ccf0  jz      loc_18002D112
0x18002ccf6  test    r12, r12
0x18002ccf9  cmovz   r12, cs:?m_pEseSession@CRepository@@0PEAUIWmiDbSession@@EA; IWmiDbSession * CRepository::m_pEseSession
0x18002cd01  mov     [rsi], r13
0x18002cd04  test    rbx, rbx
0x18002cd07  jz      loc_18002D175
0x18002cd0d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002cd11  mov     rsi, rcx
0x18002cd14  inc     rsi
0x18002cd17  cmp     [rbx+rsi*2], r13w
0x18002cd1c  jnz     short loc_18002CD14
0x18002cd1e  inc     rsi
0x18002cd21  mov     eax, 2
0x18002cd26  mul     rsi
0x18002cd29  cmovb   rax, rcx
0x18002cd2d  mov     rcx, rax
0x18002cd30  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002cd36  mov     r14, rax
0x18002cd39  mov     [rsp+0B8h+var_68], rax
0x18002cd3e  mov     [rsp+0B8h+var_60], r13
0x18002cd43  test    rax, rax
0x18002cd46  jz      loc_18002D00B
0x18002cd4c  test    rsi, rsi
0x18002cd4f  jnz     loc_18002CDEA
0x18002cd55  mov     ebx, 80070057h
0x18002cd5a  test    rsi, rsi
0x18002cd5d  jz      short loc_18002CD63
0x18002cd5f  mov     [rax], r13w
0x18002cd63  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cd69  mov     edx, ebx
0x18002cd6b  mov     rcx, rax
0x18002cd6e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cd74  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd7b  cmp     rcx, r15
0x18002cd7e  jz      loc_18002CE45
0x18002cd84  test    byte ptr [rcx+1Ch], 1
0x18002cd88  jz      loc_18002CE45
0x18002cd8e  cmp     byte ptr [rcx+19h], 2
0x18002cd92  jb      loc_18002CE45
0x18002cd98  mov     edx, 28h ; '('
0x18002cd9d  mov     r9d, ebx
0x18002cda0  mov     r8, rdi
0x18002cda3  mov     rcx, [rcx+10h]
0x18002cda7  call    WPP_SF_d
0x18002cdac  jmp     loc_18002CE45
0x18002cdb1  test    byte ptr [rcx+1Ch], 1
0x18002cdb5  jz      loc_18002CCE3
0x18002cdbb  cmp     byte ptr [rcx+19h], 5
0x18002cdbf  jb      loc_18002CCE3
0x18002cdc5  mov     edx, 23h ; '#'
0x18002cdca  mov     [rsp+0B8h+var_98], rbx
0x18002cdcf  mov     r9, r12
0x18002cdd2  lea     rdi, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18002cdd9  mov     r8, rdi
0x18002cddc  mov     rcx, [rcx+10h]
0x18002cde0  call    WPP_SF_qS
0x18002cde5  jmp     loc_18002CCEA
0x18002cdea  cmp     rsi, 7FFFFFFFh
0x18002cdf1  ja      loc_18002D20E
0x18002cdf7  mov     eax, 7FFFFFFEh
0x18002cdfc  mov     rdx, r14
0x18002cdff  test    rax, rax
0x18002ce02  jz      short loc_18002CE20
0x18002ce04  movzx   ecx, word ptr [rbx]
0x18002ce07  test    cx, cx
0x18002ce0a  jz      short loc_18002CE20
0x18002ce0c  add     rbx, 2
0x18002ce10  mov     [rdx], cx
0x18002ce13  add     rdx, 2
0x18002ce17  dec     rax
0x18002ce1a  sub     rsi, 1
0x18002ce1e  jnz     short loc_18002CDFF
0x18002ce20  mov     rax, rsi
0x18002ce23  neg     rax
0x18002ce26  sbb     ebx, ebx
0x18002ce28  not     ebx
0x18002ce2a  and     ebx, 8007007Ah
0x18002ce30  lea     rcx, [rdx-2]
0x18002ce34  test    rsi, rsi
0x18002ce37  cmovnz  rcx, rdx
0x18002ce3b  mov     [rcx], r13w
0x18002ce3f  jz      loc_18002CD63
0x18002ce45  lea     rdx, Delimiter; "\\"
0x18002ce4c  mov     rcx, r14; String
0x18002ce4f  call    wcstok_mvcrt_legacy_two_parameter_form
0x18002ce54  mov     rbx, rax
0x18002ce57  lea     rdx, ?g_globCS@@3VCStaticCritSec@@A; CStaticCritSec g_globCS
0x18002ce5e  lea     rcx, [rsp+0B8h+var_70]
0x18002ce63  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18002ce69  nop
0x18002ce6a  mov     r15, cs:?m_pEseRoot@CRepository@@0PEAUIWmiDbHandle@@EA; IWmiDbHandle * CRepository::m_pEseRoot
0x18002ce71  test    r15, r15
0x18002ce74  jz      short loc_18002CE8C
0x18002ce76  mov     rax, [r15]
0x18002ce79  mov     rcx, r15
0x18002ce7c  mov     rax, [rax+8]
0x18002ce80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce85  mov     r15, cs:?m_pEseRoot@CRepository@@0PEAUIWmiDbHandle@@EA; IWmiDbHandle * CRepository::m_pEseRoot
0x18002ce8c  lea     rcx, [rsp+0B8h+var_70]
0x18002ce91  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18002ce97  mov     [rsp+0B8h+var_78], r13
0x18002ce9c  test    r15, r15
0x18002ce9f  jz      loc_18002D218
0x18002cea5  test    rbx, rbx
0x18002cea8  jz      loc_18002CFC1
0x18002ceae  call    ?GetNewPath@ConfigMgr@@SAPEAUIWbemPath@@XZ; ConfigMgr::GetNewPath(void)
0x18002ceb3  mov     rsi, rax
0x18002ceb6  test    rax, rax
0x18002ceb9  jz      loc_18002D266
0x18002cebf  mov     [rsp+0B8h+arg_18], rax
0x18002cec7  lea     rcx, [rsp+0B8h+var_58]
0x18002cecc  call    cs:__imp_??0WString2@@QEAA@XZ; WString2::WString2(void)
0x18002ced2  nop
0x18002ced3  lea     rdx, aNamespace_3; "__namespace='"
0x18002ceda  lea     rcx, [rsp+0B8h+var_58]
0x18002cedf  call    cs:__imp_??4WString2@@QEAAAEAV0@PEBG@Z; WString2::operator=(ushort const *)
0x18002cee5  mov     rdx, rbx
0x18002cee8  lea     rcx, [rsp+0B8h+var_58]
0x18002ceed  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002cef3  lea     rdx, asc_1800EB884; "'"
0x18002cefa  lea     rcx, [rsp+0B8h+var_58]
0x18002ceff  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002cf05  nop
0x18002cf06  mov     rax, [rsi]
0x18002cf09  mov     rbx, [rax+18h]
0x18002cf0d  lea     rcx, [rsp+0B8h+var_58]
0x18002cf12  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x18002cf18  mov     r8, rax
0x18002cf1b  mov     edx, 0Ch
0x18002cf20  mov     rcx, rsi
0x18002cf23  mov     rax, rbx
0x18002cf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf2b  mov     rax, [r12]
0x18002cf2f  lea     rcx, [rsp+0B8h+var_78]
0x18002cf34  mov     [rsp+0B8h+var_90], rcx
0x18002cf39  mov     dword ptr [rsp+0B8h+var_98], 1
0x18002cf41  xor     r9d, r9d
0x18002cf44  mov     r8, rsi
0x18002cf47  mov     rdx, r15
0x18002cf4a  mov     rcx, r12
0x18002cf4d  mov     rax, [rax+18h]
0x18002cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf56  mov     r13d, eax
0x18002cf59  lea     rdx, Delimiter; "\\"
0x18002cf60  xor     ecx, ecx; String
0x18002cf62  call    wcstok_mvcrt_legacy_two_parameter_form
0x18002cf67  mov     rbx, rax
0x18002cf6a  mov     rcx, [r15]
0x18002cf6d  mov     rax, [rcx+10h]
0x18002cf71  mov     rcx, r15
0x18002cf74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf79  test    r13d, r13d
0x18002cf7c  js      loc_18002D063
0x18002cf82  xor     r13d, r13d
0x18002cf85  test    rbx, rbx
0x18002cf88  jnz     loc_18002D036
0x18002cf8e  mov     rax, [rsp+0B8h+var_78]
0x18002cf93  mov     rcx, [rsp+0B8h+arg_10]
0x18002cf9b  mov     [rcx], rax
0x18002cf9e  lea     rcx, [rsp+0B8h+var_58]
0x18002cfa3  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18002cfa9  nop
0x18002cfaa  mov     rax, [rsi]
0x18002cfad  mov     rcx, rsi
0x18002cfb0  mov     rax, [rax+10h]
0x18002cfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfb9  mov     [rsp+0B8h+arg_18], r13
0x18002cfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfc8  lea     rax, WPP_GLOBAL_Control
0x18002cfcf  cmp     rcx, rax
0x18002cfd2  jz      short loc_18002CFDE
0x18002cfd4  test    byte ptr [rcx+1Ch], 1
0x18002cfd8  jnz     loc_18002D0C9
0x18002cfde  test    r14, r14
0x18002cfe1  jz      short loc_18002CFEC
0x18002cfe3  mov     rcx, r14
0x18002cfe6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002cfec  xor     eax, eax
0x18002cfee  lea     r11, [rsp+0B8h+var_28]
0x18002cff6  mov     rbx, [r11+30h]
0x18002cffa  mov     rsi, [r11+38h]
0x18002cffe  mov     rsp, r11
0x18002d001  pop     r15
0x18002d003  pop     r14
0x18002d005  pop     r13
0x18002d007  pop     r12
0x18002d009  pop     rdi
0x18002d00a  retn
0x18002d00b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d011  nop
0x18002d012  mov     ebx, 80041006h
0x18002d017  mov     edx, ebx
0x18002d019  mov     rcx, rax
0x18002d01c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d022  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d029  cmp     rcx, r15
0x18002d02c  jnz     loc_18002D1FF
0x18002d032  mov     eax, ebx
0x18002d034  jmp     short loc_18002CFEE
0x18002d036  mov     r15, [rsp+0B8h+var_78]
0x18002d03b  lea     rcx, [rsp+0B8h+var_58]
0x18002d040  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18002d046  nop
0x18002d047  mov     rax, [rsi]
0x18002d04a  mov     rcx, rsi
0x18002d04d  mov     rax, [rax+10h]
0x18002d051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d056  mov     [rsp+0B8h+arg_18], r13
0x18002d05e  jmp     loc_18002CEA5
0x18002d063  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d069  mov     edx, r13d
0x18002d06c  mov     rcx, rax
0x18002d06f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d075  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d07c  lea     rax, WPP_GLOBAL_Control
0x18002d083  cmp     rcx, rax
0x18002d086  jnz     loc_18002D2C3
0x18002d08c  lea     rcx, [rsp+0B8h+var_58]
0x18002d091  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18002d097  nop
0x18002d098  mov     rax, [rsi]
0x18002d09b  mov     rcx, rsi
0x18002d09e  mov     rax, [rax+10h]
0x18002d0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0a7  mov     [rsp+0B8h+arg_18], 0
0x18002d0b3  test    r14, r14
0x18002d0b6  jz      short loc_18002D0C1
0x18002d0b8  mov     rcx, r14
0x18002d0bb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002d0c1  mov     eax, r13d
0x18002d0c4  jmp     loc_18002CFEE
0x18002d0c9  cmp     byte ptr [rcx+19h], 2
0x18002d0cd  jb      loc_18002CFDE
0x18002d0d3  mov     edx, 2Dh ; '-'
0x18002d0d8  xor     r9d, r9d
0x18002d0db  mov     r8, rdi
0x18002d0de  mov     rcx, [rcx+10h]
0x18002d0e2  call    WPP_SF_d
0x18002d0e7  jmp     loc_18002CFDE
0x18002d0ec  cmp     byte ptr [rcx+19h], 2
0x18002d0f0  jb      loc_18002D032
0x18002d0f6  mov     edx, 27h ; '''
0x18002d0fb  mov     r9d, 80041006h
0x18002d101  mov     r8, rdi
0x18002d104  mov     rcx, [rcx+10h]
0x18002d108  call    WPP_SF_d
0x18002d10d  jmp     loc_18002D032
0x18002d112  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d118  mov     ebx, 80041008h
0x18002d11d  mov     edx, ebx
0x18002d11f  mov     rcx, rax
0x18002d122  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d128  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d12f  cmp     rcx, r15
0x18002d132  jz      loc_18002D032
0x18002d138  test    byte ptr [rcx+1Ch], 1
0x18002d13c  jz      loc_18002D032
0x18002d142  cmp     byte ptr [rcx+19h], 2
0x18002d146  jb      loc_18002D032
0x18002d14c  mov     edx, 24h ; '$'
0x18002d151  mov     r9d, 80041008h
0x18002d157  jmp     short loc_18002D164
0x18002d159  mov     edx, 25h ; '%'
0x18002d15e  mov     r9d, 8004100Ah
0x18002d164  mov     r8, rdi
0x18002d167  mov     rcx, [rcx+10h]
0x18002d16b  call    WPP_SF_d
0x18002d170  jmp     loc_18002D032
0x18002d175  cmp     cs:?m_pEseRoot@CRepository@@0PEAUIWmiDbHandle@@EA, r13; IWmiDbHandle * CRepository::m_pEseRoot
0x18002d17c  jnz     short loc_18002D1BA
0x18002d17e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002d184  mov     ebx, 8004100Ah
0x18002d189  mov     edx, ebx
0x18002d18b  mov     rcx, rax
0x18002d18e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002d194  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d19b  cmp     rcx, r15
0x18002d19e  jz      loc_18002D032
0x18002d1a4  test    byte ptr [rcx+1Ch], 1
0x18002d1a8  jz      loc_18002D032
0x18002d1ae  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
