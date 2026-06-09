# DAV_HTTP_MODULE::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009480`
- end: `0x180009cee`
- name: `?OnExecuteRequestHandler@DAV_HTTP_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `2158`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(struct IHttpContext *, struct IHttpEventProvider *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007cc0`
- `0x180008694`
- `0x180008754`
- `0x1800088d4`
- `0x180009480`
- `0x18000a21c`
- `0x180010098`
- `0x1800106b0`
- `0x18001a250`
- `0x18001a468`
- `0x18001b2cc`
- `0x180020614`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009c6e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009c6e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000974e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000981f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800098c9`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000996b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800099f6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180009a60`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000974e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000981f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800098c9`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000996b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800099f6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180009a60`

## string_xrefs

- `0x180009bca`: `Impersonation Failure`
- `0x1800095bd`: `Invalid Request URI`

## pseudocode

```c
__int64 __fastcall DAV_HTTP_MODULE::OnExecuteRequestHandler(
        __int64 a1,
        struct IHttpContext *a2,
        struct IHttpEventProvider *a3)
{
  int v5; // edi
  int ParsedMetadata; // eax
  DAV_HTTP_MODULE *v7; // rcx
  __int64 v8; // rdx
  DAV_SITE_STORED_CONTEXT *v10; // r13
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  DAV_BASE_HANDLER *v33; // rax
  DAV_BASE_HANDLER *v34; // rbx
  int v35; // r15d
  XML_ASYNC_HANDLER *v36; // rax
  DAV_BASE_HANDLER *v37; // rax
  XML_ASYNC_HANDLER *v38; // rax
  XML_ASYNC_HANDLER *v39; // rax
  DAV_BASE_HANDLER *v40; // rax
  void **v41; // rax
  DAV_BASE_HANDLER *v42; // rax
  DAV_BASE_HANDLER *v43; // rax
  DAV_BASE_HANDLER *v44; // rax
  __int64 v45; // rax
  unsigned int v46; // ebx
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // [rsp+40h] [rbp-18h] BYREF
  __int64 v50; // [rsp+48h] [rbp-10h]
  DAV_SITE_STORED_CONTEXT *v51; // [rsp+B8h] [rbp+60h] BYREF

  v51 = 0;
  v5 = 1;
  ParsedMetadata = DAV_SITE_STORED_CONTEXT::GetParsedMetadata(a2, &v51, 1, 1);
  v8 = (unsigned int)ParsedMetadata;
  if ( ParsedMetadata < 0 )
    goto LABEL_2;
  v10 = v51;
  if ( !*((_DWORD *)v51 + 4) )
  {
    v11 = (*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 272LL))(
            a2,
            (unsigned int)ParsedMetadata);
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v11 + 32LL))(
      v11,
      L"WebDAV Disabled",
      0,
      0,
      3);
    HandleMethodNotAllowed(a2);
    return 2;
  }
  v12 = DAV_HTTP_MODULE::SetupLogData(v7, a2);
  v8 = (unsigned int)v12;
  if ( v12 < 0 )
  {
LABEL_2:
    (**(void (__fastcall ***)(struct IHttpEventProvider *, __int64))a3)(a3, v8);
    return 2;
  }
  v13 = 2;
  if ( DAV_SITE_STORED_CONTEXT::TestDavPreconditions(v10, a2, a3) < 0 )
    return v13;
  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v16 = *(_QWORD *)(v15 + 96);
  v17 = *(_QWORD *)(v15 + 88);
  if ( v16 )
  {
    v18 = (v16 - v17) >> 1;
  }
  else
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v17 + 2 * v18) );
  }
  if ( !(unsigned int)IsValidUri(*(const unsigned __int16 **)(v15 + 88), v18) )
  {
    v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v19 + 272))(a2);
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v20 + 32LL))(
      v20,
      L"Invalid Request URI",
      0,
      0,
      3);
    v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21) + 536) = 0;
    v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v22 + 24LL))(
      v22,
      400,
      "Bad Request",
      0,
      0,
      0,
      0);
    (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 200LL))(a2);
    return v13;
  }
  v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v19 + 24))(a2);
  v24 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23) + 36);
  if ( (unsigned int)(v24 - 4) <= 1 )
    return (unsigned int)GET_VERB_HANDLER::ExecuteRequest(a2, a3);
  v25 = v24 - 7;
  if ( !v25 )
  {
    v44 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                a2,
                                424);
    v34 = v44;
    if ( v44 )
    {
      DAV_BASE_HANDLER::DAV_BASE_HANDLER(v44);
      *((_QWORD *)v34 + 38) = 0;
      *((_DWORD *)v34 + 84) = -1;
      *((_DWORD *)v34 + 85) = -1;
      *(_QWORD *)v34 = &PUT_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'};
      *((_QWORD *)v34 + 37) = &PUT_VERB_HANDLER::`vftable'{for `IAsyncEventSink'};
      *((_QWORD *)v34 + 45) = &ASYNC_FILE_BUFFER_FACTORY::`vftable';
      *((_QWORD *)v34 + 39) = 0;
      *((_QWORD *)v34 + 40) = 0;
      *((_QWORD *)v34 + 41) = 0;
      *((_QWORD *)v34 + 43) = 0;
      *((_DWORD *)v34 + 88) = 0;
      *((_DWORD *)v34 + 94) = 1024;
      *((_QWORD *)v34 + 46) = v34;
      *((_QWORD *)v34 + 48) = -1;
      *((_QWORD *)v34 + 49) = 0;
      *((_DWORD *)v34 + 100) = 0;
      *((_QWORD *)v34 + 51) = 0;
      *((_QWORD *)v34 + 52) = 0;
      goto LABEL_52;
    }
LABEL_51:
    v34 = 0;
    goto LABEL_52;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    v43 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                a2,
                                400);
    v34 = v43;
    if ( v43 )
    {
      DAV_BASE_HANDLER::DAV_BASE_HANDLER(v43);
      *(_QWORD *)v34 = &DELETE_VERB_HANDLER::`vftable';
      STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 320));
      *((_DWORD *)v34 + 74) = 1;
      *((_QWORD *)v34 + 38) = &word_1800263B2;
      *((_QWORD *)v34 + 39) = ">";
      *((_DWORD *)v34 + 94) = 65537;
      *((_QWORD *)v34 + 48) = 0;
      *((_DWORD *)v34 + 98) = 0;
      goto LABEL_37;
    }
    goto LABEL_36;
  }
  v27 = v26 - 4;
  if ( !v27 )
  {
    v42 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                a2,
                                416);
    v34 = v42;
    if ( !v42 )
      goto LABEL_40;
    DAV_BASE_HANDLER::DAV_BASE_HANDLER(v42);
    *(_QWORD *)v34 = &COPY_MOVE_BASE_HANDLER::`vftable';
    STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 320));
    *((_QWORD *)v34 + 38) = &word_1800263B2;
    *((_QWORD *)v34 + 39) = ">";
    v41 = &MOVE_VERB_HANDLER::`vftable';
    goto LABEL_44;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
    v40 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                a2,
                                416);
    v34 = v40;
    if ( !v40 )
      goto LABEL_40;
    DAV_BASE_HANDLER::DAV_BASE_HANDLER(v40);
    *(_QWORD *)v34 = &COPY_MOVE_BASE_HANDLER::`vftable';
    STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 320));
    *((_QWORD *)v34 + 38) = &word_1800263B2;
    *((_QWORD *)v34 + 39) = ">";
    v41 = &COPY_VERB_HANDLER::`vftable';
