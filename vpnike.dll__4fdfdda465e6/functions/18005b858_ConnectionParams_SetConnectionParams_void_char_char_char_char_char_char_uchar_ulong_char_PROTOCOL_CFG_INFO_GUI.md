# ConnectionParams::SetConnectionParams(void *,char *,char *,char *,char *,char *,char *,uchar *,ulong,char *,_PROTOCOL_CFG_INFO &,_GUID &,void *,_PROTOCOL_INTERFACE_INFO &,_RAS_ADVCONNECTIONPARAMS &)

- ea: `0x18005b858`
- end: `0x18005c033`
- name: `?SetConnectionParams@ConnectionParams@@QEAAKPEAXPEAD11111PEAEK1AEAU_PROTOCOL_CFG_INFO@@AEAU_GUID@@0AEAU_PROTOCOL_INTERFACE_INFO@@AEAU_RAS_ADVCONNECTIONPARAMS@@@Z`
- size: `2011`
- prototype: `__int64 __fastcall(ConnectionParams *this, void *, char *, char *, char *, STRSAFE_LPCSTR pszSrc, STRSAFE_LPCSTR, char *, unsigned __int8 *Src, size_t Size, char *, struct _PROTOCOL_CFG_INFO *, struct _GUID *, void *, struct _PROTOCOL_INTERFACE_INFO *, struct _RAS_ADVCONNECTIONPARAMS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800052bc`

## callees

