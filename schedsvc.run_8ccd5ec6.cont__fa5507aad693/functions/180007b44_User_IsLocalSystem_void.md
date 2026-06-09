# User::IsLocalSystem(void)

- ea: `0x180007b44`
- end: `0x180007c1e`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `218`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003310`
- `0x180006a10`
- `0x180006a74`
- `0x180006ac0`
- `0x180025a3c`
- `0x180047ee0`
- `0x1800793bc`
- `0x18007b33c`

## callees

- `0x180007b44`
- `0x180011e40`
- `0x1800433ac`
- `0x18006a6b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b60`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180007baa`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180007baa`

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
0x180007b44  mov     [rsp+arg_8], rbx
0x180007b49  mov     [rsp+arg_10], rsi
0x180007b4e  push    rdi
0x180007b4f  sub     rsp, 20h
0x180007b53  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180007b5a  mov     rdi, rcx
0x180007b5d  mov     rcx, rbx; lpCriticalSection
0x180007b60  call    cs:__imp_EnterCriticalSection
0x180007b67  nop     dword ptr [rax+rax+00h]
0x180007b6c  mov     rax, [rdi]
0x180007b6f  xor     esi, esi
0x180007b71  test    rax, rax
0x180007b74  jnz     short loc_180007B9C
0x180007b76  mov     dil, sil
0x180007b79  mov     rcx, rbx; lpCriticalSection
0x180007b7c  call    cs:__imp_LeaveCriticalSection
0x180007b83  nop     dword ptr [rax+rax+00h]
0x180007b88  mov     rbx, [rsp+28h+arg_8]
0x180007b8d  mov     al, dil
0x180007b90  mov     rsi, [rsp+28h+arg_10]
0x180007b95  add     rsp, 20h
0x180007b99  pop     rdi
0x180007b9a  retn
0x180007b9c  mov     rcx, [rax+20h]; pSid
0x180007ba0  test    rcx, rcx
0x180007ba3  jz      short loc_180007BBE
0x180007ba5  mov     edx, 16h; WellKnownSidType
0x180007baa  call    cs:__imp_IsWellKnownSid
0x180007bb1  nop     dword ptr [rax+rax+00h]
0x180007bb6  test    eax, eax
0x180007bb8  setnz   dil
0x180007bbc  jmp     short loc_180007B79
0x180007bbe  lea     rdx, [rsp+28h+arg_0]
0x180007bc3  mov     rcx, rdi
0x180007bc6  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180007bcb  mov     rax, [rsp+28h+arg_0]
0x180007bd0  test    rax, rax
0x180007bd3  jnz     short loc_180007C17
0x180007bd5  lea     rcx, [rsp+28h+arg_0]; this
0x180007bda  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180007bdf  jmp     short loc_180007B76
0x180007be1  test    rax, rax
0x180007be4  jz      short loc_180007C0D
0x180007be6  mov     rcx, [rax]
0x180007be9  cmp     [rcx], si
0x180007bec  jz      short loc_180007BD5
0x180007bee  test    rax, rax
0x180007bf1  jz      short loc_180007C12
0x180007bf3  mov     rcx, [rax]; String1
0x180007bf6  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x180007bfb  lea     rcx, [rsp+28h+arg_0]; this
0x180007c00  mov     dil, al
0x180007c03  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180007c08  jmp     loc_180007B79
0x180007c0d  mov     rcx, rsi
0x180007c10  jmp     short loc_180007BE9
0x180007c12  mov     rcx, rsi
0x180007c15  jmp     short loc_180007BF6
0x180007c17  cmp     [rax], rsi
0x180007c1a  jz      short loc_180007BD5
0x180007c1c  jmp     short loc_180007BE1
```
