# WdcNetworkMonitor::AddressThread(void *)

- ea: `0x18007dfc0`
- end: `0x18007e1ea`
- name: `?AddressThread@WdcNetworkMonitor@@CAKPEAX@Z`
- size: `554`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180012420`
- `0x1800150d0`
- `0x180016880`
- `0x18001d64c`
- `0x18003a3c0`
- `0x18003b0ac`
- `0x18007de4c`
- `0x18007dfc0`
- `0x18007e778`
- `0x18007ed0c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e0a4`
- `KERNEL32!GetLastError` at `0x18007e0a4`
- `KERNEL32!WaitForSingleObject` at `0x18007e112`
- `KERNEL32!WaitForSingleObject` at `0x18007e112`
- `KERNEL32!WaitForMultipleObjects` at `0x18007e091`
- `KERNEL32!WaitForMultipleObjects` at `0x18007e091`
- `WS2_32!__imp_WSAGetLastError` at `0x18007e033`
- `WS2_32!__imp_WSAGetLastError` at `0x18007e033`
- `WS2_32!__imp_WSAStartup` at `0x18007e029`
- `WS2_32!__imp_WSAStartup` at `0x18007e029`
- `WS2_32!__imp_WSACleanup` at `0x18007e1bb`
- `WS2_32!__imp_WSACleanup` at `0x18007e1bb`

## string_xrefs

- `0x18007e181`: `WdcNetworkMonitor::AddressThread`

## pseudocode

```c
__int64 __fastcall WdcNetworkMonitor::AddressThread(HANDLE *Parameter)
{
  struct _WDC_NET_ADDRESS *v2; // rdi
  const char *v3; // rdx
  int v4; // r8d
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // r14
  signed int v7; // ebx
  DWORD v8; // eax
  const char *v9; // rdx
  int v10; // r8d
  signed int LastError; // eax
  signed int v12; // eax
  WdcNetworkMonitor *v13; // rcx
  int v14; // eax
  WdcNetworkMonitor *v15; // rcx
  unsigned int AddressKey; // eax
  const char *v17; // rdx
  int v18; // r8d
  unsigned __int64 v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  struct _WDC_NET_ADDRESS *v22; // [rsp+38h] [rbp-C8h] BYREF
  struct _WDC_DATA_INFO *v23; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-B8h] BYREF
  WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF

  v23 = 0;
  v2 = 0;
  v22 = 0;
  v21 = 0;
  *(_OWORD *)Handles = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
    WSAGetLastError();
  v5 = (unsigned __int16 *)WdcAlloc(0x802u, v3, v4);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v7 = 0;
    Handles[0] = Parameter[1170];
    Handles[1] = Parameter[1146];
    while ( v7 >= 0 )
    {
      v8 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v8 )
        goto LABEL_15;
      if ( v8 == 1 )
        break;
      LastError = GetLastError();
      v7 = 0;
      if ( LastError )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
      }
      if ( v7 < 0 )
        goto LABEL_5;
      while ( 1 )
      {
LABEL_15:
        if ( v2 )
        {
          WdcFree(v2, v9, v10);
          v22 = 0;
        }
        v12 = WdcNetworkMonitor::AddressPop((WdcNetworkMonitor *)Parameter, &v22);
        v2 = v22;
        v7 = v12;
        if ( v12 == 1 )
          break;
        v14 = WdcNetworkMonitor::DecodeAddress(v13, v22, 1, v6, v20);
        v7 = v14;
        if ( v14 < 0 )
          goto LABEL_24;
        if ( WaitForSingleObject(Parameter[1146], 0) != 258 )
        {
          v7 = 0;
          goto LABEL_26;
        }
        WdcLockObject::LockEnter((WdcLockObject *)Parameter, &v21);
        AddressKey = WdcNetworkMonitor::GetAddressKey(v15, v2);
        if ( (int)WdcDataMonitor::InfoFind((WdcDataMonitor *)Parameter, AddressKey, &v23) >= 0 )
        {
          v14 = WdcNetworkMonitor::SetAddress((WdcNetworkMonitor *)Parameter, v23, v6);
          v7 = v14;
          if ( v14 < 0 )
          {
LABEL_24:
            LODWORD(v20) = v14;
            goto LABEL_25;
          }
        }
        WdcLockObject::LockLeave((WdcLockObject *)Parameter, &v21);
      }
    }
  }
  else
  {
    v7 = -2147024882;
LABEL_5:
    LODWORD(v20) = v7;
LABEL_25:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\network.cpp",
      "WdcNetworkMonitor::AddressThread",
      0,
      L"FAILURE: 0x%08x",
      v20);
  }
