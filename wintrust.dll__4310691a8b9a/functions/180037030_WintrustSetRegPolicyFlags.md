# WintrustSetRegPolicyFlags

- ea: `0x180037030`
- end: `0x1800370af`
- name: `WintrustSetRegPolicyFlags`
- size: `127`
- prototype: `BOOL __stdcall(DWORD dwPolicyFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013ec0`
- `0x180037030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003708f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003708f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800370a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800370a1`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall WintrustSetRegPolicyFlags(DWORD dwPolicyFlags)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  BOOL v5; // ebx
  int lpData; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+30h] [rbp-28h]
  DWORD Data; // [rsp+60h] [rbp+8h] BYREF
  DWORD v9; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = dwPolicyFlags;
  hKey = 0;
  v9 = 0;
  if ( RegCreateHKCUKeyExU(*(__int64 *)&dwPolicyFlags, v1, v2, v3, lpData, 0x20006u, v7, &hKey, &v9) )
    return 0;
  v5 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u) == 0;
  RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180037030  mov     [rsp+Data], ecx
0x180037034  mov     r11, rsp
0x180037037  push    rbx
0x180037038  sub     rsp, 50h
0x18003703c  lea     rax, [r11+10h]
0x180037040  xor     ebx, ebx
0x180037042  mov     [r11-18h], rax
0x180037046  lea     rax, [r11+18h]
0x18003704a  mov     [r11-20h], rax
0x18003704e  mov     [rsp+58h+cbData], 20006h; REGSAM
0x180037056  mov     [r11+18h], rbx
0x18003705a  mov     [rsp+58h+arg_8], ebx
0x18003705e  call    RegCreateHKCUKeyExU
0x180037063  test    eax, eax
0x180037065  jz      short loc_18003706B
0x180037067  xor     eax, eax
0x180037069  jmp     short loc_1800370A9
0x18003706b  mov     rcx, [rsp+58h+hKey]; hKey
0x180037070  lea     rax, [rsp+58h+Data]
0x180037075  mov     r9d, 4; dwType
0x18003707b  lea     rdx, aState; "State"
0x180037082  mov     [rsp+58h+cbData], r9d; cbData
0x180037087  xor     r8d, r8d; Reserved
0x18003708a  mov     [rsp+58h+lpData], rax; lpData
0x18003708f  call    cs:__imp_RegSetValueExW
0x180037095  test    eax, eax
0x180037097  jnz     short loc_18003709C
0x180037099  lea     ebx, [rax+1]
0x18003709c  mov     rcx, [rsp+58h+hKey]; hKey
0x1800370a1  call    cs:__imp_RegCloseKey
0x1800370a7  mov     eax, ebx
0x1800370a9  add     rsp, 50h
0x1800370ad  pop     rbx
0x1800370ae  retn
```
