# CCacheClientConfig::Initialize(void)

- ea: `0x1800a6ed4`
- end: `0x1800a7480`
- name: `?Initialize@CCacheClientConfig@@AEAAJXZ`
- size: `1452`
- prototype: `__int64 __fastcall(CCacheClientConfig *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a6df0`

## callees

- `0x18001bce8`
- `0x18001cfb8`
- `0x18002086c`
- `0x180025514`
- `0x180025910`
- `0x180044a44`
- `0x180046a1c`
- `0x1800a6ed4`
- `0x1800a74e8`
- `0x1800a7e28`
- `0x1800a8448`
- `0x1800a85a8`
- `0x1800a8bec`
- `0x1800c14f4`
- `0x18014a7a0`
- `0x1801dbe18`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7425`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a744c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7425`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a744c`
- `iertutil!__imp_GetKeyPath` at `0x1800a6fe5`
- `iertutil!__imp_GetKeyPath` at `0x1800a7005`
- `iertutil!__imp_GetKeyPath` at `0x1800a6fe5`
- `iertutil!__imp_GetKeyPath` at `0x1800a7005`

## string_xrefs

- `0x1800a70bc`: `Internet Settings\Cache\Extensible Cache`
- `0x1800a71d0`: `Internet Settings\Cache\Extensible Cache`
- `0x1800a7140`: `Extensible Cache`
- `0x1800a7196`: `Internet Settings\Cache`

## pseudocode

```c
__int64 __fastcall CCacheClientConfig::Initialize(CCacheClientConfig *this)
{
  int v1; // edi
  int ProcessInternalIntegrityLevel; // ebx
  unsigned int v4; // r12d
  DWORD v5; // r14d
  __int64 v6; // rdx
  unsigned int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  unsigned __int16 v11; // dx
  unsigned __int16 v12; // dx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh]
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR ppszPath; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY v22; // [rsp+80h] [rbp-80h] BYREF
  HKEY v23; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v24[264]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[10]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR SubKey[259]; // [rsp+2AAh] [rbp+1AAh] BYREF

  v1 = 1966080;
  v15 = 0;
  v16 = 0;
  v23 = 0;
  v22 = 0;
  hKey = 0;
  ppszPath = 0;
  v18[0] = &Data;
  v18[1] = 0;
  v19[0] = &Data;
  v19[1] = 0;
  v17[0] = &Data;
  v17[1] = 0;
  v14 = 1966080;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 10, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids);
  ProcessInternalIntegrityLevel = WxGetProcessInternalIntegrityLevel(&v16);
  if ( ProcessInternalIntegrityLevel < 0 )
  {
    v15 = 306;
    goto LABEL_59;
  }
  v4 = v16;
  v5 = 0x4000;
  if ( v16 == 1 )
  {
    ProcessInternalIntegrityLevel = GetAppContainerRegistryLocation(0x104u, &hKey);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v15 = 314;
      goto LABEL_59;
    }
    ProcessInternalIntegrityLevel = WxOpenRegistryKey(hKey, L"Internet Settings\\Cache", 0xFu, 1, &v23);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v15 = 315;
      goto LABEL_59;
    }
    ProcessInternalIntegrityLevel = WxOpenRegistryKey(
                                      hKey,
                                      L"Internet Settings\\Cache\\Extensible Cache",
                                      0xFu,
                                      1,
                                      &v22);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v15 = 316;
      goto LABEL_59;
    }
    goto LABEL_25;
  }
  if ( v16 - 2 < 2 )
  {
    if ( v16 == 2 )
    {
      ProcessInternalIntegrityLevel = GetKeyPath(IEKEY_GUID_wininet_LowCache, 2, v25, 260);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 327;
        goto LABEL_59;
      }
    }
    else
    {
      ProcessInternalIntegrityLevel = GetKeyPath(IEKEY_GUID_wininet_Cache, 2, v25, 260);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 334;
        goto LABEL_59;
      }
      ProcessInternalIntegrityLevel = AppModelPolicy_GetPolicy(-6, v6, &v14);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 336;
        goto LABEL_59;
      }
      v1 = v14;
    }
    ProcessInternalIntegrityLevel = WxOpenRegistryKey(HKEY_CURRENT_USER, SubKey, 0xFu, 1, &v23);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v15 = 345;
      goto LABEL_59;
    }
    if ( v1 == 1966081 )
    {
      ProcessInternalIntegrityLevel = GetAppContainerRegistryLocation(v7, &hKey);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 349;
        goto LABEL_59;
      }
      ProcessInternalIntegrityLevel = WxOpenRegistryKey(
                                        hKey,
                                        L"Internet Settings\\Cache\\Extensible Cache",
                                        0xFu,
                                        1,
                                        &v22);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 350;
        goto LABEL_59;
      }
      if ( !GlobalKirWinInetFixAppContainerPath )
        goto LABEL_38;
      v5 = 147456;
    }
    else
    {
      ProcessInternalIntegrityLevel = WxOpenRegistryKey(v23, L"Extensible Cache", 0xFu, 1, &v22);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 366;
        goto LABEL_59;
      }
    }
