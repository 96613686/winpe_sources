# OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x140015a7c`
- end: `0x140015bb8`
- name: `?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `316`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005d74`
- `0x1400085ac`
- `0x140008854`
- `0x14000a238`
- `0x14000a3f8`
- `0x14000a568`

## callees

- `0x140015a7c`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015b21`
- `KERNEL32!GetLastError` at `0x140015b21`
- `KERNEL32!WideCharToMultiByte` at `0x140015b14`
- `KERNEL32!WideCharToMultiByte` at `0x140015b70`
- `KERNEL32!WideCharToMultiByte` at `0x140015b14`
- `KERNEL32!WideCharToMultiByte` at `0x140015b70`
- `ADVAPI32!RegOpenKeyExA` at `0x140015b90`
- `ADVAPI32!RegOpenKeyExA` at `0x140015b90`
- `ADVAPI32!RegOpenKeyExW` at `0x140015ac1`
- `ADVAPI32!RegOpenKeyExW` at `0x140015ac1`

## pseudocode

```c
signed int __fastcall OpenRegSettings(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)
{
  signed int result; // eax
  bool v9; // cc
  int cbMultiByte; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  CHAR *v15; // rdi
  CHAR MultiByteStr[64]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegOpenKeyExW(hKey, lpWideCharStr, 0, samDesired, phkResult);
  }
  else
  {
    if ( lpWideCharStr && *lpWideCharStr )
    {
      cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
      if ( !cbMultiByte )
        goto LABEL_9;
      v11 = cbMultiByte + 15LL;
      if ( v11 < cbMultiByte )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
      v13 = alloca(v12);
      v14 = alloca(v12);
      v15 = MultiByteStr;
      if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, cbMultiByte, 0, 0) )
      {
LABEL_9:
        result = GetLastError();
        v9 = result <= 0;
        goto LABEL_4;
      }
    }
    else
    {
      v15 = 0;
    }
    result = RegOpenKeyExA(hKey, v15, 0, samDesired, phkResult);
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
0x140015a7c  push    rbp
0x140015a7e  push    rbx
0x140015a7f  push    rsi
0x140015a80  push    rdi
0x140015a81  push    r12
0x140015a83  push    r14
0x140015a85  push    r15
0x140015a87  sub     rsp, 50h
0x140015a8b  lea     rbp, [rsp+40h]
0x140015a90  mov     rax, cs:__security_cookie
0x140015a97  xor     rax, rbp
0x140015a9a  mov     qword ptr [rbp+40h+MultiByteStr], rax
0x140015a9e  xor     r12d, r12d
0x140015aa1  mov     rsi, r9
0x140015aa4  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x140015aab  mov     r14d, r8d
0x140015aae  mov     rbx, rdx
0x140015ab1  mov     r15, rcx
0x140015ab4  jz      short loc_140015AE2
0x140015ab6  mov     [rsp+80h+phkResult], r9; phkResult
0x140015abb  mov     r9d, r8d; samDesired
0x140015abe  xor     r8d, r8d; ulOptions
0x140015ac1  call    cs:__imp_RegOpenKeyExW
0x140015ac7  test    eax, eax
0x140015ac9  jz      loc_140015B9B
0x140015acf  jle     loc_140015B9D
0x140015ad5  movzx   eax, ax
0x140015ad8  or      eax, 80070000h
0x140015add  jmp     loc_140015B9D
0x140015ae2  test    rbx, rbx
0x140015ae5  jz      loc_140015B7C
0x140015aeb  cmp     [rdx], r12w
0x140015aef  jz      loc_140015B7C
0x140015af5  mov     [rsp+80h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140015afa  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015afe  mov     [rsp+80h+lpDefaultChar], r12; lpDefaultChar
0x140015b03  mov     r8, rbx; lpWideCharStr
0x140015b06  mov     [rsp+80h+cbMultiByte], r12d; cbMultiByte
0x140015b0b  xor     edx, edx; dwFlags
0x140015b0d  xor     ecx, ecx; CodePage
0x140015b0f  mov     [rsp+80h+phkResult], r12; lpMultiByteStr
0x140015b14  call    cs:__imp_WideCharToMultiByte
0x140015b1a  movsxd  rdx, eax
0x140015b1d  test    eax, eax
0x140015b1f  jnz     short loc_140015B2B
0x140015b21  call    cs:__imp_GetLastError
0x140015b27  test    eax, eax
0x140015b29  jmp     short loc_140015ACF
0x140015b2b  lea     rcx, [rdx+0Fh]
0x140015b2f  cmp     rcx, rdx
0x140015b32  ja      short loc_140015B3E
0x140015b34  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140015b3e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140015b42  mov     rax, rcx
0x140015b45  call    _alloca_probe
0x140015b4a  sub     rsp, rcx
0x140015b4d  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015b51  mov     r8, rbx; lpWideCharStr
0x140015b54  xor     ecx, ecx; CodePage
0x140015b56  mov     [rsp+80h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140015b5b  lea     rdi, [rsp+80h+MultiByteStr]
0x140015b60  mov     [rsp+80h+lpDefaultChar], r12; lpDefaultChar
0x140015b65  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x140015b69  xor     edx, edx; dwFlags
0x140015b6b  mov     [rsp+80h+phkResult], rdi; lpMultiByteStr
0x140015b70  call    cs:__imp_WideCharToMultiByte
0x140015b76  test    eax, eax
0x140015b78  jnz     short loc_140015B7F
0x140015b7a  jmp     short loc_140015B21
0x140015b7c  mov     rdi, r12
0x140015b7f  mov     r9d, r14d; samDesired
0x140015b82  mov     [rsp+80h+phkResult], rsi; phkResult
0x140015b87  xor     r8d, r8d; ulOptions
0x140015b8a  mov     rdx, rdi; lpSubKey
0x140015b8d  mov     rcx, r15; hKey
0x140015b90  call    cs:__imp_RegOpenKeyExA
0x140015b96  jmp     loc_140015AC7
0x140015b9b  xor     eax, eax
0x140015b9d  mov     rcx, qword ptr [rbp+40h+MultiByteStr]
0x140015ba1  xor     rcx, rbp; StackCookie
0x140015ba4  call    __security_check_cookie
0x140015ba9  lea     rsp, [rbp+10h]
0x140015bad  pop     r15
0x140015baf  pop     r14
0x140015bb1  pop     r12
0x140015bb3  pop     rdi
0x140015bb4  pop     rsi
0x140015bb5  pop     rbx
0x140015bb6  pop     rbp
0x140015bb7  retn
```
