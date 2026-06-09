# WDSCheckForDebugger(ushort const *)

- ea: `0x180007ca0`
- end: `0x180007d76`
- name: `?WDSCheckForDebugger@@YAXPEBG@Z`
- size: `214`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007ca0`
- `0x18000ef70`

## import_xrefs

- `msvcrt!clock` at `0x180007d07`
- `msvcrt!clock` at `0x180007d36`
- `msvcrt!clock` at `0x180007d07`
- `msvcrt!clock` at `0x180007d36`
- `KERNEL32!IsDebuggerPresent` at `0x180007d17`
- `KERNEL32!IsDebuggerPresent` at `0x180007d17`
- `KERNEL32!Sleep` at `0x180007d2a`
- `KERNEL32!Sleep` at `0x180007d2a`
- `KERNEL32!DebugBreak` at `0x180007d4d`
- `KERNEL32!DebugBreak` at `0x180007d4d`
- `ADVAPI32!RegCloseKey` at `0x180007d63`
- `ADVAPI32!RegCloseKey` at `0x180007d63`
- `ADVAPI32!RegOpenKeyExW` at `0x180007cce`
- `ADVAPI32!RegOpenKeyExW` at `0x180007cce`

## pseudocode

```c
void __fastcall WDSCheckForDebugger(LPCWSTR lpSubKey)
{
  clock_t v1; // ebx
  int v2; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey)
    && !CRegKey::GetValue((CRegKey *)&hKey, L"DebugBreak", 4u, &v2, 4u)
    && v2 )
  {
    v1 = clock();
    while ( clock() - v1 < 60000 )
    {
      if ( IsDebuggerPresent() )
      {
        DebugBreak();
        break;
      }
      Sleep(0x64u);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180007ca0  push    rbx
0x180007ca2  sub     rsp, 30h
0x180007ca6  and     [rsp+38h+hKey], 0
0x180007cac  lea     rax, [rsp+38h+hKey]
0x180007cb1  and     [rsp+38h+arg_8], 0
0x180007cb6  mov     rdx, rcx; lpSubKey
0x180007cb9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007cc0  mov     [rsp+38h+phkResult], rax; phkResult
0x180007cc5  mov     r9d, 20119h; samDesired
0x180007ccb  xor     r8d, r8d; ulOptions
0x180007cce  call    cs:__imp_RegOpenKeyExW
0x180007cd5  nop     dword ptr [rax+rax+00h]
0x180007cda  test    eax, eax
0x180007cdc  jnz     short loc_180007D59
0x180007cde  lea     r8d, [rax+4]; unsigned int
0x180007ce2  lea     r9, [rsp+38h+arg_8]; void *
0x180007ce7  mov     dword ptr [rsp+38h+phkResult], r8d; unsigned int
0x180007cec  lea     rdx, aDebugbreak; "DebugBreak"
0x180007cf3  lea     rcx, [rsp+38h+hKey]; this
0x180007cf8  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180007cfd  test    eax, eax
0x180007cff  jnz     short loc_180007D59
0x180007d01  cmp     [rsp+38h+arg_8], eax
0x180007d05  jbe     short loc_180007D59
0x180007d07  call    cs:__imp_clock
0x180007d0e  nop     dword ptr [rax+rax+00h]
0x180007d13  mov     ebx, eax
0x180007d15  jmp     short loc_180007D36
0x180007d17  call    cs:__imp_IsDebuggerPresent
0x180007d1e  nop     dword ptr [rax+rax+00h]
0x180007d23  test    eax, eax
0x180007d25  jnz     short loc_180007D4D
0x180007d27  lea     ecx, [rax+64h]; dwMilliseconds
0x180007d2a  call    cs:__imp_Sleep
0x180007d31  nop     dword ptr [rax+rax+00h]
0x180007d36  call    cs:__imp_clock
0x180007d3d  nop     dword ptr [rax+rax+00h]
0x180007d42  sub     eax, ebx
0x180007d44  cmp     eax, 0EA60h
0x180007d49  jl      short loc_180007D17
0x180007d4b  jmp     short loc_180007D59
0x180007d4d  call    cs:__imp_DebugBreak
0x180007d54  nop     dword ptr [rax+rax+00h]
0x180007d59  mov     rcx, [rsp+38h+hKey]; hKey
0x180007d5e  test    rcx, rcx
0x180007d61  jz      short loc_180007D6F
0x180007d63  call    cs:__imp_RegCloseKey
0x180007d6a  nop     dword ptr [rax+rax+00h]
0x180007d6f  add     rsp, 30h
0x180007d73  pop     rbx
0x180007d74  retn
```
