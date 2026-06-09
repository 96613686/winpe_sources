# RegSetValue_Helper

- ea: `0x1800102c0`
- end: `0x18001034f`
- name: `RegSetValue_Helper`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010358`
- `0x1800103b8`

## callees

- `0x180010150`
- `0x1800102c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001033c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001033c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001030c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001030c`

## pseudocode

```c
__int64 __fastcall RegSetValue_Helper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  signed int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v8 = RegCreateKeyHelperPrivate(a1, a2, a3, &hKey);
  if ( v8 >= 0 )
  {
    v9 = RegSetValueExW(hKey, a4, 0, dwType, lpData, cbData);
    if ( v9 )
    {
      v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v8 = v9;
    }
  }
  if ( hKey != HKEY_LOCAL_MACHINE && hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800102c0  mov     rax, rsp
0x1800102c3  mov     [rax+10h], rbx
0x1800102c7  mov     [rax+8], rcx
0x1800102cb  push    rsi
0x1800102cc  sub     rsp, 30h
0x1800102d0  mov     rsi, r9
0x1800102d3  mov     qword ptr [rax+8], 0
0x1800102db  lea     r9, [rax+8]
0x1800102df  call    RegCreateKeyHelperPrivate
0x1800102e4  mov     ebx, eax
0x1800102e6  test    eax, eax
0x1800102e8  js      short loc_180010324
0x1800102ea  mov     ecx, [rsp+38h+arg_30]
0x1800102ee  xor     r8d, r8d; Reserved
0x1800102f1  mov     r9d, [rsp+38h+dwType]; dwType
0x1800102f6  mov     rdx, rsi; lpValueName
0x1800102f9  mov     [rsp+38h+cbData], ecx; cbData
0x1800102fd  mov     rcx, [rsp+38h+arg_28]
0x180010302  mov     [rsp+38h+lpData], rcx; lpData
0x180010307  mov     rcx, [rsp+38h+hKey]; hKey
0x18001030c  call    cs:__imp_RegSetValueExW
0x180010312  test    eax, eax
0x180010314  jz      short loc_180010324
0x180010316  movzx   ebx, ax
0x180010319  or      ebx, 80070000h
0x18001031f  test    eax, eax
0x180010321  cmovle  ebx, eax
0x180010324  cmp     [rsp+38h+hKey], 0FFFFFFFF80000002h
0x18001032d  jz      short loc_180010342
0x18001032f  cmp     [rsp+38h+hKey], 0
0x180010335  jz      short loc_180010342
0x180010337  mov     rcx, [rsp+38h+hKey]; hKey
0x18001033c  call    cs:__imp_RegCloseKey
0x180010342  mov     eax, ebx
0x180010344  mov     rbx, [rsp+38h+arg_8]
0x180010349  add     rsp, 30h
0x18001034d  pop     rsi
0x18001034e  retn
```
