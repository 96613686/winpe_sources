# RegSetValue_Helper

- ea: `0x14001095c`
- end: `0x1400109e4`
- name: `RegSetValue_Helper`
- size: `136`
- prototype: `__int64 __fastcall(int, int, int, int, int, BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400197cc`

## callees

- `0x1400107fc`
- `0x14001095c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400109a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400109a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400109d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400109d6`

## pseudocode

```c
__int64 __fastcall RegSetValue_Helper(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        int a5,
        BYTE *lpData,
        DWORD cbData)
{
  int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v7 = RegCreateKeyHelperPrivate(a1, a2, a3, &hKey);
  if ( v7 >= 0 )
  {
    v8 = RegSetValueExW(hKey, L"AppID", 0, 1u, lpData, cbData);
    if ( v8 )
    {
      v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v7 = v8;
    }
  }
  if ( hKey != HKEY_LOCAL_MACHINE && hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001095c  mov     [rsp+hKey], r9
0x140010961  push    rbx
0x140010962  sub     rsp, 30h
0x140010966  lea     r9, [rsp+38h+hKey]
0x14001096b  mov     [rsp+38h+hKey], 0
0x140010974  call    RegCreateKeyHelperPrivate
0x140010979  mov     ebx, eax
0x14001097b  test    eax, eax
0x14001097d  js      short loc_1400109BE
0x14001097f  mov     ecx, [rsp+38h+arg_30]
0x140010983  lea     rdx, ValueName; "AppID"
0x14001098a  mov     [rsp+38h+cbData], ecx; cbData
0x14001098e  mov     r9d, 1; dwType
0x140010994  mov     rcx, [rsp+38h+arg_28]
0x140010999  xor     r8d, r8d; Reserved
0x14001099c  mov     [rsp+38h+lpData], rcx; lpData
0x1400109a1  mov     rcx, [rsp+38h+hKey]; hKey
0x1400109a6  call    cs:__imp_RegSetValueExW
0x1400109ac  test    eax, eax
0x1400109ae  jz      short loc_1400109BE
0x1400109b0  movzx   ebx, ax
0x1400109b3  or      ebx, 80070000h
0x1400109b9  test    eax, eax
0x1400109bb  cmovle  ebx, eax
0x1400109be  cmp     [rsp+38h+hKey], 0FFFFFFFF80000002h
0x1400109c7  jz      short loc_1400109DC
0x1400109c9  cmp     [rsp+38h+hKey], 0
0x1400109cf  jz      short loc_1400109DC
0x1400109d1  mov     rcx, [rsp+38h+hKey]; hKey
0x1400109d6  call    cs:__imp_RegCloseKey
0x1400109dc  mov     eax, ebx
0x1400109de  add     rsp, 30h
0x1400109e2  pop     rbx
0x1400109e3  retn
```
