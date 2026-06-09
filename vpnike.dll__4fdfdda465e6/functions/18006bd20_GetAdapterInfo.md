# GetAdapterInfo

- ea: `0x18006bd20`
- end: `0x18006c426`
- name: `GetAdapterInfo`
- size: `1798`
- prototype: `__int64 __fastcall(ULONG IfIndex, NET_IF_COMPARTMENT_ID CompartmentId)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180070034`

## callees

- `0x180069a8c`
- `0x18006bd20`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bed8`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18006c1a5`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18006c206`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18006c1a5`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18006c206`
- `IPHLPAPI!GetAdaptersInfo` at `0x18006be7e`
- `IPHLPAPI!GetAdaptersInfo` at `0x18006bfc0`
- `IPHLPAPI!GetAdaptersInfo` at `0x18006be7e`
- `IPHLPAPI!GetAdaptersInfo` at `0x18006bfc0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006be4e`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006be4e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006be5a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006bf76`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006be5a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006bf76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bec6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c1e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bec6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c1e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bf5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bf65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bf5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bf65`
- `WS2_32!__imp_htonl` at `0x18006c091`
- `WS2_32!__imp_htonl` at `0x18006c111`
- `WS2_32!__imp_htonl` at `0x18006c255`
- `WS2_32!__imp_htonl` at `0x18006c2ed`
- `WS2_32!__imp_htonl` at `0x18006c091`
- `WS2_32!__imp_htonl` at `0x18006c111`
- `WS2_32!__imp_htonl` at `0x18006c255`
- `WS2_32!__imp_htonl` at `0x18006c2ed`
- `WS2_32!__imp_inet_addr` at `0x18006c04f`
- `WS2_32!__imp_inet_addr` at `0x18006c05e`
- `WS2_32!__imp_inet_addr` at `0x18006c074`
- `WS2_32!__imp_inet_addr` at `0x18006c083`
- `WS2_32!__imp_inet_addr` at `0x18006c244`
- `WS2_32!__imp_inet_addr` at `0x18006c2e2`
- `WS2_32!__imp_inet_addr` at `0x18006c04f`
- `WS2_32!__imp_inet_addr` at `0x18006c05e`
- `WS2_32!__imp_inet_addr` at `0x18006c074`
- `WS2_32!__imp_inet_addr` at `0x18006c083`
- `WS2_32!__imp_inet_addr` at `0x18006c244`
- `WS2_32!__imp_inet_addr` at `0x18006c2e2`

## string_xrefs

- `0x18006c3be`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18006c413`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetAdapterInfo(ULONG IfIndex, NET_IF_COMPARTMENT_ID CompartmentId, unsigned int *a3)
{
  unsigned int v3; // r14d
  struct _IP_ADAPTER_INFO *v6; // r12
  IP_PER_ADAPTER_INFO_W2KSP1 *v7; // r13
  unsigned int v8; // esi
  __int64 v9; // rdx
  unsigned int RoutingDomainIdForCompartment; // edi
  ULONG AdaptersInfo; // eax
  const wchar_t *v12; // rdx
  const CHAR *v13; // rcx
  struct _IP_ADAPTER_INFO *v14; // rax
  DWORD PerAdapterInfo; // eax
  const wchar_t *v16; // rdx
  const CHAR *v18; // rcx
  struct _IP_ADAPTER_INFO *v19; // rbx
  __int64 v20; // rdx
  const wchar_t *v21; // r8
  const CHAR *v22; // rcx
  unsigned int v23; // edi
  IP_PER_ADAPTER_INFO_W2KSP1 *v24; // rax
  unsigned int v25; // ebx
  struct _IP_ADDR_STRING *Next; // rcx
  unsigned int v27; // ebx
  ULONG SizePointer; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+44h] [rbp-BCh]
  NET_IF_COMPARTMENT_ID CompartmentIda; // [rsp+48h] [rbp-B8h]
  unsigned int *v31; // [rsp+50h] [rbp-B0h]
  _OWORD v32[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+7Ch] [rbp-84h]
  __int128 v35; // [rsp+8Ch] [rbp-74h]
  int v36; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+A0h] [rbp-60h] BYREF
  char v38[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = 0;
  v31 = a3;
  SizePointer = 0;
  v29 = 0;
  v37 = 0;
  memset(v32, 0, sizeof(v32));
  v6 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v38, 0, sizeof(v38));
  v33 = 0;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  if ( CompartmentId != 1 && unk_1800AB320 || xmmword_1800AB328 != 0 || (v9 = unk_1800AB338) != 0 )
  {
    CompartmentIda = 1;
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(CompartmentId, v32);
    if ( RoutingDomainIdForCompartment )
      goto LABEL_23;
    v9 = unk_1800AB338;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v9 )
    {
      LOWORD(v33) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v9,
        L"GetAdapterInfo",
        v32,
        0,
        &v33);
    }
  }
  else
  {
    TraceHlp("GetAdapterInfo");
  }
  CompartmentIda = GetCurrentThreadCompartmentId();
  AdaptersInfo = SetCurrentThreadCompartmentId(CompartmentId);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        v12 = L"GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
        goto LABEL_85;
      }
      goto LABEL_24;
    }
    v13 = "GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_87;
  }
  v29 = 1;
  SizePointer = 0;
  AdaptersInfo = GetAdaptersInfo(0, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo != 111 && AdaptersInfo )
    goto LABEL_14;
  v14 = (struct _IP_ADAPTER_INFO *)LocalAlloc(0x40u, SizePointer);
  v6 = v14;
  if ( !v14 )
    goto LABEL_19;
  AdaptersInfo = GetAdaptersInfo(v14, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
LABEL_14:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        v12 = L"GetAdaptersInfo failed and returned %d";
LABEL_85:
        LOWORD(v33) = 0;
        LOWORD(v37) = 0;
        FormatRRASErrorString(&v37, v12, AdaptersInfo);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v37,
          v32,
          0,
          &v33);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    v13 = "GetAdaptersInfo failed and returned %d";
    goto LABEL_87;
  }
  v19 = v6;
  while ( v19->Index != IfIndex )
  {
    v19 = v19->Next;
    if ( !v19 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        v20 = *((_QWORD *)&xmmword_1800AB328 + 1);
        if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
        {
          v21 = L"Couldn't get info for the adapter";
          goto LABEL_39;
        }
        goto LABEL_42;
      }
      v22 = "Couldn't get info for the adapter";
      goto LABEL_41;
    }
  }
  v23 = 0;
  v8 = inet_addr(v19->IpAddressList.IpAddress.String);
  inet_addr(v19->GatewayList.IpAddress.String);
  if ( v19->HaveWins )
  {
    v23 = inet_addr(v19->PrimaryWinsServer.IpAddress.String);
    v3 = inet_addr(v19->SecondaryWinsServer.IpAddress.String);
  }
  if ( v23 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( unk_1800AB338 )
      {
        LOWORD(v37) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v37, L"GetAdapterInfo: replacing WINS1 with 0x%x since its loopback", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          unk_1800AB338,
          &v37,
          v32,
          0,
          &v33);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing WINS1 with 0x%x since its loopback");
    }
  }
  if ( v3 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        LOWORD(v37) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v37, L"GetAdapterInfo: replacing WINS2 with 0x%x since its loopback", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v37,
          v32,
          0,
          &v33);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing WINS2 with 0x%x since its loopback");
    }
  }
  SizePointer = 0;
  PerAdapterInfo = GetPerAdapterInfo(IfIndex, 0, &SizePointer);
  RoutingDomainIdForCompartment = PerAdapterInfo;
  if ( PerAdapterInfo != 111 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        v16 = L"GetPerAdapterInfo failed and returned %d";
LABEL_22:
        LOWORD(v33) = 0;
        LOWORD(v37) = 0;
        FormatRRASErrorString(&v37, v16, PerAdapterInfo);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v37,
          v32,
          0,
          &v33);
      }
