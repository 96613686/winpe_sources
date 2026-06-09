# WsSaveGlobalMappingToRegistry

- ea: `0x1800315f8`
- end: `0x180031693`
- name: `WsSaveGlobalMappingToRegistry`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001750`

## callees

- `0x1800312d8`
- `0x1800315f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031653`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031679`

## pseudocode

```c
__int64 __fastcall WsSaveGlobalMappingToRegistry(__int64 a1)
{
  unsigned int v2; // ebx
  DWORD v4; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v4 = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &v4);
  if ( !v2 )
  {
    v2 = SaveConnectionInfoToRegistry(hKey, a1);
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800315f8  mov     r11, rsp
0x1800315fb  mov     [r11+8], rbx
0x1800315ff  push    rdi
0x180031600  sub     rsp, 50h
0x180031604  lea     rax, [r11+10h]
0x180031608  mov     qword ptr [r11+18h], 0
0x180031610  mov     [r11-18h], rax
0x180031614  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18003161b  lea     rax, [r11+18h]
0x18003161f  mov     [rsp+58h+arg_8], 0
0x180031627  mov     [r11-20h], rax
0x18003162b  mov     rdi, rcx
0x18003162e  mov     qword ptr [r11-28h], 0
0x180031636  xor     r9d, r9d; lpClass
0x180031639  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180031641  xor     r8d, r8d; Reserved
0x180031644  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003164b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180031653  call    cs:__imp_RegCreateKeyExW
0x18003165a  nop     dword ptr [rax+rax+00h]
0x18003165f  mov     ebx, eax
0x180031661  test    eax, eax
0x180031663  jnz     short loc_180031685
0x180031665  mov     rcx, [rsp+58h+hKey]
0x18003166a  mov     rdx, rdi
0x18003166d  call    SaveConnectionInfoToRegistry
0x180031672  mov     rcx, [rsp+58h+hKey]; hKey
0x180031677  mov     ebx, eax
0x180031679  call    cs:__imp_RegCloseKey
0x180031680  nop     dword ptr [rax+rax+00h]
0x180031685  mov     eax, ebx
0x180031687  mov     rbx, [rsp+58h+arg_0]
0x18003168c  add     rsp, 50h
0x180031690  pop     rdi
0x180031691  retn
```
