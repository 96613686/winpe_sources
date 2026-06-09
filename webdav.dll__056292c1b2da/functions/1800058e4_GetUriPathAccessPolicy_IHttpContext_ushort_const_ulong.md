# GetUriPathAccessPolicy(IHttpContext *,ushort const *,ulong *)

- ea: `0x1800058e4`
- end: `0x180005a55`
- name: `?GetUriPathAccessPolicy@@YAJPEAVIHttpContext@@PEBGPEAK@Z`
- size: `369`
- prototype: `__int64 __fastcall(struct IHttpContext *, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002740`
- `0x180006c54`
- `0x18000e6e0`

## callees

- `0x180001214`
- `0x180001c5c`
- `0x1800058e4`
- `0x180006310`
- `0x1800111f4`
- `0x180019a30`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180005a33`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005a33`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005934`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005934`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059d6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059d6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005912`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005912`

## pseudocode

```c
__int64 __fastcall GetUriPathAccessPolicy(struct IHttpContext *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, struct INativeConfigurationSystem **); // rax
  int AccessForUri; // esi
  struct IHttpContext *v8; // rdx
  struct IHttpUser *v9; // rax
  DAV_AUTH_RULES_ENTRY *v10; // rdi
  DAV_AUTH_RULES_ENTRY *v11; // rbx
  struct INativeConfigurationSystem *v13; // [rsp+30h] [rbp-79h] BYREF
  void *Block[3]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v15[56]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v16; // [rsp+90h] [rbp-19h]
  _BYTE v17[32]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned __int16 *v18; // [rsp+C0h] [rbp+17h]

  STRA::STRA((STRA *)v15);
  Block[0] = 0;
  Block[1] = Block;
  v16 = 0;
  STRU::STRU((STRU *)v17);
  v13 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct INativeConfigurationSystem **))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  AccessForUri = (**v6)(v6, &IID_INativeConfigurationSystem, &v13);
  if ( AccessForUri >= 0 )
  {
    AccessForUri = BuildMetaPathForUri(a1, v13, a2, (struct STRU *)v17, 0);
    if ( AccessForUri >= 0 )
      AccessForUri = DAV_URI_CONFIG::InitializeHelper((DAV_URI_CONFIG *)Block, v8, v13, v18, 0);
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  STRU::~STRU((STRU *)v17);
  if ( AccessForUri >= 0 )
  {
    v9 = (struct IHttpUser *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 48LL))(a1);
    AccessForUri = DAV_URI_CONFIG::QueryAccessForUri((DAV_URI_CONFIG *)Block, v9, a2, a3);
  }
  v10 = (DAV_AUTH_RULES_ENTRY *)Block[0];
  if ( Block[0] )
  {
    do
    {
      v11 = *(DAV_AUTH_RULES_ENTRY **)v10;
      DAV_AUTH_RULES_ENTRY::~DAV_AUTH_RULES_ENTRY(v10);
      operator delete(v10);
      v10 = v11;
    }
    while ( v11 );
  }
  Block[0] = 0;
  STRA::~STRA((STRA *)v15);
  return (unsigned int)AccessForUri;
}

```

## disassembly

