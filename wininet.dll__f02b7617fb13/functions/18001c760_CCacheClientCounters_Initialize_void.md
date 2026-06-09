# CCacheClientCounters::Initialize(void)

- ea: `0x18001c760`
- end: `0x18001cd61`
- name: `?Initialize@CCacheClientCounters@@AEAAJXZ`
- size: `1537`
- prototype: `__int64 __fastcall(CCacheClientCounters *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001c2b0`

## callees

- `0x18001afec`
- `0x18001c760`
- `0x18001cd68`
- `0x18001cfb8`
- `0x18001d81c`
- `0x180021cd0`
- `0x18002482c`
- `0x180025910`
- `0x1800701d0`
- `0x180118448`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x18015387c`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e5350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c94d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001c94d`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x18001ca79`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x18001ccda`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x18001ca79`
- `api-ms-win-security-appcontainer-l1-1-0!GetAppContainerNamedObjectPath` at `0x18001ccda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c98b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c98b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cabe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cabe`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageSid` at `0x18001ca32`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageSid` at `0x18001ca32`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001cd56`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001cd56`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18001ca0a`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18001ca0a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001c889`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001c8fd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001c889`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001c8fd`

## string_xrefs

- `0x18001cb48`: `Local\windows_webcache_counters_{00000000-5d8e-4eed-b3fa-e30684411323}`
- `0x18001cbcc`: `\windows_webcache_counters_{00000000-5d8e-4eed-b3fa-e30684411323}`
- `0x18001ccfa`: `Local\windows_webcache_counters_{00000000-2795-4b43-819d-cf625101d5ed}`

## pseudocode

```c
__int64 __fastcall CCacheClientCounters::Initialize(CCacheClientCounters *this)
{
  __int64 v2; // rdx
  int v3; // ecx
  int ProcessInternalIntegrityLevel; // ebx
  int v5; // r8d
  unsigned int v6; // edi
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  LONG CurrentPackageFullName; // eax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rbx
  PSID v19; // rcx
  int v20; // eax
  int LastError; // eax
  __int64 v22; // rcx
  unsigned int v23; // [rsp+40h] [rbp-C0h]
  unsigned int v24; // [rsp+50h] [rbp-B0h]
  unsigned int *v25; // [rsp+58h] [rbp-A8h]
  unsigned int LengthSid; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v30[2]; // [rsp+78h] [rbp-88h] BYREF
  PWSTR v31; // [rsp+88h] [rbp-78h] BYREF
  PWSTR ppszPath; // [rsp+90h] [rbp-70h] BYREF
  PSID pSid; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v34; // [rsp+A0h] [rbp-60h] BYREF
  struct _SID *v35; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v36[2]; // [rsp+B0h] [rbp-50h] BYREF
  UINT32 packageFullNameLength; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR packageFullName[128]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v39[400]; // [rsp+1C0h] [rbp+C0h] BYREF

  v27 = 0;
  v36[0] = 0;
  v31 = 0;
  ppszPath = 0;
  v30[0] = (unsigned __int16 *)&Data;
  v30[1] = 0;
  memset_0(v39, 0, sizeof(v39));
  pSid = 0;
  packageFullNameLength = 128;
  v28 = (unsigned __int16 *)&Data;
  v29 = 0;
  v34 = 0;
  ProcessInternalIntegrityLevel = WxGetProcessInternalIntegrityLevel(v36);
  if ( ProcessInternalIntegrityLevel < 0 )
  {
    v27 = 215;
    goto LABEL_25;
  }
  v6 = v36[0];
  LengthSid = 0;
  if ( v36[0] > 2
    && (unsigned __int8)IsGetPackageFullNamePresent()
    && (*(_QWORD *)v36 = 0,
        v35 = 0,
        AppModelPolicy_GetPolicy_Internal(-6, v2, &LengthSid, &v35, v36),
        LengthSid == 1966081) )
  {
    ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeGlobalCounters(this, 1);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v27 = 228;
      goto LABEL_25;
    }
    CurrentPackageFullName = GetCurrentPackageFullName(&packageFullNameLength, packageFullName);
    ProcessInternalIntegrityLevel = CurrentPackageFullName;
    if ( CurrentPackageFullName > 0 )
      ProcessInternalIntegrityLevel = (unsigned __int16)CurrentPackageFullName | 0x80070000;
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v27 = 233;
      goto LABEL_25;
    }
    ProcessInternalIntegrityLevel = AppXGetPackageSid(packageFullName, &pSid);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v27 = 234;
      goto LABEL_25;
    }
    ProcessInternalIntegrityLevel = CWxString::ExtendBuffer((CWxString *)&v28, 0x200u);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v27 = 235;
      goto LABEL_25;
    }
    v12 = v28;
    v13 = HIDWORD(v29);
    if ( (unsigned int)GetAppContainerNamedObjectPath(0, pSid, HIDWORD(v29), v28) )
      goto LABEL_41;
    LastError = WxGetLastError(v15, v14);
    ProcessInternalIntegrityLevel = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        ProcessInternalIntegrityLevel = (unsigned __int16)LastError | 0x80070000;
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v27 = 245;
        goto LABEL_25;
      }
    }
    ProcessInternalIntegrityLevel = CWxString::ExtendBuffer((CWxString *)&v28, v34);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v27 = 247;
      goto LABEL_25;
    }
    v12 = v28;
    v13 = HIDWORD(v29);
    v34 = 0;
    if ( (unsigned int)GetAppContainerNamedObjectPath(0, pSid, HIDWORD(v29), v28) )
    {
LABEL_41:
      if ( v12 != &Data )
      {
        v17 = v13;
        v18 = -1;
        v12[v17] = 0;
        do
          ++v18;
        while ( v12[v18] );
        LODWORD(v29) = v18;
      }
      v19 = pSid;
      v35 = (struct _SID *)pSid;
      v36[0] = -1073741824;
      LengthSid = 0;
      if ( pSid )
        LengthSid = GetLengthSid(pSid);
      ProcessInternalIntegrityLevel = ConstructSecurityDescriptorInternal(
                                        (__int64)v19,
                                        v14,
                                        v16,
                                        0,
                                        (unsigned int)&v34,
                                        &v35,
                                        &LengthSid,
                                        v36,
                                        v23,
                                        v39,
                                        v24,
                                        v25);
      if ( ProcessInternalIntegrityLevel >= 0 )
      {
        ProcessInternalIntegrityLevel = CWxString::Append(
                                          (CWxString *)v30,
                                          v12,
                                          L"\\windows_webcache_counters_{00000000-5d8e-4eed-b3fa-e30684411323}");
        if ( ProcessInternalIntegrityLevel < 0 )
        {
          v27 = 268;
        }
        else
        {
          ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeLocalCounters(this, v30[0], v39);
          if ( ProcessInternalIntegrityLevel < 0 )
            v27 = 269;
        }
      }
      else
      {
        v27 = 266;
      }
    }
    else
    {
      v20 = WxGetLastError(v22, v14);
      ProcessInternalIntegrityLevel = v20;
      if ( v20 > 0 )
        ProcessInternalIntegrityLevel = (unsigned __int16)v20 | 0x80070000;
      v27 = 253;
      if ( ProcessInternalIntegrityLevel >= 0 )
        ProcessInternalIntegrityLevel = -2147418113;
    }
  }
  else
  {
    if ( v6 >= 3 )
    {
      HIDWORD(v35) = 0;
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
        WPP_SF__guid_dq(v3, v2, v5, (unsigned int)&FOLDERID_InternetCache, 0x4000, -1);
      ProcessInternalIntegrityLevel = SHGetKnownFolderPath(
                                        &FOLDERID_InternetCache,
                                        0x4000u,
                                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                        &ppszPath);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        HIDWORD(v35) = 33;
      }
      else
      {
        if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
          goto LABEL_13;
        WPP_SF_S(1038, 11, WPP_399a03e428863a414a3dbf9528417340_Traceguids, ppszPath);
      }
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
        WPP_SF_d(1038, 12, WPP_399a03e428863a414a3dbf9528417340_Traceguids, (unsigned int)ProcessInternalIntegrityLevel);
LABEL_13:
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v27 = 305;
        goto LABEL_25;
      }
      HIDWORD(v35) = 0;
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
        WPP_SF__guid_dq(v8, v7, v9, (unsigned int)&FOLDERID_InternetCache, 0x4000, 0);
      ProcessInternalIntegrityLevel = SHGetKnownFolderPath(&FOLDERID_InternetCache, 0x4000u, 0, &v31);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        HIDWORD(v35) = 33;
      }
      else
      {
        if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
        {
LABEL_21:
          if ( ProcessInternalIntegrityLevel < 0 )
          {
            v27 = 306;
          }
          else if ( (unsigned int)_o__wcsicmp(ppszPath) )
          {
            ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeGlobalCounters(this, 0);
            if ( ProcessInternalIntegrityLevel < 0 )
              v27 = 310;
          }
          else
          {
            ProcessInternalIntegrityLevel = -2147024894;
            v27 = 308;
          }
          goto LABEL_25;
        }
        WPP_SF_S(1038, 11, WPP_399a03e428863a414a3dbf9528417340_Traceguids, v31);
      }
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
        WPP_SF_d(1038, 12, WPP_399a03e428863a414a3dbf9528417340_Traceguids, (unsigned int)ProcessInternalIntegrityLevel);
      goto LABEL_21;
    }
    ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeGlobalCounters(this, 1);
    if ( ProcessInternalIntegrityLevel >= 0 )
    {
      if ( v6 >= 2 )
      {
        ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeLocalCounters(
                                          this,
                                          L"Local\\windows_webcache_counters_{00000000-2795-4b43-819d-cf625101d5ed}",
                                          0);
        if ( ProcessInternalIntegrityLevel < 0 )
          v27 = 291;
      }
      else
      {
        ProcessInternalIntegrityLevel = CCacheClientCounters::InitializeLocalCounters(
                                          this,
                                          L"Local\\windows_webcache_counters_{00000000-5d8e-4eed-b3fa-e30684411323}",
                                          0);
        if ( ProcessInternalIntegrityLevel < 0 )
          v27 = 284;
      }
    }
    else
    {
      v27 = 277;
    }
  }