LABEL_44:
    *((_DWORD *)v34 + 74) = 1;
    *((_DWORD *)v34 + 94) = 65537;
    *((_DWORD *)v34 + 98) = 0;
    *((_QWORD *)v34 + 48) = 0;
    *(_QWORD *)v34 = v41;
    goto LABEL_41;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    v39 = (XML_ASYNC_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                 a2,
                                 6048);
    v34 = v39;
    if ( v39 )
    {
      XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(v39);
      *(_QWORD *)v34 = &PROPFIND_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'};
      *((_QWORD *)v34 + 37) = &PROPFIND_VERB_HANDLER::`vftable'{for `IAsyncEventSink'};
      STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 472));
      *((_DWORD *)v34 + 112) = 1;
      *((_QWORD *)v34 + 57) = &word_1800263B2;
      *((_DWORD *)v34 + 132) = 65537;
      *((_QWORD *)v34 + 58) = ">";
      *((_QWORD *)v34 + 67) = 0;
      *((_DWORD *)v34 + 136) = 0;
      DAV_NAMESPACE_SET::DAV_NAMESPACE_SET((DAV_BASE_HANDLER *)((char *)v34 + 552), L"n");
      *((_DWORD *)v34 + 1510) = -1;
LABEL_41:
      v35 = 1;
      goto LABEL_54;
    }
