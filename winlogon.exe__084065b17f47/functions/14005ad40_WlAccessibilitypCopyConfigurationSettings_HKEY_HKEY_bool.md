# WlAccessibilitypCopyConfigurationSettings(HKEY__ *,HKEY__ *,bool)

- ea: `0x14005ad40`
- end: `0x14005ae7c`
- name: `?WlAccessibilitypCopyConfigurationSettings@@YAKPEAUHKEY__@@0_N@Z`
- size: `316`
- prototype: `unsigned int __fastcall(HKEY hKey, HKEY, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400180f0`

## callees

- `0x1400057f4`
- `0x14005ad40`
- `0x14005ae84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005ad79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005ad79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005adc6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005adc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ae5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ae6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ec85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ec95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ae5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ae6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ec85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ec95`

## string_xrefs

- `0x14005ad6f`: `ATConfig`
- `0x14005adbc`: `ATConfig`

## pseudocode

```c
__int64 __fastcall WlAccessibilitypCopyConfigurationSettings(HKEY hKey, HKEY a2)
{
  unsigned int v3; // ebx
  bool v4; // r8
  CUser *v5; // rcx
  __int64 v6; // rdx
  HKEY v8; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  hKeya = 0;
  if ( RegOpenKeyExW(a2, L"ATConfig", 0, 0x20019u, &v8) )
    goto LABEL_13;
  v3 = RegCreateKeyExW(hKey, L"ATConfig", 0, 0, 1u, 0xF003Fu, 0, &hKeya, 0);
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 33;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v3);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  v3 = WlAccessibilitypCopyRegTreeWithoutACLs(v8, hKeya, v4);
  if ( !v3 )
  {
LABEL_13:
    v3 = 0;
    goto LABEL_14;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 34;
    goto LABEL_7;
  }
LABEL_14:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v8 )
    RegCloseKey(v8);
  return v3;
}

```

## disassembly

```asm
0x14005ad40  mov     r11, rsp
0x14005ad43  push    rbx
0x14005ad44  sub     rsp, 60h
0x14005ad48  mov     rax, rdx
0x14005ad4b  mov     rbx, rcx
0x14005ad4e  mov     qword ptr [r11-18h], 0
0x14005ad56  mov     qword ptr [r11+20h], 0
0x14005ad5e  lea     rcx, [r11-18h]
0x14005ad62  mov     [r11-48h], rcx
0x14005ad66  mov     r9d, 20019h; samDesired
0x14005ad6c  xor     r8d, r8d; ulOptions
0x14005ad6f  lea     rdx, aAtconfig; "ATConfig"
0x14005ad76  mov     rcx, rax; hKey
0x14005ad79  call    cs:__imp_RegOpenKeyExW
0x14005ad7f  test    eax, eax
0x14005ad81  jnz     loc_14005AE4F
0x14005ad87  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x14005ad90  lea     rax, [rsp+68h+hKey]
0x14005ad98  mov     [rsp+68h+phkResult], rax; phkResult
0x14005ad9d  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14005ada6  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x14005adae  mov     [rsp+68h+dwOptions], 1; dwOptions
0x14005adb6  xor     r9d, r9d; lpClass
0x14005adb9  xor     r8d, r8d; Reserved
0x14005adbc  lea     rdx, aAtconfig; "ATConfig"
0x14005adc3  mov     rcx, rbx; hKey
0x14005adc6  call    cs:__imp_RegCreateKeyExW
0x14005adcc  mov     ebx, eax
0x14005adce  test    eax, eax
0x14005add0  jz      short loc_14005AE0E
0x14005add2  lea     rax, WPP_GLOBAL_Control
0x14005add9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ade0  cmp     rcx, rax
0x14005ade3  jz      short loc_14005AE51
0x14005ade5  test    dword ptr [rcx+1Ch], 40000h
0x14005adec  jz      short loc_14005AE51
0x14005adee  cmp     byte ptr [rcx+19h], 2
0x14005adf2  jb      short loc_14005AE51
0x14005adf4  mov     edx, 21h ; '!'
0x14005adf9  mov     r9d, ebx
0x14005adfc  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14005ae03  mov     rcx, [rcx+10h]
0x14005ae07  call    WPP_SF_d
0x14005ae0c  jmp     short loc_14005AE51
0x14005ae0e  mov     rdx, [rsp+68h+hKey]; HKEY
0x14005ae16  mov     rcx, [rsp+68h+var_18]; hKey
0x14005ae1b  call    ?WlAccessibilitypCopyRegTreeWithoutACLs@@YAKPEAUHKEY__@@0_N@Z; WlAccessibilitypCopyRegTreeWithoutACLs(HKEY__ *,HKEY__ *,bool)
0x14005ae20  mov     ebx, eax
0x14005ae22  test    eax, eax
0x14005ae24  jz      short loc_14005AE4F
0x14005ae26  lea     rax, WPP_GLOBAL_Control
0x14005ae2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae34  cmp     rcx, rax
0x14005ae37  jz      short loc_14005AE51
0x14005ae39  test    dword ptr [rcx+1Ch], 40000h
0x14005ae40  jz      short loc_14005AE51
0x14005ae42  cmp     byte ptr [rcx+19h], 2
0x14005ae46  jb      short loc_14005AE51
0x14005ae48  mov     edx, 22h ; '"'
0x14005ae4d  jmp     short loc_14005ADF9
0x14005ae4f  xor     ebx, ebx
0x14005ae51  mov     rcx, [rsp+68h+hKey]; hKey
0x14005ae59  test    rcx, rcx
0x14005ae5c  jz      short loc_14005AE64
0x14005ae5e  call    cs:__imp_RegCloseKey
0x14005ae64  mov     rcx, [rsp+68h+var_18]; hKey
0x14005ae69  test    rcx, rcx
0x14005ae6c  jz      short loc_14005AE74
0x14005ae6e  call    cs:__imp_RegCloseKey
0x14005ae74  mov     eax, ebx
0x14005ae76  add     rsp, 60h
0x14005ae7a  pop     rbx
0x14005ae7b  retn
0x14009ec70  push    rbp
0x14009ec72  sub     rsp, 50h
0x14009ec76  mov     rbp, rdx
0x14009ec79  mov     rcx, [rbp+88h]; hKey
0x14009ec80  test    rcx, rcx
0x14009ec83  jz      short loc_14009EC8C
0x14009ec85  call    cs:__imp_RegCloseKey
0x14009ec8b  nop
0x14009ec8c  mov     rcx, [rbp+50h]; hKey
0x14009ec90  test    rcx, rcx
0x14009ec93  jz      short loc_14009EC9C
0x14009ec95  call    cs:__imp_RegCloseKey
0x14009ec9b  nop
0x14009ec9c  add     rsp, 50h
0x14009eca0  pop     rbp
0x14009eca1  retn
```
