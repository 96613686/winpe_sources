# User::IsLocalSystem(void)

- ea: `0x18002adcc`
- end: `0x18002ae8a`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `190`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002ad84`

## callees

- `0x180008d30`
- `0x18002adcc`
- `0x18004e49c`
- `0x18004e510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ae13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ade8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ade8`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ae04`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ae04`

## pseudocode

```c
bool __fastcall User::IsLocalSystem(User *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  void *v3; // rcx
  bool IsLocalSystem; // di
  wchar_t *v6; // rcx
  wchar_t *v7; // rcx
  wchar_t **v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this )
    goto LABEL_6;
  v3 = *(void **)(*(_QWORD *)this + 32LL);
  if ( v3 )
  {
    IsLocalSystem = IsWellKnownSid(v3, WinLocalSystemSid);
    goto LABEL_4;
  }
  User::GetDomainAccount(this, &v8);
  if ( !v8 || !*v8 || (!v8 ? (v6 = 0) : (v6 = *v8), !*v6) )
  {
    _bstr_t::_Free((_bstr_t *)&v8);
LABEL_6:
    IsLocalSystem = 0;
    goto LABEL_4;
  }
  if ( v8 )
    v7 = *v8;
  else
    v7 = 0;
  IsLocalSystem = User::IsLocalSystem(v7);
  _bstr_t::_Free((_bstr_t *)&v8);
LABEL_4:
  LeaveCriticalSection(v1);
  return IsLocalSystem;
}

```

## disassembly

```asm
0x18002adcc  mov     [rsp+arg_8], rbx
0x18002add1  mov     [rsp+arg_10], rsi
0x18002add6  push    rdi
0x18002add7  sub     rsp, 20h
0x18002addb  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002ade2  mov     rdi, rcx
0x18002ade5  mov     rcx, rbx; lpCriticalSection
0x18002ade8  call    cs:__imp_EnterCriticalSection
0x18002adee  mov     rax, [rdi]
0x18002adf1  xor     esi, esi
0x18002adf3  test    rax, rax
0x18002adf6  jz      short loc_18002AE36
0x18002adf8  mov     rcx, [rax+20h]; pSid
0x18002adfc  test    rcx, rcx
0x18002adff  jz      short loc_18002AE3B
0x18002ae01  lea     edx, [rsi+16h]; WellKnownSidType
0x18002ae04  call    cs:__imp_IsWellKnownSid
0x18002ae0a  test    eax, eax
0x18002ae0c  setnz   dil
0x18002ae10  mov     rcx, rbx; lpCriticalSection
0x18002ae13  call    cs:__imp_LeaveCriticalSection
0x18002ae19  mov     rbx, [rsp+28h+arg_8]
0x18002ae1e  mov     al, dil
0x18002ae21  mov     rsi, [rsp+28h+arg_10]
0x18002ae26  add     rsp, 20h
0x18002ae2a  pop     rdi
0x18002ae2b  retn
0x18002ae2c  lea     rcx, [rsp+28h+arg_0]; this
0x18002ae31  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ae36  mov     dil, sil
0x18002ae39  jmp     short loc_18002AE10
0x18002ae3b  lea     rdx, [rsp+28h+arg_0]
0x18002ae40  mov     rcx, rdi
0x18002ae43  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x18002ae48  mov     rax, [rsp+28h+arg_0]
0x18002ae4d  test    rax, rax
0x18002ae50  jz      short loc_18002AE2C
0x18002ae52  cmp     [rax], rsi
0x18002ae55  jz      short loc_18002AE2C
0x18002ae57  test    rax, rax
0x18002ae5a  jz      short loc_18002AE80
0x18002ae5c  mov     rcx, [rax]
0x18002ae5f  cmp     [rcx], si
0x18002ae62  jz      short loc_18002AE2C
0x18002ae64  test    rax, rax
0x18002ae67  jz      short loc_18002AE85
0x18002ae69  mov     rcx, [rax]; String1
0x18002ae6c  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x18002ae71  lea     rcx, [rsp+28h+arg_0]; this
0x18002ae76  mov     dil, al
0x18002ae79  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ae7e  jmp     short loc_18002AE10
0x18002ae80  mov     rcx, rsi
0x18002ae83  jmp     short loc_18002AE5F
0x18002ae85  mov     rcx, rsi
0x18002ae88  jmp     short loc_18002AE6C
```
