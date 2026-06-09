# WldpIsVulnerableDriverBlocklistDisabled

- ea: `0x18002dea0`
- end: `0x18002df21`
- name: `WldpIsVulnerableDriverBlocklistDisabled`
- size: `129`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002dea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002deee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002deee`

## string_xrefs

- `0x18002dee0`: `System\CurrentControlSet\Control\CI\Config`

## pseudocode

```c
__int64 __fastcall WldpIsVulnerableDriverBlocklistDisabled(_DWORD *a1)
{
  LSTATUS ValueW; // eax
  unsigned int v3; // ecx
  int v5; // [rsp+58h] [rbp+10h] BYREF
  DWORD v6; // [rsp+60h] [rbp+18h] BYREF

  v5 = 0;
  v6 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\CI\\Config",
             L"VulnerableDriverBlocklistEnable",
             0x10u,
             0,
             &v5,
             &v6);
  v3 = ValueW;
  if ( ValueW )
  {
    *a1 = 0;
    if ( ValueW > 0 )
      return (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    *a1 = v5 != 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18002dea0  mov     r11, rsp
0x18002dea3  push    rbx
0x18002dea4  sub     rsp, 40h
0x18002dea8  lea     rax, [r11+18h]
0x18002deac  mov     [rsp+48h+arg_8], 0
0x18002deb4  mov     [r11-18h], rax
0x18002deb8  lea     r8, ValueName; "VulnerableDriverBlocklistEnable"
0x18002debf  lea     rax, [r11+10h]
0x18002dec3  mov     [rsp+48h+arg_10], 4
0x18002decb  mov     rbx, rcx
0x18002dece  mov     [r11-20h], rax
0x18002ded2  mov     r9d, 10h; dwFlags
0x18002ded8  mov     qword ptr [r11-28h], 0
0x18002dee0  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\CI"...
0x18002dee7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002deee  call    cs:__imp_RegGetValueW
0x18002def4  mov     ecx, eax
0x18002def6  test    eax, eax
0x18002def8  jnz     short loc_18002DF06
0x18002defa  cmp     [rsp+48h+arg_8], 1
0x18002deff  setnz   al
0x18002df02  mov     [rbx], eax
0x18002df04  jmp     short loc_18002DF19
0x18002df06  mov     dword ptr [rbx], 0
0x18002df0c  test    eax, eax
0x18002df0e  jle     short loc_18002DF19
0x18002df10  movzx   ecx, ax
0x18002df13  or      ecx, 80070000h
0x18002df19  mov     eax, ecx
0x18002df1b  add     rsp, 40h
0x18002df1f  pop     rbx
0x18002df20  retn
```
