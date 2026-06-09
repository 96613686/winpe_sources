# BINDING_TABLE::CreateRequestQueue(void)

- ea: `0x180012180`
- end: `0x1800124d5`
- name: `?CreateRequestQueue@BINDING_TABLE@@AEAAJXZ`
- size: `853`
- prototype: `__int64 __fastcall(BINDING_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001060`

## callees

- `0x180012180`
- `0x180015f6c`

## import_xrefs

- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1800121ed`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180012327`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x1800121ed`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180012327`
- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800121b3`
- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800121b3`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1800122c8`
- `HTTPAPI!HttpCloseRequestQueue` at `0x1800122c8`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180012298`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180012298`
- `HTTPAPI!HttpSetRequestQueueProperty` at `0x1800123d0`
- `HTTPAPI!HttpSetRequestQueueProperty` at `0x1800123d0`
- `iisutil!PuDbgPrint` at `0x180012238`
- `iisutil!PuDbgPrint` at `0x18001237b`
- `iisutil!PuDbgPrint` at `0x1800124ab`
- `iisutil!PuDbgPrint` at `0x180012238`
- `iisutil!PuDbgPrint` at `0x18001237b`
- `iisutil!PuDbgPrint` at `0x1800124ab`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001243f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001243f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001226f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001226f`

## string_xrefs

- `0x180012231`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180012374`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800124a4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001221f`: `BINDING_TABLE::CreateRequestQueue`
- `0x18001234b`: `BINDING_TABLE::CreateRequestQueue`
- `0x1800123f4`: `BINDING_TABLE::CreateRequestQueue`
- `0x180012449`: `BINDING_TABLE::CreateRequestQueue`
- `0x180012492`: `BINDING_TABLE::CreateRequestQueue`
- `0x180012214`: `Unable to activate Config Group. Error=%08x. Returning\n`
- `0x18001245b`: `CreateRequestQueue failed for AppPool '%ws'. Error=%08x. Returning\n`
- `0x180012361`: `SetConfigGroupRequestQueueHandle failed for AppPool '%ws'. Error=%08x. Returning\n`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::CreateRequestQueue(BINDING_TABLE *this)
{
  signed int v2; // ebx
  HTTP_URL_GROUP_ID v3; // rcx
  const WCHAR *Str; // rax
  _QWORD *v6; // rdi
  signed int RequestQueue; // ebx
  void *v8; // r8
  _BYTE *v9; // rax
  HTTP_URL_GROUP_ID v10; // rcx
  __int64 v11; // rdx
  void *v12; // rcx
  unsigned __int16 *v13; // rax
  _OWORD v14[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 PropertyInformation; // [rsp+70h] [rbp+8h] BYREF

  PropertyInformation = 1;
  v2 = HttpSetServerSessionProperty(*((_QWORD *)this + 46), HttpServerStateProperty, &PropertyInformation, 8u);
  if ( v2 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        677,
        "BINDING_TABLE::CreateRequestQueue",
        "Unable to activate ControlChannel. Error=%08x. Returning\n",
        v2);
    if ( v2 <= 0 )
      return (unsigned int)v2;
    return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    *((_DWORD *)this + 94) = 1;
    v3 = *((_QWORD *)this + 48);
    PropertyInformation = 1;
    v2 = HttpSetUrlGroupProperty(v3, HttpServerStateProperty, &PropertyInformation, 8u);
    if ( v2 )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          693,
          "BINDING_TABLE::CreateRequestQueue",
          "Unable to activate Config Group. Error=%08x. Returning\n",
          v2);
      if ( v2 > 0 )
        return (unsigned __int16)v2 | 0x80070000;
      return (unsigned int)v2;
    }
    Str = STRU::QueryStr((BINDING_TABLE *)((char *)this + 72));
    v6 = (_QWORD *)((char *)this + 392);
    LODWORD(PropertyInformation) = 2;
    RequestQueue = HttpCreateRequestQueue((HTTPAPI_VERSION)2, Str, 0, 2u, (PHANDLE)this + 49);
    if ( RequestQueue || (RequestQueue = HTTP_WRAPPER::SetRequestQueueState((char *)this + 352, *v6, 2)) != 0 )
    {
      if ( *v6 )
      {
        HttpCloseRequestQueue((char *)this + 392);
        *v6 = 0;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v13 = STRU::QueryStr((BINDING_TABLE *)((char *)this + 16));
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          715,
          "BINDING_TABLE::CreateRequestQueue",
          "CreateRequestQueue failed for AppPool '%ws'. Error=%08x. Returning\n",
          v13,
          RequestQueue);
      }
    }
    else
    {
      v8 = (void *)*v6;
      v9 = v14;
      v10 = *((_QWORD *)this + 48);
      v14[0] = 0;
      v11 = 16;
      do
      {
        *v9++ = 0;
        --v11;
      }
      while ( v11 );
      LODWORD(v14[0]) |= 1u;
      *((_QWORD *)&v14[0] + 1) = v8;
      RequestQueue = HttpSetUrlGroupProperty(v10, HttpServerBindingProperty, v14, 0x10u);
      if ( RequestQueue )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
            736,
            "BINDING_TABLE::CreateRequestQueue",
            "SetConfigGroupRequestQueueHandle failed for AppPool '%ws'. Error=%08x. Returning\n",
            *((_QWORD *)this + 6),
            RequestQueue);
      }
      else
      {
        v12 = (void *)*v6;
        LODWORD(PropertyInformation) = 0;
        RequestQueue = HttpSetRequestQueueProperty(v12, HttpServerStateProperty, &PropertyInformation, 4u, 0, 0);
        if ( !RequestQueue )
          return 0;
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
            752,
            "BINDING_TABLE::CreateRequestQueue",
            "SetRequestQueueState failed for AppPool '%ws'. Error=%08x. Returning\n",
            *((_QWORD *)this + 6),
            RequestQueue);
      }
    }
    if ( RequestQueue > 0 )
      return (unsigned __int16)RequestQueue | 0x80070000;
    return (unsigned int)RequestQueue;
  }
}

