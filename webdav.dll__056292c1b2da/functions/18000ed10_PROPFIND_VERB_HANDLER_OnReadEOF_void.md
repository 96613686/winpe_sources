# PROPFIND_VERB_HANDLER::OnReadEOF(void)

- ea: `0x18000ed10`
- end: `0x18000f03b`
- name: `?OnReadEOF@PROPFIND_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ`
- size: `811`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x18000e6e0`
- `0x18000ec34`
- `0x18000ed10`
- `0x180013254`
- `0x180015204`
- `0x18001a068`
- `0x18001a314`
- `0x18001b2cc`
- `0x18001f128`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ef32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f018`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000ef32`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f018`
- `XmlLite!CreateXmlReader` at `0x18000ed67`
- `XmlLite!CreateXmlReader` at `0x18000ed67`

## pseudocode

```c
__int64 __fastcall PROPFIND_VERB_HANDLER::OnReadEOF(__int64 a1)
{
  PROPFIND_VERB_HANDLER *v1; // rdi
  HRESULT v3; // ebx
  _DWORD *v4; // rdx
  struct IIS_VDIR *LongestVDirPrefix; // rax
  struct IHttpServer *v6; // r12
  int v7; // r15d
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rdi
  struct IBaseFileSystem *v10; // r14
  __int64 v11; // rsi
  void *EffectiveToken; // rcx
  unsigned int v13; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  void **v19; // [rsp+50h] [rbp-20h] BYREF
  HRESULT v20; // [rsp+58h] [rbp-18h]
  PROPFIND_VERB_HANDLER *v21; // [rsp+60h] [rbp-10h]
  BOOL v22; // [rsp+B0h] [rbp+40h]
  int v23; // [rsp+B8h] [rbp+48h]
  void *ppvObject; // [rsp+C0h] [rbp+50h] BYREF

  v1 = (PROPFIND_VERB_HANDLER *)(a1 - 296);
  v22 = 0;
  v17 = 0;
  v18 = 0;
  if ( *(_QWORD *)(a1 - 296 + 368) )
  {
    ppvObject = 0;
    v3 = CreateXmlReader(&stru_180028158, &ppvObject, 0);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a1 + 64);
      if ( v3 >= 0 )
      {
        v3 = ParsePropfind(
               *(struct IHttpContext **)(a1 - 288),
               (struct IXmlReader *)ppvObject,
               (struct DAV_NAMESPACE_SET *)(a1 + 256),
               (enum DAV_PROPFIND_TYPE *)(a1 + 5744),
               *(_DWORD *)(*(_QWORD *)(a1 - 272) + 8LL));
        v22 = v3 < 0;
      }
    }
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    if ( v3 < 0 )
      goto LABEL_25;
  }
  else
  {
    *(_DWORD *)(a1 + 5744) = 0;
  }
  v3 = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v17, *(struct IHttpContext **)(a1 - 288));
  if ( v3 >= 0 )
  {
    v4 = *(_DWORD **)(a1 - 272);
    v23 = *(_DWORD *)(a1 + 5748);
    if ( v23 )
    {
      v6 = g_pGlobalInfo;
      v19 = &PROPFIND_URI_ENUMERATOR::`vftable';
      v20 = 0;
      v21 = v1;
      v7 = (v4[6] != 0 ? 0x18 : 0) | 0x8000;
      if ( v4[8] )
        v7 = v4[6] != 0 ? 0x18 : 0;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
      v8 = *(const unsigned __int16 **)(a1 - 112);
      v9 = *(const unsigned __int16 **)(a1 - 224);
      v10 = *(struct IBaseFileSystem **)(a1 - 56);
      v11 = *(_QWORD *)(a1 - 272);
      EffectiveToken = GetEffectiveToken(*(struct IHttpContext **)(a1 - 288));
      v13 = v7 | 1;
      if ( v23 != 2 )
        v13 = v7;
      v3 = EnumUri(
             EffectiveToken,
             (struct IIS_VDIR_CONFIG *)(v11 + 64),
             v10,
             (struct IUriEnumerator *)&v19,
             v9,
             v8,
             v13);
      if ( v3 >= 0 )
        v3 = v20;
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v6 + 32LL))(v6);
      v1 = (PROPFIND_VERB_HANDLER *)(a1 - 296);
    }
    else
    {
      LongestVDirPrefix = IIS_VDIR_CONFIG::FindLongestVDirPrefix(
                            (IIS_VDIR_CONFIG *)(v4 + 16),
                            *(const unsigned __int16 **)(a1 - 224));
      v3 = PROPFIND_VERB_HANDLER::DoOnePropfind(
             v1,
             LongestVDirPrefix,
             *(const unsigned __int16 **)(a1 - 224),
             *(const unsigned __int16 **)(a1 - 112));
    }
    if ( v3 >= 0 )
    {
      if ( !*(_DWORD *)(a1 + 248)
        || (v3 = XML_RESPONDER::FinishXmlMultistatusResponse((XML_RESPONDER *)(a1 + 152)), v3 >= 0) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 288) + 200LL))(*(_QWORD *)(a1 - 288));
        if ( v17 )
          RevertToSelf();
        return 0;
      }
    }
  }
