# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180008a58`
- end: `0x180008aec`
- name: `?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001c00c`

## callees

- `0x180008a58`
- `0x180019204`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ade`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
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
0x180008a58  mov     rax, rsp
0x180008a5b  mov     [rax+8], rbx
0x180008a5f  mov     [rax+18h], rsi
0x180008a63  mov     [rax+10h], rdx
0x180008a67  push    rdi
0x180008a68  sub     rsp, 30h
0x180008a6c  mov     rsi, rcx
0x180008a6f  mov     qword ptr [rax+10h], 0
0x180008a77  lea     rcx, [rax+10h]
0x180008a7b  mov     rdi, r9
0x180008a7e  mov     [rax-18h], rcx
0x180008a82  mov     rdx, r8; lpSubKey
0x180008a85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008a8c  mov     r9d, 20019h; samDesired
0x180008a92  xor     r8d, r8d; ulOptions
0x180008a95  call    cs:__imp_RegOpenKeyExW
0x180008a9c  nop     dword ptr [rax+rax+00h]
0x180008aa1  mov     ebx, eax
0x180008aa3  test    eax, eax
0x180008aa5  jle     short loc_180008AB0
0x180008aa7  movzx   ebx, ax
0x180008aaa  or      ebx, 80070000h
0x180008ab0  test    ebx, ebx
0x180008ab2  jns     short loc_180008AC7
0x180008ab4  mov     rsi, [rsp+38h+arg_10]
0x180008ab9  mov     eax, ebx
0x180008abb  mov     rbx, [rsp+38h+arg_0]
0x180008ac0  add     rsp, 30h
0x180008ac4  pop     rdi
0x180008ac5  retn
0x180008ac7  mov     rdx, [rsp+38h+hKey]
0x180008acc  mov     r8, rdi
0x180008acf  mov     rcx, rsi
0x180008ad2  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180008ad7  mov     rcx, [rsp+38h+hKey]; hKey
0x180008adc  mov     ebx, eax
0x180008ade  call    cs:__imp_RegCloseKey
0x180008ae5  nop     dword ptr [rax+rax+00h]
0x180008aea  jmp     short loc_180008AB4
```
