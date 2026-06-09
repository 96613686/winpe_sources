# IsSystemResource(ushort const *)

- ea: `0x180068aac`
- end: `0x180068b63`
- name: `?IsSystemResource@@YAHPEBG@Z`
- size: `183`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180067010`

## callees

- `0x1800358c0`
- `0x180068aac`

## import_xrefs

- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180068afc`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180068afc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068b30`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068b30`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180068ae1`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180068ae1`

## pseudocode

```c
__int64 __fastcall IsSystemResource(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR String1[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = 0;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) && (unsigned int)SHExpandEnvironmentStringsW(a1, String1, 260) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    LOBYTE(v2) = CompareStringOrdinal(String1, v3, Buffer, v3, 1) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x180068aac  mov     [rsp+arg_8], rbx
0x180068ab1  mov     [rsp+arg_10], rsi
0x180068ab6  push    rdi
0x180068ab7  sub     rsp, 460h
0x180068abe  mov     rax, cs:__security_cookie
0x180068ac5  xor     rax, rsp
0x180068ac8  mov     [rsp+468h+var_18], rax
0x180068ad0  mov     rdi, rcx
0x180068ad3  xor     esi, esi
0x180068ad5  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x180068ada  mov     edx, 104h; uSize
0x180068adf  mov     ebx, esi
0x180068ae1  call    cs:__imp_GetWindowsDirectoryW
0x180068ae7  test    eax, eax
0x180068ae9  jz      short loc_180068B3C
0x180068aeb  mov     r8d, 104h
0x180068af1  lea     rdx, [rsp+468h+String1]
0x180068af9  mov     rcx, rdi
0x180068afc  call    cs:__imp_SHExpandEnvironmentStringsW
0x180068b02  test    eax, eax
0x180068b04  jz      short loc_180068B3C
0x180068b06  lea     rax, [rsp+468h+Buffer]
0x180068b0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180068b0f  inc     rdx; cchCount1
0x180068b12  cmp     [rax+rdx*2], si
0x180068b16  jnz     short loc_180068B0F
0x180068b18  mov     r9d, edx; cchCount2
0x180068b1b  mov     [rsp+468h+bIgnoreCase], 1; bIgnoreCase
0x180068b23  lea     r8, [rsp+468h+Buffer]; lpString2
0x180068b28  lea     rcx, [rsp+468h+String1]; lpString1
0x180068b30  call    cs:__imp_CompareStringOrdinal
0x180068b36  cmp     eax, 2
0x180068b39  setz    bl
0x180068b3c  mov     eax, ebx
0x180068b3e  mov     rcx, [rsp+468h+var_18]
0x180068b46  xor     rcx, rsp; StackCookie
0x180068b49  call    __security_check_cookie
0x180068b4e  lea     r11, [rsp+468h+var_8]
0x180068b56  mov     rbx, [r11+18h]
0x180068b5a  mov     rsi, [r11+20h]
0x180068b5e  mov     rsp, r11
0x180068b61  pop     rdi
0x180068b62  retn
```
