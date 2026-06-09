# PutRegSettingsString(HKEY__ *,ushort const *,ushort const *,bool)

- ea: `0x18000f2cc`
- end: `0x18000f499`
- name: `?PutRegSettingsString@@YAJPEAUHKEY__@@PEBG1_N@Z`
- size: `461`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008930`

## callees

- `0x18000f2cc`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f33a`
- `ADVAPI32!RegSetValueExW` at `0x18000f33a`
- `ADVAPI32!RegSetValueExA` at `0x18000f46a`
- `ADVAPI32!RegSetValueExA` at `0x18000f46a`
- `KERNEL32!GetLastError` at `0x18000f378`
- `KERNEL32!GetLastError` at `0x18000f378`
- `KERNEL32!WideCharToMultiByte` at `0x18000f36b`
- `KERNEL32!WideCharToMultiByte` at `0x18000f3ce`
- `KERNEL32!WideCharToMultiByte` at `0x18000f3f6`
- `KERNEL32!WideCharToMultiByte` at `0x18000f444`
- `KERNEL32!WideCharToMultiByte` at `0x18000f36b`
- `KERNEL32!WideCharToMultiByte` at `0x18000f3ce`
- `KERNEL32!WideCharToMultiByte` at `0x18000f3f6`
- `KERNEL32!WideCharToMultiByte` at `0x18000f444`

## pseudocode

