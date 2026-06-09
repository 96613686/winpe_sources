# W3WP_HOST::AddToActiveProtocolsList(ushort const *)

- ea: `0x180003150`
- end: `0x1800032a1`
- name: `?AddToActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z`
- size: `337`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006e3c`

## callees

- `0x180001f68`
- `0x180002f84`
- `0x180003000`
- `0x180003150`
- `0x180003878`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003188`
- `msvcrt!_wcsicmp` at `0x180003188`
- `iisutil!PuDbgPrintError` at `0x180003241`
- `iisutil!PuDbgPrintError` at `0x180003290`
- `iisutil!PuDbgPrintError` at `0x180003241`
- `iisutil!PuDbgPrintError` at `0x180003290`

## string_xrefs

- `0x180003236`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003289`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003268`: `Failed to allocate memory for PROTOCOL_ID_ARRAY_LIST_ENTRY.\n`
- `0x180003228`: `W3WP_HOST::AddToActiveProtocolsList`
- `0x180003274`: `W3WP_HOST::AddToActiveProtocolsList`
- `0x1800031e7`: `pEntry->SetProtocolId() failed.\n`
- `0x180003216`: `m_ProtocolIDsList.AddEntry() failed.\n`

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
    v5 = &dword_18000EB74;
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
0x180003150  push    rbx
0x180003152  push    rbp
0x180003153  push    rsi
0x180003154  push    rdi
0x180003155  sub     rsp, 38h
0x180003159  mov     rbp, rdx
0x18000315c  mov     rsi, rcx
0x18000315f  xor     ebx, ebx
0x180003161  cmp     ebx, [rsi+160h]
0x180003167  jnb     short loc_18000319F
0x180003169  mov     rax, [rsi+158h]
0x180003170  lea     rdx, dword_18000EB74
0x180003177  mov     rcx, rbp; String1
0x18000317a  mov     rdi, [rax+rbx*8]
0x18000317e  cmp     qword ptr [rdi+8], 0
0x180003183  cmovnz  rdx, [rdi+8]; String2
0x180003188  call    cs:__imp__wcsicmp
0x18000318e  test    eax, eax
0x180003190  jz      short loc_180003196
0x180003192  inc     ebx
0x180003194  jmp     short loc_180003161
0x180003196  lock inc dword ptr [rdi+10h]
0x18000319a  jmp     loc_180003296
0x18000319f  mov     ecx, 18h; Size
0x1800031a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800031a9  mov     rbx, rax
0x1800031ac  test    rax, rax
0x1800031af  jz      loc_180003258
0x1800031b5  lea     rax, ??_7PROTOCOL_ID_ARRAY_LIST_ENTRY@@6B@; const PROTOCOL_ID_ARRAY_LIST_ENTRY::`vftable'
0x1800031bc  mov     rdx, rbp; unsigned __int16 *
0x1800031bf  mov     [rbx], rax
0x1800031c2  lea     rcx, [rbx+8]; this
0x1800031c6  mov     qword ptr [rbx+8], 0
0x1800031ce  mov     dword ptr [rbx+10h], 0
0x1800031d5  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x1800031da  test    eax, eax
0x1800031dc  jns     short loc_1800031F6
0x1800031de  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800031e5  jz      short loc_180003247
0x1800031e7  lea     rcx, aPentrySetproto; "pEntry->SetProtocolId() failed.\n"
0x1800031ee  mov     r8d, 0DBEh
0x1800031f4  jmp     short loc_180003223
0x1800031f6  lock inc dword ptr [rbx+10h]
0x1800031fa  lea     rcx, [rsi+158h]; this
0x180003201  mov     rdx, rbx; struct IArrayListEntry *
0x180003204  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180003209  test    eax, eax
0x18000320b  jns     short loc_180003251
0x18000320d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003214  jz      short loc_180003247
0x180003216  lea     rcx, aMProtocolidsli; "m_ProtocolIDsList.AddEntry() failed.\n"
0x18000321d  mov     r8d, 0DD0h
0x180003223  mov     [rsp+58h+var_30], rcx
0x180003228  lea     r9, aW3wpHostAddtoa; "W3WP_HOST::AddToActiveProtocolsList"
0x18000322f  mov     rcx, cs:g_pDebug
0x180003236  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000323d  mov     [rsp+58h+var_38], eax
0x180003241  call    cs:__imp_PuDbgPrintError
0x180003247  mov     rcx, rbx; this
0x18000324a  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x18000324f  jmp     short loc_180003296
0x180003251  mov     eax, 1
0x180003256  jmp     short loc_180003298
0x180003258  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000325f  jz      short loc_180003296
0x180003261  mov     rcx, cs:g_pDebug
0x180003268  lea     rax, aFailedToAlloca; "Failed to allocate memory for PROTOCOL_"...
0x18000326f  mov     [rsp+58h+var_30], rax
0x180003274  lea     r9, aW3wpHostAddtoa; "W3WP_HOST::AddToActiveProtocolsList"
0x18000327b  mov     r8d, 0DAEh
0x180003281  mov     [rsp+58h+var_38], 80070008h
0x180003289  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003290  call    cs:__imp_PuDbgPrintError
0x180003296  xor     eax, eax
0x180003298  add     rsp, 38h
0x18000329c  pop     rdi
0x18000329d  pop     rsi
0x18000329e  pop     rbp
0x18000329f  pop     rbx
0x1800032a0  retn
```
