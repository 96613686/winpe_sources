# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x14000ea8c`
- end: `0x14000eae4`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `88`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `21`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000dd50`
- `0x14000dea0`
- `0x140012f54`
- `0x1400137c4`
- `0x140014128`
- `0x1400150b4`
- `0x140015210`
- `0x140015300`
- `0x140015468`
- `0x140015600`
- `0x140015720`
- `0x140015c74`
- `0x140015fb8`
- `0x140016e8c`
- `0x140017e18`
- `0x140018ac8`
- `0x140019a74`
- `0x14001aa78`
- `0x14001c778`
- `0x14001c8d0`
- `0x14001cfa0`

## callees

- `0x14000d75c`
- `0x14000ea8c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000eab7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000eab7`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x14000ea8c  push    rbx
0x14000ea8e  sub     rsp, 40h
0x14000ea92  mov     rbx, rcx
0x14000ea95  mov     [rsp+48h+var_18], 0
0x14000ea9e  mov     rax, r8
0x14000eaa1  lea     rcx, [rsp+48h+var_18]
0x14000eaa6  mov     r10, rdx
0x14000eaa9  mov     [rsp+48h+phkResult], rcx; phkResult
0x14000eaae  mov     rcx, r10; hKey
0x14000eab1  xor     r8d, r8d; ulOptions
0x14000eab4  mov     rdx, rax; lpSubKey
0x14000eab7  call    cs:__imp_RegOpenKeyExW
0x14000eabe  nop     dword ptr [rax+rax+00h]
0x14000eac3  mov     edx, eax
0x14000eac5  test    eax, eax
0x14000eac7  jnz     short loc_14000EADB
0x14000eac9  mov     rcx, rbx; this
0x14000eacc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000ead1  mov     edx, eax
0x14000ead3  mov     rax, [rsp+48h+var_18]
0x14000ead8  mov     [rbx], rax
0x14000eadb  mov     eax, edx
0x14000eadd  add     rsp, 40h
0x14000eae1  pop     rbx
0x14000eae2  retn
```
