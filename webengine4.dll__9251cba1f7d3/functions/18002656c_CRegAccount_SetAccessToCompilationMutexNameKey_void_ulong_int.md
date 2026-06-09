# CRegAccount::SetAccessToCompilationMutexNameKey(void *,ulong,int)

- ea: `0x18002656c`
- end: `0x180026634`
- name: `?SetAccessToCompilationMutexNameKey@CRegAccount@@SAJPEAXKH@Z`
- size: `200`
- prototype: `__int64 __fastcall(void *, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039628`
- `0x1800396b4`

## callees

- `0x18000d56c`
- `0x18002656c`
- `0x180026634`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180026607`
- `ADVAPI32!RegCloseKey` at `0x180026617`
- `ADVAPI32!RegCloseKey` at `0x180026607`
- `ADVAPI32!RegCloseKey` at `0x180026617`
- `ADVAPI32!RegOpenKeyExW` at `0x1800265ce`
- `ADVAPI32!RegOpenKeyExW` at `0x1800265ce`

## string_xrefs

- `0x1800265c7`: `CompilationMutexName`

## pseudocode

```c
__int64 __fastcall CRegAccount::SetAccessToCompilationMutexNameKey(void *a1, unsigned int a2, int a3)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  v6 = CRegInfo::OpenCurrentVersionKey(&hKey, 0x20006u, 1, 1);
  if ( !v6 )
  {
    v7 = RegOpenKeyExW(hKey, L"CompilationMutexName", 0, 0x60019u, &phkResult);
    if ( v7 )
    {
      v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 <= 0 )
        v6 = v7;
    }
    else
    {
      v6 = CRegAccount::SetAccessToRegKey(a1, phkResult, a2, a3);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x18002656c  mov     rax, rsp
0x18002656f  mov     [rax+8], rbx
0x180026573  mov     [rax+10h], rbp
0x180026577  mov     [rax+18h], rsi
0x18002657b  push    rdi
0x18002657c  sub     rsp, 40h
0x180026580  and     qword ptr [rax+20h], 0
0x180026585  mov     edi, r8d
0x180026588  and     qword ptr [rax-18h], 0
0x18002658d  mov     r8d, 1; int
0x180026593  mov     esi, edx
0x180026595  mov     rbp, rcx
0x180026598  mov     r9d, r8d; int
0x18002659b  lea     rcx, [rax+20h]; dwOptions
0x18002659f  mov     edx, 20006h; samDesired
0x1800265a4  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x1800265a9  mov     ebx, eax
0x1800265ab  test    eax, eax
0x1800265ad  jnz     short loc_1800265FD
0x1800265af  mov     rcx, [rsp+48h+hKey]; hKey
0x1800265b4  lea     rax, [rsp+48h+var_18]
0x1800265b9  mov     r9d, 60019h; samDesired
0x1800265bf  mov     [rsp+48h+phkResult], rax; phkResult
0x1800265c4  xor     r8d, r8d; ulOptions
0x1800265c7  lea     rdx, aCompilationmut; "CompilationMutexName"
0x1800265ce  call    cs:__imp_RegOpenKeyExW
0x1800265d4  test    eax, eax
0x1800265d6  jz      short loc_1800265E8
0x1800265d8  movzx   ebx, ax
0x1800265db  or      ebx, 80070000h
0x1800265e1  test    eax, eax
0x1800265e3  cmovle  ebx, eax
0x1800265e6  jmp     short loc_1800265FD
0x1800265e8  mov     rdx, [rsp+48h+var_18]; HKEY
0x1800265ed  mov     r9d, edi; int
0x1800265f0  mov     r8d, esi; unsigned int
0x1800265f3  mov     rcx, rbp; void *
0x1800265f6  call    ?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z; CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)
0x1800265fb  mov     ebx, eax
0x1800265fd  mov     rcx, [rsp+48h+hKey]; hKey
0x180026602  test    rcx, rcx
0x180026605  jz      short loc_18002660D
0x180026607  call    cs:__imp_RegCloseKey
0x18002660d  mov     rcx, [rsp+48h+var_18]; hKey
0x180026612  test    rcx, rcx
0x180026615  jz      short loc_18002661D
0x180026617  call    cs:__imp_RegCloseKey
0x18002661d  mov     rbp, [rsp+48h+arg_8]
0x180026622  mov     eax, ebx
0x180026624  mov     rbx, [rsp+48h+arg_0]
0x180026629  mov     rsi, [rsp+48h+arg_10]
0x18002662e  add     rsp, 40h
0x180026632  pop     rdi
0x180026633  retn
```
