# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x180001f8c`
- end: `0x18000224c`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(struct User *this, void *, enum _SID_NAME_USE)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002260`
- `0x18003a6e8`
- `0x18004e9d0`
- `0x18006a260`
- `0x18007c724`

## callees

- `0x180001f8c`
- `0x180002790`
- `0x1800044b0`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180027910`
- `0x1800460dc`
- `0x18005a2bc`
- `0x18005dcd4`
- `0x18006acbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000205e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000208e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000205e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000208e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002222`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000207c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000207c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002028`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002028`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall User::FromSid(struct User *this, void *a2, enum _SID_NAME_USE a3)
{
  char v4; // r15
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  User::UserEntry *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // r14
  User::UserEntry ***v9; // r13
  User::UserEntry **v10; // rbx
  void *v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  User::UserEntry *v13; // rax
  __int64 v14; // rbx
  unsigned int updated; // ebx
  __int64 v16; // [rsp+48h] [rbp-39h] BYREF
  __int64 v17; // [rsp+50h] [rbp-31h] BYREF
  __int64 v18; // [rsp+58h] [rbp-29h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-21h] BYREF
  char v20; // [rsp+68h] [rbp-19h]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-11h]
  __int64 v22; // [rsp+78h] [rbp-9h]
  __int64 v23; // [rsp+80h] [rbp-1h]
  int v24; // [rsp+88h] [rbp+7h]
  __int64 v25; // [rsp+8Ch] [rbp+Bh]
  LPCRITICAL_SECTION v26; // [rsp+98h] [rbp+17h]
  User::UserEntry *v27; // [rsp+A0h] [rbp+1Fh]
  PSID pSid2; // [rsp+F0h] [rbp+6Fh] BYREF
  enum _SID_NAME_USE v29; // [rsp+F8h] [rbp+77h]
  User::UserEntry *v30; // [rsp+100h] [rbp+7Fh] BYREF

  v29 = a3;
  pSid2 = a2;
  v4 = 0;
  LODWORD(v30) = 0;
  if ( !a2 )
    return 2147942487LL;
  v6 = User::s_cs;
  v26 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v7 = 0;
  v30 = 0;
  v8 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v9 = (User::UserEntry ***)User::s_userTable;
  v10 = *(User::UserEntry ***)User::s_userTable;
  if ( *(_QWORD *)User::s_userTable != *((_QWORD *)User::s_userTable + 1) )
  {
    while ( v10 != v9[1] )
    {
      v11 = (void *)*((_QWORD *)*v10 + 4);
      if ( v11 && EqualSid(v11, pSid2) )
      {
        v7 = *v10;
        if ( *v10 )
          User::UserEntry::AddRef(*v10);
        wmi::AutoRef<User::UserEntry>::Release(&v30);
        v30 = v7;
        break;
      }
      ++v10;
    }
  }
  LeaveCriticalSection(v8);
  if ( v7 )
  {
    v12 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    ++*((_DWORD *)v7 + 11);
    LeaveCriticalSection(v12);
  }
  wmi::AutoRef<User::UserEntry>::Release(this);
  *(_QWORD *)this = v7;
  wmi::AutoRef<User::UserEntry>::Release(&v30);
  if ( *(_QWORD *)this )
  {
    pSid2 = 0;
    v30 = 0;
    v16 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v16,
      (const struct _bstr_t *)&v30,
      (const struct _bstr_t *)&pSid2,
      v29,
      0,
      0);
    LeaveCriticalSection(v6);
    return 0;
  }
  else
  {
    v13 = (User::UserEntry *)operator new(0x30u);
    v27 = v13;
    if ( v13 )
    {
      v16 = 0;
      v18 = 0;
      v17 = 0;
      v4 = 7;
      LODWORD(v30) = 7;
      v14 = User::UserEntry::UserEntry(
              v13,
              0,
              (const struct _bstr_t *)&v17,
              (const struct _bstr_t *)&v18,
              (const struct _bstr_t *)&v16,
              v29,
              pSid2);
    }
    else
    {
      v14 = 0;
    }
    if ( (v4 & 4) != 0 )
    {
      v4 &= ~4u;
      _bstr_t::~_bstr_t((_bstr_t *)&v17);
    }
    if ( (v4 & 2) != 0 )
    {
      v4 &= ~2u;
      _bstr_t::~_bstr_t((_bstr_t *)&v18);
    }
    if ( (v4 & 1) != 0 )
      _bstr_t::~_bstr_t((_bstr_t *)&v16);
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v20 = 0;
      v21 = &qword_1800A8718;
      v22 = 0;
      v23 = 0;
      v24 = 14;
      v25 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::operator=(this, v14);
    updated = User::UpdateEntry(this);
    LeaveCriticalSection(v6);
    return updated;
  }
}

