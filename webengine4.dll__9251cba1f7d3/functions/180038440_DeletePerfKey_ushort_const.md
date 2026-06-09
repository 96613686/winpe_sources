# DeletePerfKey(ushort const *)

- ea: `0x180038440`
- end: `0x1800385d5`
- name: `?DeletePerfKey@@YAJPEBG@Z`
- size: `405`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800397d4`
- `0x180039d9c`
- `0x18003ea8c`

## callees

- `0x18000dd78`
- `0x180038440`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003845f`
- `KERNEL32!lstrlenW` at `0x18003846a`
- `KERNEL32!lstrlenW` at `0x1800384ac`
- `KERNEL32!lstrlenW` at `0x1800384b7`
- `KERNEL32!lstrlenW` at `0x18003845f`
- `KERNEL32!lstrlenW` at `0x18003846a`
- `KERNEL32!lstrlenW` at `0x1800384ac`
- `KERNEL32!lstrlenW` at `0x1800384b7`
- `ADVAPI32!RegCloseKey` at `0x180038561`
- `ADVAPI32!RegCloseKey` at `0x1800385b5`
- `ADVAPI32!RegCloseKey` at `0x180038561`
- `ADVAPI32!RegCloseKey` at `0x1800385b5`
- `ADVAPI32!RegOpenKeyExW` at `0x180038509`
- `ADVAPI32!RegOpenKeyExW` at `0x180038585`
- `ADVAPI32!RegOpenKeyExW` at `0x180038509`
- `ADVAPI32!RegOpenKeyExW` at `0x180038585`
- `ADVAPI32!RegDeleteKeyW` at `0x180038532`
- `ADVAPI32!RegDeleteKeyW` at `0x180038544`
- `ADVAPI32!RegDeleteKeyW` at `0x180038556`
- `ADVAPI32!RegDeleteKeyW` at `0x1800385aa`
- `ADVAPI32!RegDeleteKeyW` at `0x180038532`
- `ADVAPI32!RegDeleteKeyW` at `0x180038544`
- `ADVAPI32!RegDeleteKeyW` at `0x180038556`
- `ADVAPI32!RegDeleteKeyW` at `0x1800385aa`

## string_xrefs

