# WDiagProcessAcmSelectionList(_WD_INTERFACE_CONTEXT *,void *,_WLAN_AVAILABLE_NETWORK_LIST_V3 *,_LIST_ENTRY *,ulong)

- ea: `0x18002b0a8`
- end: `0x18002b7eb`
- name: `?WDiagProcessAcmSelectionList@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_WLAN_AVAILABLE_NETWORK_LIST_V3@@PEAU_LIST_ENTRY@@K@Z`
- size: `1859`
- prototype: `unsigned int __usercall@<eax>(struct _WD_INTERFACE_CONTEXT *@<rcx>, void *@<rdx>, struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *@<r8>, struct _LIST_ENTRY *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180011558`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180029ed4`
- `0x18002ae00`
- `0x18002b0a8`
- `0x18002b7f4`
- `0x18002b93c`
- `0x18002bde8`
- `0x18002f3d8`
- `0x18002f450`
- `0x18009ae14`
- `0x180106340`
- `0x180107300`
- `0x180107318`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x18002b626`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x18002b626`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b10f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b10f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b11c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b11c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b3be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b3be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b3ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b100`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b79e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b100`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b79e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b355`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b5f0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b355`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b5f0`

## pseudocode

```c
__int64 __fastcall WDiagProcessAcmSelectionList(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *a3,
        struct _LIST_ENTRY *a4,
        unsigned int a5)
{
  struct _LIST_ENTRY *v5; // r12
  struct _RTL_CRITICAL_SECTION *v8; // rbp
  DWORD CurrentThreadId; // esi
  int v10; // r14d
  unsigned int v11; // ebp
  void *v12; // rax
  unsigned int v13; // edx
  int v14; // r8d
  void *v15; // rsi
  unsigned int v16; // kr00_4
  int v17; // r14d
  __int64 v18; // r15
  void *v19; // rcx
  PVOID *v20; // r10
  unsigned int v21; // r15d
  __int64 v22; // rcx
  char *v23; // rsi
  char *v24; // r12
  WCHAR *lpWideCharStr; // rax
  wchar_t *v26; // r14
  int v27; // eax
  __int64 v28; // rbp
  HANDLE ProcessHeap; // rax
  unsigned int v30; // edi
  int v32; // eax
  unsigned int v33; // esi
  __int64 v34; // rbp
  char v35; // al
  int cchWideChar; // [rsp+28h] [rbp-110h]
  int v37; // [rsp+70h] [rbp-C8h]
  int v38; // [rsp+74h] [rbp-C4h]
  int v39; // [rsp+78h] [rbp-C0h]
  int v40; // [rsp+7Ch] [rbp-BCh]
  int v41; // [rsp+80h] [rbp-B8h]
  int v42; // [rsp+84h] [rbp-B4h]
  int v43; // [rsp+88h] [rbp-B0h]
  int v44; // [rsp+8Ch] [rbp-ACh]
  wchar_t S1[40]; // [rsp+A0h] [rbp-98h] BYREF

  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 110, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 3360);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
  WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
  if ( (*((_BYTE *)a1 + 3448) & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      *((_DWORD *)a1 + 864),
      *((_QWORD *)a1 + 433),
      *((_DWORD *)a1 + 865),
      CurrentThreadId,
      (__int64)"WDiagProcessAcmSelectionList",
      44);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 1836;
  *((_QWORD *)a1 + 433) = "WDiagProcessAcmSelectionList";
  if ( a3 )
  {
    v10 = *((_DWORD *)a1 + 42);
    v11 = 688 * *(_DWORD *)a3 + 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 19, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
    v12 = WDiagAllocMem(v11);
    v15 = v12;
    if ( v12 )
    {
      memcpy_0(v12, a3, v11);
      v16 = v10 - 1;
      v17 = 0;
      v13 = v16 / 5;
      v18 = 624LL * (v16 % 5);
      v19 = *(void **)((char *)a1 + v18 + 792);
      if ( v19 )
        WDiagFreeMem(v19);
      *(_QWORD *)((char *)a1 + v18 + 792) = v15;
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && *((char *)WPP_GLOBAL_Control + 228) < 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 20, &WPP_79512908d13336da9f44adf151438c1a_Traceguids, v11);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      v17 = 8;
    }
    if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 57) & 0x200) != 0 )
    {
      WPP_SF_(v20[27], 21, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v17 )
    {
      if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 225) && (*((_BYTE *)v20 + 228) & 4) != 0 )
      {
        cchWideChar = v17;
        WPP_SF_lll(v20[27], 113, &WPP_fec73b95d5a537674450248f38664378_Traceguids, v11);
      }
    }
    else
    {
      if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 225) >= 3u && (*((_BYTE *)v20 + 228) & 4) != 0 )
      {
        WPP_SF_DD(v20[27], 111, &WPP_fec73b95d5a537674450248f38664378_Traceguids, *(unsigned int *)a3);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      v21 = 0;
      if ( *(_DWORD *)a3 )
      {
        while ( 1 )
        {
          if ( v20 == &WPP_GLOBAL_Control || *((_BYTE *)v20 + 225) < 3u || (*((_BYTE *)v20 + 228) & 4) == 0 )
            goto LABEL_34;
          v22 = 688LL * v21;
          v38 = *(_DWORD *)((char *)a3 + v22 + 624);
          v39 = *(_DWORD *)((char *)a3 + v22 + 620);
          v40 = *(_DWORD *)((char *)a3 + v22 + 580);
          v41 = *(_DWORD *)((char *)a3 + v22 + 556);
          v42 = *(_DWORD *)((char *)a3 + v22 + 572);
          v43 = *(_DWORD *)((char *)a3 + v22 + 568);
          v44 = *(_DWORD *)((char *)a3 + v22 + 636);
          v37 = *(_DWORD *)((char *)a3 + v22 + 628);
          v23 = (char *)a3 + v22 + 520;
          if ( v23 )
          {
            if ( *(_DWORD *)v23 <= 0x20u && (unsigned int)(*(_DWORD *)v23 + 1) <= 0x21 )
            {
              v24 = v23 + 4;
              S1[0] = 0;
              if ( v23 != (char *)-4LL )
                break;
            }
          }
LABEL_33:
          WPP_SF_dSDddddddd(
            (unsigned int)v20[27],
            v13,
            v14,
            v21 + 1,
            (__int64)S1,
            v44,
            v43,
            v42,
            v41,
            v40,
            v39,
            v38,
            v37);
          v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
          if ( ++v21 >= *(_DWORD *)a3 )
          {
            v5 = a4;
            goto LABEL_36;
          }
        }
        lpWideCharStr = (WCHAR *)AllocWLMem(0x42u);
        v26 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          *lpWideCharStr = 0;
          v27 = MultiByteToWideChar(0xFDE9u, 8u, v23 + 4, *(_DWORD *)v23, lpWideCharStr, 32);
          if ( v27 <= 0 )
          {
            GetLastError();
          }
          else
          {
            v28 = v27;
            if ( !o_wmemcpy_s_0(S1, 0x21u, v26, v27) )
            {
LABEL_27:
              S1[v28] = 0;
              goto LABEL_30;
            }
          }
          v32 = MultiByteToWideChar(0, 8u, v23 + 4, *(_DWORD *)v23, v26, 32);
          if ( v32 > 0 )
          {
            v28 = v32;
            if ( !o_wmemcpy_s_0(S1, 0x21u, v26, v32) )
              goto LABEL_27;
          }
          else
          {
            GetLastError();
          }
        }
        v33 = *(_DWORD *)v23;
        v34 = 0;
        if ( v33 <= 0x20 )
        {
          if ( !v33 )
            goto LABEL_29;
        }
        else
        {
          v33 = 32;
        }
        do
        {
          mbtowc(&S1[v34], &v24[v34], 1u);
          v34 = (unsigned int)(v34 + 1);
        }
        while ( (unsigned int)v34 < v33 );
LABEL_29:
        S1[v33] = 0;
        if ( !v26 )
        {
LABEL_32:
          v20 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_33;
        }
LABEL_30:
        ProcessHeap = GetProcessHeap();
        if ( ProcessHeap )
          HeapFree(ProcessHeap, 0, v26);
        goto LABEL_32;
      }
LABEL_36:
      WDiagGetTime((LPFILETIME)a1 + 18);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 3360);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
         && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 114, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a5);
  }
  v30 = SaveSelectionList(a1, v5);
  if ( (*((_BYTE *)a1 + 3448) & 4) == 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    v35 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      cchWideChar,
      *((_QWORD *)a1 + 435),
      *((_DWORD *)a1 + 868),
      v35,
      (__int64)"WDiagProcessAcmSelectionList",
      109);
  }
  *((_DWORD *)a1 + 862) &= ~4u;
  *((_DWORD *)a1 + 868) = 1901;
  *((_QWORD *)a1 + 435) = "WDiagProcessAcmSelectionList";
  *((_DWORD *)a1 + 864) = 0;
  LeaveCriticalSection(v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 115, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return v30;
}

```

