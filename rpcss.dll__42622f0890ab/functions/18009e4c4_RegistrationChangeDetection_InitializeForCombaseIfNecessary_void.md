# RegistrationChangeDetection::InitializeForCombaseIfNecessary(void)

- ea: `0x18009e4c4`
- end: `0x18009e98e`
- name: `?InitializeForCombaseIfNecessary@RegistrationChangeDetection@@YAJXZ`
- size: `1226`
- prototype: `__int64 __fastcall(RegistrationChangeDetection *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800401c4`
- `0x18009e490`

## callees

- `0x180024cc4`
- `0x180031910`
- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x18006ca54`
- `0x1800814c8`
- `0x180098b54`
- `0x18009e4c4`
- `0x1800a261c`
- `0x1800c7190`
- `0x1800d3864`
- `0x1800d392c`
- `0x1800d3968`
- `0x1800d3af8`
- `0x1800d3b5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e8a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e8a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e85c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e85c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e70a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009e70a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18009e600`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18009e600`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e835`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e835`

## string_xrefs

- `0x18009e728`: `path:%ls`
- `0x18009e634`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18009e734`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18009e5db`: `onecore\com\combase\catalog\cache.cxx`
- `0x18009e6ce`: `onecore\com\combase\catalog\cache.cxx`
- `0x18009e7d2`: `onecore\com\combase\catalog\cache.cxx`
- `0x18009e5d2`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x18009e6c2`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x18009e7c9`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x18009e617`: `OpenCurrentUser: %!HRESULT!`
- `0x18009e648`: `OpenCurrentUser: %!HRESULT!`
- `0x18009e7b3`: `OpenCurrentUser: %!HRESULT!`
- `0x18009e5bc`: `SuspendImpersonate: %!HRESULT!`

## pseudocode

```c
__int64 __fastcall RegistrationChangeDetection::InitializeForCombaseIfNecessary(RegistrationChangeDetection *this)
{
  signed int v2; // ebx
  char v3; // r12
  bool v4; // r15
  LSTATUS v5; // eax
  signed int v6; // esi
  const unsigned __int16 *v7; // r9
  int v8; // r8d
  LSTATUS v9; // eax
  signed int v10; // esi
  int v11; // r8d
  LPVOID v12; // rax
  RegistrationChangeDetection::NotificationChecker *v13; // rax
  RegistrationChangeDetection::NotificationChecker *v14; // rsi
  signed int LastError; // eax
  __int64 v16; // rbx
  signed __int8 v17; // cl
  char v18; // tt
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22[8]; // [rsp+0h] [rbp-40h] BYREF
  PHKEY v23; // [rsp+20h] [rbp-20h]
  char *v24; // [rsp+28h] [rbp-18h]
  void **v25; // [rsp+30h] [rbp-10h] BYREF
  HANDLE EventW; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HKEY phkResult; // [rsp+80h] [rbp+40h] BYREF
  HANDLE Token; // [rsp+88h] [rbp+48h] BYREF
  HKEY v30; // [rsp+90h] [rbp+50h] BYREF

  switch ( byte_18014FBD0 )
  {
    case 10:
      return 2147500065LL;
    case 11:
      return 0;
    case 12:
      ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(qword_18014F278);
      v2 = RegistrationChangeDetection::NotificationChecker::RegisterNotification(*(_QWORD *)&qword_18014F278, &v25);
      if ( v2 >= 0 )
        byte_18014FBD0 = 11;
      ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(&v25);
      return (unsigned int)v2;
  }
  v2 = 0;
  v3 = 0;
  v4 = (g_GLBOPT_RoFlags & 0x100) == 0 && ProcessToken::IsUserHiveOk(this);
  v30 = 0;
  Token = 0;
  if ( !v4 )
    goto LABEL_73;
  v2 = SuspendImpersonate(&Token);
  if ( v2 >= 0 )
  {
    if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(3) )
      goto LABEL_21;
  }
  else if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
  {
    goto LABEL_73;
  }
  LODWORD(v24) = v2;
  ComTraceHr(
    v2,
    "onecore\\com\\combase\\catalog\\cache.cxx",
    "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
    840,
    L"SuspendImpersonate: %!HRESULT!",
    v24);
  if ( v2 < 0 )
    goto LABEL_73;
