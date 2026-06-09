# ProfileManager::SaveProfileSecurityDescriptor(_GUID const *,PM_PCB *,int,ushort const *)

- ea: `0x1801fcf5c`
- end: `0x1801fd2c2`
- name: `?SaveProfileSecurityDescriptor@ProfileManager@@AEAAKPEBU_GUID@@PEAUPM_PCB@@HPEBG@Z`
- size: `870`
- prototype: `__int64 __fastcall(ProfileManager *this, struct _GUID *, struct PM_PCB *, int, BYTE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b8394`
- `0x1801fd6a0`

## callees

- `0x18001a988`
- `0x180067d90`
- `0x1800ba438`
- `0x1801fb838`
- `0x1801fb8f8`
- `0x1801fcf5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fcfb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd06a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd18f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fcfb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd06a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd18f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801fd299`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd17e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd215`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd17e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd215`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fd274`
- `MobileNetworking!GetSDDetailsFromObjectID` at `0x1801fd0af`
- `MobileNetworking!GetSDDetailsFromObjectID` at `0x1801fd0af`
- `MobileNetworking!FreeSecurityDescriptor` at `0x1801fd239`
- `MobileNetworking!FreeSecurityDescriptor` at `0x1801fd239`
- `MobileNetworking!ConvertSDDLToValidSecurityDescriptor` at `0x1801fd00a`
- `MobileNetworking!ConvertSDDLToValidSecurityDescriptor` at `0x1801fd00a`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x1801fd133`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x1801fd133`

## string_xrefs

- `0x1801fd1c2`: `All User Profile Security Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ProfileManager::SaveProfileSecurityDescriptor(
        ProfileManager *this,
        struct _GUID *a2,
        struct PM_PCB *a3,
        int a4,
        BYTE *a5)
{
  _QWORD *v8; // rsi
  BYTE *lpData; // rdi
  __int64 result; // rax
  unsigned int valid; // eax
  unsigned int v12; // r14d
  HLOCAL v13; // rcx
  unsigned int SDDetailsFromObjectID; // edi
  HLOCAL v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // r14d
  HLOCAL v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // edi
  const char *v21; // r9
  HLOCAL v22; // rcx
  __int64 v23; // rax
  HLOCAL v24; // rcx
  unsigned int *cbData; // [rsp+20h] [rbp-58h]
  unsigned int cbDataa; // [rsp+20h] [rbp-58h]
  __int64 v27; // [rsp+30h] [rbp-48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-40h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-38h] BYREF
  __int64 v30; // [rsp+48h] [rbp-30h] BYREF
  char v31; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v33; // [rsp+80h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+18h] BYREF

  wil::EnterCriticalSection(&lpCriticalSection, this);
  if ( (*((_BYTE *)a3 + 72) & 3) != 0 )
  {
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  else
  {
    v8 = (_QWORD *)((char *)a3 + 48);
    if ( !*((_QWORD *)a3 + 6) || a4 )
    {
      lpData = a5;
    }
    else
    {
      lpData = a5;
      if ( !a5 )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return 0;
      }
    }
    v33 = 0;
    hMem = 0;
    v27 = 0;
    if ( lpData )
    {
      valid = ConvertSDDLToValidSecurityDescriptor(lpData, 458787, &v33, &v27);
      v12 = valid;
      if ( valid )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x196,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
          (const char *)valid,
          (unsigned int)cbData);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
        v13 = hMem;
        hMem = 0;
        if ( v13 )
          LocalFree(v13);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return v12;
      }
      goto LABEL_23;
    }
    p_hMem = &hMem;
    v30 = 0;
    v31 = 1;
    cbData = &v33;
    SDDetailsFromObjectID = GetSDDetailsFromObjectID(9, 0, &v27, &v30);
    wil::details::out_param_ptr_t<unsigned short * *,wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<unsigned short * *,wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( !SDDetailsFromObjectID )
    {
      lpData = (BYTE *)hMem;
LABEL_23:
      v16 = VerifyRpcClientAccessToSecurityDescriptor(v27, 458787);
      v17 = v16;
      if ( v16 )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1A1,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
          (const char *)v16,
          (unsigned int)cbData);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
        v18 = hMem;
        hMem = 0;
        if ( v18 )
          LocalFree(v18);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return v17;
      }
      else
      {
        try
        {
          v19 = StSaveNamedProfileMetaData(
                  a2,
                  *(unsigned __int8 *)(*(_QWORD *)a3 + 164LL),
                  (GUID *)((char *)a3 + 56),
                  (wchar_t *)L"All User Profile Security Descriptor",
                  2 * v33 + 2,
                  lpData);
          v20 = v19;
          if ( v19 )
          {
            wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1AA,
              (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
              (const char *)v19,
              cbDataa);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
            v22 = hMem;
            hMem = 0;
            if ( v22 )
              LocalFree(v22);
            if ( lpCriticalSection )
              LeaveCriticalSection(lpCriticalSection);
            result = v20;
          }
          else
          {
            if ( *v8 )
              FreeSecurityDescriptor((char *)a3 + 48);
            v23 = v27;
            v27 = 0;
            *v8 = v23;
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
            v24 = hMem;
            hMem = 0;
            if ( v24 )
              LocalFree(v24);
            if ( lpCriticalSection )
              LeaveCriticalSection(lpCriticalSection);
            result = 0;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Win32_Return_CaughtException(
                                 retaddr,
                                 (void *)0x1B5,
                                 (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                                 v21);
        }
      }
      return result;
    }
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
      (const char *)SDDetailsFromObjectID,
      (unsigned int)&v33);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
    v15 = hMem;
    hMem = 0;
    if ( v15 )
      LocalFree(v15);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return SDDetailsFromObjectID;
  }
}

