# _SHCreatePropSheetExtArrayEx(HKEY__ *,ushort const *,uint,IDataObject *)

- ea: `0x180061c1c`
- end: `0x180061da7`
- name: `?_SHCreatePropSheetExtArrayEx@@YAPEAUHPSXA__@@PEAUHKEY__@@PEBGIPEAUIDataObject@@@Z`
- size: `395`
- prototype: `HPSXA(HKEY, const unsigned __int16 *, unsigned int, struct IDataObject *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18004c414`
- `0x18005a5e8`
- `0x180068a34`

## callees

- `0x180035590`
- `0x18006163c`
- `0x180061c1c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180061c52`
- `KERNEL32!LocalAlloc` at `0x180061c52`
- `ADVAPI32!RegCloseKey` at `0x180061d5d`
- `ADVAPI32!RegCloseKey` at `0x180061d6d`
- `ADVAPI32!RegCloseKey` at `0x180061d5d`
- `ADVAPI32!RegCloseKey` at `0x180061d6d`
- `ADVAPI32!RegOpenKeyExW` at `0x180061c91`
- `ADVAPI32!RegOpenKeyExW` at `0x180061cc3`
- `ADVAPI32!RegOpenKeyExW` at `0x180061c91`
- `ADVAPI32!RegOpenKeyExW` at `0x180061cc3`
- `ADVAPI32!RegEnumKeyW` at `0x180061ce5`
- `ADVAPI32!RegEnumKeyW` at `0x180061ce5`
- `SHLWAPI!SHRegGetValueW` at `0x180061d26`
- `SHLWAPI!SHRegGetValueW` at `0x180061d26`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x180061d7a`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x180061d7a`

## pseudocode

