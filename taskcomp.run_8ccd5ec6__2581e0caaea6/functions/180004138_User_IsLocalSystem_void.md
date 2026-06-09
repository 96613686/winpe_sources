# User::IsLocalSystem(void)

- ea: `0x180004138`
- end: `0x180004209`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `209`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800036a0`
- `0x180004a40`
- `0x18000b218`
- `0x180016620`
- `0x18001bcc0`

## callees

- `0x180004138`
- `0x1800050d0`
- `0x1800052d8`
- `0x180005354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004154`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004154`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800041e9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180004176`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180004176`

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
0x180004138  mov     [rsp+arg_8], rbx
0x18000413d  mov     [rsp+arg_10], rsi
0x180004142  push    rdi
0x180004143  sub     rsp, 20h
0x180004147  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000414e  mov     rdi, rcx
0x180004151  mov     rcx, rbx; lpCriticalSection
0x180004154  call    cs:__imp_EnterCriticalSection
0x18000415b  nop     dword ptr [rax+rax+00h]
0x180004160  mov     rax, [rdi]
0x180004163  xor     esi, esi
0x180004165  test    rax, rax
0x180004168  jz      short loc_1800041E3
0x18000416a  mov     rcx, [rax+20h]; pSid
0x18000416e  test    rcx, rcx
0x180004171  jz      short loc_18000418A
0x180004173  lea     edx, [rsi+16h]; WellKnownSidType
0x180004176  call    cs:__imp_IsWellKnownSid
0x18000417d  nop     dword ptr [rax+rax+00h]
0x180004182  test    eax, eax
0x180004184  setnz   dil
0x180004188  jmp     short loc_1800041E6
0x18000418a  lea     rdx, [rsp+28h+arg_0]
0x18000418f  mov     rcx, rdi
0x180004192  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180004197  mov     rax, [rsp+28h+arg_0]
0x18000419c  test    rax, rax
0x18000419f  jz      short loc_1800041D9
0x1800041a1  cmp     [rax], rsi
0x1800041a4  jz      short loc_1800041D9
0x1800041a6  test    rax, rax
0x1800041a9  jz      short loc_1800041B0
0x1800041ab  mov     rcx, [rax]
0x1800041ae  jmp     short loc_1800041B3
0x1800041b0  mov     rcx, rsi
0x1800041b3  cmp     [rcx], si
0x1800041b6  jz      short loc_1800041D9
0x1800041b8  test    rax, rax
0x1800041bb  jz      short loc_1800041C2
0x1800041bd  mov     rcx, [rax]
0x1800041c0  jmp     short loc_1800041C5
0x1800041c2  mov     rcx, rsi; String1
0x1800041c5  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x1800041ca  lea     rcx, [rsp+28h+arg_0]; this
0x1800041cf  mov     dil, al
0x1800041d2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800041d7  jmp     short loc_1800041E6
0x1800041d9  lea     rcx, [rsp+28h+arg_0]; this
0x1800041de  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800041e3  mov     dil, sil
0x1800041e6  mov     rcx, rbx; lpCriticalSection
0x1800041e9  call    cs:__imp_LeaveCriticalSection
0x1800041f0  nop     dword ptr [rax+rax+00h]
0x1800041f5  mov     rbx, [rsp+28h+arg_8]
0x1800041fa  mov     al, dil
0x1800041fd  mov     rsi, [rsp+28h+arg_10]
0x180004202  add     rsp, 20h
0x180004206  pop     rdi
0x180004207  retn
```
