# RasTcpSetRoute

- ea: `0x180070800`
- end: `0x180070c23`
- name: `RasTcpSetRoute`
- size: `1059`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070034`
- `0x180070498`

## callees

- `0x1800697b4`
- `0x180069a8c`
- `0x18006f864`
- `0x18006f8a8`
- `0x180070800`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070bfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070bfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800709e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800709e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709f4`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180070b63`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180070b63`

## pseudocode

```c
__int64 __fastcall RasTcpSetRoute(
        DWORD a1,
        DWORD a2,
        DWORD a3,
        int a4,
        int a5,
        int a6,
        int a7,
        NET_IF_COMPARTMENT_ID a8)
{
  int v8; // ebx
  __int64 v12; // rax
  DWORD RoutingDomainIdForCompartment; // ebx
  const char *v14; // rax
  const char *v15; // rax
  HANDLE ProcessHeap; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // rsi
  DWORD LastError; // eax
  DWORD IpAddrTable; // eax
  void *v22; // rdi
  __int64 i; // rcx
  DWORD v24; // eax
  const char *v26; // [rsp+30h] [rbp-D0h]
  const char *v27; // [rsp+38h] [rbp-C8h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  _MIB_IPFORWARDROW pRoute; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v31[2]; // [rsp+98h] [rbp-68h] BYREF
  int v32; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v33; // [rsp+BCh] [rbp-44h]
  __int128 v34; // [rsp+CCh] [rbp-34h]
  int v35; // [rsp+DCh] [rbp-24h]
  int v36; // [rsp+E0h] [rbp-20h] BYREF
  char v37[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v8 = a4;
  memset(&pRoute, 0, sizeof(pRoute));
  lpMem = 0;
  memset(v31, 0, sizeof(v31));
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  if ( unk_1800AB320
    || __PAIR128__(xmmword_1800AB328, 0) != *((unsigned __int64 *)&xmmword_1800AB328 + 1)
    || (v12 = unk_1800AB338) != 0 && a8 != 1 )
  {
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a8, v31);
    if ( RoutingDomainIdForCompartment )
      return RoutingDomainIdForCompartment;
    v12 = unk_1800AB338;
    v8 = a4;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v12 )
    {
      v14 = "Add";
      LOWORD(v36) = 0;
      if ( !a5 )
        v14 = "Del";
      LOWORD(v32) = 0;
      FormatRRASErrorString(
        &v36,
        L"RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)",
        a1,
        a3,
        a2,
        v8,
        1,
        v14,
        "Stack");
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800AB338,
        &v36,
        v31,
        0,
        &v32);
    }
  }
  else
  {
    v15 = "Add";
    if ( !a5 )
      v15 = "Del";
    v27 = "Stack";
    v26 = v15;
    TraceHlp("RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)");
  }
  memset(&pRoute, 0, sizeof(pRoute));
  ProcessHeap = GetProcessHeap();
  v19 = ProcessHeap;
  if ( ProcessHeap )
  {
    IpAddrTable = AllocateAndGetIpAddrTable(&lpMem, v17, ProcessHeap, v18, a8);
    v22 = lpMem;
    RoutingDomainIdForCompartment = IpAddrTable;
    if ( IpAddrTable )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
        {
          LOWORD(v36) = 0;
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v36, L"AllocateAndGetIpAddrTable failed and returned %d", IpAddrTable);
LABEL_36:
          ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            *((_QWORD *)&xmmword_1800AB328 + 1),
            &v36,
            v31,
            0,
            &v32,
            v26,
            v27);
        }
      }
      else
      {
        TraceHlp("AllocateAndGetIpAddrTable failed and returned %d");
      }
    }
    else
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)lpMem; i = (unsigned int)(i + 1) )
      {
        if ( a4 == *((_DWORD *)lpMem + 6 * i + 1) )
        {
          pRoute.dwForwardDest = a1;
          pRoute.dwForwardPolicy = 0;
          pRoute.dwForwardMask = a3;
          pRoute.dwForwardNextHop = a2;
          pRoute.dwForwardIfIndex = *((_DWORD *)lpMem + 6 * i + 2);
          pRoute.dwForwardProto = 3;
          pRoute.dwForwardAge = -1;
          pRoute.dwForwardNextHopAS = 0;
          pRoute.dwForwardMetric1 = 1;
          *(__m128i *)&pRoute.dwForwardMetric2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          if ( a5 )
          {
            pRoute.dwForwardType = 3;
            v24 = CreateOrSetIpForwardEntry(&pRoute);
          }
          else
          {
            pRoute.dwForwardType = 2;
            v24 = DeleteIpForwardEntry(&pRoute);
          }
          RoutingDomainIdForCompartment = v24;
          if ( !v24 )
            break;
          if ( !gIsIphlpEtwTracingAvailable )
          {
            TraceHlp("SetIpForwardEntry%hs failed and returned 0x%x");
            break;
          }
          if ( !*((_QWORD *)&xmmword_1800AB328 + 1) )
            break;
          LOWORD(v36) = 0;
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v36, L"SetIpForwardEntry%hs failed and returned 0x%x", "ToStack", v24);
          goto LABEL_36;
        }
      }
    }
    if ( v22 )
      HeapFree(v19, 0, v22);
  }
  else
  {
    LastError = GetLastError();
    RoutingDomainIdForCompartment = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"GetProcessHeap failed and returned %d", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v36,
          v31,
          0,
          &v32,
          v26,
          v27);
      }
    }
    else
    {
      TraceHlp("GetProcessHeap failed and returned %d");
    }
  }
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x180070800  push    rbp
0x180070802  push    rbx
0x180070803  push    rsi
0x180070804  push    rdi
0x180070805  push    r12
0x180070807  push    r13
0x180070809  push    r15
0x18007080b  lea     rbp, [rsp-7F0h]
0x180070813  sub     rsp, 8F0h
0x18007081a  mov     rax, cs:__security_cookie
0x180070821  xor     rax, rsp
0x180070824  mov     [rbp+820h+var_40], rax
0x18007082b  xorps   xmm0, xmm0
0x18007082e  mov     ebx, r9d
0x180070831  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x180070836  mov     r13d, r8d
0x180070839  mov     r12d, edx
0x18007083c  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x180070841  mov     r15d, ecx
0x180070844  xor     esi, esi
0x180070846  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x18007084a  xor     eax, eax
0x18007084c  xor     edx, edx; Val
0x18007084e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180070855  mov     r8d, 7FCh; Size
0x18007085b  mov     [rsp+920h+var_8D0], ebx
0x18007085f  lea     rcx, [rbp+820h+var_83C]; void *
0x180070863  mov     [rsp+920h+lpMem], rsi
0x180070868  movdqu  [rbp+820h+var_888], xmm0
0x18007086d  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180070871  mov     [rbp+820h+var_840], esi
0x180070874  call    memset_0
0x180070879  mov     edi, [rbp+820h+arg_38]
0x18007087f  xorps   xmm0, xmm0
0x180070882  xor     eax, eax
0x180070884  mov     [rbp+820h+var_868], esi
0x180070887  cmp     qword ptr cs:unk_1800AB320, rsi
0x18007088e  movups  [rbp+820h+var_864], xmm0
0x180070892  mov     [rbp+820h+var_844], eax
0x180070895  movups  [rbp+820h+var_854], xmm0
0x180070899  movups  [rbp+820h+var_878], xmm0
0x18007089d  jnz     short loc_1800708C2
0x18007089f  cmp     qword ptr cs:xmmword_1800AB328, rsi
0x1800708a6  jnz     short loc_1800708C2
0x1800708a8  cmp     qword ptr cs:xmmword_1800AB328+8, rsi
0x1800708af  jnz     short loc_1800708C2
0x1800708b1  mov     rax, qword ptr cs:unk_1800AB338
0x1800708b8  test    rax, rax
0x1800708bb  jz      short loc_1800708E2
0x1800708bd  cmp     edi, 1
0x1800708c0  jz      short loc_1800708E2
0x1800708c2  lea     rdx, [rbp+820h+var_888]
0x1800708c6  mov     ecx, edi
0x1800708c8  call    NsiGetRoutingDomainIdForCompartment
0x1800708cd  mov     ebx, eax
0x1800708cf  test    eax, eax
0x1800708d1  jnz     loc_180070C00
0x1800708d7  mov     rax, qword ptr cs:unk_1800AB338
0x1800708de  mov     ebx, [rsp+920h+var_8D0]
0x1800708e2  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800708e8  jz      loc_180070981
0x1800708ee  test    rax, rax
0x1800708f1  jz      loc_1800709CB
0x1800708f7  cmp     [rbp+820h+arg_20], esi
0x1800708fd  lea     rcx, aDel; "Del"
0x180070904  lea     rax, aAdd; "Add"
0x18007090b  mov     word ptr [rbp+820h+var_840], si
0x18007090f  cmovz   rax, rcx
0x180070913  mov     word ptr [rbp+820h+var_868], si
0x180070917  lea     rcx, aStack; "Stack"
0x18007091e  mov     r9d, r13d
0x180070921  mov     [rsp+920h+var_8E0], rcx
0x180070926  lea     rdx, aRastcpsetroute_2; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18007092d  mov     [rsp+920h+var_8E8], rax
0x180070932  lea     rcx, [rbp+820h+var_840]
0x180070936  mov     dword ptr [rsp+920h+var_8F0], 1
0x18007093e  mov     r8d, r15d
0x180070941  mov     dword ptr [rsp+920h+var_8F8], ebx
0x180070945  mov     dword ptr [rsp+920h+var_900], r12d
0x18007094a  call    FormatRRASErrorString
0x18007094f  mov     rdx, qword ptr cs:unk_1800AB338
0x180070956  lea     rax, [rbp+820h+var_868]
0x18007095a  mov     rcx, cs:gIphlpEtwContext
0x180070961  lea     r9, [rbp+820h+var_888]
0x180070965  mov     [rsp+920h+var_8F8], rax
0x18007096a  lea     r8, [rbp+820h+var_840]
0x18007096e  mov     rax, cs:gIphlpParamTemplateFunc
0x180070975  mov     [rsp+920h+var_900], rsi
0x18007097a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007097f  jmp     short loc_1800709CB
0x180070981  cmp     [rbp+820h+arg_20], esi
0x180070987  lea     rcx, aDel; "Del"
0x18007098e  lea     rax, aAdd; "Add"
0x180070995  mov     r9d, r12d
0x180070998  cmovz   rax, rcx
0x18007099c  mov     r8d, r13d
0x18007099f  lea     rcx, aStack; "Stack"
0x1800709a6  mov     edx, r15d
0x1800709a9  mov     [rsp+920h+var_8E8], rcx
0x1800709ae  lea     rcx, aRastcpsetroute_1; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x1800709b5  mov     [rsp+920h+var_8F0], rax
0x1800709ba  mov     dword ptr [rsp+920h+var_8F8], 1
0x1800709c2  mov     dword ptr [rsp+920h+var_900], ebx
0x1800709c6  call    TraceHlp
0x1800709cb  xorps   xmm0, xmm0
0x1800709ce  xor     eax, eax
0x1800709d0  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x1800709d5  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x1800709d9  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x1800709de  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x1800709e2  call    cs:__imp_GetProcessHeap
0x1800709e8  mov     rsi, rax
0x1800709eb  test    rax, rax
0x1800709ee  jnz     loc_180070A76
0x1800709f4  call    cs:__imp_GetLastError
0x1800709fa  xor     edi, edi
0x1800709fc  mov     ebx, eax
0x1800709fe  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x180070a04  jz      short loc_180070A63
0x180070a06  cmp     qword ptr cs:xmmword_1800AB328+8, rdi
0x180070a0d  jz      loc_180070C00
0x180070a13  mov     r8d, eax
0x180070a16  mov     word ptr [rbp+820h+var_840], di
0x180070a1a  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x180070a21  mov     word ptr [rbp+820h+var_868], di
0x180070a25  lea     rcx, [rbp+820h+var_840]
0x180070a29  call    FormatRRASErrorString
0x180070a2e  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x180070a35  lea     rax, [rbp+820h+var_868]
0x180070a39  mov     rcx, cs:gIphlpEtwContext
0x180070a40  lea     r9, [rbp+820h+var_888]
0x180070a44  mov     [rsp+920h+var_8F8], rax
0x180070a49  lea     r8, [rbp+820h+var_840]
0x180070a4d  mov     rax, cs:gIphlpParamTemplateFunc
0x180070a54  mov     [rsp+920h+var_900], rdi
0x180070a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a5e  jmp     loc_180070C00
0x180070a63  mov     edx, eax
0x180070a65  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x180070a6c  call    TraceHlp
0x180070a71  jmp     loc_180070C00
0x180070a76  mov     r8, rsi
0x180070a79  mov     dword ptr [rsp+920h+var_900], edi
0x180070a7d  lea     rcx, [rsp+920h+lpMem]
0x180070a82  call    AllocateAndGetIpAddrTable
0x180070a87  mov     rdi, [rsp+920h+lpMem]
0x180070a8c  mov     ebx, eax
0x180070a8e  test    eax, eax
0x180070a90  jz      short loc_180070AE0
0x180070a92  xor     r15d, r15d
0x180070a95  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180070a9c  jz      short loc_180070ACD
0x180070a9e  cmp     qword ptr cs:xmmword_1800AB328+8, r15
0x180070aa5  jz      loc_180070BED
0x180070aab  mov     r8d, eax
0x180070aae  mov     word ptr [rbp+820h+var_840], r15w
0x180070ab3  lea     rdx, aAllocateandget_16; "AllocateAndGetIpAddrTable failed and re"...
0x180070aba  mov     word ptr [rbp+820h+var_868], r15w
0x180070abf  lea     rcx, [rbp+820h+var_840]
0x180070ac3  call    FormatRRASErrorString
0x180070ac8  jmp     loc_180070BA5
0x180070acd  mov     edx, eax
0x180070acf  lea     rcx, aAllocateandget_6; "AllocateAndGetIpAddrTable failed and re"...
0x180070ad6  call    TraceHlp
0x180070adb  jmp     loc_180070BED
0x180070ae0  mov     edx, [rsp+920h+var_8D0]
0x180070ae4  xor     ecx, ecx
0x180070ae6  cmp     ecx, [rdi]
0x180070ae8  jnb     loc_180070BED
0x180070aee  lea     rax, [rcx+rcx*2]
0x180070af2  cmp     edx, [rdi+rax*8+4]
0x180070af6  jz      short loc_180070AFC
0x180070af8  inc     ecx
0x180070afa  jmp     short loc_180070AE6
0x180070afc  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180070b04  lea     rcx, [rsp+920h+pRoute]; pRoute
0x180070b09  mov     [rsp+920h+pRoute.dwForwardDest], r15d
0x180070b0e  xor     r15d, r15d
0x180070b11  mov     [rsp+920h+pRoute.dwForwardPolicy], r15d
0x180070b16  mov     [rsp+920h+pRoute.dwForwardMask], r13d
0x180070b1b  mov     [rsp+920h+pRoute.dwForwardNextHop], r12d
0x180070b20  mov     eax, [rdi+rax*8+8]
0x180070b24  mov     [rsp+920h+pRoute.dwForwardIfIndex], eax
0x180070b28  lea     eax, [r15+3]
0x180070b2c  mov     dword ptr [rsp+920h+pRoute.18h], eax
0x180070b30  mov     [rsp+920h+pRoute.dwForwardAge], 0FFFFFFFFh
0x180070b38  mov     [rbp+820h+pRoute.dwForwardNextHopAS], r15d
0x180070b3c  mov     [rbp+820h+pRoute.dwForwardMetric1], 1
0x180070b43  movups  xmmword ptr [rbp+820h+pRoute.dwForwardMetric2], xmm0
0x180070b47  cmp     [rbp+820h+arg_20], r15d
0x180070b4e  jz      short loc_180070B5B
0x180070b50  mov     dword ptr [rsp+920h+pRoute.14h], eax
0x180070b54  call    CreateOrSetIpForwardEntry
0x180070b59  jmp     short loc_180070B69
0x180070b5b  mov     dword ptr [rsp+920h+pRoute.14h], 2
0x180070b63  call    cs:__imp_DeleteIpForwardEntry
0x180070b69  mov     ebx, eax
0x180070b6b  test    eax, eax
0x180070b6d  jz      short loc_180070BED
0x180070b6f  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180070b76  jz      short loc_180070BD7
0x180070b78  cmp     qword ptr cs:xmmword_1800AB328+8, r15
0x180070b7f  jz      short loc_180070BED
0x180070b81  mov     r9d, eax
0x180070b84  mov     word ptr [rbp+820h+var_840], r15w
0x180070b89  lea     r8, aTostack; "ToStack"
0x180070b90  mov     word ptr [rbp+820h+var_868], r15w
0x180070b95  lea     rdx, aSetipforwarden_1; "SetIpForwardEntry%hs failed and returne"...
0x180070b9c  lea     rcx, [rbp+820h+var_840]
0x180070ba0  call    FormatRRASErrorString
0x180070ba5  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x180070bac  lea     rax, [rbp+820h+var_868]
0x180070bb0  mov     rcx, cs:gIphlpEtwContext
0x180070bb7  lea     r9, [rbp+820h+var_888]
0x180070bbb  mov     [rsp+920h+var_8F8], rax
0x180070bc0  lea     r8, [rbp+820h+var_840]
0x180070bc4  mov     rax, cs:gIphlpParamTemplateFunc
0x180070bcb  mov     [rsp+920h+var_900], r15
0x180070bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bd5  jmp     short loc_180070BED
0x180070bd7  mov     r8d, ebx
0x180070bda  lea     rdx, aTostack; "ToStack"
0x180070be1  lea     rcx, aSetipforwarden_0; "SetIpForwardEntry%hs failed and returne"...
0x180070be8  call    TraceHlp
0x180070bed  test    rdi, rdi
0x180070bf0  jz      short loc_180070C00
0x180070bf2  mov     r8, rdi; lpMem
0x180070bf5  xor     edx, edx; dwFlags
0x180070bf7  mov     rcx, rsi; hHeap
0x180070bfa  call    cs:__imp_HeapFree
0x180070c00  mov     eax, ebx
0x180070c02  mov     rcx, [rbp+820h+var_40]
0x180070c09  xor     rcx, rsp; StackCookie
0x180070c0c  call    __security_check_cookie
0x180070c11  add     rsp, 8F0h
0x180070c18  pop     r15
0x180070c1a  pop     r13
0x180070c1c  pop     r12
0x180070c1e  pop     rdi
0x180070c1f  pop     rsi
0x180070c20  pop     rbx
0x180070c21  pop     rbp
0x180070c22  retn
```
