# InstallSdbEntry(ushort const *,ushort const *,unsigned __int64,int)

- ea: `0x140005988`
- end: `0x140005b27`
- name: `?InstallSdbEntry@@YAHPEBG0_KH@Z`
- size: `415`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004df8`
- `0x140006480`

## callees

- `0x140005988`
- `0x140006238`
- `0x140006f60`
- `0x140007098`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140005ae2`
- `ADVAPI32!RegSetValueExW` at `0x140005ae2`
- `ADVAPI32!RegCreateKeyExW` at `0x140005aa0`
- `ADVAPI32!RegCreateKeyExW` at `0x140005aa0`
- `ADVAPI32!RegCloseKey` at `0x140005b02`
- `ADVAPI32!RegCloseKey` at `0x140005b02`

## string_xrefs

- `0x140005a4b`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`

## pseudocode

```c
__int64 __fastcall InstallSdbEntry(const unsigned __int16 *a1, WCHAR *a2, __int64 a3, int a4)
{
  WCHAR *v5; // rax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  const unsigned __int16 *v12; // r8
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[520]; // [rsp+270h] [rbp+170h] BYREF

  *(_QWORD *)Data = a3;
  hKey = 0;
  v5 = ValueName;
  v8 = 260;
  v9 = 0;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*a2 )
      break;
    *v5++ = *a2++;
    --v10;
    --v8;
  }
  while ( v8 );
  v11 = v5 - 1;
  if ( v8 )
    v11 = v5;
  *v11 = 0;
  if ( !v8 || (int)StringCchCatW(ValueName, 0x104u, L".sdb") < 0 )
    goto LABEL_8;
  v12 = L"%s\\Layers\\%s";
  if ( !a4 )
    v12 = L"%s\\%s";
  if ( (int)StringCchPrintfW(
              SubKey,
              0x208u,
              v12,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom",
              a1) >= 0 )
  {
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x102u, 0, &hKey, 0) )
    {
      PrintMessage(0x3F1u, SubKey);
    }
    else if ( RegSetValueExW(hKey, ValueName, 0, 0xBu, Data, 8u) )
    {
      PrintMessage(0x3F4u, SubKey);
    }
    else
    {
      v9 = 1;
    }
  }
  else
  {
LABEL_8:
    PrintMessage(0x409u, v8, v10);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x140005988  push    rbp
0x14000598a  push    rbx
0x14000598b  push    rsi
0x14000598c  push    rdi
0x14000598d  push    r14
0x14000598f  lea     rbp, [rsp-590h]
0x140005997  sub     rsp, 690h
0x14000599e  mov     rax, cs:__security_cookie
0x1400059a5  xor     rax, rsp
0x1400059a8  mov     [rbp+5B0h+var_30], rax
0x1400059af  xor     r14d, r14d
0x1400059b2  mov     qword ptr [rsp+6B0h+Data], r8
0x1400059b7  mov     edi, r9d
0x1400059ba  mov     [rsp+6B0h+hKey], r14
0x1400059bf  mov     r9d, 104h
0x1400059c5  lea     rax, [rsp+6B0h+ValueName]
0x1400059ca  mov     r10, rdx
0x1400059cd  mov     rsi, rcx
0x1400059d0  mov     edx, r9d
0x1400059d3  mov     ebx, r14d
0x1400059d6  mov     r8d, 7FFFFFFEh
0x1400059dc  test    r8, r8
0x1400059df  jz      short loc_1400059FE
0x1400059e1  movzx   ecx, word ptr [r10]
0x1400059e5  test    cx, cx
0x1400059e8  jz      short loc_1400059FE
0x1400059ea  mov     [rax], cx
0x1400059ed  add     r10, 2
0x1400059f1  add     rax, 2
0x1400059f5  dec     r8
0x1400059f8  sub     rdx, 1
0x1400059fc  jnz     short loc_1400059DC
0x1400059fe  test    rdx, rdx
0x140005a01  lea     rcx, [rax-2]
0x140005a05  cmovnz  rcx, rax
0x140005a09  mov     [rcx], r14w
0x140005a0d  jnz     short loc_140005A1E
0x140005a0f  mov     ecx, 409h; unsigned int
0x140005a14  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140005a19  jmp     loc_140005AF8
0x140005a1e  lea     r8, aSdb; ".sdb"
0x140005a25  mov     rdx, r9; unsigned __int64
0x140005a28  lea     rcx, [rsp+6B0h+ValueName]; unsigned __int16 *
0x140005a2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005a32  test    eax, eax
0x140005a34  js      short loc_140005A0F
0x140005a36  lea     rax, aSS_0; "%s\\%s"
0x140005a3d  mov     qword ptr [rsp+6B0h+dwOptions], rsi
0x140005a42  test    edi, edi
0x140005a44  lea     r8, aSLayersS; "%s\\Layers\\%s"
0x140005a4b  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x140005a52  mov     edx, 208h; unsigned __int64
0x140005a57  cmovz   r8, rax; unsigned __int16 *
0x140005a5b  lea     rcx, [rbp+5B0h+SubKey]; unsigned __int16 *
0x140005a62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005a67  test    eax, eax
0x140005a69  js      short loc_140005A0F
0x140005a6b  mov     [rsp+6B0h+lpdwDisposition], r14; lpdwDisposition
0x140005a70  lea     rax, [rsp+6B0h+hKey]
0x140005a75  mov     [rsp+6B0h+phkResult], rax; phkResult
0x140005a7a  lea     rdx, [rbp+5B0h+SubKey]; lpSubKey
0x140005a81  mov     [rsp+6B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140005a86  xor     r9d, r9d; lpClass
0x140005a89  mov     [rsp+6B0h+samDesired], 102h; samDesired
0x140005a91  xor     r8d, r8d; Reserved
0x140005a94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005a9b  mov     [rsp+6B0h+dwOptions], r14d; dwOptions
0x140005aa0  call    cs:__imp_RegCreateKeyExW
0x140005aa6  test    eax, eax
0x140005aa8  jz      short loc_140005ABD
0x140005aaa  mov     ecx, 3F1h; unsigned int
0x140005aaf  lea     rdx, [rbp+5B0h+SubKey]
0x140005ab6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140005abb  jmp     short loc_140005AF8
0x140005abd  mov     rcx, [rsp+6B0h+hKey]; hKey
0x140005ac2  lea     rax, [rsp+6B0h+Data]
0x140005ac7  mov     [rsp+6B0h+samDesired], 8; cbData
0x140005acf  lea     rdx, [rsp+6B0h+ValueName]; lpValueName
0x140005ad4  mov     r9d, 0Bh; dwType
0x140005ada  mov     qword ptr [rsp+6B0h+dwOptions], rax; lpData
0x140005adf  xor     r8d, r8d; Reserved
0x140005ae2  call    cs:__imp_RegSetValueExW
0x140005ae8  test    eax, eax
0x140005aea  jz      short loc_140005AF3
0x140005aec  mov     ecx, 3F4h
0x140005af1  jmp     short loc_140005AAF
0x140005af3  mov     ebx, 1
0x140005af8  mov     rcx, [rsp+6B0h+hKey]; hKey
0x140005afd  test    rcx, rcx
0x140005b00  jz      short loc_140005B08
0x140005b02  call    cs:__imp_RegCloseKey
0x140005b08  mov     eax, ebx
0x140005b0a  mov     rcx, [rbp+5B0h+var_30]
0x140005b11  xor     rcx, rsp; StackCookie
0x140005b14  call    __security_check_cookie
0x140005b19  add     rsp, 690h
0x140005b20  pop     r14
0x140005b22  pop     rdi
0x140005b23  pop     rsi
0x140005b24  pop     rbx
0x140005b25  pop     rbp
0x140005b26  retn
```
