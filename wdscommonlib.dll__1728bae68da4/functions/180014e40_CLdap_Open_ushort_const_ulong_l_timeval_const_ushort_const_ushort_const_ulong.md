# CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)

- ea: `0x180014e40`
- end: `0x180014fab`
- name: `?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z`
- size: `363`
- prototype: `unsigned int __usercall@<eax>(CLdap *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const struct l_timeval *@<r9>, PWSTR dn, PWCHAR cred, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180015310`
- `0x18001f2c0`

## callees

- `0x180004df4`
- `0x180014a20`
- `0x180014e40`
- `0x180015290`
- `0x1800154f8`
- `0x180031010`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014f16`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014f65`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014f16`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014f65`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180014f4a`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180014f4a`
- `WLDAP32!__imp_ldap_connect` at `0x180014efb`
- `WLDAP32!__imp_ldap_connect` at `0x180014efb`

## string_xrefs

- `0x180014e9d`: `CLdap::Open: Server=%s, Port=%u, DN=%s\n`

## pseudocode

```c
__int64 __fastcall CLdap::Open(
        CLdap *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct l_timeval *a4,
        PWSTR dn,
        PWCHAR cred,
        ULONG method)
{
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  const wchar_t *v14; // rdx
  const wchar_t *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  struct l_timeval *p_timeout; // rdx
  ULONG v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  ULONG v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  ULONG v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  ULONG v28; // eax
  ULONG v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  struct l_timeval timeout; // [rsp+30h] [rbp-18h] BYREF

  v11 = CLdap::Shutdown(this);
  if ( !(unsigned int)ElValidateWin32_5(v11, v12, v13, 0xC7u) )
  {
    if ( g_ErrLibTraceFunction )
    {
      v14 = &psz;
      v15 = &psz;
      if ( dn )
        v15 = dn;
      if ( a2 )
        v14 = a2;
      g_ErrLibTraceFunction(L"CLdap::Open: Server=%s, Port=%u, DN=%s\n", v14, a3, v15);
    }
    v11 = CLdap::Initialize(this, a2, a3);
    if ( !(unsigned int)ElValidateWin32_5(v11, v16, v17, 0xD6u) )
    {
      timeout = 0;
      p_timeout = 0;
      if ( a4 )
      {
        p_timeout = &timeout;
        timeout = *a4;
      }
      v19 = ldap_connect(*(LDAP **)this, p_timeout);
      v22 = ElValidateWin32(v19, v20, v21, 0xB9u);
      v11 = LdapMapErrorToWin32(v22);
      if ( !(unsigned int)ElValidateWin32_5(v11, v23, v24, 0xDDu) )
      {
        v25 = ldap_bind_sW(*(LDAP **)this, dn, cred, method);
        v28 = ElValidateWin32(v25, v26, v27, 0xCAu);
        v29 = LdapMapErrorToWin32(v28);
        v11 = ElValidateWin32_5(v29, v30, v31, 0xE3u);
        ElValidateWin32_5(v11, v32, v33, 0xE4u);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180014e40  mov     rax, rsp
0x180014e43  mov     [rax+8], rbx
0x180014e47  mov     [rax+10h], rbp
0x180014e4b  mov     [rax+18h], rsi
0x180014e4f  mov     [rax+20h], rdi
0x180014e53  push    r15
0x180014e55  sub     rsp, 40h
0x180014e59  mov     rdi, r9
0x180014e5c  mov     r15d, r8d
0x180014e5f  mov     rbp, rdx
0x180014e62  mov     rsi, rcx
0x180014e65  call    ?Shutdown@CLdap@@QEAAKXZ; CLdap::Shutdown(void)
0x180014e6a  mov     r9d, 0C7h
0x180014e70  mov     ecx, eax
0x180014e72  mov     ebx, eax
0x180014e74  call    ElValidateWin32_5
0x180014e79  test    eax, eax
0x180014e7b  jnz     loc_180014F8D
0x180014e81  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014e88  test    rax, rax
0x180014e8b  jz      short loc_180014EB9
0x180014e8d  cmp     [rsp+48h+dn], 0
0x180014e93  lea     rdx, psz
0x180014e9a  mov     r9, rdx
0x180014e9d  lea     rcx, aCldapOpenServe; "CLdap::Open: Server=%s, Port=%u, DN=%s"...
0x180014ea4  cmovnz  r9, [rsp+48h+dn]
0x180014eaa  mov     r8d, r15d
0x180014ead  test    rbp, rbp
0x180014eb0  cmovnz  rdx, rbp
0x180014eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb9  mov     r8d, r15d; unsigned int
0x180014ebc  mov     rdx, rbp; unsigned __int16 *
0x180014ebf  mov     rcx, rsi; this
0x180014ec2  call    ?Initialize@CLdap@@QEAAKPEBGK@Z; CLdap::Initialize(ushort const *,ulong)
0x180014ec7  mov     r9d, 0D6h
0x180014ecd  mov     ecx, eax
0x180014ecf  mov     ebx, eax
0x180014ed1  call    ElValidateWin32_5
0x180014ed6  test    eax, eax
0x180014ed8  jnz     loc_180014F8D
0x180014ede  and     qword ptr [rsp+48h+timeout.tv_sec], 0
0x180014ee4  xor     edx, edx
0x180014ee6  test    rdi, rdi
0x180014ee9  jz      short loc_180014EF8
0x180014eeb  mov     rax, [rdi]
0x180014eee  lea     rdx, [rsp+48h+timeout]; timeout
0x180014ef3  mov     qword ptr [rsp+48h+timeout.tv_sec], rax
0x180014ef8  mov     rcx, [rsi]; ld
0x180014efb  call    cs:__imp_ldap_connect
0x180014f02  nop     dword ptr [rax+rax+00h]
0x180014f07  mov     ecx, eax
0x180014f09  mov     r9d, 0B9h
0x180014f0f  call    ElValidateWin32
0x180014f14  mov     ecx, eax; LdapError
0x180014f16  call    cs:__imp_LdapMapErrorToWin32
0x180014f1d  nop     dword ptr [rax+rax+00h]
0x180014f22  mov     ecx, eax
0x180014f24  mov     r9d, 0DDh
0x180014f2a  mov     ebx, eax
0x180014f2c  call    ElValidateWin32_5
0x180014f31  test    eax, eax
0x180014f33  jnz     short loc_180014F8D
0x180014f35  mov     r9d, [rsp+48h+method]; method
0x180014f3d  mov     r8, [rsp+48h+cred]; cred
0x180014f42  mov     rdx, [rsp+48h+dn]; dn
0x180014f47  mov     rcx, [rsi]; ld
0x180014f4a  call    cs:__imp_ldap_bind_sW
0x180014f51  nop     dword ptr [rax+rax+00h]
0x180014f56  mov     ecx, eax
0x180014f58  mov     r9d, 0CAh
0x180014f5e  call    ElValidateWin32
0x180014f63  mov     ecx, eax; LdapError
0x180014f65  call    cs:__imp_LdapMapErrorToWin32
0x180014f6c  nop     dword ptr [rax+rax+00h]
0x180014f71  mov     ecx, eax
0x180014f73  mov     r9d, 0E3h
0x180014f79  call    ElValidateWin32_5
0x180014f7e  mov     r9d, 0E4h
0x180014f84  mov     ecx, eax
0x180014f86  mov     ebx, eax
0x180014f88  call    ElValidateWin32_5
0x180014f8d  mov     rbp, [rsp+48h+arg_8]
0x180014f92  mov     eax, ebx
0x180014f94  mov     rbx, [rsp+48h+arg_0]
0x180014f99  mov     rsi, [rsp+48h+arg_10]
0x180014f9e  mov     rdi, [rsp+48h+arg_18]
0x180014fa3  add     rsp, 40h
0x180014fa7  pop     r15
0x180014fa9  retn
```
