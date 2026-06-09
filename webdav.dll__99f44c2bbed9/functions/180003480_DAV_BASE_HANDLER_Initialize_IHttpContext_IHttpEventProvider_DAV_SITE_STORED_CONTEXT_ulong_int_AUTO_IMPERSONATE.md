# DAV_BASE_HANDLER::Initialize(IHttpContext *,IHttpEventProvider *,DAV_SITE_STORED_CONTEXT *,ulong,int,AUTO_IMPERSONATE *)

- ea: `0x180003480`
- end: `0x18000362d`
- name: `?Initialize@DAV_BASE_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVDAV_SITE_STORED_CONTEXT@@KHPEAVAUTO_IMPERSONATE@@@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1800092e0`

## callees

- `0x1800033d4`
- `0x180003480`
- `0x180003634`
- `0x180003c4c`
- `0x18000d718`
- `0x18000da04`
- `0x18001a314`
- `0x180023010`

## import_xrefs

- `KERNELBASE!WTSGetServiceSessionId` at `0x1800035c8`
- `KERNELBASE!WTSGetServiceSessionId` at `0x1800035c8`

## pseudocode

```c
__int64 __fastcall DAV_BASE_HANDLER::Initialize(
        __int64 a1,
        struct IHttpContext *a2,
        void (__fastcall ***a3)(_QWORD, _QWORD),
        __int64 a4,
        unsigned int a5,
        int a6,
        struct AUTO_IMPERSONATE *a7)
{
  int ParsedMetadata; // ebx
  struct IHttpEventProvider *v11; // r9
  int v12; // eax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rax

  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 24) = a4;
  ParsedMetadata = DAV_META_STORED_CONTEXT::GetParsedMetadata(a2, (struct DAV_META_STORED_CONTEXT **)(a1 + 16), 1, 1);
  if ( ParsedMetadata < 0 )
    goto LABEL_7;
  ParsedMetadata = DAV_META_STORED_CONTEXT::TestDavPreconditions(*(DAV_META_STORED_CONTEXT **)(a1 + 16), a5, a2, v11);
  if ( ParsedMetadata < 0 )
    goto LABEL_7;
  v12 = DAV_PATH_INFO::Initialize((DAV_PATH_INFO *)(a1 + 32), a2, a6, a7);
  ParsedMetadata = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -2147024891 && (unsigned int)IsAnonymousUser(a2) )
    {
      DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0x191u, "Unauthorized", 0, ParsedMetadata);
LABEL_7:
      (**a3)(a3, (unsigned int)ParsedMetadata);
      (**(void (__fastcall ***)(__int64))a1)(a1);
      return 2;
    }
LABEL_13:
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, ParsedMetadata);
    goto LABEL_7;
  }
  v14 = *(_QWORD *)(a1 + 8);
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14);
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v17 = *(_QWORD *)(a1 + 184);
  v18 = *(_QWORD *)(a1 + 128);
  *(_QWORD *)(a1 + 256) = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(a1 + 264) = v18;
  *(_QWORD *)(a1 + 272) = v17;
  *(_QWORD *)(a1 + 280) = v16;
  *(_QWORD *)(a1 + 288) = v14;
  v19 = *(_QWORD *)(a1 + 24);
  if ( !*(_DWORD *)(v19 + 28)
    || *(_DWORD *)(v19 + 2228)
    || (v20 = (unsigned int)WTSGetServiceSessionId() == 0, v21 = 224, !v20) )
  {
    v21 = 216;
  }
  *(_QWORD *)(a1 + 240) = a1 + v21;
  v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  ParsedMetadata = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v22 + 8LL))(
                     v22,
                     a1,
                     g_DavModuleContext);
  if ( ParsedMetadata < 0 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x180003480  push    rbx
0x180003482  push    rsi
0x180003483  push    rdi
0x180003484  push    r14
0x180003486  push    r15
0x180003488  sub     rsp, 30h
0x18000348c  mov     rsi, rdx
0x18000348f  mov     [rcx+8], rdx
0x180003493  mov     [rcx+18h], r9
0x180003497  lea     rdx, [rcx+10h]; struct DAV_META_STORED_CONTEXT **
0x18000349b  mov     r15, r8
0x18000349e  mov     rdi, rcx
0x1800034a1  mov     r8d, 1; int
0x1800034a7  mov     rcx, rsi; struct IHttpContext *
0x1800034aa  mov     r9d, r8d; int
0x1800034ad  call    ?GetParsedMetadata@DAV_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@HH@Z; DAV_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,DAV_META_STORED_CONTEXT * *,int,int)
0x1800034b2  mov     ebx, eax
0x1800034b4  test    eax, eax
0x1800034b6  js      short loc_180003529
0x1800034b8  mov     edx, [rsp+58h+arg_20]; unsigned int
0x1800034bf  mov     r8, rsi; struct IHttpContext *
0x1800034c2  mov     rcx, [rdi+10h]; this
0x1800034c6  call    ?TestDavPreconditions@DAV_META_STORED_CONTEXT@@QEAAJKPEAVIHttpContext@@PEAVIHttpEventProvider@@@Z; DAV_META_STORED_CONTEXT::TestDavPreconditions(ulong,IHttpContext *,IHttpEventProvider *)
0x1800034cb  mov     ebx, eax
0x1800034cd  test    eax, eax
0x1800034cf  js      short loc_180003529
0x1800034d1  mov     r9, [rsp+58h+arg_30]; struct AUTO_IMPERSONATE *
0x1800034d9  lea     rcx, [rdi+20h]; this
0x1800034dd  mov     r8d, [rsp+58h+arg_28]; int
0x1800034e5  mov     rdx, rsi; struct IHttpContext *
0x1800034e8  call    ?Initialize@DAV_PATH_INFO@@QEAAJPEAVIHttpContext@@HPEAVAUTO_IMPERSONATE@@@Z; DAV_PATH_INFO::Initialize(IHttpContext *,int,AUTO_IMPERSONATE *)
0x1800034ed  mov     ebx, eax
0x1800034ef  test    eax, eax
0x1800034f1  jns     short loc_180003558
0x1800034f3  cmp     eax, 80070005h
0x1800034f8  jnz     loc_180003617
0x1800034fe  mov     rcx, rsi; struct IHttpContext *
0x180003501  call    ?IsAnonymousUser@@YAHPEAVIHttpContext@@@Z; IsAnonymousUser(IHttpContext *)
0x180003506  test    eax, eax
0x180003508  jz      loc_180003617
0x18000350e  xor     r9d, r9d; unsigned __int16
0x180003511  mov     [rsp+58h+var_38], ebx; int
0x180003515  mov     edx, 191h; unsigned __int16
0x18000351a  lea     r8, aUnauthorized; "Unauthorized"
0x180003521  mov     rcx, rdi; this
0x180003524  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x180003529  mov     rax, [r15]
0x18000352c  mov     edx, ebx
0x18000352e  mov     rcx, r15
0x180003531  mov     rax, [rax]
0x180003534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003539  mov     rax, [rdi]
0x18000353c  mov     rcx, rdi
0x18000353f  mov     rax, [rax]
0x180003542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003547  mov     eax, 2
0x18000354c  add     rsp, 30h
0x180003550  pop     r15
0x180003552  pop     r14
0x180003554  pop     rdi
0x180003555  pop     rsi
0x180003556  pop     rbx
0x180003557  retn
0x180003558  mov     rbx, [rdi+8]
0x18000355c  mov     rcx, rbx
0x18000355f  mov     rax, [rbx]
0x180003562  mov     rax, [rax+0A0h]
0x180003569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356e  mov     rdx, rax
0x180003571  mov     rcx, [rax]
0x180003574  mov     rax, [rcx+10h]
0x180003578  mov     rcx, rdx
0x18000357b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003580  mov     r8, [rdi+0B8h]
0x180003587  mov     rdx, [rdi+80h]
0x18000358e  mov     rcx, [rdi+48h]
0x180003592  mov     [rdi+100h], rcx
0x180003599  mov     [rdi+108h], rdx
0x1800035a0  mov     [rdi+110h], r8
0x1800035a7  mov     [rdi+118h], rax
0x1800035ae  mov     [rdi+120h], rbx
0x1800035b5  mov     rax, [rdi+18h]
0x1800035b9  cmp     dword ptr [rax+1Ch], 0
0x1800035bd  jz      short loc_1800035D7
0x1800035bf  cmp     dword ptr [rax+8B4h], 0
0x1800035c6  jnz     short loc_1800035D7
0x1800035c8  call    cs:__imp_WTSGetServiceSessionId
0x1800035ce  test    eax, eax
0x1800035d0  mov     eax, 0E0h
0x1800035d5  jz      short loc_1800035DC
0x1800035d7  mov     eax, 0D8h
0x1800035dc  add     rax, rdi
0x1800035df  mov     rcx, rsi
0x1800035e2  mov     [rdi+0F0h], rax
0x1800035e9  mov     rax, [rsi]
0x1800035ec  mov     rax, [rax+38h]
0x1800035f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f5  mov     r8, cs:?g_DavModuleContext@@3PEAXEA; void * g_DavModuleContext
0x1800035fc  mov     r9, rax
0x1800035ff  mov     rdx, rdi
0x180003602  mov     rcx, [rax]
0x180003605  mov     rax, [rcx+8]
0x180003609  mov     rcx, r9
0x18000360c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003611  mov     ebx, eax
0x180003613  test    eax, eax
0x180003615  jns     short loc_180003626
0x180003617  mov     edx, ebx; int
0x180003619  mov     rcx, rdi; this
0x18000361c  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x180003621  jmp     loc_180003529
0x180003626  xor     eax, eax
0x180003628  jmp     loc_18000354C
```
