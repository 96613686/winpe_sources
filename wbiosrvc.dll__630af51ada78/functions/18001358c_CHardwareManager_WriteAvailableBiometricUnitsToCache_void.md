# CHardwareManager::WriteAvailableBiometricUnitsToCache(void)

- ea: `0x18001358c`
- end: `0x1800136e4`
- name: `?WriteAvailableBiometricUnitsToCache@CHardwareManager@@QEBAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CHardwareManager *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800447b0`
- `0x180045d10`

## callees

- `0x180011d90`
- `0x18001358c`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x1800148b4`
- `0x180014914`
- `0x180014fa4`
- `0x18005388c`
- `0x180058504`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001365b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001365b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800135bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800135bc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800136b2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800136b2`

## string_xrefs

- `0x1800135fa`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x1800136c4`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHardwareManager::WriteAvailableBiometricUnitsToCache(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 ***Ptr; // rdi
  __int64 **i; // rbx
  int WinBioRegistryLocation; // eax
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  const WCHAR *v13; // rax
  unsigned int v14; // eax
  int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  int Data; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Data = 0;
  v2 = this + 1;
  AcquireSRWLockShared(this + 1);
  Ptr = (__int64 ***)this[3].Ptr;
  for ( i = *Ptr; i != (__int64 **)Ptr; i = (__int64 **)*i )
  {
    if ( CBiometricUnit::ParentPoolType((CBiometricUnit *)i[2]) == 1 )
      Data |= *((_DWORD *)i[2] + 22);
  }
  if ( v2 )
    ReleaseSRWLockShared(v2);
  std::wstring::wstring(v18, v3, v4, v5);
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v18);
  v9 = WinBioRegistryLocation;
  if ( WinBioRegistryLocation >= 0 )
  {
    v11 = std::_WChar_traits<unsigned short>::length(L"SensorInfo\\");
    std::wstring::_Append<unsigned short>(v18, v12, v11);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    v14 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v13, L"AvailableFactors", 4u, &Data, 4u);
    if ( v14 )
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xC9B,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
             (const char *)v14,
             lpDataa);
    else
      v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC92,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      lpData);
  }
  std::wstring::_Tidy_deallocate(v18);
  return v9;
}

```

## disassembly

```asm
0x18001358c  mov     [rsp+arg_8], rbx
0x180013591  mov     [rsp+arg_10], rsi
0x180013596  push    rdi
0x180013597  sub     rsp, 60h
0x18001359b  mov     rax, cs:__security_cookie
0x1800135a2  xor     rax, rsp
0x1800135a5  mov     [rsp+68h+var_10], rax
0x1800135aa  mov     rdi, rcx
0x1800135ad  mov     [rsp+68h+Data], 0
0x1800135b5  lea     rsi, [rcx+8]
0x1800135b9  mov     rcx, rsi; SRWLock
0x1800135bc  call    cs:__imp_AcquireSRWLockShared
0x1800135c2  mov     rdi, [rdi+18h]
0x1800135c6  mov     rbx, [rdi]
0x1800135c9  cmp     rbx, rdi
0x1800135cc  jnz     short loc_180013637
0x1800135ce  test    rsi, rsi
0x1800135d1  jnz     loc_180013658
0x1800135d7  lea     rcx, [rsp+68h+var_30]
0x1800135dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800135e1  nop
0x1800135e2  lea     rcx, [rsp+68h+var_30]
0x1800135e7  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800135ec  mov     ebx, eax
0x1800135ee  test    eax, eax
0x1800135f0  jns     short loc_180013666
0x1800135f2  mov     rcx, [rsp+68h]; this
0x1800135f7  mov     r9d, eax; char *
0x1800135fa  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180013601  mov     edx, 0C92h; void *
0x180013606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001360b  nop
0x18001360c  lea     rcx, [rsp+68h+var_30]
0x180013611  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013616  mov     eax, ebx
0x180013618  mov     rcx, [rsp+68h+var_10]
0x18001361d  xor     rcx, rsp; StackCookie
0x180013620  call    __security_check_cookie
0x180013625  lea     r11, [rsp+68h+var_8]
0x18001362a  mov     rbx, [r11+18h]
0x18001362e  mov     rsi, [r11+20h]
0x180013632  mov     rsp, r11
0x180013635  pop     rdi
0x180013636  retn
0x180013637  mov     rcx, [rbx+10h]; this
0x18001363b  call    ?ParentPoolType@CBiometricUnit@@QEBAKXZ; CBiometricUnit::ParentPoolType(void)
0x180013640  cmp     eax, 1
0x180013643  jnz     short loc_180013650
0x180013645  mov     rax, [rbx+10h]
0x180013649  mov     ecx, [rax+58h]
0x18001364c  or      [rsp+68h+Data], ecx
0x180013650  mov     rbx, [rbx]
0x180013653  jmp     loc_1800135C9
0x180013658  mov     rcx, rsi; SRWLock
0x18001365b  call    cs:__imp_ReleaseSRWLockShared
0x180013661  jmp     loc_1800135D7
0x180013666  lea     rcx, aSensorinfo; "SensorInfo\\"
0x18001366d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180013672  mov     r8, rax
0x180013675  mov     rdx, rcx
0x180013678  lea     rcx, [rsp+68h+var_30]
0x18001367d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013682  lea     rcx, [rsp+68h+var_30]
0x180013687  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001368c  mov     rdx, rax; lpSubKey
0x18001368f  mov     r9d, 4; dwType
0x180013695  mov     [rsp+68h+cbData], r9d; cbData
0x18001369a  lea     rax, [rsp+68h+Data]
0x18001369f  mov     [rsp+68h+lpData], rax; unsigned int
0x1800136a4  lea     r8, ValueName; "AvailableFactors"
0x1800136ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800136b2  call    cs:__imp_RegSetKeyValueW
0x1800136b8  test    eax, eax
0x1800136ba  jz      short loc_1800136DC
0x1800136bc  mov     rcx, [rsp+68h]; this
0x1800136c1  mov     r9d, eax; char *
0x1800136c4  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x1800136cb  mov     edx, 0C9Bh; void *
0x1800136d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800136d5  mov     ebx, eax
0x1800136d7  jmp     loc_18001360C
0x1800136dc  xor     ebx, ebx
0x1800136de  jmp     loc_18001360C
```