- `0x1800077bc`
- `0x18000a3a0`
- `0x180020b78`
- `0x180042028`
- `0x18005af78`
- `0x18005b304`
- `0x18005b858`
- `0x18005c03c`
- `0x18005c804`
- `0x18005c8e0`
- `0x18005c944`
- `0x180076ccc`
- `0x180077552`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!strstr` at `0x18005bcb0`
- `msvcrt!strstr` at `0x18005bcb0`
- `ntdll!RtlIpv6StringToAddressA` at `0x18005bcf5`
- `ntdll!RtlIpv6StringToAddressA` at `0x18005bcf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bc24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bc7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bc24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bc7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bc12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bc68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bc12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005bc68`
- `WS2_32!__imp_inet_addr` at `0x18005bcc5`
- `WS2_32!__imp_inet_addr` at `0x18005bcc5`

## string_xrefs

- `0x18005bd47`: `PhonebookPath: [%hs], EntryName: [%hs]`
- `0x18005be3e`: `ConfigFlags: 0x%08x, ProtocolConfigFlags: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectionParams::SetConnectionParams(
        ConnectionParams *this,
        void *a2,
        char *a3,
        char *a4,
        char *a5,
        STRSAFE_LPCSTR pszSrc,
        STRSAFE_LPCSTR a7,
        char *a8,
        unsigned __int8 *Src,
        size_t Size,
        char *a11,
        struct _PROTOCOL_CFG_INFO *a12,
        struct _GUID *a13,
        void *a14,
        struct _PROTOCOL_INTERFACE_INFO *a15,
        struct _RAS_ADVCONNECTIONPARAMS *a16)
{
  char *v18; // r15
  __int128 v19; // xmm0
  __int64 v20; // r8
  PVOID *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // rsi
  const char *v25; // r14
  bool v26; // cl
  __int64 v27; // rbx
  HANDLE ProcessHeap; // rax
  char *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rbx
  HANDLE v32; // rax
  char *v33; // rax
  char *v34; // rbx
  char *v35; // rax
  char *v36; // rcx
  int v37; // edx
  __int64 v38; // r8
  PVOID *v40; // rcx
  __int64 v41; // r9
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r8
  unsigned int v45; // eax
  unsigned int v46; // ebx
  const wchar_t *v47; // rdx
  unsigned int v48; // eax
  char *Str; // [rsp+30h] [rbp-D0h] BYREF
  STRSAFE_LPCSTR v50; // [rsp+38h] [rbp-C8h]
  struct _PROTOCOL_INTERFACE_INFO *v51; // [rsp+40h] [rbp-C0h]
  struct _RAS_ADVCONNECTIONPARAMS *v52; // [rsp+48h] [rbp-B8h]
  char *v53; // [rsp+50h] [rbp-B0h]
  int v54; // [rsp+60h] [rbp-A0h] BYREF
  char v55[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v18 = a8;
  Str = a5;
  v53 = a11;
  *((_QWORD *)this + 3) = a2;
  v51 = a15;
  v52 = a16;
  *((_DWORD *)this + 1108) = *(_DWORD *)a12;
  *((_DWORD *)this + 1109) = *((_DWORD *)a12 + 3);
  *((_DWORD *)this + 89) = *((_DWORD *)a12 + 2);
  *((_DWORD *)this + 88) = *((_DWORD *)a12 + 4);
  *((_DWORD *)this + 1110) = *((_DWORD *)a12 + 5);
  *((_QWORD *)this + 8) = a14;
  v50 = a3;
  v19 = (__int128)*a13;
  v54 = 0;
  *(_OWORD *)((char *)this + 44) = v19;
  memset_0(v55, 0, sizeof(v55));
  if ( !pszSrc )
    goto LABEL_8;
  StringCbCopyA((STRSAFE_LPSTR)this + 400, 0x101u, pszSrc);
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v20, (char *)this + 400);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, L"Username: %hs", (char *)this + 400);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
LABEL_8:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a7 )
  {
    StringCbCopyA((STRSAFE_LPSTR)this + 657, 0x101u, a7);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a8 )
  {
    StringCbCopyA((STRSAFE_LPSTR)this + 1176, 0x10u, a8);
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v22, (char *)this + 1176);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    v18 = 0;
    if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"Domain: %hs", (char *)this + 1176);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        *((_QWORD *)&xmmword_1800AABC0 + 1),
        &v54);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( Src && (unsigned int)Size <= 0x101 )
  {
    memcpy_0((char *)this + 914, Src, (unsigned int)Size);
    *((_DWORD *)this + 293) = Size;
  }
  else
  {
    if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x20000) != 0 && *((_BYTE *)v21 + 25) >= 2u )
      WPP_SF_d(v21[2], 13, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, (unsigned int)Size);
    if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
    {
      LOWORD(v54) = (_WORD)v18;
      FormatRRASErrorString(&v54, L"Un-expected PSK size: %d received. Ignoring the PSK.", (unsigned int)Size);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        *((_QWORD *)&xmmword_1800AABC0 + 1),
        &v54);
    }
  }
  PrintGuid((STRSAFE_LPSTR)this + 360);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v23, (char *)this + 360);
  }
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, L"CorrelationGuid: %hs", (char *)this + 360);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
  }
  v24 = -1;
  v25 = v50;
  v26 = (*((_DWORD *)this + 1108) & 0x8000000) != 0;
  *((_BYTE *)this + 4428) = (*((_DWORD *)this + 1108) & 8) != 0;
  *((_BYTE *)this + 4429) = v26;
  if ( v25 && *v25 != (_BYTE)v18 )
  {
    v27 = -1;
    do
      ++v27;
    while ( v25[v27] != (_BYTE)v18 );
    ProcessHeap = GetProcessHeap();
    v29 = (char *)HeapAlloc(ProcessHeap, 8u, v27 + 1);
    *((_QWORD *)this + 9) = v29;
    if ( !v29 )
      return 8;
    v30 = -1;
    do
      ++v30;
    while ( v25[v30] != (_BYTE)v18 );
    StringCchCopyA(v29, v30 + 1, v25);
  }
  if ( !a4 || *a4 == (_BYTE)v18 )
    goto LABEL_48;
  v31 = -1;
  do
    ++v31;
  while ( a4[v31] != (_BYTE)v18 );
  v32 = GetProcessHeap();
  v33 = (char *)HeapAlloc(v32, 8u, v31 + 1);
  *((_QWORD *)this + 10) = v33;
  if ( !v33 )
    return 8;
  do
    ++v24;
  while ( a4[v24] != (_BYTE)v18 );
  StringCchCopyA(v33, v24 + 1, a4);
