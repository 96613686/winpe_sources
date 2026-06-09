# W3WP_HOST::AddToActiveProtocolsList(ushort const *)

- ea: `0x180003340`
- end: `0x1800034a4`
- name: `?AddToActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z`
- size: `356`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000750c`

## callees

- `0x180002090`
- `0x18000315c`
- `0x1800031d8`
- `0x180003340`
- `0x180003b18`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003378`
- `msvcrt!_wcsicmp` at `0x180003378`
- `iisutil!PuDbgPrintError` at `0x180003437`
- `iisutil!PuDbgPrintError` at `0x18000348c`
- `iisutil!PuDbgPrintError` at `0x180003437`
- `iisutil!PuDbgPrintError` at `0x18000348c`

## string_xrefs

- `0x18000342c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003485`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003464`: `Failed to allocate memory for PROTOCOL_ID_ARRAY_LIST_ENTRY.\n`
- `0x18000341e`: `W3WP_HOST::AddToActiveProtocolsList`
- `0x180003470`: `W3WP_HOST::AddToActiveProtocolsList`
- `0x1800033dd`: `pEntry->SetProtocolId() failed.\n`
- `0x18000340c`: `m_ProtocolIDsList.AddEntry() failed.\n`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::AddToActiveProtocolsList(W3WP_HOST *this, const unsigned __int16 *a2)
{
  __int64 i; // rbx
  const wchar_t *v5; // rdx
  __int64 v6; // rdi
  char *v7; // rbx
  int v8; // eax
  unsigned int v9; // edx
  unsigned int v10; // r8d
  int v11; // eax

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 88); i = (unsigned int)(i + 1) )
  {
    v5 = &dword_18000FB84;
    v6 = *(_QWORD *)(*((_QWORD *)this + 43) + 8 * i);
    if ( *(_QWORD *)(v6 + 8) )
      v5 = *(const wchar_t **)(v6 + 8);
    if ( !_wcsicmp(a2, v5) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
      return 0;
    }
  }
  v7 = (char *)operator new(0x18u);
  if ( v7 )
  {
    *(_QWORD *)v7 = &PROTOCOL_ID_ARRAY_LIST_ENTRY::`vftable';
    *((_QWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 4) = 0;
    v8 = SMALL_STRU::Copy((SMALL_STRU *)(v7 + 8), a2);
    if ( v8 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 4);
      v11 = ARRAY_LIST::AddEntry((W3WP_HOST *)((char *)this + 344), (struct IArrayListEntry *)v7, v10);
      if ( v11 >= 0 )
        return 1;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          3536,
          "W3WP_HOST::AddToActiveProtocolsList",
          v11,
          "m_ProtocolIDsList.AddEntry() failed.\n");
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3518,
        "W3WP_HOST::AddToActiveProtocolsList",
        v8,
        "pEntry->SetProtocolId() failed.\n");
    }
    PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'((PROTOCOL_ID_ARRAY_LIST_ENTRY *)v7, v9);
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3502,
      "W3WP_HOST::AddToActiveProtocolsList",
      -2147024888,
      "Failed to allocate memory for PROTOCOL_ID_ARRAY_LIST_ENTRY.\n");
  }
  return 0;
}

```

## disassembly

```asm
0x180003340  push    rbx
0x180003342  push    rbp
0x180003343  push    rsi
0x180003344  push    rdi
0x180003345  sub     rsp, 38h
0x180003349  mov     rbp, rdx
0x18000334c  mov     rsi, rcx
0x18000334f  xor     ebx, ebx
0x180003351  cmp     ebx, [rsi+160h]
0x180003357  jnb     short loc_180003395
0x180003359  mov     rax, [rsi+158h]
0x180003360  lea     rdx, dword_18000FB84
0x180003367  mov     rcx, rbp; String1
0x18000336a  mov     rdi, [rax+rbx*8]
0x18000336e  cmp     qword ptr [rdi+8], 0
0x180003373  cmovnz  rdx, [rdi+8]; String2
0x180003378  call    cs:__imp__wcsicmp
0x18000337f  nop     dword ptr [rax+rax+00h]
0x180003384  test    eax, eax
0x180003386  jz      short loc_18000338C
0x180003388  inc     ebx
0x18000338a  jmp     short loc_180003351
0x18000338c  lock inc dword ptr [rdi+10h]
0x180003390  jmp     loc_180003498
0x180003395  mov     ecx, 18h; Size
0x18000339a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000339f  mov     rbx, rax
0x1800033a2  test    rax, rax
0x1800033a5  jz      loc_180003454
0x1800033ab  lea     rax, ??_7PROTOCOL_ID_ARRAY_LIST_ENTRY@@6B@; const PROTOCOL_ID_ARRAY_LIST_ENTRY::`vftable'
0x1800033b2  mov     rdx, rbp; unsigned __int16 *
0x1800033b5  mov     [rbx], rax
0x1800033b8  lea     rcx, [rbx+8]; this
0x1800033bc  mov     qword ptr [rbx+8], 0
0x1800033c4  mov     dword ptr [rbx+10h], 0
0x1800033cb  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x1800033d0  test    eax, eax
0x1800033d2  jns     short loc_1800033EC
0x1800033d4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800033db  jz      short loc_180003443
0x1800033dd  lea     rcx, aPentrySetproto; "pEntry->SetProtocolId() failed.\n"
0x1800033e4  mov     r8d, 0DBEh
0x1800033ea  jmp     short loc_180003419
0x1800033ec  lock inc dword ptr [rbx+10h]
0x1800033f0  lea     rcx, [rsi+158h]; this
0x1800033f7  mov     rdx, rbx; struct IArrayListEntry *
0x1800033fa  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x1800033ff  test    eax, eax
0x180003401  jns     short loc_18000344D
0x180003403  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000340a  jz      short loc_180003443
0x18000340c  lea     rcx, aMProtocolidsli; "m_ProtocolIDsList.AddEntry() failed.\n"
0x180003413  mov     r8d, 0DD0h
0x180003419  mov     [rsp+58h+var_30], rcx
0x18000341e  lea     r9, aW3wpHostAddtoa; "W3WP_HOST::AddToActiveProtocolsList"
0x180003425  mov     rcx, cs:g_pDebug
0x18000342c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003433  mov     [rsp+58h+var_38], eax
0x180003437  call    cs:__imp_PuDbgPrintError
0x18000343e  nop     dword ptr [rax+rax+00h]
0x180003443  mov     rcx, rbx; this
0x180003446  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000344b  jmp     short loc_180003498
0x18000344d  mov     eax, 1
0x180003452  jmp     short loc_18000349A
0x180003454  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000345b  jz      short loc_180003498
0x18000345d  mov     rcx, cs:g_pDebug
0x180003464  lea     rax, aFailedToAlloca; "Failed to allocate memory for PROTOCOL_"...
0x18000346b  mov     [rsp+58h+var_30], rax
0x180003470  lea     r9, aW3wpHostAddtoa; "W3WP_HOST::AddToActiveProtocolsList"
0x180003477  mov     r8d, 0DAEh
0x18000347d  mov     [rsp+58h+var_38], 80070008h
0x180003485  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000348c  call    cs:__imp_PuDbgPrintError
0x180003493  nop     dword ptr [rax+rax+00h]
0x180003498  xor     eax, eax
0x18000349a  add     rsp, 38h
0x18000349e  pop     rdi
0x18000349f  pop     rsi
0x1800034a0  pop     rbp
0x1800034a1  pop     rbx
0x1800034a2  retn
```
