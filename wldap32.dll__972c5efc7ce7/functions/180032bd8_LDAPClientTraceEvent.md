# LDAPClientTraceEvent

- ea: `0x180032bd8`
- end: `0x180032e56`
- name: `LDAPClientTraceEvent`
- size: `638`
- prototype: ``
- caller_count: `47`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022c0`
- `0x1800037a8`
- `0x1800057a0`
- `0x1800094a0`
- `0x18000a358`
- `0x18000b5c8`
- `0x18000df44`
- `0x1800112b0`
- `0x180013610`
- `0x1800164a0`
- `0x180017854`
- `0x1800191d0`
- `0x18001b0d4`
- `0x18001c2d0`
- `0x18001cf70`
- `0x18001d470`
- `0x18001da40`
- `0x18001de00`
- `0x18001e6c4`
- `0x18001ea90`
- `0x18001f4a0`
- `0x180021454`
- `0x1800224cc`
- `0x1800227d8`
- `0x1800245ec`
- `0x180024df0`
- `0x180025cc8`
- `0x180026b50`
- `0x180027cf0`
- `0x18002d530`
- `0x18002d7f0`
- `0x18002df60`
- `0x18002e24c`
- `0x18002e6d4`
- `0x180031128`
- `0x1800314a8`
- `0x180031c98`
- `0x1800334bc`
- `0x18003b448`
- `0x18003d78c`
- `0x1800400e4`
- `0x180041aa0`
- `0x180041b20`
- `0x180041cd0`
- `0x180045de8`
- `0x18004af90`
- `0x18004c308`

## callees

- `0x180032bd8`
- `0x180034510`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180032e2c`
- `ntdll!EtwEventWrite` at `0x180032e2c`

## pseudocode

