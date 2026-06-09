# VmbusPipeClientEnumeratePipesInternal(_GUID const *,void *,void (*)(void *,uchar *,_VMBUS_PIPE_CHANNEL_INFO *,_GUID const *),bool *)

- ea: `0x180006718`
- end: `0x180006a08`
- name: `?VmbusPipeClientEnumeratePipesInternal@@YAJPEBU_GUID@@PEAXP6AX1PEAEPEAU_VMBUS_PIPE_CHANNEL_INFO@@0@ZPEA_N@Z`
- size: `752`
- prototype: `__int64 __fastcall(const struct _GUID *, void *, void (*)(void *, unsigned __int8 *, struct _VMBUS_PIPE_CHANNEL_INFO *, const struct _GUID *), bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000526c`
- `0x180007110`

## callees

- `0x180001b44`
- `0x180001f64`
- `0x1800024e0`
- `0x1800030ae`
- `0x180003ff0`
- `0x180004034`
- `0x1800048b0`
- `0x180005d94`
- `0x180006718`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697c`
- `DEVOBJ!DevObjGetClassDevs` at `0x180006797`
- `DEVOBJ!DevObjGetClassDevs` at `0x180006797`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000689a`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18000689a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180006765`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180006765`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180006833`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180006833`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800067d4`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800067d4`

## string_xrefs

- `0x18000692d`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x180006960`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x1800069a8`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`
- `0x1800069c4`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VmbusPipeClientEnumeratePipesInternal(
        const struct _GUID *a1,
        void *a2,
        void (__fastcall *a3)(void *, BYTE *, BYTE *, __int128 *),
        bool *a4)
{
  unsigned int v8; // esi
  __int64 DeviceInfoList; // rbx
  const char *v10; // r9
  __int64 v11; // rdx
  bool v12; // di
  int InstanceIdFromDevInfo; // eax
  unsigned int v14; // edi
  HKEY v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  DWORD v18; // eax
  int LastError; // eax
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v24; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v25[3]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+88h] [rbp-78h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h]
  __int128 v31; // [rsp+A8h] [rbp-58h]
  unsigned int v32[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+E0h] [rbp-20h] BYREF
  BYTE v35[524]; // [rsp+E4h] [rbp-1Ch] BYREF
  BYTE Data[112]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v8 = 0;
  *a4 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v23 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = 154;
    goto LABEL_23;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, a1, 0, 18, 0, 0, v23) )
  {
    v11 = 161;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                  v10);
    goto LABEL_24;
  }
  v12 = 0;
  while ( 1 )
  {
    *(_OWORD *)v32 = 0;
    v33 = 0;
    v32[0] = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, a1, v8) )
      break;
    memset_0(v35, 0, sizeof(v35));
    v34 = 8;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    LODWORD(v29) = 48;
    lpcbData = (LPDWORD)&v29;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v32, &v34, 528) )
    {
      v11 = 201;
      goto LABEL_23;
    }
    v28 = 0;
    v25[0] = v29;
    v25[1] = v30;
    v25[2] = v31;
    InstanceIdFromDevInfo = GetInstanceIdFromDevInfo(DeviceInfoList, v25, &v28);
    v14 = InstanceIdFromDevInfo;
    if ( InstanceIdFromDevInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
        (const char *)(unsigned int)InstanceIdFromDevInfo,
        0);
      v17 = v14;
      goto LABEL_25;
    }
    v12 = 1;
    LODWORD(lpcbData) = 1;
    v15 = (HKEY)DevObjOpenDevRegKey(DeviceInfoList, &v29, 1, 0, 1, lpcbData);
    if ( v15 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v11 = 220;
      goto LABEL_23;
    }
    v24 = v15;
    Type = 3;
    cbData = 112;
    v16 = RegQueryValueExW(v15, L"UserDefined", 0, &Type, Data, &cbData);
    if ( v16 )
    {
      v17 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE9,
              (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
              (const char *)v16,
              lpData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
      goto LABEL_25;
    }
    if ( a3 )
      a3(a2, Data, v35, &v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
    ++v8;
  }
  v18 = GetLastError();
  if ( v18 == 259 )
  {
    *a4 = v12;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v23);
    return 0;
  }
  if ( v18 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xB6,
                  (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
                  (const char *)v18,
                  (unsigned int)v32);
LABEL_24:
    v17 = LastError;
    goto LABEL_25;
  }
  v17 = 0;
LABEL_25:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v23);
  return v17;
}

```

## disassembly

