# SxIsAuditMode(void)

- ea: `0x18002d00c`
- end: `0x18002d0ac`
- name: `?SxIsAuditMode@@YAHXZ`
- size: `160`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006730`
- `0x180013c7c`

## callees

- `0x18002d00c`
- `0x18002e6e0`
- `0x180035b00`
- `0x180035ba6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d09e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d048`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d048`

## pseudocode

```c
_BOOL8 SxIsAuditMode(void)
{
  BOOL v0; // ebx
  wchar_t *String1[3]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  String1[0] = (wchar_t *)&FileName;
  hKey = 0;
  String1[1] = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
          0,
          0x20019u,
          &hKey)
    && (int)SxRegReadString(hKey, L"ImageState", (struct CBsString *)String1) >= 0 )
  {
    v0 = wcscmp_0(String1[0], L"IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT") == 0;
  }
  CBsString::_Release(String1);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18002d00c  mov     r11, rsp
0x18002d00f  push    rbx
0x18002d010  sub     rsp, 40h
0x18002d014  lea     rax, FileName
0x18002d01b  xor     ebx, ebx
0x18002d01d  mov     [r11-18h], rax
0x18002d021  lea     rdx, c_wszAuditModeRegistryKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d028  lea     rax, [r11+8]
0x18002d02c  mov     [r11+8], rbx
0x18002d030  mov     r9d, 20019h; samDesired
0x18002d036  mov     [r11-28h], rax
0x18002d03a  xor     r8d, r8d; ulOptions
0x18002d03d  mov     [r11-10h], rbx
0x18002d041  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d048  call    cs:__imp_RegOpenKeyExW
0x18002d04e  test    eax, eax
0x18002d050  jnz     short loc_18002D085
0x18002d052  mov     rcx, [rsp+48h+hKey]; hKey
0x18002d057  lea     r8, [rsp+48h+String1]; this
0x18002d05c  lea     rdx, c_wszImageState; "ImageState"
0x18002d063  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18002d068  test    eax, eax
0x18002d06a  js      short loc_18002D085
0x18002d06c  mov     rcx, [rsp+48h+String1]; String1
0x18002d071  lea     rdx, aImageStateSpec; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT"
0x18002d078  call    wcscmp_0
0x18002d07d  test    eax, eax
0x18002d07f  lea     ecx, [rbx+1]
0x18002d082  cmovz   ebx, ecx
0x18002d085  lea     rcx, [rsp+48h+String1]; this
0x18002d08a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002d08f  mov     rcx, [rsp+48h+hKey]; hKey
0x18002d094  lea     rdx, [rcx-1]
0x18002d098  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d09c  ja      short loc_18002D0A4
0x18002d09e  call    cs:__imp_RegCloseKey
0x18002d0a4  mov     eax, ebx
0x18002d0a6  add     rsp, 40h
0x18002d0aa  pop     rbx
0x18002d0ab  retn
```
