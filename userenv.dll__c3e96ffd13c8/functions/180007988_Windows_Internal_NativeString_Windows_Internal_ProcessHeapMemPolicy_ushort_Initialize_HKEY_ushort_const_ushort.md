# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180007988`
- end: `0x180007a0f`
- name: `?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `135`
- prototype: `__int64 __fastcall(BYTE **, __int64, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a540`

## callees

- `0x180007988`
- `0x1800178ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a07`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
        BYTE **a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4)
{
  LSTATUS v6; // eax
  int v7; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
           a1,
           hKey,
           a4);
    RegCloseKey(hKey);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007988  mov     rax, rsp
0x18000798b  mov     [rax+8], rbx
0x18000798f  mov     [rax+18h], rsi
0x180007993  mov     [rax+10h], rdx
0x180007997  push    rdi
0x180007998  sub     rsp, 30h
0x18000799c  mov     rsi, rcx
0x18000799f  mov     qword ptr [rax+10h], 0
0x1800079a7  lea     rcx, [rax+10h]
0x1800079ab  mov     rdi, r9
0x1800079ae  mov     [rax-18h], rcx
0x1800079b2  mov     rdx, r8; lpSubKey
0x1800079b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800079bc  mov     r9d, 20019h; samDesired
0x1800079c2  xor     r8d, r8d; ulOptions
0x1800079c5  call    cs:__imp_RegOpenKeyExW
0x1800079cb  mov     ebx, eax
0x1800079cd  test    eax, eax
0x1800079cf  jle     short loc_1800079DA
0x1800079d1  movzx   ebx, ax
0x1800079d4  or      ebx, 80070000h
0x1800079da  test    ebx, ebx
0x1800079dc  jns     short loc_1800079F0
0x1800079de  mov     rsi, [rsp+38h+arg_10]
0x1800079e3  mov     eax, ebx
0x1800079e5  mov     rbx, [rsp+38h+arg_0]
0x1800079ea  add     rsp, 30h
0x1800079ee  pop     rdi
0x1800079ef  retn
0x1800079f0  mov     rdx, [rsp+38h+hKey]
0x1800079f5  mov     r8, rdi
0x1800079f8  mov     rcx, rsi
0x1800079fb  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180007a00  mov     rcx, [rsp+38h+hKey]; hKey
0x180007a05  mov     ebx, eax
0x180007a07  call    cs:__imp_RegCloseKey
0x180007a0d  jmp     short loc_1800079DE
```
