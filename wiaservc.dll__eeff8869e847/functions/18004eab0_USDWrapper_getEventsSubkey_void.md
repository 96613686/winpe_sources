# USDWrapper::getEventsSubkey(void)

- ea: `0x18004eab0`
- end: `0x18004eb46`
- name: `?getEventsSubkey@USDWrapper@@MEAAPEAUHKEY__@@XZ`
- size: `150`
- prototype: `HKEY __fastcall(USDWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18004eab0`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18004eb35`
- `ADVAPI32!RegCloseKey` at `0x18004eb35`
- `ADVAPI32!RegOpenKeyExW` at `0x18004eaf8`
- `ADVAPI32!RegOpenKeyExW` at `0x18004eb2c`
- `ADVAPI32!RegOpenKeyExW` at `0x18004eaf8`
- `ADVAPI32!RegOpenKeyExW` at `0x18004eb2c`

## pseudocode

```c
HKEY __fastcall USDWrapper::getEventsSubkey(USDWrapper *this)
{
  __int64 v1; // rax
  HKEY v2; // rbx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  phkResult = 0;
  v2 = (HKEY)(*(__int64 (__fastcall **)(USDWrapper *))(v1 + 480))(this);
  if ( (unsigned __int64)v2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegOpenKeyExW(v2, L"Events", 0, 0xF003Fu, &phkResult);
    if ( (((unsigned __int64)phkResult + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      RegOpenKeyExW(v2, L"Events", 0, 0x20019u, &phkResult);
    RegCloseKey(v2);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18004eab0  push    rbx
0x18004eab2  sub     rsp, 30h
0x18004eab6  mov     rax, [rcx]
0x18004eab9  mov     [rsp+38h+arg_0], 0
0x18004eac2  mov     rax, [rax+1E0h]
0x18004eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eace  mov     rbx, rax
0x18004ead1  lea     rcx, [rax-1]
0x18004ead5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004ead9  ja      short loc_18004EB3B
0x18004eadb  lea     rax, [rsp+38h+arg_0]
0x18004eae0  mov     r9d, 0F003Fh; samDesired
0x18004eae6  xor     r8d, r8d; ulOptions
0x18004eae9  mov     [rsp+38h+phkResult], rax; phkResult
0x18004eaee  lea     rdx, aEvents; "Events"
0x18004eaf5  mov     rcx, rbx; hKey
0x18004eaf8  call    cs:__imp_RegOpenKeyExW
0x18004eafe  mov     rcx, [rsp+38h+arg_0]
0x18004eb03  inc     rcx
0x18004eb06  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18004eb0d  jnz     short loc_18004EB32
0x18004eb0f  lea     rax, [rsp+38h+arg_0]
0x18004eb14  mov     r9d, 20019h; samDesired
0x18004eb1a  xor     r8d, r8d; ulOptions
0x18004eb1d  mov     [rsp+38h+phkResult], rax; phkResult
0x18004eb22  lea     rdx, aEvents; "Events"
0x18004eb29  mov     rcx, rbx; hKey
0x18004eb2c  call    cs:__imp_RegOpenKeyExW
0x18004eb32  mov     rcx, rbx; hKey
0x18004eb35  call    cs:__imp_RegCloseKey
0x18004eb3b  mov     rax, [rsp+38h+arg_0]
0x18004eb40  add     rsp, 30h
0x18004eb44  pop     rbx
0x18004eb45  retn
```