LABEL_40:
    v34 = 0;
    goto LABEL_41;
  }
  v30 = v29 - 1;
  if ( v30 )
  {
    v31 = v30 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        if ( v32 != 1 )
        {
          HandleMethodNotAllowed(a2);
          return v13;
        }
        v33 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                    a2,
                                    296);
        v34 = v33;
        if ( v33 )
        {
          DAV_BASE_HANDLER::DAV_BASE_HANDLER(v33);
          *(_QWORD *)v34 = &UNLOCK_VERB_HANDLER::`vftable';
LABEL_29:
          v35 = 1;
LABEL_53:
          v5 = 0;
          goto LABEL_54;
        }
      }
      else
      {
        v36 = (XML_ASYNC_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                     a2,
                                     5584);
        v34 = v36;
        if ( v36 )
        {
          XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(v36);
          *(_QWORD *)v34 = &LOCK_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'};
          *((_QWORD *)v34 + 37) = &LOCK_VERB_HANDLER::`vftable'{for `IAsyncEventSink'};
          STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 472));
          *((_DWORD *)v34 + 112) = 1;
          *((_QWORD *)v34 + 57) = &word_1800263B2;
          *((_DWORD *)v34 + 132) = 65537;
          *((_QWORD *)v34 + 58) = ">";
          *((_QWORD *)v34 + 67) = 0;
          *((_DWORD *)v34 + 136) = 0;
          LOCK_SET::LOCK_SET((DAV_BASE_HANDLER *)((char *)v34 + 568));
          goto LABEL_29;
        }
      }
      v34 = 0;
      goto LABEL_29;
    }
    v37 = (DAV_BASE_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                                a2,
                                296);
    v34 = v37;
    if ( v37 )
    {
      DAV_BASE_HANDLER::DAV_BASE_HANDLER(v37);
      *(_QWORD *)v34 = &MKCOL_VERB_HANDLER::`vftable';
LABEL_52:
      v35 = 2;
      goto LABEL_53;
    }
    goto LABEL_51;
  }
  v38 = (XML_ASYNC_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a2 + 144LL))(
                               a2,
                               6040);
  v34 = v38;
  if ( !v38 )
  {
LABEL_36:
    v34 = 0;
    goto LABEL_37;
  }
  XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(v38);
  *(_QWORD *)v34 = &PROPPATCH_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'};
  *((_QWORD *)v34 + 37) = &PROPPATCH_VERB_HANDLER::`vftable'{for `IAsyncEventSink'};
  STRA::STRA((DAV_BASE_HANDLER *)((char *)v34 + 472));
  *((_DWORD *)v34 + 112) = 1;
  *((_QWORD *)v34 + 57) = &word_1800263B2;
  *((_DWORD *)v34 + 132) = 65537;
  *((_QWORD *)v34 + 58) = ">";
  *((_QWORD *)v34 + 67) = 0;
  *((_DWORD *)v34 + 136) = 0;
  DAV_NAMESPACE_SET::DAV_NAMESPACE_SET((DAV_BASE_HANDLER *)((char *)v34 + 552), L"n");
LABEL_37:
  v35 = 2;
LABEL_54:
  if ( v34 )
  {
    v49 = 0;
    v50 = 0;
    LODWORD(v51) = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v49, a2);
    if ( (int)v51 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(DAV_BASE_HANDLER *, struct IHttpContext *, struct IHttpEventProvider *, DAV_SITE_STORED_CONTEXT *, int, int, int *))(*(_QWORD *)v34 + 16LL))(
              v34,
              a2,
              a3,
              v10,
              v35,
              v5,
              &v49);
      if ( !v13 )
        v13 = (*(__int64 (__fastcall **)(DAV_BASE_HANDLER *, int *))(*(_QWORD *)v34 + 24LL))(v34, &v49);
      if ( !v49 )
        return v13;
      v49 = 0;
    }
    else
    {
      v45 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v46 = (unsigned int)v51;
      (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v45 + 32LL))(
        v45,
        L"Impersonation Failure",
        0,
        (unsigned int)v51,
        3);
      v47 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47) + 536) = 0;
      v48 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD))(*(_QWORD *)v48 + 24LL))(
        v48,
        500,
        "Internal Server Error",
        0,
        v46,
        0,
        0);
      (**(void (__fastcall ***)(struct IHttpEventProvider *, _QWORD))a3)(a3, v46);
      if ( !v49 )
        return v13;
      v49 = 0;
    }
    RevertToSelf();
    return v13;
  }
  (**(void (__fastcall ***)(struct IHttpEventProvider *, __int64))a3)(a3, 2147942408LL);
  return v13;
}

