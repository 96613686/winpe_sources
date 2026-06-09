# PfSvProcessCommand

- ea: `0x18005afd0`
- end: `0x18005b4c9`
- name: `PfSvProcessCommand`
- size: `1273`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `4`
- callee_count: `17`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007cbc`
- `0x18005aefc`
- `0x18005af4c`
- `0x1800971b0`

## callees

- `0x180032574`
- `0x180039f94`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18005afd0`
- `0x18005bfcc`
- `0x180071db8`
- `0x1800789a8`
- `0x180082378`
- `0x180083494`
- `0x180090198`
- `0x180096d40`
- `0x18009e35c`
- `0x18009e3d0`
- `0x1800a8b44`
- `0x1800abd94`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!_wfopen` at `0x18005b2d1`
- `msvcrt!_wfopen` at `0x18005b2d1`
- `msvcrt!srand` at `0x18005b075`
- `msvcrt!srand` at `0x18005b075`
- `msvcrt!fclose` at `0x18005b497`
- `msvcrt!fclose` at `0x18005b497`
- `msvcrt!fprintf` at `0x18005b2f5`
- `msvcrt!fprintf` at `0x18005b2f5`
- `ntdll!NtSetSystemInformation` at `0x18005b16c`
- `ntdll!NtSetSystemInformation` at `0x18005b264`
- `ntdll!NtSetSystemInformation` at `0x18005b16c`
- `ntdll!NtSetSystemInformation` at `0x18005b264`
- `ntdll!RtlNtStatusToDosError` at `0x18005b270`
- `ntdll!RtlNtStatusToDosError` at `0x18005b270`
- `ntdll!NtClose` at `0x18005b489`
- `ntdll!NtClose` at `0x18005b489`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005b06d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005b06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b19c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b19c`

## string_xrefs

- `0x18005b2ee`: `Could not open %S for write!\n`

## pseudocode