LABEL_25:
    if ( GlobalKirWinInetFixAppContainerPath )
    {
      ProcessInternalIntegrityLevel = GetKnownFolderPath((KNOWNFOLDERID *)&FOLDERID_LocalAppData, v5, 0, &ppszPath);
      if ( ProcessInternalIntegrityLevel < 0 )
      {
        v15 = 386;
        goto LABEL_59;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_DS(v9, v8, v10, v5, (__int64)ppszPath);
      goto LABEL_42;
    }
LABEL_38:
    ProcessInternalIntegrityLevel = GetKnownFolderPath((KNOWNFOLDERID *)&FOLDERID_LocalAppData, 0x4000u, 0, &ppszPath);
    if ( ProcessInternalIntegrityLevel < 0 )
    {
      v15 = 399;
      goto LABEL_59;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_S(1036, 12, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids, ppszPath);
LABEL_42:
    ProcessInternalIntegrityLevel = CWxString::Set((CWxString *)v18, ppszPath);
    if ( ProcessInternalIntegrityLevel >= 0 )
    {
      ProcessInternalIntegrityLevel = CWxString::Trailing((CWxString *)v18, v11);
      if ( ProcessInternalIntegrityLevel >= 0 )
      {
        ProcessInternalIntegrityLevel = CCacheClientConfig::_GetContentContainerDirectory(v4, (struct CWxString *)v19);
        if ( ProcessInternalIntegrityLevel >= 0 )
        {
          ProcessInternalIntegrityLevel = GetBrowserProfileDataFilePathWrapper(1, v24, 260);
          if ( ProcessInternalIntegrityLevel >= 0 )
          {
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_S(1036, 13, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids, v24);
            ProcessInternalIntegrityLevel = WxValidateCacheDirectory(v24);
            if ( ProcessInternalIntegrityLevel >= 0 )
            {
              ProcessInternalIntegrityLevel = CWxString::Set((CWxString *)v17, v24);
              if ( ProcessInternalIntegrityLevel >= 0 )
              {
                ProcessInternalIntegrityLevel = CWxString::Trailing((CWxString *)v17, v12);
                if ( ProcessInternalIntegrityLevel >= 0 )
                {
                  CWxString::Transfer((CWxString *)v18, (CCacheClientConfig *)((char *)this + 32));
                  CWxString::Transfer((CWxString *)v19, (CCacheClientConfig *)((char *)this + 48));
                  CWxString::Transfer((CWxString *)v17, (CCacheClientConfig *)((char *)this + 64));
                  *((_QWORD *)this + 1) = v23;
                  *((_QWORD *)this + 2) = v22;
                  v23 = 0;
                  v22 = 0;
                  *(_DWORD *)this = v4;
                }
                else
                {
                  v15 = 423;
                }
              }
              else
              {
                v15 = 422;
              }
            }
            else
            {
              v15 = 421;
            }
          }
          else
          {
            v15 = 414;
          }
        }
        else
        {
          v15 = 410;
        }
      }
      else
      {
        v15 = 408;
      }
    }
    else
    {
      v15 = 407;
    }
LABEL_59:
    if ( ProcessInternalIntegrityLevel >= 0 )
      goto LABEL_63;
    goto LABEL_60;
  }
  ProcessInternalIntegrityLevel = -2147418113;
  v15 = 373;
LABEL_60:
  if ( (BYTE1(xmmword_180266B50) & 0x10) != 0 )
    WPP_SF_d(524, 14, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids, (unsigned int)ProcessInternalIntegrityLevel);
  ProcessInternalIntegrityLevel = -2147012892;
LABEL_63:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 15, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids, (unsigned int)ProcessInternalIntegrityLevel);
  CWxString::_Release((CWxString *)v17);
  CWxString::_Release((CWxString *)v19);
  CWxString::_Release((CWxString *)v18);
  if ( ppszPath )
    WxCoTaskAllocator::Free((void **)&ppszPath);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v22 )
  {
    RegCloseKey(v22);
    v22 = 0;
  }
  if ( v23 )
    RegCloseKey(v23);
  return (unsigned int)ProcessInternalIntegrityLevel;
}

