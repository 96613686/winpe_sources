# Settings::_GetPropertySizeHelper(ushort const *,ushort const *,ulong *)

- ea: `0x1800189dc`
- end: `0x180018a6c`
- name: `?_GetPropertySizeHelper@Settings@@YAJPEBG0PEAK@Z`
- size: `144`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002ecec`

## callees

- `0x1800189dc`
- `0x1800329cc`
- `0x1800329f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a15`

## pseudocode

```c
__int64 __fastcall Settings::_GetPropertySizeHelper(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  LSTATUS v6; // eax
  signed int Generic; // ebx
  HKEY v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &v9);
  Generic = v6;
  if ( v6 > 0 )
    Generic = (unsigned __int16)v6 | 0x80070000;
  if ( Generic >= 0 )
  {
    Generic = _RegQueryGeneric(v9, 0, a2, 0, 0, a3);
    _RegCloseKey(v9);
  }
  return (unsigned int)Generic;
}

```

## disassembly

```asm
0x1800189dc  mov     r11, rsp
0x1800189df  mov     [r11+8], rbx
0x1800189e3  mov     [r11+10h], rsi
0x1800189e7  push    rdi
0x1800189e8  sub     rsp, 30h
0x1800189ec  mov     rsi, rdx
0x1800189ef  mov     qword ptr [r11+20h], 0
0x1800189f7  mov     rdx, rcx; lpSubKey
0x1800189fa  lea     rax, [r11+20h]
0x1800189fe  mov     rdi, r8
0x180018a01  mov     [r11-18h], rax
0x180018a05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018a0c  mov     r9d, 1; samDesired
0x180018a12  xor     r8d, r8d; ulOptions
0x180018a15  call    cs:__imp_RegOpenKeyExW
0x180018a1b  mov     ebx, eax
0x180018a1d  test    eax, eax
0x180018a1f  jle     short loc_180018A2A
0x180018a21  movzx   ebx, ax
0x180018a24  or      ebx, 80070000h
0x180018a2a  test    ebx, ebx
0x180018a2c  js      short loc_180018A5A
0x180018a2e  mov     rcx, [rsp+38h+arg_18]; HKEY
0x180018a33  xor     r9d, r9d; unsigned int *
0x180018a36  mov     [rsp+38h+var_10], rdi; unsigned int *
0x180018a3b  mov     r8, rsi; unsigned __int16 *
0x180018a3e  xor     edx, edx; unsigned __int16 *
0x180018a40  mov     [rsp+38h+var_18], 0; unsigned __int8 *
0x180018a49  call    ?_RegQueryGeneric@@YAJPEAUHKEY__@@PEBG1PEAKPEAE2@Z; _RegQueryGeneric(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *,ulong *)
0x180018a4e  mov     rcx, [rsp+38h+arg_18]; HKEY
0x180018a53  mov     ebx, eax
0x180018a55  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x180018a5a  mov     rsi, [rsp+38h+arg_8]
0x180018a5f  mov     eax, ebx
0x180018a61  mov     rbx, [rsp+38h+arg_0]
0x180018a66  add     rsp, 30h
0x180018a6a  pop     rdi
0x180018a6b  retn
```
