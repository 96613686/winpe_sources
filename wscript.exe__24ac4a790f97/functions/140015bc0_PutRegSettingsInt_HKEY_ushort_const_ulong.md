# PutRegSettingsInt(HKEY__ *,ushort const *,ulong)

- ea: `0x140015bc0`
- end: `0x140015cfc`
- name: `?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `316`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400085ac`
- `0x140010e30`

## callees

- `0x140015bc0`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015c55`
- `KERNEL32!GetLastError` at `0x140015c55`
- `KERNEL32!WideCharToMultiByte` at `0x140015c48`
- `KERNEL32!WideCharToMultiByte` at `0x140015caa`
- `KERNEL32!WideCharToMultiByte` at `0x140015c48`
- `KERNEL32!WideCharToMultiByte` at `0x140015caa`
- `ADVAPI32!RegSetValueExA` at `0x140015cd5`
- `ADVAPI32!RegSetValueExA` at `0x140015cd5`
- `ADVAPI32!RegSetValueExW` at `0x140015c06`
- `ADVAPI32!RegSetValueExW` at `0x140015c06`

## pseudocode

```c
signed int __fastcall PutRegSettingsInt(HKEY hKey, LPCWCH lpWideCharStr, int a3)
{
  signed int result; // eax
  int v6; // eax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  CHAR *v11; // rdi
  CHAR MultiByteStr[48]; // [rsp+40h] [rbp+0h] BYREF
  int Data; // [rsp+90h] [rbp+50h] BYREF

  Data = a3;
  if ( Global::g_fWindowsNT )
  {
    result = RegSetValueExW(hKey, lpWideCharStr, 0, 4u, (const BYTE *)&Data, 4u);
    goto LABEL_12;
  }
  if ( lpWideCharStr )
  {
    v6 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v6 )
      goto LABEL_5;
    v7 = v6 + 15LL;
    if ( v7 < v6 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    v11 = MultiByteStr;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v6, 0, 0) )
    {
LABEL_5:
      result = GetLastError();
      goto LABEL_12;
    }
  }
  else
  {
    v11 = 0;
  }
  result = RegSetValueExA(hKey, v11, 0, 4u, (const BYTE *)&Data, 4u);
LABEL_12:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015bc0  mov     [rsp-8+Data], r8d
0x140015bc5  push    rbp
0x140015bc6  push    rbx
0x140015bc7  push    rsi
0x140015bc8  push    rdi
0x140015bc9  sub     rsp, 58h
0x140015bcd  lea     rbp, [rsp+40h]
0x140015bd2  mov     rax, cs:__security_cookie
0x140015bd9  xor     rax, rbp
0x140015bdc  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x140015be0  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140015be7  mov     rbx, rdx
0x140015bea  mov     rsi, rcx
0x140015bed  jz      short loc_140015C11
0x140015bef  mov     r9d, 4; dwType
0x140015bf5  lea     rax, [rbp+30h+Data]
0x140015bf9  mov     [rsp+70h+cbData], r9d; cbData
0x140015bfe  xor     r8d, r8d; Reserved
0x140015c01  mov     [rsp+70h+lpData], rax; lpData
0x140015c06  call    cs:__imp_RegSetValueExW
0x140015c0c  jmp     loc_140015CDB
0x140015c11  test    rbx, rbx
0x140015c14  jz      loc_140015CB6
0x140015c1a  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015c23  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015c27  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140015c30  mov     r8, rbx; lpWideCharStr
0x140015c33  mov     [rsp+70h+cbData], 0; cbMultiByte
0x140015c3b  xor     edx, edx; dwFlags
0x140015c3d  xor     ecx, ecx; CodePage
0x140015c3f  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x140015c48  call    cs:__imp_WideCharToMultiByte
0x140015c4e  movsxd  rdx, eax
0x140015c51  test    eax, eax
0x140015c53  jnz     short loc_140015C5D
0x140015c55  call    cs:__imp_GetLastError
0x140015c5b  jmp     short loc_140015CDB
0x140015c5d  lea     rcx, [rdx+0Fh]
0x140015c61  cmp     rcx, rdx
0x140015c64  ja      short loc_140015C70
0x140015c66  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140015c70  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140015c74  mov     rax, rcx
0x140015c77  call    _alloca_probe
0x140015c7c  sub     rsp, rcx
0x140015c7f  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015c83  mov     r8, rbx; lpWideCharStr
0x140015c86  xor     ecx, ecx; CodePage
0x140015c88  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015c91  lea     rdi, [rsp+70h+MultiByteStr]
0x140015c96  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140015c9f  mov     [rsp+70h+cbData], edx; cbMultiByte
0x140015ca3  xor     edx, edx; dwFlags
0x140015ca5  mov     [rsp+70h+lpData], rdi; lpMultiByteStr
0x140015caa  call    cs:__imp_WideCharToMultiByte
0x140015cb0  test    eax, eax
0x140015cb2  jnz     short loc_140015CB8
0x140015cb4  jmp     short loc_140015C55
0x140015cb6  xor     edi, edi
0x140015cb8  mov     r9d, 4; dwType
0x140015cbe  lea     rax, [rbp+30h+Data]
0x140015cc2  mov     [rsp+70h+cbData], r9d; cbData
0x140015cc7  xor     r8d, r8d; Reserved
0x140015cca  mov     rdx, rdi; lpValueName
0x140015ccd  mov     [rsp+70h+lpData], rax; lpData
0x140015cd2  mov     rcx, rsi; hKey
0x140015cd5  call    cs:__imp_RegSetValueExA
0x140015cdb  test    eax, eax
0x140015cdd  jle     short loc_140015CE7
0x140015cdf  movzx   eax, ax
0x140015ce2  or      eax, 80070000h
0x140015ce7  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x140015ceb  xor     rcx, rbp; StackCookie
0x140015cee  call    __security_check_cookie
0x140015cf3  lea     rsp, [rbp+18h]
0x140015cf7  pop     rdi
0x140015cf8  pop     rsi
0x140015cf9  pop     rbx
0x140015cfa  pop     rbp
0x140015cfb  retn
```
