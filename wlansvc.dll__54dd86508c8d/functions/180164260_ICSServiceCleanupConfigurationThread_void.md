# ICSServiceCleanupConfigurationThread(void *)

- ea: `0x180164260`
- end: `0x18016467a`
- name: `?ICSServiceCleanupConfigurationThread@@YAKPEAX@Z`
- size: `1050`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180029ed4`
- `0x180036110`
- `0x18003fda0`
- `0x1800a5a98`
- `0x180106340`
- `0x180107330`
- `0x18011a058`
- `0x180164260`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801643ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801643ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180164372`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180164372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801645f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801645f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180164307`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180164307`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180164518`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180164518`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180164609`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180164609`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801644b0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801644b0`

## string_xrefs

- `0x180164361`: `System\CurrentControlSet\Services\WlanSvc\Parameters\ComInterfaceProviders`
- `0x1801643a7`: `System\CurrentControlSet\Services\WlanSvc\Parameters\ComInterfaceProviders`

## pseudocode

```c
__int64 __fastcall ICSServiceCleanupConfigurationThread(PVOID Parameter)
{
  HRESULT v1; // eax
  int v2; // edi
  unsigned int v3; // ebx
  int v4; // esi
  PVOID *v5; // rcx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  int v8; // edx
  const WCHAR *v9; // r9
  HRESULT v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-69h] BYREF
  DWORD Type; // [rsp+34h] [rbp-65h] BYREF
  int v14; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v15; // [rsp+3Ch] [rbp-5Dh] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-51h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-49h] BYREF
  OLECHAR Data[40]; // [rsp+60h] [rbp-39h] BYREF

  hKey = 0;
  ppv = 0;
  v15 = 0;
  v14 = 0;
  cbData = 0;
  Type = 0;
  pclsid = 0;
  memset_0(Data, 0, 0x4Eu);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, &WPP_748d1d10ca5b345524c60852363a0006_Traceguids);
  }
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 0;
    v4 = 0;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v6 = 16;
LABEL_10:
      WPP_SF_d(v5[12], v6, &WPP_748d1d10ca5b345524c60852363a0006_Traceguids, (unsigned int)v1);
LABEL_51:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  v4 = 1;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WlanSvc\\Parameters\\ComInterfaceProviders",
         0,
         1u,
         &hKey);
  v3 = v7;
  if ( v7 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
    {
      goto LABEL_52;
    }
    v8 = 17;
    v9 = L"System\\CurrentControlSet\\Services\\WlanSvc\\Parameters\\ComInterfaceProviders";
    goto LABEL_16;
  }
  cbData = 78;
  v7 = RegQueryValueExW(hKey, L"IHNetIcsSettings", 0, &Type, (LPBYTE)Data, &cbData);
  v3 = v7;
  if ( v7 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
    {
      goto LABEL_52;
    }
    v8 = 18;
    v9 = L"IHNetIcsSettings";
LABEL_16:
    WPP_SF_SD((unsigned int)v5[12], v8, (unsigned int)&WPP_748d1d10ca5b345524c60852363a0006_Traceguids, (_DWORD)v9, v7);
    goto LABEL_51;
  }
  if ( Type == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, &WPP_748d1d10ca5b345524c60852363a0006_Traceguids, Data);
    }
    v10 = CLSIDFromString(Data, &pclsid);
    v2 = v10;
    if ( v10 >= 0 )
    {
      v1 = CoCreateInstance(&pclsid, 0, 0x17u, &IID_IHNetIcsSettings, &ppv);
      v2 = v1;
      if ( v1 >= 0 )
      {
        v1 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, int *))(*(_QWORD *)ppv + 40LL))(ppv, &v15, &v14);
        v2 = v1;
        if ( v1 >= 0 )
        {
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, &WPP_748d1d10ca5b345524c60852363a0006_Traceguids, v15);
            goto LABEL_51;
          }
        }
        else
        {
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v6 = 23;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          v6 = 22;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          21,
          (unsigned int)&WPP_748d1d10ca5b345524c60852363a0006_Traceguids,
          (unsigned int)Data,
          v10);
        goto LABEL_51;
      }
    }
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        19,
        (unsigned int)&WPP_748d1d10ca5b345524c60852363a0006_Traceguids,
        Type,
        (__int64)L"IHNetIcsSettings");
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 13;
  }