```

## disassembly

```asm
0x180001f8c  mov     rax, rsp
0x180001f8f  mov     [rax+8], rbx
0x180001f93  mov     [rax+18h], r8d
0x180001f97  mov     [rax+10h], rdx
0x180001f9b  push    rbp
0x180001f9c  push    rsi
0x180001f9d  push    rdi
0x180001f9e  push    r12
0x180001fa0  push    r13
0x180001fa2  push    r14
0x180001fa4  push    r15
0x180001fa6  lea     rbp, [rax-5Fh]
0x180001faa  sub     rsp, 0A0h
0x180001fb1  mov     r12, rcx
0x180001fb4  xor     r15d, r15d
0x180001fb7  mov     dword ptr [rbp+57h+arg_18], r15d
0x180001fbb  test    rdx, rdx
0x180001fbe  jnz     short loc_180001FCA
0x180001fc0  mov     eax, 80070057h
0x180001fc5  jmp     loc_180002230
0x180001fca  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180001fd1  mov     [rbp+57h+var_40], rsi
0x180001fd5  mov     rcx, rsi; lpCriticalSection
0x180001fd8  call    cs:__imp_EnterCriticalSection
0x180001fdf  nop     dword ptr [rax+rax+00h]
0x180001fe4  nop
0x180001fe5  xor     edi, edi
0x180001fe7  mov     [rbp+57h+arg_18], rdi
0x180001feb  mov     r14, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180001ff2  mov     rcx, r14; lpCriticalSection
0x180001ff5  call    cs:__imp_EnterCriticalSection
0x180001ffc  nop     dword ptr [rax+rax+00h]
0x180002001  mov     r13, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180002008  mov     rbx, [r13+0]
0x18000200c  cmp     rbx, [r13+8]
0x180002010  jz      short loc_18000205B
0x180002012  cmp     rbx, [r13+8]
0x180002016  jz      short loc_18000205B
0x180002018  mov     rax, [rbx]
0x18000201b  mov     rcx, [rax+20h]; pSid1
0x18000201f  test    rcx, rcx
0x180002022  jz      short loc_180002038
0x180002024  mov     rdx, [rbp+57h+pSid2]; pSid2
0x180002028  call    cs:__imp_EqualSid
0x18000202f  nop     dword ptr [rax+rax+00h]
0x180002034  test    eax, eax
0x180002036  jnz     short loc_18000203E
0x180002038  add     rbx, 8
0x18000203c  jmp     short loc_180002012
0x18000203e  mov     rdi, [rbx]
0x180002041  test    rdi, rdi
0x180002044  jz      short loc_18000204E
0x180002046  mov     rcx, rdi; this
0x180002049  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18000204e  lea     rcx, [rbp+57h+arg_18]
0x180002052  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180002057  mov     [rbp+57h+arg_18], rdi
0x18000205b  mov     rcx, r14; lpCriticalSection
0x18000205e  call    cs:__imp_LeaveCriticalSection
0x180002065  nop     dword ptr [rax+rax+00h]
0x18000206a  xor     r14d, r14d
0x18000206d  test    rdi, rdi
0x180002070  jz      short loc_18000209A
0x180002072  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180002079  mov     rcx, rbx; lpCriticalSection
0x18000207c  call    cs:__imp_EnterCriticalSection
0x180002083  nop     dword ptr [rax+rax+00h]
0x180002088  inc     dword ptr [rdi+2Ch]
0x18000208b  mov     rcx, rbx; lpCriticalSection
0x18000208e  call    cs:__imp_LeaveCriticalSection
0x180002095  nop     dword ptr [rax+rax+00h]
0x18000209a  mov     rcx, r12
0x18000209d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800020a2  mov     [r12], rdi
0x1800020a6  lea     rcx, [rbp+57h+arg_18]
0x1800020aa  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800020af  cmp     [r12], r14
0x1800020b3  jnz     loc_1800021ED
0x1800020b9  mov     ecx, 30h ; '0'; dwBytes
0x1800020be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800020c3  mov     [rbp+57h+var_38], rax
0x1800020c7  test    rax, rax
0x1800020ca  jz      short loc_180002112
0x1800020cc  mov     [rbp+57h+var_90], r14
0x1800020d0  mov     [rbp+57h+var_80], r14
0x1800020d4  mov     [rbp+57h+var_88], r14
0x1800020d8  mov     r15d, 7
0x1800020de  mov     dword ptr [rbp+57h+arg_18], r15d
0x1800020e2  mov     rcx, [rbp+57h+pSid2]
0x1800020e6  mov     [rsp+30h], rcx; void *
0x1800020eb  mov     ecx, [rbp+57h+arg_10]
0x1800020ee  mov     [rsp+0D0h+var_A8], ecx; enum _SID_NAME_USE
0x1800020f2  lea     rcx, [rbp+57h+var_90]
0x1800020f6  mov     qword ptr [rsp+0D0h+var_B0], rcx; struct _bstr_t *
0x1800020fb  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x1800020ff  lea     r8, [rbp+57h+var_88]; struct _bstr_t *
0x180002103  xor     edx, edx; bool
0x180002105  mov     rcx, rax; this
0x180002108  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18000210d  mov     rbx, rax
0x180002110  jmp     short loc_180002115
0x180002112  mov     rbx, r14
0x180002115  test    r15b, 4
0x180002119  jz      short loc_180002129
0x18000211b  and     r15d, 0FFFFFFFBh
0x18000211f  lea     rcx, [rbp+57h+var_88]; this
0x180002123  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180002128  nop
0x180002129  test    r15b, 2
0x18000212d  jz      short loc_18000213D
0x18000212f  and     r15d, 0FFFFFFFDh
0x180002133  lea     rcx, [rbp+57h+var_80]; this
0x180002137  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000213c  nop
0x18000213d  test    r15b, 1
0x180002141  jz      short loc_18000214C
0x180002143  lea     rcx, [rbp+57h+var_90]; this
0x180002147  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000214c  test    rbx, rbx
0x18000214f  jnz     short loc_1800021C5
0x180002151  lea     rax, WPP_GLOBAL_Control
0x180002158  mov     rcx, cs:WPP_GLOBAL_Control
0x18000215f  cmp     rcx, rax
0x180002162  jz      short loc_180002183
0x180002164  test    byte ptr [rcx+1Ch], 80h
0x180002168  jz      short loc_180002183
0x18000216a  cmp     byte ptr [rcx+19h], 2
0x18000216e  jb      short loc_180002183
0x180002170  lea     edx, [rbx+17h]
0x180002173  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18000217a  mov     rcx, [rcx+10h]
0x18000217e  call    WPP_SF_
0x180002183  mov     [rbp+57h+var_70], r14b
0x180002187  lea     rax, qword_1800A8718
0x18000218e  mov     [rbp+57h+var_68], rax
0x180002192  mov     [rbp+57h+var_60], r14
0x180002196  mov     [rbp+57h+var_58], r14
0x18000219a  mov     [rbp+57h+var_50], 0Eh
0x1800021a1  mov     [rbp+57h+var_4C], 0FFFFFFFFFFFFFFFFh
0x1800021a9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800021b0  mov     [rbp+57h+pExceptionObject], rax
0x1800021b4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800021bb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800021bf  call    _CxxThrowException_0
0x1800021c5  mov     rdx, rbx
0x1800021c8  mov     rcx, r12
0x1800021cb  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800021d0  mov     rcx, r12; this
0x1800021d3  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x1800021d8  mov     ebx, eax
0x1800021da  mov     rcx, rsi; lpCriticalSection
0x1800021dd  call    cs:__imp_LeaveCriticalSection
0x1800021e4  nop     dword ptr [rax+rax+00h]
0x1800021e9  mov     eax, ebx
0x1800021eb  jmp     short loc_180002230
0x1800021ed  mov     [rbp+57h+pSid2], r14
0x1800021f1  mov     [rbp+57h+arg_18], r14
0x1800021f5  mov     [rbp+57h+var_90], r14
0x1800021f9  mov     [rsp+30h], r14b; bool
0x1800021fe  mov     qword ptr [rsp+0D0h+var_A8], r14; void *
0x180002203  mov     ecx, [rbp+57h+arg_10]
0x180002206  mov     [rsp+0D0h+var_B0], ecx; enum _SID_NAME_USE
0x18000220a  lea     r9, [rbp+57h+pSid2]; struct _bstr_t *
0x18000220e  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x180002212  lea     rdx, [rbp+57h+var_90]; struct _bstr_t *
0x180002216  mov     rcx, r12; this
0x180002219  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18000221e  nop
0x18000221f  mov     rcx, rsi; lpCriticalSection
0x180002222  call    cs:__imp_LeaveCriticalSection
0x180002229  nop     dword ptr [rax+rax+00h]
0x18000222e  xor     eax, eax
0x180002230  mov     rbx, [rsp+0D0h+arg_0]
0x180002238  add     rsp, 0A0h
0x18000223f  pop     r15
0x180002241  pop     r14
0x180002243  pop     r13
0x180002245  pop     r12
0x180002247  pop     rdi
0x180002248  pop     rsi
0x180002249  pop     rbp
0x18000224a  retn
```
