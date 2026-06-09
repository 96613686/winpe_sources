# CPxeProviderHandler::Register(ushort const *,ushort const *,ulong,int,HKEY__ * *)

- ea: `0x180005e44`
- end: `0x18000635f`
- name: `?Register@CPxeProviderHandler@@QEAAKPEBG0KHPEAPEAUHKEY__@@@Z`
- size: `1307`
- prototype: `unsigned int __usercall@<eax>(CPxeProviderHandler *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008c90`

## callees

- `0x180001ad8`
- `0x180005440`
- `0x1800059ac`
- `0x180005e44`
- `0x1800065b4`
- `0x1800070c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800062b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062fe`
- `KERNEL32!GetLastError` at `0x180005ee2`
- `KERNEL32!GetLastError` at `0x180005ee2`
- `KERNEL32!EnterCriticalSection` at `0x180005efc`
- `KERNEL32!EnterCriticalSection` at `0x1800060e4`
- `KERNEL32!EnterCriticalSection` at `0x180006110`
- `KERNEL32!EnterCriticalSection` at `0x180006173`
- `KERNEL32!EnterCriticalSection` at `0x1800061ff`
- `KERNEL32!EnterCriticalSection` at `0x180005efc`
- `KERNEL32!EnterCriticalSection` at `0x1800060e4`
- `KERNEL32!EnterCriticalSection` at `0x180006110`
- `KERNEL32!EnterCriticalSection` at `0x180006173`
- `KERNEL32!EnterCriticalSection` at `0x1800061ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800060f6`
- `KERNEL32!LeaveCriticalSection` at `0x18000614e`
- `KERNEL32!LeaveCriticalSection` at `0x1800061b5`
- `KERNEL32!LeaveCriticalSection` at `0x180006212`
- `KERNEL32!LeaveCriticalSection` at `0x180006296`
- `KERNEL32!LeaveCriticalSection` at `0x1800060f6`
- `KERNEL32!LeaveCriticalSection` at `0x18000614e`
- `KERNEL32!LeaveCriticalSection` at `0x1800061b5`
- `KERNEL32!LeaveCriticalSection` at `0x180006212`
- `KERNEL32!LeaveCriticalSection` at `0x180006296`
- `KERNEL32!GetFileAttributesW` at `0x180005ed1`
- `KERNEL32!GetFileAttributesW` at `0x180005ed1`
- `ADVAPI32!RegCloseKey` at `0x180005f3c`
- `ADVAPI32!RegCloseKey` at `0x180005f98`
- `ADVAPI32!RegCloseKey` at `0x180006318`
- `ADVAPI32!RegCloseKey` at `0x180006332`
- `ADVAPI32!RegCloseKey` at `0x180005f3c`
- `ADVAPI32!RegCloseKey` at `0x180005f98`
- `ADVAPI32!RegCloseKey` at `0x180006318`
- `ADVAPI32!RegCloseKey` at `0x180006332`
- `ADVAPI32!RegOpenKeyExW` at `0x180005f68`
- `ADVAPI32!RegOpenKeyExW` at `0x180005f68`
- `ADVAPI32!RegCreateKeyExW` at `0x180005fcf`
- `ADVAPI32!RegCreateKeyExW` at `0x180005fcf`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180006097`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800060ba`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180006097`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800060ba`
- `WdsCommonLib!WdsExpandEnvironmentStrings` at `0x180005eb7`
- `WdsCommonLib!WdsExpandEnvironmentStrings` at `0x180005eb7`
- `WdsCommonLib!?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z` at `0x180006000`
- `WdsCommonLib!?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z` at `0x180006000`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x180006032`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x180006032`

## string_xrefs

