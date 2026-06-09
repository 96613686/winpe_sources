# WldpChangeVulnerableDriverBlocklistState

- ea: `0x180020b70`
- end: `0x180020c06`
- name: `WldpChangeVulnerableDriverBlocklistState`
- size: `150`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180020b70`
- `0x180020c0c`
- `0x18002df30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180020bca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180020bca`

## string_xrefs

- `0x180020bb7`: `System\CurrentControlSet\Control\CI\Config`

## pseudocode

```c
__int64 __fastcall WldpChangeVulnerableDriverBlocklistState(int a1)
{
  LSTATUS v1; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+48h] [rbp+10h] BYREF
  BOOL v5; // [rsp+50h] [rbp+18h] BYREF

  Data = a1;
  v4 = 0;
  v5 = 0;
  WldpIsVulnerableDriverBlocklistEligibleToDisable(&v4);
  if ( v4 )
  {
    v1 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\CI\\Config",
           L"VulnerableDriverBlocklistEnable",
           4u,
           &Data,
           4u);
    v5 = v1 == 0;
  }
  else
  {
    v1 = 50;
  }
  CIStateProvider::VulnerableDriverBlocklistStateChanged<enum VULNERABLE_DRIVER_BLOCKLIST_STATE &,int &,int &>(
    &Data,
    &v4,
    &v5);
  if ( v1 > 0 )
    return (unsigned __int16)v1 | 0x80070000;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180020b70  mov     rax, rsp
0x180020b73  mov     [rax+8], ecx
0x180020b76  push    rbx
0x180020b77  sub     rsp, 30h
0x180020b7b  lea     rcx, [rax+10h]
0x180020b7f  mov     dword ptr [rax+10h], 0
0x180020b86  mov     dword ptr [rax+18h], 0
0x180020b8d  call    WldpIsVulnerableDriverBlocklistEligibleToDisable
0x180020b92  cmp     [rsp+38h+arg_8], 0
0x180020b97  jnz     short loc_180020BA0
0x180020b99  mov     ebx, 32h ; '2'
0x180020b9e  jmp     short loc_180020BDD
0x180020ba0  mov     r9d, 4; dwType
0x180020ba6  lea     rax, [rsp+38h+Data]
0x180020bab  mov     [rsp+38h+cbData], r9d; cbData
0x180020bb0  lea     r8, ValueName; "VulnerableDriverBlocklistEnable"
0x180020bb7  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\CI"...
0x180020bbe  mov     [rsp+38h+lpData], rax; lpData
0x180020bc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020bca  call    cs:__imp_RegSetKeyValueW
0x180020bd0  mov     ebx, eax
0x180020bd2  xor     eax, eax
0x180020bd4  test    ebx, ebx
0x180020bd6  setz    al
0x180020bd9  mov     [rsp+38h+arg_10], eax
0x180020bdd  lea     r8, [rsp+38h+arg_10]
0x180020be2  lea     rdx, [rsp+38h+arg_8]
0x180020be7  lea     rcx, [rsp+38h+Data]
0x180020bec  call    ??$VulnerableDriverBlocklistStateChanged@AEAW4VULNERABLE_DRIVER_BLOCKLIST_STATE@@AEAHAEAH@CIStateProvider@@SAXAEAW4VULNERABLE_DRIVER_BLOCKLIST_STATE@@AEAH1@Z; CIStateProvider::VulnerableDriverBlocklistStateChanged<VULNERABLE_DRIVER_BLOCKLIST_STATE &,int &,int &>(VULNERABLE_DRIVER_BLOCKLIST_STATE &,int &,int &)
0x180020bf1  test    ebx, ebx
0x180020bf3  jle     short loc_180020BFE
0x180020bf5  movzx   ebx, bx
0x180020bf8  or      ebx, 80070000h
0x180020bfe  mov     eax, ebx
0x180020c00  add     rsp, 30h
0x180020c04  pop     rbx
0x180020c05  retn
```