```

## disassembly

```asm
0x180012180  mov     [rsp+arg_18], rbx
0x180012185  push    rbp
0x180012186  push    rsi
0x180012187  push    r14
0x180012189  sub     rsp, 50h
0x18001218d  mov     rsi, rcx
0x180012190  mov     [rsp+68h+PropertyInformation], 1
0x180012199  mov     rcx, [rcx+170h]; ServerSessionId
0x1800121a0  lea     r8, [rsp+68h+PropertyInformation]; PropertyInformation
0x1800121a5  mov     r9d, 8; PropertyInformationLength
0x1800121ab  mov     edx, 5; Property
0x1800121b0  xor     r14d, r14d
0x1800121b3  call    cs:__imp_HttpSetServerSessionProperty
0x1800121b9  mov     ebx, eax
0x1800121bb  test    eax, eax
0x1800121bd  jnz     loc_18001246C
0x1800121c3  mov     dword ptr [rsi+178h], 1
0x1800121cd  lea     r8, [rsp+68h+PropertyInformation]; PropertyInformation
0x1800121d2  mov     rcx, [rsi+180h]; UrlGroupId
0x1800121d9  mov     r9d, 8; PropertyInformationLength
0x1800121df  mov     edx, 5; Property
0x1800121e4  mov     [rsp+68h+PropertyInformation], 1
0x1800121ed  call    cs:__imp_HttpSetUrlGroupProperty
0x1800121f3  mov     ebx, eax
0x1800121f5  test    eax, eax
0x1800121f7  jz      short loc_18001225E
0x1800121f9  mov     eax, cs:g_dwDebugFlags
0x1800121ff  test    al, 3
0x180012201  setnz   cl
0x180012204  test    al, 8
0x180012206  setnz   al
0x180012209  test    al, cl
0x18001220b  jz      short loc_18001223E
0x18001220d  mov     rcx, cs:g_pDebug
0x180012214  lea     rax, aUnableToActiva; "Unable to activate Config Group. Error="...
0x18001221b  mov     dword ptr [rsp+68h+Reserved2], ebx
0x18001221f  lea     r9, aBindingTableCr_0; "BINDING_TABLE::CreateRequestQueue"
0x180012226  mov     r8d, 2B5h
0x18001222c  mov     [rsp+68h+RequestQueueHandle], rax
0x180012231  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180012238  call    cs:__imp_PuDbgPrint
0x18001223e  test    ebx, ebx
0x180012240  jle     short loc_18001224B
0x180012242  movzx   ebx, bx
0x180012245  or      ebx, 80070000h
0x18001224b  mov     eax, ebx
0x18001224d  mov     rbx, [rsp+68h+arg_18]
0x180012255  add     rsp, 50h
0x180012259  pop     r14
0x18001225b  pop     rsi
0x18001225c  pop     rbp
0x18001225d  retn
0x18001225e  mov     [rsp+68h+arg_8], rdi
0x180012263  lea     rcx, [rsi+48h]
0x180012267  mov     [rsp+68h+arg_10], r15
0x18001226f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012275  mov     r15d, 2
0x18001227b  lea     rdi, [rsi+188h]
0x180012282  mov     r9d, r15d; Flags
0x180012285  mov     dword ptr [rsp+68h+PropertyInformation], r15d
0x18001228a  mov     rdx, rax; Name
0x18001228d  mov     [rsp+68h+RequestQueueHandle], rdi; RequestQueueHandle
0x180012292  mov     ecx, r15d; Version
0x180012295  xor     r8d, r8d; SecurityAttributes
0x180012298  call    cs:__imp_HttpCreateRequestQueue
0x18001229e  mov     ebx, eax
0x1800122a0  test    eax, eax
0x1800122a2  jnz     short loc_1800122BC
0x1800122a4  mov     rdx, [rdi]
0x1800122a7  lea     rcx, [rsi+160h]
0x1800122ae  mov     r8d, r15d
0x1800122b1  call    ?SetRequestQueueState@HTTP_WRAPPER@@QEAAKPEAXW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@@Z; HTTP_WRAPPER::SetRequestQueueState(void *,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)
0x1800122b6  mov     ebx, eax
0x1800122b8  test    eax, eax
0x1800122ba  jz      short loc_1800122D9
0x1800122bc  cmp     [rdi], r14
0x1800122bf  jz      loc_180012423
0x1800122c5  mov     rcx, rdi; RequestQueueHandle
0x1800122c8  call    cs:__imp_HttpCloseRequestQueue
0x1800122ce  mov     [rdi], r14
0x1800122d1  test    ebx, ebx
0x1800122d3  jnz     loc_180012423
0x1800122d9  mov     r8, [rdi]
0x1800122dc  lea     rax, [rsp+68h+var_28]
0x1800122e1  mov     rcx, [rsi+180h]; UrlGroupId
0x1800122e8  xorps   xmm0, xmm0
0x1800122eb  movups  [rsp+68h+var_28], xmm0
0x1800122f0  mov     edx, 10h
0x1800122f5  nop     word ptr [rax+rax+00000000h]
0x180012300  mov     [rax], r14b
0x180012303  lea     rax, [rax+1]
0x180012307  sub     rdx, 1
0x18001230b  jnz     short loc_180012300
0x18001230d  or      dword ptr [rsp+68h+var_28], 1
0x180012312  mov     r9d, 10h; PropertyInformationLength
0x180012318  mov     qword ptr [rsp+68h+var_28+8], r8
0x18001231d  mov     edx, 7; Property
0x180012322  lea     r8, [rsp+68h+var_28]; PropertyInformation
0x180012327  call    cs:__imp_HttpSetUrlGroupProperty
0x18001232d  mov     ebx, eax
0x18001232f  test    eax, eax
0x180012331  jz      short loc_1800123AE
0x180012333  mov     eax, cs:g_dwDebugFlags
0x180012339  test    al, 3
0x18001233b  setnz   cl
0x18001233e  test    al, 8
0x180012340  setnz   al
0x180012343  test    al, cl
0x180012345  jz      short loc_180012381
0x180012347  mov     rax, [rsi+30h]
0x18001234b  lea     r9, aBindingTableCr_0; "BINDING_TABLE::CreateRequestQueue"
0x180012352  mov     [rsp+68h+var_38], ebx
0x180012356  mov     r8d, 2E0h
0x18001235c  mov     [rsp+68h+Reserved2], rax
0x180012361  lea     rax, aSetconfiggroup; "SetConfigGroupRequestQueueHandle failed"...
0x180012368  mov     [rsp+68h+RequestQueueHandle], rax
0x18001236d  mov     rcx, cs:g_pDebug
0x180012374  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001237b  call    cs:__imp_PuDbgPrint
0x180012381  test    ebx, ebx
0x180012383  jle     short loc_18001238E
0x180012385  movzx   ebx, bx
0x180012388  or      ebx, 80070000h
0x18001238e  mov     eax, ebx
0x180012390  mov     rdi, [rsp+68h+arg_8]
0x180012395  mov     r15, [rsp+68h+arg_10]
0x18001239d  mov     rbx, [rsp+68h+arg_18]
0x1800123a5  add     rsp, 50h
0x1800123a9  pop     r14
0x1800123ab  pop     rsi
0x1800123ac  pop     rbp
0x1800123ad  retn
0x1800123ae  mov     rcx, [rdi]; RequestQueueHandle
0x1800123b1  lea     r8, [rsp+68h+PropertyInformation]; PropertyInformation
0x1800123b6  mov     [rsp+68h+Reserved2], r14; Reserved2
0x1800123bb  mov     r9d, 4; PropertyInformationLength
0x1800123c1  mov     edx, 5; Property
0x1800123c6  mov     dword ptr [rsp+68h+RequestQueueHandle], r14d; Reserved1
0x1800123cb  mov     dword ptr [rsp+68h+PropertyInformation], r14d
0x1800123d0  call    cs:__imp_HttpSetRequestQueueProperty
0x1800123d6  mov     ebx, eax
0x1800123d8  test    eax, eax
0x1800123da  jz      short loc_18001241B
0x1800123dc  mov     eax, cs:g_dwDebugFlags
0x1800123e2  test    al, 3
0x1800123e4  setnz   cl
0x1800123e7  test    al, 8
0x1800123e9  setnz   al
0x1800123ec  test    al, cl
0x1800123ee  jz      short loc_180012381
0x1800123f0  mov     rax, [rsi+30h]
0x1800123f4  lea     r9, aBindingTableCr_0; "BINDING_TABLE::CreateRequestQueue"
0x1800123fb  mov     [rsp+68h+var_38], ebx
0x1800123ff  mov     r8d, 2F0h
0x180012405  mov     [rsp+68h+Reserved2], rax
0x18001240a  lea     rax, aSetrequestqueu; "SetRequestQueueState failed for AppPool"...
0x180012411  mov     [rsp+68h+RequestQueueHandle], rax
0x180012416  jmp     loc_18001236D
0x18001241b  mov     eax, r14d
0x18001241e  jmp     loc_180012390
0x180012423  mov     eax, cs:g_dwDebugFlags
0x180012429  test    al, 3
0x18001242b  setnz   cl
0x18001242e  test    al, 8
0x180012430  setnz   al
0x180012433  test    al, cl
0x180012435  jz      loc_180012381
0x18001243b  lea     rcx, [rsi+10h]
0x18001243f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012445  mov     [rsp+68h+var_38], ebx
0x180012449  lea     r9, aBindingTableCr_0; "BINDING_TABLE::CreateRequestQueue"
0x180012450  mov     [rsp+68h+Reserved2], rax
0x180012455  mov     r8d, 2CBh
0x18001245b  lea     rax, aCreaterequestq; "CreateRequestQueue failed for AppPool '"...
0x180012462  mov     [rsp+68h+RequestQueueHandle], rax
0x180012467  jmp     loc_18001236D
0x18001246c  mov     eax, cs:g_dwDebugFlags
0x180012472  test    al, 3
0x180012474  setnz   cl
0x180012477  test    al, 8
0x180012479  setnz   al
0x18001247c  test    al, cl
0x18001247e  jz      short loc_1800124B1
0x180012480  mov     rcx, cs:g_pDebug
0x180012487  lea     rax, aUnableToActiva_0; "Unable to activate ControlChannel. Erro"...
0x18001248e  mov     dword ptr [rsp+68h+Reserved2], ebx
0x180012492  lea     r9, aBindingTableCr_0; "BINDING_TABLE::CreateRequestQueue"
0x180012499  mov     r8d, 2A5h
0x18001249f  mov     [rsp+68h+RequestQueueHandle], rax
0x1800124a4  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800124ab  call    cs:__imp_PuDbgPrint
0x1800124b1  test    ebx, ebx
0x1800124b3  jle     loc_18001224B
0x1800124b9  movzx   ebx, bx
0x1800124bc  or      ebx, 80070000h
0x1800124c2  mov     eax, ebx
0x1800124c4  mov     rbx, [rsp+68h+arg_18]
0x1800124cc  add     rsp, 50h
0x1800124d0  pop     r14
0x1800124d2  pop     rsi
0x1800124d3  pop     rbp
0x1800124d4  retn
```
