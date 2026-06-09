# T2OSSvcIsEmbeddingEnabledForFacename

- ea: `0x180022f10`
- end: `0x180022fc3`
- name: `T2OSSvcIsEmbeddingEnabledForFacename`
- size: `179`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020440`

## callees

- `0x180022f10`

## import_xrefs

- `KERNEL32!RegOpenKeyExA` at `0x180022f62`
- `KERNEL32!RegOpenKeyExA` at `0x180022f62`
- `KERNEL32!RegQueryValueExA` at `0x180022f96`
- `KERNEL32!RegQueryValueExA` at `0x180022f96`
- `KERNEL32!RegCloseKey` at `0x180022fad`
- `KERNEL32!RegCloseKey` at `0x180022fad`

## pseudocode

```c
__int64 __fastcall T2OSSvcIsEmbeddingEnabledForFacename(LPCSTR lpValueName, _DWORD *a2, __int64 a3)
{
  int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v8; // [rsp+54h] [rbp+1Ch]
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v8 = HIDWORD(a3);
  hKey = 0;
  Data = 0;
  cbData = 0;
  *a2 = 1;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\Shared Tools\\t2embed", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, lpValueName, 0, 0, (LPBYTE)&Data, &cbData) && !Data )
      *a2 = 0;
    RegCloseKey(hKey);
  }
  return 1;
}

```

## disassembly

```asm
0x180022f10  mov     rax, rsp
0x180022f13  mov     [rax+8], rbx
0x180022f17  mov     [rax+18h], r8
0x180022f1b  push    rdi
0x180022f1c  sub     rsp, 30h
0x180022f20  mov     qword ptr [rax+20h], 0
0x180022f28  mov     rbx, rdx
0x180022f2b  mov     dword ptr [rax+10h], 0
0x180022f32  mov     rdi, rcx
0x180022f35  mov     dword ptr [rax+18h], 0
0x180022f3c  lea     rax, [rax+20h]
0x180022f40  mov     dword ptr [rdx], 1
0x180022f46  mov     r9d, 20019h; samDesired
0x180022f4c  xor     r8d, r8d; ulOptions
0x180022f4f  mov     [rsp+38h+phkResult], rax; phkResult
0x180022f54  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Shared Tools\\t2em"...
0x180022f5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022f62  call    cs:__imp_RegOpenKeyExA
0x180022f68  test    eax, eax
0x180022f6a  jnz     short loc_180022FB3
0x180022f6c  mov     rcx, [rsp+38h+hKey]; hKey
0x180022f71  lea     rax, [rsp+38h+cbData]
0x180022f76  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180022f7b  xor     r9d, r9d; lpType
0x180022f7e  lea     rax, [rsp+38h+Data]
0x180022f83  mov     [rsp+38h+cbData], 4
0x180022f8b  xor     r8d, r8d; lpReserved
0x180022f8e  mov     [rsp+38h+phkResult], rax; lpData
0x180022f93  mov     rdx, rdi; lpValueName
0x180022f96  call    cs:__imp_RegQueryValueExA
0x180022f9c  test    eax, eax
0x180022f9e  jnz     short loc_180022FA8
0x180022fa0  cmp     [rsp+38h+Data], eax
0x180022fa4  jnz     short loc_180022FA8
0x180022fa6  mov     [rbx], eax
0x180022fa8  mov     rcx, [rsp+38h+hKey]; hKey
0x180022fad  call    cs:__imp_RegCloseKey
0x180022fb3  mov     rbx, [rsp+38h+arg_0]
0x180022fb8  mov     eax, 1
0x180022fbd  add     rsp, 30h
0x180022fc1  pop     rdi
0x180022fc2  retn
```
