# GetLDAPOptionName(int)

- ea: `0x18003fb24`
- end: `0x18003fdd6`
- name: `?GetLDAPOptionName@@YAPEADH@Z`
- size: `690`
- prototype: `char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ce40`

## callees

- `0x18003fb24`

## string_xrefs

- `0x18003fdb3`: `LDAP_OPT_SECURITY_CONTEXT`
- `0x18003fb90`: `LDAP_OPT_THREAD_FN_PTRS`
- `0x18003fc11`: `LDAP_OPT_CACHE_FN_PTRS`
- `0x18003fc08`: `LDAP_OPT_CACHE_STRATEGY`
- `0x18003fbff`: `LDAP_OPT_CACHE_ENABLE`
- `0x18003fdaa`: `LDAP_OPT_ROOTDSE_CACHE`

## pseudocode

```c
char *__fastcall GetLDAPOptionName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx

  if ( a1 <= 112 )
  {
    if ( a1 == 112 )
      return "LDAP_OPT_REFERRAL_CALLBACK";
    if ( a1 > 48 )
    {
      if ( a1 > 64 )
      {
        v22 = a1 - 65;
        if ( !v22 )
          return "LDAP_OPT_FAST_CONCURRENT_BIND";
        v23 = v22 - 1;
        if ( !v23 )
          return "LDAP_OPT_SEND_TIMEOUT";
        v24 = v23 - 1;
        if ( !v24 )
          return "LDAP_OPT_SCH_FLAGS";
        v25 = v24 - 1;
        if ( !v25 )
          return "LDAP_OPT_SOCKET_BIND_ADDRESSES";
        v26 = v25 - 1;
        if ( !v26 )
          return "LDAP_OPT_CLDAP_TIMEOUT";
        v27 = v26 - 1;
        if ( !v27 )
          return "LDAP_OPT_CLDAP_TRIES";
        if ( v27 == 1 )
          return "LDAP_OPT_ANONYMOUS_MAX_VAL_RANGE";
      }
      else
      {
        if ( a1 == 64 )
          return "LDAP_OPT_TCP_KEEPALIVE";
        v15 = a1 - 49;
        if ( !v15 )
          return "LDAP_OPT_ERROR_NUMBER";
        v16 = v15 - 1;
        if ( !v16 )
          return "LDAP_OPT_ERROR_STRING";
        v17 = v16 - 4;
        if ( !v17 )
          return "LDAP_OPT_PING_KEEP_ALIVE";
        v18 = v17 - 1;
        if ( !v18 )
          return "LDAP_OPT_PING_WAIT_TIME";
        v19 = v18 - 1;
        if ( !v19 )
          return "LDAP_OPT_PING_LIMIT";
        v20 = v19 - 3;
        if ( !v20 )
          return "LDAP_OPT_DNSDOMAIN_NAME";
        v21 = v20 - 2;
        if ( !v21 )
          return "LDAP_OPT_GETDSNAME_FLAGS";
        if ( v21 == 2 )
          return "LDAP_OPT_PROMPT_CREDENTIALS";
      }
    }
    else
    {
      if ( a1 == 48 )
        return "LDAP_OPT_HOST_NAME";
      if ( a1 > 9 )
      {
        v9 = a1 - 10;
        if ( !v9 )
          return "LDAP_OPT_SSL";
        v10 = v9 - 1;
        if ( !v10 )
          return "LDAP_OPT_IO_FN_PTRS";
        v11 = v10 - 2;
        if ( !v11 )
          return "LDAP_OPT_CACHE_FN_PTRS";
        v12 = v11 - 1;
        if ( !v12 )
          return "LDAP_OPT_CACHE_STRATEGY";
        v13 = v12 - 1;
        if ( !v13 )
          return "LDAP_OPT_CACHE_ENABLE";
        v14 = v13 - 1;
        if ( !v14 )
          return "LDAP_OPT_REFERRAL_HOP_LIMIT";
        if ( v14 == 1 )
          return "LDAP_OPT_VERSION";
      }
      else
      {
        if ( a1 == 9 )
          return "LDAP_OPT_RESTART";
        v1 = a1 - 1;
        if ( !v1 )
          return "LDAP_OPT_DESC";
        v2 = v1 - 1;
        if ( !v2 )
          return "LDAP_OPT_DEREF";
        v3 = v2 - 1;
        if ( !v3 )
          return "LDAP_OPT_SIZELIMIT";
        v4 = v3 - 1;
        if ( !v4 )
          return "LDAP_OPT_TIMELIMIT";
        v5 = v4 - 1;
        if ( !v5 )
          return "LDAP_OPT_THREAD_FN_PTRS";
        v6 = v5 - 1;
        if ( !v6 )
          return "LDAP_OPT_REBIND_FN";
        v7 = v6 - 1;
        if ( !v7 )
          return "LDAP_OPT_REBIND_ARG";
        if ( v7 == 1 )
          return "LDAP_OPT_REFERRALS";
      }
    }
    return "INVALID_OPTION";
  }
  if ( a1 <= 149 )
  {
    if ( a1 == 149 )
      return "LDAP_OPT_SIGN";
    v28 = a1 - 128;
    if ( !v28 )
      return "LDAP_OPT_CLIENT_CERTIFICATE";
    v29 = v28 - 1;
    if ( !v29 )
      return "LDAP_OPT_SERVER_CERTIFICATE";
    v30 = v29 - 16;
    if ( !v30 )
      return "LDAP_OPT_AUTO_RECONNECT";
    v31 = v30 - 1;
    if ( !v31 )
      return "LDAP_OPT_SSPI_FLAGS";
    if ( v31 == 2 )
      return "LDAP_OPT_REF_DEREF_CONN_PER_MSG";
    return "INVALID_OPTION";
  }
  v32 = a1 - 150;
  if ( !v32 )
    return "LDAP_OPT_ENCRYPT";
  v33 = v32 - 1;
  if ( !v33 )
    return "LDAP_OPT_SASL_METHOD";
  v34 = v33 - 1;
  if ( !v34 )
    return "LDAP_OPT_AREC_EXCLUSIVE";
  v35 = v34 - 1;
  if ( !v35 )
    return "LDAP_OPT_SECURITY_CONTEXT";
  if ( v35 != 1 )
    return "INVALID_OPTION";
  return "LDAP_OPT_ROOTDSE_CACHE";
}

```

