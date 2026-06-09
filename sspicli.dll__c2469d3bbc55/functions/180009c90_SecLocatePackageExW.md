# SecLocatePackageExW

- ea: `0x180009c90`
- end: `0x18000a097`
- name: `SecLocatePackageExW`
- size: `1031`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005190`
- `0x18000996c`
- `0x180009c40`
- `0x1800197b0`
- `0x18001a33c`
- `0x18001a660`
- `0x18001ab40`
- `0x18001c2b0`

## callees

- `0x1800069d8`
- `0x180006eac`
- `0x1800070d0`
- `0x180008fc4`
- `0x180009c90`
- `0x18001d478`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180009f5d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009fad`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009f5d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009fad`
- `ntdll!RtlReleaseResource` at `0x180009d62`
- `ntdll!RtlReleaseResource` at `0x180009e47`
- `ntdll!RtlReleaseResource` at `0x180009e91`
- `ntdll!RtlReleaseResource` at `0x180009eda`
- `ntdll!RtlReleaseResource` at `0x180009f0b`
- `ntdll!RtlReleaseResource` at `0x180009f39`
- `ntdll!RtlReleaseResource` at `0x18000a050`
- `ntdll!RtlReleaseResource` at `0x18000a070`
- `ntdll!RtlReleaseResource` at `0x180009d62`
- `ntdll!RtlReleaseResource` at `0x180009e47`
- `ntdll!RtlReleaseResource` at `0x180009e91`
- `ntdll!RtlReleaseResource` at `0x180009eda`
- `ntdll!RtlReleaseResource` at `0x180009f0b`
- `ntdll!RtlReleaseResource` at `0x180009f39`
- `ntdll!RtlReleaseResource` at `0x18000a050`
- `ntdll!RtlReleaseResource` at `0x18000a070`
- `ntdll!RtlInitUnicodeString` at `0x180009cb3`
- `ntdll!RtlInitUnicodeString` at `0x180009cb3`
- `ntdll!RtlEqualUnicodeString` at `0x180009d3c`
- `ntdll!RtlEqualUnicodeString` at `0x180009e2c`
- `ntdll!RtlEqualUnicodeString` at `0x180009d3c`
- `ntdll!RtlEqualUnicodeString` at `0x180009e2c`
- `ntdll!RtlAcquireResourceShared` at `0x180009cec`
- `ntdll!RtlAcquireResourceShared` at `0x180009df6`
- `ntdll!RtlAcquireResourceShared` at `0x180009cec`
- `ntdll!RtlAcquireResourceShared` at `0x180009df6`

## pseudocode

```c
__int64 __fastcall SecLocatePackageExW(int a1, const WCHAR *a2, struct _DLL_SECURITY_PACKAGE **a3)
{
  struct _RTL_RESOURCE *v5; // rsi
  __int64 v6; // r8
  UNICODE_STRING *v7; // rbx
  struct _DLL_SECURITY_PACKAGE *v8; // rdi
  int v9; // eax
  __int64 i; // rbx
  NTSTATUS SaslProfiles; // ebx
  __int64 v12; // rdi
  struct _RTL_RESOURCE *v13; // rbx
  __int64 v14; // r8
  UNICODE_STRING *v15; // rsi
  __int64 v16; // rdx
  int v17; // r8d
  int v19; // eax
  __int64 j; // rbx
  __int64 v21; // rbx
  __int64 v22; // rbx
  unsigned int k; // esi
  __int64 v24; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-58h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v5 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                 * (unsigned __int8)((SecPackageListLockCount - 1)
                                                                   & NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v5, 1u);
  v7 = (UNICODE_STRING *)SecPackageControlList;
  v8 = 0;
  if ( SecPackageControlList != &SecPackageControlList )
  {
    while ( 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v6, v7[6].Buffer);
      if ( RtlEqualUnicodeString(v7 + 6, &DestinationString, 1u) )
      {
        v8 = (struct _DLL_SECURITY_PACKAGE *)v7;
        if ( (v7[1].Length & 0x20) != 0 )
          break;
      }
      v7 = *(UNICODE_STRING **)&v7->Length;
      if ( v7 == (UNICODE_STRING *)&SecPackageControlList )
        goto LABEL_5;
    }
    if ( (*(_DWORD *)&v7[5].Length & 0x200000) != 0 && a1 && SecGlobalExtenderPackage )
      v8 = SecGlobalExtenderPackage;
  }
  if ( v8 )
  {
    RtlReleaseResource(v5);
    goto LABEL_23;
  }
