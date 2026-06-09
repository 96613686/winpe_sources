# SaveToWallpaperMRU(_ITEMIDLIST_ABSOLUTE *,ushort const *)

- ea: `0x180022534`
- end: `0x1800226a0`
- name: `?SaveToWallpaperMRU@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003336c`

## callees

- `0x1800089c0`
- `0x18001987c`
- `0x180022534`
- `0x1800358c0`
- `0x18006d010`

## import_xrefs

- `SHELL32!__imp_ILSaveToStream` at `0x1800225dc`
- `SHELL32!__imp_ILSaveToStream` at `0x1800225dc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800225c5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800225c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002265d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002265d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800225a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800225a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022677`
- `PROPSYS!PropVariantToStringAlloc` at `0x180022616`
- `PROPSYS!PropVariantToStringAlloc` at `0x180022616`

## pseudocode

```c
__int64 __fastcall SaveToWallpaperMRU(LPCITEMIDLIST pidl, const unsigned __int16 *a2)
{
  HRESULT v3; // ebx
  LPSTREAM ppstm; // [rsp+58h] [rbp-9h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+7h] BYREF
  PROPVARIANT propvar[2]; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v9; // [rsp+80h] [rbp+1Fh]
  unsigned __int16 v10[16]; // [rsp+88h] [rbp+27h] BYREF

  hKey = 0;
  v3 = -2147467259;
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
    v3 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v3 >= 0 )
    {
      v3 = ILSaveToStream(ppstm, pidl);
      if ( v3 >= 0 )
      {
        ppszOut = 0;
        v9 = 0;
        propvar[0] = (PROPVARIANT)66;
        propvar[1] = ppstm;
        v3 = PropVariantToStringAlloc(propvar, &ppszOut);
        if ( v3 >= 0 )
        {
          v3 = StringCchPrintfW(v10, 0xDu, L"ID%s", L"-1");
          if ( v3 >= 0 )
            v3 = SHRegSetString(hKey, 0, v10, ppszOut);
          CoTaskMemFree(ppszOut);
        }
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022534  mov     r11, rsp
0x180022537  mov     [r11+10h], rbx
0x18002253b  mov     [r11+18h], rdi
0x18002253f  push    rbp
0x180022540  lea     rbp, [r11-5Fh]
0x180022544  sub     rsp, 0B0h
0x18002254b  mov     rax, cs:__security_cookie
0x180022552  xor     rax, rsp
0x180022555  mov     [rbp+57h+var_10], rax
0x180022559  mov     qword ptr [r11-78h], 0
0x180022561  lea     rax, [rbp+57h+hKey]
0x180022565  mov     [r11-80h], rax
0x180022569  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022570  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180022579  mov     rdi, rcx
0x18002257c  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x180022584  xor     r9d, r9d; lpClass
0x180022587  xor     r8d, r8d; Reserved
0x18002258a  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x180022592  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180022599  mov     [rbp+57h+hKey], 0
0x1800225a1  mov     ebx, 80004005h
0x1800225a6  call    cs:__imp_RegCreateKeyExW
0x1800225ac  test    eax, eax
0x1800225ae  jnz     loc_18002267D
0x1800225b4  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800225b8  mov     [rbp+57h+ppstm], 0
0x1800225c0  lea     edx, [rax+1]; fDeleteOnRelease
0x1800225c3  xor     ecx, ecx; hGlobal
0x1800225c5  call    cs:__imp_CreateStreamOnHGlobal
0x1800225cb  mov     ebx, eax
0x1800225cd  test    eax, eax
0x1800225cf  js      loc_180022673
0x1800225d5  mov     rcx, [rbp+57h+ppstm]; pstm
0x1800225d9  mov     rdx, rdi; pidl
0x1800225dc  call    cs:__imp_ILSaveToStream
0x1800225e2  mov     ebx, eax
0x1800225e4  test    eax, eax
0x1800225e6  js      short loc_180022663
0x1800225e8  xor     eax, eax
0x1800225ea  mov     [rbp+57h+ppszOut], 0
0x1800225f2  mov     [rbp+57h+var_38], rax
0x1800225f6  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x1800225fa  xorps   xmm0, xmm0
0x1800225fd  lea     rcx, [rbp+57h+propvar]; propvar
0x180022601  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x180022605  mov     eax, 42h ; 'B'
0x18002260a  mov     word ptr [rbp+57h+propvar], ax
0x18002260e  mov     rax, [rbp+57h+ppstm]
0x180022612  mov     [rbp+57h+propvar+8], rax
0x180022616  call    cs:__imp_PropVariantToStringAlloc
0x18002261c  mov     ebx, eax
0x18002261e  test    eax, eax
0x180022620  js      short loc_180022663
0x180022622  lea     r9, a1; "-1"
0x180022629  mov     edx, 0Dh; unsigned __int64
0x18002262e  lea     r8, aIdS; "ID%s"
0x180022635  lea     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x180022639  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002263e  mov     ebx, eax
0x180022640  test    eax, eax
0x180022642  js      short loc_180022659
0x180022644  mov     r9, [rbp+57h+ppszOut]; unsigned __int16 *
0x180022648  lea     r8, [rbp+57h+var_30]; unsigned __int16 *
0x18002264c  mov     rcx, [rbp+57h+hKey]; HKEY
0x180022650  xor     edx, edx; unsigned __int16 *
0x180022652  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180022657  mov     ebx, eax
0x180022659  mov     rcx, [rbp+57h+ppszOut]; pv
0x18002265d  call    cs:__imp_CoTaskMemFree
0x180022663  mov     rcx, [rbp+57h+ppstm]
0x180022667  mov     rax, [rcx]
0x18002266a  mov     rax, [rax+10h]
0x18002266e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022673  mov     rcx, [rbp+57h+hKey]; hKey
0x180022677  call    cs:__imp_RegCloseKey
0x18002267d  mov     eax, ebx
0x18002267f  mov     rcx, [rbp+57h+var_10]
0x180022683  xor     rcx, rsp; StackCookie
0x180022686  call    __security_check_cookie
0x18002268b  lea     r11, [rsp+0B0h+var_s0]
0x180022693  mov     rbx, [r11+18h]
0x180022697  mov     rdi, [r11+20h]
0x18002269b  mov     rsp, r11
0x18002269e  pop     rbp
0x18002269f  retn
```
