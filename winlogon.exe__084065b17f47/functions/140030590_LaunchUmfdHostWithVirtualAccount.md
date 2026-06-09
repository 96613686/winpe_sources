# LaunchUmfdHostWithVirtualAccount

- ea: `0x140030590`
- end: `0x140030b29`
- name: `LaunchUmfdHostWithVirtualAccount`
- size: `1433`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14008d360`
- `0x140095ed0`

## callees

- `0x14000d4e0`
- `0x140030590`
- `0x140030b30`
- `0x140030ccc`
- `0x1400426f0`
- `0x140053720`
- `0x140095d3c`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003072b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003072b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400306e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400306e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003097d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003097d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003073a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003073a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140030969`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140030969`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140030acf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140030acf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400308a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400308a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003099b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003099b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400307d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400307d8`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400308e9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1400308e9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400308bc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400308bc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140030aed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140030aed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030af8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030b11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030af8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030b11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140030829`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140030829`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003065b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003065b`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x1400309fc`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x1400309fc`
- `ntdll!RtlSetEnvironmentVariable` at `0x140030944`
- `ntdll!RtlSetEnvironmentVariable` at `0x140030944`
- `ntdll!RtlInitUnicodeString` at `0x140030920`
- `ntdll!RtlInitUnicodeString` at `0x140030931`
- `ntdll!RtlInitUnicodeString` at `0x140030920`
- `ntdll!RtlInitUnicodeString` at `0x140030931`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400307f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400307f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003086a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14003086a`
- `USERENV!CreateEnvironmentBlock` at `0x140030907`
- `USERENV!CreateEnvironmentBlock` at `0x140030907`
- `USERENV!DestroyEnvironmentBlock` at `0x140030ae2`
- `USERENV!DestroyEnvironmentBlock` at `0x140030ae2`
- `USERENV!CreateAppContainerProfile` at `0x1400309e1`
- `USERENV!CreateAppContainerProfile` at `0x1400309e1`

## string_xrefs

- `0x140030926`: `%TEMP%`

## pseudocode