LABEL_25:
  if ( v31 )
  {
    CoTaskMemFree(v31);
    v31 = 0;
  }
  if ( ppszPath )
  {
    CoTaskMemFree(ppszPath);
    ppszPath = 0;
  }
  if ( pSid )
    AppXFreeMemory();
  if ( ProcessInternalIntegrityLevel < 0 )
    ProcessInternalIntegrityLevel = -2147012892;
  CWxString::_Release((CWxString *)&v28);
  CWxString::_Release((CWxString *)v30);
  return (unsigned int)ProcessInternalIntegrityLevel;
}

```

## disassembly

```asm
0x18001c760  mov     [rsp-8+arg_8], rbx
0x18001c765  mov     [rsp-8+arg_10], rsi
0x18001c76a  push    rbp
0x18001c76b  push    rdi
0x18001c76c  push    r12
0x18001c76e  push    r14
0x18001c770  push    r15
0x18001c772  lea     rbp, [rsp-260h]
0x18001c77a  sub     rsp, 360h
0x18001c781  mov     rax, cs:__security_cookie
0x18001c788  xor     rax, rsp
0x18001c78b  mov     [rbp+280h+var_30], rax
0x18001c792  xor     r14d, r14d
0x18001c795  lea     r12, Data
0x18001c79c  mov     rsi, rcx
0x18001c79f  mov     [rsp+380h+var_31C], r14d
0x18001c7a4  lea     rcx, [rbp+280h+var_1C0]; void *
0x18001c7ab  mov     [rbp+280h+var_2D0], r14d
0x18001c7af  xor     edx, edx; Val
0x18001c7b1  mov     [rbp+280h+var_2F8], r14
0x18001c7b5  mov     r8d, 190h; Size
0x18001c7bb  mov     [rbp+280h+ppszPath], r14
0x18001c7bf  mov     [rsp+380h+var_308], r12
0x18001c7c4  mov     [rbp+280h+var_300], r14
0x18001c7c8  call    memset_0
0x18001c7cd  lea     rcx, [rbp+280h+var_2D0]; unsigned int *
0x18001c7d1  mov     [rbp+280h+pSid], r14
0x18001c7d5  mov     [rbp+280h+packageFullNameLength], 80h
0x18001c7dc  mov     [rsp+380h+var_318], r12
0x18001c7e1  mov     [rsp+380h+var_310], r14
0x18001c7e6  mov     [rbp+280h+var_2E0], r14d
0x18001c7ea  call    ?WxGetProcessInternalIntegrityLevel@@YAJPEAK@Z; WxGetProcessInternalIntegrityLevel(ulong *)
0x18001c7ef  mov     ebx, eax
0x18001c7f1  test    eax, eax
0x18001c7f3  js      loc_18001CC65
0x18001c7f9  mov     edi, [rbp+280h+var_2D0]
0x18001c7fc  mov     [rsp+380h+var_320], r14d
0x18001c801  cmp     edi, 2
0x18001c804  jbe     short loc_18001C840
0x18001c806  call    IsGetPackageFullNamePresent
0x18001c80b  test    al, al
0x18001c80d  jz      short loc_18001C840
0x18001c80f  lea     rax, [rbp+280h+var_2D0]
0x18001c813  mov     qword ptr [rbp+280h+var_2D0], r14
0x18001c817  lea     r9, [rbp+280h+var_2D8]
0x18001c81b  mov     qword ptr [rsp+380h+var_360], rax
0x18001c820  lea     r8, [rsp+380h+var_320]
0x18001c825  mov     [rbp+280h+var_2D8], r14
0x18001c829  lea     rcx, [r14-6]
0x18001c82d  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18001c832  cmp     [rsp+380h+var_320], 1E0001h
0x18001c83a  jz      loc_18001C9EB
0x18001c840  cmp     edi, 3
0x18001c843  jb      loc_18001CB19
0x18001c849  mov     dword ptr [rbp+280h+var_2D8+4], r14d
0x18001c84d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c851  lea     r12, FOLDERID_InternetCache
0x18001c858  mov     dil, 40h ; '@'
0x18001c85b  mov     r15d, 4000h
0x18001c861  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c868  jz      short loc_18001C87C
0x18001c86a  mov     [rsp+380h+var_358], rbx
0x18001c86f  mov     r9, r12
0x18001c872  mov     [rsp+380h+var_360], r15d
0x18001c877  call    WPP_SF__guid_dq
0x18001c87c  lea     r9, [rbp+280h+ppszPath]; ppszPath
0x18001c880  mov     r8, rbx; hToken
0x18001c883  mov     edx, r15d; dwFlags
0x18001c886  mov     rcx, r12; rfid
0x18001c889  call    cs:__imp_SHGetKnownFolderPath
0x18001c88f  mov     ebx, eax
0x18001c891  test    eax, eax
0x18001c893  js      loc_18001CBA7
0x18001c899  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c8a0  jz      short loc_18001C8C9
0x18001c8a2  mov     r9, [rbp+280h+ppszPath]
0x18001c8a6  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18001c8ad  mov     edx, 0Bh
0x18001c8b2  mov     ecx, 40Eh
0x18001c8b7  call    WPP_SF_S
0x18001c8bc  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c8c3  jnz     loc_18001CB6B
0x18001c8c9  test    ebx, ebx
0x18001c8cb  js      loc_18001CD1D
0x18001c8d1  mov     dword ptr [rbp+280h+var_2D8+4], r14d
0x18001c8d5  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c8dc  jz      short loc_18001C8F0
0x18001c8de  mov     [rsp+380h+var_358], r14
0x18001c8e3  mov     r9, r12
0x18001c8e6  mov     [rsp+380h+var_360], r15d
0x18001c8eb  call    WPP_SF__guid_dq
0x18001c8f0  lea     r9, [rbp+280h+var_2F8]; ppszPath
0x18001c8f4  xor     r8d, r8d; hToken
0x18001c8f7  mov     edx, r15d; dwFlags
0x18001c8fa  mov     rcx, r12; rfid
0x18001c8fd  call    cs:__imp_SHGetKnownFolderPath
0x18001c903  mov     ebx, eax
0x18001c905  test    eax, eax
0x18001c907  js      loc_18001CBB3
0x18001c90d  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c914  jz      short loc_18001C93D
0x18001c916  mov     r9, [rbp+280h+var_2F8]
0x18001c91a  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18001c921  mov     edx, 0Bh
0x18001c926  mov     ecx, 40Eh
0x18001c92b  call    WPP_SF_S
0x18001c930  test    byte ptr cs:xmmword_180266B60+1, dil
0x18001c937  jnz     loc_18001CB89
0x18001c93d  test    ebx, ebx
0x18001c93f  js      loc_18001CD2A
0x18001c945  mov     rdx, [rbp+280h+var_2F8]
0x18001c949  mov     rcx, [rbp+280h+ppszPath]
0x18001c94d  call    cs:__imp__o__wcsicmp
0x18001c953  test    eax, eax
0x18001c955  jz      loc_18001CD37
0x18001c95b  xor     edx, edx; int
0x18001c95d  mov     rcx, rsi; this
0x18001c960  call    ?InitializeGlobalCounters@CCacheClientCounters@@AEAAJH@Z; CCacheClientCounters::InitializeGlobalCounters(int)
0x18001c965  mov     ebx, eax
0x18001c967  test    eax, eax
0x18001c969  js      loc_18001CD49
0x18001c96f  mov     rcx, [rbp+280h+var_2F8]; pv
0x18001c973  test    rcx, rcx
0x18001c976  jz      short loc_18001C982
0x18001c978  call    cs:__imp_CoTaskMemFree
0x18001c97e  mov     [rbp+280h+var_2F8], r14
0x18001c982  mov     rcx, [rbp+280h+ppszPath]; pv
0x18001c986  test    rcx, rcx
0x18001c989  jz      short loc_18001C995
0x18001c98b  call    cs:__imp_CoTaskMemFree
0x18001c991  mov     [rbp+280h+ppszPath], r14
0x18001c995  mov     rcx, [rbp+280h+pSid]
0x18001c999  test    rcx, rcx
0x18001c99c  jnz     loc_18001CD56
0x18001c9a2  test    ebx, ebx
0x18001c9a4  js      loc_18001CB0F
0x18001c9aa  lea     rcx, [rsp+380h+var_318]; this
0x18001c9af  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18001c9b4  lea     rcx, [rsp+380h+var_308]; this
0x18001c9b9  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18001c9be  mov     eax, ebx
0x18001c9c0  mov     rcx, [rbp+280h+var_30]
0x18001c9c7  xor     rcx, rsp; StackCookie
0x18001c9ca  call    __security_check_cookie
0x18001c9cf  lea     r11, [rsp+380h+var_20]
0x18001c9d7  mov     rbx, [r11+38h]
0x18001c9db  mov     rsi, [r11+40h]
0x18001c9df  mov     rsp, r11
0x18001c9e2  pop     r15
0x18001c9e4  pop     r14
0x18001c9e6  pop     r12
0x18001c9e8  pop     rdi
0x18001c9e9  pop     rbp
0x18001c9ea  retn
0x18001c9eb  mov     edx, 1; int
0x18001c9f0  mov     rcx, rsi; this
0x18001c9f3  call    ?InitializeGlobalCounters@CCacheClientCounters@@AEAAJH@Z; CCacheClientCounters::InitializeGlobalCounters(int)
0x18001c9f8  mov     ebx, eax
0x18001c9fa  test    eax, eax
0x18001c9fc  js      loc_18001CBBF
0x18001ca02  lea     rdx, [rbp+280h+packageFullName]; packageFullName
0x18001ca06  lea     rcx, [rbp+280h+packageFullNameLength]; packageFullNameLength
0x18001ca0a  call    cs:__imp_GetCurrentPackageFullName
0x18001ca10  mov     ebx, eax
0x18001ca12  mov     r15d, 80070000h
0x18001ca18  test    eax, eax
0x18001ca1a  jle     short loc_18001CA22
0x18001ca1c  movzx   ebx, ax
0x18001ca1f  or      ebx, r15d
0x18001ca22  test    ebx, ebx
0x18001ca24  js      loc_18001CC72
0x18001ca2a  lea     rdx, [rbp+280h+pSid]
0x18001ca2e  lea     rcx, [rbp+280h+packageFullName]
0x18001ca32  call    cs:__imp_AppXGetPackageSid
0x18001ca38  mov     ebx, eax
0x18001ca3a  test    eax, eax
0x18001ca3c  js      loc_18001CC15
0x18001ca42  mov     edx, 200h; unsigned int
0x18001ca47  lea     rcx, [rsp+380h+var_318]; this
0x18001ca4c  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x18001ca51  mov     ebx, eax
0x18001ca53  test    eax, eax
0x18001ca55  js      loc_18001CC7F
0x18001ca5b  mov     rdi, [rsp+380h+var_318]
0x18001ca60  lea     rax, [rbp+280h+var_2E0]
0x18001ca64  mov     ebx, dword ptr [rsp+380h+var_310+4]
0x18001ca68  mov     r9, rdi
0x18001ca6b  mov     rdx, [rbp+280h+pSid]
0x18001ca6f  mov     r8d, ebx
0x18001ca72  xor     ecx, ecx
0x18001ca74  mov     qword ptr [rsp+380h+var_360], rax; unsigned int
0x18001ca79  call    cs:__imp_GetAppContainerNamedObjectPath
0x18001ca7f  test    eax, eax
0x18001ca81  jz      loc_18001CC8C
0x18001ca87  cmp     rdi, r12
0x18001ca8a  jz      short loc_18001CAA5
0x18001ca8c  mov     ecx, ebx
0x18001ca8e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ca92  mov     [rdi+rcx*2], r14w
0x18001ca97  inc     rbx
0x18001ca9a  cmp     [rdi+rbx*2], r14w
0x18001ca9f  jnz     short loc_18001CA97
0x18001caa1  mov     dword ptr [rsp+380h+var_310], ebx
0x18001caa5  mov     rcx, [rbp+280h+pSid]; pSid
0x18001caa9  mov     [rbp+280h+var_2D8], rcx
0x18001caad  mov     [rbp+280h+var_2D0], 0C0000000h
0x18001cab4  mov     [rsp+380h+var_320], r14d
0x18001cab9  test    rcx, rcx
0x18001cabc  jz      short loc_18001CAC8
0x18001cabe  call    cs:__imp_GetLengthSid
0x18001cac4  mov     [rsp+380h+var_320], eax
0x18001cac8  lea     rax, [rbp+280h+var_1C0]
0x18001cacf  xor     r9d, r9d; unsigned int
0x18001cad2  mov     [rsp+380h+var_338], rax; unsigned __int8 *
0x18001cad7  lea     rax, [rbp+280h+var_2D0]
0x18001cadb  mov     [rsp+380h+var_348], rax; unsigned int *
0x18001cae0  lea     rax, [rsp+380h+var_320]
0x18001cae5  mov     [rsp+380h+var_350], rax; unsigned int *
0x18001caea  lea     rax, [rbp+280h+var_2D8]
0x18001caee  mov     [rsp+380h+var_358], rax; struct _SID **
0x18001caf3  call    ?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z; ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)
0x18001caf8  mov     ebx, eax
0x18001cafa  test    eax, eax
0x18001cafc  jns     loc_18001CBCC
0x18001cb02  mov     [rsp+380h+var_31C], 10Ah
0x18001cb0a  jmp     loc_18001C96F
0x18001cb0f  mov     ebx, 80072EE4h
0x18001cb14  jmp     loc_18001C9AA
0x18001cb19  mov     edx, 1; int
0x18001cb1e  mov     rcx, rsi; this
0x18001cb21  call    ?InitializeGlobalCounters@CCacheClientCounters@@AEAAJH@Z; CCacheClientCounters::InitializeGlobalCounters(int)
0x18001cb26  mov     ebx, eax
0x18001cb28  test    eax, eax
0x18001cb2a  jns     short loc_18001CB39
0x18001cb2c  mov     [rsp+380h+var_31C], 115h
0x18001cb34  jmp     loc_18001C96F
0x18001cb39  xor     r8d, r8d; unsigned __int8 *
0x18001cb3c  mov     rcx, rsi; this
0x18001cb3f  cmp     edi, 2
0x18001cb42  jnb     loc_18001CCFA
0x18001cb48  lea     rdx, aLocalWindowsWe; "Local\\windows_webcache_counters_{00000"...
0x18001cb4f  call    ?InitializeLocalCounters@CCacheClientCounters@@AEAAJPEBGPEAE@Z; CCacheClientCounters::InitializeLocalCounters(ushort const *,uchar *)
0x18001cb54  mov     ebx, eax
0x18001cb56  test    eax, eax
0x18001cb58  jns     loc_18001C96F
0x18001cb5e  mov     [rsp+380h+var_31C], 11Ch
0x18001cb66  jmp     loc_18001C96F
0x18001cb6b  mov     edx, 0Ch
0x18001cb70  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18001cb77  mov     ecx, 40Eh
0x18001cb7c  mov     r9d, ebx
0x18001cb7f  call    WPP_SF_d
0x18001cb84  jmp     loc_18001C8C9
0x18001cb89  mov     edx, 0Ch
0x18001cb8e  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18001cb95  mov     ecx, 40Eh
0x18001cb9a  mov     r9d, ebx
0x18001cb9d  call    WPP_SF_d
0x18001cba2  jmp     loc_18001C93D
0x18001cba7  mov     dword ptr [rbp+280h+var_2D8+4], 21h ; '!'
0x18001cbae  jmp     loc_18001C8BC
0x18001cbb3  mov     dword ptr [rbp+280h+var_2D8+4], 21h ; '!'
0x18001cbba  jmp     loc_18001C930
0x18001cbbf  mov     [rsp+380h+var_31C], 0E4h
0x18001cbc7  jmp     loc_18001C96F
0x18001cbcc  lea     r8, aWindowsWebcach; "\\windows_webcache_counters_{00000000-5"...
0x18001cbd3  mov     rdx, rdi; unsigned __int16 *
0x18001cbd6  lea     rcx, [rsp+380h+var_308]; this
0x18001cbdb  call    ?Append@CWxString@@QEAAJPEBG0@Z; CWxString::Append(ushort const *,ushort const *)
0x18001cbe0  mov     ebx, eax
0x18001cbe2  test    eax, eax
0x18001cbe4  js      loc_18001CCED
0x18001cbea  mov     rdx, [rsp+380h+var_308]; unsigned __int16 *
0x18001cbef  lea     r8, [rbp+280h+var_1C0]; unsigned __int8 *
0x18001cbf6  mov     rcx, rsi; this
0x18001cbf9  call    ?InitializeLocalCounters@CCacheClientCounters@@AEAAJPEBGPEAE@Z; CCacheClientCounters::InitializeLocalCounters(ushort const *,uchar *)
0x18001cbfe  mov     ebx, eax
0x18001cc00  test    eax, eax
0x18001cc02  jns     loc_18001C96F
0x18001cc08  mov     [rsp+380h+var_31C], 10Dh
0x18001cc10  jmp     loc_18001C96F
0x18001cc15  mov     [rsp+380h+var_31C], 0EAh
0x18001cc1d  jmp     loc_18001C96F
0x18001cc22  test    eax, eax
0x18001cc24  jle     short loc_18001CC2C
0x18001cc26  movzx   ebx, ax
0x18001cc29  or      ebx, r15d
0x18001cc2c  test    ebx, ebx
0x18001cc2e  jns     short loc_18001CC98
0x18001cc30  mov     [rsp+380h+var_31C], 0F5h
0x18001cc38  jmp     loc_18001C96F
0x18001cc3d  call    WxGetLastError
0x18001cc42  mov     ebx, eax
0x18001cc44  test    eax, eax
0x18001cc46  jle     short loc_18001CC4E
0x18001cc48  movzx   ebx, ax
0x18001cc4b  or      ebx, r15d
0x18001cc4e  test    ebx, ebx
0x18001cc50  mov     [rsp+380h+var_31C], 0FDh
0x18001cc58  mov     eax, 8000FFFFh
  ... truncated ...
```
