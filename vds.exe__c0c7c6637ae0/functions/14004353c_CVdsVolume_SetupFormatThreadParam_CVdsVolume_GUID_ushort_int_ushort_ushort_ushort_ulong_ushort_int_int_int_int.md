# CVdsVolume::SetupFormatThreadParam(CVdsVolume *,_GUID,ushort *,int,ushort *,ushort *,ushort,ulong,ushort *,int,int,int,int,ulong *,ATL::CComObject<CVdsServiceAsyncObject> * *,_FORMAT_VOLUME_THREAD_PARAMETER * *)

- ea: `0x14004353c`
- end: `0x14004392d`
- name: `?SetupFormatThreadParam@CVdsVolume@@SAJPEAV1@U_GUID@@PEAGH22GK2HHHHPEAKPEAPEAV?$CComObject@VCVdsServiceAsyncObject@@@ATL@@PEAPEAU_FORMAT_VOLUME_THREAD_PARAMETER@@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14002b3f8`

## callees

- `0x140006e60`
- `0x14003ce10`
- `0x14004353c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140043732`
- `msvcrt!_wcsnicmp` at `0x140043732`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400435ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400436a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004378a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400437e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400435ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400436a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004378a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400437e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400438f8`
- `vdsutil!VdsHeapAlloc` at `0x1400435c2`
- `vdsutil!VdsHeapAlloc` at `0x1400436b9`
- `vdsutil!VdsHeapAlloc` at `0x14004379b`
- `vdsutil!VdsHeapAlloc` at `0x1400437f5`
- `vdsutil!VdsHeapAlloc` at `0x1400435c2`
- `vdsutil!VdsHeapAlloc` at `0x1400436b9`
- `vdsutil!VdsHeapAlloc` at `0x14004379b`
- `vdsutil!VdsHeapAlloc` at `0x1400437f5`
- `vdsutil!VdsHeapFree` at `0x1400438db`
- `vdsutil!VdsHeapFree` at `0x1400438ef`
- `vdsutil!VdsHeapFree` at `0x140043906`
- `vdsutil!VdsHeapFree` at `0x1400438db`
- `vdsutil!VdsHeapFree` at `0x1400438ef`
- `vdsutil!VdsHeapFree` at `0x140043906`
- `vdsutil!VdsTraceEx` at `0x1400438c4`
- `vdsutil!VdsTraceEx` at `0x1400438c4`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043571`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043571`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043644`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043914`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043644`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043914`
- `vdsutil!VdsTraceW` at `0x1400435e2`
- `vdsutil!VdsTraceW` at `0x140043638`
- `vdsutil!VdsTraceW` at `0x1400436d9`
- `vdsutil!VdsTraceW` at `0x1400435e2`
- `vdsutil!VdsTraceW` at `0x140043638`
- `vdsutil!VdsTraceW` at `0x1400436d9`

## string_xrefs

- `0x140043560`: `CVdsVolume::SetupFormatThreadParam()`
- `0x1400438b8`: `CVdsVolume::SetupFormatThreadParam, 1, hr=%lX, Volume=%p, Device=%p, Asynch=%p`
- `0x1400435d9`: `CVdsVolume::SetupFormatThreadParam, 2, hr=%lX`
- `0x14004362f`: `CVdsVolume::SetupFormatThreadParam, 3, hr=%lX`
- `0x14004367a`: `CVdsVolume::SetupFormatThreadParam, 4, hr=%lX`
- `0x1400436c7`: `CVdsVolume::SetupFormatThreadParam, 5, hr=%lX`
- `0x140043708`: `CVdsVolume::SetupFormatThreadParam, 6, hr=%lX`
- `0x1400437a9`: `CVdsVolume::SetupFormatThreadParam, 7, hr=%lX`
- `0x1400437d7`: `CVdsVolume::SetupFormatThreadParam, 8, hr=%lX`
- `0x140043803`: `CVdsVolume::SetupFormatThreadParam, 9, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsVolume::SetupFormatThreadParam(
        __int64 a1,
        _OWORD *a2,
        const unsigned __int16 *a3,
        int a4,
        STRSAFE_PCNZWCH pszSrc,
        unsigned __int16 *a6,
        __int16 a7,
        int a8,
        unsigned __int16 *a9,
        int a10,
        int a11,
        int a12,
        int a13,
        __int64 a14,
        _QWORD *a15,
        __int64 *a16)
{
  unsigned __int16 *v19; // r12
  __int64 v20; // r15
  HANDLE ProcessHeap; // rax
  _QWORD *v22; // rax
  unsigned int v23; // edi
  int v24; // eax
  size_t *v25; // r8
  unsigned int v26; // ebx
  wchar_t *v28; // rcx
  HRESULT v29; // eax
  __int64 v30; // rbp
  __int64 v31; // rbx
  HANDLE v32; // rax
  unsigned __int16 *v33; // rax
  const wchar_t *v34; // rdx
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rbx
  HANDLE v38; // rax
  unsigned __int16 *v39; // rax
  int v40; // eax
  HANDLE v41; // rax
  HANDLE v42; // rax
  HANDLE v43; // rax
  __int64 v44; // rbx
  HANDLE v45; // rax
  _BYTE v46[88]; // [rsp+40h] [rbp-58h] BYREF

  v19 = 0;
  v20 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v46, 0x5Eu, "CVdsVolume::SetupFormatThreadParam()");
  if ( !a3 || !pszSrc || !a15 )
  {
    v23 = -2147024809;
    VdsTraceEx(
      94,
      0,
      "CVdsVolume::SetupFormatThreadParam, 1, hr=%lX, Volume=%p, Device=%p, Asynch=%p",
      -2147024809,
      a3,
      pszSrc,
      a15);
    goto LABEL_42;
  }
  *a16 = 0;
  ProcessHeap = GetProcessHeap();
  v22 = (_QWORD *)VdsHeapAlloc(ProcessHeap, 8, 1200);
  *a16 = (__int64)v22;
  if ( v22 )
  {
    *v22 = a1;
    *(_QWORD *)(*a16 + 8) = *a15;
    *(_OWORD *)(*a16 + 16) = *a2;
    v24 = StringCchCopyW((unsigned __int16 *)(*a16 + 32), 0x104u, a3);
    v26 = v24;
    if ( v24 < 0 )
    {
      VdsTraceW(0, L"CVdsVolume::SetupFormatThreadParam, 3, hr=%lX", (unsigned int)v24);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v46);
      return v26;
    }
    v28 = (wchar_t *)(*a16 + 552);
    if ( a4 )
    {
      v29 = StringCopyWorkerW(v28, 0x112u, v25, pszSrc, 0x112u);
      v23 = v29;
      if ( v29 < 0 )
      {
        VdsTraceW(0, L"CVdsVolume::SetupFormatThreadParam, 4, hr=%lX", (unsigned int)v29);
        goto LABEL_42;
      }
    }
    else
    {
      *v28 = 0;
    }
    v30 = -1;
    v31 = -1;
    do
      ++v31;
    while ( a6[v31] );
    v32 = GetProcessHeap();
    v33 = (unsigned __int16 *)VdsHeapAlloc(v32, 8, 2 * v31 + 2);
    v19 = v33;
    if ( !v33 )
    {
      v34 = L"CVdsVolume::SetupFormatThreadParam, 5, hr=%lX";
LABEL_16:
      v23 = -2147024882;
      VdsTraceW(0, v34, 2147942414LL);
      goto LABEL_42;
    }
    v35 = -1;
    do
      ++v35;
    while ( a6[v35] );
    v36 = StringCchCopyW(v33, v35 + 1, a6);
    v23 = v36;
    if ( v36 < 0 )
    {
      VdsTraceW(0, L"CVdsVolume::SetupFormatThreadParam, 6, hr=%lX", (unsigned int)v36);
      goto LABEL_42;
    }
    *(_QWORD *)(*a16 + 1104) = v19;
    if ( !_wcsnicmp(*(const wchar_t **)(*a16 + 1104), L"NTFS", 4u) )
      *(_DWORD *)(*a16 + 1168) = a12;
    *(_QWORD *)(*a16 + 1184) = a14;
    *(_DWORD *)(*a16 + 1192) = 0;
    if ( a9 )
    {
      v37 = -1;
      do
        ++v37;
      while ( a9[v37] );
      v38 = GetProcessHeap();
      v39 = (unsigned __int16 *)VdsHeapAlloc(v38, 8, 2 * v37 + 2);
      v20 = (__int64)v39;
      if ( !v39 )
      {
        v34 = L"CVdsVolume::SetupFormatThreadParam, 7, hr=%lX";
        goto LABEL_16;
      }
      do
        ++v30;
      while ( a9[v30] );
      v40 = StringCchCopyW(v39, v30 + 1, a9);
      v23 = v40;
      if ( v40 < 0 )
      {
        VdsTraceW(0, L"CVdsVolume::SetupFormatThreadParam, 8, hr=%lX", (unsigned int)v40);
        goto LABEL_42;
      }
    }
    else
    {
      v41 = GetProcessHeap();
      v20 = VdsHeapAlloc(v41, 8, 2);
      if ( !v20 )
      {
        v34 = L"CVdsVolume::SetupFormatThreadParam, 9, hr=%lX";
        goto LABEL_16;
      }
    }
    *(_BYTE *)(*a16 + 1112) = 2;
    *(_BYTE *)(*a16 + 1113) = 0;
    if ( a10 )
      *(_DWORD *)(*a16 + 1116) |= 4u;
    if ( a11 )
      *(_DWORD *)(*a16 + 1116) |= 1u;
    if ( a13 )
      *(_DWORD *)(*a16 + 1116) |= 8u;
    *(_QWORD *)(*a16 + 1120) = v20;
    *(_DWORD *)(*a16 + 1128) = a8;
    *(_WORD *)(*a16 + 1132) = a7;
    *(_QWORD *)(*a16 + 1136) = 0;
    *(_DWORD *)(*a16 + 1144) = 0;
    goto LABEL_43;
  }
  v23 = -2147024882;
  VdsTraceW(0, L"CVdsVolume::SetupFormatThreadParam, 2, hr=%lX");
