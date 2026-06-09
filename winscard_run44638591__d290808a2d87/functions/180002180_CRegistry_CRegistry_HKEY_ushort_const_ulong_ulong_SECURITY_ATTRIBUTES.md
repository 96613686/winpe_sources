# CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180002180`
- end: `0x18000221a`
- name: `??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `154`
- prototype: `CRegistry *__fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD dwOptions, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001a20`
- `0x180002030`
- `0x180019990`
- `0x18001aae0`
- `0x18001b044`
- `0x18001b448`
- `0x18002a528`
- `0x18002aaf8`
- `0x18002ad8c`
- `0x18002b0ec`
- `0x18002b2d8`

## callees

- `0x180002180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002211`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002211`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800021cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800021cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRegistry *__fastcall CRegistry::CRegistry(
        _DWORD *phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        DWORD dwOptions)
{
  LSTATUS Key; // eax

  *((_QWORD *)phkResult + 2) = &CBuffer::`vftable';
  *((_QWORD *)phkResult + 3) = 0;
  *((_QWORD *)phkResult + 4) = 0;
  *(_QWORD *)phkResult = 0;
  phkResult[10] = 1010;
  phkResult[8] = 0;
  if ( dwOptions == -32 )
  {
    Key = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, (PHKEY)phkResult);
    phkResult[2] = 2;
  }
  else
  {
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, (LPWSTR)&Class, dwOptions, samDesired, 0, (PHKEY)phkResult, phkResult + 2);
  }
  phkResult[10] = Key;
  return (CRegistry *)phkResult;
}

```

## disassembly

```asm
0x180002180  mov     [rsp+arg_0], rcx
0x180002185  push    rbx
0x180002186  sub     rsp, 50h
0x18000218a  mov     r10, r8
0x18000218d  mov     r11, rdx
0x180002190  mov     rbx, rcx
0x180002193  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000219a  mov     [rcx+10h], rax
0x18000219e  xor     edx, edx
0x1800021a0  mov     [rcx+18h], rdx
0x1800021a4  mov     [rcx+20h], rdx
0x1800021a8  mov     [rcx], rdx
0x1800021ab  mov     dword ptr [rcx+28h], 3F2h
0x1800021b2  mov     [rcx+20h], edx
0x1800021b5  mov     ecx, [rsp+58h+dwOptions]
0x1800021bc  xor     r8d, r8d; Reserved
0x1800021bf  cmp     ecx, 0FFFFFFE0h
0x1800021c2  jnz     short loc_1800021E8
0x1800021c4  mov     [rsp+58h+phkResult], rbx; phkResult
0x1800021c9  mov     rdx, r10; lpSubKey
0x1800021cc  mov     rcx, r11; hKey
0x1800021cf  call    cs:__imp_RegOpenKeyExW
0x1800021d5  mov     dword ptr [rbx+8], 2
0x1800021dc  mov     [rbx+28h], eax
0x1800021df  mov     rax, rbx
0x1800021e2  add     rsp, 50h
0x1800021e6  pop     rbx
0x1800021e7  retn
0x1800021e8  lea     rax, [rbx+8]
0x1800021ec  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800021f1  mov     [rsp+58h+var_20], rbx; phkResult
0x1800021f6  mov     [rsp+58h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1800021fb  mov     [rsp+58h+samDesired], r9d; samDesired
0x180002200  mov     dword ptr [rsp+58h+phkResult], ecx; dwOptions
0x180002204  lea     r9, Class; lpClass
0x18000220b  mov     rdx, r10; lpSubKey
0x18000220e  mov     rcx, r11; hKey
0x180002211  call    cs:__imp_RegCreateKeyExW
0x180002217  jmp     short loc_1800021DC
```
