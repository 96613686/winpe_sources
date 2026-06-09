# DeleteRegistryValue

- ea: `0x180041a64`
- end: `0x180041ba8`
- name: `DeleteRegistryValue`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003bc7c`

## callees

- `0x18002f08c`
- `0x1800404a4`
- `0x180041a64`
- `0x180042a80`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180041a93`
- `ADVAPI32!RegOpenKeyExW` at `0x180041a93`
- `ADVAPI32!RegDeleteValueW` at `0x180041b12`
- `ADVAPI32!RegDeleteValueW` at `0x180041b12`
- `ADVAPI32!RegCloseKey` at `0x180041b90`
- `ADVAPI32!RegCloseKey` at `0x180041b90`

## string_xrefs

- `0x180041acd`: `RegOpenKeyEx (HKLM\%S) failed with 0x%x`
- `0x180041b43`: `RegDeleteValue (HKLM\%S\%S) failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DeleteRegistryValue(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(a1, a2, 0, 2u, &hKey);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("RegOpenKeyEx (HKLM\\%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        (__int64)a2,
        v5);
    }
  }
  else
  {
    v5 = RegDeleteValueW(hKey, a3);
    if ( (v5 & 0xFFFFFFFD) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("RegDeleteValue (HKLM\\%S\\%S) failed with 0x%x");
      WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v5);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180041a64  mov     r11, rsp
0x180041a67  mov     [r11+8], rbx
0x180041a6b  mov     [r11+10h], rsi
0x180041a6f  push    rdi
0x180041a70  sub     rsp, 40h
0x180041a74  mov     rsi, r8
0x180041a77  mov     qword ptr [r11+20h], 0
0x180041a7f  lea     rax, [r11+20h]
0x180041a83  xor     r8d, r8d; ulOptions
0x180041a86  mov     r9d, 2; samDesired
0x180041a8c  mov     [r11-28h], rax
0x180041a90  mov     rdi, rdx
0x180041a93  call    cs:__imp_RegOpenKeyExW
0x180041a99  mov     ebx, eax
0x180041a9b  test    eax, eax
0x180041a9d  jz      short loc_180041B0A
0x180041a9f  mov     rax, cs:WPP_GLOBAL_Control
0x180041aa6  lea     rcx, WPP_GLOBAL_Control
0x180041aad  cmp     rax, rcx
0x180041ab0  jz      loc_180041B86
0x180041ab6  cmp     byte ptr [rax+19h], 2
0x180041aba  jb      loc_180041B86
0x180041ac0  test    byte ptr [rax+1Ch], 1
0x180041ac4  jz      loc_180041B86
0x180041aca  mov     r8d, ebx
0x180041acd  lea     rcx, aRegopenkeyexHk; "RegOpenKeyEx (HKLM\\%S) failed with 0x%"...
0x180041ad4  mov     rdx, rdi
0x180041ad7  call    WppDbgPrint
0x180041adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ae3  lea     r9, aNapbase; "NAPBASE"
0x180041aea  mov     edx, 20h ; ' '
0x180041aef  mov     dword ptr [rsp+48h+var_20], ebx
0x180041af3  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041afa  mov     [rsp+48h+var_28], rdi
0x180041aff  mov     rcx, [rcx+10h]
0x180041b03  call    WPP_SF_sSd
0x180041b08  jmp     short loc_180041B86
0x180041b0a  mov     rcx, [rsp+48h+hKey]; hKey
0x180041b0f  mov     rdx, rsi; lpValueName
0x180041b12  call    cs:__imp_RegDeleteValueW
0x180041b18  mov     ebx, eax
0x180041b1a  test    eax, 0FFFFFFFDh
0x180041b1f  jz      short loc_180041B86
0x180041b21  mov     rax, cs:WPP_GLOBAL_Control
0x180041b28  lea     rcx, WPP_GLOBAL_Control
0x180041b2f  cmp     rax, rcx
0x180041b32  jz      short loc_180041B86
0x180041b34  cmp     byte ptr [rax+19h], 2
0x180041b38  jb      short loc_180041B86
0x180041b3a  test    byte ptr [rax+1Ch], 1
0x180041b3e  jz      short loc_180041B86
0x180041b40  mov     r9d, ebx
0x180041b43  lea     rcx, aRegdeletevalue; "RegDeleteValue (HKLM\\%S\\%S) failed wi"...
0x180041b4a  mov     r8, rsi
0x180041b4d  mov     rdx, rdi
0x180041b50  call    WppDbgPrint
0x180041b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b5c  lea     r9, aNapbase; "NAPBASE"
0x180041b63  mov     dword ptr [rsp+48h+var_18], ebx; char
0x180041b67  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180041b6e  mov     edx, 21h ; '!'
0x180041b73  mov     [rsp+48h+var_20], rsi; __int64
0x180041b78  mov     [rsp+48h+var_28], rdi; __int64
0x180041b7d  mov     rcx, [rcx+10h]; LoggerHandle
0x180041b81  call    WPP_SF_sSSD
0x180041b86  mov     rcx, [rsp+48h+hKey]; hKey
0x180041b8b  test    rcx, rcx
0x180041b8e  jz      short loc_180041B96
0x180041b90  call    cs:__imp_RegCloseKey
0x180041b96  mov     rsi, [rsp+48h+arg_8]
0x180041b9b  mov     eax, ebx
0x180041b9d  mov     rbx, [rsp+48h+arg_0]
0x180041ba2  add     rsp, 40h
0x180041ba6  pop     rdi
0x180041ba7  retn
```
