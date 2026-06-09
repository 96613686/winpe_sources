# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x180008240`
- end: `0x1800086ae`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `1134`
- prototype: `__int64 __fastcall(struct User *this, PSID pSourceSid, enum _SID_NAME_USE)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800089e0`

## callees

- `0x180007e90`
- `0x180008240`
- `0x180009070`
- `0x180009150`
- `0x1800091d8`
- `0x180009248`
- `0x180009280`
- `0x18000a020`
- `0x18000a148`
- `0x18000a1d0`
- `0x18003e88c`
- `0x18005224c`
- `0x180052284`

## import_xrefs

- `msvcrt!malloc` at `0x18000833e`
- `msvcrt!malloc` at `0x18000833e`
- `msvcrt!free` at `0x1800083b2`
- `msvcrt!free` at `0x1800083b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000843b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000848d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008507`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800082ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000843b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000848d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008507`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008452`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008624`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800082dc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800082dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800083d3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800083d3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008391`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008391`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall User::FromSid(struct User *this, PSID pSourceSid, enum _SID_NAME_USE a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  User::UserEntry *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  _QWORD **v8; // r12
  _QWORD *v9; // r14
  void *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // r14
  DWORD LengthSid; // esi
  void *v14; // rbx
  void *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  _QWORD **v17; // rsi
  unsigned __int64 v18; // rax
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  unsigned int updated; // ebx
  __int64 v22; // r12
  DWORD LastError; // ebx
  __int64 v24; // r8
  bool v25; // [rsp+30h] [rbp-59h]
  void **pExceptionObject; // [rsp+40h] [rbp-49h] BYREF
  char v27; // [rsp+48h] [rbp-41h]
  __int64 *v28; // [rsp+50h] [rbp-39h]
  __int64 v29; // [rsp+58h] [rbp-31h]
  __int64 v30; // [rsp+60h] [rbp-29h]
  int v31; // [rsp+68h] [rbp-21h]
  __int64 v32; // [rsp+6Ch] [rbp-1Dh]
  _QWORD *v33; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v34[12]; // [rsp+80h] [rbp-9h] BYREF
  User::UserEntry *v35; // [rsp+F8h] [rbp+6Fh] BYREF
  enum _SID_NAME_USE v36; // [rsp+100h] [rbp+77h]
  _QWORD *v37; // [rsp+108h] [rbp+7Fh] BYREF

  v36 = a3;
  LODWORD(v35) = 0;
  if ( !pSourceSid )
    return 2147942487LL;
  v5 = User::s_cs;
  v34[1] = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v6 = 0;
  v35 = 0;
  v7 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v8 = (_QWORD **)User::s_userTable;
  v9 = *(_QWORD **)User::s_userTable;
  if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
  {
    while ( v9 != v8[1] )
    {
      v10 = *(void **)(*v9 + 32LL);
      if ( v10 && EqualSid(v10, pSourceSid) )
      {
        wmi::AutoRef<User::UserEntry>::operator=(&v35, *v9);
        v6 = v35;
        break;
      }
      ++v9;
    }
  }
  LeaveCriticalSection(v7);
  if ( v6 )
  {
    User::UserEntry::AddRef(v6);
    User::~User(this);
    *(_QWORD *)this = v6;
    User::UserEntry::Release(v6);
  }
  else
  {
    User::~User(this);
    *(_QWORD *)this = 0;
  }
  if ( *(_QWORD *)this )
  {
    v34[0] = 0;
    v37 = 0;
    v35 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v35,
      (const struct _bstr_t *)&v37,
      (const struct _bstr_t *)v34,
      v36,
      0,
      v25);
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v37);
    _bstr_t::_Free((_bstr_t *)v34);
    LeaveCriticalSection(v5);
    return 0;
  }
  else
  {
    v11 = malloc(0x30u);
    v12 = v11;
    if ( !v11 )
    {
      v27 = 0;
      v28 = &qword_18007B2F0;
      v29 = 0;
      v30 = 0;
      v31 = 14;
      v32 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v37 = v11;
    v34[0] = 0;
    v34[2] = 0;
    v34[3] = 0;
    LODWORD(v35) = 7;
    *(_BYTE *)v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    *((_DWORD *)v11 + 10) = v36;
    *((_DWORD *)v11 + 11) = 0;
    LengthSid = GetLengthSid(pSourceSid);
    v14 = operator new(LengthSid);
    v15 = (void *)v12[4];
    if ( v15 )
      free(v15);
    v12[4] = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
      }
      v27 = 0;
      v28 = &qword_18007B2F0;
      v29 = 0;
      v30 = 0;
      v31 = 14;
      v32 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( !CopySid(LengthSid, v14, pSourceSid) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v24, LastError);
      }
      v27 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v28 = &qword_18007B2F0;
      v29 = 0;
      v30 = 0;
      v31 = LastError;
      v32 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v16 = User::s_cs;
    v34[4] = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v17 = (_QWORD **)User::s_userTable;
    v33 = v12;
    v18 = *((_QWORD *)User::s_userTable + 1);
    if ( (unsigned __int64)&v33 >= v18 || *(_QWORD *)User::s_userTable > (unsigned __int64)&v33 )
    {
      if ( v18 == *((_QWORD *)User::s_userTable + 2) )
        std::vector<User::UserEntry *>::_Reserve(User::s_userTable);
      *v17[1] = v12;
    }
    else
    {
      v22 = ((__int64)&v34[-1] - *(_QWORD *)User::s_userTable) >> 3;
      if ( v18 == *((_QWORD *)User::s_userTable + 2) )
        std::vector<User::UserEntry *>::_Reserve(User::s_userTable);
      *v17[1] = (*v17)[v22];
    }
    ++v17[1];
    LeaveCriticalSection(v16);
    v19 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    ++*((_DWORD *)v12 + 11);
    LeaveCriticalSection(v19);
    if ( *(_QWORD *)this )
      User::UserEntry::Release(*(User::UserEntry **)this);
    *(_QWORD *)this = v12;
    updated = User::UpdateEntry(this);
    LeaveCriticalSection(v5);
    return updated;
  }
}

```

