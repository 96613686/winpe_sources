# CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)

- ea: `0x180029130`
- end: `0x180029220`
- name: `?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, bool *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800402e8`

## callees

- `0x180029130`
- `0x18002b1b0`
- `0x18003ffe8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800291f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800291fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800291f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800291fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800291c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800291c5`

## pseudocode

```c
__int64 __fastcall CreateShellSessionSubKey(const unsigned __int16 *a1, __int64 a2, bool *a3, HKEY *a4)
{
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-18h] BYREF

  if ( a4 )
    *a4 = 0;
  hKey = 0;
  v5 = CreateShellSessionKey((unsigned int)a1, &hKey);
  if ( v5 >= 0 )
  {
    phkResult = 0;
    dwDisposition = 0;
    v6 = RegCreateKeyExW(hKey, L"DirectLaunchHandlers", 0, 0, 1u, 0xF003Fu, 0, &phkResult, &dwDisposition);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( a4 )
        *a4 = phkResult;
      else
        RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029130  mov     [rsp+arg_0], rbx
0x180029135  push    rdi
0x180029136  sub     rsp, 70h
0x18002913a  mov     rax, cs:__security_cookie
0x180029141  xor     rax, rsp
0x180029144  mov     [rsp+78h+var_10], rax
0x180029149  mov     rdi, r9
0x18002914c  test    r9, r9
0x18002914f  jz      short loc_180029158
0x180029151  mov     qword ptr [r9], 0
0x180029158  lea     rdx, [rsp+78h+hKey]; HKEY *
0x18002915d  mov     [rsp+78h+hKey], 0
0x180029166  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x18002916b  mov     ebx, eax
0x18002916d  test    eax, eax
0x18002916f  js      loc_180029203
0x180029175  mov     rcx, [rsp+78h+hKey]; hKey
0x18002917a  lea     rax, [rsp+78h+dwDisposition]
0x18002917f  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180029184  lea     rdx, aDirectlaunchha; "DirectLaunchHandlers"
0x18002918b  lea     rax, [rsp+78h+var_28]
0x180029190  mov     [rsp+78h+var_28], 0
0x180029199  mov     [rsp+78h+phkResult], rax; phkResult
0x18002919e  xor     r9d, r9d; lpClass
0x1800291a1  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800291aa  xor     r8d, r8d; Reserved
0x1800291ad  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x1800291b5  mov     [rsp+78h+dwOptions], 1; dwOptions
0x1800291bd  mov     [rsp+78h+dwDisposition], 0
0x1800291c5  call    cs:__imp_RegCreateKeyExW
0x1800291cb  mov     ebx, eax
0x1800291cd  test    eax, eax
0x1800291cf  jle     short loc_1800291DA
0x1800291d1  movzx   ebx, ax
0x1800291d4  or      ebx, 80070000h
0x1800291da  test    ebx, ebx
0x1800291dc  js      short loc_1800291F8
0x1800291de  test    rdi, rdi
0x1800291e1  jz      short loc_1800291ED
0x1800291e3  mov     rax, [rsp+78h+var_28]
0x1800291e8  mov     [rdi], rax
0x1800291eb  jmp     short loc_1800291F8
0x1800291ed  mov     rcx, [rsp+78h+var_28]; hKey
0x1800291f2  call    cs:__imp_RegCloseKey
0x1800291f8  mov     rcx, [rsp+78h+hKey]; hKey
0x1800291fd  call    cs:__imp_RegCloseKey
0x180029203  mov     eax, ebx
0x180029205  mov     rcx, [rsp+78h+var_10]
0x18002920a  xor     rcx, rsp; StackCookie
0x18002920d  call    __security_check_cookie
0x180029212  mov     rbx, [rsp+78h+arg_0]
0x18002921a  add     rsp, 70h
0x18002921e  pop     rdi
0x18002921f  retn
```
