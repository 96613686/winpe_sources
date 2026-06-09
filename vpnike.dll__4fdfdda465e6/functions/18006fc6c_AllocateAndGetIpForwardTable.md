# AllocateAndGetIpForwardTable

- ea: `0x18006fc6c`
- end: `0x18007002b`
- name: `AllocateAndGetIpForwardTable`
- size: `959`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180070034`

## callees

- `0x180069a8c`
- `0x18006f864`
- `0x18006fc6c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ff90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fe0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006fe0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ff65`
- `IPHLPAPI!GetIpForwardTable` at `0x18006fdb9`
- `IPHLPAPI!GetIpForwardTable` at `0x18006feb6`
- `IPHLPAPI!GetIpForwardTable` at `0x18006fdb9`
- `IPHLPAPI!GetIpForwardTable` at `0x18006feb6`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006fd8f`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006fd8f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006fd9a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006ffa1`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006fd9a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006ffa1`

## string_xrefs

- `0x18006fed5`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18006ff27`: `AllocateAndGetIpNetTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall AllocateAndGetIpForwardTable(
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
  DWORD IpForwardTable; // eax
  DWORD v12; // ebx
  const wchar_t *v13; // rdx
  const CHAR *v14; // rcx
  struct _MIB_IPFORWARDTABLE *v15; // rax
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
        L"AllocateAndGetIpForwardTable Begin",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable Begin");
  }
  *a1 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  IpForwardTable = SetCurrentThreadCompartmentId(CompartmentId);
  v12 = IpForwardTable;
  if ( IpForwardTable )
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
  IpForwardTable = GetIpForwardTable(0, &pdwSize, 0);
  v12 = IpForwardTable;
  if ( IpForwardTable != 122 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800AB328 + 1) )
        goto LABEL_29;
      v13 = L"AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_26:
      LOWORD(v19) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, v13, IpForwardTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800AB328 + 1),
        &v23,
        v18,
        0,
        &v19);
      goto LABEL_29;
    }
    v14 = "AllocateAndGetIpForwardTable : error %d getting table size";
LABEL_28:
    TraceHlp(v14);
    goto LABEL_29;
  }
  pdwSize += 280;
  v15 = (struct _MIB_IPFORWARDTABLE *)HeapAlloc(a3, 0x40u, pdwSize);
  *a1 = v15;
  if ( !v15 )
    goto LABEL_18;
  v12 = GetIpForwardTable(v15, &pdwSize, 0);
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
  pdwSize = 68;
  v16 = HeapAlloc(a3, 0x40u, 0x44u);
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
        FormatRRASErrorString(&v23, L"AllocateAndGetIpForwardTable : error %d allocating %d bytes", 14, pdwSize);
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
      TraceHlp("AllocateAndGetIpForwardTable : error %d allocating %d bytes");
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
        L"AllocateAndGetIpForwardTable End",
        v18,
        0,
        &v19);
    }
  }
  else
  {
    TraceHlp("AllocateAndGetIpForwardTable End");
  }
  return v12;
}

