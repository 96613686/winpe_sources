# User::operator==(User const &)

- ea: `0x180054130`
- end: `0x18005424c`
- name: `??8User@@QEBA_NAEBV0@@Z`
- size: `284`
- prototype: `__int64 __fastcall(User *this, User *)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003310`
- `0x180047ee0`
- `0x18004d704`
- `0x18004e9d0`
- `0x1800534c8`
- `0x1800535dc`
- `0x180053748`
- `0x180056fe0`
- `0x18007c724`

## callees

- `0x1800449bc`
- `0x18004595c`
- `0x180054130`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180054201`
- `msvcrt!_wcsicmp` at `0x180054201`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005422c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005422c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005414f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005414f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800541b4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800541b4`

## pseudocode

```c
bool __fastcall User::operator==(User *this, User *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  bool v7; // di
  void *v8; // rcx
  void *v9; // rdx
  int v10; // eax
  __int64 v11; // r8
  const wchar_t ***v12; // rcx
  __int64 v13; // r9
  const wchar_t *v14; // rdx
  const wchar_t **v15; // rax
  const wchar_t *v16; // rcx

  v2 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  if ( !*(_QWORD *)this )
  {
    if ( *(_QWORD *)a2 )
      goto LABEL_24;
    goto LABEL_8;
  }
  if ( !*(_QWORD *)a2 )
  {
LABEL_24:
    v7 = 0;
    goto LABEL_25;
  }
  if ( User::IsAlias(this) || User::IsAlias(a2) )
  {
    if ( !User::IsAlias(this) || !User::IsAlias(a2) )
      goto LABEL_24;
    goto LABEL_13;
  }
  if ( v5 != v6 )
  {
    v8 = *(void **)(v6 + 32);
    if ( v8 )
    {
      v9 = *(void **)(v5 + 32);
      if ( v9 )
      {
        v10 = EqualSid(v8, v9);
LABEL_12:
        v7 = v10 != 0;
        goto LABEL_25;
      }
    }
LABEL_13:
    if ( (unsigned __int8)_bstr_t::operator!(v6 + 8) || (unsigned __int8)_bstr_t::operator!(v11 + 8) )
      goto LABEL_24;
    if ( *v12 )
      v14 = **v12;
    else
      v14 = 0;
    v15 = *(const wchar_t ***)(v13 + 8);
    if ( v15 )
      v16 = *v15;
    else
      v16 = 0;
    v10 = _wcsicmp(v16, v14);
    goto LABEL_12;
  }
LABEL_8:
  v7 = 1;
LABEL_25:
  LeaveCriticalSection(v2);
  return v7;
}

```

## disassembly

```asm
0x180054130  mov     [rsp+arg_0], rbx
0x180054135  mov     [rsp+arg_8], rsi
0x18005413a  push    rdi
0x18005413b  sub     rsp, 20h
0x18005413f  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180054146  mov     rsi, rcx
0x180054149  mov     rcx, rbx; lpCriticalSection
0x18005414c  mov     rdi, rdx
0x18005414f  call    cs:__imp_EnterCriticalSection
0x180054156  nop     dword ptr [rax+rax+00h]
0x18005415b  mov     r9, [rsi]
0x18005415e  test    r9, r9
0x180054161  jnz     short loc_18005416D
0x180054163  cmp     [rdi], r9
0x180054166  jz      short loc_18005419A
0x180054168  jmp     loc_180054227
0x18005416d  mov     r8, [rdi]
0x180054170  test    r8, r8
0x180054173  jz      loc_180054227
0x180054179  mov     rcx, rsi; this
0x18005417c  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180054181  test    al, al
0x180054183  jnz     loc_18005420F
0x180054189  mov     rcx, rdi; this
0x18005418c  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180054191  test    al, al
0x180054193  jnz     short loc_18005420F
0x180054195  cmp     r8, r9
0x180054198  jnz     short loc_1800541A2
0x18005419a  mov     dil, 1
0x18005419d  jmp     loc_180054229
0x1800541a2  mov     rcx, [r9+20h]; pSid1
0x1800541a6  test    rcx, rcx
0x1800541a9  jz      short loc_1800541C8
0x1800541ab  mov     rdx, [r8+20h]; pSid2
0x1800541af  test    rdx, rdx
0x1800541b2  jz      short loc_1800541C8
0x1800541b4  call    cs:__imp_EqualSid
0x1800541bb  nop     dword ptr [rax+rax+00h]
0x1800541c0  test    eax, eax
0x1800541c2  setnz   dil
0x1800541c6  jmp     short loc_180054229
0x1800541c8  lea     rcx, [r9+8]
0x1800541cc  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x1800541d1  test    al, al
0x1800541d3  jnz     short loc_180054227
0x1800541d5  lea     rcx, [r8+8]
0x1800541d9  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x1800541de  test    al, al
0x1800541e0  jnz     short loc_180054227
0x1800541e2  mov     rax, [rcx]
0x1800541e5  test    rax, rax
0x1800541e8  jz      short loc_1800541EF
0x1800541ea  mov     rdx, [rax]
0x1800541ed  jmp     short loc_1800541F1
0x1800541ef  xor     edx, edx; String2
0x1800541f1  mov     rax, [r9+8]
0x1800541f5  test    rax, rax
0x1800541f8  jz      short loc_1800541FF
0x1800541fa  mov     rcx, [rax]
0x1800541fd  jmp     short loc_180054201
0x1800541ff  xor     ecx, ecx; String1
0x180054201  call    cs:__imp__wcsicmp
0x180054208  nop     dword ptr [rax+rax+00h]
0x18005420d  jmp     short loc_1800541C0
0x18005420f  mov     rcx, rsi; this
0x180054212  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180054217  test    al, al
0x180054219  jz      short loc_180054227
0x18005421b  mov     rcx, rdi; this
0x18005421e  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180054223  test    al, al
0x180054225  jnz     short loc_1800541C8
0x180054227  xor     edi, edi
0x180054229  mov     rcx, rbx; lpCriticalSection
0x18005422c  call    cs:__imp_LeaveCriticalSection
0x180054233  nop     dword ptr [rax+rax+00h]
0x180054238  mov     rbx, [rsp+28h+arg_0]
0x18005423d  mov     al, dil
0x180054240  mov     rsi, [rsp+28h+arg_8]
0x180054245  add     rsp, 20h
0x180054249  pop     rdi
0x18005424a  retn
```