## disassembly

```asm
0x18003fb24  cmp     ecx, 70h ; 'p'
0x18003fb27  jg      loc_18003FD28
0x18003fb2d  jz      loc_18003FD1F
0x18003fb33  cmp     ecx, 30h ; '0'
0x18003fb36  jg      loc_18003FC35
0x18003fb3c  jz      loc_18003FC2C
0x18003fb42  cmp     ecx, 9
0x18003fb45  jg      short loc_18003FBC6
0x18003fb47  jz      short loc_18003FBBD
0x18003fb49  sub     ecx, 1
0x18003fb4c  jz      short loc_18003FBB4
0x18003fb4e  sub     ecx, 1
0x18003fb51  jz      short loc_18003FBAB
0x18003fb53  sub     ecx, 1
0x18003fb56  jz      short loc_18003FBA2
0x18003fb58  sub     ecx, 1
0x18003fb5b  jz      short loc_18003FB99
0x18003fb5d  sub     ecx, 1
0x18003fb60  jz      short loc_18003FB90
0x18003fb62  sub     ecx, 1
0x18003fb65  jz      short loc_18003FB87
0x18003fb67  sub     ecx, 1
0x18003fb6a  jz      short loc_18003FB7E
0x18003fb6c  cmp     ecx, 1
0x18003fb6f  jnz     loc_18003FDA1
0x18003fb75  lea     rax, aLdapOptReferra; "LDAP_OPT_REFERRALS"
0x18003fb7c  retn
0x18003fb7e  lea     rax, aLdapOptRebindA; "LDAP_OPT_REBIND_ARG"
0x18003fb85  retn
0x18003fb87  lea     rax, aLdapOptRebindF; "LDAP_OPT_REBIND_FN"
0x18003fb8e  retn
0x18003fb90  lea     rax, aLdapOptThreadF; "LDAP_OPT_THREAD_FN_PTRS"
0x18003fb97  retn
0x18003fb99  lea     rax, aLdapOptTimelim; "LDAP_OPT_TIMELIMIT"
0x18003fba0  retn
0x18003fba2  lea     rax, aLdapOptSizelim; "LDAP_OPT_SIZELIMIT"
0x18003fba9  retn
0x18003fbab  lea     rax, aLdapOptDeref; "LDAP_OPT_DEREF"
0x18003fbb2  retn
0x18003fbb4  lea     rax, aLdapOptDesc; "LDAP_OPT_DESC"
0x18003fbbb  retn
0x18003fbbd  lea     rax, aLdapOptRestart; "LDAP_OPT_RESTART"
0x18003fbc4  retn
0x18003fbc6  sub     ecx, 0Ah
0x18003fbc9  jz      short loc_18003FC23
0x18003fbcb  sub     ecx, 1
0x18003fbce  jz      short loc_18003FC1A
0x18003fbd0  sub     ecx, 2
0x18003fbd3  jz      short loc_18003FC11
0x18003fbd5  sub     ecx, 1
0x18003fbd8  jz      short loc_18003FC08
0x18003fbda  sub     ecx, 1
0x18003fbdd  jz      short loc_18003FBFF
0x18003fbdf  sub     ecx, 1
0x18003fbe2  jz      short loc_18003FBF6
0x18003fbe4  cmp     ecx, 1
0x18003fbe7  jnz     loc_18003FDA1
0x18003fbed  lea     rax, aLdapOptVersion; "LDAP_OPT_VERSION"
0x18003fbf4  retn
0x18003fbf6  lea     rax, aLdapOptReferra_1; "LDAP_OPT_REFERRAL_HOP_LIMIT"
0x18003fbfd  retn
0x18003fbff  lea     rax, aLdapOptCacheEn; "LDAP_OPT_CACHE_ENABLE"
0x18003fc06  retn
0x18003fc08  lea     rax, aLdapOptCacheSt; "LDAP_OPT_CACHE_STRATEGY"
0x18003fc0f  retn
0x18003fc11  lea     rax, aLdapOptCacheFn; "LDAP_OPT_CACHE_FN_PTRS"
0x18003fc18  retn
0x18003fc1a  lea     rax, aLdapOptIoFnPtr; "LDAP_OPT_IO_FN_PTRS"
0x18003fc21  retn
0x18003fc23  lea     rax, aLdapOptSsl; "LDAP_OPT_SSL"
0x18003fc2a  retn
0x18003fc2c  lea     rax, aLdapOptHostNam; "LDAP_OPT_HOST_NAME"
0x18003fc33  retn
0x18003fc35  cmp     ecx, 40h ; '@'
0x18003fc38  jg      short loc_18003FCB9
0x18003fc3a  jz      short loc_18003FCB0
0x18003fc3c  sub     ecx, 31h ; '1'
0x18003fc3f  jz      short loc_18003FCA7
0x18003fc41  sub     ecx, 1
0x18003fc44  jz      short loc_18003FC9E
0x18003fc46  sub     ecx, 4
0x18003fc49  jz      short loc_18003FC95
0x18003fc4b  sub     ecx, 1
0x18003fc4e  jz      short loc_18003FC8C
0x18003fc50  sub     ecx, 1
0x18003fc53  jz      short loc_18003FC83
0x18003fc55  sub     ecx, 3
0x18003fc58  jz      short loc_18003FC7A
0x18003fc5a  sub     ecx, 2
0x18003fc5d  jz      short loc_18003FC71
0x18003fc5f  cmp     ecx, 2
0x18003fc62  jnz     loc_18003FDA1
0x18003fc68  lea     rax, aLdapOptPromptC; "LDAP_OPT_PROMPT_CREDENTIALS"
0x18003fc6f  retn
0x18003fc71  lea     rax, aLdapOptGetdsna; "LDAP_OPT_GETDSNAME_FLAGS"
0x18003fc78  retn
0x18003fc7a  lea     rax, aLdapOptDnsdoma; "LDAP_OPT_DNSDOMAIN_NAME"
0x18003fc81  retn
0x18003fc83  lea     rax, aLdapOptPingLim; "LDAP_OPT_PING_LIMIT"
0x18003fc8a  retn
0x18003fc8c  lea     rax, aLdapOptPingWai; "LDAP_OPT_PING_WAIT_TIME"
0x18003fc93  retn
0x18003fc95  lea     rax, aLdapOptPingKee; "LDAP_OPT_PING_KEEP_ALIVE"
0x18003fc9c  retn
0x18003fc9e  lea     rax, aLdapOptErrorSt; "LDAP_OPT_ERROR_STRING"
0x18003fca5  retn
0x18003fca7  lea     rax, aLdapOptErrorNu; "LDAP_OPT_ERROR_NUMBER"
0x18003fcae  retn
0x18003fcb0  lea     rax, aLdapOptTcpKeep; "LDAP_OPT_TCP_KEEPALIVE"
0x18003fcb7  retn
0x18003fcb9  sub     ecx, 41h ; 'A'
0x18003fcbc  jz      short loc_18003FD16
0x18003fcbe  sub     ecx, 1
0x18003fcc1  jz      short loc_18003FD0D
0x18003fcc3  sub     ecx, 1
0x18003fcc6  jz      short loc_18003FD04
0x18003fcc8  sub     ecx, 1
0x18003fccb  jz      short loc_18003FCFB
0x18003fccd  sub     ecx, 1
0x18003fcd0  jz      short loc_18003FCF2
0x18003fcd2  sub     ecx, 1
0x18003fcd5  jz      short loc_18003FCE9
0x18003fcd7  cmp     ecx, 1
0x18003fcda  jnz     loc_18003FDA1
0x18003fce0  lea     rax, aLdapOptAnonymo; "LDAP_OPT_ANONYMOUS_MAX_VAL_RANGE"
0x18003fce7  retn
0x18003fce9  lea     rax, aLdapOptCldapTr; "LDAP_OPT_CLDAP_TRIES"
0x18003fcf0  retn
0x18003fcf2  lea     rax, aLdapOptCldapTi; "LDAP_OPT_CLDAP_TIMEOUT"
0x18003fcf9  retn
0x18003fcfb  lea     rax, aLdapOptSocketB; "LDAP_OPT_SOCKET_BIND_ADDRESSES"
0x18003fd02  retn
0x18003fd04  lea     rax, aLdapOptSchFlag; "LDAP_OPT_SCH_FLAGS"
0x18003fd0b  retn
0x18003fd0d  lea     rax, aLdapOptSendTim; "LDAP_OPT_SEND_TIMEOUT"
0x18003fd14  retn
0x18003fd16  lea     rax, aLdapOptFastCon; "LDAP_OPT_FAST_CONCURRENT_BIND"
0x18003fd1d  retn
0x18003fd1f  lea     rax, aLdapOptReferra_0; "LDAP_OPT_REFERRAL_CALLBACK"
0x18003fd26  retn
0x18003fd28  mov     eax, 95h
0x18003fd2d  cmp     ecx, eax
0x18003fd2f  jg      short loc_18003FD85
0x18003fd31  jz      short loc_18003FD7C
0x18003fd33  sub     ecx, 80h
0x18003fd39  jz      short loc_18003FD73
0x18003fd3b  sub     ecx, 1
0x18003fd3e  jz      short loc_18003FD6A
0x18003fd40  sub     ecx, 10h
0x18003fd43  jz      short loc_18003FD61
0x18003fd45  sub     ecx, 1
0x18003fd48  jz      short loc_18003FD58
0x18003fd4a  cmp     ecx, 2
0x18003fd4d  jnz     short loc_18003FDA1
0x18003fd4f  lea     rax, aLdapOptRefDere; "LDAP_OPT_REF_DEREF_CONN_PER_MSG"
0x18003fd56  retn
0x18003fd58  lea     rax, aLdapOptSspiFla; "LDAP_OPT_SSPI_FLAGS"
0x18003fd5f  retn
0x18003fd61  lea     rax, aLdapOptAutoRec; "LDAP_OPT_AUTO_RECONNECT"
0x18003fd68  retn
0x18003fd6a  lea     rax, aLdapOptServerC; "LDAP_OPT_SERVER_CERTIFICATE"
0x18003fd71  retn
0x18003fd73  lea     rax, aLdapOptClientC; "LDAP_OPT_CLIENT_CERTIFICATE"
0x18003fd7a  retn
0x18003fd7c  lea     rax, aLdapOptSign; "LDAP_OPT_SIGN"
0x18003fd83  retn
0x18003fd85  sub     ecx, 96h
0x18003fd8b  jz      short loc_18003FDCE
0x18003fd8d  sub     ecx, 1
0x18003fd90  jz      short loc_18003FDC5
0x18003fd92  sub     ecx, 1
0x18003fd95  jz      short loc_18003FDBC
0x18003fd97  sub     ecx, 1
0x18003fd9a  jz      short loc_18003FDB3
0x18003fd9c  cmp     ecx, 1
0x18003fd9f  jz      short loc_18003FDAA
0x18003fda1  lea     rax, aInvalidOption; "INVALID_OPTION"
0x18003fda8  retn
0x18003fdaa  lea     rax, aLdapOptRootdse; "LDAP_OPT_ROOTDSE_CACHE"
0x18003fdb1  retn
0x18003fdb3  lea     rax, aLdapOptSecurit; "LDAP_OPT_SECURITY_CONTEXT"
0x18003fdba  retn
0x18003fdbc  lea     rax, aLdapOptArecExc; "LDAP_OPT_AREC_EXCLUSIVE"
0x18003fdc3  retn
0x18003fdc5  lea     rax, aLdapOptSaslMet; "LDAP_OPT_SASL_METHOD"
0x18003fdcc  retn
0x18003fdce  lea     rax, aLdapOptEncrypt; "LDAP_OPT_ENCRYPT"
0x18003fdd5  retn
```
