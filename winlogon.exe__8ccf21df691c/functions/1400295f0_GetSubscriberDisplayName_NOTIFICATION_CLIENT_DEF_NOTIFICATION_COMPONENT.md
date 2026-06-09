# GetSubscriberDisplayName(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *)

- ea: `0x1400295f0`
- end: `0x140029aa7`
- name: `?GetSubscriberDisplayName@@YAXPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@@Z`
- size: `1207`
- prototype: `void(struct _NOTIFICATION_CLIENT_DEF *, struct _NOTIFICATION_COMPONENT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400403d8`

## callees

- `0x14000f870`
- `0x14000fb30`
- `0x14001a520`
- `0x140026970`
- `0x1400295f0`
- `0x140031890`
- `0x14005f43c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002963e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14002963e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140029842`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140029842`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029699`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029699`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029a2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029a2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002987f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400299a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400299dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002987f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400299a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400299dc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140029917`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140029917`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140029a3e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009df79`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140029a3e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009df79`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400297de`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400297de`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14002966c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400296cd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14002966c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400296cd`

## pseudocode

```c
void __fastcall GetSubscriberDisplayName(struct _NOTIFICATION_CLIENT_DEF *a1, struct _NOTIFICATION_COMPONENT *a2)
{
  struct _QUERY_SERVICE_CONFIGW *v4; // rsi
  int v5; // r14d
  WCHAR *v6; // r15
  SC_HANDLE v7; // rax
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  LPWSTR lpDisplayName; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  WCHAR *v14; // r8
  __int64 v15; // r10
  WCHAR v16; // r9
  SC_HANDLE v17; // rax
  char v18; // al
  int v19; // edx
  HANDLE v20; // rax
  SC_HANDLE v21; // rcx
  DWORD LastError; // [rsp+28h] [rbp-60h]
  DWORD pcbBytesNeeded; // [rsp+A0h] [rbp+18h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v24; // [rsp+A8h] [rbp+20h]

  v4 = 0;
  v24 = 0;
  v5 = 0;
  pcbBytesNeeded = 0;
  v6 = (WCHAR *)((char *)a2 + 34);
  if ( *((_WORD *)a2 + 17) )
    goto LABEL_49;
  if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 72), L"System-LSM") )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
        (_DWORD)a2,
        *((_QWORD *)a2 + 72));
    }
    if ( !LoadStringW(0, 0x771u, v6, 257) )
    {
      v5 = 1;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          (_DWORD)a2,
          *((_QWORD *)a2 + 72),
          LastError,
          1);
      }
    }
    goto LABEL_49;
  }
  v7 = (SC_HANDLE)*((_QWORD *)a2 + 73);
  if ( !v7 )
  {
    v17 = (SC_HANDLE)*((_QWORD *)a1 + 4);
    if ( !v17 )
    {
      v17 = OpenSCManagerW(0, 0, 1u);
      *((_QWORD *)a1 + 4) = v17;
      if ( !v17 )
      {
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v18 = GetLastError();
        v19 = 72;
        goto LABEL_37;
      }
    }
    v7 = OpenServiceW(v17, *((LPCWSTR *)a2 + 72), 5u);
    *((_QWORD *)a2 + 73) = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v18 = GetLastError();
      v19 = 73;
      goto LABEL_37;
    }
  }
  QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded);
  if ( GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v18 = GetLastError();
    v19 = 74;
    goto LABEL_37;
  }
  v8 = pcbBytesNeeded;
  ProcessHeap = GetProcessHeap();
  v10 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 8u, v8);
  v4 = v10;
  v24 = v10;
  if ( !v10 )
  {
    v5 = 1;
    goto LABEL_49;
  }
  if ( !QueryServiceConfigW(*((SC_HANDLE *)a2 + 73), v10, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v18 = GetLastError();
    v19 = 75;
LABEL_37:
    WPP_SF_Sl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
      (_DWORD)a2,
      v18);
LABEL_20:
    v5 = 1;
    goto LABEL_49;
  }
  lpDisplayName = v4->lpDisplayName;
  v12 = 2147483646;
  v13 = 257;
  v14 = v6;
  v15 = 0;
  while ( v13 )
  {
    if ( !v12 )
      goto LABEL_12;
    v16 = *lpDisplayName;
    if ( !*lpDisplayName )
      goto LABEL_12;
    ++lpDisplayName;
    *v14++ = v16;
    --v13;
    --v12;
    ++v15;
  }
  --v14;
LABEL_12:
  *v14 = 0;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
      (_DWORD)a2,
      (__int64)v6);
  }
LABEL_49:
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v4);
  }
  v21 = (SC_HANDLE)*((_QWORD *)a2 + 73);
  if ( v21 )
  {
    CloseServiceHandle(v21);
    *((_QWORD *)a2 + 73) = 0;
  }
  if ( v5 )
  {
    StringCchCopyW(v6, 0x101u, (const unsigned __int16 *)a2);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, a2);
    }
  }
}

```

