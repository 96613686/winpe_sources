# SetSelectiveBindingBuffer(ulong,void *)

- ea: `0x1800cc458`
- end: `0x1800cc512`
- name: `?SetSelectiveBindingBuffer@@YAKKPEAX@Z`
- size: `186`
- prototype: `unsigned int __fastcall(DWORD cbData, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800cb5b0`

## callees

- `0x1800cc458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cc4f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cc4f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cc4b9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cc4b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cc4e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cc4e5`

## string_xrefs

- `0x1800cc496`: `System\CurrentControlSet\Services\Rpc\Linkage`

## pseudocode

```c
LSTATUS __fastcall SetSelectiveBindingBuffer(DWORD cbData, BYTE *lpData)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  DWORD v6; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v6 = 0;
  result = RegCreateKeyExA(
             HKEY_LOCAL_MACHINE,
             "System\\CurrentControlSet\\Services\\Rpc\\Linkage",
             0,
             (LPSTR)Class,
             0,
             0x20006u,
             0,
             &hKey,
             &v6);
  if ( !result )
  {
    v5 = RegSetValueExA(hKey, "Bind", 0, 3u, lpData, cbData);
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800cc458  mov     r11, rsp
0x1800cc45b  mov     [r11+8], rbx
0x1800cc45f  push    rdi
0x1800cc460  sub     rsp, 50h
0x1800cc464  lea     rax, [r11+18h]
0x1800cc468  mov     qword ptr [r11+20h], 0
0x1800cc470  mov     [r11-18h], rax
0x1800cc474  lea     r9, Class; lpClass
0x1800cc47b  lea     rax, [r11+20h]
0x1800cc47f  mov     [rsp+58h+arg_10], 0
0x1800cc487  mov     [r11-20h], rax
0x1800cc48b  mov     rbx, rdx
0x1800cc48e  mov     qword ptr [r11-28h], 0
0x1800cc496  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Rp"...
0x1800cc49d  mov     edi, ecx
0x1800cc49f  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800cc4a7  xor     r8d, r8d; Reserved
0x1800cc4aa  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800cc4b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cc4b9  call    cs:__imp_RegCreateKeyExA
0x1800cc4c0  nop     dword ptr [rax+rax+00h]
0x1800cc4c5  test    eax, eax
0x1800cc4c7  jnz     short loc_1800CC506
0x1800cc4c9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800cc4ce  lea     r9d, [rax+3]; dwType
0x1800cc4d2  mov     [rsp+58h+samDesired], edi; cbData
0x1800cc4d6  lea     rdx, aBind; "Bind"
0x1800cc4dd  xor     r8d, r8d; Reserved
0x1800cc4e0  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x1800cc4e5  call    cs:__imp_RegSetValueExA
0x1800cc4ec  nop     dword ptr [rax+rax+00h]
0x1800cc4f1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800cc4f6  mov     ebx, eax
0x1800cc4f8  call    cs:__imp_RegCloseKey
0x1800cc4ff  nop     dword ptr [rax+rax+00h]
0x1800cc504  mov     eax, ebx
0x1800cc506  mov     rbx, [rsp+58h+arg_0]
0x1800cc50b  add     rsp, 50h
0x1800cc50f  pop     rdi
0x1800cc510  retn
```