```c
_BOOL8 __fastcall LDAPClientTraceEvent(int a1, __int64 a2)
{
  int v2; // r9d
  __int64 v3; // rax
  __int64 *v4; // rdx
  __int64 v6; // [rsp+20h] [rbp-20h] BYREF
  int v7; // [rsp+28h] [rbp-18h]
  int v8; // [rsp+2Ch] [rbp-14h]

  v2 = 0;
  if ( g_fTracingOn && g_RegistrationHandle )
  {
    v6 = a2;
    v3 = -1;
    do
      ++v3;
    while ( *(_BYTE *)(a2 + v3) );
    v8 = 0;
    v7 = v3 + 1;
    if ( (a1 & 1) != 0 )
    {
      v4 = LDAP_CLIENT_SEARCH;
LABEL_65:
      v2 = ((__int64 (__fastcall *)(unsigned __int64, __int64 *, __int64, __int64 *))EtwEventWrite)(
             g_RegistrationHandle,
             v4,
             1,
             &v6);
      return v2 == 0;
    }
    if ( (a1 & 2) != 0 )
    {
      v4 = LDAP_CLIENT_WRITE;
      goto LABEL_65;
    }
    if ( (a1 & 4) != 0 )
    {
      v4 = LDAP_CLIENT_REFCNT;
      goto LABEL_65;
    }
    if ( (a1 & 8) != 0 )
    {
      v4 = LDAP_CLIENT_HEAP;
      goto LABEL_65;
    }
    if ( (a1 & 0x10) != 0 )
    {
      v4 = LDAP_CLIENT_CACHE;
      goto LABEL_65;
    }
    if ( (a1 & 0x20) != 0 )
    {
      v4 = LDAP_CLIENT_SSL;
      goto LABEL_65;
    }
    if ( (a1 & 0x40) != 0 )
    {
      v4 = LDAP_CLIENT_SPEWSEARCH;
      goto LABEL_65;
    }
    if ( (a1 & 0x80u) != 0 )
    {
      v4 = LDAP_CLIENT_SERVERDOWN;
      goto LABEL_65;
    }
    if ( (a1 & 0x100) != 0 )
    {
      v4 = LDAP_CLIENT_CONNECT;
      goto LABEL_65;
    }
    if ( (a1 & 0x200) != 0 )
    {
      v4 = LDAP_CLIENT_RECONNECT;
      goto LABEL_65;
    }
    if ( (a1 & 0x400) != 0 )
    {
      v4 = LDAP_CLIENT_RECEIVEDATA;
      goto LABEL_65;
    }
    if ( (a1 & 0x800) != 0 )
    {
      v4 = LDAP_CLIENT_BYTES_SENT;
      goto LABEL_65;
    }
    if ( (a1 & 0x1000) != 0 )
    {
      v4 = LDAP_CLIENT_EOM;
      goto LABEL_65;
    }
    if ( (a1 & 0x2000) != 0 )
    {
      v4 = LDAP_CLIENT_BER;
      goto LABEL_65;
    }
    if ( (a1 & 0x4000) != 0 )
    {
      v4 = LDAP_CLIENT_OUTMEMORY;
      goto LABEL_65;
    }
    if ( (a1 & 0x8000) != 0 )
    {
      v4 = LDAP_CLIENT_CONTROLS;
      goto LABEL_65;
    }
    if ( (a1 & 0x10000) != 0 )
    {
      v4 = LDAP_CLIENT_BYTES_RECEIVED;
      goto LABEL_65;
    }
    if ( (a1 & 0x20000) != 0 )
    {
      v4 = LDAP_CLIENT_CLDAP;
      goto LABEL_65;
    }
    if ( (a1 & 0x40000) != 0 )
    {
      v4 = LDAP_CLIENT_FILTER;
      goto LABEL_65;
    }
    if ( (a1 & 0x80000) != 0 )
    {
      v4 = LDAP_CLIENT_BIND;
      goto LABEL_65;
    }
    if ( (a1 & 0x100000) != 0 )
    {
      v4 = LDAP_CLIENT_NETWORK_ERRORS;
      goto LABEL_65;
    }
    if ( (a1 & 0x200000) != 0 )
    {
      v4 = LDAP_CLIENT_VERBOSE;
      goto LABEL_65;
    }
    if ( (a1 & 0x400000) != 0 )
    {
      v4 = LDAP_CLIENT_PARSE;
      goto LABEL_65;
    }
    if ( (a1 & 0x800000) != 0 )
    {
      v4 = LDAP_CLIENT_REFERRALS;
      goto LABEL_65;
    }
    if ( (a1 & 0x1000000) != 0 )
    {
      v4 = LDAP_CLIENT_REQUEST;
      goto LABEL_65;
    }
    if ( (a1 & 0x2000000) != 0 )
    {
      v4 = LDAP_CLIENT_CONNECTION;
      goto LABEL_65;
    }
    if ( (a1 & 0x4000000) != 0 )
    {
      v4 = LDAP_CLIENT_INIT_TERM;
      goto LABEL_65;
    }
    if ( (a1 & 0x8000000) != 0 )
    {
      v4 = LDAP_CLIENT_API_ERRORS;
      goto LABEL_65;
    }
    if ( (a1 & 0x10000000) != 0 )
    {
      v4 = LDAP_CLIENT_ERRORS;
      goto LABEL_65;
    }
    if ( (a1 & 0x20000000) != 0 )
    {
      v4 = LDAP_CLIENT_PERFORMANCE;
      goto LABEL_65;
    }
  }
  return v2 == 0;
}

```

## disassembly