## disassembly

```asm
0x1400295f0  mov     rax, rsp
0x1400295f3  mov     [rax+8], rbx
0x1400295f7  mov     [rax+10h], rdx
0x1400295fb  push    rsi
0x1400295fc  push    rdi
0x1400295fd  push    r12
0x1400295ff  push    r14
0x140029601  push    r15
0x140029603  sub     rsp, 60h
0x140029607  mov     rdi, rdx
0x14002960a  mov     rbx, rcx
0x14002960d  xor     r12d, r12d
0x140029610  mov     esi, r12d
0x140029613  mov     [rax+20h], r12
0x140029617  mov     r14d, r12d
0x14002961a  mov     [rax-58h], r12d
0x14002961e  mov     [rax+18h], r12d
0x140029622  lea     r15, [rdx+22h]
0x140029626  cmp     r12w, [r15]
0x14002962a  jnz     loc_1400298C4
0x140029630  lea     rdx, aSystemLsm; "System-LSM"
0x140029637  mov     rcx, [rdi+240h]
0x14002963e  call    cs:__imp__o__wcsicmp
0x140029644  test    eax, eax
0x140029646  jz      loc_14002981B
0x14002964c  mov     rax, [rdi+248h]
0x140029653  test    rax, rax
0x140029656  jz      loc_1400297C1
0x14002965c  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x140029664  xor     r8d, r8d; cbBufSize
0x140029667  xor     edx, edx; lpServiceConfig
0x140029669  mov     rcx, rax; hService
0x14002966c  call    cs:__imp_QueryServiceConfigW
0x140029672  call    cs:__imp_GetLastError
0x140029678  cmp     eax, 7Ah ; 'z'
0x14002967b  jnz     loc_1400299B1
0x140029681  mov     ebx, [rsp+88h+pcbBytesNeeded]
0x140029688  call    cs:__imp_GetProcessHeap
0x14002968e  mov     rcx, rax; hHeap
0x140029691  mov     r8d, ebx; dwBytes
0x140029694  mov     edx, 8; dwFlags
0x140029699  call    cs:__imp_HeapAlloc
0x14002969f  mov     rsi, rax
0x1400296a2  mov     [rsp+88h+arg_18], rax
0x1400296aa  test    rax, rax
0x1400296ad  jz      loc_1400298B9
0x1400296b3  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x1400296bb  mov     r8d, [rsp+88h+pcbBytesNeeded]; cbBufSize
0x1400296c3  mov     rdx, rax; lpServiceConfig
0x1400296c6  mov     rcx, [rdi+248h]; hService
0x1400296cd  call    cs:__imp_QueryServiceConfigW
0x1400296d3  test    eax, eax
0x1400296d5  jz      loc_1400299E9
0x1400296db  mov     rdx, [rsi+38h]
0x1400296df  mov     ecx, 7FFFFFFEh
0x1400296e4  mov     [rsp+88h+var_30], rcx
0x1400296e9  mov     [rsp+88h+var_40], rdx
0x1400296ee  mov     eax, 101h
0x1400296f3  mov     [rsp+88h+var_38], rax
0x1400296f8  mov     r8, r15
0x1400296fb  mov     [rsp+88h+var_50], r15
0x140029700  mov     r10, r12
0x140029703  mov     [rsp+88h+var_48], r12
0x140029708  nop     dword ptr [rax+rax+00000000h]
0x140029710  test    rax, rax
0x140029713  jz      loc_1400297AE
0x140029719  test    rcx, rcx
0x14002971c  jz      short loc_140029758
0x14002971e  movzx   r9d, word ptr [rdx]
0x140029722  test    r9w, r9w
0x140029726  jz      short loc_140029758
0x140029728  add     rdx, 2
0x14002972c  mov     [rsp+88h+var_40], rdx
0x140029731  mov     [r8], r9w
0x140029735  add     r8, 2
0x140029739  mov     [rsp+88h+var_50], r8
0x14002973e  dec     rax
0x140029741  mov     [rsp+88h+var_38], rax
0x140029746  dec     rcx
0x140029749  mov     [rsp+88h+var_30], rcx
0x14002974e  inc     r10
0x140029751  mov     [rsp+88h+var_48], r10
0x140029756  jmp     short loc_140029710
0x140029758  test    rax, rax
0x14002975b  jz      short loc_1400297AE
0x14002975d  mov     [r8], r12w
0x140029761  lea     rbx, WPP_GLOBAL_Control
0x140029768  mov     rcx, cs:WPP_GLOBAL_Control
0x14002976f  cmp     rcx, rbx
0x140029772  jz      loc_140029A19
0x140029778  test    byte ptr [rcx+1Ch], 1
0x14002977c  jz      loc_140029A19
0x140029782  cmp     byte ptr [rcx+19h], 4
0x140029786  jb      loc_140029A19
0x14002978c  mov     edx, 4Ch ; 'L'
0x140029791  mov     [rsp+88h+var_68], r15
0x140029796  mov     r9, rdi
0x140029799  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400297a0  mov     rcx, [rcx+10h]
0x1400297a4  call    WPP_SF_SS
0x1400297a9  jmp     loc_140029A19
0x1400297ae  sub     r8, 2
0x1400297b2  mov     [rsp+88h+var_50], r8
0x1400297b7  dec     r10
0x1400297ba  mov     [rsp+88h+var_48], r10
0x1400297bf  jmp     short loc_14002975D
0x1400297c1  mov     rax, [rbx+20h]
0x1400297c5  test    rax, rax
0x1400297c8  jz      loc_14002990D
0x1400297ce  mov     r8d, 5; dwDesiredAccess
0x1400297d4  mov     rdx, [rdi+240h]; lpServiceName
0x1400297db  mov     rcx, rax; hSCManager
0x1400297de  call    cs:__imp_OpenServiceW
0x1400297e4  mov     [rdi+248h], rax
0x1400297eb  test    rax, rax
0x1400297ee  jnz     loc_14002965C
0x1400297f4  lea     rbx, WPP_GLOBAL_Control
0x1400297fb  mov     rax, cs:WPP_GLOBAL_Control
0x140029802  cmp     rax, rbx
0x140029805  jnz     loc_140029990
0x14002980b  mov     r14d, 1
0x140029811  mov     [rsp+88h+var_58], r14d
0x140029816  jmp     loc_140029A19
0x14002981b  lea     rbx, WPP_GLOBAL_Control
0x140029822  mov     rcx, cs:WPP_GLOBAL_Control
0x140029829  cmp     rcx, rbx
0x14002982c  jnz     loc_1400298D0
0x140029832  mov     r9d, 101h; cchBufferMax
0x140029838  mov     r8, r15; lpBuffer
0x14002983b  mov     edx, 771h; uID
0x140029840  xor     ecx, ecx; hInstance
0x140029842  call    cs:__imp_LoadStringW
0x140029848  test    eax, eax
0x14002984a  jnz     loc_140029A19
0x140029850  mov     r14d, 1
0x140029856  mov     [rsp+88h+var_58], r14d
0x14002985b  mov     rax, cs:WPP_GLOBAL_Control
0x140029862  cmp     rax, rbx
0x140029865  jz      loc_140029A19
0x14002986b  test    [rax+1Ch], r14b
0x14002986f  jz      loc_140029A19
0x140029875  cmp     byte ptr [rax+19h], 2
0x140029879  jb      loc_140029A19
0x14002987f  call    cs:__imp_GetLastError
0x140029885  mov     edx, 47h ; 'G'
0x14002988a  mov     [rsp+88h+var_60], eax
0x14002988e  mov     rax, [rdi+240h]
0x140029895  mov     [rsp+88h+var_68], rax
0x14002989a  mov     r9, rdi
0x14002989d  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400298a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400298ab  mov     rcx, [rcx+10h]
0x1400298af  call    WPP_SF_SSD
0x1400298b4  jmp     loc_140029A19
0x1400298b9  mov     r14d, 1
0x1400298bf  mov     [rsp+88h+var_58], r14d
0x1400298c4  lea     rbx, WPP_GLOBAL_Control
0x1400298cb  jmp     loc_140029A19
0x1400298d0  test    byte ptr [rcx+1Ch], 1
0x1400298d4  jz      loc_140029832
0x1400298da  cmp     byte ptr [rcx+19h], 4
0x1400298de  jb      loc_140029832
0x1400298e4  mov     edx, 46h ; 'F'
0x1400298e9  mov     rax, [rdi+240h]
0x1400298f0  mov     [rsp+88h+var_68], rax
0x1400298f5  mov     r9, rdi
0x1400298f8  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400298ff  mov     rcx, [rcx+10h]
0x140029903  call    WPP_SF_SS
0x140029908  jmp     loc_140029832
0x14002990d  xor     edx, edx; lpDatabaseName
0x14002990f  xor     ecx, ecx; lpMachineName
0x140029911  mov     r8d, 1; dwDesiredAccess
0x140029917  call    cs:__imp_OpenSCManagerW
0x14002991d  mov     [rbx+20h], rax
0x140029921  test    rax, rax
0x140029924  jnz     loc_1400297CE
0x14002992a  lea     rbx, WPP_GLOBAL_Control
0x140029931  mov     rax, cs:WPP_GLOBAL_Control
0x140029938  cmp     rax, rbx
0x14002993b  jz      loc_14002980B
0x140029941  test    byte ptr [rax+1Ch], 1
0x140029945  jz      loc_14002980B
0x14002994b  cmp     byte ptr [rax+19h], 2
0x14002994f  jb      loc_14002980B
0x140029955  call    cs:__imp_GetLastError
0x14002995b  mov     edx, 48h ; 'H'
0x140029960  jmp     short loc_14002996D
0x140029962  call    cs:__imp_GetLastError
0x140029968  mov     edx, 4Bh ; 'K'
0x14002996d  mov     dword ptr [rsp+88h+var_68], eax
0x140029971  mov     r9, rdi
0x140029974  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x14002997b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029982  mov     rcx, [rcx+10h]
0x140029986  call    WPP_SF_Sl
0x14002998b  jmp     loc_14002980B
0x140029990  test    byte ptr [rax+1Ch], 1
0x140029994  jz      loc_14002980B
0x14002999a  cmp     byte ptr [rax+19h], 2
0x14002999e  jb      loc_14002980B
0x1400299a4  call    cs:__imp_GetLastError
0x1400299aa  mov     edx, 49h ; 'I'
0x1400299af  jmp     short loc_14002996D
0x1400299b1  lea     rbx, WPP_GLOBAL_Control
0x1400299b8  mov     rax, cs:WPP_GLOBAL_Control
0x1400299bf  cmp     rax, rbx
0x1400299c2  jz      loc_14002980B
0x1400299c8  test    byte ptr [rax+1Ch], 1
0x1400299cc  jz      loc_14002980B
0x1400299d2  cmp     byte ptr [rax+19h], 2
0x1400299d6  jb      loc_14002980B
0x1400299dc  call    cs:__imp_GetLastError
0x1400299e2  mov     edx, 4Ah ; 'J'
0x1400299e7  jmp     short loc_14002996D
0x1400299e9  lea     rbx, WPP_GLOBAL_Control
0x1400299f0  mov     rax, cs:WPP_GLOBAL_Control
0x1400299f7  cmp     rax, rbx
0x1400299fa  jz      loc_14002980B
0x140029a00  test    byte ptr [rax+1Ch], 1
0x140029a04  jz      loc_14002980B
0x140029a0a  cmp     byte ptr [rax+19h], 2
0x140029a0e  jb      loc_14002980B
0x140029a14  jmp     loc_140029962
0x140029a19  test    rsi, rsi
0x140029a1c  jz      short loc_140029A32
0x140029a1e  call    cs:__imp_GetProcessHeap
0x140029a24  mov     r8, rsi; lpMem
0x140029a27  xor     edx, edx; dwFlags
0x140029a29  mov     rcx, rax; hHeap
0x140029a2c  call    cs:__imp_HeapFree
0x140029a32  mov     rcx, [rdi+248h]; hSCObject
0x140029a39  test    rcx, rcx
0x140029a3c  jz      short loc_140029A4B
0x140029a3e  call    cs:__imp_CloseServiceHandle
0x140029a44  mov     [rdi+248h], r12
0x140029a4b  test    r14d, r14d
0x140029a4e  jnz     short loc_140029A65
0x140029a50  mov     rbx, [rsp+88h+arg_0]
0x140029a58  add     rsp, 60h
0x140029a5c  pop     r15
0x140029a5e  pop     r14
0x140029a60  pop     r12
0x140029a62  pop     rdi
0x140029a63  pop     rsi
0x140029a64  retn
0x140029a65  mov     r8, rdi; unsigned __int16 *
0x140029a68  mov     edx, 101h; unsigned __int64
0x140029a6d  mov     rcx, r15; unsigned __int16 *
0x140029a70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140029a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a7c  cmp     rcx, rbx
0x140029a7f  jz      short loc_140029A50
0x140029a81  test    byte ptr [rcx+1Ch], 1
0x140029a85  jz      short loc_140029A50
0x140029a87  cmp     byte ptr [rcx+19h], 3
0x140029a8b  jb      short loc_140029A50
0x140029a8d  mov     edx, 4Dh ; 'M'
0x140029a92  mov     r9, rdi
0x140029a95  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140029a9c  mov     rcx, [rcx+10h]
0x140029aa0  call    WPP_SF_S
0x140029aa5  jmp     short loc_140029A50
0x14009df40  push    rbx
0x14009df42  push    rbp
0x14009df43  sub     rsp, 38h
0x14009df47  mov     rbp, rdx
0x14009df4a  cmp     qword ptr [rbp+0A8h], 0
0x14009df52  jz      short loc_14009DF61
0x14009df54  lea     rcx, [rbp+0A8h]
0x14009df5b  call    NotifyFree
0x14009df60  nop
0x14009df61  mov     rbx, [rbp+98h]
0x14009df68  cmp     qword ptr [rbx+248h], 0
0x14009df70  jz      short loc_14009DF8A
0x14009df72  mov     rcx, [rbx+248h]; hSCObject
0x14009df79  call    cs:__imp_CloseServiceHandle
0x14009df7f  mov     qword ptr [rbx+248h], 0
0x14009df8a  cmp     dword ptr [rbp+30h], 0
0x14009df8e  jz      short loc_14009DFD9
0x14009df90  lea     rcx, [rbx+22h]; unsigned __int16 *
0x14009df94  mov     r8, rbx; unsigned __int16 *
0x14009df97  mov     edx, 101h; unsigned __int64
0x14009df9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14009dfa1  lea     rax, WPP_GLOBAL_Control
0x14009dfa8  mov     rcx, cs:WPP_GLOBAL_Control
0x14009dfaf  cmp     rcx, rax
0x14009dfb2  jz      short loc_14009DFD9
0x14009dfb4  test    byte ptr [rcx+1Ch], 1
0x14009dfb8  jz      short loc_14009DFD9
0x14009dfba  cmp     byte ptr [rcx+19h], 3
0x14009dfbe  jb      short loc_14009DFD9
0x14009dfc0  mov     edx, 4Dh ; 'M'
0x14009dfc5  mov     r9, rbx
0x14009dfc8  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x14009dfcf  mov     rcx, [rcx+10h]
0x14009dfd3  call    WPP_SF_S
0x14009dfd8  nop
0x14009dfd9  add     rsp, 38h
0x14009dfdd  pop     rbp
  ... truncated ...
```
