# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x180019a10`
- end: `0x180019c1f`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct User *this, void *, enum _SID_NAME_USE)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000518c`
- `0x180018a4c`

## callees

- `0x180003b3c`
- `0x180004e50`
- `0x1800050fc`
- `0x180007488`
- `0x18000878c`
- `0x18000fbb8`
- `0x180017210`
- `0x18001862c`
- `0x180019a10`
- `0x18001ab20`
- `0x18001af08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019bfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall User::FromSid(struct User *this, void *a2, enum _SID_NAME_USE a3)
{
  char v6; // di
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD *v9; // rax
  User::UserEntry *v10; // rax
  __int64 v11; // rdx
  User::UserEntry *v12; // rsi
  unsigned int updated; // edi
  bool v14; // [rsp+30h] [rbp-39h]
  __int64 v15; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-21h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  char v18; // [rsp+68h] [rbp-1h]
  char *v19; // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+78h] [rbp+Fh]
  __int64 v21; // [rsp+80h] [rbp+17h]
  int v22; // [rsp+88h] [rbp+1Fh]
  __int64 v23; // [rsp+8Ch] [rbp+23h]
  __int64 v24; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = 0;
  LODWORD(v24) = 0;
  if ( !a2 )
    return 2147942487LL;
  v8 = User::s_cs;
  v16[1] = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v9 = (_QWORD *)User::LookupUser(&v24, a2);
  wmi::AutoRef<User::UserEntry>::operator=(this, *v9);
  wmi::AutoRef<User::UserEntry>::Release(&v24);
  if ( *(_QWORD *)this )
  {
    v15 = 0;
    v25 = 0;
    v24 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v24,
      (const struct _bstr_t *)&v25,
      (const struct _bstr_t *)&v15,
      a3,
      0,
      v14);
    _bstr_t::~_bstr_t((_bstr_t *)&v24);
    _bstr_t::~_bstr_t((_bstr_t *)&v25);
    _bstr_t::~_bstr_t((_bstr_t *)&v15);
    LeaveCriticalSection(v8);
    return 0;
  }
  else
  {
    v10 = (User::UserEntry *)operator new(0x30u);
    v16[2] = v10;
    if ( v10 )
    {
      v16[0] = 0;
      v15 = 0;
      v25 = 0;
      v6 = 7;
      LODWORD(v24) = 7;
      v12 = User::UserEntry::UserEntry(
              v10,
              v11,
              (const struct _bstr_t *)&v25,
              (const struct _bstr_t *)&v15,
              (const struct _bstr_t *)v16,
              a3,
              a2);
    }
    else
    {
      v12 = 0;
    }
    if ( (v6 & 4) != 0 )
    {
      v6 &= ~4u;
      _bstr_t::~_bstr_t((_bstr_t *)&v25);
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      _bstr_t::~_bstr_t((_bstr_t *)&v15);
    }
    if ( (v6 & 1) != 0 )
      _bstr_t::~_bstr_t((_bstr_t *)v16);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v18 = 0;
      v19 = byte_1800505F8;
      v20 = 0;
      v21 = 0;
      v22 = 14;
      v23 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::operator=(this, v12);
    updated = User::UpdateEntry(this);
    LeaveCriticalSection(v8);
    return updated;
  }
}

