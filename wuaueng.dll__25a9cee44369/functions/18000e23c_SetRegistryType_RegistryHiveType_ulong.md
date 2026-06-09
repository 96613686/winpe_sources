# SetRegistryType(RegistryHiveType,ulong *)

- ea: `0x18000e23c`
- end: `0x18000e317`
- name: `?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z`
- size: `219`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3b0`

## callees

- `0x180003760`
- `0x18000e23c`
- `0x18000f4ec`

## string_xrefs

- `0x18000e2a6`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall SetRegistryType(int a1, _DWORD *a2)
{
  int ProcessorArchitecture; // eax
  unsigned int v5; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
  if ( !byte_180022035 )
  {
    byte_180022034 = 0;
    LOWORD(v7) = -1;
    ProcessorArchitecture = GetProcessorArchitecture((unsigned __int16 *)&v7);
    v5 = ProcessorArchitecture;
    if ( ProcessorArchitecture < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
        (const char *)(unsigned int)ProcessorArchitecture);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\RegUtil\\RegUtil.cpp",
        (const char *)v5);
      return v5;
    }
    if ( (_WORD)v7 == 9 || (_WORD)v7 == 12 )
      byte_180022034 = 1;
    byte_180022035 = 1;
  }
  if ( byte_180022034 )
    *a2 |= 0x100u;
  return 0;
}

```

## disassembly

```asm
0x18000e23c  mov     [rsp+arg_8], rbx
0x18000e241  mov     [rsp+arg_0], ecx
0x18000e245  push    rdi; int
0x18000e246  sub     rsp, 20h
0x18000e24a  mov     rbx, rdx
0x18000e24d  test    rdx, rdx
0x18000e250  jnz     short loc_18000E277
0x18000e252  mov     rcx, [rsp+28h]; this
0x18000e257  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18000e25e  mov     ebx, 80070057h
0x18000e263  mov     edx, 1B4h; void *
0x18000e268  mov     r9d, ebx; char *
0x18000e26b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e270  mov     eax, ebx
0x18000e272  jmp     loc_18000E30C
0x18000e277  cmp     cs:byte_180022035, 0
0x18000e27e  jnz     short loc_18000E2FD
0x18000e280  mov     eax, 0FFFFh
0x18000e285  mov     cs:byte_180022034, 0
0x18000e28c  lea     rcx, [rsp+28h+arg_0]; unsigned __int16 *
0x18000e291  mov     word ptr [rsp+28h+arg_0], ax
0x18000e296  call    ?GetProcessorArchitecture@@YAJPEAG@Z; GetProcessorArchitecture(ushort *)
0x18000e29b  mov     edi, eax
0x18000e29d  test    eax, eax
0x18000e29f  jns     short loc_18000E2D7
0x18000e2a1  mov     rcx, [rsp+28h]; this
0x18000e2a6  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e2ad  mov     r9d, eax; char *
0x18000e2b0  mov     edx, 0FCh; void *
0x18000e2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2ba  mov     rcx, [rsp+28h]; this
0x18000e2bf  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18000e2c6  mov     r9d, edi; char *
0x18000e2c9  mov     edx, 1C1h; void *
0x18000e2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2d3  mov     eax, edi
0x18000e2d5  jmp     short loc_18000E30C
0x18000e2d7  mov     eax, 9
0x18000e2dc  cmp     ax, word ptr [rsp+28h+arg_0]
0x18000e2e1  jz      short loc_18000E2EF
0x18000e2e3  mov     eax, 0Ch
0x18000e2e8  cmp     ax, word ptr [rsp+28h+arg_0]
0x18000e2ed  jnz     short loc_18000E2F6
0x18000e2ef  mov     cs:byte_180022034, 1
0x18000e2f6  mov     cs:byte_180022035, 1
0x18000e2fd  cmp     cs:byte_180022034, 0
0x18000e304  jz      short loc_18000E30A
0x18000e306  bts     dword ptr [rbx], 8
0x18000e30a  xor     eax, eax
0x18000e30c  mov     rbx, [rsp+28h+arg_8]
0x18000e311  add     rsp, 20h
0x18000e315  pop     rdi
0x18000e316  retn
```
