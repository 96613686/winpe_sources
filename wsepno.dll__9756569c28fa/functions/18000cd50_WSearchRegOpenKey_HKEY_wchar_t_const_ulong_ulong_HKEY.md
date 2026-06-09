# WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x18000cd50`
- end: `0x18000cdde`
- name: `?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `142`
- prototype: `LSTATUS __fastcall(const wchar_t *, wchar_t *, __int64, REGSAM, HKEY *phkResult)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800068e0`
- `0x18000d2f8`

## callees

- `0x180001770`
- `0x18000c9d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cdb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cdb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall WSearchRegOpenKey(const wchar_t *a1, wchar_t *a2, __int64 a3, REGSAM a4, HKEY *phkResult)
{
  bool v7; // al
  wchar_t *v8; // rdx
  wchar_t v10[264]; // [rsp+30h] [rbp-228h] BYREF

  v7 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, a2, v10);
  v8 = v10;
  if ( !v7 )
    v8 = a2;
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, a4, phkResult);
}

```

## disassembly

```asm
0x18000cd50  mov     [rsp+arg_0], rbx
0x18000cd55  mov     [rsp+arg_10], rsi
0x18000cd5a  push    rdi
0x18000cd5b  sub     rsp, 250h
0x18000cd62  mov     rax, cs:__security_cookie
0x18000cd69  xor     rax, rsp
0x18000cd6c  mov     [rsp+258h+var_18], rax
0x18000cd74  mov     rbx, [rsp+258h+arg_20]
0x18000cd7c  mov     esi, r9d
0x18000cd7f  mov     rdi, rdx
0x18000cd82  lea     r9, [rsp+258h+var_228]; wchar_t *
0x18000cd87  mov     r8, rdx; wchar_t *
0x18000cd8a  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000cd91  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18000cd96  test    al, al
0x18000cd98  mov     [rsp+258h+phkResult], rbx; phkResult
0x18000cd9d  lea     rdx, [rsp+258h+var_228]
0x18000cda2  mov     r9d, esi; samDesired
0x18000cda5  cmovz   rdx, rdi; lpSubKey
0x18000cda9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cdb0  xor     r8d, r8d; ulOptions
0x18000cdb3  call    cs:__imp_RegOpenKeyExW
0x18000cdb9  mov     rcx, [rsp+258h+var_18]
0x18000cdc1  xor     rcx, rsp; StackCookie
0x18000cdc4  call    __security_check_cookie
0x18000cdc9  lea     r11, [rsp+258h+var_8]
0x18000cdd1  mov     rbx, [r11+10h]
0x18000cdd5  mov     rsi, [r11+20h]
0x18000cdd9  mov     rsp, r11
0x18000cddc  pop     rdi
0x18000cddd  retn
```
