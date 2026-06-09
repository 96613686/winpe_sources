# PROPPATCH_VERB_HANDLER::OnReadEOF(void)

- ea: `0x18000f200`
- end: `0x18000f3e3`
- name: `?OnReadEOF@PROPPATCH_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ`
- size: `483`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x180005334`
- `0x18000f200`
- `0x1800134f0`
- `0x180015038`
- `0x180015204`
- `0x1800158a8`
- `0x18001b2cc`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f390`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f3c5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f390`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f3c5`
- `XmlLite!CreateXmlReader` at `0x18000f238`
- `XmlLite!CreateXmlReader` at `0x18000f238`

## pseudocode

```c
__int64 __fastcall PROPPATCH_VERB_HANDLER::OnReadEOF(__int64 a1)
{
  int v2; // esi
  int v3; // r14d
  HRESULT XmlReader; // ebx
  __int64 v5; // rcx
  int v6; // eax
  DAV_BASE_HANDLER *v7; // rcx
  int v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  struct IXmlReader *v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = 0;
  v2 = 0;
  v9 = 0;
  v10 = 0;
  v3 = 0;
  XmlReader = CreateXmlReader(&stru_1800281F0, (void **)&v11, 0);
  if ( XmlReader >= 0 )
  {
    XmlReader = ((__int64 (__fastcall *)(struct IXmlReader *, __int64))v11->lpVtbl->SetInput)(v11, a1 + 64);
    if ( XmlReader >= 0 )
    {
      XmlReader = ParseProppatch(
                    *(struct IHttpContext **)(a1 - 288),
                    v11,
                    (struct DAV_NAMESPACE_SET *)(a1 + 256),
                    *(_DWORD *)(*(_QWORD *)(a1 - 272) + 8LL));
      LOBYTE(v3) = XmlReader < 0;
    }
  }
  if ( v11 )
    ((void (__fastcall *)(struct IXmlReader *))v11->lpVtbl->Release)(v11);
  if ( XmlReader >= 0 )
  {
    XmlReader = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v9, *(struct IHttpContext **)(a1 - 288));
    if ( XmlReader >= 0 )
    {
      v5 = *(_QWORD *)(a1 - 264);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *(_QWORD *)(a1 - 264) = 0;
      }
      XmlReader = DAV_PROPERTY_STORE_MANAGER::SetProperties(
                    (DAV_PROPERTY_STORE_MANAGER *)(*(_QWORD *)(a1 - 272) + 2240LL),
                    (struct DAV_RESOURCE *)(a1 - 48),
                    (struct DAV_NAMESPACE_SET *)(a1 + 256));
      if ( XmlReader >= 0 )
      {
        v6 = XML_RESPONDER::BeginXmlCommon((XML_RESPONDER *)(a1 + 152), "multistatus", 0xCFu, "Multi Status", 0);
        if ( v6 >= 0 )
        {
          v6 = XML_RESPONDER::SendXmlProppatchResponse(
                 (XML_RESPONDER *)(a1 + 152),
                 *(const unsigned __int16 **)(a1 - 168),
                 *(const unsigned __int16 **)(a1 - 224),
                 (struct DAV_NAMESPACE_SET *)(a1 + 256),
                 XmlReader != 1);
          if ( v6 >= 0 )
            v6 = XML_RESPONDER::FinishXmlMultistatusResponse((XML_RESPONDER *)(a1 + 152));
        }
        XmlReader = v6;
      }
    }
    v2 = v9;
  }
  v7 = (DAV_BASE_HANDLER *)(a1 - 296);
  if ( XmlReader < 0 )
  {
    if ( v3 )
      DAV_BASE_HANDLER::FinishRequest(v7, 0x190u, "Bad Request", 0, 0);
    else
      DAV_BASE_HANDLER::MapAndHandleError(v7, XmlReader);
    if ( v2 )
      RevertToSelf();
    return 2;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v7 + 1) + 200LL))(*((_QWORD **)v7 + 1));
    if ( v2 )
      RevertToSelf();
    return 0;
  }
}

```

