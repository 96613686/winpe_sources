# WSearchRegSetKeyValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong)

- ea: `0x18000cde4`
- end: `0x18000ce7a`
- name: `?WSearchRegSetKeyValue@@YAJPEAUHKEY__@@PEB_W1KPEBXK@Z`
- size: `150`
- prototype: `LSTATUS __fastcall(const wchar_t *, wchar_t *, const wchar_t *, __int64, LPCVOID)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006b50`

## callees

- `0x180001770`
- `0x18000c9d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000ce4f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000ce4f`

## pseudocode

```c
LSTATUS __fastcall WSearchRegSetKeyValue(const wchar_t *a1, wchar_t *a2, const wchar_t *a3, __int64 a4, LPCVOID a5)
{
  bool v7; // al
  wchar_t *v8; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-238h]
  wchar_t v11[264]; // [rsp+30h] [rbp-228h] BYREF

  v7 = MapRegistryKeyPath(a1, HKEY_LOCAL_MACHINE, a2, v11, lpData);
  v8 = v11;
  if ( !v7 )
    v8 = a2;
  return RegSetKeyValueW(HKEY_LOCAL_MACHINE, v8, a3, 4u, a5, 4u);
}

```

## disassembly

```asm
0x18000cde4  mov     [rsp+arg_0], rbx
0x18000cde9  mov     [rsp+arg_18], rsi
0x18000cdee  push    rdi
0x18000cdef  sub     rsp, 250h
0x18000cdf6  mov     rax, cs:__security_cookie
0x18000cdfd  xor     rax, rsp
0x18000ce00  mov     [rsp+258h+var_18], rax
0x18000ce08  mov     rbx, [rsp+258h+arg_20]
0x18000ce10  lea     r9, [rsp+258h+var_228]; wchar_t *
0x18000ce15  mov     rsi, r8
0x18000ce18  mov     rdi, rdx
0x18000ce1b  mov     r8, rdx; wchar_t *
0x18000ce1e  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000ce25  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x18000ce2a  test    al, al
0x18000ce2c  lea     rdx, [rsp+258h+var_228]
0x18000ce31  mov     r9d, 4; dwType
0x18000ce37  mov     r8, rsi; lpValueName
0x18000ce3a  mov     [rsp+258h+cbData], r9d; cbData
0x18000ce3f  cmovz   rdx, rdi; lpSubKey
0x18000ce43  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ce4a  mov     [rsp+258h+lpData], rbx; lpData
0x18000ce4f  call    cs:__imp_RegSetKeyValueW
0x18000ce55  mov     rcx, [rsp+258h+var_18]
0x18000ce5d  xor     rcx, rsp; StackCookie
0x18000ce60  call    __security_check_cookie
0x18000ce65  lea     r11, [rsp+258h+var_8]
0x18000ce6d  mov     rbx, [r11+10h]
0x18000ce71  mov     rsi, [r11+28h]
0x18000ce75  mov     rsp, r11
0x18000ce78  pop     rdi
0x18000ce79  retn
```
