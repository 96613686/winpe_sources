# ProcessNewCall

- ea: `0x18000bf68`
- end: `0x18000c782`
- name: `ProcessNewCall`
- size: `2074`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000a620`

## callees

- `0x180002908`
- `0x180002d40`
- `0x180004d10`
- `0x18000827c`
- `0x180008360`
- `0x18000bf68`
- `0x18000cb08`
- `0x18000cb54`
- `0x18000ed24`
- `0x18001bca2`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000c0d4`
- `msvcrt!_stricmp` at `0x18000c0d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c67b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c67b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c68c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c68c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c6e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c6e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c492`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c492`
- `RPCRT4!UuidCreate` at `0x18000c3c3`
- `RPCRT4!UuidCreate` at `0x18000c3c3`
- `RPCRT4!UuidFromStringA` at `0x18000c1c7`
- `RPCRT4!UuidFromStringA` at `0x18000c1c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c389`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c371`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c371`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c3b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c3b8`
- `prxyqry!GetLinkSpeedForAddress` at `0x18000c5b0`
- `prxyqry!GetLinkSpeedForAddress` at `0x18000c5b0`

## string_xrefs

- `0x18000c5cc`: `CoId=%hs:GetLinkSpeedForAddr completes with %d [Tx: %I64u][Rx: %I64u]`

## pseudocode