LABEL_52:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CoUninitialize();
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 < 0 )
  {
    v3 = 774;
    if ( (v2 & 0x1FFF0000) == 0x70000 )
    {
      if ( (_WORD)v2 )
        v3 = (unsigned __int16)v2;
    }
  }
  if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) >= 4u && (*((_BYTE *)v5 + 108) & 1) != 0 )
    WPP_SF_d(v5[12], 25, &WPP_748d1d10ca5b345524c60852363a0006_Traceguids, v3);
  return 0;
}

```

## disassembly

```asm
0x180164260  push    rbp
0x180164262  push    rbx
0x180164263  push    rsi
0x180164264  push    rdi
0x180164265  push    r12
0x180164267  push    r13
0x180164269  push    r14
0x18016426b  lea     rbp, [rsp-27h]
0x180164270  sub     rsp, 0C0h
0x180164277  mov     rax, cs:__security_cookie
0x18016427e  xor     rax, rsp
0x180164281  mov     [rbp+57h+var_40], rax
0x180164285  xor     edx, edx; Val
0x180164287  mov     [rbp+57h+hKey], 0
0x18016428f  xorps   xmm0, xmm0
0x180164292  mov     [rbp+57h+ppv], 0
0x18016429a  lea     rcx, [rbp+57h+Data]; void *
0x18016429e  mov     [rbp+57h+var_B4], 0
0x1801642a5  mov     [rbp+57h+var_B8], 0
0x1801642ac  lea     r8d, [rdx+4Eh]; Size
0x1801642b0  mov     [rbp+57h+cbData], 0
0x1801642b7  mov     [rbp+57h+Type], 0
0x1801642be  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1801642c2  call    memset_0
0x1801642c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801642ce  lea     r12, WPP_GLOBAL_Control
0x1801642d5  lea     r13, WPP_748d1d10ca5b345524c60852363a0006_Traceguids
0x1801642dc  mov     r14d, 1
0x1801642e2  cmp     rcx, r12
0x1801642e5  jz      short loc_180164303
0x1801642e7  cmp     byte ptr [rcx+69h], 4
0x1801642eb  jb      short loc_180164303
0x1801642ed  test    [rcx+6Ch], r14b
0x1801642f1  jz      short loc_180164303
0x1801642f3  mov     rcx, [rcx+60h]
0x1801642f7  lea     edx, [r14+0Eh]
0x1801642fb  mov     r8, r13
0x1801642fe  call    WPP_SF_
0x180164303  xor     edx, edx; dwCoInit
0x180164305  xor     ecx, ecx; pvReserved
0x180164307  call    cs:__imp_CoInitializeEx
0x18016430d  mov     edi, eax
0x18016430f  test    eax, eax
0x180164311  jns     short loc_180164352
0x180164313  xor     ebx, ebx
0x180164315  xor     esi, esi
0x180164317  mov     rcx, cs:WPP_GLOBAL_Control
0x18016431e  cmp     rcx, r12
0x180164321  jz      loc_1801645CD
0x180164327  cmp     [rcx+69h], r14b
0x18016432b  jb      loc_1801645CD
0x180164331  test    [rcx+6Ch], r14b
0x180164335  jz      loc_1801645CD
0x18016433b  lea     edx, [rbx+10h]
0x18016433e  mov     rcx, [rcx+60h]
0x180164342  mov     r9d, eax
0x180164345  mov     r8, r13
0x180164348  call    WPP_SF_d
0x18016434d  jmp     loc_1801645C6
0x180164352  lea     rax, [rbp+57h+hKey]
0x180164356  mov     r9d, r14d; samDesired
0x180164359  xor     r8d, r8d; ulOptions
0x18016435c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180164361  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Wl"...
0x180164368  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18016436f  mov     esi, r14d
0x180164372  call    cs:__imp_RegOpenKeyExW
0x180164378  mov     ebx, eax
0x18016437a  test    eax, eax
0x18016437c  jz      short loc_1801643C3
0x18016437e  mov     rcx, cs:WPP_GLOBAL_Control
0x180164385  cmp     rcx, r12
0x180164388  jz      loc_1801645CD
0x18016438e  cmp     [rcx+69h], r14b
0x180164392  jb      loc_1801645CD
0x180164398  test    [rcx+6Ch], r14b
0x18016439c  jz      loc_1801645CD
0x1801643a2  mov     edx, 11h
0x1801643a7  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Wl"...
0x1801643ae  mov     rcx, [rcx+60h]
0x1801643b2  mov     r8, r13
0x1801643b5  mov     dword ptr [rsp+0F0h+phkResult], eax
0x1801643b9  call    WPP_SF_SD
0x1801643be  jmp     loc_1801645C6
0x1801643c3  mov     rcx, [rbp+57h+hKey]; hKey
0x1801643c7  lea     rax, [rbp+57h+cbData]
0x1801643cb  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x1801643d0  lea     r9, [rbp+57h+Type]; lpType
0x1801643d4  lea     rax, [rbp+57h+Data]
0x1801643d8  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x1801643df  xor     r8d, r8d; lpReserved
0x1801643e2  mov     [rsp+0F0h+phkResult], rax; lpData
0x1801643e7  lea     rdx, aIhneticssettin; "IHNetIcsSettings"
0x1801643ee  call    cs:__imp_RegQueryValueExW
0x1801643f4  mov     ebx, eax
0x1801643f6  test    eax, eax
0x1801643f8  jz      short loc_18016442C
0x1801643fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180164401  cmp     rcx, r12
0x180164404  jz      loc_1801645CD
0x18016440a  cmp     [rcx+69h], r14b
0x18016440e  jb      loc_1801645CD
0x180164414  test    [rcx+6Ch], r14b
0x180164418  jz      loc_1801645CD
0x18016441e  mov     edx, 12h
0x180164423  lea     r9, aIhneticssettin; "IHNetIcsSettings"
0x18016442a  jmp     short loc_1801643AE
0x18016442c  mov     r9d, [rbp+57h+Type]
0x180164430  cmp     r9d, r14d
0x180164433  jz      short loc_18016447B
0x180164435  mov     rcx, cs:WPP_GLOBAL_Control
0x18016443c  cmp     rcx, r12
0x18016443f  jz      short loc_180164471
0x180164441  cmp     [rcx+69h], r14b
0x180164445  jb      short loc_180164471
0x180164447  test    [rcx+6Ch], r14b
0x18016444b  jz      short loc_180164471
0x18016444d  mov     rcx, [rcx+60h]
0x180164451  lea     rax, aIhneticssettin; "IHNetIcsSettings"
0x180164458  mov     edx, 13h
0x18016445d  mov     [rsp+0F0h+phkResult], rax
0x180164462  mov     r8, r13
0x180164465  call    WPP_SF_DS
0x18016446a  mov     rcx, cs:WPP_GLOBAL_Control
0x180164471  mov     ebx, 0Dh
0x180164476  jmp     loc_1801645CD
0x18016447b  mov     rcx, cs:WPP_GLOBAL_Control
0x180164482  cmp     rcx, r12
0x180164485  jz      short loc_1801644A8
0x180164487  cmp     byte ptr [rcx+69h], 3
0x18016448b  jb      short loc_1801644A8
0x18016448d  test    [rcx+6Ch], r14b
0x180164491  jz      short loc_1801644A8
0x180164493  mov     rcx, [rcx+60h]
0x180164497  lea     r9, [rbp+57h+Data]
0x18016449b  mov     edx, 14h
0x1801644a0  mov     r8, r13
0x1801644a3  call    WPP_SF_S
0x1801644a8  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1801644ac  lea     rcx, [rbp+57h+Data]; lpsz
0x1801644b0  call    cs:__imp_CLSIDFromString
0x1801644b6  mov     edi, eax
0x1801644b8  test    eax, eax
0x1801644ba  jns     short loc_1801644FE
0x1801644bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801644c3  cmp     rcx, r12
0x1801644c6  jz      loc_1801645CD
0x1801644cc  cmp     [rcx+69h], r14b
0x1801644d0  jb      loc_1801645CD
0x1801644d6  test    [rcx+6Ch], r14b
0x1801644da  jz      loc_1801645CD
0x1801644e0  mov     rcx, [rcx+60h]
0x1801644e4  lea     r9, [rbp+57h+Data]
0x1801644e8  mov     edx, 15h
0x1801644ed  mov     dword ptr [rsp+0F0h+phkResult], eax
0x1801644f1  mov     r8, r13
0x1801644f4  call    WPP_SF_Sd
0x1801644f9  jmp     loc_1801645C6
0x1801644fe  xor     edx, edx; pUnkOuter
0x180164500  lea     rax, [rbp+57h+ppv]
0x180164504  lea     r9, IID_IHNetIcsSettings; riid
0x18016450b  mov     [rsp+0F0h+phkResult], rax; ppv
0x180164510  lea     rcx, [rbp+57h+pclsid]; rclsid
0x180164514  lea     r8d, [rdx+17h]; dwClsContext
0x180164518  call    cs:__imp_CoCreateInstance
0x18016451e  mov     edi, eax
0x180164520  test    eax, eax
0x180164522  jns     short loc_180164552
0x180164524  mov     rcx, cs:WPP_GLOBAL_Control
0x18016452b  cmp     rcx, r12
0x18016452e  jz      loc_1801645CD
0x180164534  cmp     [rcx+69h], r14b
0x180164538  jb      loc_1801645CD
0x18016453e  test    [rcx+6Ch], r14b
0x180164542  jz      loc_1801645CD
0x180164548  mov     edx, 16h
0x18016454d  jmp     loc_18016433E
0x180164552  mov     rcx, [rbp+57h+ppv]
0x180164556  lea     r8, [rbp+57h+var_B8]
0x18016455a  lea     rdx, [rbp+57h+var_B4]
0x18016455e  mov     rax, [rcx]
0x180164561  mov     rax, [rax+28h]
0x180164565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016456a  mov     edi, eax
0x18016456c  test    eax, eax
0x18016456e  jns     short loc_180164592
0x180164570  mov     rcx, cs:WPP_GLOBAL_Control
0x180164577  cmp     rcx, r12
0x18016457a  jz      short loc_1801645CD
0x18016457c  cmp     [rcx+69h], r14b
0x180164580  jb      short loc_1801645CD
0x180164582  test    [rcx+6Ch], r14b
0x180164586  jz      short loc_1801645CD
0x180164588  mov     edx, 17h
0x18016458d  jmp     loc_18016433E
0x180164592  mov     rcx, cs:WPP_GLOBAL_Control
0x180164599  cmp     rcx, r12
0x18016459c  jz      short loc_1801645CD
0x18016459e  cmp     byte ptr [rcx+69h], 3
0x1801645a2  jb      short loc_1801645CD
0x1801645a4  test    [rcx+6Ch], r14b
0x1801645a8  jz      short loc_1801645CD
0x1801645aa  mov     eax, [rbp+57h+var_B8]
0x1801645ad  mov     edx, 18h
0x1801645b2  mov     r9d, [rbp+57h+var_B4]
0x1801645b6  mov     r8, r13
0x1801645b9  mov     rcx, [rcx+60h]
0x1801645bd  mov     dword ptr [rsp+0F0h+phkResult], eax
0x1801645c1  call    WPP_SF_DD
0x1801645c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801645cd  mov     rdx, [rbp+57h+ppv]
0x1801645d1  test    rdx, rdx
0x1801645d4  jz      short loc_1801645EC
0x1801645d6  mov     rax, [rdx]
0x1801645d9  mov     rcx, rdx
0x1801645dc  mov     rax, [rax+10h]
0x1801645e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801645e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801645ec  mov     rax, [rbp+57h+hKey]
0x1801645f0  test    rax, rax
0x1801645f3  jz      short loc_180164605
0x1801645f5  mov     rcx, rax; hKey
0x1801645f8  call    cs:__imp_RegCloseKey
0x1801645fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180164605  test    esi, esi
0x180164607  jz      short loc_180164616
0x180164609  call    cs:__imp_CoUninitialize
0x18016460f  mov     rcx, cs:WPP_GLOBAL_Control
0x180164616  test    edi, edi
0x180164618  jns     short loc_180164635
0x18016461a  mov     eax, edi
0x18016461c  mov     ebx, 306h
0x180164621  and     eax, 1FFF0000h
0x180164626  cmp     eax, 70000h
0x18016462b  jnz     short loc_180164635
0x18016462d  movzx   eax, di
0x180164630  test    eax, eax
0x180164632  cmovnz  ebx, eax
0x180164635  cmp     rcx, r12
0x180164638  jz      short loc_18016465A
0x18016463a  cmp     byte ptr [rcx+69h], 4
0x18016463e  jb      short loc_18016465A
0x180164640  test    [rcx+6Ch], r14b
0x180164644  jz      short loc_18016465A
0x180164646  mov     rcx, [rcx+60h]
0x18016464a  mov     edx, 19h
0x18016464f  mov     r9d, ebx
0x180164652  mov     r8, r13
0x180164655  call    WPP_SF_d
0x18016465a  xor     eax, eax
0x18016465c  mov     rcx, [rbp+57h+var_40]
0x180164660  xor     rcx, rsp; StackCookie
0x180164663  call    __security_check_cookie
0x180164668  add     rsp, 0C0h
0x18016466f  pop     r14
0x180164671  pop     r13
0x180164673  pop     r12
0x180164675  pop     rdi
0x180164676  pop     rsi
0x180164677  pop     rbx
0x180164678  pop     rbp
0x180164679  retn
```
