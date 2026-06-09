# ConnectionParams::SetInterfaceInfo(_PROTOCOL_INTERFACE_INFO &)

- ea: `0x18005c03c`
- end: `0x18005c5b1`
- name: `?SetInterfaceInfo@ConnectionParams@@QEAAKAEAU_PROTOCOL_INTERFACE_INFO@@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(ConnectionParams *this, struct _PROTOCOL_INTERFACE_INFO *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180024ef0`
- `0x18005b858`

## callees

- `0x180007794`
- `0x1800077bc`
- `0x18000a3a0`
- `0x180020ba4`
- `0x18005c03c`
- `0x18005c5b8`
- `0x180074b28`
- `0x180074b98`
- `0x180076ccc`
- `0x18007755e`
- `0x18007756a`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c379`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c2f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c2f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c2dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c36b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c2dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c36b`

## string_xrefs

- `0x18005c539`: `Demand dial interface is not added to any of the available transport protocols`

## pseudocode

```c
__int64 __fastcall ConnectionParams::SetInterfaceInfo(ConnectionParams *this, struct _PROTOCOL_INTERFACE_INFO *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // rdx
  __int64 v9; // rdx
  const wchar_t *v10; // r8
  _QWORD *v11; // r14
  HANDLE v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  struct _MPR_VPN_SELECTOR *v16; // xmm0_8
  unsigned int v17; // eax
  unsigned __int8 v18; // dl
  unsigned __int8 v19; // al
  PVOID *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r8
  unsigned int v23; // r11d
  _MPR_VPN_TRAFFIC_SELECTORS v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  *((_DWORD *)this + 368) = *(_DWORD *)a2;
  *((_QWORD *)this + 186) = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 185) = *((_QWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 2008) = *(_OWORD *)((char *)a2 + 536);
  *((_DWORD *)this + 508) = *((_DWORD *)a2 + 140);
  *((_DWORD *)this + 510) = *((_DWORD *)a2 + 142);
  *((_DWORD *)this + 522) = *((_DWORD *)a2 + 154);
  *((_DWORD *)this + 511) = *((_DWORD *)a2 + 143);
  *((_DWORD *)this + 507) = *((_DWORD *)a2 + 139);
  *((_DWORD *)this + 506) = *((_DWORD *)a2 + 138);
  *((_DWORD *)this + 800) = *((_DWORD *)a2 + 432);
  v4 = *((_DWORD *)a2 + 695);
  *((_DWORD *)this + 1063) = v4;
  if ( v4 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids);
    }
    wcsncpy_0((wchar_t *)this + 1612, (const wchar_t *)a2 + 876, 0x100u);
    wcsncpy_0((wchar_t *)this + 1869, (const wchar_t *)a2 + 1133, 0x100u);
  }
  *(_OWORD *)((char *)this + 2136) = *(_OWORD *)((char *)a2 + 664);
  *(_OWORD *)((char *)this + 2148) = *(_OWORD *)((char *)a2 + 676);
  *(_OWORD *)((char *)this + 3204) = *(_OWORD *)((char *)a2 + 1732);
  *((_DWORD *)this + 805) = *((_DWORD *)a2 + 437);
  if ( *((_DWORD *)a2 + 144) )
  {
    FreeCertificateBlob((char *)this + 2048);
    v5 = DuplicateCertificateBlob((char *)a2 + 576, (char *)this + 2048);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v7 = 22;
LABEL_13:
        WPP_SF_d(v6[2], v7, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, v5);
        goto LABEL_14;
      }
      goto LABEL_14;
    }
  }
  if ( *((_DWORD *)a2 + 150) )
  {
    FreeCertificateBlob((char *)this + 2072);
    v5 = DuplicateCertificateBlob((char *)a2 + 600, (char *)this + 2072);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v7 = 23;
        goto LABEL_13;
      }
LABEL_14:
      if ( (_QWORD)xmmword_1800AABC0 )
      {
        v8 = L"DuplicateCertificateBlob failed: %d";
LABEL_16:
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, v8, v5);
        v9 = xmmword_1800AABC0;
        v10 = (const wchar_t *)&v26;
LABEL_17:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gBaseTemplateFunc)(
          gBaseEtwContext,
          v9,
          v10);
        return v5;
      }
      return v5;
    }
  }
  v11 = (_QWORD *)*((_QWORD *)this + 258);
  if ( !*((_QWORD *)a2 + 74) )
  {
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      *((_QWORD *)this + 258) = 0;
    }
LABEL_36:
    *(_OWORD *)((char *)this + 2120) = *(_OWORD *)((char *)a2 + 648);
    v16 = (struct _MPR_VPN_SELECTOR *)*((_QWORD *)a2 + 80);
    *(_OWORD *)&v25.numTsi = *((_OWORD *)a2 + 39);
    v25.tsR = v16;
    v17 = ConnectionParams::SetTrafficSelectorInfo(this, &v25);
    v5 = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, v17);
      }
      if ( (_QWORD)xmmword_1800AABC0 )
      {
        v8 = L"SetTrafficSelectorInfo failed: %d";
        goto LABEL_16;
      }
      return v5;
    }
    if ( *((_DWORD *)this + 368) != 2 )
      return v5;
    v18 = *((_BYTE *)this + 4428);
    if ( v18 )
    {
      if ( *((_QWORD *)this + 185) != -1 )
        goto LABEL_48;
      *((_BYTE *)this + 4428) = 0;
    }
    v18 = 0;
LABEL_48:
    v19 = *((_BYTE *)this + 4429);
    if ( v19 )
    {
      if ( *((_QWORD *)this + 186) != -1 )
      {
LABEL_52:
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, v18, v19);
          v20 = (PVOID *)WPP_GLOBAL_Control;
        }
        v9 = xmmword_1800AABC0;
        if ( (_QWORD)xmmword_1800AABC0 )
        {
          v21 = *((unsigned __int8 *)this + 4429);
          v22 = *((unsigned __int8 *)this + 4428);
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, L"NegotiateIPv4: %d, NegotiateIPv6: %d", v22, v21);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
            gBaseEtwContext,
            xmmword_1800AABC0,
            &v26);
          v20 = (PVOID *)WPP_GLOBAL_Control;
          v9 = xmmword_1800AABC0;
        }
        if ( *((_BYTE *)this + 4428) || *((_BYTE *)this + 4429) )
        {
          *(_QWORD *)((char *)this + 2164) = *(_QWORD *)((char *)a2 + 692);
          StringCchCopyW((STRSAFE_LPWSTR)this + 1086, 0x101u, (STRSAFE_LPCWSTR)a2 + 350);
          StringCchCopyW((STRSAFE_LPWSTR)this + 1343, v23, (STRSAFE_LPCWSTR)a2 + 607);
          return v5;
        }
        v5 = 720;
        if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x20000) != 0 && *((_BYTE *)v20 + 25) )
        {
          WPP_SF_(v20[2], 27, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids);
          v9 = xmmword_1800AABC0;
        }
        if ( v9 )
        {
          v10 = L"Demand dial interface is not added to any of the available transport protocols";
          goto LABEL_17;
        }
        return v5;
      }
      *((_BYTE *)this + 4429) = 0;
    }
    v19 = 0;
    goto LABEL_52;
  }
  if ( v11
    || (v12 = GetProcessHeap(), v5 = 8, v13 = HeapAlloc(v12, 8u, 0x18u), *((_QWORD *)this + 258) = v13, (v11 = v13) != 0) )
  {
    v14 = *((_QWORD *)a2 + 74);
    *(_OWORD *)v11 = *(_OWORD *)v14;
    v11[2] = *(_QWORD *)(v14 + 16);
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids, 8);
  }
  if ( (_QWORD)xmmword_1800AABC0 )
  {
    v8 = L"Failed to allocate memory: %d";
    goto LABEL_16;
  }
  return v5;
}

```