LABEL_42:
  v42 = GetProcessHeap();
  VdsHeapFree(v42, 0, v19);
  v43 = GetProcessHeap();
  VdsHeapFree(v43, 0, v20);
  v44 = *a16;
  v45 = GetProcessHeap();
  VdsHeapFree(v45, 0, v44);
  *a16 = 0;
LABEL_43:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v46);
  return v23;
}

```

## disassembly

```asm
0x14004353c  mov     [rsp+arg_0], rcx
0x140043541  push    rbx
0x140043542  push    rbp
0x140043543  push    rsi
0x140043544  push    rdi
0x140043545  push    r12
0x140043547  push    r13
0x140043549  push    r14
0x14004354b  push    r15
0x14004354d  sub     rsp, 58h
0x140043551  mov     edi, r9d
0x140043554  mov     r14, r8
0x140043557  mov     r13, rdx
0x14004355a  xor     r12d, r12d
0x14004355d  xor     r15d, r15d
0x140043560  lea     r8, aCvdsvolumeSetu_5; "CVdsVolume::SetupFormatThreadParam()"
0x140043567  lea     edx, [r12+5Eh]
0x14004356c  lea     rcx, [rsp+98h+var_58]
0x140043571  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140043577  nop
0x140043578  mov     rsi, [rsp+98h+arg_78]
0x140043580  mov     rbx, [rsp+98h+arg_70]
0x140043588  mov     rbp, [rsp+98h+pszSrc]
0x140043590  test    r14, r14
0x140043593  jz      loc_1400438A1
0x140043599  test    rbp, rbp
0x14004359c  jz      loc_1400438A1
0x1400435a2  test    rbx, rbx
0x1400435a5  jz      loc_1400438A1
0x1400435ab  mov     [rsi], r15
0x1400435ae  call    cs:__imp_GetProcessHeap
0x1400435b4  mov     rcx, rax
0x1400435b7  lea     edx, [r12+8]
0x1400435bc  mov     r8d, 4B0h
0x1400435c2  call    cs:__imp_VdsHeapAlloc
0x1400435c8  mov     [rsi], rax
0x1400435cb  test    rax, rax
0x1400435ce  jnz     short loc_1400435ED
0x1400435d0  mov     r8d, 8007000Eh
0x1400435d6  mov     edi, r8d
0x1400435d9  lea     rdx, aCvdsvolumeSetu_1; "CVdsVolume::SetupFormatThreadParam, 2, "...
0x1400435e0  xor     ecx, ecx
0x1400435e2  call    cs:__imp_VdsTraceW
0x1400435e8  jmp     loc_1400438CA
0x1400435ed  mov     rcx, [rsp+98h+arg_0]
0x1400435f5  mov     [rax], rcx
0x1400435f8  mov     rcx, [rsi]
0x1400435fb  mov     rax, [rbx]
0x1400435fe  mov     [rcx+8], rax
0x140043602  mov     rax, [rsi]
0x140043605  movaps  xmm0, xmmword ptr [r13+0]
0x14004360a  movdqu  xmmword ptr [rax+10h], xmm0
0x14004360f  mov     rcx, [rsi]
0x140043612  add     rcx, 20h ; ' '; unsigned __int16 *
0x140043616  mov     r8, r14; unsigned __int16 *
0x140043619  mov     edx, 104h; unsigned __int64
0x14004361e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140043623  mov     ebx, eax
0x140043625  xor     r13d, r13d
0x140043628  test    eax, eax
0x14004362a  jns     short loc_140043651
0x14004362c  mov     r8d, eax
0x14004362f  lea     rdx, aCvdsvolumeSetu; "CVdsVolume::SetupFormatThreadParam, 3, "...
0x140043636  xor     ecx, ecx
0x140043638  call    cs:__imp_VdsTraceW
0x14004363e  nop
0x14004363f  lea     rcx, [rsp+98h+var_58]
0x140043644  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004364a  mov     eax, ebx
0x14004364c  jmp     loc_14004391C
0x140043651  mov     rcx, [rsi]
0x140043654  add     rcx, 228h; pszDest
0x14004365b  test    edi, edi
0x14004365d  jz      short loc_140043683
0x14004365f  mov     edx, 112h; cchDest
0x140043664  mov     [rsp+98h+cchToCopy], rdx; cchToCopy
0x140043669  mov     r9, rbp; pszSrc
0x14004366c  call    StringCopyWorkerW
0x140043671  mov     edi, eax
0x140043673  test    eax, eax
0x140043675  jns     short loc_140043687
0x140043677  mov     r8d, eax
0x14004367a  lea     rdx, aCvdsvolumeSetu_8; "CVdsVolume::SetupFormatThreadParam, 4, "...
0x140043681  jmp     short loc_1400436D7
0x140043683  mov     [rcx], r13w
0x140043687  mov     rdi, [rsp+98h+arg_28]
0x14004368f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140043693  mov     rbx, rbp
0x140043696  inc     rbx
0x140043699  cmp     [rdi+rbx*2], r13w
0x14004369e  jnz     short loc_140043696
0x1400436a0  lea     rbx, ds:2[rbx*2]
0x1400436a8  call    cs:__imp_GetProcessHeap
0x1400436ae  mov     rcx, rax
0x1400436b1  mov     r8, rbx
0x1400436b4  mov     edx, 8
0x1400436b9  call    cs:__imp_VdsHeapAlloc
0x1400436bf  mov     r12, rax
0x1400436c2  test    rax, rax
0x1400436c5  jnz     short loc_1400436E4
0x1400436c7  lea     rdx, aCvdsvolumeSetu_0; "CVdsVolume::SetupFormatThreadParam, 5, "...
0x1400436ce  mov     r8d, 8007000Eh
0x1400436d4  mov     edi, r8d
0x1400436d7  xor     ecx, ecx
0x1400436d9  call    cs:__imp_VdsTraceW
0x1400436df  jmp     loc_1400438CD
0x1400436e4  mov     rdx, rbp
0x1400436e7  inc     rdx
0x1400436ea  cmp     [rdi+rdx*2], r13w
0x1400436ef  jnz     short loc_1400436E7
0x1400436f1  inc     rdx; unsigned __int64
0x1400436f4  mov     r8, rdi; unsigned __int16 *
0x1400436f7  mov     rcx, r12; unsigned __int16 *
0x1400436fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400436ff  mov     edi, eax
0x140043701  test    eax, eax
0x140043703  jns     short loc_140043711
0x140043705  mov     r8d, eax
0x140043708  lea     rdx, aCvdsvolumeSetu_6; "CVdsVolume::SetupFormatThreadParam, 6, "...
0x14004370f  jmp     short loc_1400436D7
0x140043711  mov     rax, [rsi]
0x140043714  mov     [rax+450h], r12
0x14004371b  mov     rcx, [rsi]
0x14004371e  mov     r8d, 4; MaxCount
0x140043724  lea     rdx, aNtfs; "NTFS"
0x14004372b  mov     rcx, [rcx+450h]; String1
0x140043732  call    cs:__imp__wcsnicmp
0x140043738  test    eax, eax
0x14004373a  jnz     short loc_14004374C
0x14004373c  mov     rcx, [rsi]
0x14004373f  mov     eax, [rsp+98h+arg_58]
0x140043746  mov     [rcx+490h], eax
0x14004374c  mov     rcx, [rsi]
0x14004374f  mov     rax, [rsp+98h+arg_68]
0x140043757  mov     [rcx+4A0h], rax
0x14004375e  mov     rax, [rsi]
0x140043761  mov     [rax+4A8h], r13d
0x140043768  mov     r14, [rsp+98h+arg_40]
0x140043770  test    r14, r14
0x140043773  jz      short loc_1400437E3
0x140043775  mov     rbx, rbp
0x140043778  inc     rbx
0x14004377b  cmp     [r14+rbx*2], r13w
0x140043780  jnz     short loc_140043778
0x140043782  lea     rbx, ds:2[rbx*2]
0x14004378a  call    cs:__imp_GetProcessHeap
0x140043790  mov     rcx, rax
0x140043793  mov     r8, rbx
0x140043796  mov     edx, 8
0x14004379b  call    cs:__imp_VdsHeapAlloc
0x1400437a1  mov     r15, rax
0x1400437a4  test    rax, rax
0x1400437a7  jnz     short loc_1400437B5
0x1400437a9  lea     rdx, aCvdsvolumeSetu_4; "CVdsVolume::SetupFormatThreadParam, 7, "...
0x1400437b0  jmp     loc_1400436CE
0x1400437b5  inc     rbp
0x1400437b8  cmp     [r14+rbp*2], r13w
0x1400437bd  jnz     short loc_1400437B5
0x1400437bf  lea     rdx, [rbp+1]; unsigned __int64
0x1400437c3  mov     r8, r14; unsigned __int16 *
0x1400437c6  mov     rcx, rax; unsigned __int16 *
0x1400437c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400437ce  mov     edi, eax
0x1400437d0  test    eax, eax
0x1400437d2  jns     short loc_14004380F
0x1400437d4  mov     r8d, eax
0x1400437d7  lea     rdx, aCvdsvolumeSetu_7; "CVdsVolume::SetupFormatThreadParam, 8, "...
0x1400437de  jmp     loc_1400436D7
0x1400437e3  call    cs:__imp_GetProcessHeap
0x1400437e9  mov     rcx, rax
0x1400437ec  mov     edx, 8
0x1400437f1  lea     r8d, [rdx-6]
0x1400437f5  call    cs:__imp_VdsHeapAlloc
0x1400437fb  mov     r15, rax
0x1400437fe  test    rax, rax
0x140043801  jnz     short loc_14004380F
0x140043803  lea     rdx, aCvdsvolumeSetu_3; "CVdsVolume::SetupFormatThreadParam, 9, "...
0x14004380a  jmp     loc_1400436CE
0x14004380f  mov     rax, [rsi]
0x140043812  mov     byte ptr [rax+458h], 2
0x140043819  mov     rax, [rsi]
0x14004381c  mov     [rax+459h], r13b
0x140043823  cmp     [rsp+98h+arg_48], r13d
0x14004382b  jz      short loc_140043837
0x14004382d  mov     rax, [rsi]
0x140043830  or      dword ptr [rax+45Ch], 4
0x140043837  cmp     [rsp+98h+arg_50], r13d
0x14004383f  jz      short loc_14004384B
0x140043841  mov     rax, [rsi]
0x140043844  or      dword ptr [rax+45Ch], 1
0x14004384b  cmp     [rsp+98h+arg_60], r13d
0x140043853  jz      short loc_14004385F
0x140043855  mov     rax, [rsi]
0x140043858  or      dword ptr [rax+45Ch], 8
0x14004385f  mov     rax, [rsi]
0x140043862  mov     [rax+460h], r15
0x140043869  mov     rcx, [rsi]
0x14004386c  mov     eax, [rsp+98h+arg_38]
0x140043873  mov     [rcx+468h], eax
0x140043879  mov     rcx, [rsi]
0x14004387c  movzx   eax, [rsp+98h+arg_30]
0x140043884  mov     [rcx+46Ch], ax
0x14004388b  mov     rax, [rsi]
0x14004388e  mov     [rax+470h], r13
0x140043895  mov     rax, [rsi]
0x140043898  mov     [rax+478h], r13d
0x14004389f  jmp     short loc_14004390F
0x1400438a1  mov     edi, 80070057h
0x1400438a6  mov     [rsp+98h+var_68], rbx
0x1400438ab  mov     [rsp+98h+var_70], rbp
0x1400438b0  mov     [rsp+98h+cchToCopy], r14
0x1400438b5  mov     r9d, edi
0x1400438b8  lea     r8, aCvdsvolumeSetu_2; "CVdsVolume::SetupFormatThreadParam, 1, "...
0x1400438bf  xor     edx, edx
0x1400438c1  lea     ecx, [rdx+5Eh]
0x1400438c4  call    cs:__imp_VdsTraceEx
0x1400438ca  xor     r13d, r13d
0x1400438cd  call    cs:__imp_GetProcessHeap
0x1400438d3  mov     rcx, rax
0x1400438d6  mov     r8, r12
0x1400438d9  xor     edx, edx
0x1400438db  call    cs:__imp_VdsHeapFree
0x1400438e1  call    cs:__imp_GetProcessHeap
0x1400438e7  mov     rcx, rax
0x1400438ea  mov     r8, r15
0x1400438ed  xor     edx, edx
0x1400438ef  call    cs:__imp_VdsHeapFree
0x1400438f5  mov     rbx, [rsi]
0x1400438f8  call    cs:__imp_GetProcessHeap
0x1400438fe  mov     r8, rbx
0x140043901  xor     edx, edx
0x140043903  mov     rcx, rax
0x140043906  call    cs:__imp_VdsHeapFree
0x14004390c  mov     [rsi], r13
0x14004390f  lea     rcx, [rsp+98h+var_58]
0x140043914  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004391a  mov     eax, edi
0x14004391c  add     rsp, 58h
0x140043920  pop     r15
0x140043922  pop     r14
0x140043924  pop     r13
0x140043926  pop     r12
0x140043928  pop     rdi
0x140043929  pop     rsi
0x14004392a  pop     rbp
0x14004392b  pop     rbx
0x14004392c  retn
```
