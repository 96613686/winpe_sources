# T2OSSvcAddFontsToSystemStartUp

- ea: `0x1800229a8`
- end: `0x180022ae4`
- name: `T2OSSvcAddFontsToSystemStartUp`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800190a4`

## callees

- `0x18001ba0c`
- `0x18001f3e4`
- `0x18001f440`
- `0x1800229a8`
- `0x18002a590`

## import_xrefs

- `KERNEL32!RegOpenKeyExA` at `0x180022a6d`
- `KERNEL32!RegOpenKeyExA` at `0x180022a6d`
- `KERNEL32!RegCloseKey` at `0x180022ab4`
- `KERNEL32!RegCloseKey` at `0x180022ab4`
- `KERNEL32!RegSetValueExA` at `0x180022aa9`
- `KERNEL32!RegSetValueExA` at `0x180022aa9`
- `KERNEL32!GetVersion` at `0x180022a39`
- `KERNEL32!GetVersion` at `0x180022a39`

## pseudocode

```c
__int64 __fastcall T2OSSvcAddFontsToSystemStartUp(__int64 a1, __int64 a2)
{
  const char *v3; // r10
  unsigned int v4; // r11d
  signed int Version; // eax
  const CHAR *v6; // rdx
  __int64 v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-88h] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-80h] BYREF
  char pszDest[96]; // [rsp+40h] [rbp-78h] BYREF

  hKey = 0;
  pcchLength = 0;
  if ( StringCchLengthA((STRSAFE_PCNZCH)(a2 + 780), 0x40u, &pcchLength) < 0
    || !pcchLength
    || StringCchCopyA(pszDest, v4, v3) < 0
    || StringCchCatA(pszDest, 0x54u, " (TrueType)") < 0 )
  {
    return 0;
  }
  Version = GetVersion();
  v6 = "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Fonts";
  if ( Version >= 0 )
    v6 = "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Fonts";
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, v6, 0, 2u, &hKey) )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_BYTE *)(a2 + 260 + v7) );
    RegSetValueExA(hKey, pszDest, 0, 1u, (const BYTE *)(a2 + 260), v7 + 1);
    RegCloseKey(hKey);
  }
  return 1;
}

```

## disassembly

```asm
0x1800229a8  mov     [rsp+arg_0], rbx
0x1800229ad  push    rdi
0x1800229ae  sub     rsp, 0B0h
0x1800229b5  mov     rax, cs:__security_cookie
0x1800229bc  xor     rax, rsp
0x1800229bf  mov     [rsp+0B8h+var_18], rax
0x1800229c7  xor     edi, edi
0x1800229c9  lea     r10, [rdx+30Ch]
0x1800229d0  mov     rbx, rdx
0x1800229d3  mov     [rsp+0B8h+hKey], rdi
0x1800229d8  lea     r8, [rsp+0B8h+pcchLength]; pcchLength
0x1800229dd  mov     [rsp+0B8h+pcchLength], rdi
0x1800229e2  mov     rcx, r10; psz
0x1800229e5  lea     r11d, [rdi+40h]
0x1800229e9  mov     edx, r11d; cchMax
0x1800229ec  call    StringCchLengthA
0x1800229f1  test    eax, eax
0x1800229f3  js      loc_180022AC1
0x1800229f9  cmp     [rsp+0B8h+pcchLength], 1
0x1800229ff  jb      loc_180022AC1
0x180022a05  mov     r8, r10; pszSrc
0x180022a08  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x180022a0d  mov     edx, r11d; cchDest
0x180022a10  call    StringCchCopyA
0x180022a15  test    eax, eax
0x180022a17  js      loc_180022AC1
0x180022a1d  lea     r8, pszSrc; " (TrueType)"
0x180022a24  lea     edx, [rdi+54h]; cchDest
0x180022a27  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x180022a2c  call    StringCchCatA
0x180022a31  test    eax, eax
0x180022a33  js      loc_180022AC1
0x180022a39  call    cs:__imp_GetVersion
0x180022a3f  shr     eax, 10h
0x180022a42  xor     r8d, r8d; ulOptions
0x180022a45  test    ax, ax
0x180022a48  lea     r9d, [rdi+2]; samDesired
0x180022a4c  lea     rax, [rsp+0B8h+hKey]
0x180022a51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022a58  mov     [rsp+0B8h+phkResult], rax; phkResult
0x180022a5d  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180022a64  js      short loc_180022A6D
0x180022a66  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022a6d  call    cs:__imp_RegOpenKeyExA
0x180022a73  test    eax, eax
0x180022a75  jnz     short loc_180022ABA
0x180022a77  lea     rdx, [rbx+104h]
0x180022a7e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022a82  inc     rcx
0x180022a85  cmp     [rdx+rcx], dil
0x180022a89  jnz     short loc_180022A82
0x180022a8b  inc     ecx
0x180022a8d  mov     r9d, 1; dwType
0x180022a93  mov     [rsp+0B8h+cbData], ecx; cbData
0x180022a97  xor     r8d, r8d; Reserved
0x180022a9a  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180022a9f  mov     [rsp+0B8h+phkResult], rdx; lpData
0x180022aa4  lea     rdx, [rsp+0B8h+pszDest]; lpValueName
0x180022aa9  call    cs:__imp_RegSetValueExA
0x180022aaf  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180022ab4  call    cs:__imp_RegCloseKey
0x180022aba  mov     eax, 1
0x180022abf  jmp     short loc_180022AC3
0x180022ac1  xor     eax, eax
0x180022ac3  mov     rcx, [rsp+0B8h+var_18]
0x180022acb  xor     rcx, rsp; StackCookie
0x180022ace  call    __security_check_cookie
0x180022ad3  mov     rbx, [rsp+0B8h+arg_0]
0x180022adb  add     rsp, 0B0h
0x180022ae2  pop     rdi
0x180022ae3  retn
```