```c
__int64 __fastcall ProcessNewCall(__int64 a1, __int64 a2, __int64 a3)
{
  size_t v5; // r12
  int v6; // edi
  unsigned int i; // esi
  unsigned __int16 *v8; // rbx
  const char *v9; // r8
  size_t v10; // r9
  size_t v11; // r9
  size_t *v12; // r8
  size_t v13; // rdx
  int v14; // edx
  int v15; // r8d
  int v16; // r10d
  int v17; // r11d
  int v18; // ebx
  int v19; // edi
  int v20; // esi
  __int64 v21; // r9
  const wchar_t *v22; // r8
  HMODULE ModuleHandleW; // rax
  RPC_STATUS v24; // eax
  unsigned int v25; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v27; // rax
  _DWORD *v28; // rbx
  int v29; // esi
  struct _RTL_CRITICAL_SECTION *v30; // rdi
  void *v31; // r13
  __int128 v32; // xmm0
  _QWORD *v33; // rdi
  _QWORD *v34; // rsi
  unsigned int LinkSpeedForAddress; // eax
  char *v36; // rcx
  __int64 v37; // rax
  __int64 result; // rax
  HANDLE v39; // rax
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  int cbMultiByte[2]; // [rsp+28h] [rbp-D8h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-D0h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  __int64 v44; // [rsp+40h] [rbp-C0h]
  __int64 v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  UUID Uuid; // [rsp+78h] [rbp-88h] BYREF
  CHAR MultiByteStr[8]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pszDest[12]; // [rsp+90h] [rbp-70h] BYREF
  char v52[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-48h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v56[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v55 = 0;
  memset_0(v56, 0, sizeof(v56));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    FormatRRASErrorString(&v55, L"Entering %ws", L"ProcessNewCall");
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(&v55, L"CallContext: %p has a new call associated", a1);
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
      }
    }
  }
  v5 = -1;
  *(_QWORD *)(a1 + 280) = *(_QWORD *)(a3 + 8);
  *(_QWORD *)(a1 + 272) = *(_QWORD *)(a3 + 16);
  *(_BYTE *)(a1 + 264) = 1;
  if ( !*(_WORD *)(a3 + 120) )
  {
LABEL_45:
    *(_QWORD *)MultiByteStr = 0;
    Uuid = 0;
    *(_OWORD *)pszDest = 0;
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"Did not receive correlation ID from peer. So generating a correlation ID on the server.");
    ModuleHandleW = GetModuleHandleW(0);
    LoadStringW(ModuleHandleW, 0x88BCu, pszDest, 8);
    WideCharToMultiByte(0, 0x400u, pszDest, -1, MultiByteStr, 8, 0, 0);
    v24 = UuidCreate(&Uuid);
    if ( v24 && v24 != 1824 )
    {
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasSSTPSvcTraceInfo,
          L"Generation of correlation ID on server failed");
      do
        ++v5;
      while ( MultiByteStr[v5] );
      StringCchCopyNA((STRSAFE_LPSTR)(a1 + 552), 0x28u, MultiByteStr, v5);
    }
    PrintGuid((STRSAFE_LPSTR)(a1 + 552));
    *(UUID *)(a1 + 592) = Uuid;
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"Correlation ID that will be used in the server logs is %hs", a1 + 552);
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
    }
    goto LABEL_56;
  }
  v6 = 0;
  *(_DWORD *)MultiByteStr = 0;
  for ( i = 0; i < *(unsigned __int16 *)(a3 + 120); *(_DWORD *)MultiByteStr = i )
  {
    v8 = (unsigned __int16 *)(*(_QWORD *)(a3 + 128) + 24LL * i);
    if ( !v8 )
    {
      if ( (byte_18002D803 & 0x10) == 0 )
        goto LABEL_43;
      v22 = L"(HttpRequest->Headers).pUnknownHeaders  is NULL";
      goto LABEL_42;
    }
    v9 = (const char *)*((_QWORD *)v8 + 1);
    if ( !v9 )
      goto LABEL_43;
    if ( *v8 >= 0x13u )
      v10 = 19;
    else
      v10 = *v8;
    StringCchCopyNA((STRSAFE_LPSTR)pszDest, 0x14u, v9, v10);
    if ( !_stricmp((const char *)pszDest, "SSTPCORRELATIONID") )
    {
      *(_OWORD *)v52 = 0;
      v54 = 0;
      v53 = 0;
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasSSTPSvcTraceInfo,
          L"Received correlation ID from peer");
      if ( v8[1] >= 0x27u )
        v11 = 39;
      else
        v11 = v8[1];
      StringCchCopyNA((STRSAFE_LPSTR)(a1 + 552), 0x28u, *((STRSAFE_PCNZCH *)v8 + 2), v11);
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(&v55, L"Correlation Id is %hs", a1 + 552);
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
      }
      v13 = -1;
      do
        ++v13;
      while ( *(_BYTE *)(a1 + 552 + v13) );
      if ( v13 )
      {
        if ( v13 <= 0x7FFFFFFF )
          StringCopyWorkerA(v52, v13, v12, (STRSAFE_PCNZCH)(a1 + 552), 0x7FFFFFFEu);
        else
          v52[0] = 0;
      }
      if ( UuidFromStringA((RPC_CSTR)&v52[1], (UUID *)(a1 + 592)) )
      {
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasSSTPSvcTraceInfo,
            L"Could not convert correlation ID from string to GUID to store in call context");
      }
      else if ( (byte_18002D803 & 0x10) != 0 )
      {
        v14 = *(unsigned __int8 *)(a1 + 605);
        v15 = *(unsigned __int8 *)(a1 + 604);
        v16 = *(unsigned __int8 *)(a1 + 603);
        v17 = *(unsigned __int8 *)(a1 + 602);
        v18 = *(unsigned __int8 *)(a1 + 601);
        v19 = *(unsigned __int8 *)(a1 + 600);
        v20 = *(unsigned __int16 *)(a1 + 598);
        v21 = *(unsigned __int16 *)(a1 + 596);
        LODWORD(v48) = *(unsigned __int8 *)(a1 + 607);
        LOWORD(v55) = 0;
        LODWORD(v47) = *(unsigned __int8 *)(a1 + 606);
        LODWORD(v46) = v14;
        LODWORD(v45) = v15;
        LODWORD(v44) = v16;
        LODWORD(lpUsedDefaultChar) = v17;
        LODWORD(lpDefaultChar) = v18;
        cbMultiByte[0] = v19;
        LODWORD(cchToCopy) = v20;
        FormatRRASErrorString(
          &v55,
          L"Correlation Guid is {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
          *(unsigned int *)(a1 + 592),
          v21,
          cchToCopy,
          *(_QWORD *)cbMultiByte,
          lpDefaultChar,
          lpUsedDefaultChar,
          v44,
          v45,
          v46,
          v47,
          v48);
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
        i = *(_DWORD *)MultiByteStr;
      }
      v6 = 1;
    }
    else if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"CorrelationIdHeaderName = %hs; does not match what we want", pszDest);
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        v22 = (const wchar_t *)&v55;
LABEL_42:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, v22);
      }
    }
LABEL_43:
    ++i;
  }
  if ( !v6 )
    goto LABEL_45;
LABEL_56:
  *(_DWORD *)MultiByteStr = *(unsigned __int16 *)(a3 + 552) + 193;
  v25 = *(_DWORD *)MultiByteStr;
  ProcessHeap = GetProcessHeap();
  v27 = HeapAlloc(ProcessHeap, 8u, v25);
  v28 = v27;
  if ( v27 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
    v27[18] = 0;
    v31 = v27 + 10;
    v27[10] = *(_DWORD *)(a1 + 244);
    v27[19] = 0;
    v27[11] = 120;
    v32 = *(_OWORD *)*(_QWORD *)(a3 + 104);
    v27[12] = 136;
    *((_OWORD *)v27 + 10) = v32;
    *((_OWORD *)v27 + 11) = *(_OWORD *)*(_QWORD *)(a3 + 112);
    if ( *(_WORD *)(a3 + 552) )
    {
      v27[38] = 152;
      v27[39] = *(unsigned __int16 *)(a3 + 552) + 1;
      memcpy_0(v27 + 48, *(const void **)(a3 + 560), *(unsigned __int16 *)(a3 + 552));
      *((_BYTE *)v28 + (unsigned int)(v28[39] - 1) + 192) = 0;
    }
    v33 = (_QWORD *)(a1 + 480);
    v34 = (_QWORD *)(a1 + 472);
    LinkSpeedForAddress = GetLinkSpeedForAddress(*(_QWORD *)(a3 + 112), a1 + 472, a1 + 480);
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(
        &v55,
        L"CoId=%hs:GetLinkSpeedForAddr completes with %d [Tx: %I64u][Rx: %I64u]",
        a1 + 552,
        LinkSpeedForAddress,
        *v34,
        *v33);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v55);
    }
    v36 = (char *)SstpSvcGlobals;
    *((_QWORD *)v28 + 7) = *v34;
    v37 = *v33;
    v30 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
    *((_QWORD *)v28 + 8) = v37;
    v28[8] = 17772;
    *((_BYTE *)v28 + 132) = v36[644];
    *((_OWORD *)v28 + 5) = *(_OWORD *)(v36 + 645);
    v28[24] = *(_DWORD *)(v36 + 661);
    *(_OWORD *)(v28 + 25) = *(_OWORD *)(v36 + 665);
    *(_OWORD *)(v28 + 29) = *(_OWORD *)(v36 + 681);
    *(_OWORD *)(v28 + 34) = *(_OWORD *)(a1 + 592);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    *(_DWORD *)(a1 + 252) |= 0x10u;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    result = AsyncSstpDeviceControl(0x128028u, v31, *(_DWORD *)MultiByteStr - 40, v31, 0x78u, (LPOVERLAPPED)v28);
    v29 = result;
    if ( (_DWORD)result )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      *(_DWORD *)(a1 + 252) &= ~0x10u;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      DereferenceRefCount(a1 + 208);
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v28);
      goto LABEL_68;
    }
  }
  else
  {
    v29 = -1073741801;
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"CoId=%hs:Error allocating call info - %d", a1 + 552, 3221225495LL);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v55);
    }
    v30 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
LABEL_68:
    EnterCriticalSection(v30);
    *(_DWORD *)(a1 + 268) = v29;
    result = InitiateCallContextCleanup(a1, 2);
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    result = FormatRRASErrorString(&v55, L"LEaving %ws", L"ProcessNewCall");
    if ( (byte_18002D803 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
  }
  return result;
}

```

