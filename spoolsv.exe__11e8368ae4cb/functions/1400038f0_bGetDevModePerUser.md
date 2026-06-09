# bGetDevModePerUser

- ea: `0x1400038f0`
- end: `0x140003c5c`
- name: `bGetDevModePerUser`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004220`

## callees

- `0x140002070`
- `0x140002b00`
- `0x1400038f0`
- `0x140003c70`
- `0x14000cd50`
- `0x14000d640`
- `0x1400140cc`
- `0x140014fc4`
- `0x140015000`
- `0x1400235dc`
- `0x140023860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003bb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003bb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003aeb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003b1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000391f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003afe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003be7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000391f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003afe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003be7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140003c29`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140003c29`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140003c38`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140003c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140003b99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140003b99`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003ac0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003ac0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003a4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003a4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003bc9`

## string_xrefs

- `0x140003b0e`: `DllAllocSplMem`

## pseudocode

```c
__int64 __fastcall bGetDevModePerUser(HKEY a1, unsigned __int16 *a2, LPVOID *a3)
{
  const unsigned __int16 *v7; // rdx
  ProcessUtils *v8; // rcx
  int *v9; // r8
  int v10; // eax
  const WCHAR *v11; // r12
  HKEY ClientUserHandle; // rdi
  unsigned int LastError; // r15d
  DWORD InfoKeyW; // ebx
  unsigned int v15; // edi
  BYTE *v16; // rbx
  HKEY v17; // rcx
  unsigned __int16 *v18; // rcx
  unsigned int IsValidDevmodeNo; // r9d
  unsigned __int64 v20; // rdx
  HANDLE v21; // rbx
  HANDLE Token; // [rsp+60h] [rbp-20h] BYREF
  char v23; // [rsp+68h] [rbp-18h]
  void *dwDisposition; // [rsp+B8h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+40h] BYREF

  hKey = 0;
  *a3 = 0;
  if ( !a2 )
  {
    SetLastError(6u);
    return 0;
  }
  Token = (HANDLE)-1LL;
  v23 = 0;
  LODWORD(dwDisposition) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
    && ProcessUtils::IsCurrentProcess(v8, v7) )
  {
    v10 = (int)NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker((NSecurityLibrary *)&Token, &dwDisposition, v9) >= 0;
  }
  else
  {
    v10 = NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly((NSecurityLibrary *)&Token, &dwDisposition, v9);
  }
  if ( v10 && (_DWORD)dwDisposition )
    v23 = 1;
  v11 = 0;
  hKey = 0;
  if ( a1 )
  {
    ClientUserHandle = 0;
  }
  else
  {
    ClientUserHandle = (HKEY)SplGetClientUserHandle(131103);
    if ( !ClientUserHandle && GetLastError() == 5 )
      ClientUserHandle = (HKEY)SplGetClientUserHandle(131097);
    if ( !ClientUserHandle )
    {
      LastError = GetLastError();
      goto LABEL_26;
    }
    a1 = ClientUserHandle;
  }
  if ( *a2 == 92 && a2[1] == 92 && (LastError = RegOpenConnectionKey(a1, a2, &hKey)) == 0 )
  {
    v11 = L"DevMode";
  }
  else
  {
    LODWORD(dwDisposition) = 0;
    LastError = RegCreateKeyExW(a1, L"Printers\\DevModePerUser", 0, 0, 0, 0x2001Fu, 0, &hKey, (LPDWORD)&dwDisposition);
    if ( !LastError )
      v11 = a2;
  }
  if ( ClientUserHandle )
    RegCloseKey(ClientUserHandle);
