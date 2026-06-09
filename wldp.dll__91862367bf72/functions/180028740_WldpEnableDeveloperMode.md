# WldpEnableDeveloperMode

- ea: `0x180028740`
- end: `0x180028999`
- name: `WldpEnableDeveloperMode`
- size: `601`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001e628`
- `0x18001f038`
- `0x1800201d4`
- `0x1800203ec`
- `0x18002084c`
- `0x180027070`
- `0x1800270cc`
- `0x180027140`
- `0x180027fd0`
- `0x180028740`
- `0x1800291e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002891a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002891a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002886e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002886e`

## string_xrefs

- `0x18002879c`: `onecore\base\ngscb\wldp\dll\wldp.cpp`
- `0x18002880d`: `onecore\base\ngscb\wldp\dll\wldp.cpp`
- `0x180028892`: `onecore\base\ngscb\wldp\dll\wldp.cpp`
- `0x18002893c`: `onecore\base\ngscb\wldp\dll\wldp.cpp`

## pseudocode

```c
__int64 WldpEnableDeveloperMode()
{
  LPCWSTR v0; // rbx
  int IsDeviceLockedDown; // eax
  unsigned int LastError; // edi
  int SepRegistryLocation; // eax
  BOOL v4; // ebx
  const char *v5; // r9
  unsigned int v6; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-39h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-39h]
  void *v10; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR v11; // [rsp+60h] [rbp+7h] BYREF
  __int64 v12; // [rsp+68h] [rbp+Fh] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp+17h] BYREF
  void **v14; // [rsp+88h] [rbp+2Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+37h] BYREF
  char v16; // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned __int8 v18; // [rsp+C8h] [rbp+6Fh] BYREF
  int v19; // [rsp+D0h] [rbp+77h] BYREF
  LPCWSTR lpSubKey; // [rsp+D8h] [rbp+7Fh] BYREF

  v12 = 0;
  v19 = 0;
  lpSubKey = (LPCWSTR)&dword_1800457FC;
  v18 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v0 = 0;
  v11 = 0;
  v10 = 0;
  IsDeviceLockedDown = WldpIsDeviceLockedDown(&v19);
  LastError = IsDeviceLockedDown;
  if ( IsDeviceLockedDown >= 0 )
  {
    if ( v19 )
    {
      SepRegistryLocation = WldpGetSepRegistryLocation(
                              L"CIDeveloper",
                              L"SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlock",
                              &v18,
                              (unsigned __int16 **)&lpSubKey);
      LastError = SepRegistryLocation;
      if ( SepRegistryLocation < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x774,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
          (const char *)(unsigned int)SepRegistryLocation,
          dwOptions);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v11);
        goto LABEL_13;
      }
      if ( v18 )
        v0 = lpSubKey;
      v11 = v0;
      v14 = &v10;
      SecurityDescriptor = 0;
      v16 = 1;
      v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"O:BAG:BAD:(A;CIID;KA;;;SY)(A;CIID;KA;;;BA)(A;CIID;KR;;;WD)(A;CIID;KR;;;RC)(A;;KR;;;AC)(A;;KR;;;S-1-15-3-102"
              "4-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)",
             1u,
             &SecurityDescriptor,
             0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v14);
      if ( !v4 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x780,
                      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
                      v5);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v11);
        goto LABEL_13;
      }
      SecurityAttributes.nLength = 24;
      SecurityAttributes.lpSecurityDescriptor = v10;
      SecurityAttributes.bInheritHandle = 0;
      v14 = (void **)&v12;
      SecurityDescriptor = 0;
      v16 = 1;
      v6 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             lpSubKey,
             0,
             0,
             0,
             0x2001Fu,
             &SecurityAttributes,
             (PHKEY)&SecurityDescriptor,
             0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v14);
      if ( v6 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x78F,
                      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
                      (const char *)v6,
                      dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v11);
        goto LABEL_13;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v11);
    LastError = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76A,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
    (const char *)(unsigned int)IsDeviceLockedDown,
    dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(&v11);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
  return LastError;
}