## disassembly

```asm
0x18002b0a8  mov     [rsp+arg_8], rbx
0x18002b0ad  push    rbp
0x18002b0ae  push    rsi
0x18002b0af  push    rdi
0x18002b0b0  push    r12
0x18002b0b2  push    r13
0x18002b0b4  push    r14
0x18002b0b6  push    r15
0x18002b0b8  sub     rsp, 100h
0x18002b0bf  mov     rax, cs:__security_cookie
0x18002b0c6  xor     rax, rsp
0x18002b0c9  mov     [rsp+138h+var_48], rax
0x18002b0d1  mov     r12, r9
0x18002b0d4  mov     [rsp+138h+var_A8], r9
0x18002b0dc  mov     rdi, r8
0x18002b0df  mov     r13, rcx
0x18002b0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0e9  lea     r15, WPP_GLOBAL_Control
0x18002b0f0  cmp     rcx, r15
0x18002b0f3  jnz     loc_18002B4E7
0x18002b0f9  lea     rbx, [r13+0D18h]
0x18002b100  call    cs:__imp_GetCurrentThreadId
0x18002b106  lea     rbp, [rbx+8]
0x18002b10a  mov     esi, eax
0x18002b10c  mov     rcx, rbp; lpCriticalSection
0x18002b10f  call    cs:__imp_EnterCriticalSection
0x18002b115  mov     rcx, [rbx+58h]; hHandle
0x18002b119  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b11c  call    cs:__imp_WaitForSingleObject
0x18002b122  test    byte ptr [rbx+60h], 4
0x18002b126  lea     rax, aWdiagprocessac_2; "WDiagProcessAcmSelectionList"
0x18002b12d  mov     r14d, 72Ch
0x18002b133  jnz     loc_18002B6C2
0x18002b139  or      dword ptr [rbx+60h], 4
0x18002b13d  mov     [rbx+68h], esi
0x18002b140  mov     [rbx+6Ch], r14d
0x18002b144  mov     [rbx+70h], rax
0x18002b148  test    rdi, rdi
0x18002b14b  jz      loc_18002B581
0x18002b151  imul    ebp, [rdi], 2B0h
0x18002b157  mov     r14d, [r13+0A8h]
0x18002b15e  add     ebp, 8
0x18002b161  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b168  cmp     rcx, r15
0x18002b16b  jz      short loc_18002B191
0x18002b16d  test    dword ptr [rcx+0E4h], 200h
0x18002b177  jz      short loc_18002B191
0x18002b179  mov     rcx, [rcx+0D8h]
0x18002b180  lea     r8, WPP_79512908d13336da9f44adf151438c1a_Traceguids
0x18002b187  mov     edx, 13h
0x18002b18c  call    WPP_SF_
0x18002b191  mov     ecx, ebp; dwBytes
0x18002b193  call    ?WDiagAllocMem@@YAPEAXK@Z; WDiagAllocMem(ulong)
0x18002b198  mov     rsi, rax
0x18002b19b  test    rax, rax
0x18002b19e  jz      loc_18002B6AB
0x18002b1a4  mov     r8d, ebp; Size
0x18002b1a7  mov     rdx, rdi; Src
0x18002b1aa  mov     rcx, rax; void *
0x18002b1ad  call    memcpy_0
0x18002b1b2  lea     ecx, [r14-1]
0x18002b1b6  mov     eax, 0CCCCCCCDh
0x18002b1bb  mul     ecx
0x18002b1bd  xor     r14d, r14d
0x18002b1c0  shr     edx, 2
0x18002b1c3  lea     eax, [rdx+rdx*4]
0x18002b1c6  sub     ecx, eax
0x18002b1c8  mov     eax, ecx
0x18002b1ca  imul    r15, rax, 270h
0x18002b1d1  mov     rcx, [r15+r13+318h]; lpMem
0x18002b1d9  test    rcx, rcx
0x18002b1dc  jz      short loc_18002B1E3
0x18002b1de  call    ?WDiagFreeMem@@YAXPEAX@Z; WDiagFreeMem(void *)
0x18002b1e3  mov     [r15+r13+318h], rsi
0x18002b1eb  lea     r15, WPP_GLOBAL_Control
0x18002b1f2  mov     r10, cs:WPP_GLOBAL_Control
0x18002b1f9  cmp     r10, r15
0x18002b1fc  jz      short loc_18002B22A
0x18002b1fe  test    dword ptr [r10+0E4h], 200h
0x18002b209  jz      short loc_18002B22A
0x18002b20b  mov     rcx, [r10+0D8h]
0x18002b212  lea     r8, WPP_79512908d13336da9f44adf151438c1a_Traceguids
0x18002b219  mov     edx, 15h
0x18002b21e  call    WPP_SF_
0x18002b223  mov     r10, cs:WPP_GLOBAL_Control
0x18002b22a  test    r14d, r14d
0x18002b22d  jnz     loc_18002B65B
0x18002b233  cmp     r10, r15
0x18002b236  jnz     loc_18002B53A
0x18002b23c  xor     r15d, r15d
0x18002b23f  cmp     [rdi], r15d
0x18002b242  jbe     loc_18002B456
0x18002b248  lea     rax, WPP_GLOBAL_Control
0x18002b24f  cmp     r10, rax
0x18002b252  jz      loc_18002B442
0x18002b258  cmp     byte ptr [r10+0E1h], 3
0x18002b260  jb      loc_18002B442
0x18002b266  test    byte ptr [r10+0E4h], 4
0x18002b26e  jz      loc_18002B442
0x18002b274  mov     eax, r15d
0x18002b277  lea     rsi, [rdi+208h]
0x18002b27e  imul    rcx, rax, 2B0h
0x18002b285  mov     eax, [rcx+rdi+270h]
0x18002b28c  mov     r9d, [rcx+rdi+274h]
0x18002b294  mov     [rsp+138h+var_C4], eax
0x18002b298  mov     eax, [rcx+rdi+26Ch]
0x18002b29f  mov     [rsp+138h+var_C0], eax
0x18002b2a3  mov     eax, [rcx+rdi+244h]
0x18002b2aa  mov     [rsp+138h+var_BC], eax
0x18002b2ae  mov     eax, [rcx+rdi+22Ch]
0x18002b2b5  mov     [rsp+138h+var_B8], eax
0x18002b2bc  mov     eax, [rcx+rdi+23Ch]
0x18002b2c3  mov     [rsp+138h+var_B4], eax
0x18002b2ca  mov     eax, [rcx+rdi+238h]
0x18002b2d1  mov     [rsp+138h+var_B0], eax
0x18002b2d8  mov     eax, [rcx+rdi+27Ch]
0x18002b2df  mov     [rsp+138h+var_AC], eax
0x18002b2e6  mov     [rsp+138h+var_C8], r9d
0x18002b2eb  add     rsi, rcx
0x18002b2ee  jz      loc_18002B3CB
0x18002b2f4  mov     eax, [rsi]
0x18002b2f6  cmp     eax, 20h ; ' '
0x18002b2f9  ja      loc_18002B3CB
0x18002b2ff  inc     eax
0x18002b301  cmp     eax, 21h ; '!'
0x18002b304  ja      loc_18002B3CB
0x18002b30a  xor     eax, eax
0x18002b30c  lea     r12, [rsi+4]
0x18002b310  mov     [rsp+138h+S1], ax
0x18002b318  test    r12, r12
0x18002b31b  jz      loc_18002B3CB
0x18002b321  lea     ecx, [rax+42h]; dwBytes
0x18002b324  call    AllocWLMem
0x18002b329  mov     r14, rax
0x18002b32c  test    rax, rax
0x18002b32f  jz      loc_18002B600
0x18002b335  xor     ecx, ecx
0x18002b337  mov     [rsp+138h+cchWideChar], 20h ; ' '; cchWideChar
0x18002b33f  mov     [rax], cx
0x18002b342  mov     r8, r12; lpMultiByteStr
0x18002b345  mov     r9d, [rsi]; cbMultiByte
0x18002b348  mov     [rsp+138h+lpWideCharStr], rax; lpWideCharStr
0x18002b34d  lea     edx, [rcx+8]; dwFlags
0x18002b350  mov     ecx, 0FDE9h; CodePage
0x18002b355  call    cs:__imp_MultiByteToWideChar
0x18002b35b  test    eax, eax
0x18002b35d  jle     loc_18002B5D0
0x18002b363  movsxd  rbp, eax
0x18002b366  lea     rcx, [rsp+138h+S1]; S1
0x18002b36e  mov     r9, rbp; N
0x18002b371  mov     r8, r14; S2
0x18002b374  mov     edx, 21h ; '!'; N1
0x18002b379  call    _o_wmemcpy_s_0
0x18002b37e  test    eax, eax
0x18002b380  jnz     loc_18002B5D6
0x18002b386  xor     eax, eax
0x18002b388  mov     [rsp+rbp*2+138h+S1], ax
0x18002b390  jmp     short loc_18002B3AB
0x18002b392  test    esi, esi
0x18002b394  jnz     loc_18002B610
0x18002b39a  xor     eax, eax
0x18002b39c  mov     ecx, esi
0x18002b39e  mov     [rsp+rcx*2+138h+S1], ax
0x18002b3a6  test    r14, r14
0x18002b3a9  jz      short loc_18002B3C4
0x18002b3ab  call    cs:__imp_GetProcessHeap
0x18002b3b1  test    rax, rax
0x18002b3b4  jz      short loc_18002B3C4
0x18002b3b6  mov     r8, r14; lpMem
0x18002b3b9  xor     edx, edx; dwFlags
0x18002b3bb  mov     rcx, rax; hHeap
0x18002b3be  call    cs:__imp_HeapFree
0x18002b3c4  mov     r10, cs:WPP_GLOBAL_Control
0x18002b3cb  mov     eax, [rsp+138h+var_C8]
0x18002b3cf  lea     r9d, [r15+1]
0x18002b3d3  mov     rcx, [r10+0D8h]
0x18002b3da  mov     [rsp+138h+var_D8], eax
0x18002b3de  mov     eax, [rsp+138h+var_C4]
0x18002b3e2  mov     [rsp+138h+var_E0], eax
0x18002b3e6  mov     eax, [rsp+138h+var_C0]
0x18002b3ea  mov     dword ptr [rsp+138h+var_E8], eax
0x18002b3ee  mov     eax, [rsp+138h+var_BC]
0x18002b3f2  mov     dword ptr [rsp+138h+var_F0], eax
0x18002b3f6  mov     eax, [rsp+138h+var_B8]
0x18002b3fd  mov     dword ptr [rsp+138h+var_F8], eax
0x18002b401  mov     eax, [rsp+138h+var_B4]
0x18002b408  mov     dword ptr [rsp+138h+var_100], eax
0x18002b40c  mov     eax, [rsp+138h+var_B0]
0x18002b413  mov     dword ptr [rsp+138h+var_108], eax
0x18002b417  mov     eax, [rsp+138h+var_AC]
0x18002b41e  mov     [rsp+138h+cchWideChar], eax; int
0x18002b422  lea     rax, [rsp+138h+S1]
0x18002b42a  mov     [rsp+138h+lpWideCharStr], rax
0x18002b42f  call    WPP_SF_dSDddddddd
0x18002b434  mov     r10, cs:WPP_GLOBAL_Control
0x18002b43b  lea     rax, WPP_GLOBAL_Control
0x18002b442  inc     r15d
0x18002b445  cmp     r15d, [rdi]
0x18002b448  jb      loc_18002B24F
0x18002b44e  mov     r12, [rsp+138h+var_A8]
0x18002b456  lea     rcx, [r13+90h]; lpFileTime
0x18002b45d  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002b462  lea     r15, WPP_GLOBAL_Control
0x18002b469  lea     rbp, [rbx+8]
0x18002b46d  mov     rdx, r12; struct _LIST_ENTRY *
0x18002b470  mov     rcx, r13; struct _WD_INTERFACE_CONTEXT *
0x18002b473  call    ?SaveSelectionList@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAU_LIST_ENTRY@@@Z; SaveSelectionList(_WD_INTERFACE_CONTEXT *,_LIST_ENTRY *)
0x18002b478  test    byte ptr [rbx+60h], 4
0x18002b47c  mov     edi, eax
0x18002b47e  mov     esi, 76Dh
0x18002b483  jz      loc_18002B774
0x18002b489  lea     r14, aWdiagprocessac_2; "WDiagProcessAcmSelectionList"
0x18002b490  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18002b494  mov     rcx, rbp; lpCriticalSection
0x18002b497  mov     [rbx+78h], esi
0x18002b49a  mov     [rbx+80h], r14
0x18002b4a1  mov     dword ptr [rbx+68h], 0
0x18002b4a8  call    cs:__imp_LeaveCriticalSection
0x18002b4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4b5  cmp     rcx, r15
0x18002b4b8  jnz     short loc_18002B514
0x18002b4ba  mov     eax, edi
0x18002b4bc  mov     rcx, [rsp+138h+var_48]
0x18002b4c4  xor     rcx, rsp; StackCookie
0x18002b4c7  call    __security_check_cookie
0x18002b4cc  mov     rbx, [rsp+138h+arg_8]
0x18002b4d4  add     rsp, 100h
0x18002b4db  pop     r15
0x18002b4dd  pop     r14
0x18002b4df  pop     r13
0x18002b4e1  pop     r12
0x18002b4e3  pop     rdi
0x18002b4e4  pop     rsi
0x18002b4e5  pop     rbp
0x18002b4e6  retn
0x18002b4e7  test    dword ptr [rcx+0E4h], 200h
0x18002b4f1  jz      loc_18002B0F9
0x18002b4f7  mov     rcx, [rcx+0D8h]
0x18002b4fe  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18002b505  mov     edx, 6Eh ; 'n'
0x18002b50a  call    WPP_SF_
0x18002b50f  jmp     loc_18002B0F9
0x18002b514  test    dword ptr [rcx+0E4h], 200h
0x18002b51e  jz      short loc_18002B4BA
0x18002b520  mov     rcx, [rcx+0D8h]
0x18002b527  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18002b52e  mov     edx, 73h ; 's'
0x18002b533  call    WPP_SF_
0x18002b538  jmp     short loc_18002B4BA
0x18002b53a  cmp     byte ptr [r10+0E1h], 3
0x18002b542  jb      loc_18002B23C
0x18002b548  test    byte ptr [r10+0E4h], 4
0x18002b550  jz      loc_18002B23C
0x18002b556  mov     r9d, [rdi]
0x18002b559  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18002b560  mov     rcx, [r10+0D8h]
0x18002b567  mov     edx, 6Fh ; 'o'
0x18002b56c  mov     dword ptr [rsp+138h+lpWideCharStr], ebp
0x18002b570  call    WPP_SF_DD
0x18002b575  mov     r10, cs:WPP_GLOBAL_Control
0x18002b57c  jmp     loc_18002B23C
0x18002b581  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b588  cmp     rcx, r15
0x18002b58b  jz      loc_18002B46D
0x18002b591  cmp     byte ptr [rcx+0E1h], 3
0x18002b598  jb      loc_18002B46D
0x18002b59e  test    byte ptr [rcx+0E4h], 4
0x18002b5a5  jz      loc_18002B46D
0x18002b5ab  mov     r9d, [rsp+138h+arg_20]
0x18002b5b3  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18002b5ba  mov     rcx, [rcx+0D8h]
0x18002b5c1  mov     edx, 72h ; 'r'
0x18002b5c6  call    WPP_SF_d
0x18002b5cb  jmp     loc_18002B46D
0x18002b5d0  call    cs:__imp_GetLastError
0x18002b5d6  mov     r9d, [rsi]; cbMultiByte
0x18002b5d9  mov     r8, r12; lpMultiByteStr
0x18002b5dc  mov     [rsp+138h+cchWideChar], 20h ; ' '; cchWideChar
0x18002b5e4  mov     edx, 8; dwFlags
0x18002b5e9  xor     ecx, ecx; CodePage
0x18002b5eb  mov     [rsp+138h+lpWideCharStr], r14; lpWideCharStr
0x18002b5f0  call    cs:__imp_MultiByteToWideChar
0x18002b5f6  test    eax, eax
0x18002b5f8  jg      short loc_18002B637
0x18002b5fa  call    cs:__imp_GetLastError
0x18002b600  mov     esi, [rsi]
0x18002b602  xor     ebp, ebp
0x18002b604  cmp     esi, 20h ; ' '
0x18002b607  jbe     loc_18002B392
0x18002b60d  lea     esi, [rbp+20h]
0x18002b610  lea     rcx, [rsp+138h+S1]
0x18002b618  mov     r8d, 1; SrcSizeInBytes
0x18002b61e  lea     rcx, [rcx+rbp*2]; DstCh
0x18002b622  lea     rdx, [r12+rbp]; SrcCh
0x18002b626  call    cs:__imp_mbtowc
0x18002b62c  inc     ebp
0x18002b62e  cmp     ebp, esi
0x18002b630  jb      short loc_18002B610
0x18002b632  jmp     loc_18002B39A
0x18002b637  movsxd  rbp, eax
  ... truncated ...
```
