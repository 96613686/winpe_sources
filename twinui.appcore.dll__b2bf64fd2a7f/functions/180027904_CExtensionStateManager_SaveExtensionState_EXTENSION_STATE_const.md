# CExtensionStateManager::_SaveExtensionState(EXTENSION_STATE const *)

- ea: `0x180027904`
- end: `0x180027a12`
- name: `?_SaveExtensionState@CExtensionStateManager@@AEAAJPEBUEXTENSION_STATE@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CExtensionStateManager *this, const WCHAR *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180078310`
- `0x18007b210`
- `0x18007c2c0`
- `0x18007c5b0`

## callees

- `0x180027904`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800279ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800279ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002795f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002795f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800279a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800279e5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800279a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800279e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CExtensionStateManager::_SaveExtensionState(CExtensionStateManager *this, const WCHAR *a2)
{
  HKEY v2; // rcx
  signed int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    hKey = 0;
    v5 = RegCreateKeyExW(v2, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 >= 0 )
    {
      v6 = RegSetKeyValueW(hKey, 0, L"State", 4u, a2 + 260, 4u);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 >= 0 )
      {
        v7 = RegSetKeyValueW(hKey, 0, L"PinnedOrder", 4u, a2 + 262, 4u);
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027904  mov     [rsp+arg_8], rbx
0x180027909  push    rdi
0x18002790a  sub     rsp, 50h
0x18002790e  mov     rcx, [rcx+10h]; hKey
0x180027912  mov     rdi, rdx
0x180027915  test    rcx, rcx
0x180027918  jnz     short loc_180027924
0x18002791a  mov     ebx, 8000FFFFh
0x18002791f  jmp     loc_180027A05
0x180027924  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002792d  lea     rax, [rsp+58h+hKey]
0x180027932  mov     [rsp+58h+phkResult], rax; phkResult
0x180027937  xor     r9d, r9d; lpClass
0x18002793a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027943  xor     r8d, r8d; Reserved
0x180027946  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18002794e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180027956  mov     [rsp+58h+hKey], 0
0x18002795f  call    cs:__imp_RegCreateKeyExW
0x180027965  mov     ebx, eax
0x180027967  test    eax, eax
0x180027969  jle     short loc_180027974
0x18002796b  movzx   ebx, ax
0x18002796e  or      ebx, 80070000h
0x180027974  test    ebx, ebx
0x180027976  js      loc_180027A05
0x18002797c  mov     rcx, [rsp+58h+hKey]; hKey
0x180027981  lea     rax, [rdi+208h]
0x180027988  mov     [rsp+58h+samDesired], 4; cbData
0x180027990  lea     r8, ValueName; "State"
0x180027997  mov     r9d, 4; dwType
0x18002799d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800279a2  xor     edx, edx; lpSubKey
0x1800279a4  call    cs:__imp_RegSetKeyValueW
0x1800279aa  mov     ebx, eax
0x1800279ac  test    eax, eax
0x1800279ae  jle     short loc_1800279B9
0x1800279b0  movzx   ebx, ax
0x1800279b3  or      ebx, 80070000h
0x1800279b9  test    ebx, ebx
0x1800279bb  js      short loc_1800279FA
0x1800279bd  mov     rcx, [rsp+58h+hKey]; hKey
0x1800279c2  lea     rax, [rdi+20Ch]
0x1800279c9  mov     [rsp+58h+samDesired], 4; cbData
0x1800279d1  lea     r8, aPinnedorder; "PinnedOrder"
0x1800279d8  mov     r9d, 4; dwType
0x1800279de  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800279e3  xor     edx, edx; lpSubKey
0x1800279e5  call    cs:__imp_RegSetKeyValueW
0x1800279eb  mov     ebx, eax
0x1800279ed  test    eax, eax
0x1800279ef  jle     short loc_1800279FA
0x1800279f1  movzx   ebx, ax
0x1800279f4  or      ebx, 80070000h
0x1800279fa  mov     rcx, [rsp+58h+hKey]; hKey
0x1800279ff  call    cs:__imp_RegCloseKey
0x180027a05  mov     eax, ebx
0x180027a07  mov     rbx, [rsp+58h+arg_8]
0x180027a0c  add     rsp, 50h
0x180027a10  pop     rdi
0x180027a11  retn
```
