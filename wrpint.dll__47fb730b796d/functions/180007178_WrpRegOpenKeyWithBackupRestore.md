# WrpRegOpenKeyWithBackupRestore

- ea: `0x180007178`
- end: `0x180007280`
- name: `WrpRegOpenKeyWithBackupRestore`
- size: `264`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006f84`

## callees

- `0x180007178`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000721d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000721d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007213`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007213`

## pseudocode

```c
__int64 __fastcall WrpRegOpenKeyWithBackupRestore(__int64 a1, const WCHAR *a2, __int64 a3, HKEY *a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  signed int LastError; // eax
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x2001Fu, &hKey);
  v7 = v6;
  if ( v6 != 5 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_5;
LABEL_11:
    v7 = 0;
    *a4 = hKey;
    return v7;
  }
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 4u, 0x2001Fu, 0, &hKey, &dwDisposition) )
    goto LABEL_11;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180007178  mov     r11, rsp
0x18000717b  mov     [r11+8], rbx
0x18000717f  mov     [r11+18h], rsi
0x180007183  push    rdi
0x180007184  sub     rsp, 70h
0x180007188  mov     rax, cs:__security_cookie
0x18000718f  xor     rax, rsp
0x180007192  mov     [rsp+78h+var_18], rax
0x180007197  mov     rdi, r9
0x18000719a  mov     qword ptr [r11-28h], 0
0x1800071a2  lea     rax, [r11-28h]
0x1800071a6  mov     [rsp+78h+dwDisposition], 0
0x1800071ae  mov     r9d, 2001Fh; samDesired
0x1800071b4  mov     [r11-58h], rax
0x1800071b8  xor     r8d, r8d; ulOptions
0x1800071bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800071c2  mov     rsi, rdx
0x1800071c5  call    cs:__imp_RegOpenKeyExW
0x1800071cb  mov     ebx, eax
0x1800071cd  cmp     eax, 5
0x1800071d0  jnz     loc_180007263
0x1800071d6  lea     rax, [rsp+78h+dwDisposition]
0x1800071db  xor     r9d, r9d; lpClass
0x1800071de  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x1800071e3  xor     r8d, r8d; Reserved
0x1800071e6  lea     rax, [rsp+78h+hKey]
0x1800071eb  mov     rdx, rsi; lpSubKey
0x1800071ee  mov     [rsp+78h+phkResult], rax; phkResult
0x1800071f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800071fa  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180007203  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18000720b  mov     [rsp+78h+dwOptions], 4; dwOptions
0x180007213  call    cs:__imp_RegCreateKeyExW
0x180007219  test    eax, eax
0x18000721b  jz      short loc_180007274
0x18000721d  call    cs:__imp_GetLastError
0x180007223  mov     ebx, eax
0x180007225  test    eax, eax
0x180007227  jle     short loc_180007232
0x180007229  movzx   ebx, ax
0x18000722c  or      ebx, 80070000h
0x180007232  mov     rcx, [rsp+78h+hKey]; hKey
0x180007237  test    rcx, rcx
0x18000723a  jz      short loc_180007242
0x18000723c  call    cs:__imp_RegCloseKey
0x180007242  mov     eax, ebx
0x180007244  mov     rcx, [rsp+78h+var_18]
0x180007249  xor     rcx, rsp; StackCookie
0x18000724c  call    __security_check_cookie
0x180007251  lea     r11, [rsp+78h+var_8]
0x180007256  mov     rbx, [r11+10h]
0x18000725a  mov     rsi, [r11+20h]
0x18000725e  mov     rsp, r11
0x180007261  pop     rdi
0x180007262  retn
0x180007263  test    eax, eax
0x180007265  jle     short loc_180007270
0x180007267  movzx   ebx, ax
0x18000726a  or      ebx, 80070000h
0x180007270  test    ebx, ebx
0x180007272  js      short loc_180007232
0x180007274  mov     rax, [rsp+78h+hKey]
0x180007279  xor     ebx, ebx
0x18000727b  mov     [rdi], rax
0x18000727e  jmp     short loc_180007242
```
