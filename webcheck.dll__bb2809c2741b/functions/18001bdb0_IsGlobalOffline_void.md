# IsGlobalOffline(void)

- ea: `0x18001bdb0`
- end: `0x18001be0e`
- name: `?IsGlobalOffline@@YAHXZ`
- size: `94`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a6d4`
- `0x18001b0f8`

## callees

- `0x18001bdb0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18001bdd5`
- `KERNEL32!LoadLibraryExA` at `0x18001bdd5`
- `WININET!InternetQueryOptionW` at `0x18001bdf1`
- `WININET!InternetQueryOptionW` at `0x18001bdf1`

## string_xrefs

- `0x18001bdce`: `wininet.dll`

## pseudocode

```c
HMODULE IsGlobalOffline(void)
{
  HMODULE result; // rax
  BOOL v1; // ebx
  int Buffer; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp+10h] BYREF

  Buffer = 0;
  dwBufferLength = 4;
  result = LoadLibraryExA("wininet.dll", 0, 0x800u);
  if ( result )
  {
    v1 = 0;
    if ( InternetQueryOptionW(0, 0x32u, &Buffer, &dwBufferLength) )
      return (HMODULE)((Buffer & 0x10) != 0);
    return (HMODULE)v1;
  }
  return result;
}

```

## disassembly

```asm
0x18001bdb0  push    rbx
0x18001bdb2  sub     rsp, 20h
0x18001bdb6  xor     edx, edx; hFile
0x18001bdb8  mov     [rsp+28h+Buffer], 0
0x18001bdc0  mov     r8d, 800h; dwFlags
0x18001bdc6  mov     [rsp+28h+dwBufferLength], 4
0x18001bdce  lea     rcx, aWininetDll_0; "wininet.dll"
0x18001bdd5  call    cs:__imp_LoadLibraryExA
0x18001bddb  test    rax, rax
0x18001bdde  jz      short loc_18001BE08
0x18001bde0  xor     ebx, ebx
0x18001bde2  lea     r9, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x18001bde7  lea     r8, [rsp+28h+Buffer]; lpBuffer
0x18001bdec  xor     ecx, ecx; hInternet
0x18001bdee  lea     edx, [rbx+32h]; dwOption
0x18001bdf1  call    cs:__imp_InternetQueryOptionW
0x18001bdf7  test    eax, eax
0x18001bdf9  jz      short loc_18001BE06
0x18001bdfb  test    byte ptr [rsp+28h+Buffer], 10h
0x18001be00  lea     eax, [rbx+1]
0x18001be03  cmovnz  ebx, eax
0x18001be06  mov     eax, ebx
0x18001be08  add     rsp, 20h
0x18001be0c  pop     rbx
0x18001be0d  retn
```
