# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x18002af2c`
- end: `0x18002b1bb`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct User *this, void *, enum _SID_NAME_USE)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022668`
- `0x18002b1d0`
- `0x18004c6d0`
- `0x18006701c`
- `0x1800785f4`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18002ab90`
- `0x18002af2c`
- `0x18002b690`
- `0x18002d390`
- `0x180030f80`
- `0x180043fcc`
- `0x18005790c`
- `0x18005b124`
- `0x1800679e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b159`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b198`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b159`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b198`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002af78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002af8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002af78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002af8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b004`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002afbc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002afbc`

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
      v21 = &qword_1800A4718;
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
0x18002af2c  mov     rax, rsp
0x18002af2f  mov     [rax+8], rbx
0x18002af33  mov     [rax+18h], r8d
0x18002af37  mov     [rax+10h], rdx
0x18002af3b  push    rbp
0x18002af3c  push    rsi
0x18002af3d  push    rdi
0x18002af3e  push    r12
0x18002af40  push    r13
0x18002af42  push    r14
0x18002af44  push    r15
0x18002af46  lea     rbp, [rax-5Fh]
0x18002af4a  sub     rsp, 0A0h
0x18002af51  mov     r12, rcx
0x18002af54  xor     r15d, r15d
0x18002af57  mov     dword ptr [rbp+57h+arg_18], r15d
0x18002af5b  test    rdx, rdx
0x18002af5e  jnz     short loc_18002AF6A
0x18002af60  mov     eax, 80070057h
0x18002af65  jmp     loc_18002B1A0
0x18002af6a  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002af71  mov     [rbp+57h+var_40], rsi
0x18002af75  mov     rcx, rsi; lpCriticalSection
0x18002af78  call    cs:__imp_EnterCriticalSection
0x18002af7e  nop
0x18002af7f  xor     edi, edi
0x18002af81  mov     [rbp+57h+arg_18], rdi
0x18002af85  mov     r14, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002af8c  mov     rcx, r14; lpCriticalSection
0x18002af8f  call    cs:__imp_EnterCriticalSection
0x18002af95  mov     r13, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x18002af9c  mov     rbx, [r13+0]
0x18002afa0  cmp     rbx, [r13+8]
0x18002afa4  jz      short loc_18002AFE9
0x18002afa6  cmp     rbx, [r13+8]
0x18002afaa  jz      short loc_18002AFE9
0x18002afac  mov     rax, [rbx]
0x18002afaf  mov     rcx, [rax+20h]; pSid1
0x18002afb3  test    rcx, rcx
0x18002afb6  jz      short loc_18002AFC6
0x18002afb8  mov     rdx, [rbp+57h+pSid2]; pSid2
0x18002afbc  call    cs:__imp_EqualSid
0x18002afc2  test    eax, eax
0x18002afc4  jnz     short loc_18002AFCC
0x18002afc6  add     rbx, 8
0x18002afca  jmp     short loc_18002AFA6
0x18002afcc  mov     rdi, [rbx]
0x18002afcf  test    rdi, rdi
0x18002afd2  jz      short loc_18002AFDC
0x18002afd4  mov     rcx, rdi; this
0x18002afd7  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x18002afdc  lea     rcx, [rbp+57h+arg_18]
0x18002afe0  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002afe5  mov     [rbp+57h+arg_18], rdi
0x18002afe9  mov     rcx, r14; lpCriticalSection
0x18002afec  call    cs:__imp_LeaveCriticalSection
0x18002aff2  xor     r14d, r14d
0x18002aff5  test    rdi, rdi
0x18002aff8  jz      short loc_18002B016
0x18002affa  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002b001  mov     rcx, rbx; lpCriticalSection
0x18002b004  call    cs:__imp_EnterCriticalSection
0x18002b00a  inc     dword ptr [rdi+2Ch]
0x18002b00d  mov     rcx, rbx; lpCriticalSection
0x18002b010  call    cs:__imp_LeaveCriticalSection
0x18002b016  mov     rcx, r12
0x18002b019  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002b01e  mov     [r12], rdi
0x18002b022  lea     rcx, [rbp+57h+arg_18]
0x18002b026  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002b02b  cmp     [r12], r14
0x18002b02f  jnz     loc_18002B163
0x18002b035  mov     ecx, 30h ; '0'; dwBytes
0x18002b03a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b03f  mov     [rbp+57h+var_38], rax
0x18002b043  test    rax, rax
0x18002b046  jz      short loc_18002B08E
0x18002b048  mov     [rbp+57h+var_90], r14
0x18002b04c  mov     [rbp+57h+var_80], r14
0x18002b050  mov     [rbp+57h+var_88], r14
0x18002b054  mov     r15d, 7
0x18002b05a  mov     dword ptr [rbp+57h+arg_18], r15d
0x18002b05e  mov     rcx, [rbp+57h+pSid2]
0x18002b062  mov     [rsp+30h], rcx; void *
0x18002b067  mov     ecx, [rbp+57h+arg_10]
0x18002b06a  mov     [rsp+0D0h+var_A8], ecx; enum _SID_NAME_USE
0x18002b06e  lea     rcx, [rbp+57h+var_90]
0x18002b072  mov     qword ptr [rsp+0D0h+var_B0], rcx; struct _bstr_t *
0x18002b077  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x18002b07b  lea     r8, [rbp+57h+var_88]; struct _bstr_t *
0x18002b07f  xor     edx, edx; bool
0x18002b081  mov     rcx, rax; this
0x18002b084  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18002b089  mov     rbx, rax
0x18002b08c  jmp     short loc_18002B091
0x18002b08e  mov     rbx, r14
0x18002b091  test    r15b, 4
0x18002b095  jz      short loc_18002B0A5
0x18002b097  and     r15d, 0FFFFFFFBh
0x18002b09b  lea     rcx, [rbp+57h+var_88]; this
0x18002b09f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b0a4  nop
0x18002b0a5  test    r15b, 2
0x18002b0a9  jz      short loc_18002B0B9
0x18002b0ab  and     r15d, 0FFFFFFFDh
0x18002b0af  lea     rcx, [rbp+57h+var_80]; this
0x18002b0b3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b0b8  nop
0x18002b0b9  test    r15b, 1
0x18002b0bd  jz      short loc_18002B0C8
0x18002b0bf  lea     rcx, [rbp+57h+var_90]; this
0x18002b0c3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002b0c8  test    rbx, rbx
0x18002b0cb  jnz     short loc_18002B141
0x18002b0cd  lea     rax, WPP_GLOBAL_Control
0x18002b0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0db  cmp     rcx, rax
0x18002b0de  jz      short loc_18002B0FF
0x18002b0e0  test    byte ptr [rcx+1Ch], 80h
0x18002b0e4  jz      short loc_18002B0FF
0x18002b0e6  cmp     byte ptr [rcx+19h], 2
0x18002b0ea  jb      short loc_18002B0FF
0x18002b0ec  lea     edx, [rbx+17h]
0x18002b0ef  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18002b0f6  mov     rcx, [rcx+10h]
0x18002b0fa  call    WPP_SF_
0x18002b0ff  mov     [rbp+57h+var_70], r14b
0x18002b103  lea     rax, qword_1800A4718
0x18002b10a  mov     [rbp+57h+var_68], rax
0x18002b10e  mov     [rbp+57h+var_60], r14
0x18002b112  mov     [rbp+57h+var_58], r14
0x18002b116  mov     [rbp+57h+var_50], 0Eh
0x18002b11d  mov     [rbp+57h+var_4C], 0FFFFFFFFFFFFFFFFh
0x18002b125  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002b12c  mov     [rbp+57h+pExceptionObject], rax
0x18002b130  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002b137  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b13b  call    _CxxThrowException_0
0x18002b141  mov     rdx, rbx
0x18002b144  mov     rcx, r12
0x18002b147  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18002b14c  mov     rcx, r12; this
0x18002b14f  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002b154  mov     ebx, eax
0x18002b156  mov     rcx, rsi; lpCriticalSection
0x18002b159  call    cs:__imp_LeaveCriticalSection
0x18002b15f  mov     eax, ebx
0x18002b161  jmp     short loc_18002B1A0
0x18002b163  mov     [rbp+57h+pSid2], r14
0x18002b167  mov     [rbp+57h+arg_18], r14
0x18002b16b  mov     [rbp+57h+var_90], r14
0x18002b16f  mov     [rsp+30h], r14b; bool
0x18002b174  mov     qword ptr [rsp+0D0h+var_A8], r14; void *
0x18002b179  mov     ecx, [rbp+57h+arg_10]
0x18002b17c  mov     [rsp+0D0h+var_B0], ecx; enum _SID_NAME_USE
0x18002b180  lea     r9, [rbp+57h+pSid2]; struct _bstr_t *
0x18002b184  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x18002b188  lea     rdx, [rbp+57h+var_90]; struct _bstr_t *
0x18002b18c  mov     rcx, r12; this
0x18002b18f  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18002b194  nop
0x18002b195  mov     rcx, rsi; lpCriticalSection
0x18002b198  call    cs:__imp_LeaveCriticalSection
0x18002b19e  xor     eax, eax
0x18002b1a0  mov     rbx, [rsp+0D0h+arg_0]
0x18002b1a8  add     rsp, 0A0h
0x18002b1af  pop     r15
0x18002b1b1  pop     r14
0x18002b1b3  pop     r13
0x18002b1b5  pop     r12
0x18002b1b7  pop     rdi
0x18002b1b8  pop     rsi
0x18002b1b9  pop     rbp
0x18002b1ba  retn
```