## disassembly

```asm
0x18000f200  mov     rax, rsp
0x18000f203  mov     [rax+8], rbx
0x18000f207  mov     [rax+18h], rbp
0x18000f20b  push    rsi
0x18000f20c  push    rdi
0x18000f20d  push    r14
0x18000f20f  sub     rsp, 40h
0x18000f213  mov     rdi, rcx
0x18000f216  mov     qword ptr [rax+10h], 0
0x18000f21e  xor     esi, esi
0x18000f220  lea     rcx, stru_1800281F0; riid
0x18000f227  xor     r8d, r8d; pMalloc
0x18000f22a  mov     [rax-28h], esi
0x18000f22d  lea     rdx, [rax+10h]; ppvObject
0x18000f231  mov     [rax-20h], rsi
0x18000f235  xor     r14d, r14d
0x18000f238  call    cs:__imp_CreateXmlReader
0x18000f23e  mov     ebx, eax
0x18000f240  test    eax, eax
0x18000f242  js      short loc_18000F28A
0x18000f244  mov     rcx, [rsp+58h+arg_8]
0x18000f249  lea     rdx, [rdi+40h]
0x18000f24d  mov     rax, [rcx]
0x18000f250  mov     rax, [rax+18h]
0x18000f254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f259  mov     ebx, eax
0x18000f25b  test    eax, eax
0x18000f25d  js      short loc_18000F28A
0x18000f25f  mov     r9, [rdi-110h]
0x18000f266  lea     r8, [rdi+100h]; struct DAV_NAMESPACE_SET *
0x18000f26d  mov     rdx, [rsp+58h+arg_8]; struct IXmlReader *
0x18000f272  mov     rcx, [rdi-120h]; struct IHttpContext *
0x18000f279  mov     r9d, [r9+8]; unsigned int
0x18000f27d  call    ?ParseProppatch@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@K@Z; ParseProppatch(IHttpContext *,IXmlReader *,DAV_NAMESPACE_SET *,ulong)
0x18000f282  test    eax, eax
0x18000f284  mov     ebx, eax
0x18000f286  sets    r14b
0x18000f28a  mov     rcx, [rsp+58h+arg_8]
0x18000f28f  test    rcx, rcx
0x18000f292  jz      short loc_18000F2A0
0x18000f294  mov     rax, [rcx]
0x18000f297  mov     rax, [rax+10h]
0x18000f29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2a0  test    ebx, ebx
0x18000f2a2  js      loc_18000F36E
0x18000f2a8  mov     rdx, [rdi-120h]; struct IHttpContext *
0x18000f2af  lea     rcx, [rsp+58h+var_28]; this
0x18000f2b4  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x18000f2b9  mov     ebx, eax
0x18000f2bb  test    eax, eax
0x18000f2bd  js      loc_18000F36A
0x18000f2c3  mov     rcx, [rdi-108h]
0x18000f2ca  test    rcx, rcx
0x18000f2cd  jz      short loc_18000F2E2
0x18000f2cf  mov     rax, [rcx]
0x18000f2d2  mov     rax, [rax+10h]
0x18000f2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2db  mov     [rdi-108h], rsi
0x18000f2e2  mov     rcx, [rdi-110h]
0x18000f2e9  lea     rbp, [rdi+100h]
0x18000f2f0  add     rcx, 8C0h; this
0x18000f2f7  lea     rdx, [rdi-30h]; struct DAV_RESOURCE *
0x18000f2fb  mov     r8, rbp; struct DAV_NAMESPACE_SET *
0x18000f2fe  call    ?SetProperties@DAV_PROPERTY_STORE_MANAGER@@QEAAJPEAVDAV_RESOURCE@@PEAVDAV_NAMESPACE_SET@@@Z; DAV_PROPERTY_STORE_MANAGER::SetProperties(DAV_RESOURCE *,DAV_NAMESPACE_SET *)
0x18000f303  mov     ebx, eax
0x18000f305  test    eax, eax
0x18000f307  js      short loc_18000F36A
0x18000f309  xor     eax, eax
0x18000f30b  lea     rsi, [rdi+98h]
0x18000f312  mov     rcx, rsi; this
0x18000f315  mov     [rsp+58h+var_38], ax; unsigned __int16
0x18000f31a  mov     r8d, 0CFh; unsigned __int16
0x18000f320  lea     r9, aMultiStatus_0; "Multi Status"
0x18000f327  lea     rdx, aMultistatus; "multistatus"
0x18000f32e  call    ?BeginXmlCommon@XML_RESPONDER@@AEAAJPEBDG0G@Z; XML_RESPONDER::BeginXmlCommon(char const *,ushort,char const *,ushort)
0x18000f333  test    eax, eax
0x18000f335  js      short loc_18000F368
0x18000f337  mov     r8, [rdi-0E0h]; unsigned __int16 *
0x18000f33e  xor     eax, eax
0x18000f340  mov     rdx, [rdi-0A8h]; unsigned __int16 *
0x18000f347  cmp     ebx, 1
0x18000f34a  mov     r9, rbp; struct DAV_NAMESPACE_SET *
0x18000f34d  mov     rcx, rsi; this
0x18000f350  setnz   al
0x18000f353  mov     dword ptr [rsp+58h+var_38], eax; int
0x18000f357  call    ?SendXmlProppatchResponse@XML_RESPONDER@@QEAAJPEBG0PEAVDAV_NAMESPACE_SET@@H@Z; XML_RESPONDER::SendXmlProppatchResponse(ushort const *,ushort const *,DAV_NAMESPACE_SET *,int)
0x18000f35c  test    eax, eax
0x18000f35e  js      short loc_18000F368
0x18000f360  mov     rcx, rsi; this
0x18000f363  call    ?FinishXmlMultistatusResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlMultistatusResponse(void)
0x18000f368  mov     ebx, eax
0x18000f36a  mov     esi, [rsp+58h+var_28]
0x18000f36e  lea     rcx, [rdi-128h]; this
0x18000f375  test    ebx, ebx
0x18000f377  js      short loc_18000F39A
0x18000f379  mov     rcx, [rcx+8]
0x18000f37d  mov     rax, [rcx]
0x18000f380  mov     rax, [rax+0C8h]
0x18000f387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f38c  test    esi, esi
0x18000f38e  jz      short loc_18000F396
0x18000f390  call    cs:__imp_RevertToSelf
0x18000f396  xor     eax, eax
0x18000f398  jmp     short loc_18000F3D0
0x18000f39a  test    r14d, r14d
0x18000f39d  jz      short loc_18000F3BA
0x18000f39f  xor     r9d, r9d; unsigned __int16
0x18000f3a2  lea     r8, aBadRequest; "Bad Request"
0x18000f3a9  mov     edx, 190h; unsigned __int16
0x18000f3ae  mov     dword ptr [rsp+58h+var_38], r9d; int
0x18000f3b3  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000f3b8  jmp     short loc_18000F3C1
0x18000f3ba  mov     edx, ebx; int
0x18000f3bc  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000f3c1  test    esi, esi
0x18000f3c3  jz      short loc_18000F3CB
0x18000f3c5  call    cs:__imp_RevertToSelf
0x18000f3cb  mov     eax, 2
0x18000f3d0  mov     rbx, [rsp+58h+arg_0]
0x18000f3d5  mov     rbp, [rsp+58h+arg_10]
0x18000f3da  add     rsp, 40h
0x18000f3de  pop     r14
0x18000f3e0  pop     rdi
0x18000f3e1  pop     rsi
0x18000f3e2  retn
```
