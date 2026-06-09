# CUwfRegKey::CopyValues(HKEY__ *)

- ea: `0x18000d884`
- end: `0x18000d9dc`
- name: `?CopyValues@CUwfRegKey@@AEAAJPEAUHKEY__@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(HKEY *this, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d690`

## callees

- `0x18000d884`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d916`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d916`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d996`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d996`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000d8f7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000d8f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d943`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d943`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d96a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d96a`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::CopyValues(HKEY *this, HKEY a2)
{
  unsigned int v2; // ebx
  DWORD v4; // esi
  HKEY v6; // rcx
  LSTATUS v7; // eax
  BYTE *v8; // rdi
  LSTATUS v9; // eax
  bool v10; // cc
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v4 = 0;
  Type = 0;
  while ( 1 )
  {
    v6 = *this;
    cbData = 0;
    cchValueName = 256;
    v7 = RegEnumValueW(v6, v4, ValueName, &cchValueName, 0, &Type, 0, &cbData);
    if ( v7 == 259 )
      break;
    if ( v7 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
    v8 = (BYTE *)LocalAlloc(0, cbData);
    if ( !v8 )
      return (unsigned int)-2147024882;
    v9 = RegQueryValueExW(*this, ValueName, 0, &Type, v8, &cbData);
    v10 = v9 <= 0;
    if ( v9 || (v9 = RegSetValueExW(a2, ValueName, 0, Type, v8, cbData), v10 = v9 <= 0, v9) )
    {
      if ( v10 )
        v2 = v9;
      else
        v2 = (unsigned __int16)v9 | 0x80070000;
      LocalFree(v8);
      return v2;
    }
    LocalFree(v8);
    ++v4;
  }
  return v2;
}

```

## disassembly

```asm
0x18000d884  mov     [rsp-8+arg_10], rbx
0x18000d889  push    rbp
0x18000d88a  push    rsi
0x18000d88b  push    rdi
0x18000d88c  push    r14
0x18000d88e  push    r15
0x18000d890  lea     rbp, [rsp-160h]
0x18000d898  sub     rsp, 260h
0x18000d89f  mov     rax, cs:__security_cookie
0x18000d8a6  xor     rax, rsp
0x18000d8a9  mov     [rbp+180h+var_30], rax
0x18000d8b0  xor     ebx, ebx
0x18000d8b2  mov     r15, rdx
0x18000d8b5  xor     esi, esi
0x18000d8b7  mov     [rsp+280h+Type], ebx
0x18000d8bb  mov     r14, rcx
0x18000d8be  mov     rcx, [r14]; hKey
0x18000d8c1  lea     rax, [rsp+280h+cbData]
0x18000d8c6  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000d8cb  lea     r9, [rsp+280h+cchValueName]; lpcchValueName
0x18000d8d0  lea     rax, [rsp+280h+Type]
0x18000d8d5  mov     [rsp+280h+lpData], rbx; lpData
0x18000d8da  mov     [rsp+280h+lpType], rax; lpType
0x18000d8df  lea     r8, [rsp+280h+ValueName]; lpValueName
0x18000d8e4  mov     edx, esi; dwIndex
0x18000d8e6  mov     [rsp+280h+lpReserved], rbx; lpReserved
0x18000d8eb  mov     [rsp+280h+cbData], ebx
0x18000d8ef  mov     [rsp+280h+cchValueName], 100h
0x18000d8f7  call    cs:__imp_RegEnumValueW
0x18000d8fd  cmp     eax, 103h
0x18000d902  jz      loc_18000D9B4
0x18000d908  test    eax, eax
0x18000d90a  jnz     loc_18000D9A5
0x18000d910  mov     edx, [rsp+280h+cbData]; uBytes
0x18000d914  xor     ecx, ecx; uFlags
0x18000d916  call    cs:__imp_LocalAlloc
0x18000d91c  mov     rdi, rax
0x18000d91f  test    rax, rax
0x18000d922  jz      short loc_18000D99E
0x18000d924  mov     rcx, [r14]; hKey
0x18000d927  lea     rax, [rsp+280h+cbData]
0x18000d92c  mov     [rsp+280h+lpType], rax; lpcbData
0x18000d931  lea     r9, [rsp+280h+Type]; lpType
0x18000d936  xor     r8d, r8d; lpReserved
0x18000d939  mov     [rsp+280h+lpReserved], rdi; lpData
0x18000d93e  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18000d943  call    cs:__imp_RegQueryValueExW
0x18000d949  test    eax, eax
0x18000d94b  jnz     short loc_18000D984
0x18000d94d  mov     eax, [rsp+280h+cbData]
0x18000d951  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18000d956  mov     r9d, [rsp+280h+Type]; dwType
0x18000d95b  xor     r8d, r8d; Reserved
0x18000d95e  mov     dword ptr [rsp+280h+lpType], eax; cbData
0x18000d962  mov     rcx, r15; hKey
0x18000d965  mov     [rsp+280h+lpReserved], rdi; lpData
0x18000d96a  call    cs:__imp_RegSetValueExW
0x18000d970  test    eax, eax
0x18000d972  jnz     short loc_18000D984
0x18000d974  mov     rcx, rdi; hMem
0x18000d977  call    cs:__imp_LocalFree
0x18000d97d  inc     esi
0x18000d97f  jmp     loc_18000D8BE
0x18000d984  jg      short loc_18000D98A
0x18000d986  mov     ebx, eax
0x18000d988  jmp     short loc_18000D993
0x18000d98a  movzx   ebx, ax
0x18000d98d  or      ebx, 80070000h
0x18000d993  mov     rcx, rdi; hMem
0x18000d996  call    cs:__imp_LocalFree
0x18000d99c  jmp     short loc_18000D9B4
0x18000d99e  mov     ebx, 8007000Eh
0x18000d9a3  jmp     short loc_18000D9B4
0x18000d9a5  jg      short loc_18000D9AB
0x18000d9a7  mov     ebx, eax
0x18000d9a9  jmp     short loc_18000D9B4
0x18000d9ab  movzx   ebx, ax
0x18000d9ae  or      ebx, 80070000h
0x18000d9b4  mov     eax, ebx
0x18000d9b6  mov     rcx, [rbp+180h+var_30]
0x18000d9bd  xor     rcx, rsp; StackCookie
0x18000d9c0  call    __security_check_cookie
0x18000d9c5  mov     rbx, [rsp+280h+arg_10]
0x18000d9cd  add     rsp, 260h
0x18000d9d4  pop     r15
0x18000d9d6  pop     r14
0x18000d9d8  pop     rdi
0x18000d9d9  pop     rsi
0x18000d9da  pop     rbp
0x18000d9db  retn
```