LABEL_5:
  if ( SecPackageLsaLoaded && SecPackageSspiLoaded )
  {
    RtlReleaseResource(v5);
    return (unsigned int)-2146893051;
  }
  RtlReleaseResource(v5);
  v9 = SecPackageListLockCount;
  for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
    v9 = SecPackageListLockCount;
  }
  if ( SecPackageLoadInProgress )
  {
    v24 = 0;
    if ( v9 )
    {
      do
      {
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v24]);
        v24 = (unsigned int)(v24 + 1);
      }
      while ( (unsigned int)v24 < SecPackageListLockCount );
    }
    return (unsigned int)-2146893051;
  }
  SecPackageLoadInProgress = 1;
  if ( SecPackageLsaLoaded || (SaslProfiles = SecpLoadLsaPackages(), SaslProfiles >= 0) )
  {
    if ( SecPackageSspiLoaded || (SaslProfiles = SecpLoadSspiPackages(), SaslProfiles >= 0) )
      SaslProfiles = SecpLoadSaslProfiles();
  }
  v12 = 0;
  for ( SecPackageLoadInProgress = 0; (unsigned int)v12 < SecPackageListLockCount; v12 = (unsigned int)(v12 + 1) )
    RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v12]);
  if ( SaslProfiles < 0 )
    return (unsigned int)-2146893051;
  v13 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                  * ((unsigned int)(SecPackageListLockCount - 1)
                                                   & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v13, 1u);
  v15 = (UNICODE_STRING *)SecPackageControlList;
  v8 = 0;
  if ( SecPackageControlList != &SecPackageControlList )
  {
    while ( 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v14, v15[6].Buffer);
      if ( RtlEqualUnicodeString(v15 + 6, &DestinationString, 1u) )
      {
        v8 = (struct _DLL_SECURITY_PACKAGE *)v15;
        if ( (v15[1].Length & 0x20) != 0 )
          break;
      }
      v15 = *(UNICODE_STRING **)&v15->Length;
      v8 = 0;
      if ( v15 == (UNICODE_STRING *)&SecPackageControlList )
        goto LABEL_16;
    }
    if ( (*(_DWORD *)&v15[5].Length & 0x200000) != 0 && a1 && SecGlobalExtenderPackage )
      v8 = SecGlobalExtenderPackage;
  }
LABEL_16:
  RtlReleaseResource(v13);
  if ( !v8 )
    return (unsigned int)-2146893051;
LABEL_23:
  if ( (*((_BYTE *)v8 + 36) & 4) == 0 )
  {
LABEL_24:
    *a3 = v8;
    return 0;
  }
  v19 = SecPackageListLockCount;
  for ( j = 0; (unsigned int)j < SecPackageListLockCount; j = (unsigned int)(j + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * j], 1u);
    v19 = SecPackageListLockCount;
  }
  if ( (*((_BYTE *)v8 + 36) & 4) == 0 )
  {
    v21 = 0;
    if ( v19 )
    {
      do
      {
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v21]);
        v21 = (unsigned int)(v21 + 1);
      }
      while ( (unsigned int)v21 < SecPackageListLockCount );
    }
    goto LABEL_24;
  }
  v22 = 0;
  for ( k = SecpSnapPackage(v8, v16, v17); (unsigned int)v22 < SecPackageListLockCount; v22 = (unsigned int)(v22 + 1) )
    RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v22]);
  if ( !k )
  {
    *a3 = v8;
    return 0;
  }
  return k;
}