```asm
0x180006718  push    rbp
0x18000671a  push    rbx
0x18000671b  push    rsi
0x18000671c  push    rdi
0x18000671d  push    r12
0x18000671f  push    r13
0x180006721  push    r14
0x180006723  push    r15
0x180006725  lea     rbp, [rsp-278h]
0x18000672d  sub     rsp, 378h
0x180006734  mov     rax, cs:__security_cookie
0x18000673b  xor     rax, rsp
0x18000673e  mov     [rbp+2B0h+var_50], rax
0x180006745  mov     r15, r9
0x180006748  mov     r14, r8
0x18000674b  mov     r13, rdx
0x18000674e  mov     r12, rcx
0x180006751  xor     esi, esi
0x180006753  mov     [r9], sil
0x180006756  mov     [rsp+3B0h+lpData], rsi
0x18000675b  xor     r9d, r9d
0x18000675e  xor     r8d, r8d
0x180006761  xor     edx, edx
0x180006763  xor     ecx, ecx
0x180006765  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000676b  mov     rbx, rax
0x18000676e  mov     [rsp+3B0h+var_380], rax
0x180006773  dec     rax
0x180006776  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000677a  ja      loc_1800069BF
0x180006780  mov     [rsp+3B0h+lpcbData], rsi
0x180006785  mov     [rsp+3B0h+lpData], rsi
0x18000678a  lea     r9d, [rsi+12h]
0x18000678e  xor     r8d, r8d
0x180006791  mov     rdx, r12
0x180006794  mov     rcx, rbx
0x180006797  call    cs:__imp_DevObjGetClassDevs
0x18000679d  test    eax, eax
0x18000679f  jnz     short loc_1800067AB
0x1800067a1  mov     edx, 0A1h
0x1800067a6  jmp     loc_1800069C4
0x1800067ab  mov     dil, sil
0x1800067ae  xorps   xmm0, xmm0
0x1800067b1  movups  xmmword ptr [rbp+2B0h+var_2F8], xmm0
0x1800067b5  movups  [rbp+2B0h+var_2E8], xmm0
0x1800067b9  mov     [rbp+2B0h+var_2F8], 20h ; ' '
0x1800067c0  lea     rax, [rbp+2B0h+var_2F8]
0x1800067c4  mov     [rsp+3B0h+lpData], rax; unsigned int
0x1800067c9  mov     r9d, esi
0x1800067cc  mov     r8, r12
0x1800067cf  xor     edx, edx
0x1800067d1  mov     rcx, rbx
0x1800067d4  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800067da  test    eax, eax
0x1800067dc  jz      loc_18000697C
0x1800067e2  xor     edx, edx; Val
0x1800067e4  mov     r8d, 20Ch; Size
0x1800067ea  lea     rcx, [rbp+2B0h+var_2CC]; void *
0x1800067ee  call    memset_0
0x1800067f3  mov     [rbp+2B0h+var_2D0], 8
0x1800067fa  xorps   xmm0, xmm0
0x1800067fd  movups  [rbp+2B0h+var_328], xmm0
0x180006801  movups  [rbp+2B0h+var_318], xmm0
0x180006805  movups  [rbp+2B0h+var_308], xmm0
0x180006809  mov     dword ptr [rbp+2B0h+var_328], 30h ; '0'
0x180006810  lea     rax, [rbp+2B0h+var_328]
0x180006814  mov     [rsp+3B0h+lpcbData], rax
0x180006819  mov     [rsp+3B0h+lpData], 0; int
0x180006822  mov     r9d, 210h
0x180006828  lea     r8, [rbp+2B0h+var_2D0]
0x18000682c  lea     rdx, [rbp+2B0h+var_2F8]
0x180006830  mov     rcx, rbx
0x180006833  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180006839  test    eax, eax
0x18000683b  jz      loc_180006975
0x180006841  xorps   xmm0, xmm0
0x180006844  movups  [rsp+3B0h+var_338], xmm0
0x180006849  movups  xmm0, [rbp+2B0h+var_328]
0x18000684d  movaps  [rsp+3B0h+var_370], xmm0
0x180006852  movups  xmm1, [rbp+2B0h+var_318]
0x180006856  movaps  [rsp+3B0h+var_360], xmm1
0x18000685b  movups  xmm0, [rbp+2B0h+var_308]
0x18000685f  movaps  [rsp+3B0h+var_350], xmm0
0x180006864  lea     r8, [rsp+3B0h+var_338]
0x180006869  lea     rdx, [rsp+3B0h+var_370]
0x18000686e  mov     rcx, rbx
0x180006871  call    GetInstanceIdFromDevInfo
0x180006876  mov     edi, eax
0x180006878  test    eax, eax
0x18000687a  js      loc_180006956
0x180006880  mov     edi, 1
0x180006885  mov     dword ptr [rsp+3B0h+lpcbData], edi
0x180006889  mov     dword ptr [rsp+3B0h+lpData], edi
0x18000688d  xor     r9d, r9d
0x180006890  mov     r8d, edi
0x180006893  lea     rdx, [rbp+2B0h+var_328]
0x180006897  mov     rcx, rbx
0x18000689a  call    cs:__imp_DevObjOpenDevRegKey
0x1800068a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068a4  jz      loc_18000694F
0x1800068aa  mov     [rsp+3B0h+var_378], rax
0x1800068af  mov     [rsp+3B0h+Type], 3
0x1800068b7  mov     [rsp+3B0h+cbData], 70h ; 'p'
0x1800068bf  lea     rcx, [rsp+3B0h+cbData]
0x1800068c4  mov     [rsp+3B0h+lpcbData], rcx; lpcbData
0x1800068c9  lea     rcx, [rbp+2B0h+Data]
0x1800068d0  mov     [rsp+3B0h+lpData], rcx; unsigned int
0x1800068d5  lea     r9, [rsp+3B0h+Type]; lpType
0x1800068da  xor     r8d, r8d; lpReserved
0x1800068dd  lea     rdx, ValueName; "UserDefined"
0x1800068e4  mov     rcx, rax; hKey
0x1800068e7  call    cs:__imp_RegQueryValueExW
0x1800068ed  test    eax, eax
0x1800068ef  jnz     short loc_180006923
0x1800068f1  test    r14, r14
0x1800068f4  jz      short loc_180006912
0x1800068f6  lea     r9, [rsp+3B0h+var_338]
0x1800068fb  lea     r8, [rbp+2B0h+var_2CC]
0x1800068ff  lea     rdx, [rbp+2B0h+Data]
0x180006906  mov     rcx, r13
0x180006909  mov     rax, r14
0x18000690c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006911  nop
0x180006912  lea     rcx, [rsp+3B0h+var_378]
0x180006917  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000691c  inc     esi
0x18000691e  jmp     loc_1800067AE
0x180006923  mov     rcx, [rbp+2B8h]; this
0x18000692a  mov     r9d, eax; char *
0x18000692d  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006934  mov     edx, 0E9h; void *
0x180006939  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000693e  mov     ebx, eax
0x180006940  lea     rcx, [rsp+3B0h+var_378]
0x180006945  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000694a  jmp     loc_1800069D9
0x18000694f  mov     edx, 0DCh
0x180006954  jmp     short loc_1800069C4
0x180006956  mov     rcx, [rbp+2B8h]; this
0x18000695d  mov     r9d, edi; char *
0x180006960  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006967  mov     edx, 0CDh; void *
0x18000696c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006971  mov     ebx, edi
0x180006973  jmp     short loc_1800069D9
0x180006975  mov     edx, 0C9h
0x18000697a  jmp     short loc_1800069C4
0x18000697c  call    cs:__imp_GetLastError
0x180006982  cmp     eax, 103h
0x180006987  jnz     short loc_18000699A
0x180006989  mov     [r15], dil
0x18000698c  lea     rcx, [rsp+3B0h+var_380]
0x180006991  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x180006996  xor     eax, eax
0x180006998  jmp     short loc_1800069E5
0x18000699a  test    eax, eax
0x18000699c  jz      short loc_1800069BB
0x18000699e  mov     rcx, [rbp+2B8h]; this
0x1800069a5  mov     r9d, eax; char *
0x1800069a8  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x1800069af  mov     edx, 0B6h; void *
0x1800069b4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800069b9  jmp     short loc_1800069D7
0x1800069bb  xor     ebx, ebx
0x1800069bd  jmp     short loc_1800069D9
0x1800069bf  mov     edx, 9Ah; void *
0x1800069c4  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x1800069cb  mov     rcx, [rbp+2B8h]; this
0x1800069d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800069d7  mov     ebx, eax
0x1800069d9  lea     rcx, [rsp+3B0h+var_380]
0x1800069de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1800069e3  mov     eax, ebx
0x1800069e5  mov     rcx, [rbp+2B0h+var_50]
0x1800069ec  xor     rcx, rsp; StackCookie
0x1800069ef  call    __security_check_cookie
0x1800069f4  add     rsp, 378h
0x1800069fb  pop     r15
0x1800069fd  pop     r14
0x1800069ff  pop     r13
0x180006a01  pop     r12
0x180006a03  pop     rdi
0x180006a04  pop     rsi
0x180006a05  pop     rbx
0x180006a06  pop     rbp
0x180006a07  retn
```