```c
__int64 __fastcall PfSvProcessCommand(_QWORD *a1, __int64 a2)
{
  int v2; // r8d
  HANDLE v3; // r15
  unsigned int v6; // ebx
  FILE *v7; // r12
  int *v8; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // r14d
  DWORD TickCount; // eax
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // r14d
  char v17; // cl
  int v18; // ecx
  __int64 v19; // rdx
  unsigned int v20; // ebx
  int v21; // ecx
  HANDLE CurrentThread; // rax
  int v23; // r14d
  unsigned int v24; // eax
  int v25; // eax
  ULONG v26; // eax
  FILE *v27; // rax
  int v28; // eax
  __int64 v29; // r10
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  void *CurrentTime; // rax
  struct _RTL_CRITICAL_SECTION *v35; // r10
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  int v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v41; // [rsp+50h] [rbp-B0h]
  _BYTE v42[24]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 SystemInformation; // [rsp+78h] [rbp-88h] BYREF
  __int128 v44; // [rsp+88h] [rbp-78h]
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = *(_DWORD *)(a2 + 4);
  v3 = 0;
  Handle = 0;
  memset(v42, 0, sizeof(v42));
  if ( (v2 & 0x800000) != 0 )
  {
    if ( v2 == 0x800000 )
      return (unsigned int)PfApFetchProcessStartCommand(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4064LL));
    else
      return 87;
  }
  v7 = 0;
  v8 = (int *)(a2 + 8);
  if ( (v2 & 0x40000) != 0 )
  {
    v9 = *v8;
    v10 = *v8 & 0x7F;
    if ( v10 )
    {
      TickCount = GetTickCount();
      srand(TickCount);
      v2 = *(_DWORD *)(a2 + 4);
    }
    v12 = *(_QWORD *)&PfSvcGlobals;
    v13 = 100;
    v14 = 100;
    if ( v10 < 0x64 )
      v14 = v10;
    v15 = (v9 >> 8) & 0x7F;
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 4160LL) = 0;
    *(_DWORD *)(v12 + 4152) = v14;
    if ( v15 < 0x64 )
      v13 = v15;
    v2 &= ~0x40000u;
    *(_DWORD *)(a2 + 4) = v2;
    *(_DWORD *)(v12 + 4156) = v13;
  }
  if ( (v2 & 0x80000) != 0 )
  {
    v16 = *v8;
    v17 = *v8;
    SystemInformation = 0;
    v44 = 0;
    v18 = v17 & 3;
    if ( v18 )
    {
      v19 = *(_QWORD *)&PfSvcGlobals;
      v20 = 0;
      *(_QWORD *)&v40 = 0x800000001LL;
      *((_QWORD *)&v40 + 1) = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 512LL);
      v21 = v18 - 1;
      if ( v21 )
      {
        if ( v21 == 2 )
        {
          v20 = 1;
          DWORD1(v40) = 10;
        }
      }
      else
      {
        v20 = -1;
        DWORD1(v40) = 6;
      }
      if ( (v16 & 8) != 0 )
      {
        *(_QWORD *)&SystemInformation = 0x6B7568430000002DLL;
        DWORD2(SystemInformation) = 11;
        *(_QWORD *)&v44 = &v40;
        DWORD2(v44) = 16;
        NtSetSystemInformation(SystemSuperfetchInformation, &SystemInformation, 0x20u);
        v19 = *(_QWORD *)&PfSvcGlobals;
      }
      if ( (v16 & 4) != 0 )
      {
        *(_DWORD *)(v19 + 244) ^= (*(_DWORD *)(v19 + 244) ^ ((v16 - 1) << 16)) & 0x30000;
        CurrentThread = GetCurrentThread();
        PfSvServiceThreadSetPriority(*(_QWORD *)&PfSvcGlobals, CurrentThread, v20);
      }
    }
    *(_DWORD *)(a2 + 4) &= ~0x80000u;
    v2 = *(_DWORD *)(a2 + 4);
  }
  if ( (v2 & 0x400000) == 0 )
  {
    v6 = 0;
LABEL_32:
    if ( (v2 & 0x2000) == 0 )
      goto LABEL_45;
    StringCbPrintfW(pszDest, 0x208u, L"%s\\MemoryAnalysis.csv", *(_QWORD *)&PfSvcGlobals + 888LL);
    v7 = _wfopen(pszDest, L"wt");
    if ( !v7 )
    {
      v27 = _acrt_iob_func(2u);
      fprintf(v27, "Could not open %S for write!\n", pszDest);
      v6 = 996;
      goto LABEL_68;
    }
    v28 = *v8;
    if ( (*v8 & 0x800000) != 0 )
    {
      v28 = -1;
    }
    else
    {
      if ( v28 )
      {
        if ( (v28 & 0xFF000000) != 0 )
          goto LABEL_43;
      }
      else
      {
        *v8 = 1;
        v28 = 1;
      }
      v28 |= 0xFF000000;
    }
    *v8 = v28;
LABEL_43:
    *(_DWORD *)&v42[8] = v28;
    *(_QWORD *)&v42[12] = 0;
    *(_QWORD *)(a2 + 16) = v42;
    *(_DWORD *)&v42[20] = 0;
    *(_QWORD *)v42 = v7;
    PfSvMemoryAnalyze(v42);
    PfScMemoryAnalyze(*(_QWORD *)&PfSvcGlobals + 96LL, v42);
    v29 = *(_QWORD *)&PfSvcGlobals;
    v30 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1792LL);
    if ( !v30 )
      goto LABEL_46;
    PfRpcServerMemoryAnalyze(v30, v42);
LABEL_45:
    v29 = *(_QWORD *)&PfSvcGlobals;
LABEL_46:
    v31 = *(_DWORD *)(a2 + 4);
    if ( v31 == 0x8000 )
    {
      if ( *v8 == 4 )
      {
        RdbCacheGetStoreset(a1[1], a2);
        goto LABEL_68;
      }
      if ( *v8 != 6 )
      {
        v6 = 87;
        goto LABEL_68;
      }
      v26 = RdbAttachStateUpdate(a2);
      goto LABEL_29;
    }
    if ( v31 == 0x200000 )
    {
      v32 = a1[2];
      if ( !v32 )
      {
        v6 = 1062;
        goto LABEL_68;
      }
      v26 = RdBtRpcProcessCommand(v32, a2, 24);
      goto LABEL_29;
    }
    if ( (v31 & 0x20000) == 0 )
      goto LABEL_65;
    if ( *v8 == 4 )
    {
      v33 = *(_QWORD *)(v29 + 4048);
      if ( v33 )
      {
        *(_DWORD *)(v33 + 1080) = 0;
        CurrentTime = (void *)PfsActionItemGetCurrentTime();
LABEL_63:
        Handle = CurrentTime;
        PfsActionItemQueueEx(v35 + 43);
      }
    }
    else
    {
      if ( *v8 != 3 )
      {
LABEL_65:
        if ( !*a1 )
        {
          v6 = v31 != 0 ? 0x15 : 0;
          goto LABEL_68;
        }
        v26 = PfSvSuperfetchProcessCommand(*a1, a2);
        goto LABEL_29;
      }
      if ( *(_QWORD *)(v29 + 4040) )
      {
        CurrentTime = (void *)PfsActionItemGetCurrentTime();
        goto LABEL_63;
      }
    }
    *(_DWORD *)(a2 + 4) &= ~0x20000u;
    v31 = *(_DWORD *)(a2 + 4);
    goto LABEL_65;
  }
  v23 = *v8;
  v39 = 0;
  v40 = 0;
  v38 = v23;
  v41 = 0;
  v24 = PfSvFIGetHandle(&Handle);
  v3 = Handle;
  v6 = v24;
  if ( v24 )
    goto LABEL_68;
  v6 = PfSvFICommand(Handle, 2228248, &v38, 4, 0, &v39);
  if ( v6 )
    goto LABEL_68;
  v6 = 0;
  *((_QWORD *)&v40 + 1) = 15;
  *((_QWORD *)&v41 + 1) = 4;
  *(_QWORD *)&v40 = 0x6B7568430000002DLL;
  *(_QWORD *)&v41 = &v38;
  v25 = NtSetSystemInformation(SystemSuperfetchInformation, &v40, 0x20u);
  if ( v25 >= 0 )
  {
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 240LL) += v23;
    *(_DWORD *)(a2 + 4) &= ~0x400000u;
    v2 = *(_DWORD *)(a2 + 4);
    goto LABEL_32;
  }
  v26 = RtlNtStatusToDosError(v25);
LABEL_29:
  v6 = v26;
LABEL_68:
  if ( v3 )
    NtClose(v3);
  if ( v7 )
    fclose(v7);
  return v6;
}

```

