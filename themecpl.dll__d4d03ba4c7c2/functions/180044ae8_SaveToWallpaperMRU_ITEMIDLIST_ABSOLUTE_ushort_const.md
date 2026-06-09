# SaveToWallpaperMRU(_ITEMIDLIST_ABSOLUTE *,ushort const *)

- ea: `0x180044ae8`
- end: `0x180044cba`
- name: `?SaveToWallpaperMRU@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEBG@Z`
- size: `466`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800429c4`

## callees

- `0x180002280`
- `0x180008110`
- `0x180044ae8`
- `0x180057010`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x180044bd3`
- `PROPSYS!PropVariantToStringAlloc` at `0x180044bd3`
- `SHELL32!__imp_ILSaveToStream` at `0x180044b94`
- `SHELL32!__imp_ILSaveToStream` at `0x180044b94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044c41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044c41`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044b56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c67`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180044b77`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180044b77`

## pseudocode

```c
__int64 __fastcall SaveToWallpaperMRU(LPCITEMIDLIST pidl, const unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  LPSTREAM ppstm; // [rsp+50h] [rbp-19h] BYREF
  PWSTR ppszOut; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  PROPVARIANT propvar[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v11; // [rsp+78h] [rbp+Fh]
  WCHAR ValueName[16]; // [rsp+80h] [rbp+17h] BYREF

  hKey = 0;
  v4 = -2147467259;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers\\Images",
          0,
          0,
          0,
          0x20006u,
          0,
          &hKey,
          0) )
  {
    ppstm = 0;
    v4 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v4 < 0 )
    {
LABEL_15:
      RegCloseKey(hKey);
      return (unsigned int)v4;
    }
    v4 = ILSaveToStream(ppstm, pidl);
    if ( v4 < 0
      || (ppszOut = 0,
          v11 = 0,
          propvar[0] = (PROPVARIANT)66,
          propvar[1] = ppstm,
          v4 = PropVariantToStringAlloc(propvar, &ppszOut),
          v4 < 0) )
    {
LABEL_14:
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      goto LABEL_15;
    }
    v4 = StringCchPrintfW(ValueName, 0xDu, L"ID%s", a2);
    if ( v4 >= 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( ppszOut[v5] );
      if ( v5 >= 0x7FFFFFFF )
      {
        LOWORD(v4) = 534;
LABEL_12:
        v4 = (unsigned __int16)v4 | 0x80070000;
        goto LABEL_13;
      }
      v4 = RegSetValueExW(hKey, ValueName, 0, 1u, (const BYTE *)ppszOut, 2 * v5 + 2);
      if ( v4 > 0 )
        goto LABEL_12;
    }
LABEL_13:
    CoTaskMemFree(ppszOut);
    goto LABEL_14;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180044ae8  mov     [rsp-8+arg_10], rbx
