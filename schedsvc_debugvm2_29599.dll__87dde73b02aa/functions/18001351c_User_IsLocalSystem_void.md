# User::IsLocalSystem(void)

- ea: `0x18001351c`
- end: `0x1800135e3`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `199`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001233c`
- `0x18001239c`
- `0x1800123e0`
- `0x18002c1b0`
- `0x18002f040`
- `0x180045df0`
- `0x18007545c`
- `0x1800772d0`

## callees

- `0x18000dc30`
- `0x18001351c`
- `0x180016e3c`
- `0x180067438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001354e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001354e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013538`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013538`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180013575`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180013575`

## pseudocode

```c
bool __fastcall User::IsLocalSystem(User *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  bool IsLocalSystem; // di
  void *v5; // rcx
  wchar_t *v6; // rcx
  wchar_t *v7; // rcx
  wchar_t **v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this )
    goto LABEL_2;
  v5 = *(void **)(*(_QWORD *)this + 32LL);
  if ( v5 )
  {
    IsLocalSystem = IsWellKnownSid(v5, WinLocalSystemSid);
    goto LABEL_3;
  }
  User::GetDomainAccount(this, &v8);
  if ( !v8 || !*v8 || (!v8 ? (v6 = 0) : (v6 = *v8), !*v6) )
  {
    _bstr_t::~_bstr_t((_bstr_t *)&v8);
LABEL_2:
    IsLocalSystem = 0;
    goto LABEL_3;
  }
  if ( v8 )
    v7 = *v8;
  else
    v7 = 0;
  IsLocalSystem = User::IsLocalSystem(v7);
  _bstr_t::~_bstr_t((_bstr_t *)&v8);
LABEL_3:
  LeaveCriticalSection(v1);
  return IsLocalSystem;
}

```

## disassembly

```asm
0x18001351c  mov     [rsp+arg_8], rbx
0x180013521  mov     [rsp+arg_10], rsi
0x180013526  push    rdi
0x180013527  sub     rsp, 20h
0x18001352b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180013532  mov     rdi, rcx
0x180013535  mov     rcx, rbx; lpCriticalSection
0x180013538  call    cs:__imp_EnterCriticalSection
0x18001353e  mov     rax, [rdi]
0x180013541  xor     esi, esi
0x180013543  test    rax, rax
0x180013546  jnz     short loc_180013567
0x180013548  mov     dil, sil
0x18001354b  mov     rcx, rbx; lpCriticalSection
0x18001354e  call    cs:__imp_LeaveCriticalSection
0x180013554  mov     rbx, [rsp+28h+arg_8]
0x180013559  mov     al, dil
0x18001355c  mov     rsi, [rsp+28h+arg_10]
0x180013561  add     rsp, 20h
0x180013565  pop     rdi
0x180013566  retn
0x180013567  mov     rcx, [rax+20h]; pSid
0x18001356b  test    rcx, rcx
0x18001356e  jz      short loc_180013583
0x180013570  mov     edx, 16h; WellKnownSidType
0x180013575  call    cs:__imp_IsWellKnownSid
0x18001357b  test    eax, eax
0x18001357d  setnz   dil
0x180013581  jmp     short loc_18001354B
0x180013583  lea     rdx, [rsp+28h+arg_0]
0x180013588  mov     rcx, rdi
0x18001358b  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180013590  mov     rax, [rsp+28h+arg_0]
0x180013595  test    rax, rax
0x180013598  jnz     short loc_1800135DC
0x18001359a  lea     rcx, [rsp+28h+arg_0]; this
0x18001359f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800135a4  jmp     short loc_180013548
0x1800135a6  test    rax, rax
0x1800135a9  jz      short loc_1800135D2
0x1800135ab  mov     rcx, [rax]
0x1800135ae  cmp     [rcx], si
0x1800135b1  jz      short loc_18001359A
0x1800135b3  test    rax, rax
0x1800135b6  jz      short loc_1800135D7
0x1800135b8  mov     rcx, [rax]; String1
0x1800135bb  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x1800135c0  lea     rcx, [rsp+28h+arg_0]; this
0x1800135c5  mov     dil, al
0x1800135c8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800135cd  jmp     loc_18001354B
0x1800135d2  mov     rcx, rsi
0x1800135d5  jmp     short loc_1800135AE
0x1800135d7  mov     rcx, rsi
0x1800135da  jmp     short loc_1800135BB
0x1800135dc  cmp     [rax], rsi
0x1800135df  jz      short loc_18001359A
0x1800135e1  jmp     short loc_1800135A6
```