## disassembly

```asm
0x18005afd0  mov     [rsp-8+arg_10], rbx
0x18005afd5  push    rbp
0x18005afd6  push    rsi
0x18005afd7  push    rdi
0x18005afd8  push    r12
0x18005afda  push    r13
0x18005afdc  push    r14
0x18005afde  push    r15
0x18005afe0  lea     rbp, [rsp-1C0h]
0x18005afe8  sub     rsp, 2C0h
0x18005afef  mov     rax, cs:__security_cookie
0x18005aff6  xor     rax, rsp
0x18005aff9  mov     [rbp+1F0h+var_40], rax
0x18005b000  mov     r8d, [rdx+4]
0x18005b004  xor     eax, eax
0x18005b006  xor     r15d, r15d
0x18005b009  mov     [rsp+2F0h+var_280], rax
0x18005b00e  mov     eax, 800000h
0x18005b013  mov     [rsp+2F0h+Handle], r15
0x18005b018  xorps   xmm0, xmm0
0x18005b01b  mov     rdi, rdx
0x18005b01e  mov     r13, rcx
0x18005b021  movups  [rsp+2F0h+var_290], xmm0
0x18005b026  test    eax, r8d
0x18005b029  jz      short loc_18005B054
0x18005b02b  cmp     r8d, eax
0x18005b02e  jnz     short loc_18005B04A
0x18005b030  mov     rcx, cs:PfSvcGlobals
0x18005b037  mov     rcx, [rcx+0FE0h]
0x18005b03e  call    PfApFetchProcessStartCommand
0x18005b043  mov     ebx, eax
0x18005b045  jmp     loc_18005B49D
0x18005b04a  mov     ebx, 57h ; 'W'
0x18005b04f  jmp     loc_18005B49D
0x18005b054  xor     r12d, r12d
0x18005b057  lea     rsi, [rdx+8]
0x18005b05b  bt      r8d, 12h
0x18005b060  jnb     short loc_18005B0BB
0x18005b062  mov     ebx, [rsi]
0x18005b064  mov     r14d, ebx
0x18005b067  and     r14d, 7Fh
0x18005b06b  jz      short loc_18005B07F
0x18005b06d  call    cs:__imp_GetTickCount
0x18005b073  mov     ecx, eax; Seed
0x18005b075  call    cs:__imp_srand
0x18005b07b  mov     r8d, [rdi+4]
0x18005b07f  mov     rdx, cs:PfSvcGlobals
0x18005b086  mov     ecx, 64h ; 'd'
0x18005b08b  cmp     r14d, ecx
0x18005b08e  mov     eax, ecx
0x18005b090  cmovb   eax, r14d
0x18005b094  shr     ebx, 8
0x18005b097  and     ebx, 7Fh
0x18005b09a  mov     [rdx+1040h], r12d
0x18005b0a1  cmp     ebx, ecx
0x18005b0a3  mov     [rdx+1038h], eax
0x18005b0a9  cmovb   ecx, ebx
0x18005b0ac  btr     r8d, 12h
0x18005b0b1  mov     [rdi+4], r8d
0x18005b0b5  mov     [rdx+103Ch], ecx
0x18005b0bb  mov     r9d, 1
0x18005b0c1  bt      r8d, 13h
0x18005b0c6  jnb     loc_18005B1BD
0x18005b0cc  mov     r14d, [rsi]
0x18005b0cf  xorps   xmm0, xmm0
0x18005b0d2  mov     ecx, r14d
0x18005b0d5  movups  [rsp+2F0h+SystemInformation], xmm0
0x18005b0da  movups  [rbp+1F0h+var_268], xmm0
0x18005b0de  and     ecx, 3
0x18005b0e1  jz      loc_18005B1B4
0x18005b0e7  mov     rdx, cs:PfSvcGlobals
0x18005b0ee  xor     ebx, ebx
0x18005b0f0  mov     dword ptr [rsp+2F0h+var_2B0], r9d
0x18005b0f5  mov     dword ptr [rsp+2F0h+var_2B0+4], 8
0x18005b0fd  mov     rax, [rdx+200h]
0x18005b104  mov     qword ptr [rsp+2F0h+var_2B0+8], rax
0x18005b109  sub     ecx, r9d
0x18005b10c  jz      short loc_18005B125
0x18005b10e  sub     ecx, r9d
0x18005b111  jz      short loc_18005B130
0x18005b113  cmp     ecx, r9d
0x18005b116  jnz     short loc_18005B130
0x18005b118  mov     ebx, r9d
0x18005b11b  mov     dword ptr [rsp+2F0h+var_2B0+4], 0Ah
0x18005b123  jmp     short loc_18005B130
0x18005b125  or      ebx, 0FFFFFFFFh
0x18005b128  mov     dword ptr [rsp+2F0h+var_2B0+4], 6
0x18005b130  test    r14b, 8
0x18005b134  jz      short loc_18005B179
0x18005b136  mov     r8d, 20h ; ' '; SystemInformationLength
0x18005b13c  mov     dword ptr [rsp+2F0h+SystemInformation+4], 6B756843h
0x18005b144  lea     rax, [rsp+2F0h+var_2B0]
0x18005b149  mov     dword ptr [rsp+2F0h+SystemInformation], 2Dh ; '-'
0x18005b151  lea     rdx, [rsp+2F0h+SystemInformation]; SystemInformation
0x18005b156  mov     dword ptr [rbp+1F0h+SystemInformation+8], 0Bh
0x18005b15d  mov     qword ptr [rbp+1F0h+var_268], rax
0x18005b161  lea     ecx, [r8+2Fh]; SystemInformationClass
0x18005b165  mov     dword ptr [rbp+1F0h+var_268+8], 10h
0x18005b16c  call    cs:__imp_NtSetSystemInformation
0x18005b172  mov     rdx, cs:PfSvcGlobals
0x18005b179  test    r14b, 4
0x18005b17d  jz      short loc_18005B1B4
0x18005b17f  mov     eax, [rdx+0F4h]
0x18005b185  lea     ecx, [r14-1]
0x18005b189  shl     ecx, 10h
0x18005b18c  xor     ecx, eax
0x18005b18e  and     ecx, 30000h
0x18005b194  xor     ecx, eax
0x18005b196  mov     [rdx+0F4h], ecx
0x18005b19c  call    cs:__imp_GetCurrentThread
0x18005b1a2  mov     rcx, cs:PfSvcGlobals
0x18005b1a9  mov     r8d, ebx
0x18005b1ac  mov     rdx, rax
0x18005b1af  call    PfSvServiceThreadSetPriority
0x18005b1b4  btr     dword ptr [rdi+4], 13h
0x18005b1b9  mov     r8d, [rdi+4]
0x18005b1bd  bt      r8d, 16h
0x18005b1c2  jnb     loc_18005B296
0x18005b1c8  mov     r14d, [rsi]
0x18005b1cb  lea     rcx, [rsp+2F0h+Handle]
0x18005b1d0  xorps   xmm0, xmm0
0x18005b1d3  mov     [rsp+2F0h+var_2B4], r12d
0x18005b1d8  movups  [rsp+2F0h+var_2B0], xmm0
0x18005b1dd  mov     [rsp+2F0h+var_2B8], r14d
0x18005b1e2  movups  [rsp+2F0h+var_2A0], xmm0
0x18005b1e7  call    PfSvFIGetHandle
0x18005b1ec  mov     r15, [rsp+2F0h+Handle]
0x18005b1f1  mov     ebx, eax
0x18005b1f3  test    eax, eax
0x18005b1f5  jnz     loc_18005B481
0x18005b1fb  lea     rax, [rsp+2F0h+var_2B4]
0x18005b200  mov     edx, 220018h
0x18005b205  mov     [rsp+2F0h+var_2C8], rax
0x18005b20a  lea     r9d, [rbx+4]
0x18005b20e  lea     r8, [rsp+2F0h+var_2B8]
0x18005b213  mov     [rsp+2F0h+var_2D0], r12
0x18005b218  mov     rcx, r15
0x18005b21b  call    PfSvFICommand
0x18005b220  mov     ebx, eax
0x18005b222  test    eax, eax
0x18005b224  jnz     loc_18005B481
0x18005b22a  xor     ebx, ebx
0x18005b22c  mov     qword ptr [rsp+2F0h+var_2B0+8], 0Fh
0x18005b235  lea     rax, [rsp+2F0h+var_2B8]
0x18005b23a  mov     qword ptr [rsp+2F0h+var_2A0+8], 4
0x18005b243  lea     rdx, [rsp+2F0h+var_2B0]; SystemInformation
0x18005b248  mov     dword ptr [rsp+2F0h+var_2B0+4], 6B756843h
0x18005b250  mov     dword ptr [rsp+2F0h+var_2B0], 2Dh ; '-'
0x18005b258  lea     r8d, [rbx+20h]; SystemInformationLength
0x18005b25c  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x18005b261  lea     ecx, [rbx+4Fh]; SystemInformationClass
0x18005b264  call    cs:__imp_NtSetSystemInformation
0x18005b26a  test    eax, eax
0x18005b26c  jns     short loc_18005B27D
0x18005b26e  mov     ecx, eax; Status
0x18005b270  call    cs:__imp_RtlNtStatusToDosError
0x18005b276  mov     ebx, eax
0x18005b278  jmp     loc_18005B481
0x18005b27d  mov     rax, cs:PfSvcGlobals
0x18005b284  add     [rax+0F0h], r14d
0x18005b28b  btr     dword ptr [rdi+4], 16h
0x18005b290  mov     r8d, [rdi+4]
0x18005b294  jmp     short loc_18005B298
0x18005b296  xor     ebx, ebx
0x18005b298  bt      r8d, 0Dh
0x18005b29d  jnb     loc_18005B387
0x18005b2a3  mov     r9, cs:PfSvcGlobals
0x18005b2aa  lea     r8, aSMemoryanalysi; "%s\\MemoryAnalysis.csv"
0x18005b2b1  add     r9, 378h
0x18005b2b8  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x18005b2bc  mov     edx, 208h; cbDest
0x18005b2c1  call    StringCbPrintfW
0x18005b2c6  lea     rdx, aWt; "wt"
0x18005b2cd  lea     rcx, [rbp+1F0h+pszDest]; FileName
0x18005b2d1  call    cs:__imp__wfopen
0x18005b2d7  mov     r12, rax
0x18005b2da  test    rax, rax
0x18005b2dd  jnz     short loc_18005B305
0x18005b2df  lea     ecx, [rax+2]; Ix
0x18005b2e2  call    __acrt_iob_func
0x18005b2e7  mov     rcx, rax; Stream
0x18005b2ea  lea     r8, [rbp+1F0h+pszDest]
0x18005b2ee  lea     rdx, aCouldNotOpenSF; "Could not open %S for write!\n"
0x18005b2f5  call    cs:__imp_fprintf
0x18005b2fb  mov     ebx, 3E4h
0x18005b300  jmp     loc_18005B481
0x18005b305  mov     eax, [rsi]
0x18005b307  bt      eax, 17h
0x18005b30b  jnb     short loc_18005B312
0x18005b30d  or      eax, 0FFFFFFFFh
0x18005b310  jmp     short loc_18005B32E
0x18005b312  mov     ecx, 0FF000000h
0x18005b317  test    eax, eax
0x18005b319  jz      short loc_18005B321
0x18005b31b  test    ecx, eax
0x18005b31d  jz      short loc_18005B32C
0x18005b31f  jmp     short loc_18005B330
0x18005b321  mov     dword ptr [rsi], 1
0x18005b327  mov     eax, 1
0x18005b32c  or      eax, ecx
0x18005b32e  mov     [rsi], eax
0x18005b330  mov     dword ptr [rsp+2F0h+var_290+8], eax
0x18005b334  lea     rcx, [rsp+2F0h+var_290]
0x18005b339  lea     rax, [rsp+2F0h+var_290]
0x18005b33e  mov     qword ptr [rsp+2F0h+var_290+0Ch], rbx
0x18005b343  mov     [rdi+10h], rax
0x18005b347  mov     dword ptr [rsp+2F0h+var_280+4], ebx
0x18005b34b  mov     qword ptr [rsp+2F0h+var_290], r12
0x18005b350  call    PfSvMemoryAnalyze
0x18005b355  mov     rcx, cs:PfSvcGlobals
0x18005b35c  lea     rdx, [rsp+2F0h+var_290]
0x18005b361  add     rcx, 60h ; '`'
0x18005b365  call    PfScMemoryAnalyze
0x18005b36a  mov     r10, cs:PfSvcGlobals
0x18005b371  mov     rcx, [r10+700h]
0x18005b378  test    rcx, rcx
0x18005b37b  jz      short loc_18005B38E
0x18005b37d  lea     rdx, [rsp+2F0h+var_290]
0x18005b382  call    PfRpcServerMemoryAnalyze
0x18005b387  mov     r10, cs:PfSvcGlobals
0x18005b38e  mov     eax, [rdi+4]
0x18005b391  cmp     eax, 8000h
0x18005b396  jnz     short loc_18005B3CA
0x18005b398  cmp     dword ptr [rsi], 4
0x18005b39b  jnz     short loc_18005B3AE
0x18005b39d  mov     rcx, [r13+8]
0x18005b3a1  mov     rdx, rdi
0x18005b3a4  call    RdbCacheGetStoreset
0x18005b3a9  jmp     loc_18005B481
0x18005b3ae  cmp     dword ptr [rsi], 6
0x18005b3b1  jnz     short loc_18005B3C0
0x18005b3b3  mov     rcx, rdi
0x18005b3b6  call    RdbAttachStateUpdate
0x18005b3bb  jmp     loc_18005B276
0x18005b3c0  mov     ebx, 57h ; 'W'
0x18005b3c5  jmp     loc_18005B481
0x18005b3ca  cmp     eax, 200000h
0x18005b3cf  jnz     short loc_18005B3FB
0x18005b3d1  mov     rcx, [r13+10h]
0x18005b3d5  test    rcx, rcx
0x18005b3d8  jz      short loc_18005B3F1
0x18005b3da  mov     r9d, 1
0x18005b3e0  mov     rdx, rdi
0x18005b3e3  lea     r8d, [r9+17h]
0x18005b3e7  call    RdBtRpcProcessCommand
0x18005b3ec  jmp     loc_18005B276
0x18005b3f1  mov     ebx, 426h
0x18005b3f6  jmp     loc_18005B481
0x18005b3fb  bt      eax, 11h
0x18005b3ff  jnb     short loc_18005B464
0x18005b401  cmp     dword ptr [rsi], 4
0x18005b404  jnz     short loc_18005B42B
0x18005b406  mov     rax, [r10+0FD0h]
0x18005b40d  test    rax, rax
0x18005b410  jz      short loc_18005B45C
0x18005b412  mov     [rax+438h], ebx
0x18005b418  mov     r10, cs:PfSvcGlobals
0x18005b41f  call    PfsActionItemGetCurrentTime
0x18005b424  mov     edx, 16h
0x18005b429  jmp     short loc_18005B443
0x18005b42b  cmp     dword ptr [rsi], 3
0x18005b42e  jnz     short loc_18005B464
0x18005b430  cmp     [r10+0FC8h], rbx
0x18005b437  jz      short loc_18005B45C
0x18005b439  call    PfsActionItemGetCurrentTime
0x18005b43e  mov     edx, 26h ; '&'
0x18005b443  xor     r9d, r9d
0x18005b446  mov     [rsp+2F0h+Handle], rax
0x18005b44b  lea     r8, [rsp+2F0h+Handle]
0x18005b450  lea     rcx, [r10+6B8h]; lpCriticalSection
0x18005b457  call    PfsActionItemQueueEx
0x18005b45c  btr     dword ptr [rdi+4], 11h
0x18005b461  mov     eax, [rdi+4]
0x18005b464  mov     rcx, [r13+0]
0x18005b468  test    rcx, rcx
0x18005b46b  jz      short loc_18005B47A
0x18005b46d  mov     rdx, rdi
0x18005b470  call    PfSvSuperfetchProcessCommand
0x18005b475  jmp     loc_18005B276
0x18005b47a  neg     eax
0x18005b47c  sbb     ebx, ebx
0x18005b47e  and     ebx, 15h
0x18005b481  test    r15, r15
0x18005b484  jz      short loc_18005B48F
0x18005b486  mov     rcx, r15; Handle
0x18005b489  call    cs:__imp_NtClose
0x18005b48f  test    r12, r12
0x18005b492  jz      short loc_18005B49D
0x18005b494  mov     rcx, r12; Stream
0x18005b497  call    cs:__imp_fclose
0x18005b49d  mov     eax, ebx
0x18005b49f  mov     rcx, [rbp+1F0h+var_40]
0x18005b4a6  xor     rcx, rsp; StackCookie
0x18005b4a9  call    __security_check_cookie
0x18005b4ae  mov     rbx, [rsp+2F0h+arg_10]
0x18005b4b6  add     rsp, 2C0h
0x18005b4bd  pop     r15
0x18005b4bf  pop     r14
0x18005b4c1  pop     r13
0x18005b4c3  pop     r12
  ... truncated ...
```
