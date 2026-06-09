# UpdateMiniportsEnabledRegistry

- ea: `0x180008ac0`
- end: `0x180008b87`
- name: `UpdateMiniportsEnabledRegistry`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800067b4`

## callees

- `0x180006f5c`
- `0x180008ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008b55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008b55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008b21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008b21`

## string_xrefs

- `0x180008b13`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180008b4e`: `MiniportsInstalled`

## pseudocode

```c
__int64 __fastcall UpdateMiniportsEnabledRegistry(int a1, int a2)
{
  int MiniportsEnabledRegistry; // eax
  int v5; // ebx
  unsigned int v6; // edi
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  MiniportsEnabledRegistry = GetMiniportsEnabledRegistry();
  if ( a2 == 8 )
  {
    v5 = MiniportsEnabledRegistry & ~a1;
  }
  else
  {
    v6 = 0;
    if ( a2 != 1 )
      goto LABEL_7;
    v5 = MiniportsEnabledRegistry | a1;
  }
  Data = v5;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters", 0, 0x20006u, &hKey);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, L"MiniportsInstalled", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_7:
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180008ac0  mov     rax, rsp
0x180008ac3  mov     [rax+8], rbx
0x180008ac7  mov     [rax+20h], rsi
0x180008acb  push    rdi
0x180008acc  sub     rsp, 30h
0x180008ad0  mov     esi, edx
0x180008ad2  mov     qword ptr [rax+18h], 0
0x180008ada  mov     ebx, ecx
0x180008adc  mov     dword ptr [rax+10h], 0
0x180008ae3  call    GetMiniportsEnabledRegistry
0x180008ae8  cmp     esi, 8
0x180008aeb  jnz     short loc_180008AF3
0x180008aed  not     ebx
0x180008aef  and     ebx, eax
0x180008af1  jmp     short loc_180008AFC
0x180008af3  xor     edi, edi
0x180008af5  cmp     esi, 1
0x180008af8  jnz     short loc_180008B63
0x180008afa  or      ebx, eax
0x180008afc  lea     rax, [rsp+38h+hKey]
0x180008b01  mov     [rsp+38h+Data], ebx
0x180008b05  mov     r9d, 20006h; samDesired
0x180008b0b  mov     [rsp+38h+phkResult], rax; phkResult
0x180008b10  xor     r8d, r8d; ulOptions
0x180008b13  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180008b1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008b21  call    cs:__imp_RegOpenKeyExW
0x180008b28  nop     dword ptr [rax+rax+00h]
0x180008b2d  mov     edi, eax
0x180008b2f  test    eax, eax
0x180008b31  jnz     short loc_180008B63
0x180008b33  mov     rcx, [rsp+38h+hKey]; hKey
0x180008b38  lea     r9d, [rax+4]; dwType
0x180008b3c  lea     rax, [rsp+38h+Data]
0x180008b41  mov     [rsp+38h+cbData], r9d; cbData
0x180008b46  xor     r8d, r8d; Reserved
0x180008b49  mov     [rsp+38h+phkResult], rax; lpData
0x180008b4e  lea     rdx, ValueName; "MiniportsInstalled"
0x180008b55  call    cs:__imp_RegSetValueExW
0x180008b5c  nop     dword ptr [rax+rax+00h]
0x180008b61  mov     edi, eax
0x180008b63  mov     rcx, [rsp+38h+hKey]; hKey
0x180008b68  call    cs:__imp_RegCloseKey
0x180008b6f  nop     dword ptr [rax+rax+00h]
0x180008b74  mov     rbx, [rsp+38h+arg_0]
0x180008b79  mov     eax, edi
0x180008b7b  mov     rsi, [rsp+38h+arg_18]
0x180008b80  add     rsp, 30h
0x180008b84  pop     rdi
0x180008b85  retn
```