```

## disassembly

```asm
0x180009480  push    rbp
0x180009482  push    rbx
0x180009483  push    rsi
0x180009484  push    rdi
0x180009485  push    r12
0x180009487  push    r13
0x180009489  push    r14
0x18000948b  push    r15
0x18000948d  mov     rbp, rsp
0x180009490  sub     rsp, 58h
0x180009494  mov     rsi, rdx
0x180009497  xor     r15d, r15d
0x18000949a  mov     r12, r8
0x18000949d  mov     [rbp+arg_18], r15
0x1800094a1  lea     rdx, [rbp+arg_18]; struct DAV_SITE_STORED_CONTEXT **
0x1800094a5  mov     rcx, rsi; struct IHttpContext *
0x1800094a8  lea     edi, [r15+1]
0x1800094ac  mov     r9d, edi; int
0x1800094af  mov     r8d, edi; int
0x1800094b2  call    ?GetParsedMetadata@DAV_SITE_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@HH@Z; DAV_SITE_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,DAV_SITE_STORED_CONTEXT * *,int,int)
0x1800094b7  mov     edx, eax
0x1800094b9  test    eax, eax
0x1800094bb  jns     short loc_1800094D6
0x1800094bd  mov     rcx, [r12]
0x1800094c1  mov     rax, [rcx]
0x1800094c4  mov     rcx, r12
0x1800094c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094cc  mov     eax, 2
0x1800094d1  jmp     loc_180009CDD
0x1800094d6  mov     r13, [rbp+arg_18]
0x1800094da  cmp     [r13+10h], r15d
0x1800094de  jnz     short loc_180009520
0x1800094e0  mov     rax, [rsi]
0x1800094e3  mov     rcx, rsi
0x1800094e6  mov     rax, [rax+110h]
0x1800094ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f2  mov     r10, rax
0x1800094f5  mov     byte ptr [rsp+58h+var_38], 3
0x1800094fa  xor     r9d, r9d
0x1800094fd  lea     rdx, aWebdavDisabled; "WebDAV Disabled"
0x180009504  xor     r8d, r8d
0x180009507  mov     rcx, [rax]
0x18000950a  mov     rax, [rcx+20h]
0x18000950e  mov     rcx, r10
0x180009511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009516  mov     rcx, rsi; struct IHttpContext *
0x180009519  call    ?HandleMethodNotAllowed@@YAXPEAVIHttpContext@@@Z; HandleMethodNotAllowed(IHttpContext *)
0x18000951e  jmp     short loc_1800094CC
0x180009520  mov     rdx, rsi; struct IHttpContext *
0x180009523  call    ?SetupLogData@DAV_HTTP_MODULE@@AEAAJPEAVIHttpContext@@@Z; DAV_HTTP_MODULE::SetupLogData(IHttpContext *)
0x180009528  mov     edx, eax
0x18000952a  test    eax, eax
0x18000952c  js      short loc_1800094BD
0x18000952e  mov     r8, r12; struct IHttpEventProvider *
0x180009531  mov     rdx, rsi; struct IHttpContext *
0x180009534  mov     rcx, r13; this
0x180009537  call    ?TestDavPreconditions@DAV_SITE_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAVIHttpEventProvider@@@Z; DAV_SITE_STORED_CONTEXT::TestDavPreconditions(IHttpContext *,IHttpEventProvider *)
0x18000953c  mov     r14d, 2
0x180009542  test    eax, eax
0x180009544  js      loc_180009CDA
0x18000954a  mov     rax, [rsi]
0x18000954d  mov     rcx, rsi
0x180009550  mov     rax, [rax+18h]
0x180009554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009559  mov     rdx, rax
0x18000955c  mov     rcx, [rax]
0x18000955f  mov     rax, [rcx+8]
0x180009563  mov     rcx, rdx
0x180009566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956b  mov     rcx, [rax+60h]
0x18000956f  mov     r8, [rax+58h]
0x180009573  test    rcx, rcx
0x180009576  jnz     short loc_180009588
0x180009578  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000957c  inc     rcx
0x18000957f  cmp     [r8+rcx*2], r15w
0x180009584  jnz     short loc_18000957C
0x180009586  jmp     short loc_18000958E
0x180009588  sub     rcx, r8
0x18000958b  sar     rcx, 1
0x18000958e  mov     r11, [rsi]
0x180009591  mov     edx, ecx; unsigned int
0x180009593  mov     rcx, r8; unsigned __int16 *
0x180009596  call    ?IsValidUri@@YAHPEBGK@Z; IsValidUri(ushort const *,ulong)
0x18000959b  mov     rcx, rsi
0x18000959e  test    eax, eax
0x1800095a0  jnz     loc_180009655
0x1800095a6  mov     rax, [r11+110h]
0x1800095ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b2  mov     r10, rax
0x1800095b5  mov     byte ptr [rsp+58h+var_38], 3
0x1800095ba  xor     r9d, r9d
0x1800095bd  lea     rdx, aInvalidRequest; "Invalid Request URI"
0x1800095c4  xor     r8d, r8d
0x1800095c7  mov     rcx, [rax]
0x1800095ca  mov     rax, [rcx+20h]
0x1800095ce  mov     rcx, r10
0x1800095d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d6  mov     rax, [rsi]
0x1800095d9  mov     rcx, rsi
0x1800095dc  mov     rax, [rax+20h]
0x1800095e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e5  mov     rdx, rax
0x1800095e8  mov     rcx, [rax]
0x1800095eb  mov     rax, [rcx+8]
0x1800095ef  mov     rcx, rdx
0x1800095f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f7  mov     rcx, rsi
0x1800095fa  mov     [rax+218h], r15w
0x180009602  mov     rax, [rsi]
0x180009605  mov     rax, [rax+20h]
0x180009609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000960e  mov     r10, rax
0x180009611  mov     dword ptr [rsp+58h+var_28], r15d
0x180009616  xor     r9d, r9d
0x180009619  mov     [rsp+58h+var_30], r15
0x18000961e  mov     edx, 190h
0x180009623  mov     [rsp+58h+var_38], r15d
0x180009628  mov     rcx, [rax]
0x18000962b  lea     r8, aBadRequest; "Bad Request"
0x180009632  mov     rax, [rcx+18h]
0x180009636  mov     rcx, r10
0x180009639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000963e  mov     rax, [rsi]
0x180009641  mov     rcx, rsi
0x180009644  mov     rax, [rax+0C8h]
0x18000964b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009650  jmp     loc_180009CDA
0x180009655  mov     rax, [r11+18h]
0x180009659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965e  mov     rdx, rax
0x180009661  mov     rcx, [rax]
0x180009664  mov     rax, [rcx+8]
0x180009668  mov     rcx, rdx
0x18000966b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009670  mov     ecx, [rax+24h]
0x180009673  lea     eax, [rcx-4]
0x180009676  cmp     eax, edi
0x180009678  jbe     loc_180009CCC
0x18000967e  sub     ecx, 7
0x180009681  jz      loc_180009AA5
0x180009687  sub     ecx, edi
0x180009689  jz      loc_180009A24
0x18000968f  sub     ecx, 4
0x180009692  jz      loc_1800099BA
0x180009698  sub     ecx, edi
0x18000969a  jz      loc_180009933
0x1800096a0  sub     ecx, edi
0x1800096a2  jz      loc_18000987F
0x1800096a8  sub     ecx, edi
0x1800096aa  jz      loc_1800097D9
0x1800096b0  sub     ecx, edi
0x1800096b2  jz      loc_18000979F
0x1800096b8  sub     ecx, edi
0x1800096ba  jz      short loc_180009708
0x1800096bc  cmp     ecx, edi
0x1800096be  mov     rcx, rsi; struct IHttpContext *
0x1800096c1  jz      short loc_1800096CD
0x1800096c3  call    ?HandleMethodNotAllowed@@YAXPEAVIHttpContext@@@Z; HandleMethodNotAllowed(IHttpContext *)
0x1800096c8  jmp     loc_180009CDA
0x1800096cd  mov     rax, [rsi]
0x1800096d0  mov     edx, 128h
0x1800096d5  mov     rax, [rax+90h]
0x1800096dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e1  mov     rbx, rax
0x1800096e4  test    rax, rax
0x1800096e7  jz      short loc_1800096FD
0x1800096e9  mov     rcx, rax; this
0x1800096ec  call    ??0DAV_BASE_HANDLER@@QEAA@XZ; DAV_BASE_HANDLER::DAV_BASE_HANDLER(void)
0x1800096f1  lea     rax, ??_7UNLOCK_VERB_HANDLER@@6B@; const UNLOCK_VERB_HANDLER::`vftable'
0x1800096f8  mov     [rbx], rax
0x1800096fb  jmp     short loc_180009700
0x1800096fd  mov     rbx, r15
0x180009700  mov     r15d, edi
0x180009703  jmp     loc_180009B6F
0x180009708  mov     rax, [rsi]
0x18000970b  mov     edx, 15D0h
0x180009710  mov     rcx, rsi
0x180009713  mov     rax, [rax+90h]
0x18000971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971f  mov     rbx, rax
0x180009722  test    rax, rax
0x180009725  jz      short loc_1800096FD
0x180009727  mov     rcx, rax; this
0x18000972a  call    ??0XML_ASYNC_HANDLER@@QEAA@XZ; XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(void)
0x18000972f  lea     rax, ??_7LOCK_VERB_HANDLER@@6BDAV_BASE_HANDLER@@@; const LOCK_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'}
0x180009736  mov     [rbx], rax
0x180009739  lea     rcx, [rbx+1D8h]
0x180009740  lea     rax, ??_7LOCK_VERB_HANDLER@@6BIAsyncEventSink@@@; const LOCK_VERB_HANDLER::`vftable'{for `IAsyncEventSink'}
0x180009747  mov     [rbx+128h], rax
0x18000974e  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180009754  mov     [rbx+1C0h], edi
0x18000975a  lea     rax, word_1800263B2
0x180009761  mov     [rbx+1C8h], rax
0x180009768  lea     rcx, [rbx+238h]; this
0x18000976f  mov     dword ptr [rbx+210h], 10001h
0x180009779  lea     rax, asc_1800263B8; ">"
0x180009780  mov     [rbx+1D0h], rax
0x180009787  mov     [rbx+218h], r15
0x18000978e  mov     [rbx+220h], r15d
0x180009795  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000979a  jmp     loc_180009700
0x18000979f  mov     rax, [rsi]
0x1800097a2  mov     edx, 128h
0x1800097a7  mov     rcx, rsi
0x1800097aa  mov     rax, [rax+90h]
0x1800097b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b6  mov     rbx, rax
0x1800097b9  test    rax, rax
0x1800097bc  jz      loc_180009B69
0x1800097c2  mov     rcx, rax; this
0x1800097c5  call    ??0DAV_BASE_HANDLER@@QEAA@XZ; DAV_BASE_HANDLER::DAV_BASE_HANDLER(void)
0x1800097ca  lea     rax, ??_7MKCOL_VERB_HANDLER@@6B@; const MKCOL_VERB_HANDLER::`vftable'
0x1800097d1  mov     [rbx], rax
0x1800097d4  jmp     loc_180009B6C
0x1800097d9  mov     rax, [rsi]
0x1800097dc  mov     edx, 1798h
0x1800097e1  mov     rcx, rsi
0x1800097e4  mov     rax, [rax+90h]
0x1800097eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f0  mov     rbx, rax
0x1800097f3  test    rax, rax
0x1800097f6  jz      short loc_180009874
0x1800097f8  mov     rcx, rax; this
0x1800097fb  call    ??0XML_ASYNC_HANDLER@@QEAA@XZ; XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(void)
0x180009800  lea     rax, ??_7PROPPATCH_VERB_HANDLER@@6BDAV_BASE_HANDLER@@@; const PROPPATCH_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'}
0x180009807  mov     [rbx], rax
0x18000980a  lea     rcx, [rbx+1D8h]
0x180009811  lea     rax, ??_7PROPPATCH_VERB_HANDLER@@6BIAsyncEventSink@@@; const PROPPATCH_VERB_HANDLER::`vftable'{for `IAsyncEventSink'}
0x180009818  mov     [rbx+128h], rax
0x18000981f  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180009825  mov     [rbx+1C0h], edi
0x18000982b  lea     rax, word_1800263B2
0x180009832  mov     [rbx+1C8h], rax
0x180009839  lea     rcx, [rbx+228h]; this
0x180009840  mov     dword ptr [rbx+210h], 10001h
0x18000984a  lea     rax, asc_1800263B8; ">"
0x180009851  mov     [rbx+1D0h], rax
0x180009858  lea     rdx, aN; "n"
0x18000985f  mov     [rbx+218h], r15
0x180009866  mov     [rbx+220h], r15d
0x18000986d  call    ??0DAV_NAMESPACE_SET@@QEAA@PEBG@Z; DAV_NAMESPACE_SET::DAV_NAMESPACE_SET(ushort const *)
0x180009872  jmp     short loc_180009877
0x180009874  mov     rbx, r15
0x180009877  mov     r15d, r14d
0x18000987a  jmp     loc_180009B71
0x18000987f  mov     rax, [rsi]
0x180009882  mov     edx, 17A0h
0x180009887  mov     rcx, rsi
0x18000988a  mov     rax, [rax+90h]
0x180009891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009896  mov     rbx, rax
0x180009899  test    rax, rax
0x18000989c  jz      loc_180009928
0x1800098a2  mov     rcx, rax; this
0x1800098a5  call    ??0XML_ASYNC_HANDLER@@QEAA@XZ; XML_ASYNC_HANDLER::XML_ASYNC_HANDLER(void)
0x1800098aa  lea     rax, ??_7PROPFIND_VERB_HANDLER@@6BDAV_BASE_HANDLER@@@; const PROPFIND_VERB_HANDLER::`vftable'{for `DAV_BASE_HANDLER'}
0x1800098b1  mov     [rbx], rax
0x1800098b4  lea     rcx, [rbx+1D8h]
0x1800098bb  lea     rax, ??_7PROPFIND_VERB_HANDLER@@6BIAsyncEventSink@@@; const PROPFIND_VERB_HANDLER::`vftable'{for `IAsyncEventSink'}
0x1800098c2  mov     [rbx+128h], rax
0x1800098c9  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800098cf  mov     [rbx+1C0h], edi
0x1800098d5  lea     rax, word_1800263B2
0x1800098dc  mov     [rbx+1C8h], rax
0x1800098e3  lea     rcx, [rbx+228h]; this
0x1800098ea  mov     dword ptr [rbx+210h], 10001h
0x1800098f4  lea     rax, asc_1800263B8; ">"
0x1800098fb  mov     [rbx+1D0h], rax
0x180009902  lea     rdx, aN; "n"
0x180009909  mov     [rbx+218h], r15
0x180009910  mov     [rbx+220h], r15d
0x180009917  call    ??0DAV_NAMESPACE_SET@@QEAA@PEBG@Z; DAV_NAMESPACE_SET::DAV_NAMESPACE_SET(ushort const *)
0x18000991c  mov     dword ptr [rbx+1798h], 0FFFFFFFFh
0x180009926  jmp     short loc_18000992B
0x180009928  mov     rbx, r15
0x18000992b  mov     r15d, edi
0x18000992e  jmp     loc_180009B71
0x180009933  mov     rax, [rsi]
0x180009936  mov     edx, 1A0h
0x18000993b  mov     rcx, rsi
0x18000993e  mov     rax, [rax+90h]
0x180009945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000994a  mov     rbx, rax
0x18000994d  test    rax, rax
0x180009950  jz      short loc_180009928
0x180009952  mov     rcx, rax; this
0x180009955  call    ??0DAV_BASE_HANDLER@@QEAA@XZ; DAV_BASE_HANDLER::DAV_BASE_HANDLER(void)
0x18000995a  lea     rax, ??_7COPY_MOVE_BASE_HANDLER@@6B@; const COPY_MOVE_BASE_HANDLER::`vftable'
0x180009961  lea     rcx, [rbx+140h]
0x180009968  mov     [rbx], rax
0x18000996b  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180009971  lea     rax, word_1800263B2
0x180009978  mov     [rbx+130h], rax
0x18000997f  lea     rax, asc_1800263B8; ">"
0x180009986  mov     [rbx+138h], rax
0x18000998d  lea     rax, ??_7COPY_VERB_HANDLER@@6B@; const COPY_VERB_HANDLER::`vftable'
0x180009994  mov     [rbx+128h], edi
0x18000999a  mov     dword ptr [rbx+178h], 10001h
0x1800099a4  mov     [rbx+188h], r15d
  ... truncated ...
```
