# DAV_URI_CONFIG::QueryAccessForUri(IHttpUser *,ushort const *,ulong *)

- ea: `0x180006310`
- end: `0x18000642d`
- name: `?QueryAccessForUri@DAV_URI_CONFIG@@QEAAJPEAVIHttpUser@@PEBGPEAK@Z`
- size: `285`
- prototype: `int(DAV_URI_CONFIG *__hidden this, struct IHttpUser *, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800058e4`
- `0x180006434`
- `0x18000da04`

## callees

- `0x1800021c4`
- `0x180006310`
- `0x180022520`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800063a8`
- `msvcrt!_wcslwr` at `0x1800063a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006382`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006382`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000636f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000636f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000639c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800063fe`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000639c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800063fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006392`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800063f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006392`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800063f4`

## pseudocode

```c
__int64 __fastcall DAV_URI_CONFIG::QueryAccessForUri(
        DAV_URI_CONFIG *this,
        struct IHttpUser *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int matched; // ebx
  DAV_AUTH_RULES_ENTRY *i; // rdi
  unsigned int v10; // eax
  int v12; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v13[5]; // [rsp+38h] [rbp-51h] BYREF
  int v14; // [rsp+60h] [rbp-29h]
  __int16 v15; // [rsp+64h] [rbp-25h]
  __int64 v16; // [rsp+68h] [rbp-21h]
  _BYTE v17[32]; // [rsp+70h] [rbp-19h] BYREF
  wchar_t *String; // [rsp+90h] [rbp+7h]
  unsigned int v19; // [rsp+A0h] [rbp+17h]

  v12 = 0;
  v13[0] = 0;
  v13[4] = v13;
  v14 = 32;
  v15 = 256;
  v16 = 0;
  STRU::STRU((STRU *)v17);
  if ( *(_QWORD *)this )
  {
    matched = STRU::Copy((STRU *)v17, a3);
    if ( matched < 0 )
    {
LABEL_3:
      STRU::~STRU((STRU *)v17);
      BUFFER::~BUFFER((BUFFER *)v13);
      return (unsigned int)matched;
    }
    _wcslwr(String);
    for ( i = *(DAV_AUTH_RULES_ENTRY **)this; i; i = *(DAV_AUTH_RULES_ENTRY **)i )
    {
      matched = DAV_AUTH_RULES_ENTRY::MatchRule(i, a2, (struct AUTH_ACCOUNT_SID *)v13, String, v19, &v12);
      if ( matched < 0 )
        goto LABEL_3;
      if ( v12 )
      {
        v10 = *((_DWORD *)i + 30);
        goto LABEL_10;
      }
    }
  }
  v10 = *((_DWORD *)this + 20);
LABEL_10:
  *a4 = v10;
  STRU::~STRU((STRU *)v17);
  BUFFER::~BUFFER((BUFFER *)v13);
  return 0;
}

```

## disassembly

```asm
0x180006310  push    rbp
0x180006312  push    rbx
0x180006313  push    rsi
0x180006314  push    rdi
0x180006315  push    r14
0x180006317  push    r15
0x180006319  lea     rbp, [rsp-2Fh]
0x18000631e  sub     rsp, 0B8h
0x180006325  mov     rax, cs:__security_cookie
0x18000632c  xor     rax, rsp
0x18000632f  mov     [rbp+57h+var_38], rax
0x180006333  mov     rsi, rcx
0x180006336  mov     [rbp+57h+var_B0], 0
0x18000633d  lea     rax, [rbp+57h+var_A8]
0x180006341  mov     [rbp+57h+var_A8], 0
0x180006349  lea     rcx, [rbp+57h+var_70]
0x18000634d  mov     [rbp+57h+var_88], rax
0x180006351  mov     r14, r9
0x180006354  mov     [rbp+57h+var_80], 20h ; ' '
0x18000635b  mov     rbx, r8
0x18000635e  mov     [rbp+57h+var_7C], 100h
0x180006364  mov     r15, rdx
0x180006367  mov     [rbp+57h+var_78], 0
0x18000636f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006375  cmp     qword ptr [rsi], 0
0x180006379  lea     rcx, [rbp+57h+var_70]
0x18000637d  jz      short loc_1800063EE
0x18000637f  mov     rdx, rbx
0x180006382  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006388  mov     ebx, eax
0x18000638a  test    eax, eax
0x18000638c  jns     short loc_1800063A4
0x18000638e  lea     rcx, [rbp+57h+var_70]
0x180006392  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006398  lea     rcx, [rbp+57h+var_A8]
0x18000639c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800063a2  jmp     short loc_180006406
0x1800063a4  mov     rcx, [rbp+57h+String]; String
0x1800063a8  call    cs:__imp__wcslwr
0x1800063ae  mov     rdi, [rsi]
0x1800063b1  jmp     short loc_1800063E5
0x1800063b3  mov     eax, [rbp+57h+var_40]
0x1800063b6  lea     rcx, [rbp+57h+var_B0]
0x1800063ba  mov     r9, [rbp+57h+String]; unsigned __int16 *
0x1800063be  lea     r8, [rbp+57h+var_A8]; struct AUTH_ACCOUNT_SID *
0x1800063c2  mov     [rsp+0E0h+var_B8], rcx; int *
0x1800063c7  mov     rdx, r15; struct IHttpUser *
0x1800063ca  mov     rcx, rdi; this
0x1800063cd  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x1800063d1  call    ?MatchRule@DAV_AUTH_RULES_ENTRY@@QEAAJPEAVIHttpUser@@PEAVAUTH_ACCOUNT_SID@@PEBGKPEAH@Z; DAV_AUTH_RULES_ENTRY::MatchRule(IHttpUser *,AUTH_ACCOUNT_SID *,ushort const *,ulong,int *)
0x1800063d6  mov     ebx, eax
0x1800063d8  test    eax, eax
0x1800063da  js      short loc_18000638E
0x1800063dc  cmp     [rbp+57h+var_B0], 0
0x1800063e0  jnz     short loc_180006424
0x1800063e2  mov     rdi, [rdi]
0x1800063e5  test    rdi, rdi
0x1800063e8  jnz     short loc_1800063B3
0x1800063ea  lea     rcx, [rbp+57h+var_70]
0x1800063ee  mov     eax, [rsi+50h]
0x1800063f1  mov     [r14], eax
0x1800063f4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800063fa  lea     rcx, [rbp+57h+var_A8]
0x1800063fe  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180006404  xor     ebx, ebx
0x180006406  mov     eax, ebx
0x180006408  mov     rcx, [rbp+57h+var_38]
0x18000640c  xor     rcx, rsp; StackCookie
0x18000640f  call    __security_check_cookie
0x180006414  add     rsp, 0B8h
0x18000641b  pop     r15
0x18000641d  pop     r14
0x18000641f  pop     rdi
0x180006420  pop     rsi
0x180006421  pop     rbx
0x180006422  pop     rbp
0x180006423  retn
0x180006424  mov     eax, [rdi+78h]
0x180006427  lea     rcx, [rbp+57h+var_70]
0x18000642b  jmp     short loc_1800063F1
```
