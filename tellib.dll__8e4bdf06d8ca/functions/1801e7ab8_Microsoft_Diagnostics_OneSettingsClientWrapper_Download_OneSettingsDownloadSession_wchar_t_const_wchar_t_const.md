# Microsoft::Diagnostics::OneSettingsClientWrapper::Download(OneSettingsDownloadSession *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1801e7ab8`
- end: `0x1801e7e3a`
- name: `?Download@OneSettingsClientWrapper@Diagnostics@Microsoft@@QEAAJPEAUOneSettingsDownloadSession@@PEB_W11@Z`
- size: `898`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::OneSettingsClientWrapper *__hidden this, struct OneSettingsDownloadSession *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801e7e40`

## callees

- `0x180026ecc`
- `0x18005af1c`
- `0x1800b83bc`
- `0x18016ff48`
- `0x1801e7ab8`

## import_xrefs

- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x1801e7dcc`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x1801e7e0a`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x1801e7e0a`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x1801e7d02`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x1801e7d02`
- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x1801e7c82`
- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x1801e7c82`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x1801e7af3`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x1801e7c02`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x1801e7c02`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x1801e7b6d`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x1801e7b6d`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x1801e7b1a`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x1801e7b1a`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::OneSettingsClientWrapper::Download(
        Microsoft::Diagnostics::OneSettingsClientWrapper *this,
        struct OneSettingsDownloadSession *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  _QWORD *v5; // r14
  int DownloadConfig; // ebx
  __int64 v11; // rdx
  __int64 *v13; // rbx
  int v14; // edi
  __int64 **v15; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v18; // rdx
  __int64 *v19; // rbx
  __int64 **v20; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 *v23; // rbx
  __int64 **v24; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  __int64 *v27; // rbx
  __int64 **v28; // rcx
  __int64 *jj; // rax
  __int64 *kk; // rcx
  __int64 *v31; // rsi
  const wchar_t *v32; // r9
  __int64 v33; // [rsp+20h] [rbp-28h]
  __int64 v34; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v35[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  __int64 v37; // [rsp+90h] [rbp+48h] BYREF

  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    v37 = *((_QWORD *)this + 1);
    wil::last_error_context::last_error_context((wil::last_error_context *)v35);
    v34 = OneSettingsFreeDownloadConfig;
    wistd::invoke<void * (*)(void *),void * &>(&v34, &v37);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v35);
  }
  *v5 = 0;
  DownloadConfig = OneSettingsCreateDownloadConfig(v5);
  if ( DownloadConfig >= 0 )
  {
    v13 = (__int64 *)**((_QWORD **)this + 3);
    while ( !*((_BYTE *)v13 + 25) )
    {
      if ( *((_BYTE *)v13 + 33) )
      {
        v14 = OneSettingsSetConfigBoolProperty(*v5, *((unsigned int *)v13 + 7), *((unsigned __int8 *)v13 + 32));
        if ( v14 < 0 )
        {
          v18 = 140;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
            (const char *)(unsigned int)v14,
            v33);
          return (unsigned int)v14;
        }
      }
      v15 = (__int64 **)v13[2];
      if ( *((_BYTE *)v15 + 25) )
      {
        for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v13 = i;
        v13 = i;
      }
      else
      {
        v13 = (__int64 *)v13[2];
        for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v13 = j;
      }
    }
    v19 = (__int64 *)**((_QWORD **)this + 5);
    while ( !*((_BYTE *)v19 + 25) )
    {
      if ( *((_BYTE *)v19 + 36) )
      {
        v14 = OneSettingsSetConfigDwordProperty(*v5, *((unsigned int *)v19 + 7), *((unsigned int *)v19 + 8));
        if ( v14 < 0 )
        {
          v18 = 150;
          goto LABEL_20;
        }
      }
      v20 = (__int64 **)v19[2];
      if ( *((_BYTE *)v20 + 25) )
      {
        for ( k = (__int64 *)v19[1]; !*((_BYTE *)k + 25) && v19 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v19 = k;
        v19 = k;
      }
      else
      {
        v19 = (__int64 *)v19[2];
        for ( m = *v20; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v19 = m;
      }
    }
    v23 = (__int64 *)**((_QWORD **)this + 7);
    while ( !*((_BYTE *)v23 + 25) )
    {
      if ( *((_BYTE *)v23 + 48) )
      {
        v14 = OneSettingsSetConfigHandleProperty(*v5, *((unsigned int *)v23 + 8), v23[5]);
        if ( v14 < 0 )
        {
          v18 = 160;
          goto LABEL_20;
        }
      }
      v24 = (__int64 **)v23[2];
      if ( *((_BYTE *)v24 + 25) )
      {
        for ( n = (__int64 *)v23[1]; !*((_BYTE *)n + 25) && v23 == (__int64 *)n[2]; n = (__int64 *)n[1] )
          v23 = n;
        v23 = n;
      }
      else
      {
        v23 = (__int64 *)v23[2];
        for ( ii = *v24; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
          v23 = ii;
      }
    }
    v27 = (__int64 *)**((_QWORD **)this + 9);
    while ( !*((_BYTE *)v27 + 25) )
    {
      if ( v27[6] )
      {
        v14 = OneSettingsSetConfigWideStringProperty(*v5, *((unsigned int *)v27 + 8), v27[5]);
        if ( v14 < 0 )
        {
          v18 = 170;
          goto LABEL_20;
        }
      }
      v28 = (__int64 **)v27[2];
      if ( *((_BYTE *)v28 + 25) )
      {
        for ( jj = (__int64 *)v27[1]; !*((_BYTE *)jj + 25) && v27 == (__int64 *)jj[2]; jj = (__int64 *)jj[1] )
          v27 = jj;
        v27 = jj;
      }
      else
      {
        v27 = (__int64 *)v27[2];
        for ( kk = *v28; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
          v27 = kk;
      }
    }
    *((_BYTE *)this + 92) = 0;
    *((_BYTE *)this + 100) = 0;
    *((_QWORD *)this + 16) = &word_1803725C0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = &Src;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = &Src;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = &Src;
    *((_QWORD *)this + 23) = 0;
    v31 = (__int64 *)((char *)this + 16);
    if ( *v31 )
    {
      v37 = *v31;
      wil::last_error_context::last_error_context((wil::last_error_context *)&v34);
      v35[0] = OneSettingsFreeDownloadResponse;
      wistd::invoke<void * (*)(void *),void * &>(v35, &v37);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v34);
    }
    v32 = a5;
    *v31 = 0;
    v33 = *v5;
    DownloadConfig = OneSettingsDownloadEndpoint(a2, a3, a4, v32);
    if ( DownloadConfig < 0 )
    {
      v11 = 181;
      goto LABEL_5;
    }
    return 0;
  }
  else
  {
    v11 = 132;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
      (const char *)(unsigned int)DownloadConfig,
      v33);
    return (unsigned int)DownloadConfig;
  }
}

```

