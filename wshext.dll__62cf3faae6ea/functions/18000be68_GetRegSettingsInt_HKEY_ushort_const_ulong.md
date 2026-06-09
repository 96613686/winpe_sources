# GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)

- ea: `0x18000be68`
- end: `0x18000bfd7`
- name: `?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `367`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000adfc`

## callees

- `0x18000be68`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bf07`
- `KERNEL32!GetLastError` at `0x18000bf07`
- `KERNEL32!WideCharToMultiByte` at `0x18000befa`
- `KERNEL32!WideCharToMultiByte` at `0x18000bf73`
- `KERNEL32!WideCharToMultiByte` at `0x18000befa`
- `KERNEL32!WideCharToMultiByte` at `0x18000bf73`
- `ADVAPI32!RegQueryValueExA` at `0x18000bf98`
- `ADVAPI32!RegQueryValueExA` at `0x18000bf98`
- `ADVAPI32!RegQueryValueExW` at `0x18000bebd`
- `ADVAPI32!RegQueryValueExW` at `0x18000bebd`

## pseudocode

```c
signed int __fastcall GetRegSettingsInt(HKEY hKey, const unsigned __int16 *a2, BYTE *lpData)
{
  signed int result; // eax
  int v6; // eax
  bool v7; // cc
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  DWORD Type; // [rsp+40h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp+4h] BYREF

  Type = 0;
  cbData = 4;
  if ( Global::g_fWindowsNT )
  {
    result = RegQueryValueExW(hKey, L"Timeout", 0, &Type, lpData, &cbData);
  }
  else
  {
    v6 = WideCharToMultiByte(0, 0, L"Timeout", -1, 0, 0, 0, 0);
    if ( !v6 )
      goto LABEL_4;
    v8 = v6 + 15LL;
    if ( v8 < v6 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    if ( !WideCharToMultiByte(0, 0, L"Timeout", -1, (LPSTR)&Type, v6, 0, 0) )
    {
LABEL_4:
      result = GetLastError();
      v7 = result <= 0;
      goto LABEL_5;
    }
    result = RegQueryValueExA(hKey, (LPCSTR)&Type, 0, &Type, lpData, &cbData);
  }
  v7 = result <= 0;
  if ( !result )
  {
    if ( Type == 4 )
      return cbData != 4 ? 0x80040153 : 0;
    else
      return -2147221165;
  }
LABEL_5:
  if ( !v7 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000be68  push    rbp
0x18000be6a  push    rbx
0x18000be6b  push    rsi
0x18000be6c  push    rdi
0x18000be6d  sub     rsp, 58h
0x18000be71  lea     rbp, [rsp+40h]
0x18000be76  mov     rax, cs:__security_cookie
0x18000be7d  xor     rax, rbp
0x18000be80  mov     [rbp+30h+var_28], rax
0x18000be84  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000be8b  mov     rbx, r8
0x18000be8e  mov     rdi, rcx
0x18000be91  mov     [rbp+30h+Type], 0
0x18000be98  mov     [rbp+30h+cbData], 4
0x18000be9f  jz      short loc_18000BEC8
0x18000bea1  lea     rax, [rbp+30h+cbData]
0x18000bea5  xor     r8d, r8d; lpReserved
0x18000bea8  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000bead  lea     r9, [rbp+30h+Type]; lpType
0x18000beb1  lea     rdx, aTimeout; "Timeout"
0x18000beb8  mov     [rsp+70h+lpData], rbx; lpData
0x18000bebd  call    cs:__imp_RegQueryValueExW
0x18000bec3  jmp     loc_18000BF9E
0x18000bec8  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000bed1  lea     r8, aTimeout; "Timeout"
0x18000bed8  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000bee1  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000bee5  mov     dword ptr [rsp+70h+lpcbData], 0; cbMultiByte
0x18000beed  xor     edx, edx; dwFlags
0x18000beef  xor     ecx, ecx; CodePage
0x18000bef1  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x18000befa  call    cs:__imp_WideCharToMultiByte
0x18000bf00  movsxd  rdx, eax
0x18000bf03  test    eax, eax
0x18000bf05  jnz     short loc_18000BF22
0x18000bf07  call    cs:__imp_GetLastError
0x18000bf0d  test    eax, eax
0x18000bf0f  jle     loc_18000BFC2
0x18000bf15  movzx   eax, ax
0x18000bf18  or      eax, 80070000h
0x18000bf1d  jmp     loc_18000BFC2
0x18000bf22  lea     rcx, [rdx+0Fh]
0x18000bf26  cmp     rcx, rdx
0x18000bf29  ja      short loc_18000BF35
0x18000bf2b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000bf35  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bf39  mov     rax, rcx
0x18000bf3c  call    _alloca_probe
0x18000bf41  sub     rsp, rcx
0x18000bf44  lea     r8, aTimeout; "Timeout"
0x18000bf4b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000bf4f  xor     ecx, ecx; CodePage
0x18000bf51  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000bf5a  lea     rsi, [rsp+70h+Type]
0x18000bf5f  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x18000bf68  mov     dword ptr [rsp+70h+lpcbData], edx; cbMultiByte
0x18000bf6c  xor     edx, edx; dwFlags
0x18000bf6e  mov     [rsp+70h+lpData], rsi; lpMultiByteStr
0x18000bf73  call    cs:__imp_WideCharToMultiByte
0x18000bf79  test    eax, eax
0x18000bf7b  jz      short loc_18000BF07
0x18000bf7d  lea     rax, [rbp+30h+cbData]
0x18000bf81  xor     r8d, r8d; lpReserved
0x18000bf84  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000bf89  lea     r9, [rbp+30h+Type]; lpType
0x18000bf8d  mov     rdx, rsi; lpValueName
0x18000bf90  mov     [rsp+70h+lpData], rbx; lpData
0x18000bf95  mov     rcx, rdi; hKey
0x18000bf98  call    cs:__imp_RegQueryValueExA
0x18000bf9e  test    eax, eax
0x18000bfa0  jnz     loc_18000BF0F
0x18000bfa6  cmp     [rbp+30h+Type], 4
0x18000bfaa  jnz     short loc_18000BFBD
0x18000bfac  mov     eax, [rbp+30h+cbData]
0x18000bfaf  sub     eax, 4
0x18000bfb2  neg     eax
0x18000bfb4  sbb     eax, eax
0x18000bfb6  and     eax, 80040153h
0x18000bfbb  jmp     short loc_18000BFC2
0x18000bfbd  mov     eax, 80040153h
0x18000bfc2  mov     rcx, [rbp+30h+var_28]
0x18000bfc6  xor     rcx, rbp; StackCookie
0x18000bfc9  call    __security_check_cookie
0x18000bfce  lea     rsp, [rbp+18h]
0x18000bfd2  pop     rdi
0x18000bfd3  pop     rsi
0x18000bfd4  pop     rbx
0x18000bfd5  pop     rbp
0x18000bfd6  retn
```