```c
_BOOL8 LaunchUmfdHostWithVirtualAccount()
{
  HANDLE v0; // rsi
  WCHAR *v1; // rdi
  int v2; // r14d
  int v3; // r15d
  int v4; // ebx
  int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  signed int LastError; // eax
  NTSTATUS v12; // ebx
  signed int v13; // eax
  __int128 *v14; // rcx
  int v15; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v16; // r14
  LPVOID Environment; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+84h] [rbp-7Ch] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp-68h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList[2]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp-50h] BYREF
  PACL pDacl; // [rsp+B8h] [rbp-48h] BYREF
  PACL v29; // [rsp+C0h] [rbp-40h] BYREF
  struct _PROCESS_INFORMATION hThread; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v31; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-10h]
  struct _SECURITY_ATTRIBUTES ThreadAttributes; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING Value; // [rsp+110h] [rbp+10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+120h] [rbp+20h] BYREF
  _BYTE StartupInfo[112]; // [rsp+130h] [rbp+30h] BYREF
  PSID TokenInformation[12]; // [rsp+1A0h] [rbp+A0h] BYREF

  TokenHandle = 0;
  SecurityDescriptor = 0;
  v29 = 0;
  v0 = 0;
  bDaclPresent = 0;
  memset(&hThread, 0, sizeof(hThread));
  bDaclDefaulted = 0;
  v1 = 0;
  memset(&ThreadAttributes, 0, sizeof(ThreadAttributes));
  pDacl = 0;
  v2 = 0;
  memset(StartupInfo, 0, sizeof(StartupInfo));
  StringSid = 0;
  ReturnLength = 0;
  lpAttributeList[0] = 0;
  Environment = 0;
  pSid = 0;
  v32 = 0;
  v24 = 0;
  v31 = 0;
  phkResult = 0;
  DestinationString = 0;
  Value = 0;
  v3 = 1;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNt", &phkResult) )
  {
    v2 = 1;
    RegCloseKey(phkResult);
  }
  v4 = MapUmfdVirtualAccount();
  if ( v4 >= 0 )
  {
    v6 = LogonUmfdAccountAndSetTokenIntegrityLevel(&TokenHandle);
    v0 = TokenHandle;
    v4 = v6;
    if ( v6 >= 0 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength)
        || !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      {
        goto LABEL_36;
      }
      v7 = -1;
      while ( StringSid[++v7] != 0 )
        ;
      v9 = v7 + 29;
      v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v7 + 29));
      v1 = v10;
      if ( !v10 )
      {
        v4 = -2147024882;
        goto LABEL_4;
      }
      v4 = StringCchPrintfW(v10, v9, L"O:SYD:(A;;GA;;;%s)(A;;GA;;;SY)", StringSid);
      if ( v4 < 0 )
        goto LABEL_4;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v1, 1u, &SecurityDescriptor, 0)
        || !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        goto LABEL_36;
      }
      if ( !pDacl )
      {
        v4 = -2147024882;
        goto LABEL_4;
      }
      v29 = pDacl;
      if ( !SetTokenInformation(v0, TokenDefaultDacl, &v29, 8u) )
      {
LABEL_36:
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_4;
      }
      if ( v2 )
        goto LABEL_62;
      v4 = CreateAppContainerProfile(
             L"microsoft.windows.fontdrvhost",
             L"Usermode Font Driver Host",
             L"Usermode Font Driver Host",
             0,
             0,
             &pSid);
      if ( v4 == -2147024713 )
        v4 = AppContainerDeriveSidFromMoniker(L"microsoft.windows.fontdrvhost", &pSid);
      if ( v4 >= 0 )
      {
LABEL_62:
        if ( CreateEnvironmentBlock(&Environment, v0, 0) )
        {
          RtlInitUnicodeString(&DestinationString, L"LOCALAPPDATA");
          RtlInitUnicodeString(&Value, L"%TEMP%");
          v12 = RtlSetEnvironmentVariable((PWSTR *)&Environment, &DestinationString, &Value);
          if ( v12 >= 0 )
          {
            v14 = &v31;
            v24 = 0x300000001LL;
            if ( v2 )
              v14 = 0;
            v32 = 0;
            v31 = (unsigned __int64)pSid;
            v15 = CreateProcThreadAttributeList(v14, &v24, lpAttributeList);
            v16 = lpAttributeList[0];
            v4 = v15;
            if ( v15 >= 0 )
            {
              *(_DWORD *)StartupInfo = 112;
              *(_QWORD *)&StartupInfo[16] = L"Winsta0\\Default";
              ThreadAttributes.lpSecurityDescriptor = SecurityDescriptor;
              *(LPPROC_THREAD_ATTRIBUTE_LIST *)&StartupInfo[104] = lpAttributeList[0];
              *(_DWORD *)&StartupInfo[60] = 0x10000;
              ThreadAttributes.nLength = 24;
              ThreadAttributes.bInheritHandle = 1;
              if ( !CreateProcessAsUserW(
                      v0,
                      L"fontdrvhost.exe",
                      0,
                      &ThreadAttributes,
                      &ThreadAttributes,
                      0,
                      0x80404u,
                      Environment,
                      0,
                      (LPSTARTUPINFOW)StartupInfo,
                      &hThread) )
              {
                v13 = GetLastError();
                v4 = v13;
                if ( v13 > 0 )
                  v4 = (unsigned __int16)v13 | 0x80070000;
              }
            }
            if ( v16 )
            {
              DeleteProcThreadAttributeList(v16);
              LocalFree(v16);
            }
          }
          else
          {
            v4 = v12 | 0x10000000;
          }
          goto LABEL_4;
        }
        goto LABEL_36;
      }
    }
  }
LABEL_4:
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( pSid )
    FreeSid(pSid);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v1 )
    LocalFree(v1);
  if ( v0 )
    CloseHandle(v0);
  if ( v4 < 0 )
  {
    if ( !gUmfdHostThreadProcExecuted )
      v3 = LaunchUmfdHostWithCurrentTokenUnconditional();
    v4 = 0;
    if ( !v3 )
      v4 = -2147467259;
  }
  else
  {
    lpAttributeList[1] = (LPPROC_THREAD_ATTRIBUTE_LIST)hThread.hProcess;
    lpAttributeList[0] = 0;
    EnterCriticalSection(&g_csNamedEscape);
    ((void (__fastcall *)(_QWORD, const wchar_t *, __int64, __int64, LPPROC_THREAD_ATTRIBUTE_LIST *, int, LPPROC_THREAD_ATTRIBUTE_LIST *))g_pfnNamedEscape)(
      0,
      L"UmfdHost",
      19,
      16,
      lpAttributeList,
      16,
      lpAttributeList);
    LeaveCriticalSection(&g_csNamedEscape);
    if ( hThread.hThread )
    {
      ResumeThread(hThread.hThread);
      if ( hThread.hThread )
      {
        CloseHandle(hThread.hThread);
        hThread.hThread = 0;
      }
    }
    if ( hThread.hProcess )
      CloseHandle(hThread.hProcess);
  }
  return v4 >= 0;
}

```

