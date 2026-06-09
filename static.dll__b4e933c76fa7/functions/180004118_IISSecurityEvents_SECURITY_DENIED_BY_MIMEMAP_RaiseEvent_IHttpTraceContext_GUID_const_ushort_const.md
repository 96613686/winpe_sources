# IISSecurityEvents::SECURITY_DENIED_BY_MIMEMAP::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x180004118`
- end: `0x180004205`
- name: `?RaiseEvent@SECURITY_DENIED_BY_MIMEMAP@IISSecurityEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dd8`

## callees

- `0x180004118`
- `0x180007010`

## string_xrefs

- `0x18000414f`: `SECURITY_DENIED_BY_MIMEMAP`

## pseudocode

```c
__int64 __fastcall IISSecurityEvents::SECURITY_DENIED_BY_MIMEMAP::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-59h] BYREF
  int v8; // [rsp+48h] [rbp-31h]
  int v9; // [rsp+4Ch] [rbp-2Dh]
  __int128 v10; // [rsp+50h] [rbp-29h]
  int v11; // [rsp+60h] [rbp-19h]
  int v12; // [rsp+64h] [rbp-15h]
  int v13; // [rsp+68h] [rbp-11h]
  _QWORD v14[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v15; // [rsp+80h] [rbp+7h] BYREF
  int v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]
  int v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+A0h] [rbp+27h]
  const wchar_t *v20; // [rsp+A8h] [rbp+2Fh]
  int v21; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v22; // [rsp+B8h] [rbp+3Fh]
  int v23; // [rsp+C0h] [rbp+47h]
  __int64 v24; // [rsp+C8h] [rbp+4Fh]

  v7[1] = 4;
  memset(v14, 0, 12);
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v7[2] = &`IISSecurityEvents::GetAreaGuid'::`2'::AreaGuid;
  v7[4] = L"SECURITY_DENIED_BY_MIMEMAP";
  v8 = 1;
  v12 = 1;
  v15 = L"ContextId";
  v20 = L"FileName";
  v7[3] = 15;
  v9 = 3;
  v13 = 2;
  v10 = 0;
  v11 = 0;
  v16 = 72;
  v17 = 0;
  v18 = 16;
  v19 = 0;
  v21 = 31;
  v22 = a3;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v3 = 2 * v4 + 2;
  }
  else
  {
    v3 = 0;
  }
  v23 = v3;
  *(_QWORD *)((char *)v14 + 4) = &v15;
  v5 = *(_QWORD *)a1;
  v24 = 0;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v5 + 16))(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x180004118  push    rbp
0x18000411a  lea     rbp, [rsp-57h]
0x18000411f  sub     rsp, 0D0h
0x180004126  xor     eax, eax
0x180004128  mov     [rbp+57h+var_A8], 4
0x180004130  mov     [rbp+57h+var_64], rax
0x180004134  xor     edx, edx
0x180004136  mov     [rbp+57h+var_5C], eax
0x180004139  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004140  mov     [rbp+57h+var_B0], rax
0x180004144  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISSecurityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISSecurityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000414b  mov     [rbp+57h+var_A0], rax
0x18000414f  lea     rax, aSecurityDenied; "SECURITY_DENIED_BY_MIMEMAP"
0x180004156  mov     [rbp+57h+var_90], rax
0x18000415a  mov     eax, 1
0x18000415f  mov     [rbp+57h+var_88], eax
0x180004162  xorps   xmm0, xmm0
0x180004165  mov     [rbp+57h+var_6C], eax
0x180004168  lea     rax, aContextid; "ContextId"
0x18000416f  mov     [rbp+57h+var_50], rax
0x180004173  lea     rax, aFilename; "FileName"
0x18000417a  mov     [rbp+57h+var_28], rax
0x18000417e  mov     [rbp+57h+var_98], 0Fh
0x180004186  mov     [rbp+57h+var_84], 3
0x18000418d  mov     [rbp+57h+var_68], 2
0x180004194  movdqa  [rbp+57h+var_80], xmm0
0x180004199  mov     [rbp+57h+var_70], edx
0x18000419c  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800041a3  mov     [rbp+57h+var_40], rdx
0x1800041a7  mov     [rbp+57h+var_38], 10h
0x1800041ae  mov     [rbp+57h+var_30], rdx
0x1800041b2  mov     [rbp+57h+var_20], 1Fh
0x1800041b9  mov     [rbp+57h+var_18], r8
0x1800041bd  test    r8, r8
0x1800041c0  jnz     short loc_1800041C6
0x1800041c2  mov     eax, edx
0x1800041c4  jmp     short loc_1800041DB
0x1800041c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800041ca  inc     rax
0x1800041cd  cmp     [r8+rax*2], dx
0x1800041d2  jnz     short loc_1800041CA
0x1800041d4  lea     eax, ds:2[rax*2]
0x1800041db  mov     [rbp+57h+var_10], eax
0x1800041de  lea     rax, [rbp+57h+var_50]
0x1800041e2  mov     [rbp+57h+var_64+4], rax
0x1800041e6  mov     rax, [rcx]
0x1800041e9  mov     [rbp+57h+var_8], rdx
0x1800041ed  lea     rdx, [rbp+57h+var_B0]
0x1800041f1  mov     rax, [rax+10h]
0x1800041f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041fa  xor     eax, eax
0x1800041fc  add     rsp, 0D0h
0x180004203  pop     rbp
0x180004204  retn
```