LABEL_23:
      if ( !RoutingDomainIdForCompartment )
        goto LABEL_25;
      goto LABEL_24;
    }
    v18 = "GetPerAdapterInfo failed and returned %d";
LABEL_31:
    TraceHlp(v18);
    goto LABEL_23;
  }
  v24 = (IP_PER_ADAPTER_INFO_W2KSP1 *)LocalAlloc(0x40u, SizePointer);
  v7 = v24;
  if ( !v24 )
  {
LABEL_19:
    PerAdapterInfo = GetLastError();
    RoutingDomainIdForCompartment = PerAdapterInfo;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800AB328 + 1) )
        goto LABEL_23;
      v16 = L"LocalAlloc failed and returned %d";
      goto LABEL_22;
    }
    v18 = "LocalAlloc failed and returned %d";
    goto LABEL_31;
  }
  AdaptersInfo = GetPerAdapterInfo(IfIndex, v24, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        v12 = L"GetPerAdapterInfo failed and returned %d";
        goto LABEL_85;
      }
LABEL_24:
      v8 = 0;
      goto LABEL_25;
    }
    v13 = "GetPerAdapterInfo failed and returned %d";
LABEL_87:
    TraceHlp(v13);
    goto LABEL_24;
  }
  v25 = inet_addr(v7->DnsServerList.IpAddress.String);
  if ( v25 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        LOWORD(v37) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v37, L"GetAdapterInfo: replacing DNS1 with 0x%x since its loopback", v8);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v37,
          v32,
          0,
          &v33);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing DNS1 with 0x%x since its loopback");
    }
  }
  Next = v7->DnsServerList.Next;
  if ( Next )
  {
    v27 = inet_addr(Next->IpAddress.String);
    if ( v27 == htonl(0x7F000001u) )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
        {
          LOWORD(v37) = 0;
          LOWORD(v33) = 0;
          FormatRRASErrorString(&v37, L"GetAdapterInfo: replacing DNS2 with 0x%x since its loopback", v8);
          ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            *((_QWORD *)&xmmword_1800AB328 + 1),
            &v37,
            v32,
            0,
            &v33);
        }
      }
      else
      {
        TraceHlp("GetAdapterInfo: replacing DNS2 with 0x%x since its loopback");
      }
    }
  }
  if ( ((v8 + 1) & 0xFFFFFFFE) == 0 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      v20 = *((_QWORD *)&xmmword_1800AB328 + 1);
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        v21 = L"Couldn't get IpAddress for the adapter";
LABEL_39:
        LOWORD(v33) = 0;
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          v20,
          v21,
          v32,
          0,
          &v33);
      }
