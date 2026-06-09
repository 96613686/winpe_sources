# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x180007da0`
- end: `0x1800081b3`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `1043`
- prototype: `__int64 __fastcall(struct User *this, PSID pSourceSid, enum _SID_NAME_USE)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180008680`

## callees

- `0x180007aa0`
- `0x180007da0`
- `0x180008c70`
- `0x180008d30`
- `0x180008da8`
- `0x180008e0c`
- `0x180008e40`
- `0x180009958`
- `0x180009a94`
- `0x180009b1c`
- `0x18003b51c`
- `0x18004e590`
- `0x18004e5c0`

## import_xrefs

- `msvcrt!malloc` at `0x180007e86`
- `msvcrt!malloc` at `0x180007e86`
- `msvcrt!free` at `0x180007eee`
- `msvcrt!free` at `0x180007eee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007de5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007de5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000812f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000812f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007e30`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007e30`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007f09`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007f09`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007ed3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007ed3`

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
      v28 = &qword_180077320;
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
      v28 = &qword_180077320;
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
      v28 = &qword_180077320;
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
0x180007da0  mov     [rsp-8+arg_0], rbx
0x180007da5  mov     [rsp-8+arg_10], r8d
0x180007daa  push    rbp
0x180007dab  push    rsi
0x180007dac  push    rdi
0x180007dad  push    r12
0x180007daf  push    r13
0x180007db1  push    r14
0x180007db3  push    r15
0x180007db5  lea     rbp, [rsp-27h]
0x180007dba  sub     rsp, 0B0h
0x180007dc1  mov     r13, rdx
0x180007dc4  mov     r15, rcx
0x180007dc7  mov     dword ptr [rbp+57h+arg_8], 0
0x180007dce  test    rdx, rdx
0x180007dd1  jz      loc_180008071
0x180007dd7  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180007dde  mov     [rbp+57h+var_58], rdi
0x180007de2  mov     rcx, rdi; lpCriticalSection
0x180007de5  call    cs:__imp_EnterCriticalSection
0x180007deb  nop
0x180007dec  xor     ebx, ebx
0x180007dee  mov     [rbp+57h+arg_8], rbx
0x180007df2  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180007df9  mov     rcx, rsi; lpCriticalSection
0x180007dfc  call    cs:__imp_EnterCriticalSection
0x180007e02  mov     r12, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180007e09  mov     r14, [r12]
0x180007e0d  cmp     r14, [r12+8]
0x180007e12  jz      short loc_180007E4A
0x180007e14  cmp     r14, [r12+8]
0x180007e19  jz      short loc_180007E4A
0x180007e1b  mov     rax, [r14]
0x180007e1e  mov     rcx, [rax+20h]; pSid1
0x180007e22  test    rcx, rcx
0x180007e25  jnz     short loc_180007E2D
0x180007e27  add     r14, 8
0x180007e2b  jmp     short loc_180007E14
0x180007e2d  mov     rdx, r13; pSid2
0x180007e30  call    cs:__imp_EqualSid
0x180007e36  test    eax, eax
0x180007e38  jz      short loc_180007E27
0x180007e3a  mov     rdx, [r14]
0x180007e3d  lea     rcx, [rbp+57h+arg_8]
0x180007e41  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180007e46  mov     rbx, [rbp+57h+arg_8]
0x180007e4a  mov     rcx, rsi; lpCriticalSection
0x180007e4d  call    cs:__imp_LeaveCriticalSection
0x180007e53  test    rbx, rbx
0x180007e56  jz      loc_180008061
0x180007e5c  mov     rcx, rbx; this
0x180007e5f  call    ?AddRef@UserEntry@User@@QEAAKXZ; User::UserEntry::AddRef(void)
0x180007e64  mov     rcx, r15; this
0x180007e67  call    ??1User@@QEAA@XZ; User::~User(void)
0x180007e6c  mov     [r15], rbx
0x180007e6f  mov     rcx, rbx; this
0x180007e72  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x180007e77  cmp     qword ptr [r15], 0
0x180007e7b  jnz     loc_180007FC8
0x180007e81  mov     ecx, 30h ; '0'; Size
0x180007e86  call    cs:__imp_malloc
0x180007e8c  mov     r14, rax
0x180007e8f  test    rax, rax
0x180007e92  jz      loc_18000807B
0x180007e98  mov     [rbp+57h+arg_18], rax
0x180007e9c  xor     r12d, r12d
0x180007e9f  mov     [rbp+57h+var_60], r12
0x180007ea3  mov     [rbp+57h+var_50], r12
0x180007ea7  mov     [rbp+57h+var_48], r12
0x180007eab  mov     dword ptr [rbp+57h+arg_8], 7
0x180007eb2  mov     [rax], r12b
0x180007eb5  mov     [rax+8], r12
0x180007eb9  mov     [rax+10h], r12
0x180007ebd  mov     [rax+18h], r12
0x180007ec1  mov     [rax+20h], r12
0x180007ec5  mov     eax, [rbp+57h+arg_10]
0x180007ec8  mov     [r14+28h], eax
0x180007ecc  mov     [r14+2Ch], r12d
0x180007ed0  mov     rcx, r13; pSid
0x180007ed3  call    cs:__imp_GetLengthSid
0x180007ed9  mov     esi, eax
0x180007edb  mov     ecx, eax; unsigned __int64
0x180007edd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ee2  mov     rbx, rax
0x180007ee5  mov     rcx, [r14+20h]; Block
0x180007ee9  test    rcx, rcx
0x180007eec  jz      short loc_180007EF4
0x180007eee  call    cs:__imp_free
0x180007ef4  mov     [r14+20h], rbx
0x180007ef8  test    rbx, rbx
0x180007efb  jz      loc_1800080C0
0x180007f01  mov     r8, r13; pSourceSid
0x180007f04  mov     rdx, rbx; pDestinationSid
0x180007f07  mov     ecx, esi; nDestinationSidLength
0x180007f09  call    cs:__imp_CopySid
0x180007f0f  test    eax, eax
0x180007f11  jz      loc_18000812F
0x180007f17  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180007f1e  mov     [rbp+57h+var_40], rbx
0x180007f22  mov     rcx, rbx; lpCriticalSection
0x180007f25  call    cs:__imp_EnterCriticalSection
0x180007f2b  nop
0x180007f2c  mov     rsi, cs:?s_userTable@User@@0PEAV?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@EA; std::vector<User::UserEntry *> * User::s_userTable
0x180007f33  mov     [rbp+57h+var_68], r14
0x180007f37  mov     rax, [rsi+8]
0x180007f3b  lea     rcx, [rbp+57h+var_68]
0x180007f3f  cmp     rcx, rax
0x180007f42  jb      loc_180008022
0x180007f48  cmp     rax, [rsi+10h]
0x180007f4c  jnz     short loc_180007F56
0x180007f4e  mov     rcx, rsi
0x180007f51  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x180007f56  mov     rax, [rsi+8]
0x180007f5a  mov     [rax], r14
0x180007f5d  add     qword ptr [rsi+8], 8
0x180007f62  mov     rcx, rbx; lpCriticalSection
0x180007f65  call    cs:__imp_LeaveCriticalSection
0x180007f6b  nop
0x180007f6c  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180007f73  mov     rcx, rbx; lpCriticalSection
0x180007f76  call    cs:__imp_EnterCriticalSection
0x180007f7c  inc     dword ptr [r14+2Ch]
0x180007f80  mov     rcx, rbx; lpCriticalSection
0x180007f83  call    cs:__imp_LeaveCriticalSection
0x180007f89  mov     rcx, [r15]; this
0x180007f8c  test    rcx, rcx
0x180007f8f  jnz     loc_180008057
0x180007f95  mov     [r15], r14
0x180007f98  mov     rcx, r15; this
0x180007f9b  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180007fa0  mov     ebx, eax
0x180007fa2  mov     rcx, rdi; lpCriticalSection
0x180007fa5  call    cs:__imp_LeaveCriticalSection
0x180007fab  mov     eax, ebx
0x180007fad  mov     rbx, [rsp+0E0h+arg_0]
0x180007fb5  add     rsp, 0B0h
0x180007fbc  pop     r15
0x180007fbe  pop     r14
0x180007fc0  pop     r13
0x180007fc2  pop     r12
0x180007fc4  pop     rdi
0x180007fc5  pop     rsi
0x180007fc6  pop     rbp
0x180007fc7  retn
0x180007fc8  xor     eax, eax
0x180007fca  mov     [rbp+57h+var_60], rax
0x180007fce  mov     [rbp+57h+arg_18], rax
0x180007fd2  mov     [rbp+57h+arg_8], rax
0x180007fd6  mov     [rsp+0E0h+var_B8], rax; void *
0x180007fdb  mov     eax, [rbp+57h+arg_10]
0x180007fde  mov     [rsp+0E0h+var_C0], eax; enum _SID_NAME_USE
0x180007fe2  lea     r9, [rbp+57h+var_60]; struct _bstr_t *
0x180007fe6  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x180007fea  lea     rdx, [rbp+57h+arg_8]; struct _bstr_t *
0x180007fee  mov     rcx, r15; this
0x180007ff1  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180007ff6  nop
0x180007ff7  lea     rcx, [rbp+57h+arg_8]; this
0x180007ffb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008000  nop
0x180008001  lea     rcx, [rbp+57h+arg_18]; this
0x180008005  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000800a  nop
0x18000800b  lea     rcx, [rbp+57h+var_60]; this
0x18000800f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008014  nop
0x180008015  mov     rcx, rdi; lpCriticalSection
0x180008018  call    cs:__imp_LeaveCriticalSection
0x18000801e  xor     eax, eax
0x180008020  jmp     short loc_180007FAD
0x180008022  lea     rcx, [rbp+57h+var_68]
0x180008026  cmp     [rsi], rcx
0x180008029  ja      loc_180007F48
0x18000802f  lea     r12, [rbp+57h+var_68]
0x180008033  sub     r12, [rsi]
0x180008036  sar     r12, 3
0x18000803a  cmp     rax, [rsi+10h]
0x18000803e  jz      loc_1800081A5
0x180008044  mov     rax, [rsi]
0x180008047  mov     rcx, [rsi+8]
0x18000804b  mov     rax, [rax+r12*8]
0x18000804f  mov     [rcx], rax
0x180008052  jmp     loc_180007F5D
0x180008057  call    ?Release@UserEntry@User@@QEAAKXZ; User::UserEntry::Release(void)
0x18000805c  jmp     loc_180007F95
0x180008061  mov     rcx, r15; this
0x180008064  call    ??1User@@QEAA@XZ; User::~User(void)
0x180008069  mov     [r15], rbx
0x18000806c  jmp     loc_180007E77
0x180008071  mov     eax, 80070057h
0x180008076  jmp     loc_180007FAD
0x18000807b  mov     [rbp+57h+var_98], 0
0x18000807f  lea     rax, qword_180077320
0x180008086  mov     [rbp+57h+var_90], rax
0x18000808a  xor     r12d, r12d
0x18000808d  mov     [rbp+57h+var_88], r12
0x180008091  mov     [rbp+57h+var_80], r12
0x180008095  mov     [rbp+57h+var_78], 0Eh
0x18000809c  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x1800080a4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800080ab  mov     [rbp+57h+pExceptionObject], rax
0x1800080af  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800080b6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800080ba  call    _CxxThrowException_0
0x1800080c0  lea     rax, WPP_GLOBAL_Control
0x1800080c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ce  cmp     rcx, rax
0x1800080d1  jz      short loc_1800080ED
0x1800080d3  test    byte ptr [rcx+1Ch], 80h
0x1800080d7  jz      short loc_1800080ED
0x1800080d9  cmp     byte ptr [rcx+19h], 2
0x1800080dd  jb      short loc_1800080ED
0x1800080df  mov     edx, 11h
0x1800080e4  mov     rcx, [rcx+10h]
0x1800080e8  call    WPP_SF_
0x1800080ed  mov     [rbp+57h+var_98], 0
0x1800080f1  lea     rax, qword_180077320
0x1800080f8  mov     [rbp+57h+var_90], rax
0x1800080fc  mov     [rbp+57h+var_88], r12
0x180008100  mov     [rbp+57h+var_80], r12
0x180008104  mov     [rbp+57h+var_78], 0Eh
0x18000810b  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x180008113  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000811a  mov     [rbp+57h+pExceptionObject], rax
0x18000811e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180008125  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008129  call    _CxxThrowException_0
0x18000812f  call    cs:__imp_GetLastError
0x180008135  mov     ebx, eax
0x180008137  lea     rax, WPP_GLOBAL_Control
0x18000813e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008145  cmp     rcx, rax
0x180008148  jz      short loc_180008167
0x18000814a  test    byte ptr [rcx+1Ch], 80h
0x18000814e  jz      short loc_180008167
0x180008150  cmp     byte ptr [rcx+19h], 2
0x180008154  jb      short loc_180008167
0x180008156  mov     edx, 12h
0x18000815b  mov     r9d, ebx
0x18000815e  mov     rcx, [rcx+10h]
0x180008162  call    WPP_SF_d
0x180008167  mov     [rbp+57h+var_98], 0
0x18000816b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180008172  mov     [rbp+57h+pExceptionObject], rax
0x180008176  lea     rax, qword_180077320
0x18000817d  mov     [rbp+57h+var_90], rax
0x180008181  mov     [rbp+57h+var_88], r12
0x180008185  mov     [rbp+57h+var_80], r12
0x180008189  mov     [rbp+57h+var_78], ebx
0x18000818c  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x180008194  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000819b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000819f  call    _CxxThrowException_0
0x1800081a5  mov     rcx, rsi
0x1800081a8  call    ?_Reserve@?$vector@PEAUUserEntry@User@@V?$allocator@PEAUUserEntry@User@@@std@@@std@@IEAAX_K@Z; std::vector<User::UserEntry *>::_Reserve(unsigned __int64)
0x1800081ad  jmp     loc_180008044
```
