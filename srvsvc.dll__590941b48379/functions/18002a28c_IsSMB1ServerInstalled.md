# IsSMB1ServerInstalled

- ea: `0x18002a28c`
- end: `0x18002a2e1`
- name: `IsSMB1ServerInstalled`
- size: `85`
- prototype: `LSTATUS __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002b5d8`

## callees

- `0x18002a28c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2c0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002a2b1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002a2b1`

## string_xrefs

- `0x18002a2aa`: `System\CurrentControlSet\Services\Srv`

## pseudocode

```c
LSTATUS __fastcall IsSMB1ServerInstalled(_DWORD *a1)
{
  LSTATUS result; // eax
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  phkResult = 0;
  result = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Srv", &phkResult);
  if ( result )
  {
    if ( result != 2 )
      return result;
    *a1 = 0;
  }
  else
  {
    RegCloseKey(phkResult);
    *a1 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a28c  push    rbx
0x18002a28e  sub     rsp, 20h
0x18002a292  mov     rbx, rcx
0x18002a295  mov     [rsp+28h+phkResult], 0
0x18002a29e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a2a5  lea     r8, [rsp+28h+phkResult]; phkResult
0x18002a2aa  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Sr"...
0x18002a2b1  call    cs:__imp_RegOpenKeyW
0x18002a2b7  test    eax, eax
0x18002a2b9  jnz     short loc_18002A2CE
0x18002a2bb  mov     rcx, [rsp+28h+phkResult]; hKey
0x18002a2c0  call    cs:__imp_RegCloseKey
0x18002a2c6  mov     dword ptr [rbx], 1
0x18002a2cc  jmp     short loc_18002A2D9
0x18002a2ce  cmp     eax, 2
0x18002a2d1  jnz     short loc_18002A2DB
0x18002a2d3  mov     dword ptr [rbx], 0
0x18002a2d9  xor     eax, eax
0x18002a2db  add     rsp, 20h
0x18002a2df  pop     rbx
0x18002a2e0  retn
```