## disassembly

```asm
0x140030590  push    rbp
0x140030592  push    rbx
0x140030593  push    rsi
0x140030594  push    rdi
0x140030595  push    r12
0x140030597  push    r14
0x140030599  push    r15
0x14003059b  lea     rbp, [rsp-110h]
0x1400305a3  sub     rsp, 210h
0x1400305aa  mov     rax, cs:__security_cookie
0x1400305b1  xor     rax, rsp
0x1400305b4  mov     [rbp+140h+var_40], rax
0x1400305bb  xor     r12d, r12d
0x1400305be  lea     r8, [rbp+140h+phkResult]; phkResult
0x1400305c2  xorps   xmm0, xmm0
0x1400305c5  mov     [rbp+140h+TokenHandle], r12
0x1400305c9  xor     eax, eax
0x1400305cb  mov     [rsp+240h+SecurityDescriptor], r12
0x1400305d0  xorps   xmm1, xmm1
0x1400305d3  mov     [rbp+140h+var_168], rax
0x1400305d7  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x1400305de  mov     qword ptr [rbp+140h+ThreadAttributes.bInheritHandle], rax
0x1400305e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400305e9  mov     [rbp+140h+var_180], r12
0x1400305ed  mov     esi, r12d
0x1400305f0  mov     [rbp+140h+bDaclPresent], r12d
0x1400305f4  movups  xmmword ptr [rbp+140h+hThread], xmm0
0x1400305f8  mov     [rbp+140h+bDaclDefaulted], r12d
0x1400305fc  mov     edi, r12d
0x1400305ff  movups  xmmword ptr [rbp+140h+ThreadAttributes.nLength], xmm0
0x140030603  mov     [rbp+140h+pDacl], r12
0x140030607  mov     r14d, r12d
0x14003060a  movups  xmmword ptr [rbp+140h+StartupInfo], xmm0
0x14003060e  mov     [rsp+240h+StringSid], r12
0x140030613  movups  xmmword ptr [rbp+140h+StartupInfo+10h], xmm0
0x140030617  mov     [rbp+140h+var_1C0], r12d
0x14003061b  movups  xmmword ptr [rbp+140h+StartupInfo+20h], xmm0
0x14003061f  mov     [rbp+140h+lpAttributeList], r12
0x140030623  movups  xmmword ptr [rbp+140h+StartupInfo+30h], xmm0
0x140030627  mov     [rsp+240h+Environment], r12
0x14003062c  movups  xmmword ptr [rbp+140h+StartupInfo+40h], xmm0
0x140030630  mov     [rsp+240h+pSid], r12
0x140030635  movups  xmmword ptr [rbp+140h+StartupInfo+50h], xmm0
0x14003063c  mov     [rbp+140h+var_150], rax
0x140030640  movups  xmmword ptr [rbp+140h+StartupInfo+60h], xmm0
0x140030647  mov     [rbp+140h+var_1B0], r12
0x14003064b  movups  [rbp+140h+var_160], xmm0
0x14003064f  mov     [rbp+140h+phkResult], r12
0x140030653  movups  xmmword ptr [rbp+140h+DestinationString.Length], xmm0
0x140030657  movups  xmmword ptr [rbp+140h+Value.Length], xmm1
0x14003065b  call    cs:__imp_RegOpenKeyW
0x140030661  mov     r15d, 1
0x140030667  test    eax, eax
0x140030669  jz      loc_140030994
0x14003066f  call    ?MapUmfdVirtualAccount@@YAJXZ; MapUmfdVirtualAccount(void)
0x140030674  mov     ebx, eax
0x140030676  test    eax, eax
0x140030678  jns     loc_1400307A5
0x14003067e  mov     rcx, [rsp+240h+Environment]; lpEnvironment
0x140030683  test    rcx, rcx
0x140030686  jnz     loc_140030AE2
0x14003068c  mov     rcx, [rsp+240h+pSid]; pSid
0x140030691  test    rcx, rcx
0x140030694  jnz     loc_140030AED
0x14003069a  mov     rcx, [rsp+240h+SecurityDescriptor]; hMem
0x14003069f  test    rcx, rcx
0x1400306a2  jnz     loc_140030AF8
0x1400306a8  mov     rcx, [rsp+240h+StringSid]; hMem
0x1400306ad  test    rcx, rcx
0x1400306b0  jnz     loc_140030B03
0x1400306b6  test    rdi, rdi
0x1400306b9  jnz     loc_140030B0E
0x1400306bf  test    rsi, rsi
0x1400306c2  jnz     loc_14003089D
0x1400306c8  test    ebx, ebx
0x1400306ca  js      loc_140030788
0x1400306d0  mov     rax, [rbp+140h+hThread]
0x1400306d4  lea     rcx, ?g_csNamedEscape@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400306db  mov     [rbp+140h+var_198], rax
0x1400306df  mov     [rbp+140h+lpAttributeList], r12
0x1400306e3  call    cs:__imp_EnterCriticalSection
0x1400306e9  lea     rax, [rbp+140h+lpAttributeList]
0x1400306ed  mov     r9d, 10h
0x1400306f3  mov     qword ptr [rsp+240h+dwCreationFlags], rax
0x1400306f8  lea     rdx, aUmfdhost; "UmfdHost"
0x1400306ff  lea     rax, [rbp+140h+lpAttributeList]
0x140030703  mov     [rsp+240h+bInheritHandles], 10h
0x14003070b  mov     [rsp+240h+ReturnLength], rax
0x140030710  mov     r8d, 13h
0x140030716  mov     rax, cs:?g_pfnNamedEscape@@3P6AHPEAUHDC__@@PEAGHHPEBDHPEAD@ZEA; int (*g_pfnNamedEscape)(HDC__ *,ushort *,int,int,char const *,int,char *)
0x14003071d  xor     ecx, ecx
0x14003071f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030724  lea     rcx, ?g_csNamedEscape@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003072b  call    cs:__imp_LeaveCriticalSection
0x140030731  mov     rcx, [rbp+140h+hThread+8]; hThread
0x140030735  test    rcx, rcx
0x140030738  jz      short loc_140030753
0x14003073a  call    cs:__imp_ResumeThread
0x140030740  mov     rcx, [rbp+140h+hThread+8]; hObject
0x140030744  test    rcx, rcx
0x140030747  jz      short loc_140030753
0x140030749  call    cs:__imp_CloseHandle
0x14003074f  mov     [rbp+140h+hThread+8], r12
0x140030753  mov     rcx, [rbp+140h+hThread]; hObject
0x140030757  test    rcx, rcx
0x14003075a  jnz     loc_140030892
0x140030760  not     ebx
0x140030762  shr     ebx, 1Fh
0x140030765  mov     eax, ebx
0x140030767  mov     rcx, [rbp+140h+var_40]
0x14003076e  xor     rcx, rsp; StackCookie
0x140030771  call    __security_check_cookie
0x140030776  add     rsp, 210h
0x14003077d  pop     r15
0x14003077f  pop     r14
0x140030781  pop     r12
0x140030783  pop     rdi
0x140030784  pop     rsi
0x140030785  pop     rbx
0x140030786  pop     rbp
0x140030787  retn
0x140030788  cmp     cs:?gUmfdHostThreadProcExecuted@@3_NA, r12b; bool gUmfdHostThreadProcExecuted
0x14003078f  jz      loc_140030B1C
0x140030795  test    r15d, r15d
0x140030798  mov     ebx, r12d
0x14003079b  mov     eax, 80004005h
0x1400307a0  cmovz   ebx, eax
0x1400307a3  jmp     short loc_140030760
0x1400307a5  lea     rcx, [rbp+140h+TokenHandle]; void **
0x1400307a9  call    ?LogonUmfdAccountAndSetTokenIntegrityLevel@@YAJPEAPEAX@Z; LogonUmfdAccountAndSetTokenIntegrityLevel(void * *)
0x1400307ae  mov     rsi, [rbp+140h+TokenHandle]
0x1400307b2  mov     ebx, eax
0x1400307b4  test    eax, eax
0x1400307b6  js      loc_14003067E
0x1400307bc  lea     rax, [rbp+140h+var_1C0]
0x1400307c0  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1400307c6  lea     r8, [rbp+140h+TokenInformation]; TokenInformation
0x1400307cd  mov     [rsp+240h+ReturnLength], rax; ReturnLength
0x1400307d2  mov     edx, r15d; TokenInformationClass
0x1400307d5  mov     rcx, rsi; TokenHandle
0x1400307d8  call    cs:__imp_GetTokenInformation
0x1400307de  test    eax, eax
0x1400307e0  jz      loc_140030874
0x1400307e6  mov     rcx, [rbp+140h+TokenInformation]; Sid
0x1400307ed  lea     rdx, [rsp+240h+StringSid]; StringSid
0x1400307f2  call    cs:__imp_ConvertSidToStringSidW
0x1400307f8  test    eax, eax
0x1400307fa  jz      short loc_140030874
0x1400307fc  mov     rcx, [rsp+240h+StringSid]
0x140030801  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140030808  nop     dword ptr [rax+rax+00000000h]
0x140030810  cmp     [rcx+rax*2+2], r12w
0x140030816  lea     rax, [rax+1]
0x14003081a  jnz     short loc_140030810
0x14003081c  lea     rbx, [rax+1Dh]
0x140030820  mov     ecx, 40h ; '@'; uFlags
0x140030825  lea     rdx, [rbx+rbx]; uBytes
0x140030829  call    cs:__imp_LocalAlloc
0x14003082f  mov     rdi, rax
0x140030832  test    rax, rax
0x140030835  jz      loc_1400309A6
0x14003083b  mov     r9, [rsp+240h+StringSid]
0x140030840  lea     r8, aOSydAGaSAGaSy; "O:SYD:(A;;GA;;;%s)(A;;GA;;;SY)"
0x140030847  mov     rdx, rbx; unsigned __int64
0x14003084a  mov     rcx, rax; unsigned __int16 *
0x14003084d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030852  mov     ebx, eax
0x140030854  test    eax, eax
0x140030856  js      loc_14003067E
0x14003085c  xor     r9d, r9d; SecurityDescriptorSize
0x14003085f  lea     r8, [rsp+240h+SecurityDescriptor]; SecurityDescriptor
0x140030864  mov     edx, r15d; StringSDRevision
0x140030867  mov     rcx, rdi; StringSecurityDescriptor
0x14003086a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140030870  test    eax, eax
0x140030872  jnz     short loc_1400308AB
0x140030874  call    cs:__imp_GetLastError
0x14003087a  mov     ebx, eax
0x14003087c  test    eax, eax
0x14003087e  jle     loc_14003067E
0x140030884  movzx   ebx, ax
0x140030887  or      ebx, 80070000h
0x14003088d  jmp     loc_14003067E
0x140030892  call    cs:__imp_CloseHandle
0x140030898  jmp     loc_140030760
0x14003089d  mov     rcx, rsi; hObject
0x1400308a0  call    cs:__imp_CloseHandle
0x1400308a6  jmp     loc_1400306C8
0x1400308ab  mov     rcx, [rsp+240h+SecurityDescriptor]; pSecurityDescriptor
0x1400308b0  lea     r9, [rbp+140h+bDaclDefaulted]; lpbDaclDefaulted
0x1400308b4  lea     r8, [rbp+140h+pDacl]; pDacl
0x1400308b8  lea     rdx, [rbp+140h+bDaclPresent]; lpbDaclPresent
0x1400308bc  call    cs:__imp_GetSecurityDescriptorDacl
0x1400308c2  test    eax, eax
0x1400308c4  jz      short loc_140030874
0x1400308c6  mov     rax, [rbp+140h+pDacl]
0x1400308ca  test    rax, rax
0x1400308cd  jz      loc_1400309B0
0x1400308d3  mov     r9d, 8; TokenInformationLength
0x1400308d9  mov     [rbp+140h+var_180], rax
0x1400308dd  lea     r8, [rbp+140h+var_180]; TokenInformation
0x1400308e1  mov     edx, 6; TokenInformationClass
0x1400308e6  mov     rcx, rsi; TokenHandle
0x1400308e9  call    cs:__imp_SetTokenInformation
0x1400308ef  test    eax, eax
0x1400308f1  jz      short loc_140030874
0x1400308f3  test    r14d, r14d
0x1400308f6  jz      loc_1400309BA
0x1400308fc  xor     r8d, r8d; bInherit
0x1400308ff  lea     rcx, [rsp+240h+Environment]; lpEnvironment
0x140030904  mov     rdx, rsi; hToken
0x140030907  call    cs:__imp_CreateEnvironmentBlock
0x14003090d  test    eax, eax
0x14003090f  jz      loc_140030874
0x140030915  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x14003091c  lea     rcx, [rbp+140h+DestinationString]; DestinationString
0x140030920  call    cs:__imp_RtlInitUnicodeString
0x140030926  lea     rdx, aTemp_0; "%TEMP%"
0x14003092d  lea     rcx, [rbp+140h+Value]; DestinationString
0x140030931  call    cs:__imp_RtlInitUnicodeString
0x140030937  lea     r8, [rbp+140h+Value]; Value
0x14003093b  lea     rdx, [rbp+140h+DestinationString]; Name
0x14003093f  lea     rcx, [rsp+240h+Environment]; Environment
0x140030944  call    cs:__imp_RtlSetEnvironmentVariable
0x14003094a  mov     ebx, eax
0x14003094c  test    eax, eax
0x14003094e  jns     loc_140030A11
0x140030954  bts     ebx, 1Ch
0x140030958  jmp     loc_14003067E
0x14003095d  test    r14, r14
0x140030960  jz      loc_14003067E
0x140030966  mov     rcx, r14; lpAttributeList
0x140030969  call    cs:__imp_DeleteProcThreadAttributeList
0x14003096f  mov     rcx, r14; hMem
0x140030972  call    cs:__imp_LocalFree
0x140030978  jmp     loc_14003067E
0x14003097d  call    cs:__imp_GetLastError
0x140030983  mov     ebx, eax
0x140030985  test    eax, eax
0x140030987  jle     short loc_14003095D
0x140030989  movzx   ebx, ax
0x14003098c  or      ebx, 80070000h
0x140030992  jmp     short loc_14003095D
0x140030994  mov     rcx, [rbp+140h+phkResult]; hKey
0x140030998  mov     r14d, r15d
0x14003099b  call    cs:__imp_RegCloseKey
0x1400309a1  jmp     loc_14003066F
0x1400309a6  mov     ebx, 8007000Eh
0x1400309ab  jmp     loc_14003067E
0x1400309b0  mov     ebx, 8007000Eh
0x1400309b5  jmp     loc_14003067E
0x1400309ba  lea     rax, [rsp+240h+pSid]
0x1400309bf  xor     r9d, r9d
0x1400309c2  mov     qword ptr [rsp+240h+bInheritHandles], rax
0x1400309c7  lea     r8, aUsermodeFontDr; "Usermode Font Driver Host"
0x1400309ce  lea     rdx, aUsermodeFontDr; "Usermode Font Driver Host"
0x1400309d5  mov     dword ptr [rsp+240h+ReturnLength], r12d
0x1400309da  lea     rcx, aMicrosoftWindo; "microsoft.windows.fontdrvhost"
0x1400309e1  call    cs:__imp_CreateAppContainerProfile
0x1400309e7  mov     ebx, eax
0x1400309e9  cmp     eax, 800700B7h
0x1400309ee  jnz     short loc_140030A04
0x1400309f0  lea     rdx, [rsp+240h+pSid]
0x1400309f5  lea     rcx, aMicrosoftWindo; "microsoft.windows.fontdrvhost"
0x1400309fc  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x140030a02  mov     ebx, eax
0x140030a04  test    ebx, ebx
0x140030a06  js      loc_14003067E
0x140030a0c  jmp     loc_1400308FC
0x140030a11  mov     rax, [rsp+240h+pSid]
0x140030a16  lea     rcx, [rbp+140h+var_160]
0x140030a1a  test    r14d, r14d
0x140030a1d  mov     dword ptr [rbp+140h+var_1B0], r15d
0x140030a21  lea     r8, [rbp+140h+lpAttributeList]; struct _PROC_THREAD_ATTRIBUTE_LIST **
0x140030a25  mov     dword ptr [rbp+140h+var_1B0+4], 3
0x140030a2c  cmovnz  rcx, r12; lpValue
0x140030a30  mov     [rbp+140h+var_150], r12
0x140030a34  lea     rdx, [rbp+140h+var_1B0]; PVOID
0x140030a38  mov     qword ptr [rbp+140h+var_160+8], r12
0x140030a3c  mov     qword ptr [rbp+140h+var_160], rax
0x140030a40  call    ?CreateProcThreadAttributeList@@YAJPEAU_SECURITY_CAPABILITIES@@PEAU_WIN32K_SYSCALL_FILTER@@PEAPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; CreateProcThreadAttributeList(_SECURITY_CAPABILITIES *,_WIN32K_SYSCALL_FILTER *,_PROC_THREAD_ATTRIBUTE_LIST * *)
0x140030a45  mov     r14, [rbp+140h+lpAttributeList]
0x140030a49  mov     ebx, eax
0x140030a4b  test    eax, eax
0x140030a4d  js      loc_14003095D
0x140030a53  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x140030a5a  mov     dword ptr [rbp+140h+StartupInfo], 70h ; 'p'
0x140030a61  mov     qword ptr [rbp+140h+StartupInfo+10h], rax
0x140030a65  lea     r9, [rbp+140h+ThreadAttributes]; lpProcessAttributes
0x140030a69  mov     rax, [rsp+240h+SecurityDescriptor]
0x140030a6e  lea     rdx, ApplicationName; "fontdrvhost.exe"
0x140030a75  mov     [rbp+140h+ThreadAttributes.lpSecurityDescriptor], rax
0x140030a79  xor     r8d, r8d; lpCommandLine
0x140030a7c  lea     rax, [rbp+140h+hThread]
0x140030a80  mov     qword ptr [rbp+140h+StartupInfo+68h], r14
0x140030a87  mov     [rsp+240h+lpProcessInformation], rax; lpProcessInformation
0x140030a8c  mov     rcx, rsi; hToken
0x140030a8f  lea     rax, [rbp+140h+StartupInfo]
0x140030a93  mov     dword ptr [rbp+140h+StartupInfo+3Ch], 10000h
0x140030a9a  mov     [rsp+240h+lpStartupInfo], rax; lpStartupInfo
  ... truncated ...
```
