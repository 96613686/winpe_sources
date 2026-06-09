# AllocateAndGetIpAddrTable

- ea: `0x18006f8a8`
- end: `0x18006fc65`
- name: `AllocateAndGetIpAddrTable`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180070800`

## callees

- `0x180069a8c`
- `0x18006f864`
- `0x18006f8a8`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fb84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fbca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fb84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fbca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fa46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fb9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fa46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fb9f`
- `IPHLPAPI!GetIpAddrTable` at `0x18006f9f5`
- `IPHLPAPI!GetIpAddrTable` at `0x18006faf0`
- `IPHLPAPI!GetIpAddrTable` at `0x18006f9f5`
- `IPHLPAPI!GetIpAddrTable` at `0x18006faf0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006f9cb`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006f9cb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006f9d6`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006fbdb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006f9d6`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006fbdb`

## string_xrefs

- `0x18006fb0f`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18006fb61`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpAddrTable(
        LPVOID *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        NET_IF_COMPARTMENT_ID CompartmentId)
{
  int v7; // r14d
  __int64 v8; // rdx
  __int64 result; // rax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r15d
  DWORD IpAddrTable; // eax
  DWORD v12; // ebx
  const wchar_t *v13; // rdx
  const CHAR *v14; // rcx
  struct _MIB_IPADDRTABLE *v15; // rax
  _DWORD *v16; // rax
  ULONG pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+6Ch] [rbp-94h]
  __int128 v21; // [rsp+7Ch] [rbp-84h]
  int v22; // [rsp+8Ch] [rbp-74h]
  int v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  pdwSize = 0;
  v23 = 0;
  memset(v18, 0, sizeof(v18));
  memset_0(v24, 0, sizeof(v24));
  v7 = 1;
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  if ( CompartmentId != 1 && unk_1800AB320 || xmmword_1800AB328 != 0 || (v8 = unk_1800AB338) != 0 )
  {
    result = NsiGetRoutingDomainIdForCompartment(CompartmentId, v18);
    if ( (_DWORD)result )
      return result;
    v8 = unk_1800AB338;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v19) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v8,
        L"AllocateAndGetIpAddrTable Begin",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable Begin");
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpAddrTable = SetCurrentThreadCompartmentId(CompartmentId);
  v12 = IpAddrTable;
  if ( IpAddrTable )
  {
    v7 = 0;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800AB328 + 1) )
        goto LABEL_29;
      v13 = L"AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
      goto LABEL_26;
    }
    v14 = "AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_28;
  }
  pdwSize = 0;
  IpAddrTable = GetIpAddrTable(0, &pdwSize, 0);
  v12 = IpAddrTable;
  if ( IpAddrTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800AB328 + 1) )
        goto LABEL_29;
      v13 = L"AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_26:
      LOWORD(v19) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, v13, IpAddrTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB328 + 1),
        &v23,
        v18,
        0,
        &v19);
      goto LABEL_29;
    }
    v14 = "AllocateAndGetIpNetTable : error %d getting address table size";
LABEL_28:
    TraceHlp(v14);
    goto LABEL_29;
  }
  pdwSize += 120;
  v15 = (struct _MIB_IPADDRTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v15;
  if ( !v15 )
    goto LABEL_18;
  v12 = GetIpAddrTable(v15, &pdwSize, 0);
LABEL_29:
  if ( v12 != 232 )
  {
    if ( !v12 )
      goto LABEL_37;
LABEL_35:
    if ( *a1 )
    {
      HeapFree(a3, 0, *a1);
      *a1 = 0;
    }
    goto LABEL_37;
  }
  if ( *a1 )
  {
    HeapFree(a3, 0, *a1);
    *a1 = 0;
  }
  pdwSize = 36;
  v16 = HeapAlloc(a3, 0x40u, 0x24u);
  *a1 = v16;
  if ( !v16 )
  {
LABEL_18:
    v12 = 14;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800AB328 + 1) )
      {
        LOWORD(v23) = 0;
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v23, L"AllocateAndGetIpAddrTable : error %d allocating %d bytes", 14, pdwSize);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800AB328 + 1),
          &v23,
          v18,
          0,
          &v19);
      }
    }
    else
    {
      TraceHlp("AllocateAndGetIpAddrTable : error %d allocating %d bytes");
    }
    goto LABEL_35;
  }
  *v16 = 0;
  v12 = 0;