## disassembly

```asm
0x1801e7ab8  push    rbp
0x1801e7aba  push    rbx
0x1801e7abb  push    rsi
0x1801e7abc  push    rdi
0x1801e7abd  push    r12
0x1801e7abf  push    r13
0x1801e7ac1  push    r14
0x1801e7ac3  push    r15
0x1801e7ac5  mov     rbp, rsp
0x1801e7ac8  sub     rsp, 48h
0x1801e7acc  lea     r14, [rcx+8]
0x1801e7ad0  xor     edi, edi
0x1801e7ad2  mov     rax, [r14]
0x1801e7ad5  mov     r15, r9
0x1801e7ad8  mov     r12, r8
0x1801e7adb  mov     r13, rdx
0x1801e7ade  mov     rsi, rcx
0x1801e7ae1  test    rax, rax
0x1801e7ae4  jz      short loc_1801E7B14
0x1801e7ae6  lea     rcx, [rbp+var_10]; this
0x1801e7aea  mov     [rbp+arg_0], rax
0x1801e7aee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801e7af3  mov     rax, cs:__imp_OneSettingsFreeDownloadConfig
0x1801e7afa  lea     rdx, [rbp+arg_0]
0x1801e7afe  lea     rcx, [rbp+var_18]
0x1801e7b02  mov     [rbp+var_18], rax
0x1801e7b06  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1801e7b0b  lea     rcx, [rbp+var_10]; this
0x1801e7b0f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801e7b14  mov     rcx, r14
0x1801e7b17  mov     [r14], rdi
0x1801e7b1a  call    cs:__imp_OneSettingsCreateDownloadConfig
0x1801e7b21  nop     dword ptr [rax+rax+00h]
0x1801e7b26  mov     ebx, eax
0x1801e7b28  test    eax, eax
0x1801e7b2a  jns     short loc_1801E7B4B
0x1801e7b2c  mov     edx, 84h; void *
0x1801e7b31  mov     rcx, [rbp+40h]; this
0x1801e7b35  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x1801e7b3c  mov     r9d, ebx; char *
0x1801e7b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e7b44  mov     eax, ebx
0x1801e7b46  jmp     loc_1801E7E28
0x1801e7b4b  mov     rbx, [rsi+18h]
0x1801e7b4f  mov     rbx, [rbx]
0x1801e7b52  cmp     [rbx+19h], dil
0x1801e7b56  jnz     loc_1801E7BE5
0x1801e7b5c  cmp     [rbx+21h], dil
0x1801e7b60  jz      short loc_1801E7B81
0x1801e7b62  movzx   r8d, byte ptr [rbx+20h]
0x1801e7b67  mov     edx, [rbx+1Ch]
0x1801e7b6a  mov     rcx, [r14]
0x1801e7b6d  call    cs:__imp_OneSettingsSetConfigBoolProperty
0x1801e7b74  nop     dword ptr [rax+rax+00h]
0x1801e7b79  mov     edi, eax
0x1801e7b7b  test    eax, eax
0x1801e7b7d  js      short loc_1801E7BC6
0x1801e7b7f  xor     edi, edi
0x1801e7b81  mov     rcx, [rbx+10h]
0x1801e7b85  cmp     [rcx+19h], dil
0x1801e7b89  jz      short loc_1801E7BA9
0x1801e7b8b  mov     rax, [rbx+8]
0x1801e7b8f  jmp     short loc_1801E7B9E
0x1801e7b91  cmp     rbx, [rax+10h]
0x1801e7b95  jnz     short loc_1801E7BA4
0x1801e7b97  mov     rbx, rax
0x1801e7b9a  mov     rax, [rax+8]
0x1801e7b9e  cmp     [rax+19h], dil
0x1801e7ba2  jz      short loc_1801E7B91
0x1801e7ba4  mov     rbx, rax
0x1801e7ba7  jmp     short loc_1801E7B52
0x1801e7ba9  mov     rbx, rcx
0x1801e7bac  mov     rcx, [rcx]
0x1801e7baf  cmp     [rcx+19h], dil
0x1801e7bb3  jnz     short loc_1801E7B52
0x1801e7bb5  mov     rax, [rcx]
0x1801e7bb8  mov     rbx, rcx
0x1801e7bbb  mov     rcx, rax
0x1801e7bbe  cmp     [rax+19h], dil
0x1801e7bc2  jz      short loc_1801E7BB5
0x1801e7bc4  jmp     short loc_1801E7B52
0x1801e7bc6  mov     edx, 8Ch; void *
0x1801e7bcb  mov     rcx, [rbp+40h]; this
0x1801e7bcf  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x1801e7bd6  mov     r9d, edi; char *
0x1801e7bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e7bde  mov     eax, edi
0x1801e7be0  jmp     loc_1801E7E28
0x1801e7be5  mov     rbx, [rsi+28h]
0x1801e7be9  mov     rbx, [rbx]
0x1801e7bec  cmp     [rbx+19h], dil
0x1801e7bf0  jnz     short loc_1801E7C65
0x1801e7bf2  cmp     [rbx+24h], dil
0x1801e7bf6  jz      short loc_1801E7C16
0x1801e7bf8  mov     r8d, [rbx+20h]
0x1801e7bfc  mov     edx, [rbx+1Ch]
0x1801e7bff  mov     rcx, [r14]
0x1801e7c02  call    cs:__imp_OneSettingsSetConfigDwordProperty
0x1801e7c09  nop     dword ptr [rax+rax+00h]
0x1801e7c0e  mov     edi, eax
0x1801e7c10  test    eax, eax
0x1801e7c12  js      short loc_1801E7C5B
0x1801e7c14  xor     edi, edi
0x1801e7c16  mov     rcx, [rbx+10h]
0x1801e7c1a  cmp     [rcx+19h], dil
0x1801e7c1e  jz      short loc_1801E7C3E
0x1801e7c20  mov     rax, [rbx+8]
0x1801e7c24  jmp     short loc_1801E7C33
0x1801e7c26  cmp     rbx, [rax+10h]
0x1801e7c2a  jnz     short loc_1801E7C39
0x1801e7c2c  mov     rbx, rax
0x1801e7c2f  mov     rax, [rax+8]
0x1801e7c33  cmp     [rax+19h], dil
0x1801e7c37  jz      short loc_1801E7C26
0x1801e7c39  mov     rbx, rax
0x1801e7c3c  jmp     short loc_1801E7BEC
0x1801e7c3e  mov     rbx, rcx
0x1801e7c41  mov     rcx, [rcx]
0x1801e7c44  cmp     [rcx+19h], dil
0x1801e7c48  jnz     short loc_1801E7BEC
0x1801e7c4a  mov     rax, [rcx]
0x1801e7c4d  mov     rbx, rcx
0x1801e7c50  mov     rcx, rax
0x1801e7c53  cmp     [rax+19h], dil
0x1801e7c57  jz      short loc_1801E7C4A
0x1801e7c59  jmp     short loc_1801E7BEC
0x1801e7c5b  mov     edx, 96h
0x1801e7c60  jmp     loc_1801E7BCB
0x1801e7c65  mov     rbx, [rsi+38h]
0x1801e7c69  mov     rbx, [rbx]
0x1801e7c6c  cmp     [rbx+19h], dil
0x1801e7c70  jnz     short loc_1801E7CE5
0x1801e7c72  cmp     [rbx+30h], dil
0x1801e7c76  jz      short loc_1801E7C96
0x1801e7c78  mov     r8, [rbx+28h]
0x1801e7c7c  mov     edx, [rbx+20h]
0x1801e7c7f  mov     rcx, [r14]
0x1801e7c82  call    cs:__imp_OneSettingsSetConfigHandleProperty
0x1801e7c89  nop     dword ptr [rax+rax+00h]
0x1801e7c8e  mov     edi, eax
0x1801e7c90  test    eax, eax
0x1801e7c92  js      short loc_1801E7CDB
0x1801e7c94  xor     edi, edi
0x1801e7c96  mov     rcx, [rbx+10h]
0x1801e7c9a  cmp     [rcx+19h], dil
0x1801e7c9e  jz      short loc_1801E7CBE
0x1801e7ca0  mov     rax, [rbx+8]
0x1801e7ca4  jmp     short loc_1801E7CB3
0x1801e7ca6  cmp     rbx, [rax+10h]
0x1801e7caa  jnz     short loc_1801E7CB9
0x1801e7cac  mov     rbx, rax
0x1801e7caf  mov     rax, [rax+8]
0x1801e7cb3  cmp     [rax+19h], dil
0x1801e7cb7  jz      short loc_1801E7CA6
0x1801e7cb9  mov     rbx, rax
0x1801e7cbc  jmp     short loc_1801E7C6C
0x1801e7cbe  mov     rbx, rcx
0x1801e7cc1  mov     rcx, [rcx]
0x1801e7cc4  cmp     [rcx+19h], dil
0x1801e7cc8  jnz     short loc_1801E7C6C
0x1801e7cca  mov     rax, [rcx]
0x1801e7ccd  mov     rbx, rcx
0x1801e7cd0  mov     rcx, rax
0x1801e7cd3  cmp     [rax+19h], dil
0x1801e7cd7  jz      short loc_1801E7CCA
0x1801e7cd9  jmp     short loc_1801E7C6C
0x1801e7cdb  mov     edx, 0A0h
0x1801e7ce0  jmp     loc_1801E7BCB
0x1801e7ce5  mov     rbx, [rsi+48h]
0x1801e7ce9  mov     rbx, [rbx]
0x1801e7cec  cmp     [rbx+19h], dil
0x1801e7cf0  jnz     short loc_1801E7D65
0x1801e7cf2  cmp     [rbx+30h], rdi
0x1801e7cf6  jz      short loc_1801E7D16
0x1801e7cf8  mov     r8, [rbx+28h]
0x1801e7cfc  mov     edx, [rbx+20h]
0x1801e7cff  mov     rcx, [r14]
0x1801e7d02  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x1801e7d09  nop     dword ptr [rax+rax+00h]
0x1801e7d0e  mov     edi, eax
0x1801e7d10  test    eax, eax
0x1801e7d12  js      short loc_1801E7D5B
0x1801e7d14  xor     edi, edi
0x1801e7d16  mov     rcx, [rbx+10h]
0x1801e7d1a  cmp     [rcx+19h], dil
0x1801e7d1e  jz      short loc_1801E7D3E
0x1801e7d20  mov     rax, [rbx+8]
0x1801e7d24  jmp     short loc_1801E7D33
0x1801e7d26  cmp     rbx, [rax+10h]
0x1801e7d2a  jnz     short loc_1801E7D39
0x1801e7d2c  mov     rbx, rax
0x1801e7d2f  mov     rax, [rax+8]
0x1801e7d33  cmp     [rax+19h], dil
0x1801e7d37  jz      short loc_1801E7D26
0x1801e7d39  mov     rbx, rax
0x1801e7d3c  jmp     short loc_1801E7CEC
0x1801e7d3e  mov     rbx, rcx
0x1801e7d41  mov     rcx, [rcx]
0x1801e7d44  cmp     [rcx+19h], dil
0x1801e7d48  jnz     short loc_1801E7CEC
0x1801e7d4a  mov     rax, [rcx]
0x1801e7d4d  mov     rbx, rcx
0x1801e7d50  mov     rcx, rax
0x1801e7d53  cmp     [rax+19h], dil
0x1801e7d57  jz      short loc_1801E7D4A
0x1801e7d59  jmp     short loc_1801E7CEC
0x1801e7d5b  mov     edx, 0AAh
0x1801e7d60  jmp     loc_1801E7BCB
0x1801e7d65  mov     [rsi+5Ch], dil
0x1801e7d69  lea     rax, word_1803725C0
0x1801e7d70  mov     [rsi+64h], dil
0x1801e7d74  mov     [rsi+80h], rax
0x1801e7d7b  lea     rax, Src
0x1801e7d82  mov     [rsi+88h], rdi
0x1801e7d89  mov     [rsi+90h], rax
0x1801e7d90  mov     [rsi+98h], rdi
0x1801e7d97  mov     [rsi+0A0h], rax
0x1801e7d9e  mov     [rsi+0A8h], rdi
0x1801e7da5  mov     [rsi+0B0h], rax
0x1801e7dac  mov     [rsi+0B8h], rdi
0x1801e7db3  add     rsi, 10h
0x1801e7db7  mov     rax, [rsi]
0x1801e7dba  test    rax, rax
0x1801e7dbd  jz      short loc_1801E7DED
0x1801e7dbf  lea     rcx, [rbp+var_18]; this
0x1801e7dc3  mov     [rbp+arg_0], rax
0x1801e7dc7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801e7dcc  mov     rax, cs:__imp_OneSettingsFreeDownloadResponse
0x1801e7dd3  lea     rdx, [rbp+arg_0]
0x1801e7dd7  lea     rcx, [rbp+var_10]
0x1801e7ddb  mov     [rbp+var_10], rax
0x1801e7ddf  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1801e7de4  lea     rcx, [rbp+var_18]; this
0x1801e7de8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801e7ded  mov     r9, [rbp+arg_20]
0x1801e7df1  mov     r8, r15
0x1801e7df4  mov     [rsi], rdi
0x1801e7df7  mov     rdx, r12
0x1801e7dfa  mov     rax, [r14]
0x1801e7dfd  mov     rcx, r13
0x1801e7e00  mov     [rsp+48h+var_20], rsi
0x1801e7e05  mov     [rsp+48h+var_28], rax
0x1801e7e0a  call    cs:__imp_OneSettingsDownloadEndpoint
0x1801e7e11  nop     dword ptr [rax+rax+00h]
0x1801e7e16  mov     ebx, eax
0x1801e7e18  test    eax, eax
0x1801e7e1a  jns     short loc_1801E7E26
0x1801e7e1c  mov     edx, 0B5h
0x1801e7e21  jmp     loc_1801E7B31
0x1801e7e26  xor     eax, eax
0x1801e7e28  add     rsp, 48h
0x1801e7e2c  pop     r15
0x1801e7e2e  pop     r14
0x1801e7e30  pop     r13
0x1801e7e32  pop     r12
0x1801e7e34  pop     rdi
0x1801e7e35  pop     rsi
0x1801e7e36  pop     rbx
0x1801e7e37  pop     rbp
0x1801e7e38  retn
```