```

## disassembly

```asm
0x180028740  mov     [rsp-8+arg_0], rbx
0x180028745  push    rbp
0x180028746  push    rsi
0x180028747  push    rdi
0x180028748  lea     rbp, [rsp-47h]
0x18002874d  sub     rsp, 0A0h
0x180028754  xor     esi, esi
0x180028756  mov     [rbp+57h+var_60], esi
0x180028759  mov     [rbp+57h+var_48], rsi
0x18002875d  mov     [rbp+57h+arg_10], esi
0x180028760  lea     rax, dword_1800457FC
0x180028767  mov     [rbp+57h+lpSubKey], rax
0x18002876b  mov     [rbp+57h+arg_8], sil
0x18002876f  xorps   xmm0, xmm0
0x180028772  xor     eax, eax
0x180028774  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x180028778  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18002877c  mov     ebx, esi
0x18002877e  mov     [rbp+57h+var_50], rbx
0x180028782  mov     [rbp+57h+var_58], rsi
0x180028786  lea     rcx, [rbp+57h+arg_10]
0x18002878a  call    WldpIsDeviceLockedDown
0x18002878f  mov     edi, eax
0x180028791  test    eax, eax
0x180028793  jns     short loc_1800287C7
0x180028795  mov     rcx, [rbp+5Fh]; this
0x180028799  mov     r9d, eax; char *
0x18002879c  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x1800287a3  mov     edx, 76Ah; void *
0x1800287a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800287ad  nop
0x1800287ae  lea     rcx, [rbp+57h+var_58]
0x1800287b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800287b7  nop
0x1800287b8  lea     rcx, [rbp+57h+var_50]
0x1800287bc  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800287c1  nop
0x1800287c2  jmp     loc_18002897B
0x1800287c7  cmp     [rbp+57h+arg_10], esi
0x1800287ca  jnz     short loc_1800287E5
0x1800287cc  lea     rcx, [rbp+57h+var_58]
0x1800287d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800287d5  nop
0x1800287d6  lea     rcx, [rbp+57h+var_50]
0x1800287da  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800287df  nop
0x1800287e0  jmp     loc_180028979
0x1800287e5  lea     r9, [rbp+57h+lpSubKey]; unsigned __int16 **
0x1800287e9  lea     r8, [rbp+57h+arg_8]; unsigned __int8 *
0x1800287ed  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x1800287f4  lea     rcx, aCideveloper; "CIDeveloper"
0x1800287fb  call    ?WldpGetSepRegistryLocation@@YAJPEBGPEAGPEAEPEAPEAG@Z; WldpGetSepRegistryLocation(ushort const *,ushort *,uchar *,ushort * *)
0x180028800  mov     edi, eax
0x180028802  test    eax, eax
0x180028804  jns     short loc_180028838
0x180028806  mov     rcx, [rbp+5Fh]; this
0x18002880a  mov     r9d, eax; char *
0x18002880d  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x180028814  mov     edx, 774h; void *
0x180028819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002881e  nop
0x18002881f  lea     rcx, [rbp+57h+var_58]
0x180028823  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028828  nop
0x180028829  lea     rcx, [rbp+57h+var_50]
0x18002882d  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180028832  nop
0x180028833  jmp     loc_18002897B
0x180028838  cmp     [rbp+57h+arg_8], sil
0x18002883c  cmovnz  rbx, [rbp+57h+lpSubKey]
0x180028841  mov     [rbp+57h+var_50], rbx
0x180028845  lea     rax, [rbp+57h+var_58]
0x180028849  mov     [rbp+57h+var_28], rax
0x18002884d  mov     [rbp+57h+SecurityDescriptor], rsi
0x180028851  mov     [rbp+57h+var_18], 1
0x180028855  mov     [rbp+57h+var_60], 1
0x18002885c  xor     r9d, r9d; SecurityDescriptorSize
0x18002885f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180028863  lea     edx, [r9+1]; StringSDRevision
0x180028867  lea     rcx, aOBagBadACiidKa; "O:BAG:BAD:(A;CIID;KA;;;SY)(A;CIID;KA;;;"...
0x18002886e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028874  mov     ebx, eax
0x180028876  mov     edi, 1
0x18002887b  and     edi, 0FFFFFFFEh
0x18002887e  mov     [rbp+57h+var_60], edi
0x180028881  lea     rcx, [rbp+57h+var_28]
0x180028885  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002888a  test    ebx, ebx
0x18002888c  jnz     short loc_1800288BE
0x18002888e  mov     rcx, [rbp+5Fh]; this
0x180028892  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x180028899  mov     edx, 780h; void *
0x18002889e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800288a3  mov     edi, eax
0x1800288a5  lea     rcx, [rbp+57h+var_58]
0x1800288a9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800288ae  nop
0x1800288af  lea     rcx, [rbp+57h+var_50]
0x1800288b3  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x1800288b8  nop
0x1800288b9  jmp     loc_18002897B
0x1800288be  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x1800288c5  mov     rax, [rbp+57h+var_58]
0x1800288c9  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800288cd  mov     [rbp+57h+SecurityAttributes.bInheritHandle], esi
0x1800288d0  lea     rax, [rbp+57h+var_48]
0x1800288d4  mov     [rbp+57h+var_28], rax
0x1800288d8  mov     [rbp+57h+SecurityDescriptor], rsi
0x1800288dc  mov     [rbp+57h+var_18], 1
0x1800288e0  or      edi, 2
0x1800288e3  mov     [rbp+57h+var_60], edi
0x1800288e6  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x1800288eb  lea     rax, [rbp+57h+SecurityDescriptor]
0x1800288ef  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800288f4  lea     rax, [rbp+57h+SecurityAttributes]
0x1800288f8  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800288fd  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x180028905  mov     [rsp+0B0h+dwOptions], esi; unsigned int
0x180028909  xor     r9d, r9d; lpClass
0x18002890c  xor     r8d, r8d; Reserved
0x18002890f  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180028913  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002891a  call    cs:__imp_RegCreateKeyExW
0x180028920  mov     ebx, eax
0x180028922  and     edi, 0FFFFFFFDh
0x180028925  mov     [rbp+57h+var_60], edi
0x180028928  lea     rcx, [rbp+57h+var_28]
0x18002892c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180028931  test    ebx, ebx
0x180028933  jz      short loc_180028965
0x180028935  mov     rcx, [rbp+5Fh]; this
0x180028939  mov     r9d, ebx; char *
0x18002893c  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x180028943  mov     edx, 78Fh; void *
0x180028948  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002894d  mov     edi, eax
0x18002894f  lea     rcx, [rbp+57h+var_58]
0x180028953  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028958  nop
0x180028959  lea     rcx, [rbp+57h+var_50]
0x18002895d  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180028962  nop
0x180028963  jmp     short loc_18002897B
0x180028965  lea     rcx, [rbp+57h+var_58]
0x180028969  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002896e  nop
0x18002896f  lea     rcx, [rbp+57h+var_50]
0x180028973  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180028978  nop
0x180028979  mov     edi, esi
0x18002897b  lea     rcx, [rbp+57h+var_48]
0x18002897f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028984  mov     eax, edi
0x180028986  mov     rbx, [rsp+0B0h+arg_0]
0x18002898e  add     rsp, 0A0h
0x180028995  pop     rdi
0x180028996  pop     rsi
0x180028997  pop     rbp
0x180028998  retn
```