```

## disassembly

```asm
0x180009c90  push    rbx
0x180009c92  push    rbp
0x180009c93  push    rsi
0x180009c94  push    rdi
0x180009c95  push    r12
0x180009c97  push    r13
0x180009c99  push    r14
0x180009c9b  push    r15
0x180009c9d  sub     rsp, 38h
0x180009ca1  mov     ebp, ecx
0x180009ca3  xorps   xmm0, xmm0
0x180009ca6  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180009cab  mov     r14, r8
0x180009cae  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180009cb3  call    cs:__imp_RtlInitUnicodeString
0x180009cb9  mov     rax, gs:30h
0x180009cc2  lea     r13, SecPackageListLock
0x180009cc9  mov     edx, cs:SecPackageListLockCount
0x180009ccf  dec     edx
0x180009cd1  movzx   r9d, byte ptr [rax+1747h]
0x180009cd9  and     r9, rdx
0x180009cdc  mov     dl, 1; Wait
0x180009cde  lea     rsi, [r9+r9*2]
0x180009ce2  shl     rsi, 5
0x180009ce6  add     rsi, r13
0x180009ce9  mov     rcx, rsi; Resource
0x180009cec  call    cs:__imp_RtlAcquireResourceShared
0x180009cf2  mov     rbx, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180009cf9  lea     r15, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180009d00  xor     edi, edi
0x180009d02  lea     r12, WPP_GLOBAL_Control
0x180009d09  cmp     rbx, r15
0x180009d0c  jz      loc_180009E85
0x180009d12  nop     dword ptr [rax+00h]
0x180009d16  nop     word ptr [rax+rax+00000000h]
0x180009d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d27  cmp     rcx, r12
0x180009d2a  jnz     loc_180009E57
0x180009d30  lea     rcx, [rbx+60h]; String1
0x180009d34  mov     r8b, 1; CaseInsensitive
0x180009d37  lea     rdx, [rsp+78h+DestinationString]; String2
0x180009d3c  call    cs:__imp_RtlEqualUnicodeString
0x180009d42  test    al, al
0x180009d44  jnz     loc_18000A00E
0x180009d4a  mov     rbx, [rbx]
0x180009d4d  cmp     rbx, r15
0x180009d50  jnz     short loc_180009D20
0x180009d52  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x180009d59  jnz     loc_180009F29
0x180009d5f  mov     rcx, rsi; Resource
0x180009d62  call    cs:__imp_RtlReleaseResource
0x180009d68  mov     eax, cs:SecPackageListLockCount
0x180009d6e  xor     ebx, ebx
0x180009d70  test    eax, eax
0x180009d72  jnz     loc_180009FA0
0x180009d78  cmp     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x180009d7f  jnz     loc_18000A03B
0x180009d85  cmp     cs:?SecPackageLsaLoaded@@3HA, 0; int SecPackageLsaLoaded
0x180009d8c  mov     cs:?SecPackageLoadInProgress@@3HA, 1; int SecPackageLoadInProgress
0x180009d96  jnz     loc_180009F75
0x180009d9c  call    ?SecpLoadLsaPackages@@YAJXZ; SecpLoadLsaPackages(void)
0x180009da1  mov     ebx, eax
0x180009da3  test    eax, eax
0x180009da5  jns     loc_180009F75
0x180009dab  xor     edi, edi
0x180009dad  mov     cs:?SecPackageLoadInProgress@@3HA, 0; int SecPackageLoadInProgress
0x180009db7  cmp     cs:SecPackageListLockCount, edi
0x180009dbd  ja      loc_18000A065
0x180009dc3  test    ebx, ebx
0x180009dc5  js      loc_180009F3F
0x180009dcb  mov     rax, gs:30h
0x180009dd4  mov     ecx, cs:SecPackageListLockCount
0x180009dda  dec     ecx
0x180009ddc  movzx   edx, byte ptr [rax+1747h]
0x180009de3  and     rdx, rcx
0x180009de6  lea     rbx, [rdx+rdx*2]
0x180009dea  mov     dl, 1; Wait
0x180009dec  shl     rbx, 5
0x180009df0  add     rbx, r13
0x180009df3  mov     rcx, rbx; Resource
0x180009df6  call    cs:__imp_RtlAcquireResourceShared
0x180009dfc  mov     rsi, cs:?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x180009e03  xor     edi, edi
0x180009e05  cmp     rsi, r15
0x180009e08  jz      short loc_180009E44
0x180009e0a  nop     word ptr [rax+rax+00h]
0x180009e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e17  cmp     rcx, r12
0x180009e1a  jnz     loc_180009FC5
0x180009e20  lea     rcx, [rsi+60h]; String1
0x180009e24  mov     r8b, 1; CaseInsensitive
0x180009e27  lea     rdx, [rsp+78h+DestinationString]; String2
0x180009e2c  call    cs:__imp_RtlEqualUnicodeString
0x180009e32  test    al, al
0x180009e34  jnz     loc_18000A085
0x180009e3a  mov     rsi, [rsi]
0x180009e3d  xor     edi, edi
0x180009e3f  cmp     rsi, r15
0x180009e42  jnz     short loc_180009E10
0x180009e44  mov     rcx, rbx; Resource
0x180009e47  call    cs:__imp_RtlReleaseResource
0x180009e4d  test    rdi, rdi
0x180009e50  jnz     short loc_180009E97
0x180009e52  jmp     loc_180009F3F
0x180009e57  test    byte ptr [rcx+1Ch], 4
0x180009e5b  jz      loc_180009D30
0x180009e61  mov     r9, [rbx+68h]
0x180009e65  mov     edx, 0Bh
0x180009e6a  mov     rcx, [rcx+10h]
0x180009e6e  call    WPP_SF_S
0x180009e73  jmp     loc_180009D30
0x180009e78  test    dword ptr [rbx+50h], 200000h
0x180009e7f  jnz     loc_18000A020
0x180009e85  test    rdi, rdi
0x180009e88  jz      loc_180009D52
0x180009e8e  mov     rcx, rsi; Resource
0x180009e91  call    cs:__imp_RtlReleaseResource
0x180009e97  test    byte ptr [rdi+24h], 4
0x180009e9b  jnz     short loc_180009EB3
0x180009e9d  mov     [r14], rdi
0x180009ea0  xor     eax, eax
0x180009ea2  add     rsp, 38h
0x180009ea6  pop     r15
0x180009ea8  pop     r14
0x180009eaa  pop     r13
0x180009eac  pop     r12
0x180009eae  pop     rdi
0x180009eaf  pop     rsi
0x180009eb0  pop     rbp
0x180009eb1  pop     rbx
0x180009eb2  retn
0x180009eb3  mov     eax, cs:SecPackageListLockCount
0x180009eb9  xor     ebx, ebx
0x180009ebb  test    eax, eax
0x180009ebd  jnz     loc_180009F50
0x180009ec3  test    byte ptr [rdi+24h], 4
0x180009ec7  jnz     short loc_180009EEC
0x180009ec9  xor     ebx, ebx
0x180009ecb  test    eax, eax
0x180009ecd  jz      short loc_180009E9D
0x180009ecf  lea     rcx, [rbx+rbx*2]
0x180009ed3  shl     rcx, 5
0x180009ed7  add     rcx, r13; Resource
0x180009eda  call    cs:__imp_RtlReleaseResource
0x180009ee0  inc     ebx
0x180009ee2  cmp     ebx, cs:SecPackageListLockCount
0x180009ee8  jb      short loc_180009ECF
0x180009eea  jmp     short loc_180009E9D
0x180009eec  mov     rcx, rdi; struct _DLL_SECURITY_PACKAGE *
0x180009eef  call    ?SecpSnapPackage@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapPackage(_DLL_SECURITY_PACKAGE *)
0x180009ef4  xor     ebx, ebx
0x180009ef6  mov     esi, eax
0x180009ef8  cmp     cs:SecPackageListLockCount, ebx
0x180009efe  jbe     short loc_180009F1B
0x180009f00  lea     rcx, [rbx+rbx*2]
0x180009f04  shl     rcx, 5
0x180009f08  add     rcx, r13; Resource
0x180009f0b  call    cs:__imp_RtlReleaseResource
0x180009f11  inc     ebx
0x180009f13  cmp     ebx, cs:SecPackageListLockCount
0x180009f19  jb      short loc_180009F00
0x180009f1b  test    esi, esi
0x180009f1d  jnz     short loc_180009F44
0x180009f1f  mov     [r14], rdi
0x180009f22  mov     eax, esi
0x180009f24  jmp     loc_180009EA2
0x180009f29  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x180009f30  jz      loc_180009D5F
0x180009f36  mov     rcx, rsi; Resource
0x180009f39  call    cs:__imp_RtlReleaseResource
0x180009f3f  mov     esi, 80090305h
0x180009f44  mov     eax, esi
0x180009f46  jmp     loc_180009EA2
0x180009f50  lea     rcx, [rbx+rbx*2]
0x180009f54  mov     dl, 1; Wait
0x180009f56  shl     rcx, 5
0x180009f5a  add     rcx, r13; Resource
0x180009f5d  call    cs:__imp_RtlAcquireResourceExclusive
0x180009f63  mov     eax, cs:SecPackageListLockCount
0x180009f69  inc     ebx
0x180009f6b  cmp     ebx, eax
0x180009f6d  jnb     loc_180009EC3
0x180009f73  jmp     short loc_180009F50
0x180009f75  cmp     cs:?SecPackageSspiLoaded@@3HA, 0; int SecPackageSspiLoaded
0x180009f7c  jnz     short loc_180009F8D
0x180009f7e  call    ?SecpLoadSspiPackages@@YAJXZ; SecpLoadSspiPackages(void)
0x180009f83  mov     ebx, eax
0x180009f85  test    eax, eax
0x180009f87  js      loc_180009DAB
0x180009f8d  call    ?SecpLoadSaslProfiles@@YAJXZ; SecpLoadSaslProfiles(void)
0x180009f92  mov     ebx, eax
0x180009f94  jmp     loc_180009DAB
0x180009fa0  lea     rcx, [rbx+rbx*2]
0x180009fa4  mov     dl, 1; Wait
0x180009fa6  shl     rcx, 5
0x180009faa  add     rcx, r13; Resource
0x180009fad  call    cs:__imp_RtlAcquireResourceExclusive
0x180009fb3  mov     eax, cs:SecPackageListLockCount
0x180009fb9  inc     ebx
0x180009fbb  cmp     ebx, eax
0x180009fbd  jnb     loc_180009D78
0x180009fc3  jmp     short loc_180009FA0
0x180009fc5  test    byte ptr [rcx+1Ch], 4
0x180009fc9  jz      loc_180009E20
0x180009fcf  mov     r9, [rsi+68h]
0x180009fd3  mov     edx, 0Bh
0x180009fd8  mov     rcx, [rcx+10h]
0x180009fdc  call    WPP_SF_S
0x180009fe1  jmp     loc_180009E20
0x180009fe6  test    dword ptr [rsi+50h], 200000h
0x180009fed  jz      loc_180009E44
0x180009ff3  test    ebp, ebp
0x180009ff5  jz      loc_180009E44
0x180009ffb  mov     rax, cs:?SecGlobalExtenderPackage@@3PEAU_DLL_SECURITY_PACKAGE@@EA; _DLL_SECURITY_PACKAGE * SecGlobalExtenderPackage
0x18000a002  test    rax, rax
0x18000a005  cmovnz  rdi, rax
0x18000a009  jmp     loc_180009E44
0x18000a00e  test    byte ptr [rbx+10h], 20h
0x18000a012  mov     rdi, rbx
0x18000a015  jnz     loc_180009E78
0x18000a01b  jmp     loc_180009D4A
0x18000a020  test    ebp, ebp
0x18000a022  jz      loc_180009E85
0x18000a028  mov     rax, cs:?SecGlobalExtenderPackage@@3PEAU_DLL_SECURITY_PACKAGE@@EA; _DLL_SECURITY_PACKAGE * SecGlobalExtenderPackage
0x18000a02f  test    rax, rax
0x18000a032  cmovnz  rdi, rax
0x18000a036  jmp     loc_180009E85
0x18000a03b  xor     ebx, ebx
0x18000a03d  test    eax, eax
0x18000a03f  jz      loc_180009F3F
0x18000a045  lea     rcx, [rbx+rbx*2]
0x18000a049  shl     rcx, 5
0x18000a04d  add     rcx, r13; Resource
0x18000a050  call    cs:__imp_RtlReleaseResource
0x18000a056  inc     ebx
0x18000a058  cmp     ebx, cs:SecPackageListLockCount
0x18000a05e  jb      short loc_18000A045
0x18000a060  jmp     loc_180009F3F
0x18000a065  lea     rcx, [rdi+rdi*2]
0x18000a069  shl     rcx, 5
0x18000a06d  add     rcx, r13; Resource
0x18000a070  call    cs:__imp_RtlReleaseResource
0x18000a076  inc     edi
0x18000a078  cmp     edi, cs:SecPackageListLockCount
0x18000a07e  jb      short loc_18000A065
0x18000a080  jmp     loc_180009DC3
0x18000a085  test    byte ptr [rsi+10h], 20h
0x18000a089  mov     rdi, rsi
0x18000a08c  jnz     loc_180009FE6
0x18000a092  jmp     loc_180009E3A
```