LABEL_21:
  phkResult = 0;
  v5 = RegOpenCurrentUser(0x20019u, &phkResult);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = L"OpenCurrentUser: %!HRESULT!";
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024894 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
      (const char *)(unsigned int)v6,
      (int)v23);
    v7 = L"OpenCurrentUser: %!HRESULT!";
    v2 = v6;
LABEL_31:
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
    {
LABEL_53:
      if ( v2 != -2147024894 )
        goto LABEL_54;
LABEL_56:
      v4 = 0;
      v2 = 0;
      goto LABEL_57;
    }
    goto LABEL_37;
  }
  v8 = gfEnableTracing;
  v2 = v6;
  if ( v6 != -2147024894 )
    goto LABEL_29;
  if ( !gfEnableTracing )
    goto LABEL_56;
  if ( !(unsigned __int8)IsWppLevelEnabled(3) )
  {
LABEL_29:
    if ( v6 >= 0 )
    {
      if ( !v8 || !(unsigned __int8)IsWppLevelEnabled(3) )
        goto LABEL_38;
      goto LABEL_37;
    }
    if ( v6 == -2147024894 )
      goto LABEL_53;
    goto LABEL_31;
  }
LABEL_37:
  LODWORD(v24) = v6;
  ComTraceHr(
    v6,
    "onecore\\com\\combase\\catalog\\cache.cxx",
    "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
    846,
    v7,
    v24);
  if ( v6 < 0 )
    goto LABEL_53;
LABEL_38:
  v9 = RegOpenKeyExW(phkResult, L"Software\\Classes", 0, 0x10u, &v30);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 == -2147024894 )
  {
    if ( !gfEnableTracing )
      goto LABEL_56;
    v2 = -2147024894;
    if ( (unsigned __int8)IsWppLevelEnabled(3) )
      goto LABEL_52;
  }
  else
  {
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\com\\combase\\inc\\RegistryKey.hpp",
      (const char *)(unsigned int)v10,
      (__int64)"path:%ls",
      (const char *)L"Software\\Classes");
    v11 = gfEnableTracing;
    v2 = v10;
  }
  if ( v10 >= 0 )
  {
    if ( !v11 || !(unsigned __int8)IsWppLevelEnabled(3) )
      goto LABEL_57;
LABEL_52:
    LODWORD(v24) = v10;
    ComTraceHr(
      v10,
      "onecore\\com\\combase\\catalog\\cache.cxx",
      "RegistrationChangeDetection::InitializeForCombaseIfNecessary",
      851,
      L"OpenCurrentUser: %!HRESULT!",
      v24);
    goto LABEL_53;
  }
  if ( v10 == -2147024894 )
    goto LABEL_53;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    goto LABEL_52;
LABEL_54:
  if ( v2 == -2147024891 )
    v3 = 1;
LABEL_57:
  RegistryKey::Close((RegistryKey *)&phkResult);
  if ( v4 && v2 >= 0 )
  {
    if ( *(_QWORD *)&qword_18014F278 )
    {
      _InterlockedOr(v22, 0);
    }
    else
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( EventW )
      {
        v12 = HeapAlloc(g_hHeap, 0, 0x40u);
        if ( v12
          && (v13 = (RegistrationChangeDetection::NotificationChecker *)RegistrationChangeDetection::NotificationChecker::NotificationChecker(
                                                                          v12,
                                                                          &v30,
                                                                          &v25),
              (v14 = v13) != 0) )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_18014F278, (signed __int64)v13, 0) )
          {
            RegistrationChangeDetection::NotificationChecker::~NotificationChecker(v13);
            HeapFree(g_hHeap, 0, v14);
          }
        }
        else
        {
          v2 = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( EventW
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v25) )
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
        JUMPOUT(0x18009E98DLL);
      }
      _InterlockedOr(v22, 0);
      if ( v2 < 0 )
        goto LABEL_73;
    }
    v16 = *(_QWORD *)&qword_18014F278;
    ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(qword_18014F278);
    v2 = RegistrationChangeDetection::NotificationChecker::RegisterNotification(v16, &v25);
    ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(&v25);
  }