```

## disassembly

```asm
0x18006fc6c  mov     [rsp-8+arg_8], rbx
0x18006fc71  mov     [rsp-8+arg_18], rsi
0x18006fc76  push    rbp
0x18006fc77  push    rdi
0x18006fc78  push    r12
0x18006fc7a  push    r14
0x18006fc7c  push    r15
0x18006fc7e  lea     rbp, [rsp-7A0h]
0x18006fc86  sub     rsp, 8A0h
0x18006fc8d  mov     rax, cs:__security_cookie
0x18006fc94  xor     rax, rsp
0x18006fc97  mov     [rbp+7C0h+var_30], rax
0x18006fc9e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006fca5  mov     rsi, r8
0x18006fca8  mov     rdi, rcx
0x18006fcab  xor     r12d, r12d
0x18006fcae  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18006fcb2  xor     edx, edx; Val
0x18006fcb4  mov     [rsp+8C0h+pdwSize], r12d
0x18006fcb9  mov     r8d, 7FCh; Size
0x18006fcbf  mov     [rbp+7C0h+var_830], r12d
0x18006fcc3  movdqu  [rsp+8C0h+var_878], xmm0
0x18006fcc9  call    memset_0
0x18006fcce  mov     ebx, [rbp+7C0h+CompartmentId]
0x18006fcd4  lea     r14d, [r12+1]
0x18006fcd9  xorps   xmm0, xmm0
0x18006fcdc  mov     [rsp+8C0h+var_858], r12d
0x18006fce1  xor     eax, eax
0x18006fce3  mov     [rbp+7C0h+var_834], eax
0x18006fce6  movups  [rsp+8C0h+var_854], xmm0
0x18006fceb  movups  [rsp+8C0h+var_844], xmm0
0x18006fcf0  movups  [rsp+8C0h+var_868], xmm0
0x18006fcf5  cmp     ebx, r14d
0x18006fcf8  jz      short loc_18006FD03
0x18006fcfa  cmp     qword ptr cs:unk_1800AB320, r12
0x18006fd01  jnz     short loc_18006FD21
0x18006fd03  cmp     qword ptr cs:xmmword_1800AB328, r12
0x18006fd0a  jnz     short loc_18006FD21
0x18006fd0c  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fd13  jnz     short loc_18006FD21
0x18006fd15  mov     rdx, qword ptr cs:unk_1800AB338
0x18006fd1c  test    rdx, rdx
0x18006fd1f  jz      short loc_18006FD3C
0x18006fd21  lea     rdx, [rsp+8C0h+var_878]
0x18006fd26  mov     ecx, ebx
0x18006fd28  call    NsiGetRoutingDomainIdForCompartment
0x18006fd2d  test    eax, eax
0x18006fd2f  jnz     loc_180070000
0x18006fd35  mov     rdx, qword ptr cs:unk_1800AB338
0x18006fd3c  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fd43  jz      short loc_18006FD80
0x18006fd45  test    rdx, rdx
0x18006fd48  jz      short loc_18006FD8C
0x18006fd4a  mov     rcx, cs:gIphlpEtwContext
0x18006fd51  lea     rax, [rsp+8C0h+var_858]
0x18006fd56  mov     [rsp+8C0h+var_898], rax
0x18006fd5b  lea     r9, [rsp+8C0h+var_878]
0x18006fd60  mov     rax, cs:gIphlpParamTemplateFunc
0x18006fd67  lea     r8, aAllocateandget_20; "AllocateAndGetIpForwardTable Begin"
0x18006fd6e  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fd74  mov     [rsp+8C0h+var_8A0], r12
0x18006fd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd7e  jmp     short loc_18006FD8C
0x18006fd80  lea     rcx, aAllocateandget_19; "AllocateAndGetIpForwardTable Begin"
0x18006fd87  call    TraceHlp
0x18006fd8c  mov     [rdi], r12
0x18006fd8f  call    cs:__imp_GetCurrentThreadCompartmentId
0x18006fd95  mov     ecx, ebx; CompartmentId
0x18006fd97  mov     r15d, eax
0x18006fd9a  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006fda0  mov     ebx, eax
0x18006fda2  test    eax, eax
0x18006fda4  jnz     loc_18006FEC0
0x18006fdaa  xor     r8d, r8d; bOrder
0x18006fdad  mov     [rsp+8C0h+pdwSize], r12d
0x18006fdb2  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006fdb7  xor     ecx, ecx; pIpForwardTable
0x18006fdb9  call    cs:__imp_GetIpForwardTable
0x18006fdbf  mov     ebx, eax
0x18006fdc1  cmp     eax, 7Ah ; 'z'
0x18006fdc4  jz      short loc_18006FDF4
0x18006fdc6  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fdcd  jz      short loc_18006FDE8
0x18006fdcf  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fdd6  jz      loc_18006FF35
0x18006fddc  lea     rdx, aAllocateandget_14; "AllocateAndGetIpForwardTable : error %d"...
0x18006fde3  jmp     loc_18006FEDC
0x18006fde8  lea     rcx, aAllocateandget_9; "AllocateAndGetIpForwardTable : error %d"...
0x18006fdef  jmp     loc_18006FF2E
0x18006fdf4  mov     eax, [rsp+8C0h+pdwSize]
0x18006fdf8  mov     edx, 40h ; '@'; dwFlags
0x18006fdfd  add     eax, 118h
0x18006fe02  mov     rcx, rsi; hHeap
0x18006fe05  mov     r8d, eax; dwBytes
0x18006fe08  mov     [rsp+8C0h+pdwSize], eax
0x18006fe0c  call    cs:__imp_HeapAlloc
0x18006fe12  mov     [rdi], rax
0x18006fe15  test    rax, rax
0x18006fe18  jnz     loc_18006FEAB
0x18006fe1e  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fe25  mov     ebx, 0Eh
0x18006fe2a  jz      short loc_18006FE93
0x18006fe2c  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fe33  jz      loc_18006FF83
0x18006fe39  mov     r9d, [rsp+8C0h+pdwSize]
0x18006fe3e  lea     rdx, aAllocateandget_3; "AllocateAndGetIpForwardTable : error %d"...
0x18006fe45  mov     r8d, ebx
0x18006fe48  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006fe4d  lea     rcx, [rbp+7C0h+var_830]
0x18006fe51  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fe57  call    FormatRRASErrorString
0x18006fe5c  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006fe63  lea     rax, [rsp+8C0h+var_858]
0x18006fe68  mov     rcx, cs:gIphlpEtwContext
0x18006fe6f  lea     r9, [rsp+8C0h+var_878]
0x18006fe74  mov     [rsp+8C0h+var_898], rax
0x18006fe79  lea     r8, [rbp+7C0h+var_830]
0x18006fe7d  mov     rax, cs:gIphlpParamTemplateFunc
0x18006fe84  mov     [rsp+8C0h+var_8A0], r12
0x18006fe89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe8e  jmp     loc_18006FF83
0x18006fe93  mov     r8d, [rsp+8C0h+pdwSize]
0x18006fe98  lea     rcx, aAllocateandget_0; "AllocateAndGetIpForwardTable : error %d"...
0x18006fe9f  mov     edx, ebx
0x18006fea1  call    TraceHlp
0x18006fea6  jmp     loc_18006FF83
0x18006feab  xor     r8d, r8d; bOrder
0x18006feae  lea     rdx, [rsp+8C0h+pdwSize]; pdwSize
0x18006feb3  mov     rcx, rax; pIpForwardTable
0x18006feb6  call    cs:__imp_GetIpForwardTable
0x18006febc  mov     ebx, eax
0x18006febe  jmp     short loc_18006FF35
0x18006fec0  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006fec7  mov     r14d, r12d
0x18006feca  jz      short loc_18006FF27
0x18006fecc  cmp     qword ptr cs:xmmword_1800AB328+8, r12
0x18006fed3  jz      short loc_18006FF35
0x18006fed5  lea     rdx, aAllocateandget_1; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006fedc  mov     r8d, eax
0x18006fedf  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006fee5  lea     rcx, [rbp+7C0h+var_830]
0x18006fee9  mov     word ptr [rbp+7C0h+var_830], r12w
0x18006feee  call    FormatRRASErrorString
0x18006fef3  mov     rdx, qword ptr cs:xmmword_1800AB328+8
0x18006fefa  lea     rax, [rsp+8C0h+var_858]
0x18006feff  mov     rcx, cs:gIphlpEtwContext
0x18006ff06  lea     r9, [rsp+8C0h+var_878]
0x18006ff0b  mov     [rsp+8C0h+var_898], rax
0x18006ff10  lea     r8, [rbp+7C0h+var_830]
0x18006ff14  mov     rax, cs:gIphlpParamTemplateFunc
0x18006ff1b  mov     [rsp+8C0h+var_8A0], r12
0x18006ff20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff25  jmp     short loc_18006FF35
0x18006ff27  lea     rcx, aAllocateandget_13; "AllocateAndGetIpNetTable: SetCurrentThr"...
0x18006ff2e  mov     edx, eax
0x18006ff30  call    TraceHlp
0x18006ff35  cmp     ebx, 0E8h
0x18006ff3b  jnz     short loc_18006FF7F
0x18006ff3d  mov     r8, [rdi]; lpMem
0x18006ff40  test    r8, r8
0x18006ff43  jz      short loc_18006FF53
0x18006ff45  xor     edx, edx; dwFlags
0x18006ff47  mov     rcx, rsi; hHeap
0x18006ff4a  call    cs:__imp_HeapFree
0x18006ff50  mov     [rdi], r12
0x18006ff53  mov     r8d, 44h ; 'D'; dwBytes
0x18006ff59  mov     rcx, rsi; hHeap
0x18006ff5c  mov     [rsp+8C0h+pdwSize], r8d
0x18006ff61  lea     edx, [r8-4]; dwFlags
0x18006ff65  call    cs:__imp_HeapAlloc
0x18006ff6b  mov     [rdi], rax
0x18006ff6e  test    rax, rax
0x18006ff71  jz      loc_18006FE1E
0x18006ff77  mov     [rax], r12d
0x18006ff7a  mov     ebx, r12d
0x18006ff7d  jmp     short loc_18006FF99
0x18006ff7f  test    ebx, ebx
0x18006ff81  jz      short loc_18006FF99
0x18006ff83  mov     r8, [rdi]; lpMem
0x18006ff86  test    r8, r8
0x18006ff89  jz      short loc_18006FF99
0x18006ff8b  xor     edx, edx; dwFlags
0x18006ff8d  mov     rcx, rsi; hHeap
0x18006ff90  call    cs:__imp_HeapFree
0x18006ff96  mov     [rdi], r12
0x18006ff99  test    r14d, r14d
0x18006ff9c  jz      short loc_18006FFA7
0x18006ff9e  mov     ecx, r15d; CompartmentId
0x18006ffa1  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006ffa7  cmp     cs:gIsIphlpEtwTracingAvailable, r12d
0x18006ffae  jz      short loc_18006FFF2
0x18006ffb0  mov     rdx, qword ptr cs:unk_1800AB338
0x18006ffb7  test    rdx, rdx
0x18006ffba  jz      short loc_18006FFFE
0x18006ffbc  mov     rcx, cs:gIphlpEtwContext
0x18006ffc3  lea     rax, [rsp+8C0h+var_858]
0x18006ffc8  mov     [rsp+8C0h+var_898], rax
0x18006ffcd  lea     r9, [rsp+8C0h+var_878]
0x18006ffd2  mov     rax, cs:gIphlpParamTemplateFunc
0x18006ffd9  lea     r8, aAllocateandget_8; "AllocateAndGetIpForwardTable End"
0x18006ffe0  mov     word ptr [rsp+8C0h+var_858], r12w
0x18006ffe6  mov     [rsp+8C0h+var_8A0], r12
0x18006ffeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fff0  jmp     short loc_18006FFFE
0x18006fff2  lea     rcx, aAllocateandget_2; "AllocateAndGetIpForwardTable End"
0x18006fff9  call    TraceHlp
0x18006fffe  mov     eax, ebx
0x180070000  mov     rcx, [rbp+7C0h+var_30]
0x180070007  xor     rcx, rsp; StackCookie
0x18007000a  call    __security_check_cookie
0x18007000f  lea     r11, [rsp+8C0h+var_20]
0x180070017  mov     rbx, [r11+38h]
0x18007001b  mov     rsi, [r11+48h]
0x18007001f  mov     rsp, r11
0x180070022  pop     r15
0x180070024  pop     r14
0x180070026  pop     r12
0x180070028  pop     rdi
0x180070029  pop     rbp
0x18007002a  retn
```
