# IISGeneralEvents::GENERAL_STATIC_FILE_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x180002760`
- end: `0x180002841`
- name: `?RaiseEvent@GENERAL_STATIC_FILE_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002dd8`

## callees

- `0x180002760`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_STATIC_FILE_HANDLER::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD v7[6]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v8; // [rsp+50h] [rbp-29h]
  int v9; // [rsp+60h] [rbp-19h]
  int v10; // [rsp+64h] [rbp-15h]
  int v11; // [rsp+68h] [rbp-11h]
  _QWORD v12[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v13; // [rsp+80h] [rbp+7h] BYREF
  int v14; // [rsp+88h] [rbp+Fh]
  __int64 v15; // [rsp+90h] [rbp+17h]
  int v16; // [rsp+98h] [rbp+1Fh]
  __int64 v17; // [rsp+A0h] [rbp+27h]
  const wchar_t *v18; // [rsp+A8h] [rbp+2Fh]
  int v19; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v20; // [rsp+B8h] [rbp+3Fh]
  int v21; // [rsp+C0h] [rbp+47h]
  __int64 v22; // [rsp+C8h] [rbp+4Fh]

  v7[3] = 10;
  v7[1] = 0;
  memset(v12, 0, 12);
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v7[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v7[4] = L"GENERAL_STATIC_FILE_HANDLER";
  v7[5] = 1;
  v10 = 1;
  v13 = L"ContextId";
  v18 = L"FileName";
  v11 = 2;
  v8 = 0;
  v9 = 0;
  v14 = 72;
  v15 = 0;
  v16 = 16;
  v17 = 0;
  v19 = 31;
  v20 = a3;
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
  v21 = v3;
  *(_QWORD *)((char *)v12 + 4) = &v13;
  v5 = *(_QWORD *)a1;
  v22 = 0;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v5 + 16))(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x180002760  push    rbp
0x180002762  lea     rbp, [rsp-57h]
0x180002767  sub     rsp, 0D0h
0x18000276e  xor     eax, eax
0x180002770  mov     [rbp+57h+var_98], 0Ah
0x180002778  mov     [rbp+57h+var_A8], rax
0x18000277c  xor     edx, edx
0x18000277e  mov     [rbp+57h+var_64], rax
0x180002782  xorps   xmm0, xmm0
0x180002785  mov     [rbp+57h+var_5C], eax
0x180002788  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000278f  mov     [rbp+57h+var_B0], rax
0x180002793  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000279a  mov     [rbp+57h+var_A0], rax
0x18000279e  lea     rax, aGeneralStaticF; "GENERAL_STATIC_FILE_HANDLER"
0x1800027a5  mov     [rbp+57h+var_90], rax
0x1800027a9  lea     eax, [rdx+1]
0x1800027ac  mov     [rbp+57h+var_88], rax
0x1800027b0  mov     [rbp+57h+var_6C], eax
0x1800027b3  lea     rax, aContextid; "ContextId"
0x1800027ba  mov     [rbp+57h+var_50], rax
0x1800027be  lea     rax, aFilename; "FileName"
0x1800027c5  mov     [rbp+57h+var_28], rax
0x1800027c9  mov     [rbp+57h+var_68], 2
0x1800027d0  movdqa  [rbp+57h+var_80], xmm0
0x1800027d5  mov     [rbp+57h+var_70], edx
0x1800027d8  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800027df  mov     [rbp+57h+var_40], rdx
0x1800027e3  mov     [rbp+57h+var_38], 10h
0x1800027ea  mov     [rbp+57h+var_30], rdx
0x1800027ee  mov     [rbp+57h+var_20], 1Fh
0x1800027f5  mov     [rbp+57h+var_18], r8
0x1800027f9  test    r8, r8
0x1800027fc  jnz     short loc_180002802
0x1800027fe  mov     eax, edx
0x180002800  jmp     short loc_180002817
0x180002802  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002806  inc     rax
0x180002809  cmp     [r8+rax*2], dx
0x18000280e  jnz     short loc_180002806
0x180002810  lea     eax, ds:2[rax*2]
0x180002817  mov     [rbp+57h+var_10], eax
0x18000281a  lea     rax, [rbp+57h+var_50]
0x18000281e  mov     [rbp+57h+var_64+4], rax
0x180002822  mov     rax, [rcx]
0x180002825  mov     [rbp+57h+var_8], rdx
0x180002829  lea     rdx, [rbp+57h+var_B0]
0x18000282d  mov     rax, [rax+10h]
0x180002831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002836  xor     eax, eax
0x180002838  add     rsp, 0D0h
0x18000283f  pop     rbp
0x180002840  retn
```