LABEL_26:
  if ( LastError )
  {
    SetLastError(LastError);
    InfoKeyW = GetLastError();
    goto LABEL_44;
  }
  LODWORD(dwDisposition) = 0;
  InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, (LPDWORD)&dwDisposition, 0, 0);
  if ( !InfoKeyW )
  {
    v15 = (unsigned int)dwDisposition;
    if ( (unsigned int)dwDisposition >= 0x48 )
    {
      v16 = (BYTE *)HeapAlloc(g_hSpoolssHeap, 8u, (unsigned int)dwDisposition);
      if ( !v16 )
      {
        SetLastError(8u);
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "DllAllocSplMem",
          L"Unable to allocate %d bytes of memory on heap.",
          v15);
        *a3 = 0;
        InfoKeyW = GetLastError();
        goto LABEL_43;
      }
      v17 = hKey;
      *a3 = v16;
      InfoKeyW = RegQueryValueExW(v17, v11, 0, 0, v16, (LPDWORD)&dwDisposition);
      if ( !InfoKeyW )
      {
        v18 = (unsigned __int16 *)*a3;
        IsValidDevmodeNo = -2147024883;
        if ( *a3 )
        {
          if ( (unsigned int)dwDisposition >= 0x4CuLL )
          {
            v20 = v18[34] + (unsigned __int64)v18[35];
            if ( (unsigned int)dwDisposition >= v20 )
              IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(
                                   v18,
                                   v20,
                                   (unsigned int)dwDisposition);
          }
        }
        InfoKeyW = StatusFromHResult(IsValidDevmodeNo);
        if ( !InfoKeyW )
          goto LABEL_41;
        if ( !RegDeleteValueW(hKey, v11) )
          InfoKeyW = 2;
      }
      HeapFree(g_hSpoolssHeap, 0, *a3);
      *a3 = 0;
LABEL_41:
      if ( InfoKeyW == 2 )
        InfoKeyW = 0;
    }
  }
LABEL_43:
  RegCloseKey(hKey);
