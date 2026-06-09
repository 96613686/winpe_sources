# CreateFileW

- ea: `0x14001abac`
- end: `0x14001abfd`
- name: `CreateFileW`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path`

## callers

- `0x14001933c`
- `0x140019678`

## callees

- `0x14001a3fc`

## string_xrefs

- `0x14001abe7`: `\\.\MountPointManager`

## pseudocode

```c
__int64 CreateFileW()
{
  int v1; // [rsp+30h] [rbp-28h] BYREF
  __int64 v2; // [rsp+34h] [rbp-24h]
  int v3; // [rsp+3Ch] [rbp-1Ch]
  __int128 v4; // [rsp+40h] [rbp-18h]

  v1 = 32;
  v2 = 128;
  v3 = 0;
  v4 = 0;
  return CreateFileInternal(L"\\\\.\\MountPointManager", 0, 3u, 3, (__int64)&v1, 1);
}

```

## disassembly

```asm
0x14001abac  mov     rax, rsp
0x14001abaf  sub     rsp, 58h
0x14001abb3  mov     dword ptr [rax-30h], 1
0x14001abba  xorps   xmm0, xmm0
0x14001abbd  mov     dword ptr [rax-28h], 20h ; ' '
0x14001abc4  mov     r8d, 3
0x14001abca  mov     qword ptr [rax-24h], 80h
0x14001abd2  mov     r9d, r8d
0x14001abd5  mov     dword ptr [rax-1Ch], 0
0x14001abdc  xor     edx, edx
0x14001abde  movdqu  xmmword ptr [rax-18h], xmm0
0x14001abe3  lea     rax, [rax-28h]
0x14001abe7  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x14001abee  mov     [rsp+58h+var_38], rax; __int64
0x14001abf3  call    CreateFileInternal
0x14001abf8  add     rsp, 58h
0x14001abfc  retn
```
