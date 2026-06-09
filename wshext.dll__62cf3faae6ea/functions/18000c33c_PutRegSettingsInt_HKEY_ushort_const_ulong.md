# PutRegSettingsInt(HKEY__ *,ushort const *,ulong)

- ea: `0x18000c33c`
- end: `0x18000c478`
- name: `?PutRegSettingsInt@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `316`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000af74`

## callees

- `0x18000c33c`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c3d1`
- `KERNEL32!GetLastError` at `0x18000c3d1`
- `KERNEL32!WideCharToMultiByte` at `0x18000c3c4`
- `KERNEL32!WideCharToMultiByte` at `0x18000c426`
- `KERNEL32!WideCharToMultiByte` at `0x18000c3c4`
- `KERNEL32!WideCharToMultiByte` at `0x18000c426`
- `ADVAPI32!RegSetValueExA` at `0x18000c451`
- `ADVAPI32!RegSetValueExA` at `0x18000c451`
- `ADVAPI32!RegSetValueExW` at `0x18000c382`
- `ADVAPI32!RegSetValueExW` at `0x18000c382`

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
0x18000c33c  mov     [rsp-8+Data], r8d
0x18000c341  push    rbp
0x18000c342  push    rbx
0x18000c343  push    rsi
0x18000c344  push    rdi
0x18000c345  sub     rsp, 58h
0x18000c349  lea     rbp, [rsp+40h]
0x18000c34e  mov     rax, cs:__security_cookie
0x18000c355  xor     rax, rbp
0x18000c358  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x18000c35c  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000c363  mov     rbx, rdx
0x18000c366  mov     rsi, rcx
0x18000c369  jz      short loc_18000C38D
0x18000c36b  mov     r9d, 4; dwType
0x18000c371  lea     rax, [rbp+30h+Data]
0x18000c375  mov     [rsp+70h+cbData], r9d; cbData
0x18000c37a  xor     r8d, r8d; Reserved
0x18000c37d  mov     [rsp+70h+lpData], rax; lpData
0x18000c382  call    cs:__imp_RegSetValueExW
0x18000c388  jmp     loc_18000C457
0x18000c38d  test    rbx, rbx
0x18000c390  jz      loc_18000C432
0x18000c396  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000c39f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000c3a3  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000c3ac  mov     r8, rbx; lpWideCharStr
0x18000c3af  mov     [rsp+70h+cbData], 0; cbMultiByte
0x18000c3b7  xor     edx, edx; dwFlags
0x18000c3b9  xor     ecx, ecx; CodePage
0x18000c3bb  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x18000c3c4  call    cs:__imp_WideCharToMultiByte
0x18000c3ca  movsxd  rdx, eax
0x18000c3cd  test    eax, eax
0x18000c3cf  jnz     short loc_18000C3D9
0x18000c3d1  call    cs:__imp_GetLastError
0x18000c3d7  jmp     short loc_18000C457
0x18000c3d9  lea     rcx, [rdx+0Fh]
0x18000c3dd  cmp     rcx, rdx
0x18000c3e0  ja      short loc_18000C3EC
0x18000c3e2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c3ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c3f0  mov     rax, rcx
0x18000c3f3  call    _alloca_probe
0x18000c3f8  sub     rsp, rcx
0x18000c3fb  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000c3ff  mov     r8, rbx; lpWideCharStr
0x18000c402  xor     ecx, ecx; CodePage
0x18000c404  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000c40d  lea     rdi, [rsp+70h+MultiByteStr]
0x18000c412  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000c41b  mov     [rsp+70h+cbData], edx; cbMultiByte
0x18000c41f  xor     edx, edx; dwFlags
0x18000c421  mov     [rsp+70h+lpData], rdi; lpMultiByteStr
0x18000c426  call    cs:__imp_WideCharToMultiByte
0x18000c42c  test    eax, eax
0x18000c42e  jnz     short loc_18000C434
0x18000c430  jmp     short loc_18000C3D1
0x18000c432  xor     edi, edi
0x18000c434  mov     r9d, 4; dwType
0x18000c43a  lea     rax, [rbp+30h+Data]
0x18000c43e  mov     [rsp+70h+cbData], r9d; cbData
0x18000c443  xor     r8d, r8d; Reserved
0x18000c446  mov     rdx, rdi; lpValueName
0x18000c449  mov     [rsp+70h+lpData], rax; lpData
0x18000c44e  mov     rcx, rsi; hKey
0x18000c451  call    cs:__imp_RegSetValueExA
0x18000c457  test    eax, eax
0x18000c459  jle     short loc_18000C463
0x18000c45b  movzx   eax, ax
0x18000c45e  or      eax, 80070000h
0x18000c463  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x18000c467  xor     rcx, rbp; StackCookie
0x18000c46a  call    __security_check_cookie
0x18000c46f  lea     rsp, [rbp+18h]
0x18000c473  pop     rdi
0x18000c474  pop     rsi
0x18000c475  pop     rbx
0x18000c476  pop     rbp
0x18000c477  retn
```
