# CContentProvidersHandler::Initialize(void)

- ea: `0x18000aa44`
- end: `0x18000aec8`
- name: `?Initialize@CContentProvidersHandler@@QEAAKXZ`
- size: `1156`
- prototype: `unsigned int __fastcall(CContentProvidersHandler *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800053a0`

## callees

- `0x18000967c`
- `0x180009ab8`
- `0x18000aa44`
- `0x18000aed0`
- `0x18001a9a8`
- `0x1800221d4`
- `0x180022210`
- `0x180022328`
- `0x1800224d4`
- `0x180022590`
- `0x180025850`
- `0x1800266a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ae4e`
- `KERNEL32!DeleteCriticalSection` at `0x18000ae4e`
- `KERNEL32!InitializeCriticalSection` at `0x18000ac81`
- `KERNEL32!InitializeCriticalSection` at `0x18000ac81`
- `ADVAPI32!RegCloseKey` at `0x18000ab01`
- `ADVAPI32!RegCloseKey` at `0x18000ae40`
- `ADVAPI32!RegCloseKey` at `0x18000ae81`
- `ADVAPI32!RegCloseKey` at `0x18000ae95`
- `ADVAPI32!RegCloseKey` at `0x18000ab01`
- `ADVAPI32!RegCloseKey` at `0x18000ae40`
- `ADVAPI32!RegCloseKey` at `0x18000ae81`
- `ADVAPI32!RegCloseKey` at `0x18000ae95`
- `ADVAPI32!RegQueryValueExW` at `0x18000ab70`
- `ADVAPI32!RegQueryValueExW` at `0x18000ab70`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aaa4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab28`
- `ADVAPI32!RegOpenKeyExW` at `0x18000aaa4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab28`

## string_xrefs

- `0x18000aa63`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Providers`
- `0x18000ab5d`: `ProviderDll`
- `0x18000ab9b`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CContentProvidersHandler::Initialize(CContentProvidersHandler *this)
{
  unsigned __int16 *v1; // r14
  WCHAR *v2; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  unsigned int ValueSz; // edi
  const char *v6; // rdx
  const char *v7; // rdx
  HKEY v8; // rbx
  unsigned __int16 *v9; // r15
  const char *v10; // rdx
  const unsigned __int16 *v11; // rdx
  unsigned int ValueExpSz; // eax
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  struct _RTL_CRITICAL_SECTION *v16; // rax
  const char *v17; // rdx
  HKEY LockSemaphore; // rcx
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LPCWCH lpWideCharStr; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-10h] BYREF
  void *v25; // [rsp+58h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  LPDWORD v27; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+58h] BYREF

  LODWORD(v27) = 1;
  v25 = 0;
  lpSubKey = 0;
  v1 = 0;
  v24 = 0;
  v2 = 0;
  lpWideCharStr = 0;
  v3 = 0;
  v28 = 0;
  phkResult = 0;
  hKey = 0;
  ValueSz = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Providers",
              0,
              0x20119u,
              &phkResult);
  if ( ElValidateWin32(ValueSz, v6, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x3Cu) )
    goto LABEL_49;
  ValueSz = CRegKey::EnumKeyFirst((CRegKey *)&phkResult, &v25);
  if ( ElValidateWin32(ValueSz, v7, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x40u) )
    goto LABEL_47;
  while ( 1 )
  {
    if ( CRegKey::EnumKeyNext((CRegKey *)&phkResult, v25, (unsigned __int16 **)&lpSubKey) )
    {
      v9 = (unsigned __int16 *)lpSubKey;
      goto LABEL_37;
    }
    v8 = phkResult;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v9 = (unsigned __int16 *)lpSubKey;
    ValueSz = RegOpenKeyExW(v8, lpSubKey, 0, 0x20119u, &hKey);
    if ( ElValidateWin32(ValueSz, v10, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x49u) )
      break;
    Type = 0;
    ValueSz = RegQueryValueExW(hKey, L"ProviderDll", 0, &Type, 0, 0);
    if ( ValueSz )
      goto LABEL_14;
    if ( Type == 2 )
    {
      ValueExpSz = CRegKey::GetValueExpSz((CRegKey *)&hKey, v11, &v24);
LABEL_12:
      v1 = v24;
      ValueSz = ValueExpSz;
      goto LABEL_14;
    }
    if ( Type == 1 )
    {
      ValueExpSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"ProviderDll", &v24);
      goto LABEL_12;
    }
    ValueSz = 1804;
