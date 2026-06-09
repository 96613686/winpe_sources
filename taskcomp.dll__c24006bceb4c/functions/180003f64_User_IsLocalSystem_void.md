# User::IsLocalSystem(void)

- ea: `0x180003f64`
- end: `0x180004022`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `190`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003500`
- `0x180004820`
- `0x18000ac28`
- `0x1800157e0`
- `0x18001a928`

## callees

- `0x180003f64`
- `0x180004e50`
- `0x180005034`
- `0x1800050a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004009`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004009`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180003f9c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180003f9c`

## pseudocode

```c
bool __fastcall User::IsLocalSystem(User *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  void *v3; // rcx
  bool IsLocalSystem; // di
  wchar_t *v5; // rcx
  wchar_t *v6; // rcx
  wchar_t **v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this )
    goto LABEL_15;
  v3 = *(void **)(*(_QWORD *)this + 32LL);
  if ( v3 )
  {
    IsLocalSystem = IsWellKnownSid(v3, WinLocalSystemSid);
    goto LABEL_16;
  }
  User::GetDomainAccount(this, &v8);
  if ( !v8 || !*v8 || (!v8 ? (v5 = 0) : (v5 = *v8), !*v5) )
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v8);
LABEL_15:
    IsLocalSystem = 0;
    goto LABEL_16;
  }
  if ( v8 )
    v6 = *v8;
  else
    v6 = 0;
  IsLocalSystem = User::IsLocalSystem(v6);
  _bstr_t::~_bstr_t((_bstr_t *)&v8);
LABEL_16:
  LeaveCriticalSection(v1);
  return IsLocalSystem;
}

```

## disassembly

```asm
0x180003f64  mov     [rsp+arg_8], rbx
0x180003f69  mov     [rsp+arg_10], rsi
0x180003f6e  push    rdi
0x180003f6f  sub     rsp, 20h
0x180003f73  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180003f7a  mov     rdi, rcx
0x180003f7d  mov     rcx, rbx; lpCriticalSection
0x180003f80  call    cs:__imp_EnterCriticalSection
0x180003f86  mov     rax, [rdi]
0x180003f89  xor     esi, esi
0x180003f8b  test    rax, rax
0x180003f8e  jz      short loc_180004003
0x180003f90  mov     rcx, [rax+20h]; pSid
0x180003f94  test    rcx, rcx
0x180003f97  jz      short loc_180003FAA
0x180003f99  lea     edx, [rsi+16h]; WellKnownSidType
0x180003f9c  call    cs:__imp_IsWellKnownSid
0x180003fa2  test    eax, eax
0x180003fa4  setnz   dil
0x180003fa8  jmp     short loc_180004006
0x180003faa  lea     rdx, [rsp+28h+arg_0]
0x180003faf  mov     rcx, rdi
0x180003fb2  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180003fb7  mov     rax, [rsp+28h+arg_0]
0x180003fbc  test    rax, rax
0x180003fbf  jz      short loc_180003FF9
0x180003fc1  cmp     [rax], rsi
0x180003fc4  jz      short loc_180003FF9
0x180003fc6  test    rax, rax
0x180003fc9  jz      short loc_180003FD0
0x180003fcb  mov     rcx, [rax]
0x180003fce  jmp     short loc_180003FD3
0x180003fd0  mov     rcx, rsi
0x180003fd3  cmp     [rcx], si
0x180003fd6  jz      short loc_180003FF9
0x180003fd8  test    rax, rax
0x180003fdb  jz      short loc_180003FE2
0x180003fdd  mov     rcx, [rax]
0x180003fe0  jmp     short loc_180003FE5
0x180003fe2  mov     rcx, rsi; String1
0x180003fe5  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x180003fea  lea     rcx, [rsp+28h+arg_0]; this
0x180003fef  mov     dil, al
0x180003ff2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003ff7  jmp     short loc_180004006
0x180003ff9  lea     rcx, [rsp+28h+arg_0]; this
0x180003ffe  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004003  mov     dil, sil
0x180004006  mov     rcx, rbx; lpCriticalSection
0x180004009  call    cs:__imp_LeaveCriticalSection
0x18000400f  mov     rbx, [rsp+28h+arg_8]
0x180004014  mov     al, dil
0x180004017  mov     rsi, [rsp+28h+arg_10]
0x18000401c  add     rsp, 20h
0x180004020  pop     rdi
0x180004021  retn
```
