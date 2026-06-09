# ReadPolicyAuthority(void)

- ea: `0x18000d6a4`
- end: `0x18000d70f`
- name: `?ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d57c`

## callees

- `0x18000d6a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6e7`

## string_xrefs

- `0x18000d6dc`: `Software\Microsoft\Windows\CurrentVersion\UserState\UserStateTechnologies\ConfigurationControls`

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
0x18000d6a4  mov     r11, rsp
0x18000d6a7  push    rbx
0x18000d6a8  sub     rsp, 40h
0x18000d6ac  xor     ebx, ebx
0x18000d6ae  mov     [rsp+48h+arg_8], 4
0x18000d6b6  lea     rax, [r11+10h]
0x18000d6ba  mov     [rsp+48h+arg_0], ebx
0x18000d6be  mov     [r11-18h], rax
0x18000d6c2  lea     r8, aRoaminguserpro; "RoamingUserProfile"
0x18000d6c9  lea     rax, [r11+8]
0x18000d6cd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000d6d4  mov     [r11-20h], rax
0x18000d6d8  lea     r9d, [rbx+10h]; dwFlags
0x18000d6dc  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d6e3  mov     [r11-28h], rbx
0x18000d6e7  call    cs:__imp_RegGetValueW
0x18000d6ee  nop     dword ptr [rax+rax+00h]
0x18000d6f3  test    eax, eax
0x18000d6f5  jle     short loc_18000D701
0x18000d6f7  movzx   eax, ax
0x18000d6fa  or      eax, 80070000h
0x18000d6ff  test    eax, eax
0x18000d701  cmovns  ebx, [rsp+48h+arg_0]
0x18000d706  mov     eax, ebx
0x18000d708  add     rsp, 40h
0x18000d70c  pop     rbx
0x18000d70d  retn
```
