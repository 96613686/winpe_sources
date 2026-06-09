# MigrateCustomWPIdentitySettings(void)

- ea: `0x18003af84`
- end: `0x18003b103`
- name: `?MigrateCustomWPIdentitySettings@@YAJXZ`
- size: `383`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c1e8`

## callees

- `0x180007824`
- `0x18003af84`
- `0x18003b104`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ucrtbase_clr0400!_wcsicmp` at `0x18003b074`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003b074`
- `ADVAPI32!RegCloseKey` at `0x18003b0c2`
- `ADVAPI32!RegCloseKey` at `0x18003b0d7`
- `ADVAPI32!RegCloseKey` at `0x18003b0c2`
- `ADVAPI32!RegCloseKey` at `0x18003b0d7`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b050`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b050`
- `ADVAPI32!RegOpenKeyExW` at `0x18003afe2`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b00e`
- `ADVAPI32!RegOpenKeyExW` at `0x18003afe2`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b00e`

## pseudocode

```c
__int64 MigrateCustomWPIdentitySettings(void)
{
  DWORD i; // ebx
  LSTATUS v1; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  phkResult = 0;
  hKey = 0;
  cchName = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\ASP.NET\\4.0.30319.0\\AutoGenKeys",
          0,
          0x20019u,
          &phkResult)
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 0x20019u, &hKey) )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      Name[0] = 0;
      v1 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v1 == 259 )
        break;
      if ( v1 )
      {
        GetLastWin32Error();
      }
      else if ( _wcsicmp(Name, L"4.0.30319.0") )
      {
        if ( (unsigned int)StringCchCatW(Name, 0x104u, L"\\AutoGenKeys") )
          break;
        MigrateCustomWPIdentitySettingsOneVersion(Name, phkResult, hKey);
      }
    }
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003af84  mov     [rsp-8+arg_0], rbx
0x18003af89  mov     [rsp-8+arg_8], rdi
0x18003af8e  push    rbp
0x18003af8f  lea     rbp, [rsp-180h]
0x18003af97  sub     rsp, 280h
0x18003af9e  mov     rax, cs:__security_cookie
0x18003afa5  xor     rax, rsp
0x18003afa8  mov     [rbp+180h+var_10], rax
0x18003afaf  xor     edi, edi
0x18003afb1  lea     rax, [rsp+280h+var_230]
0x18003afb6  mov     ebx, 20019h
0x18003afbb  mov     [rsp+280h+var_230], rdi
0x18003afc0  mov     r9d, ebx; samDesired
0x18003afc3  mov     [rsp+280h+hKey], rdi
0x18003afc8  xor     r8d, r8d; ulOptions
0x18003afcb  mov     [rsp+280h+cchName], edi
0x18003afcf  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\ASP.NET\\4.0.30319"...
0x18003afd6  mov     [rsp+280h+phkResult], rax; phkResult
0x18003afdb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003afe2  call    cs:__imp_RegOpenKeyExW
0x18003afe8  test    eax, eax
0x18003afea  jnz     loc_18003B0B3
0x18003aff0  lea     rax, [rsp+280h+hKey]
0x18003aff5  mov     r9d, ebx; samDesired
0x18003aff8  xor     r8d, r8d; ulOptions
0x18003affb  mov     [rsp+280h+phkResult], rax; phkResult
0x18003b000  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18003b007  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b00e  call    cs:__imp_RegOpenKeyExW
0x18003b014  test    eax, eax
0x18003b016  jnz     loc_18003B0B3
0x18003b01c  mov     ebx, edi
0x18003b01e  mov     rcx, [rsp+280h+hKey]; hKey
0x18003b023  lea     r9, [rsp+280h+cchName]; lpcchName
0x18003b028  mov     [rsp+280h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18003b02d  lea     r8, [rsp+280h+Name]; lpName
0x18003b032  mov     [rsp+280h+lpcchClass], rdi; lpcchClass
0x18003b037  mov     edx, ebx; dwIndex
0x18003b039  mov     [rsp+280h+lpClass], rdi; lpClass
0x18003b03e  mov     [rsp+280h+phkResult], rdi; lpReserved
0x18003b043  mov     [rsp+280h+cchName], 104h
0x18003b04b  mov     [rsp+280h+Name], di
0x18003b050  call    cs:__imp_RegEnumKeyExW
0x18003b056  cmp     eax, 103h
0x18003b05b  jz      short loc_18003B0B3
0x18003b05d  test    eax, eax
0x18003b05f  jz      short loc_18003B068
0x18003b061  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003b066  jmp     short loc_18003B0AC
0x18003b068  lea     rdx, a40303190; "4.0.30319.0"
0x18003b06f  lea     rcx, [rsp+280h+Name]; String1
0x18003b074  call    cs:__imp__wcsicmp
0x18003b07a  test    eax, eax
0x18003b07c  jz      short loc_18003B0AC
0x18003b07e  lea     r8, aAutogenkeys; "\\AutoGenKeys"
0x18003b085  mov     edx, 104h; unsigned __int64
0x18003b08a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003b08f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b094  test    eax, eax
0x18003b096  jnz     short loc_18003B0B3
0x18003b098  mov     r8, [rsp+280h+hKey]; HKEY
0x18003b09d  lea     rcx, [rsp+280h+Name]; lpSubKey
0x18003b0a2  mov     rdx, [rsp+280h+var_230]; hKey
0x18003b0a7  call    ?MigrateCustomWPIdentitySettingsOneVersion@@YAJPEBGPEAUHKEY__@@1@Z; MigrateCustomWPIdentitySettingsOneVersion(ushort const *,HKEY__ *,HKEY__ *)
0x18003b0ac  inc     ebx
0x18003b0ae  jmp     loc_18003B01E
0x18003b0b3  mov     rcx, [rsp+280h+var_230]; hKey
0x18003b0b8  lea     rax, [rcx-1]
0x18003b0bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b0c0  ja      short loc_18003B0C8
0x18003b0c2  call    cs:__imp_RegCloseKey
0x18003b0c8  mov     rcx, [rsp+280h+hKey]; hKey
0x18003b0cd  lea     rax, [rcx-1]
0x18003b0d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b0d5  ja      short loc_18003B0DD
0x18003b0d7  call    cs:__imp_RegCloseKey
0x18003b0dd  xor     eax, eax
0x18003b0df  mov     rcx, [rbp+180h+var_10]
0x18003b0e6  xor     rcx, rsp; StackCookie
0x18003b0e9  call    __security_check_cookie
0x18003b0ee  lea     r11, [rsp+280h+var_s0]
0x18003b0f6  mov     rbx, [r11+10h]
0x18003b0fa  mov     rdi, [r11+18h]
0x18003b0fe  mov     rsp, r11
0x18003b101  pop     rbp
0x18003b102  retn
```
