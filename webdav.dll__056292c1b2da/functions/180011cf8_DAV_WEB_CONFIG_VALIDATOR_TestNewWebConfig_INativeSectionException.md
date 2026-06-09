# DAV_WEB_CONFIG_VALIDATOR::TestNewWebConfig(INativeSectionException * *)

- ea: `0x180011cf8`
- end: `0x180011e0b`
- name: `?TestNewWebConfig@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAPEAVINativeSectionException@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(DAV_WEB_CONFIG_VALIDATOR *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f30`

## callees

- `0x180011358`
- `0x18001170c`
- `0x180011cf8`
- `0x180019a30`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180011d38`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011d38`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011ddf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011ddf`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::TestNewWebConfig(
        DAV_WEB_CONFIG_VALIDATOR *this,
        struct INativeSectionException **a2)
{
  int v4; // eax
  struct INativeConfigurationSystem *v5; // rbx
  int v6; // edi
  DAV_WEB_CONFIG_VALIDATOR *v7; // rcx
  struct INativeConfigFile *v9; // [rsp+30h] [rbp-50h] BYREF
  struct INativeConfigurationSystem *v10; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v12; // [rsp+60h] [rbp-20h]

  v10 = 0;
  v9 = 0;
  STRU::STRU((STRU *)v11);
  v4 = DAV_WEB_CONFIG_VALIDATOR::CreateTestConfigSystem(this, &v10);
  v5 = v10;
  v6 = v4;
  if ( v4 >= 0 )
  {
    v6 = BuildMetaPathForUri(
           *((struct IHttpContext **)this + 1),
           v10,
           *((const unsigned __int16 **)this + 10),
           (struct STRU *)v11,
           a2);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, unsigned __int16 *, struct INativeConfigFile **, _QWORD))(*(_QWORD *)v5 + 88LL))(
             v5,
             v12,
             &v9,
             0);
      if ( v6 >= 0 )
        v6 = DAV_WEB_CONFIG_VALIDATOR::IssueTestQueries(v7, v5, v9, v12, a2);
    }
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(struct INativeConfigFile *))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v5 + 16LL))(v5);
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011cf8  mov     [rsp-18h+arg_10], rbx
0x180011cfd  mov     [rsp-18h+arg_18], rsi
0x180011d02  push    rbp
0x180011d03  push    rdi
0x180011d04  push    r14
0x180011d06  mov     rbp, rsp
0x180011d09  sub     rsp, 80h
0x180011d10  mov     rax, cs:__security_cookie
0x180011d17  xor     rax, rsp
0x180011d1a  mov     [rbp+var_8], rax
0x180011d1e  mov     rsi, rcx
0x180011d21  mov     [rbp+var_48], 0
0x180011d29  lea     rcx, [rbp+var_40]
0x180011d2d  mov     [rbp+var_50], 0
0x180011d35  mov     r14, rdx
0x180011d38  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011d3e  lea     rdx, [rbp+var_48]; struct INativeConfigurationSystem **
0x180011d42  mov     rcx, rsi; this
0x180011d45  call    ?CreateTestConfigSystem@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAPEAVINativeConfigurationSystem@@@Z; DAV_WEB_CONFIG_VALIDATOR::CreateTestConfigSystem(INativeConfigurationSystem * *)
0x180011d4a  mov     rbx, [rbp+var_48]
0x180011d4e  mov     edi, eax
0x180011d50  test    eax, eax
0x180011d52  js      short loc_180011DAA
0x180011d54  mov     r8, [rsi+50h]; unsigned __int16 *
0x180011d58  lea     r9, [rbp+var_40]; struct STRU *
0x180011d5c  mov     rcx, [rsi+8]; struct IHttpContext *
0x180011d60  mov     rdx, rbx; struct INativeConfigurationSystem *
0x180011d63  mov     [rsp+80h+var_60], r14; struct INativeSectionException **
0x180011d68  call    ?BuildMetaPathForUri@@YAJPEAVIHttpContext@@PEAVINativeConfigurationSystem@@PEBGPEAVSTRU@@PEAPEAVINativeSectionException@@@Z; BuildMetaPathForUri(IHttpContext *,INativeConfigurationSystem *,ushort const *,STRU *,INativeSectionException * *)
0x180011d6d  mov     edi, eax
0x180011d6f  test    eax, eax
0x180011d71  js      short loc_180011DAA
0x180011d73  mov     rax, [rbx]
0x180011d76  lea     r8, [rbp+var_50]
0x180011d7a  mov     rdx, [rbp+var_20]
0x180011d7e  xor     r9d, r9d
0x180011d81  mov     rcx, rbx
0x180011d84  mov     rax, [rax+58h]
0x180011d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d8d  mov     edi, eax
0x180011d8f  test    eax, eax
0x180011d91  js      short loc_180011DAA
0x180011d93  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180011d97  mov     rdx, rbx; struct INativeConfigurationSystem *
0x180011d9a  mov     r8, [rbp+var_50]; struct INativeConfigFile *
0x180011d9e  mov     [rsp+80h+var_60], r14; struct INativeSectionException **
0x180011da3  call    ?IssueTestQueries@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAVINativeConfigurationSystem@@PEAVINativeConfigFile@@PEBGPEAPEAVINativeSectionException@@@Z; DAV_WEB_CONFIG_VALIDATOR::IssueTestQueries(INativeConfigurationSystem *,INativeConfigFile *,ushort const *,INativeSectionException * *)
0x180011da8  mov     edi, eax
0x180011daa  mov     rcx, [rbp+var_50]
0x180011dae  test    rcx, rcx
0x180011db1  jz      short loc_180011DC7
0x180011db3  mov     rax, [rcx]
0x180011db6  mov     rax, [rax+10h]
0x180011dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dbf  mov     [rbp+var_50], 0
0x180011dc7  test    rbx, rbx
0x180011dca  jz      short loc_180011DDB
0x180011dcc  mov     rax, [rbx]
0x180011dcf  mov     rcx, rbx
0x180011dd2  mov     rax, [rax+10h]
0x180011dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ddb  lea     rcx, [rbp+var_40]
0x180011ddf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011de5  mov     eax, edi
0x180011de7  mov     rcx, [rbp+var_8]
0x180011deb  xor     rcx, rsp; StackCookie
0x180011dee  call    __security_check_cookie
0x180011df3  lea     r11, [rsp+80h+var_s0]
0x180011dfb  mov     rbx, [r11+30h]
0x180011dff  mov     rsi, [r11+38h]
0x180011e03  mov     rsp, r11
0x180011e06  pop     r14
0x180011e08  pop     rdi
0x180011e09  pop     rbp
0x180011e0a  retn
```
