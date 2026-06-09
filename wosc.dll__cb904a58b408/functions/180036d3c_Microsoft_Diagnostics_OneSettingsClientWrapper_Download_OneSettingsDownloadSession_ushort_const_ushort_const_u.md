# Microsoft::Diagnostics::OneSettingsClientWrapper::Download(OneSettingsDownloadSession *,ushort const *,ushort const *,ushort const *)

- ea: `0x180036d3c`
- end: `0x1800370b5`
- name: `?Download@OneSettingsClientWrapper@Diagnostics@Microsoft@@QEAAJPEAUOneSettingsDownloadSession@@PEBG11@Z`
- size: `889`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::OneSettingsClientWrapper *__hidden this, struct OneSettingsDownloadSession *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037130`

## callees

- `0x180009c0c`
- `0x18000a7c0`
- `0x18000e5ac`
- `0x18001a64c`
- `0x1800353c0`
- `0x180036d3c`

## import_xrefs

- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x180036d9f`
- `OneSettingsClient!OneSettingsCreateDownloadConfig` at `0x180036d9f`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x180036d78`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x180036dec`
- `OneSettingsClient!OneSettingsSetConfigBoolProperty` at `0x180036dec`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x180036e7e`
- `OneSettingsClient!OneSettingsSetConfigDwordProperty` at `0x180036e7e`
- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x180036efa`
- `OneSettingsClient!OneSettingsSetConfigHandleProperty` at `0x180036efa`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x18003708c`
- `OneSettingsClient!OneSettingsDownloadEndpoint` at `0x18003708c`
- `OneSettingsClient!OneSettingsFreeDownloadResponse` at `0x18003704b`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x180036f76`
- `OneSettingsClient!OneSettingsSetConfigWideStringProperty` at `0x180036f76`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::OneSettingsClientWrapper::Download(
        Microsoft::Diagnostics::OneSettingsClientWrapper *this,
        struct OneSettingsDownloadSession *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  _QWORD *v5; // rsi
  int DownloadConfig; // ebx
  __int64 v11; // rdx
  __int64 *v13; // rbx
  int v14; // r14d
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
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 *v37; // rdi
  __int64 v38; // [rsp+20h] [rbp-28h]
  _BYTE v39[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  __int64 v41; // [rsp+90h] [rbp+48h] BYREF

  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    v41 = *((_QWORD *)this + 1);
    wil::last_error_context::last_error_context((wil::last_error_context *)v39);
    a5 = (const unsigned __int16 *)OneSettingsFreeDownloadConfig;
    wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(&a5, &v41);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v39);
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
            v38);
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
    *((_QWORD *)this + 16) = &qword_18005F908;
    *((_QWORD *)this + 17) = 0;
    v31 = std::_WChar_traits<unsigned short>::length(&String1);
    *((_QWORD *)this + 18) = v32;
    *((_QWORD *)this + 19) = v31;
    v33 = std::_WChar_traits<unsigned short>::length(v32);
    *((_QWORD *)this + 20) = v34;
    *((_QWORD *)this + 21) = v33;
    v35 = std::_WChar_traits<unsigned short>::length(v34);
    *((_QWORD *)this + 22) = v36;
    *((_QWORD *)this + 23) = v35;
    v37 = (__int64 *)((char *)this + 16);
    if ( *v37 )
    {
      v41 = *v37;
      wil::last_error_context::last_error_context((wil::last_error_context *)v39);
      a5 = (const unsigned __int16 *)OneSettingsFreeDownloadResponse;
      wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(&a5, &v41);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v39);
    }
    *v37 = 0;
    v38 = *v5;
    DownloadConfig = OneSettingsDownloadEndpoint(a2, a3, a4, L"v3.0");
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
      v38);
    return (unsigned int)DownloadConfig;
  }
}

