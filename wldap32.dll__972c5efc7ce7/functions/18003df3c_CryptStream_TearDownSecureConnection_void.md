# CryptStream::TearDownSecureConnection(void)

- ea: `0x18003df3c`
- end: `0x18003e249`
- name: `?TearDownSecureConnection@CryptStream@@QEAAJXZ`
- size: `781`
- prototype: `__int64 __fastcall(CryptStream *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004b920`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x18001ce90`
- `0x18001da40`
- `0x180031a10`
- `0x180034510`
- `0x18003de10`
- `0x18003df3c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dfb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dfb9`

## string_xrefs

- `0x18003e001`: `TearDownSecureConnection:ApplyControlToken returned 0x%x\n`

## pseudocode

```c
__int64 __fastcall CryptStream::TearDownSecureConnection(CryptStream *this)
{
  char *v1; // rbx
  char *v3; // rdi
  __int64 v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  unsigned int len; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+74h] [rbp-8Ch]
  char *buf; // [rsp+78h] [rbp-88h]
  unsigned int v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+84h] [rbp-7Ch] BYREF
  int v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  int v22; // [rsp+94h] [rbp-6Ch]
  unsigned int *p_len; // [rsp+98h] [rbp-68h]
  __int128 v24; // [rsp+A0h] [rbp-60h] BYREF
  char *v25; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v26[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v27[7]; // [rsp+C8h] [rbp-38h]

  v16 = 2;
  v20 = 0;
  buf = (char *)&v19;
  v1 = (char *)this + 48;
  v18 = 0;
  len = 4;
  v19 = 1;
  v22 = 1;
  p_len = &len;
  v24 = 0;
  v3 = 0;
  v21 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  v4 = *((_QWORD *)this + 3);
  v25 = v1;
  v5 = (*(__int64 (__fastcall **)(char *, int *))(v4 + 80))((char *)this + 72, &v21);
  v6 = v5;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
    LDAPClientPrint(32, "TearDownSecureConnection:ApplyControlToken returned 0x%x\n", v5);
  if ( !v6 )
  {
    buf = 0;
    p_len = &len;
    v7 = *((_QWORD *)this + 3);
    v16 = 2;
    len = 0;
    v22 = 1;
    v21 = 0;
    v6 = (*(__int64 (__fastcall **)(char *, char *, _QWORD, __int64, _DWORD, int, _QWORD, _DWORD, char *, int *, int *, char *))(v7 + 48))(
           (char *)this + 56,
           (char *)this + 72,
           0,
           49436,
           0,
           16,
           0,
           0,
           (char *)this + 72,
           &v21,
           &v20,
           (char *)this + 96);
    if ( !v6 )
    {
      v8 = LdapSendRaw(*((struct ldap_connection **)this + 2), buf, len, 0, 0);
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 3) + 128LL))(buf);
      len = 0;
      buf = 0;
      if ( v8 )
      {
        v6 = 1229;
      }
      else
      {
        v3 = (char *)ldapMalloc(SspiMaxTokenSize, 1667593036);
        if ( v3 )
        {
          while ( 1 )
          {
            v9 = CryptStream::SslBlockingReceive(this, v3, SspiMaxTokenSize, &v18);
            if ( v9 )
              break;
            v10 = 1;
            v26[0] = v18;
            v11 = 4;
            v26[1] = 1;
            v27[0] = v3;
            do
            {
              ++v10;
              v27[v11 / 2] = 0;
              *(_QWORD *)&v26[v11] = 0;
              v11 += 4LL;
            }
            while ( v10 != 4 );
            v12 = 4;
            LODWORD(v24) = 0;
            if ( *((_DWORD *)this + 29) < 4u )
              v12 = *((_DWORD *)this + 29);
            DWORD1(v24) = v12;
            *((_QWORD *)&v24 + 1) = v26;
            v13 = (*((__int64 (__fastcall **)(char *, __int128 *, _QWORD, _QWORD))this + 1))(
                    (char *)this + 72,
                    &v24,
                    0,
                    0);
            if ( v13 == 590615 )
            {
              v6 = 0;
              goto LABEL_24;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
              LDAPClientPrint(32, "TearDownSecureConnection: DecryptMessage returns 0x%x\n", v13);
          }
          v6 = 1460;
          if ( v9 != 85 )
            v6 = 58;
        }
        else
        {
          v6 = 8;
        }
      }
    }
  }
