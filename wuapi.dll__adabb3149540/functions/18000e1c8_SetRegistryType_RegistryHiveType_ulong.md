# SetRegistryType(RegistryHiveType,ulong *)

- ea: `0x18000e1c8`
- end: `0x18000e2a3`
- name: `?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z`
- size: `219`
- prototype: `int __high(enum RegistryHiveType, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e33c`

## callees

- `0x180003760`
- `0x18000e1c8`
- `0x18000f53c`

## string_xrefs

- `0x18000e232`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

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
  if ( !byte_180022031 )
  {
    byte_180022030 = 0;
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
      byte_180022030 = 1;
    byte_180022031 = 1;
  }
  if ( byte_180022030 )
    *a2 |= 0x100u;
  return 0;
}

```

## disassembly

```asm
0x18000e1c8  mov     [rsp+arg_8], rbx
0x18000e1cd  mov     [rsp+arg_0], ecx
0x18000e1d1  push    rdi; int
0x18000e1d2  sub     rsp, 20h
0x18000e1d6  mov     rbx, rdx
0x18000e1d9  test    rdx, rdx
0x18000e1dc  jnz     short loc_18000E203
0x18000e1de  mov     rcx, [rsp+28h]; this
0x18000e1e3  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18000e1ea  mov     ebx, 80070057h
0x18000e1ef  mov     edx, 1B4h; void *
0x18000e1f4  mov     r9d, ebx; char *
0x18000e1f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1fc  mov     eax, ebx
0x18000e1fe  jmp     loc_18000E298
0x18000e203  cmp     cs:byte_180022031, 0
0x18000e20a  jnz     short loc_18000E289
0x18000e20c  mov     eax, 0FFFFh
0x18000e211  mov     cs:byte_180022030, 0
0x18000e218  lea     rcx, [rsp+28h+arg_0]; unsigned __int16 *
0x18000e21d  mov     word ptr [rsp+28h+arg_0], ax
0x18000e222  call    ?GetProcessorArchitecture@@YAJPEAG@Z; GetProcessorArchitecture(ushort *)
0x18000e227  mov     edi, eax
0x18000e229  test    eax, eax
0x18000e22b  jns     short loc_18000E263
0x18000e22d  mov     rcx, [rsp+28h]; this
0x18000e232  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e239  mov     r9d, eax; char *
0x18000e23c  mov     edx, 0FCh; void *
0x18000e241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e246  mov     rcx, [rsp+28h]; this
0x18000e24b  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\RegUti"...
0x18000e252  mov     r9d, edi; char *
0x18000e255  mov     edx, 1C1h; void *
0x18000e25a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e25f  mov     eax, edi
0x18000e261  jmp     short loc_18000E298
0x18000e263  mov     eax, 9
0x18000e268  cmp     ax, word ptr [rsp+28h+arg_0]
0x18000e26d  jz      short loc_18000E27B
0x18000e26f  mov     eax, 0Ch
0x18000e274  cmp     ax, word ptr [rsp+28h+arg_0]
0x18000e279  jnz     short loc_18000E282
0x18000e27b  mov     cs:byte_180022030, 1
0x18000e282  mov     cs:byte_180022031, 1
0x18000e289  cmp     cs:byte_180022030, 0
0x18000e290  jz      short loc_18000E296
0x18000e292  bts     dword ptr [rbx], 8
0x18000e296  xor     eax, eax
0x18000e298  mov     rbx, [rsp+28h+arg_8]
0x18000e29d  add     rsp, 20h
0x18000e2a1  pop     rdi
0x18000e2a2  retn
```
