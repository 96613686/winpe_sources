# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001bfb4`
- end: `0x18001c00b`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b7b0`

## callees

- `0x18001bd50`
- `0x18001bfb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bfe5`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x18001bfb4  push    rbx
0x18001bfb6  sub     rsp, 40h
0x18001bfba  mov     rbx, rcx
0x18001bfbd  mov     [rsp+48h+var_18], 0
0x18001bfc6  mov     rax, r8
0x18001bfc9  lea     rcx, [rsp+48h+var_18]
0x18001bfce  mov     r10, rdx
0x18001bfd1  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001bfd6  mov     rcx, r10; hKey
0x18001bfd9  mov     r9d, 20019h; samDesired
0x18001bfdf  xor     r8d, r8d; ulOptions
0x18001bfe2  mov     rdx, rax; lpSubKey
0x18001bfe5  call    cs:__imp_RegOpenKeyExW
0x18001bfeb  mov     edx, eax
0x18001bfed  test    eax, eax
0x18001bfef  jnz     short loc_18001C003
0x18001bff1  mov     rcx, rbx; this
0x18001bff4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001bff9  mov     edx, eax
0x18001bffb  mov     rax, [rsp+48h+var_18]
0x18001c000  mov     [rbx], rax
0x18001c003  mov     eax, edx
0x18001c005  add     rsp, 40h
0x18001c009  pop     rbx
0x18001c00a  retn
```
