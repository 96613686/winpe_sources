# IsLoggingEnabledW(void)

- ea: `0x180012098`
- end: `0x180012105`
- name: `?IsLoggingEnabledW@@YAHXZ`
- size: `109`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011958`

## callees

- `0x180012098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800120e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800120e2`

## string_xrefs

- `0x1800120c6`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Configuration`

## pseudocode

```c
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
0x180012098  mov     r11, rsp
0x18001209b  sub     rsp, 48h
0x18001209f  lea     rax, [r11+10h]
0x1800120a3  mov     [rsp+48h+arg_0], 0
0x1800120ab  mov     [r11-18h], rax
0x1800120af  lea     r8, Value; "AdapterLoggingEnabled"
0x1800120b6  lea     rax, [r11+8]
0x1800120ba  mov     [rsp+48h+arg_8], 4
0x1800120c2  mov     [r11-20h], rax
0x1800120c6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800120cd  mov     r9d, 10h; dwFlags
0x1800120d3  mov     qword ptr [r11-28h], 0
0x1800120db  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800120e2  call    cs:__imp_RegGetValueW
0x1800120e9  nop     dword ptr [rax+rax+00h]
0x1800120ee  test    eax, eax
0x1800120f0  jz      short loc_1800120F6
0x1800120f2  xor     eax, eax
0x1800120f4  jmp     short loc_1800120FF
0x1800120f6  xor     eax, eax
0x1800120f8  cmp     [rsp+48h+arg_0], eax
0x1800120fc  setnz   al
0x1800120ff  add     rsp, 48h
0x180012103  retn
```
