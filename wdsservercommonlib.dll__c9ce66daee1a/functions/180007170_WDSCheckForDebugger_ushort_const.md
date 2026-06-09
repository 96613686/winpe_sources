# WDSCheckForDebugger(ushort const *)

- ea: `0x180007170`
- end: `0x180007246`
- name: `?WDSCheckForDebugger@@YAXPEBG@Z`
- size: `214`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007170`
- `0x18000e400`

## import_xrefs

- `msvcrt!clock` at `0x1800071d7`
- `msvcrt!clock` at `0x180007206`
- `msvcrt!clock` at `0x1800071d7`
- `msvcrt!clock` at `0x180007206`
- `KERNEL32!IsDebuggerPresent` at `0x1800071e7`
- `KERNEL32!IsDebuggerPresent` at `0x1800071e7`
- `KERNEL32!DebugBreak` at `0x18000721d`
- `KERNEL32!DebugBreak` at `0x18000721d`
- `KERNEL32!Sleep` at `0x1800071fa`
- `KERNEL32!Sleep` at `0x1800071fa`
- `ADVAPI32!RegCloseKey` at `0x180007233`
- `ADVAPI32!RegCloseKey` at `0x180007233`
- `ADVAPI32!RegOpenKeyExW` at `0x18000719e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000719e`

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
0x180007170  push    rbx
0x180007172  sub     rsp, 30h
0x180007176  and     [rsp+38h+hKey], 0
0x18000717c  lea     rax, [rsp+38h+hKey]
0x180007181  and     [rsp+38h+arg_8], 0
0x180007186  mov     rdx, rcx; lpSubKey
0x180007189  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007190  mov     [rsp+38h+phkResult], rax; phkResult
0x180007195  mov     r9d, 20119h; samDesired
0x18000719b  xor     r8d, r8d; ulOptions
0x18000719e  call    cs:__imp_RegOpenKeyExW
0x1800071a5  nop     dword ptr [rax+rax+00h]
0x1800071aa  test    eax, eax
0x1800071ac  jnz     short loc_180007229
0x1800071ae  lea     r8d, [rax+4]; unsigned int
0x1800071b2  lea     r9, [rsp+38h+arg_8]; void *
0x1800071b7  mov     dword ptr [rsp+38h+phkResult], r8d; unsigned int
0x1800071bc  lea     rdx, aDebugbreak; "DebugBreak"
0x1800071c3  lea     rcx, [rsp+38h+hKey]; this
0x1800071c8  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x1800071cd  test    eax, eax
0x1800071cf  jnz     short loc_180007229
0x1800071d1  cmp     [rsp+38h+arg_8], eax
0x1800071d5  jbe     short loc_180007229
0x1800071d7  call    cs:__imp_clock
0x1800071de  nop     dword ptr [rax+rax+00h]
0x1800071e3  mov     ebx, eax
0x1800071e5  jmp     short loc_180007206
0x1800071e7  call    cs:__imp_IsDebuggerPresent
0x1800071ee  nop     dword ptr [rax+rax+00h]
0x1800071f3  test    eax, eax
0x1800071f5  jnz     short loc_18000721D
0x1800071f7  lea     ecx, [rax+64h]; dwMilliseconds
0x1800071fa  call    cs:__imp_Sleep
0x180007201  nop     dword ptr [rax+rax+00h]
0x180007206  call    cs:__imp_clock
0x18000720d  nop     dword ptr [rax+rax+00h]
0x180007212  sub     eax, ebx
0x180007214  cmp     eax, 0EA60h
0x180007219  jl      short loc_1800071E7
0x18000721b  jmp     short loc_180007229
0x18000721d  call    cs:__imp_DebugBreak
0x180007224  nop     dword ptr [rax+rax+00h]
0x180007229  mov     rcx, [rsp+38h+hKey]; hKey
0x18000722e  test    rcx, rcx
0x180007231  jz      short loc_18000723F
0x180007233  call    cs:__imp_RegCloseKey
0x18000723a  nop     dword ptr [rax+rax+00h]
0x18000723f  add     rsp, 30h
0x180007243  pop     rbx
0x180007244  retn
```