LABEL_14:
    if ( ElValidateWin32(ValueSz, (const char *)v11, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x4Du) )
      break;
    ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"InitRoutine", (unsigned __int16 **)&lpWideCharStr);
    if ( ElValidateWin32(ValueSz, v13, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x53u)
      || (ValueSz = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"AllowUnauth", 0, &v28),
          ElValidateWin32(ValueSz, v14, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x5Au))
      || (ValueSz = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"IsCritical", 1u, (unsigned int *)&v27),
          ElValidateWin32(ValueSz, v15, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x61u)) )
    {
      v2 = (WCHAR *)lpWideCharStr;
      v3 = 0;
      goto LABEL_37;
    }
    v16 = (struct _RTL_CRITICAL_SECTION *)operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v16;
    if ( v16 )
    {
      InitializeCriticalSection(v16);
      v3[1].LockSemaphore = 0;
      v3[4].LockSemaphore = 0;
      v3[4].SpinCount = 0;
      v3[1].DebugInfo = 0;
      v3[1].OwningThread = 0;
      v3[1].LockCount = 0;
      LODWORD(v3[1].SpinCount) = 0;
      v3[2].DebugInfo = 0;
      *(_QWORD *)&v3[2].LockCount = 0;
      v3[2].OwningThread = 0;
      v3[2].LockSemaphore = 0;
      v3[2].SpinCount = 0;
      v3[3].DebugInfo = 0;
      *(_QWORD *)&v3[3].LockCount = 0;
      v3[3].OwningThread = 0;
      v3[3].LockSemaphore = 0;
      v3[3].SpinCount = 0;
      v3[4].DebugInfo = 0;
      *(_QWORD *)&v3[4].LockCount = 0;
      v3[4].OwningThread = 0;
      v3[1].RecursionCount = 0;
    }
    else
    {
      v3 = 0;
    }
    v2 = (WCHAR *)lpWideCharStr;
    if ( !v3 )
    {
      ValueSz = 8;
      goto LABEL_37;
    }
    ValueSz = CContentProvider::Initialize(v3, v9, v1, lpWideCharStr, v28, (int)v27);
    if ( ElValidateWin32(ValueSz, v17, "base\\eco\\wds\\transport\\server\\mc\\cpprovhdl.cpp", 0x73u) )
    {
      if ( (_DWORD)v27 )
        goto LABEL_37;
      ValueSz = 0;
    }
    else
    {
      if ( *(_QWORD *)this )
      {
        v3[4].LockSemaphore = 0;
        v3[4].SpinCount = *((_QWORD *)this + 1);
        *(_QWORD *)(*((_QWORD *)this + 1) + 184LL) = v3;
        *((_QWORD *)this + 1) = v3;
      }
      else
      {
        *((_QWORD *)this + 1) = v3;
        *(_QWORD *)this = v3;
        v3[4].LockSemaphore = 0;
        v3[4].SpinCount = 0;
      }
      ++*((_DWORD *)this + 5);
    }
    v3 = 0;
    if ( v9 )
    {
      operator delete(v9);
      lpSubKey = 0;
    }
    if ( v1 )
    {
      operator delete(v1);
      v1 = 0;
      v24 = 0;
    }
    if ( v2 )
    {
      operator delete(v2);
      v2 = 0;
      lpWideCharStr = 0;
    }
  }
  v3 = 0;
LABEL_37:
  if ( v9 )
    operator delete(v9);
  if ( v1 )
    operator delete(v1);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
  {
    CContentProvider::Shutdown(v3);
    LockSemaphore = (HKEY)v3[1].LockSemaphore;
    if ( LockSemaphore )
    {
      RegCloseKey(LockSemaphore);
      v3[1].LockSemaphore = 0;
    }
    DeleteCriticalSection(v3);
    operator delete(v3);
  }
