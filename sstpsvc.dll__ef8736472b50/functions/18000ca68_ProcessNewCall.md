# ProcessNewCall

- ea: `0x18000ca68`
- end: `0x18000d2e3`
- name: `ProcessNewCall`
- size: `2171`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000afb0`

## callees

- `0x180002aac`
- `0x180002f50`
- `0x180005110`
- `0x1800089dc`
- `0x180008b90`
- `0x18000ca68`
- `0x18000d694`
- `0x18000d6e0`
- `0x18000faa0`
- `0x18001d1c2`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000cbd4`
- `msvcrt!_stricmp` at `0x18000cbd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d205`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d253`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d205`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d253`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d21c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d21c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d244`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d244`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d230`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfbc`
- `RPCRT4!UuidCreate` at `0x18000cee1`
- `RPCRT4!UuidCreate` at `0x18000cee1`
- `RPCRT4!UuidFromStringA` at `0x18000cccd`
- `RPCRT4!UuidFromStringA` at `0x18000cccd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ce9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ce9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce7d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ced0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ced0`
- `prxyqry!GetLinkSpeedForAddress` at `0x18000d0e0`
- `prxyqry!GetLinkSpeedForAddress` at `0x18000d0e0`

## string_xrefs

- `0x18000d102`: `CoId=%hs:GetLinkSpeedForAddr completes with %d [Tx: %I64u][Rx: %I64u]`

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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    FormatRRASErrorString(&v55, L"Entering %ws", L"ProcessNewCall");
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
      if ( (byte_18002E903 & 0x10) != 0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(&v55, L"CallContext: %p has a new call associated", a1);
        if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 0x10) != 0 )
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
      if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"Correlation ID that will be used in the server logs is %hs", a1 + 552);
      if ( (byte_18002E903 & 0x10) != 0 )
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
      if ( (byte_18002E903 & 0x10) == 0 )
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
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasSSTPSvcTraceInfo,
          L"Received correlation ID from peer");
      if ( v8[1] >= 0x27u )
        v11 = 39;
      else
        v11 = v8[1];
      StringCchCopyNA((STRSAFE_LPSTR)(a1 + 552), 0x28u, *((STRSAFE_PCNZCH *)v8 + 2), v11);
      if ( (byte_18002E903 & 0x10) != 0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(&v55, L"Correlation Id is %hs", a1 + 552);
        if ( (byte_18002E903 & 0x10) != 0 )
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
        if ( (byte_18002E903 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasSSTPSvcTraceInfo,
            L"Could not convert correlation ID from string to GUID to store in call context");
      }
      else if ( (byte_18002E903 & 0x10) != 0 )
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
        if ( (byte_18002E903 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
        i = *(_DWORD *)MultiByteStr;
      }
      v6 = 1;
    }
    else if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"CorrelationIdHeaderName = %hs; does not match what we want", pszDest);
      if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(
        &v55,
        L"CoId=%hs:GetLinkSpeedForAddr completes with %d [Tx: %I64u][Rx: %I64u]",
        a1 + 552,
        LinkSpeedForAddress,
        *v34,
        *v33);
      if ( (byte_18002E903 & 8) != 0 )
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
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"CoId=%hs:Error allocating call info - %d", a1 + 552, 3221225495LL);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v55);
    }
    v30 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
LABEL_68:
    EnterCriticalSection(v30);
    *(_DWORD *)(a1 + 268) = v29;
    result = InitiateCallContextCleanup(a1, 2);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v55) = 0;
    result = FormatRRASErrorString(&v55, L"LEaving %ws", L"ProcessNewCall");
    if ( (byte_18002E903 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v55);
  }
  return result;
}

```

## disassembly