LABEL_37:
  if ( v7 )
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( unk_1800AB338 )
    {
      LOWORD(v19) = 0;
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800AB338,
        L"AllocateAndGetIpAddrTable End",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpAddrTable End");
  }
  return v12;
}

```

## disassembly

```asm
0x18006f8a8  mov     [rsp-8+arg_8], rbx
0x18006f8ad  mov     [rsp-8+arg_18], rsi
0x18006f8b2  push    rbp
0x18006f8b3  push    rdi
0x18006f8b4  push    r12
0x18006f8b6  push    r14
0x18006f8b8  push    r15
0x18006f8ba  lea     rbp, [rsp-7A0h]
0x18006f8c2  sub     rsp, 8A0h
0x18006f8c9  mov     rax, cs:__security_cookie
0x18006f8d0  xor     rax, rsp
0x18006f8d3  mov     [rbp+7C0h+var_30], rax
0x18006f8da  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006f8e1  mov     rsi, r8
0x18006f8e4  mov     rdi, rcx
0x18006f8e7  xor     r12d, r12d
0x18006f8ea  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18006f8ee  xor     edx, edx; Val
0x18006f8f0  mov     [rsp+8C0h+pdwSize], r12d
0x18006f8f5  mov     r8d, 7FCh; Size
0x18006f8fb  mov     [rbp+7C0h+var_830], r12d
0x18006f8ff  movdqu  [rsp+8C0h+var_878], xmm0
0x18006f905  call    memset_0
0x18006f90a  mov     ebx, [rbp+7C0h+CompartmentId]
0x18006f910  lea     r14d, [r12+1]
0x18006f915  xorps   xmm0, xmm0
0x18006f918  mov     [rsp+8C0h+var_858], r12d
0x18006f91d  xor     eax, eax
0x18006f91f  mov     [rbp+7C0h+var_834], eax
0x18006f922  movups  [rsp+8C0h+var_854], xmm0
0x18006f927  movups  [rsp+8C0h+var_844], xmm0
0x18006f92c  movups  [rsp+8C0h+var_868], xmm0
0x18006f931  cmp     ebx, r14d
0x18006f934  jz      short loc_18006F93F
0x18006f936  cmp     qword ptr cs:unk_1800AB320, r12
0x18006f93d  jnz     short loc_18006F95D
0x18006f93f  cmp     qword ptr cs:xmmword_1800AB328, r12
0x18006f946  jnz     short loc_18006F95D
0x18006f948  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006f94f  jnz     short loc_18006F95D
0x18006f951  mov     rdx, qword ptr cs:unk_1800AB338
0x18006f958  test    rdx, rdx
0x18006f95b  jz      short loc_18006F978
0x18006f95d  lea     rdx, [rsp+8C0h+var_878]
0x18006f962  mov     ecx, ebx
0x18006f964  call    NsiGetRoutingDomainIdForCompartment
0x18006f969  test    eax, eax
0x18006f96b  jnz     loc_18006FC3A
0x18006f971  mov     rdx, qword ptr cs:unk_1800AB338
0x18006f978  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006f97f  jz      short loc_18006F9BC
0x18006f981  test    rdx, rdx
0x18006f984  jz      short loc_18006F9C8
0x18006f986  mov     rcx, cs:gIphlpEtwContext
0x18006f98d  lea     rax, [rsp+8C0h+var_858]
0x18006f992  mov     [rsp+8C0h+var_898], rax
0x18006f997  lea     r9, [rsp+8C0h+var_878]
0x18006f99c  mov     rax, cs:gIphlpParamTemplateFunc
0x18006f9a3  lea     r8, aAllocateandget_18; "AllocateAndGetIpAddrTable Begin"
0x18006f9aa  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006f9b0  mov     [rsp+8C0h+var_8A0], r12
0x18006f9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9ba  jmp     short loc_18006F9C8
0x18006f9bc  lea     rcx, aAllocateandget_11; "AllocateAndGetIpAddrTable Begin"
0x18006f9c3  call    TraceHlp
0x18006f9c8  mov     [rdi], r12
0x18006f9cb  call    cs:__imp_GetCurrentThreadCompartmentId
0x18006f9d1  mov     ecx, ebx; CompartmentId
0x18006f9d3  mov     r15d, eax
0x18006f9d6  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006f9dc  mov     ebx, eax
0x18006f9de  test    eax, eax
0x18006f9e0  jnz     loc_18006FAFA
0x18006f9e6  xor     r8d, r8d; bOrder
0x18006f9e9  mov     [rsp+8C0h+pdwSize], r12d
0x18006f9ee  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006f9f3  xor     ecx, ecx; pIpAddrTable
0x18006f9f5  call    cs:__imp_GetIpAddrTable
0x18006f9fb  mov     ebx, eax
0x18006f9fd  cmp     eax, 7Ah ; 'z'
0x18006fa00  jz      short loc_18006FA30
0x18006fa02  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fa09  jz      short loc_18006FA24
0x18006fa0b  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fa12  jz      loc_18006FB6F
0x18006fa18  lea     rdx, aAllocateandget_15; "AllocateAndGetIpNetTable : error %d get"...
0x18006fa1f  jmp     loc_18006FB16
0x18006fa24  lea     rcx, aAllocateandget_12; "AllocateAndGetIpNetTable : error %d get"...
0x18006fa2b  jmp     loc_18006FB68
0x18006fa30  mov     eax, [rsp+8C0h+pdwSize]
0x18006fa34  mov     edx, 40h ; '@'; dwFlags
0x18006fa39  add     eax, 78h ; 'x'
0x18006fa3c  mov     rcx, rsi; hHeap
0x18006fa3f  mov     r8d, eax; dwBytes
0x18006fa42  mov     [rsp+8C0h+pdwSize], eax
0x18006fa46  call    cs:__imp_HeapAlloc
0x18006fa4c  mov     [rdi], rax
0x18006fa4f  test    rax, rax
0x18006fa52  jnz     loc_18006FAE5
0x18006fa58  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fa5f  mov     ebx, 0Eh
0x18006fa64  jz      short loc_18006FACD
0x18006fa66  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fa6d  jz      loc_18006FBBD
0x18006fa73  mov     r9d, [rsp+8C0h+pdwSize]
0x18006fa78  lea     rdx, aAllocateandget_10; "AllocateAndGetIpAddrTable : error %d al"...
0x18006fa7f  mov     r8d, ebx
0x18006fa82  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006fa87  lea     rcx, [rbp+7C0h+var_830]
0x18006fa8b  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fa91  call    FormatRRASErrorString
0x18006fa96  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006fa9d  lea     rax, [rsp+8C0h+var_858]
0x18006faa2  mov     rcx, cs:gIphlpEtwContext
0x18006faa9  lea     r9, [rsp+8C0h+var_878]
0x18006faae  mov     [rsp+8C0h+var_898], rax
0x18006fab3  lea     r8, [rbp+7C0h+var_830]
0x18006fab7  mov     rax, cs:gIphlpParamTemplateFunc
0x18006fabe  mov     [rsp+8C0h+var_8A0], r12
0x18006fac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fac8  jmp     loc_18006FBBD
0x18006facd  mov     r8d, [rsp+8C0h+pdwSize]
0x18006fad2  lea     rcx, aAllocateandget_5; "AllocateAndGetIpAddrTable : error %d al"...
0x18006fad9  mov     edx, ebx
0x18006fadb  call    TraceHlp
0x18006fae0  jmp     loc_18006FBBD
0x18006fae5  xor     r8d, r8d; bOrder
0x18006fae8  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006faed  mov     rcx, rax; pIpAddrTable
0x18006faf0  call    cs:__imp_GetIpAddrTable
0x18006faf6  mov     ebx, eax
0x18006faf8  jmp     short loc_18006FB6F
0x18006fafa  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fb01  mov     r14d, r12d
0x18006fb04  jz      short loc_18006FB61
0x18006fb06  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fb0d  jz      short loc_18006FB6F
0x18006fb0f  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006fb16  mov     r8d, eax
0x18006fb19  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fb1f  lea     rcx, [rbp+7C0h+var_830]
0x18006fb23  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006fb28  call    FormatRRASErrorString
0x18006fb2d  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006fb34  lea     rax, [rsp+8C0h+var_858]
0x18006fb39  mov     rcx, cs:gIphlpEtwContext
0x18006fb40  lea     r9, [rsp+8C0h+var_878]
0x18006fb45  mov     [rsp+8C0h+var_898], rax
0x18006fb4a  lea     r8, [rbp+7C0h+var_830]
0x18006fb4e  mov     rax, cs:gIphlpParamTemplateFunc
0x18006fb55  mov     [rsp+8C0h+var_8A0], r12
0x18006fb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb5f  jmp     short loc_18006FB6F
0x18006fb61  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006fb68  mov     edx, eax
0x18006fb6a  call    TraceHlp
0x18006fb6f  cmp     ebx, 0E8h
0x18006fb75  jnz     short loc_18006FBB9
0x18006fb77  mov     r8, [rdi]; lpMem
0x18006fb7a  test    r8, r8
0x18006fb7d  jz      short loc_18006FB8D
0x18006fb7f  xor     edx, edx; dwFlags
0x18006fb81  mov     rcx, rsi; hHeap
0x18006fb84  call    cs:__imp_HeapFree
0x18006fb8a  mov     [rdi], r12
0x18006fb8d  mov     r8d, 24h ; '$'; dwBytes
0x18006fb93  mov     rcx, rsi; hHeap
0x18006fb96  mov     [rsp+8C0h+pdwSize], r8d
0x18006fb9b  lea     edx, [r8+1Ch]; dwFlags
0x18006fb9f  call    cs:__imp_HeapAlloc
0x18006fba5  mov     [rdi], rax
0x18006fba8  test    rax, rax
0x18006fbab  jz      loc_18006FA58
0x18006fbb1  mov     [rax], r12d
0x18006fbb4  mov     ebx, r12d
0x18006fbb7  jmp     short loc_18006FBD3
0x18006fbb9  test    ebx, ebx
0x18006fbbb  jz      short loc_18006FBD3
0x18006fbbd  mov     r8, [rdi]; lpMem
0x18006fbc0  test    r8, r8
0x18006fbc3  jz      short loc_18006FBD3
0x18006fbc5  xor     edx, edx; dwFlags
0x18006fbc7  mov     rcx, rsi; hHeap
0x18006fbca  call    cs:__imp_HeapFree
0x18006fbd0  mov     [rdi], r12
0x18006fbd3  test    r14d, r14d
0x18006fbd6  jz      short loc_18006FBE1
0x18006fbd8  mov     ecx, r15d; CompartmentId
0x18006fbdb  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006fbe1  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fbe8  jz      short loc_18006FC2C
0x18006fbea  mov     rdx, qword ptr cs:unk_1800AB338
0x18006fbf1  test    rdx, rdx
0x18006fbf4  jz      short loc_18006FC38
0x18006fbf6  mov     rcx, cs:gIphlpEtwContext
0x18006fbfd  lea     rax, [rsp+8C0h+var_858]
0x18006fc02  mov     [rsp+8C0h+var_898], rax
0x18006fc07  lea     r9, [rsp+8C0h+var_878]
0x18006fc0c  mov     rax, cs:gIphlpParamTemplateFunc
0x18006fc13  lea     r8, aAllocateandget_17; "AllocateAndGetIpAddrTable End"
0x18006fc1a  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fc20  mov     [rsp+8C0h+var_8A0], r12
0x18006fc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc2a  jmp     short loc_18006FC38
0x18006fc2c  lea     rcx, aAllocateandget; "AllocateAndGetIpAddrTable End"
0x18006fc33  call    TraceHlp
0x18006fc38  mov     eax, ebx
0x18006fc3a  mov     rcx, [rbp+7C0h+var_30]
0x18006fc41  xor     rcx, rsp; StackCookie
0x18006fc44  call    __security_check_cookie
0x18006fc49  lea     r11, [rsp+8C0h+var_20]
0x18006fc51  mov     rbx, [r11+38h]
0x18006fc55  mov     rsi, [r11+48h]
0x18006fc59  mov     rsp, r11
0x18006fc5c  pop     r15
0x18006fc5e  pop     r14
0x18006fc60  pop     r12
0x18006fc62  pop     rdi
0x18006fc63  pop     rbp
0x18006fc64  retn
```