LABEL_26:
  WdcLockObject::LockLeave((WdcLockObject *)Parameter, &v21);
  if ( v2 )
    WdcFree(v2, v17, v18);
  if ( v6 )
    WdcFree(v6, v17, v18);
  WSACleanup();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007dfc0  mov     [rsp-8+arg_8], rbx
0x18007dfc5  mov     [rsp-8+arg_10], rsi
0x18007dfca  push    rbp
0x18007dfcb  push    rdi
0x18007dfcc  push    r14
0x18007dfce  lea     rbp, [rsp-110h]
0x18007dfd6  sub     rsp, 210h
0x18007dfdd  mov     rax, cs:__security_cookie
0x18007dfe4  xor     rax, rsp
0x18007dfe7  mov     [rbp+120h+var_20], rax
0x18007dfee  mov     rsi, rcx
0x18007dff1  mov     [rsp+220h+var_1E0], 0
0x18007dffa  xor     edi, edi
0x18007dffc  lea     rcx, [rsp+220h+WSAData]; void *
0x18007e001  xorps   xmm0, xmm0
0x18007e004  mov     [rsp+220h+var_1E8], rdi
0x18007e009  xor     edx, edx; Val
0x18007e00b  mov     [rsp+220h+var_1F0], edi
0x18007e00f  mov     r8d, 198h; Size
0x18007e015  movups  xmmword ptr [rsp+220h+Handles], xmm0
0x18007e01a  call    memset_0
0x18007e01f  mov     ecx, 202h; wVersionRequested
0x18007e024  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x18007e029  call    cs:__imp_WSAStartup
0x18007e02f  test    eax, eax
0x18007e031  jz      short loc_18007E039
0x18007e033  call    cs:__imp_WSAGetLastError
0x18007e039  mov     ecx, 802h; dwBytes
0x18007e03e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18007e043  mov     r14, rax
0x18007e046  test    rax, rax
0x18007e049  jnz     short loc_18007E059
0x18007e04b  mov     ebx, 8007000Eh
0x18007e050  mov     [rsp+220h+var_200], ebx
0x18007e054  jmp     loc_18007E177
0x18007e059  xor     eax, eax
0x18007e05b  mov     [r14], ax
0x18007e05f  xor     ebx, ebx
0x18007e061  mov     rax, [rsi+2490h]
0x18007e068  mov     [rsp+220h+Handles], rax
0x18007e06d  mov     rax, [rsi+23D0h]
0x18007e074  mov     [rsp+220h+Handles+8], rax
0x18007e079  test    ebx, ebx
0x18007e07b  js      loc_18007E194
0x18007e081  xor     r8d, r8d; bWaitAll
0x18007e084  lea     rdx, [rsp+220h+Handles]; lpHandles
0x18007e089  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18007e08d  lea     ecx, [r8+2]; nCount
0x18007e091  call    cs:__imp_WaitForMultipleObjects
0x18007e097  test    eax, eax
0x18007e099  jz      short loc_18007E0C3
0x18007e09b  cmp     eax, 1
0x18007e09e  jz      loc_18007E194
0x18007e0a4  call    cs:__imp_GetLastError
0x18007e0aa  xor     ebx, ebx
0x18007e0ac  test    eax, eax
0x18007e0ae  jz      short loc_18007E0BF
0x18007e0b0  jg      short loc_18007E0B6
0x18007e0b2  mov     ebx, eax
0x18007e0b4  jmp     short loc_18007E0BF
0x18007e0b6  movzx   ebx, ax
0x18007e0b9  or      ebx, 80070000h
0x18007e0bf  test    ebx, ebx
0x18007e0c1  js      short loc_18007E050
0x18007e0c3  test    rdi, rdi
0x18007e0c6  jz      short loc_18007E0D9
0x18007e0c8  mov     rcx, rdi; void *
0x18007e0cb  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18007e0d0  mov     [rsp+220h+var_1E8], 0
0x18007e0d9  lea     rdx, [rsp+220h+var_1E8]; struct _WDC_NET_ADDRESS **
0x18007e0de  mov     rcx, rsi; this
0x18007e0e1  call    ?AddressPop@WdcNetworkMonitor@@AEAAJPEAPEAU_WDC_NET_ADDRESS@@@Z; WdcNetworkMonitor::AddressPop(_WDC_NET_ADDRESS * *)
0x18007e0e6  mov     rdi, [rsp+220h+var_1E8]
0x18007e0eb  mov     ebx, eax
0x18007e0ed  cmp     eax, 1
0x18007e0f0  jz      short loc_18007E079
0x18007e0f2  mov     r9, r14; unsigned __int16 *
0x18007e0f5  mov     r8d, 1; int
0x18007e0fb  mov     rdx, rdi; struct _WDC_NET_ADDRESS *
0x18007e0fe  call    ?DecodeAddress@WdcNetworkMonitor@@AEAAJPEAU_WDC_NET_ADDRESS@@HPEAG_K@Z; WdcNetworkMonitor::DecodeAddress(_WDC_NET_ADDRESS *,int,ushort *,unsigned __int64)
0x18007e103  mov     ebx, eax
0x18007e105  test    eax, eax
0x18007e107  js      short loc_18007E173
0x18007e109  mov     rcx, [rsi+23D0h]; hHandle
0x18007e110  xor     edx, edx; dwMilliseconds
0x18007e112  call    cs:__imp_WaitForSingleObject
0x18007e118  cmp     eax, 102h
0x18007e11d  jnz     short loc_18007E16F
0x18007e11f  lea     rdx, [rsp+220h+var_1F0]; int *
0x18007e124  mov     rcx, rsi; this
0x18007e127  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x18007e12c  mov     rdx, rdi; struct _WDC_NET_ADDRESS *
0x18007e12f  call    ?GetAddressKey@WdcNetworkMonitor@@AEAAKPEAU_WDC_NET_ADDRESS@@@Z; WdcNetworkMonitor::GetAddressKey(_WDC_NET_ADDRESS *)
0x18007e134  mov     edx, eax; unsigned __int64
0x18007e136  lea     r8, [rsp+220h+var_1E0]; struct _WDC_DATA_INFO **
0x18007e13b  mov     rcx, rsi; this
0x18007e13e  call    ?InfoFind@WdcDataMonitor@@QEAAJ_KPEAPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::InfoFind(unsigned __int64,_WDC_DATA_INFO * *)
0x18007e143  test    eax, eax
0x18007e145  js      short loc_18007E15D
0x18007e147  mov     rdx, [rsp+220h+var_1E0]; struct _WDC_NETWORK_INFO *
0x18007e14c  mov     r8, r14; unsigned __int16 *
0x18007e14f  mov     rcx, rsi; this
0x18007e152  call    ?SetAddress@WdcNetworkMonitor@@AEAAJPEAU_WDC_NETWORK_INFO@@PEBG@Z; WdcNetworkMonitor::SetAddress(_WDC_NETWORK_INFO *,ushort const *)
0x18007e157  mov     ebx, eax
0x18007e159  test    eax, eax
0x18007e15b  js      short loc_18007E173
0x18007e15d  lea     rdx, [rsp+220h+var_1F0]; int *
0x18007e162  mov     rcx, rsi; this
0x18007e165  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x18007e16a  jmp     loc_18007E0C3
0x18007e16f  xor     ebx, ebx
0x18007e171  jmp     short loc_18007E194
0x18007e173  mov     [rsp+220h+var_200], eax
0x18007e177  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18007e17e  xor     r8d, r8d; int
0x18007e181  lea     rdx, aWdcnetworkmoni_3; "WdcNetworkMonitor::AddressThread"
0x18007e188  lea     rcx, aBaseDiagnosisP_11; "base\\diagnosis\\pdui\\perfmon\\mon\\ne"...
0x18007e18f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18007e194  lea     rdx, [rsp+220h+var_1F0]; int *
0x18007e199  mov     rcx, rsi; this
0x18007e19c  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x18007e1a1  test    rdi, rdi
0x18007e1a4  jz      short loc_18007E1AE
0x18007e1a6  mov     rcx, rdi; void *
0x18007e1a9  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18007e1ae  test    r14, r14
0x18007e1b1  jz      short loc_18007E1BB
0x18007e1b3  mov     rcx, r14; void *
0x18007e1b6  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18007e1bb  call    cs:__imp_WSACleanup
0x18007e1c1  mov     eax, ebx
0x18007e1c3  mov     rcx, [rbp+120h+var_20]
0x18007e1ca  xor     rcx, rsp; StackCookie
0x18007e1cd  call    __security_check_cookie
0x18007e1d2  lea     r11, [rsp+220h+var_10]
0x18007e1da  mov     rbx, [r11+28h]
0x18007e1de  mov     rsi, [r11+30h]
0x18007e1e2  mov     rsp, r11
0x18007e1e5  pop     r14
0x18007e1e7  pop     rdi
0x18007e1e8  pop     rbp
0x18007e1e9  retn
```