LABEL_48:
  v34 = Str;
  v35 = strstr(Str, ":");
  v36 = Str;
  if ( v35 )
  {
    Str = v18;
    *((_BYTE *)this + 4284) = (_BYTE)v18;
    RtlIpv6StringToAddressA(v36, (PCSTR *)&Str, (struct in6_addr *)((char *)this + 4312));
  }
  else
  {
    *((_BYTE *)this + 4284) = 1;
    *((_DWORD *)this + 1073) = inet_addr(v36);
  }
  v40 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, v38, (_DWORD)v25, (__int64)a4);
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, L"PhonebookPath: [%hs], EntryName: [%hs]", v25, a4);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x20000) != 0 && *((_BYTE *)v40 + 25) >= 3u )
  {
    WPP_SF_s(v40[2], 16, v38, v34);
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, L"Destination Address: [%hs]", v34);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x20000) != 0 && *((_BYTE *)v40 + 25) >= 3u )
  {
    WPP_SF_dd(
      v40[2],
      17,
      &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids,
      *((unsigned int *)this + 1108),
      *((_DWORD *)this + 1109));
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    v41 = *((unsigned int *)this + 1109);
    v42 = *((unsigned int *)this + 1108);
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, L"ConfigFlags: 0x%08x, ProtocolConfigFlags: 0x%08x", v42, v41);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x20000) != 0 && *((_BYTE *)v40 + 25) >= 3u )
    WPP_SF_dd(
      v40[2],
      18,
      &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids,
      *((unsigned int *)this + 89),
      *((_DWORD *)this + 88));
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    v43 = *((unsigned int *)this + 88);
    v44 = *((unsigned int *)this + 89);
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, L"IdleTimeOut: %d, NetworkOutageTime: %d", v44, v43);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
  }
  v45 = ConnectionParams::SetInterfaceInfo(this, v51);
  v46 = v45;
  if ( v45 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, v45);
    }
    if ( *((char **)&xmmword_1800AABC0 + 1) == v18 )
      return v46;
    v47 = L"SetInterfaceInfo failed: %x";
    goto LABEL_83;
  }
  v48 = ConnectionParams::SetAdvConnectionParams(this, v52);
  v46 = v48;
  if ( !v48 )
  {
    if ( *((_DWORD *)this + 368) == 2 )
      *((_DWORD *)this + 1108) |= 0x100000u;
    ConnectionParams::ParseStringParams(this, v53);
    return v46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, v48);
  }
  if ( *((char **)&xmmword_1800AABC0 + 1) != v18 )
  {
    v47 = L"SetAdvConnectionParams failed: %x";
LABEL_83:
    LOWORD(v54) = (_WORD)v18;
    FormatRRASErrorString(&v54, v47, v46);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v54);
  }
  return v46;
}