```

## disassembly

```asm
0x1801fcf5c  mov     [rsp+arg_8], rsi
0x1801fcf61  mov     [rsp+arg_18], rdi
0x1801fcf66  push    r12
0x1801fcf68  push    r14
0x1801fcf6a  push    r15
0x1801fcf6c  sub     rsp, 60h
0x1801fcf70  mov     edi, r9d
0x1801fcf73  mov     r15, r8
0x1801fcf76  mov     r12, rdx
0x1801fcf79  mov     rdx, rcx
0x1801fcf7c  lea     rcx, [rsp+78h+lpCriticalSection]
0x1801fcf81  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801fcf86  nop
0x1801fcf87  test    byte ptr [r15+48h], 3
0x1801fcf8c  jnz     loc_1801FD28F
0x1801fcf92  lea     rsi, [r15+30h]
0x1801fcf96  cmp     qword ptr [rsi], 0
0x1801fcf9a  jz      short loc_1801FCFC4
0x1801fcf9c  test    edi, edi
0x1801fcf9e  jnz     short loc_1801FCFC4
0x1801fcfa0  mov     rdi, [rsp+78h+arg_20]
0x1801fcfa8  test    rdi, rdi
0x1801fcfab  jnz     short loc_1801FCFCC
0x1801fcfad  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fcfb2  test    rcx, rcx
0x1801fcfb5  jz      short loc_1801FCFBD
0x1801fcfb7  call    cs:__imp_LeaveCriticalSection
0x1801fcfbd  xor     eax, eax
0x1801fcfbf  jmp     loc_1801FD2AA
0x1801fcfc4  mov     rdi, [rsp+78h+arg_20]
0x1801fcfcc  mov     [rsp+78h+arg_0], 0
0x1801fcfd7  mov     [rsp+78h+hMem], 0
0x1801fcfe3  mov     [rsp+78h+var_48], 0
0x1801fcfec  test    rdi, rdi
0x1801fcfef  jz      loc_1801FD078
0x1801fcff5  lea     r9, [rsp+78h+var_48]
0x1801fcffa  lea     r8, [rsp+78h+arg_0]
0x1801fd002  mov     edx, 70023h
0x1801fd007  mov     rcx, rdi
0x1801fd00a  call    cs:__imp_ConvertSDDLToValidSecurityDescriptor
0x1801fd010  mov     r14d, eax
0x1801fd013  test    eax, eax
0x1801fd015  jz      loc_1801FD129
0x1801fd01b  mov     rcx, [rsp+78h]; this
0x1801fd020  mov     r9d, eax; char *
0x1801fd023  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801fd02a  mov     edx, 196h; void *
0x1801fd02f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801fd034  nop
0x1801fd035  lea     rcx, [rsp+78h+var_48]
0x1801fd03a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeSecurityDescriptor@details@utils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fd03f  nop
0x1801fd040  mov     rcx, [rsp+78h+hMem]; hMem
0x1801fd048  mov     [rsp+78h+hMem], 0
0x1801fd054  test    rcx, rcx
0x1801fd057  jz      short loc_1801FD060
0x1801fd059  call    cs:__imp_LocalFree
0x1801fd05f  nop
0x1801fd060  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd065  test    rcx, rcx
0x1801fd068  jz      short loc_1801FD070
0x1801fd06a  call    cs:__imp_LeaveCriticalSection
0x1801fd070  mov     eax, r14d
0x1801fd073  jmp     loc_1801FD2AA
0x1801fd078  lea     rax, [rsp+78h+hMem]
0x1801fd080  mov     [rsp+78h+var_38], rax
0x1801fd085  mov     [rsp+78h+var_30], 0
0x1801fd08e  mov     [rsp+78h+var_28], 1
0x1801fd093  lea     rax, [rsp+78h+arg_0]
0x1801fd09b  mov     qword ptr [rsp+78h+cbData], rax; unsigned int
0x1801fd0a0  lea     r9, [rsp+78h+var_30]
0x1801fd0a5  lea     r8, [rsp+78h+var_48]
0x1801fd0aa  xor     edx, edx
0x1801fd0ac  lea     ecx, [rdx+9]
0x1801fd0af  call    cs:__imp_GetSDDetailsFromObjectID
0x1801fd0b5  mov     edi, eax
0x1801fd0b7  lea     rcx, [rsp+78h+var_38]
0x1801fd0bc  call    ??1?$out_param_ptr_t@PEAPEAGV?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<ushort * *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<ushort * *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1801fd0c1  test    edi, edi
0x1801fd0c3  jz      short loc_1801FD121
0x1801fd0c5  mov     rcx, [rsp+78h]; this
0x1801fd0ca  mov     r9d, edi; char *
0x1801fd0cd  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801fd0d4  mov     edx, 19Bh; void *
0x1801fd0d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801fd0de  nop
0x1801fd0df  lea     rcx, [rsp+78h+var_48]
0x1801fd0e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeSecurityDescriptor@details@utils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fd0e9  nop
0x1801fd0ea  mov     rcx, [rsp+78h+hMem]; hMem
0x1801fd0f2  mov     [rsp+78h+hMem], 0
0x1801fd0fe  test    rcx, rcx
0x1801fd101  jz      short loc_1801FD10A
0x1801fd103  call    cs:__imp_LocalFree
0x1801fd109  nop
0x1801fd10a  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd10f  test    rcx, rcx
0x1801fd112  jz      short loc_1801FD11A
0x1801fd114  call    cs:__imp_LeaveCriticalSection
0x1801fd11a  mov     eax, edi
0x1801fd11c  jmp     loc_1801FD2AA
0x1801fd121  mov     rdi, [rsp+78h+hMem]
0x1801fd129  mov     edx, 70023h
0x1801fd12e  mov     rcx, [rsp+78h+var_48]
0x1801fd133  call    cs:__imp_VerifyRpcClientAccessToSecurityDescriptor
0x1801fd139  mov     r14d, eax
0x1801fd13c  test    eax, eax
0x1801fd13e  jz      short loc_1801FD19D
0x1801fd140  mov     rcx, [rsp+78h]; this
0x1801fd145  mov     r9d, eax; char *
0x1801fd148  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801fd14f  mov     edx, 1A1h; void *
0x1801fd154  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801fd159  nop
0x1801fd15a  lea     rcx, [rsp+78h+var_48]
0x1801fd15f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeSecurityDescriptor@details@utils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fd164  nop
0x1801fd165  mov     rcx, [rsp+78h+hMem]; hMem
0x1801fd16d  mov     [rsp+78h+hMem], 0
0x1801fd179  test    rcx, rcx
0x1801fd17c  jz      short loc_1801FD185
0x1801fd17e  call    cs:__imp_LocalFree
0x1801fd184  nop
0x1801fd185  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd18a  test    rcx, rcx
0x1801fd18d  jz      short loc_1801FD195
0x1801fd18f  call    cs:__imp_LeaveCriticalSection
0x1801fd195  mov     eax, r14d
0x1801fd198  jmp     loc_1801FD2AA
0x1801fd19d  mov     eax, [rsp+78h+arg_0]
0x1801fd1a4  lea     ecx, ds:2[rax*2]
0x1801fd1ab  lea     r8, [r15+38h]; GUID *
0x1801fd1af  mov     rax, [r15]
0x1801fd1b2  movzx   edx, byte ptr [rax+0A4h]; int
0x1801fd1b9  mov     [rsp+78h+lpData], rdi; lpData
0x1801fd1be  mov     [rsp+78h+cbData], ecx; unsigned int
0x1801fd1c2  lea     r9, aAllUserProfile_0; "All User Profile Security Descriptor"
0x1801fd1c9  mov     rcx, r12; rguid
0x1801fd1cc  call    ?StSaveNamedProfileMetaData@@YAKPEBU_GUID@@HPEAU1@PEBGKPEBE@Z; StSaveNamedProfileMetaData(_GUID const *,int,_GUID *,ushort const *,ulong,uchar const *)
0x1801fd1d1  mov     edi, eax
0x1801fd1d3  test    eax, eax
0x1801fd1d5  jz      short loc_1801FD230
0x1801fd1d7  mov     rcx, [rsp+78h]; this
0x1801fd1dc  mov     r9d, eax; char *
0x1801fd1df  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801fd1e6  mov     edx, 1AAh; void *
0x1801fd1eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801fd1f0  nop
0x1801fd1f1  lea     rcx, [rsp+78h+var_48]
0x1801fd1f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeSecurityDescriptor@details@utils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fd1fb  nop
0x1801fd1fc  mov     rcx, [rsp+78h+hMem]; hMem
0x1801fd204  mov     [rsp+78h+hMem], 0
0x1801fd210  test    rcx, rcx
0x1801fd213  jz      short loc_1801FD21C
0x1801fd215  call    cs:__imp_LocalFree
0x1801fd21b  nop
0x1801fd21c  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd221  test    rcx, rcx
0x1801fd224  jz      short loc_1801FD22C
0x1801fd226  call    cs:__imp_LeaveCriticalSection
0x1801fd22c  mov     eax, edi
0x1801fd22e  jmp     short loc_1801FD2AA
0x1801fd230  cmp     qword ptr [rsi], 0
0x1801fd234  jz      short loc_1801FD23F
0x1801fd236  mov     rcx, rsi
0x1801fd239  call    cs:__imp_FreeSecurityDescriptor
0x1801fd23f  mov     rax, [rsp+78h+var_48]
0x1801fd244  mov     [rsp+78h+var_48], 0
0x1801fd24d  mov     [rsi], rax
0x1801fd250  lea     rcx, [rsp+78h+var_48]
0x1801fd255  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeSecurityDescriptor@details@utils@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&utils::details::FreeSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fd25a  nop
0x1801fd25b  mov     rcx, [rsp+78h+hMem]; hMem
0x1801fd263  mov     [rsp+78h+hMem], 0
0x1801fd26f  test    rcx, rcx
0x1801fd272  jz      short loc_1801FD27B
0x1801fd274  call    cs:__imp_LocalFree
0x1801fd27a  nop
0x1801fd27b  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd280  test    rcx, rcx
0x1801fd283  jz      short loc_1801FD28B
0x1801fd285  call    cs:__imp_LeaveCriticalSection
0x1801fd28b  xor     eax, eax
0x1801fd28d  jmp     short loc_1801FD2AA
0x1801fd28f  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1801fd294  test    rcx, rcx
0x1801fd297  jz      short loc_1801FD29F
0x1801fd299  call    cs:__imp_LeaveCriticalSection
0x1801fd29f  xor     eax, eax
0x1801fd2a1  jmp     short loc_1801FD2AA
0x1801fd2a3  mov     eax, [rsp+78h+arg_0]
0x1801fd2aa  lea     r11, [rsp+78h+var_18]
0x1801fd2af  mov     rsi, [r11+28h]
0x1801fd2b3  mov     rdi, [r11+38h]
0x1801fd2b7  mov     rsp, r11
0x1801fd2ba  pop     r15
0x1801fd2bc  pop     r14
0x1801fd2be  pop     r12
0x1801fd2c0  retn
```
