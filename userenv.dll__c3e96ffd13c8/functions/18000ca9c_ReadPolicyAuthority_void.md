# ReadPolicyAuthority(void)

- ea: `0x18000ca9c`
- end: `0x18000cb00`
- name: `?ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ`
- size: `100`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c97c`

## callees

- `0x18000ca9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cadf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cadf`

## string_xrefs

- `0x18000cad4`: `Software\Microsoft\Windows\CurrentVersion\UserState\UserStateTechnologies\ConfigurationControls`

## pseudocode

```c
__int64 ReadPolicyAuthority()
{
  unsigned int v0; // ebx
  LSTATUS ValueW; // eax
  bool v2; // sf
  unsigned int v4; // [rsp+50h] [rbp+8h] BYREF
  DWORD v5; // [rsp+58h] [rbp+10h] BYREF

  v0 = 0;
  v5 = 4;
  v4 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\UserStateTechnologies\\ConfigurationControls",
             L"RoamingUserProfile",
             0x10u,
             0,
             &v4,
             &v5);
  v2 = ValueW < 0;
  if ( ValueW > 0 )
    v2 = 1;
  if ( !v2 )
    return v4;
  return v0;
}

```

## disassembly

```asm
0x18000ca9c  mov     r11, rsp
0x18000ca9f  push    rbx
0x18000caa0  sub     rsp, 40h
0x18000caa4  xor     ebx, ebx
0x18000caa6  mov     [rsp+48h+arg_8], 4
0x18000caae  lea     rax, [r11+10h]
0x18000cab2  mov     [rsp+48h+arg_0], ebx
0x18000cab6  mov     [r11-18h], rax
0x18000caba  lea     r8, aRoaminguserpro; "RoamingUserProfile"
0x18000cac1  lea     rax, [r11+8]
0x18000cac5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000cacc  mov     [r11-20h], rax
0x18000cad0  lea     r9d, [rbx+10h]; dwFlags
0x18000cad4  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cadb  mov     [r11-28h], rbx
0x18000cadf  call    cs:__imp_RegGetValueW
0x18000cae5  test    eax, eax
0x18000cae7  jle     short loc_18000CAF3
0x18000cae9  movzx   eax, ax
0x18000caec  or      eax, 80070000h
0x18000caf1  test    eax, eax
0x18000caf3  cmovns  ebx, [rsp+48h+arg_0]
0x18000caf8  mov     eax, ebx
0x18000cafa  add     rsp, 40h
0x18000cafe  pop     rbx
0x18000caff  retn
```