```

## disassembly

```asm
0x180019a10  mov     [rsp-8+arg_0], rbx
0x180019a15  mov     [rsp-8+arg_10], rsi
0x180019a1a  push    rbp
0x180019a1b  push    rdi
0x180019a1c  push    r12
0x180019a1e  push    r14
0x180019a20  push    r15
0x180019a22  lea     rbp, [rsp-37h]
0x180019a27  sub     rsp, 0A0h
0x180019a2e  mov     r15d, r8d
0x180019a31  mov     rsi, rdx
0x180019a34  mov     r14, rcx
0x180019a37  xor     r12d, r12d
0x180019a3a  mov     edi, r12d
0x180019a3d  mov     dword ptr [rbp+57h+arg_8], r12d
0x180019a41  test    rdx, rdx
0x180019a44  jnz     short loc_180019A50
0x180019a46  mov     eax, 80070057h
0x180019a4b  jmp     loc_180019C03
0x180019a50  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180019a57  mov     [rbp+57h+var_70], rbx
0x180019a5b  mov     rcx, rbx; lpCriticalSection
0x180019a5e  call    cs:__imp_EnterCriticalSection
0x180019a64  nop
0x180019a65  mov     rdx, rsi
0x180019a68  lea     rcx, [rbp+57h+arg_8]
0x180019a6c  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x180019a71  mov     rdx, [rax]
0x180019a74  mov     rcx, r14
0x180019a77  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180019a7c  lea     rcx, [rbp+57h+arg_8]
0x180019a80  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180019a85  cmp     [r14], r12
0x180019a88  jz      short loc_180019AE3
0x180019a8a  mov     [rbp+57h+var_80], r12
0x180019a8e  mov     [rbp+57h+arg_18], r12
0x180019a92  mov     [rbp+57h+arg_8], r12
0x180019a96  mov     qword ptr [rsp+0C0h+var_98], r12; void *
0x180019a9b  mov     [rsp+0C0h+var_A0], r15d; enum _SID_NAME_USE
0x180019aa0  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x180019aa4  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x180019aa8  lea     rdx, [rbp+57h+arg_8]; struct _bstr_t *
0x180019aac  mov     rcx, r14; this
0x180019aaf  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180019ab4  nop
0x180019ab5  lea     rcx, [rbp+57h+arg_8]; this
0x180019ab9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019abe  nop
0x180019abf  lea     rcx, [rbp+57h+arg_18]; this
0x180019ac3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019ac8  nop
0x180019ac9  lea     rcx, [rbp+57h+var_80]; this
0x180019acd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019ad2  nop
0x180019ad3  mov     rcx, rbx; lpCriticalSection
0x180019ad6  call    cs:__imp_LeaveCriticalSection
0x180019adc  xor     eax, eax
0x180019ade  jmp     loc_180019C03
0x180019ae3  mov     ecx, 30h ; '0'; Size
0x180019ae8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019aed  mov     [rbp+57h+var_68], rax
0x180019af1  test    rax, rax
0x180019af4  jz      short loc_180019B32
0x180019af6  mov     [rbp+57h+var_78], r12
0x180019afa  mov     [rbp+57h+var_80], r12
0x180019afe  mov     [rbp+57h+arg_18], r12
0x180019b02  mov     edi, 7
0x180019b07  mov     dword ptr [rbp+57h+arg_8], edi
0x180019b0a  mov     qword ptr [rsp+0C0h+var_90], rsi; void *
0x180019b0f  mov     [rsp+0C0h+var_98], r15d; enum _SID_NAME_USE
0x180019b14  lea     rcx, [rbp+57h+var_78]
0x180019b18  mov     qword ptr [rsp+0C0h+var_A0], rcx; struct _bstr_t *
0x180019b1d  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x180019b21  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x180019b25  mov     rcx, rax; this
0x180019b28  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x180019b2d  mov     rsi, rax
0x180019b30  jmp     short loc_180019B35
0x180019b32  mov     rsi, r12
0x180019b35  test    dil, 4
0x180019b39  jz      short loc_180019B48
0x180019b3b  and     edi, 0FFFFFFFBh
0x180019b3e  lea     rcx, [rbp+57h+arg_18]; this
0x180019b42  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019b47  nop
0x180019b48  test    dil, 2
0x180019b4c  jz      short loc_180019B5B
0x180019b4e  and     edi, 0FFFFFFFDh
0x180019b51  lea     rcx, [rbp+57h+var_80]; this
0x180019b55  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019b5a  nop
0x180019b5b  test    dil, 1
0x180019b5f  jz      short loc_180019B6A
0x180019b61  lea     rcx, [rbp+57h+var_78]; this
0x180019b65  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180019b6a  test    rsi, rsi
0x180019b6d  jnz     short loc_180019BE3
0x180019b6f  lea     rax, WPP_GLOBAL_Control
0x180019b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b7d  cmp     rcx, rax
0x180019b80  jz      short loc_180019BA1
0x180019b82  test    byte ptr [rcx+1Ch], 80h
0x180019b86  jz      short loc_180019BA1
0x180019b88  cmp     byte ptr [rcx+19h], 2
0x180019b8c  jb      short loc_180019BA1
0x180019b8e  lea     edx, [rsi+17h]
0x180019b91  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019b98  mov     rcx, [rcx+10h]
0x180019b9c  call    WPP_SF_
0x180019ba1  mov     [rbp+57h+var_58], r12b
0x180019ba5  lea     rax, byte_1800505F8
0x180019bac  mov     [rbp+57h+var_50], rax
0x180019bb0  mov     [rbp+57h+var_48], r12
0x180019bb4  mov     [rbp+57h+var_40], r12
0x180019bb8  mov     [rbp+57h+var_38], 0Eh
0x180019bbf  mov     [rbp+57h+var_34], 0FFFFFFFFFFFFFFFFh
0x180019bc7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019bce  mov     [rbp+57h+pExceptionObject], rax
0x180019bd2  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180019bd9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019bdd  call    _CxxThrowException_0
0x180019be3  mov     rdx, rsi
0x180019be6  mov     rcx, r14
0x180019be9  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180019bee  mov     rcx, r14; this
0x180019bf1  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180019bf6  mov     edi, eax
0x180019bf8  mov     rcx, rbx; lpCriticalSection
0x180019bfb  call    cs:__imp_LeaveCriticalSection
0x180019c01  mov     eax, edi
0x180019c03  lea     r11, [rsp+0C0h+var_20]
0x180019c0b  mov     rbx, [r11+30h]
0x180019c0f  mov     rsi, [r11+40h]
0x180019c13  mov     rsp, r11
0x180019c16  pop     r15
0x180019c18  pop     r14
0x180019c1a  pop     r12
0x180019c1c  pop     rdi
0x180019c1d  pop     rbp
0x180019c1e  retn
```
