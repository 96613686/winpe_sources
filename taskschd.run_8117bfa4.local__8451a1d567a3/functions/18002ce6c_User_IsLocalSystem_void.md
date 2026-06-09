# User::IsLocalSystem(void)

- ea: `0x18002ce6c`
- end: `0x18002cf3d`
- name: `?IsLocalSystem@User@@QEBA_NXZ`
- size: `209`
- prototype: `bool __fastcall(User *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002ce24`

## callees

- `0x180009150`
- `0x18002ce6c`
- `0x18005213c`
- `0x1800521b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cebf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cebf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ce88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ce88`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ceaa`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ceaa`

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
0x18002ce6c  mov     [rsp+arg_8], rbx
0x18002ce71  mov     [rsp+arg_10], rsi
0x18002ce76  push    rdi
0x18002ce77  sub     rsp, 20h
0x18002ce7b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002ce82  mov     rdi, rcx
0x18002ce85  mov     rcx, rbx; lpCriticalSection
0x18002ce88  call    cs:__imp_EnterCriticalSection
0x18002ce8f  nop     dword ptr [rax+rax+00h]
0x18002ce94  mov     rax, [rdi]
0x18002ce97  xor     esi, esi
0x18002ce99  test    rax, rax
0x18002ce9c  jz      short loc_18002CEE9
0x18002ce9e  mov     rcx, [rax+20h]; pSid
0x18002cea2  test    rcx, rcx
0x18002cea5  jz      short loc_18002CEEE
0x18002cea7  lea     edx, [rsi+16h]; WellKnownSidType
0x18002ceaa  call    cs:__imp_IsWellKnownSid
0x18002ceb1  nop     dword ptr [rax+rax+00h]
0x18002ceb6  test    eax, eax
0x18002ceb8  setnz   dil
0x18002cebc  mov     rcx, rbx; lpCriticalSection
0x18002cebf  call    cs:__imp_LeaveCriticalSection
0x18002cec6  nop     dword ptr [rax+rax+00h]
0x18002cecb  mov     rbx, [rsp+28h+arg_8]
0x18002ced0  mov     al, dil
0x18002ced3  mov     rsi, [rsp+28h+arg_10]
0x18002ced8  add     rsp, 20h
0x18002cedc  pop     rdi
0x18002cedd  retn
0x18002cedf  lea     rcx, [rsp+28h+arg_0]; this
0x18002cee4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002cee9  mov     dil, sil
0x18002ceec  jmp     short loc_18002CEBC
0x18002ceee  lea     rdx, [rsp+28h+arg_0]
0x18002cef3  mov     rcx, rdi
0x18002cef6  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x18002cefb  mov     rax, [rsp+28h+arg_0]
0x18002cf00  test    rax, rax
0x18002cf03  jz      short loc_18002CEDF
0x18002cf05  cmp     [rax], rsi
0x18002cf08  jz      short loc_18002CEDF
0x18002cf0a  test    rax, rax
0x18002cf0d  jz      short loc_18002CF33
0x18002cf0f  mov     rcx, [rax]
0x18002cf12  cmp     [rcx], si
0x18002cf15  jz      short loc_18002CEDF
0x18002cf17  test    rax, rax
0x18002cf1a  jz      short loc_18002CF38
0x18002cf1c  mov     rcx, [rax]; String1
0x18002cf1f  call    ?IsLocalSystem@User@@SA_NPEBG@Z; User::IsLocalSystem(ushort const *)
0x18002cf24  lea     rcx, [rsp+28h+arg_0]; this
0x18002cf29  mov     dil, al
0x18002cf2c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002cf31  jmp     short loc_18002CEBC
0x18002cf33  mov     rcx, rsi
0x18002cf36  jmp     short loc_18002CF12
0x18002cf38  mov     rcx, rsi
0x18002cf3b  jmp     short loc_18002CF1F
```
