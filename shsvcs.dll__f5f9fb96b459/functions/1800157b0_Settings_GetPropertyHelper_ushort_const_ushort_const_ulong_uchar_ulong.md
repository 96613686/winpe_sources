# Settings::_GetPropertyHelper(ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x1800157b0`
- end: `0x18001586a`
- name: `?_GetPropertyHelper@Settings@@YAJPEBG0KPEAEK@Z`
- size: `186`
- prototype: `int __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002ebd4`

## callees

- `0x1800157b0`
- `0x1800329cc`
- `0x1800329f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ee`

## pseudocode

```c
int __fastcall Settings::_GetPropertyHelper(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5)
{
  int v7; // ebx
  int result; // eax
  bool v9; // sf
  int v10; // edi
  unsigned int v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF

  phkResult = 0;
  v7 = (int)a3;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &phkResult);
  v9 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v9 = result < 0;
  }
  if ( !v9 )
  {
    v12 = (unsigned int)a5;
    v11 = 0;
    v10 = _RegQueryGeneric(phkResult, 0, a2, &v11, a4, &v12);
    if ( v10 >= 0 && v11 != v7 )
      v10 = -2147467259;
    _RegCloseKey(phkResult);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800157b0  mov     [rsp+arg_0], rbx
0x1800157b5  mov     [rsp+arg_8], rsi
0x1800157ba  push    rdi
0x1800157bb  sub     rsp, 50h
0x1800157bf  mov     rsi, rdx
0x1800157c2  mov     [rsp+58h+var_18], 0
0x1800157cb  mov     rdx, rcx; lpSubKey
0x1800157ce  lea     rax, [rsp+58h+var_18]
0x1800157d3  mov     rdi, r9
0x1800157d6  mov     [rsp+58h+phkResult], rax; phkResult
0x1800157db  mov     ebx, r8d
0x1800157de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800157e5  mov     r9d, 1; samDesired
0x1800157eb  xor     r8d, r8d; ulOptions
0x1800157ee  call    cs:__imp_RegOpenKeyExW
0x1800157f4  test    eax, eax
0x1800157f6  jle     short loc_180015802
0x1800157f8  movzx   eax, ax
0x1800157fb  or      eax, 80070000h
0x180015800  test    eax, eax
0x180015802  jns     short loc_180015814
0x180015804  mov     rbx, [rsp+58h+arg_0]
0x180015809  mov     rsi, [rsp+58h+arg_8]
0x18001580e  add     rsp, 50h
0x180015812  pop     rdi
0x180015813  retn
0x180015814  mov     eax, dword ptr [rsp+58h+arg_20]
0x18001581b  lea     r9, [rsp+58h+var_28]; unsigned int *
0x180015820  mov     rcx, [rsp+58h+var_18]; HKEY
0x180015825  mov     r8, rsi; unsigned __int16 *
0x180015828  mov     [rsp+58h+var_20], eax
0x18001582c  xor     edx, edx; unsigned __int16 *
0x18001582e  lea     rax, [rsp+58h+var_20]
0x180015833  mov     [rsp+58h+var_28], 0
0x18001583b  mov     [rsp+58h+var_30], rax; unsigned int *
0x180015840  mov     [rsp+58h+phkResult], rdi; unsigned __int8 *
0x180015845  call    ?_RegQueryGeneric@@YAJPEAUHKEY__@@PEBG1PEAKPEAE2@Z; _RegQueryGeneric(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *,ulong *)
0x18001584a  mov     edi, eax
0x18001584c  test    eax, eax
0x18001584e  js      short loc_18001585C
0x180015850  cmp     [rsp+58h+var_28], ebx
0x180015854  mov     eax, 80004005h
0x180015859  cmovnz  edi, eax
0x18001585c  mov     rcx, [rsp+58h+var_18]; HKEY
0x180015861  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x180015866  mov     eax, edi
0x180015868  jmp     short loc_180015804
```
