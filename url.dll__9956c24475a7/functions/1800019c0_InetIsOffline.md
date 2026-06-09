# InetIsOffline

- ea: `0x1800019c0`
- end: `0x180001a09`
- name: `InetIsOffline`
- size: `73`
- prototype: `BOOL __stdcall(DWORD dwFlags)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800019c0`

## import_xrefs

- `WININET!InternetQueryOptionA` at `0x1800019e5`
- `WININET!InternetQueryOptionA` at `0x1800019e5`

## pseudocode

```c
BOOL __stdcall InetIsOffline(DWORD dwFlags)
{
  BOOL v1; // ebx
  int v3; // [rsp+38h] [rbp+10h] BYREF
  DWORD v4; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v3 = 0;
  v4 = 4;
  if ( InternetQueryOptionA(0, 0x32u, &v3, &v4) )
    return (v3 & 0x10) != 0;
  return v1;
}

```

## disassembly

```asm
0x1800019c0  mov     rax, rsp
0x1800019c3  push    rbx
0x1800019c4  sub     rsp, 20h
0x1800019c8  xor     ebx, ebx
0x1800019ca  mov     dword ptr [rax+10h], 0
0x1800019d1  lea     r9, [rax+18h]; lpdwBufferLength
0x1800019d5  mov     dword ptr [rax+18h], 4
0x1800019dc  lea     r8, [rax+10h]; lpBuffer
0x1800019e0  xor     ecx, ecx; hInternet
0x1800019e2  lea     edx, [rbx+32h]; dwOption
0x1800019e5  call    cs:__imp_InternetQueryOptionA
0x1800019ec  nop     dword ptr [rax+rax+00h]
0x1800019f1  test    eax, eax
0x1800019f3  jz      short loc_180001A00
0x1800019f5  test    byte ptr [rsp+28h+arg_8], 10h
0x1800019fa  lea     eax, [rbx+1]
0x1800019fd  cmovnz  ebx, eax
0x180001a00  mov     eax, ebx
0x180001a02  add     rsp, 20h
0x180001a06  pop     rbx
0x180001a07  retn
```