```

## disassembly

```asm
0x18005b858  mov     [rsp-8+arg_8], rbx
0x18005b85d  push    rbp
0x18005b85e  push    rsi
0x18005b85f  push    rdi
0x18005b860  push    r12
0x18005b862  push    r13
0x18005b864  push    r14
0x18005b866  push    r15
0x18005b868  lea     rbp, [rsp-770h]
0x18005b870  sub     rsp, 870h
0x18005b877  mov     rax, cs:__security_cookie
0x18005b87e  xor     rax, rsp
0x18005b881  mov     [rbp+7A0h+var_40], rax
0x18005b888  mov     rax, [rbp+7A0h+arg_20]
0x18005b88f  mov     rdi, rcx
0x18005b892  mov     r14, [rbp+7A0h+pszSrc]
0x18005b899  mov     r13, r9
0x18005b89c  mov     rsi, [rbp+7A0h+arg_30]
0x18005b8a3  mov     r15, [rbp+7A0h+arg_38]
0x18005b8aa  mov     r12, [rbp+7A0h+Src]
0x18005b8b1  mov     [rsp+8A0h+Str], rax
0x18005b8b6  mov     rax, [rbp+7A0h+arg_50]
0x18005b8bd  mov     [rsp+8A0h+var_850], rax
0x18005b8c2  mov     rax, [rbp+7A0h+arg_70]
0x18005b8c9  mov     [rcx+18h], rdx
0x18005b8cd  xor     edx, edx; Val
0x18005b8cf  mov     rcx, [rbp+7A0h+arg_58]
0x18005b8d6  mov     [rsp+8A0h+var_860], rax
0x18005b8db  mov     rax, [rbp+7A0h+arg_78]
0x18005b8e2  mov     [rsp+8A0h+var_858], rax
0x18005b8e7  mov     eax, [rcx]
0x18005b8e9  mov     [rdi+1150h], eax
0x18005b8ef  mov     eax, [rcx+0Ch]
0x18005b8f2  mov     [rdi+1154h], eax
0x18005b8f8  mov     eax, [rcx+8]
0x18005b8fb  mov     [rdi+164h], eax
0x18005b901  mov     eax, [rcx+10h]
0x18005b904  mov     [rdi+160h], eax
0x18005b90a  mov     eax, [rcx+14h]
0x18005b90d  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18005b912  mov     [rdi+1158h], eax
0x18005b918  mov     rax, [rbp+7A0h+arg_68]
0x18005b91f  mov     [rdi+40h], rax
0x18005b923  mov     rax, [rbp+7A0h+arg_60]
0x18005b92a  mov     [rsp+8A0h+var_868], r8
0x18005b92f  mov     r8d, 7FCh; Size
0x18005b935  movups  xmm0, xmmword ptr [rax]
0x18005b938  xor     eax, eax
0x18005b93a  mov     [rsp+8A0h+var_840], eax
0x18005b93e  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x18005b943  call    memset_0
0x18005b948  test    r14, r14
0x18005b94b  jz      loc_18005B9E8
0x18005b951  lea     rbx, [rdi+190h]
0x18005b958  mov     r8, r14; pszSrc
0x18005b95b  mov     rcx, rbx; pszDest
0x18005b95e  mov     edx, 101h; cbDest
0x18005b963  call    StringCbCopyA
0x18005b968  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b96f  lea     r14, WPP_GLOBAL_Control
0x18005b976  cmp     rcx, r14
0x18005b979  jz      short loc_18005B9A2
0x18005b97b  test    dword ptr [rcx+1Ch], 20000h
0x18005b982  jz      short loc_18005B9A2
0x18005b984  cmp     byte ptr [rcx+19h], 3
0x18005b988  jb      short loc_18005B9A2
0x18005b98a  mov     rcx, [rcx+10h]
0x18005b98e  mov     edx, 0Bh
0x18005b993  mov     r9, rbx
0x18005b996  call    WPP_SF_s
0x18005b99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9a2  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18005b9aa  jz      short loc_18005B9F6
0x18005b9ac  xor     eax, eax
0x18005b9ae  lea     rdx, aUsernameHs; "Username: %hs"
0x18005b9b5  mov     r8, rbx
0x18005b9b8  mov     word ptr [rsp+8A0h+var_840], ax
0x18005b9bd  lea     rcx, [rsp+8A0h+var_840]
0x18005b9c2  call    FormatRRASErrorString
0x18005b9c7  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005b9ce  lea     r8, [rsp+8A0h+var_840]
0x18005b9d3  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005b9da  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005b9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9e6  jmp     short loc_18005B9EF
0x18005b9e8  lea     r14, WPP_GLOBAL_Control
0x18005b9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9f6  test    rsi, rsi
0x18005b9f9  jz      short loc_18005BA16
0x18005b9fb  lea     rcx, [rdi+291h]; pszDest
0x18005ba02  mov     r8, rsi; pszSrc
0x18005ba05  mov     edx, 101h; cbDest
0x18005ba0a  call    StringCbCopyA
0x18005ba0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba16  test    r15, r15
0x18005ba19  jz      loc_18005BAB5
0x18005ba1f  lea     rbx, [rdi+498h]
0x18005ba26  mov     r8, r15; pszSrc
0x18005ba29  mov     rcx, rbx; pszDest
0x18005ba2c  mov     edx, 10h; cbDest
0x18005ba31  call    StringCbCopyA
0x18005ba36  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba3d  cmp     rcx, r14
0x18005ba40  jz      short loc_18005BA69
0x18005ba42  test    dword ptr [rcx+1Ch], 20000h
0x18005ba49  jz      short loc_18005BA69
0x18005ba4b  cmp     byte ptr [rcx+19h], 3
0x18005ba4f  jb      short loc_18005BA69
0x18005ba51  mov     rcx, [rcx+10h]
0x18005ba55  mov     edx, 0Ch
0x18005ba5a  mov     r9, rbx
0x18005ba5d  call    WPP_SF_s
0x18005ba62  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba69  xor     r15d, r15d
0x18005ba6c  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005ba73  jz      short loc_18005BAB5
0x18005ba75  mov     r8, rbx
0x18005ba78  mov     word ptr [rsp+8A0h+var_840], r15w
0x18005ba7e  lea     rdx, aDomainHs; "Domain: %hs"
0x18005ba85  lea     rcx, [rsp+8A0h+var_840]
0x18005ba8a  call    FormatRRASErrorString
0x18005ba8f  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005ba96  lea     r8, [rsp+8A0h+var_840]
0x18005ba9b  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005baa2  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005baa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005baae  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bab5  mov     ebx, dword ptr [rbp+7A0h+Size]
0x18005babb  test    r12, r12
0x18005babe  jz      short loc_18005BAE2
0x18005bac0  cmp     ebx, 101h
0x18005bac6  ja      short loc_18005BAE2
0x18005bac8  mov     r8d, ebx; Size
0x18005bacb  lea     rcx, [rdi+392h]; void *
0x18005bad2  mov     rdx, r12; Src
0x18005bad5  call    memcpy_0
0x18005bada  mov     [rdi+494h], ebx
0x18005bae0  jmp     short loc_18005BB50
0x18005bae2  cmp     rcx, r14
0x18005bae5  jz      short loc_18005BB0E
0x18005bae7  test    dword ptr [rcx+1Ch], 20000h
0x18005baee  jz      short loc_18005BB0E
0x18005baf0  cmp     byte ptr [rcx+19h], 2
0x18005baf4  jb      short loc_18005BB0E
0x18005baf6  mov     rcx, [rcx+10h]
0x18005bafa  lea     r8, WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids
0x18005bb01  mov     edx, 0Dh
0x18005bb06  mov     r9d, ebx
0x18005bb09  call    WPP_SF_d
0x18005bb0e  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005bb15  jz      short loc_18005BB50
0x18005bb17  mov     r8d, ebx
0x18005bb1a  mov     word ptr [rsp+8A0h+var_840], r15w
0x18005bb20  lea     rdx, aUnExpectedPskS; "Un-expected PSK size: %d received. Igno"...
0x18005bb27  lea     rcx, [rsp+8A0h+var_840]
0x18005bb2c  call    FormatRRASErrorString
0x18005bb31  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005bb38  lea     r8, [rsp+8A0h+var_840]
0x18005bb3d  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005bb44  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb50  lea     rbx, [rdi+168h]
0x18005bb57  mov     rcx, rbx; pszDest
0x18005bb5a  lea     r8, [rdi+2Ch]
0x18005bb5e  call    PrintGuid
0x18005bb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb6a  mov     r12d, 20000h
0x18005bb70  cmp     rcx, r14
0x18005bb73  jz      short loc_18005BB92
0x18005bb75  test    [rcx+1Ch], r12d
0x18005bb79  jz      short loc_18005BB92
0x18005bb7b  cmp     byte ptr [rcx+19h], 3
0x18005bb7f  jb      short loc_18005BB92
0x18005bb81  mov     rcx, [rcx+10h]
0x18005bb85  mov     edx, 0Eh
0x18005bb8a  mov     r9, rbx
0x18005bb8d  call    WPP_SF_s
0x18005bb92  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005bb99  jz      short loc_18005BBD4
0x18005bb9b  mov     r8, rbx
0x18005bb9e  mov     word ptr [rsp+8A0h+var_840], r15w
0x18005bba4  lea     rdx, aCorrelationgui_1; "CorrelationGuid: %hs"
0x18005bbab  lea     rcx, [rsp+8A0h+var_840]
0x18005bbb0  call    FormatRRASErrorString
0x18005bbb5  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005bbbc  lea     r8, [rsp+8A0h+var_840]
0x18005bbc1  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005bbc8  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbd4  mov     ecx, [rdi+1150h]
0x18005bbda  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005bbde  mov     r14, [rsp+8A0h+var_868]
0x18005bbe3  mov     eax, ecx
0x18005bbe5  shr     eax, 3
0x18005bbe8  shr     ecx, 1Bh
0x18005bbeb  and     al, 1
0x18005bbed  and     cl, 1
0x18005bbf0  mov     [rdi+114Ch], al
0x18005bbf6  mov     [rdi+114Dh], cl
0x18005bbfc  test    r14, r14
0x18005bbff  jz      short loc_18005BC51
0x18005bc01  cmp     [r14], r15b
0x18005bc04  jz      short loc_18005BC51
0x18005bc06  mov     rbx, rsi
0x18005bc09  inc     rbx
0x18005bc0c  cmp     [r14+rbx], r15b
0x18005bc10  jnz     short loc_18005BC09
0x18005bc12  call    cs:__imp_GetProcessHeap
0x18005bc18  lea     r8, [rbx+1]; dwBytes
0x18005bc1c  mov     edx, 8; dwFlags
0x18005bc21  mov     rcx, rax; hHeap
0x18005bc24  call    cs:__imp_HeapAlloc
0x18005bc2a  mov     [rdi+48h], rax
0x18005bc2e  test    rax, rax
0x18005bc31  jz      loc_18005BCD3
0x18005bc37  mov     rdx, rsi
0x18005bc3a  inc     rdx
0x18005bc3d  cmp     [r14+rdx], r15b
0x18005bc41  jnz     short loc_18005BC3A
0x18005bc43  inc     rdx; cchDest
0x18005bc46  mov     r8, r14; pszSrc
0x18005bc49  mov     rcx, rax; pszDest
0x18005bc4c  call    StringCchCopyA
0x18005bc51  test    r13, r13
0x18005bc54  jz      short loc_18005BCA1
0x18005bc56  cmp     [r13+0], r15b
0x18005bc5a  jz      short loc_18005BCA1
0x18005bc5c  mov     rbx, rsi
0x18005bc5f  inc     rbx
0x18005bc62  cmp     [rbx+r13], r15b
0x18005bc66  jnz     short loc_18005BC5F
0x18005bc68  call    cs:__imp_GetProcessHeap
0x18005bc6e  lea     r8, [rbx+1]; dwBytes
0x18005bc72  mov     edx, 8; dwFlags
0x18005bc77  mov     rcx, rax; hHeap
0x18005bc7a  call    cs:__imp_HeapAlloc
0x18005bc80  mov     [rdi+50h], rax
0x18005bc84  test    rax, rax
0x18005bc87  jz      short loc_18005BCD3
0x18005bc89  inc     rsi
0x18005bc8c  cmp     [rsi+r13], r15b
0x18005bc90  jnz     short loc_18005BC89
0x18005bc92  lea     rdx, [rsi+1]; cchDest
0x18005bc96  mov     r8, r13; pszSrc
0x18005bc99  mov     rcx, rax; pszDest
0x18005bc9c  call    StringCchCopyA
0x18005bca1  mov     rbx, [rsp+8A0h+Str]
0x18005bca6  lea     rdx, SubStr; ":"
0x18005bcad  mov     rcx, rbx; Str
0x18005bcb0  call    cs:__imp_strstr
0x18005bcb6  mov     rcx, rbx; S
0x18005bcb9  test    rax, rax
0x18005bcbc  jnz     short loc_18005BCDD
0x18005bcbe  mov     byte ptr [rdi+10BCh], 1
0x18005bcc5  call    cs:__imp_inet_addr
0x18005bccb  mov     [rdi+10C4h], eax
0x18005bcd1  jmp     short loc_18005BCFB
0x18005bcd3  mov     eax, 8
0x18005bcd8  jmp     loc_18005C009
0x18005bcdd  lea     r8, [rdi+10D8h]; Addr
0x18005bce4  mov     [rsp+8A0h+Str], r15
0x18005bce9  lea     rdx, [rsp+8A0h+Str]; Terminator
0x18005bcee  mov     [rdi+10BCh], r15b
0x18005bcf5  call    cs:__imp_RtlIpv6StringToAddressA
0x18005bcfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd02  lea     rsi, WPP_GLOBAL_Control
0x18005bd09  cmp     rcx, rsi
0x18005bd0c  jz      short loc_18005BD32
0x18005bd0e  test    [rcx+1Ch], r12d
0x18005bd12  jz      short loc_18005BD32
0x18005bd14  cmp     byte ptr [rcx+19h], 3
0x18005bd18  jb      short loc_18005BD32
0x18005bd1a  mov     rcx, [rcx+10h]
0x18005bd1e  mov     r9, r14
0x18005bd21  mov     [rsp+8A0h+var_880], r13
0x18005bd26  call    WPP_SF_ss
0x18005bd2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd32  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005bd39  jz      short loc_18005BD7E
0x18005bd3b  mov     r9, r13
0x18005bd3e  mov     word ptr [rsp+8A0h+var_840], r15w
0x18005bd44  mov     r8, r14
0x18005bd47  lea     rdx, aPhonebookpathH; "PhonebookPath: [%hs], EntryName: [%hs]"
0x18005bd4e  lea     rcx, [rsp+8A0h+var_840]
0x18005bd53  call    FormatRRASErrorString
0x18005bd58  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005bd5f  lea     r8, [rsp+8A0h+var_840]
0x18005bd64  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005bd6b  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd77  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd7e  cmp     rcx, rsi
0x18005bd81  jz      short loc_18005BDA7
0x18005bd83  test    [rcx+1Ch], r12d
0x18005bd87  jz      short loc_18005BDA7
0x18005bd89  cmp     byte ptr [rcx+19h], 3
0x18005bd8d  jb      short loc_18005BDA7
0x18005bd8f  mov     rcx, [rcx+10h]
0x18005bd93  mov     edx, 10h
0x18005bd98  mov     r9, rbx
  ... truncated ...
```