- `0x180038458`: `SYSTEM\CurrentControlSet\Services\`
- `0x1800384a5`: `SYSTEM\CurrentControlSet\Services\`
- `0x1800384bd`: `SYSTEM\CurrentControlSet\Services\`
- `0x180038577`: `SYSTEM\CurrentControlSet\Services\`
- `0x18003852b`: `Linkage`

## pseudocode

```c
__int64 __fastcall DeletePerfKey(LPCWSTR lpSubKey)
{
  int v2; // ebx
  unsigned __int64 v3; // rax
  wchar_t *v4; // rdi
  int v5; // ebx
  int v6; // ebx
  int v7; // eax
  LSTATUS v8; // eax
  unsigned int v9; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = lstrlenW(L"SYSTEM\\CurrentControlSet\\Services\\");
  v3 = saturated_mul(v2 + lstrlenW(lpSubKey) + 1, 2u);
  v4 = (wchar_t *)MemAlloc(v3);
  if ( v4 )
  {
    v6 = lstrlenW(L"SYSTEM\\CurrentControlSet\\Services\\");
    v7 = lstrlenW(lpSubKey);
    v5 = StringCchPrintfW(v4, v6 + v7 + 1, L"%s%s", L"SYSTEM\\CurrentControlSet\\Services\\", lpSubKey);
    if ( !v5 )
    {
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20006u, &hKey);
      if ( v8 )
      {
        v5 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 <= 0 )
          v5 = v8;
      }
      else
      {
        RegDeleteKeyW(hKey, L"Linkage");
        RegDeleteKeyW(hKey, L"Performance");
        RegDeleteKeyW(hKey, L"Names");
        RegCloseKey(hKey);
        v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\", 0, 0x20006u, &hKey);
        if ( v5 )
        {
          v9 = (unsigned __int16)v5 | 0x80070000;
          if ( v5 <= 0 )
            v9 = v5;
          v5 = v9;
        }
        else
        {
          RegDeleteKeyW(hKey, lpSubKey);
          RegCloseKey(hKey);
        }
      }
    }
    MemFree(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180038440  mov     [rsp+arg_0], rbx
0x180038445  mov     [rsp+arg_10], rsi
0x18003844a  push    rdi
0x18003844b  sub     rsp, 30h
0x18003844f  and     [rsp+38h+hKey], 0
0x180038455  mov     rsi, rcx
0x180038458  lea     rcx, aSystemCurrentc_3
0x18003845f  call    cs:__imp_lstrlenW
0x180038465  mov     rcx, rsi; lpString
0x180038468  mov     ebx, eax
0x18003846a  call    cs:__imp_lstrlenW
0x180038470  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038477  lea     edx, [rax+1]
0x18003847a  mov     eax, 2
0x18003847f  add     edx, ebx
0x180038481  movsxd  r8, edx
0x180038484  mul     r8
0x180038487  cmovo   rax, rcx
0x18003848b  mov     rcx, rax; unsigned __int64
0x18003848e  call    ?MemAlloc@@YAPEAX_K@Z
0x180038493  mov     rdi, rax
0x180038496  test    rax, rax
0x180038499  jnz     short loc_1800384A5
0x18003849b  mov     ebx, 8007000Eh
0x1800384a0  jmp     loc_1800385C3
0x1800384a5  lea     rcx, aSystemCurrentc_3
0x1800384ac  call    cs:__imp_lstrlenW
0x1800384b2  mov     rcx, rsi; lpString
0x1800384b5  mov     ebx, eax
0x1800384b7  call    cs:__imp_lstrlenW
0x1800384bd  lea     r9, aSystemCurrentc_3
0x1800384c4  mov     [rsp+38h+phkResult], rsi
0x1800384c9  lea     r8, aSS
0x1800384d0  lea     ecx, [rax+1]
0x1800384d3  add     ecx, ebx
0x1800384d5  movsxd  rdx, ecx; unsigned __int64
0x1800384d8  mov     rcx, rdi; Buffer
0x1800384db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x1800384e0  mov     ebx, eax
0x1800384e2  test    eax, eax
0x1800384e4  jnz     loc_1800385BB
0x1800384ea  lea     rax, [rsp+38h+hKey]
0x1800384ef  mov     ebx, 20006h
0x1800384f4  mov     r9d, ebx; samDesired
0x1800384f7  mov     [rsp+38h+phkResult], rax; phkResult
0x1800384fc  xor     r8d, r8d; ulOptions
0x1800384ff  mov     rdx, rdi; lpSubKey
0x180038502  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038509  call    cs:__imp_RegOpenKeyExW
0x18003850f  test    eax, eax
0x180038511  jz      short loc_180038526
0x180038513  movzx   ebx, ax
0x180038516  or      ebx, 80070000h
0x18003851c  test    eax, eax
0x18003851e  cmovle  ebx, eax
0x180038521  jmp     loc_1800385BB
0x180038526  mov     rcx, [rsp+38h+hKey]; hKey
0x18003852b  lea     rdx, aLinkage
0x180038532  call    cs:__imp_RegDeleteKeyW
0x180038538  mov     rcx, [rsp+38h+hKey]; hKey
0x18003853d  lea     rdx, aPerformance
0x180038544  call    cs:__imp_RegDeleteKeyW
0x18003854a  mov     rcx, [rsp+38h+hKey]; hKey
0x18003854f  lea     rdx, aNames
0x180038556  call    cs:__imp_RegDeleteKeyW
0x18003855c  mov     rcx, [rsp+38h+hKey]; hKey
0x180038561  call    cs:__imp_RegCloseKey
0x180038567  lea     rax, [rsp+38h+hKey]
0x18003856c  mov     r9d, ebx; samDesired
0x18003856f  xor     r8d, r8d; ulOptions
0x180038572  mov     [rsp+38h+phkResult], rax; phkResult
0x180038577  lea     rdx, aSystemCurrentc_3
0x18003857e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038585  call    cs:__imp_RegOpenKeyExW
0x18003858b  mov     ebx, eax
0x18003858d  test    eax, eax
0x18003858f  jz      short loc_1800385A2
0x180038591  movzx   eax, bx
0x180038594  or      eax, 80070000h
0x180038599  test    ebx, ebx
0x18003859b  cmovle  eax, ebx
0x18003859e  mov     ebx, eax
0x1800385a0  jmp     short loc_1800385BB
0x1800385a2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800385a7  mov     rdx, rsi; lpSubKey
0x1800385aa  call    cs:__imp_RegDeleteKeyW
0x1800385b0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800385b5  call    cs:__imp_RegCloseKey
0x1800385bb  mov     rcx, rdi; lpMem
0x1800385be  call    ?MemFree@@YAXPEAX@Z
0x1800385c3  mov     rsi, [rsp+38h+arg_10]
0x1800385c8  mov     eax, ebx
0x1800385ca  mov     rbx, [rsp+38h+arg_0]
0x1800385cf  add     rsp, 30h
0x1800385d3  pop     rdi
0x1800385d4  retn
```
