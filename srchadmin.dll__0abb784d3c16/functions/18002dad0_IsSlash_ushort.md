# IsSlash(ushort)

- ea: `0x18002dad0`
- end: `0x18002db3f`
- name: `?IsSlash@@YAHG@Z`
- size: `111`
- prototype: `__int64 __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002da3c`

## callees

- `0x18002dad0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002db02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002db2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002db02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002db2a`

## pseudocode

```c
__int64 __fastcall IsSlash(WCHAR a1)
{
  unsigned int v1; // ebx
  WCHAR String1; // [rsp+40h] [rbp+8h] BYREF
  __int16 v4; // [rsp+42h] [rbp+Ah]

  String1 = a1;
  v4 = 0;
  v1 = 1;
  if ( CompareStringW(0x7Fu, 1u, &String1, 1, L"\\", 1) != 2 )
    return CompareStringW(0x7Fu, 1u, &String1, 1, L"/", 1) == 2;
  return v1;
}

```

## disassembly

```asm
0x18002dad0  push    rbx
0x18002dad2  sub     rsp, 30h
0x18002dad6  xor     eax, eax
0x18002dad8  mov     [rsp+38h+String1], cx
0x18002dadd  mov     [rsp+38h+arg_2], ax
0x18002dae2  lea     r8, [rsp+38h+String1]; lpString1
0x18002dae7  lea     ebx, [rax+1]
0x18002daea  lea     rax, SubStr; "\\"
0x18002daf1  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18002daf5  mov     r9d, ebx; cchCount1
0x18002daf8  mov     [rsp+38h+lpString2], rax; lpString2
0x18002dafd  mov     edx, ebx; dwCmpFlags
0x18002daff  lea     ecx, [rbx+7Eh]; Locale
0x18002db02  call    cs:__imp_CompareStringW
0x18002db08  cmp     eax, 2
0x18002db0b  jz      short loc_18002DB37
0x18002db0d  lea     rax, asc_180038444; "/"
0x18002db14  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18002db18  mov     r9d, ebx; cchCount1
0x18002db1b  mov     [rsp+38h+lpString2], rax; lpString2
0x18002db20  lea     r8, [rsp+38h+String1]; lpString1
0x18002db25  mov     edx, ebx; dwCmpFlags
0x18002db27  lea     ecx, [rbx+7Eh]; Locale
0x18002db2a  call    cs:__imp_CompareStringW
0x18002db30  cmp     eax, 2
0x18002db33  jz      short loc_18002DB37
0x18002db35  xor     ebx, ebx
0x18002db37  mov     eax, ebx
0x18002db39  add     rsp, 30h
0x18002db3d  pop     rbx
0x18002db3e  retn
```
