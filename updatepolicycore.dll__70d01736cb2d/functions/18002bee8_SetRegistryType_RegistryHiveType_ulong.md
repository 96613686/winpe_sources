# SetRegistryType(RegistryHiveType,ulong *)

- ea: `0x18002bee8`
- end: `0x18002bfc3`
- name: `?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bfcc`
- `0x18002c120`
- `0x18002c288`
- `0x18002c374`
- `0x18002c610`
- `0x18002c6dc`
- `0x18002c77c`

## callees

- `0x18000aac0`
- `0x18002bee8`
- `0x18002d294`

## string_xrefs

- `0x18002bf52`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall SetRegistryType(int a1, _DWORD *a2)
{
  int ProcessorArchitecture; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = a1;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  if ( !byte_18004EE1D )
  {
    byte_18004EE1C = 0;
    LOWORD(v9) = -1;
    ProcessorArchitecture = GetProcessorArchitecture((unsigned __int16 *)&v9);
    v5 = ProcessorArchitecture;
    if ( ProcessorArchitecture < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
        (const char *)(unsigned int)ProcessorArchitecture,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
        (const char *)v5,
        v7);
      return v5;
    }
    if ( (_WORD)v9 == 9 || (_WORD)v9 == 12 )
      byte_18004EE1C = 1;
    byte_18004EE1D = 1;
  }
  if ( byte_18004EE1C )
    *a2 |= 0x100u;
  return 0;
}

```

## disassembly

```asm
0x18002bee8  mov     [rsp+arg_8], rbx
0x18002beed  mov     [rsp+arg_0], ecx
0x18002bef1  push    rdi; int
0x18002bef2  sub     rsp, 20h
0x18002bef6  mov     rbx, rdx
0x18002bef9  test    rdx, rdx
0x18002befc  jnz     short loc_18002BF23
0x18002befe  mov     rcx, [rsp+28h]; this
0x18002bf03  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18002bf0a  mov     ebx, 80070057h
0x18002bf0f  mov     edx, 1B4h; void *
0x18002bf14  mov     r9d, ebx; char *
0x18002bf17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bf1c  mov     eax, ebx
0x18002bf1e  jmp     loc_18002BFB8
0x18002bf23  cmp     cs:byte_18004EE1D, 0
0x18002bf2a  jnz     short loc_18002BFA9
0x18002bf2c  mov     eax, 0FFFFh
0x18002bf31  mov     cs:byte_18004EE1C, 0
0x18002bf38  lea     rcx, [rsp+28h+arg_0]; unsigned __int16 *
0x18002bf3d  mov     word ptr [rsp+28h+arg_0], ax
0x18002bf42  call    ?GetProcessorArchitecture@@YAJPEAG@Z; GetProcessorArchitecture(ushort *)
0x18002bf47  mov     edi, eax
0x18002bf49  test    eax, eax
0x18002bf4b  jns     short loc_18002BF83
0x18002bf4d  mov     rcx, [rsp+28h]; this
0x18002bf52  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002bf59  mov     r9d, eax; char *
0x18002bf5c  mov     edx, 0FCh; void *
0x18002bf61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bf66  mov     rcx, [rsp+28h]; this
0x18002bf6b  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18002bf72  mov     r9d, edi; char *
0x18002bf75  mov     edx, 1C1h; void *
0x18002bf7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bf7f  mov     eax, edi
0x18002bf81  jmp     short loc_18002BFB8
0x18002bf83  mov     eax, 9
0x18002bf88  cmp     ax, word ptr [rsp+28h+arg_0]
0x18002bf8d  jz      short loc_18002BF9B
0x18002bf8f  mov     eax, 0Ch
0x18002bf94  cmp     ax, word ptr [rsp+28h+arg_0]
0x18002bf99  jnz     short loc_18002BFA2
0x18002bf9b  mov     cs:byte_18004EE1C, 1
0x18002bfa2  mov     cs:byte_18004EE1D, 1
0x18002bfa9  cmp     cs:byte_18004EE1C, 0
0x18002bfb0  jz      short loc_18002BFB6
0x18002bfb2  bts     dword ptr [rbx], 8
0x18002bfb6  xor     eax, eax
0x18002bfb8  mov     rbx, [rsp+28h+arg_8]
0x18002bfbd  add     rsp, 20h
0x18002bfc1  pop     rdi
0x18002bfc2  retn
```
