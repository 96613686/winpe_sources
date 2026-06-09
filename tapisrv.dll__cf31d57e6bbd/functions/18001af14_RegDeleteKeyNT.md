# RegDeleteKeyNT

- ea: `0x18001af14`
- end: `0x18001b046`
- name: `RegDeleteKeyNT`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001af14`
- `0x18001dd40`

## callees

- `0x180001600`
- `0x18001af14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b012`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001b005`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001b005`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001afd3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001afd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001af82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001af82`
- `KERNEL32!lstrlenW` at `0x18001af5b`
- `KERNEL32!lstrlenW` at `0x18001af5b`

## pseudocode

```c
__int64 __fastcall RegDeleteKeyNT(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD cchName; // [rsp+40h] [rbp-228h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-220h] BYREF
  WCHAR String[256]; // [rsp+50h] [rbp-218h] BYREF

  cchName = 0;
  hKey = 0;
  if ( a2 && lstrlenW(a2) )
  {
    v4 = RegOpenKeyExW(a1, a2, 0, 0x10008u, &hKey);
    if ( !v4 )
    {
      while ( !v4 )
      {
        cchName = 256;
        v5 = RegEnumKeyExW(hKey, 0, String, &cchName, 0, 0, 0, 0);
        v4 = v5;
        if ( v5 == 259 )
        {
          v4 = RegDeleteKeyExW(a1, a2, 0, 0);
          break;
        }
        if ( !v5 )
          v4 = RegDeleteKeyNT(hKey, String);
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    return 1010;
  }
  return v4;
}

```

## disassembly

```asm
0x18001af14  mov     [rsp+arg_10], rbx
0x18001af19  mov     [rsp+arg_18], rsi
0x18001af1e  push    rdi
0x18001af1f  sub     rsp, 260h
0x18001af26  mov     rax, cs:__security_cookie
0x18001af2d  xor     rax, rsp
0x18001af30  mov     [rsp+268h+var_18], rax
0x18001af38  mov     [rsp+268h+cchName], 0
0x18001af40  mov     rdi, rdx
0x18001af43  mov     [rsp+268h+hKey], 0
0x18001af4c  mov     rsi, rcx
0x18001af4f  test    rdx, rdx
0x18001af52  jz      loc_18001B01A
0x18001af58  mov     rcx, rdx; lpString
0x18001af5b  call    cs:__imp_lstrlenW
0x18001af61  test    eax, eax
0x18001af63  jz      loc_18001B01A
0x18001af69  lea     rax, [rsp+268h+hKey]
0x18001af6e  mov     r9d, 10008h; samDesired
0x18001af74  xor     r8d, r8d; ulOptions
0x18001af77  mov     [rsp+268h+phkResult], rax; phkResult
0x18001af7c  mov     rdx, rdi; lpSubKey
0x18001af7f  mov     rcx, rsi; hKey
0x18001af82  call    cs:__imp_RegOpenKeyExW
0x18001af88  mov     ebx, eax
0x18001af8a  test    eax, eax
0x18001af8c  jnz     loc_18001B01F
0x18001af92  test    ebx, ebx
0x18001af94  jnz     short loc_18001B00D
0x18001af96  mov     rcx, [rsp+268h+hKey]; hKey
0x18001af9b  lea     r9, [rsp+268h+cchName]; lpcchName
0x18001afa0  mov     [rsp+268h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001afa9  lea     r8, [rsp+268h+String]; lpName
0x18001afae  mov     [rsp+268h+lpcchClass], 0; lpcchClass
0x18001afb7  xor     edx, edx; dwIndex
0x18001afb9  mov     [rsp+268h+lpClass], 0; lpClass
0x18001afc2  mov     [rsp+268h+phkResult], 0; lpReserved
0x18001afcb  mov     [rsp+268h+cchName], 100h
0x18001afd3  call    cs:__imp_RegEnumKeyExW
0x18001afd9  mov     ebx, eax
0x18001afdb  cmp     eax, 103h
0x18001afe0  jz      short loc_18001AFF9
0x18001afe2  test    eax, eax
0x18001afe4  jnz     short loc_18001AF92
0x18001afe6  mov     rcx, [rsp+268h+hKey]
0x18001afeb  lea     rdx, [rsp+268h+String]
0x18001aff0  call    RegDeleteKeyNT
0x18001aff5  mov     ebx, eax
0x18001aff7  jmp     short loc_18001AF92
0x18001aff9  xor     r9d, r9d; Reserved
0x18001affc  xor     r8d, r8d; samDesired
0x18001afff  mov     rdx, rdi; lpSubKey
0x18001b002  mov     rcx, rsi; hKey
0x18001b005  call    cs:__imp_RegDeleteKeyExW
0x18001b00b  mov     ebx, eax
0x18001b00d  mov     rcx, [rsp+268h+hKey]; hKey
0x18001b012  call    cs:__imp_RegCloseKey
0x18001b018  jmp     short loc_18001B01F
0x18001b01a  mov     ebx, 3F2h
0x18001b01f  mov     eax, ebx
0x18001b021  mov     rcx, [rsp+268h+var_18]
0x18001b029  xor     rcx, rsp; StackCookie
0x18001b02c  call    __security_check_cookie
0x18001b031  lea     r11, [rsp+268h+var_8]
0x18001b039  mov     rbx, [r11+20h]
0x18001b03d  mov     rsi, [r11+28h]
0x18001b041  mov     rsp, r11
0x18001b044  pop     rdi
0x18001b045  retn
```
