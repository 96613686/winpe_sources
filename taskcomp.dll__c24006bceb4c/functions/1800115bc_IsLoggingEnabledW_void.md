# IsLoggingEnabledW(void)

- ea: `0x1800115bc`
- end: `0x180011622`
- name: `?IsLoggingEnabledW@@YAHXZ`
- size: `102`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010efc`

## callees

- `0x1800115bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011606`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011606`

## string_xrefs

- `0x1800115ea`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 IsLoggingEnabledW(void)
{
  int v1; // [rsp+50h] [rbp+8h] BYREF
  DWORD v2; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 4;
  return !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Configuration",
            L"AdapterLoggingEnabled",
            0x10u,
            0,
            &v1,
            &v2)
      && v1 != 0;
}

```

## disassembly

```asm
0x1800115bc  mov     r11, rsp
0x1800115bf  sub     rsp, 48h
0x1800115c3  lea     rax, [r11+10h]
0x1800115c7  mov     [rsp+48h+arg_0], 0
0x1800115cf  mov     [r11-18h], rax
0x1800115d3  lea     r8, Value; "AdapterLoggingEnabled"
0x1800115da  lea     rax, [r11+8]
0x1800115de  mov     [rsp+48h+arg_8], 4
0x1800115e6  mov     [r11-20h], rax
0x1800115ea  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800115f1  mov     r9d, 10h; dwFlags
0x1800115f7  mov     qword ptr [r11-28h], 0
0x1800115ff  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180011606  call    cs:__imp_RegGetValueW
0x18001160c  test    eax, eax
0x18001160e  jz      short loc_180011614
0x180011610  xor     eax, eax
0x180011612  jmp     short loc_18001161D
0x180011614  xor     eax, eax
0x180011616  cmp     [rsp+48h+arg_0], eax
0x18001161a  setnz   al
0x18001161d  add     rsp, 48h
0x180011621  retn
```
