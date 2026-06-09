# OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18003e95c`
- end: `0x18003ec07`
- name: `?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `683`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *, PHKEY phkResult)`
- caller_count: `15`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bb98`
- `0x180024f94`
- `0x180026bfc`
- `0x18002a3f8`
- `0x18002fe70`
- `0x180030078`
- `0x1800301c4`
- `0x18003037c`
- `0x180030b04`
- `0x180031660`
- `0x180031bb4`
- `0x180031cec`
- `0x180033d44`
- `0x180039ff8`
- `0x18003a254`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012c50`
- `0x180012c9c`
- `0x180019210`
- `0x180019d4c`
- `0x180019db4`
- `0x18001dcf4`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ea06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ea06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003ea1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003ea1d`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003eb8a`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003eb8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003eaa6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003eaa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea82`
- `RPCRT4!RpcRevertToSelf` at `0x18003eb08`
- `RPCRT4!RpcRevertToSelf` at `0x18003eb08`
- `RPCRT4!RpcImpersonateClient` at `0x18003ea29`
- `RPCRT4!RpcImpersonateClient` at `0x18003ea29`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003eada`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ebb5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ebd3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003eada`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ebb5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ebd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OpenStorageRegKey(HKEY hKey, wchar_t *a2, PHKEY phkResult)
{
  unsigned __int64 v6; // rdx
  signed int v7; // ebx
  unsigned __int64 v8; // rdx
  int v9; // esi
  HANDLE CurrentThread; // rax
  unsigned int v11; // eax
  LSTATUS v12; // eax
  LSTATUS KeyW; // eax
  unsigned __int64 v14; // rdx
  int PersistedStateLocation; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v24[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v25[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  v21 = 520;
  v7 = StringCchCopyW(SubKey, 0x104u, L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters");
  if ( v7 >= 0 )
  {
    v7 = StringCchCatW(SubKey, v6, L"\\");
    if ( v7 >= 0 )
    {
      v7 = StringCchCatW(SubKey, v8, a2);
      if ( v7 >= 0 )
      {
        if ( hKey == HKEY_CURRENT_USER )
        {
          v9 = 0;
          TokenHandle = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &TokenHandle,
            0);
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
          {
            v11 = RpcImpersonateClient(0);
            if ( v11 )
            {
              v7 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0xE8,
                     (unsigned int)"onecore\\drivers\\storage\\storsvc\\treewalker\\desktopappscan.cpp",
                     (const char *)v11,
                     v19);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
              return (unsigned int)v7;
            }
            v9 = 1;
          }
          hKeya = 0;
          v12 = RegOpenCurrentUser(0xF003Fu, &hKeya);
          v7 = v12;
          if ( v12 > 0 )
            v7 = (unsigned __int16)v12 | 0x80070000;
          if ( v7 >= 0 )
          {
            KeyW = RegCreateKeyW(hKeya, SubKey, phkResult);
            v7 = KeyW;
            if ( KeyW > 0 )
              v7 = (unsigned __int16)KeyW | 0x80070000;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          if ( v9 )
            RpcRevertToSelf();
        }
        else if ( hKey == HKEY_LOCAL_MACHINE )
        {
          v7 = StringCchCopyW(v24, 0x104u, a2);
          if ( v7 >= 0 )
          {
            v7 = StringCchCatW(v24, v14, L"ID");
            if ( v7 >= 0 )
            {
              PersistedStateLocation = RtlGetPersistedStateLocation(v24, 0, SubKey, 0, v25, v21, &v21);
              v7 = PersistedStateLocation;
              if ( PersistedStateLocation > 0 )
                v7 = (unsigned __int16)PersistedStateLocation | 0x80070000;
              if ( v7 >= 0 )
              {
                v16 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v25, phkResult);
                v7 = v16;
                if ( v16 > 0 )
                  return (unsigned __int16)v16 | 0x80070000;
              }
            }
          }
        }
        else
        {
          v17 = RegCreateKeyW(hKey, SubKey, phkResult);
          v7 = v17;
          if ( v17 > 0 )
            return (unsigned __int16)v17 | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e95c  push    rbp
0x18003e95e  push    rbx
0x18003e95f  push    rsi
0x18003e960  push    rdi
0x18003e961  push    r14
0x18003e963  lea     rbp, [rsp-5A0h]
0x18003e96b  sub     rsp, 6A0h
0x18003e972  mov     rax, cs:__security_cookie
0x18003e979  xor     rax, rsp
0x18003e97c  mov     [rbp+5C0h+var_30], rax
0x18003e983  mov     r14, r8
0x18003e986  mov     rsi, rdx
0x18003e989  mov     rdi, rcx
0x18003e98c  mov     [rsp+6C0h+var_678], 208h
0x18003e994  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e99b  mov     edx, 104h; unsigned __int64
0x18003e9a0  lea     rcx, [rsp+6C0h+SubKey]; wchar_t *
0x18003e9a5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003e9aa  mov     ebx, eax
0x18003e9ac  test    eax, eax
0x18003e9ae  js      loc_18003EBE8
0x18003e9b4  lea     r8, asc_180092790; "\\"
0x18003e9bb  lea     rcx, [rsp+6C0h+SubKey]; unsigned __int16 *
0x18003e9c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e9c5  mov     ebx, eax
0x18003e9c7  test    eax, eax
0x18003e9c9  js      loc_18003EBE8
0x18003e9cf  mov     r8, rsi; unsigned __int16 *
0x18003e9d2  lea     rcx, [rsp+6C0h+SubKey]; unsigned __int16 *
0x18003e9d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e9dc  mov     ebx, eax
0x18003e9de  test    eax, eax
0x18003e9e0  js      loc_18003EBE8
0x18003e9e6  cmp     rdi, 0FFFFFFFF80000001h
0x18003e9ed  jnz     loc_18003EB13
0x18003e9f3  xor     esi, esi
0x18003e9f5  mov     [rsp+6C0h+TokenHandle], rsi
0x18003e9fa  xor     edx, edx
0x18003e9fc  lea     rcx, [rsp+6C0h+TokenHandle]
0x18003ea01  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003ea06  call    cs:__imp_GetCurrentThread
0x18003ea0c  lea     r9, [rsp+6C0h+TokenHandle]; TokenHandle
0x18003ea11  lea     ebx, [rsi+1]
0x18003ea14  mov     r8d, ebx; OpenAsSelf
0x18003ea17  lea     edx, [rsi+0Ch]; DesiredAccess
0x18003ea1a  mov     rcx, rax; ThreadHandle
0x18003ea1d  call    cs:__imp_OpenThreadToken
0x18003ea23  test    eax, eax
0x18003ea25  jnz     short loc_18003EA61
0x18003ea27  xor     ecx, ecx; BindingHandle
0x18003ea29  call    cs:__imp_RpcImpersonateClient
0x18003ea2f  test    eax, eax
0x18003ea31  jz      short loc_18003EA5F
0x18003ea33  mov     rcx, [rbp+5C8h]; this
0x18003ea3a  mov     r9d, eax; char *
0x18003ea3d  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\storage\\storsvc\\tre"...
0x18003ea44  mov     edx, 0E8h; void *
0x18003ea49  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ea4e  mov     ebx, eax
0x18003ea50  lea     rcx, [rsp+6C0h+TokenHandle]
0x18003ea55  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003ea5a  jmp     loc_18003EBE8
0x18003ea5f  mov     esi, ebx
0x18003ea61  mov     [rsp+6C0h+hKey], 0
0x18003ea6a  mov     rbx, [rsp+6C0h+hKey]
0x18003ea6f  test    rbx, rbx
0x18003ea72  jz      short loc_18003EA93
0x18003ea74  lea     rcx, [rsp+6C0h+var_668]; this
0x18003ea79  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ea7e  nop
0x18003ea7f  mov     rcx, rbx; hKey
0x18003ea82  call    cs:__imp_RegCloseKey
0x18003ea88  nop
0x18003ea89  lea     rcx, [rsp+6C0h+var_668]; this
0x18003ea8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003ea93  mov     [rsp+6C0h+hKey], 0
0x18003ea9c  lea     rdx, [rsp+6C0h+hKey]; phkResult
0x18003eaa1  mov     ecx, 0F003Fh; samDesired
0x18003eaa6  call    cs:__imp_RegOpenCurrentUser
0x18003eaac  mov     ebx, eax
0x18003eaae  mov     edi, 80070000h
0x18003eab3  test    eax, eax
0x18003eab5  jle     short loc_18003EABC
0x18003eab7  movzx   ebx, ax
0x18003eaba  or      ebx, edi
0x18003eabc  test    ebx, ebx
0x18003eabe  jns     short loc_18003EACD
0x18003eac0  lea     rcx, [rsp+6C0h+hKey]
0x18003eac5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eaca  nop
0x18003eacb  jmp     short loc_18003EAF6
0x18003eacd  mov     r8, r14; phkResult
0x18003ead0  lea     rdx, [rsp+6C0h+SubKey]; lpSubKey
0x18003ead5  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18003eada  call    cs:__imp_RegCreateKeyW
0x18003eae0  mov     ebx, eax
0x18003eae2  test    eax, eax
0x18003eae4  jle     short loc_18003EAEB
0x18003eae6  movzx   ebx, ax
0x18003eae9  or      ebx, edi
0x18003eaeb  lea     rcx, [rsp+6C0h+hKey]
0x18003eaf0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eaf5  nop
0x18003eaf6  lea     rcx, [rsp+6C0h+TokenHandle]
0x18003eafb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003eb00  test    esi, esi
0x18003eb02  jz      loc_18003EBE8
0x18003eb08  call    cs:__imp_RpcRevertToSelf
0x18003eb0e  jmp     loc_18003EBE8
0x18003eb13  cmp     rdi, 0FFFFFFFF80000002h
0x18003eb1a  jnz     loc_18003EBC8
0x18003eb20  mov     r8, rsi; wchar_t *
0x18003eb23  mov     edx, 104h; unsigned __int64
0x18003eb28  lea     rcx, [rbp+5C0h+var_450]; wchar_t *
0x18003eb2f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003eb34  mov     ebx, eax
0x18003eb36  test    eax, eax
0x18003eb38  js      loc_18003EBE8
0x18003eb3e  lea     r8, aId; "ID"
0x18003eb45  lea     rcx, [rbp+5C0h+var_450]; unsigned __int16 *
0x18003eb4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003eb51  mov     ebx, eax
0x18003eb53  test    eax, eax
0x18003eb55  js      loc_18003EBE8
0x18003eb5b  lea     rax, [rsp+6C0h+var_678]
0x18003eb60  mov     [rsp+6C0h+var_690], rax
0x18003eb65  mov     eax, [rsp+6C0h+var_678]
0x18003eb69  mov     [rsp+6C0h+var_698], eax
0x18003eb6d  lea     rax, [rbp+5C0h+var_240]
0x18003eb74  mov     [rsp+6C0h+var_6A0], rax
0x18003eb79  xor     r9d, r9d
0x18003eb7c  lea     r8, [rsp+6C0h+SubKey]
0x18003eb81  xor     edx, edx
0x18003eb83  lea     rcx, [rbp+5C0h+var_450]
0x18003eb8a  call    cs:__imp_RtlGetPersistedStateLocation
0x18003eb90  mov     ebx, eax
0x18003eb92  mov     edi, 80070000h
0x18003eb97  test    eax, eax
0x18003eb99  jle     short loc_18003EBA0
0x18003eb9b  movzx   ebx, ax
0x18003eb9e  or      ebx, edi
0x18003eba0  test    ebx, ebx
0x18003eba2  js      short loc_18003EBE8
0x18003eba4  mov     r8, r14; phkResult
0x18003eba7  lea     rdx, [rbp+5C0h+var_240]; lpSubKey
0x18003ebae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ebb5  call    cs:__imp_RegCreateKeyW
0x18003ebbb  mov     ebx, eax
0x18003ebbd  test    eax, eax
0x18003ebbf  jle     short loc_18003EBE8
0x18003ebc1  movzx   ebx, ax
0x18003ebc4  or      ebx, edi
0x18003ebc6  jmp     short loc_18003EBE8
0x18003ebc8  mov     r8, r14; phkResult
0x18003ebcb  lea     rdx, [rsp+6C0h+SubKey]; lpSubKey
0x18003ebd0  mov     rcx, rdi; hKey
0x18003ebd3  call    cs:__imp_RegCreateKeyW
0x18003ebd9  mov     ebx, eax
0x18003ebdb  test    eax, eax
0x18003ebdd  jle     short loc_18003EBE8
0x18003ebdf  movzx   ebx, ax
0x18003ebe2  or      ebx, 80070000h
0x18003ebe8  mov     eax, ebx
0x18003ebea  mov     rcx, [rbp+5C0h+var_30]
0x18003ebf1  xor     rcx, rsp; StackCookie
0x18003ebf4  call    __security_check_cookie
0x18003ebf9  add     rsp, 6A0h
0x18003ec00  pop     r14
0x18003ec02  pop     rdi
0x18003ec03  pop     rsi
0x18003ec04  pop     rbx
0x18003ec05  pop     rbp
0x18003ec06  retn
```