```asm
0x18000ca68  mov     [rsp-8+arg_8], rbx
0x18000ca6d  push    rbp
0x18000ca6e  push    rsi
0x18000ca6f  push    rdi
0x18000ca70  push    r12
0x18000ca72  push    r13
0x18000ca74  push    r14
0x18000ca76  push    r15
0x18000ca78  lea     rbp, [rsp-7E0h]
0x18000ca80  sub     rsp, 8E0h
0x18000ca87  mov     rax, cs:__security_cookie
0x18000ca8e  xor     rax, rsp
0x18000ca91  mov     [rbp+810h+var_40], rax
0x18000ca98  mov     r15, r8
0x18000ca9b  mov     r14, rcx
0x18000ca9e  xor     r13d, r13d
0x18000caa1  lea     rcx, [rbp+810h+var_83C]; void *
0x18000caa5  mov     r8d, 7FCh; Size
0x18000caab  mov     [rbp+810h+var_840], r13d
0x18000caaf  xor     edx, edx; Val
0x18000cab1  call    memset_0
0x18000cab6  mov     al, cs:byte_18002E903
0x18000cabc  lea     rsi, RasSSTPSvcTraceInfo
0x18000cac3  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000caca  test    al, 10h
0x18000cacc  jz      short loc_18000CB3D
0x18000cace  lea     r8, aProcessnewcall; "ProcessNewCall"
0x18000cad5  mov     word ptr [rbp+810h+var_840], r13w
0x18000cada  lea     rdx, aEnteringWs; "Entering %ws"
0x18000cae1  lea     rcx, [rbp+810h+var_840]
0x18000cae5  call    FormatRRASErrorString
0x18000caea  mov     al, cs:byte_18002E903
0x18000caf0  test    al, 10h
0x18000caf2  jz      short loc_18000CB3D
0x18000caf4  lea     r8, [rbp+810h+var_840]
0x18000caf8  mov     rdx, rsi
0x18000cafb  mov     rcx, rdi
0x18000cafe  call    McTemplateU0z_EventWriteTransfer
0x18000cb03  mov     al, cs:byte_18002E903
0x18000cb09  test    al, 10h
0x18000cb0b  jz      short loc_18000CB3D
0x18000cb0d  mov     r8, r14
0x18000cb10  mov     word ptr [rbp+810h+var_840], r13w
0x18000cb15  lea     rdx, aCallcontextPHa; "CallContext: %p has a new call associat"...
0x18000cb1c  lea     rcx, [rbp+810h+var_840]
0x18000cb20  call    FormatRRASErrorString
0x18000cb25  test    cs:byte_18002E903, 10h
0x18000cb2c  jz      short loc_18000CB3D
0x18000cb2e  lea     r8, [rbp+810h+var_840]
0x18000cb32  mov     rdx, rsi
0x18000cb35  mov     rcx, rdi
0x18000cb38  call    McTemplateU0z_EventWriteTransfer
0x18000cb3d  mov     rax, [r15+8]
0x18000cb41  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000cb45  mov     [r14+118h], rax
0x18000cb4c  mov     rax, [r15+10h]
0x18000cb50  mov     [r14+110h], rax
0x18000cb57  mov     byte ptr [r14+108h], 1
0x18000cb5f  cmp     [r15+78h], r13w
0x18000cb64  jz      loc_18000CE4D
0x18000cb6a  mov     edi, r13d
0x18000cb6d  mov     dword ptr [rbp+810h+MultiByteStr], r13d
0x18000cb71  mov     esi, r13d
0x18000cb74  lea     edx, [r12+14h]
0x18000cb79  movzx   eax, word ptr [r15+78h]
0x18000cb7e  cmp     esi, eax
0x18000cb80  jnb     loc_18000CE37
0x18000cb86  mov     eax, esi
0x18000cb88  lea     rcx, [rax+rax*2]
0x18000cb8c  mov     rax, [r15+80h]
0x18000cb93  lea     rbx, [rax+rcx*8]
0x18000cb97  test    rbx, rbx
0x18000cb9a  jz      loc_18000CE05
0x18000cba0  mov     r8, [rbx+8]; pszSrc
0x18000cba4  test    r8, r8
0x18000cba7  jz      loc_18000CE2D
0x18000cbad  cmp     [rbx], dx
0x18000cbb0  jnb     short loc_18000CBB8
0x18000cbb2  movzx   r9d, word ptr [rbx]
0x18000cbb6  jmp     short loc_18000CBBB
0x18000cbb8  mov     r9, rdx; cchToCopy
0x18000cbbb  mov     edx, 14h; cchDest
0x18000cbc0  lea     rcx, [rbp+810h+pszDest]; pszDest
0x18000cbc4  call    StringCchCopyNA
0x18000cbc9  lea     rdx, String2; "SSTPCORRELATIONID"
0x18000cbd0  lea     rcx, [rbp+810h+pszDest]; String1
0x18000cbd4  call    cs:__imp__stricmp
0x18000cbdb  nop     dword ptr [rax+rax+00h]
0x18000cbe0  test    eax, eax
0x18000cbe2  jnz     loc_18000CDD4
0x18000cbe8  xor     eax, eax
0x18000cbea  xorps   xmm0, xmm0
0x18000cbed  test    cs:byte_18002E903, 10h
0x18000cbf4  movups  xmmword ptr [rbp+810h+var_868], xmm0
0x18000cbf8  mov     [rbp+810h+var_848], rax
0x18000cbfc  movups  [rbp+810h+var_858], xmm0
0x18000cc00  jz      short loc_18000CC1C
0x18000cc02  lea     r8, aReceivedCorrel; "Received correlation ID from peer"
0x18000cc09  lea     rdx, RasSSTPSvcTraceInfo
0x18000cc10  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cc17  call    McTemplateU0z_EventWriteTransfer
0x18000cc1c  mov     eax, 27h ; '''
0x18000cc21  cmp     [rbx+2], ax
0x18000cc25  jnb     short loc_18000CC2E
0x18000cc27  movzx   r9d, word ptr [rbx+2]
0x18000cc2c  jmp     short loc_18000CC31
0x18000cc2e  mov     r9, rax; cchToCopy
0x18000cc31  mov     r8, [rbx+10h]; pszSrc
0x18000cc35  lea     rdi, [r14+228h]
0x18000cc3c  mov     rcx, rdi; pszDest
0x18000cc3f  mov     edx, 28h ; '('; cchDest
0x18000cc44  call    StringCchCopyNA
0x18000cc49  test    cs:byte_18002E903, 10h
0x18000cc50  jz      short loc_18000CC8A
0x18000cc52  mov     r8, rdi
0x18000cc55  mov     word ptr [rbp+810h+var_840], r13w
0x18000cc5a  lea     rdx, aCorrelationIdI; "Correlation Id is %hs"
0x18000cc61  lea     rcx, [rbp+810h+var_840]
0x18000cc65  call    FormatRRASErrorString
0x18000cc6a  test    cs:byte_18002E903, 10h
0x18000cc71  jz      short loc_18000CC8A
0x18000cc73  lea     r8, [rbp+810h+var_840]
0x18000cc77  lea     rdx, RasSSTPSvcTraceInfo
0x18000cc7e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cc85  call    McTemplateU0z_EventWriteTransfer
0x18000cc8a  mov     rdx, r12
0x18000cc8d  inc     rdx; cchDest
0x18000cc90  cmp     [rdi+rdx], r13b
0x18000cc94  jnz     short loc_18000CC8D
0x18000cc96  test    rdx, rdx
0x18000cc99  jz      short loc_18000CCBF
0x18000cc9b  cmp     rdx, 7FFFFFFFh
0x18000cca2  jbe     short loc_18000CCAA
0x18000cca4  mov     [rbp+810h+var_868], r13b
0x18000cca8  jmp     short loc_18000CCBF
0x18000ccaa  mov     r9, rdi; pszSrc
0x18000ccad  mov     [rsp+910h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000ccb6  lea     rcx, [rbp+810h+var_868]; pszDest
0x18000ccba  call    StringCopyWorkerA
0x18000ccbf  lea     r13, [r14+250h]
0x18000ccc6  mov     rdx, r13; Uuid
0x18000ccc9  lea     rcx, [rbp+810h+var_868+1]; StringUuid
0x18000cccd  call    cs:__imp_UuidFromStringA
0x18000ccd4  nop     dword ptr [rax+rax+00h]
0x18000ccd9  xor     ecx, ecx
0x18000ccdb  test    eax, eax
0x18000ccdd  jz      short loc_18000CD0B
0x18000ccdf  test    cs:byte_18002E903, 10h
0x18000cce6  jz      loc_18000CDCA
0x18000ccec  lea     r8, aCouldNotConver; "Could not convert correlation ID from s"...
0x18000ccf3  lea     rdx, RasSSTPSvcTraceInfo
0x18000ccfa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cd01  call    McTemplateU0z_EventWriteTransfer
0x18000cd06  jmp     loc_18000CDCA
0x18000cd0b  test    cs:byte_18002E903, 10h
0x18000cd12  jz      loc_18000CDCA
0x18000cd18  movzx   edx, byte ptr [r14+25Dh]
0x18000cd20  movzx   r8d, byte ptr [r14+25Ch]
0x18000cd28  movzx   eax, byte ptr [r14+25Fh]
0x18000cd30  movzx   r10d, byte ptr [r14+25Bh]
0x18000cd38  movzx   r11d, byte ptr [r14+25Ah]
0x18000cd40  movzx   ebx, byte ptr [r14+259h]
0x18000cd48  movzx   edi, byte ptr [r14+258h]
0x18000cd50  movzx   esi, word ptr [r14+256h]
0x18000cd58  movzx   r9d, word ptr [r14+254h]
0x18000cd60  mov     dword ptr [rsp+910h+var_8B0], eax
0x18000cd64  mov     word ptr [rbp+810h+var_840], cx
0x18000cd68  movzx   ecx, byte ptr [r14+25Eh]
0x18000cd70  mov     dword ptr [rsp+910h+var_8B8], ecx
0x18000cd74  lea     rcx, [rbp+810h+var_840]
0x18000cd78  mov     dword ptr [rsp+910h+var_8C0], edx
0x18000cd7c  lea     rdx, aCorrelationGui; "Correlation Guid is {%08X-%04X-%04X-%02"...
0x18000cd83  mov     dword ptr [rsp+910h+var_8C8], r8d
0x18000cd88  mov     r8d, [r13+0]
0x18000cd8c  mov     dword ptr [rsp+910h+var_8D0], r10d
0x18000cd91  mov     dword ptr [rsp+910h+lpUsedDefaultChar], r11d
0x18000cd96  mov     dword ptr [rsp+910h+lpDefaultChar], ebx
0x18000cd9a  mov     [rsp+910h+cbMultiByte], edi
0x18000cd9e  mov     dword ptr [rsp+910h+cchToCopy], esi
0x18000cda2  call    FormatRRASErrorString
0x18000cda7  test    cs:byte_18002E903, 10h
0x18000cdae  jz      short loc_18000CDC7
0x18000cdb0  lea     r8, [rbp+810h+var_840]
0x18000cdb4  lea     rdx, RasSSTPSvcTraceInfo
0x18000cdbb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cdc2  call    McTemplateU0z_EventWriteTransfer
0x18000cdc7  mov     esi, dword ptr [rbp+810h+MultiByteStr]
0x18000cdca  mov     edi, 1
0x18000cdcf  xor     r13d, r13d
0x18000cdd2  jmp     short loc_18000CE28
0x18000cdd4  test    cs:byte_18002E903, 10h
0x18000cddb  jz      short loc_18000CE28
0x18000cddd  lea     r8, [rbp+810h+pszDest]
0x18000cde1  mov     word ptr [rbp+810h+var_840], r13w
0x18000cde6  lea     rdx, aCorrelationidh; "CorrelationIdHeaderName = %hs; does not"...
0x18000cded  lea     rcx, [rbp+810h+var_840]
0x18000cdf1  call    FormatRRASErrorString
0x18000cdf6  test    cs:byte_18002E903, 10h
0x18000cdfd  jz      short loc_18000CE28
0x18000cdff  lea     r8, [rbp+810h+var_840]
0x18000ce03  jmp     short loc_18000CE15
0x18000ce05  test    cs:byte_18002E903, 10h
0x18000ce0c  jz      short loc_18000CE2D
0x18000ce0e  lea     r8, aHttprequestHea; "(HttpRequest->Headers).pUnknownHeaders "...
0x18000ce15  lea     rdx, RasSSTPSvcTraceInfo
0x18000ce1c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ce23  call    McTemplateU0z_EventWriteTransfer
0x18000ce28  mov     edx, 13h
0x18000ce2d  inc     esi
0x18000ce2f  mov     dword ptr [rbp+810h+MultiByteStr], esi
0x18000ce32  jmp     loc_18000CB79
0x18000ce37  test    edi, edi
0x18000ce39  jnz     loc_18000CF93
0x18000ce3f  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ce46  lea     rsi, RasSSTPSvcTraceInfo
0x18000ce4d  test    cs:byte_18002E903, 10h
0x18000ce54  xorps   xmm0, xmm0
0x18000ce57  xorps   xmm1, xmm1
0x18000ce5a  mov     qword ptr [rbp+810h+MultiByteStr], r13
0x18000ce5e  movups  xmmword ptr [rsp+910h+Uuid.Data1], xmm0
0x18000ce63  movups  xmmword ptr [rbp+810h+pszDest], xmm1
0x18000ce67  jz      short loc_18000CE7B
0x18000ce69  lea     r8, aDidNotReceiveC; "Did not receive correlation ID from pee"...
0x18000ce70  mov     rdx, rsi
0x18000ce73  mov     rcx, rdi
0x18000ce76  call    McTemplateU0z_EventWriteTransfer
0x18000ce7b  xor     ecx, ecx; lpModuleName
0x18000ce7d  call    cs:__imp_GetModuleHandleW
0x18000ce84  nop     dword ptr [rax+rax+00h]
0x18000ce89  mov     r9d, 8; cchBufferMax
0x18000ce8f  lea     r8, [rbp+810h+pszDest]; lpBuffer
0x18000ce93  mov     rcx, rax; hInstance
0x18000ce96  mov     edx, 88BCh; uID
0x18000ce9b  call    cs:__imp_LoadStringW
0x18000cea2  nop     dword ptr [rax+rax+00h]
0x18000cea7  mov     [rsp+910h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000ceac  lea     rax, [rbp+810h+MultiByteStr]
0x18000ceb0  mov     [rsp+910h+lpDefaultChar], r13; lpDefaultChar
0x18000ceb5  lea     r8, [rbp+810h+pszDest]; lpWideCharStr
0x18000ceb9  mov     [rsp+910h+cbMultiByte], 8; cbMultiByte
0x18000cec1  mov     r9d, r12d; cchWideChar
0x18000cec4  mov     edx, 400h; dwFlags
0x18000cec9  mov     [rsp+910h+cchToCopy], rax; lpMultiByteStr
0x18000cece  xor     ecx, ecx; CodePage
0x18000ced0  call    cs:__imp_WideCharToMultiByte
0x18000ced7  nop     dword ptr [rax+rax+00h]
0x18000cedc  lea     rcx, [rsp+910h+Uuid]; Uuid
0x18000cee1  call    cs:__imp_UuidCreate
0x18000cee8  nop     dword ptr [rax+rax+00h]
0x18000ceed  test    eax, eax
0x18000ceef  jz      short loc_18000CF38
0x18000cef1  cmp     eax, 720h
0x18000cef6  jz      short loc_18000CF38
0x18000cef8  test    cs:byte_18002E903, 10h
0x18000ceff  jz      short loc_18000CF13
0x18000cf01  lea     r8, aGenerationOfCo; "Generation of correlation ID on server "...
0x18000cf08  mov     rdx, rsi
0x18000cf0b  mov     rcx, rdi
0x18000cf0e  call    McTemplateU0z_EventWriteTransfer
0x18000cf13  lea     rax, [rbp+810h+MultiByteStr]
0x18000cf17  inc     r12
0x18000cf1a  cmp     [rax+r12], r13b
0x18000cf1e  jnz     short loc_18000CF17
0x18000cf20  lea     rcx, [r14+228h]; pszDest
0x18000cf27  mov     r9, r12; cchToCopy
0x18000cf2a  lea     r8, [rbp+810h+MultiByteStr]; pszSrc
0x18000cf2e  mov     edx, 28h ; '('; cchDest
0x18000cf33  call    StringCchCopyNA
0x18000cf38  lea     rbx, [r14+228h]
0x18000cf3f  mov     rcx, rbx; pszDest
0x18000cf42  lea     r8, [rsp+910h+Uuid]
0x18000cf47  call    PrintGuid
0x18000cf4c  movups  xmm0, xmmword ptr [rsp+910h+Uuid.Data1]
0x18000cf51  movdqu  xmmword ptr [r14+250h], xmm0
0x18000cf5a  test    cs:byte_18002E903, 10h
0x18000cf61  jz      short loc_18000CF93
0x18000cf63  mov     r8, rbx
0x18000cf66  mov     word ptr [rbp+810h+var_840], r13w
0x18000cf6b  lea     rdx, aCorrelationIdT; "Correlation ID that will be used in the"...
0x18000cf72  lea     rcx, [rbp+810h+var_840]
0x18000cf76  call    FormatRRASErrorString
0x18000cf7b  test    cs:byte_18002E903, 10h
0x18000cf82  jz      short loc_18000CF93
0x18000cf84  lea     r8, [rbp+810h+var_840]
0x18000cf88  mov     rdx, rsi
0x18000cf8b  mov     rcx, rdi
0x18000cf8e  call    McTemplateU0z_EventWriteTransfer
0x18000cf93  movzx   eax, word ptr [r15+228h]
0x18000cf9b  add     eax, 0C1h
0x18000cfa0  mov     dword ptr [rbp+810h+MultiByteStr], eax
0x18000cfa3  mov     ebx, eax
0x18000cfa5  call    cs:__imp_GetProcessHeap
0x18000cfac  nop     dword ptr [rax+rax+00h]
0x18000cfb1  mov     r8d, ebx; dwBytes
0x18000cfb4  mov     edx, 8; dwFlags
0x18000cfb9  mov     rcx, rax; hHeap
0x18000cfbc  call    cs:__imp_HeapAlloc
0x18000cfc3  nop     dword ptr [rax+rax+00h]
0x18000cfc8  mov     rbx, rax
0x18000cfcb  test    rax, rax
  ... truncated ...
```
