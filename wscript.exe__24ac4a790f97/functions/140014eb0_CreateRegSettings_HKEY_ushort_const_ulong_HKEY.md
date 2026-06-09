# CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x140014eb0`
- end: `0x140014ff9`
- name: `?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `329`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400085ac`
- `0x140010d64`
- `0x140010e30`

## callees

- `0x140014eb0`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140014f54`
- `KERNEL32!GetLastError` at `0x140014f54`
- `KERNEL32!WideCharToMultiByte` at `0x140014f47`
- `KERNEL32!WideCharToMultiByte` at `0x140014fa3`
- `KERNEL32!WideCharToMultiByte` at `0x140014f47`
- `KERNEL32!WideCharToMultiByte` at `0x140014fa3`
- `ADVAPI32!RegCreateKeyExA` at `0x140014fd1`
- `ADVAPI32!RegCreateKeyExA` at `0x140014fd1`
- `ADVAPI32!RegCreateKeyExW` at `0x140014f07`
- `ADVAPI32!RegCreateKeyExW` at `0x140014f07`

## pseudocode

```c
signed int __fastcall CreateRegSettings(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)
{
  signed int result; // eax
  bool v9; // cc
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  CHAR MultiByteStr[64]; // [rsp+50h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegCreateKeyExW(hKey, lpWideCharStr, 0, 0, 0, samDesired, 0, phkResult, 0);
  }
  else
  {
    v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_7;
    v11 = v10 + 15LL;
    if ( v11 < v10 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v10, 0, 0) )
    {
LABEL_7:
      result = GetLastError();
      v9 = result <= 0;
      goto LABEL_4;
    }
    result = RegCreateKeyExA(hKey, MultiByteStr, 0, 0, 0, samDesired, 0, phkResult, 0);
  }
  v9 = result <= 0;
  if ( !result )
    return 0;
LABEL_4:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140014eb0  mov     r11, rsp
0x140014eb3  push    rbp
0x140014eb4  push    rbx
0x140014eb5  push    rsi
0x140014eb6  push    rdi
0x140014eb7  push    r12
0x140014eb9  push    r14
0x140014ebb  push    r15
0x140014ebd  sub     rsp, 60h
0x140014ec1  lea     rbp, [rsp+50h]
0x140014ec6  mov     rax, cs:__security_cookie
0x140014ecd  xor     rax, rbp
0x140014ed0  mov     qword ptr [rbp+40h+MultiByteStr], rax
0x140014ed4  xor     r12d, r12d
0x140014ed7  mov     rdi, r9
0x140014eda  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x140014ee1  mov     esi, r8d
0x140014ee4  mov     rbx, rdx
0x140014ee7  mov     r14, rcx
0x140014eea  jz      short loc_140014F28
0x140014eec  mov     [r11-58h], r12
0x140014ef0  mov     [r11-60h], r9
0x140014ef4  xor     r9d, r9d; lpClass
0x140014ef7  mov     [r11-68h], r12
0x140014efb  mov     [rsp+90h+samDesired], r8d; samDesired
0x140014f00  xor     r8d, r8d; Reserved
0x140014f03  mov     [r11-78h], r12d
0x140014f07  call    cs:__imp_RegCreateKeyExW
0x140014f0d  test    eax, eax
0x140014f0f  jz      loc_140014FDC
0x140014f15  jle     loc_140014FDE
0x140014f1b  movzx   eax, ax
0x140014f1e  or      eax, 80070000h
0x140014f23  jmp     loc_140014FDE
0x140014f28  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140014f2d  or      r9d, 0FFFFFFFFh; cchWideChar
0x140014f31  mov     [rsp+90h+lpDefaultChar], r12; lpDefaultChar
0x140014f36  mov     r8, rbx; lpWideCharStr
0x140014f39  mov     [rsp+90h+samDesired], r12d; cbMultiByte
0x140014f3e  xor     edx, edx; dwFlags
0x140014f40  xor     ecx, ecx; CodePage
0x140014f42  mov     [rsp+90h+lpMultiByteStr], r12; lpMultiByteStr
0x140014f47  call    cs:__imp_WideCharToMultiByte
0x140014f4d  movsxd  rdx, eax
0x140014f50  test    eax, eax
0x140014f52  jnz     short loc_140014F5E
0x140014f54  call    cs:__imp_GetLastError
0x140014f5a  test    eax, eax
0x140014f5c  jmp     short loc_140014F15
0x140014f5e  lea     rcx, [rdx+0Fh]
0x140014f62  cmp     rcx, rdx
0x140014f65  ja      short loc_140014F71
0x140014f67  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140014f71  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140014f75  mov     rax, rcx
0x140014f78  call    _alloca_probe
0x140014f7d  sub     rsp, rcx
0x140014f80  or      r9d, 0FFFFFFFFh; cchWideChar
0x140014f84  mov     r8, rbx; lpWideCharStr
0x140014f87  xor     ecx, ecx; CodePage
0x140014f89  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140014f8e  lea     r15, [rsp+90h+MultiByteStr]
0x140014f93  mov     [rsp+90h+lpDefaultChar], r12; lpDefaultChar
0x140014f98  mov     [rsp+90h+samDesired], edx; cbMultiByte
0x140014f9c  xor     edx, edx; dwFlags
0x140014f9e  mov     [rsp+90h+lpMultiByteStr], r15; lpMultiByteStr
0x140014fa3  call    cs:__imp_WideCharToMultiByte
0x140014fa9  test    eax, eax
0x140014fab  jz      short loc_140014F54
0x140014fad  mov     [rsp+90h+lpdwDisposition], r12; lpdwDisposition
0x140014fb2  xor     r9d, r9d; lpClass
0x140014fb5  mov     [rsp+90h+lpUsedDefaultChar], rdi; phkResult
0x140014fba  xor     r8d, r8d; Reserved
0x140014fbd  mov     [rsp+90h+lpDefaultChar], r12; lpSecurityAttributes
0x140014fc2  mov     rdx, r15; lpSubKey
0x140014fc5  mov     [rsp+90h+samDesired], esi; samDesired
0x140014fc9  mov     rcx, r14; hKey
0x140014fcc  mov     dword ptr [rsp+90h+lpMultiByteStr], r12d; dwOptions
0x140014fd1  call    cs:__imp_RegCreateKeyExA
0x140014fd7  jmp     loc_140014F0D
0x140014fdc  xor     eax, eax
0x140014fde  mov     rcx, qword ptr [rbp+40h+MultiByteStr]
0x140014fe2  xor     rcx, rbp; StackCookie
0x140014fe5  call    __security_check_cookie
0x140014fea  lea     rsp, [rbp+10h]
0x140014fee  pop     r15
0x140014ff0  pop     r14
0x140014ff2  pop     r12
0x140014ff4  pop     rdi
0x140014ff5  pop     rsi
0x140014ff6  pop     rbx
0x140014ff7  pop     rbp
0x140014ff8  retn
```