## disassembly

```asm
0x180008240  mov     [rsp-8+arg_0], rbx
0x180008245  mov     [rsp-8+arg_10], r8d
0x18000824a  push    rbp
0x18000824b  push    rsi
0x18000824c  push    rdi
0x18000824d  push    r12
0x18000824f  push    r13
0x180008251  push    r14
0x180008253  push    r15
0x180008255  lea     rbp, [rsp-27h]
0x18000825a  sub     rsp, 0B0h
0x180008261  mov     r13, rdx
0x180008264  mov     r15, rcx
0x180008267  mov     dword ptr [rbp+57h+arg_8], 0
0x18000826e  test    rdx, rdx
0x180008271  jz      loc_180008566
0x180008277  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000827e  mov     [rbp+57h+var_58], rdi
0x180008282  mov     rcx, rdi; lpCriticalSection
0x180008285  call    cs:__imp_EnterCriticalSection
0x18000828c  nop     dword ptr [rax+rax+00h]
0x180008291  nop
0x180008292  xor     ebx, ebx
0x180008294  mov     [rbp+57h+arg_8], rbx
0x180008298  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000829f  mov     rcx, rsi; lpCriticalSection
0x1800082a2  call    cs:__imp_EnterCriticalSection
0x1800082a9  nop     dword ptr [rax+rax+00h]
0x1800082ae  mov     r12, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x1800082b5  mov     r14, [r12]
0x1800082b9  cmp     r14, [r12+8]
0x1800082be  jz      short loc_1800082FC
0x1800082c0  cmp     r14, [r12+8]
0x1800082c5  jz      short loc_1800082FC
0x1800082c7  mov     rax, [r14]
0x1800082ca  mov     rcx, [rax+20h]; pSid1
0x1800082ce  test    rcx, rcx
0x1800082d1  jnz     short loc_1800082D9
0x1800082d3  add     r14, 8
0x1800082d7  jmp     short loc_1800082C0
0x1800082d9  mov     rdx, r13; pSid2
0x1800082dc  call    cs:__imp_EqualSid
0x1800082e3  nop     dword ptr [rax+rax+00h]
0x1800082e8  test    eax, eax
0x1800082ea  jz      short loc_1800082D3
0x1800082ec  mov     rdx, [r14]
0x1800082ef  lea     rcx, [rbp+57h+arg_8]
0x1800082f3  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800082f8  mov     rbx, [rbp+57h+arg_8]
0x1800082fc  mov     rcx, rsi; lpCriticalSection
0x1800082ff  call    cs:__imp_LeaveCriticalSection
0x180008306  nop     dword ptr [rax+rax+00h]
0x18000830b  test    rbx, rbx
0x18000830e  jz      loc_180008556
0x180008314  mov     rcx, rbx; this
0x180008317  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18000831c  mov     rcx, r15; this
0x18000831f  call    ??1User@@QEAA@XZ; User::~User(void)
0x180008324  mov     [r15], rbx
0x180008327  mov     rcx, rbx; this
0x18000832a  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x18000832f  cmp     qword ptr [r15], 0
0x180008333  jnz     loc_1800084B7
0x180008339  mov     ecx, 30h ; '0'; Size
0x18000833e  call    cs:__imp_malloc
0x180008345  nop     dword ptr [rax+rax+00h]
0x18000834a  mov     r14, rax
0x18000834d  test    rax, rax
0x180008350  jz      loc_180008570
0x180008356  mov     [rbp+57h+arg_18], rax
0x18000835a  xor     r12d, r12d
0x18000835d  mov     [rbp+57h+var_60], r12
0x180008361  mov     [rbp+57h+var_50], r12
0x180008365  mov     [rbp+57h+var_48], r12
0x180008369  mov     dword ptr [rbp+57h+arg_8], 7
0x180008370  mov     [rax], r12b
0x180008373  mov     [rax+8], r12
0x180008377  mov     [rax+10h], r12
0x18000837b  mov     [rax+18h], r12
0x18000837f  mov     [rax+20h], r12
0x180008383  mov     eax, [rbp+57h+arg_10]
0x180008386  mov     [r14+28h], eax
0x18000838a  mov     [r14+2Ch], r12d
0x18000838e  mov     rcx, r13; pSid
0x180008391  call    cs:__imp_GetLengthSid
0x180008398  nop     dword ptr [rax+rax+00h]
0x18000839d  mov     esi, eax
0x18000839f  mov     ecx, eax; unsigned __int64
0x1800083a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083a6  mov     rbx, rax
0x1800083a9  mov     rcx, [r14+20h]; Block
0x1800083ad  test    rcx, rcx
0x1800083b0  jz      short loc_1800083BE
0x1800083b2  call    cs:__imp_free
0x1800083b9  nop     dword ptr [rax+rax+00h]
0x1800083be  mov     [r14+20h], rbx
0x1800083c2  test    rbx, rbx
0x1800083c5  jz      loc_1800085B5
0x1800083cb  mov     r8, r13; pSourceSid
0x1800083ce  mov     rdx, rbx; pDestinationSid
0x1800083d1  mov     ecx, esi; nDestinationSidLength
0x1800083d3  call    cs:__imp_CopySid
0x1800083da  nop     dword ptr [rax+rax+00h]
0x1800083df  test    eax, eax
0x1800083e1  jz      loc_180008624
0x1800083e7  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x1800083ee  mov     [rbp+57h+var_40], rbx
0x1800083f2  mov     rcx, rbx; lpCriticalSection
0x1800083f5  call    cs:__imp_EnterCriticalSection
0x1800083fc  nop     dword ptr [rax+rax+00h]
0x180008401  nop
0x180008402  mov     rsi, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180008409  mov     [rbp+57h+var_68], r14
0x18000840d  mov     rax, [rsi+8]
0x180008411  lea     rcx, [rbp+57h+var_68]
0x180008415  cmp     rcx, rax
0x180008418  jb      loc_180008517
0x18000841e  cmp     rax, [rsi+10h]
0x180008422  jnz     short loc_18000842C
0x180008424  mov     rcx, rsi
0x180008427  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x18000842c  mov     rax, [rsi+8]
0x180008430  mov     [rax], r14
0x180008433  add     qword ptr [rsi+8], 8
0x180008438  mov     rcx, rbx; lpCriticalSection
0x18000843b  call    cs:__imp_LeaveCriticalSection
0x180008442  nop     dword ptr [rax+rax+00h]
0x180008447  nop
0x180008448  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000844f  mov     rcx, rbx; lpCriticalSection
0x180008452  call    cs:__imp_EnterCriticalSection
0x180008459  nop     dword ptr [rax+rax+00h]
0x18000845e  inc     dword ptr [r14+2Ch]
0x180008462  mov     rcx, rbx; lpCriticalSection
0x180008465  call    cs:__imp_LeaveCriticalSection
0x18000846c  nop     dword ptr [rax+rax+00h]
0x180008471  mov     rcx, [r15]; this
0x180008474  test    rcx, rcx
0x180008477  jnz     loc_18000854C
0x18000847d  mov     [r15], r14
0x180008480  mov     rcx, r15; this
0x180008483  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180008488  mov     ebx, eax
0x18000848a  mov     rcx, rdi; lpCriticalSection
0x18000848d  call    cs:__imp_LeaveCriticalSection
0x180008494  nop     dword ptr [rax+rax+00h]
0x180008499  mov     eax, ebx
0x18000849b  mov     rbx, [rsp+0E0h+arg_0]
0x1800084a3  add     rsp, 0B0h
0x1800084aa  pop     r15
0x1800084ac  pop     r14
0x1800084ae  pop     r13
0x1800084b0  pop     r12
0x1800084b2  pop     rdi
0x1800084b3  pop     rsi
0x1800084b4  pop     rbp
0x1800084b5  retn
0x1800084b7  xor     eax, eax
0x1800084b9  mov     [rbp+57h+var_60], rax
0x1800084bd  mov     [rbp+57h+arg_18], rax
0x1800084c1  mov     [rbp+57h+arg_8], rax
0x1800084c5  mov     [rsp+0E0h+var_B8], rax; void *
0x1800084ca  mov     eax, [rbp+57h+arg_10]
0x1800084cd  mov     [rsp+0E0h+var_C0], eax; enum _SID_NAME_USE
0x1800084d1  lea     r9, [rbp+57h+var_60]; struct _bstr_t *
0x1800084d5  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x1800084d9  lea     rdx, [rbp+57h+arg_8]; struct _bstr_t *
0x1800084dd  mov     rcx, r15; this
0x1800084e0  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x1800084e5  nop
0x1800084e6  lea     rcx, [rbp+57h+arg_8]; this
0x1800084ea  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800084ef  nop
0x1800084f0  lea     rcx, [rbp+57h+arg_18]; this
0x1800084f4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800084f9  nop
0x1800084fa  lea     rcx, [rbp+57h+var_60]; this
0x1800084fe  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008503  nop
0x180008504  mov     rcx, rdi; lpCriticalSection
0x180008507  call    cs:__imp_LeaveCriticalSection
0x18000850e  nop     dword ptr [rax+rax+00h]
0x180008513  xor     eax, eax
0x180008515  jmp     short loc_18000849B
0x180008517  lea     rcx, [rbp+57h+var_68]
0x18000851b  cmp     [rsi], rcx
0x18000851e  ja      loc_18000841E
0x180008524  lea     r12, [rbp+57h+var_68]
0x180008528  sub     r12, [rsi]
0x18000852b  sar     r12, 3
0x18000852f  cmp     rax, [rsi+10h]
0x180008533  jz      loc_1800086A0
0x180008539  mov     rax, [rsi]
0x18000853c  mov     rcx, [rsi+8]
0x180008540  mov     rax, [rax+r12*8]
0x180008544  mov     [rcx], rax
0x180008547  jmp     loc_180008433
0x18000854c  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x180008551  jmp     loc_18000847D
0x180008556  mov     rcx, r15; this
0x180008559  call    ??1User@@QEAA@XZ; User::~User(void)
0x18000855e  mov     [r15], rbx
0x180008561  jmp     loc_18000832F
0x180008566  mov     eax, 80070057h
0x18000856b  jmp     loc_18000849B
0x180008570  mov     [rbp+57h+var_98], 0
0x180008574  lea     rax, qword_18007B2F0
0x18000857b  mov     [rbp+57h+var_90], rax
0x18000857f  xor     r12d, r12d
0x180008582  mov     [rbp+57h+var_88], r12
0x180008586  mov     [rbp+57h+var_80], r12
0x18000858a  mov     [rbp+57h+var_78], 0Eh
0x180008591  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x180008599  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800085a0  mov     [rbp+57h+pExceptionObject], rax
0x1800085a4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800085ab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800085af  call    _CxxThrowException_0
0x1800085b5  lea     rax, WPP_GLOBAL_Control
0x1800085bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085c3  cmp     rcx, rax
0x1800085c6  jz      short loc_1800085E2
0x1800085c8  test    byte ptr [rcx+1Ch], 80h
0x1800085cc  jz      short loc_1800085E2
0x1800085ce  cmp     byte ptr [rcx+19h], 2
0x1800085d2  jb      short loc_1800085E2
0x1800085d4  mov     edx, 11h
0x1800085d9  mov     rcx, [rcx+10h]
0x1800085dd  call    WPP_SF_
0x1800085e2  mov     [rbp+57h+var_98], 0
0x1800085e6  lea     rax, qword_18007B2F0
0x1800085ed  mov     [rbp+57h+var_90], rax
0x1800085f1  mov     [rbp+57h+var_88], r12
0x1800085f5  mov     [rbp+57h+var_80], r12
0x1800085f9  mov     [rbp+57h+var_78], 0Eh
0x180008600  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x180008608  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000860f  mov     [rbp+57h+pExceptionObject], rax
0x180008613  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000861a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000861e  call    _CxxThrowException_0
0x180008624  call    cs:__imp_GetLastError
0x18000862b  nop     dword ptr [rax+rax+00h]
0x180008630  mov     ebx, eax
0x180008632  lea     rax, WPP_GLOBAL_Control
0x180008639  mov     rcx, cs:WPP_GLOBAL_Control
0x180008640  cmp     rcx, rax
0x180008643  jz      short loc_180008662
0x180008645  test    byte ptr [rcx+1Ch], 80h
0x180008649  jz      short loc_180008662
0x18000864b  cmp     byte ptr [rcx+19h], 2
0x18000864f  jb      short loc_180008662
0x180008651  mov     edx, 12h
0x180008656  mov     r9d, ebx
0x180008659  mov     rcx, [rcx+10h]
0x18000865d  call    WPP_SF_d
0x180008662  mov     [rbp+57h+var_98], 0
0x180008666  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000866d  mov     [rbp+57h+pExceptionObject], rax
0x180008671  lea     rax, qword_18007B2F0
0x180008678  mov     [rbp+57h+var_90], rax
0x18000867c  mov     [rbp+57h+var_88], r12
0x180008680  mov     [rbp+57h+var_80], r12
0x180008684  mov     [rbp+57h+var_78], ebx
0x180008687  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x18000868f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180008696  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000869a  call    _CxxThrowException_0
0x1800086a0  mov     rcx, rsi
0x1800086a3  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x1800086a8  jmp     loc_180008539
```