```asm
0x1800058e4  push    rbp
0x1800058e6  push    rbx
0x1800058e7  push    rsi
0x1800058e8  push    rdi
0x1800058e9  push    r14
0x1800058eb  lea     rbp, [rsp-37h]
0x1800058f0  sub     rsp, 0E0h
0x1800058f7  mov     rax, cs:__security_cookie
0x1800058fe  xor     rax, rsp
0x180005901  mov     [rbp+57h+var_28], rax
0x180005905  mov     rbx, rcx
0x180005908  mov     r14, r8
0x18000590b  lea     rcx, [rbp+57h+var_A8]
0x18000590f  mov     rdi, rdx
0x180005912  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180005918  lea     rax, [rbp+57h+Block]
0x18000591c  mov     [rbp+57h+Block], 0
0x180005924  lea     rcx, [rbp+57h+var_60]
0x180005928  mov     [rbp+57h+var_B8], rax
0x18000592c  mov     [rbp+57h+var_70], 0
0x180005934  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000593a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180005941  mov     [rbp+57h+var_D0], 0
0x180005949  mov     rax, [rcx]
0x18000594c  mov     rax, [rax+38h]
0x180005950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005955  mov     r9, rax
0x180005958  lea     r8, [rbp+57h+var_D0]
0x18000595c  lea     rdx, IID_INativeConfigurationSystem
0x180005963  mov     rcx, [rax]
0x180005966  mov     rax, [rcx]
0x180005969  mov     rcx, r9
0x18000596c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005971  mov     esi, eax
0x180005973  test    eax, eax
0x180005975  js      short loc_1800059B5
0x180005977  mov     rdx, [rbp+57h+var_D0]; struct INativeConfigurationSystem *
0x18000597b  lea     r9, [rbp+57h+var_60]; struct STRU *
0x18000597f  mov     r8, rdi; unsigned __int16 *
0x180005982  mov     [rsp+100h+var_E0], 0; struct INativeSectionException **
0x18000598b  mov     rcx, rbx; struct IHttpContext *
0x18000598e  call    ?BuildMetaPathForUri@@YAJPEAVIHttpContext@@PEAVINativeConfigurationSystem@@PEBGPEAVSTRU@@PEAPEAVINativeSectionException@@@Z; BuildMetaPathForUri(IHttpContext *,INativeConfigurationSystem *,ushort const *,STRU *,INativeSectionException * *)
0x180005993  mov     esi, eax
0x180005995  test    eax, eax
0x180005997  js      short loc_1800059B5
0x180005999  mov     r9, [rbp+57h+var_40]; unsigned __int16 *
0x18000599d  lea     rcx, [rbp+57h+Block]; this
0x1800059a1  mov     r8, [rbp+57h+var_D0]; struct INativeConfigurationSystem *
0x1800059a5  mov     [rsp+100h+var_E0], 0; struct INativeSectionException **
0x1800059ae  call    ?InitializeHelper@DAV_URI_CONFIG@@AEAAJPEAVIHttpContext@@PEAVINativeConfigurationSystem@@PEBGPEAPEAVINativeSectionException@@@Z; DAV_URI_CONFIG::InitializeHelper(IHttpContext *,INativeConfigurationSystem *,ushort const *,INativeSectionException * *)
0x1800059b3  mov     esi, eax
0x1800059b5  mov     rcx, [rbp+57h+var_D0]
0x1800059b9  test    rcx, rcx
0x1800059bc  jz      short loc_1800059D2
0x1800059be  mov     rax, [rcx]
0x1800059c1  mov     rax, [rax+10h]
0x1800059c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ca  mov     [rbp+57h+var_D0], 0
0x1800059d2  lea     rcx, [rbp+57h+var_60]
0x1800059d6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800059dc  test    esi, esi
0x1800059de  js      short loc_180005A03
0x1800059e0  mov     rax, [rbx]
0x1800059e3  mov     rcx, rbx
0x1800059e6  mov     rax, [rax+30h]
0x1800059ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ef  mov     rdx, rax; struct IHttpUser *
0x1800059f2  lea     rcx, [rbp+57h+Block]; this
0x1800059f6  mov     r9, r14; unsigned int *
0x1800059f9  mov     r8, rdi; unsigned __int16 *
0x1800059fc  call    ?QueryAccessForUri@DAV_URI_CONFIG@@QEAAJPEAVIHttpUser@@PEBGPEAK@Z; DAV_URI_CONFIG::QueryAccessForUri(IHttpUser *,ushort const *,ulong *)
0x180005a01  mov     esi, eax
0x180005a03  mov     rdi, [rbp+57h+Block]
0x180005a07  test    rdi, rdi
0x180005a0a  jz      short loc_180005A27
0x180005a0c  mov     rbx, [rdi]
0x180005a0f  mov     rcx, rdi; this
0x180005a12  call    ??1DAV_AUTH_RULES_ENTRY@@QEAA@XZ; DAV_AUTH_RULES_ENTRY::~DAV_AUTH_RULES_ENTRY(void)
0x180005a17  mov     rcx, rdi; Block
0x180005a1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a1f  mov     rdi, rbx
0x180005a22  test    rbx, rbx
0x180005a25  jnz     short loc_180005A0C
0x180005a27  lea     rcx, [rbp+57h+var_A8]
0x180005a2b  mov     [rbp+57h+Block], 0
0x180005a33  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005a39  mov     eax, esi
0x180005a3b  mov     rcx, [rbp+57h+var_28]
0x180005a3f  xor     rcx, rsp; StackCookie
0x180005a42  call    __security_check_cookie
0x180005a47  add     rsp, 0E0h
0x180005a4e  pop     r14
0x180005a50  pop     rdi
0x180005a51  pop     rsi
0x180005a52  pop     rbx
0x180005a53  pop     rbp
0x180005a54  retn
```