```c
HPSXA __fastcall _SHCreatePropSheetExtArrayEx(HKEY a1, const unsigned __int16 *a2, __int64 a3, struct IDataObject *a4)
{
  HPSXA v6; // rax
  HPSXA v7; // rbx
  DWORD v8; // edi
  HKEY v9; // r8
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = (HPSXA)LocalAlloc(0x40u, 0x48u);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 1) = 8;
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 1u, &hKey) )
      goto LABEL_13;
    v8 = 0;
    hkey = 0;
    if ( !RegOpenKeyExW(hKey, L"shellex\\PropertySheetHandlers", 0, 9u, &hkey) )
    {
      while ( *(_DWORD *)v7 < *((_DWORD *)v7 + 1) && !RegEnumKeyW(hkey, v8, Name, 0x40u) )
      {
        pcbData = 520;
        if ( !SHRegGetValueW(hkey, Name, 0, 2, 0, pvData, &pcbData)
          && (unsigned int)_InitPropSheetExt((struct IShellPropSheetExt **)v7 + *(_DWORD *)v7 + 1, pvData, v9, a4) )
        {
          ++*(_DWORD *)v7;
        }
        ++v8;
      }
      RegCloseKey(hkey);
      v8 = 1;
    }
    RegCloseKey(hKey);
    if ( !v8 )
    {
LABEL_13:
      SHDestroyPropSheetExtArray(v7);
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180061c1c  mov     [rsp-8+arg_0], rbx
0x180061c21  push    rbp
0x180061c22  push    rsi
0x180061c23  push    rdi
0x180061c24  lea     rbp, [rsp-200h]
0x180061c2c  sub     rsp, 300h
0x180061c33  mov     rax, cs:__security_cookie
0x180061c3a  xor     rax, rsp
0x180061c3d  mov     [rbp+210h+var_20], rax
0x180061c44  mov     rdi, rdx
0x180061c47  mov     rsi, r9
0x180061c4a  mov     edx, 48h ; 'H'; uBytes
0x180061c4f  lea     ecx, [rdx-8]; uFlags
0x180061c52  call    cs:__imp_LocalAlloc
0x180061c58  mov     rbx, rax
0x180061c5b  test    rax, rax
0x180061c5e  jz      loc_180061D82
0x180061c64  mov     dword ptr [rax+4], 8
0x180061c6b  mov     r9d, 1; samDesired
0x180061c71  lea     rax, [rsp+310h+hKey]
0x180061c76  mov     [rsp+310h+hKey], 0
0x180061c7f  xor     r8d, r8d; ulOptions
0x180061c82  mov     [rsp+310h+phkResult], rax; phkResult
0x180061c87  mov     rdx, rdi; lpSubKey
0x180061c8a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180061c91  call    cs:__imp_RegOpenKeyExW
0x180061c97  test    eax, eax
0x180061c99  jnz     loc_180061D77
0x180061c9f  mov     rcx, [rsp+310h+hKey]; hKey
0x180061ca4  lea     rax, [rsp+310h+hkey]
0x180061ca9  xor     edi, edi
0x180061cab  mov     [rsp+310h+phkResult], rax; phkResult
0x180061cb0  xor     r8d, r8d; ulOptions
0x180061cb3  mov     [rsp+310h+hkey], rdi
0x180061cb8  lea     rdx, aShellexPropert; "shellex\\PropertySheetHandlers"
0x180061cbf  lea     r9d, [rdi+9]; samDesired
0x180061cc3  call    cs:__imp_RegOpenKeyExW
0x180061cc9  test    eax, eax
0x180061ccb  jnz     loc_180061D68
0x180061cd1  jmp     short loc_180061D4D
0x180061cd3  mov     rcx, [rsp+310h+hkey]; hKey
0x180061cd8  lea     r8, [rsp+310h+Name]; lpName
0x180061cdd  mov     r9d, 40h ; '@'; cchName
0x180061ce3  mov     edx, edi; dwIndex
0x180061ce5  call    cs:__imp_RegEnumKeyW
0x180061ceb  test    eax, eax
0x180061ced  jnz     short loc_180061D58
0x180061cef  mov     rcx, [rsp+310h+hkey]; hkey
0x180061cf4  lea     rax, [rsp+310h+var_2C8]
0x180061cf9  mov     [rsp+310h+pcbData], rax; pcbData
0x180061cfe  lea     rdx, [rsp+310h+Name]; pszSubKey
0x180061d03  lea     rax, [rbp+210h+var_230]
0x180061d07  mov     [rsp+310h+var_2C8], 208h
0x180061d0f  mov     [rsp+310h+pvData], rax; pvData
0x180061d14  mov     r9d, 2; srrfFlags
0x180061d1a  xor     r8d, r8d; pszValue
0x180061d1d  mov     [rsp+310h+phkResult], 0; pdwType
0x180061d26  call    cs:__imp_SHRegGetValueW
0x180061d2c  test    eax, eax
0x180061d2e  jnz     short loc_180061D4B
0x180061d30  mov     eax, [rbx]
0x180061d32  lea     rdx, [rbp+210h+var_230]; unsigned __int16 *
0x180061d36  inc     rax
0x180061d39  mov     r9, rsi; struct IDataObject *
0x180061d3c  lea     rcx, [rbx+rax*8]; struct IShellPropSheetExt **
0x180061d40  call    ?_InitPropSheetExt@@YAHPEAPEAUIShellPropSheetExt@@PEBGPEAUHKEY__@@PEAUIDataObject@@@Z; _InitPropSheetExt(IShellPropSheetExt * *,ushort const *,HKEY__ *,IDataObject *)
0x180061d45  test    eax, eax
0x180061d47  jz      short loc_180061D4B
0x180061d49  inc     dword ptr [rbx]
0x180061d4b  inc     edi
0x180061d4d  mov     eax, [rbx+4]
0x180061d50  cmp     [rbx], eax
0x180061d52  jb      loc_180061CD3
0x180061d58  mov     rcx, [rsp+310h+hkey]; hKey
0x180061d5d  call    cs:__imp_RegCloseKey
0x180061d63  mov     edi, 1
0x180061d68  mov     rcx, [rsp+310h+hKey]; hKey
0x180061d6d  call    cs:__imp_RegCloseKey
0x180061d73  test    edi, edi
0x180061d75  jnz     short loc_180061D82
0x180061d77  mov     rcx, rbx; hpsxa
0x180061d7a  call    cs:__imp_SHDestroyPropSheetExtArray
0x180061d80  xor     ebx, ebx
0x180061d82  mov     rax, rbx
0x180061d85  mov     rcx, [rbp+210h+var_20]
0x180061d8c  xor     rcx, rsp; StackCookie
0x180061d8f  call    __security_check_cookie
0x180061d94  mov     rbx, [rsp+310h+arg_0]
0x180061d9c  add     rsp, 300h
0x180061da3  pop     rdi
0x180061da4  pop     rsi
0x180061da5  pop     rbp
0x180061da6  retn
```