```

## disassembly

```asm
0x180036d3c  push    rbp
0x180036d3e  push    rbx
0x180036d3f  push    rsi
0x180036d40  push    rdi
0x180036d41  push    r12
0x180036d43  push    r13
0x180036d45  push    r14
0x180036d47  push    r15
0x180036d49  mov     rbp, rsp
0x180036d4c  sub     rsp, 48h
0x180036d50  lea     rsi, [rcx+8]
0x180036d54  xor     r14d, r14d
0x180036d57  mov     rax, [rsi]
0x180036d5a  mov     r15, r9
0x180036d5d  mov     r12, r8
0x180036d60  mov     r13, rdx
0x180036d63  mov     rdi, rcx
0x180036d66  test    rax, rax
0x180036d69  jz      short loc_180036D99
0x180036d6b  lea     rcx, [rbp+var_18]; this
0x180036d6f  mov     [rbp+arg_0], rax
0x180036d73  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036d78  mov     rax, cs:__imp_OneSettingsFreeDownloadConfig
0x180036d7f  lea     rdx, [rbp+arg_0]
0x180036d83  lea     rcx, [rbp+arg_20]
0x180036d87  mov     [rbp+arg_20], rax
0x180036d8b  call    ??$invoke@P6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@wistd@@YAJ$$QEAP6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@Z; wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(long (*&&)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &)
0x180036d90  lea     rcx, [rbp+var_18]; this
0x180036d94  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036d99  mov     rcx, rsi
0x180036d9c  mov     [rsi], r14
0x180036d9f  call    cs:__imp_OneSettingsCreateDownloadConfig
0x180036da5  mov     ebx, eax
0x180036da7  test    eax, eax
0x180036da9  jns     short loc_180036DCA
0x180036dab  mov     edx, 84h; void *
0x180036db0  mov     rcx, [rbp+40h]; this
0x180036db4  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x180036dbb  mov     r9d, ebx; char *
0x180036dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036dc3  mov     eax, ebx
0x180036dc5  jmp     loc_1800370A4
0x180036dca  mov     rbx, [rdi+18h]
0x180036dce  mov     rbx, [rbx]
0x180036dd1  cmp     [rbx+19h], r14b
0x180036dd5  jnz     loc_180036E61
0x180036ddb  cmp     [rbx+21h], r14b
0x180036ddf  jz      short loc_180036DFC
0x180036de1  movzx   r8d, byte ptr [rbx+20h]
0x180036de6  mov     edx, [rbx+1Ch]
0x180036de9  mov     rcx, [rsi]
0x180036dec  call    cs:__imp_OneSettingsSetConfigBoolProperty
0x180036df2  mov     r14d, eax
0x180036df5  test    eax, eax
0x180036df7  js      short loc_180036E41
0x180036df9  xor     r14d, r14d
0x180036dfc  mov     rcx, [rbx+10h]
0x180036e00  cmp     [rcx+19h], r14b
0x180036e04  jz      short loc_180036E24
0x180036e06  mov     rax, [rbx+8]
0x180036e0a  jmp     short loc_180036E19
0x180036e0c  cmp     rbx, [rax+10h]
0x180036e10  jnz     short loc_180036E1F
0x180036e12  mov     rbx, rax
0x180036e15  mov     rax, [rax+8]
0x180036e19  cmp     [rax+19h], r14b
0x180036e1d  jz      short loc_180036E0C
0x180036e1f  mov     rbx, rax
0x180036e22  jmp     short loc_180036DD1
0x180036e24  mov     rbx, rcx
0x180036e27  mov     rcx, [rcx]
0x180036e2a  cmp     [rcx+19h], r14b
0x180036e2e  jnz     short loc_180036DD1
0x180036e30  mov     rax, [rcx]
0x180036e33  mov     rbx, rcx
0x180036e36  mov     rcx, rax
0x180036e39  cmp     [rax+19h], r14b
0x180036e3d  jz      short loc_180036E30
0x180036e3f  jmp     short loc_180036DD1
0x180036e41  mov     edx, 8Ch; void *
0x180036e46  mov     rcx, [rbp+40h]; this
0x180036e4a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x180036e51  mov     r9d, r14d; char *
0x180036e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e59  mov     eax, r14d
0x180036e5c  jmp     loc_1800370A4
0x180036e61  mov     rbx, [rdi+28h]
0x180036e65  mov     rbx, [rbx]
0x180036e68  cmp     [rbx+19h], r14b
0x180036e6c  jnz     short loc_180036EDD
0x180036e6e  cmp     [rbx+24h], r14b
0x180036e72  jz      short loc_180036E8E
0x180036e74  mov     r8d, [rbx+20h]
0x180036e78  mov     edx, [rbx+1Ch]
0x180036e7b  mov     rcx, [rsi]
0x180036e7e  call    cs:__imp_OneSettingsSetConfigDwordProperty
0x180036e84  mov     r14d, eax
0x180036e87  test    eax, eax
0x180036e89  js      short loc_180036ED3
0x180036e8b  xor     r14d, r14d
0x180036e8e  mov     rcx, [rbx+10h]
0x180036e92  cmp     [rcx+19h], r14b
0x180036e96  jz      short loc_180036EB6
0x180036e98  mov     rax, [rbx+8]
0x180036e9c  jmp     short loc_180036EAB
0x180036e9e  cmp     rbx, [rax+10h]
0x180036ea2  jnz     short loc_180036EB1
0x180036ea4  mov     rbx, rax
0x180036ea7  mov     rax, [rax+8]
0x180036eab  cmp     [rax+19h], r14b
0x180036eaf  jz      short loc_180036E9E
0x180036eb1  mov     rbx, rax
0x180036eb4  jmp     short loc_180036E68
0x180036eb6  mov     rbx, rcx
0x180036eb9  mov     rcx, [rcx]
0x180036ebc  cmp     [rcx+19h], r14b
0x180036ec0  jnz     short loc_180036E68
0x180036ec2  mov     rax, [rcx]
0x180036ec5  mov     rbx, rcx
0x180036ec8  mov     rcx, rax
0x180036ecb  cmp     [rax+19h], r14b
0x180036ecf  jz      short loc_180036EC2
0x180036ed1  jmp     short loc_180036E68
0x180036ed3  mov     edx, 96h
0x180036ed8  jmp     loc_180036E46
0x180036edd  mov     rbx, [rdi+38h]
0x180036ee1  mov     rbx, [rbx]
0x180036ee4  cmp     [rbx+19h], r14b
0x180036ee8  jnz     short loc_180036F59
0x180036eea  cmp     [rbx+30h], r14b
0x180036eee  jz      short loc_180036F0A
0x180036ef0  mov     r8, [rbx+28h]
0x180036ef4  mov     edx, [rbx+20h]
0x180036ef7  mov     rcx, [rsi]
0x180036efa  call    cs:__imp_OneSettingsSetConfigHandleProperty
0x180036f00  mov     r14d, eax
0x180036f03  test    eax, eax
0x180036f05  js      short loc_180036F4F
0x180036f07  xor     r14d, r14d
0x180036f0a  mov     rcx, [rbx+10h]
0x180036f0e  cmp     [rcx+19h], r14b
0x180036f12  jz      short loc_180036F32
0x180036f14  mov     rax, [rbx+8]
0x180036f18  jmp     short loc_180036F27
0x180036f1a  cmp     rbx, [rax+10h]
0x180036f1e  jnz     short loc_180036F2D
0x180036f20  mov     rbx, rax
0x180036f23  mov     rax, [rax+8]
0x180036f27  cmp     [rax+19h], r14b
0x180036f2b  jz      short loc_180036F1A
0x180036f2d  mov     rbx, rax
0x180036f30  jmp     short loc_180036EE4
0x180036f32  mov     rbx, rcx
0x180036f35  mov     rcx, [rcx]
0x180036f38  cmp     [rcx+19h], r14b
0x180036f3c  jnz     short loc_180036EE4
0x180036f3e  mov     rax, [rcx]
0x180036f41  mov     rbx, rcx
0x180036f44  mov     rcx, rax
0x180036f47  cmp     [rax+19h], r14b
0x180036f4b  jz      short loc_180036F3E
0x180036f4d  jmp     short loc_180036EE4
0x180036f4f  mov     edx, 0A0h
0x180036f54  jmp     loc_180036E46
0x180036f59  mov     rbx, [rdi+48h]
0x180036f5d  mov     rbx, [rbx]
0x180036f60  cmp     [rbx+19h], r14b
0x180036f64  jnz     short loc_180036FD5
0x180036f66  cmp     [rbx+30h], r14
0x180036f6a  jz      short loc_180036F86
0x180036f6c  mov     r8, [rbx+28h]
0x180036f70  mov     edx, [rbx+20h]
0x180036f73  mov     rcx, [rsi]
0x180036f76  call    cs:__imp_OneSettingsSetConfigWideStringProperty
0x180036f7c  mov     r14d, eax
0x180036f7f  test    eax, eax
0x180036f81  js      short loc_180036FCB
0x180036f83  xor     r14d, r14d
0x180036f86  mov     rcx, [rbx+10h]
0x180036f8a  cmp     [rcx+19h], r14b
0x180036f8e  jz      short loc_180036FAE
0x180036f90  mov     rax, [rbx+8]
0x180036f94  jmp     short loc_180036FA3
0x180036f96  cmp     rbx, [rax+10h]
0x180036f9a  jnz     short loc_180036FA9
0x180036f9c  mov     rbx, rax
0x180036f9f  mov     rax, [rax+8]
0x180036fa3  cmp     [rax+19h], r14b
0x180036fa7  jz      short loc_180036F96
0x180036fa9  mov     rbx, rax
0x180036fac  jmp     short loc_180036F60
0x180036fae  mov     rbx, rcx
0x180036fb1  mov     rcx, [rcx]
0x180036fb4  cmp     [rcx+19h], r14b
0x180036fb8  jnz     short loc_180036F60
0x180036fba  mov     rax, [rcx]
0x180036fbd  mov     rbx, rcx
0x180036fc0  mov     rcx, rax
0x180036fc3  cmp     [rax+19h], r14b
0x180036fc7  jz      short loc_180036FBA
0x180036fc9  jmp     short loc_180036F60
0x180036fcb  mov     edx, 0AAh
0x180036fd0  jmp     loc_180036E46
0x180036fd5  mov     [rdi+5Ch], r14b
0x180036fd9  lea     rax, qword_18005F908
0x180036fe0  mov     [rdi+64h], r14b
0x180036fe4  lea     rcx, String1
0x180036feb  mov     [rdi+80h], rax
0x180036ff2  mov     [rdi+88h], r14
0x180036ff9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180036ffe  mov     [rdi+90h], rcx
0x180037005  mov     [rdi+98h], rax
0x18003700c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180037011  mov     [rdi+0A0h], rcx
0x180037018  mov     [rdi+0A8h], rax
0x18003701f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180037024  mov     [rdi+0B0h], rcx
0x18003702b  mov     [rdi+0B8h], rax
0x180037032  add     rdi, 10h
0x180037036  mov     rax, [rdi]
0x180037039  test    rax, rax
0x18003703c  jz      short loc_18003706C
0x18003703e  lea     rcx, [rbp+var_18]; this
0x180037042  mov     [rbp+arg_0], rax
0x180037046  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003704b  mov     rax, cs:__imp_OneSettingsFreeDownloadResponse
0x180037052  lea     rdx, [rbp+arg_0]
0x180037056  lea     rcx, [rbp+arg_20]
0x18003705a  mov     [rbp+arg_20], rax
0x18003705e  call    ??$invoke@P6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@wistd@@YAJ$$QEAP6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@Z; wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(long (*&&)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &)
0x180037063  lea     rcx, [rbp+var_18]; this
0x180037067  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003706c  mov     [rdi], r14
0x18003706f  lea     r9, aV30; "v3.0"
0x180037076  mov     rax, [rsi]
0x180037079  mov     r8, r15
0x18003707c  mov     [rsp+48h+var_20], rdi
0x180037081  mov     rdx, r12
0x180037084  mov     rcx, r13
0x180037087  mov     [rsp+48h+var_28], rax
0x18003708c  call    cs:__imp_OneSettingsDownloadEndpoint
0x180037092  mov     ebx, eax
0x180037094  test    eax, eax
0x180037096  jns     short loc_1800370A2
0x180037098  mov     edx, 0B5h
0x18003709d  jmp     loc_180036DB0
0x1800370a2  xor     eax, eax
0x1800370a4  add     rsp, 48h
0x1800370a8  pop     r15
0x1800370aa  pop     r14
0x1800370ac  pop     r13
0x1800370ae  pop     r12
0x1800370b0  pop     rdi
0x1800370b1  pop     rsi
0x1800370b2  pop     rbx
0x1800370b3  pop     rbp
0x1800370b4  retn
```
