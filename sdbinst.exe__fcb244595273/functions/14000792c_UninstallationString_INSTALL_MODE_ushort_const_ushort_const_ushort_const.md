# UninstallationString(_INSTALL_MODE,ushort const *,ushort const *,ushort const *)

- ea: `0x14000792c`
- end: `0x140007b1a`
- name: `?UninstallationString@@YAHW4_INSTALL_MODE@@PEBG11@Z`
- size: `494`
- prototype: `__int64 __fastcall(int, __int64, __int64, const BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004df8`

## callees

- `0x140006238`
- `0x140007098`
- `0x14000792c`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140007a7f`
- `ADVAPI32!RegSetValueExW` at `0x140007ac6`
- `ADVAPI32!RegSetValueExW` at `0x140007a7f`
- `ADVAPI32!RegSetValueExW` at `0x140007ac6`
- `ADVAPI32!RegCreateKeyExW` at `0x140007a33`
- `ADVAPI32!RegCreateKeyExW` at `0x140007a33`
- `ADVAPI32!RegDeleteKeyExW` at `0x1400079aa`
- `ADVAPI32!RegDeleteKeyExW` at `0x1400079aa`
- `ADVAPI32!RegCloseKey` at `0x140007aec`
- `ADVAPI32!RegCloseKey` at `0x140007aec`

## string_xrefs

- `0x140007968`: `Software\Microsoft\Windows\CurrentVersion\Uninstall\`
- `0x1400079b7`: `Software\Microsoft\Windows\CurrentVersion\Uninstall\`
- `0x1400079e0`: `%%windir%%\system32\sdbinst.exe -u "%s"`
- `0x140007aaa`: `UninstallString`

## pseudocode

```c
__int64 __fastcall UninstallationString(int a1, __int64 a2, __int64 a3, const BYTE *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Data[536]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s%s.sdb",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\",
              a3) < 0 )
    goto LABEL_14;
  if ( (RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0x100u, 0) & 0xFFFFFFFD) == 0 )
  {
    v8 = 1;
    if ( a1 )
      goto LABEL_15;
    if ( (int)StringCchPrintfW(Data, 0x212u, L"%%windir%%\\system32\\sdbinst.exe -u \"%s\"", a2) >= 0 )
    {
      if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x102u, 0, &hKey, 0) )
      {
        PrintMessage(0x3F1u, SubKey);
        goto LABEL_14;
      }
      v9 = -1;
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&a4[2 * v10] );
      if ( !RegSetValueExW(hKey, L"DisplayName", 0, 1u, a4, 2 * v10 + 2) )
      {
        do
          ++v9;
        while ( Data[v9] );
        if ( !RegSetValueExW(hKey, L"UninstallString", 0, 2u, (const BYTE *)Data, 2 * v9 + 2) )
          goto LABEL_15;
      }
    }
    PrintMessage(0x3F4u, SubKey);
    goto LABEL_14;
  }
  PrintMessage(0x3F7u, a3, L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\");
LABEL_14:
  v8 = 0;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x14000792c  mov     [rsp-8+arg_0], rbx
0x140007931  push    rbp
0x140007932  push    rsi
0x140007933  push    rdi
0x140007934  push    r14
0x140007936  push    r15
0x140007938  lea     rbp, [rsp-5B0h]
0x140007940  sub     rsp, 6B0h
0x140007947  mov     rax, cs:__security_cookie
0x14000794e  xor     rax, rsp
0x140007951  mov     [rbp+5D0h+var_30], rax
0x140007958  mov     rbx, r8
0x14000795b  mov     rsi, r9
0x14000795e  mov     r14, rdx
0x140007961  mov     qword ptr [rsp+6D0h+dwOptions], rbx
0x140007966  mov     edi, ecx
0x140007968  lea     r9, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000796f  xor     r15d, r15d
0x140007972  lea     r8, aSSSdb; "%s%s.sdb"
0x140007979  mov     edx, 104h; unsigned __int64
0x14000797e  mov     [rsp+6D0h+hKey], r15
0x140007983  lea     rcx, [rsp+6D0h+SubKey]; unsigned __int16 *
0x140007988  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000798d  test    eax, eax
0x14000798f  js      loc_140007ADF
0x140007995  xor     r9d, r9d; Reserved
0x140007998  lea     rdx, [rsp+6D0h+SubKey]; lpSubKey
0x14000799d  mov     r8d, 100h; samDesired
0x1400079a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400079aa  call    cs:__imp_RegDeleteKeyExW
0x1400079b0  test    eax, 0FFFFFFFDh
0x1400079b5  jz      short loc_1400079D0
0x1400079b7  lea     r8, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400079be  mov     rdx, rbx
0x1400079c1  mov     ecx, 3F7h; unsigned int
0x1400079c6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400079cb  jmp     loc_140007ADF
0x1400079d0  mov     ebx, 1
0x1400079d5  test    edi, edi
0x1400079d7  jnz     loc_140007AE2
0x1400079dd  mov     r9, r14
0x1400079e0  lea     r8, aWindirSystem32; "%%windir%%\\system32\\sdbinst.exe -u \""...
0x1400079e7  mov     edx, 212h; unsigned __int64
0x1400079ec  lea     rcx, [rbp+5D0h+Data]; unsigned __int16 *
0x1400079f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400079f8  lea     rdx, [rsp+6D0h+SubKey]; lpSubKey
0x1400079fd  test    eax, eax
0x1400079ff  js      loc_140007AD5
0x140007a05  mov     [rsp+6D0h+lpdwDisposition], r15; lpdwDisposition
0x140007a0a  lea     rax, [rsp+6D0h+hKey]
0x140007a0f  mov     [rsp+6D0h+phkResult], rax; phkResult
0x140007a14  xor     r9d, r9d; lpClass
0x140007a17  mov     [rsp+6D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140007a1c  xor     r8d, r8d; Reserved
0x140007a1f  mov     [rsp+6D0h+samDesired], 102h; samDesired
0x140007a27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007a2e  mov     [rsp+6D0h+dwOptions], r15d; dwOptions
0x140007a33  call    cs:__imp_RegCreateKeyExW
0x140007a39  test    eax, eax
0x140007a3b  jz      short loc_140007A4C
0x140007a3d  lea     rdx, [rsp+6D0h+SubKey]
0x140007a42  mov     ecx, 3F1h
0x140007a47  jmp     loc_140007ADA
0x140007a4c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007a50  mov     rax, rdi
0x140007a53  inc     rax
0x140007a56  cmp     [rsi+rax*2], r15w
0x140007a5b  jnz     short loc_140007A53
0x140007a5d  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140007a62  lea     eax, ds:2[rax*2]
0x140007a69  mov     [rsp+6D0h+samDesired], eax; cbData
0x140007a6d  lea     rdx, aDisplayname; "DisplayName"
0x140007a74  mov     r9d, ebx; dwType
0x140007a77  mov     qword ptr [rsp+6D0h+dwOptions], rsi; lpData
0x140007a7c  xor     r8d, r8d; Reserved
0x140007a7f  call    cs:__imp_RegSetValueExW
0x140007a85  test    eax, eax
0x140007a87  jnz     short loc_140007AD0
0x140007a89  lea     rax, [rbp+5D0h+Data]
0x140007a90  inc     rdi
0x140007a93  cmp     [rax+rdi*2], r15w
0x140007a98  jnz     short loc_140007A90
0x140007a9a  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140007a9f  lea     eax, ds:2[rdi*2]
0x140007aa6  mov     [rsp+6D0h+samDesired], eax; cbData
0x140007aaa  lea     rdx, aUninstallstrin; "UninstallString"
0x140007ab1  lea     rax, [rbp+5D0h+Data]
0x140007ab8  mov     r9d, 2; dwType
0x140007abe  xor     r8d, r8d; Reserved
0x140007ac1  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x140007ac6  call    cs:__imp_RegSetValueExW
0x140007acc  test    eax, eax
0x140007ace  jz      short loc_140007AE2
0x140007ad0  lea     rdx, [rsp+6D0h+SubKey]
0x140007ad5  mov     ecx, 3F4h; unsigned int
0x140007ada  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140007adf  mov     ebx, r15d
0x140007ae2  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140007ae7  test    rcx, rcx
0x140007aea  jz      short loc_140007AF2
0x140007aec  call    cs:__imp_RegCloseKey
0x140007af2  mov     eax, ebx
0x140007af4  mov     rcx, [rbp+5D0h+var_30]
0x140007afb  xor     rcx, rsp; StackCookie
0x140007afe  call    __security_check_cookie
0x140007b03  mov     rbx, [rsp+6D0h+arg_0]
0x140007b0b  add     rsp, 6B0h
0x140007b12  pop     r15
0x140007b14  pop     r14
0x140007b16  pop     rdi
0x140007b17  pop     rsi
0x140007b18  pop     rbp
0x140007b19  retn
```