```asm
0x180032bd8  push    rbp
0x180032bda  mov     rbp, rsp
0x180032bdd  sub     rsp, 40h
0x180032be1  mov     rax, cs:__security_cookie
0x180032be8  xor     rax, rsp
0x180032beb  mov     [rbp+var_10], rax
0x180032bef  xor     r9d, r9d
0x180032bf2  cmp     cs:g_fTracingOn, r9d
0x180032bf9  jz      loc_180032E3B
0x180032bff  mov     r10, cs:?g_RegistrationHandle@@3_KA; unsigned __int64 g_RegistrationHandle
0x180032c06  test    r10, r10
0x180032c09  jz      loc_180032E3B
0x180032c0f  mov     [rbp+var_20], rdx
0x180032c13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032c17  inc     rax
0x180032c1a  cmp     [rdx+rax], r9b
0x180032c1e  jnz     short loc_180032C17
0x180032c20  inc     eax
0x180032c22  mov     [rbp+var_14], r9d
0x180032c26  mov     r8d, 1
0x180032c2c  mov     [rbp+var_18], eax
0x180032c2f  test    r8b, cl
0x180032c32  jz      short loc_180032C40
0x180032c34  lea     rdx, LDAP_CLIENT_SEARCH
0x180032c3b  jmp     loc_180032E25
0x180032c40  test    cl, 2
0x180032c43  jz      short loc_180032C51
0x180032c45  lea     rdx, LDAP_CLIENT_WRITE
0x180032c4c  jmp     loc_180032E25
0x180032c51  test    cl, 4
0x180032c54  jz      short loc_180032C62
0x180032c56  lea     rdx, LDAP_CLIENT_REFCNT
0x180032c5d  jmp     loc_180032E25
0x180032c62  test    cl, 8
0x180032c65  jz      short loc_180032C73
0x180032c67  lea     rdx, LDAP_CLIENT_HEAP
0x180032c6e  jmp     loc_180032E25
0x180032c73  test    cl, 10h
0x180032c76  jz      short loc_180032C84
0x180032c78  lea     rdx, LDAP_CLIENT_CACHE
0x180032c7f  jmp     loc_180032E25
0x180032c84  test    cl, 20h
0x180032c87  jz      short loc_180032C95
0x180032c89  lea     rdx, LDAP_CLIENT_SSL
0x180032c90  jmp     loc_180032E25
0x180032c95  test    cl, 40h
0x180032c98  jz      short loc_180032CA6
0x180032c9a  lea     rdx, LDAP_CLIENT_SPEWSEARCH
0x180032ca1  jmp     loc_180032E25
0x180032ca6  test    cl, cl
0x180032ca8  jns     short loc_180032CB6
0x180032caa  lea     rdx, LDAP_CLIENT_SERVERDOWN
0x180032cb1  jmp     loc_180032E25
0x180032cb6  bt      ecx, 8
0x180032cba  jnb     short loc_180032CC8
0x180032cbc  lea     rdx, LDAP_CLIENT_CONNECT
0x180032cc3  jmp     loc_180032E25
0x180032cc8  bt      ecx, 9
0x180032ccc  jnb     short loc_180032CDA
0x180032cce  lea     rdx, LDAP_CLIENT_RECONNECT
0x180032cd5  jmp     loc_180032E25
0x180032cda  bt      ecx, 0Ah
0x180032cde  jnb     short loc_180032CEC
0x180032ce0  lea     rdx, LDAP_CLIENT_RECEIVEDATA
0x180032ce7  jmp     loc_180032E25
0x180032cec  bt      ecx, 0Bh
0x180032cf0  jnb     short loc_180032CFE
0x180032cf2  lea     rdx, LDAP_CLIENT_BYTES_SENT
0x180032cf9  jmp     loc_180032E25
0x180032cfe  bt      ecx, 0Ch
0x180032d02  jnb     short loc_180032D10
0x180032d04  lea     rdx, LDAP_CLIENT_EOM
0x180032d0b  jmp     loc_180032E25
0x180032d10  bt      ecx, 0Dh
0x180032d14  jnb     short loc_180032D22
0x180032d16  lea     rdx, LDAP_CLIENT_BER
0x180032d1d  jmp     loc_180032E25
0x180032d22  bt      ecx, 0Eh
0x180032d26  jnb     short loc_180032D34
0x180032d28  lea     rdx, LDAP_CLIENT_OUTMEMORY
0x180032d2f  jmp     loc_180032E25
0x180032d34  bt      ecx, 0Fh
0x180032d38  jnb     short loc_180032D46
0x180032d3a  lea     rdx, LDAP_CLIENT_CONTROLS
0x180032d41  jmp     loc_180032E25
0x180032d46  bt      ecx, 10h
0x180032d4a  jnb     short loc_180032D58
0x180032d4c  lea     rdx, LDAP_CLIENT_BYTES_RECEIVED
0x180032d53  jmp     loc_180032E25
0x180032d58  bt      ecx, 11h
0x180032d5c  jnb     short loc_180032D6A
0x180032d5e  lea     rdx, LDAP_CLIENT_CLDAP
0x180032d65  jmp     loc_180032E25
0x180032d6a  bt      ecx, 12h
0x180032d6e  jnb     short loc_180032D7C
0x180032d70  lea     rdx, LDAP_CLIENT_FILTER
0x180032d77  jmp     loc_180032E25
0x180032d7c  bt      ecx, 13h
0x180032d80  jnb     short loc_180032D8E
0x180032d82  lea     rdx, LDAP_CLIENT_BIND
0x180032d89  jmp     loc_180032E25
0x180032d8e  bt      ecx, 14h
0x180032d92  jnb     short loc_180032DA0
0x180032d94  lea     rdx, LDAP_CLIENT_NETWORK_ERRORS
0x180032d9b  jmp     loc_180032E25
0x180032da0  bt      ecx, 15h
0x180032da4  jnb     short loc_180032DAF
0x180032da6  lea     rdx, LDAP_CLIENT_VERBOSE
0x180032dad  jmp     short loc_180032E25
0x180032daf  bt      ecx, 16h
0x180032db3  jnb     short loc_180032DBE
0x180032db5  lea     rdx, LDAP_CLIENT_PARSE
0x180032dbc  jmp     short loc_180032E25
0x180032dbe  bt      ecx, 17h
0x180032dc2  jnb     short loc_180032DCD
0x180032dc4  lea     rdx, LDAP_CLIENT_REFERRALS
0x180032dcb  jmp     short loc_180032E25
0x180032dcd  bt      ecx, 18h
0x180032dd1  jnb     short loc_180032DDC
0x180032dd3  lea     rdx, LDAP_CLIENT_REQUEST
0x180032dda  jmp     short loc_180032E25
0x180032ddc  bt      ecx, 19h
0x180032de0  jnb     short loc_180032DEB
0x180032de2  lea     rdx, LDAP_CLIENT_CONNECTION
0x180032de9  jmp     short loc_180032E25
0x180032deb  bt      ecx, 1Ah
0x180032def  jnb     short loc_180032DFA
0x180032df1  lea     rdx, LDAP_CLIENT_INIT_TERM
0x180032df8  jmp     short loc_180032E25
0x180032dfa  bt      ecx, 1Bh
0x180032dfe  jnb     short loc_180032E09
0x180032e00  lea     rdx, LDAP_CLIENT_API_ERRORS
0x180032e07  jmp     short loc_180032E25
0x180032e09  bt      ecx, 1Ch
0x180032e0d  jnb     short loc_180032E18
0x180032e0f  lea     rdx, LDAP_CLIENT_ERRORS
0x180032e16  jmp     short loc_180032E25
0x180032e18  bt      ecx, 1Dh
0x180032e1c  jnb     short loc_180032E3B
0x180032e1e  lea     rdx, LDAP_CLIENT_PERFORMANCE
0x180032e25  lea     r9, [rbp+var_20]
0x180032e29  mov     rcx, r10
0x180032e2c  call    cs:__imp_EtwEventWrite
0x180032e33  nop     dword ptr [rax+rax+00h]
0x180032e38  mov     r9d, eax
0x180032e3b  xor     eax, eax
0x180032e3d  test    r9d, r9d
0x180032e40  setz    al
0x180032e43  mov     rcx, [rbp+var_10]
0x180032e47  xor     rcx, rsp; StackCookie
0x180032e4a  call    __security_check_cookie
0x180032e4f  add     rsp, 40h
0x180032e53  pop     rbp
0x180032e54  retn
```