0x180044aed  mov     [rsp-8+arg_18], rsi
0x180044af2  push    rbp
0x180044af3  push    rdi
0x180044af4  push    r14
0x180044af6  lea     rbp, [rsp-47h]
0x180044afb  sub     rsp, 0B0h
0x180044b02  mov     rax, cs:__security_cookie
0x180044b09  xor     rax, rsp
0x180044b0c  mov     [rbp+57h+var_20], rax
0x180044b10  xor     r14d, r14d
0x180044b13  lea     rax, [rbp+57h+hKey]
0x180044b17  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x180044b1c  mov     rsi, rdx
0x180044b1f  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180044b24  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180044b2b  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180044b30  mov     rdi, rcx
0x180044b33  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x180044b3b  xor     r9d, r9d; lpClass
0x180044b3e  xor     r8d, r8d; Reserved
0x180044b41  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x180044b46  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180044b4d  mov     [rbp+57h+hKey], r14
0x180044b51  mov     ebx, 80004005h
0x180044b56  call    cs:__imp_RegCreateKeyExW
0x180044b5d  nop     dword ptr [rax+rax+00h]
0x180044b62  test    eax, eax
0x180044b64  jnz     loc_180044C93
0x180044b6a  lea     r8, [rbp+57h+ppstm]; ppstm
0x180044b6e  mov     [rbp+57h+ppstm], r14
0x180044b72  lea     edx, [rax+1]; fDeleteOnRelease
0x180044b75  xor     ecx, ecx; hGlobal
0x180044b77  call    cs:__imp_CreateStreamOnHGlobal
0x180044b7e  nop     dword ptr [rax+rax+00h]
0x180044b83  mov     ebx, eax
0x180044b85  test    eax, eax
0x180044b87  js      loc_180044C83
0x180044b8d  mov     rcx, [rbp+57h+ppstm]; pstm
0x180044b91  mov     rdx, rdi; pidl
0x180044b94  call    cs:__imp_ILSaveToStream
0x180044b9b  nop     dword ptr [rax+rax+00h]
0x180044ba0  mov     ebx, eax
0x180044ba2  test    eax, eax
0x180044ba4  js      loc_180044C73
0x180044baa  xor     eax, eax
0x180044bac  mov     [rbp+57h+ppszOut], r14
0x180044bb0  mov     [rbp+57h+var_48], rax
0x180044bb4  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x180044bb8  xorps   xmm0, xmm0
0x180044bbb  lea     eax, [r14+42h]
0x180044bbf  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x180044bc3  mov     word ptr [rbp+57h+propvar], ax
0x180044bc7  lea     rcx, [rbp+57h+propvar]; propvar
0x180044bcb  mov     rax, [rbp+57h+ppstm]
0x180044bcf  mov     [rbp+57h+propvar+8], rax
0x180044bd3  call    cs:__imp_PropVariantToStringAlloc
0x180044bda  nop     dword ptr [rax+rax+00h]
0x180044bdf  mov     ebx, eax
0x180044be1  test    eax, eax
0x180044be3  js      loc_180044C73
0x180044be9  mov     r9, rsi
0x180044bec  lea     r8, aIdS; "ID%s"
0x180044bf3  lea     edx, [r14+0Dh]; unsigned __int64
0x180044bf7  lea     rcx, [rbp+57h+ValueName]; unsigned __int16 *
0x180044bfb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044c00  mov     ebx, eax
0x180044c02  test    eax, eax
0x180044c04  js      short loc_180044C63
0x180044c06  mov     rcx, [rbp+57h+ppszOut]
0x180044c0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044c0e  inc     rax
0x180044c11  cmp     [rcx+rax*2], r14w
0x180044c16  jnz     short loc_180044C0E
0x180044c18  cmp     rax, 7FFFFFFFh
0x180044c1e  jnb     short loc_180044C55
0x180044c20  lea     eax, ds:2[rax*2]
0x180044c27  mov     r9d, 1; dwType
0x180044c2d  mov     [rsp+0C0h+samDesired], eax; cbData
0x180044c31  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180044c35  mov     qword ptr [rsp+0C0h+dwOptions], rcx; lpData
0x180044c3a  xor     r8d, r8d; Reserved
0x180044c3d  mov     rcx, [rbp+57h+hKey]; hKey
0x180044c41  call    cs:__imp_RegSetValueExW
0x180044c48  nop     dword ptr [rax+rax+00h]
0x180044c4d  mov     ebx, eax
0x180044c4f  test    eax, eax
0x180044c51  jle     short loc_180044C63
0x180044c53  jmp     short loc_180044C5A
0x180044c55  mov     ebx, 216h
0x180044c5a  movzx   ebx, bx
0x180044c5d  or      ebx, 80070000h
0x180044c63  mov     rcx, [rbp+57h+ppszOut]; pv
0x180044c67  call    cs:__imp_CoTaskMemFree
0x180044c6e  nop     dword ptr [rax+rax+00h]
0x180044c73  mov     rcx, [rbp+57h+ppstm]
0x180044c77  mov     rax, [rcx]
0x180044c7a  mov     rax, [rax+10h]
0x180044c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c83  mov     rcx, [rbp+57h+hKey]; hKey
0x180044c87  call    cs:__imp_RegCloseKey
0x180044c8e  nop     dword ptr [rax+rax+00h]
0x180044c93  mov     eax, ebx
0x180044c95  mov     rcx, [rbp+57h+var_20]
0x180044c99  xor     rcx, rsp; StackCookie
0x180044c9c  call    __security_check_cookie
0x180044ca1  lea     r11, [rsp+0C0h+var_10]
0x180044ca9  mov     rbx, [r11+30h]
0x180044cad  mov     rsi, [r11+38h]
0x180044cb1  mov     rsp, r11
0x180044cb4  pop     r14
0x180044cb6  pop     rdi
0x180044cb7  pop     rbp
0x180044cb8  retn
```
