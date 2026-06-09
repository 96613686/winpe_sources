# CW32System::ReadRegDigitSubstitutionMode(void)

- ea: `0x180092d44`
- end: `0x180092e5e`
- name: `?ReadRegDigitSubstitutionMode@CW32System@@SAEXZ`
- size: `282`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180042bf8`

## callees

- `0x180040ae0`
- `0x180046cb4`
- `0x18005ff78`
- `0x180091fb0`
- `0x180092d44`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180092d80`
- `KERNEL32!GetThreadLocale` at `0x180092d80`
- `ADVAPI32!RegOpenKeyExA` at `0x180092de0`
- `ADVAPI32!RegOpenKeyExA` at `0x180092de0`
- `ADVAPI32!RegQueryValueExA` at `0x180092e1f`
- `ADVAPI32!RegQueryValueExA` at `0x180092e1f`
- `ADVAPI32!RegCloseKey` at `0x180092e48`
- `ADVAPI32!RegCloseKey` at `0x180092e48`

## pseudocode

```c
char CW32System::ReadRegDigitSubstitutionMode(void)
{
  char v0; // bl
  LCID ThreadLocale; // eax
  unsigned int v2; // edx
  BYTE Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v0 = 0;
  Type = 0;
  cbData = 0;
  if ( !CW32System::OnWin9xFE() && !CW32System::OnWinNTFE() )
  {
    ThreadLocale = GetThreadLocale();
    if ( ((unsigned int)CW32System::IsBiDiLcid(ThreadLocale)
       || (v2 & 0x3FF) == 0x1E
       || (v2 & 0x3FF) == 0x2A
       || (unsigned int)CW32System::IsIndicLcid(v2))
      && !RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\International", 0, 1u, &hKey) )
    {
      cbData = 2;
      if ( !RegQueryValueExA(hKey, "NumShape", 0, &Type, &Data, &cbData) && Data > 0x2Fu )
      {
        v0 = Data - 47;
        if ( (unsigned __int8)(Data - 47) > 3u )
          v0 = 2;
      }
      RegCloseKey(hKey);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180092d44  push    rbx
0x180092d46  push    rsi
0x180092d47  sub     rsp, 38h
0x180092d4b  mov     [rsp+48h+hKey], 0
0x180092d54  xor     bl, bl
0x180092d56  mov     [rsp+48h+Type], 0
0x180092d5e  mov     [rsp+48h+cbData], 0
0x180092d66  call    ?OnWin9xFE@CW32System@@SA_NXZ; CW32System::OnWin9xFE(void)
0x180092d6b  test    al, al
0x180092d6d  jnz     loc_180092E54
0x180092d73  call    ?OnWinNTFE@CW32System@@SA_NXZ; CW32System::OnWinNTFE(void)
0x180092d78  test    al, al
0x180092d7a  jnz     loc_180092E54
0x180092d80  call    cs:__imp_GetThreadLocale
0x180092d87  nop     dword ptr [rax+rax+00h]
0x180092d8c  mov     ecx, eax; unsigned int
0x180092d8e  mov     edx, eax
0x180092d90  call    ?IsBiDiLcid@CW32System@@SAHK@Z; CW32System::IsBiDiLcid(ulong)
0x180092d95  test    eax, eax
0x180092d97  jnz     short loc_180092DBF
0x180092d99  movzx   ecx, dx
0x180092d9c  mov     eax, 3FFh
0x180092da1  and     cx, ax
0x180092da4  cmp     cx, 1Eh
0x180092da8  jz      short loc_180092DBF
0x180092daa  cmp     cx, 2Ah ; '*'
0x180092dae  jz      short loc_180092DBF
0x180092db0  mov     ecx, edx; unsigned int
0x180092db2  call    ?IsIndicLcid@CW32System@@SAHK@Z; CW32System::IsIndicLcid(ulong)
0x180092db7  test    eax, eax
0x180092db9  jz      loc_180092E54
0x180092dbf  lea     rax, [rsp+48h+hKey]
0x180092dc4  mov     r9d, 1; samDesired
0x180092dca  xor     r8d, r8d; ulOptions
0x180092dcd  mov     [rsp+48h+phkResult], rax; phkResult
0x180092dd2  lea     rdx, SubKey; "Control Panel\\International"
0x180092dd9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180092de0  call    cs:__imp_RegOpenKeyExA
0x180092de7  nop     dword ptr [rax+rax+00h]
0x180092dec  test    eax, eax
0x180092dee  jnz     short loc_180092E54
0x180092df0  mov     rcx, [rsp+48h+hKey]; hKey
0x180092df5  lea     esi, [rax+2]
0x180092df8  lea     rax, [rsp+48h+cbData]
0x180092dfd  mov     [rsp+48h+cbData], esi
0x180092e01  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180092e06  lea     r9, [rsp+48h+Type]; lpType
0x180092e0b  lea     rax, [rsp+48h+Data]
0x180092e10  xor     r8d, r8d; lpReserved
0x180092e13  lea     rdx, ValueName; "NumShape"
0x180092e1a  mov     [rsp+48h+phkResult], rax; lpData
0x180092e1f  call    cs:__imp_RegQueryValueExA
0x180092e26  nop     dword ptr [rax+rax+00h]
0x180092e2b  test    eax, eax
0x180092e2d  jnz     short loc_180092E43
0x180092e2f  movzx   eax, word ptr [rsp+48h+Data]
0x180092e34  cmp     al, 2Fh ; '/'
0x180092e36  jbe     short loc_180092E43
0x180092e38  sub     al, 2Fh ; '/'
0x180092e3a  movzx   ebx, al
0x180092e3d  cmp     bl, 3
0x180092e40  cmova   ebx, esi
0x180092e43  mov     rcx, [rsp+48h+hKey]; hKey
0x180092e48  call    cs:__imp_RegCloseKey
0x180092e4f  nop     dword ptr [rax+rax+00h]
0x180092e54  mov     al, bl
0x180092e56  add     rsp, 38h
0x180092e5a  pop     rsi
0x180092e5b  pop     rbx
0x180092e5c  retn
```