LABEL_42:
      RoutingDomainIdForCompartment = 1168;
      goto LABEL_24;
    }
    v22 = "Couldn't get IpAddress for the adapter";
LABEL_41:
    TraceHlp(v22);
    goto LABEL_42;
  }
LABEL_25:
  if ( v31 )
    *v31 = v8;
  LocalFree(v6);
  LocalFree(v7);
  if ( v29 )
    SetCurrentThreadCompartmentId(CompartmentIda);
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x18006bd20  mov     [rsp-8+arg_18], rbx
0x18006bd25  push    rbp
0x18006bd26  push    rsi
0x18006bd27  push    rdi
0x18006bd28  push    r12
0x18006bd2a  push    r13
0x18006bd2c  push    r14
0x18006bd2e  push    r15
0x18006bd30  lea     rbp, [rsp-7B0h]
0x18006bd38  sub     rsp, 8B0h
0x18006bd3f  mov     rax, cs:__security_cookie
0x18006bd46  xor     rax, rsp
0x18006bd49  mov     [rbp+7E0h+var_40], rax
0x18006bd50  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006bd57  xor     r14d, r14d
0x18006bd5a  mov     [rsp+8E0h+var_890], r8
0x18006bd5f  mov     ebx, edx
0x18006bd61  mov     [rsp+8E0h+SizePointer], r14d
0x18006bd66  mov     r15d, ecx
0x18006bd69  mov     [rsp+8E0h+var_89C], r14d
0x18006bd6e  xor     edx, edx; Val
0x18006bd70  mov     [rbp+7E0h+var_840], r14d
0x18006bd74  mov     r8d, 7FCh; Size
0x18006bd7a  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18006bd7e  movdqu  [rsp+8E0h+var_888], xmm0
0x18006bd84  mov     r12d, r14d
0x18006bd87  mov     r13d, r14d
0x18006bd8a  mov     esi, r14d
0x18006bd8d  call    memset_0
0x18006bd92  xorps   xmm0, xmm0
0x18006bd95  mov     [rsp+8E0h+var_868], r14d
0x18006bd9a  xor     eax, eax
0x18006bd9c  mov     [rbp+7E0h+var_844], eax
0x18006bd9f  movups  [rsp+8E0h+var_864], xmm0
0x18006bda4  movups  [rbp+7E0h+var_854], xmm0
0x18006bda8  movups  [rsp+8E0h+var_878], xmm0
0x18006bdad  cmp     ebx, 1
0x18006bdb0  jz      short loc_18006BDBB
0x18006bdb2  cmp     qword ptr cs:unk_1800AB320, r14
0x18006bdb9  jnz     short loc_18006BDD9
0x18006bdbb  cmp     qword ptr cs:xmmword_1800AB328, r14
0x18006bdc2  jnz     short loc_18006BDD9
0x18006bdc4  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006bdcb  jnz     short loc_18006BDD9
0x18006bdcd  mov     rdx, qword ptr cs:unk_1800AB338
0x18006bdd4  test    rdx, rdx
0x18006bdd7  jz      short loc_18006BDFE
0x18006bdd9  lea     rdx, [rsp+8E0h+var_888]
0x18006bdde  mov     [rsp+8E0h+CompartmentId], 1
0x18006bde6  mov     ecx, ebx
0x18006bde8  call    NsiGetRoutingDomainIdForCompartment
0x18006bded  mov     edi, eax
0x18006bdef  test    eax, eax
0x18006bdf1  jnz     loc_18006BF46
0x18006bdf7  mov     rdx, qword ptr cs:unk_1800AB338
0x18006bdfe  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006be05  jz      short loc_18006BE42
0x18006be07  test    rdx, rdx
0x18006be0a  jz      short loc_18006BE4E
0x18006be0c  mov     rcx, cs:gIphlpEtwContext
0x18006be13  lea     rax, [rsp+8E0h+var_868]
0x18006be18  mov     [rsp+8E0h+var_8B8], rax
0x18006be1d  lea     r9, [rsp+8E0h+var_888]
0x18006be22  mov     rax, cs:gIphlpParamTemplateFunc
0x18006be29  lea     r8, aGetadapterinfo; "GetAdapterInfo"
0x18006be30  mov     word ptr [rsp+8E0h+var_868], r14w
0x18006be36  mov     [rsp+8E0h+var_8C0], r14
0x18006be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be40  jmp     short loc_18006BE4E
0x18006be42  lea     rcx, aGetadapterinfo_6; "GetAdapterInfo"
0x18006be49  call    TraceHlp
0x18006be4e  call    cs:__imp_GetCurrentThreadCompartmentId
0x18006be54  mov     ecx, ebx; CompartmentId
0x18006be56  mov     [rsp+8E0h+CompartmentId], eax
0x18006be5a  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006be60  mov     edi, eax
0x18006be62  test    eax, eax
0x18006be64  jnz     loc_18006C3A8
0x18006be6a  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18006be6f  mov     [rsp+8E0h+var_89C], 1
0x18006be77  xor     ecx, ecx; AdapterInfo
0x18006be79  mov     [rsp+8E0h+SizePointer], r14d
0x18006be7e  call    cs:__imp_GetAdaptersInfo
0x18006be84  mov     edi, eax
0x18006be86  cmp     eax, 6Fh ; 'o'
0x18006be89  jz      short loc_18006BEBD
0x18006be8b  test    eax, eax
0x18006be8d  jz      short loc_18006BEBD
0x18006be8f  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006be96  jz      short loc_18006BEB1
0x18006be98  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006be9f  jz      loc_18006BF4A
0x18006bea5  lea     rdx, aGetadaptersinf; "GetAdaptersInfo failed and returned %d"
0x18006beac  jmp     loc_18006C3C5
0x18006beb1  lea     rcx, aGetadaptersinf_0; "GetAdaptersInfo failed and returned %d"
0x18006beb8  jmp     loc_18006C41A
0x18006bebd  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18006bec1  mov     ecx, 40h ; '@'; uFlags
0x18006bec6  call    cs:__imp_LocalAlloc
0x18006becc  mov     r12, rax
0x18006becf  test    rax, rax
0x18006bed2  jnz     loc_18006BFB8
0x18006bed8  call    cs:__imp_GetLastError
0x18006bede  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006bee5  mov     edi, eax
0x18006bee7  jz      loc_18006BFA8
0x18006beed  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006bef4  jz      short loc_18006BF46
0x18006bef6  lea     rdx, aLocalallocFail_2; "LocalAlloc failed and returned %d"
0x18006befd  mov     r8d, eax
0x18006bf00  mov     word ptr [rsp+8E0h+var_868], r14w
0x18006bf06  lea     rcx, [rbp+7E0h+var_840]
0x18006bf0a  mov     word ptr [rbp+7E0h+var_840], r14w
0x18006bf0f  call    FormatRRASErrorString
0x18006bf14  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006bf1b  lea     rax, [rsp+8E0h+var_868]
0x18006bf20  mov     rcx, cs:gIphlpEtwContext
0x18006bf27  lea     r9, [rsp+8E0h+var_888]
0x18006bf2c  mov     [rsp+8E0h+var_8B8], rax
0x18006bf31  lea     r8, [rbp+7E0h+var_840]
0x18006bf35  mov     rax, cs:gIphlpParamTemplateFunc
0x18006bf3c  mov     [rsp+8E0h+var_8C0], r14
0x18006bf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf46  test    edi, edi
0x18006bf48  jz      short loc_18006BF4D
0x18006bf4a  mov     esi, r14d
0x18006bf4d  mov     rax, [rsp+8E0h+var_890]
0x18006bf52  test    rax, rax
0x18006bf55  jz      short loc_18006BF59
0x18006bf57  mov     [rax], esi
0x18006bf59  mov     rcx, r12; hMem
0x18006bf5c  call    cs:__imp_LocalFree
0x18006bf62  mov     rcx, r13; hMem
0x18006bf65  call    cs:__imp_LocalFree
0x18006bf6b  cmp     [rsp+8E0h+var_89C], r14d
0x18006bf70  jz      short loc_18006BF7C
0x18006bf72  mov     ecx, [rsp+8E0h+CompartmentId]; CompartmentId
0x18006bf76  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006bf7c  mov     eax, edi
0x18006bf7e  mov     rcx, [rbp+7E0h+var_40]
0x18006bf85  xor     rcx, rsp; StackCookie
0x18006bf88  call    __security_check_cookie
0x18006bf8d  mov     rbx, [rsp+8E0h+arg_18]
0x18006bf95  add     rsp, 8B0h
0x18006bf9c  pop     r15
0x18006bf9e  pop     r14
0x18006bfa0  pop     r13
0x18006bfa2  pop     r12
0x18006bfa4  pop     rdi
0x18006bfa5  pop     rsi
0x18006bfa6  pop     rbp
0x18006bfa7  retn
0x18006bfa8  lea     rcx, aLocalallocFail_0; "LocalAlloc failed and returned %d"
0x18006bfaf  mov     edx, eax
0x18006bfb1  call    TraceHlp
0x18006bfb6  jmp     short loc_18006BF46
0x18006bfb8  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18006bfbd  mov     rcx, r12; AdapterInfo
0x18006bfc0  call    cs:__imp_GetAdaptersInfo
0x18006bfc6  mov     edi, eax
0x18006bfc8  test    eax, eax
0x18006bfca  jnz     loc_18006BE8F
0x18006bfd0  mov     rbx, r12
0x18006bfd3  cmp     [rbx+1A0h], r15d
0x18006bfda  jz      short loc_18006C045
0x18006bfdc  mov     rbx, [rbx]
0x18006bfdf  test    rbx, rbx
0x18006bfe2  jnz     short loc_18006BFD3
0x18006bfe4  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006bfeb  jz      short loc_18006C02F
0x18006bfed  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006bff4  test    rdx, rdx
0x18006bff7  jz      short loc_18006C03B
0x18006bff9  lea     r8, aCouldnTGetInfo_0; "Couldn't get info for the adapter"
0x18006c000  mov     rcx, cs:gIphlpEtwContext
0x18006c007  lea     rax, [rsp+8E0h+var_868]
0x18006c00c  mov     [rsp+8E0h+var_8B8], rax
0x18006c011  lea     r9, [rsp+8E0h+var_888]
0x18006c016  mov     rax, cs:gIphlpParamTemplateFunc
0x18006c01d  mov     [rsp+8E0h+var_8C0], r14
0x18006c022  mov     word ptr [rsp+8E0h+var_868], r14w
0x18006c028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c02d  jmp     short loc_18006C03B
0x18006c02f  lea     rcx, aCouldnTGetInfo; "Couldn't get info for the adapter"
0x18006c036  call    TraceHlp
0x18006c03b  mov     edi, 490h
0x18006c040  jmp     loc_18006BF4A
0x18006c045  lea     rcx, [rbx+1C0h]; cp
0x18006c04c  mov     edi, r14d
0x18006c04f  call    cs:__imp_inet_addr
0x18006c055  lea     rcx, [rbx+1F0h]; cp
0x18006c05c  mov     esi, eax
0x18006c05e  call    cs:__imp_inet_addr
0x18006c064  cmp     [rbx+248h], r14d
0x18006c06b  jz      short loc_18006C08C
0x18006c06d  lea     rcx, [rbx+258h]; cp
0x18006c074  call    cs:__imp_inet_addr
0x18006c07a  lea     rcx, [rbx+288h]; cp
0x18006c081  mov     edi, eax
0x18006c083  call    cs:__imp_inet_addr
0x18006c089  mov     r14d, eax
0x18006c08c  mov     ecx, 7F000001h; hostlong
0x18006c091  call    cs:__imp_htonl
0x18006c097  cmp     edi, eax
0x18006c099  jnz     short loc_18006C10C
0x18006c09b  xor     ebx, ebx
0x18006c09d  cmp     cs:gIsIphlpEtwTracingAvailable, ebx
0x18006c0a3  jz      short loc_18006C0FE
0x18006c0a5  cmp     qword ptr cs:unk_1800AB338, rbx
0x18006c0ac  jz      short loc_18006C10C
0x18006c0ae  mov     r8d, esi
0x18006c0b1  mov     word ptr [rbp+7E0h+var_840], bx
0x18006c0b5  lea     rdx, aGetadapterinfo_7; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18006c0bc  mov     word ptr [rsp+8E0h+var_868], bx
0x18006c0c1  lea     rcx, [rbp+7E0h+var_840]
0x18006c0c5  call    FormatRRASErrorString
0x18006c0ca  mov     rdx, qword ptr cs:unk_1800AB338
0x18006c0d1  lea     rax, [rsp+8E0h+var_868]
0x18006c0d6  mov     rcx, cs:gIphlpEtwContext
0x18006c0dd  lea     r9, [rsp+8E0h+var_888]
0x18006c0e2  mov     [rsp+8E0h+var_8B8], rax
0x18006c0e7  lea     r8, [rbp+7E0h+var_840]
0x18006c0eb  mov     rax, cs:gIphlpParamTemplateFunc
0x18006c0f2  mov     [rsp+8E0h+var_8C0], rbx
0x18006c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0fc  jmp     short loc_18006C10C
0x18006c0fe  mov     edx, esi
0x18006c100  lea     rcx, aGetadapterinfo_5; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18006c107  call    TraceHlp
0x18006c10c  mov     ecx, 7F000001h; hostlong
0x18006c111  call    cs:__imp_htonl
0x18006c117  cmp     r14d, eax
0x18006c11a  jnz     short loc_18006C193
0x18006c11c  xor     r14d, r14d
0x18006c11f  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006c126  jz      short loc_18006C183
0x18006c128  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006c12f  jz      short loc_18006C196
0x18006c131  mov     r8d, esi
0x18006c134  mov     word ptr [rbp+7E0h+var_840], r14w
0x18006c139  lea     rdx, aGetadapterinfo_8; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18006c140  mov     word ptr [rsp+8E0h+var_868], r14w
0x18006c146  lea     rcx, [rbp+7E0h+var_840]
0x18006c14a  call    FormatRRASErrorString
0x18006c14f  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006c156  lea     rax, [rsp+8E0h+var_868]
0x18006c15b  mov     rcx, cs:gIphlpEtwContext
0x18006c162  lea     r9, [rsp+8E0h+var_888]
0x18006c167  mov     [rsp+8E0h+var_8B8], rax
0x18006c16c  lea     r8, [rbp+7E0h+var_840]
0x18006c170  mov     rax, cs:gIphlpParamTemplateFunc
0x18006c177  mov     [rsp+8E0h+var_8C0], r14
0x18006c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c181  jmp     short loc_18006C196
0x18006c183  mov     edx, esi
0x18006c185  lea     rcx, aGetadapterinfo_4; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18006c18c  call    TraceHlp
0x18006c191  jmp     short loc_18006C196
0x18006c193  xor     r14d, r14d
0x18006c196  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18006c19b  mov     [rsp+8E0h+SizePointer], r14d
0x18006c1a0  xor     edx, edx; pPerAdapterInfo
0x18006c1a2  mov     ecx, r15d; IfIndex
0x18006c1a5  call    cs:__imp_GetPerAdapterInfo
0x18006c1ab  mov     edi, eax
0x18006c1ad  cmp     eax, 6Fh ; 'o'
0x18006c1b0  jz      short loc_18006C1E0
0x18006c1b2  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006c1b9  jz      short loc_18006C1D4
0x18006c1bb  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006c1c2  jz      loc_18006BF46
0x18006c1c8  lea     rdx, aGetperadapteri_0; "GetPerAdapterInfo failed and returned %"...
0x18006c1cf  jmp     loc_18006BEFD
0x18006c1d4  lea     rcx, aGetperadapteri; "GetPerAdapterInfo failed and returned %"...
0x18006c1db  jmp     loc_18006BFAF
0x18006c1e0  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18006c1e4  mov     ecx, 40h ; '@'; uFlags
0x18006c1e9  call    cs:__imp_LocalAlloc
0x18006c1ef  mov     r13, rax
0x18006c1f2  test    rax, rax
0x18006c1f5  jz      loc_18006BED8
0x18006c1fb  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18006c200  mov     rdx, rax; pPerAdapterInfo
0x18006c203  mov     ecx, r15d; IfIndex
0x18006c206  call    cs:__imp_GetPerAdapterInfo
0x18006c20c  mov     edi, eax
0x18006c20e  test    eax, eax
0x18006c210  jz      short loc_18006C240
0x18006c212  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006c219  jz      short loc_18006C234
0x18006c21b  cmp     qword ptr cs:xmmword_1800AB328+8, r14
0x18006c222  jz      loc_18006BF4A
0x18006c228  lea     rdx, aGetperadapteri_0; "GetPerAdapterInfo failed and returned %"...
0x18006c22f  jmp     loc_18006C3C5
0x18006c234  lea     rcx, aGetperadapteri; "GetPerAdapterInfo failed and returned %"...
0x18006c23b  jmp     loc_18006C41A
0x18006c240  lea     rcx, [r13+18h]; cp
0x18006c244  call    cs:__imp_inet_addr
0x18006c24a  mov     r15d, 7F000001h
0x18006c250  mov     ebx, eax
  ... truncated ...
```