- `0x180005f5a`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Providers`
- `0x180005ff5`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::Register(
        CPxeProviderHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        HKEY *a6)
{
  unsigned __int16 **v10; // rdi
  DWORD LastError; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  HKEY v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned __int16 **v25; // rax
  unsigned __int16 **v26; // rsi
  char *v27; // r14
  __int64 v28; // rbx
  bool v29; // zf
  __int64 v30; // rbx
  struct _RTL_CRITICAL_SECTION *v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rbx
  __int64 v36; // rax
  unsigned int v37; // edx
  __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // rcx
  HKEY v43; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  __int64 v46; // [rsp+A8h] [rbp+38h] BYREF

  lpFileName = 0;
  hKey = 0;
  v43 = 0;
  v10 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a2 || !*a2 || !a3 || !*a3 )
  {
    LastError = 87;
    goto LABEL_61;
  }
  LastError = WdsExpandEnvironmentStrings(a3, &lpFileName);
  if ( !LastError )
  {
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      LastError = GetLastError();
      goto LABEL_53;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
    if ( !CPxeProviderHandler::QueryIndex(this, a2, (unsigned int *)&v46) )
    {
      LastError = 183;
LABEL_52:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
      goto LABEL_53;
    }
    if ( a4 > *((_DWORD *)this + 32) )
      a4 = *((_DWORD *)this + 32);
    if ( hKey )
      RegCloseKey(hKey);
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Providers",
            0,
            0xF013Fu,
            &hKey);
    LastError = ElValidateWin32_2(v12, v13, v14, 1001);
    if ( LastError )
      goto LABEL_52;
    v15 = hKey;
    if ( v43 )
      RegCloseKey(v43);
    v16 = RegCreateKeyExW(v15, a2, 0, 0, 0, 0xF013Fu, 0, &v43, 0);
    LastError = ElValidateWin32_2(v16, v17, v18, 1010);
    if ( LastError )
      goto LABEL_52;
    v19 = CRegKey::SetValueExpSz((CRegKey *)&v43, L"ProviderDll", a3);
    LastError = ElValidateWin32_2(v19, v20, v21, 1018);
    if ( LastError )
      goto LABEL_52;
    v22 = CRegKey::SetValueDword((CRegKey *)&v43, L"IsCritical", a5);
    LastError = ElValidateWin32_2(v22, v23, v24, 1026);
    if ( LastError )
      goto LABEL_52;
    v25 = (unsigned __int16 **)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    if ( !v25 )
    {
      LastError = 8;
      goto LABEL_52;
    }
    v25[4] = 0;
    v25[5] = 0;
    *(_OWORD *)v25 = 0;
    *((_OWORD *)v25 + 1) = 0;
    *(_DWORD *)v25 = 48;
    *((_DWORD *)v25 + 7) = a4;
    *((_DWORD *)v25 + 6) = a5;
    v10 = v25;
    LastError = DuplicateStringW(a2, v25 + 1);
    if ( LastError )
      goto LABEL_52;
    LastError = DuplicateStringW(a3, v26 + 2);
    if ( LastError )
      goto LABEL_52;
    v27 = (char *)this + 72;
    if ( a4 )
    {
      v31 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
      if ( a4 == *((_DWORD *)this + 32) )
      {
        EnterCriticalSection(v31);
        if ( *(_QWORD *)v27 )
        {
          v26[4] = 0;
          v26[5] = (unsigned __int16 *)*((_QWORD *)this + 10);
          *(_QWORD *)(*((_QWORD *)this + 10) + 32LL) = v26;
          *((_QWORD *)this + 10) = v26;
        }
        else
        {
          *((_QWORD *)this + 10) = v26;
          *(_QWORD *)v27 = v26;
          v26[4] = 0;
          v26[5] = 0;
        }
        ++*((_DWORD *)this + 32);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
LABEL_37:
        v32 = CPxeProviderHandler::SaveProvidersOrder(this);
        LastError = ElValidateWin32_2(v32, v33, v34, 1106);
        if ( !LastError && a6 )
        {
          *a6 = v43;
          v43 = 0;
        }
        goto LABEL_52;
      }
      EnterCriticalSection(v31);
      v35 = *(_QWORD *)v27;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v36 = 0;
      if ( v35 )
        v36 = *(_QWORD *)v27;
      v46 = v36;
      if ( !v36 )
        goto LABEL_37;
      v37 = *((_DWORD *)v26 + 7);
      v38 = v36;
      while ( 1 )
      {
        v10 = v26;
        if ( *(_DWORD *)(v38 + 28) >= v37 )
          break;
        v36 = *(_QWORD *)(v36 + 32);
        v46 = v36;
        v38 = v36;
        if ( !v36 )
          goto LABEL_37;
      }
      CList<CPxeProviderHandler::PROV_INFO,CCriticalSection>::InsertBefore((char *)this + 72, &v46, v26);
      v30 = v46;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v28 = *(_QWORD *)v27;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v29 = v28 == 0;
      v30 = 0;
      if ( !v29 )
        v30 = *(_QWORD *)v27;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      if ( *(_QWORD *)v27 )
      {
        v26[4] = *(unsigned __int16 **)v27;
        v26[5] = 0;
        *(_QWORD *)(*(_QWORD *)v27 + 40LL) = v26;
        *(_QWORD *)v27 = v26;
      }
      else
      {
        *((_QWORD *)this + 10) = v26;
        *(_QWORD *)v27 = v26;
        v26[4] = 0;
        v26[5] = 0;
      }
      ++*((_DWORD *)this + 32);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v10 = v26;
    }
    if ( v30 )
    {
      do
      {
        v39 = *(_QWORD *)(v30 + 32);
        ++*(_DWORD *)(v30 + 28);
        v30 = v39;
      }
      while ( v39 );
    }
    goto LABEL_37;
  }
LABEL_53:
  if ( LastError && v10 )
  {
    v40 = v10[1];
    if ( v40 )
    {
      operator delete(v40);
      v10[1] = 0;
    }
    v41 = v10[2];
    if ( v41 )
    {
      operator delete(v41);
      v10[2] = 0;
    }
    operator delete(v10);
  }
LABEL_61:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v43 )
  {
    RegCloseKey(v43);
    v43 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x180005e44  mov     [rsp-28h+arg_0], rbx
0x180005e49  mov     [rsp-28h+arg_10], rsi
0x180005e4e  mov     [rsp-28h+arg_18], rdi
0x180005e53  push    rbp
0x180005e54  push    r12
0x180005e56  push    r13
0x180005e58  push    r14
0x180005e5a  push    r15
0x180005e5c  mov     rbp, rsp
0x180005e5f  sub     rsp, 70h
0x180005e63  mov     rax, [rbp+arg_28]
0x180005e67  xor     esi, esi
0x180005e69  mov     [rbp+lpFileName], rsi
0x180005e6d  mov     r15d, r9d
0x180005e70  mov     [rbp+hKey], rsi
0x180005e74  mov     r14, r8
0x180005e77  mov     [rbp+var_20], rsi
0x180005e7b  mov     r12, rdx
0x180005e7e  mov     r13, rcx
0x180005e81  mov     edi, esi
0x180005e83  test    rax, rax
0x180005e86  jz      short loc_180005E8B
0x180005e88  mov     [rax], rsi
0x180005e8b  test    r12, r12
0x180005e8e  jz      loc_1800062F0
0x180005e94  cmp     [rdx], si
0x180005e97  jz      loc_1800062F0
0x180005e9d  test    r14, r14
0x180005ea0  jz      loc_1800062F0
0x180005ea6  cmp     [r8], si
0x180005eaa  jz      loc_1800062F0
0x180005eb0  lea     rdx, [rbp+lpFileName]
0x180005eb4  mov     rcx, r14
0x180005eb7  call    cs:__imp_WdsExpandEnvironmentStrings
0x180005ebe  nop     dword ptr [rax+rax+00h]
0x180005ec3  mov     ebx, eax
0x180005ec5  test    eax, eax
0x180005ec7  jnz     loc_1800062A2
0x180005ecd  mov     rcx, [rbp+lpFileName]; lpFileName
0x180005ed1  call    cs:__imp_GetFileAttributesW
0x180005ed8  nop     dword ptr [rax+rax+00h]
0x180005edd  cmp     eax, 0FFFFFFFFh
0x180005ee0  jnz     short loc_180005EF5
0x180005ee2  call    cs:__imp_GetLastError
0x180005ee9  nop     dword ptr [rax+rax+00h]
0x180005eee  mov     ebx, eax
0x180005ef0  jmp     loc_1800062A2
0x180005ef5  lea     rcx, [r13+150h]; lpCriticalSection
0x180005efc  call    cs:__imp_EnterCriticalSection
0x180005f03  nop     dword ptr [rax+rax+00h]
0x180005f08  lea     r8, [rbp+arg_8]; unsigned int *
0x180005f0c  mov     rdx, r12; unsigned __int16 *
0x180005f0f  mov     rcx, r13; this
0x180005f12  call    ?QueryIndex@CPxeProviderHandler@@QEAAKPEBGPEAK@Z; CPxeProviderHandler::QueryIndex(ushort const *,ulong *)
0x180005f17  test    eax, eax
0x180005f19  jnz     short loc_180005F25
0x180005f1b  mov     ebx, 0B7h
0x180005f20  jmp     loc_18000628F
0x180005f25  mov     eax, [r13+80h]
0x180005f2c  cmp     r15d, eax
0x180005f2f  mov     rcx, [rbp+hKey]; hKey
0x180005f33  cmova   r15d, eax
0x180005f37  test    rcx, rcx
0x180005f3a  jz      short loc_180005F48
0x180005f3c  call    cs:__imp_RegCloseKey
0x180005f43  nop     dword ptr [rax+rax+00h]
0x180005f48  lea     rax, [rbp+hKey]
0x180005f4c  mov     r9d, 0F013Fh; samDesired
0x180005f52  xor     r8d, r8d; ulOptions
0x180005f55  mov     [rsp+70h+phkResult], rax; phkResult
0x180005f5a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x180005f61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005f68  call    cs:__imp_RegOpenKeyExW
0x180005f6f  nop     dword ptr [rax+rax+00h]
0x180005f74  mov     ecx, eax
0x180005f76  mov     r9d, 3E9h
0x180005f7c  call    ElValidateWin32_2
0x180005f81  mov     ebx, eax
0x180005f83  test    eax, eax
0x180005f85  jnz     loc_18000628F
0x180005f8b  mov     rcx, [rbp+var_20]; hKey
0x180005f8f  mov     rbx, [rbp+hKey]
0x180005f93  test    rcx, rcx
0x180005f96  jz      short loc_180005FA4
0x180005f98  call    cs:__imp_RegCloseKey
0x180005f9f  nop     dword ptr [rax+rax+00h]
0x180005fa4  mov     [rsp+70h+lpdwDisposition], rsi; lpdwDisposition
0x180005fa9  lea     rax, [rbp+var_20]
0x180005fad  mov     [rsp+70h+var_38], rax; phkResult
0x180005fb2  xor     r9d, r9d; lpClass
0x180005fb5  mov     [rsp+70h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180005fba  xor     r8d, r8d; Reserved
0x180005fbd  mov     [rsp+70h+samDesired], 0F013Fh; samDesired
0x180005fc5  mov     rdx, r12; lpSubKey
0x180005fc8  mov     rcx, rbx; hKey
0x180005fcb  mov     dword ptr [rsp+70h+phkResult], esi; dwOptions
0x180005fcf  call    cs:__imp_RegCreateKeyExW
0x180005fd6  nop     dword ptr [rax+rax+00h]
0x180005fdb  mov     ecx, eax
0x180005fdd  mov     r9d, 3F2h
0x180005fe3  call    ElValidateWin32_2
0x180005fe8  mov     ebx, eax
0x180005fea  test    eax, eax
0x180005fec  jnz     loc_18000628F
0x180005ff2  mov     r8, r14
0x180005ff5  lea     rdx, aProviderdll; "ProviderDll"
0x180005ffc  lea     rcx, [rbp+var_20]
0x180006000  call    cs:__imp_?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueExpSz(ushort const *,ushort const *)
0x180006007  nop     dword ptr [rax+rax+00h]
0x18000600c  mov     ecx, eax
0x18000600e  mov     r9d, 3FAh
0x180006014  call    ElValidateWin32_2
0x180006019  mov     ebx, eax
0x18000601b  test    eax, eax
0x18000601d  jnz     loc_18000628F
0x180006023  mov     r8d, [rbp+arg_20]
0x180006027  lea     rdx, aIscritical; "IsCritical"
0x18000602e  lea     rcx, [rbp+var_20]
0x180006032  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x180006039  nop     dword ptr [rax+rax+00h]
0x18000603e  mov     ecx, eax
0x180006040  mov     r9d, 402h
0x180006046  call    ElValidateWin32_2
0x18000604b  mov     ebx, eax
0x18000604d  test    eax, eax
0x18000604f  jnz     loc_18000628F
0x180006055  lea     ebx, [rax+30h]
0x180006058  mov     ecx, ebx; unsigned __int64
0x18000605a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006061  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006066  mov     rsi, rax
0x180006069  test    rax, rax
0x18000606c  jz      loc_18000628A
0x180006072  and     [rax+20h], rdi
0x180006076  lea     rdx, [rsi+8]
0x18000607a  and     [rax+28h], rdi
0x18000607e  xorps   xmm0, xmm0
0x180006081  movups  xmmword ptr [rax], xmm0
0x180006084  mov     rcx, r12
0x180006087  movups  xmmword ptr [rax+10h], xmm0
0x18000608b  mov     [rax], ebx
0x18000608d  mov     [rax+1Ch], r15d
0x180006091  mov     eax, [rbp+arg_20]
0x180006094  mov     [rsi+18h], eax
0x180006097  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000609e  nop     dword ptr [rax+rax+00h]
0x1800060a3  xor     r12d, r12d
0x1800060a6  mov     rdi, rsi
0x1800060a9  mov     ebx, eax
0x1800060ab  test    eax, eax
0x1800060ad  jnz     loc_18000628F
0x1800060b3  lea     rdx, [rsi+10h]
0x1800060b7  mov     rcx, r14
0x1800060ba  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800060c1  nop     dword ptr [rax+rax+00h]
0x1800060c6  mov     ebx, eax
0x1800060c8  test    eax, eax
0x1800060ca  jnz     loc_18000628F
0x1800060d0  lea     r14, [r13+48h]
0x1800060d4  test    r15d, r15d
0x1800060d7  jnz     loc_180006162
0x1800060dd  lea     rdi, [r14+10h]
0x1800060e1  mov     rcx, rdi; lpCriticalSection
0x1800060e4  call    cs:__imp_EnterCriticalSection
0x1800060eb  nop     dword ptr [rax+rax+00h]
0x1800060f0  mov     rbx, [r14]
0x1800060f3  mov     rcx, rdi; lpCriticalSection
0x1800060f6  call    cs:__imp_LeaveCriticalSection
0x1800060fd  nop     dword ptr [rax+rax+00h]
0x180006102  test    rbx, rbx
0x180006105  mov     ebx, r12d
0x180006108  jz      short loc_18000610D
0x18000610a  mov     rbx, [r14]
0x18000610d  mov     rcx, rdi; lpCriticalSection
0x180006110  call    cs:__imp_EnterCriticalSection
0x180006117  nop     dword ptr [rax+rax+00h]
0x18000611c  mov     rax, [r14]
0x18000611f  test    rax, rax
0x180006122  jnz     short loc_180006135
0x180006124  mov     [r14+8], rsi
0x180006128  mov     [r14], rsi
0x18000612b  mov     [rsi+20h], r12
0x18000612f  mov     [rsi+28h], r12
0x180006133  jmp     short loc_180006147
0x180006135  mov     [rsi+20h], rax
0x180006139  mov     [rsi+28h], r12
0x18000613d  mov     rax, [r14]
0x180006140  mov     [rax+28h], rsi
0x180006144  mov     [r14], rsi
0x180006147  inc     dword ptr [r14+38h]
0x18000614b  mov     rcx, rdi; lpCriticalSection
0x18000614e  call    cs:__imp_LeaveCriticalSection
0x180006155  nop     dword ptr [rax+rax+00h]
0x18000615a  mov     rdi, rsi
0x18000615d  jmp     loc_180006268
0x180006162  lea     rcx, [r14+10h]; lpCriticalSection
0x180006166  cmp     r15d, [r13+80h]
0x18000616d  jnz     loc_1800061FF
0x180006173  call    cs:__imp_EnterCriticalSection
0x18000617a  nop     dword ptr [rax+rax+00h]
0x18000617f  cmp     [r14], r12
0x180006182  jnz     short loc_180006195
0x180006184  mov     [r14+8], rsi
0x180006188  mov     [r14], rsi
0x18000618b  mov     [rsi+20h], r12
0x18000618f  mov     [rsi+28h], r12
0x180006193  jmp     short loc_1800061AD
0x180006195  mov     [rsi+20h], r12
0x180006199  mov     rax, [r14+8]
0x18000619d  mov     [rsi+28h], rax
0x1800061a1  mov     rax, [r14+8]
0x1800061a5  mov     [rax+20h], rsi
0x1800061a9  mov     [r14+8], rsi
0x1800061ad  inc     dword ptr [r14+38h]
0x1800061b1  lea     rcx, [r14+10h]; lpCriticalSection
0x1800061b5  call    cs:__imp_LeaveCriticalSection
0x1800061bc  nop     dword ptr [rax+rax+00h]
0x1800061c1  xor     esi, esi
0x1800061c3  mov     rcx, r13; this
0x1800061c6  call    ?SaveProvidersOrder@CPxeProviderHandler@@AEAAKXZ; CPxeProviderHandler::SaveProvidersOrder(void)
0x1800061cb  mov     ecx, eax
0x1800061cd  mov     r9d, 452h
0x1800061d3  call    ElValidateWin32_2
0x1800061d8  mov     ebx, eax
0x1800061da  test    eax, eax
0x1800061dc  jnz     loc_18000628F
0x1800061e2  mov     rcx, [rbp+arg_28]
0x1800061e6  test    rcx, rcx
0x1800061e9  jz      loc_18000628F
0x1800061ef  mov     rax, [rbp+var_20]
0x1800061f3  mov     [rcx], rax
0x1800061f6  mov     [rbp+var_20], rsi
0x1800061fa  jmp     loc_18000628F
0x1800061ff  call    cs:__imp_EnterCriticalSection
0x180006206  nop     dword ptr [rax+rax+00h]
0x18000620b  mov     rbx, [r14]
0x18000620e  lea     rcx, [r14+10h]; lpCriticalSection
0x180006212  call    cs:__imp_LeaveCriticalSection
0x180006219  nop     dword ptr [rax+rax+00h]
0x18000621e  mov     rax, r12
0x180006221  test    rbx, rbx
0x180006224  jz      short loc_180006229
0x180006226  mov     rax, [r14]
0x180006229  mov     [rbp+arg_8], rax
0x18000622d  test    rax, rax
0x180006230  jz      short loc_1800061C1
0x180006232  mov     edx, [rsi+1Ch]
0x180006235  mov     rcx, rax
0x180006238  mov     rdi, rsi
0x18000623b  cmp     [rcx+1Ch], edx
0x18000623e  jnb     short loc_180006255
0x180006240  mov     rax, [rax+20h]
0x180006244  mov     [rbp+arg_8], rax
0x180006248  mov     rcx, rax
0x18000624b  test    rax, rax
0x18000624e  jnz     short loc_180006238
0x180006250  jmp     loc_1800061C1
0x180006255  mov     r8, rsi
0x180006258  lea     rdx, [rbp+arg_8]
0x18000625c  mov     rcx, r14
0x18000625f  call    ?InsertBefore@?$CList@UPROV_INFO@CPxeProviderHandler@@VCCriticalSection@@@@QEAAXAEAPEAXPEAUPROV_INFO@CPxeProviderHandler@@@Z; CList<CPxeProviderHandler::PROV_INFO,CCriticalSection>::InsertBefore(void * &,CPxeProviderHandler::PROV_INFO *)
0x180006264  mov     rbx, [rbp+arg_8]
0x180006268  xor     esi, esi
0x18000626a  test    rbx, rbx
0x18000626d  jz      loc_1800061C3
0x180006273  mov     rcx, [rbx+20h]
0x180006277  lea     rax, [rbx]
0x18000627a  inc     dword ptr [rax+1Ch]
0x18000627d  mov     rbx, rcx
0x180006280  test    rcx, rcx
0x180006283  jnz     short loc_180006273
0x180006285  jmp     loc_1800061C3
0x18000628a  mov     ebx, 8
0x18000628f  lea     rcx, [r13+150h]; lpCriticalSection
0x180006296  call    cs:__imp_LeaveCriticalSection
0x18000629d  nop     dword ptr [rax+rax+00h]
0x1800062a2  test    ebx, ebx
0x1800062a4  jz      short loc_1800062F5
0x1800062a6  test    rdi, rdi
0x1800062a9  jz      short loc_1800062F5
0x1800062ab  mov     rcx, [rdi+8]
0x1800062af  test    rcx, rcx
0x1800062b2  jz      short loc_1800062C5
0x1800062b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062bb  nop     dword ptr [rax+rax+00h]
0x1800062c0  and     qword ptr [rdi+8], 0
0x1800062c5  mov     rcx, [rdi+10h]
0x1800062c9  test    rcx, rcx
0x1800062cc  jz      short loc_1800062DF
0x1800062ce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062d5  nop     dword ptr [rax+rax+00h]
0x1800062da  and     qword ptr [rdi+10h], 0
0x1800062df  mov     rcx, rdi
0x1800062e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062e9  nop     dword ptr [rax+rax+00h]
0x1800062ee  jmp     short loc_1800062F5
0x1800062f0  mov     ebx, 57h ; 'W'
0x1800062f5  mov     rcx, [rbp+lpFileName]
0x1800062f9  test    rcx, rcx
0x1800062fc  jz      short loc_18000630F
  ... truncated ...
```
