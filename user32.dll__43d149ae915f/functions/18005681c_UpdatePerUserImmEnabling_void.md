# UpdatePerUserImmEnabling(void)

- ea: `0x18005681c`
- end: `0x18005685f`
- name: `?UpdatePerUserImmEnabling@@YAXXZ`
- size: `67`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800564a0`

## callees

- `0x18005681c`

## import_xrefs

- `win32u!NtUserUpdatePerUserImmEnabling` at `0x180056820`
- `win32u!NtUserUpdatePerUserImmEnabling` at `0x180056820`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005683d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005683d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056854`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056854`

## string_xrefs

- `0x180056836`: `IMM32.DLL`
- `0x18005684b`: `IMM32.DLL`

## pseudocode

```c
void UpdatePerUserImmEnabling(void)
{
  if ( (unsigned int)NtUserUpdatePerUserImmEnabling() && (*(_BYTE *)gpsi & 4) != 0 && !GetModuleHandleW(L"IMM32.DLL") )
    LoadLibraryExW(L"IMM32.DLL", 0, 0);
}

```

## disassembly

```asm
0x18005681c  sub     rsp, 28h
0x180056820  call    cs:__imp_NtUserUpdatePerUserImmEnabling
0x180056826  test    eax, eax
0x180056828  jz      short loc_18005685A
0x18005682a  mov     rax, cs:gpsi
0x180056831  test    byte ptr [rax], 4
0x180056834  jz      short loc_18005685A
0x180056836  lea     rcx, aImm32Dll; "IMM32.DLL"
0x18005683d  call    cs:__imp_GetModuleHandleW
0x180056843  test    rax, rax
0x180056846  jnz     short loc_18005685A
0x180056848  xor     r8d, r8d; dwFlags
0x18005684b  lea     rcx, aImm32Dll; "IMM32.DLL"
0x180056852  xor     edx, edx; hFile
0x180056854  call    cs:__imp_LoadLibraryExW
0x18005685a  add     rsp, 28h
0x18005685e  retn
```
