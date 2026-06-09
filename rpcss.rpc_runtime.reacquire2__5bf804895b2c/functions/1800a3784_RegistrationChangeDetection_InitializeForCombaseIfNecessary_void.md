# RegistrationChangeDetection::InitializeForCombaseIfNecessary(void)

- ea: `0x1800a3784`
- end: `0x1800a3c79`
- name: `?InitializeForCombaseIfNecessary@RegistrationChangeDetection@@YAJXZ`
- size: `1269`
- prototype: `__int64 __fastcall(RegistrationChangeDetection *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180049c58`
- `0x1800a3750`

## callees

- `0x18002efd4`
- `0x180034260`
- `0x18003ca38`
- `0x18004ab7c`
- `0x18004ac08`
- `0x180064120`
- `0x180072c6c`
- `0x180090234`
- `0x180091a10`
- `0x18009e160`
- `0x1800a3784`
- `0x1800cd1e0`
- `0x1800da214`
- `0x1800da348`
- `0x1800da4a8`
- `0x1800da51c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3b78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a3b78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3b2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3b2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a39d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a39d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800a38c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800a38c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3b01`

## string_xrefs

- `0x1800a39f4`: `path:%ls`
- `0x1800a38fa`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x1800a3a00`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x1800a389b`: `onecore\com\combase\catalog\cache.cxx`
- `0x1800a3994`: `onecore\com\combase\catalog\cache.cxx`
- `0x1800a3a9e`: `onecore\com\combase\catalog\cache.cxx`
- `0x1800a38dd`: `OpenCurrentUser: %!HRESULT!`
- `0x1800a390e`: `OpenCurrentUser: %!HRESULT!`
- `0x1800a3a7f`: `OpenCurrentUser: %!HRESULT!`
- `0x1800a387c`: `SuspendImpersonate: %!HRESULT!`
- `0x1800a3892`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x1800a3988`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`
- `0x1800a3a95`: `RegistrationChangeDetection::InitializeForCombaseIfNecessary`

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

  switch ( byte_180158CD8 )
  {
    case 10:
      return 2147500065LL;
    case 11:
      return 0;
    case 12:
      ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(qword_180158378);
      v2 = RegistrationChangeDetection::NotificationChecker::RegisterNotification(*(_QWORD *)&qword_180158378, &v25);
      if ( v2 >= 0 )
        byte_180158CD8 = 11;
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
  else if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
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
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    goto LABEL_52;
LABEL_54:
  if ( v2 == -2147024891 )
    v3 = 1;
LABEL_57:
  RegistryKey::Close((RegistryKey *)&phkResult);
  if ( v4 && v2 >= 0 )
  {
    if ( *(_QWORD *)&qword_180158378 )
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
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_180158378, (signed __int64)v13, 0) )
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
        JUMPOUT(0x1800A3C78LL);
      }
      _InterlockedOr(v22, 0);
      if ( v2 < 0 )
        goto LABEL_73;
    }
    v16 = *(_QWORD *)&qword_180158378;
    ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(qword_180158378);
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
    v18 = byte_180158CD8;
    if ( v18 == _InterlockedCompareExchange8(&byte_180158CD8, v17, byte_180158CD8) )
      goto LABEL_84;
  }
  if ( byte_180158CD8 == 10 )
    goto LABEL_84;
  if ( (unsigned __int8)byte_180158CD8 < 0xBu )
  {
    if ( v3 )
      v17 = 10;
    else
      v17 = byte_180158CD8 + 1;
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
0x1800a3784  push    rbp
0x1800a3786  push    rbx
0x1800a3787  push    rsi
0x1800a3788  push    r12
0x1800a378a  push    r13
0x1800a378c  push    r14
0x1800a378e  push    r15
0x1800a3790  mov     rbp, rsp
0x1800a3793  sub     rsp, 40h
0x1800a3797  mov     al, cs:byte_180158CD8
0x1800a379d  nop
0x1800a379e  cmp     al, 0Ah
0x1800a37a0  jnz     short loc_1800A37AC
0x1800a37a2  mov     eax, 80004021h
0x1800a37a7  jmp     loc_1800A3C4A
0x1800a37ac  mov     r14d, 0Bh
0x1800a37b2  cmp     al, r14b
0x1800a37b5  jnz     short loc_1800A37BE
0x1800a37b7  xor     eax, eax
0x1800a37b9  jmp     loc_1800A3C4A
0x1800a37be  cmp     al, 0Ch
0x1800a37c0  jnz     short loc_1800A37FD
0x1800a37c2  mov     rcx, cs:qword_180158378; int
0x1800a37c9  lea     rdx, [rbp+var_10]
0x1800a37cd  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x1800a37d2  mov     rcx, cs:qword_180158378
0x1800a37d9  lea     rdx, [rbp+var_10]
0x1800a37dd  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x1800a37e2  mov     ebx, eax
0x1800a37e4  test    eax, eax
0x1800a37e6  js      short loc_1800A37EF
0x1800a37e8  xchg    r14b, cs:byte_180158CD8
0x1800a37ef  lea     rcx, [rbp+var_10]
0x1800a37f3  call    ??1LockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(void)
0x1800a37f8  jmp     loc_1800A3C48
0x1800a37fd  xor     ebx, ebx
0x1800a37ff  xor     r12b, r12b
0x1800a3802  test    cs:?g_GLBOPT_RoFlags@@3KA, 100h; ulong g_GLBOPT_RoFlags
0x1800a380c  jz      short loc_1800A3813
0x1800a380e  xor     r15b, r15b
0x1800a3811  jmp     short loc_1800A381B
0x1800a3813  call    ?IsUserHiveOk@ProcessToken@@QEAA_NXZ; ProcessToken::IsUserHiveOk(void)
0x1800a3818  mov     r15b, al
0x1800a381b  mov     [rbp+arg_10], rbx
0x1800a381f  mov     [rbp+Token], rbx
0x1800a3823  test    r15b, r15b
0x1800a3826  jz      loc_1800A3BFB
0x1800a382c  lea     rcx, [rbp+Token]; TokenHandle
0x1800a3830  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800a3835  mov     ebx, eax
0x1800a3837  mov     r13d, 80070000h
0x1800a383d  test    eax, eax
0x1800a383f  jns     short loc_1800A3865
0x1800a3841  mov     ecx, cs:dword_1801574B8
0x1800a3847  test    ecx, ecx
0x1800a3849  jnz     short loc_1800A387C
0x1800a384b  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800a3851  jz      loc_1800A3BFB
0x1800a3857  call    IsWppLevelEnabled
0x1800a385c  test    al, al
0x1800a385e  jnz     short loc_1800A387C
0x1800a3860  jmp     loc_1800A3BFB
0x1800a3865  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800a386c  jz      short loc_1800A38AF
0x1800a386e  mov     ecx, 3
0x1800a3873  call    IsWppLevelEnabled
0x1800a3878  test    al, al
0x1800a387a  jz      short loc_1800A38AF
0x1800a387c  lea     rax, aSuspendimperso; "SuspendImpersonate: %!HRESULT!"
0x1800a3883  mov     dword ptr [rsp+40h+var_18], ebx
0x1800a3887  mov     r9d, 348h; int
0x1800a388d  mov     [rsp+40h+var_20], rax; int
0x1800a3892  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x1800a3899  mov     ecx, ebx; int
0x1800a389b  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x1800a38a2  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800a38a7  test    ebx, ebx
0x1800a38a9  js      loc_1800A3BFB
0x1800a38af  lea     rdx, [rbp+phkResult]; phkResult
0x1800a38b3  mov     [rbp+phkResult], 0
0x1800a38bb  mov     ecx, 20019h; samDesired
0x1800a38c0  call    cs:__imp_RegOpenCurrentUser
0x1800a38c7  nop     dword ptr [rax+rax+00h]
0x1800a38cc  mov     esi, eax
0x1800a38ce  test    eax, eax
0x1800a38d0  jle     short loc_1800A38D8
0x1800a38d2  movzx   esi, ax
0x1800a38d5  or      esi, r13d
0x1800a38d8  mov     ecx, 80000000h
0x1800a38dd  lea     r9, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x1800a38e4  mov     r13d, 80070002h
0x1800a38ea  lea     eax, [rsi+rcx]
0x1800a38ed  test    ecx, eax
0x1800a38ef  jnz     short loc_1800A3919
0x1800a38f1  cmp     esi, r13d
0x1800a38f4  jz      short loc_1800A3919
0x1800a38f6  mov     rcx, [rbp+38h]; this
0x1800a38fa  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x1800a3901  mov     r9d, esi; char *
0x1800a3904  mov     edx, 178h; void *
0x1800a3909  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a390e  lea     r9, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x1800a3915  mov     ebx, esi
0x1800a3917  jmp     short loc_1800A394B
0x1800a3919  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800a3920  mov     ebx, esi
0x1800a3922  cmp     esi, r13d
0x1800a3925  jnz     short loc_1800A393E
0x1800a3927  test    r8d, r8d
0x1800a392a  jz      loc_1800A3ABC
0x1800a3930  mov     ecx, 3
0x1800a3935  call    IsWppLevelEnabled
0x1800a393a  test    al, al
0x1800a393c  jnz     short loc_1800A3984
0x1800a393e  test    esi, esi
0x1800a3940  jns     short loc_1800A3971
0x1800a3942  cmp     esi, r13d
0x1800a3945  jz      loc_1800A3AAA
0x1800a394b  mov     eax, cs:dword_1801574B8
0x1800a3951  test    eax, eax
0x1800a3953  jnz     short loc_1800A3984
0x1800a3955  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800a395b  jz      loc_1800A3AAA
0x1800a3961  xor     ecx, ecx
0x1800a3963  call    IsWppLevelEnabled
0x1800a3968  test    al, al
0x1800a396a  jnz     short loc_1800A3984
0x1800a396c  jmp     loc_1800A3AAA
0x1800a3971  test    r8d, r8d
0x1800a3974  jz      short loc_1800A39B0
0x1800a3976  mov     ecx, 3
0x1800a397b  call    IsWppLevelEnabled
0x1800a3980  test    al, al
0x1800a3982  jz      short loc_1800A39B0
0x1800a3984  mov     dword ptr [rsp+40h+var_18], esi
0x1800a3988  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x1800a398f  mov     [rsp+40h+var_20], r9; unsigned __int16 *
0x1800a3994  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x1800a399b  mov     r9d, 34Eh; int
0x1800a39a1  mov     ecx, esi; int
0x1800a39a3  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800a39a8  test    esi, esi
0x1800a39aa  js      loc_1800A3AAA
0x1800a39b0  mov     rcx, [rbp+phkResult]; hKey
0x1800a39b4  lea     rax, [rbp+arg_10]
0x1800a39b8  lea     rbx, aSoftwareClasse_0; "Software\\Classes"
0x1800a39bf  mov     [rsp+40h+var_20], rax; phkResult
0x1800a39c4  mov     rdx, rbx; lpSubKey
0x1800a39c7  mov     r9d, 10h; samDesired
0x1800a39cd  xor     r8d, r8d; ulOptions
0x1800a39d0  call    cs:__imp_RegOpenKeyExW
0x1800a39d7  nop     dword ptr [rax+rax+00h]
0x1800a39dc  mov     esi, eax
0x1800a39de  test    eax, eax
0x1800a39e0  jle     short loc_1800A39EB
0x1800a39e2  movzx   esi, ax
0x1800a39e5  or      esi, 80070000h
0x1800a39eb  cmp     esi, r13d
0x1800a39ee  jz      short loc_1800A3A24
0x1800a39f0  mov     rcx, [rbp+38h]; this
0x1800a39f4  lea     rax, aPathLs; "path:%ls"
0x1800a39fb  mov     [rsp+40h+var_18], rbx; char *
0x1800a3a00  lea     r8, aOnecoreComComb_7; "onecore\\com\\combase\\inc\\RegistryKey"...
0x1800a3a07  mov     r9d, esi; char *
0x1800a3a0a  mov     [rsp+40h+var_20], rax; __int64
0x1800a3a0f  mov     edx, 10Eh; void *
0x1800a3a14  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800a3a19  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800a3a20  mov     ebx, esi
0x1800a3a22  jmp     short loc_1800A3A44
0x1800a3a24  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800a3a2b  test    r8d, r8d
0x1800a3a2e  jz      loc_1800A3ABC
0x1800a3a34  mov     ecx, 3
0x1800a3a39  mov     ebx, esi
0x1800a3a3b  call    IsWppLevelEnabled
0x1800a3a40  test    al, al
0x1800a3a42  jnz     short loc_1800A3A7F
0x1800a3a44  test    esi, esi
0x1800a3a46  jns     short loc_1800A3A6C
0x1800a3a48  cmp     esi, r13d
0x1800a3a4b  jz      short loc_1800A3AAA
0x1800a3a4d  mov     eax, cs:dword_1801574B8
0x1800a3a53  test    eax, eax
0x1800a3a55  jnz     short loc_1800A3A7F
0x1800a3a57  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800a3a5d  jz      short loc_1800A3AAF
0x1800a3a5f  xor     ecx, ecx
0x1800a3a61  call    IsWppLevelEnabled
0x1800a3a66  test    al, al
0x1800a3a68  jnz     short loc_1800A3A7F
0x1800a3a6a  jmp     short loc_1800A3AAF
0x1800a3a6c  test    r8d, r8d
0x1800a3a6f  jz      short loc_1800A3AC1
0x1800a3a71  mov     ecx, 3
0x1800a3a76  call    IsWppLevelEnabled
0x1800a3a7b  test    al, al
0x1800a3a7d  jz      short loc_1800A3AC1
0x1800a3a7f  lea     rax, aOpencurrentuse; "OpenCurrentUser: %!HRESULT!"
0x1800a3a86  mov     dword ptr [rsp+40h+var_18], esi
0x1800a3a8a  mov     r9d, 353h; int
0x1800a3a90  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x1800a3a95  lea     r8, aRegistrationch_0; "RegistrationChangeDetection::Initialize"...
0x1800a3a9c  mov     ecx, esi; int
0x1800a3a9e  lea     rdx, aOnecoreComComb_76; "onecore\\com\\combase\\catalog\\cache.c"...
0x1800a3aa5  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800a3aaa  cmp     ebx, r13d
0x1800a3aad  jz      short loc_1800A3ABC
0x1800a3aaf  cmp     ebx, 80070005h
0x1800a3ab5  jnz     short loc_1800A3AC1
0x1800a3ab7  mov     r12b, 1
0x1800a3aba  jmp     short loc_1800A3AC1
0x1800a3abc  xor     r15b, r15b
0x1800a3abf  xor     ebx, ebx
0x1800a3ac1  lea     rcx, [rbp+phkResult]; this
0x1800a3ac5  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x1800a3aca  test    r15b, r15b
0x1800a3acd  jz      loc_1800A3BFB
0x1800a3ad3  mov     r13d, 80070000h
0x1800a3ad9  test    ebx, ebx
0x1800a3adb  js      loc_1800A3BFB
0x1800a3ae1  mov     rax, cs:qword_180158378
0x1800a3ae8  test    rax, rax
0x1800a3aeb  jz      short loc_1800A3AF7
0x1800a3aed  lock or [rsp+40h+var_40], 0
0x1800a3af2  jmp     loc_1800A3BD1
0x1800a3af7  xor     r9d, r9d; lpName
0x1800a3afa  xor     r8d, r8d; bInitialState
0x1800a3afd  xor     edx, edx; bManualReset
0x1800a3aff  xor     ecx, ecx; lpEventAttributes
0x1800a3b01  call    cs:__imp_CreateEventW
0x1800a3b08  nop     dword ptr [rax+rax+00h]
0x1800a3b0d  mov     [rbp+var_8], rax
0x1800a3b11  lea     rcx, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800a3b18  mov     [rbp+var_10], rcx
0x1800a3b1c  test    rax, rax
0x1800a3b1f  jz      short loc_1800A3B8D
0x1800a3b21  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a3b28  xor     edx, edx; dwFlags
0x1800a3b2a  lea     r8d, [rdx+40h]; dwBytes
0x1800a3b2e  call    cs:__imp_HeapAlloc
0x1800a3b35  nop     dword ptr [rax+rax+00h]
0x1800a3b3a  test    rax, rax
0x1800a3b3d  jz      short loc_1800A3B86
0x1800a3b3f  lea     r8, [rbp+var_10]
0x1800a3b43  mov     rcx, rax
0x1800a3b46  lea     rdx, [rbp+arg_10]
0x1800a3b4a  call    ??0NotificationChecker@RegistrationChangeDetection@@QEAA@$$QEAVRegistryKey@@$$QEAVEvent@Wrappers@WRL@Microsoft@@@Z; RegistrationChangeDetection::NotificationChecker::NotificationChecker(RegistryKey &&,Microsoft::WRL::Wrappers::Event &&)
0x1800a3b4f  mov     rsi, rax
0x1800a3b52  test    rax, rax
0x1800a3b55  jz      short loc_1800A3B86
0x1800a3b57  xor     eax, eax
0x1800a3b59  lock cmpxchg cs:qword_180158378, rsi
0x1800a3b62  jz      short loc_1800A3BA5
0x1800a3b64  mov     rcx, rsi; this
0x1800a3b67  call    ??1NotificationChecker@RegistrationChangeDetection@@QEAA@XZ; RegistrationChangeDetection::NotificationChecker::~NotificationChecker(void)
0x1800a3b6c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a3b73  mov     r8, rsi; lpMem
0x1800a3b76  xor     edx, edx; dwFlags
0x1800a3b78  call    cs:__imp_HeapFree
0x1800a3b7f  nop     dword ptr [rax+rax+00h]
0x1800a3b84  jmp     short loc_1800A3BA5
0x1800a3b86  mov     ebx, 8007000Eh
0x1800a3b8b  jmp     short loc_1800A3BA5
0x1800a3b8d  call    cs:__imp_GetLastError
0x1800a3b94  nop     dword ptr [rax+rax+00h]
0x1800a3b99  mov     ebx, eax
0x1800a3b9b  test    eax, eax
0x1800a3b9d  jle     short loc_1800A3BA5
0x1800a3b9f  movzx   ebx, ax
0x1800a3ba2  or      ebx, r13d
0x1800a3ba5  cmp     [rbp+var_8], 0
0x1800a3baa  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800a3bb1  mov     [rbp+var_10], rax
0x1800a3bb5  jz      short loc_1800A3BC8
0x1800a3bb7  lea     rcx, [rbp+var_10]
0x1800a3bbb  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800a3bc0  test    al, al
0x1800a3bc2  jz      loc_1800A3C5B
0x1800a3bc8  lock or [rsp+40h+var_40], 0
0x1800a3bcd  test    ebx, ebx
0x1800a3bcf  js      short loc_1800A3BFB
0x1800a3bd1  mov     rbx, cs:qword_180158378
0x1800a3bd8  lea     rdx, [rbp+var_10]
0x1800a3bdc  mov     rcx, rbx; int
0x1800a3bdf  call    ?Lock@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA?AVLockWrapper@123@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::Lock(void)
0x1800a3be4  lea     rdx, [rbp+var_10]
0x1800a3be8  mov     rcx, rbx
0x1800a3beb  call    ?RegisterNotification@NotificationChecker@RegistrationChangeDetection@@QEAAJAEBVLockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@@Z; RegistrationChangeDetection::NotificationChecker::RegisterNotification(ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper const &)
0x1800a3bf0  lea     rcx, [rbp+var_10]
0x1800a3bf4  mov     ebx, eax
0x1800a3bf6  call    ??1LockWrapper@?$LockableHelper@VNil@Details@ObjectLibrary@@V?$AddAllocation@U?$AllocationOptions@UPrivMemAllocator@@$0A@VNil@Details@ObjectLibrary@@@ObjectLibrary@@VNil@Details@2@V342@@3@@Details@ObjectLibrary@@QEAA@XZ; ObjectLibrary::Details::LockableHelper<ObjectLibrary::Details::Nil,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,0,ObjectLibrary::Details::Nil>,ObjectLibrary::Details::Nil,ObjectLibrary::Details::Nil>>::LockWrapper::~LockWrapper(void)
0x1800a3bfb  mov     rcx, [rbp+Token]; Token
0x1800a3bff  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800a3c04  mov     [rbp+Token], 0
0x1800a3c0c  mov     al, cs:byte_180158CD8
0x1800a3c12  nop
0x1800a3c13  test    ebx, ebx
0x1800a3c15  js      short loc_1800A3C1C
0x1800a3c17  mov     cl, r14b
  ... truncated ...
```
