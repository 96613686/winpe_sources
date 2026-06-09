# CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)

- ea: `0x180014170`
- end: `0x1800142db`
- name: `?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z`
- size: `363`
- prototype: `unsigned int __usercall@<eax>(CLdap *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const struct l_timeval *@<r9>, PWSTR dn, PWCHAR cred, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180014640`
- `0x18001e300`

## callees

- `0x180004344`
- `0x180013d60`
- `0x180014170`
- `0x1800145c0`
- `0x180014800`
- `0x180030010`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014246`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014295`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014246`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180014295`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001427a`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001427a`
- `WLDAP32!__imp_ldap_connect` at `0x18001422b`
- `WLDAP32!__imp_ldap_connect` at `0x18001422b`

## string_xrefs

- `0x1800141cd`: `CLdap::Open: Server=%s, Port=%u, DN=%s\n`

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
0x180014170  mov     rax, rsp
0x180014173  mov     [rax+8], rbx
0x180014177  mov     [rax+10h], rbp
0x18001417b  mov     [rax+18h], rsi
0x18001417f  mov     [rax+20h], rdi
0x180014183  push    r15
0x180014185  sub     rsp, 40h
0x180014189  mov     rdi, r9
0x18001418c  mov     r15d, r8d
0x18001418f  mov     rbp, rdx
0x180014192  mov     rsi, rcx
0x180014195  call    ?Shutdown@CLdap@@QEAAKXZ; CLdap::Shutdown(void)
0x18001419a  mov     r9d, 0C7h
0x1800141a0  mov     ecx, eax
0x1800141a2  mov     ebx, eax
0x1800141a4  call    ElValidateWin32_5
0x1800141a9  test    eax, eax
0x1800141ab  jnz     loc_1800142BD
0x1800141b1  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800141b8  test    rax, rax
0x1800141bb  jz      short loc_1800141E9
0x1800141bd  cmp     [rsp+48h+dn], 0
0x1800141c3  lea     rdx, psz
0x1800141ca  mov     r9, rdx
0x1800141cd  lea     rcx, aCldapOpenServe; "CLdap::Open: Server=%s, Port=%u, DN=%s"...
0x1800141d4  cmovnz  r9, [rsp+48h+dn]
0x1800141da  mov     r8d, r15d
0x1800141dd  test    rbp, rbp
0x1800141e0  cmovnz  rdx, rbp
0x1800141e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e9  mov     r8d, r15d; unsigned int
0x1800141ec  mov     rdx, rbp; unsigned __int16 *
0x1800141ef  mov     rcx, rsi; this
0x1800141f2  call    ?Initialize@CLdap@@QEAAKPEBGK@Z; CLdap::Initialize(ushort const *,ulong)
0x1800141f7  mov     r9d, 0D6h
0x1800141fd  mov     ecx, eax
0x1800141ff  mov     ebx, eax
0x180014201  call    ElValidateWin32_5
0x180014206  test    eax, eax
0x180014208  jnz     loc_1800142BD
0x18001420e  and     qword ptr [rsp+48h+timeout.tv_sec], 0
0x180014214  xor     edx, edx
0x180014216  test    rdi, rdi
0x180014219  jz      short loc_180014228
0x18001421b  mov     rax, [rdi]
0x18001421e  lea     rdx, [rsp+48h+timeout]; timeout
0x180014223  mov     qword ptr [rsp+48h+timeout.tv_sec], rax
0x180014228  mov     rcx, [rsi]; ld
0x18001422b  call    cs:__imp_ldap_connect
0x180014232  nop     dword ptr [rax+rax+00h]
0x180014237  mov     ecx, eax
0x180014239  mov     r9d, 0B9h
0x18001423f  call    ElValidateWin32
0x180014244  mov     ecx, eax; LdapError
0x180014246  call    cs:__imp_LdapMapErrorToWin32
0x18001424d  nop     dword ptr [rax+rax+00h]
0x180014252  mov     ecx, eax
0x180014254  mov     r9d, 0DDh
0x18001425a  mov     ebx, eax
0x18001425c  call    ElValidateWin32_5
0x180014261  test    eax, eax
0x180014263  jnz     short loc_1800142BD
0x180014265  mov     r9d, [rsp+48h+method]; method
0x18001426d  mov     r8, [rsp+48h+cred]; cred
0x180014272  mov     rdx, [rsp+48h+dn]; dn
0x180014277  mov     rcx, [rsi]; ld
0x18001427a  call    cs:__imp_ldap_bind_sW
0x180014281  nop     dword ptr [rax+rax+00h]
0x180014286  mov     ecx, eax
0x180014288  mov     r9d, 0CAh
0x18001428e  call    ElValidateWin32
0x180014293  mov     ecx, eax; LdapError
0x180014295  call    cs:__imp_LdapMapErrorToWin32
0x18001429c  nop     dword ptr [rax+rax+00h]
0x1800142a1  mov     ecx, eax
0x1800142a3  mov     r9d, 0E3h
0x1800142a9  call    ElValidateWin32_5
0x1800142ae  mov     r9d, 0E4h
0x1800142b4  mov     ecx, eax
0x1800142b6  mov     ebx, eax
0x1800142b8  call    ElValidateWin32_5
0x1800142bd  mov     rbp, [rsp+48h+arg_8]
0x1800142c2  mov     eax, ebx
0x1800142c4  mov     rbx, [rsp+48h+arg_0]
0x1800142c9  mov     rsi, [rsp+48h+arg_10]
0x1800142ce  mov     rdi, [rsp+48h+arg_18]
0x1800142d3  add     rsp, 40h
0x1800142d7  pop     r15
0x1800142d9  retn
```