LABEL_44:
  if ( InfoKeyW )
  {
    SetLastError(InfoKeyW);
    if ( InfoKeyW != 5 )
      PrvSpoolssTelemetry::WriteDbgTraceError("bGetDevModePerUser", L"Failed to get devmode. Error %d.", InfoKeyW);
    NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)&Token);
    return 0;
  }
  else
  {
    v21 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( Token && !SetThreadToken(0, Token) )
        ExitProcess(1u);
      CloseHandle(v21);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1400038f0  push    rbp
0x1400038f2  push    rbx
0x1400038f3  push    rsi
0x1400038f4  push    r13
0x1400038f6  push    r14
0x1400038f8  mov     rbp, rsp
0x1400038fb  sub     rsp, 80h
0x140003902  xor     r13d, r13d
0x140003905  mov     r14, r8
0x140003908  mov     [rbp+hKey], r13
0x14000390c  mov     rbx, rdx
0x14000390f  mov     [r8], r13
0x140003912  mov     rsi, rcx
0x140003915  test    rdx, rdx
0x140003918  jnz     short loc_14000392C
0x14000391a  mov     ecx, 6; dwErrCode
0x14000391f  call    cs:__imp_SetLastError
0x140003925  xor     eax, eax
0x140003927  jmp     loc_140003C4D
0x14000392c  mov     [rsp+80h+var_8], r12
0x140003931  mov     [rsp+80h+var_10], r15
0x140003936  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x14000393e  mov     [rbp+var_18], r13b
0x140003942  mov     dword ptr [rbp+dwDisposition], r13d
0x140003946  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14000394d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140003952  test    al, al
0x140003954  jz      short loc_140003973
0x140003956  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x14000395b  lea     rdx, [rbp+dwDisposition]; void **
0x14000395f  lea     rcx, [rbp+Token]; this
0x140003963  test    al, al
0x140003965  jz      short loc_14000397B
0x140003967  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x14000396c  not     eax
0x14000396e  shr     eax, 1Fh
0x140003971  jmp     short loc_140003980
0x140003973  lea     rdx, [rbp+dwDisposition]; void **
0x140003977  lea     rcx, [rbp+Token]; this
0x14000397b  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x140003980  test    eax, eax
0x140003982  jz      short loc_14000398E
0x140003984  cmp     dword ptr [rbp+dwDisposition], r13d
0x140003988  jz      short loc_14000398E
0x14000398a  mov     [rbp+var_18], 1
0x14000398e  mov     [rsp+80h+arg_0], rdi
0x140003996  mov     r12, r13
0x140003999  mov     [rbp+hKey], r13
0x14000399d  test    rsi, rsi
0x1400039a0  jnz     short loc_1400039E4
0x1400039a2  mov     ecx, 2001Fh
0x1400039a7  call    SplGetClientUserHandle
0x1400039ac  mov     rdi, rax
0x1400039af  test    rax, rax
0x1400039b2  jnz     short loc_1400039CC
0x1400039b4  call    cs:__imp_GetLastError
0x1400039ba  cmp     eax, 5
0x1400039bd  jnz     short loc_1400039CC
0x1400039bf  mov     ecx, 20019h
0x1400039c4  call    SplGetClientUserHandle
0x1400039c9  mov     rdi, rax
0x1400039cc  test    rdi, rdi
0x1400039cf  jnz     short loc_1400039DF
0x1400039d1  call    cs:__imp_GetLastError
0x1400039d7  mov     r15d, eax
0x1400039da  jmp     loc_140003A69
0x1400039df  mov     rsi, rdi
0x1400039e2  jmp     short loc_1400039E7
0x1400039e4  mov     rdi, r13
0x1400039e7  cmp     word ptr [rbx], 5Ch ; '\'
0x1400039eb  jnz     short loc_140003A13
0x1400039ed  cmp     word ptr [rbx+2], 5Ch ; '\'
0x1400039f2  jnz     short loc_140003A13
0x1400039f4  lea     r8, [rbp+hKey]; phkResult
0x1400039f8  mov     rdx, rbx; unsigned __int16 *
0x1400039fb  mov     rcx, rsi; hKey
0x1400039fe  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140003a03  mov     r15d, eax
0x140003a06  test    eax, eax
0x140003a08  jnz     short loc_140003A13
0x140003a0a  lea     r12, gszDevMode; "DevMode"
0x140003a11  jmp     short loc_140003A5B
0x140003a13  lea     rax, [rbp+dwDisposition]
0x140003a17  mov     dword ptr [rbp+dwDisposition], r13d
0x140003a1b  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x140003a20  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140003a27  lea     rax, [rbp+hKey]
0x140003a2b  xor     r9d, r9d; lpClass
0x140003a2e  mov     [rsp+80h+phkResult], rax; phkResult
0x140003a33  xor     r8d, r8d; Reserved
0x140003a36  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140003a3b  mov     rcx, rsi; hKey
0x140003a3e  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x140003a46  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x140003a4b  call    cs:__imp_RegCreateKeyExW
0x140003a51  mov     r15d, eax
0x140003a54  test    eax, eax
0x140003a56  jnz     short loc_140003A5B
0x140003a58  mov     r12, rbx
0x140003a5b  test    rdi, rdi
0x140003a5e  jz      short loc_140003A69
0x140003a60  mov     rcx, rdi; hKey
0x140003a63  call    cs:__imp_RegCloseKey
0x140003a69  test    r15d, r15d
0x140003a6c  jz      short loc_140003A84
0x140003a6e  mov     ecx, r15d; dwErrCode
0x140003a71  call    cs:__imp_SetLastError
0x140003a77  call    cs:__imp_GetLastError
0x140003a7d  mov     ebx, eax
0x140003a7f  jmp     loc_140003BCF
0x140003a84  mov     rcx, [rbp+hKey]; hKey
0x140003a88  lea     rax, [rbp+dwDisposition]
0x140003a8c  mov     [rsp+80h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140003a91  xor     r9d, r9d; lpReserved
0x140003a94  mov     [rsp+80h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140003a99  xor     r8d, r8d; lpcchClass
0x140003a9c  mov     [rsp+80h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140003aa1  xor     edx, edx; lpClass
0x140003aa3  mov     [rsp+80h+lpdwDisposition], r13; lpcbMaxValueNameLen
0x140003aa8  mov     [rsp+80h+phkResult], r13; lpcValues
0x140003aad  mov     [rsp+80h+lpSecurityAttributes], r13; lpcbMaxClassLen
0x140003ab2  mov     qword ptr [rsp+80h+samDesired], r13; lpcbMaxSubKeyLen
0x140003ab7  mov     qword ptr [rsp+80h+dwOptions], r13; lpcSubKeys
0x140003abc  mov     dword ptr [rbp+dwDisposition], r13d
0x140003ac0  call    cs:__imp_RegQueryInfoKeyW
0x140003ac6  mov     ebx, eax
0x140003ac8  test    eax, eax
0x140003aca  jnz     loc_140003BC5
0x140003ad0  mov     edi, dword ptr [rbp+dwDisposition]
0x140003ad3  cmp     edi, 48h ; 'H'
0x140003ad6  jb      loc_140003BC5
0x140003adc  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140003ae3  mov     r8d, edi; dwBytes
0x140003ae6  mov     edx, 8; dwFlags
0x140003aeb  call    cs:__imp_HeapAlloc
0x140003af1  mov     rbx, rax
0x140003af4  test    rax, rax
0x140003af7  jnz     short loc_140003B2A
0x140003af9  mov     ecx, 8; dwErrCode
0x140003afe  call    cs:__imp_SetLastError
0x140003b04  mov     r8d, edi
0x140003b07  lea     rdx, aUnableToAlloca; "Unable to allocate %d bytes of memory o"...
0x140003b0e  lea     rcx, aDllallocsplmem; "DllAllocSplMem"
0x140003b15  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003b1a  mov     [r14], rbx
0x140003b1d  call    cs:__imp_GetLastError
0x140003b23  mov     ebx, eax
0x140003b25  jmp     loc_140003BC5
0x140003b2a  mov     rcx, [rbp+hKey]; hKey
0x140003b2e  lea     rax, [rbp+dwDisposition]
0x140003b32  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x140003b37  xor     r9d, r9d; lpType
0x140003b3a  xor     r8d, r8d; lpReserved
0x140003b3d  mov     qword ptr [rsp+80h+dwOptions], rbx; lpData
0x140003b42  mov     rdx, r12; lpValueName
0x140003b45  mov     [r14], rbx
0x140003b48  call    cs:__imp_RegQueryValueExW
0x140003b4e  mov     ebx, eax
0x140003b50  test    eax, eax
0x140003b52  jnz     short loc_140003BA9
0x140003b54  mov     rcx, [r14]
0x140003b57  mov     r9d, 8007000Dh
0x140003b5d  test    rcx, rcx
0x140003b60  jz      short loc_140003B84
0x140003b62  mov     r8d, dword ptr [rbp+dwDisposition]
0x140003b66  cmp     r8, 4Ch ; 'L'
0x140003b6a  jb      short loc_140003B84
0x140003b6c  movzx   edx, word ptr [rcx+46h]
0x140003b70  movzx   eax, word ptr [rcx+44h]
0x140003b74  add     rdx, rax
0x140003b77  cmp     r8, rdx
0x140003b7a  jb      short loc_140003B84
0x140003b7c  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x140003b81  mov     r9d, eax
0x140003b84  mov     ecx, r9d
0x140003b87  call    StatusFromHResult
0x140003b8c  mov     ebx, eax
0x140003b8e  test    eax, eax
0x140003b90  jz      short loc_140003BBE
0x140003b92  mov     rcx, [rbp+hKey]; hKey
0x140003b96  mov     rdx, r12; lpValueName
0x140003b99  call    cs:__imp_RegDeleteValueW
0x140003b9f  test    eax, eax
0x140003ba1  mov     ecx, 2
0x140003ba6  cmovz   ebx, ecx
0x140003ba9  mov     r8, [r14]; lpMem
0x140003bac  xor     edx, edx; dwFlags
0x140003bae  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140003bb5  call    cs:__imp_HeapFree
0x140003bbb  mov     [r14], r13
0x140003bbe  cmp     ebx, 2
0x140003bc1  cmovz   ebx, r13d
0x140003bc5  mov     rcx, [rbp+hKey]; hKey
0x140003bc9  call    cs:__imp_RegCloseKey
0x140003bcf  mov     r15, [rsp+80h+var_10]
0x140003bd4  mov     r12, [rsp+80h+var_8]
0x140003bd9  mov     rdi, [rsp+80h+arg_0]
0x140003be1  test    ebx, ebx
0x140003be3  jz      short loc_140003C15
0x140003be5  mov     ecx, ebx; dwErrCode
0x140003be7  call    cs:__imp_SetLastError
0x140003bed  cmp     ebx, 5
0x140003bf0  jz      short loc_140003C08
0x140003bf2  mov     r8d, ebx
0x140003bf5  lea     rdx, aFailedToGetDev; "Failed to get devmode. Error %d."
0x140003bfc  lea     rcx, aBgetdevmodeper; "bGetDevModePerUser"
0x140003c03  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003c08  lea     rcx, [rbp+Token]; this
0x140003c0c  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x140003c11  xor     eax, eax
0x140003c13  jmp     short loc_140003C4D
0x140003c15  mov     rbx, [rbp+Token]
0x140003c19  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140003c1d  jz      short loc_140003C48
0x140003c1f  test    rbx, rbx
0x140003c22  jz      short loc_140003C3F
0x140003c24  mov     rdx, rbx; Token
0x140003c27  xor     ecx, ecx; Thread
0x140003c29  call    cs:__imp_SetThreadToken
0x140003c2f  test    eax, eax
0x140003c31  jnz     short loc_140003C3F
0x140003c33  mov     ecx, 1; uExitCode
0x140003c38  call    cs:__imp_ExitProcess
0x140003c3f  mov     rcx, rbx; hObject
0x140003c42  call    cs:__imp_CloseHandle
0x140003c48  mov     eax, 1
0x140003c4d  add     rsp, 80h
0x140003c54  pop     r14
0x140003c56  pop     r13
0x140003c58  pop     rsi
0x140003c59  pop     rbx
0x140003c5a  pop     rbp
0x140003c5b  retn
```
