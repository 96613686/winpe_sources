# CUwfRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000d9f0`
- end: `0x18000da7a`
- name: `?Create@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `138`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, LPWSTR lpClass, DWORD, REGSAM, LPSECURITY_ATTRIBUTES, LPDWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b20`
- `0x1800092a8`
- `0x180009a50`
- `0x18000e780`

## callees

- `0x18000d5f0`
- `0x18000d9f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000da54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000da54`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::Create(
        PHKEY phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPWSTR lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        LPDWORD lpdwDisposition)
{
  unsigned int v8; // ebx
  LSTATUS Key; // eax

  v8 = 0;
  if ( *phkResult )
    CUwfRegKey::Close(phkResult);
  Key = RegCreateKeyExW(
          hKey,
          lpSubKey,
          0,
          lpClass,
          dwOptions,
          samDesired,
          lpSecurityAttributes,
          phkResult,
          lpdwDisposition);
  if ( Key )
  {
    if ( Key > 0 )
      return (unsigned __int16)Key | 0x80070000;
    else
      return (unsigned int)Key;
  }
  return v8;
}

```

## disassembly

```asm
0x18000d9f0  push    rbx
0x18000d9f2  push    rbp
0x18000d9f3  push    rsi
0x18000d9f4  push    rdi
0x18000d9f5  push    r14
0x18000d9f7  sub     rsp, 50h
0x18000d9fb  xor     ebx, ebx
0x18000d9fd  mov     rsi, r9
0x18000da00  mov     rbp, r8
0x18000da03  mov     r14, rdx
0x18000da06  mov     rdi, rcx
0x18000da09  cmp     [rcx], rbx
0x18000da0c  jz      short loc_18000DA13
0x18000da0e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000da13  mov     rax, [rsp+78h+arg_38]
0x18000da1b  mov     r9, rsi; lpClass
0x18000da1e  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18000da23  xor     r8d, r8d; Reserved
0x18000da26  mov     rax, [rsp+78h+arg_30]
0x18000da2e  mov     rdx, rbp; lpSubKey
0x18000da31  mov     [rsp+78h+phkResult], rdi; phkResult
0x18000da36  mov     rcx, r14; hKey
0x18000da39  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000da3e  mov     eax, [rsp+78h+arg_28]
0x18000da45  mov     [rsp+78h+samDesired], eax; samDesired
0x18000da49  mov     eax, [rsp+78h+arg_20]
0x18000da50  mov     [rsp+78h+dwOptions], eax; dwOptions
0x18000da54  call    cs:__imp_RegCreateKeyExW
0x18000da5a  test    eax, eax
0x18000da5c  jz      short loc_18000DA6D
0x18000da5e  jg      short loc_18000DA64
0x18000da60  mov     ebx, eax
0x18000da62  jmp     short loc_18000DA6D
0x18000da64  movzx   ebx, ax
0x18000da67  or      ebx, 80070000h
0x18000da6d  mov     eax, ebx
0x18000da6f  add     rsp, 50h
0x18000da73  pop     r14
0x18000da75  pop     rdi
0x18000da76  pop     rsi
0x18000da77  pop     rbp
0x18000da78  pop     rbx
0x18000da79  retn
```
