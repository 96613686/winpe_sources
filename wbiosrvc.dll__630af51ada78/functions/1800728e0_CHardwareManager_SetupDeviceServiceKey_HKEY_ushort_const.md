# CHardwareManager::SetupDeviceServiceKey(HKEY__ *,ushort const *)

- ea: `0x1800728e0`
- end: `0x1800729df`
- name: `?SetupDeviceServiceKey@CHardwareManager@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(CHardwareManager *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180041c14`

## callees

- `0x18001434c`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180068f60`
- `0x1800728e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072991`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800729ce`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800729ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072970`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180072970`

## string_xrefs

- `0x18007290b`: `System\CurrentControlSet\Services\WbioSrvc\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHardwareManager::SetupDeviceServiceKey(CHardwareManager *this, HKEY a2, const unsigned __int16 *a3)
{
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-30h] BYREF

  hKey = 0;
  std::wstring::wstring(v10, L"System\\CurrentControlSet\\Services\\WbioSrvc\\");
  std::wstring::append(v10, a3);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v7 = 0;
  v6 = RegCopyTreeW(a2, 0, hKey);
  if ( v6 )
  {
    if ( v6 > 0 )
    {
LABEL_3:
      v7 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_4;
    }
    v7 = v6;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(v10);
  return v7;
}

```

## disassembly

```asm
0x1800728e0  mov     [rsp+arg_0], rbx
0x1800728e5  push    rdi
0x1800728e6  sub     rsp, 80h
0x1800728ed  mov     rax, cs:__security_cookie
0x1800728f4  xor     rax, rsp
0x1800728f7  mov     [rsp+88h+var_10], rax
0x1800728fc  mov     rbx, r8
0x1800728ff  mov     rdi, rdx
0x180072902  mov     [rsp+88h+hKey], 0
0x18007290b  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Wb"...
0x180072912  lea     rcx, [rsp+88h+var_30]
0x180072917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007291c  nop
0x18007291d  mov     rdx, rbx
0x180072920  lea     rcx, [rsp+88h+var_30]
0x180072925  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007292a  lea     rcx, [rsp+88h+var_30]
0x18007292f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072934  mov     rdx, rax; lpSubKey
0x180072937  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180072940  lea     rax, [rsp+88h+hKey]
0x180072945  mov     [rsp+88h+phkResult], rax; phkResult
0x18007294a  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180072953  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x18007295b  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180072963  xor     r9d, r9d; lpClass
0x180072966  xor     r8d, r8d; Reserved
0x180072969  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072970  call    cs:__imp_RegCreateKeyExW
0x180072976  mov     ebx, eax
0x180072978  test    eax, eax
0x18007297a  jz      short loc_1800729C2
0x18007297c  jle     short loc_180072987
0x18007297e  movzx   ebx, ax
0x180072981  or      ebx, 80070000h
0x180072987  mov     rcx, [rsp+88h+hKey]; hKey
0x18007298c  test    rcx, rcx
0x18007298f  jz      short loc_180072998
0x180072991  call    cs:__imp_RegCloseKey
0x180072997  nop
0x180072998  lea     rcx, [rsp+88h+var_30]
0x18007299d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800729a2  mov     eax, ebx
0x1800729a4  mov     rcx, [rsp+88h+var_10]
0x1800729a9  xor     rcx, rsp; StackCookie
0x1800729ac  call    __security_check_cookie
0x1800729b1  mov     rbx, [rsp+88h+arg_0]
0x1800729b9  add     rsp, 80h
0x1800729c0  pop     rdi
0x1800729c1  retn
0x1800729c2  xor     ebx, ebx
0x1800729c4  mov     r8, [rsp+88h+hKey]; hKeyDest
0x1800729c9  xor     edx, edx; lpSubKey
0x1800729cb  mov     rcx, rdi; hKeySrc
0x1800729ce  call    cs:__imp_RegCopyTreeW
0x1800729d4  test    eax, eax
0x1800729d6  jz      short loc_180072987
0x1800729d8  jg      short loc_18007297E
0x1800729da  mov     ebx, eax
0x1800729dc  jmp     short loc_180072987
```