## disassembly

```asm
0x18000bf68  mov     [rsp-8+arg_8], rbx
0x18000bf6d  push    rbp
0x18000bf6e  push    rsi
0x18000bf6f  push    rdi
0x18000bf70  push    r12
0x18000bf72  push    r13
0x18000bf74  push    r14
0x18000bf76  push    r15
0x18000bf78  lea     rbp, [rsp-7E0h]
0x18000bf80  sub     rsp, 8E0h
0x18000bf87  mov     rax, cs:__security_cookie
0x18000bf8e  xor     rax, rsp
0x18000bf91  mov     [rbp+810h+var_40], rax
0x18000bf98  mov     r15, r8
0x18000bf9b  mov     r14, rcx
0x18000bf9e  xor     r13d, r13d
0x18000bfa1  lea     rcx, [rbp+810h+var_83C]; void *
0x18000bfa5  mov     r8d, 7FCh; Size
0x18000bfab  mov     [rbp+810h+var_840], r13d
0x18000bfaf  xor     edx, edx; Val
0x18000bfb1  call    memset_0
0x18000bfb6  mov     al, cs:byte_18002D803
0x18000bfbc  lea     rsi, RasSSTPSvcTraceInfo
0x18000bfc3  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bfca  test    al, 10h
0x18000bfcc  jz      short loc_18000C03D
0x18000bfce  lea     r8, aProcessnewcall; "ProcessNewCall"
0x18000bfd5  mov     word ptr [rbp+810h+var_840], r13w
0x18000bfda  lea     rdx, aEnteringWs; "Entering %ws"
0x18000bfe1  lea     rcx, [rbp+810h+var_840]
0x18000bfe5  call    FormatRRASErrorString
0x18000bfea  mov     al, cs:byte_18002D803
0x18000bff0  test    al, 10h
0x18000bff2  jz      short loc_18000C03D
0x18000bff4  lea     r8, [rbp+810h+var_840]
0x18000bff8  mov     rdx, rsi
0x18000bffb  mov     rcx, rdi
0x18000bffe  call    McTemplateU0z_EventWriteTransfer
0x18000c003  mov     al, cs:byte_18002D803
0x18000c009  test    al, 10h
0x18000c00b  jz      short loc_18000C03D
0x18000c00d  mov     r8, r14
0x18000c010  mov     word ptr [rbp+810h+var_840], r13w
0x18000c015  lea     rdx, aCallcontextPHa; "CallContext: %p has a new call associat"...
0x18000c01c  lea     rcx, [rbp+810h+var_840]
0x18000c020  call    FormatRRASErrorString
0x18000c025  test    cs:byte_18002D803, 10h
0x18000c02c  jz      short loc_18000C03D
0x18000c02e  lea     r8, [rbp+810h+var_840]
0x18000c032  mov     rdx, rsi
0x18000c035  mov     rcx, rdi
0x18000c038  call    McTemplateU0z_EventWriteTransfer
0x18000c03d  mov     rax, [r15+8]
0x18000c041  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000c045  mov     [r14+118h], rax
0x18000c04c  mov     rax, [r15+10h]
0x18000c050  mov     [r14+110h], rax
0x18000c057  mov     byte ptr [r14+108h], 1
0x18000c05f  cmp     [r15+78h], r13w
0x18000c064  jz      loc_18000C341
0x18000c06a  mov     edi, r13d
0x18000c06d  mov     dword ptr [rbp+810h+MultiByteStr], r13d
0x18000c071  mov     esi, r13d
0x18000c074  lea     edx, [r12+14h]
0x18000c079  movzx   eax, word ptr [r15+78h]
0x18000c07e  cmp     esi, eax
0x18000c080  jnb     loc_18000C32B
0x18000c086  mov     eax, esi
0x18000c088  lea     rcx, [rax+rax*2]
0x18000c08c  mov     rax, [r15+80h]
0x18000c093  lea     rbx, [rax+rcx*8]
0x18000c097  test    rbx, rbx
0x18000c09a  jz      loc_18000C2F9
0x18000c0a0  mov     r8, [rbx+8]; pszSrc
0x18000c0a4  test    r8, r8
0x18000c0a7  jz      loc_18000C321
0x18000c0ad  cmp     [rbx], dx
0x18000c0b0  jnb     short loc_18000C0B8
0x18000c0b2  movzx   r9d, word ptr [rbx]
0x18000c0b6  jmp     short loc_18000C0BB
0x18000c0b8  mov     r9, rdx; cchToCopy
0x18000c0bb  mov     edx, 14h; cchDest
0x18000c0c0  lea     rcx, [rbp+810h+pszDest]; pszDest
0x18000c0c4  call    StringCchCopyNA
0x18000c0c9  lea     rdx, String2; "SSTPCORRELATIONID"
0x18000c0d0  lea     rcx, [rbp+810h+pszDest]; String1
0x18000c0d4  call    cs:__imp__stricmp
0x18000c0da  test    eax, eax
0x18000c0dc  jnz     loc_18000C2C8
0x18000c0e2  xor     eax, eax
0x18000c0e4  xorps   xmm0, xmm0
0x18000c0e7  test    cs:byte_18002D803, 10h
0x18000c0ee  movups  xmmword ptr [rbp+810h+var_868], xmm0
0x18000c0f2  mov     [rbp+810h+var_848], rax
0x18000c0f6  movups  [rbp+810h+var_858], xmm0
0x18000c0fa  jz      short loc_18000C116
0x18000c0fc  lea     r8, aReceivedCorrel; "Received correlation ID from peer"
0x18000c103  lea     rdx, RasSSTPSvcTraceInfo
0x18000c10a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c111  call    McTemplateU0z_EventWriteTransfer
0x18000c116  mov     eax, 27h ; '''
0x18000c11b  cmp     [rbx+2], ax
0x18000c11f  jnb     short loc_18000C128
0x18000c121  movzx   r9d, word ptr [rbx+2]
0x18000c126  jmp     short loc_18000C12B
0x18000c128  mov     r9, rax; cchToCopy
0x18000c12b  mov     r8, [rbx+10h]; pszSrc
0x18000c12f  lea     rdi, [r14+228h]
0x18000c136  mov     rcx, rdi; pszDest
0x18000c139  mov     edx, 28h ; '('; cchDest
0x18000c13e  call    StringCchCopyNA
0x18000c143  test    cs:byte_18002D803, 10h
0x18000c14a  jz      short loc_18000C184
0x18000c14c  mov     r8, rdi
0x18000c14f  mov     word ptr [rbp+810h+var_840], r13w
0x18000c154  lea     rdx, aCorrelationIdI; "Correlation Id is %hs"
0x18000c15b  lea     rcx, [rbp+810h+var_840]
0x18000c15f  call    FormatRRASErrorString
0x18000c164  test    cs:byte_18002D803, 10h
0x18000c16b  jz      short loc_18000C184
0x18000c16d  lea     r8, [rbp+810h+var_840]
0x18000c171  lea     rdx, RasSSTPSvcTraceInfo
0x18000c178  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c17f  call    McTemplateU0z_EventWriteTransfer
0x18000c184  mov     rdx, r12
0x18000c187  inc     rdx; cchDest
0x18000c18a  cmp     [rdi+rdx], r13b
0x18000c18e  jnz     short loc_18000C187
0x18000c190  test    rdx, rdx
0x18000c193  jz      short loc_18000C1B9
0x18000c195  cmp     rdx, 7FFFFFFFh
0x18000c19c  jbe     short loc_18000C1A4
0x18000c19e  mov     [rbp+810h+var_868], r13b
0x18000c1a2  jmp     short loc_18000C1B9
0x18000c1a4  mov     r9, rdi; pszSrc
0x18000c1a7  mov     [rsp+910h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000c1b0  lea     rcx, [rbp+810h+var_868]; pszDest
0x18000c1b4  call    StringCopyWorkerA
0x18000c1b9  lea     r13, [r14+250h]
0x18000c1c0  mov     rdx, r13; Uuid
0x18000c1c3  lea     rcx, [rbp+810h+var_868+1]; StringUuid
0x18000c1c7  call    cs:__imp_UuidFromStringA
0x18000c1cd  xor     ecx, ecx
0x18000c1cf  test    eax, eax
0x18000c1d1  jz      short loc_18000C1FF
0x18000c1d3  test    cs:byte_18002D803, 10h
0x18000c1da  jz      loc_18000C2BE
0x18000c1e0  lea     r8, aCouldNotConver; "Could not convert correlation ID from s"...
0x18000c1e7  lea     rdx, RasSSTPSvcTraceInfo
0x18000c1ee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c1f5  call    McTemplateU0z_EventWriteTransfer
0x18000c1fa  jmp     loc_18000C2BE
0x18000c1ff  test    cs:byte_18002D803, 10h
0x18000c206  jz      loc_18000C2BE
0x18000c20c  movzx   edx, byte ptr [r14+25Dh]
0x18000c214  movzx   r8d, byte ptr [r14+25Ch]
0x18000c21c  movzx   eax, byte ptr [r14+25Fh]
0x18000c224  movzx   r10d, byte ptr [r14+25Bh]
0x18000c22c  movzx   r11d, byte ptr [r14+25Ah]
0x18000c234  movzx   ebx, byte ptr [r14+259h]
0x18000c23c  movzx   edi, byte ptr [r14+258h]
0x18000c244  movzx   esi, word ptr [r14+256h]
0x18000c24c  movzx   r9d, word ptr [r14+254h]
0x18000c254  mov     dword ptr [rsp+910h+var_8B0], eax
0x18000c258  mov     word ptr [rbp+810h+var_840], cx
0x18000c25c  movzx   ecx, byte ptr [r14+25Eh]
0x18000c264  mov     dword ptr [rsp+910h+var_8B8], ecx
0x18000c268  lea     rcx, [rbp+810h+var_840]
0x18000c26c  mov     dword ptr [rsp+910h+var_8C0], edx
0x18000c270  lea     rdx, aCorrelationGui; "Correlation Guid is {%08X-%04X-%04X-%02"...
0x18000c277  mov     dword ptr [rsp+910h+var_8C8], r8d
0x18000c27c  mov     r8d, [r13+0]
0x18000c280  mov     dword ptr [rsp+910h+var_8D0], r10d
0x18000c285  mov     dword ptr [rsp+910h+lpUsedDefaultChar], r11d
0x18000c28a  mov     dword ptr [rsp+910h+lpDefaultChar], ebx
0x18000c28e  mov     [rsp+910h+cbMultiByte], edi
0x18000c292  mov     dword ptr [rsp+910h+cchToCopy], esi
0x18000c296  call    FormatRRASErrorString
0x18000c29b  test    cs:byte_18002D803, 10h
0x18000c2a2  jz      short loc_18000C2BB
0x18000c2a4  lea     r8, [rbp+810h+var_840]
0x18000c2a8  lea     rdx, RasSSTPSvcTraceInfo
0x18000c2af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c2b6  call    McTemplateU0z_EventWriteTransfer
0x18000c2bb  mov     esi, dword ptr [rbp+810h+MultiByteStr]
0x18000c2be  mov     edi, 1
0x18000c2c3  xor     r13d, r13d
0x18000c2c6  jmp     short loc_18000C31C
0x18000c2c8  test    cs:byte_18002D803, 10h
0x18000c2cf  jz      short loc_18000C31C
0x18000c2d1  lea     r8, [rbp+810h+pszDest]
0x18000c2d5  mov     word ptr [rbp+810h+var_840], r13w
0x18000c2da  lea     rdx, aCorrelationidh; "CorrelationIdHeaderName = %hs; does not"...
0x18000c2e1  lea     rcx, [rbp+810h+var_840]
0x18000c2e5  call    FormatRRASErrorString
0x18000c2ea  test    cs:byte_18002D803, 10h
0x18000c2f1  jz      short loc_18000C31C
0x18000c2f3  lea     r8, [rbp+810h+var_840]
0x18000c2f7  jmp     short loc_18000C309
0x18000c2f9  test    cs:byte_18002D803, 10h
0x18000c300  jz      short loc_18000C321
0x18000c302  lea     r8, aHttprequestHea; "(HttpRequest->Headers).pUnknownHeaders "...
0x18000c309  lea     rdx, RasSSTPSvcTraceInfo
0x18000c310  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c317  call    McTemplateU0z_EventWriteTransfer
0x18000c31c  mov     edx, 13h
0x18000c321  inc     esi
0x18000c323  mov     dword ptr [rbp+810h+MultiByteStr], esi
0x18000c326  jmp     loc_18000C079
0x18000c32b  test    edi, edi
0x18000c32d  jnz     loc_18000C46F
0x18000c333  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c33a  lea     rsi, RasSSTPSvcTraceInfo
0x18000c341  test    cs:byte_18002D803, 10h
0x18000c348  xorps   xmm0, xmm0
0x18000c34b  xorps   xmm1, xmm1
0x18000c34e  mov     qword ptr [rbp+810h+MultiByteStr], r13
0x18000c352  movups  xmmword ptr [rsp+910h+Uuid.Data1], xmm0
0x18000c357  movups  xmmword ptr [rbp+810h+pszDest], xmm1
0x18000c35b  jz      short loc_18000C36F
0x18000c35d  lea     r8, aDidNotReceiveC; "Did not receive correlation ID from pee"...
0x18000c364  mov     rdx, rsi
0x18000c367  mov     rcx, rdi
0x18000c36a  call    McTemplateU0z_EventWriteTransfer
0x18000c36f  xor     ecx, ecx; lpModuleName
0x18000c371  call    cs:__imp_GetModuleHandleW
0x18000c377  mov     r9d, 8; cchBufferMax
0x18000c37d  lea     r8, [rbp+810h+pszDest]; lpBuffer
0x18000c381  mov     rcx, rax; hInstance
0x18000c384  mov     edx, 88BCh; uID
0x18000c389  call    cs:__imp_LoadStringW
0x18000c38f  mov     [rsp+910h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000c394  lea     rax, [rbp+810h+MultiByteStr]
0x18000c398  mov     [rsp+910h+lpDefaultChar], r13; lpDefaultChar
0x18000c39d  lea     r8, [rbp+810h+pszDest]; lpWideCharStr
0x18000c3a1  mov     [rsp+910h+cbMultiByte], 8; cbMultiByte
0x18000c3a9  mov     r9d, r12d; cchWideChar
0x18000c3ac  mov     edx, 400h; dwFlags
0x18000c3b1  mov     [rsp+910h+cchToCopy], rax; lpMultiByteStr
0x18000c3b6  xor     ecx, ecx; CodePage
0x18000c3b8  call    cs:__imp_WideCharToMultiByte
0x18000c3be  lea     rcx, [rsp+910h+Uuid]; Uuid
0x18000c3c3  call    cs:__imp_UuidCreate
0x18000c3c9  test    eax, eax
0x18000c3cb  jz      short loc_18000C414
0x18000c3cd  cmp     eax, 720h
0x18000c3d2  jz      short loc_18000C414
0x18000c3d4  test    cs:byte_18002D803, 10h
0x18000c3db  jz      short loc_18000C3EF
0x18000c3dd  lea     r8, aGenerationOfCo; "Generation of correlation ID on server "...
0x18000c3e4  mov     rdx, rsi
0x18000c3e7  mov     rcx, rdi
0x18000c3ea  call    McTemplateU0z_EventWriteTransfer
0x18000c3ef  lea     rax, [rbp+810h+MultiByteStr]
0x18000c3f3  inc     r12
0x18000c3f6  cmp     [rax+r12], r13b
0x18000c3fa  jnz     short loc_18000C3F3
0x18000c3fc  lea     rcx, [r14+228h]; pszDest
0x18000c403  mov     r9, r12; cchToCopy
0x18000c406  lea     r8, [rbp+810h+MultiByteStr]; pszSrc
0x18000c40a  mov     edx, 28h ; '('; cchDest
0x18000c40f  call    StringCchCopyNA
0x18000c414  lea     rbx, [r14+228h]
0x18000c41b  mov     rcx, rbx; pszDest
0x18000c41e  lea     r8, [rsp+910h+Uuid]
0x18000c423  call    PrintGuid
0x18000c428  movups  xmm0, xmmword ptr [rsp+910h+Uuid.Data1]
0x18000c42d  movdqu  xmmword ptr [r14+250h], xmm0
0x18000c436  test    cs:byte_18002D803, 10h
0x18000c43d  jz      short loc_18000C46F
0x18000c43f  mov     r8, rbx
0x18000c442  mov     word ptr [rbp+810h+var_840], r13w
0x18000c447  lea     rdx, aCorrelationIdT; "Correlation ID that will be used in the"...
0x18000c44e  lea     rcx, [rbp+810h+var_840]
0x18000c452  call    FormatRRASErrorString
0x18000c457  test    cs:byte_18002D803, 10h
0x18000c45e  jz      short loc_18000C46F
0x18000c460  lea     r8, [rbp+810h+var_840]
0x18000c464  mov     rdx, rsi
0x18000c467  mov     rcx, rdi
0x18000c46a  call    McTemplateU0z_EventWriteTransfer
0x18000c46f  movzx   eax, word ptr [r15+228h]
0x18000c477  add     eax, 0C1h
0x18000c47c  mov     dword ptr [rbp+810h+MultiByteStr], eax
0x18000c47f  mov     ebx, eax
0x18000c481  call    cs:__imp_GetProcessHeap
0x18000c487  mov     r8d, ebx; dwBytes
0x18000c48a  mov     edx, 8; dwFlags
0x18000c48f  mov     rcx, rax; hHeap
0x18000c492  call    cs:__imp_HeapAlloc
0x18000c498  mov     rbx, rax
0x18000c49b  test    rax, rax
0x18000c49e  jnz     short loc_18000C4F9
0x18000c4a0  test    cs:byte_18002D803, 8
0x18000c4a7  mov     esi, 0C0000017h
0x18000c4ac  jz      short loc_18000C4ED
0x18000c4ae  lea     r8, [r14+228h]
0x18000c4b5  mov     word ptr [rbp+810h+var_840], r13w
0x18000c4ba  mov     r9d, esi
0x18000c4bd  lea     rdx, aCoidHsErrorAll; "CoId=%hs:Error allocating call info - %"...
  ... truncated ...
```