## disassembly

```asm
0x18005c03c  mov     [rsp-8+arg_10], rbx
0x18005c041  push    rbp
0x18005c042  push    rsi
0x18005c043  push    rdi
0x18005c044  push    r12
0x18005c046  push    r13
0x18005c048  push    r14
0x18005c04a  push    r15
0x18005c04c  lea     rbp, [rsp-760h]
0x18005c054  sub     rsp, 860h
0x18005c05b  mov     rax, cs:__security_cookie
0x18005c062  xor     rax, rsp
0x18005c065  mov     [rbp+790h+var_40], rax
0x18005c06c  mov     rsi, rdx
0x18005c06f  mov     rdi, rcx
0x18005c072  xor     r15d, r15d
0x18005c075  lea     rcx, [rsp+890h+var_83C]; void *
0x18005c07a  xor     edx, edx; Val
0x18005c07c  mov     [rsp+890h+var_840], r15d
0x18005c081  mov     r8d, 7FCh; Size
0x18005c087  call    memset_0
0x18005c08c  mov     eax, [rsi]
0x18005c08e  lea     r12, WPP_GLOBAL_Control
0x18005c095  mov     [rdi+5C0h], eax
0x18005c09b  lea     r13, WPP_e8479ce5123c37bed1cf6d9fdb85020b_Traceguids
0x18005c0a2  mov     rax, [rsi+10h]
0x18005c0a6  mov     [rdi+5D0h], rax
0x18005c0ad  mov     rax, [rsi+8]
0x18005c0b1  mov     [rdi+5C8h], rax
0x18005c0b8  movups  xmm0, xmmword ptr [rsi+218h]
0x18005c0bf  movdqu  xmmword ptr [rdi+7D8h], xmm0
0x18005c0c7  mov     eax, [rsi+230h]
0x18005c0cd  mov     [rdi+7F0h], eax
0x18005c0d3  mov     eax, [rsi+238h]
0x18005c0d9  mov     [rdi+7F8h], eax
0x18005c0df  mov     eax, [rsi+268h]
0x18005c0e5  mov     [rdi+828h], eax
0x18005c0eb  mov     eax, [rsi+23Ch]
0x18005c0f1  mov     [rdi+7FCh], eax
0x18005c0f7  mov     eax, [rsi+22Ch]
0x18005c0fd  mov     [rdi+7ECh], eax
0x18005c103  mov     eax, [rsi+228h]
0x18005c109  mov     [rdi+7E8h], eax
0x18005c10f  mov     eax, [rsi+6C0h]
0x18005c115  mov     [rdi+0C80h], eax
0x18005c11b  mov     eax, [rsi+0ADCh]
0x18005c121  mov     [rdi+109Ch], eax
0x18005c127  cmp     eax, 1
0x18005c12a  jnz     short loc_18005C187
0x18005c12c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c133  cmp     rcx, r12
0x18005c136  jz      short loc_18005C156
0x18005c138  test    dword ptr [rcx+1Ch], 20000h
0x18005c13f  jz      short loc_18005C156
0x18005c141  cmp     byte ptr [rcx+19h], 4
0x18005c145  jb      short loc_18005C156
0x18005c147  mov     rcx, [rcx+10h]
0x18005c14b  lea     edx, [rax+14h]
0x18005c14e  mov     r8, r13
0x18005c151  call    WPP_SF_
0x18005c156  mov     ebx, 100h
0x18005c15b  lea     rdx, [rsi+6D8h]; Source
0x18005c162  mov     r8d, ebx; Count
0x18005c165  lea     rcx, [rdi+0C98h]; Destination
0x18005c16c  call    wcsncpy_0
0x18005c171  lea     rdx, [rsi+8DAh]; Source
0x18005c178  mov     r8d, ebx; Count
0x18005c17b  lea     rcx, [rdi+0E9Ah]; Destination
0x18005c182  call    wcsncpy_0
0x18005c187  movups  xmm0, xmmword ptr [rsi+298h]
0x18005c18e  lea     r14, [rsi+240h]
0x18005c195  movups  xmmword ptr [rdi+858h], xmm0
0x18005c19c  movups  xmm1, xmmword ptr [rsi+2A4h]
0x18005c1a3  movups  xmmword ptr [rdi+864h], xmm1
0x18005c1aa  movups  xmm0, xmmword ptr [rsi+6C4h]
0x18005c1b1  movups  xmmword ptr [rdi+0C84h], xmm0
0x18005c1b8  mov     eax, [rsi+6D4h]
0x18005c1be  mov     [rdi+0C94h], eax
0x18005c1c4  cmp     [r14], r15d
0x18005c1c7  jz      loc_18005C267
0x18005c1cd  lea     rbx, [rdi+800h]
0x18005c1d4  mov     rcx, rbx
0x18005c1d7  call    FreeCertificateBlob
0x18005c1dc  mov     rdx, rbx
0x18005c1df  mov     rcx, r14
0x18005c1e2  call    DuplicateCertificateBlob
0x18005c1e7  mov     ebx, eax
0x18005c1e9  test    eax, eax
0x18005c1eb  jz      short loc_18005C267
0x18005c1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1f4  cmp     rcx, r12
0x18005c1f7  jz      short loc_18005C21C
0x18005c1f9  test    dword ptr [rcx+1Ch], 40000h
0x18005c200  jz      short loc_18005C21C
0x18005c202  cmp     byte ptr [rcx+19h], 1
0x18005c206  jb      short loc_18005C21C
0x18005c208  mov     edx, 16h
0x18005c20d  mov     rcx, [rcx+10h]
0x18005c211  mov     r9d, ebx
0x18005c214  mov     r8, r13
0x18005c217  call    WPP_SF_d
0x18005c21c  cmp     qword ptr cs:xmmword_1800AABC0, r15
0x18005c223  jz      loc_18005C585
0x18005c229  lea     rdx, aDuplicatecerti; "DuplicateCertificateBlob failed: %d"
0x18005c230  mov     r8d, ebx
0x18005c233  mov     word ptr [rsp+890h+var_840], r15w
0x18005c239  lea     rcx, [rsp+890h+var_840]
0x18005c23e  call    FormatRRASErrorString
0x18005c243  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005c24a  lea     r8, [rsp+890h+var_840]
0x18005c24f  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005c256  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c262  jmp     loc_18005C585
0x18005c267  lea     r14, [rsi+258h]
0x18005c26e  cmp     [r14], r15d
0x18005c271  jz      short loc_18005C2C4
0x18005c273  lea     rbx, [rdi+818h]
0x18005c27a  mov     rcx, rbx
0x18005c27d  call    FreeCertificateBlob
0x18005c282  mov     rdx, rbx
0x18005c285  mov     rcx, r14
0x18005c288  call    DuplicateCertificateBlob
0x18005c28d  mov     ebx, eax
0x18005c28f  test    eax, eax
0x18005c291  jz      short loc_18005C2C4
0x18005c293  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c29a  cmp     rcx, r12
0x18005c29d  jz      loc_18005C21C
0x18005c2a3  test    dword ptr [rcx+1Ch], 40000h
0x18005c2aa  jz      loc_18005C21C
0x18005c2b0  cmp     byte ptr [rcx+19h], 1
0x18005c2b4  jb      loc_18005C21C
0x18005c2ba  mov     edx, 17h
0x18005c2bf  jmp     loc_18005C20D
0x18005c2c4  mov     r14, [rdi+810h]
0x18005c2cb  cmp     [rsi+250h], r15
0x18005c2d2  jz      loc_18005C366
0x18005c2d8  test    r14, r14
0x18005c2db  jnz     short loc_18005C34B
0x18005c2dd  call    cs:__imp_GetProcessHeap
0x18005c2e3  lea     ebx, [r14+8]
0x18005c2e7  mov     rcx, rax; hHeap
0x18005c2ea  mov     edx, ebx; dwFlags
0x18005c2ec  lea     r8d, [r14+18h]; dwBytes
0x18005c2f0  call    cs:__imp_HeapAlloc
0x18005c2f6  mov     [rdi+810h], rax
0x18005c2fd  mov     r14, rax
0x18005c300  test    rax, rax
0x18005c303  jnz     short loc_18005C34B
0x18005c305  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c30c  cmp     rcx, r12
0x18005c30f  jz      short loc_18005C332
0x18005c311  test    dword ptr [rcx+1Ch], 40000h
0x18005c318  jz      short loc_18005C332
0x18005c31a  cmp     byte ptr [rcx+19h], 1
0x18005c31e  jb      short loc_18005C332
0x18005c320  mov     rcx, [rcx+10h]
0x18005c324  lea     edx, [rbx+10h]
0x18005c327  mov     r9d, ebx
0x18005c32a  mov     r8, r13
0x18005c32d  call    WPP_SF_d
0x18005c332  cmp     qword ptr cs:xmmword_1800AABC0, r15
0x18005c339  jz      loc_18005C585
0x18005c33f  lea     rdx, aFailedToAlloca_2; "Failed to allocate memory: %d"
0x18005c346  jmp     loc_18005C230
0x18005c34b  mov     rax, [rsi+250h]
0x18005c352  movups  xmm0, xmmword ptr [rax]
0x18005c355  movups  xmmword ptr [r14], xmm0
0x18005c359  movsd   xmm1, qword ptr [rax+10h]
0x18005c35e  movsd   qword ptr [r14+10h], xmm1
0x18005c364  jmp     short loc_18005C386
0x18005c366  test    r14, r14
0x18005c369  jz      short loc_18005C386
0x18005c36b  call    cs:__imp_GetProcessHeap
0x18005c371  mov     r8, r14; lpMem
0x18005c374  xor     edx, edx; dwFlags
0x18005c376  mov     rcx, rax; hHeap
0x18005c379  call    cs:__imp_HeapFree
0x18005c37f  mov     [rdi+810h], r15
0x18005c386  movups  xmm0, xmmword ptr [rsi+288h]
0x18005c38d  lea     rdx, [rsp+890h+var_860]; struct _MPR_VPN_TRAFFIC_SELECTORS
0x18005c392  mov     rcx, rdi; this
0x18005c395  movdqu  xmmword ptr [rdi+848h], xmm0
0x18005c39d  movups  xmm1, xmmword ptr [rsi+270h]
0x18005c3a4  movsd   xmm0, qword ptr [rsi+280h]
0x18005c3ac  movaps  xmmword ptr [rsp+890h+var_860.numTsi], xmm1
0x18005c3b1  movsd   [rsp+890h+var_860.tsR], xmm0
0x18005c3b7  call    ?SetTrafficSelectorInfo@ConnectionParams@@AEAAKU_MPR_VPN_TRAFFIC_SELECTORS@@@Z; ConnectionParams::SetTrafficSelectorInfo(_MPR_VPN_TRAFFIC_SELECTORS)
0x18005c3bc  mov     ebx, eax
0x18005c3be  test    eax, eax
0x18005c3c0  jz      short loc_18005C40A
0x18005c3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3c9  cmp     rcx, r12
0x18005c3cc  jz      short loc_18005C3F1
0x18005c3ce  test    dword ptr [rcx+1Ch], 40000h
0x18005c3d5  jz      short loc_18005C3F1
0x18005c3d7  cmp     byte ptr [rcx+19h], 1
0x18005c3db  jb      short loc_18005C3F1
0x18005c3dd  mov     rcx, [rcx+10h]
0x18005c3e1  mov     edx, 19h
0x18005c3e6  mov     r9d, eax
0x18005c3e9  mov     r8, r13
0x18005c3ec  call    WPP_SF_d
0x18005c3f1  cmp     qword ptr cs:xmmword_1800AABC0, r15
0x18005c3f8  jz      loc_18005C585
0x18005c3fe  lea     rdx, aSettrafficsele; "SetTrafficSelectorInfo failed: %d"
0x18005c405  jmp     loc_18005C230
0x18005c40a  cmp     dword ptr [rdi+5C0h], 2
0x18005c411  jnz     loc_18005C585
0x18005c417  mov     dl, [rdi+114Ch]
0x18005c41d  test    dl, dl
0x18005c41f  jz      short loc_18005C432
0x18005c421  cmp     qword ptr [rdi+5C8h], 0FFFFFFFFFFFFFFFFh
0x18005c429  jnz     short loc_18005C435
0x18005c42b  mov     [rdi+114Ch], r15b
0x18005c432  mov     dl, r15b
0x18005c435  mov     al, [rdi+114Dh]
0x18005c43b  test    al, al
0x18005c43d  jz      short loc_18005C450
0x18005c43f  cmp     qword ptr [rdi+5D0h], 0FFFFFFFFFFFFFFFFh
0x18005c447  jnz     short loc_18005C453
0x18005c449  mov     [rdi+114Dh], r15b
0x18005c450  mov     al, r15b
0x18005c453  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c45a  cmp     rcx, r12
0x18005c45d  jz      short loc_18005C491
0x18005c45f  test    dword ptr [rcx+1Ch], 20000h
0x18005c466  jz      short loc_18005C491
0x18005c468  cmp     byte ptr [rcx+19h], 3
0x18005c46c  jb      short loc_18005C491
0x18005c46e  mov     rcx, [rcx+10h]
0x18005c472  mov     r8, r13
0x18005c475  movzx   eax, al
0x18005c478  movzx   r9d, dl
0x18005c47c  mov     edx, 1Ah
0x18005c481  mov     [rsp+890h+var_870], eax
0x18005c485  call    WPP_SF_dd
0x18005c48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c491  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005c498  test    rdx, rdx
0x18005c49b  jz      short loc_18005C4F1
0x18005c49d  movzx   r9d, byte ptr [rdi+114Dh]
0x18005c4a5  lea     rdx, aNegotiateipv4D; "NegotiateIPv4: %d, NegotiateIPv6: %d"
0x18005c4ac  movzx   r8d, byte ptr [rdi+114Ch]
0x18005c4b4  lea     rcx, [rsp+890h+var_840]
0x18005c4b9  mov     word ptr [rsp+890h+var_840], r15w
0x18005c4bf  call    FormatRRASErrorString
0x18005c4c4  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005c4cb  lea     r8, [rsp+890h+var_840]
0x18005c4d0  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005c4d7  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4ea  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005c4f1  cmp     [rdi+114Ch], r15b
0x18005c4f8  jnz     short loc_18005C545
0x18005c4fa  cmp     [rdi+114Dh], r15b
0x18005c501  jnz     short loc_18005C545
0x18005c503  mov     ebx, 2D0h
0x18005c508  cmp     rcx, r12
0x18005c50b  jz      short loc_18005C534
0x18005c50d  test    dword ptr [rcx+1Ch], 20000h
0x18005c514  jz      short loc_18005C534
0x18005c516  cmp     byte ptr [rcx+19h], 1
0x18005c51a  jb      short loc_18005C534
0x18005c51c  mov     rcx, [rcx+10h]
0x18005c520  mov     edx, 1Bh
0x18005c525  mov     r8, r13
0x18005c528  call    WPP_SF_
0x18005c52d  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005c534  test    rdx, rdx
0x18005c537  jz      short loc_18005C585
0x18005c539  lea     r8, aDemandDialInte; "Demand dial interface is not added to a"...
0x18005c540  jmp     loc_18005C24F
0x18005c545  mov     rax, [rsi+2B4h]
0x18005c54c  lea     r8, [rsi+2BCh]; pszSrc
0x18005c553  mov     r11d, 101h
0x18005c559  mov     [rdi+874h], rax
0x18005c560  mov     edx, r11d; cchDest
0x18005c563  lea     rcx, [rdi+87Ch]; pszDest
0x18005c56a  call    StringCchCopyW
0x18005c56f  lea     r8, [rsi+4BEh]; pszSrc
0x18005c576  mov     edx, r11d; cchDest
0x18005c579  lea     rcx, [rdi+0A7Eh]; pszDest
0x18005c580  call    StringCchCopyW
0x18005c585  mov     eax, ebx
0x18005c587  mov     rcx, [rbp+790h+var_40]
0x18005c58e  xor     rcx, rsp; StackCookie
0x18005c591  call    __security_check_cookie
0x18005c596  mov     rbx, [rsp+890h+arg_10]
0x18005c59e  add     rsp, 860h
0x18005c5a5  pop     r15
0x18005c5a7  pop     r14
0x18005c5a9  pop     r13
0x18005c5ab  pop     r12
0x18005c5ad  pop     rdi
0x18005c5ae  pop     rsi
0x18005c5af  pop     rbp
0x18005c5b0  retn
  ... truncated ...
```
