# IniRegCreateKeyExW

- ea: `0x383adc710`
- end: `0x383adc859`
- name: `IniRegCreateKeyExW`
- size: `329`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD ulOptions, REGSAM samDesired, LPSECURITY_ATTRIBUTES, PHKEY, LPDWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x383895830`

## callees

- `0x383adc710`
- `0x383add760`
- `0x383addfe0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x383adc7a3`
- `KERNEL32!SetLastError` at `0x383adc7f3`
- `KERNEL32!SetLastError` at `0x383adc7a3`
- `KERNEL32!SetLastError` at `0x383adc7f3`
- `KERNEL32!DebugBreak` at `0x383adc732`
- `KERNEL32!DebugBreak` at `0x383adc743`
- `KERNEL32!DebugBreak` at `0x383adc732`
- `KERNEL32!DebugBreak` at `0x383adc743`
- `ADVAPI32!RegOpenKeyExW` at `0x383adc784`
- `ADVAPI32!RegOpenKeyExW` at `0x383adc784`
- `ADVAPI32!RegCreateKeyExW` at `0x383adc848`
- `ADVAPI32!RegCreateKeyExW` at `0x383adc848`

## pseudocode

```c
LSTATUS __fastcall IniRegCreateKeyExW(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD ulOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  LSTATUS v11; // eax
  HKEY Path; // rax

  if ( !dword_383B1F178 )
    return RegCreateKeyExW(
             hKey,
             lpSubKey,
             a3,
             a4,
             ulOptions,
             samDesired,
             lpSecurityAttributes,
             phkResult,
             lpdwDisposition);
  if ( a4 )
    DebugBreak();
  if ( lpSecurityAttributes )
    DebugBreak();
  if ( dword_383B1F178 )
    v11 = IniRegOpenKeyW(hKey, lpSubKey, phkResult);
  else
    v11 = RegOpenKeyExW(hKey, lpSubKey, ulOptions, samDesired, phkResult);
  if ( v11 )
  {
    Path = (HKEY)IniRegMakePath(hKey, lpSubKey);
    if ( !Path )
      return 8;
    *phkResult = Path;
    *lpdwDisposition = 1;
  }
  else if ( lpdwDisposition )
  {
    *lpdwDisposition = 2;
    SetLastError(0);
    return 0;
  }
  SetLastError(0);
  return 0;
}

```

## disassembly

```asm
0x383adc710  mov     [rsp+arg_8], rsi
0x383adc715  push    rdi
0x383adc716  sub     rsp, 50h
0x383adc71a  cmp     cs:dword_383B1F178, 0
0x383adc721  mov     rdi, rdx
0x383adc724  mov     rsi, rcx
0x383adc727  jz      loc_383ADC80B
0x383adc72d  test    r9, r9
0x383adc730  jz      short loc_383ADC738
0x383adc732  call    cs:__imp_DebugBreak
0x383adc738  cmp     [rsp+58h+arg_30], 0
0x383adc741  jz      short loc_383ADC749
0x383adc743  call    cs:__imp_DebugBreak
0x383adc749  cmp     cs:dword_383B1F178, 0
0x383adc750  mov     [rsp+58h+arg_0], rbx
0x383adc755  mov     rbx, [rsp+58h+arg_38]
0x383adc75d  mov     rdx, rdi; lpSubKey
0x383adc760  mov     rcx, rsi; hKey
0x383adc763  jz      short loc_383ADC76F
0x383adc765  mov     r8, rbx
0x383adc768  call    IniRegOpenKeyW
0x383adc76d  jmp     short loc_383ADC78A
0x383adc76f  mov     r9d, [rsp+58h+samDesired]; samDesired
0x383adc777  mov     r8d, [rsp+58h+ulOptions]; ulOptions
0x383adc77f  mov     [rsp+58h+phkResult], rbx; phkResult
0x383adc784  call    cs:__imp_RegOpenKeyExW
0x383adc78a  test    eax, eax
0x383adc78c  jnz     short loc_383ADC7BB
0x383adc78e  mov     rax, [rsp+58h+arg_40]
0x383adc796  test    rax, rax
0x383adc799  jz      short loc_383ADC7F1
0x383adc79b  xor     ecx, ecx; dwErrCode
0x383adc79d  mov     dword ptr [rax], 2
0x383adc7a3  call    cs:__imp_SetLastError
0x383adc7a9  mov     rbx, [rsp+58h+arg_0]
0x383adc7ae  xor     eax, eax
0x383adc7b0  mov     rsi, [rsp+58h+arg_8]
0x383adc7b5  add     rsp, 50h
0x383adc7b9  pop     rdi
0x383adc7ba  retn
0x383adc7bb  mov     rdx, rdi
0x383adc7be  mov     rcx, rsi
0x383adc7c1  call    IniRegMakePath
0x383adc7c6  test    rax, rax
0x383adc7c9  jnz     short loc_383ADC7E0
0x383adc7cb  mov     eax, 8
0x383adc7d0  mov     rbx, [rsp+58h+arg_0]
0x383adc7d5  mov     rsi, [rsp+58h+arg_8]
0x383adc7da  add     rsp, 50h
0x383adc7de  pop     rdi
0x383adc7df  retn
0x383adc7e0  mov     [rbx], rax
0x383adc7e3  mov     rax, [rsp+58h+arg_40]
0x383adc7eb  mov     dword ptr [rax], 1
0x383adc7f1  xor     ecx, ecx; dwErrCode
0x383adc7f3  call    cs:__imp_SetLastError
0x383adc7f9  mov     rbx, [rsp+58h+arg_0]
0x383adc7fe  xor     eax, eax
0x383adc800  mov     rsi, [rsp+58h+arg_8]
0x383adc805  add     rsp, 50h
0x383adc809  pop     rdi
0x383adc80a  retn
0x383adc80b  mov     rax, [rsp+58h+arg_40]
0x383adc813  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x383adc818  mov     rax, [rsp+58h+arg_38]
0x383adc820  mov     [rsp+58h+var_20], rax; phkResult
0x383adc825  mov     rax, [rsp+58h+arg_30]
0x383adc82d  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x383adc832  mov     eax, [rsp+58h+samDesired]
0x383adc839  mov     [rsp+58h+var_30], eax; samDesired
0x383adc83d  mov     eax, [rsp+58h+ulOptions]
0x383adc844  mov     dword ptr [rsp+58h+phkResult], eax; dwOptions
0x383adc848  call    cs:__imp_RegCreateKeyExW
0x383adc84e  mov     rsi, [rsp+58h+arg_8]
0x383adc853  add     rsp, 50h
0x383adc857  pop     rdi
0x383adc858  retn
```