LABEL_25:
  if ( v22 )
  {
    DAV_BASE_HANDLER::FinishRequest(v1, 0x190u, "Bad Request", 0, 0);
  }
  else if ( v3 == -2147024891 && (unsigned int)IsAnonymousUser(*(struct IHttpContext **)(a1 - 288)) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 288) + 32LL))(*(_QWORD *)(a1 - 288));
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15) + 536) = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 288) + 32LL))(*(_QWORD *)(a1 - 288));
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v16 + 24LL))(
      v16,
      401,
      "Unauthorized",
      0,
      -2147024891,
      0,
      0);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 288) + 200LL))(*(_QWORD *)(a1 - 288));
  }
  else
  {
    DAV_BASE_HANDLER::MapAndHandleError(v1, v3);
  }
  if ( v17 )
    RevertToSelf();
  return 2;
}

```

## disassembly

```asm
0x18000ed10  mov     [rsp-38h+arg_18], rbx
0x18000ed15  push    rbp
0x18000ed16  push    rsi
0x18000ed17  push    rdi
0x18000ed18  push    r12
0x18000ed1a  push    r13
0x18000ed1c  push    r14
0x18000ed1e  push    r15
0x18000ed20  mov     rbp, rsp
0x18000ed23  sub     rsp, 70h
0x18000ed27  xor     r14d, r14d
0x18000ed2a  lea     rdi, [rcx-128h]
0x18000ed31  mov     r13, rcx
0x18000ed34  mov     [rbp+arg_0], r14d
0x18000ed38  mov     [rbp+var_30], r14d
0x18000ed3c  mov     [rbp+var_28], r14
0x18000ed40  cmp     [rdi+170h], r14
0x18000ed47  jnz     short loc_18000ED55
0x18000ed49  mov     [rcx+1670h], r14d
0x18000ed50  jmp     loc_18000EDE4
0x18000ed55  xor     r8d, r8d; pMalloc
0x18000ed58  mov     [rbp+ppvObject], r14
0x18000ed5c  lea     rdx, [rbp+ppvObject]; ppvObject
0x18000ed60  lea     rcx, stru_180028158; riid
0x18000ed67  call    cs:__imp_CreateXmlReader
0x18000ed6d  mov     ebx, eax
0x18000ed6f  test    eax, eax
0x18000ed71  js      short loc_18000EDC7
0x18000ed73  mov     rcx, [rbp+ppvObject]
0x18000ed77  lea     rdx, [r13+40h]
0x18000ed7b  mov     rax, [rcx]
0x18000ed7e  mov     rax, [rax+18h]
0x18000ed82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed87  mov     ebx, eax
0x18000ed89  test    eax, eax
0x18000ed8b  js      short loc_18000EDC7
0x18000ed8d  mov     rax, [r13-110h]
0x18000ed94  lea     r9, [r13+1670h]; enum DAV_PROPFIND_TYPE *
0x18000ed9b  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x18000ed9f  lea     r8, [r13+100h]; struct DAV_NAMESPACE_SET *
0x18000eda6  mov     rcx, [r13-120h]; struct IHttpContext *
0x18000edad  mov     eax, [rax+8]
0x18000edb0  mov     dword ptr [rsp+70h+var_50], eax; unsigned int
0x18000edb4  call    ?ParsePropfind@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@PEAW4DAV_PROPFIND_TYPE@@K@Z; ParsePropfind(IHttpContext *,IXmlReader *,DAV_NAMESPACE_SET *,DAV_PROPFIND_TYPE *,ulong)
0x18000edb9  mov     esi, r14d
0x18000edbc  test    eax, eax
0x18000edbe  mov     ebx, eax
0x18000edc0  sets    sil
0x18000edc4  mov     [rbp+arg_0], esi
0x18000edc7  mov     rcx, [rbp+ppvObject]
0x18000edcb  test    rcx, rcx
0x18000edce  jz      short loc_18000EDDC
0x18000edd0  mov     rax, [rcx]
0x18000edd3  mov     rax, [rax+10h]
0x18000edd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eddc  test    ebx, ebx
0x18000edde  js      loc_18000EF3F
0x18000ede4  mov     rdx, [r13-120h]; struct IHttpContext *
0x18000edeb  lea     rcx, [rbp+var_30]; this
0x18000edef  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x18000edf4  mov     ebx, eax
0x18000edf6  test    eax, eax
0x18000edf8  js      loc_18000EF3F
0x18000edfe  mov     eax, [r13+1674h]
0x18000ee05  mov     rdx, [r13-110h]
0x18000ee0c  mov     [rbp+arg_8], eax
0x18000ee0f  test    eax, eax
0x18000ee11  jnz     short loc_18000EE40
0x18000ee13  lea     rcx, [rdx+40h]; this
0x18000ee17  mov     rdx, [r13-0E0h]; unsigned __int16 *
0x18000ee1e  call    ?FindLongestVDirPrefix@IIS_VDIR_CONFIG@@QEAAPEAVIIS_VDIR@@PEBG@Z; IIS_VDIR_CONFIG::FindLongestVDirPrefix(ushort const *)
0x18000ee23  mov     r9, [r13-70h]; unsigned __int16 *
0x18000ee27  mov     rdx, rax; struct IIS_VDIR *
0x18000ee2a  mov     r8, [r13-0E0h]; unsigned __int16 *
0x18000ee31  mov     rcx, rdi; this
0x18000ee34  call    ?DoOnePropfind@PROPFIND_VERB_HANDLER@@QEAAJPEAVIIS_VDIR@@PEBG1@Z; PROPFIND_VERB_HANDLER::DoOnePropfind(IIS_VDIR *,ushort const *,ushort const *)
0x18000ee39  mov     ebx, eax
0x18000ee3b  jmp     loc_18000EEF7
0x18000ee40  mov     r12, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000ee47  lea     rax, ??_7PROPFIND_URI_ENUMERATOR@@6B@; const PROPFIND_URI_ENUMERATOR::`vftable'
0x18000ee4e  mov     [rbp+var_20], rax
0x18000ee52  mov     [rbp+var_18], r14d
0x18000ee56  mov     [rbp+var_10], rdi
0x18000ee5a  mov     eax, [rdx+18h]
0x18000ee5d  neg     eax
0x18000ee5f  mov     rax, [r12]
0x18000ee63  sbb     ecx, ecx
0x18000ee65  and     ecx, 18h
0x18000ee68  mov     r15d, ecx
0x18000ee6b  mov     rax, [rax+18h]
0x18000ee6f  bts     r15d, 0Fh
0x18000ee74  cmp     [rdx+20h], r14d
0x18000ee78  cmovnz  r15d, ecx
0x18000ee7c  mov     rcx, r12
0x18000ee7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee84  mov     rcx, [r13-120h]; struct IHttpContext *
0x18000ee8b  mov     rbx, [r13-70h]
0x18000ee8f  mov     rdi, [r13-0E0h]
0x18000ee96  mov     r14, [r13-38h]
0x18000ee9a  mov     rsi, [r13-110h]
0x18000eea1  call    ?GetEffectiveToken@@YAPEAXPEAVIHttpContext@@@Z; GetEffectiveToken(IHttpContext *)
0x18000eea6  mov     rcx, rax; void *
0x18000eea9  lea     r9, [rbp+var_20]; struct IUriEnumerator *
0x18000eead  mov     eax, r15d
0x18000eeb0  lea     rdx, [rsi+40h]; struct IIS_VDIR_CONFIG *
0x18000eeb4  or      eax, 1
0x18000eeb7  mov     r8, r14; struct IBaseFileSystem *
0x18000eeba  cmp     [rbp+arg_8], 2
0x18000eebe  cmovnz  eax, r15d
0x18000eec2  mov     [rsp+70h+var_40], eax; unsigned int
0x18000eec6  mov     [rsp+70h+var_48], rbx; unsigned __int16 *
0x18000eecb  mov     [rsp+70h+var_50], rdi; unsigned __int16 *
0x18000eed0  call    ?EnumUri@@YAJPEAXPEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEAVIUriEnumerator@@PEBG4K@Z; EnumUri(void *,IIS_VDIR_CONFIG *,IBaseFileSystem *,IUriEnumerator *,ushort const *,ushort const *,ulong)
0x18000eed5  mov     ebx, eax
0x18000eed7  xor     r14d, r14d
0x18000eeda  test    eax, eax
0x18000eedc  mov     rcx, r12
0x18000eedf  mov     rax, [r12]
0x18000eee3  cmovns  ebx, [rbp+var_18]
0x18000eee7  mov     rax, [rax+20h]
0x18000eeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef0  lea     rdi, [r13-128h]
0x18000eef7  test    ebx, ebx
0x18000eef9  js      short loc_18000EF3F
0x18000eefb  cmp     [r13+0F8h], r14d
0x18000ef02  jz      short loc_18000EF16
0x18000ef04  lea     rcx, [r13+98h]; this
0x18000ef0b  call    ?FinishXmlMultistatusResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlMultistatusResponse(void)
0x18000ef10  mov     ebx, eax
0x18000ef12  test    eax, eax
0x18000ef14  js      short loc_18000EF3F
0x18000ef16  mov     rcx, [r13-120h]
0x18000ef1d  mov     rax, [rcx]
0x18000ef20  mov     rax, [rax+0C8h]
0x18000ef27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef2c  cmp     [rbp+var_30], r14d
0x18000ef30  jz      short loc_18000EF38
0x18000ef32  call    cs:__imp_RevertToSelf
0x18000ef38  xor     eax, eax
0x18000ef3a  jmp     loc_18000F023
0x18000ef3f  cmp     [rbp+arg_0], r14d
0x18000ef43  jz      short loc_18000EF66
0x18000ef45  xor     r9d, r9d; unsigned __int16
0x18000ef48  mov     dword ptr [rsp+70h+var_50], r14d; int
0x18000ef4d  mov     edx, 190h; unsigned __int16
0x18000ef52  lea     r8, aBadRequest; "Bad Request"
0x18000ef59  mov     rcx, rdi; this
0x18000ef5c  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000ef61  jmp     loc_18000F012
0x18000ef66  mov     esi, 80070005h
0x18000ef6b  cmp     ebx, esi
0x18000ef6d  jnz     loc_18000F008
0x18000ef73  mov     rcx, [r13-120h]; struct IHttpContext *
0x18000ef7a  call    ?IsAnonymousUser@@YAHPEAVIHttpContext@@@Z; IsAnonymousUser(IHttpContext *)
0x18000ef7f  test    eax, eax
0x18000ef81  jz      loc_18000F008
0x18000ef87  mov     rcx, [r13-120h]
0x18000ef8e  mov     rax, [rcx]
0x18000ef91  mov     rax, [rax+20h]
0x18000ef95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef9a  mov     rcx, rax
0x18000ef9d  mov     rax, [rax]
0x18000efa0  mov     rax, [rax+8]
0x18000efa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efa9  mov     [rax+218h], r14w
0x18000efb1  mov     rcx, [r13-120h]
0x18000efb8  mov     rax, [rcx]
0x18000efbb  mov     rax, [rax+20h]
0x18000efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc4  mov     rcx, rax
0x18000efc7  mov     [rsp+70h+var_40], r14d
0x18000efcc  xor     r9d, r9d
0x18000efcf  mov     [rsp+70h+var_48], r14
0x18000efd4  mov     edx, 191h
0x18000efd9  mov     dword ptr [rsp+70h+var_50], esi
0x18000efdd  mov     rax, [rax]
0x18000efe0  lea     r8, aUnauthorized; "Unauthorized"
0x18000efe7  mov     rax, [rax+18h]
0x18000efeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff0  mov     rcx, [r13-120h]
0x18000eff7  mov     rax, [rcx]
0x18000effa  mov     rax, [rax+0C8h]
0x18000f001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f006  jmp     short loc_18000F012
0x18000f008  mov     edx, ebx; int
0x18000f00a  mov     rcx, rdi; this
0x18000f00d  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000f012  cmp     [rbp+var_30], r14d
0x18000f016  jz      short loc_18000F01E
0x18000f018  call    cs:__imp_RevertToSelf
0x18000f01e  mov     eax, 2
0x18000f023  mov     rbx, [rsp+70h+arg_18]
0x18000f02b  add     rsp, 70h
0x18000f02f  pop     r15
0x18000f031  pop     r14
0x18000f033  pop     r13
0x18000f035  pop     r12
0x18000f037  pop     rdi
0x18000f038  pop     rsi
0x18000f039  pop     rbp
0x18000f03a  retn
```
