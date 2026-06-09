# bGetDevModePerUser

- ea: `0x1400043e0`
- end: `0x14000477c`
- name: `bGetDevModePerUser`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000487c`

## callees

- `0x140002c80`
- `0x140002f40`
- `0x1400043e0`
- `0x140004790`
- `0x140004800`
- `0x14000de80`
- `0x14000deb0`
- `0x140015378`
- `0x140016314`
- `0x140016350`
- `0x140025504`
- `0x1400257ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400046b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400046b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400044cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004611`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000440f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000440f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400046ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140004736`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140004736`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000474b`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000474b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000475b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000475b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004696`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140004696`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400045e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400045e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000454d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000454d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000463f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000463f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000456b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000456b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046d2`

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
  BYTE *v15; // rax
  unsigned __int16 *v16; // rcx
  unsigned int IsValidDevmodeNo; // r9d
  unsigned __int64 v18; // rdx
  HANDLE v19; // rbx
  HANDLE Token; // [rsp+60h] [rbp-20h] BYREF
  char v21; // [rsp+68h] [rbp-18h]
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
  v21 = 0;
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
    v21 = 1;
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
  if ( !InfoKeyW && (unsigned int)dwDisposition >= 0x48 )
  {
    v15 = (BYTE *)DllAllocSplMem((unsigned int)dwDisposition);
    *a3 = v15;
    if ( !v15 )
    {
      InfoKeyW = GetLastError();
      goto LABEL_43;
    }
    InfoKeyW = RegQueryValueExW(hKey, v11, 0, 0, v15, (LPDWORD)&dwDisposition);
    if ( !InfoKeyW )
    {
      v16 = (unsigned __int16 *)*a3;
      IsValidDevmodeNo = -2147024883;
      if ( *a3 )
      {
        if ( (unsigned int)dwDisposition >= 0x4CuLL )
        {
          v18 = v16[34] + (unsigned __int64)v16[35];
          if ( (unsigned int)dwDisposition >= v18 )
            IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(
                                 v16,
                                 v18,
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
    v19 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( Token && !SetThreadToken(0, Token) )
        ExitProcess(1u);
      CloseHandle(v19);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1400043e0  push    rbp
0x1400043e2  push    rbx
0x1400043e3  push    rsi
0x1400043e4  push    r13
0x1400043e6  push    r14
0x1400043e8  mov     rbp, rsp
0x1400043eb  sub     rsp, 80h
0x1400043f2  xor     r13d, r13d
0x1400043f5  mov     r14, r8
0x1400043f8  mov     [rbp+hKey], r13
0x1400043fc  mov     rbx, rdx
0x1400043ff  mov     [r8], r13
0x140004402  mov     rsi, rcx
0x140004405  test    rdx, rdx
0x140004408  jnz     short loc_140004422
0x14000440a  mov     ecx, 6; dwErrCode
0x14000440f  call    cs:__imp_SetLastError
0x140004416  nop     dword ptr [rax+rax+00h]
0x14000441b  xor     eax, eax
0x14000441d  jmp     loc_14000476C
0x140004422  mov     [rsp+80h+var_8], r12
0x140004427  mov     [rsp+80h+var_10], r15
0x14000442c  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x140004434  mov     [rbp+var_18], r13b
0x140004438  mov     dword ptr [rbp+dwDisposition], r13d
0x14000443c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140004443  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140004448  test    al, al
0x14000444a  jz      short loc_140004469
0x14000444c  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140004451  lea     rdx, [rbp+dwDisposition]; void **
0x140004455  lea     rcx, [rbp+Token]; this
0x140004459  test    al, al
0x14000445b  jz      short loc_140004471
0x14000445d  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x140004462  not     eax
0x140004464  shr     eax, 1Fh
0x140004467  jmp     short loc_140004476
0x140004469  lea     rdx, [rbp+dwDisposition]; void **
0x14000446d  lea     rcx, [rbp+Token]; this
0x140004471  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x140004476  test    eax, eax
0x140004478  jz      short loc_140004484
0x14000447a  cmp     dword ptr [rbp+dwDisposition], r13d
0x14000447e  jz      short loc_140004484
0x140004480  mov     [rbp+var_18], 1
0x140004484  mov     [rsp+80h+arg_0], rdi
0x14000448c  mov     r12, r13
0x14000448f  mov     [rbp+hKey], r13
0x140004493  test    rsi, rsi
0x140004496  jnz     short loc_1400044E6
0x140004498  mov     ecx, 2001Fh
0x14000449d  call    SplGetClientUserHandle
0x1400044a2  mov     rdi, rax
0x1400044a5  test    rax, rax
0x1400044a8  jnz     short loc_1400044C8
0x1400044aa  call    cs:__imp_GetLastError
0x1400044b1  nop     dword ptr [rax+rax+00h]
0x1400044b6  cmp     eax, 5
0x1400044b9  jnz     short loc_1400044C8
0x1400044bb  mov     ecx, 20019h
0x1400044c0  call    SplGetClientUserHandle
0x1400044c5  mov     rdi, rax
0x1400044c8  test    rdi, rdi
0x1400044cb  jnz     short loc_1400044E1
0x1400044cd  call    cs:__imp_GetLastError
0x1400044d4  nop     dword ptr [rax+rax+00h]
0x1400044d9  mov     r15d, eax
0x1400044dc  jmp     loc_140004577
0x1400044e1  mov     rsi, rdi
0x1400044e4  jmp     short loc_1400044E9
0x1400044e6  mov     rdi, r13
0x1400044e9  cmp     word ptr [rbx], 5Ch ; '\'
0x1400044ed  jnz     short loc_140004515
0x1400044ef  cmp     word ptr [rbx+2], 5Ch ; '\'
0x1400044f4  jnz     short loc_140004515
0x1400044f6  lea     r8, [rbp+hKey]; phkResult
0x1400044fa  mov     rdx, rbx; unsigned __int16 *
0x1400044fd  mov     rcx, rsi; hKey
0x140004500  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140004505  mov     r15d, eax
0x140004508  test    eax, eax
0x14000450a  jnz     short loc_140004515
0x14000450c  lea     r12, gszDevMode; "DevMode"
0x140004513  jmp     short loc_140004563
0x140004515  lea     rax, [rbp+dwDisposition]
0x140004519  mov     dword ptr [rbp+dwDisposition], r13d
0x14000451d  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x140004522  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140004529  lea     rax, [rbp+hKey]
0x14000452d  xor     r9d, r9d; lpClass
0x140004530  mov     [rsp+80h+phkResult], rax; phkResult
0x140004535  xor     r8d, r8d; Reserved
0x140004538  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14000453d  mov     rcx, rsi; hKey
0x140004540  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x140004548  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x14000454d  call    cs:__imp_RegCreateKeyExW
0x140004554  nop     dword ptr [rax+rax+00h]
0x140004559  mov     r15d, eax
0x14000455c  test    eax, eax
0x14000455e  jnz     short loc_140004563
0x140004560  mov     r12, rbx
0x140004563  test    rdi, rdi
0x140004566  jz      short loc_140004577
0x140004568  mov     rcx, rdi; hKey
0x14000456b  call    cs:__imp_RegCloseKey
0x140004572  nop     dword ptr [rax+rax+00h]
0x140004577  mov     rdi, [rsp+80h+arg_0]
0x14000457f  test    r15d, r15d
0x140004582  jz      short loc_1400045A6
0x140004584  mov     ecx, r15d; dwErrCode
0x140004587  call    cs:__imp_SetLastError
0x14000458e  nop     dword ptr [rax+rax+00h]
0x140004593  call    cs:__imp_GetLastError
0x14000459a  nop     dword ptr [rax+rax+00h]
0x14000459f  mov     ebx, eax
0x1400045a1  jmp     loc_1400046DE
0x1400045a6  mov     rcx, [rbp+hKey]; hKey
0x1400045aa  lea     rax, [rbp+dwDisposition]
0x1400045ae  mov     [rsp+80h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1400045b3  xor     r9d, r9d; lpReserved
0x1400045b6  mov     [rsp+80h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1400045bb  xor     r8d, r8d; lpcchClass
0x1400045be  mov     [rsp+80h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400045c3  xor     edx, edx; lpClass
0x1400045c5  mov     [rsp+80h+lpdwDisposition], r13; lpcbMaxValueNameLen
0x1400045ca  mov     [rsp+80h+phkResult], r13; lpcValues
0x1400045cf  mov     [rsp+80h+lpSecurityAttributes], r13; lpcbMaxClassLen
0x1400045d4  mov     qword ptr [rsp+80h+samDesired], r13; lpcbMaxSubKeyLen
0x1400045d9  mov     qword ptr [rsp+80h+dwOptions], r13; lpcSubKeys
0x1400045de  mov     dword ptr [rbp+dwDisposition], r13d
0x1400045e2  call    cs:__imp_RegQueryInfoKeyW
0x1400045e9  nop     dword ptr [rax+rax+00h]
0x1400045ee  mov     ebx, eax
0x1400045f0  test    eax, eax
0x1400045f2  jnz     loc_1400046CE
0x1400045f8  mov     ecx, dword ptr [rbp+dwDisposition]; dwBytes
0x1400045fb  cmp     ecx, 48h ; 'H'
0x1400045fe  jb      loc_1400046CE
0x140004604  call    DllAllocSplMem
0x140004609  mov     [r14], rax
0x14000460c  test    rax, rax
0x14000460f  jnz     short loc_140004624
0x140004611  call    cs:__imp_GetLastError
0x140004618  nop     dword ptr [rax+rax+00h]
0x14000461d  mov     ebx, eax
0x14000461f  jmp     loc_1400046CE
0x140004624  lea     rcx, [rbp+dwDisposition]
0x140004628  xor     r9d, r9d; lpType
0x14000462b  mov     qword ptr [rsp+80h+samDesired], rcx; lpcbData
0x140004630  xor     r8d, r8d; lpReserved
0x140004633  mov     rcx, [rbp+hKey]; hKey
0x140004637  mov     rdx, r12; lpValueName
0x14000463a  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x14000463f  call    cs:__imp_RegQueryValueExW
0x140004646  nop     dword ptr [rax+rax+00h]
0x14000464b  mov     ebx, eax
0x14000464d  test    eax, eax
0x14000464f  jnz     short loc_1400046AC
0x140004651  mov     rcx, [r14]
0x140004654  mov     r9d, 8007000Dh
0x14000465a  test    rcx, rcx
0x14000465d  jz      short loc_140004681
0x14000465f  mov     r8d, dword ptr [rbp+dwDisposition]
0x140004663  cmp     r8, 4Ch ; 'L'
0x140004667  jb      short loc_140004681
0x140004669  movzx   edx, word ptr [rcx+46h]
0x14000466d  movzx   eax, word ptr [rcx+44h]
0x140004671  add     rdx, rax
0x140004674  cmp     r8, rdx
0x140004677  jb      short loc_140004681
0x140004679  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x14000467e  mov     r9d, eax
0x140004681  mov     ecx, r9d
0x140004684  call    StatusFromHResult
0x140004689  mov     ebx, eax
0x14000468b  test    eax, eax
0x14000468d  jz      short loc_1400046C7
0x14000468f  mov     rcx, [rbp+hKey]; hKey
0x140004693  mov     rdx, r12; lpValueName
0x140004696  call    cs:__imp_RegDeleteValueW
0x14000469d  nop     dword ptr [rax+rax+00h]
0x1400046a2  test    eax, eax
0x1400046a4  mov     ecx, 2
0x1400046a9  cmovz   ebx, ecx
0x1400046ac  mov     r8, [r14]; lpMem
0x1400046af  xor     edx, edx; dwFlags
0x1400046b1  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400046b8  call    cs:__imp_HeapFree
0x1400046bf  nop     dword ptr [rax+rax+00h]
0x1400046c4  mov     [r14], r13
0x1400046c7  cmp     ebx, 2
0x1400046ca  cmovz   ebx, r13d
0x1400046ce  mov     rcx, [rbp+hKey]; hKey
0x1400046d2  call    cs:__imp_RegCloseKey
0x1400046d9  nop     dword ptr [rax+rax+00h]
0x1400046de  mov     r15, [rsp+80h+var_10]
0x1400046e3  mov     r12, [rsp+80h+var_8]
0x1400046e8  test    ebx, ebx
0x1400046ea  jz      short loc_140004722
0x1400046ec  mov     ecx, ebx; dwErrCode
0x1400046ee  call    cs:__imp_SetLastError
0x1400046f5  nop     dword ptr [rax+rax+00h]
0x1400046fa  cmp     ebx, 5
0x1400046fd  jz      short loc_140004715
0x1400046ff  mov     r8d, ebx
0x140004702  lea     rdx, aFailedToGetDev; "Failed to get devmode. Error %d."
0x140004709  lea     rcx, aBgetdevmodeper; "bGetDevModePerUser"
0x140004710  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140004715  lea     rcx, [rbp+Token]; this
0x140004719  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x14000471e  xor     eax, eax
0x140004720  jmp     short loc_14000476C
0x140004722  mov     rbx, [rbp+Token]
0x140004726  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000472a  jz      short loc_140004767
0x14000472c  test    rbx, rbx
0x14000472f  jz      short loc_140004758
0x140004731  mov     rdx, rbx; Token
0x140004734  xor     ecx, ecx; Thread
0x140004736  call    cs:__imp_SetThreadToken
0x14000473d  nop     dword ptr [rax+rax+00h]
0x140004742  test    eax, eax
0x140004744  jnz     short loc_140004758
0x140004746  mov     ecx, 1; uExitCode
0x14000474b  call    cs:__imp_ExitProcess
0x140004758  mov     rcx, rbx; hObject
0x14000475b  call    cs:__imp_CloseHandle
0x140004762  nop     dword ptr [rax+rax+00h]
0x140004767  mov     eax, 1
0x14000476c  add     rsp, 80h
0x140004773  pop     r14
0x140004775  pop     r13
0x140004777  pop     rsi
0x140004778  pop     rbx
0x140004779  pop     rbp
0x14000477a  retn
```