LABEL_47:
  if ( v25 )
    operator delete(v25);
LABEL_49:
  if ( ValueSz )
    CContentProvidersHandler::Shutdown(this);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return ValueSz;
}

```

## disassembly

```asm
0x18000aa44  push    rbp
0x18000aa46  push    rbx
0x18000aa47  push    rsi
0x18000aa48  push    rdi
0x18000aa49  push    r12
0x18000aa4b  push    r14
0x18000aa4d  push    r15
0x18000aa4f  mov     rbp, rsp
0x18000aa52  sub     rsp, 60h
0x18000aa56  xor     eax, eax
0x18000aa58  mov     dword ptr [rbp+arg_10], 1
0x18000aa5f  mov     [rbp+var_8], rax
0x18000aa63  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\WD"...
0x18000aa6a  mov     [rbp+lpSubKey], rax
0x18000aa6e  mov     r14d, eax
0x18000aa71  mov     [rbp+var_10], rax
0x18000aa75  mov     esi, eax
0x18000aa77  mov     [rbp+lpWideCharStr], rax
0x18000aa7b  mov     ebx, eax
0x18000aa7d  mov     [rbp+arg_18], eax
0x18000aa80  mov     r12, rcx
0x18000aa83  mov     [rbp+var_18], rax
0x18000aa87  mov     r9d, 20119h; samDesired
0x18000aa8d  mov     [rbp+hKey], rax
0x18000aa91  xor     r8d, r8d; ulOptions
0x18000aa94  lea     rax, [rbp+var_18]
0x18000aa98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aa9f  mov     [rsp+60h+phkResult], rax; phkResult
0x18000aaa4  call    cs:__imp_RegOpenKeyExW
0x18000aaaa  mov     ecx, eax; unsigned int
0x18000aaac  lea     r9d, [rbx+3Ch]; unsigned int
0x18000aab0  lea     r8, aBaseEcoWdsTran_10; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000aab7  mov     edi, eax
0x18000aab9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000aabe  test    eax, eax
0x18000aac0  jnz     loc_18000AE6C
0x18000aac6  lea     rdx, [rbp+var_8]; void **
0x18000aaca  lea     rcx, [rbp+var_18]; this
0x18000aace  call    ?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z; CRegKey::EnumKeyFirst(void * *)
0x18000aad3  lea     r9d, [rbx+40h]; unsigned int
0x18000aad7  mov     ecx, eax; unsigned int
0x18000aad9  lea     r8, aBaseEcoWdsTran_10; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000aae0  mov     edi, eax
0x18000aae2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000aae7  test    eax, eax
0x18000aae9  jnz     loc_18000AE5C
0x18000aaef  jmp     loc_18000ADE6
0x18000aaf4  mov     rcx, [rbp+hKey]; hKey
0x18000aaf8  mov     rbx, [rbp+var_18]
0x18000aafc  test    rcx, rcx
0x18000aaff  jz      short loc_18000AB0C
0x18000ab01  call    cs:__imp_RegCloseKey
0x18000ab07  and     [rbp+hKey], 0
0x18000ab0c  mov     r15, [rbp+lpSubKey]
0x18000ab10  lea     rax, [rbp+hKey]
0x18000ab14  mov     rdx, r15; lpSubKey
0x18000ab17  mov     [rsp+60h+phkResult], rax; lpData
0x18000ab1c  mov     r9d, 20119h; samDesired
0x18000ab22  xor     r8d, r8d; ulOptions
0x18000ab25  mov     rcx, rbx; hKey
0x18000ab28  call    cs:__imp_RegOpenKeyExW
0x18000ab2e  lea     rbx, aBaseEcoWdsTran_10; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000ab35  mov     r9d, 49h ; 'I'; unsigned int
0x18000ab3b  mov     r8, rbx; char *
0x18000ab3e  mov     ecx, eax; unsigned int
0x18000ab40  mov     edi, eax
0x18000ab42  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ab47  test    eax, eax
0x18000ab49  jnz     loc_18000AEC1
0x18000ab4f  and     [rsp+60h+lpcbData], 0
0x18000ab55  lea     r9, [rbp+Type]; lpType
0x18000ab59  mov     rcx, [rbp+hKey]; hKey
0x18000ab5d  lea     rdx, ValueName; "ProviderDll"
0x18000ab64  and     [rsp+60h+phkResult], 0
0x18000ab6a  xor     r8d, r8d; lpReserved
0x18000ab6d  and     [rbp+Type], eax
0x18000ab70  call    cs:__imp_RegQueryValueExW
0x18000ab76  mov     edi, eax
0x18000ab78  test    eax, eax
0x18000ab7a  jnz     short loc_18000ABB8
0x18000ab7c  cmp     [rbp+Type], 2
0x18000ab80  jnz     short loc_18000AB91
0x18000ab82  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18000ab86  lea     rcx, [rbp+hKey]; this
0x18000ab8a  call    ?GetValueExpSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueExpSz(ushort const *,ushort * *)
0x18000ab8f  jmp     short loc_18000ABAB
0x18000ab91  cmp     [rbp+Type], 1
0x18000ab95  jnz     short loc_18000ABB3
0x18000ab97  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18000ab9b  lea     rdx, ValueName; "ProviderDll"
0x18000aba2  lea     rcx, [rbp+hKey]; this
0x18000aba6  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18000abab  mov     r14, [rbp+var_10]
0x18000abaf  mov     edi, eax
0x18000abb1  jmp     short loc_18000ABB8
0x18000abb3  mov     edi, 70Ch
0x18000abb8  mov     r9d, 4Dh ; 'M'; unsigned int
0x18000abbe  mov     r8, rbx; char *
0x18000abc1  mov     ecx, edi; unsigned int
0x18000abc3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000abc8  test    eax, eax
0x18000abca  jnz     loc_18000AEC1
0x18000abd0  lea     r8, [rbp+lpWideCharStr]; unsigned __int16 **
0x18000abd4  lea     rdx, aInitroutine; "InitRoutine"
0x18000abdb  lea     rcx, [rbp+hKey]; this
0x18000abdf  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18000abe4  mov     r9d, 53h ; 'S'; unsigned int
0x18000abea  mov     r8, rbx; char *
0x18000abed  mov     ecx, eax; unsigned int
0x18000abef  mov     edi, eax
0x18000abf1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000abf6  test    eax, eax
0x18000abf8  jnz     loc_18000AEB6
0x18000abfe  lea     r9, [rbp+arg_18]; unsigned int *
0x18000ac02  xor     r8d, r8d; unsigned int
0x18000ac05  lea     rdx, aAllowunauth; "AllowUnauth"
0x18000ac0c  lea     rcx, [rbp+hKey]; this
0x18000ac10  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000ac15  mov     r9d, 5Ah ; 'Z'; unsigned int
0x18000ac1b  mov     r8, rbx; char *
0x18000ac1e  mov     ecx, eax; unsigned int
0x18000ac20  mov     edi, eax
0x18000ac22  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ac27  test    eax, eax
0x18000ac29  jnz     loc_18000AEB6
0x18000ac2f  lea     r9, [rbp+arg_10]; unsigned int *
0x18000ac33  lea     r8d, [rax+1]; unsigned int
0x18000ac37  lea     rdx, aIscritical; "IsCritical"
0x18000ac3e  lea     rcx, [rbp+hKey]; this
0x18000ac42  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000ac47  mov     r9d, 61h ; 'a'; unsigned int
0x18000ac4d  mov     r8, rbx; char *
0x18000ac50  mov     ecx, eax; unsigned int
0x18000ac52  mov     edi, eax
0x18000ac54  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ac59  test    eax, eax
0x18000ac5b  jnz     loc_18000AEB6
0x18000ac61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac68  mov     ecx, 0C8h; unsigned __int64
0x18000ac6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac72  mov     rbx, rax
0x18000ac75  test    rax, rax
0x18000ac78  jz      loc_18000AD0A
0x18000ac7e  mov     rcx, rax; lpCriticalSection
0x18000ac81  call    cs:__imp_InitializeCriticalSection
0x18000ac87  and     qword ptr [rbx+40h], 0
0x18000ac8c  and     qword ptr [rbx+0B8h], 0
0x18000ac94  and     qword ptr [rbx+0C0h], 0
0x18000ac9c  and     qword ptr [rbx+28h], 0
0x18000aca1  and     qword ptr [rbx+38h], 0
0x18000aca6  and     dword ptr [rbx+30h], 0
0x18000acaa  and     dword ptr [rbx+48h], 0
0x18000acae  and     qword ptr [rbx+50h], 0
0x18000acb3  and     qword ptr [rbx+58h], 0
0x18000acb8  and     qword ptr [rbx+60h], 0
0x18000acbd  and     qword ptr [rbx+68h], 0
0x18000acc2  and     qword ptr [rbx+70h], 0
0x18000acc7  and     qword ptr [rbx+78h], 0
0x18000accc  and     qword ptr [rbx+80h], 0
0x18000acd4  and     qword ptr [rbx+88h], 0
0x18000acdc  and     qword ptr [rbx+90h], 0
0x18000ace4  and     qword ptr [rbx+98h], 0
0x18000acec  and     qword ptr [rbx+0A0h], 0
0x18000acf4  and     qword ptr [rbx+0A8h], 0
0x18000acfc  and     qword ptr [rbx+0B0h], 0
0x18000ad04  and     dword ptr [rbx+34h], 0
0x18000ad08  jmp     short loc_18000AD0C
0x18000ad0a  xor     ebx, ebx
0x18000ad0c  mov     rsi, [rbp+lpWideCharStr]
0x18000ad10  test    rbx, rbx
0x18000ad13  jz      loc_18000AEAC
0x18000ad19  mov     eax, dword ptr [rbp+arg_10]
0x18000ad1c  mov     r9, rsi; lpWideCharStr
0x18000ad1f  mov     dword ptr [rsp+60h+lpcbData], eax; int
0x18000ad23  mov     r8, r14; lpLibFileName
0x18000ad26  mov     eax, [rbp+arg_18]
0x18000ad29  mov     rdx, r15; unsigned __int16 *
0x18000ad2c  mov     rcx, rbx; lpCriticalSection
0x18000ad2f  mov     dword ptr [rsp+60h+phkResult], eax; int
0x18000ad33  call    ?Initialize@CContentProvider@@QEAAKPEBG00HH@Z; CContentProvider::Initialize(ushort const *,ushort const *,ushort const *,int,int)
0x18000ad38  mov     r9d, 73h ; 's'; unsigned int
0x18000ad3e  lea     r8, aBaseEcoWdsTran_10; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000ad45  mov     ecx, eax; unsigned int
0x18000ad47  mov     edi, eax
0x18000ad49  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ad4e  test    eax, eax
0x18000ad50  jz      short loc_18000AD60
0x18000ad52  cmp     dword ptr [rbp+arg_10], 0
0x18000ad56  jnz     loc_18000AE03
0x18000ad5c  xor     edi, edi
0x18000ad5e  jmp     short loc_18000ADAC
0x18000ad60  cmp     qword ptr [r12], 0
0x18000ad65  jnz     short loc_18000AD82
0x18000ad67  mov     [r12+8], rbx
0x18000ad6c  mov     [r12], rbx
0x18000ad70  and     qword ptr [rbx+0B8h], 0
0x18000ad78  and     qword ptr [rbx+0C0h], 0
0x18000ad80  jmp     short loc_18000ADA7
0x18000ad82  and     qword ptr [rbx+0B8h], 0
0x18000ad8a  mov     rax, [r12+8]
0x18000ad8f  mov     [rbx+0C0h], rax
0x18000ad96  mov     rax, [r12+8]
0x18000ad9b  mov     [rax+0B8h], rbx
0x18000ada2  mov     [r12+8], rbx
0x18000ada7  inc     dword ptr [r12+14h]
0x18000adac  xor     ebx, ebx
0x18000adae  test    r15, r15
0x18000adb1  jz      short loc_18000ADBF
0x18000adb3  mov     rcx, r15; void *
0x18000adb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000adbb  and     [rbp+lpSubKey], rbx
0x18000adbf  test    r14, r14
0x18000adc2  jz      short loc_18000ADD3
0x18000adc4  mov     rcx, r14; void *
0x18000adc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000adcc  xor     r14d, r14d
0x18000adcf  mov     [rbp+var_10], r14
0x18000add3  test    rsi, rsi
0x18000add6  jz      short loc_18000ADE6
0x18000add8  mov     rcx, rsi; void *
0x18000addb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ade0  xor     esi, esi
0x18000ade2  mov     [rbp+lpWideCharStr], rsi
0x18000ade6  mov     rdx, [rbp+var_8]; void *
0x18000adea  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18000adee  lea     rcx, [rbp+var_18]; this
0x18000adf2  call    ?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z; CRegKey::EnumKeyNext(void *,ushort * *)
0x18000adf7  test    eax, eax
0x18000adf9  jz      loc_18000AAF4
0x18000adff  mov     r15, [rbp+lpSubKey]
0x18000ae03  test    r15, r15
0x18000ae06  jz      short loc_18000AE10
0x18000ae08  mov     rcx, r15; void *
0x18000ae0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae10  test    r14, r14
0x18000ae13  jz      short loc_18000AE1D
0x18000ae15  mov     rcx, r14; void *
0x18000ae18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae1d  test    rsi, rsi
0x18000ae20  jz      short loc_18000AE2A
0x18000ae22  mov     rcx, rsi; void *
0x18000ae25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae2a  test    rbx, rbx
0x18000ae2d  jz      short loc_18000AE5C
0x18000ae2f  mov     rcx, rbx; lpCriticalSection
0x18000ae32  call    ?Shutdown@CContentProvider@@QEAAKXZ; CContentProvider::Shutdown(void)
0x18000ae37  mov     rcx, [rbx+40h]; hKey
0x18000ae3b  test    rcx, rcx
0x18000ae3e  jz      short loc_18000AE4B
0x18000ae40  call    cs:__imp_RegCloseKey
0x18000ae46  and     qword ptr [rbx+40h], 0
0x18000ae4b  mov     rcx, rbx; lpCriticalSection
0x18000ae4e  call    cs:__imp_DeleteCriticalSection
0x18000ae54  mov     rcx, rbx; void *
0x18000ae57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae5c  cmp     [rbp+var_8], 0
0x18000ae61  jz      short loc_18000AE6C
0x18000ae63  mov     rcx, [rbp+var_8]; void *
0x18000ae67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae6c  test    edi, edi
0x18000ae6e  jz      short loc_18000AE78
0x18000ae70  mov     rcx, r12; this
0x18000ae73  call    ?Shutdown@CContentProvidersHandler@@QEAAKXZ; CContentProvidersHandler::Shutdown(void)
0x18000ae78  mov     rcx, [rbp+hKey]; hKey
0x18000ae7c  test    rcx, rcx
0x18000ae7f  jz      short loc_18000AE8C
0x18000ae81  call    cs:__imp_RegCloseKey
0x18000ae87  and     [rbp+hKey], 0
0x18000ae8c  mov     rcx, [rbp+var_18]; hKey
0x18000ae90  test    rcx, rcx
0x18000ae93  jz      short loc_18000AE9B
0x18000ae95  call    cs:__imp_RegCloseKey
0x18000ae9b  mov     eax, edi
0x18000ae9d  add     rsp, 60h
0x18000aea1  pop     r15
0x18000aea3  pop     r14
0x18000aea5  pop     r12
0x18000aea7  pop     rdi
0x18000aea8  pop     rsi
0x18000aea9  pop     rbx
0x18000aeaa  pop     rbp
0x18000aeab  retn
0x18000aeac  mov     edi, 8
0x18000aeb1  jmp     loc_18000AE03
0x18000aeb6  mov     rsi, [rbp+lpWideCharStr]
0x18000aeba  xor     ebx, ebx
0x18000aebc  jmp     loc_18000AE03
0x18000aec1  xor     ebx, ebx
0x18000aec3  jmp     loc_18000AE03
```