LABEL_24:
  ldapFree((__int64)v3, 1667593036);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
    LDAPClientPrint(32, "TearDownSecureConnection win32 error is 0x%x\n", v6);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  return v6;
}

```

## disassembly

```asm
0x18003df3c  mov     [rsp-8+arg_8], rbx
0x18003df41  mov     [rsp-8+arg_10], rsi
0x18003df46  push    rbp
0x18003df47  push    rdi
0x18003df48  push    r13
0x18003df4a  push    r14
0x18003df4c  push    r15
0x18003df4e  lea     rbp, [rsp-10h]
0x18003df53  sub     rsp, 110h
0x18003df5a  mov     rax, cs:__security_cookie
0x18003df61  xor     rax, rsp
0x18003df64  mov     [rbp+30h+var_30], rax
0x18003df68  xor     r15d, r15d
0x18003df6b  mov     [rsp+130h+var_BC], 2
0x18003df73  lea     rax, [rbp+30h+var_AC]
0x18003df77  mov     [rbp+30h+var_A8], r15d
0x18003df7b  mov     [rsp+130h+buf], rax
0x18003df80  lea     rbx, [rcx+30h]
0x18003df84  mov     rsi, rcx
0x18003df87  mov     [rbp+30h+var_B0], r15d
0x18003df8b  lea     r13d, [r15+1]
0x18003df8f  mov     [rsp+130h+len], 4
0x18003df97  xorps   xmm0, xmm0
0x18003df9a  mov     [rbp+30h+var_AC], r13d
0x18003df9e  lea     rax, [rsp+130h+len]
0x18003dfa3  mov     [rbp+30h+var_9C], r13d
0x18003dfa7  mov     rcx, rbx; SRWLock
0x18003dfaa  mov     [rbp+30h+var_98], rax
0x18003dfae  movups  [rbp+30h+var_90], xmm0
0x18003dfb2  mov     edi, r15d
0x18003dfb5  mov     [rbp+30h+var_A0], r15d
0x18003dfb9  call    cs:__imp_AcquireSRWLockExclusive
0x18003dfc0  nop     dword ptr [rax+rax+00h]
0x18003dfc5  mov     rax, [rsi+18h]
0x18003dfc9  lea     r14, [rsi+48h]
0x18003dfcd  lea     rdx, [rbp+30h+var_A0]
0x18003dfd1  mov     [rbp+30h+var_80], rbx
0x18003dfd5  mov     rcx, r14
0x18003dfd8  mov     rax, [rax+50h]
0x18003dfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfe1  cmp     cs:g_fTracingOn, r15d
0x18003dfe8  mov     ebx, eax
0x18003dfea  jz      short loc_18003E011
0x18003dfec  cmp     cs:g_fProviderEnabled, r15d
0x18003dff3  jz      short loc_18003E011
0x18003dff5  test    byte ptr cs:g_ulTraceFlags, 20h
0x18003dffc  jz      short loc_18003E011
0x18003dffe  mov     r8d, eax
0x18003e001  lea     rdx, aTeardownsecure; "TearDownSecureConnection:ApplyControlTo"...
0x18003e008  lea     ecx, [r15+20h]
0x18003e00c  call    LDAPClientPrint
0x18003e011  test    ebx, ebx
0x18003e013  jnz     loc_18003E1D9
0x18003e019  lea     rdx, [rsi+60h]
0x18003e01d  mov     [rsp+130h+buf], r15
0x18003e022  mov     [rsp+130h+var_D8], rdx
0x18003e027  lea     rax, [rsp+130h+len]
0x18003e02c  mov     [rbp+30h+var_98], rax
0x18003e030  lea     rdx, [rbp+30h+var_A8]
0x18003e034  mov     rax, [rsi+18h]
0x18003e038  lea     rcx, [rsi+38h]
0x18003e03c  mov     [rsp+130h+var_E0], rdx
0x18003e041  mov     r9d, 0C11Ch
0x18003e047  lea     rdx, [rbp+30h+var_A0]
0x18003e04b  mov     [rsp+130h+var_BC], 2
0x18003e053  mov     [rsp+130h+var_E8], rdx
0x18003e058  xor     r8d, r8d
0x18003e05b  mov     [rsp+130h+var_F0], r14
0x18003e060  mov     rdx, r14
0x18003e063  mov     [rsp+130h+var_F8], r15d
0x18003e068  mov     [rsp+130h+var_100], r15
0x18003e06d  mov     [rsp+130h+len], r15d
0x18003e072  mov     [rbp+30h+var_9C], r13d
0x18003e076  mov     [rbp+30h+var_A0], r15d
0x18003e07a  mov     rax, [rax+30h]
0x18003e07e  mov     [rsp+130h+var_108], 10h
0x18003e086  mov     [rsp+130h+var_110], r15d
0x18003e08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e090  mov     ebx, eax
0x18003e092  test    eax, eax
0x18003e094  jnz     loc_18003E1D9
0x18003e09a  mov     r8d, [rsp+130h+len]; len
0x18003e09f  xor     r9d, r9d; char *
0x18003e0a2  mov     rdx, [rsp+130h+buf]; buf
0x18003e0a7  mov     rcx, [rsi+10h]; struct ldap_connection *
0x18003e0ab  mov     [rsp+130h+var_110], r15d; unsigned int
0x18003e0b0  call    ?LdapSendRaw@@YAKPEAUldap_connection@@PEADK1K@Z; LdapSendRaw(ldap_connection *,char *,ulong,char *,ulong)
0x18003e0b5  mov     rcx, [rsp+130h+buf]
0x18003e0ba  mov     ebx, eax
0x18003e0bc  mov     rax, [rsi+18h]
0x18003e0c0  mov     rax, [rax+80h]
0x18003e0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0cc  mov     [rsp+130h+len], r15d
0x18003e0d1  mov     [rsp+130h+buf], r15
0x18003e0d6  test    ebx, ebx
0x18003e0d8  jz      short loc_18003E0E4
0x18003e0da  mov     ebx, 4CDh
0x18003e0df  jmp     loc_18003E1D9
0x18003e0e4  mov     ecx, cs:SspiMaxTokenSize
0x18003e0ea  mov     edx, 6365734Ch
0x18003e0ef  call    ldapMalloc
0x18003e0f4  mov     rdi, rax
0x18003e0f7  test    rax, rax
0x18003e0fa  jnz     short loc_18003E104
0x18003e0fc  lea     ebx, [rax+8]
0x18003e0ff  jmp     loc_18003E1D9
0x18003e104  mov     r8d, cs:SspiMaxTokenSize; unsigned int
0x18003e10b  lea     r9, [rbp+30h+var_B0]; unsigned int *
0x18003e10f  mov     rdx, rdi; unsigned __int8 *
0x18003e112  mov     rcx, rsi; this
0x18003e115  call    ?SslBlockingReceive@CryptStream@@QEAAKPEAEKPEAK@Z; CryptStream::SslBlockingReceive(uchar *,ulong,ulong *)
0x18003e11a  test    eax, eax
0x18003e11c  jnz     loc_18003E1C9
0x18003e122  mov     eax, [rbp+30h+var_B0]
0x18003e125  mov     rcx, r13
0x18003e128  mov     dword ptr [rbp+30h+var_70], eax
0x18003e12b  mov     eax, 10h
0x18003e130  mov     dword ptr [rbp+30h+var_70+4], r13d
0x18003e134  mov     [rbp+30h+var_68], rdi
0x18003e138  add     rcx, r13
0x18003e13b  mov     [rbp+rax+30h+var_68], r15
0x18003e140  mov     [rbp+rax+30h+var_70], r15
0x18003e145  lea     rax, [rax+10h]
0x18003e149  cmp     rcx, 4
0x18003e14d  jnz     short loc_18003E138
0x18003e14f  mov     eax, ecx
0x18003e151  mov     dword ptr [rbp+30h+var_90], r15d
0x18003e155  cmp     [rsi+74h], eax
0x18003e158  lea     rdx, [rbp+30h+var_90]
0x18003e15c  mov     rcx, r14
0x18003e15f  cmovb   eax, [rsi+74h]
0x18003e163  xor     r9d, r9d
0x18003e166  mov     dword ptr [rbp+30h+var_90+4], eax
0x18003e169  xor     r8d, r8d
0x18003e16c  lea     rax, [rbp+30h+var_70]
0x18003e170  mov     qword ptr [rbp+30h+var_90+8], rax
0x18003e174  mov     rax, [rsi+8]
0x18003e178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e17d  cmp     eax, 90317h
0x18003e182  jz      short loc_18003E1C4
0x18003e184  cmp     cs:g_fTracingOn, r15d
0x18003e18b  jz      loc_18003E104
0x18003e191  cmp     cs:g_fProviderEnabled, r15d
0x18003e198  jz      loc_18003E104
0x18003e19e  test    byte ptr cs:g_ulTraceFlags, 20h
0x18003e1a5  jz      loc_18003E104
0x18003e1ab  mov     r8d, eax
0x18003e1ae  lea     rdx, aTeardownsecure_0; "TearDownSecureConnection: DecryptMessag"...
0x18003e1b5  mov     ecx, 20h ; ' '
0x18003e1ba  call    LDAPClientPrint
0x18003e1bf  jmp     loc_18003E104
0x18003e1c4  mov     ebx, r15d
0x18003e1c7  jmp     short loc_18003E1D9
0x18003e1c9  cmp     eax, 55h ; 'U'
0x18003e1cc  mov     ebx, 5B4h
0x18003e1d1  mov     ecx, 3Ah ; ':'
0x18003e1d6  cmovnz  ebx, ecx
0x18003e1d9  mov     edx, 6365734Ch
0x18003e1de  mov     rcx, rdi
0x18003e1e1  call    ldapFree
0x18003e1e6  cmp     cs:g_fTracingOn, r15d
0x18003e1ed  jz      short loc_18003E215
0x18003e1ef  cmp     cs:g_fProviderEnabled, r15d
0x18003e1f6  jz      short loc_18003E215
0x18003e1f8  test    byte ptr cs:g_ulTraceFlags, 20h
0x18003e1ff  jz      short loc_18003E215
0x18003e201  mov     r8d, ebx
0x18003e204  lea     rdx, aTeardownsecure_2; "TearDownSecureConnection win32 error is"...
0x18003e20b  mov     ecx, 20h ; ' '
0x18003e210  call    LDAPClientPrint
0x18003e215  lea     rcx, [rbp+30h+var_80]
0x18003e219  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003e21e  mov     eax, ebx
0x18003e220  mov     rcx, [rbp+30h+var_30]
0x18003e224  xor     rcx, rsp; StackCookie
0x18003e227  call    __security_check_cookie
0x18003e22c  lea     r11, [rsp+130h+var_20]
0x18003e234  mov     rbx, [r11+38h]
0x18003e238  mov     rsi, [r11+40h]
0x18003e23c  mov     rsp, r11
0x18003e23f  pop     r15
0x18003e241  pop     r14
0x18003e243  pop     r13
0x18003e245  pop     rdi
0x18003e246  pop     rbp
0x18003e247  retn
```
