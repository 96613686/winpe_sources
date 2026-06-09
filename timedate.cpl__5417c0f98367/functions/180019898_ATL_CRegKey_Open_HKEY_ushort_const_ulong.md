# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180019898`
- end: `0x1800198e9`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019b88`
- `0x180019fa0`

## callees

- `0x180018e94`
- `0x180019898`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800198c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800198c3`

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
0x180019898  push    rbx
0x18001989a  sub     rsp, 40h
0x18001989e  mov     rbx, rcx
0x1800198a1  mov     [rsp+48h+var_18], 0
0x1800198aa  mov     rax, r8
0x1800198ad  lea     rcx, [rsp+48h+var_18]
0x1800198b2  mov     r10, rdx
0x1800198b5  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800198ba  mov     rcx, r10; hKey
0x1800198bd  xor     r8d, r8d; ulOptions
0x1800198c0  mov     rdx, rax; lpSubKey
0x1800198c3  call    cs:__imp_RegOpenKeyExW
0x1800198c9  mov     edx, eax
0x1800198cb  test    eax, eax
0x1800198cd  jnz     short loc_1800198E1
0x1800198cf  mov     rcx, rbx; this
0x1800198d2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800198d7  mov     edx, eax
0x1800198d9  mov     rax, [rsp+48h+var_18]
0x1800198de  mov     [rbx], rax
0x1800198e1  mov     eax, edx
0x1800198e3  add     rsp, 40h
0x1800198e7  pop     rbx
0x1800198e8  retn
```