LABEL_73:
  ResumeImpersonate(Token);
  Token = 0;
  while ( v2 >= 0 )
  {
    v17 = 11;
LABEL_81:
    v18 = byte_18014FBD0;
    if ( v18 == _InterlockedCompareExchange8(&byte_18014FBD0, v17, byte_18014FBD0) )
      goto LABEL_84;
  }
  if ( byte_18014FBD0 == 10 )
    goto LABEL_84;
  if ( (unsigned __int8)byte_18014FBD0 < 0xBu )
  {
    if ( v3 )
      v17 = 10;
    else
      v17 = byte_18014FBD0 + 1;
    goto LABEL_81;
  }
  v2 = 0;
LABEL_84:
  RegistryKey::Close((RegistryKey *)&v30);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18009e4c4  push    rbp
0x18009e4c6  push    rbx
0x18009e4c7  push    rsi
0x18009e4c8  push    r12
0x18009e4ca  push    r13
0x18009e4cc  push    r14
0x18009e4ce  push    r15
0x18009e4d0  mov     rbp, rsp
0x18009e4d3  sub     rsp, 40h
0x18009e4d7  mov     al, cs:byte_18014FBD0
0x18009e4dd  nop
0x18009e4de  cmp     al, 0Ah
0x18009e4e0  jnz     short loc_18009E4EC
0x18009e4e2  mov     eax, 80004021h
0x18009e4e7  jmp     loc_18009E966
0x18009e4ec  mov     r14d, 0Bh
0x18009e4f2  cmp     al, r14b
0x18009e4f5  jnz     short loc_18009E4FE
0x18009e4f7  xor     eax, eax
0x18009e4f9  jmp     loc_18009E966
0x18009e4fe  cmp     al, 0Ch
0x18009e500  jnz     short loc_18009E53D
0x18009e502  mov     rcx, cs:qword_18014F278; int
0x18009e509  lea     rdx, [rbp+var_10]
0x18009e50d  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x18009e512  mov     rcx, cs:qword_18014F278
0x18009e519  lea     rdx, [rbp+var_10]
0x18009e51d  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x18009e522  mov     ebx, eax
0x18009e524  test    eax, eax
0x18009e526  js      short loc_18009E52F
0x18009e528  xchg    r14b, cs:byte_18014FBD0
0x18009e52f  lea     rcx, [rbp+var_10]
0x18009e533  call    ??1LockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(void)
0x18009e538  jmp     loc_18009E964
0x18009e53d  xor     ebx, ebx
0x18009e53f  xor     r12b, r12b
0x18009e542  test    cs:?g_GLBOPT_RoFlags@@3KA, 100h; ulong g_GLBOPT_RoFlags
0x18009e54c  jz      short loc_18009E553
0x18009e54e  xor     r15b, r15b
0x18009e551  jmp     short loc_18009E55B
0x18009e553  call    ?IsUserHiveOk@ProcessToken@@QEAA_NXZ; ProcessToken::IsUserHiveOk(void)
0x18009e558  mov     r15b, al
0x18009e55b  mov     [rbp+arg_10], rbx
0x18009e55f  mov     [rbp+Token], rbx
0x18009e563  test    r15b, r15b
0x18009e566  jz      loc_18009E917
0x18009e56c  lea     rcx, [rbp+Token]; TokenHandle
0x18009e570  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18009e575  mov     ebx, eax
0x18009e577  mov     r13d, 80070000h
0x18009e57d  test    eax, eax
0x18009e57f  jns     short loc_18009E5A5
0x18009e581  mov     ecx, cs:dword_18014E4B8
0x18009e587  test    ecx, ecx
0x18009e589  jnz     short loc_18009E5BC
0x18009e58b  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18009e591  jz      loc_18009E917
0x18009e597  call    IsWppLevelEnabled
0x18009e59c  test    al, al
0x18009e59e  jnz     short loc_18009E5BC
0x18009e5a0  jmp     loc_18009E917
0x18009e5a5  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18009e5ac  jz      short loc_18009E5EF
0x18009e5ae  mov     ecx, 3
0x18009e5b3  call    IsWppLevelEnabled
0x18009e5b8  test    al, al
0x18009e5ba  jz      short loc_18009E5EF
0x18009e5bc  lea     rax, aSuspendimperso; "SuspendImpersonate: %!HRESULT!"
0x18009e5c3  mov     dword ptr [rsp+40h+var_18], ebx
0x18009e5c7  mov     r9d, 348h; int
0x18009e5cd  mov     [rsp+40h+var_20], rax; int
0x18009e5d2  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x18009e5d9  mov     ecx, ebx; int
0x18009e5db  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x18009e5e2  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18009e5e7  test    ebx, ebx
0x18009e5e9  js      loc_18009E917
0x18009e5ef  lea     rdx, [rbp+phkResult]; phkResult
0x18009e5f3  mov     [rbp+phkResult], 0
0x18009e5fb  mov     ecx, 20019h; samDesired
0x18009e600  call    cs:__imp_RegOpenCurrentUser
0x18009e606  mov     esi, eax
0x18009e608  test    eax, eax
0x18009e60a  jle     short loc_18009E612
0x18009e60c  movzx   esi, ax
0x18009e60f  or      esi, r13d
0x18009e612  mov     ecx, 80000000h
0x18009e617  lea     r9, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x18009e61e  mov     r13d, 80070002h
0x18009e624  lea     eax, [rsi+rcx]
0x18009e627  test    ecx, eax
0x18009e629  jnz     short loc_18009E653
0x18009e62b  cmp     esi, r13d
0x18009e62e  jz      short loc_18009E653
0x18009e630  mov     rcx, [rbp+38h]; this
0x18009e634  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18009e63b  mov     r9d, esi; char *
0x18009e63e  mov     edx, 178h; void *
0x18009e643  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009e648  lea     r9, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x18009e64f  mov     ebx, esi
0x18009e651  jmp     short loc_18009E685
0x18009e653  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18009e65a  mov     ebx, esi
0x18009e65c  cmp     esi, r13d
0x18009e65f  jnz     short loc_18009E678
0x18009e661  test    r8d, r8d
0x18009e664  jz      loc_18009E7F0
0x18009e66a  mov     ecx, 3
0x18009e66f  call    IsWppLevelEnabled
0x18009e674  test    al, al
0x18009e676  jnz     short loc_18009E6BE
0x18009e678  test    esi, esi
0x18009e67a  jns     short loc_18009E6AB
0x18009e67c  cmp     esi, r13d
0x18009e67f  jz      loc_18009E7DE
0x18009e685  mov     eax, cs:dword_18014E4B8
0x18009e68b  test    eax, eax
0x18009e68d  jnz     short loc_18009E6BE
0x18009e68f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18009e695  jz      loc_18009E7DE
0x18009e69b  xor     ecx, ecx
0x18009e69d  call    IsWppLevelEnabled
0x18009e6a2  test    al, al
0x18009e6a4  jnz     short loc_18009E6BE
0x18009e6a6  jmp     loc_18009E7DE
0x18009e6ab  test    r8d, r8d
0x18009e6ae  jz      short loc_18009E6EA
0x18009e6b0  mov     ecx, 3
0x18009e6b5  call    IsWppLevelEnabled
0x18009e6ba  test    al, al
0x18009e6bc  jz      short loc_18009E6EA
0x18009e6be  mov     dword ptr [rsp+40h+var_18], esi
0x18009e6c2  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x18009e6c9  mov     [rsp+40h+var_20], r9; unsigned __int16 *
0x18009e6ce  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x18009e6d5  mov     r9d, 34Eh; int
0x18009e6db  mov     ecx, esi; int
0x18009e6dd  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18009e6e2  test    esi, esi
0x18009e6e4  js      loc_18009E7DE
0x18009e6ea  mov     rcx, [rbp+phkResult]; hKey
0x18009e6ee  lea     rax, [rbp+arg_10]
0x18009e6f2  lea     rbx, aSoftwareClasse_0; "Software\\Classes"
0x18009e6f9  mov     [rsp+40h+var_20], rax; phkResult
0x18009e6fe  mov     rdx, rbx; lpSubKey
0x18009e701  mov     r9d, 10h; samDesired
0x18009e707  xor     r8d, r8d; ulOptions
0x18009e70a  call    cs:__imp_RegOpenKeyExW
0x18009e710  mov     esi, eax
0x18009e712  test    eax, eax
0x18009e714  jle     short loc_18009E71F
0x18009e716  movzx   esi, ax
0x18009e719  or      esi, 80070000h
0x18009e71f  cmp     esi, r13d
0x18009e722  jz      short loc_18009E758
0x18009e724  mov     rcx, [rbp+38h]; this
0x18009e728  lea     rax, aPathLs; "path:%ls"
0x18009e72f  mov     [rsp+40h+var_18], rbx; char *
0x18009e734  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18009e73b  mov     r9d, esi; char *
0x18009e73e  mov     [rsp+40h+var_20], rax; __int64
0x18009e743  mov     edx, 10Eh; void *
0x18009e748  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18009e74d  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18009e754  mov     ebx, esi
0x18009e756  jmp     short loc_18009E778
0x18009e758  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18009e75f  test    r8d, r8d
0x18009e762  jz      loc_18009E7F0
0x18009e768  mov     ecx, 3
0x18009e76d  mov     ebx, esi
0x18009e76f  call    IsWppLevelEnabled
0x18009e774  test    al, al
0x18009e776  jnz     short loc_18009E7B3
0x18009e778  test    esi, esi
0x18009e77a  jns     short loc_18009E7A0
0x18009e77c  cmp     esi, r13d
0x18009e77f  jz      short loc_18009E7DE
0x18009e781  mov     eax, cs:dword_18014E4B8
0x18009e787  test    eax, eax
0x18009e789  jnz     short loc_18009E7B3
0x18009e78b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18009e791  jz      short loc_18009E7E3
0x18009e793  xor     ecx, ecx
0x18009e795  call    IsWppLevelEnabled
0x18009e79a  test    al, al
0x18009e79c  jnz     short loc_18009E7B3
0x18009e79e  jmp     short loc_18009E7E3
0x18009e7a0  test    r8d, r8d
0x18009e7a3  jz      short loc_18009E7F5
0x18009e7a5  mov     ecx, 3
0x18009e7aa  call    IsWppLevelEnabled
0x18009e7af  test    al, al
0x18009e7b1  jz      short loc_18009E7F5
0x18009e7b3  lea     rax, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x18009e7ba  mov     dword ptr [rsp+40h+var_18], esi
0x18009e7be  mov     r9d, 353h; int
0x18009e7c4  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18009e7c9  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x18009e7d0  mov     ecx, esi; int
0x18009e7d2  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x18009e7d9  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18009e7de  cmp     ebx, r13d
0x18009e7e1  jz      short loc_18009E7F0
0x18009e7e3  cmp     ebx, 80070005h
0x18009e7e9  jnz     short loc_18009E7F5
0x18009e7eb  mov     r12b, 1
0x18009e7ee  jmp     short loc_18009E7F5
0x18009e7f0  xor     r15b, r15b
0x18009e7f3  xor     ebx, ebx
0x18009e7f5  lea     rcx, [rbp+phkResult]; this
0x18009e7f9  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x18009e7fe  test    r15b, r15b
0x18009e801  jz      loc_18009E917
0x18009e807  mov     r13d, 80070000h
0x18009e80d  test    ebx, ebx
0x18009e80f  js      loc_18009E917
0x18009e815  mov     rax, cs:qword_18014F278
0x18009e81c  test    rax, rax
0x18009e81f  jz      short loc_18009E82B
0x18009e821  lock or [rsp+40h+var_40], 0
0x18009e826  jmp     loc_18009E8ED
0x18009e82b  xor     r9d, r9d; lpName
0x18009e82e  xor     r8d, r8d; bInitialState
0x18009e831  xor     edx, edx; bManualReset
0x18009e833  xor     ecx, ecx; lpEventAttributes
0x18009e835  call    cs:__imp_CreateEventW
0x18009e83b  mov     [rbp+var_8], rax
0x18009e83f  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18009e846  mov     [rbp+var_10], rcx
0x18009e84a  test    rax, rax
0x18009e84d  jz      short loc_18009E8AF
0x18009e84f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e856  xor     edx, edx; dwFlags
0x18009e858  lea     r8d, [rdx+40h]; dwBytes
0x18009e85c  call    cs:__imp_HeapAlloc
0x18009e862  test    rax, rax
0x18009e865  jz      short loc_18009E8A8
0x18009e867  lea     r8, [rbp+var_10]
0x18009e86b  mov     rcx, rax
0x18009e86e  lea     rdx, [rbp+arg_10]
0x18009e872  call    ??0NotificationChecker@RegistrationChangeDetection@@QEAA@$$QEAVRegistryKey@@$$QEAVEvent@Wrappers@WRL@Microsoft@@@Z; RegistrationChangeDetection::NotificationChecker::NotificationChecker(RegistryKey &&,Microsoft::WRL::Wrappers::Event &&)
0x18009e877  mov     rsi, rax
0x18009e87a  test    rax, rax
0x18009e87d  jz      short loc_18009E8A8
0x18009e87f  xor     eax, eax
0x18009e881  lock cmpxchg cs:qword_18014F278, rsi
0x18009e88a  jz      short loc_18009E8C1
0x18009e88c  mov     rcx, rsi; this
0x18009e88f  call    ??1NotificationChecker@RegistrationChangeDetection@@QEAA@XZ; RegistrationChangeDetection::NotificationChecker::~NotificationChecker(void)
0x18009e894  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e89b  mov     r8, rsi; lpMem
0x18009e89e  xor     edx, edx; dwFlags
0x18009e8a0  call    cs:__imp_HeapFree
0x18009e8a6  jmp     short loc_18009E8C1
0x18009e8a8  mov     ebx, 8007000Eh
0x18009e8ad  jmp     short loc_18009E8C1
0x18009e8af  call    cs:__imp_GetLastError
0x18009e8b5  mov     ebx, eax
0x18009e8b7  test    eax, eax
0x18009e8b9  jle     short loc_18009E8C1
0x18009e8bb  movzx   ebx, ax
0x18009e8be  or      ebx, r13d
0x18009e8c1  cmp     [rbp+var_8], 0
0x18009e8c6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18009e8cd  mov     [rbp+var_10], rax
0x18009e8d1  jz      short loc_18009E8E4
0x18009e8d3  lea     rcx, [rbp+var_10]
0x18009e8d7  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18009e8dc  test    al, al
0x18009e8de  jz      loc_18009E976
0x18009e8e4  lock or [rsp+40h+var_40], 0
0x18009e8e9  test    ebx, ebx
0x18009e8eb  js      short loc_18009E917
0x18009e8ed  mov     rbx, cs:qword_18014F278
0x18009e8f4  lea     rdx, [rbp+var_10]
0x18009e8f8  mov     rcx, rbx; int
0x18009e8fb  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x18009e900  lea     rdx, [rbp+var_10]
0x18009e904  mov     rcx, rbx
0x18009e907  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x18009e90c  lea     rcx, [rbp+var_10]
0x18009e910  mov     ebx, eax
0x18009e912  call    ??1LockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(void)
0x18009e917  mov     rcx, [rbp+Token]; Token
0x18009e91b  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18009e920  mov     [rbp+Token], 0
0x18009e928  mov     al, cs:byte_18014FBD0
0x18009e92e  nop
0x18009e92f  test    ebx, ebx
0x18009e931  js      short loc_18009E938
0x18009e933  mov     cl, r14b
0x18009e936  jmp     short loc_18009E94D
0x18009e938  cmp     al, 0Ah
0x18009e93a  jz      short loc_18009E95B
0x18009e93c  cmp     al, r14b
0x18009e93f  jnb     short loc_18009E959
0x18009e941  test    r12b, r12b
  ... truncated ...
```