```

## disassembly

```asm
0x1800a6ed4  mov     [rsp-8+arg_8], rbx
0x1800a6ed9  mov     [rsp-8+arg_10], rdi
0x1800a6ede  push    rbp
0x1800a6edf  push    r12
0x1800a6ee1  push    r13
0x1800a6ee3  push    r14
0x1800a6ee5  push    r15
0x1800a6ee7  lea     rbp, [rsp-3C0h]
0x1800a6eef  sub     rsp, 4C0h
0x1800a6ef6  mov     rax, cs:__security_cookie
0x1800a6efd  xor     rax, rsp
0x1800a6f00  mov     [rbp+3E0h+var_30], rax
0x1800a6f07  xor     r13d, r13d
0x1800a6f0a  lea     rax, Data
0x1800a6f11  mov     edi, 1E0000h
0x1800a6f16  mov     [rsp+4E0h+var_4AC], r13d
0x1800a6f1b  mov     [rsp+4E0h+var_4A8], r13d
0x1800a6f20  mov     r15, rcx
0x1800a6f23  mov     [rbp+3E0h+var_458], r13
0x1800a6f27  mov     [rbp+3E0h+var_460], r13
0x1800a6f2b  mov     [rsp+4E0h+hKey], r13
0x1800a6f30  mov     [rsp+4E0h+ppszPath], r13
0x1800a6f35  mov     [rsp+4E0h+var_490], rax
0x1800a6f3a  mov     [rsp+4E0h+var_488], r13
0x1800a6f3f  mov     [rsp+4E0h+var_480], rax
0x1800a6f44  mov     [rsp+4E0h+var_478], r13
0x1800a6f49  mov     [rsp+4E0h+var_4A0], rax
0x1800a6f4e  mov     [rsp+4E0h+var_498], r13
0x1800a6f53  mov     [rsp+4E0h+var_4B0], edi
0x1800a6f57  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800a6f5e  jz      short loc_1800A6F75
0x1800a6f60  lea     edx, [r13+0Ah]
0x1800a6f64  mov     ecx, 40Ch
0x1800a6f69  lea     r8, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids
0x1800a6f70  call    WPP_SF_
0x1800a6f75  lea     rcx, [rsp+4E0h+var_4A8]; unsigned int *
0x1800a6f7a  call    ?WxGetProcessInternalIntegrityLevel@@YAJPEAK@Z; WxGetProcessInternalIntegrityLevel(ulong *)
0x1800a6f7f  mov     ebx, eax
0x1800a6f81  test    eax, eax
0x1800a6f83  jns     short loc_1800A6F92
0x1800a6f85  mov     [rsp+4E0h+var_4AC], 132h
0x1800a6f8d  jmp     loc_1800A739F
0x1800a6f92  mov     r12d, [rsp+4E0h+var_4A8]
0x1800a6f97  mov     r14d, 4000h
0x1800a6f9d  mov     eax, r12d
0x1800a6fa0  mov     ecx, 104h; unsigned int
0x1800a6fa5  sub     eax, 1
0x1800a6fa8  jz      loc_1800A7163
0x1800a6fae  sub     eax, 1
0x1800a6fb1  jz      short loc_1800A6FCA
0x1800a6fb3  cmp     eax, 1
0x1800a6fb6  jz      short loc_1800A6FCA
0x1800a6fb8  mov     ebx, 8000FFFFh
0x1800a6fbd  mov     [rsp+4E0h+var_4AC], 175h
0x1800a6fc5  jmp     loc_1800A73A3
0x1800a6fca  mov     edx, 2
0x1800a6fcf  lea     r8, [rbp+3E0h+var_240]
0x1800a6fd6  mov     r9d, ecx
0x1800a6fd9  cmp     r12d, edx
0x1800a6fdc  jnz     short loc_1800A6FFE
0x1800a6fde  lea     rcx, IEKEY_GUID_wininet_LowCache
0x1800a6fe5  call    cs:__imp_GetKeyPath
0x1800a6feb  mov     ebx, eax
0x1800a6fed  test    eax, eax
0x1800a6fef  jns     short loc_1800A7046
0x1800a6ff1  mov     [rsp+4E0h+var_4AC], 147h
0x1800a6ff9  jmp     loc_1800A739F
0x1800a6ffe  lea     rcx, IEKEY_GUID_wininet_Cache
0x1800a7005  call    cs:__imp_GetKeyPath
0x1800a700b  mov     ebx, eax
0x1800a700d  test    eax, eax
0x1800a700f  jns     short loc_1800A701E
0x1800a7011  mov     [rsp+4E0h+var_4AC], 14Eh
0x1800a7019  jmp     loc_1800A739F
0x1800a701e  lea     r8, [rsp+4E0h+var_4B0]
0x1800a7023  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800a702a  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x1800a702f  mov     ebx, eax
0x1800a7031  test    eax, eax
0x1800a7033  jns     short loc_1800A7042
0x1800a7035  mov     [rsp+4E0h+var_4AC], 150h
0x1800a703d  jmp     loc_1800A739F
0x1800a7042  mov     edi, [rsp+4E0h+var_4B0]
0x1800a7046  mov     r9d, 1; int
0x1800a704c  lea     rax, [rbp+3E0h+var_458]
0x1800a7050  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x1800a7057  mov     [rsp+4E0h+var_4C0], rax; HKEY *
0x1800a705c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800a7063  lea     r8d, [r9+0Eh]; samDesired
0x1800a7067  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800a706c  mov     ebx, eax
0x1800a706e  test    eax, eax
0x1800a7070  jns     short loc_1800A707F
0x1800a7072  mov     [rsp+4E0h+var_4AC], 159h
0x1800a707a  jmp     loc_1800A739F
0x1800a707f  cmp     edi, 1E0001h
0x1800a7085  jnz     loc_1800A712D
0x1800a708b  lea     rdx, [rsp+4E0h+hKey]; HKEY *
0x1800a7090  call    ?GetAppContainerRegistryLocation@@YAJKPEAPEAUHKEY__@@@Z; GetAppContainerRegistryLocation(ulong,HKEY__ * *)
0x1800a7095  mov     ebx, eax
0x1800a7097  test    eax, eax
0x1800a7099  jns     short loc_1800A70A8
0x1800a709b  mov     [rsp+4E0h+var_4AC], 15Dh
0x1800a70a3  jmp     loc_1800A739F
0x1800a70a8  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800a70ad  lea     rax, [rbp+3E0h+var_460]
0x1800a70b1  mov     r9d, 1; int
0x1800a70b7  mov     [rsp+4E0h+var_4C0], rax; HKEY *
0x1800a70bc  lea     rdx, aInternetSettin; "Internet Settings\\Cache\\Extensible Ca"...
0x1800a70c3  lea     r8d, [r9+0Eh]; samDesired
0x1800a70c7  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800a70cc  mov     ebx, eax
0x1800a70ce  test    eax, eax
0x1800a70d0  jns     short loc_1800A70DF
0x1800a70d2  mov     [rsp+4E0h+var_4AC], 15Eh
0x1800a70da  jmp     loc_1800A739F
0x1800a70df  cmp     cs:GlobalKirWinInetFixAppContainerPath, r13d
0x1800a70e6  jz      loc_1800A7210
0x1800a70ec  mov     r14d, 24000h
0x1800a70f2  cmp     cs:GlobalKirWinInetFixAppContainerPath, r13d
0x1800a70f9  jz      loc_1800A7210
0x1800a70ff  lea     r9, [rsp+4E0h+ppszPath]; ppszPath
0x1800a7104  xor     r8d, r8d; hToken
0x1800a7107  mov     edx, r14d; dwFlags
0x1800a710a  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800a7111  call    ?GetKnownFolderPath@@YAJAEBU_GUID@@KPEAXPEAPEAG@Z; GetKnownFolderPath(_GUID const &,ulong,void *,ushort * *)
0x1800a7116  mov     ebx, eax
0x1800a7118  test    eax, eax
0x1800a711a  jns     loc_1800A71F3
0x1800a7120  mov     [rsp+4E0h+var_4AC], 182h
0x1800a7128  jmp     loc_1800A739F
0x1800a712d  mov     rcx, [rbp+3E0h+var_458]; hKey
0x1800a7131  lea     rax, [rbp+3E0h+var_460]
0x1800a7135  mov     r9d, 1; int
0x1800a713b  mov     [rsp+4E0h+var_4C0], rax; HKEY *
0x1800a7140  lea     rdx, aExtensibleCach; "Extensible Cache"
0x1800a7147  lea     r8d, [r9+0Eh]; samDesired
0x1800a714b  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800a7150  mov     ebx, eax
0x1800a7152  test    eax, eax
0x1800a7154  jns     short loc_1800A70F2
0x1800a7156  mov     [rsp+4E0h+var_4AC], 16Eh
0x1800a715e  jmp     loc_1800A739F
0x1800a7163  lea     rdx, [rsp+4E0h+hKey]; HKEY *
0x1800a7168  call    ?GetAppContainerRegistryLocation@@YAJKPEAPEAUHKEY__@@@Z; GetAppContainerRegistryLocation(ulong,HKEY__ * *)
0x1800a716d  mov     ebx, eax
0x1800a716f  test    eax, eax
0x1800a7171  jns     short loc_1800A7180
0x1800a7173  mov     [rsp+4E0h+var_4AC], 13Ah
0x1800a717b  jmp     loc_1800A739F
0x1800a7180  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800a7185  lea     rax, [rbp+3E0h+var_458]
0x1800a7189  mov     edi, 0Fh
0x1800a718e  mov     [rsp+4E0h+var_4C0], rax; HKEY *
0x1800a7193  mov     r8d, edi; samDesired
0x1800a7196  lea     rdx, aInternetSettin_0; "Internet Settings\\Cache"
0x1800a719d  lea     r9d, [rdi-0Eh]; int
0x1800a71a1  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800a71a6  mov     ebx, eax
0x1800a71a8  test    eax, eax
0x1800a71aa  jns     short loc_1800A71B9
0x1800a71ac  mov     [rsp+4E0h+var_4AC], 13Bh
0x1800a71b4  jmp     loc_1800A739F
0x1800a71b9  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800a71be  lea     rax, [rbp+3E0h+var_460]
0x1800a71c2  mov     r9d, 1; int
0x1800a71c8  mov     [rsp+4E0h+var_4C0], rax; HKEY *
0x1800a71cd  mov     r8d, edi; samDesired
0x1800a71d0  lea     rdx, aInternetSettin; "Internet Settings\\Cache\\Extensible Ca"...
0x1800a71d7  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800a71dc  mov     ebx, eax
0x1800a71de  test    eax, eax
0x1800a71e0  jns     loc_1800A70F2
0x1800a71e6  mov     [rsp+4E0h+var_4AC], 13Ch
0x1800a71ee  jmp     loc_1800A739F
0x1800a71f3  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800a71fa  jz      short loc_1800A7260
0x1800a71fc  mov     rax, [rsp+4E0h+ppszPath]
0x1800a7201  mov     r9d, r14d
0x1800a7204  mov     [rsp+4E0h+var_4C0], rax
0x1800a7209  call    WPP_SF_DS
0x1800a720e  jmp     short loc_1800A7260
0x1800a7210  lea     r9, [rsp+4E0h+ppszPath]; ppszPath
0x1800a7215  xor     r8d, r8d; hToken
0x1800a7218  mov     edx, 4000h; dwFlags
0x1800a721d  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800a7224  call    ?GetKnownFolderPath@@YAJAEBU_GUID@@KPEAXPEAPEAG@Z; GetKnownFolderPath(_GUID const &,ulong,void *,ushort * *)
0x1800a7229  mov     ebx, eax
0x1800a722b  test    eax, eax
0x1800a722d  jns     short loc_1800A723C
0x1800a722f  mov     [rsp+4E0h+var_4AC], 18Fh
0x1800a7237  jmp     loc_1800A739F
0x1800a723c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800a7243  jz      short loc_1800A7260
0x1800a7245  mov     r9, [rsp+4E0h+ppszPath]
0x1800a724a  lea     r8, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids
0x1800a7251  mov     edx, 0Ch
0x1800a7256  mov     ecx, 40Ch
0x1800a725b  call    WPP_SF_S
0x1800a7260  mov     rdx, [rsp+4E0h+ppszPath]; unsigned __int16 *
0x1800a7265  lea     rcx, [rsp+4E0h+var_490]; this
0x1800a726a  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800a726f  mov     ebx, eax
0x1800a7271  test    eax, eax
0x1800a7273  jns     short loc_1800A7282
0x1800a7275  mov     [rsp+4E0h+var_4AC], 197h
0x1800a727d  jmp     loc_1800A739F
0x1800a7282  lea     rcx, [rsp+4E0h+var_490]; this
0x1800a7287  call    ?Trailing@CWxString@@QEAAJG@Z; CWxString::Trailing(ushort)
0x1800a728c  mov     ebx, eax
0x1800a728e  test    eax, eax
0x1800a7290  jns     short loc_1800A729F
0x1800a7292  mov     [rsp+4E0h+var_4AC], 198h
0x1800a729a  jmp     loc_1800A739F
0x1800a729f  lea     rdx, [rsp+4E0h+var_480]; this
0x1800a72a4  mov     ecx, r12d; unsigned int
0x1800a72a7  call    ?_GetContentContainerDirectory@CCacheClientConfig@@CAJKPEAVCWxString@@@Z; CCacheClientConfig::_GetContentContainerDirectory(ulong,CWxString *)
0x1800a72ac  mov     ebx, eax
0x1800a72ae  test    eax, eax
0x1800a72b0  jns     short loc_1800A72BF
0x1800a72b2  mov     [rsp+4E0h+var_4AC], 19Ah
0x1800a72ba  jmp     loc_1800A739F
0x1800a72bf  mov     r8d, 104h
0x1800a72c5  lea     rdx, [rbp+3E0h+var_450]
0x1800a72c9  mov     ecx, 1
0x1800a72ce  call    ?GetBrowserProfileDataFilePathWrapper@@YAJW4BROWSERPROFILEDATA_FILEPATHID@@PEAGK@Z; GetBrowserProfileDataFilePathWrapper(BROWSERPROFILEDATA_FILEPATHID,ushort *,ulong)
0x1800a72d3  mov     ebx, eax
0x1800a72d5  test    eax, eax
0x1800a72d7  jns     short loc_1800A72E6
0x1800a72d9  mov     [rsp+4E0h+var_4AC], 19Eh
0x1800a72e1  jmp     loc_1800A739F
0x1800a72e6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800a72ed  jz      short loc_1800A7309
0x1800a72ef  mov     edx, 0Dh
0x1800a72f4  lea     r9, [rbp+3E0h+var_450]
0x1800a72f8  mov     ecx, 40Ch
0x1800a72fd  lea     r8, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids
0x1800a7304  call    WPP_SF_S
0x1800a7309  lea     rcx, [rbp+3E0h+var_450]; unsigned __int16 *
0x1800a730d  call    ?WxValidateCacheDirectory@@YAJPEBG@Z; WxValidateCacheDirectory(ushort const *)
0x1800a7312  mov     ebx, eax
0x1800a7314  test    eax, eax
0x1800a7316  jns     short loc_1800A7322
0x1800a7318  mov     [rsp+4E0h+var_4AC], 1A5h
0x1800a7320  jmp     short loc_1800A739F
0x1800a7322  lea     rdx, [rbp+3E0h+var_450]; unsigned __int16 *
0x1800a7326  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800a732b  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800a7330  mov     ebx, eax
0x1800a7332  test    eax, eax
0x1800a7334  jns     short loc_1800A7340
0x1800a7336  mov     [rsp+4E0h+var_4AC], 1A6h
0x1800a733e  jmp     short loc_1800A739F
0x1800a7340  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800a7345  call    ?Trailing@CWxString@@QEAAJG@Z; CWxString::Trailing(ushort)
0x1800a734a  mov     ebx, eax
0x1800a734c  test    eax, eax
0x1800a734e  jns     short loc_1800A735A
0x1800a7350  mov     [rsp+4E0h+var_4AC], 1A7h
0x1800a7358  jmp     short loc_1800A739F
0x1800a735a  lea     rdx, [r15+20h]; struct CWxString *
0x1800a735e  lea     rcx, [rsp+4E0h+var_490]; this
0x1800a7363  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1800a7368  lea     rdx, [r15+30h]; struct CWxString *
0x1800a736c  lea     rcx, [rsp+4E0h+var_480]; this
0x1800a7371  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1800a7376  lea     rdx, [r15+40h]; struct CWxString *
0x1800a737a  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800a737f  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1800a7384  mov     rax, [rbp+3E0h+var_458]
0x1800a7388  mov     [r15+8], rax
0x1800a738c  mov     rax, [rbp+3E0h+var_460]
0x1800a7390  mov     [r15+10h], rax
0x1800a7394  mov     [rbp+3E0h+var_458], r13
0x1800a7398  mov     [rbp+3E0h+var_460], r13
0x1800a739c  mov     [r15], r12d
0x1800a739f  test    ebx, ebx
0x1800a73a1  jns     short loc_1800A73CA
0x1800a73a3  test    byte ptr cs:xmmword_180266B50+1, 10h
0x1800a73aa  jz      short loc_1800A73C5
0x1800a73ac  mov     edx, 0Eh
0x1800a73b1  lea     r8, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids
0x1800a73b8  mov     ecx, 20Ch
0x1800a73bd  mov     r9d, ebx
0x1800a73c0  call    WPP_SF_d
0x1800a73c5  mov     ebx, 80072EE4h
0x1800a73ca  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800a73d1  jz      short loc_1800A73EC
0x1800a73d3  mov     edx, 0Fh
0x1800a73d8  lea     r8, WPP_2bb46e6c2a343fe28d0e2d53551cba08_Traceguids
0x1800a73df  mov     ecx, 40Ch
0x1800a73e4  mov     r9d, ebx
0x1800a73e7  call    WPP_SF_d
0x1800a73ec  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800a73f1  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800a73f6  lea     rcx, [rsp+4E0h+var_480]; this
0x1800a73fb  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800a7400  lea     rcx, [rsp+4E0h+var_490]; this
0x1800a7405  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800a740a  cmp     [rsp+4E0h+ppszPath], r13
  ... truncated ...
```
