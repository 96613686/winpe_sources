# CreateMiniportDevices

- ea: `0x180006290`
- end: `0x1800067ae`
- name: `CreateMiniportDevices`
- size: `1310`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800067b4`

## callees

- `0x180006290`
- `0x1800067b4`
- `0x180006c60`
- `0x180006f5c`
- `0x18001d1da`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000650f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000650f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000659b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000659b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000661c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000663c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006679`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000661c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000663c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006664`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006664`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000670d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000670d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180006580`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180006580`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x1800065ef`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x1800065ef`

## pseudocode

```c
__int64 __fastcall CreateMiniportDevices(int a1, unsigned int a2, char a3, _QWORD *a4)
{
  HANDLE ProcessHeap; // rax
  signed int v7; // ebx
  __int16 MiniportsEnabledRegistry; // cx
  __int64 i; // r15
  const wchar_t *v10; // rax
  _QWORD *v11; // rdi
  signed int v12; // eax
  DWORD v13; // eax
  signed int LastError; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v20; // [rsp+40h] [rbp-59h] BYREF
  __int64 v21; // [rsp+48h] [rbp-51h] BYREF
  HANDLE hHandle[2]; // [rsp+50h] [rbp-49h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-39h]
  int v24; // [rsp+70h] [rbp-29h] BYREF
  const wchar_t *v25; // [rsp+78h] [rbp-21h]
  const wchar_t *v26; // [rsp+80h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-1h]
  __int16 v28; // [rsp+100h] [rbp+67h]

  memset_0(&v24, 0, 0x48u);
  ProcessHeap = GetProcessHeap();
  v20 = HeapAlloc(ProcessHeap, 8u, 8LL * (a2 + 1));
  if ( !v20 )
  {
    v7 = -2147024882;
    goto LABEL_64;
  }
  v7 = 0;
  v24 = 72;
  v27 = 8;
  MiniportsEnabledRegistry = GetMiniportsEnabledRegistry();
  v28 = MiniportsEnabledRegistry;
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    if ( !a1 )
      goto LABEL_63;
    v20[i] = 0;
    if ( (a1 & 1) != 0 )
    {
      a1 ^= 1u;
      if ( (MiniportsEnabledRegistry & 1) == 0 )
        continue;
      v25 = L"MS_AGILEVPNMINIPORT";
      v26 = L"ms_agilevpnminiport";
      goto LABEL_34;
    }
    if ( (a1 & 2) != 0 )
    {
      a1 ^= 2u;
      if ( (MiniportsEnabledRegistry & 2) == 0 )
        continue;
      v25 = L"MS_L2TPMINIPORT";
      v26 = L"ms_l2tpminiport";
      goto LABEL_34;
    }
    if ( (a1 & 4) != 0 )
    {
      a1 ^= 4u;
      if ( (MiniportsEnabledRegistry & 4) == 0 )
        continue;
      v25 = L"MS_PPTPMINIPORT";
      v10 = L"ms_pptpminiport";
LABEL_33:
      v26 = v10;
      goto LABEL_34;
    }
    if ( (a1 & 0x10) != 0 )
    {
      a1 ^= 0x10u;
      if ( (MiniportsEnabledRegistry & 0x10) == 0 )
        continue;
      v25 = L"MS_SSTPMINIPORT";
      v26 = L"ms_sstpminiport";
LABEL_34:
      v11 = v20;
      v21 = 0;
      *(_OWORD *)hHandle = 0;
      *(_OWORD *)lpMem = 0;
      hHandle[0] = CreateEventW(0, 0, 0, 0);
      if ( hHandle[0] )
      {
        v7 = SwDeviceCreate(
               L"MSRRAS",
               L"SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}",
               &v24,
               0,
               0,
               &RrasSwDeviceCreateCallback,
               hHandle,
               &v21);
        if ( v7 < 0 )
          goto LABEL_46;
        v13 = WaitForSingleObject(hHandle[0], 0x7530u);
        if ( !v13 )
          goto LABEL_43;
        if ( v13 == 258 )
        {
          v7 = -2147023436;
          goto LABEL_46;
        }
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 < 0 )
        {
LABEL_46:
          if ( v21 )
            SwDeviceClose();
        }
        else
        {
LABEL_43:
          if ( SLODWORD(lpMem[0]) < 0 )
          {
            v7 = (signed int)lpMem[0];
            goto LABEL_45;
          }
          v16 = GetProcessHeap();
          v17 = HeapAlloc(v16, 8u, 0x10u);
          if ( !v17 )
          {
            v7 = -2147024882;
            goto LABEL_46;
          }
          v17[1] = v21;
          *v17 = lpMem[1];
          lpMem[1] = 0;
          v11[i] = v17;
        }
      }
      else
      {
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
LABEL_45:
        if ( v7 < 0 )
          goto LABEL_46;
      }
      if ( hHandle[0] )
        CloseHandle(hHandle[0]);
      if ( lpMem[1] )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, lpMem[1]);
      }
      if ( v7 )
        goto LABEL_64;
      if ( (a3 & 4) != 0 )
      {
        v7 = WaitForInterface(*(_QWORD *)v20[i]);
        if ( v7 )
          goto LABEL_64;
      }
      MiniportsEnabledRegistry = v28;
      continue;
    }
    if ( (a1 & 8) != 0 )
    {
      a1 ^= 8u;
      if ( (MiniportsEnabledRegistry & 8) == 0 )
        continue;
      v25 = L"MS_PPPOEMINIPORT";
      v10 = L"ms_pppoeminiport";
      goto LABEL_33;
    }
    if ( (a1 & 0x100) != 0 )
    {
      a1 ^= 0x100u;
      if ( (MiniportsEnabledRegistry & 0x100) == 0 )
        continue;
      v25 = L"MS_GREMINIPORT";
      v10 = L"ms_greminiport";
      goto LABEL_33;
    }
    if ( (a1 & 0x20) != 0 )
    {
      a1 ^= 0x20u;
      if ( (MiniportsEnabledRegistry & 0x20) == 0 )
        continue;
      v25 = L"MS_NDISWANIP";
      v10 = L"ms_ndiswanip";
      goto LABEL_33;
    }
    if ( (a1 & 0x40) != 0 )
    {
      a1 ^= 0x40u;
      if ( (MiniportsEnabledRegistry & 0x40) == 0 )
        continue;
      v25 = L"MS_NDISWANIPV6";
      v10 = L"ms_ndiswanipv6";
      goto LABEL_33;
    }
    if ( (a1 & 0x80u) == 0 )
      goto LABEL_62;
    a1 ^= 0x80u;
    if ( (MiniportsEnabledRegistry & 0x80u) != 0 )
    {
      v25 = L"MS_NDISWANBH";
      v10 = L"ms_ndiswanbh";
      goto LABEL_33;
    }
  }
  if ( a1 )
  {
LABEL_62:
    v7 = -2147024809;
    goto LABEL_64;
  }
LABEL_63:
  v18 = v20;
  v20 = 0;
  *a4 = v18;
LABEL_64:
  ConfigureMiniports(0, 2, &v20, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006290  mov     [rsp-8+arg_18], r9
0x180006295  mov     [rsp-8+arg_10], r8d
0x18000629a  push    rbp
0x18000629b  push    rbx
0x18000629c  push    r13
0x18000629e  push    r14
0x1800062a0  lea     rbp, [rsp-3Fh]
0x1800062a5  sub     rsp, 0D8h
0x1800062ac  mov     r13d, edx
0x1800062af  mov     r14d, ecx
0x1800062b2  xor     edx, edx; Val
0x1800062b4  lea     rcx, [rbp+57h+var_80]; void *
0x1800062b8  mov     r8d, 48h ; 'H'; Size
0x1800062be  call    memset_0
0x1800062c3  lea     ebx, [r13+1]
0x1800062c7  mov     [rbp+57h+var_B0], 0
0x1800062cf  shl     rbx, 3
0x1800062d3  call    cs:__imp_GetProcessHeap
0x1800062da  nop     dword ptr [rax+rax+00h]
0x1800062df  mov     r8, rbx; dwBytes
0x1800062e2  mov     edx, 8; dwFlags
0x1800062e7  mov     rcx, rax; hHeap
0x1800062ea  call    cs:__imp_HeapAlloc
0x1800062f1  nop     dword ptr [rax+rax+00h]
0x1800062f6  mov     [rbp+57h+var_B0], rax
0x1800062fa  test    rax, rax
0x1800062fd  jnz     short loc_180006309
0x1800062ff  mov     ebx, 8007000Eh
0x180006304  jmp     loc_18000678A
0x180006309  mov     [rsp+0F0h+arg_8], rsi
0x180006311  xor     ebx, ebx
0x180006313  mov     [rsp+0F0h+var_20], rdi
0x18000631b  mov     [rsp+0F0h+var_30], r15
0x180006323  mov     [rbp+57h+var_80], 48h ; 'H'
0x18000632a  mov     [rbp+57h+var_58], 8
0x180006331  call    GetMiniportsEnabledRegistry
0x180006336  mov     ecx, eax
0x180006338  mov     [rbp+57h+arg_0], eax
0x18000633b  xor     r15d, r15d
0x18000633e  mov     [rsp+0F0h+var_28], r12
0x180006346  lea     rdx, c_szInstId_MS_AgileVpnMiniport; "MS_AGILEVPNMINIPORT"
0x18000634d  lea     r8, c_szHwId_MS_AgileVpnMiniport; "ms_agilevpnminiport"
0x180006354  lea     r11, c_szInstId_MS_L2tpMiniport; "MS_L2TPMINIPORT"
0x18000635b  lea     r9, c_szInstId_MS_SstpMiniport; "MS_SSTPMINIPORT"
0x180006362  lea     r10, c_szHwId_MS_SstpMiniport; "ms_sstpminiport"
0x180006369  lea     rdi, c_szHwId_MS_L2tpMiniport; "ms_l2tpminiport"
0x180006370  lea     rsi, c_szInstId_MS_PptpMiniport; "MS_PPTPMINIPORT"
0x180006377  cmp     r15d, r13d
0x18000637a  jnb     loc_18000674B
0x180006380  test    r14d, r14d
0x180006383  jz      loc_180006757
0x180006389  mov     rax, [rbp+57h+var_B0]
0x18000638d  lea     r12, ds:0[r15*8]
0x180006395  mov     qword ptr [r12+rax], 0
0x18000639d  test    r14b, 1
0x1800063a1  jz      short loc_1800063BD
0x1800063a3  xor     r14d, 1
0x1800063a7  test    cl, 1
0x1800063aa  jz      loc_1800066E1
0x1800063b0  mov     [rbp+57h+var_78], rdx
0x1800063b4  mov     [rbp+57h+var_70], r8
0x1800063b8  jmp     loc_1800064EE
0x1800063bd  test    r14b, 2
0x1800063c1  jz      short loc_1800063DD
0x1800063c3  xor     r14d, 2
0x1800063c7  test    cl, 2
0x1800063ca  jz      loc_1800066E1
0x1800063d0  mov     [rbp+57h+var_78], r11
0x1800063d4  mov     [rbp+57h+var_70], rdi
0x1800063d8  jmp     loc_1800064EE
0x1800063dd  test    r14b, 4
0x1800063e1  jz      short loc_180006400
0x1800063e3  xor     r14d, 4
0x1800063e7  test    cl, 4
0x1800063ea  jz      loc_1800066E1
0x1800063f0  mov     [rbp+57h+var_78], rsi
0x1800063f4  lea     rax, c_szHwId_MS_PptpMiniport; "ms_pptpminiport"
0x1800063fb  jmp     loc_1800064EA
0x180006400  test    r14b, 10h
0x180006404  jz      short loc_180006420
0x180006406  xor     r14d, 10h
0x18000640a  test    cl, 10h
0x18000640d  jz      loc_1800066E1
0x180006413  mov     [rbp+57h+var_78], r9
0x180006417  mov     [rbp+57h+var_70], r10
0x18000641b  jmp     loc_1800064EE
0x180006420  test    r14b, 8
0x180006424  jz      short loc_18000644A
0x180006426  xor     r14d, 8
0x18000642a  test    cl, 8
0x18000642d  jz      loc_1800066E1
0x180006433  lea     rax, c_szInstId_MS_PppoeMiniport; "MS_PPPOEMINIPORT"
0x18000643a  mov     [rbp+57h+var_78], rax
0x18000643e  lea     rax, c_szHwId_MS_PppoeMiniport; "ms_pppoeminiport"
0x180006445  jmp     loc_1800064EA
0x18000644a  bt      r14d, 8
0x18000644f  jnb     short loc_180006474
0x180006451  btc     r14d, 8
0x180006456  bt      ecx, 8
0x18000645a  jnb     loc_1800066E1
0x180006460  lea     rax, c_szInstId_MS_GreMiniport; "MS_GREMINIPORT"
0x180006467  mov     [rbp+57h+var_78], rax
0x18000646b  lea     rax, c_szHwId_MS_GreMiniport; "ms_greminiport"
0x180006472  jmp     short loc_1800064EA
0x180006474  test    r14b, 20h
0x180006478  jz      short loc_18000649B
0x18000647a  xor     r14d, 20h
0x18000647e  test    cl, 20h
0x180006481  jz      loc_1800066E1
0x180006487  lea     rax, c_szInstId_MS_NdisWanIp; "MS_NDISWANIP"
0x18000648e  mov     [rbp+57h+var_78], rax
0x180006492  lea     rax, c_szHwId_MS_NdisWanIp; "ms_ndiswanip"
0x180006499  jmp     short loc_1800064EA
0x18000649b  test    r14b, 40h
0x18000649f  jz      short loc_1800064C2
0x1800064a1  xor     r14d, 40h
0x1800064a5  test    cl, 40h
0x1800064a8  jz      loc_1800066E1
0x1800064ae  lea     rax, c_szInstId_MS_NdisWanIpv6; "MS_NDISWANIPV6"
0x1800064b5  mov     [rbp+57h+var_78], rax
0x1800064b9  lea     rax, c_szHwId_MS_NdisWanIpv6; "ms_ndiswanipv6"
0x1800064c0  jmp     short loc_1800064EA
0x1800064c2  test    r14b, r14b
0x1800064c5  jns     loc_180006750
0x1800064cb  btc     r14d, 7
0x1800064d0  test    cl, cl
0x1800064d2  jns     loc_1800066E1
0x1800064d8  lea     rax, c_szInstId_MS_NdisWanBh; "MS_NDISWANBH"
0x1800064df  mov     [rbp+57h+var_78], rax
0x1800064e3  lea     rax, c_szHwId_MS_NdisWanBh; "ms_ndiswanbh"
0x1800064ea  mov     [rbp+57h+var_70], rax
0x1800064ee  mov     rdi, [rbp+57h+var_B0]
0x1800064f2  xorps   xmm0, xmm0
0x1800064f5  xor     ebx, ebx
0x1800064f7  xor     r9d, r9d; lpName
0x1800064fa  xor     r8d, r8d; bInitialState
0x1800064fd  mov     [rbp+57h+var_A8], rbx
0x180006501  xor     edx, edx; bManualReset
0x180006503  xor     ecx, ecx; lpEventAttributes
0x180006505  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x180006509  mov     esi, ebx
0x18000650b  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x18000650f  call    cs:__imp_CreateEventW
0x180006516  nop     dword ptr [rax+rax+00h]
0x18000651b  mov     [rbp+57h+hHandle], rax
0x18000651f  test    rax, rax
0x180006522  jnz     short loc_180006548
0x180006524  call    cs:__imp_GetLastError
0x18000652b  nop     dword ptr [rax+rax+00h]
0x180006530  mov     ebx, eax
0x180006532  test    eax, eax
0x180006534  jle     loc_1800065E2
0x18000653a  movzx   ebx, ax
0x18000653d  or      ebx, 80070000h
0x180006543  jmp     loc_1800065E2
0x180006548  lea     rax, [rbp+57h+var_A8]
0x18000654c  xor     r9d, r9d
0x18000654f  mov     [rsp+0F0h+var_B8], rax
0x180006554  lea     r8, [rbp+57h+var_80]
0x180006558  lea     rax, [rbp+57h+hHandle]
0x18000655c  mov     [rsp+0F0h+var_C0], rax
0x180006561  lea     rdx, aSwdMsrras5e259; "SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8"...
0x180006568  lea     rax, RrasSwDeviceCreateCallback
0x18000656f  mov     [rsp+0F0h+var_C8], rax
0x180006574  lea     rcx, aMsrras; "MSRRAS"
0x18000657b  mov     [rsp+0F0h+var_D0], rbx
0x180006580  call    cs:__imp_SwDeviceCreate
0x180006587  nop     dword ptr [rax+rax+00h]
0x18000658c  mov     ebx, eax
0x18000658e  test    eax, eax
0x180006590  js      short loc_1800065E6
0x180006592  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180006596  mov     edx, 7530h; dwMilliseconds
0x18000659b  call    cs:__imp_WaitForSingleObject
0x1800065a2  nop     dword ptr [rax+rax+00h]
0x1800065a7  test    eax, eax
0x1800065a9  jz      short loc_1800065D5
0x1800065ab  cmp     eax, 102h
0x1800065b0  jz      loc_1800066E9
0x1800065b6  call    cs:__imp_GetLastError
0x1800065bd  nop     dword ptr [rax+rax+00h]
0x1800065c2  mov     ebx, eax
0x1800065c4  test    eax, eax
0x1800065c6  jle     short loc_1800065D1
0x1800065c8  movzx   ebx, ax
0x1800065cb  or      ebx, 80070000h
0x1800065d1  test    ebx, ebx
0x1800065d3  js      short loc_1800065E6
0x1800065d5  mov     eax, dword ptr [rbp+57h+lpMem]
0x1800065d8  test    eax, eax
0x1800065da  jns     loc_1800066F3
0x1800065e0  mov     ebx, eax
0x1800065e2  test    ebx, ebx
0x1800065e4  jns     short loc_180006648
0x1800065e6  mov     rcx, [rbp+57h+var_A8]
0x1800065ea  test    rcx, rcx
0x1800065ed  jz      short loc_1800065FB
0x1800065ef  call    cs:__imp_SwDeviceClose
0x1800065f6  nop     dword ptr [rax+rax+00h]
0x1800065fb  test    rsi, rsi
0x1800065fe  jz      short loc_180006648
0x180006600  mov     rdi, [rsi]
0x180006603  test    rdi, rdi
0x180006606  jz      short loc_180006628
0x180006608  call    cs:__imp_GetProcessHeap
0x18000660f  nop     dword ptr [rax+rax+00h]
0x180006614  mov     r8, rdi; lpMem
0x180006617  xor     edx, edx; dwFlags
0x180006619  mov     rcx, rax; hHeap
0x18000661c  call    cs:__imp_HeapFree
0x180006623  nop     dword ptr [rax+rax+00h]
0x180006628  call    cs:__imp_GetProcessHeap
0x18000662f  nop     dword ptr [rax+rax+00h]
0x180006634  mov     r8, rsi; lpMem
0x180006637  xor     edx, edx; dwFlags
0x180006639  mov     rcx, rax; hHeap
0x18000663c  call    cs:__imp_HeapFree
0x180006643  nop     dword ptr [rax+rax+00h]
0x180006648  mov     rcx, [rbp+57h+hHandle]; hObject
0x18000664c  test    rcx, rcx
0x18000664f  jz      short loc_18000665D
0x180006651  call    cs:__imp_CloseHandle
0x180006658  nop     dword ptr [rax+rax+00h]
0x18000665d  cmp     [rbp+57h+lpMem+8], 0
0x180006662  jz      short loc_180006685
0x180006664  call    cs:__imp_GetProcessHeap
0x18000666b  nop     dword ptr [rax+rax+00h]
0x180006670  mov     r8, [rbp+57h+lpMem+8]; lpMem
0x180006674  xor     edx, edx; dwFlags
0x180006676  mov     rcx, rax; hHeap
0x180006679  call    cs:__imp_HeapFree
0x180006680  nop     dword ptr [rax+rax+00h]
0x180006685  test    ebx, ebx
0x180006687  jnz     loc_18000676A
0x18000668d  test    byte ptr [rbp+57h+arg_10], 4
0x180006691  jz      short loc_1800066AD
0x180006693  mov     rax, [rbp+57h+var_B0]
0x180006697  mov     rcx, [r12+rax]
0x18000669b  mov     rcx, [rcx]
0x18000669e  call    WaitForInterface
0x1800066a3  mov     ebx, eax
0x1800066a5  test    eax, eax
0x1800066a7  jnz     loc_18000676A
0x1800066ad  mov     ecx, [rbp+57h+arg_0]
0x1800066b0  lea     rsi, c_szInstId_MS_PptpMiniport; "MS_PPTPMINIPORT"
0x1800066b7  lea     rdi, c_szHwId_MS_L2tpMiniport; "ms_l2tpminiport"
0x1800066be  lea     r11, c_szInstId_MS_L2tpMiniport; "MS_L2TPMINIPORT"
0x1800066c5  lea     r10, c_szHwId_MS_SstpMiniport; "ms_sstpminiport"
0x1800066cc  lea     r9, c_szInstId_MS_SstpMiniport; "MS_SSTPMINIPORT"
0x1800066d3  lea     r8, c_szHwId_MS_AgileVpnMiniport; "ms_agilevpnminiport"
0x1800066da  lea     rdx, c_szInstId_MS_AgileVpnMiniport; "MS_AGILEVPNMINIPORT"
0x1800066e1  inc     r15d
0x1800066e4  jmp     loc_180006377
0x1800066e9  mov     ebx, 800705B4h
0x1800066ee  jmp     loc_1800065E6
0x1800066f3  call    cs:__imp_GetProcessHeap
0x1800066fa  nop     dword ptr [rax+rax+00h]
0x1800066ff  mov     edx, 8; dwFlags
0x180006704  mov     r8d, 10h; dwBytes
0x18000670a  mov     rcx, rax; hHeap
0x18000670d  call    cs:__imp_HeapAlloc
0x180006714  nop     dword ptr [rax+rax+00h]
0x180006719  mov     rsi, rax
0x18000671c  test    rax, rax
0x18000671f  jnz     short loc_18000672B
0x180006721  mov     ebx, 8007000Eh
0x180006726  jmp     loc_1800065E6
0x18000672b  mov     rax, [rbp+57h+var_A8]
0x18000672f  mov     [rsi+8], rax
0x180006733  mov     rax, [rbp+57h+lpMem+8]
0x180006737  mov     [rsi], rax
0x18000673a  mov     [rbp+57h+lpMem+8], 0
0x180006742  mov     [rdi+r12], rsi
0x180006746  jmp     loc_180006648
0x18000674b  test    r14d, r14d
0x18000674e  jz      short loc_180006757
0x180006750  mov     ebx, 80070057h
0x180006755  jmp     short loc_18000676A
0x180006757  mov     rax, [rbp+57h+var_B0]
0x18000675b  mov     rcx, [rbp+57h+arg_18]
0x18000675f  mov     [rbp+57h+var_B0], 0
0x180006767  mov     [rcx], rax
0x18000676a  mov     r12, [rsp+0F0h+var_28]
0x180006772  mov     rdi, [rsp+0F0h+var_20]
0x18000677a  mov     rsi, [rsp+0F0h+arg_8]
0x180006782  mov     r15, [rsp+0F0h+var_30]
0x18000678a  xor     r9d, r9d
0x18000678d  lea     r8, [rbp+57h+var_B0]
0x180006791  mov     edx, 2
0x180006796  xor     ecx, ecx
0x180006798  call    ConfigureMiniports
0x18000679d  mov     eax, ebx
0x18000679f  add     rsp, 0D8h
0x1800067a6  pop     r14
0x1800067a8  pop     r13
0x1800067aa  pop     rbx
0x1800067ab  pop     rbp
0x1800067ac  retn
```
