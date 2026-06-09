# GetDriveInfo(ushort,ushort *,ulong *)

- ea: `0x18002cf30`
- end: `0x18002d074`
- name: `?GetDriveInfo@@YAXGPEAGPEAK@Z`
- size: `324`
- prototype: `void(unsigned __int16, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ac8`

## callees

- `0x180005cc0`
- `0x1800094f0`
- `0x18000957c`
- `0x18002cf30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cfdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d03a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cfdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d03a`

## string_xrefs

- `0x18002cf6d`: `SOFTWARE\Microsoft\Windows Search\VolumeInfoCache`

## pseudocode

```c
void __fastcall GetDriveInfo(WCHAR a1, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v6; // r11d
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v8[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR SubKey[56]; // [rsp+50h] [rbp-B0h] BYREF
  size_t pvData[66]; // [rsp+C0h] [rbp-40h] BYREF

  *a2 = 0;
  *a3 = 3;
  StringCchCopyW(SubKey, 0x35u, (size_t *)L"SOFTWARE\\Microsoft\\Windows Search\\VolumeInfoCache");
  StringCchCatW(SubKey, v6, L"\\ :");
  SubKey[50] = a1;
  pcbData = 520;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"VolumeLabel", 2u, 0, pvData, &pcbData) )
    StringCchCopyW(a2, 0x104u, pvData);
  v8[0] = 0;
  pcbData = 4;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"DriveType", 0x10u, 0, v8, &pcbData) && v8[0] - 2 <= 1 )
    *a3 = v8[0];
}

```

## disassembly

```asm
0x18002cf30  mov     [rsp-8+arg_0], rbx
0x18002cf35  push    rbp
0x18002cf36  push    rsi
0x18002cf37  push    rdi
0x18002cf38  lea     rbp, [rsp-1E0h]
0x18002cf40  sub     rsp, 2E0h
0x18002cf47  mov     rax, cs:__security_cookie
0x18002cf4e  xor     rax, rsp
0x18002cf51  mov     [rbp+1F0h+var_20], rax
0x18002cf58  xor     eax, eax
0x18002cf5a  mov     rdi, r8
0x18002cf5d  mov     [rdx], ax
0x18002cf60  mov     rsi, rdx
0x18002cf63  movzx   ebx, cx
0x18002cf66  mov     dword ptr [r8], 3
0x18002cf6d  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows Search\\Vo"...
0x18002cf74  lea     r11d, [rax+35h]
0x18002cf78  mov     edx, r11d; unsigned __int64
0x18002cf7b  lea     rcx, [rsp+2F0h+SubKey]; unsigned __int16 *
0x18002cf80  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cf85  lea     r8, asc_180038460; "\\ :"
0x18002cf8c  mov     edx, r11d; unsigned __int64
0x18002cf8f  lea     rcx, [rsp+2F0h+SubKey]; unsigned __int16 *
0x18002cf94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cf99  lea     rax, [rsp+2F0h+var_2B0]
0x18002cf9e  mov     [rbp+1F0h+var_23C], bx
0x18002cfa2  mov     [rsp+2F0h+pcbData], rax; pcbData
0x18002cfa7  lea     r8, aVolumelabel; "VolumeLabel"
0x18002cfae  lea     rax, [rbp+1F0h+var_230]
0x18002cfb2  mov     [rsp+2F0h+var_2B0], 208h
0x18002cfba  mov     [rsp+2F0h+pvData], rax; pvData
0x18002cfbf  lea     rdx, [rsp+2F0h+SubKey]; lpSubKey
0x18002cfc4  mov     rbx, 0FFFFFFFF80000002h
0x18002cfcb  mov     [rsp+2F0h+pdwType], 0; pdwType
0x18002cfd4  mov     r9d, 2; dwFlags
0x18002cfda  mov     rcx, rbx; hkey
0x18002cfdd  call    cs:__imp_RegGetValueW
0x18002cfe3  test    eax, eax
0x18002cfe5  jnz     short loc_18002CFF8
0x18002cfe7  lea     r8, [rbp+1F0h+var_230]; unsigned __int16 *
0x18002cfeb  mov     edx, 104h; unsigned __int64
0x18002cff0  mov     rcx, rsi; unsigned __int16 *
0x18002cff3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cff8  lea     rax, [rsp+2F0h+var_2B0]
0x18002cffd  mov     [rsp+2F0h+var_2AC], 0
0x18002d005  mov     [rsp+2F0h+pcbData], rax; pcbData
0x18002d00a  lea     r8, aDrivetype; "DriveType"
0x18002d011  lea     rax, [rsp+2F0h+var_2AC]
0x18002d016  mov     [rsp+2F0h+var_2B0], 4
0x18002d01e  mov     [rsp+2F0h+pvData], rax; pvData
0x18002d023  lea     rdx, [rsp+2F0h+SubKey]; lpSubKey
0x18002d028  mov     r9d, 10h; dwFlags
0x18002d02e  mov     [rsp+2F0h+pdwType], 0; pdwType
0x18002d037  mov     rcx, rbx; hkey
0x18002d03a  call    cs:__imp_RegGetValueW
0x18002d040  test    eax, eax
0x18002d042  jnz     short loc_18002D052
0x18002d044  mov     ecx, [rsp+2F0h+var_2AC]
0x18002d048  lea     eax, [rcx-2]
0x18002d04b  cmp     eax, 1
0x18002d04e  ja      short loc_18002D052
0x18002d050  mov     [rdi], ecx
0x18002d052  mov     rcx, [rbp+1F0h+var_20]
0x18002d059  xor     rcx, rsp; StackCookie
0x18002d05c  call    __security_check_cookie
0x18002d061  mov     rbx, [rsp+2F0h+arg_0]
0x18002d069  add     rsp, 2E0h
0x18002d070  pop     rdi
0x18002d071  pop     rsi
0x18002d072  pop     rbp
0x18002d073  retn
```
