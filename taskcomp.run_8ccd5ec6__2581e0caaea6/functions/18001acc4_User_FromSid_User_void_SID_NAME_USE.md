# User::FromSid(User &,void *,_SID_NAME_USE)

- ea: `0x18001acc4`
- end: `0x18001aee6`
- name: `?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(struct User *this, void *, enum _SID_NAME_USE)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800053e8`
- `0x180019c3c`

## callees

- `0x180003cec`
- `0x1800050d0`
- `0x1800053bc`
- `0x180007948`
- `0x180008c4c`
- `0x180010570`
- `0x1800181ec`
- `0x1800197c4`
- `0x18001acc4`
- `0x18001bee0`
- `0x18001c3ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aebb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aebb`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall User::FromSid(User::UserEntry **this, void *a2, enum _SID_NAME_USE a3)
{
  char v6; // di
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD *v9; // rax
  User::UserEntry *v10; // rax
  bool v11; // dl
  __int64 v12; // rsi
  unsigned int updated; // edi
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v15[3]; // [rsp+48h] [rbp-21h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  char v17; // [rsp+68h] [rbp-1h]
  char *v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 v20; // [rsp+80h] [rbp+17h]
  int v21; // [rsp+88h] [rbp+1Fh]
  __int64 v22; // [rsp+8Ch] [rbp+23h]
  __int64 v23; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = 0;
  LODWORD(v23) = 0;
  if ( !a2 )
    return 2147942487LL;
  v8 = User::s_cs;
  v15[1] = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v9 = User::LookupUser(&v23, a2);
  wmi::AutoRef<User::UserEntry>::operator=(this, *v9);
  wmi::AutoRef<User::UserEntry>::Release(&v23);
  if ( *this )
  {
    v14 = 0;
    v24 = 0;
    v23 = 0;
    User::UpdateEntry(
      this,
      (const struct _bstr_t *)&v23,
      (const struct _bstr_t *)&v24,
      (const struct _bstr_t *)&v14,
      a3,
      0);
    _bstr_t::~_bstr_t((_bstr_t *)&v23);
    _bstr_t::~_bstr_t((_bstr_t *)&v24);
    _bstr_t::~_bstr_t((_bstr_t *)&v14);
    LeaveCriticalSection(v8);
    return 0;
  }
  else
  {
    v10 = (User::UserEntry *)operator new(0x30u);
    v15[2] = v10;
    if ( v10 )
    {
      v15[0] = 0;
      v14 = 0;
      v24 = 0;
      v6 = 7;
      LODWORD(v23) = 7;
      v12 = User::UserEntry::UserEntry(
              v10,
              v11,
              (const struct _bstr_t *)&v24,
              (const struct _bstr_t *)&v14,
              (const struct _bstr_t *)v15,
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
      _bstr_t::~_bstr_t((_bstr_t *)&v24);
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      _bstr_t::~_bstr_t((_bstr_t *)&v14);
    }
    if ( (v6 & 1) != 0 )
      _bstr_t::~_bstr_t((_bstr_t *)v15);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v17 = 0;
      v18 = byte_180052608;
      v19 = 0;
      v20 = 0;
      v21 = 14;
      v22 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    wmi::AutoRef<User::UserEntry>::operator=(this, v12);
    updated = User::UpdateEntry((User *)this);
    LeaveCriticalSection(v8);
    return updated;
  }
}

```

## disassembly

```asm
0x18001acc4  mov     [rsp-8+arg_0], rbx
0x18001acc9  mov     [rsp-8+arg_10], rsi
0x18001acce  push    rbp
0x18001accf  push    rdi
0x18001acd0  push    r12
0x18001acd2  push    r14
0x18001acd4  push    r15
0x18001acd6  lea     rbp, [rsp-37h]
0x18001acdb  sub     rsp, 0A0h
0x18001ace2  mov     r15d, r8d
0x18001ace5  mov     rsi, rdx
0x18001ace8  mov     r14, rcx
0x18001aceb  xor     r12d, r12d
0x18001acee  mov     edi, r12d
0x18001acf1  mov     dword ptr [rbp+57h+arg_8], r12d
0x18001acf5  test    rdx, rdx
0x18001acf8  jnz     short loc_18001AD04
0x18001acfa  mov     eax, 80070057h
0x18001acff  jmp     loc_18001AEC9
0x18001ad04  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18001ad0b  mov     [rbp+57h+var_70], rbx
0x18001ad0f  mov     rcx, rbx; lpCriticalSection
0x18001ad12  call    cs:__imp_EnterCriticalSection
0x18001ad19  nop     dword ptr [rax+rax+00h]
0x18001ad1e  nop
0x18001ad1f  mov     rdx, rsi
0x18001ad22  lea     rcx, [rbp+57h+arg_8]
0x18001ad26  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18001ad2b  mov     rdx, [rax]
0x18001ad2e  mov     rcx, r14
0x18001ad31  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001ad36  lea     rcx, [rbp+57h+arg_8]
0x18001ad3a  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001ad3f  cmp     [r14], r12
0x18001ad42  jz      short loc_18001ADA3
0x18001ad44  mov     [rbp+57h+var_80], r12
0x18001ad48  mov     [rbp+57h+arg_18], r12
0x18001ad4c  mov     [rbp+57h+arg_8], r12
0x18001ad50  mov     qword ptr [rsp+0C0h+var_98], r12; void *
0x18001ad55  mov     [rsp+0C0h+var_A0], r15d; enum _SID_NAME_USE
0x18001ad5a  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x18001ad5e  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x18001ad62  lea     rdx, [rbp+57h+arg_8]; struct _bstr_t *
0x18001ad66  mov     rcx, r14; this
0x18001ad69  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18001ad6e  nop
0x18001ad6f  lea     rcx, [rbp+57h+arg_8]; this
0x18001ad73  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ad78  nop
0x18001ad79  lea     rcx, [rbp+57h+arg_18]; this
0x18001ad7d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ad82  nop
0x18001ad83  lea     rcx, [rbp+57h+var_80]; this
0x18001ad87  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ad8c  nop
0x18001ad8d  mov     rcx, rbx; lpCriticalSection
0x18001ad90  call    cs:__imp_LeaveCriticalSection
0x18001ad97  nop     dword ptr [rax+rax+00h]
0x18001ad9c  xor     eax, eax
0x18001ad9e  jmp     loc_18001AEC9
0x18001ada3  mov     ecx, 30h ; '0'; Size
0x18001ada8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001adad  mov     [rbp+57h+var_68], rax
0x18001adb1  test    rax, rax
0x18001adb4  jz      short loc_18001ADF2
0x18001adb6  mov     [rbp+57h+var_78], r12
0x18001adba  mov     [rbp+57h+var_80], r12
0x18001adbe  mov     [rbp+57h+arg_18], r12
0x18001adc2  mov     edi, 7
0x18001adc7  mov     dword ptr [rbp+57h+arg_8], edi
0x18001adca  mov     [rsp+0C0h+var_90], rsi; void *
0x18001adcf  mov     [rsp+0C0h+var_98], r15d; enum _SID_NAME_USE
0x18001add4  lea     rcx, [rbp+57h+var_78]
0x18001add8  mov     qword ptr [rsp+0C0h+var_A0], rcx; struct _bstr_t *
0x18001addd  lea     r9, [rbp+57h+var_80]; struct _bstr_t *
0x18001ade1  lea     r8, [rbp+57h+arg_18]; struct _bstr_t *
0x18001ade5  mov     rcx, rax; this
0x18001ade8  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18001aded  mov     rsi, rax
0x18001adf0  jmp     short loc_18001ADF5
0x18001adf2  mov     rsi, r12
0x18001adf5  test    dil, 4
0x18001adf9  jz      short loc_18001AE08
0x18001adfb  and     edi, 0FFFFFFFBh
0x18001adfe  lea     rcx, [rbp+57h+arg_18]; this
0x18001ae02  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ae07  nop
0x18001ae08  test    dil, 2
0x18001ae0c  jz      short loc_18001AE1B
0x18001ae0e  and     edi, 0FFFFFFFDh
0x18001ae11  lea     rcx, [rbp+57h+var_80]; this
0x18001ae15  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ae1a  nop
0x18001ae1b  test    dil, 1
0x18001ae1f  jz      short loc_18001AE2A
0x18001ae21  lea     rcx, [rbp+57h+var_78]; this
0x18001ae25  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ae2a  test    rsi, rsi
0x18001ae2d  jnz     short loc_18001AEA3
0x18001ae2f  lea     rax, WPP_GLOBAL_Control
0x18001ae36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae3d  cmp     rcx, rax
0x18001ae40  jz      short loc_18001AE61
0x18001ae42  test    byte ptr [rcx+1Ch], 80h
0x18001ae46  jz      short loc_18001AE61
0x18001ae48  cmp     byte ptr [rcx+19h], 2
0x18001ae4c  jb      short loc_18001AE61
0x18001ae4e  lea     edx, [rsi+17h]
0x18001ae51  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001ae58  mov     rcx, [rcx+10h]
0x18001ae5c  call    WPP_SF_
0x18001ae61  mov     [rbp+57h+var_58], r12b
0x18001ae65  lea     rax, byte_180052608
0x18001ae6c  mov     [rbp+57h+var_50], rax
0x18001ae70  mov     [rbp+57h+var_48], r12
0x18001ae74  mov     [rbp+57h+var_40], r12
0x18001ae78  mov     [rbp+57h+var_38], 0Eh
0x18001ae7f  mov     [rbp+57h+var_34], 0FFFFFFFFFFFFFFFFh
0x18001ae87  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ae8e  mov     [rbp+57h+pExceptionObject], rax
0x18001ae92  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001ae99  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001ae9d  call    _CxxThrowException_0
0x18001aea3  mov     rdx, rsi
0x18001aea6  mov     rcx, r14
0x18001aea9  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001aeae  mov     rcx, r14; this
0x18001aeb1  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18001aeb6  mov     edi, eax
0x18001aeb8  mov     rcx, rbx; lpCriticalSection
0x18001aebb  call    cs:__imp_LeaveCriticalSection
0x18001aec2  nop     dword ptr [rax+rax+00h]
0x18001aec7  mov     eax, edi
0x18001aec9  lea     r11, [rsp+0C0h+var_20]
0x18001aed1  mov     rbx, [r11+30h]
0x18001aed5  mov     rsi, [r11+40h]
0x18001aed9  mov     rsp, r11
0x18001aedc  pop     r15
0x18001aede  pop     r14
0x18001aee0  pop     r12
0x18001aee2  pop     rdi
0x18001aee3  pop     rbp
0x18001aee4  retn
```