```c
signed int __fastcall PutRegSettingsString(HKEY hKey, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v5; // rbx
  signed int result; // eax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  int v12; // eax
  DWORD cbData; // esi
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  BYTE MultiByteStr[80]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    if ( lpData )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&lpData[2 * v5] );
    }
    else
    {
      LODWORD(v5) = 0;
    }
    result = RegSetValueExW(hKey, L"Device", 0, 1u, lpData, 2 * v5 + 2);
  }
  else
  {
    v7 = WideCharToMultiByte(0, 0, L"Device", -1, 0, 0, 0, 0);
    if ( !v7 )
      goto LABEL_9;
    v8 = v7 + 15LL;
    if ( v8 < v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    if ( !WideCharToMultiByte(0, 0, L"Device", -1, (LPSTR)MultiByteStr, v7, 0, 0) )
      goto LABEL_9;
    v12 = WideCharToMultiByte(0, 0, (LPCWCH)lpData, -1, 0, 0, 0, 0);
    cbData = v12;
    if ( !v12 )
      goto LABEL_9;
    v14 = v12 + 15LL;
    if ( v14 < v12 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    if ( WideCharToMultiByte(0, 0, (LPCWCH)lpData, -1, (LPSTR)MultiByteStr, v12, 0, 0) )
      result = RegSetValueExA(hKey, (LPCSTR)MultiByteStr, 0, 1u, MultiByteStr, cbData);
    else
LABEL_9:
      result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f2cc  push    rbp
0x18000f2ce  push    rbx
0x18000f2cf  push    rsi
0x18000f2d0  push    rdi
0x18000f2d1  push    r12
0x18000f2d3  push    r13
0x18000f2d5  push    r14
0x18000f2d7  push    r15
0x18000f2d9  sub     rsp, 58h
0x18000f2dd  lea     rbp, [rsp+40h]
0x18000f2e2  mov     rax, cs:__security_cookie
0x18000f2e9  xor     rax, rbp
0x18000f2ec  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18000f2f0  xor     r13d, r13d
0x18000f2f3  mov     rdi, r8
0x18000f2f6  cmp     cs:?g_fWindowsNT@Global@@2_NA, r13b; bool Global::g_fWindowsNT
0x18000f2fd  mov     r15, rcx
0x18000f300  jz      short loc_18000F345
0x18000f302  test    r8, r8
0x18000f305  jz      short loc_18000F317
0x18000f307  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f30b  inc     rbx
0x18000f30e  cmp     [r8+rbx*2], r13w
0x18000f313  jnz     short loc_18000F30B
0x18000f315  jmp     short loc_18000F31A
0x18000f317  mov     rbx, r13
0x18000f31a  lea     eax, ds:2[rbx*2]
0x18000f321  mov     r9d, 1; dwType
0x18000f327  mov     [rsp+90h+cbData], eax; cbData
0x18000f32b  lea     rdx, ValueName; "Device"
0x18000f332  xor     r8d, r8d; Reserved
0x18000f335  mov     [rsp+90h+lpData], rdi; lpData
0x18000f33a  call    cs:__imp_RegSetValueExW
0x18000f340  jmp     loc_18000F470
0x18000f345  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000f34a  lea     r8, ValueName; "Device"
0x18000f351  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000f356  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f35a  mov     [rsp+90h+cbData], r13d; cbMultiByte
0x18000f35f  mov     r9d, ebx; cchWideChar
0x18000f362  xor     edx, edx; dwFlags
0x18000f364  mov     [rsp+90h+lpData], r13; lpMultiByteStr
0x18000f369  xor     ecx, ecx; CodePage
0x18000f36b  call    cs:__imp_WideCharToMultiByte
0x18000f371  movsxd  rdx, eax
0x18000f374  test    eax, eax
0x18000f376  jnz     short loc_18000F383
0x18000f378  call    cs:__imp_GetLastError
0x18000f37e  jmp     loc_18000F470
0x18000f383  lea     rcx, [rdx+0Fh]
0x18000f387  mov     r14, 0FFFFFFFFFFFFFF0h
0x18000f391  cmp     rcx, rdx
0x18000f394  ja      short loc_18000F399
0x18000f396  mov     rcx, r14
0x18000f399  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000f39d  mov     rax, rcx
0x18000f3a0  call    _alloca_probe
0x18000f3a5  sub     rsp, rcx
0x18000f3a8  lea     r8, ValueName; "Device"
0x18000f3af  mov     r9d, ebx; cchWideChar
0x18000f3b2  xor     ecx, ecx; CodePage
0x18000f3b4  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000f3b9  lea     r12, [rsp+90h+MultiByteStr]
0x18000f3be  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000f3c3  mov     [rsp+90h+cbData], edx; cbMultiByte
0x18000f3c7  xor     edx, edx; dwFlags
0x18000f3c9  mov     [rsp+90h+lpData], r12; lpMultiByteStr
0x18000f3ce  call    cs:__imp_WideCharToMultiByte
0x18000f3d4  test    eax, eax
0x18000f3d6  jz      short loc_18000F378
0x18000f3d8  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000f3dd  mov     r9d, ebx; cchWideChar
0x18000f3e0  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000f3e5  mov     r8, rdi; lpWideCharStr
0x18000f3e8  mov     [rsp+90h+cbData], r13d; cbMultiByte
0x18000f3ed  xor     edx, edx; dwFlags
0x18000f3ef  xor     ecx, ecx; CodePage
0x18000f3f1  mov     [rsp+90h+lpData], r13; lpMultiByteStr
0x18000f3f6  call    cs:__imp_WideCharToMultiByte
0x18000f3fc  movsxd  rsi, eax
0x18000f3ff  test    eax, eax
0x18000f401  jz      loc_18000F378
0x18000f407  lea     rcx, [rsi+0Fh]
0x18000f40b  cmp     rcx, rsi
0x18000f40e  ja      short loc_18000F413
0x18000f410  mov     rcx, r14
0x18000f413  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000f417  mov     rax, rcx
0x18000f41a  call    _alloca_probe
0x18000f41f  sub     rsp, rcx
0x18000f422  mov     r9d, ebx; cchWideChar
0x18000f425  mov     r8, rdi; lpWideCharStr
0x18000f428  xor     edx, edx; dwFlags
0x18000f42a  xor     ecx, ecx; CodePage
0x18000f42c  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000f431  lea     r14, [rsp+90h+MultiByteStr]
0x18000f436  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x18000f43b  mov     [rsp+90h+cbData], esi; cbMultiByte
0x18000f43f  mov     [rsp+90h+lpData], r14; lpMultiByteStr
0x18000f444  call    cs:__imp_WideCharToMultiByte
0x18000f44a  test    eax, eax
0x18000f44c  jz      loc_18000F378
0x18000f452  mov     [rsp+90h+cbData], esi; cbData
0x18000f456  mov     r9d, 1; dwType
0x18000f45c  xor     r8d, r8d; Reserved
0x18000f45f  mov     [rsp+90h+lpData], r14; lpData
0x18000f464  mov     rdx, r12; lpValueName
0x18000f467  mov     rcx, r15; hKey
0x18000f46a  call    cs:__imp_RegSetValueExA
0x18000f470  test    eax, eax
0x18000f472  jle     short loc_18000F47C
0x18000f474  movzx   eax, ax
0x18000f477  or      eax, 80070000h
0x18000f47c  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x18000f480  xor     rcx, rbp; StackCookie
0x18000f483  call    __security_check_cookie
0x18000f488  lea     rsp, [rbp+18h]
0x18000f48c  pop     r15
0x18000f48e  pop     r14
0x18000f490  pop     r13
0x18000f492  pop     r12
0x18000f494  pop     rdi
0x18000f495  pop     rsi
0x18000f496  pop     rbx
0x18000f497  pop     rbp
0x18000f498  retn
```
